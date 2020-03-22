---
title: Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
ms.openlocfilehash: 27e0698d1ad7d05adfa69e18e9b5b21edb74b1eb
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893647"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>Inviare messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi

Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata o messaggi di phishing nella cartella posta in arrivo o se non ricevono un messaggio di posta elettronica legittimo perché sono contrassegnati come posta indesiderata. La correzione dei filtri per la posta indesiderata è sempre più accurata. L'utente e gli utenti possono aiutare questo processo inviando messaggi di posta indesiderata negativi e falsi positivi a Microsoft per l'analisi. Un "falso negativo" è un messaggio di posta indesiderata che avrebbe dovuto essere ma non è stato identificato come posta indesiderata. Un "falso positivo" è un messaggio di posta elettronica legittimo che è stato erroneamente identificato come posta indesiderata.

> [!NOTE]
> A causa dell'elevato volume di invii ricevuti, potrebbe non essere possibile rispondere a tutte le richieste di analisi.

Gli amministratori possono inviare messaggi di posta elettronica, URL e allegati a Microsoft per la revisione. Vedere gli [invii di amministratore in Office 365 ATP](admin-submission.md).

## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>Inviare messaggi di posta indesiderata o tentativi di phishing che hanno superato i filtri posta indesiderata

Se si riceve un messaggio che passa attraverso i filtri per la posta indesiderata e che deve essere classificato come posta indesiderata o phishing, è possibile inviare il messaggio "falso negativo" ai team di analisi di posta indesiderata e Microsoft Phishing Analysis, a seconda dei casi. Gli analisti rivedranno il messaggio e lo aggiungeranno ai filtri a livello di servizio, se soddisfano i criteri di classificazione.

Per ulteriori impostazioni di posta indesiderata che si applicano all'intera organizzazione, vedere [protezione da posta indesiderata in Office 365](anti-spam-protection.md). In questo articolo sono contenuti suggerimenti che consentono di evitare falsi negativi.

È possibile inviare messaggi di posta indesiderata nei modi seguenti:

- Per gli utenti di Outlook e Outlook sul Web, utilizzare il componente aggiuntivo segnala messaggio per Microsoft Outlook. Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).

- È inoltre possibile utilizzare la posta elettronica per inviare messaggi a Microsoft che devono essere classificati come indesiderati o truffe di phishing, come descritto nella procedura seguente.

### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>Inviare messaggi di posta indesiderata o tentativi di phishing a Microsoft 

Per inviare messaggi di posta indesiderata o tentativi di phishing a Microsoft:

1. Creare un messaggio di posta elettronica vuoto.

2. Indirizzare il messaggio al team di Microsoft che esamina i messaggi, come indicato di seguito:

   - Per i messaggi di posta indesiderata: junk@office365.microsoft.com

   - Per i messaggi di truffa di phishing: phish@office365.microsoft.com

3. Copiare e incollare il messaggio di posta indesiderata o di phishing nel nuovo messaggio come allegato.

   > [!NOTE]
   > * È possibile allegare più messaggi nel nuovo messaggio. Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di truffa di phishing o messaggi di posta indesiderata. <br/><br/>* Lasciare vuoto il corpo del nuovo messaggio. <br/><br/>* Utilizzare i formati. msg (default Outlook Format) o. eml (impostazione predefinita di Outlook sul Web Format) per i messaggi allegati.

4. Fare clic su **Invia**.

## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>Inviare messaggi contrassegnati come posta indesiderata ma che dovrebbero essere autorizzati 

Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviare il messaggio "falso positivo" al team di analisi di posta indesiderata di Microsoft. Gli analisti valuterà e analizzerà il messaggio. A seconda dei risultati dell'analisi, i criteri di filtro del contenuto della posta indesiderata a livello di servizio potrebbero essere modificati per consentire l'inoltro del messaggio.

Gli amministratori possono esaminare altre informazioni sulle impostazioni di posta indesiderata che si applicano a un'intera organizzazione. Vedere [creare elenchi di mittenti attendibili in Office 365](create-safe-sender-lists-in-office-365.md). Queste informazioni sono utili se si svolge il ruolo di amministratore e si desidera impedire la visualizzazione di falsi positivi.

È possibile inviare messaggi non di posta indesiderata nei modi seguenti:

