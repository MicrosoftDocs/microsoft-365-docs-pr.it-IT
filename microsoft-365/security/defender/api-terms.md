---
title: Microsoft 365 Licenza e condizioni per l'uso delle API Defender
description: Descrizione della licenza e delle condizioni per l'uso per le API in Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9b70311726b6c1c5bedf34a18ee1763255c93ba3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062034"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Licenza e condizioni per l'uso delle API Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

## <a name="official-terms"></a>Condizioni ufficiali

Microsoft 365 Le API Defender sono disciplinate dalla licenza e dalle condizioni per [l'uso](/legal/microsoft-apis/terms-of-use)delle API Microsoft.

## <a name="legal-notices"></a>Note legali

Microsoft e tutti i collaboratori ti concedono una licenza per la documentazione Microsoft e altri contenuti in questo [repository,](https://github.com/MicrosoftDocs/microsoft-365-docs)nella licenza pubblica internazionale Creative Commons Attribution 4.0. Per ulteriori informazioni, vedere il file [LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure e/o altri prodotti e servizi Microsoft a cui si fa riferimento nella documentazione possono essere marchi o marchi registrati di Microsoft negli Stati Uniti e/o in altri paesi.

Le licenze per questo progetto non concedono all'utente i diritti di utilizzo di nomi, logo o marchi Microsoft. Le linee guida generali per i marchi di Microsoft sono disponibili all'indirizzo [Marchi Microsoft](https://go.microsoft.com/fwlink/?LinkID=254653).

Le informazioni sulla privacy sono disponibili [all'indirizzo Privacy all'indirizzo Microsoft](https://privacy.microsoft.com).

Microsoft e tutti i collaboratori si riservano tutti gli altri diritti, in base ai rispettivi diritti d'autore, brevetti o marchi, per implicazione, estoppel o altro.

## <a name="other-restrictions"></a>Altre restrizioni

L'API di ricerca avanzata presenta alcune [limitazioni](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) sul numero di risultati restituiti e sui dati su cui è possibile eseguire query.

1. È possibile eseguire query solo sui dati degli ultimi 30 giorni.
1. I risultati includeranno un massimo di 100.000 righe.

### <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

Le API Microsoft 365 Defender hanno soglie di limitazione.

- **API eventi imprevisti**: fino a 50 chiamate al minuto o 1500 chiamate all'ora.
- **API di ricerca avanzata**: fino a 15 chiamate al minuto, 10 minuti di tempo di esecuzione all'ora e 4 ore di esecuzione al giorno.

Il codice di stato della risposta HTTP che indica la limitazione è `429` .

Se la richiesta è stata limitato, il corpo della risposta indicherà l'ora in cui è possibile iniziare di nuovo a effettuare richieste.

## <a name="related-articles"></a>Articoli correlati

- [Microsoft 365 Panoramica delle API defender](api-overview.md)
- [API supportate di Microsoft 365 Defender](api-supported.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)