---
title: Esaminare i requisiti e i concetti chiave dell'architettura di Microsoft Defender per endpoint
description: Il diagramma tecnico per Microsoft Defender for Endpoint in Microsoft 365 Defender ti aiuterà a comprendere l'identità in Microsoft 365 prima di creare il laboratorio di valutazione o l'ambiente pilota.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458128"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Esaminare i requisiti e i concetti chiave dell'architettura di Microsoft Defender per endpoint

**Si applica a:** Microsoft 365 Defender

Questo articolo ti guiderà nel processo di configurazione della valutazione per Microsoft Defender per l'ambiente endpoint.

Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-endpoint-overview.md).

Prima di abilitare Microsoft Defender per Endpoint, assicurati di aver compreso l'architettura e di poter soddisfare i requisiti.

## <a name="understand-the-architecture"></a>Informazioni sull'architettura

Il diagramma seguente illustra l'architettura e le integrazioni di Microsoft Defender for Endpoint. 

![Passaggi per l'aggiunta di Microsoft Defender per Office all'ambiente di valutazione di Defender](../../media/defender/m365-defender-endpoint-architecture.png)

Nella tabella seguente viene descritta l'illustrazione.

Call-out | Descrizione
:---|:---|
1 | I dispositivi sono a bordo tramite uno degli strumenti di gestione supportati. 
2  | I dispositivi a bordo forniscono e rispondono ai dati del segnale di Microsoft Defender for Endpoint.
3  | I dispositivi gestiti vengono aggiunti e/o registrati in Azure Active Directory.
4  | I dispositivi Windows 10 aggiunti a un dominio vengono sincronizzati con Azure Active Directory tramite Azure Active Directory Connessione.
5  | Gli avvisi, le indagini e le risposte di Microsoft Defender per endpoint vengono gestiti in Microsoft 365 Defender.

## <a name="understand-key-concepts"></a>Comprendere i concetti chiave

Nella tabella seguente sono stati identificati i concetti chiave importanti da comprendere durante la valutazione, la configurazione e la distribuzione di Microsoft Defender per Endpoint: 

Concetti | Descrizione | Ulteriori informazioni
:---|:---|:---|
Portale di amministrazione | Microsoft 365 Defender portale per monitorare e aiutare a rispondere agli avvisi di potenziali attività avanzate di minacce persistenti o violazioni dei dati. | [Panoramica del portale di Microsoft Defender for Endpoint](/defender-endpoint/portal-overview)
Riduzione della superficie di attacco | Aiuta a ridurre le superfici di attacco riducendo al minimo i luoghi in cui l'organizzazione è vulnerabile a minacce informatiche e attacchi. | [Panoramica della riduzione della superficie di attacco](/defender-endpoint/overview-attack-surface-reduction)
Rilevamento e risposta degli endpoint | Le funzionalità di risposta e rilevamento degli endpoint offrono rilevamenti di attacchi avanzati quasi in tempo reale e utilizzabili. | [Panoramica delle funzionalità di rilevamento e risposta degli endpoint](/defender-endpoint/overview-endpoint-detection-response)
Blocco e contenimento comportamentali | Le funzionalità di blocco e contenimento comportamentali possono aiutare a identificare e arrestare le minacce, in base ai comportamenti e agli alberi di processo, anche quando la minaccia ha iniziato l'esecuzione. | [Blocco e contenimento comportamentale](/defender-endpoint/behavioral-blocking-containment)
Analisi e risposta automatizzate | L'indagine automatizzata utilizza vari algoritmi di ispezione basati su processi utilizzati dagli analisti della sicurezza e progettati per esaminare gli avvisi e intervenire immediatamente per risolvere le violazioni. | [Usare indagini automatizzate per analizzare e correggere le minacce](/defender-endpoint/automated-investigations)
Rilevazione avanzata | La ricerca avanzata è uno strumento di ricerca delle minacce basato su query che consente di esplorare fino a 30 giorni di dati non elaborati in modo da poter esaminare in modo proattivo gli eventi nella rete per individuare gli indicatori e le entità delle minacce. | [Panoramica della ricerca avanzata](/defender-endpoint/advanced-hunting-overview)
Analisi delle minacce | L'analisi delle minacce è una serie di report di esperti ricercatori di sicurezza Microsoft che coprono le minacce più rilevanti. | [Monitorare e rispondere alle nuove minacce](/defender-endpoint/threat-analytics)


Per informazioni più dettagliate sulle funzionalità incluse in Microsoft Defender for Endpoint, vedi Che cos'è [Microsoft Defender per Endpoint](/defender-endpoint/microsoft-defender-endpoint).

## <a name="siem-integration"></a>Integrazione SIEM

Puoi integrare Microsoft Defender for Endpoint con Azure Sentinel per analizzare in modo più completo gli eventi di sicurezza all'interno dell'organizzazione e creare playbook per una risposta efficace e immediata. 

Microsoft Defender for Endpoint può anche essere integrato in altre soluzioni SIEM (Security Information and Event Management). Per altre informazioni, vedi [Abilitare l'integrazione SIEM in Microsoft Defender per Endpoint.](/defender-endpoint/enable-siem-integration)


## <a name="next-steps"></a>Passaggi successivi
[Abilitare la valutazione](eval-defender-endpoint-enable-eval.md)

Torna alla panoramica per [valutare Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)