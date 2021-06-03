---
title: API supportate di Microsoft 365 Defender
description: API supportate di Microsoft 365 Defender
keywords: Microsoft 365 Defender, API, api
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
ms.openlocfilehash: c10b2863503a5bda829cbf67379a606b687ac2e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730943"
---
# <a name="supported-microsoft-365-defender-apis"></a>API supportate di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

## <a name="list-of-available-apis"></a>Elenco delle API disponibili

Articolo | Descrizione
-|-
[Rilevazione avanzata API](api-advanced-hunting.md) | Eseguire query di ricerca avanzata.
[Incidenti delle API](api-incident.md) | Elencare e aggiornare gli eventi imprevisti, insieme ad altre attività pratiche.
[API di streaming](../defender-endpoint/raw-data-export.md) (anteprima) | Spedire gli eventi e gli avvisi in tempo reale quando si verificano in un singolo flusso di dati.

### <a name="endpoint-uris"></a>URI endpoint

L'URI di base per entrambe le API principali è: https://api.security.microsoft.com . Per ottenere prestazioni migliori, utilizzare un server più vicino alla georilevazione:

- Stati Uniti: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Regno Unito: api-uk.security.microsoft.com

I token possono essere acquisiti accedendo a https://api.security.microsoft.com .

Tutte le API lungo `/api` il percorso usano il protocollo [OData,](/odata/overview) ad esempio https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Articoli correlati

- [Microsoft 365 Panoramica delle API defender](api-overview.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
- [Streaming API](../defender-endpoint/raw-data-export.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Comprendere i codici di errore](api-error-codes.md)
