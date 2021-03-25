---
title: Valutare Microsoft 365 Defender
description: Configurare il laboratorio di valutazione o l'ambiente pilota di Microsoft 365 Defender per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
keywords: Versione di valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, microsoft threat protection pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068618"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Creare un ambiente pilota o un laboratorio di valutazione di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


Questa guida consente di configurare un ambiente lab con utenti e gruppi, quindi di illustrare la configurazione delle funzionalità in Microsoft 365 Defender in modo da poter simulare un attacco di minacce e ottenere un risultato di prova significativo. 

Lo scopo della creazione di questo laboratorio di valutazione o ambiente pilota è illustrare le funzionalità complete e integrate di Microsoft 365 Defender. Scopri come questa soluzione di sicurezza intelligente rileva, impedisce, analizza automaticamente e risponde alle minacce avanzate dell'organizzazione. 


Verrà illustrata la procedura per avviare la valutazione di Microsoft 365 Defender in base ai percorsi di distribuzione consigliati. L'obiettivo è quello di configurare la soluzione di sicurezza in un ambiente lab con un account di prova o in un ambiente pilota in produzione con una licenza completa. La preparazione del laboratorio di valutazione o dell'ambiente pilota può essere utile per presentare i casi di utilizzo delle operazioni di sicurezza ai decision maker dell'organizzazione. Al termine dell'esecuzione delle simulazioni di attacco e si è soddisfatti dei risultati, è possibile distribuirlo e operarlo completamente nell'organizzazione con l'aiuto di tecnici o esperti dell'organizzazione. 

Questa guida ti aiuterà a:
- Configurare il server lab e i computer
- Configurare Active Directory con utenti e gruppi
- Configurare Microsoft Defender per l'identità, Microsoft Defender per Office 365, Microsoft Defender for Endpoint e Microsoft Cloud App Security
- Configurare criteri locali per il server e i computer
- Simulare un attacco di minaccia per generare un evento imprevisto o un avviso di test in Microsoft 365 Defender

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni per la configurazione del lab il più possibile.


## <a name="deployment-phases"></a>Fasi di distribuzione

La creazione di un ambiente lab di valutazione di Microsoft 365 Defender è in tre fasi.

![Fasi di distribuzione: preparazione, installazione, onboard](../../media/evaluation-guide-phases.png)

|Fase | Descrizione | 
|:-------|:-----|
|[Fase 1: preparare](prepare-m365d-eval.md)| Informazioni su cosa è necessario considerare quando si distribuisce Microsoft 365 Defender in un laboratorio di valutazione o in un ambiente pilota: <br><br>- Parti interessate e disconnessione <br> - Considerazioni sull'ambiente <br>- Accesso <br>- Configurazione di Azure Active Directory <br> - Ordine di configurazione
|[Fase 2: installazione](setup-m365deval.md)|  Eseguire i passaggi iniziali per accedere al Centro sicurezza Microsoft 365 per configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender. Sarai guidato a:<br><br>- Iscriversi alla versione di valutazione di Microsoft 365 E5 <br>  - Configurare il dominio<br>- Assegnare le licenze di Microsoft 365 E5<br>- Completare la configurazione guidata nel portale|
|[Fase 3: configurare & onboard](config-m365d-eval.md) | Configurare ogni pilastro di Microsoft 365 Defender e gli endpoint di onboard. Sarai guidato a:<br><br>- Configurare Microsoft Defender per Office 365<br>- Configurare Microsoft Cloud App Security<br>- Configurare Microsoft Defender per l'identità<br>- Configurare Microsoft Defender per Endpoint


Dopo aver completato questa guida, si sarebbero identificate le parti interessate coinvolte e le approvazioni necessarie, avere le autorizzazioni di accesso corrette, aver effettuato la registrazione per la versione di valutazione, configurato i domini e ognuno dei pilastri di Microsoft 365 Defender e gli endpoint verranno onboarded al servizio.

## <a name="key-capabilities"></a>Caratteristiche chiave

Mentre Microsoft 365 Defender offre molte funzionalità, lo scopo principale di questa guida alla distribuzione è quello di iniziare a usare i dispositivi di onboarding. Oltre all'onboarding, questa guida ti consente di iniziare con le funzionalità seguenti.


Funzionalità | Descrizione 
:---|:---
Microsoft Defender per Office 365 | Aiuta a proteggere l'intero ambiente di Office 365 dalle minacce odierne
Microsoft Defender per identità | Identifica e rileva le minacce su identità compromesse e azioni insider dannose.
Microsoft Cloud App Security | Offre visibilità completa, controlla il viaggio dei dati e rileva le minacce informatiche nei servizi cloud.
Microsoft Defender ATP | Impedisce, rileva e fornisce funzionalità di risposta alle minacce avanzate con una sicurezza completa degli endpoint.


## <a name="in-scope"></a>Nell'ambito

Per questa guida sono disponibili le attività seguenti:
-   Configurare Azure Active Directory
-   Configurare Microsoft 365 Defender
    -   Iscriversi alla versione di valutazione di Microsoft 365 E5 o usare la licenza completa se si esegue un progetto pilota
    -   Configurare il dominio
    -   Assegnare licenze di Microsoft 365 E5
    -   Completamento dell'installazione guidata all'interno del portale
-   Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate
    -   Microsoft Defender per Office 365
    -   Microsoft Defender per identità
    -   Microsoft Cloud App Security
    -   Microsoft Defender ATP

## <a name="out-of-scope"></a>Esclusioni

Gli elementi seguenti non sono nell'ambito di questa guida alla distribuzione:

-   Configurazione di soluzioni di terze parti che potrebbero integrarsi con Microsoft 365 Defender
-   Test di penetrazione nell'ambiente di produzione

## <a name="next-step"></a>Passaggio successivo
[Fase 1: preparare](prepare-m365d-eval.md) 
<br> Preparare il laboratorio di valutazione o l'ambiente pilota di Microsoft 365 Defender