- Se si utilizza l'azione **Sposta messaggio all'interno della cartella posta indesiderata** quando si configurano i filtri del contenuto (questa è l'azione predefinita), gli utenti possono rilasciare messaggi falsi positivi nella cartella posta indesiderata di Outlook o Outlook sul Web (in precedenza noto come Outlook Web App).

  - Gli utenti di Outlook possono rilasciare messaggi falsi positivi utilizzando l'opzione di menu **non indesiderata** con il pulsante destro del mouse. Tuttavia, è necessario inviare il messaggio a Microsoft tramite posta elettronica, come illustrato nella procedura descritta in questo articolo.

  - Gli utenti di Outlook sul Web possono rilasciare messaggi falsi positivi e inviarli a Microsoft per l'analisi usando il **segno come azione non indesiderata** . Per ulteriori informazioni su come eseguire questa operazione, vedere [segnalare la posta indesiderata e i tentativi di phishing in Outlook sul Web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).

- Se si utilizza l'azione del **messaggio in quarantena** invece dell'azione **Sposta messaggio nell'indesiderata della cartella posta elettronica** quando si configurano i filtri del contenuto:

  - Gli amministratori possono rilasciare i messaggi di posta indesiderata in quarantena e segnalarli come falsi positivi dall'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).

  - Gli utenti possono rilasciare i propri messaggi di posta indesiderata in quarantena e segnalarli come falsi positivi tramite i seguenti canali:

  - Interfaccia utente EAC. Per ulteriori informazioni, vedere [Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md).

  - Messaggi di notifica di posta indesiderata utente finale (se abilitati dall'amministratore).

- È inoltre possibile utilizzare la posta elettronica per inviare messaggi a Microsoft che non devono essere classificati come posta indesiderata. Quando si esegue questa operazione, accertarsi di utilizzare i passaggi descritti nella procedura seguente.

### <a name="use-email-to-submit-false-positive-messages"></a>Utilizzo della posta elettronica per inviare messaggi falsi positivi

Utilizzare la stessa procedura descritta nella sezione [utilizzo della posta elettronica per inviare messaggi di posta indesiderata o tentativi di phishing a Microsoft](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft) , ma inviare il messaggio a not_junk@office365.microsoft.com.

## <a name="spam-evaluation-and-rules-deployment"></a>Distribuzione di valutazioni e regole di posta indesiderata

Il team di analisi di posta indesiderata esamina i messaggi inviati e regola i filtri di posta indesiderata per impedire la posta indesiderata futura. Di conseguenza, i filtri posta indesiderata di Office 365 areconstantly sono stati affinati. Gli elementi inviati vengono valutati a livello di rete. Gli invii falsi positivi sono esaminati e valutati per una possibile rettifica delle regole per consentire i messaggi futuri tramite i filtri di posta indesiderata. Pertanto, la notifica al servizio dei falsi positivi e anche falsi negativi (posta indesiderata non filtrata) è vantaggiosa per tutti i clienti che usano la rete globale. Il team di posta indesiderata esamina gli indicatori all'interno di ogni messaggio inviato, ad esempio:

- Indirizzo mittente

- Indirizzo IP di invio

- Parole chiave

- Frasi

- Frequenza di trasmissione

- Altre tendenze e modelli

Dopo aver esaminato queste informazioni, il team di posta indesiderata potrebbe apportare modifiche ai layer del filtro della posta indesiderata del servizio. Per ulteriori informazioni sul team di posta indesiderata, è possibile guardare il seguente video solo in inglese:

[Video del team di posta indesiderata di Microsoft Exchange](https://youtu.be/-TpX_-GMC7o?hd=1)

La valutazione della posta indesiderata è un processo continuo applicabile a prescindere dal set di caratteri o della lingua di origine. Dal momento che un messaggio di posta indesiderata può essere vago o non contenere testo nell'oggetto o nel corpo, il team della posta indesiderata si basa su altre caratteristiche del messaggio per eseguire il filtraggio. Ciò significa che dopo che il team ha contrassegnato un determinato messaggio come posta indesiderata e ha apportato le necessarie modifiche alla base di regole, il messaggio viene bloccato finché le relative caratteristiche non hanno subito modifiche sufficienti ad evitare i filtri. Nuove regole per la posta indesiderata vengono sviluppate continuamente. I tempi necessari per lo sviluppo di nuove regole o l'analisi dei messaggi inviati possono variare a seconda della quantità e della qualità degli invii. Poiché le nuove regole della posta indesiderata vengono impostate globalmente per tutti gli utenti, non tutti i singoli invii di posta indesiderata determineranno la creazione di una nuova regola.
