---
title: Aggiungere i depositari a un caso avanzato di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come utilizzare lo strumento di gestione del custode incorporato in Advanced eDiscovery per coordinare i flussi di lavoro e identificare le origini dati rilevanti in un caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b0c85fb080faeeafd5909c033bc95ef14efc2c45
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034690"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Aggiungere i depositari a un caso avanzato di eDiscovery

Utilizzare lo strumento di gestione del custode incorporato in Advanced eDiscovery per coordinare i flussi di lavoro in merito alla gestione dei depositari e identificare le origini dati rilevanti e detentive associate a un caso. Quando si aggiunge un custode, il sistema può identificare automaticamente e inserire un blocco sulla cassetta postale di Exchange e OneDrive for business. Durante il processo di individuazione, è possibile identificare anche altre origini dati (ad esempio, cassette postali, siti o Team) a cui un custode ha eseguito l'accesso o ha contribuito. In questa situazione, è possibile utilizzare lo strumento di gestione dei depositari per associare tali origini dati a un determinato custode. Dopo aver aggiunto i depositari a un caso e aver associato altre origini dati, è possibile conservare i dati in modo rapido e cercarli.

Utilizzare il flusso di lavoro seguente per aggiungere e gestire i depositari nei casi avanzati di eDiscovery. 

![Scheda Gestione depositaria](../media/CustodianMgtPage.png)

## <a name="before-you-begin"></a>Prima di iniziare

Per aggiungere depositari a un caso, è necessario essere membri del gruppo di ruoli eDiscovery Manager. In questo modo, vengono fornite le autorizzazioni necessarie per aggiungere i depositari a un caso e inserire un'esenzione nelle origini dati della custodia.


## <a name="step-1-add-potential-custodians"></a>Passaggio 1: aggiungere potenziali depositari

Il primo passaggio consiste nell'identificare e aggiungere i depositari al caso.

1. Nella Home page di **Advanced eDiscovery** fare clic sul caso in cui si desidera aggiungere i depositari. 
 
2. Fare clic sulla scheda **depositari** e quindi fare clic su **+ Aggiungi depositari**.

3. Individuare i depositari da aggiungere al caso. Digitare la prima parte del nome di una persona per visualizzare gli utenti di Azure Active Directory dell'organizzazione. Quando si trova la persona corretta, fare clic sul relativo nome per aggiungerli all'elenco.

   ![Identificare i potenziali depositari](../media/AddCustodianStep1.png)
 
4. Dopo aver aggiunto tutti i depositari rilevanti, fare clic su **Avanti** per selezionare le origini dati primarie dei depositari.
  
## <a name="step-2-select-custodian-data-sources"></a>Passaggio 2: selezionare origini dati di un custode

Dopo aver aggiunto gli strumenti di gestione, lo strumento di gestione delle risorse di gestione consente di identificare le origini dati primarie possedute da ogni custode. Tali posizioni di dati sono le cassette postali di Exchange e l'account OneDrive del custode. 

Per identificare le origini dati del custode: 

1. Per selezionare la cassetta postale di Exchange per tutti i depositari, selezionare la casella di controllo **Exchange** nella parte superiore della colonna. È quindi possibile deselezionare la casella di controllo per qualsiasi custode specifico per rimuovere una cassetta postale come posizione di custodia. In alternativa, è possibile lasciare la casella di controllo **Exchange** nella parte superiore della colonna deselezionata e quindi selezionare la casella di controllo per i singoli depositari. 
 
   ![Selezionare origini dati di custodia](../media/AddCustodianStep2.png)
 
2. Ripetere la stessa operazione per gli account OneDrive dei depositari. 

    Dopo aver selezionato le origini dati del custode, il sistema tenta automaticamente di identificare e verificare queste origini dati e quindi le aggiunge al caso come origini dati associate ai depositari.
 
4. Fare clic su **Avanti** per iniziare a associare altre origini dati ai depositari nel caso.

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a>Passaggio 3: associare altre origini dati a un custode

A seconda del caso in cui si sta indagando, potrebbe essere necessario eseguire la ricerca e la conservazione dei contenuti delle cassette postali a cui è stato effettuato l'accesso a un determinato custode, Microsoft 365 gruppi a cui è attualmente associato un custode o i siti a cui è stato effettuato l'accesso a un custode. Pertanto, oltre alle origini dati del custode principale specificate nel passaggio precedente, è anche possibile associare altre origini dati Microsoft a un custode nel caso. 

Per eseguire il mapping di cassette postali, siti o team a un determinato custode:

