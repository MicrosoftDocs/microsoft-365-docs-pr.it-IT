---
title: Denominazione delle modifiche apportate nello schema di ricerca avanzata di Microsoft 365 Defender
description: Monitorare e verificare le modifiche alle tabelle di denominazione e le colonne nello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, Table, data, Naming changes, Rename, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780812"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Schema di caccia avanzato-modifiche dei nomi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Lo [schema di ricerca avanzata](advanced-hunting-schema-tables.md) viene aggiornato regolarmente per aggiungere nuove tabelle e colonne. In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza dell'utente. Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.

Le modifiche alla denominazione vengono applicate automaticamente alle query salvate nel centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate. Non è necessario aggiornare queste query manualmente. Tuttavia, sarà necessario aggiornare le query seguenti:
- Query eseguite utilizzando l'API
- Query salvate altrove all'esterno del Centro sicurezza

## <a name="december-2020"></a>Dicembre 2020

| Nome della tabella | Nome della colonna originale | Nuovo nome di colonna | Motivo della modifica
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Commenti e suggerimenti dei clienti |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Commenti e suggerimenti dei clienti |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Commenti e suggerimenti dei clienti |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)