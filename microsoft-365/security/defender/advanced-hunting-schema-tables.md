---
title: Tabelle di dati nello schema Microsoft 365 Defender ricerca avanzata
description: Informazioni sulle tabelle nello schema di ricerca avanzata per comprendere i dati su cui è possibile eseguire query di ricerca delle minacce
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 50a221a65c8264d816de958ec74fa99e9e6db762
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53225993"
---
# <a name="understand-the-advanced-hunting-schema"></a>Comprendere schema di ricerca avanzato

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Lo schema [di ricerca](advanced-hunting-overview.md) avanzata è costituito da più tabelle che forniscono informazioni sull'evento o informazioni su dispositivi, avvisi, identità e altri tipi di entità. Per creare efficacemente query che coprano più tabelle, è necessario capire le tabelle e le colonne nello schema per Ricerca avanzata.

## <a name="get-schema-information-in-the-security-center"></a>Ottenere informazioni sullo schema nel Centro sicurezza
Durante la creazione di query, utilizzare il riferimento allo schema predefinito per ottenere rapidamente le informazioni seguenti su ogni tabella nello schema:

- **Descrizione tabelle:** tipo di dati contenuti nella tabella e l'origine di questi dati.
- **Colonne:** tutte le colonne della tabella.
- **Tipi di** azione: valori possibili nella `ActionType` colonna che rappresentano i tipi di evento supportati dalla tabella. Queste informazioni vengono fornite solo per le tabelle che contengono informazioni sull'evento.
- **Query di esempio:** query di esempio che illustrano come utilizzare la tabella.

### <a name="access-the-schema-reference"></a>Accedere al riferimento allo schema
Per accedere rapidamente al riferimento allo schema, selezionare l'azione Visualizza **riferimento** accanto al nome della tabella nella rappresentazione dello schema. È inoltre possibile selezionare **Riferimento allo schema** per cercare una tabella.

![Immagine che mostra come accedere al riferimento allo schema nel portale](../../media/mtp-ah/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Informazioni sulle tabelle dello schema
Di seguito sono elencate tutte le tabelle dello schema. Ogni nome di tabella rimanda a una pagina che descrive i nomi delle colonne di quella tabella. I nomi delle tabelle e delle colonne sono inoltre elencati nel Centro sicurezza come parte della rappresentazione dello schema nella schermata di ricerca avanzata.

| Nome della tabella | Descrizione |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Avvisi da Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender per l'identità, incluse le informazioni sulla gravità e la categorizzazione delle minacce  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Eventi che coinvolgono account e oggetti in Office 365 e altri servizi e app cloud |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Più tipi di evento, inclusi gli eventi attivati da controlli di sicurezza, ad esempio Windows Defender Antivirus e protezione dagli exploit |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Informazioni sui certificati dei file firmati ottenuti dagli eventi di verifica dei certificati sugli endpoint |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Creazione e modifica dei file, e altri file evento di sistema |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Caricamento eventi DDL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Informazioni sul computer, incluse le informazioni sul sistema operativo |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Accesso e altri eventi di autenticazione nei dispositivi |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Connessione rete ed eventi correlati |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Proprietà di rete dei dispositivi, incluse schede fisiche, indirizzi IP e MAC, nonché reti e domini connessi |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Creazione processi ed eventi correlati |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Creazione e modifica di voci del registro di sistema |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Eventi di valutazione della gestione delle minacce e della vulnerabilità che indicano lo stato di diverse configurazioni di sicurezza nei dispositivi |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Knowledge base di diverse configurazioni di sicurezza usate dalla gestione delle minacce e vulnerabilità per valutare i dispositivi, inclusa la mappatura a diversi standard e parametri di riferimento  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventario del software installato nei dispositivi, incluse le informazioni sulla versione e lo stato di fine del supporto |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Vulnerabilità software riscontrate nei dispositivi e elenco degli aggiornamenti della sicurezza disponibili che affrontano ogni vulnerabilità |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Knowledge base sulle vulnerabilità divulgate pubblicamente, anche se il codice di exploit è disponibile pubblicamente |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informazioni sui file allegati ai messaggi di posta elettronica |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 di posta elettronica, inclusi il recapito della posta elettronica e gli eventi di blocco |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Eventi di sicurezza che si verificano dopo il recapito, dopo Microsoft 365 recapitato i messaggi di posta elettronica alla cassetta postale del destinatario |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informazioni sugli URL nei messaggi di posta elettronica |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD). In questa tabella viene illustrata una serie di eventi correlati all'identità ed eventi di sistema nel controller di dominio. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Informazioni sull'account provenienti da varie fonti, tra cui Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventi di autenticazione in Active Directory e Microsoft online Services |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Query per oggetti Active Directory, ad esempio utenti, gruppi, dispositivi e domini |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