1. Nella pagina **Seleziona origini dati aggiuntive** fare clic su **Aggiungi** nella riga per il custode specifico. 
  
   ![Mapping di origini dati aggiuntive](../media/AddCustodianStep3.PNG)

2. Nella pagina a comparsa è possibile specificare un'origine dati da uno dei servizi seguenti:
  
   -  **Posta elettronica di Exchange** -fare clic su **Scegli utenti, gruppi o team** e quindi fare di nuovo clic su **Scegli utenti, gruppi o team** . Utilizzare la casella di ricerca per trovare le cassette postali da associare al custode. Per specificare le cassette postali da assegnare al custode selezionato, utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione. È inoltre possibile assegnare la cassetta postale associata a un gruppo di Microsoft 365 o a un team Microsoft. Selezionare la casella di controllo utente, gruppo, team, fare clic su **Scegli**e quindi su **fine**.

        > [!NOTE]
        > Quando si fa clic su Scegli utenti, gruppi o team per specificare le cassette postali, lo strumento di selezione delle cassette postali visualizzato è vuoto. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere una cassetta postale a questo elenco, digitare un nome o un alias (almeno 3 caratteri) nella casella di ricerca.
     
     - **Siti di SharePoint** -fare clic su **Scegli siti** , quindi fare di nuovo clic su **Choose sites** per visualizzare un elenco di siti di SharePoint nell'organizzazione. Per associare un sito al custode, è possibile selezionare un sito nell'elenco oppure digitare l'URL di un altro sito o di un sito associato a un gruppo di Microsoft 365, Microsoft Team o a un account di OneDrive.
     
     - **Teams** -fare clic su **Scegli team** e quindi fare di nuovo clic su **Scegli squadre** per visualizzare un elenco di Microsoft teams di cui è attualmente membro il custode. Selezionare i team che si desidera aggiungere al custode. Una volta selezionata, il sistema identificherà automaticamente & selezionare il sito di SharePoint associato e la cassetta postale del gruppo associata a quel team Microsoft. Fare clic su **Scegli**e quindi su **fine**.

       ![Mapping delle origini dati](../media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > Per associare un altro team a un custode, è necessario aggiungere separatamente la cassetta postale e il sito associati al team utilizzando i percorsi di **posta elettronica di Exchange** e **siti di SharePoint** .

Una volta terminata l'associazione di origini dati aggiuntive ai depositari, è possibile visualizzare il numero totale di cassette postali, siti e team associati a ciascun custode nella **pagina Seleziona origini dati aggiuntive**. Dopo aver finalizzato le origini dati rilevanti per uno specifico custode, questa associazione verrà mantenuta e utilizzata durante le fasi di raccolta, elaborazione e revisione del flusso di lavoro di eDiscovery.

## <a name="step-4-place-custodians-on-hold"></a>Passaggio 4: mettere in attesa i depositari

Dopo aver completato i depositari e le origini dati da aggiungere al caso, è facoltativamente possibile mettere in attesa alcuni o tutti i depositari. Quando si posiziona un custode in attesa, tutto il contenuto in tutti i percorsi di contenuto associati al custode viene mantenuto finché non si rimuove il blocco o si rilascia il custode dall'esenzione. In alcuni casi, potrebbe essere necessario aggiungere i depositari a un caso senza bloccarli.

Per inserire i depositari e le origini dati in attesa:

1. Selezionare la casella di controllo **blocca** nella parte superiore della colonna per inserire tutti i custodi in attesa nella pagina Archivia i **depositari selezionati** . È quindi possibile deselezionare la casella di controllo per qualsiasi custode specifico da rimuovere dall'esenzione. In alternativa, è possibile lasciare la casella di controllo **blocca** nella parte superiore della colonna deselezionata e quindi selezionare la casella di controllo per i singoli depositari. 
 
   ![Esenzioni di posizione](../media/AddCustodianStep5.PNG)

2. Verificare le selezioni di blocco del custode e quindi fare clic su **completa**.

Se non si dispone di un'esenzione su un custode, il custode e le origini dati associate verranno aggiunte al caso, ma il contenuto di tali origini dati non verrà bloccato.

Dopo che un custode è stato messo in attesa, verrà creato automaticamente un criterio di conservazione dei depositari che contiene tutte le fonti detentive. Per visualizzare questo criterio:

1. Nella **Home** page del caso, fare clic sulla scheda **esenzioni** , quindi fare clic su **CustodianHold-GUID**,  

2. Nella pagina riquadro a comparsa, fare clic su **Modifica blocco** per visualizzare tutte le origini dati del custode che vengono conservate.

