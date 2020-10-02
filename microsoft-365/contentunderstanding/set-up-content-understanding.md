---
title: Configurazione di SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Configurazione della comprensione dei contenuti in Project Cortex
ms.openlocfilehash: 7fb5998729c9f11902f8fdfaffa62b160928077c
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321350"
---
# <a name="set-up-sharepoint-syntex"></a>Configurazione di SharePoint Syntex

Gli amministratori possono usare l'interfaccia di amministrazione di Microsoft 365 per configurare [Microsoft SharePoint Syntex](document-understanding-overview.md). 

Prima di iniziare, prendere in considerazione quanto segue:

- Quali siti di SharePoint verranno abilitati all’elaborazione moduli? Tutti, alcuni o determinati siti?
- Quale sarà il nome del centro contenuti predefinito?

È possibile cambiare le impostazioni dopo la configurazione iniziale nell'interfaccia di amministrazione di Microsoft 365.

Il contenuto di questo articolo riguarda l'anteprima privata di Project Cortex. [Altre informazioni su Project Cortex](https://aka.ms/projectcortex).

Prima di procedere, assicurarsi di pianificare in modo ottimale la configurazione della comprensione dei contenuti nel proprio ambiente. Ad esempio, è necessario prendere in considerazione i nomi delle seguenti entità:

- I siti di SharePoint in cui si vuole abilitare l'elaborazione moduli: tutti, alcuni o determinati siti.
- Il centro contenuti e il nome dell'amministratore del sito principale

## <a name="requirements"></a>Requisiti 

> [!NOTE]
> È necessario avere le autorizzazioni di amministratore globale o amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare la comprensione dei contenuti.

Gli amministratori possono anche modificare le impostazioni selezionate in qualsiasi momento dopo la configurazione, nonché le impostazioni di gestione della comprensione dei contenuti nell'interfaccia di amministrazione di Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Per configurare SharePoint Syntex

1. Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Configura** e poi visualizzare la sezione **Informazioni dell’organizzazione**.

2. Nella sezione **Informazioni dell’organizzazione**, selezionare **Comprensione dei contenuti automatica**.<br/>

    ![Pagina di configurazione delle Informazioni dell’organizzazione](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. Nella pagina **Comprensione dei contenuti automatica**, fare clic su **Inizia** e seguire le istruzioni per completare il processo di configurazione.<br/>

    ![Avviare la configurazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. Nella pagina di abilitazione dell’aggiunta di tag alle immagini, scegliere se si vuole consentire l’[aggiunta di tag alle immagini](image-tagging.md).

    ![Schermata delle opzioni di aggiunta di tag alle immagini](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. Nella pagina **Configurare l’elaborazione moduli**, è possibile scegliere se si vuole consentire agli utenti di creare modelli di elaborazione moduli in raccolte documenti di SharePoint specifiche. Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione del menu che consente di **Creare un modello di elaborazione moduli** nelle raccolte documenti di SharePoint in cui è abilitato.
 
     In **Quale raccolta di SharePoint deve mostrare l'opzione di creazione del modello di elaborazione moduli**, è possibile selezionare:</br>
      - **Tutte le raccolte di SharePoint** per renderla disponibile per tutte le raccolte di SharePoint nell'organizzazione.</br>
      - **Solo le raccolte dei siti selezionati** e quindi selezionare i siti in cui si vuole rendere l’opzione disponibile o caricare un elenco di massimo 50 siti.</br>
      - **Nessuna raccolta di SharePoint** se non si vuole rendere l’opzione disponibile in alcun sito. È possibile modificare questa impostazione dopo la configurazione.

   ![Configurare l'elaborazione moduli](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Rimuovere un sito dopo che l’opzione è stata inclusa, non influisce sui modelli esistenti applicati alle raccolte del sito o sulla possibilità di applicare modelli di analisi dei documenti a una raccolta. 
    
6. Nella pagina **Creare un centro contenuti**, è possibile creare un sito del centro contenuti di SharePoint in cui gli utenti possono creare e gestire i modelli di analisi dei documenti. </br>
    a. Per **Nome del sito**, digitare il nome che si vuole assegnare al sito del centro contenuti.</br>
    b. L’**Indirizzo del sito** mostrerà l'URL del sito in base a ciò che è stato selezionato per il nome del sito. Per modificarlo, fare clic su **Modifica**.</br>

      ![Creare un centro contenuti](../media/content-understanding/admin-cu-create-cc.png)</br>

    Selezionare **Avanti**.

7. Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche. Al termine, selezionare **Attiva**.

8. Nella pagina di conferma, fare clic su **Fine**.

9. Si verrà indirizzati nuovamente alla pagina **Comprensione dei contenuti automatica**. In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione. 

## <a name="assign-licenses"></a>Assegnazione delle licenze

Dopo aver configurato SharePoint Syntex, è necessario assegnare le licenze per gli utenti che useranno le funzionalità di SharePoint Syntex.

Per assegnare le licenze:

1. Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.

2. Selezionare gli utenti a cui si vuole assegnare una licenza, poi fare clic su **Gestisci le licenze di prodotto**.

3. Selezionare **Assegna altre**.

4. Selezionare **Servizi per contenuti intelligenti**. In **App**, verificare che siano selezionate le opzioni **Common Data Services per i servizi per contenuti intelligenti** e **Servizi per contenuti intelligenti**.

    ![Licenze di SharePoint Syntex nell'interfaccia di amministrazione di Microsoft 365.](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Fare clic su **Salva modifiche**.

## <a name="ai-builder-credits"></a>Crediti di AI Builder

Se nell'organizzazione sono presenti più di 300 licenze di SharePoint Syntex, si riceverà un milione di crediti di AI Builder. Se si hanno meno di 300 licenze, è necessario acquistare i crediti di AI Builder per poter usare l'elaborazione moduli.

È possibile stimare la capacità di AI Builder che più adatta all’utente con [Calcolatore AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).

Passare all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) per controllare i crediti e il relativo utilizzo.

## <a name="see-also"></a>Vedere anche

[Panoramica del modello di elaborazione moduli](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Istruzioni dettagliate per la creazione di un modello di analisi dei documenti (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

