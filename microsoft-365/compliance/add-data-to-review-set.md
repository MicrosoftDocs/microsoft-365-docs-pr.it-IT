---
title: Aggiungere i risultati della ricerca a un insieme da rivedere
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
description: Aggiungere i risultati di una ricerca associata a un caso di eDiscovery avanzato. Gli elementi vengono copiati dal percorso originale e copiati in una posizione di archiviazione di Azure fornita da Microsoft. Gli elementi vengono anche reindicizzati e Advanced eDiscovery eseguirà il riconoscimento ottico dei caratteri (OCR) sui file di immagine e caricherà il testo dell'immagine per la revisione e l'analisi.
ms.openlocfilehash: 99fe0cce8bd872ecd5f4a94699857c36c3a4d617
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202327"
---
# <a name="add-search-results-to-a-review-set"></a>Aggiungere i risultati della ricerca a un insieme da rivedere

Quando si è soddisfatti dei risultati di una ricerca e si è pronti per esaminare e analizzare i risultati della ricerca, è possibile aggiungerli a un set di revisione nel caso. La copia dei dati originali nel set di revisione facilita anche la revisione e il processo di analisi fornendovi strumenti di analisi avanzati, come il rilevamento di temi, il rilevamento quasi duplicati e l'identificazione dei thread di posta elettronica. È inoltre possibile aggiungere dati provenienti da origini dati non di Office 365 a un set di revisione, in modo da poter esaminare tali dati oltre ai dati raccolti da Office 365. 

Quando si aggiungono i risultati di una ricerca a un set di revisione (i set di revisione in un caso sono elencati nella scheda dei **set di revisione** ), si verificano le operazioni seguenti:

- La ricerca viene eseguita di nuovo. Questo significa che i risultati della ricerca copiati nel set di revisione possono essere diversi dai risultati stimati restituiti al momento dell'ultima esecuzione della ricerca.

- Tutti gli elementi nei risultati della ricerca vengono copiati dall'origine dati originale nei servizi Live di Office 365 e copiati in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

- Tutti gli elementi (inclusi il contenuto e i metadati) vengono reindicizzati in modo che tutti i dati del set di revisione siano completamente ricercabili durante la revisione dei dati del caso. Reindicizzare i risultati dei dati in ricerche accurate e veloci quando si esegue una ricerca nei dati del set di verifica durante l'analisi del caso.

Per aggiungere dati a un set di revisione, fare clic su una ricerca nella scheda **ricerche** e quindi fare clic su **Aggiungi risultati al set di revisione** nella pagina a comparsa.

![Aggiunta di dati a un set di Revisione](media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

È possibile aggiungere a un set di revisione esistente o creare un nuovo set di revisione.  Se si aggiunge un nuovo set di revisione, specificare il nome e quindi fare clic su **Aggiungi**.

![Selezionare un set di Revisione](media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

L'aggiunta di dati a un set di revisione è un processo a esecuzione prolungata. Questo processo include la raccolta di elementi dalle origini dati originali in Office 365 (ad esempio, da cassette postali e siti), la loro copia nel percorso di archiviazione di Azure (questo processo di copia è denominato anche *ingestione*) e quindi reindicizzare gli elementi. È possibile monitorare lo stato di avanzamento nella scheda **processi** o nella scheda **ricerche** monitorando lo stato nella colonna **set di dati aggiunti a revisione** . Dopo aver completato l'elaborazione del set di revisione, fare clic sulla scheda **Revisione set** nel caso, quindi fare clic sul set di riesame per avviare il processo di filtro, revisione, tagging ed esportazione dei dati nel set di revisione.

## <a name="add-a-sample-to-a-review-set"></a>Aggiungere un esempio a un set di Revisione

Se si desidera convalidare i risultati di una ricerca in modo più approfondito prima di aggiungerli a un set di revisione, è possibile aggiungere un esempio dei risultati di ricerca a un set di revisione invece di aggiungere tutto.

Per aggiungere un esempio a un set di revisione, fare clic su una ricerca nella scheda **ricerche** e fare clic su **campionamento** nella pagina a comparsa. Nella pagina **parametri di campionamento** scegliere una delle opzioni seguenti:

- **Livello di confidenza%** e **intervallo di confidenza%** -gli elementi aggiunti al set di revisione saranno determinati dai parametri statistici impostati. Se si utilizza in genere un livello di confidenza e un intervallo durante il campionamento dei risultati, specificarli nelle caselle di menu a discesa. In caso contrario, utilizzare le impostazioni predefinite.

- **% Casuale di esempio** -gli elementi aggiunti al set di revisione si basano su una selezione casuale della percentuale specificata del numero totale di elementi restituiti dalla ricerca.

Dopo aver selezionato e configurato una delle opzioni precedenti, scegliere un set di revisione in cui aggiungere il campione e quindi fare clic su **Invia**. Anche in questo caso, è possibile monitorare lo stato di avanzamento nella scheda **processi** o nella scheda **ricerche** monitorando lo stato nella colonna **set di dati aggiunta a revisione** .

## <a name="optical-character-recognition"></a>Riconoscimento ottico del carattere

Quando si aggiungono i risultati di ricerca a un set di revisione, la funzionalità di riconoscimento ottico dei caratteri (OCR) in Advanced eDiscovery estrae automaticamente il testo dalle immagini e include il testo dell'immagine con i dati aggiunti a un set di revisione. È possibile visualizzare il testo estratto nel Visualizzatore di testo del file di immagine selezionato nel set di revisione. In questo modo è possibile eseguire ulteriori riesami e analisi sul testo nelle immagini. OCR è supportato per file sciolti, allegati di posta elettronica e immagini incorporate. Per un elenco dei formati di file immagine supportati per l'OCR, vedere [tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).

È necessario abilitare la funzionalità OCR per ogni caso creato in Advanced eDiscovery. Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).