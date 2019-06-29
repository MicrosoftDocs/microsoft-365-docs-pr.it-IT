---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: bfa769cab9f8d812fa2533232f66b0d4f8a4edb7
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390513"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop

Dopo aver apportato le modifiche alle categorie di impostazioni e a organizzare una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi. In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile. Aprendo una categoria di impostazione è possibile distribuire le impostazioni ai gruppi e monitorare lo stato di avanzamento di queste distribuzioni.

## <a name="deployment-statuses"></a>Stati di distribuzione 

Queste sono le statue che verranno visualizzate per ogni distribuzione.

Stato  | Spiegazione 
--- | --- 
Distribuzione | La modifica è in attesa di essere distribuita in questo gruppo.
In corso | La modifica viene applicata ai dispositivi attivi di questo gruppo. 
Completa | La modifica completata su tutti i dispositivi attivi di questo gruppo. 
Failed | La modifica ha avuto esito negativo su un 10% dei dispositivi attivi nel gruppo, quindi la distribuzione è stata interrotta.<br><br> Una richiesta di supporto verrà aperta automaticamente con le operazioni di Microsoft Managed Desktop per la risoluzione dei problemi relativi alla distribuzione. 
Ripristinati | La modifica è stata ripristinata all'Ultima modifica che è stata distribuita correttamente in tutti i gruppi di distribuzione.

## <a name="deploy-changes"></a>Distribuire le modifiche

In queste istruzioni viene visualizzata l'immagine di sfondo del desktop. Dopo aver organizzato una distribuzione, è necessario distribuire le modifiche dalla pagina Stato distribuzione. 

**Per distribuire le modifiche**

1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](http://aka.ms/mwaasportal)
2. In **Impostazioni**, selezionare **** configurabile.
3. In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.
4. Fare **** clic su Distribuisci per distribuire la modifica a uno dei gruppi di distribuzione.

![Panoramica dello stato di distribuzione delle impostazioni configurabili](images/deploy-cs-overview.png)

Microsoft Managed Desktop consiglia la distribuzione ai gruppi di distribuzione nell'ordine seguente: test, First, Fast e then Broad. 

Quando le modifiche vengono completate in ogni gruppo, lo stato diventa **completo**.

![Completamento della distribuzione delle impostazioni configurabili](images/config-setting-complete.png)

## <a name="revert-deployment"></a>Ripristinare la distribuzione

Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**. Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta. L'impostazione ritornerà all'ultima versione distribuita in tutti i gruppi. 

Vengono illustrati i passaggi da eseguire per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio. 

**Per annullare una modifica**
1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](http://aka.ms/mwaasportal)
2. In **Impostazioni**, selezionare **** configurabile.
3. Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.
4. In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.

![Ripristinare la distribuzione delle impostazioni configurabili](images/config-setting-revert.png) 

## <a name="additional-resources"></a>Risorse aggiuntive
- [Panoramica delle impostazioni configurabili](config-setting-overview.md)
- [Informazioni di riferimento sulle impostazioni configurabili](config-setting-ref.md) 
