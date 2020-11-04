---
title: Inviare manualmente messaggi a Microsoft per l'analisi
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Gli amministratori e gli utenti finali possono imparare a inviare messaggi di posta elettronica (buona posta contrassegnata come cattiva o cattiva posta elettronica consentita) a Microsoft per l'analisi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68a0921f85e5b916cd53ebe84e4ea7d35e39967e
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877706"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Inviare manualmente messaggi a Microsoft per l'analisi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale degli invii nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).

Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata o messaggi di phishing nella cartella posta in arrivo o se non ricevono un messaggio di posta elettronica legittimo perché sono contrassegnati come posta indesiderata. La correzione dei filtri per la posta indesiderata è sempre più accurata.

L'utente e gli utenti possono aiutare questo processo inviando falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo), falsi negativi (posta errata consentita) e messaggi di phishing a Microsoft per l'analisi.

> [!NOTE]
> A causa dell'elevato volume di invii ricevuti, potrebbe non essere possibile rispondere a tutte le richieste di analisi.

## <a name="submit-false-negatives-to-microsoft"></a>Inviare falsi negativi a Microsoft

> [!TIP]
> Invece di utilizzare le procedure seguenti per segnalare falsi negativi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook. Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).

Se si riceve un messaggio che passa attraverso il filtro di posta indesiderata che dovrebbe essere stato identificato come posta indesiderata o phishing, è possibile inviare il messaggio ai team di analisi di posta indesiderata di Microsoft e Microsoft Phishing Analysis come appropriato. Gli analisti rivedranno il messaggio e lo aggiungeranno ai filtri a livello di servizio, se soddisfano i criteri di classificazione.

1. Creare un nuovo messaggio di posta elettronica vuoto con uno dei destinatari seguenti:

   - **Posta indesiderata** : `junk@office365.microsoft.com`

   - **Phishing** : `phish@office365.microsoft.com`

2. Trascinare e rilasciare il messaggio di posta indesiderata o di phishing nel nuovo messaggio. In questo modo verrà salvato il messaggio di posta indesiderata o di phishing come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).

   > [!NOTE]
   >
   > - È possibile allegare più messaggi nel nuovo messaggio. Verificare che tutti i messaggi siano dello stesso tipo, ovvero messaggi di phishing o messaggi di posta indesiderata.
   >
   > - Lasciare vuoto il corpo del nuovo messaggio.
   >
   > - Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.

3. Al termine, fare clic su **Invia**.

> [!TIP]
> Gli amministratori dispongono di diversi modi per bloccare messaggi specifici che vengono erroneamente identificati come posta indesiderata. Per ulteriori informazioni, vedere [creare elenchi di mittenti bloccati in EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Inviare falsi positivi a Microsoft

> [!TIP]
> Invece di utilizzare le procedure seguenti per segnalare falsi positivi, gli utenti di Outlook e Outlook sul Web possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook. Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).

Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviare il messaggio al team di analisi di posta indesiderata di Microsoft. Gli analisti valuteranno il messaggio e (a seconda dei risultati dell'analisi), i filtri a livello di servizio possono essere modificati in modo da consentire il passaggio del messaggio.

1. Creare un nuovo messaggio di posta elettronica vuoto `not_junk@office365.microsoft.com` come destinatario:

2. Trascinare e rilasciare il messaggio erroneamente identificato nel nuovo messaggio. In questo modo verrà salvato il messaggio erroneamente identificato come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).

   > [!NOTE]
   >
   > - È possibile allegare più messaggi nel nuovo messaggio. Verificare che tutti i messaggi siano dello stesso tipo, ovvero messaggi di phishing o messaggi di posta indesiderata.
   >
   > - Lasciare vuoto il corpo del nuovo messaggio.
   >
   > - Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.

3. Al termine, fare clic su **Invia**.

> [!TIP]
> Gli amministratori dispongono di diversi modi per consentire ai messaggi specifici di ignorare il filtro posta indesiderata. Per informazioni dettagliate, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Creare una regola del flusso di posta elettronica per ricevere le copie dei messaggi segnalati a Microsoft

Per istruzioni, vedere [utilizzo delle regole del flusso di posta per vedere cosa gli utenti stanno segnalando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
