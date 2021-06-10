---
title: Monitoraggio della sicurezza dell'esplorazione Web in Microsoft Defender for Endpoint
description: Usare la protezione Web in Microsoft Defender for Endpoint per monitorare la sicurezza dell'esplorazione Web
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, monitoraggio, report, schede, elenco di domini, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee6388c779d2c5bc09a82f5e9064d1b981e885cb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687424"
---
# <a name="monitor-web-browsing-security"></a>Monitorare la sicurezza dell'esplorazione Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protezione Web consente di monitorare la sicurezza dell'esplorazione Web dell'organizzazione tramite i report in Report **> protezione Web** nell'Microsoft Defender Security Center. Il report contiene schede che forniscono statistiche di rilevamento delle minacce Web.

- **Rilevamenti di** Protezione dalle minacce Web nel tempo - Questa scheda tendenze visualizza il numero di minacce Web rilevate per tipo durante il periodo di tempo selezionato (Ultimi 30 giorni, Ultimi 3 mesi, Ultimi 6 mesi)
 
    ![Immagine della scheda che mostra i rilevamenti di protezione dalle minacce Web nel tempo](images/wtp-blocks-over-time.png)

- **Riepilogo di Protezione dalle** minacce Web: questa scheda visualizza i rilevamenti totali delle minacce Web negli ultimi 30 giorni, mostrando la distribuzione tra i diversi tipi di minacce Web. Selezionando una sezione viene aperto l'elenco dei domini trovati con siti Web dannosi o indesiderati.

    ![Immagine della scheda che mostra il riepilogo della protezione dalle minacce Web](images/wtp-summary.png)

>[!Note]
>Possono essere necessario fino a 12 ore prima che un blocco si rifletta nelle schede o nell'elenco dei domini.

## <a name="types-of-web-threats"></a>Tipi di minacce Web

La protezione Web classifica i siti Web dannosi e indesiderati come:

- **Phishing:** siti Web contenenti moduli Web contraffatti e altri meccanismi di phishing progettati per indurre gli utenti a divulgare credenziali e altre informazioni riservate
- **Dannoso:** siti Web che ospitano malware e codice di exploit
- **Indicatore personalizzato** : siti Web i cui URL o domini sono stati aggiunti all'elenco [di indicatori personalizzati](manage-indicators.md) per il blocco

## <a name="view-the-domain-list"></a>Visualizzare l'elenco dei domini

Selezionare una categoria specifica di minacce Web nella **scheda di riepilogo** protezione dalle minacce Web per aprire la **pagina** Domini. In questa pagina viene visualizzato l'elenco dei domini in tale categoria di minacce. La pagina fornisce le informazioni seguenti per ogni dominio:

- **Numero di** accessi - Numero di richieste di URL nel dominio
- **Blocchi** : numero di volte in cui le richieste sono state bloccate
- **Tendenza di accesso** - Modifica del numero di tentativi di accesso
- **Categoria di minacce** - Tipo di minaccia Web
- **Dispositivi** - Numero di dispositivi con tentativi di accesso

Seleziona un dominio per visualizzare l'elenco dei dispositivi che hanno tentato di accedere agli URL in tale dominio e l'elenco degli URL.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica protezione Web](web-protection-overview.md)
- [Filtro contenuti Web](web-content-filtering.md)
- [Protezione dalle minacce sul Web](web-threat-protection.md)
- [Rispondere alle minacce sul Web](web-protection-response.md)
