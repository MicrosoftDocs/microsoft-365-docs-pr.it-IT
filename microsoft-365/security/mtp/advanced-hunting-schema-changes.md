---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche dei nomi, rinominare, Microsoft Threat Protection
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
ms.openlocfilehash: 948c8bb5c1e6b67f6de355bc532c6b14d5a83933
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551873"
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
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Feedback dei clienti |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Feedback dei clienti |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Feedback dei clienti |

## <a name="january-2021"></a>Gennaio 2021

| Nome colonna | Nome valore originale | Nome nuovo valore | Motivo della modifica
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  Ti personalizzato | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender per Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    Che cosa è Microsoft Defender per identità? | Rebranding |
| `DetectionSource` | CustomDetection   | Rilevamento personalizzato | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Indagine automatizzata | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft Threat Experts | Rebranding |
| `DetectionSource` | TI di terze parti | Sensori di terze parti | Rebranding |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender per endpoint | Rebranding |
|`ServiceSource` |Microsoft Threat Protection   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender per Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Che cosa è Microsoft Defender per identità? | Rebranding |

`DetectionSource`è disponibile nella [tabella AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`è disponibile nelle tabelle [AlertEvidence](advanced-hunting-alertevidence-table.md) [e AlertInfo.](advanced-hunting-alertinfo-table.md) 

## <a name="february-2021"></a>Febbraio 2021

1. Nelle tabelle [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) e [EmailEvents,](advanced-hunting-emailevents-table.md) le colonne e sono `MalwareFilterVerdict` state `PhishFilterVerdict` sostituite dalla `ThreatTypes` colonna. Anche `MalwareDetectionMethod` le colonne e le colonne sono state `PhishDetectionMethod` sostituite dalla `DetectionMethods` colonna. Questa snellizione consente di fornire ulteriori informazioni nelle nuove colonne. Il mapping viene fornito di seguito.

| Nome della tabella | Nome colonna originale | Nome nuova colonna | Motivo della modifica
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Includere altri metodi di rilevamento |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Includere altri tipi di minaccia |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Includere altri metodi di rilevamento |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Includere altri tipi di minaccia |


2. Nelle tabelle `EmailAttachmentInfo` e `EmailEvents` nelle tabelle, la colonna è stata `ThreatNames` aggiunta per fornire ulteriori informazioni sulla minaccia di posta elettronica. Questa colonna contiene valori come Posta indesiderata o Phish.

3. Nella tabella [DeviceInfo](advanced-hunting-deviceinfo-table.md) la colonna è stata sostituita dalla colonna in base `DeviceObjectId` al feedback dei `AadDeviceId` clienti.

4. Nella tabella [DeviceEvents](advanced-hunting-deviceevents-table.md) sono stati modificati diversi nomi ActionType per riflettere meglio la descrizione dell'azione. I dettagli delle modifiche sono disponibili di seguito.

| Nome della tabella | Nome ActionType originale | Nuovo nome ActionType | Motivo della modifica
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Feedback dei clienti |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Feedback dei clienti |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Feedback dei clienti |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Feedback dei clienti |






## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)