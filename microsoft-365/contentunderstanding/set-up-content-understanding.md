---
title: Configurazione di SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Configurazione della comprensione dei contenuti in Project Cortex
ms.openlocfilehash: db6340e8bf4dc23163b67e749f60567f7841a943
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911187"
---
# <a name="set-up-sharepoint-syntex"></a>Configurazione di SharePoint Syntex

Gli amministratori possono usare l'interfaccia di amministrazione di Microsoft 365 per configurare [Microsoft SharePoint Syntex](index.md). 

Prima di iniziare, prendere in considerazione quanto segue:

- In quali siti di SharePoint verrà abilitata l'elaborazione dei moduli? Tutti, alcuni o determinati siti?
- Quale sarà il nome assegnato al centro contenuti predefinito?

È possibile cambiare le impostazioni dopo la configurazione iniziale nell'interfaccia di amministrazione di Microsoft 365.

Prima di procedere, assicurarsi di pianificare in modo ottimale la configurazione della comprensione dei contenuti nel proprio ambiente. Ad esempio, è necessario prendere le decisioni seguenti:

- I siti di SharePoint in cui si vuole abilitare l'elaborazione dei moduli: tutti, alcuni o determinati siti.
- Il nome e gli amministratori del centro contenuti

## <a name="requirements"></a>Requisiti 

> [!NOTE]
> È necessario disporre delle autorizzazioni di amministratore globale o amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare SharePoint Syntex.

Gli amministratori possono anche modificare le impostazioni selezionate in qualsiasi momento dopo la configurazione, nonché le impostazioni di gestione della comprensione dei contenuti nell'interfaccia di amministrazione di Microsoft 365.

### <a name="licensing"></a>Licenze

Per usare SharePoint Syntex, l'organizzazione deve avere un abbonamento a SharePoint Syntex e a ogni utente devono essere assegnate le licenze seguenti:

- SharePoint Syntex
- SharePoint Syntex - tipo SPO
- Servizio dati comuni per SharePoint Syntex

Se si annulla l'abbonamento a SharePoint Syntex in futuro (o scade la versione di valutazione), gli utenti non saranno più in grado di creare o eseguire analisi dei documenti o modelli per l’elaborazione dei moduli e il modello del Centro contenuto non sarà più disponibile. Inoltre, i report dell'archivio termini, l'importazione della tassonomia SKOS e il push del tipo di contenuto non saranno più disponibili. Nessun contenuto verrà eliminato e le autorizzazioni per il sito non verranno modificate.

## <a name="to-set-up-sharepoint-syntex"></a>Per configurare SharePoint Syntex

1. Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Configura** e poi visualizzare la sezione **File e contenuti**.

2. Nella sezione **File e contenuti**, selezionare **Comprensione dei contenuti automatica**.<br/>

3. Nella pagina **Comprensione dei contenuti automatica**, fare clic su **Inizia** e seguire le istruzioni per completare il processo di configurazione.<br/>

    > [!div class="mx-imgBorder"]
    > ![Avviare la configurazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. Nella pagina **Configurare l’elaborazione moduli**, è possibile scegliere se si vuole consentire agli utenti di creare modelli di elaborazione moduli in raccolte documenti di SharePoint specifiche. Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione del menu che consente di **Creare un modello di elaborazione moduli** nelle raccolte documenti di SharePoint in cui è abilitato.
 
     In **Quale raccolta di SharePoint deve mostrare l'opzione di creazione del modello di elaborazione moduli**, è possibile selezionare:</br>
      - **Librerie in tutti i siti di SharePoint** per renderla disponibile per tutte le raccolte di SharePoint nell'organizzazione.</br>
      - **Librerie in siti di SharePoint selezionati** e quindi selezionare i siti in cui si vuole rendere disponibile l'opzione oppure caricare un elenco di massimo 50 siti.</br>
      - **Nessuna raccolta di SharePoint** se non si vuole rendere l’opzione disponibile in alcun sito. È possibile modificare questa impostazione dopo la configurazione.

   > [!div class="mx-imgBorder"]
   > ![Configurare l'elaborazione moduli](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Rimuovere un sito dopo che l’opzione è stata inclusa, non influisce sui modelli esistenti applicati alle raccolte del sito o sulla possibilità di applicare modelli di analisi dei documenti a una raccolta. 
    
5. Nella pagina **Creare un centro contenuti**, è possibile creare un sito del centro contenuti di SharePoint in cui gli utenti possono creare e gestire i modelli di analisi dei documenti.

    1. Per **Nome del sito**, digitare il nome che si desidera assegnare al sito del centro contenuti.
    
    1. L’**Indirizzo del sito** mostrerà l'URL del sito in base a ciò che è stato selezionato per il nome del sito. Per modificarlo, fare clic su **Modifica**.

       > [!div class="mx-imgBorder"]
       > ![Creare un centro contenuti](../media/content-understanding/admin-cu-create-cc.png)</br>

       Selezionare **Avanti**.

6. Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche. Al termine, selezionare **Attiva**.

7. Nella pagina di conferma, fare clic su **Fine**.

8. Si verrà indirizzati nuovamente alla pagina **Comprensione dei contenuti automatica**. In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione. 

## <a name="assign-licenses"></a>Assegnazione delle licenze

Dopo aver configurato SharePoint Syntex, è necessario assegnare le licenze per gli utenti che useranno le funzionalità di SharePoint Syntex.

Per assegnare le licenze:

1. Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.

2. Selezionare gli utenti a cui si vuole assegnare una licenza e quindi scegliere **Gestisci licenze prodotto**.

3. Scegliere **App** nel menu a discesa.

4. Selezionare **Mostra app per SharePoint Syntex**. In **App** verificare che l'opzione **Common Data Service per SharePoint Syntex**, **SharePoint Syntex** e **SharePoint Syntex - tipo SPO** sia selezionata.

    > [!div class="mx-imgBorder"]
    > ![Licenze di SharePoint Syntex nell'interfaccia di amministrazione di Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Fare clic su **Salva modifiche**.

## <a name="ai-builder-credits"></a>Crediti di AI Builder

Se nell'organizzazione sono presenti più di 300 licenze di SharePoint Syntex, si riceverà un milione di crediti di AI Builder. Se si hanno meno di 300 licenze, è necessario acquistare i crediti di AI Builder per poter usare l'elaborazione moduli.

È possibile stimare la capacità di AI Builder che più adatta all’utente con [Calcolatore AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).

Passare all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) per controllare i crediti e il relativo utilizzo.

## <a name="see-also"></a>Vedere anche

[Panoramica del modello di elaborazione moduli](/ai-builder/form-processing-model-overview)

[Istruzioni dettagliate per la creazione di un modello di analisi dei documenti (video)](https://www.youtube.com/watch?v=DymSHObD-bg)