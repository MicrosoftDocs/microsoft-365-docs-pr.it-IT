---
title: API supportate di Microsoft 365 Defender
description: API supportate di Microsoft 365 Defender
keywords: MTP, API, api
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
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060805"
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

### <a name="endpoint-uris"></a>URI endpoint

L'URI di base per entrambe le API principali è: https://api.security.microsoft.com . Per ottenere prestazioni migliori, utilizzare un server più vicino alla georilevazione:

- Stati Uniti: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Regno Unito: api-uk.security.microsoft.com

I token possono essere acquisiti accedendo a https://api.security.microsoft.com .

Tutte le API lungo `/api` il percorso usano il protocollo [OData,](/odata/overview) ad esempio https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Accedere alle API di Microsoft Threat Protection](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Comprendere i codici di errore](api-error-codes.md)