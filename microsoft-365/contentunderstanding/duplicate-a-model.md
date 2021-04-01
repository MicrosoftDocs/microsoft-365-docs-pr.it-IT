---
title: Duplicare un modello in Microsoft SharePoint Syntex
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
description: Informazioni su come e perché duplicare un modello in Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446037"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>Duplicare un modello in Microsoft SharePoint Syntex

Duplicare un modello di analisi dei documenti consente di risparmiare tempo e risorse se si necessita di creare un nuovo modello e di sapere che un modello esistente è molto simile a ciò di cui si ha bisogno.

Ad esempio, un modello esistente denominato "Contratti" classifica gli stessi file di cui si necessita per lavorare. Il nuovo modello estrarrà alcuni dati esistenti, ma dovrà essere aggiornato per estrarre alcuni dati aggiuntivi. Invece di creare ed eseguire il training di un nuovo modello da zero, sarà possibile usare la funzionalità di duplicazione modello per creare una copia del modello Contratti, che copierà anche tutti gli elementi del training associati, quali estrattori di file ed entità.

Quando si duplica il modello, dopo averlo rinominato (ad esempio, "Rinnovi contrattuali"), sarà possibile apportare aggiornamenti allo stesso. Ad esempio, è possibile scegliere di rimuovere alcuni dei campi estratti esistenti di cui non si necessita, quindi eseguire il training del modello per estrarne uno nuovo (ad esempio, "Data di rinnovo").

## <a name="duplicate-a-model"></a>Duplicare un modello

Seguire questi passaggi per duplicare un modello di analisi dei documenti.

1. Nel centro contenuti, selezionare **Modelli** per visualizzare l'elenco dei modelli.

2. Alla pagina **Modelli**, selezionare il modello che si desidera duplicare.

3. Usando la barra multifunzione o il pulsante **Mostra azioni** (accanto al nome modello), selezionare **Duplica**.</br>

    ![Screenshot della pagina Modelli che mostra un modello selezionato con le opzioni Duplica evidenziate.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. Nel pannello **Duplica modello**:

   a. In **Nome**, immettere il nuovo nome del modello che si desidera duplicare.</br>

    ![Screenshot che mostra il pannello Duplica modello.](../media/content-understanding/duplicate-model-panel.png) </br>

   b. In **Descrizione**, aggiungere una descrizione del nuovo modello.

   c. (Facoltativo) In **Impostazioni avanzate**, selezionare se si desidera associare un [tipo di contenuto](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) esistente.

5. Selezionare **Duplica**.

## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)

[Rinominare un modello](rename-a-model.md)

[Creare un estrattore](create-an-extractor.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)

[Tipi di spiegazione](explanation-types-overview.md)

[Applicare un modello](apply-a-model.md) 

[Modalità di accessibilità di SharePoint Syntex](accessibility-mode.md)