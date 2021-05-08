---
title: Passaggio 1. Usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati utilizzando una Microsoft 365 soluzione.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281212"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Passaggio 1. Usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati

L'organizzazione ha bisogno di un modo per identificare e classificare tutti i documenti di contratto dai numerosi file ricevuti. È inoltre possibile visualizzare rapidamente diversi elementi chiave in ognuno dei file di contratto identificati (ad esempio, *Cliente,* Appaltatore e *Importo commissione).* A tale scopo, utilizzare [SharePoint Syntex](index.md) per creare un modello di comprensione dei documenti e applicarlo a una raccolta documenti.

[La comprensione dei](document-understanding-overview.md) documenti usa modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni. I modelli di comprensione dei documenti sono inoltre ottimali nell'estrazione di informazioni da documenti non strutturati e semistrutturati in cui le informazioni necessarie non sono contenute in tabelle o moduli, ad esempio contratti.

1. Innanzitutto, è necessario trovare almeno cinque file di esempio che è possibile utilizzare per "formare" il modello per cercare caratteristiche specifiche del tipo di contenuto che si sta tentando di identificare (un contratto). 

2. Usando SharePoint Syntex, crea un nuovo modello di comprensione dei documenti. Usando i file di esempio, è necessario [creare un classificatore](create-a-classifier.md). Formando il classificatore con i file di esempio, viene insegnato a cercare caratteristiche specifiche di ciò che si potrebbe vedere nei contratti dell'azienda. Ad esempio, [creare una "spiegazione"](create-a-classifier.md#create-an-explanation) che cerca stringhe specifiche presenti nei contratti, ad esempio Contratto di *servizio,* *Condizioni* del contratto e *Compensazione.* Puoi anche formare la tua spiegazione per cercare queste stringhe in sezioni specifiche del documento o posizionate accanto ad altre stringhe. Quando si pensa di aver addestrato il classificatore con le informazioni necessarie, è possibile testare il modello su un set di file di esempio di esempio per verificare l'efficienza. Dopo il test, se necessario, è possibile scegliere di apportare modifiche alle spiegazioni per renderle più efficienti. 

3. Nel modello puoi creare un [estrattore](create-an-extractor.md) per estrarre parti specifiche di dati da ogni contratto. Ad esempio, per ogni contratto, le informazioni più preoccupate sono chi è il cliente, il nome dell'appaltatore e il costo totale.

4. Dopo aver creato correttamente il modello, applicarlo a una [raccolta SharePoint documenti.](apply-a-model.md) Quando si caricano documenti nella raccolta documenti, verrà eseguito il modello di comprensione dei documenti e verranno identificati e classificati tutti i file che corrispondono al tipo di contenuto dei contratti definito nel modello. Tutti i file classificati come contratti verranno visualizzati in una visualizzazione raccolta personalizzata. I file visualizzano anche i valori di ogni contratto definito nell'estrattore.

   ![Contratti nella raccolta documenti](../media/content-understanding/doc-lib-solution.png)

5. Inoltre, se si dispone di requisiti di conservazione per i [](apply-a-retention-label-to-a-model.md) contratti, è anche possibile utilizzare il modello per applicare un'etichetta di conservazione che impedirà l'eliminazione dei contratti per un periodo di tempo specificato.

## <a name="next-step"></a>Passaggio successivo

[Passaggio 2. Usare Microsoft Teams per creare il canale di gestione dei contratti](solution-manage-contracts-step2.md)