---
title: Configurare SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Configurare la comprensione del contenuto in Project Cortex
ms.openlocfilehash: 31c6b6dd31b3f1bc47deb8424dd847cc0af6d429
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304781"
---
# <a name="set-up-sharepoint-syntex"></a>Configurare SharePoint Syntex

Gli amministratori possono utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare e Microsoft SharePoint Syntex. 

Prima di iniziare, prendere in considerazione quanto segue:

- Quali siti di SharePoint consentiranno di abilitare l'elaborazione dei moduli? Tutti, alcuni o Seleziona siti?
- Che cosa è il nome del centro di contenuti e chi è l'amministratore principale del sito?

È possibile modificare le impostazioni dopo l'installazione iniziale nell'interfaccia di amministrazione di Microsoft 365.

Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

Prima di eseguire l'installazione, assicurarsi di pianificare il modo migliore per impostare e configurare la comprensione del contenuto nell'ambiente in uso. Ad esempio, è necessario prendere in considerazione i seguenti nomi:

- I siti di SharePoint che si desidera abilitare l'elaborazione del modulo: tutti, alcuni o siti selezionati
- Il centro contenuto e il nome dell'amministratore del sito principale

## <a name="requirements"></a>Requisiti 

> [!NOTE]
> È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare la comprensione del contenuto.

Come amministratore, è anche possibile apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione e in tutte le impostazioni di gestione del contenuto nell'interfaccia di amministrazione di Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Per configurare SharePoint Syntex

1. Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .

2. Nella sezione **informazioni organizzative** selezionare **automatizza la comprensione del contenuto**.<br/>

    ![Pagina di configurazione della conoscenza organizzativa](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. Nella pagina **automatizzare SharePoint Syntex** , fare clic su Guida **introduttiva** per eseguire il processo di installazione.<br/>

    ![Avviare l'installazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. Nella pagina attiva tagging immagine scegliere se si desidera consentire il [tagging dell'immagine](image-tagging.md).

    ![Schermata delle opzioni di tagging dell'immagine](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. Nella pagina **Configura elaborazione moduli** è possibile scegliere se si desidera consentire agli utenti di utilizzare il generatore ai per creare modelli di elaborazione dei moduli in specifiche raccolte documenti di SharePoint. Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione di menu per **creare un modello di elaborazione dei moduli** nelle raccolte documenti di SharePoint in cui è abilitata.
 
     Per **il quale le raccolte di SharePoint dovrebbero mostrare l'opzione per creare un modello di elaborazione dei moduli**, è possibile selezionare:</br>
      - **Tutte le raccolte di SharePoint** per renderle disponibili per tutte le raccolte di SharePoint nell'organizzazione.</br>
      - **Solo le raccolte nei siti selezionati**, quindi selezionare i siti in cui si desidera renderli disponibili.</br>

   ![Configurare l'elaborazione dei moduli](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > L'abilitazione di questa impostazione in una raccolta documenti di SharePoint non influisce sui modelli esistenti applicati alla raccolta o sulla possibilità di applicare i modelli di comprensione dei documenti a una raccolta. 
    
6. Nella pagina **Crea centro contenuto** è possibile creare un sito Centro contenuto di SharePoint in cui gli utenti possono creare e gestire i modelli di comprensione dei documenti. </br>
    a. Per **nome sito**, digitare il nome che si desidera assegnare al sito Centro contenuto.</br>
    b. L' **indirizzo del sito** mostrerà l'URL del sito, in base alle operazioni selezionate per il nome del sito. Se si desidera modificarlo, fare clic su **modifica**.</br>

      ![Creare centro contenuto](../media/content-understanding/admin-cu-create-cc.png)</br>

    Selezionare **Avanti**.

7. Nella pagina **revisione e fine** è possibile esaminare l'impostazione selezionata e scegliere di apportare modifiche. Se si è soddisfatti delle selezioni, selezionare **attiva**.

8. Nella pagina Conferma fare clic su **fine**.

9. Verrà restituita la pagina di **informazioni sul contenuto automatico** . Da questa pagina, è possibile selezionare **Gestisci** per apportare modifiche alle impostazioni di configurazione. 

## <a name="assign-licenses"></a>Assegnazione delle licenze

Dopo aver configurato SharePoint Syntex, è necessario assegnare le licenze per gli utenti che utilizzeranno le funzionalità di elaborazione dei moduli e la comprensione dei documenti.

Per assegnare le licenze:

1. Nell'interfaccia di amministrazione di Microsoft 365, in **utenti**, fare clic su **utenti attivi**.

2. Selezionare gli utenti che si desidera concedere una licenza e fare clic su **Gestisci licenze di prodotto**.

3. Selezionare **assegna altro**.

4. Selezionare **Intelligent Content Services**. In **app**, verificare che sia selezionata l'opzione **Common Data Service per Intelligent Content Services** e **Intelligent Content Services** .

    ![Licenze di Syntex di SharePoint nell'interfaccia di amministrazione di Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Fare clic su **Salva modifiche**.

## <a name="ai-builder-credits"></a>Crediti AI Builder

Se si dispone di 300 o più licenze di Syntex di SharePoint per SharePoint Syntex nell'organizzazione, verranno assegnati 1 milione AI Credits Builder. Se si dispone di meno di 300 licenze, è necessario acquistare i crediti Builder AI per poter utilizzare l'elaborazione dei moduli.

È possibile valutare la capacità del generatore AI che è adatta a te con la [calcolatrice di ai Builder](https://powerapps.microsoft.com/ai-builder-calculator).

Accedere all'interfaccia di [amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) per controllare i crediti e l'utilizzo.

## <a name="see-also"></a>Vedere anche

[Panoramica del modello di elaborazione dei moduli](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Step-by-Step: come creare un modello di comprensione dei documenti (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

