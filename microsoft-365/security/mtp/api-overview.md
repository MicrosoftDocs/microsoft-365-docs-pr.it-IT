---
title: Panoramica delle API di Microsoft 365 Defender
description: Informazioni sulle API disponibili in Microsoft 365 Defender
keywords: api, api, panoramica, incidente, eventi imprevisti, ricerca delle minacce, microsoft 365 defender
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
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931003"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Panoramica delle API di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender si basa su una piattaforma pronta per l'integrazione.

Usare le API di Microsoft 365 Defender per automatizzare i flussi di lavoro in base all'evento imprevisto condiviso e alle tabelle di ricerca avanzata.

- **[Coda degli eventi imprevisti combinati:](api-incident.md)** concentrarsi sugli elementi critici raggruppando l'ambito completo degli attacchi e tutte le risorse influenzate nell'API degli incidenti.

- **[Ricerca delle](api-advanced-hunting.md)** minacce tra prodotti: sfruttare le conoscenze dell'organizzazione del team di sicurezza per cercare segni di compromissione, creando query personalizzate per setacciare i dati non elaborati raccolti tra più prodotti di protezione.

Insieme a queste API specifiche di Microsoft 365 Defender, [](api-articles.md) ognuno degli altri prodotti di sicurezza espone API aggiuntive per aiutarti a sfruttare le loro funzionalità uniche.

## <a name="learn-more"></a>Ulteriori informazioni

| **Informazioni su come accedere alle API** |
|-|
| [Informazioni sulle quote API e sulle licenze](api-terms.md) |
| [Accedere alle API di Microsoft 365 Defender](api-access.md) |
| **Creare app** |
| [Creare un'app "Hello world"](api-hello-world.md) |
| [Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente](api-create-app-user-context.md) |
| [Creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md) |
| [Creare un'app con accesso partner multi-tenant alle API di Microsoft 365 Defender](api-partner-access.md) |
| **Risolvere i problemi e gestire le app** |
| [Informazioni su codici di errore API](api-error-codes.md) |
| [Gestire i segreti nelle app con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementare l'autorizzazione OAuth 2.0 per l'accesso utente](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
