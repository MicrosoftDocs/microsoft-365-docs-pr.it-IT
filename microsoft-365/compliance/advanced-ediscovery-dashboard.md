---
title: Advanced eDiscovery dashboard per i set di revisione
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Usa il dashboard Advanced eDiscovery per i set di revisione per analizzare rapidamente il corpo per identificare le tendenze o le statistiche chiave che ti aiuteranno a sviluppare la strategia di revisione.
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741702"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Advanced eDiscovery dashboard per i set di revisione

Per alcuni casi in Advanced eDiscovery, potrebbe essere necessario esaminare un volume elevato di documenti e messaggi di posta elettronica. Prima di avviare il processo di revisione, è possibile analizzare rapidamente il corpo per identificare le tendenze o le statistiche chiave che consentono di sviluppare la strategia di revisione. A tale scopo, è possibile usare il dashboard di Advanced eDiscovery per i set di revisione per analizzare rapidamente il corpo.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Passaggio 1: Creare un widget nel dashboard del set di revisione

1. Nel Centro sicurezza & conformità passare a **eDiscovery > Advanced eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione.
  
2. Selezionare un caso esistente.
  
3. Fare clic **sulla scheda Revisione** set e quindi selezionare un set di recensioni.
  
4. Nell'elenco a discesa **Singoli risultati**, fare clic su **Visualizzazione profilo di ricerca**. 

   ![DashbordPivot](../media/dashboardpivot.png)

   Viene **visualizzata la** pagina Visualizzazione profilo di ricerca. la prima volta che si visualizza questa pagina, vengono visualizzati tre widget predefiniti.

   ![Dashboard](../media/dashboardonly.png)
  
5. Fare clic **sul widget Nuovo** e quindi selezionare uno degli elementi seguenti:

   ![Nuovo elenco a discesa widget](../media/NewWidgetDropdownBox.png)

   - **Scegli dalla raccolta:** Visualizza una raccolta predefinita di widget. Si fa clic su un widget e quindi **si** fa clic su Aggiungi per aggiungerlo ai widget nella pagina Visualizzazione **profilo di** ricerca.
  
   - **Crea widget personalizzato:** Visualizza una pagina a comparsa che è possibile utilizzare per configurare un widget personalizzato. 

6. Per creare un widget personalizzato, eseguire le operazioni seguenti nella pagina a comparsa Aggiungi **widget:**

   ![Crea widget](../media/addwidget.png)

    a. Digitare un nome per il widget, visualizzato nella barra del titolo del widget. È necessario assegnare un nome a un widget, ma è utile identificare i dati del widget.

    b. Selezionare una proprietà **nell'elenco a** discesa Scegli pivot che verrà utilizzata per i dati del widget. Gli elementi di questo elenco sono le proprietà disponibili per la ricerca per gli elementi nel set di recensioni. Per una descrizione di queste proprietà, vedere [Campi di metadati del documento in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). Le opzioni pivot per il widget sono elencate nella colonna **Nome campo** ricercabile in questo argomento.

    c. Selezionare un tipo di grafico per visualizzare i dati della proprietà pivot selezionata.

  6. Fare **clic su** Aggiungi per creare il widget personalizzato e visualizzarlo nella pagina Visualizzazione profilo **di** ricerca.

## <a name="step-2-create-a-review-set-search-query"></a>Passaggio 2: Creare una query di ricerca set di revisione

1. Fare **clic su ...** sulla barra del titolo del widget e quindi su Applica **condizione.**

   ![Dashboard](../media/searchprofilehome.png)

2. Nella pagina a comparsa fare clic su un elemento del grafico a chiave del widget o del widget per creare un filtro.

   ![CreateFilter](../media/applyconditionfilter.png)

3. Ripetere i passaggi da 1 a 2 per altri widget più widget. 

4. Al termine, fare clic su Salva **come query** per salvare le condizioni come nuova query di ricerca per il set di revisioni.

   ![Query](../media/savequery.png)

5. Chiudere la **visualizzazione profilo di ricerca** per tornare alla visualizzazione dei risultati della ricerca.

   Se sono stati creati filtri visivi, la query risultante viene applicata ai risultati della ricerca visualizzati e la query di ricerca salvata nel passaggio 4 viene visualizzata in **Query salvate**. Per ulteriori informazioni sulle query di set di revisione, vedere [Query the data in a review set](review-set-search.md).
