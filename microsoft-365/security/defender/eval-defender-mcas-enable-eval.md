---
title: Abilitare l'ambiente di valutazione per Microsoft Cloud App Security
description: Informazioni sull'architettura di MCAS in Microsoft Defender per Office 365 e comprendere le interazioni tra i Microsoft 365 Defender prodotti.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458050"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>Abilitare l'ambiente di valutazione per Microsoft Cloud App Security


**Si applica a:**

- Microsoft 365 Defender

Questo articolo è [il passaggio 2 di 2](eval-defender-mcas-overview.md) nel processo di configurazione dell'ambiente di valutazione per Microsoft Cloud App Security. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-mcas-overview.md).

Questo articolo illustra il processo di accesso al portale Cloud App Security e la configurazione dell'integrazione necessaria per raccogliere i dati sul traffico delle app cloud.

Per individuare le app cloud usate nell'ambiente, è possibile eseguire una o entrambe le operazioni seguenti:

- Iniziare rapidamente a utilizzare Cloud Discovery integrandosi con Microsoft Defender for Endpoint. Questa integrazione nativa consente di avviare immediatamente la raccolta di dati sul traffico cloud nei dispositivi Windows 10, all'interno e all'uscita dalla rete.
- Per individuare tutte le app cloud accessibili da tutti i dispositivi connessi alla rete, distribuire l'Cloud App Security di log nei firewall e in altri proxy. In questo modo vengono raccolti i dati dagli endpoint e inviati a Cloud App Security per l'analisi. Cloud App Security si integra in modo nativo con alcuni proxy di terze parti per altre funzionalità.

Questo articolo include indicazioni per entrambi i metodi.

Eseguire la procedura seguente per configurare Microsoft Cloud App Security.

![Passaggi per abilitare Microsoft Microsoft Cloud App Security nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [Passaggio 1. Connessione al portale Cloud App Security](#step-1-connect-to-the-cloud-app-security-portal)
- [Passaggio 2. Integrazione con Microsoft Defender for Endpoint](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [Passaggio 3. Distribuire l'Cloud App Security di log nei firewall e in altri proxy](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [Passaggio 4. Visualizzare il dashboard di Cloud Discovery per sapere quali app vengono usate nell'organizzazione](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>Passaggio 1. Connessione al portale Cloud App Security

Per verificare le licenze e connettersi al portale Cloud App Security, vedere [Guida introduttiva:](/cloud-app-security/getting-started-with-cloud-app-security)Introduzione a Microsoft Cloud App Security . 

Se non si è immediatamente in grado di connettersi al portale, potrebbe essere necessario aggiungere l'indirizzo IP all'elenco consenti del firewall. Vedere [Configurazione di base per Cloud App Security](/cloud-app-security/general-setup).

Se il problema persiste, vedere Requisiti [di rete.](/cloud-app-security/network-requirements)

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Passaggio 2. Integrazione con Microsoft Defender for Endpoint

Microsoft Cloud App Security si integra in modo nativo con Microsoft Defender for Endpoint. L'integrazione semplifica l'implementazione di Cloud Discovery, estende le funzionalità di Cloud Discovery oltre la rete aziendale e consente l'analisi basata su dispositivi. Questa integrazione rivela le app cloud e i servizi a cui si accede da dispositivi Windows 10 IT. 

Se hai già configurato Microsoft Defender per Endpoint, la configurazione dell'integrazione con Cloud App Security è un interruttore in Microsoft 365 Defender. Dopo aver attivato l'integrazione, è possibile tornare al portale Cloud App Security e visualizzare dati rtf nel dashboard di individuazione cloud.

Per eseguire queste attività, vedi [Integrazione di Microsoft Defender per Endpoint con Microsoft Cloud App Security](/cloud-app-security/mde-integration). 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>Passaggio 3. Distribuire l'Cloud App Security di log nei firewall e in altri proxy

Per la copertura su tutti i dispositivi connessi alla rete, distribuire l'agente di raccolta log di Cloud App Security nei firewall e in altri proxy per raccogliere i dati dagli endpoint e inviarli a Cloud App Security per l'analisi. 

Se si utilizza uno dei seguenti gateway Web protetti (SWG), Cloud App Security la distribuzione e l'integrazione senza problemi:
- Zscaler
- iboss
- Corrata
- Menlo Security

Per ulteriori informazioni sull'integrazione con questi dispositivi di rete, vedere [Set up Cloud Discovery.](/cloud-app-security/set-up-cloud-discovery) 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Passaggio 4. Visualizzare il dashboard di Cloud Discovery per sapere quali app vengono usate nell'organizzazione

Il dashboard di Cloud Discovery è progettato per fornire informazioni più approfondite sull'uso delle app cloud nell'organizzazione. Fornisce una panoramica generale dei tipi di app in uso, degli avvisi aperti e dei livelli di rischio delle app nell'organizzazione. 

Per iniziare a usare il dashboard di Cloud Discovery, vedi [Uso delle app individuate.](/cloud-app-security/discovered-apps)

## <a name="next-steps"></a>Passaggi successivi

Passaggio 3 di 3: [test pilota Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

Tornare alla panoramica di [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)