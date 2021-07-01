---
title: Creare un modello di codifica predittivo in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Scopri come creare un modello di codifica predittivo in Advanced eDiscovery. Questo è il primo passaggio nell'uso delle funzionalità di machine learning in Advanced eDiscovery per identificare il contenuto pertinente e non pertinente in un set di recensioni.
ms.openlocfilehash: ab84f529169c780e58888cc2726fbabfef33219e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226228"
---
# <a name="create-a-predictive-coding-model-preview"></a>Creare un modello di codifica predittivo (anteprima)

Il primo passaggio nell'uso delle funzionalità di machine learning della codifica predittiva in Advanced eDiscovery consiste nel creare un modello di codifica predittivo. Dopo aver creato un modello, puoi addestrarlo a identificare il contenuto rilevante e non rilevante in un set di recensioni.

Per esaminare il flusso di lavoro di codifica predittiva, vedere Informazioni sulla codifica [predittiva in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>Prima di creare un modello

- Devono essere presenti almeno 2.000 elementi in un set di revisione per creare un modello di codifica predittivo.

- Assicurati di eseguire il commit di tutte le raccolte nel set di revisione prima di creare un modello. Gli elementi aggiunti a un set di revisione dopo la creazione del modello non verranno elaborati e verrà assegnato un punteggio di previsione generato dal modello.

- Qualsiasi elemento nel set di revisione che non contiene testo non verrà elaborato dal modello o assegnato un punteggio di previsione. Gli elementi con testo verranno inclusi nel set di controlli o in un set di training.

## <a name="create-a-model"></a>Creare un modello

1. Nella finestra Centro conformità Microsoft 365 aprire un Advanced eDiscovery e quindi selezionare la **scheda Set di** revisioni.

2. Apri un set di recensioni e quindi fai clic su **Analisi**  >  **Gestisci codifica predittiva (anteprima)**.

   ![Fai clic sul menu a discesa Analizza nel set di recensioni per passare alla pagina Codifica predittiva](..\media\ManagePredictiveCoding.png)

3. Nella pagina **Modelli di codifica predittiva (anteprima)** fare clic su **Nuovo modello.**

4. Nella pagina a comparsa digitare un nome per il modello e una descrizione facoltativa.

5. Facoltativamente, è possibile configurare le impostazioni avanzate (facendo clic su Opzioni **avanzate** nella pagina a comparsa) relative al livello di probabilità e al margine di errore. Queste impostazioni influiscono sul numero di elementi inclusi nel set di controlli. Il *set di* controlli viene utilizzato durante il processo di training per valutare i punteggi di stima assegnati dal modello agli elementi con l'etichettatura eseguita durante i round di training. Se l'organizzazione dispone di linee guida sul livello di probabilità e sul margine di errore per la revisione dei documenti, specificarle nelle caselle appropriate. In caso contrario, utilizzare le impostazioni predefinite.

6. Fare **clic su** Salva per creare il modello.

   Il sistema predisporrà il modello in un paio di minuti. Una volta pronto, è possibile eseguire il primo ciclo di formazione.

## <a name="what-happens-after-you-create-a-model"></a>Cosa succede dopo aver creato un modello

Dopo aver creato un modello, durante la creazione e la preparazione del modello si verificano le operazioni seguenti in background:

- Il sistema calcola il numero di elementi per il set di controlli. Queste dimensioni si basano sul numero di elementi nel set di revisione e sulle impostazioni per il livello di confidenza e il margine di errore. Gli elementi per il set di controlli vengono selezionati in modo casuale e designati come elementi del set di controlli. Il sistema include 10 elementi del set di controlli nel primo ciclo di formazione.

- Il sistema seleziona casualmente 40 elementi dal set di revisione da includere nel set di formazione per il primo ciclo di formazione. Di conseguenza, il primo ciclo di formazione include 50 elementi per l'etichettatura: 40 elementi dal set di training e 10 elementi dal set di controlli.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver creato un modello per un set di revisione, il passaggio successivo consiste nell'eseguire round di training per "insegnare" il modello a identificare il contenuto rilevante per l'indagine. Per ulteriori informazioni, vedere [Training a predictive coding model](predictive-coding-train-model.md).
