---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.openlocfilehash: d6e669ecb2e00158dd3ce6712014244fa2f081c9
ms.sourcegitcommit: b838e1dc7a98fcce1bdf7b76173f5f04f16be703
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "30175778"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop

Dopo aver apportato le modifiche alle categorie di impostazioni e aver eseguito una distribuzione, è possibile distribuire e registrare lo stato di avanzamento per la distribuzione in stato di distribuzione. In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile. Aprire una categoria di impostazioni per visualizzare tutte le distribuzioni e i relativi dettagli, per distribuire le modifiche. 

## <a name="deployment-statuses"></a>Stati di distribuzione 

Queste sono le statue che verranno visualizzate per ogni distribuzione.

Stato  | Descrizione 
--- | --- 
Distribuzione | La modifica è in attesa di essere distribuita su questo anello.
In corso | La modifica viene applicata ai dispositivi attivi in questo anello. 
Completa | La modifica completata su tutti i dispositivi attivi in questo anello. 
Failed | La modifica ha avuto esito negativo su un 10% dei dispositivi attivi sul ring, quindi la distribuzione è stata interrotta.<br><br> Una richiesta di supporto verrà aperta automaticamente con le operazioni di Microsoft Managed Desktop per la risoluzione dei problemi relativi alla distribuzione. 
Ripristinati | La modifica è stata ripristinata all'Ultima modifica che è stata distribuita correttamente in tutti gli anelli di distribuzione.

## <a name="deploy-changes"></a>Distribuire le modifiche

In queste istruzioni viene visualizzata l'immagine di sfondo del desktop. Dopo aver organizzato una distribuzione, è necessario distribuire le modifiche dallo stato di distribuzione. 

**Per distribuire le modifiche**

1. Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)
2. In **Impostazioni**, selezionare **** configurabile.
3. In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.
4. Fare **** clic su Distribuisci per distribuire la modifica a uno degli anelli di distribuzione.

![Panoramica dello stato di distribuzione delle impostazioni conFigurabili](images/deploy-cs-overview.png)

Microsoft Managed Desktop consiglia la distribuzione agli anelli di distribuzione nell'ordine seguente: test, First, Fast e then Broad. 

Quando le modifiche vengono completate in ogni anello, lo stato diventa **completo**.

![Completamento della distribuzione delle impostazioni conFigurabili](images/config-setting-complete.png)

## <a name="revert-deployment"></a>Ripristinare la distribuzione

In queste istruzioni viene visualizzata l'immagine di sfondo del desktop. 

Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**. Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta. L'impostazione ritornerà all'ultima versione distribuita in tutti gli anelli. 

**Per annullare una modifica**
1. Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)
2. In **Impostazioni**, selezionare **** configurabile.
3. Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.
4. In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.

![Ripristinare la distribuzione delle impostazioni conFigurabili](images/config-setting-revert.png) 

## <a name="additional-resources"></a>Risorse aggiuntive
- [Panoramica delle impostazioni conFigurabili](config-setting-overview.md)
- [Informazioni di riferimento sulle impostazioni conFigurabili](config-setting-ref.md) 