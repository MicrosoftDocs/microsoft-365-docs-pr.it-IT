---
title: Licenza e condizioni per l'utilizzo delle API di Microsoft 365 Defender
description: Descrizione della licenza e delle condizioni per l'utilizzo per le API in Microsoft 365 Defender
keywords: api, api, licenza, termini, api, legale, avvisi, codice di condotta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930955"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licenza e condizioni per l'utilizzo delle API di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>Termini ufficiali

Le API di Microsoft 365 Defender sono disciplinate dalla licenza e dalle condizioni per [l'utilizzo](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)delle API Microsoft.

## <a name="legal-notices"></a>Note legali

Microsoft e tutti i collaboratori ti concedono una licenza per la documentazione Microsoft e altri contenuti in questo [repository,](https://github.com/MicrosoftDocs/microsoft-365-docs)in base alla Licenza pubblica internazionale Creative Commons Attribution 4.0. Per ulteriori informazioni, vedere il file [LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure e/o altri prodotti e servizi Microsoft a cui si fa riferimento nella documentazione possono essere marchi o marchi registrati di Microsoft negli Stati Uniti e/o in altri paesi.

Le licenze per questo progetto non ti concedono diritti per l'uso di nomi, logo o marchi Microsoft. Le linee guida generali sui marchi di Microsoft sono disponibili in [Marchi Microsoft.](https://go.microsoft.com/fwlink/?LinkID=254653)

Le informazioni sulla privacy sono disponibili [in Privacy in Microsoft.](https://privacy.microsoft.com)

Microsoft e i collaboratori si riservano tutti gli altri diritti, in base ai rispettivi copyright, brevetti o marchi, per implicazione, esoppel o altro.

## <a name="other-restrictions"></a>Altre restrizioni

L'API per la ricerca avanzata [presenta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) alcune limitazioni sul numero di risultati restituiti e sui dati su cui è possibile eseguire query.

1. È possibile eseguire query solo sui dati degli ultimi 30 giorni.
1. I risultati includeranno un massimo di 100.000 righe.

### <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

Le API di Microsoft 365 Defender hanno soglie di limitazione.

- **API eventi imprevisti:** fino a 50 chiamate al minuto o 1500 chiamate all'ora.
- **API Advanced Hunting:** fino a 15 chiamate al minuto, 10 minuti di tempo di esecuzione all'ora e 4 ore di tempo di esecuzione al giorno.

Il codice di stato della risposta HTTP che indica la limitazione è `429` .

Se la richiesta è stata limitate, il corpo della risposta indicherà l'ora in cui è possibile iniziare a effettuare nuovamente le richieste.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [API supportate di Microsoft 365 Defender](api-supported.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
