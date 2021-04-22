---
title: Distribuire i servizi supportati da Microsoft 365 Defender
description: Informazioni sui servizi di sicurezza Microsoft che possono essere integrati da Microsoft 365 Defender, sui requisiti di licenza e sulle procedure di distribuzione
keywords: distribuire, licenze, servizi supportati, provisioning, configurazione Microsoft 365 Defender, M365, idoneità alla licenza, Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security, MCAS, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4e1b36423974e46a485727f7e1f158dc6163d834
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935678"
---
# <a name="deploy-supported-services"></a>Distribuire i servizi supportati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) integra vari servizi di sicurezza Microsoft per fornire funzionalità centralizzate di rilevamento, prevenzione e indagine contro attacchi sofisticati. In questo articolo vengono descritti i servizi supportati, i relativi requisiti di licenza, i vantaggi e le limitazioni associati alla distribuzione di uno o più servizi e i collegamenti a come è possibile distribuirli completamente singolarmente.

## <a name="supported-services"></a>Servizi supportati
Una licenza di Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinazione valida di licenze consente di accedere ai servizi supportati seguenti e consente di utilizzare Microsoft 365 Defender nel Centro sicurezza Microsoft 365. [Vedere requisiti di licenza](prerequisites.md#licensing-requirements)

| Servizio supportato | Descrizione |
| ------ | ------ |
| Microsoft Defender per endpoint | Suite di endpoint protection basata su potenti sensori comportamentali, analisi cloud e intelligence per le minacce |
|Microsoft Defender per Office 365 | Protezione avanzata per le app e i dati in Office 365, inclusi la posta elettronica e altri strumenti di collaborazione |
| Microsoft Defender per identità | Difendersi da minacce avanzate, identità compromesse e utenti malintenzionati che usano segnali di Active Directory correlati |
| Microsoft Cloud App Security | Identificare e contrastare le minacce informatiche nei servizi cloud Microsoft e di terze parti |

## <a name="deployed-services-and-functionality"></a>Servizi e funzionalità distribuiti
Microsoft 365 Defender offre una migliore visibilità, correlazione e correzione quando distribuisci altri servizi supportati.

### <a name="benefits-of-full-deployment"></a>Vantaggi della distribuzione completa
Per ottenere i vantaggi completi di Microsoft 365 Defender, è consigliabile distribuire tutti i servizi supportati. Ecco alcuni dei principali vantaggi della distribuzione completa:
- Gli eventi imprevisti vengono identificati e correlati in base agli avvisi e ai segnali di evento di tutti i sensori disponibili e funzionalità di analisi specifiche del servizio
- I playbook AIR (Automated Investigation and Remediation) si applicano a vari tipi di entità, inclusi dispositivi, cassette postali e account utente
- È possibile eseguire query su uno schema di ricerca avanzata più completo per i dati di eventi ed entità da dispositivi, cassette postali e altre entità

### <a name="limited-deployment-scenarios"></a>Scenari di distribuzione limitati
Ogni servizio supportato distribuito fornisce un set estremamente ricco di segnali non elaborati e informazioni correlate. Anche se la distribuzione limitata non causa la disattivazione della funzionalità di Microsoft 365 Defender, ne è influenzata la capacità di fornire una visibilità completa su endpoint, app, dati e identità. Contemporaneamente, tutte le funzionalità di correzione si applicano solo alle entità che possono essere gestite dai servizi distribuiti.

La tabella seguente elenca il modo in cui ogni servizio supportato fornisce dati aggiuntivi, opportunità per ottenere informazioni aggiuntive correlando i dati e migliorare le funzionalità di correzione e risposta.

| Servizio | Dati (segnali & informazioni correlate) | Remediation & response scope |
| ------ | ------ | ------ |
| Microsoft Defender per endpoint | - Stati degli endpoint ed eventi non elaborati<br />- Rilevamenti e avvisi degli endpoint, tra cui antivirus, EDR, riduzione della superficie di attacco<br />- Informazioni su file e altre entità osservate sugli endpoint | Endpoint |
|Microsoft Defender per Office 365 | - Stati della posta e delle cassette postali ed eventi non elaborati<br />- Rilevamenti di posta elettronica, allegati e collegamenti | - Cassette postali<br />- Account di Microsoft 365 |
| Microsoft Defender per identità | - Segnali di Active Directory, inclusi gli eventi di autenticazione<br />- Rilevamenti comportamentali correlati all'identità | Identità |
| Microsoft Cloud App Security | - Rilevamento di app e servizi cloud non sanzionati (IT shadow)<br />- Esposizione dei dati alle app cloud<br />- Attività di minacce associate alle app cloud | App cloud |

## <a name="deploy-the-services"></a>Distribuire i servizi
La distribuzione di ogni servizio richiede in genere il provisioning nel tenant e alcune configurazioni iniziali. Vedere la tabella seguente per comprendere come vengono distribuiti ognuno di questi servizi.

| Servizio | Istruzioni per il provisioning | Configurazione iniziale |
| ------ | ------ | ------ |
| Microsoft Defender per endpoint | [Guida alla distribuzione di Microsoft Defender for Endpoint](../defender-endpoint/deployment-phases.md) | *Vedere le istruzioni per il provisioning* |
|Microsoft Defender per Office 365 | *Nessuno, provisioning con Office 365* | [Configurazione criteri di Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender per identità | [Guida introduttiva: Creare l'istanza di Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step1) | *Vedere le istruzioni per il provisioning* |
| Microsoft Cloud App Security | *Nessuna* | [Guida introduttiva: Introduzione a Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

Dopo aver distribuito i servizi supportati, [attivare Microsoft 365 Defender](m365d-enable.md).

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft 365 Defender](microsoft-365-defender.md)
- [Attivare Microsoft 365 Defender](m365d-enable.md)
- [Panoramica di Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Panoramica di Microsoft Defender per Office 365](../office-365-security/defender-for-office-365.md)
- [Panoramica di Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
