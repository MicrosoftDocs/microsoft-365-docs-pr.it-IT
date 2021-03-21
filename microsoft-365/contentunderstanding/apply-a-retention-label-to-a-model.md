---
title: Applicare un'etichetta di conservazione a un modello
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Questo articolo spiega come applicare un'etichetta di conservazione a un modello in SharePoint Syntex
ms.openlocfilehash: 796130bfa967663b5696f49279154cfe9b16f703
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925369"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>Applicare un'etichetta di conservazione a un modello in SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Applicare un'[etichetta di conservazione](../compliance/retention.md) a un modello in Microsoft SharePoint Syntex è molto semplice. È possibile farlo sia per i modelli di analisi dei documenti, sia per i modelli di elaborazione dei moduli.

Le etichette di conservazione permettono di applicare impostazioni di conservazione ai documenti identificati dai modelli.  Ad esempio, si può fare modo che il modello non solo identifichi i documenti di tipo *Contratto di assicurazione* caricati in una raccolta documenti, ma anche che applichi l'etichetta di conservazione *Business*, in modo che non sia possibile eliminare questi documenti dalla raccolta per il periodo di tempo specificato, ad esempio i cinque mesi successivi.

Si può applicare al modello un'etichetta di conservazione preesistente, usando le impostazioni del modello nella home page del modello. 

> [!Important]
> Affinché siano disponibili etichette di conservazione da applicare ai modelli di analisi dei documenti, occorre [crearle e pubblicarle nel Centro conformità Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Per aggiungere un'etichetta di conservazione a un modello di analisi dei documenti

1. Nella home page del modello selezionare **Impostazioni modello**.</br>
2. In **Impostazioni modello** selezionare il menu **Etichetta di conservazione** nella sezione **Sicurezza e conformità** per visualizzare un elenco delle etichette di conservazione disponibili per il modello.</br>
 ![Menu Etichetta di conservazione](../media/content-understanding/retention-labels-menu.png)</br> 
3. Selezionare l'etichetta di conservazione da applicare al modello e scegliere **Salva**.</br>

Dopo aver applicato l'etichetta conservazione al modello, è possibile applicarla:
- A una nuova raccolta documenti
- A una raccolta documenti a cui è già applicato il modello
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Applicare l'etichetta conservazione a una raccolta documenti a cui è già applicato il modello

Se il modello di analisi dei documenti è già stato applicato a una raccolta documenti, è possibile procedere come segue per sincronizzare l'aggiornamento dell'etichetta di conservazione e applicarlo alla raccolta documenti:</br>

1. Nella home page del modello selezionare la raccolta documenti alla quale si vuole applicare l'aggiornamento dell'etichetta di conservazione nella sezione **Raccolte con questo modello**. </br> 
2. Selezionare **Sincronizza**. </br>
 ![Sincronizzazione del modello](../media/content-understanding/sync-model.png)</br> 


Dopo aver applicato l'aggiornamento e averlo sincronizzato con il modello, è possibile verificare che sia stato applicato eseguendo le operazioni seguenti:

1. Nella sezione **Raccolte con questo modello** del centro contenuti fare clic sulla raccolta a cui è stato applicato il modello aggiornato. </br>
2. Nella visualizzazione Raccolta documenti selezionare l'icona informazioni per controllare le proprietà del modello.</br>  
3. Selezionare il modello aggiornato nell'elenco **Modelli attivi**.</br>
4. Nella sezione **Etichetta di conservazione** sarà visualizzato il nome dell'etichetta di conservazione applicata.</br>


Nella pagina di visualizzazione del modello della raccolta documenti comparirà una nuova colonna **Etichetta di conservazione**.  Man mano che il modello classifica i file che identifica come appartenenti al proprio tipo di contenuto e li elenca nella visualizzazione della raccolta, nella colonna Etichetta di conservazione compare anche il nome dell'etichetta di conservazione applicata mediante il modello.


Ad esempio, a tutti i documenti *Contratto di assicurazione* identificati dal modello verrà anche applicata l'etichetta di conservazione *Business*, che ne impedisce l'eliminazione dalla raccolta documenti per cinque mesi. Se qualcuno tenta di eliminare il file dalla raccolta documenti, verrà visualizzato un messaggio di errore che segnala che non è consentito a causa dell'etichetta di conservazione applicata.

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli

> [!Important]
> Affinché siano disponibili etichette di conservazione da applicare al modello di elaborazione moduli, occorre [crearle e pubblicarle nel Centro conformità Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

È possibile applicare un'etichetta di conservazione a un modello di elaborazione moduli quando si crea il modello oppure applicarla a un modello esistente.

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>Per aggiungere un'etichetta di conservazione al momento della creazione di un modello di elaborazione moduli

1. Quando si [crea un nuovo modello di elaborazione moduli](./create-a-form-processing-model.md), selezionare <b>Impostazioni avanzate.</b>
2. Nella sezione <b>Etichetta di conservazione</b> delle <b>Impostazioni avanzate</b> selezionare il menu e quindi l'etichetta di conservazione da applicare al modello.</b>

 
     ![Aggiungere un'etichetta a un nuovo modello di elaborazione moduli](../media/content-understanding/retention-label-forms.png)</br>

3.  Dopo aver completato le impostazioni rimanenti del modello, selezionare <b>Crea</b> per creare il modello.

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente

Si può aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente in vari modi:
- Tramite il menu Automatizza nella raccolta documenti
- Tramite le impostazioni dei modelli attivi nella raccolta documenti 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente tramite il menu Automatizza

È possibile aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente di cui si è proprietari tramite il menu Automatizza della raccolta documenti in cui è applicato il modello.


1. Nella raccolta documenti a cui è applicato il modello di elaborazione moduli selezionare il menu <b>Automatizza</b>, selezionare <b>AI Builder</b>, quindi <b>Visualizza dettagli modello di elaborazione dei moduli</b>.

   ![Menu Automatizza](../media/content-understanding/automate-menu.png)</br>

2. Nella sezione <b>Etichetta di conservazione</b> dei dettagli del modello selezionare l'etichetta di conservazione da applicare.  Quindi selezionare <b>Salva</b>.

     ![Aggiungere un'etichetta a un modello di elaborazione moduli esistente](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>Per aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente nelle impostazioni dei modelli attivi

È possibile aggiungere un'etichetta di conservazione a un modello di elaborazione moduli esistente di cui si è proprietari tramite le impostazioni dei modelli attivi della raccolta documenti in cui è applicato il modello.

1. Nella raccolta documenti di SharePoint in cui è applicato il modello selezionare l'icona <b>Visualizza modelli attivi</b> e quindi selezionare <b>Visualizza modelli attivi</b>.</b>

   ![Visualizza i modelli attivi](../media/content-understanding/info-du.png)</br> 

2. In <b>Modelli attivi</b> selezionare il modello di elaborazione moduli a cui si vuole applicare l'etichetta di conservazione.

     ![Dettagli del modello](../media/content-understanding/retention-label-model-details.png)</br> 


3. Nella sezione <b>Etichetta di conservazione</b> dei dettagli del modello selezionare l'etichetta di conservazione da applicare.  Quindi selezionare <b>Salva</b>.

> [!NOTE]
> È necessario essere il proprietario del modello per poter apportare modifiche nel riquadro delle impostazioni modello. 


## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)

[Creare un estrattore](create-an-extractor.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)