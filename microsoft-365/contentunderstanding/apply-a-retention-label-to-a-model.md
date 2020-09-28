---
title: Applicazione di un'etichetta di conservazione a un modello di comprensione del documento
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: In questo articolo viene illustrato come applicare un'etichetta di conservazione a un modello di comprensione del documento
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294924"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Applicazione di un'etichetta di conservazione a un modello di comprensione del documento

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

È possibile applicare facilmente un' [etichetta di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modello di comprensione del documento in Microsoft SharePoint Syntex.

Le etichette di conservazione consentono di applicare le impostazioni di conservazione ai documenti identificati dai modelli.  Ad esempio, si desidera che il modello non identifichi solo i documenti di *avviso di assicurazione* caricati nella raccolta documenti, ma applichi anche un tag di conservazione *aziendale* in modo che tali documenti non possano essere eliminati dalla raccolta documenti per il periodo di tempo specificato (ad esempio, i prossimi cinque mesi).

È possibile applicare un'etichetta di conservazione preesistente al modello di comprensione dei documenti tramite le impostazioni del modello nella Home page del modello. 

> [!Important]
> Affinché le etichette di conservazione siano disponibili per essere applicate al modello di comprensione del contenuto, è necessario [crearle e pubblicarle nel centro conformità di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Per aggiungere un'etichetta di conservazione a un modello di comprensione del documento

1. Nella Home page del modello selezionare **Impostazioni modello**.</br>
2. Nelle **impostazioni del modello**, nella sezione **sicurezza e conformità** , selezionare il menu **etichetta di conservazione** per visualizzare un elenco delle etichette di conservazione disponibili per il modello da applicare.</br>
 ![Menu etichetta di conservazione](../media/content-understanding/retention-labels-menu.png)</br> 
3. Selezionare l'etichetta di conservazione che si desidera applicare al modello e quindi fare clic su **Salva**.</br>

Dopo aver applicato l'etichetta di conservazione al modello, è possibile applicarla a una delle seguenti operazioni:
- Nuova raccolta documenti
- Raccolta documenti a cui è già applicato il modello
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Applicare l'etichetta di conservazione a una raccolta documenti a cui è già applicato il modello

Se il modello di conoscenza del documento è già stato applicato a una raccolta documenti, è possibile eseguire le operazioni seguenti per sincronizzare l'aggiornamento dell'etichetta di conservazione per applicarlo alla raccolta documenti:</br>

1. Nella sezione **raccolte con questo modello** della Home page del modello selezionare la raccolta documenti in cui si desidera applicare l'aggiornamento per l'etichetta di conservazione. </br> 
2. Selezionare **Sincronizza**. </br>
 ![Modello di sincronizzazione](../media/content-understanding/sync-model.png)</br> 


Dopo aver applicato l'aggiornamento e averla sincronizzata con il modello, è possibile verificare che sia stata applicata eseguendo le operazioni seguenti:

1. Nel centro contenuto, nella sezione **raccolte con questo modello** , fare clic sulla raccolta a cui è stato applicato il modello aggiornato. </br>
2. Nella visualizzazione raccolta documenti selezionare l'icona informazioni per controllare le proprietà del modello.</br>  
3. Nell'elenco **modelli attivi** selezionare il modello aggiornato.</br>
4. Nella sezione **etichetta di conservazione** verrà visualizzato il nome dell'etichetta di conservazione applicata.</br>


Nella pagina visualizzazione del modello nella raccolta documenti verrà visualizzata una nuova colonna di **etichette di conservazione** .  Poiché il modello classifica i file identificati come appartenenti al tipo di contenuto e li elenca nella visualizzazione libreria, nella colonna etichetta di conservazione verrà visualizzato anche il nome dell'etichetta di conservazione applicata tramite il modello.


Ad esempio, tutti i documenti di *avviso di assicurazione* che il modello identifica avrà anche l'etichetta di conservazione dell' *azienda* applicata, impedendo che vengano eliminati dalla raccolta documenti per cinque mesi. Se si tenta di eliminare il file dalla raccolta documenti, verrà visualizzato un messaggio di errore che indica che non è consentito a causa dell'etichetta di conservazione applicata.

## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)</br>
[Creare un estrattore](create-an-extractor.md)</br>
[Panoramica della comprensione del documento](document-understanding-overview.md)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)  
