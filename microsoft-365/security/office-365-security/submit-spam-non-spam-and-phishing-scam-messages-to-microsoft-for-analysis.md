---
title: Inviare manualmente i messaggi a Microsoft per l'analisi
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Gli amministratori e gli utenti finali possono imparare a inviare messaggi di posta elettronica (posta elettronica buona contrassegnata come posta non buona o non consentita) a Microsoft per l'analisi.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0a6f564d82750c5ab8156680854c2453cda6971
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206502"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Inviare manualmente i messaggi a Microsoft per l'analisi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata (posta indesiderata) o phishing nella posta in arrivo o se non ricevono un messaggio di posta elettronica legittimo perché è contrassegnato come posta indesiderata. Stiamo costantemente per ottimizzare i filtri per la posta indesiderata per essere più accurati.

L'utente e gli utenti possono contribuire a questo processo inviando falsi positivi (buona posta elettronica contrassegnata come non buona), falsi negativi (posta non consentita) e messaggi di phishing a Microsoft per l'analisi.

> [!NOTE]
> A causa dell'elevato volume di invii ricevuti, potrebbe non essere possibile rispondere a tutte le richieste di analisi.

## <a name="submit-false-negatives-to-microsoft"></a>Inviare falsi negativi a Microsoft

> [!TIP]
> Anziché utilizzare le procedure seguenti per segnalare falsi negativi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo Segnala messaggio o Segnala phishing. Per informazioni su come installare e utilizzare questi strumenti, vedere [Enable the Report Message add-in](enable-the-report-message-add-in.md) e Enable the Report Phishing [add-in.](enable-the-report-phish-add-in.md)

Se si riceve un messaggio che passa attraverso il filtro posta indesiderata che dovrebbe essere stato identificato come posta indesiderata o phishing, è possibile inviare il messaggio ai team di analisi della posta indesiderata Microsoft e analisi di phishing Microsoft in base alle esigenze. Gli analisti rivedranno il messaggio e lo aggiungeranno ai filtri a livello di servizio se soddisfano i criteri di classificazione.

1. Creare un nuovo messaggio di posta elettronica vuoto con uno dei seguenti destinatari:

   - **Posta indesiderata**: `junk@office365.microsoft.com`

   - **Phishing**: `phish@office365.microsoft.com`

2. Trascinare e rilasciare il messaggio di posta indesiderata o phishing nel nuovo messaggio. In questo modo il messaggio di posta indesiderata o phishing verrà salvato come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale in modo da poter esaminare le intestazioni del messaggio).

   > [!NOTE]
   >
   > - È possibile allegare più messaggi nel nuovo messaggio. Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di phishing o messaggi di posta indesiderata.
   >
   > - Lasciare vuoto il corpo del nuovo messaggio.
   >
   > - Utilizzare i formati .msg (formato predefinito di Outlook) o .eml (formato predefinito di Outlook sul Web) per i messaggi allegati.

3. Al termine, fare clic su **Invia**.

> [!TIP]
> Gli amministratori hanno diversi modi per bloccare messaggi specifici che vengono maldentificati come posta indesiderata. Per informazioni dettagliate, vedere [Create blocked sender lists in EOP.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Inviare falsi positivi a Microsoft

> [!TIP]
> Anziché utilizzare le procedure seguenti per segnalare falsi positivi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo Segnala messaggio o Segnala phishing. Per informazioni su come installare e utilizzare questi strumenti, vedere [Enable the Report Message add-in](enable-the-report-message-add-in.md) e Enable the Report Phishing [add-in.](enable-the-report-phish-add-in.md)


Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviarlo al team di analisi della posta indesiderata di Microsoft. Gli analisti valuteranno il messaggio e, a seconda dei risultati dell'analisi, i filtri a livello di servizio possono essere modificati per consentire l'invio del messaggio.

1. Creare un nuovo messaggio di posta elettronica vuoto con `not_junk@office365.microsoft.com` come destinatario:

2. Trascinare il messaggio non identificato nel nuovo messaggio. In questo modo il messaggio non identificato verrà salvato come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale in modo da poter esaminare le intestazioni del messaggio).

   > [!NOTE]
   >
   > - È possibile allegare più messaggi nel nuovo messaggio. Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di phishing o messaggi di posta indesiderata.
   >
   > - Lasciare vuoto il corpo del nuovo messaggio.
   >
   > - Utilizzare i formati .msg (formato predefinito di Outlook) o .eml (formato predefinito di Outlook sul Web) per i messaggi allegati.

3. Al termine, fare clic su **Invia**.

> [!TIP]
> Gli amministratori hanno diversi modi per consentire a messaggi specifici di ignorare il filtro posta indesiderata. Per informazioni dettagliate, vedere [Create safe sender lists in EOP.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Dove vengono archiviati i dati degli invii a Microsoft?

I dati si trovano nel limite di conformità di Office 365 nei data center nordamericani. I dati vengono esaminati dagli analisti del team di progettazione per migliorare l'efficacia dei filtri.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Creare una regola del flusso di posta per ricevere copie dei messaggi segnalati a Microsoft

Per istruzioni, vedere [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
