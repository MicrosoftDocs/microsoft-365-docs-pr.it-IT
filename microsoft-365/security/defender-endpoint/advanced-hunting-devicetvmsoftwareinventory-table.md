---
title: Tabella DeviceTvmSoftwareInventory nello schema di ricerca avanzata
description: Informazioni sull'inventario del software nei dispositivi nella tabella DeviceTvmSoftwareInventory dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067506"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

La tabella nello schema di ricerca avanzata contiene l'inventario threat & Vulnerability Management del software attualmente installato nei dispositivi della rete, incluse le informazioni sulla fine `DeviceTvmSoftwareInventory` del supporto. [](next-gen-threat-and-vuln-mgt.md) Puoi, ad esempio, cercare eventi che coinvolgono dispositivi installati con una versione software attualmente vulnerabile. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

>[!NOTE]
>Le `DeviceTvmSoftwareInventory` tabelle e hanno `DeviceTvmSoftwareVulnerabilities` sostituito la `DeviceTvmSoftwareInventoryVulnerabilities` tabella. Insieme, le prime due tabelle includono più colonne che è possibile utilizzare per informare le attività di gestione delle vulnerabilità.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `DeviceId` | stringa | Identificatore univoco del dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `OSVersion` | stringa | Versione del sistema operativo in esecuzione nel dispositivo |
| `OSArchitecture` | stringa | Architettura del sistema operativo in esecuzione nel dispositivo |
| `SoftwareVendor` | stringa | Nome del fornitore del software |
| `SoftwareName` | stringa | Nome del prodotto software |
| `SoftwareVersion` | stringa | Numero della versione del prodotto software |
| `EndOfSupportStatus` | stringa | Indica la fase del ciclo di vita del prodotto software rispetto alla data di fine del supporto (EOS) o di fine vita (EOL) specificata |
| `EndOfSupportDate` | stringa | Data di fine del supporto (EOS) o fine vita (EOL) del prodotto software |



## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprendere lo schema](advanced-hunting-schema-reference.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](next-gen-threat-and-vuln-mgt.md)

