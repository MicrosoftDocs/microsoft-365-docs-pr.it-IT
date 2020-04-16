---
title: Distribuire i servizi supportati da Microsoft Threat Protection
description: Informazioni sui servizi di sicurezza Microsoft che possono essere integrati da Microsoft Threat Protection, dai rispettivi requisiti di licenza e dalle procedure di distribuzione
keywords: distribuzione, licenze, servizi supportati, provisioning, configurazione di Microsoft Threat Protection, M365, idoneità alle licenze, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft cloud app Security, MCAS, Advanced Threat Protection, E5, a5, EMS
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1441790bfa0c587c4abceb87eb1e4daae6e4d157
ms.sourcegitcommit: 09c3e2f3129c5e43cd8420cccd0676ff3a29a355
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521481"
---
# <a name="deploy-supported-services"></a>Distribuire i servizi supportati

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integra vari servizi di sicurezza Microsoft per fornire funzionalità di rilevamento, prevenzione e analisi centralizzate a fronte di attacchi sofisticati. In questo articolo vengono illustrati i servizi supportati, i relativi requisiti di licenza, i vantaggi e le limitazioni associati alla distribuzione di uno o più servizi e i collegamenti a come è possibile distribuirli completamente singolarmente.

## <a name="supported-services"></a>Servizi supportati
Una licenza di sicurezza Microsoft 365 E5, E5, a5 o a5 o una combinazione valida di licenze fornisce l'accesso ai seguenti servizi supportati e consente di utilizzare Microsoft Threat Protection in Microsoft 365 Security Center. [Visualizzare i requisiti di licenza](prerequisites.md#licensing-requirements)

| Servizio supportato | Descrizione |
| ------ | ------ |
| Microsoft Defender ATP | Serie di Endpoint Protection sviluppata attorno a potenti sensori comportamentali, cloud Analytics e Threat Intelligence |
| Office 365 ATP | Protezione avanzata per le app e i dati in Office 365, inclusi i messaggi di posta elettronica e altri strumenti di collaborazione |
| Azure ATP | Difendersi da minacce avanzate, identità compromesse e insiders dannosi che utilizzano segnali correlati di Active Directory |
| Microsoft Cloud App Security | Identificare e combattere Cyberthreats tra i servizi cloud Microsoft e di terze parti |

## <a name="deployed-services-and-functionality"></a>Servizi e funzionalità distribuiti
Microsoft Threat Protection offre una migliore visibilità, correlazione e correzione quando si distribuiscono servizi più supportati.

### <a name="benefits-of-full-deployment"></a>Vantaggi della distribuzione completa
Per ottenere i vantaggi completi di Microsoft Threat Protection, è consigliabile distribuire tutti i servizi supportati. Di seguito sono illustrati alcuni dei vantaggi principali della distribuzione completa:
- Gli incidenti sono identificati e correlati in base agli avvisi e ai segnali di evento provenienti da tutti i sensori disponibili e dalle funzionalità di analisi specifiche del servizio
- I PlayBook automatizzati di analisi e correzione (AIR) si applicano ai vari tipi di entità, inclusi i dispositivi, le cassette postali e gli account utente.
- È possibile eseguire query su uno schema di caccia avanzato più esaustivo per i dati di eventi e di entità provenienti da dispositivi, cassette postali e altre entità

### <a name="limited-deployment-scenarios"></a>Scenari di distribuzione limitati
Ogni servizio supportato distribuito fornisce un insieme estremamente ricco di segnali non elaborati e informazioni correlate. Anche se la distribuzione limitata non causa la disattivazione della funzionalità di protezione dalle minacce di Microsoft, la sua capacità di fornire una visibilità completa tra gli endpoint, le app, i dati e le identità è intaccata. Allo stesso tempo, le funzionalità di correzione si applicano solo alle entità che possono essere gestite dai servizi che sono stati distribuiti.

La tabella seguente elenca la modalità in cui ogni servizio supportato fornisce dati aggiuntivi, le opportunità di ottenere ulteriori informazioni correlate ai dati e le migliori funzionalità di correzione e risposta.

| Servizio | Dati (segnali & informazioni correlate) | Ambito di correzione & risposta |
| ------ | ------ | ------ |
| Microsoft Defender ATP | -Stati endpoint e eventi RAW<br />-Rilevamento e avvisi degli endpoint, tra cui antivirus, EDR, riduzione della superficie di attacco<br />-Informazioni sui file e su altre entità osservate negli endpoint | Endpoint |
| Office 365 ATP | -Stati di posta e cassette postali e eventi RAW<br />-Rilevamento di messaggi di posta elettronica, allegati e collegamenti | -Cassette postali<br />-Account di Office 365 |
| Azure ATP | -Segnali di Active Directory, inclusi gli eventi di autenticazione<br />-Rilevamento comportamentale relativo all'identità | Identità |
| Microsoft Cloud App Security | -Rilevamento di applicazioni e servizi cloud non autorizzati (Shadow IT)<br />-Esposizione dei dati alle app del cloud<br />-Attività di minacce associate alle app Cloud | App cloud |

## <a name="deploy-the-services"></a>Distribuire i servizi
La distribuzione di ogni servizio in genere richiede il provisioning del tenant e una configurazione iniziale. Vedere la tabella seguente per comprendere in che modo ognuno di questi servizi è distribuito.

| Servizio | Istruzioni per il provisioning | Configurazione iniziale |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Guida alla distribuzione di ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Vedere Provisioning instructions* |
| Office 365 ATP | *None, provisioning con Office 365* | [Configurare i criteri ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Guida introduttiva: creare l'istanza di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Vedere Provisioning instructions* |
| Microsoft Cloud App Security | *Nessuna* | [Guida introduttiva: Introduzione a Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Dopo aver distribuito i servizi supportati, [abilitare Microsoft Threat Protection](mtp-enable.md).

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica su Microsoft Threat Protection](microsoft-threat-protection.md)
- [Attivare Microsoft Threat Protection](mtp-enable.md)
- [Panoramica di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Panoramica di Office 365 ATP](../office-365-security/office-365-atp.md)
- [Panoramica di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
