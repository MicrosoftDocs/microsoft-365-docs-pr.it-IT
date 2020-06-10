---
title: Configurare EOP per la posta indesiderata in ambienti ibridi
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a instradare la posta indesiderata alle cartelle posta indesiderata degli utenti in un ambiente ibrido di Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d8ba6aae599ee4dd327bd1ec82b46e8f3ee3ca8
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679121"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Configurare EOP autonomo per recapitare la posta indesiderata nella cartella posta indesiderata in ambienti ibridi

> [!IMPORTANT]
> Questo argomento è solo per i clienti di EOP autonomi in ambienti ibridi. Questo argomento non si applica ai clienti Microsoft 365 con cassette postali di Exchange Online.

Se si è un cliente autonomo di Exchange Online Protection (EOP) in un ambiente ibrido, è necessario configurare l'organizzazione di Exchange locale per riconoscere e tradurre i verdetti del filtro della posta indesiderata di EOP, in modo che la regola di posta indesiderata nella cassetta postale locale possa spostare i messaggi nella cartella posta indesiderata.

In particolare, è necessario creare regole del flusso di posta (note anche come regole di trasporto) nell'organizzazione di Exchange locale con condizioni che consentono di trovare messaggi con uno dei seguenti valori e intestazioni di protezione da posta indesiderata di EOP e le azioni che configurano il livello di probabilità di posta indesiderata (SCL) di tali messaggi su 6:

- `X-Forefront-Antispam-Report: SFV:SPM`(messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata)

- `X-Forefront-Antispam-Report: SFV:SKS`messaggio contrassegnato come posta indesiderata dalle regole del flusso di posta in EOP prima del filtro posta indesiderata

- `X-Forefront-Antispam-Report: SFV:SKB`(messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata a causa dell'indirizzo di posta elettronica o del dominio di posta elettronica del mittente nell'elenco dei mittenti bloccati o nell'elenco dei domini bloccati in EOP)

Per ulteriori informazioni su questi valori di intestazione, vedere intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md).

In questo argomento viene descritto come creare queste regole del flusso di posta dell'interfaccia di amministrazione di Exchange (EAC) e in Exchange Management Shell (Exchange PowerShell) nell'organizzazione di Exchange locale.

> [!TIP]
> Invece di inviare i messaggi alla cartella posta indesiderata dell'utente locale, è possibile configurare i criteri di protezione dalla posta indesiderata in EOP per la quarantena dei messaggi di posta indesiderata in EOP. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni nell'ambiente di Exchange locale. In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita. Per ulteriori informazioni, vedere [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).

- Se e quando un messaggio viene recapitato nella cartella posta indesiderata in un'organizzazione di Exchange locale, è controllato da una combinazione delle seguenti impostazioni:

  - Il valore del parametro _SCLJunkThreshold_ nel cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in Exchange Management Shell. Il valore predefinito è 4, il che significa che un SCL di 5 o superiore deve recapitare il messaggio alla cartella posta indesiderata dell'utente.

  - Il valore del parametro _SCLJunkThreshold_ nel cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in Exchange Management Shell. Il valore predefinito è vuoto ($null), che indica che viene utilizzata l'impostazione dell'organizzazione.

  Per ulteriori informazioni, vedere [soglie del livello di probabilità di posta indesiderata (SCL) di Exchange](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Se la regola di posta indesiderata è abilitata per la cassetta postale (il valore del parametro _Enabled_ è $true sul cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in Exchange Management Shell). È la regola di posta indesiderata che in realtà sposta il messaggio nella cartella posta indesiderata dopo il recapito. Per impostazione predefinita, la regola di posta indesiderata è abilitata sulle cassette postali. Per ulteriori informazioni, vedere [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).
  
- Per aprire EAC su un server Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Per aprire Exchange Management Shell, vedere [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange locale, vedere i seguenti argomenti:

  - [Regole del flusso di posta in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Azioni delle regole del flusso di posta in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Utilizzare EAC per creare regole del flusso di posta che configurano il SCL dei messaggi di posta indesiderata di EOP

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e selezionare **Crea una nuova regola** nell'elenco a discesa che viene visualizzato.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per la regola. Ad esempio:

     - EOP SFV: SPM a SCL 6

     - EOP SFV: SKS to SCL 6

     - EOP SFV: SKB to SCL 6

   - Fare clic su **altre opzioni**.

   - **Applica questa regola se**: selezionare **un'intestazione** \> **del messaggio include una di queste parole**.

     Nell' **intestazione Enter Text è inclusa l'indicazione Enter Words** , che viene visualizzata, eseguire le operazioni seguenti:

     - Fare clic su **Immetti testo**. Nella finestra di dialogo **Specifica nome intestazione** che viene visualizzata, immettere **X-Forefront-antispam-report** e quindi fare clic su **OK**.

     - Fare clic su **Immetti parole**. Nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori delle intestazioni di posta indesiderata di EOP (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**), fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi fare clic su **OK**.

   - **Eseguire le operazioni seguenti**: selezionare **modifica le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)**.

     Nella finestra di dialogo **specifica SCL** visualizzata, selezionare **6** (il valore predefinito è **5**).

   Al termine, fare clic su **Salva**

Ripetere questi passaggi per i valori del verdetto di posta indesiderata EOP rimanenti (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Utilizzare Exchange Management Shell per creare regole del flusso di posta che configurano il livello SCL dei messaggi di posta indesiderata di EOP

Per creare le tre regole del flusso di posta, utilizzare la sintassi seguente:

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

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta configurazione di EOP autonomo per recapitare la posta indesiderata alla cartella posta indesiderata in ambiente ibrido, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \> **Rules**, selezionare la regola, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) per verificare le impostazioni.

- In Exchange Management Shell, sostituire \<RuleName\> con il nome della regola del flusso di posta e RUL il comando seguente per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- In un sistema di posta elettronica esterno **che non esegue l'analisi dei messaggi in uscita per la posta indesiderata**, inviare un test generico per il messaggio di posta elettronica indesiderata (GTUBE) a un destinatario coinvolto e verificare che sia recapitato nella cartella posta indesiderata. Un messaggio GTUBE è simile al file di testo EICAR (European Institute for Computer Antivirus Research) per la verifica delle impostazioni antimalware.

  Per inviare un messaggio di GTUBE, includere il testo seguente nel corpo di un messaggio di posta elettronica su una singola riga, senza spazi o interruzioni di riga:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
