---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085761"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop

Dopo aver apportato le modifiche alle categorie di impostazioni e a organizzare una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi. In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile. Aprendo una categoria di impostazione è possibile distribuire le impostazioni ai gruppi e monitorare lo stato di avanzamento di queste distribuzioni.

## <a name="deployment-statuses"></a>Stati di distribuzione 

Si tratta degli Stati che verranno visualizzati per ogni distribuzione.

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

1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal)
2. In **Impostazioni**, selezionare **configurabile**.
3. In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.
4. Fare clic su **Distribuisci** per distribuire la modifica a uno dei gruppi di distribuzione.

> [!NOTE] 
> L'icona di avviso arancione indica che è disponibile un gruppo precedente per la distribuzione, come consigliato per l'implementazione in ordine. 

![Area di lavoro stato distribuzione. Riquadro siti attendibili sulla destra. Nella sezione gruppi di distribuzione sono disponibili tre colonne: gruppi di distribuzione, dispositivi e stato. Nella colonna stato "deploy" è evidenziato.](../../media/1deployedit.png)
È consigliabile eseguire la distribuzione ai gruppi di distribuzione nell'ordine seguente: test, First, Fast e then Broad. 

Quando le modifiche vengono completate in ogni gruppo, lo stato diventa **completo**.

![Area di lavoro dello stato di distribuzione con colonne per Data aggiornata, versione, test, First, Fast e Broad. La riga del proxy viene espansa, mostrando un'impostazione datata contrassegnata come "completata" in ognuno dei quattro gruppi di distribuzione.](../../media/2completeedit.png)

## <a name="revert-deployment"></a>Ripristinare la distribuzione

Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**. Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta. L'impostazione ritornerà all'ultima versione distribuita in tutti i gruppi. 

Vengono illustrati i passaggi da eseguire per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio. 

**Per annullare una modifica**
1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal)
2. In **Impostazioni**, selezionare **configurabile**.
3. Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.
4. In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.

![Area di lavoro stato distribuzione. Le pagine iniziali del browser sono selezionate, aprendo un riquadro a destra con i dati relativi alla modifica inviata e al relativo stato. In basso è la sezione "necessità di ripristinare questa modifica", in cui è possibile selezionare "Ripristina distribuzione".](../../media/3revert.png) 

## <a name="additional-resources"></a>Altre risorse
- [Panoramica delle impostazioni configurabili](config-setting-overview.md)
- [Riferimento alle impostazioni configurabili](config-setting-ref.md) 
