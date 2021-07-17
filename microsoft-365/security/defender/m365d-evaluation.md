---
title: Valutare Microsoft 365 Defender
description: Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458426"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Creare un ambiente Microsoft 365 Defender di prova o un ambiente pilota 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


Questa guida consente di configurare un ambiente lab con utenti e gruppi, quindi di illustrare la configurazione delle funzionalità di Microsoft 365 Defender in modo da poter simulare un attacco di minacce e ottenere un risultato di prova significativo. 

Lo scopo della creazione di questo laboratorio di valutazione o ambiente pilota è illustrare le funzionalità complete e integrate Microsoft 365 Defender test. Scopri come questa soluzione di sicurezza intelligente rileva, impedisce, analizza automaticamente e risponde alle minacce avanzate dell'organizzazione. 


Verrà illustrata la procedura per avviare la valutazione Microsoft 365 Defender in base ai percorsi di distribuzione consigliati. L'obiettivo è quello di configurare la soluzione di sicurezza in un ambiente lab con un account di prova o in un ambiente pilota in produzione con una licenza completa. La preparazione del laboratorio di valutazione o dell'ambiente pilota può essere utile per presentare i casi di utilizzo delle operazioni di sicurezza ai decision maker dell'organizzazione. Al termine dell'esecuzione delle simulazioni di attacco e si è soddisfatti dei risultati, è possibile distribuirlo e operarlo completamente nell'organizzazione con l'aiuto di tecnici o esperti dell'organizzazione. 

Questa guida ti aiuterà a:
- Configurare il server lab e i computer
- Configurare Active Directory con utenti e gruppi
- Configurare Microsoft Defender per l'identità, Microsoft Defender per Office 365, Microsoft Defender per Endpoint e Microsoft Cloud App Security
- Configurare criteri locali per il server e i computer
- Simulare un attacco di minaccia per generare un evento imprevisto o un avviso di test in Microsoft 365 Defender

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni per la configurazione del lab il più possibile.


## <a name="deployment-phases"></a>Fasi della distribuzione

La creazione di un ambiente lab di Microsoft 365 Defender di valutazione è Microsoft 365 Defender tre fasi.

![Fasi di distribuzione: preparazione, installazione, onboard](../../media/evaluation-guide-phases.png)

|Fase | Descrizione | 
|:-------|:-----|
|[Fase 1: preparazione](prepare-m365d-eval.md)| Informazioni su cosa è necessario considerare quando si distribuiscono Microsoft 365 Defender in un laboratorio di valutazione o in un ambiente pilota: <br><br>- Parti interessate e disconnessione <br> - Considerazioni sull'ambiente <br>- Accesso <br>- Azure Active Directory configurazione <br> - Ordine di configurazione
|[Fase 2: configurazione](setup-m365deval.md)|  Eseguire i passaggi iniziali per accedere Microsoft 365 Security Center per configurare il Microsoft 365 Defender di prova o l'ambiente pilota. Sarai guidato a:<br><br>- Iscriversi per la Microsoft 365 E5 prova <br>  - Configurare il dominio<br>- Assegnare Microsoft 365 E5 licenze<br>- Completare la configurazione guidata nel portale|
|[Fase 3: configurare & onboard](config-m365d-eval.md) | Configurare ogni Microsoft 365 Defender pilastro e gli endpoint di onboard. Sarai guidato a:<br><br>- Configurare Microsoft Defender per Office 365<br>- Configurare Microsoft Cloud App Security<br>- Configurare Microsoft Defender per l'identità<br>- Configurare Microsoft Defender per Endpoint


Dopo aver completato questa guida, si sarebbero identificate le parti interessate coinvolte e le approvazioni necessarie, avere le autorizzazioni di accesso corrette, aver effettuato la registrazione per la valutazione, configurato i domini e ognuno dei pilastri di Microsoft 365 Defender e gli endpoint verranno onboarded al servizio.

## <a name="key-capabilities"></a>Funzionalità chiave

Sebbene Microsoft 365 Defender offre molte funzionalità, lo scopo principale di questa guida alla distribuzione è iniziare a usare i dispositivi di onboarding. Oltre all'onboarding, questa guida ti consente di iniziare con le funzionalità seguenti.


Funzionalità | Descrizione 
:---|:---
Microsoft Defender per Office 365 | Aiuta a proteggere l Office 365 intero invidio dalle minacce di oggi
Microsoft Defender per identità | Identifica e rileva le minacce su identità compromesse e azioni insider dannose.
Microsoft Cloud App Security | Offre visibilità completa, controlla il viaggio dei dati e rileva le minacce informatiche nei servizi cloud.
Microsoft Defender per endpoint | Impedisce, rileva e fornisce funzionalità di risposta alle minacce avanzate con una sicurezza completa degli endpoint.


## <a name="in-scope"></a>Nell'ambito

Per questa guida sono disponibili le attività seguenti:
-   Configurare Azure Active Directory
-   Configurare Microsoft 365 Defender
    -   Iscriversi per Microsoft 365 E5 prova o usare la licenza completa se si esegue un progetto pilota
    -   Configurare il dominio
    -   Assegnare Microsoft 365 E5 licenze
    -   Completamento dell'installazione guidata all'interno del portale
-   Configurare tutti Microsoft 365 Defender pilastri in base alle procedure consigliate
    -   Microsoft Defender per Office 365
    -   Microsoft Defender per identità
    -   Microsoft Cloud App Security
    -   Microsoft Defender per endpoint

## <a name="out-of-scope"></a>Esclusioni

Gli elementi seguenti non sono nell'ambito di questa guida alla distribuzione:

-   Configurazione di soluzioni di terze parti che potrebbero integrarsi con Microsoft 365 Defender
-   Test di penetrazione nell'ambiente di produzione

## <a name="next-step"></a>Passaggio successivo
[Fase 1: preparare](prepare-m365d-eval.md) 
<br> Preparare il laboratorio di Microsoft 365 Defender o l'ambiente pilota
