---
title: Rinominare un estrattore in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informazioni su come rinominare un estrattore in Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445995"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>Rinominare un estrattore in Microsoft SharePoint Syntex

A un certo punto, potrebbe essere necessario rinominare un estrattore per poter fare riferimento a un campo dati estratto da un nome diverso. Ad esempio, l'organizzazione decide di apportare modifiche ai documenti contrattuali e chiama i "clienti" "acquirenti" nei documenti. Nell'ambito dell'estrazione di un campo "Cliente" nel modello, sarà possibile rinominarlo "Acquirente".

Quando viene sincronizzato il modello aggiornato nella libreria documenti di SharePoint, verrà visualizzata una nuova colonna "Acquirente" nella vista libreria documenti. La vista conserverà la colonna "Cliente" per le attività precedenti, ma aggiornerà la nuova colonna "Acquirente" per tutti i nuovi documenti elaborati dal modello. 

> [!IMPORTANT]
>  Assicurarsi di sincronizzare il modello aggiornato nelle librerie documenti in cui è stato applicato in precedenza per fare in modo che venga visualizzato il nuovo nome colonna. 

## <a name="rename-an-extractor"></a>Rinominare un estrattore

Seguire questi passaggi per rinominare un estrattore di entità.

1. Nel centro contenuti, selezionare **Modelli** per visualizzare l'elenco dei modelli.

2. Alla pagina **Modelli**, nella colonna **Nome**, selezionare il modello per cui si desidera rinominare un estrattore.

3. In **Estrattori di entità**, selezionare il nome dell'estrattore che si desidera rinominare, quindi **Rinomina**.</br>

    ![Screenshot della sezione Estrattori entità che mostra un estrattore selezionato con l'opzione Rinomina evidenziata.](../media/content-understanding/entity-extractor-rename.png) </br>

4. Nel pannello **Rinominare estrattore di entità**:

   a. In **Nuovo nome**, immettere il nuovo nome dell'estrattore.</br>

    ![Screenshot che mostra un pannello di un Estrattore di entità.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (Facoltativo) In **Impostazioni avanzate**, selezionare se si desidera associare una colonna sito esistente.

5. Selezionare **Rinomina**.

## <a name="see-also"></a>Vedere anche
[Creare un estrattore](create-an-extractor.md)

[Creare un classificatore](create-a-classifier.md)

[Rinominare un modello](rename-a-model.md)

[Tipi di spiegazione](explanation-types-overview.md)

[Sfruttare la tassonomia dell'archivio termini durante la creazione di un estrattore](leverage-term-store-taxonomy.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)

[Applicare un modello](apply-a-model.md) 
