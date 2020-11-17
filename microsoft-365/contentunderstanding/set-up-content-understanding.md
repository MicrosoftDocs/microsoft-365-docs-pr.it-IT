---
title: Configurazione di SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Configurazione della comprensione dei contenuti in Project Cortex
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087572"
---
# <a name="set-up-sharepoint-syntex"></a>Configurazione di SharePoint Syntex

Gli amministratori possono usare l'interfaccia di amministrazione di Microsoft 365 per configurare [Microsoft SharePoint Syntex](index.md). 

Prima di iniziare, prendere in considerazione quanto segue:

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- Quale sarà il nome del centro contenuti predefinito?

È possibile cambiare le impostazioni dopo la configurazione iniziale nell'interfaccia di amministrazione di Microsoft 365.

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- I siti di SharePoint in cui si vuole abilitare l'elaborazione moduli: tutti, alcuni o determinati siti.
- Il centro contenuti e il nome dell'amministratore del sito principale

## <a name="requirements"></a>Requisiti 

> [!NOTE]
> È necessario avere le autorizzazioni di amministratore globale o amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare la comprensione dei contenuti.

Gli amministratori possono anche modificare le impostazioni selezionate in qualsiasi momento dopo la configurazione, nonché le impostazioni di gestione della comprensione dei contenuti nell'interfaccia di amministrazione di Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Per configurare SharePoint Syntex

1. Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Configura** e poi visualizzare la sezione **File e contenuti**.

2. Nella sezione **File e contenuti**, selezionare **Comprensione dei contenuti automatica**.<br/>

3. Nella pagina **Comprensione dei contenuti automatica**, fare clic su **Inizia** e seguire le istruzioni per completare il processo di configurazione.<br/>

    > [!div class="mx-imgBorder"]
    > ![Avviare la configurazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     In **Quale raccolta di SharePoint deve mostrare l'opzione di creazione del modello di elaborazione moduli**, è possibile selezionare:</br>
      - **Tutte le raccolte di SharePoint** per renderla disponibile per tutte le raccolte di SharePoint nell'organizzazione.</br>
      - **Solo le raccolte dei siti selezionati** e quindi selezionare i siti in cui si vuole rendere l’opzione disponibile o caricare un elenco di massimo 50 siti.</br>
      - **Nessuna raccolta di SharePoint** se non si vuole rendere l’opzione disponibile in alcun sito. È possibile modificare questa impostazione dopo la configurazione.

   > [!div class="mx-imgBorder"]
   > ![Configurare l'elaborazione moduli](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Rimuovere un sito dopo che l’opzione è stata inclusa, non influisce sui modelli esistenti applicati alle raccolte del sito o sulla possibilità di applicare modelli di analisi dei documenti a una raccolta. 
    
5. Nella pagina **Creare un centro contenuti**, è possibile creare un sito del centro contenuti di SharePoint in cui gli utenti possono creare e gestire i modelli di analisi dei documenti.

    1. Per **Nome del sito**, digitare il nome che si desidera assegnare al sito del centro contenuti.
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![Creare un centro contenuti](../media/content-understanding/admin-cu-create-cc.png)</br>

       Selezionare **Avanti**.

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. Nella pagina di conferma, fare clic su **Fine**.

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>Assegnazione delle licenze

Dopo aver configurato SharePoint Syntex, è necessario assegnare le licenze per gli utenti che useranno le funzionalità di SharePoint Syntex.

Per assegnare le licenze:

1. Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.

2. Selezionare gli utenti a cui si vuole assegnare una licenza, poi fare clic su **Gestisci le licenze di prodotto**.

3. Selezionare **Assegna altre**.

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![Licenze di SharePoint Syntex nell'interfaccia di amministrazione di Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Fare clic su **Salva modifiche**.

## <a name="ai-builder-credits"></a>Crediti di AI Builder

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

È possibile stimare la capacità di AI Builder che più adatta all’utente con [Calcolatore AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).

Passare all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) per controllare i crediti e il relativo utilizzo.

## <a name="see-also"></a>Vedere anche

[Panoramica del modello di elaborazione moduli](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Istruzioni dettagliate per la creazione di un modello di analisi dei documenti (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

