---
title: Tabelle di dati nello schema di caccia avanzato di Microsoft 365 Defender
description: Informazioni sulle tabelle nello schema di ricerca avanzata per comprendere i dati su cui è possibile eseguire query di ricerca delle minacce
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, Table, data
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
ms.openlocfilehash: ed5c7084e899c99237074a46af21454a4c21dfe8
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087016"
---
# <a name="understand-the-advanced-hunting-schema"></a>Comprendere schema di ricerca avanzato

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Lo schema di [ricerca avanzato](advanced-hunting-overview.md) è costituito da più tabelle che forniscono informazioni sugli eventi o informazioni su dispositivi, avvisi, identità e altri tipi di entità. Per creare efficacemente query che coprano più tabelle, è necessario capire le tabelle e le colonne nello schema per Ricerca avanzata.

## <a name="get-schema-information-in-the-security-center"></a>Ottenere informazioni sullo schema nel centro sicurezza
Durante la creazione di query, utilizzare il riferimento allo schema incorporato per ottenere rapidamente le informazioni seguenti su ogni tabella nello schema:

- **Descrizione tabelle**: tipo di dati contenuti nella tabella e l'origine di tali dati.
- **Colonne**: tutte le colonne della tabella.
- **Tipi di azione**, ovvero valori possibili nella `ActionType` colonna che rappresenta i tipi di evento supportati dalla tabella. Queste informazioni vengono fornite solo per le tabelle che contengono informazioni sugli eventi.
- Esempio di **query**: query di esempio in cui è possibile utilizzare la tabella.

### <a name="access-the-schema-reference"></a>Accedere alla guida di riferimento allo schema
Per accedere rapidamente alla guida di riferimento allo schema, selezionare l'azione **Visualizza riferimento** accanto al nome della tabella nella rappresentazione dello schema. È inoltre possibile selezionare **riferimento allo schema** per cercare una tabella.   

![Immagine che Mostra come accedere alla guida di riferimento allo schema in-Portal ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Informazioni sulle tabelle dello schema
Di seguito sono elencate tutte le tabelle dello schema. Ogni nome di tabella rimanda a una pagina che descrive i nomi delle colonne di quella tabella. I nomi di tabella e di colonna sono elencati anche nel centro sicurezza come parte della rappresentazione dello schema nella schermata di ricerca avanzata.

| Nome della tabella | Descrizione |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Avvisi di Microsoft Defender per endpoint, Microsoft Defender per Office 365, Microsoft cloud app Security e Microsoft Defender per Identity, incluse le informazioni sulla gravità e la categorizzazione delle minacce  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Attività correlate ai file nelle app e nei servizi cloud |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Eventi che coinvolgono account e oggetti in Office 365 e altre app e servizi cloud |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Più tipi di evento, inclusi gli eventi attivati da controlli di sicurezza, ad esempio Windows Defender Antivirus e protezione dagli exploit |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Informazioni sui certificati dei file firmati ottenuti da eventi di verifica certificati sugli endpoint |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Creazione e modifica dei file, e altri file evento di sistema |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Caricamento eventi DDL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Informazioni sul computer, incluse le informazioni sul sistema operativo |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Accessi e altri eventi di autenticazione nei dispositivi |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Connessione rete ed eventi correlati |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Proprietà di rete dei dispositivi, inclusi gli adattatori fisici, gli indirizzi IP e MAC, nonché le reti e i domini connessi |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Creazione processi ed eventi correlati |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Creazione e modifica di voci del registro di sistema |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Eventi di valutazione della gestione delle minacce e della vulnerabilità che indicano lo stato di diverse configurazioni di sicurezza nei dispositivi |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Knowledge base di diverse configurazioni di sicurezza usate dalla gestione delle minacce e vulnerabilità per valutare i dispositivi, inclusa la mappatura a diversi standard e parametri di riferimento  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventario del software sui dispositivi e di eventuali vulnerabilità note in questi prodotti software |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Knowledge base sulle vulnerabilità divulgate pubblicamente, anche se il codice di exploit è disponibile pubblicamente |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informazioni sui file allegati ai messaggi di posta elettronica |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 eventi di posta elettronica, inclusi gli eventi di blocco e recapito della posta elettronica |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Eventi di sicurezza che si verificano dopo il recapito, dopo che Microsoft 365 ha inviato i messaggi di posta elettronica alla cassetta postale del destinatario |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informazioni sugli URL nei messaggi di posta elettronica |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD). In questa tabella viene illustrata una serie di eventi relativi a identità e eventi di sistema nel controller di dominio. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Informazioni sugli account provenienti da origini diverse, tra cui Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventi di autenticazione in Active Directory e nei Microsoft Online Services |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Query per gli oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
