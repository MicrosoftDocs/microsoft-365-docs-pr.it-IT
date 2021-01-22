---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche dei nomi, rinominare, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932203"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Schema ricerca avanzata - Modifiche alla denominazione

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Lo [schema di ricerca](advanced-hunting-schema-tables.md) avanzata viene aggiornato regolarmente per aggiungere nuove tabelle e colonne. In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza utente. Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.

Le modifiche di denominazione vengono applicate automaticamente alle query salvate nel Centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate. Non è necessario aggiornare manualmente queste query. Sarà tuttavia necessario aggiornare le query seguenti:
- Query eseguite con l'API
- Query salvate altrove all'esterno del Centro sicurezza

## <a name="december-2020"></a>Dicembre 2020

| Nome della tabella | Nome colonna originale | Nome nuova colonna | Motivo della modifica
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Feedback dei clienti |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Feedback dei clienti |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Feedback dei clienti |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)