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
ms.openlocfilehash: 7589003505aafb480872b14a09c383cfbe0dff40
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683554"
---
# <a name="set-up-sharepoint-syntex"></a>Configurazione di SharePoint Syntex

Gli amministratori possono usare l'interfaccia di amministrazione di Microsoft 365 per configurare [Microsoft SharePoint Syntex](index.md). 

Prima di iniziare, prendere in considerazione quanto segue:

- In quali siti di SharePoint verrà abilitata l'elaborazione dei moduli? Tutti, alcuni o determinati siti?
- Quale sarà il nome assegnato al centro contenuti predefinito?

È possibile cambiare le impostazioni dopo la configurazione iniziale nell'interfaccia di amministrazione di Microsoft 365.

Prima di eseguire la configurazione, assicurarsi di pianificare il modo migliore per configurare e impostare la comprensione dei contenuti nel proprio ambiente. Ad esempio, è necessario prendere le decisioni seguenti:

- I siti di SharePoint in cui si vuole abilitare l'elaborazione dei moduli: tutti, alcuni o determinati siti.
- Il nome e gli amministratori del centro contenuti

## <a name="requirements"></a>Requisiti 

> [!NOTE]
> È necessario disporre delle autorizzazioni di amministratore globale o amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare SharePoint Syntex.

Gli amministratori possono anche modificare le impostazioni selezionate in qualsiasi momento dopo la configurazione, nonché le impostazioni di gestione della comprensione dei contenuti nell'interfaccia di amministrazione di Microsoft 365.

Se si prevede di usare un ambiente di Power Platform personalizzato, è necessario [installare l'app *AI Builder per Project Cortex* in questo ambiente](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) e [allocare crediti di AI Builder](/power-platform/admin/capacity-add-on) prima di poter creare modelli di elaborazione dei moduli.

### <a name="licensing"></a>Licenze

Per usare SharePoint Syntex, l'organizzazione deve avere un abbonamento a SharePoint Syntex e a ogni utente devono essere assegnate le licenze seguenti:

- SharePoint Syntex
- SharePoint Syntex - tipo SPO
- Servizio dati comuni per SharePoint Syntex

Se si annulla l'abbonamento a SharePoint Syntex in futuro (o scade la versione di valutazione), gli utenti non saranno più in grado di creare o eseguire analisi dei documenti o modelli per l’elaborazione dei moduli e il modello del Centro contenuto non sarà più disponibile. Inoltre, i report dell'archivio termini, l'importazione della tassonomia SKOS e il push del tipo di contenuto non saranno più disponibili. Nessun contenuto verrà eliminato e le autorizzazioni per il sito non verranno modificate.

### <a name="ai-builder-credits"></a>Crediti di AI Builder

Se nell'organizzazione sono presenti più di 300 licenze di SharePoint Syntex, si riceverà un milione di crediti di AI Builder. Se si hanno meno di 300 licenze, è necessario acquistare i crediti di AI Builder per poter usare l'elaborazione moduli.

È possibile stimare la capacità di AI Builder che più adatta all’utente con [Calcolatore AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).

Se si pianifica di usare un ambiente Power Platform personalizzato, è necessario [allocare crediti a tale ambiente](/power-platform/admin/capacity-add-on).

Passare all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) per controllare i crediti e il relativo utilizzo.

## <a name="to-set-up-sharepoint-syntex"></a>Per configurare SharePoint Syntex

1. Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Configura** e poi visualizzare la sezione **File e contenuti**.

2. Nella sezione **File e contenuti**, selezionare **Comprensione dei contenuti automatica**. Notare che la disponibilità di crediti di AI Builder corrente è illustrata nella sezione **In breve**.<br/>

3. Nella pagina **Comprensione dei contenuti automatica**, fare clic su **Inizia** e seguire le istruzioni per completare il processo di configurazione. <br/>

    > [!div class="mx-imgBorder"]
    > ![Avviare la configurazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. Nella pagina **Configurare l’elaborazione moduli**, è possibile scegliere se si vuole consentire agli utenti di creare modelli di elaborazione moduli in raccolte documenti di SharePoint specifiche. Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione del menu che consente di **Creare un modello di elaborazione moduli** nelle raccolte documenti di SharePoint in cui è abilitato.
 
     In **Quale raccolta di SharePoint deve mostrare l'opzione di creazione del modello di elaborazione moduli**, è possibile selezionare:</br>
      - **Librerie in tutti i siti di SharePoint** per renderla disponibile per tutte le raccolte di SharePoint nell'organizzazione.</br>
      - **Librerie in siti di SharePoint selezionati** e quindi selezionare i siti in cui si vuole rendere disponibile l'opzione oppure caricare un elenco di massimo 50 siti.</br>
      - **Nessuna raccolta di SharePoint** se non si vuole rendere l’opzione disponibile in alcun sito. È possibile modificare questa impostazione dopo la configurazione.

   > [!div class="mx-imgBorder"]
   > ![Configurare le opzioni del sito per l'elaborazione moduli](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Rimuovere un sito dopo che l’opzione è stata inclusa, non influisce sui modelli esistenti applicati alle raccolte del sito o sulla possibilità di applicare modelli di analisi dei documenti a una raccolta. 
    
    Se sono configurati più ambienti Power Platform, sarà possibile scegliere quale usare per l'elaborazione moduli. (Questa opzione non verrà visualizzata se si dispone di un solo ambiente.)

    ![Configurare le opzioni di Power Platform per l'elaborazione moduli](../media/content-understanding/setup-power-platform-env.png)

    Per l'**ambiente di Power Platform**, è possibile selezionare:
    - **Usare l'ambiente predefinito** per usare l'ambiente Power Platform predefinito.
    - **Usare un ambiente personalizzato** per utilizzare un ambiente personalizzato. Scegliere l'ambiente che si desidera usare dall'elenco. [Vedere i requisiti per un ambiente personalizzato](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements).

    Fare clic su **Avanti**.

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

## <a name="see-also"></a>Vedere anche

[Panoramica del modello di elaborazione moduli](/ai-builder/form-processing-model-overview)

[Istruzioni dettagliate per la creazione di un modello di analisi dei documenti (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

[Creare e gestire ambienti nell'interfaccia di amministrazione di Power Platform](/power-platform/admin/create-environment)
