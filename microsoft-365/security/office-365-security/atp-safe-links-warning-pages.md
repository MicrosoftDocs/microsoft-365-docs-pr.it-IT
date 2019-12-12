---
title: Pagine di avviso per collegamenti sicuri ATP di Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
ms.collection:
- M365-security-compliance
description: Ottenere una panoramica delle pagine di avviso che è possibile visualizzare quando Office 365 Advanced Threat Protection è al lavoro.
ms.openlocfilehash: 2c14947f9d9b988eb4f5086500da0d4455f50a43
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970952"
---
# <a name="office-365-atp-safe-links-warning-pages"></a>Pagine di avviso per collegamenti sicuri ATP di Office 365

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si utilizza Outlook.com, Office 365 Home o Office 365 Personal e si cercano informazioni sui collegamenti sicuri di Outlook, vedere [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) consente di proteggere l'organizzazione da tentativi di phishing e malware tramite funzionalità, ad esempio [collegamenti sicuri di ATP](atp-safe-links.md), [allegati sicuri di ATP](atp-safe-attachments.md)e [protezione anti-phishing](anti-phishing-protection.md). Quando la protezione è sul posto, vengono controllati i collegamenti (URL) nei messaggi di posta elettronica e nei documenti di Office. Se un URL viene identificato come sospetto o dannoso, potrebbe essere impedito di aprire l'URL quando si fa clic su di esso. Invece di passare direttamente al sito, è possibile che venga visualizzata una pagina di avviso. 
  
Leggere questo articolo per visualizzare esempi di pagine di avviso che potrebbero essere visualizzate, insieme agli aggiornamenti recenti delle pagine di avviso.
  
## <a name="examples-of-warning-pages"></a>Esempi di pagine di avviso

### <a name="atp-is-scanning-the-link"></a>ATP sta analizzando il collegamento

Un URL viene analizzato da collegamenti sicuri ATP. Potrebbe essere necessario attendere alcuni istanti per riprovare il collegamento.

![ATP sta analizzando il collegamento](../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="a-url-is-in-a-suspicious-email-message"></a>Un URL è in un messaggio di posta elettronica sospetto

L'URL è presente in un messaggio di posta elettronica che sembra simile ad altri messaggi di posta elettronica considerati sospetti. Si consiglia di controllare il messaggio di posta elettronica prima di procedere con il sito.

![Questo URL è in un messaggio di posta elettronica sospetto](../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a>Un URL è presente in un messaggio identificato come tentativo di phishing

L'URL è in un messaggio di posta elettronica identificato come un attacco di phishing. Di conseguenza, tutti gli URL del messaggio di posta elettronica vengono bloccati. Si consiglia di non procedere al sito.

![Questo URL è presente in un messaggio identificato come tentativo di phishing](../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="a-site-has-been-identified-as-malicious"></a>Un sito è stato identificato come dannoso

L'URL punta a un sito che è stato identificato come dannoso.  <br/> Si consiglia di non procedere al sito.

![Questo sito è stato identificato come dannoso](../media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="a-site-is-blocked"></a>Un sito è bloccato

L'URL è bloccato per l'organizzazione. Sono diversi i motivi per cui un URL potrebbe essere bloccato. Si consiglia di contattare l'amministratore di Office 365 dell'organizzazione.

![Questo sito è bloccato](../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="an-error-has-occurred"></a>An error has occurred

Si è verificato un errore e l'URL non può essere aperto.

![An error has occurred](../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

## <a name="recent-updates-to-warning-pages"></a>Aggiornamenti recenti per le pagine di avviso

Alcune pagine di avviso sono state aggiornate di recente per Office 365 ATP. Se non si vedono già le pagine aggiornate, sarà presto possibile. Gli aggiornamenti includono una nuova combinazione di colori, maggiori dettagli e la possibilità di procedere a un sito nonostante gli avvisi e i consigli specificati.

### <a name="url-scan-in-progress"></a>Analisi degli URL in corso

Pagina avviso originale:

![Pagina di avviso originale relativa all'analisi di un URL in corso](../media/04368763-763f-43d6-94a4-a48291d36893.png)

Pagina di avviso aggiornata:

![ATP sta analizzando il collegamento](../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a>Avviso sito dannoso

Pagina avviso originale:

![Pagina di avviso originale relativa a un sito dannoso](../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

Pagina di avviso aggiornata:

![Questo sito è stato identificato come dannoso](../media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a>Avviso URL bloccato

Pagina avviso originale:

![Pagina di avviso originale relativa a un URL bloccato](../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

Pagina di avviso aggiornata:

![Questo sito è bloccato](../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a>Pagina di avviso "errore verificato"

Pagina avviso originale:

![Pagina di avviso "errore verificato" originale](../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

Pagina di avviso aggiornata:

![An error has occurred](../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
   
