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
description: Gli amministratori e gli utenti finali possono imparare a inviare messaggi di posta elettronica (posta buona contrassegnata come posta non buona o non consentita) a Microsoft per l'analisi.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98964d17c41222fa708bdf0059c0e67151582ef1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290370"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Inviare manualmente i messaggi a Microsoft per l'analisi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, si consiglia di utilizzare il portale Invii nel Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft.](admin-submission.md)

Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata (posta indesiderata) o phishing nella posta in arrivo oppure se non ricevono un messaggio di posta elettronica legittimo perché è contrassegnato come posta indesiderata. We're constantly fine-tuning our spam filters to be more accurate.

You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.

> [!NOTE]
> A causa dell'elevato volume di invii ricevuti, potremmo non essere in grado di rispondere a tutte le richieste di analisi.

## <a name="submit-false-negatives-to-microsoft"></a>Inviare falsi negativi a Microsoft

> [!TIP]
> Anziché utilizzare le procedure seguenti per segnalare falsi negativi, gli utenti di Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo Segnala messaggio o Segnala phishing. Per informazioni su come installare e utilizzare questi strumenti, vedere [Abilitare](enable-the-report-message-add-in.md) il componente aggiuntivo Segnala messaggio e Abilitare il componente aggiuntivo [Segnala phishing.](enable-the-report-phish-add-in.md)

Se si riceve un messaggio che ha superato il filtro di protezione da posta indesiderata che dovrebbe essere stato identificato come posta indesiderata o phishing, è possibile inviare il messaggio ai team di analisi della posta indesiderata di Microsoft e analisi di phishing Microsoft in base alle esigenze. Gli analisti esaminano il messaggio e lo aggiungono ai filtri a livello di servizio se soddisfano i criteri di classificazione.

1. Creare un nuovo messaggio di posta elettronica vuoto con uno dei seguenti destinatari:

   - **Posta indesiderata:**`junk@office365.microsoft.com`

   - **Phishing:**`phish@office365.microsoft.com`

2. Trascinare e rilasciare il messaggio di posta indesiderata o phishing nel nuovo messaggio. In questo modo il messaggio di posta indesiderata o di phishing verrà salvato come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale in modo da poter esaminare le intestazioni del messaggio).

   > [!NOTE]
   >
   > - È possibile allegare più messaggi nel nuovo messaggio. Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di phishing o messaggi di posta indesiderata.
   >
   > - Lasciare vuoto il corpo del nuovo messaggio.
   >
   > - Utilizzare i formati .msg (formato predefinito di Outlook) o .eml (formato predefinito di Outlook sul Web) per i messaggi allegati.

3. Al termine, fare clic su **Invia.**

> [!TIP]
> Gli amministratori hanno diversi modi per bloccare messaggi specifici non identificati come posta indesiderata. Per informazioni dettagliate, vedere [Creare elenchi di mittenti bloccati in EOP.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Inviare falsi positivi a Microsoft

> [!TIP]
> Anziché utilizzare le procedure seguenti per segnalare falsi positivi, gli utenti di Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo Segnala messaggio o Segnala phishing. Per informazioni su come installare e utilizzare questi strumenti, vedere [Abilitare](enable-the-report-message-add-in.md) il componente aggiuntivo Segnala messaggio e Abilitare il componente aggiuntivo [Segnala phishing.](enable-the-report-phish-add-in.md)


Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviarlo al team di analisi della posta indesiderata di Microsoft. Gli analisti valuteranno il messaggio e, a seconda dei risultati dell'analisi, i filtri a livello di servizio possono essere modificati per consentire l'invio del messaggio.

1. Creare un nuovo messaggio di posta elettronica vuoto con `not_junk@office365.microsoft.com` il destinatario:

2. Trascinare e rilasciare il messaggio non identificato nel nuovo messaggio. In questo modo il messaggio non identificato verrà salvato come allegato nel nuovo messaggio. Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale in modo da poter esaminare le intestazioni del messaggio).

   > [!NOTE]
   >
   > - È possibile allegare più messaggi nel nuovo messaggio. Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di phishing o messaggi di posta indesiderata.
   >
   > - Lasciare vuoto il corpo del nuovo messaggio.
   >
   > - Utilizzare i formati .msg (formato predefinito di Outlook) o .eml (formato predefinito di Outlook sul Web) per i messaggi allegati.

3. Al termine, fare clic su **Invia.**

> [!TIP]
> Gli amministratori hanno diversi modi per consentire a messaggi specifici di ignorare il filtro posta indesiderata. Per informazioni dettagliate, vedere [Creare elenchi di mittenti attendibili in EOP.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Dove vengono archiviati i dati degli invii a Microsoft?

I dati risiedono nel limite di conformità di Office 365 nei data center del Nord America. I dati vengono esaminati dagli analisti del team di progettazione per migliorare l'efficacia dei filtri.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Creare una regola del flusso di posta per ricevere copie dei messaggi segnalati a Microsoft

Per istruzioni, vedere [Usare le regole del flusso di posta per vedere cosa segnalano gli](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)utenti a Microsoft.
