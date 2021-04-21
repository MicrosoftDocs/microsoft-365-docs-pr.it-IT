---
title: Panoramica delle API di Microsoft 365 Defender
description: Informazioni sulle API disponibili in Microsoft 365 Defender
keywords: api, api, panoramica, incidente, incidenti, ricerca delle minacce, microsoft 365 defender
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
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904189"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Panoramica delle API di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

Microsoft 365 Defender si basa su una piattaforma pronta per l'integrazione.

Usa le API di Microsoft 365 Defender per automatizzare i flussi di lavoro in base all'evento imprevisto condiviso e alle tabelle di ricerca avanzate.

- **[Coda degli eventi imprevisti combinati:](api-incident.md)** concentrarsi su ciò che è critico raggruppando l'ambito di attacco completo e tutti gli asset influenzati insieme nell'API degli eventi imprevisti.

- **[Ricerca delle](api-advanced-hunting.md)** minacce tra prodotti - Sfruttare le conoscenze organizzative del team di sicurezza per cercare segni di compromissione, creando query personalizzate per setacciare i dati non elaborati raccolti tra più prodotti di protezione.

Insieme a queste API specifiche di Microsoft 365 Defender, [](api-articles.md) ognuno dei nostri altri prodotti di sicurezza espone API aggiuntive per aiutarti a sfruttare le loro funzionalità uniche.


> [!NOTE]
> La transizione al portale unificato non deve influire sui dashboard di PowerBi basati sulle API di Microsoft Defender for Endpoint. Puoi continuare a usare le API esistenti indipendentemente dalla transizione interattiva del portale.


## <a name="learn-more"></a>Altre informazioni

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
| [Gestire i segreti nelle app con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementare l'autorizzazione OAuth 2.0 per l'accesso utente](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |