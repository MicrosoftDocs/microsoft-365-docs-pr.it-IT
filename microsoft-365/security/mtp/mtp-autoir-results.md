---
title: Visualizzare i dettagli e i risultati di un'indagine automatizzata
description: Durante e dopo un'indagine automatizzata, è possibile visualizzare i risultati principali
keywords: automatizzata, indagine, risultati, analizzare, dettagli, correzione, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 062dd86de49eb3dfe47566aa8d7269780cf9995c
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175719"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>Visualizzare i dettagli e i risultati di un'indagine automatizzata

**Si applica a:**
- Microsoft Threat Protection

Quando si verifica un'indagine automatizzata in Microsoft Threat Protection, i dettagli di tale indagine sono disponibili durante e dopo il processo di indagine automatizzata. Se di dispone delle [autorizzazioni necessarie](mtp-action-center.md#required-permissions-for-action-center-tasks), è possibile visualizzare i dettagli in una visualizzazione dei dettagli dell'indagine. La vista dei dettagli dell'indagine consente di avere uno stato aggiornato e la possibilità di approvare eventuali azioni in sospeso. 

![Dettagli indagine](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>Aprire la visualizzazione dei dettagli dell'indagine

È possibile aprire la visualizzazione dei dettagli dell'indagine utilizzando uno dei metodi seguenti:
- [Selezionare un elemento nel centro notifiche](#select-an-item-in-the-action-center)
- [Selezionare un'indagine dalla pagina dei dettagli dell'incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Selezionare un elemento nel centro notifiche

Usare il centro notifiche per visualizzare le azioni in attesa di approvazione (nella scheda **In sospeso**) o quelle già approvate (nella scheda **Cronologia**). 

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 

2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

3. Nella scheda **In sospeso** o **Cronologia**, selezionare un elemento. Se si dispone delle [autorizzazioni necessarie](mtp-action-center.md#required-permissions-for-action-center-tasks), è possibile approvare (o rifiutare) le azioni in sospeso.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Aprire un'indagine dalla pagina dei dettagli dell'incidente

Utilizzare una pagina dei dettagli di un incidente per visualizzare informazioni dettagliate relative a un incidente, inclusi gli avvisi che sono stati attivati, le informazioni su eventuali dispositivi, gli account utente o le cassette postali interessati.

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 

2. Nel riquadro di spostamento, scegliere **Incidenti**. 

3. Selezionare un elemento nell'elenco per aprire la visualizzazione dei dettagli dell'evento.<br/>![Dettagli incidente](../../media/mtp-incidentdetails-tabs.png)

4. Nella scheda **Indagini**, selezionare un'indagine nell'elenco.

## <a name="investigation-details"></a>Dettagli indagine

Utilizzare la vista dei dettagli dell'indagine per visualizzare le attività passate, attuali e in sospeso relative a un'indagine. La visualizzazione dei dettagli dell'indagine è simile all'immagine seguente:

![Dettagli indagine](../../media/mtp-air-investdetails.png)

Nella visualizzazione dei dettagli dell'indagine, è possibile vedere le informazioni nelle schede **Grafico dell'indagine**, **Avvisi**, **Dispositivi**, **Identità**, **Risultati principali**, **Entità**, **Log**, e **Azioni in sospeso**, descritte nella tabella seguente.

|Scheda    |Descrizione |
|--------|--------|
|Grafico dell'indagine    |Fornisce una rappresentazione visiva dell'indagine. Descrive le entità ed elenca le minacce rilevate, insieme agli avvisi e alle eventuali azioni ancora in fase di approvazione.<br/>È possibile fare clic su un elemento del grafico per visualizzare ulteriori dettagli. Ad esempio, facendo clic sull'icona **Minacce rilevate** si verrà indirizzati alla scheda **Risultati principali**. |
|Avvisi |Elenca gli avvisi associati all'indagine. Gli avvisi possono provenire dalle funzionalità di protezione dalle minacce sul computer di un utente, dalle app di Office, da Cloud App Security e da altre funzionalità di protezione dalle minacce di Microsoft 365.|
|Dispositivi|Elenca i computer inclusi nell'indagine insieme al livello di correzione.|
|Risultati principali   |Elenca i risultati dell'indagine, insieme allo stato e alle azioni eseguite o in sospeso. In questa scheda è possibile approvare le azioni in sospeso per dispositivi e identità.|
|Entità   |Elenca le attività dell'utente, i file, i processi, i servizi, i driver, gli indirizzi IP e i metodi di persistenza associati all'indagine, insieme allo stato e alle azioni eseguite.|
|Log    |Fornisce una visualizzazione dettagliata di tutti i passaggi seguiti durante l'indagine, insieme allo stato.|
|Azioni in sospeso    |Elenca gli elementi che richiedono l'approvazione per continuare.|

## <a name="remediation-actions-following-automated-investigation"></a>Azioni correttive in seguito all'indagine automatizzata

Una volta completata un'indagine automatizzata, viene emesso un verdetto per ogni prova inclusa e vengono identificate le azioni correttive. In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle. Nella tabella seguente sono elencati i possibili verdetti e i risultati:

|Verdetto    |Area   |Risultati|
|------|------|------|
|Dannosa  |Dispositivi (endpoint)    |Le azioni correttive vengono eseguite automaticamente|
|Dannosa  |Contenuto della posta elettronica (URL o allegati) | Le azioni correttive consigliate sono in attesa di approvazione|
|Sospetta |Dispositivi o contenuto della posta elettronica |Le azioni correttive consigliate sono in attesa di approvazione|
|Pulita  |Dispositivi o contenuto della posta elettronica   |Non sono necessarie azioni correttive|

[Rivedere un'azione in sospeso nel centro notifiche](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Se si pensa che qualcosa è stato perso o rilevato erroneamente dalle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection, fatecelo sapere! Vedere [How to report false positives/negatives in Automatic Investigation and Response (Air) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Passaggi successivi

- [Panoramica delle autorizzazioni del centro notifiche](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate](mtp-autoir-actions.md)

