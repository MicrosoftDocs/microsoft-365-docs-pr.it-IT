---
title: 'Configurare la comprensione del contenuto (anteprima) '
description: Come configurare la corteccia del progetto.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612703"
---
# <a name="set-up-content-understanding-preview"></a>Configurare la comprensione del contenuto (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

Gli amministratori possono utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare la comprensione del contenuto. 

Prima di eseguire l'installazione, assicurarsi di pianificare il modo migliore per impostare e configurare la comprensione del contenuto nell'ambiente in uso. Ad esempio, è necessario prendere in considerazione quanto segue:
- Quali siti di SharePoint consentiranno di abilitare l'elaborazione dei moduli? Tutti, alcuni o Seleziona siti?
- Nome del centro di contenuto e chi è l'amministratore principale del sito?

Un amministratore può anche apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione tramite le impostazioni di gestione del contenuto nell'interfaccia di amministrazione di Microsoft 365.


## <a name="requirements"></a>Requisiti 
È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare la comprensione del contenuto.


## <a name="to-set-up-content-understanding"></a>Per configurare la comprensione del contenuto

1. Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .
2. Nella sezione **informazioni organizzative** selezionare **automatizza la comprensione del contenuto**.<br/>

    ![Pagina di configurazione della conoscenza organizzativa](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. Nella pagina **informazioni sull'automatizzazione del contenuto** , fare clic su Guida **introduttiva** per eseguire il processo di installazione.<br/>

    ![Avviare l'installazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. Nella pagina **Configura elaborazione moduli** è possibile scegliere se si desidera consentire agli utenti di utilizzare il generatore ai per creare modelli di elaborazione dei moduli in specifiche raccolte documenti di SharePoint. Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione di menu per **creare un modello di elaborazione dei moduli** nelle raccolte documenti di SharePoint in cui è abilitata.
 
     Per **il quale le raccolte di SharePoint dovrebbero mostrare l'opzione per creare un modello di elaborazione dei moduli**, è possibile selezionare:</br>
    - **Tutte le raccolte di SharePoint** per renderle disponibili per tutte le raccolte di SharePoint nel tenant.</br>
    - **Solo le raccolte nei siti selezionati**, quindi selezionare i siti in cui si desidera renderli disponibili.</br>
    - **Nessuna libreria di SharePoint** se attualmente non si desidera renderla disponibile per i siti (è possibile modificare questa impostazione dopo l'installazione).
</br>

   ![Configurare l'elaborazione dei moduli](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > L'abilitazione di questa impostazione in una raccolta documenti di SharePoint non influisce sui modelli esistenti applicati alla raccolta o sulla possibilità di applicare i modelli di comprensione dei documenti a una raccolta. 

    
5. Nella pagina **Crea centro contenuto** è possibile creare un sito Centro contenuto di SharePoint in cui gli utenti possono creare e gestire i modelli di comprensione dei documenti. </br>
    a. Per **nome sito**, digitare il nome che si desidera assegnare al sito Centro contenuto.</br>
    b. L' **indirizzo del sito** mostrerà l'URL del sito, in base alle operazioni selezionate per il nome del sito.</br>

    > [!Note] 
    > Sebbene sia possibile selezionare una lingua supportata, tenere presente che i modelli di comprensione del contenuto possono essere creati solo per l'inglese.</br>

      ![Creare centro contenuto](../media/content-understanding/admin-cu-create-cc.png)</br>


    Selezionare **Avanti**.
6. Nella pagina **fine e revisione** è possibile esaminare l'impostazione selezionata e scegliere di apportare modifiche. Se si è soddisfatti delle selezioni, selezionare **attiva**.



7. Verrà visualizzata la pagina **informazioni sull'attivazione del contenuto** , confermando che il sistema ha aggiunto le preferenze di elaborazione dei moduli e ha creato il sito Centro contenuto. Scegliere **Fine**.

8. Verrà restituita la pagina di **informazioni sul contenuto automatico** . Da questa pagina, è possibile selezionare **Gestisci** per apportare modifiche alle impostazioni di configurazione. 

## <a name="see-also"></a>Vedere anche



  






