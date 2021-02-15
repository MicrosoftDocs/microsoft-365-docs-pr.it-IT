---
title: Distribuire i servizi supportati da Microsoft 365 Defender
description: Informazioni sui servizi di sicurezza Microsoft che possono essere integrati da Microsoft 365 Defender, sui requisiti di licenza e sulle procedure di distribuzione
keywords: distribuire, licenze, servizi supportati, provisioning, configurazione di Microsoft Threat Protection, M365, idoneità alle licenze, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, protezione avanzata dalle minacce, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928963"
---
# <a name="deploy-supported-services"></a>Distribuire i servizi supportati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integra vari servizi di sicurezza Microsoft per fornire funzionalità di rilevamento, prevenzione e analisi centralizzate contro attacchi sofisticati. In questo articolo vengono descritti i servizi supportati, i relativi requisiti di licenza, i vantaggi e le limitazioni associati alla distribuzione di uno o più servizi e vengono forniti collegamenti a come distribuirli completamente singolarmente.

## <a name="supported-services"></a>Servizi supportati
Una licenza di Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinazione valida di licenze consente di accedere ai servizi supportati seguenti e consente di usare Microsoft 365 Defender nel Centro sicurezza Microsoft 365. [Visualizzare i requisiti di licenza](prerequisites.md#licensing-requirements)

| Servizio supportato | Descrizione |
| ------ | ------ |
| Microsoft Defender per endpoint | Famiglia di prodotti di endpoint protection basata su potenti sensori comportamentali, analisi del cloud e intelligence per le minacce |
|Microsoft Defender per Office 365 | Protezione avanzata per le app e i dati in Office 365, inclusi la posta elettronica e altri strumenti di collaborazione |
| Che cosa è Microsoft Defender per identità? | Difendersi da minacce avanzate, identità compromesse e insider malintenzionati usando segnali di Active Directory correlati |
| Microsoft Cloud App Security | Identificare e contrastare le minacce informatiche nei servizi cloud Microsoft e di terze parti |

## <a name="deployed-services-and-functionality"></a>Servizi e funzionalità distribuiti
Microsoft 365 Defender offre maggiore visibilità, correlazione e correzione man quando si distribuiscono altri servizi supportati.

### <a name="benefits-of-full-deployment"></a>Vantaggi della distribuzione completa
Per ottenere tutti i vantaggi di Microsoft 365 Defender, è consigliabile distribuire tutti i servizi supportati. Ecco alcuni dei principali vantaggi della distribuzione completa:
- Gli eventi imprevisti vengono identificati e correlati in base agli avvisi e ai segnali di evento provenienti da tutti i sensori disponibili e dalle funzionalità di analisi specifiche del servizio
- I playbook di analisi e correzione automatizzati (AIR) si applicano a diversi tipi di entità, tra cui dispositivi, cassette postali e account utente
- È possibile eseguire query su uno schema di ricerca avanzata più completo per i dati di eventi ed entità da dispositivi, cassette postali e altre entità

### <a name="limited-deployment-scenarios"></a>Scenari di distribuzione limitati
Ogni servizio supportato che distribuisci fornisce un set estremamente ricco di segnali non elaborati e informazioni correlate. Anche se la distribuzione limitata non causa la disattivazione della funzionalità di Microsoft 365 Defender, ne viene influenzata la capacità di fornire visibilità completa tra endpoint, app, dati e identità. Allo stesso tempo, tutte le funzionalità di correzione si applicano solo alle entità che possono essere gestite dai servizi distribuiti.

La tabella seguente elenca il modo in cui ogni servizio supportato fornisce dati aggiuntivi, opportunità per ottenere ulteriori informazioni correlando i dati e migliori funzionalità di correzione e risposta.

| Servizio | Dati (segnali & informazioni correlate) | Correzione dell'& di risposta |
| ------ | ------ | ------ |
| Microsoft Defender per endpoint | - Stati degli endpoint ed eventi non elaborati<br />- Rilevamenti e avvisi degli endpoint, tra cui antivirus, EDR, riduzione della superficie di attacco<br />- Informazioni su file e altre entità osservate sugli endpoint | Endpoint |
|Microsoft Defender per Office 365 | - Stati di posta e cassette postali ed eventi non elaborati<br />- Rilevamenti di posta elettronica, allegati e collegamenti | - Cassette postali<br />- Account di Microsoft 365 |
| Che cosa è Microsoft Defender per identità? | - Segnali di Active Directory, inclusi gli eventi di autenticazione<br />- Rilevamenti comportamentali correlati all'identità | Identità |
| Microsoft Cloud App Security | - Rilevamento di app e servizi cloud non sanzionati (SHADOW IT)<br />- Esposizione dei dati alle app cloud<br />- Attività di minaccia associata alle app cloud | App cloud |

## <a name="deploy-the-services"></a>Distribuire i servizi
La distribuzione di ogni servizio in genere richiede il provisioning nel tenant e alcune configurazioni iniziali. Per informazioni sulla distribuzione di ognuno di questi servizi, vedere la tabella seguente.

| Servizio | Istruzioni per il provisioning | Configurazione iniziale |
| ------ | ------ | ------ |
| Microsoft Defender per endpoint | [Guida alla distribuzione di Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Vedere le istruzioni di provisioning* |
|Microsoft Defender per Office 365 | *Nessuno, provisioning con Office 365* | [Configurazione criteri di Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Che cosa è Microsoft Defender per identità? | [Guida introduttiva: Creare l'istanza di Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Vedere le istruzioni di provisioning* |
| Microsoft Cloud App Security | *Nessuna* | [Guida introduttiva: Introduzione a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Dopo aver distribuito i servizi supportati, [attivare Microsoft 365 Defender.](mtp-enable.md)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft 365 Defender](microsoft-threat-protection.md)
- [Attivare Microsoft 365 Defender](mtp-enable.md)
- [Panoramica di Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Panoramica di Microsoft Defender per Office 365](../office-365-security/office-365-atp.md)
- [Panoramica di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
