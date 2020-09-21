---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104535"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop

Dopo aver apportato le modifiche alle categorie di impostazioni e a organizzare una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi. In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile. Aprendo una categoria di impostazione è possibile distribuire le impostazioni ai gruppi e monitorare lo stato di avanzamento di queste distribuzioni.

## <a name="deployment-statuses"></a>Stati di distribuzione 

Si tratta degli Stati che verranno visualizzati per ogni distribuzione.

Stato  | Spiegazione 
--- | --- 
Distribuire | La modifica è in attesa di essere distribuita in questo gruppo.
In corso | La modifica viene applicata ai dispositivi attivi di questo gruppo. 
Completa | La modifica completata su tutti i dispositivi attivi di questo gruppo. 
Esito negativo | La modifica ha avuto esito negativo su un 10% dei dispositivi attivi nel gruppo, quindi la distribuzione è stata interrotta.<br><br> Una richiesta di supporto verrà aperta automaticamente con le operazioni di Microsoft Managed Desktop per la risoluzione dei problemi relativi alla distribuzione. 
Ripristinati | La modifica è stata ripristinata all'Ultima modifica che è stata distribuita correttamente in tutti i gruppi di distribuzione.

## <a name="deploy-changes"></a>Distribuire le modifiche

In queste istruzioni viene visualizzata l'immagine di sfondo del desktop. Dopo aver organizzato una distribuzione, è necessario distribuire le modifiche dalla pagina Stato distribuzione. 

**Per distribuire le modifiche**

1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.
4. Fare clic su **Distribuisci** per distribuire la modifica a uno dei gruppi di distribuzione.

> [!NOTE] 
> L'icona di avviso arancione indica che è disponibile un gruppo precedente per la distribuzione, come consigliato per l'implementazione in ordine. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

È consigliabile eseguire la distribuzione ai gruppi di distribuzione nell'ordine seguente: test, First, Fast e then Broad. 

Quando le modifiche vengono completate in ogni gruppo, lo stato diventa **completo**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Ripristinare la distribuzione

Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**. Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta. L'impostazione ritornerà all'ultima versione distribuita in tutti i gruppi. 

Vengono illustrati i passaggi da eseguire per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio. 

**Per annullare una modifica**
1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.
4. In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Risorse aggiuntive
- [Panoramica delle impostazioni configurabili](config-setting-overview.md)
- [Riferimento alle impostazioni configurabili](config-setting-ref.md) 
