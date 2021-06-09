---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e tenere traccia delle modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, distribuzione, distribuzione a fasi, impostazioni configurabili
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
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuire e tenere traccia delle impostazioni configurabili - Microsoft Managed Desktop

Dopo aver apportato modifiche alle categorie di impostazioni e aver in fasi una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi. Questa pagina mostra un riepilogo di ogni impostazione configurabile. Aprendo una categoria di impostazioni è possibile distribuire le impostazioni ai gruppi e tenere traccia dello stato di avanzamento di queste distribuzioni.

## <a name="deployment-statuses"></a>Stati della distribuzione 

Questi sono gli stati che verranno visualizzati per ogni distribuzione.

Stato  | Spiegazione 
--- | --- 
Distribuzione | La modifica è in attesa di essere distribuita in questo gruppo.
In corso | La modifica viene applicata ai dispositivi attivi in questo gruppo. 
Completa | Modifica completata in tutti i dispositivi attivi in questo gruppo. 
Esito negativo | La modifica non è riuscita su un 10% dei dispositivi attivi nel gruppo, quindi la distribuzione è stata interrotta.<br><br> Una richiesta di supporto verrà aperta automaticamente con le Microsoft Managed Desktop per risolvere i problemi della distribuzione. 
Ripristinato | La modifica è stata ripristinata all'ultima modifica distribuita correttamente in tutti i gruppi di distribuzione.

## <a name="deploy-changes"></a>Distribuire le modifiche

In queste istruzioni verrà mostrata l'immagine di sfondo del desktop. Dopo aver a fasi una distribuzione, è possibile distribuire le modifiche dalla pagina Stato distribuzione. 

**Per distribuire le modifiche**

1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. **Nell'area di** lavoro Stato distribuzione selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.
4. Selezionare **Distribuisci** per distribuire la modifica a uno dei gruppi di distribuzione.

> [!NOTE] 
> L'icona di attenzione arancione indica che è disponibile un gruppo precedente per la distribuzione, in quanto è consigliabile implementarlo nell'ordine indicato. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

È consigliabile eseguire la distribuzione nei gruppi di distribuzione nell'ordine seguente: Test, First, Fast e quindi Broad. 

Quando le modifiche vengono completate in ogni gruppo, lo stato viene modificato in **Completa**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Ripristinare la distribuzione

Dopo aver distribuito una modifica, è possibile ripristinare lo **stato della distribuzione**. Quando si ripristina una modifica **in corso** **o** Completata, la distribuzione corrente viene interrotta. Verrà ripristinata l'ultima versione distribuita in tutti i gruppi. 

Verrà illustrata la procedura per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio. 

**Per ripristinare una modifica**
1. Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. **Nell'area di lavoro** Stato distribuzione selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.
4. In **È necessario annullare questa modifica?** selezionare Ripristina **distribuzione.**

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Risorse aggiuntive
- [Panoramica delle impostazioni configurabili](config-setting-overview.md)
- [Riferimento alle impostazioni configurabili](config-setting-ref.md) 
