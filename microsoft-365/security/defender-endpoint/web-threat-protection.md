---
title: Proteggere l'organizzazione dalle minacce Web
description: Informazioni sulla protezione Web in Microsoft Defender ATP e su come può proteggere l'organizzazione.
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser
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
ms.openlocfilehash: aeeea02ca1ef2d37623e9ab434b162237c2f4946
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499901"
---
# <a name="protect-your-organization-against-web-threats"></a>Proteggere l'organizzazione dalle minacce Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protezione dalle minacce Web fa [parte della protezione Web](web-protection-overview.md) in Defender for Endpoint. Usa la [protezione di rete](network-protection.md) per proteggere i dispositivi dalle minacce Web. Grazie all'integrazione con Microsoft Edge e i browser di terze parti più diffusi come Chrome e Firefox, La protezione dalle minacce Web interrompe le minacce Web senza un proxy Web e può proteggere i dispositivi mentre sono in locale o in locale. La protezione dalle minacce Web interrompe l'accesso ai siti di phishing, ai vettori di malware, ai siti di exploit, a siti non attendibili o a bassa reputazione, nonché ai siti bloccati [nell'elenco degli indicatori personalizzati.](manage-indicators.md)

>[!Note]
>I dispositivi possono richiedere fino a un'ora per ricevere nuovi indicatori personalizzati.

## <a name="prerequisites"></a>Prerequisiti
La protezione Web usa la protezione di rete per garantire la sicurezza dell'esplorazione Web in Microsoft Edge e nei Web browser di terze parti.

Per attivare la protezione di rete nei dispositivi:
- Modificare la linea di base per la sicurezza di Defender per endpoint in **Protezione di rete &** Web per abilitare la protezione di rete prima di distribuirla o ridistribuirla. [Informazioni su come esaminare e assegnare la baseline di sicurezza di Defender for Endpoint](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Attivare la protezione di rete usando la configurazione del dispositivo Intune, SCCM, Criteri di gruppo o la soluzione MDM. [Altre informazioni sull'abilitazione della protezione di rete](enable-network-protection.md)  

>[!Note]
>Se si imposta la protezione di rete **solo su Controlla**, il blocco non sarà disponibile. Inoltre, sarà possibile rilevare e registrare i tentativi di accesso a siti Web dannosi e indesiderati solo in Microsoft Edge.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica protezione Web](web-protection-overview.md)
- [Protezione dalle minacce sul Web](web-threat-protection.md)
- [Monitorare la sicurezza sul Web](web-protection-monitoring.md)
- [Rispondere alle minacce sul Web](web-protection-response.md)
- [Protezione di rete](network-protection.md)
