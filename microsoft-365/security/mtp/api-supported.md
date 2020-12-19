---
title: API supportate di Microsoft 365 Defender
description: API supportate di Microsoft 365 Defender
keywords: MTP, API, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719323"
---
# <a name="supported-microsoft-365-defender-apis"></a>API supportate di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>Elenco delle API disponibili

Articolo | Descrizione
-|-
[Rilevazione avanzata API](api-advanced-hunting.md) | Eseguire query di ricerca avanzate.
[Incidenti delle API](api-incident.md) | Elencare e aggiornare gli incidenti, insieme ad altre attività pratiche.

### <a name="endpoint-uris"></a>URI dell'endpoint

L'URI di base per entrambe le API principali è: https://api.security.microsoft.com . Per migliorare le prestazioni, utilizzare un server più vicino alla propria geolocalizzazione:

- Stati Uniti: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Regno Unito: api-uk.security.microsoft.com

I token possono essere acquisiti tramite l'accesso https://api.security.microsoft.com .

Tutte le API lungo il `/api` percorso utilizzano il protocollo [OData](https://docs.microsoft.com/odata/overview) , ad esempio, https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Accedere alle API di Microsoft Threat Protection](api-access.md)
- [Informazioni sui limiti delle API e sulle licenze](api-terms.md)
- [Informazioni sui codici di errore](api-error-codes.md)
