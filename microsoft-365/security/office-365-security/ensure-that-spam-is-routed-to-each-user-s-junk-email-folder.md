---
title: Configurare EOP per la posta indesiderata in ambienti ibridi
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a instradare la posta indesiderata alle cartelle posta indesiderata dell'utente in un ambiente ibrido di Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205520"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Configurare EOP autonomo per recapitare posta indesiderata alla cartella Posta indesiderata in ambienti ibridi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

> [!IMPORTANT]
> Questo argomento è disponibile solo per i clienti EOP autonomi in ambienti ibridi. Questo argomento non si applica ai clienti di Microsoft 365 con cassette postali di Exchange Online.

Se si è un cliente autonomo di Exchange Online Protection (EOP) in un ambiente ibrido, è necessario configurare l'organizzazione di Exchange locale per riconoscere e tradurre i verdetti del filtro posta indesiderata di EOP, in modo che la regola di posta indesiderata nella cassetta postale locale possa spostare i messaggi nella cartella Posta indesiderata.

In particolare, è necessario creare regole del flusso di posta (note anche come regole di trasporto) nell'organizzazione exchange locale con condizioni che trovano i messaggi con una delle intestazioni e valori di protezione da posta indesiderata EOP seguenti e azioni che impostano il livello di probabilità di posta indesiderata (SCL) di tali messaggi su 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata)

- `X-Forefront-Antispam-Report: SFV:SKS` (messaggio contrassegnato come posta indesiderata dalle regole del flusso di posta in EOP prima del filtro posta indesiderata)

- `X-Forefront-Antispam-Report: SFV:SKB` (messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata a causa dell'indirizzo di posta elettronica o del dominio di posta elettronica del mittente nell'elenco dei mittenti bloccati o nell'elenco dei domini bloccati in EOP)

Per ulteriori informazioni su questi valori di intestazione, vedere [Intestazioni dei](anti-spam-message-headers.md)messaggi di posta indesiderata .

In questo argomento viene descritto come creare queste regole del flusso di posta nell'interfaccia di amministrazione di Exchange (EAC) e in Exchange Management Shell (Exchange PowerShell) nell'organizzazione di Exchange locale.

> [!TIP]
> Anziché recapitare i messaggi nella cartella Posta indesiderata dell'utente locale, è possibile configurare i criteri di protezione da posta indesiderata in EOP per mettere in quarantena i messaggi di posta indesiderata in EOP. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni nell'ambiente Exchange locale. In particolare, è necessario  essere assegnati al ruolo Regole di trasporto, assegnato ai ruoli **Gestione** **organizzazione,** Gestione conformità e **Gestione** record per impostazione predefinita. Per ulteriori informazioni, vedere [Add members to a role group](/Exchange/permissions/role-group-members#add-members-to-a-role-group).

- Se e quando un messaggio viene recapitato nella cartella Posta indesiderata in un'organizzazione exchange locale è controllato da una combinazione delle impostazioni seguenti:

  - Valore _del parametro SCLJunkThreshold_ nel cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) in Exchange Management Shell. Il valore predefinito è 4, ovvero un livello di probabilità di posta indesiderata pari o superiore a 5 deve recapitare il messaggio nella cartella Posta indesiderata dell'utente.

  - Il _valore del parametro SCLJunkThreshold nel_ cmdlet [Set-Mailbox](/powershell/module/exchange/set-mailbox) in Exchange Management Shell. Il valore predefinito è vuoto ($null), ovvero viene utilizzata l'impostazione dell'organizzazione.

  Per informazioni dettagliate, vedere [Exchange spam confidence level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Indica se la regola di posta indesiderata è abilitata nella cassetta postale (il valore del parametro _Enabled_ è $true nel cmdlet [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) in Exchange Management Shell). È la regola di posta indesiderata che sposta effettivamente il messaggio nella cartella Posta indesiderata dopo il recapito. Per impostazione predefinita, la regola di posta indesiderata è abilitata nelle cassette postali. Per ulteriori informazioni, vedere [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Per aprire l'interfaccia di amministrazione di Exchange in Exchange Server, vedere Interfaccia di amministrazione [di Exchange in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center). Per aprire Exchange Management Shell, vedere [Aprire Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange locale, vedere i seguenti argomenti:

  - [Regole del flusso di posta Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condizioni ed eccezioni delle regole del flusso di posta (predicati) in Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Azioni delle regole del flusso di posta Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare regole del flusso di posta che impostano il livello di probabilità di posta indesiderata dei messaggi di posta indesiderata di EOP

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare **clic** ![ su Aggiungi Icona Aggiungi e selezionare Crea una ](../../media/ITPro-EAC-AddIcon.png) **nuova** regola nell'elenco a discesa visualizzato.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome descrittivo univoco per la regola. Ad esempio:

     - EOP SFV:SPM a SCL 6

     - EOP SFV:SKS a SCL 6

     - EOP SFV:SKB a SCL 6

   - Fare **clic su Altre opzioni.**

   - **Applica questa regola se**: Selezionare **Un'intestazione del** messaggio include una di queste \> **parole.**

     **Nell'intestazione Immettere testo include la frase** Immettere parole che viene visualizzata, eseguire la procedura seguente:

     - Fare **clic su Immetti testo.** Nella finestra **di dialogo Specifica nome** intestazione visualizzata immettere **X-Forefront-Antispam-Report** e quindi fare clic su **OK.**

     - Fare **clic su Immetti parole.** Nella  finestra di dialogo Specifica parole o frasi visualizzata immettere uno dei valori di intestazione della posta indesiderata EOP (  **SFV:SPM,** **SFV:SKS** o **SFV:SKB**), fare clic su Aggiungi Icona Aggiungi e quindi su ![ ](../../media/ITPro-EAC-AddIcon.png) **OK**.

   - **Eseguire le operazioni seguenti:** Selezionare **Modifica le proprietà del messaggio** Impostare il livello di probabilità di posta indesiderata \> **(SCL).**

     Nella finestra **di dialogo Specifica SCL** visualizzata selezionare **6** (il valore predefinito è **5**).

   Al termine, fare clic su **Salva**

Ripetere questi passaggi per i restanti valori di verdetto della posta indesiderata EOP (**SFV:SPM,** **SFV:SKS** o **SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Utilizzo di Exchange Management Shell per creare regole del flusso di posta che impostano il livello di probabilità di posta indesiderata di EOP

Utilizzare la sintassi seguente per creare le tre regole del flusso di posta:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Ad esempio:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta configurazione di EOP autonomo per il recapito della posta indesiderata nella cartella Posta indesiderata nell'ambiente ibrido, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta Regole, selezionare la regola e quindi fare \> clic **su Modifica** Icona Modifica per verificare ![ le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.

- In Exchange Management Shell, sostituire con il nome della regola del flusso di posta e utilizzare il comando seguente \<RuleName\> per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- In un sistema di posta elettronica esterno che non analizza i messaggi in uscita alla ricerca di posta **indesiderata,** inviare un messaggio GTUBE (Generic Test for Unsolicited Bulk Email) a un destinatario interessato e verificare che sia recapitato nella cartella Posta indesiderata. Un messaggio GTUBE è simile al file di testo EICAR (European Institute for Computer Antivirus Research) per la verifica delle impostazioni antimalware.

  Per inviare un messaggio GTUBE, includere il testo seguente nel corpo di un messaggio di posta elettronica su una singola riga, senza spazi o interruzioni di riga:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```