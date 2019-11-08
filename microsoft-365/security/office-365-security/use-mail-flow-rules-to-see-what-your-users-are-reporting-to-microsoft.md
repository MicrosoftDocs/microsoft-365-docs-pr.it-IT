---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: È possibile creare una regola del flusso di posta di Exchange per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza
ms.openlocfilehash: d1b67d60d10ea9ce5d3ed47e20959c85d785e437
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030640"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft

Sono disponibili differenti modalità per inviare messaggi falsi positivi e falsi negativi a Microsoft per l'analisi. Come amministratore, è possibile utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft su posta indesiderata, non indesiderata e tentativi di phishing. Per ulteriori informazioni, vedere [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Al contrario, è possibile creare una regola del flusso di posta di Exchange (nota anche come regola di trasporto) per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento: 5 minuti

Devi disporre delle autorizzazioni per poter eseguire queste procedure.  Per sapere quali autorizzazioni sono necessarie, vedere la voce "regole del flusso di posta" nell'argomento [criteri di messaggistica e autorizzazioni di conformità](https://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) e "criteri cassetta postale di Outlook sul Web" nell'argomento [autorizzazioni per client e dispositivi mobili](https://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) .

Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Utilizzare l'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per visualizzare report manuali dell'utente su posta indesiderata, phishing e posta non indesiderata.

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.

2. Fare clic su ![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.

3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.

4. In **Applica questa regola se**, selezionare **Il destinatario** e scegliere **l'indirizzo include una di queste parole**.

5. Nella casella **specifica parole o frasi** eseguire le operazioni seguenti:

   - Digitare `abuse@messaging.microsoft.com`, fare **** ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif)icona, `junk@office365.microsoft.com` digitare e quindi fare clic su](../media/ITPro-EAC-AddIcon.gif) **Aggiungi** ![icona Aggiungi. Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi negativi falsi a Microsoft.

   - Digitare `phish@office365.microsoft.com` e quindi fare **** ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif)icona. Questo indirizzo di posta elettronica viene utilizzato per inviare messaggi di phishing non letti a Microsoft.

   - Digitare `false_positive@messaging.microsoft.com`, fare **** ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif)icona, `not_junk@office365.microsoft.com`digitare e quindi fare clic su **Aggiungi** ![icona](../media/ITPro-EAC-AddIcon.gif)Aggiungi. Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi positivi a Microsoft.

   - Fare clic su **OK**.

6. In **Eseguire le operazioni seguenti** selezionare **Invia il messaggio in Ccn a...**, quindi selezionare le cassette postali in cui si desidera ricevere i messaggi.

7. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. Vedere [procedure per le regole del flusso di posta](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).

8. Fare clic sul pulsante **salva** per salvare la regola. Viene visualizzata nell'elenco delle regole.

Dopo aver creato e impostato la regola, eventuali messaggi inviati dall'organizzazione agli indirizzi di posta elettronica specificati verranno copiati alla cassetta postale specificata.
