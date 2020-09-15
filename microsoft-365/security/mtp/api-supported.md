---
title: API di Microsoft Threat Protection supportate
description: API di Microsoft Threat Protection supportate
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650354"
---
# <a name="supported-microsoft-threat-protection-apis"></a>API di Microsoft Threat Protection supportate 
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
[API di caccia avanzata](api-advanced-hunting.md) | Eseguire query di ricerca avanzate dall'API.
[API Incident](api-incident.md) | Eseguire le chiamate API correlate agli incidenti, ad esempio: eventi di elenco, incidenti di aggiornamento e altro ancora.
