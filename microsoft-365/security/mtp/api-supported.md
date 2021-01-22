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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926199"
---
# <a name="supported-microsoft-365-defender-apis"></a>API supportate di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>Elenco delle API disponibili

Articolo | Descrizione
-|-
[Rilevazione avanzata API](api-advanced-hunting.md) | Eseguire query di Ricerca avanzata.
[Incidenti delle API](api-incident.md) | Elencare e aggiornare gli eventi imprevisti, insieme ad altre attività pratiche.

### <a name="endpoint-uris"></a>URI endpoint

L'URI di base per entrambe le API principali è: https://api.security.microsoft.com . Per ottenere prestazioni migliori, utilizzare un server più vicino alla georilevazione:

- Stati Uniti: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Regno Unito: api-uk.security.microsoft.com

I token possono essere acquisiti accedendo https://api.security.microsoft.com a .

Tutte le API lungo il `/api` percorso usano il protocollo [OData,](https://docs.microsoft.com/odata/overview) ad esempio https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Accedere alle API di Microsoft Threat Protection](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Comprendere i codici di errore](api-error-codes.md)
