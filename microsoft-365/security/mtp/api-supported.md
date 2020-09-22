---
title: API supportate per Microsoft Threat Protection
description: API supportate per Microsoft Threat Protection
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203696"
---
# <a name="supported-microsoft-threat-protection-apis"></a>API supportate per Microsoft Threat Protection 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>URI del punto finale:

- L'URI di base del servizio è il seguente: https://api.security.microsoft.com <br>

>[!NOTE]
>Per ottenere prestazioni migliori, è possibile utilizzare il server più vicino alla posizione geografica:
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - La risorsa per l'acquisizione di token dovrebbe essere la seguente: https://api.security.microsoft.com

 - Tutte le API in ```/api``` path sono API OData. e.g. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>Elenco delle API disponibili:

Argomento | Descrizione
:---|:---
[Rilevazione avanzata API](api-advanced-hunting.md) | Eseguire query di ricerca avanzate dall'API.
[Incidenti delle API](api-incident.md) | Eseguire le chiamate API correlate agli incidenti, ad esempio: eventi di elenco, incidenti di aggiornamento e altro ancora.
