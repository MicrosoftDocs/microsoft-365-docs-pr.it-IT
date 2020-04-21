---
title: Inviare manualmente messaggi a Microsoft per l'analisi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: "Gli utenti possono inviare messaggi di posta indesiderata falsi negativi e falsi positivi a Microsoft per l'analisi. "
ms.openlocfilehash: f6dbd808fac54ae273c21773bf8caeabce09b7fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631242"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Inviare manualmente messaggi a Microsoft per l'analisi

> [!NOTE]
> Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).

Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata o messaggi di phishing nella cartella posta in arrivo o se non ricevono un messaggio di posta elettronica legittimo perché sono contrassegnati come posta indesiderata. La correzione dei filtri per la posta indesiderata è sempre più accurata.

L'utente e gli utenti possono aiutare questo processo inviando falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo), falsi negativi (posta errata consentita) e messaggi di phishing a Microsoft per l'analisi.

> [!NOTE]
> A causa dell'elevato volume di invii ricevuti, potrebbe non essere possibile rispondere a tutte le richieste di analisi.

## <a name="submit-false-negatives-to-microsoft"></a>Inviare falsi negativi a Microsoft

> [!TIP]
> Invece di utilizzare le procedure seguenti per segnalare falsi negativi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook. Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).

Se si riceve un messaggio che passa attraverso il filtro di posta indesiderata che dovrebbe essere stato identificato come posta indesiderata o phishing, è possibile inviare il messaggio ai team di analisi di posta indesiderata di Microsoft e Microsoft Phishing Analysis come appropriato. Gli analisti rivedranno il messaggio e lo aggiungeranno ai filtri a livello di servizio, se soddisfano i criteri di classificazione.

1. Creare un nuovo messaggio di posta elettronica vuoto con uno dei destinatari seguenti:

   - **Posta indesiderata**:`junk@office365.microsoft.com`

   - **Phishing**:`phish@office365.microsoft.com`

2. Trascinare e rilasciare il messaggio di posta indesiderata o di phishing nel nuovo messaggio. In questo modo verrà salvato il messaggio di posta indesiderata o di phishing come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).

   > [!NOTE]
   > <ul><li>È possibile allegare più messaggi nel nuovo messaggio. Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di truffa di phishing o messaggi di posta indesiderata.</li><li>Lasciare vuoto il corpo del nuovo messaggio.</li><li>Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.</li></ul>

3. Al termine, fare clic su **Invia**.

> [!TIP]
> Gli amministratori dispongono di diversi modi per bloccare messaggi specifici che vengono erroneamente identificati come posta indesiderata. Per ulteriori informazioni, vedere [creare elenchi di mittenti bloccati in Office 365](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Inviare falsi positivi a Microsoft

> [!TIP]
> Invece di utilizzare le procedure seguenti per segnalare falsi positivi, gli utenti di Outlook e Outlook sul Web possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook. Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).

Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviare il messaggio al team di analisi di posta indesiderata di Microsoft. Gli analisti valuteranno il messaggio e (a seconda dei risultati dell'analisi), i filtri a livello di servizio possono essere modificati in modo da consentire il passaggio del messaggio.

1. Creare un nuovo messaggio di posta elettronica vuoto `not_junk@office365.microsoft.com` come destinatario:

2. Trascinare e rilasciare il messaggio erroneamente identificato nel nuovo messaggio. In questo modo verrà salvato il messaggio erroneamente identificato come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).

   > [!NOTE]
   > <ul><li>È possibile allegare più messaggi nel nuovo messaggio. Verificare che tutti i messaggi siano dello stesso tipo, ovvero messaggi di phishing o messaggi di posta indesiderata.</li><li>Lasciare vuoto il corpo del nuovo messaggio.</li><li>Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.</li></ul>

3. Al termine, fare clic su **Invia**.

> [!TIP]
> Gli amministratori dispongono di diversi modi per consentire ai messaggi specifici di ignorare il filtro posta indesiderata. Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Creare una regola del flusso di posta elettronica per ricevere le copie dei messaggi segnalati a Microsoft

È possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che consente di cercare i messaggi di posta elettronica segnalati a Microsoft utilizzando i metodi descritti in questo argomento ed è possibile configurare i destinatari Ccn in modo che ricevano le copie dei messaggi segnalati.

È possibile creare la regola del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell (Exchange Online PowerShell per i clienti di Microsoft 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online. In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita. Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell per Exchange Online Protection autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:

  - [Regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Azioni delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare **Add** ![clic su Aggiungi](../../media/ITPro-EAC-AddIcon.png) icona e quindi selezionare **Crea una nuova regola**.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per la regola. Ad esempio, i messaggi Ccn segnalati a Microsoft.

   - Fare clic su **altre opzioni**.

   - **Applica questa regola se**: selezionare **l'indirizzo del destinatario** \> **include una**o più delle seguenti parole: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic](../../media/ITPro-EAC-AddIcon.png)su **Aggiungi** ![icona e ripetere fino a quando non sono stati immessi tutti i valori.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Per modificare una voce, selezionarla e fare **Edit** ![clic su modifica](../../media/ITPro-EAC-EditIcon.png)icona modifica. Per rimuovere una voce, selezionarla e fare **Remove** ![clic su Rimuovi](../../media/ITPro-EAC-DeleteIcon.png)icona Rimuovi.

     Al termine, fare clic su **OK**.

   - **Eseguire le operazioni seguenti**: selezionare **Aggiungi destinatari** \> **alla casella Ccn**. Nella finestra di dialogo che viene visualizzata, individuare e selezionare i destinatari che si desidera aggiungere. Al termine, fare clic su **OK**.

4. È possibile effettuare selezioni aggiuntive per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre impostazioni. È consigliabile testare la regola prima di applicarla.

5. Al termine, scegliere **Salva**.

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Utilizzo di PowerShell per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati

In questo esempio viene creata una nuova regola del flusso di posta denominata Ccn messaggi segnalati a Microsoft che consente di cercare i messaggi di posta elettronica segnalati a Microsoft tramite i metodi descritti in questo argomento e di aggiungere gli utenti laura@contoso.com e julia@contoso.com come destinatari Ccn.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver configurato le regole del flusso di posta elettronica per ricevere le copie dei messaggi segnalati, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a **regole** \> del **flusso** \> di **Edit** ![posta selezionare la](../../media/ITPro-EAC-EditIcon.png)regola \> fare clic su Modifica icona modifica e verificare le impostazioni.

- In PowerShell, eseguire il comando riportato di seguito per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Inviare un messaggio di prova a uno degli indirizzi di posta elettronica per la creazione di report e verificare i risultati.
