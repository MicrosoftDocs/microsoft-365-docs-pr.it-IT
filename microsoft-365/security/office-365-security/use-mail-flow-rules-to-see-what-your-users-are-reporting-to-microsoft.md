---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a usare le regole del flusso di posta (note anche come regole di trasporto) per ricevere copie dei messaggi che gli utenti segnalano a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206097"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, esistono diversi modi per segnalare i messaggi a Microsoft per l'analisi, come descritto in Segnalare messaggi e file a [Microsoft](report-junk-email-messages-to-microsoft.md).

È possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che cerca i messaggi che gli utenti segnalano a Microsoft ed è possibile configurare i destinatari Ccn per ricevere copie di questi messaggi segnalati.

È possibile creare la regola del flusso di posta nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online o Exchange Online Protection. In particolare, è necessario il ruolo **Regole** di trasporto, assegnato ai gruppi  di ruoli **Gestione** **organizzazione,** Gestione conformità (amministratori globali) e Gestione record per impostazione predefinita.

  Per ulteriori informazioni, vedere i seguenti argomenti:

  - [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Autorizzazioni in Exchange Online Protection autonomo](feature-permissions-in-eop.md)
  - [Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per aprire l'interfaccia di amministrazione di Exchange in Exchange Online, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/Exchange/exchange-admin-center) Per aprire l'interfaccia di amministrazione di Exchange in EOP autonomo, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e in EOP autonomo, vedere i seguenti argomenti:
  - [Regole del flusso di posta (regole di trasporto) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Azioni delle regole del flusso di posta in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per ricevere copie dei messaggi segnalati

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare **clic su** Aggiungi Icona Aggiungi e quindi selezionare Crea una nuova ![ ](../../media/ITPro-EAC-AddIcon.png) **regola.**

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome descrittivo univoco per la regola. Ad esempio, Ccn Messaggi segnalati a Microsoft.

   - Fare **clic su Altre opzioni.**

   - Applica questa regola  **se**: Selezionare L'indirizzo del destinatario include una delle seguenti parole: nella finestra di dialogo Specifica parole o frasi visualizzata immettere uno dei valori seguenti, fare clic su Aggiungi icona Aggiungi e ripetere \>    ![ l'operazione fino a quando non sono stati immessi tutti i ](../../media/ITPro-EAC-AddIcon.png) valori.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Per modificare una voce, selezionarla e fare clic **su Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica. Per rimuovere una voce, selezionarla e fare clic **su Rimuovi** ![ Icona ](../../media/ITPro-EAC-DeleteIcon.png) Rimuovi.

     Al termine, fare clic su **OK**.

   - **Eseguire le operazioni seguenti:** Selezionare **Aggiungi** \> **destinatari alla casella Ccn**. Nella finestra di dialogo visualizzata individuare e selezionare i destinatari che si desidera aggiungere. Al termine, fare clic su **OK**.

4. È possibile effettuare ulteriori selezioni per controllare la regola, testarla, attivare la regola in un periodo di tempo specifico e altre impostazioni. È consigliabile testare la regola prima di applicarla.

5. Al termine, scegliere **Salva**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Utilizzare PowerShell per creare una regola del flusso di posta per ricevere copie dei messaggi segnalati

In questo esempio viene creata una nuova regola del flusso di posta denominata Ccn Messaggi segnalati a Microsoft che cerca i messaggi di posta elettronica segnalati a Microsoft utilizzando i metodi descritti in questo articolo e aggiunge gli utenti laura@contoso.com e julia@contoso.com come destinatari Ccn.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver configurato regole del flusso di posta per ricevere copie dei messaggi segnalati, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta Regole selezionare la regola fare clic \>  \> su \> **Modifica** Icona Modifica e verificare ![ le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.

- In PowerShell, eseguire il comando seguente per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Inviare messaggi di prova a uno degli indirizzi di posta elettronica di segnalazione e verificare i risultati.