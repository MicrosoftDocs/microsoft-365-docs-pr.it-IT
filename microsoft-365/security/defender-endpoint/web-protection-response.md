---
title: Rispondere alle minacce Web in Microsoft Defender ATP
description: Rispondere agli avvisi relativi a siti Web dannosi e indesiderati. Comprendere in che modo Protezione dalle minacce Web informa gli utenti finali tramite i web browser e le notifiche di Windows
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, avvisi, risposta, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser, notifiche, utenti finali, notifiche di Windows, pagina di blocco,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 339944b94ca55c5d73fafaabfe3f7bc26dafe7bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063677"
---
# <a name="respond-to-web-threats"></a>Rispondere alle minacce Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protezione Web in Microsoft Defender for Endpoint consente di analizzare e rispondere in modo efficiente agli avvisi relativi a siti Web e siti Web dannosi nell'elenco di indicatori personalizzati.

## <a name="view-web-threat-alerts"></a>Visualizzare gli avvisi relativi alle minacce Web
Microsoft Defender for Endpoint genera gli avvisi [seguenti per](manage-alerts.md) attività Web dannose o sospette:
- **Connessione sospetta bloccata dalla** protezione di rete: questo avviso viene generato quando un tentativo  di accedere a un sito Web dannoso o a un sito Web nell'elenco di indicatori personalizzati viene arrestato dalla protezione di rete in *modalità* blocco
- **Connessione sospetta rilevata** dalla protezione di rete: questo avviso viene generato quando un tentativo di accedere a un sito Web dannoso o a un sito Web nell'elenco di indicatori personalizzati viene rilevato dalla protezione di rete in *modalità solo* controllo

Ogni avviso fornisce le informazioni seguenti: 
- Dispositivo che ha tentato di accedere al sito Web bloccato
- Applicazione o programma utilizzato per inviare la richiesta Web
- URL o URL dannoso nell'elenco degli indicatori personalizzati
- Azioni consigliate per i risponditori

![Immagine di un avviso relativo alla protezione dalle minacce Web](images/wtp-alert.png)

>[!Note]
>Per ridurre il volume di avvisi, Microsoft Defender for Endpoint consolida i rilevamenti di minacce Web per lo stesso dominio nello stesso dispositivo ogni giorno in un singolo avviso. Nel report di protezione Web viene generato e conteggiato [un solo avviso.](web-protection-monitoring.md)

## <a name="inspect-website-details"></a>Esaminare i dettagli del sito Web
Puoi approfondire selezionando l'URL o il dominio del sito Web nell'avviso. Verrà aperta una pagina sull'URL o sul dominio specifico con diverse informazioni, tra cui:
- Dispositivi che hanno tentato di accedere al sito Web
- Eventi imprevisti e avvisi correlati al sito Web
- Frequenza con cui il sito Web è stato visualizzato negli eventi dell'organizzazione

    ![Immagine della pagina dei dettagli del dominio o dell'entità URL](images/wtp-website-details.png)

[Altre informazioni sulle pagine dell'URL o dell'entità di dominio](investigate-domain.md)

## <a name="inspect-the-device"></a>Esaminare il dispositivo
Puoi anche controllare il dispositivo che ha tentato di accedere a un URL bloccato. Selezionando il nome del dispositivo nella pagina di avviso si apre una pagina con informazioni complete sul dispositivo.

[Altre informazioni sulle pagine dell'entità dispositivo](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Notifiche di Web browser e Windows per gli utenti finali

Con la protezione Web in Microsoft Defender for Endpoint, agli utenti finali verrà impedito di visitare siti Web dannosi o indesiderati utilizzando Microsoft Edge o altri browser. Poiché il blocco viene eseguito dalla [protezione di](network-protection.md)rete, verrà visualizzato un errore generico dal Web browser. Verrà inoltre visualizzata una notifica da Windows.

![Immagine di Microsoft Edge che mostra un errore 403 e la minaccia Web di notifica di Windows ](images/wtp-browser-blocking-page.png)
 *bloccata in Microsoft Edge*

![Immagine del web browser Chrome che mostra un avviso di connessione sicura e la minaccia Web di notifica di Windows ](images/wtp-chrome-browser-blocking-page.png)
 *bloccata in Chrome*

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della protezione Web](web-protection-overview.md)
- [Filtro contenuto Web](web-content-filtering.md)
- [Protezione dalle minacce Web](web-threat-protection.md)
- [Monitorare la sicurezza Web](web-protection-monitoring.md)
