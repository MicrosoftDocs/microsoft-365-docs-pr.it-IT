---
title: Applicare un'etichetta di conservazione a un modello di analisi dei documenti
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Questo articolo spiega come applicare un'etichetta di conservazione a un modello di analisi dei documenti
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087476"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Applicare un'etichetta di conservazione a un modello di analisi dei documenti

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Microsoft SharePoint Syntex consente di applicare facilmente un'[etichetta di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modello di analisi dei documenti.

Le etichette di conservazione permettono di applicare impostazioni di conservazione ai documenti identificati dal modello di analisi dei documenti.  Ad esempio, si può fare modo che il modello non solo identifichi i documenti di tipo *Contratto di assicurazione* caricati in una raccolta documenti, ma anche che applichi l'etichetta di conservazione *Business*, in modo che non sia possibile eliminare questi documenti dalla raccolta per il periodo di tempo specificato, ad esempio i cinque mesi successivi.

Si può applicare al modello di analisi dei documenti un'etichetta di conservazione preesistente, usando le impostazioni del modello nella home page del modello. 

> [!Important]
> Affinché siano disponibili etichette di conservazione da applicare al modello di comprensione dei contenuti, occorre [crearle e pubblicarle nel Centro conformità Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

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

## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)

[Creare un estrattore](create-an-extractor.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)


