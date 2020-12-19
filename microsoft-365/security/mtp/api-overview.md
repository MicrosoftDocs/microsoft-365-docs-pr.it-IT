---
title: Informazioni generali su Microsoft 365 Defender APIs
description: Informazioni sulle API disponibili in Microsoft 365 Defender
keywords: API, API, panoramica, incidenti, incidenti, minacce di caccia, Microsoft 365 Defender
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719191"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Informazioni generali su Microsoft 365 Defender APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender è basato su una piattaforma di integrazione pronta.

Utilizzare le API di Microsoft 365 Defender per automatizzare i flussi di lavoro in base alle tabelle degli incidenti condivisi e di ricerca avanzata.

- **[Coda degli incidenti combinati](api-incident.md)** -concentrarsi su ciò che è critico raggruppando l'ambito di attacco completo e tutte le risorse interessate insieme nell'API Incident.

- **[Caccia ai rischi tra prodotti](api-advanced-hunting.md)** -sfruttare le conoscenze organizzative del team di sicurezza per la ricerca di segnali di compromesso, creando query personalizzate per setacciare i dati non elaborati raccolti su più prodotti di protezione.

Insieme a queste API Microsoft 365 Defender specifiche, ognuno degli altri prodotti di sicurezza espone altre [API](api-articles.md) che consentono di sfruttare le loro funzionalità esclusive.

## <a name="learn-more"></a>Ulteriori informazioni

| **Informazioni su come accedere alle API** |
|-|
| [Informazioni sulle quote e sulle licenze per l'API](api-terms.md) |
| [Accedere alle API di Microsoft 365 Defender](api-access.md) |
| **Creare app** |
| [Creare un'app ' Hello World '](api-hello-world.md) |
| [Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente](api-create-app-user-context.md) |
| [Creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md) |
| [Creare un'app con accesso partner multi-tenant a Microsoft 365 Defender APIs](api-partner-access.md) |
| **Risoluzione dei problemi e gestione delle app** |
| [Informazioni sui codici di errore dell'API](api-error-codes.md) |
| [Gestione dei segreti nelle app con il Vault Key di Azure](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementazione dell'autorizzazione OAuth 2,0 per l'accesso dell'utente](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
