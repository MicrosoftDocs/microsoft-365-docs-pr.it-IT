---
title: Tabelle dati nello schema di ricerca avanzata di Microsoft Threat Protection
description: Informazioni sulle tabelle nello schema di ricerca avanzata per comprendere i dati su cui è possibile eseguire query di ricerca delle minacce
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, ricerche, query, telemetria, schema di riferimento, esplora dati, tabella, dati
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1803445dfd9b46fce23b0dcc9585ea543f1b0347
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911205"
---
# <a name="understand-the-advanced-hunting-schema"></a>Comprendere schema di ricerca avanzato

**Si applica a:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

Lo schema per [Ricerca avanzata](advanced-hunting-overview.md) è costituito da più tabelle che forniscono informazioni sull'evento o informazioni su computer ed entità. Per creare efficacemente query che coprano più tabelle, è necessario capire le tabelle e le colonne nello schema per Ricerca avanzata.

## <a name="schema-tables"></a>Tabelle dello schema

Di seguito sono elencate tutte le tabelle dello schema. Ogni nome di tabella rimanda a una pagina che descrive i nomi delle colonne di quella tabella. I nomi di tabella e di colonna sono elencati anche nel Centro sicurezza come parte della rappresentazione nella schermata della Ricerca avanzata.

| Nome della tabella | Descrizione |
|------------|-------------|
| **[MachineInfo](advanced-hunting-machineinfo-table.md)** | Informazioni sul computer, incluse le informazioni sul sistema operativo |
| **[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)** | Proprietà di rete dei computer, tra cui adattatori, indirizzi IP e MAC, oltre a reti e domini collegati |
| **[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)** | Creazione processi ed eventi correlati |
| **[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)** | Connessione rete ed eventi correlati |
| **[FileCreationEvents](advanced-hunting-filecreationevents-table.md)** | Creazione e modifica dei file, e altri file evento di sistema |
| **[RegistryEvents](advanced-hunting-registryevents-table.md)** | Creazione e modifica di voci del registro di sistema |
| **[LogonEvents](advanced-hunting-logonevents-table.md)** | Accessi e altri eventi di autenticazione |
| **[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)** | Caricamento eventi DDL |
| **[MiscEvents](advanced-hunting-miscevents-table.md)** | Più tipi di evento, inclusi gli eventi attivati da controlli di sicurezza, ad esempio Windows Defender Antivirus e protezione dagli exploit |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventi di posta elettronica di Office 365, tra cui il recapito e-mail e gli eventi blocco |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informazioni sui file allegati ai messaggi di posta elettronica di Office 365 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informazioni sugli URL dei messaggi di posta elettronica di Office 365 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventario dei software presenti sui dispositivi, oltre a qualsiasi vulnerabilità nota in questi prodotti software |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | Knowledge base sulle vulnerabilità divulgate pubblicamente, anche se il codice di exploit è disponibile pubblicamente |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | Eventi di valutazione della gestione delle minacce e della vulnerabilità che indicano lo stato di diverse configurazioni di sicurezza nei dispositivi |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Knowledge base di diverse configurazioni di sicurezza usate dalla gestione delle minacce e vulnerabilità per valutare i dispositivi, inclusa la mappatura a diversi standard e parametri di riferimento  |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce su dispositivi ed e-mail](advanced-hunting-query-emails-devices.md)
- [Applicazione delle procedure consigliate per le query](advanced-hunting-best-practices.md)
