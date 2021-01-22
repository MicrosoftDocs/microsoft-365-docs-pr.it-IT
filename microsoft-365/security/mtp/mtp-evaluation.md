---
title: Valutare Microsoft 365 Defender
description: Configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
keywords: Versione di valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, laboratorio di valutazione di Microsoft Threat Protection, pilota di Microsoft Threat Protection, cyber security, minacce persistenti avanzate, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, eventi imprevisti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930211"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Creare un ambiente pilota o un lab di valutazione di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


Questa guida consente di lavorare nella configurazione di un ambiente lab con utenti e gruppi, quindi guida l'utente attraverso la configurazione delle funzionalità in Microsoft 365 Defender in modo da poter simulare un attacco di minaccia e ottenere un risultato di prova significativo. 

Lo scopo della creazione di questo laboratorio di valutazione o ambiente pilota è illustrare le funzionalità complete e integrate di Microsoft 365 Defender. Scopri come questa soluzione di sicurezza intelligente rileva, impedisce, analizza automaticamente e risponde alle minacce avanzate dell'organizzazione. 


You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths. L'obiettivo è quello di aiutare a configurare la soluzione di sicurezza in un ambiente lab con un account di prova o in un ambiente pilota in produzione con una licenza completa. La preparazione del laboratorio di valutazione o dell'ambiente pilota può essere utile per presentare i casi d'uso delle operazioni di sicurezza ai decisori dell'organizzazione. Al termine dell'esecuzione delle simulazioni di attacco e si è soddisfatti dei risultati, è possibile distribuirlo e operarlo completamente nell'organizzazione con l'aiuto di tecnici o esperti dell'organizzazione. 

Questa guida ti aiuterà a:
- Configurare il server lab e i computer
- Configurare Active Directory con utenti e gruppi
- Configurare Microsoft Defender per l'identità, Microsoft Defender per Office 365, Microsoft Defender per Endpoint e Microsoft Cloud App Security
- Configurare i criteri locali per il server e i computer
- Simulare un attacco di minaccia per generare un evento imprevisto o un avviso di test in Microsoft 365 Defender

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni di configurazione del lab il più possibile.


## <a name="deployment-phases"></a>Fasi di distribuzione

La creazione di un ambiente lab di valutazione di Microsoft 365 Defender è in tre fasi.

![Fasi di distribuzione: preparazione, configurazione, onboard](../../media/evaluation-guide-phases.png)

|Fase | Descrizione | 
|:-------|:-----|
|[Fase 1: preparazione](prepare-mtpeval.md)| Informazioni su cosa è necessario considerare quando si distribuisce Microsoft 365 Defender in un ambiente di prova o pilota: <br><br>- Parti interessate e disconnessione <br> - Considerazioni sull'ambiente <br>- Access <br>- Configurazione di Azure Active Directory <br> - Ordine di configurazione
|[Fase 2: installazione](setup-mtpeval.md)|  Eseguire i passaggi iniziali per accedere al Centro sicurezza Microsoft 365 per configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender. Verrà indicato come:<br><br>- Iscriversi alla versione di valutazione di Microsoft 365 E5 <br>  - Configurare il dominio<br>- Assegnare le licenze di Microsoft 365 E5<br>- Completare la configurazione guidata nel portale|
|[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro di Microsoft 365 Defender e gli endpoint di onboard. Verrà indicato come:<br><br>- Configurare Microsoft Defender per Office 365<br>- Configurare Microsoft Cloud App Security<br>- Configurare Microsoft Defender per l'identità<br>- Configurare Microsoft Defender per Endpoint


Dopo aver completato questa guida, si avrebbero identificato i cointeressati coinvolti e le approvazioni necessarie, avere le autorizzazioni di accesso corrette, aver effettuato la registrazione per la versione di valutazione, configurato i domini e ognuno dei pilastri di Microsoft 365 Defender e gli endpoint verranno onboarded al servizio.

## <a name="key-capabilities"></a>Caratteristiche chiave

Anche se Microsoft 365 Defender offre molte funzionalità, lo scopo principale di questa guida alla distribuzione è quello di iniziare a usare i dispositivi di onboarding. Oltre all'onboarding, queste indicazioni ti consentono di iniziare con le funzionalità seguenti.


Funzionalità | Descrizione 
:---|:---
Microsoft Defender per Office 365 | Aiuta a proteggere l'intero ambiente di Office 365 dalle minacce odierne
Che cosa è Microsoft Defender per identità? | Identifica e rileva le minacce alle identità compromesse e alle azioni Insider dannose.
Microsoft Cloud App Security | Offre visibilità completa, controlla il viaggio dei dati e rileva le minacce informatiche nei servizi cloud.
Microsoft Defender per endpoint | Impedisce, rileva e fornisce funzionalità di risposta alle minacce avanzate con sicurezza completa degli endpoint.


## <a name="in-scope"></a>Nell'ambito

L'ambito di questa guida è quello delle attività seguenti:
-   Configurare Azure Active Directory
-   Configurare Microsoft 365 Defender
    -   Iscriversi alla versione di valutazione di Microsoft 365 E5 o usare la licenza completa se si esegue un progetto pilota
    -   Configurare il dominio
    -   Assegnare licenze di Microsoft 365 E5
    -   Completamento dell'installazione guidata all'interno del portale
-   Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate
    -   Microsoft Defender per Office 365
    -   Che cosa è Microsoft Defender per identità?
    -   Microsoft Cloud App Security
    -   Microsoft Defender per endpoint

## <a name="out-of-scope"></a>Esclusioni

Gli elementi seguenti non sono disponibili nell'ambito di questa guida alla distribuzione:

-   Configurazione di soluzioni di terze parti che potrebbero integrarsi con Microsoft 365 Defender
-   Test di penetrazione nell'ambiente di produzione

## <a name="next-step"></a>Passaggio successivo
[Fase 1: preparazione](prepare-mtpeval.md) 
<br> Preparare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender
