---
title: Valutare Microsoft 365 Defender
description: Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
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
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659634"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Creare un laboratorio di valutazione di Microsoft 365 Defender o un ambiente pilota 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


In questa guida viene descritto come configurare un ambiente lab con utenti e gruppi, quindi è possibile eseguire la configurazione delle funzionalità di Microsoft 365 Defender per simulare un attacco di minacce e ottenere un risultato di prova significativo. 

Lo scopo della creazione di questo laboratorio di valutazione o di un ambiente pilota è quello di illustrare le funzionalità complete e integrate di Microsoft 365 Defender. Sperimentare come questa soluzione di sicurezza intelligente rileva, impedisce, indaga automaticamente e risponde alle minacce avanzate dell'organizzazione. 


L'utente verrà guidato tramite la procedura per avviare la valutazione di Microsoft 365 Defender in base ai percorsi di distribuzione consigliati. L'obiettivo è facilitare la configurazione della soluzione di sicurezza in un ambiente lab con un account di prova oppure in un ambiente pilota in produzione con una licenza completa. La preparazione del Lab di valutazione o dell'ambiente pilota può fornire informazioni sui casi di utilizzo delle operazioni di sicurezza ai responsabili decisionali nell'organizzazione. Al termine dell'esecuzione delle simulazioni di attacco e soddisfatte dei risultati, è possibile distribuirlo e operazionalizzare completamente nell'organizzazione con l'ausilio di professionisti o esperti di Microsoft Technical Sales nella propria organizzazione. 

Questa guida ti aiuterà a:
- Configurare il server e i computer lab
- Configurare Active Directory con utenti e gruppi
- Impostare e configurare Microsoft Defender per Identity, Microsoft Defender per Office 365, Microsoft Defender per endpoint e Microsoft cloud app Security
- Impostare i criteri locali per il server e i computer
- Simulare un attacco di minaccia per generare un avviso o un evento di prova in Microsoft 365 Defender

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.


## <a name="deployment-phases"></a>Fasi di distribuzione

Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft 365 Defender.

![Fasi di distribuzione: preparazione, installazione, Onboard](../../media/evaluation-guide-phases.png)

|Fase | Descrizione | 
|:-------|:-----|
|[Fase 1: preparazione](prepare-mtpeval.md)| Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft 365 Defender in un laboratorio di valutazione o in un ambiente pilota: <br><br>-Parti interessate e disconnessione <br> -Considerazioni sull'ambiente <br>-Access <br>-Configurazione di Azure Active Directory <br> -Ordine di configurazione
|[Fase 2: installazione](setup-mtpeval.md)|  Eseguire la procedura iniziale per accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota o il laboratorio di valutazione di Microsoft 365 Defender. Verrà visualizzata la guida per:<br><br>-Iscriversi alla versione di valutazione di Microsoft 365 E5 <br>  -Configurare il dominio<br>-Assegnare licenze Microsoft 365 E5<br>-Completare l'installazione guidata nel portale|
|[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro Microsoft 365 Defender e gli endpoint di bordo. Verrà visualizzata la guida per:<br><br>-Configurare Microsoft Defender per Office 365<br>-Configurare Microsoft cloud app Security<br>-Configurare Microsoft Defender per Identity<br>-Configurare Microsoft Defender per endpoint


Dopo aver completato questa guida, sono state identificate le parti interessate e le approvazioni necessarie, sono state apportate le autorizzazioni di accesso appropriate, sono state sottoscritte per il processo, i domini configurati e tutti i pilastri di Microsoft 365 Defender e gli endpoint verranno onboarded al servizio.

## <a name="key-capabilities"></a>Caratteristiche chiave

Anche se Microsoft 365 Defender fornisce molte funzionalità, lo scopo principale di questa guida alla distribuzione è iniziare con i dispositivi onboarding. Oltre all'onboarding, queste linee guida consentono di iniziare con le seguenti funzionalità.


Funzionalità | Descrizione 
:---|:---
Microsoft Defender per Office 365 | Consente di proteggere l'intero Office 365 ambiente dalle minacce odierne
Che cosa è Microsoft Defender per identità? | Identifica e rileva le minacce per le identità compromesse e le azioni Insider dannose.
Microsoft Cloud App Security | Offre una visibilità completa, il controllo dei dati di viaggio e rileva Cyberthreats tra i servizi cloud.
Microsoft Defender per endpoint | Impedisce, rileva e fornisce le funzionalità di risposta alle minacce avanzate con la sicurezza completa degli endpoint.


## <a name="in-scope"></a>Nell'ambito

Le attività seguenti rientrano nell'ambito di questa guida:
-   Configurare Azure Active Directory
-   Configurare Microsoft 365 Defender
    -   Iscriversi a Microsoft 365 E5 trial o utilizzare la licenza completa se si sta eseguendo un progetto pilota
    -   Configurare il dominio
    -   Assegnare le licenze Microsoft 365 E5
    -   Completamento dell'installazione guidata all'interno del portale
-   Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate
    -   Microsoft Defender per Office 365
    -   Che cosa è Microsoft Defender per identità?
    -   Microsoft Cloud App Security
    -   Microsoft Defender per endpoint

## <a name="out-of-scope"></a>Esclusioni

Di seguito sono riportate le seguenti condizioni:

-   Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft 365 Defender
-   Test di penetrazione nell'ambiente di produzione

## <a name="next-step"></a>Passaggio successivo
[Fase 1: preparazione](prepare-mtpeval.md) 
<br> Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota
