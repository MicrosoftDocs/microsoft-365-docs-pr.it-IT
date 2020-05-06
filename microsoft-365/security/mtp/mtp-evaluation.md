---
title: Valutare Microsoft Threat Protection
description: Configurare l'ambiente di laboratorio di valutazione di Microsoft Threat Protection per provare come la soluzione coordinata di protezione dalle minacce progettata per proteggere dispositivi, identità, dati e applicazioni può aiutare l'organizzazione
keywords: Microsoft Threat Protection Trial, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, Microsoft Threat Protection Lab, sicurezza cibernetica, Advanced Persistent Threat, Enterprise Security, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi automatizzata e correzione, ricerca avanzata
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049640"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Creare un ambiente lab di valutazione di Microsoft Threat Protection 

**Si applica a:**
- Microsoft Threat Protection

Lo scopo della creazione di questo ambiente di laboratorio di valutazione consiste nell'illustrare le funzionalità complete, integrate e intelligenti di Microsoft Threat Protection in Detection, Prevention, Investigation e Response che è possibile utilizzare nell'organizzazione. 

In questa guida vengono illustrati i passaggi necessari per avviare la valutazione di Microsoft Threat Protection in base ai percorsi di distribuzione consigliati. L'obiettivo è facilitare la configurazione dei servizi di Microsoft Threat Protection integrati in un ambiente lab o come prova del concetto (POC) quando si presentano ai responsabili delle decisioni della soluzione di sicurezza nell'organizzazione. Dopo aver completato l'esecuzione delle simulazioni di attacco, l'analisi e la risposta automatizzate e sono soddisfatte con i risultati, è possibile distribuirla nell'ambiente di produzione con l'ausilio di professionisti o esperti di Microsoft Technical Sales all'interno dell'organizzazione. 

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
| ![Fase 1: preparazione](../../media/prepare.png)<br>[Fase 1: preparazione](prepare-mtpeval.md)| Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft Threat Protection in un ambiente di prova: <br><br>-Parti interessate e disconnessione <br> -Considerazioni sull'ambiente <br>-Access <br>-Configurazione di Azure Active Directory <br> -Ordine di configurazione
|  ![Fase 2: installazione](../../media/setup.png) <br>[Fase 2: installazione](setup-mtpeval.md)|  Eseguire la procedura iniziale per accedere a Microsoft 365 Security Center per configurare l'ambiente di valutazione di Microsoft Threat Protection. Verrà guidato per:<br><br>-Iscriversi alla versione di valutazione di Microsoft 365 E5 <br>  -Configurare il dominio<br>-Assegnare licenze Microsoft 365 E5<br>-Completare l'installazione guidata nel portale|
|  ![Fase 3: configurare & onboard](../../media/config-onboard.png) <br>[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro di Microsoft Threat Protection e gli endpoint di bordo. Verrà guidato per:<br><br>-Configurare Office 365 Advanced Threat Protection<br>-Configurare Microsoft cloud app Security<br>-Configurare Azure Advanced Threat Protection<br>-Configurare Microsoft Defender Advanced Threat Protection 


## <a name="in-scope"></a>Nell'ambito

Di seguito sono riportate le opzioni per questa guida all'ambiente lab di valutazione:
-   Configurare Azure Active Directory
-   Configurare Microsoft Threat Protection
    -   Iscriversi alla versione di valutazione di Microsoft 365 E5
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

-   Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft Defender ATP
-   Test di penetrazione nell'ambiente di produzione

## <a name="next-step"></a>Passaggio successivo
|||
|:-------|:-----|
|![Fase 1: preparazione](../../media/prepare.png) <br>[Fase 1: preparazione](prepare-mtpeval.md) | Preparare l'ambiente lab di valutazione di Microsoft Threat Protection
