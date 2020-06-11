---
title: Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Configurare l'infrastruttura di sicurezza e di servizio per proteggere le informazioni e attenersi alle normative sulla privacy dei dati.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695110"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365

Questa soluzione fornisce indicazioni su come pianificare e proteggere i dati personali archiviati nei servizi Microsoft 365 e potenzialmente soggetti alle normative sulla privacy dei dati, come il regolamento generale sulla protezione dei dati (GDPR) dell'Unione europea. Questa soluzione è incentrata sulle funzionalità di Microsoft Information Protection and Compliance, sul punteggio di conformità di Microsoft e sugli strumenti di valutazione che consentono di conoscere i dati. 
 
Sono inoltre disponibili ulteriori informazioni sull'utilizzo dei controlli Microsoft Identity, Device e Threat Protection per le esigenze relative alla privacy dei dati, nonché sugli strumenti per l'individuazione e la risposta degli incidenti di dati. 

## <a name="organization-of-this-guidance-material"></a>Organizzazione di questo materiale di orientamento

Per facilitare la comprensione degli strumenti di Microsoft 365 disponibili per identificare, gestire, controllare e monitorare i dati personali soggetti a una o più normative relative alla privacy, queste linee guida sono organizzate in sezioni.
 
![Distribuire protezione delle informazioni per le normative sulla privacy dei dati](../media/information-protection-deploy/information-protection-deploy-grid.png)

Ognuna di queste sezioni corrisponde a un articolo distinto della soluzione.

>[!Note]
>Se si ha già familiarità con gli obblighi relativi alla privacy dei dati e si esegue in base a un piano esistente, potrebbe essere necessario concentrarsi sulle indicazioni di prevenzione, protezione, conservazione e analisi.

>[!Important]
>Seguendo queste indicazioni non sarà necessariamente conforme a qualsiasi normativa sulla privacy dei dati, in particolare considerando il numero di passaggi necessari che non rientrano nel contesto delle caratteristiche. L'utente è responsabile per garantire la conformità e per consultare i propri team legali e di conformità o per richiedere indicazioni e consigli da terze parti specializzate in conformità.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Pianificare: valutare i rischi per la privacy dei dati e identificare gli elementi sensibili 

Valutare le normative sulla privacy dei dati e i rischi a cui l'organizzazione è soggetta è un primo passo importante da intraprendere prima di iniziare a implementare i miglioramenti, compresi quelli ottenibili tramite la configurazione di Microsoft 365. Ciò può includere una valutazione generale della conformità o l'identificazione di particolari tipi di informazioni sensibili che sono soggetti ai controlli normativi che l'organizzazione deve soddisfare, nonché la loro occorrenza nell'ambiente Microsoft 365.

Per ulteriori informazioni, vedere [valutare i rischi per la privacy dei dati e identificare gli elementi sensibili](information-protection-deploy-assess.md).

## <a name="track-use-compliance-score-and-compliance-manager"></a>Track: utilizzare la conformità score e Compliance Manager 

Score compliance e Compliance Manager offrono un set integrato di strumenti disponibili nell'interfaccia di amministrazione di Microsoft 365 compliance e nel portale di gestione dei servizi. Insieme, questi strumenti offrono una capacità integrata di monitorare e gestire le azioni di miglioramento complessive, nonché quelle relative a più normative sulla privacy dei dati a cui sono soggetti.

Gli strumenti consentono inoltre di utilizzare modelli di valutazione specifici per ogni regola, in cui è possibile tenere presenti gli elementi di azione per ogni modello di valutazione selezionato, nonché visualizzare controlli normativi specifici e correlarli a azioni specifiche.

Per ulteriori informazioni, vedere [use Compliance score and Compliance Manager to Manage Improvement actions](information-protection-deploy-compliance.md).

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Impedisci: utilizzare l'identità, il dispositivo e la protezione dalle minacce per la normativa sulla privacy dei dati

Microsoft 365 fornisce una serie di funzionalità di protezione delle minacce e delle identità che è possibile utilizzare per conformarsi alla conformità alle normative sulla privacy dei dati. 

Per ulteriori informazioni, vedere [use Identity, Device, and Threat Protection for data privacy Regulation](information-protection-deploy-identity-device-threat.md).

Questo articolo descrive brevemente cosa richiedono generalmente le normative sulla privacy dei dati in queste aree e fornisce un elenco delle soluzioni Microsoft 365 correlate, con collegamenti a ulteriori informazioni che consentono di soddisfare i requisiti di implementazione. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteggere le informazioni soggette alla normativa sulla privacy dei dati

Le normative sulla privacy dei dati prevedono una serie di controlli di protezione delle informazioni personali che possono essere utilizzati nel proprio ambiente, tra cui oltre 40 proteggere i controlli delle informazioni in tutte le quattro normative sulla privacy dei dati nel nostro set di GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States Health Care Act) e Brasile Data Protection Act (LGPD)

Per ulteriori informazioni, vedere [Protect Information subject to data privacy Regulation nell'organizzazione](information-protection-deploy-protect-information.md).

In questo articolo vengono illustrati i principali schemi di controllo che è possibile utilizzare per soddisfare le esigenze di protezione delle informazioni per la privacy dei dati nell'organizzazione.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Mantieni: regola le informazioni soggette alla normativa sulla privacy dei dati

Le normative sulla privacy dei dati richiedono controlli per la governance delle informazioni personali che possono essere utilizzati nel proprio ambiente, tra cui oltre ventiquattro controlli nelle quattro normative sulla privacy dei dati nel nostro set di esempi di GDPR, CCPA, HIPAA-HITECH e LGPD.

Per ulteriori informazioni, vedere [govern Information subject to data privacy Regulation nell'organizzazione](information-protection-deploy-govern.md).

Anche se le normative sulla privacy dei dati possono essere vaghe per quanto riguarda la governance delle informazioni &mdash; , come la conservazione, l'eliminazione e l'archiviazione mirate &mdash; in questo articolo vengono illustrati gli schemi di controllo principali che è possibile utilizzare per la privacy dei dati nell'organizzazione.

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>Esaminare: monitorare e rispondere alla normativa sulla privacy dei dati

Sono disponibili funzionalità di Microsoft 365 che consentono di monitorare, esaminare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione durante la operazionalizzare delle funzionalità correlate. 

L'utilizzo di processi, procedure e altre documentazioni per ognuna di queste operazioni può essere importante per dimostrare la conformità agli organismi di regolamentazione.

Per ulteriori informazioni, vedere [monitorare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione](information-protection-deploy-monitor-respond.md).
