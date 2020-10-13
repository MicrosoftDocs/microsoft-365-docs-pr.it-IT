---
title: Valutare Microsoft Threat Protection
description: Configurare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
keywords: Valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, Microsoft Threat Protection Lab, Microsoft Threat Protection Pilot, Cyber Security, Advanced Persistent Threat, Enterprise Security, Devices, Device, Identity, Users, data, Applications, Incidents, Automatic Investigation and remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447120"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Creare un laboratorio di valutazione di Microsoft Threat Protection o un ambiente pilota 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Lo scopo della creazione di questo laboratorio di valutazione o dell'ambiente pilota è di illustrare le funzionalità complete e integrate di Microsoft Threat Protection. Sperimentare come questa soluzione di sicurezza intelligente rileva, impedisce, indaga automaticamente e risponde alle minacce avanzate dell'organizzazione. 

In questa guida vengono illustrati i passaggi necessari per avviare la valutazione di Microsoft Threat Protection in base ai percorsi di distribuzione consigliati. L'obiettivo è facilitare la configurazione della soluzione di sicurezza in un ambiente lab con un account di prova oppure in un ambiente pilota in produzione con una licenza completa. La preparazione del Lab di valutazione o dell'ambiente pilota può fornire informazioni sui casi di utilizzo delle operazioni di sicurezza ai responsabili decisionali nell'organizzazione. Al termine dell'esecuzione delle simulazioni di attacco e soddisfatte dei risultati, è possibile distribuirlo e operazionalizzare completamente nell'organizzazione con l'ausilio di professionisti o esperti di Microsoft Technical Sales nella propria organizzazione. 

Questa guida ti aiuterà a:
- Configurare il server e i computer lab
- Configurare Active Directory con utenti e gruppi
- Configurazione e configurazione di Azure ATP, Office ATP, Microsoft Defender ATP e Microsoft cloud app Security
- Impostare i criteri locali per il server e i computer
- Simulare un attacco di minacce per generare un evento o un avviso di testing in Microsoft Threat Protection

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.


## <a name="deployment-phases"></a>Fasi di distribuzione

Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la relativa distribuzione:

|Fase | Descrizione | 
|:-------|:-----|
| ![Fase 1: preparazione](../../media/prepare.png)<br>[Fase 1: preparazione](prepare-mtpeval.md)| Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft Threat Protection in un laboratorio di valutazione o in un ambiente pilota: <br><br>-Parti interessate e disconnessione <br> -Considerazioni sull'ambiente <br>-Access <br>-Configurazione di Azure Active Directory <br> -Ordine di configurazione
|  ![Fase 2: installazione](../../media/setup.png) <br>[Fase 2: installazione](setup-mtpeval.md)|  Eseguire la procedura iniziale per accedere al centro sicurezza Microsoft 365 per configurare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota. Verrà visualizzata la guida per:<br><br>-Iscriversi alla versione di valutazione di Microsoft 365 E5 <br>  -Configurare il dominio<br>-Assegnare licenze Microsoft 365 E5<br>-Completare l'installazione guidata nel portale|
|  ![Fase 3: configurare & onboard](../../media/config-onboard.png) <br>[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro di Microsoft Threat Protection e gli endpoint di bordo. Verrà visualizzata la guida per:<br><br>-Configurare Office 365 Advanced Threat Protection<br>-Configurare Microsoft cloud app Security<br>-Configurare Azure Advanced Threat Protection<br>-Configurare Microsoft Defender Advanced Threat Protection 


## <a name="in-scope"></a>Nell'ambito

Le attività seguenti rientrano nell'ambito di questa guida:
-   Configurare Azure Active Directory
-   Configurare Microsoft Threat Protection
    -   Iscriversi a Microsoft 365 E5 trial o utilizzare la licenza completa se si sta eseguendo un progetto pilota
    -   Configurare il dominio
    -   Assegnare le licenze Microsoft 365 E5
    -   Completamento dell'installazione guidata all'interno del portale
-   Configurare tutti i pilastri di protezione dalle minacce Microsoft in base alle procedure consigliate
    -   Office 365 Advanced Threat Protection
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Microsoft Defender Advanced Threat Protection

## <a name="out-of-scope"></a>Esclusioni

Di seguito sono riportate le seguenti condizioni:

-   Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft Threat Protection
-   Test di penetrazione nell'ambiente di produzione

## <a name="next-step"></a>Passaggio successivo
![Fase 1: preparazione](../../media/prepare.png) <br>[Fase 1: preparazione](prepare-mtpeval.md) 
<br> Preparare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota
