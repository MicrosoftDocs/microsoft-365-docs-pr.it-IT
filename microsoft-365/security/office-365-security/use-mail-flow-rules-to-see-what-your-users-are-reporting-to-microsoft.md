---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come utilizzare le regole del flusso di posta (note anche come regole di trasporto) per ricevere le copie dei messaggi che gli utenti segnalano a Microsoft.
ms.openlocfilehash: 9798e808470a506da3d6dff65a5ea91934c1690d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195868"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, esistono diversi modi per consentire agli utenti di segnalare i messaggi a Microsoft per l'analisi, come descritto in [messaggi e file di report a Microsoft](report-junk-email-messages-to-microsoft.md).

È possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che consente di cercare i messaggi che gli utenti riferiscono a Microsoft ed è possibile configurare i destinatari Ccn in modo che ricevano copie dei messaggi segnalati.

È possibile creare la regola del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online, standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online o EOP. In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita. Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Per aprire EAC, vedere interfaccia di amministrazione di Exchange [in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:

  - [Regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Azioni delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare **Crea una nuova regola**.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per la regola. Ad esempio, i messaggi Ccn segnalati a Microsoft.

   - Fare clic su **altre opzioni**.

   - **Applica questa regola se**: selezionare **l'indirizzo del destinatario** \> **include una**o più delle seguenti parole: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e ripetere fino a quando non sono stati immessi tutti i valori.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Per modificare una voce, selezionarla e fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) . Per rimuovere una voce, selezionarla e fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-DeleteIcon.png) .

     Al termine, fare clic su **OK**.

   - **Eseguire le operazioni seguenti**: selezionare **Aggiungi destinatari** \> **alla casella Ccn**. Nella finestra di dialogo che viene visualizzata, individuare e selezionare i destinatari che si desidera aggiungere. Al termine, fare clic su **OK**.

4. È possibile effettuare selezioni aggiuntive per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre impostazioni. È consigliabile testare la regola prima di applicarla.

5. Al termine, scegliere **Salva**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Utilizzo di PowerShell per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati

In questo esempio viene creata una nuova regola del flusso di posta denominata Ccn messaggi segnalati a Microsoft che consente di cercare i messaggi di posta elettronica segnalati a Microsoft tramite i metodi descritti in questo argomento e di aggiungere gli utenti laura@contoso.com e julia@contoso.com come destinatari Ccn.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver configurato le regole del flusso di posta elettronica per ricevere le copie dei messaggi segnalati, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \> **Rules** \> selezionare la regola \> fare clic su **Modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) e verificare le impostazioni.

- In PowerShell, eseguire il comando riportato di seguito per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Inviare un messaggio di prova a uno degli indirizzi di posta elettronica per la creazione di report e verificare i risultati.
