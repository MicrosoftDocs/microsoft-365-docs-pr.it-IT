---
title: Aggiungere i risultati della ricerca a un insieme da rivedere
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
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come aggiungere risultati di ricerca o esempi di tali risultati a un set di Advanced eDiscovery di revisione dei casi.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919978"
---
# <a name="add-search-results-to-a-review-set"></a>Aggiungere i risultati della ricerca a un insieme da rivedere

Quando si è soddisfatti dei risultati di una ricerca e si è pronti per esaminare e analizzare tali risultati di ricerca, è possibile aggiungerli a un set di recensioni nel caso. La copia dei dati originali nel set di revisione facilita inoltre il processo di revisione e analisi fornendo strumenti di analisi avanzati come il rilevamento dei temi, il rilevamento quasi duplicato e l'identificazione del thread di posta elettronica. È inoltre possibile aggiungere dati da origini dati non Microsoft 365 a un set di recensioni in modo da poter esaminare i dati oltre ai dati raccolti da Microsoft 365.

Quando si aggiungono i risultati di una ricerca a un set di recensioni (i set di revisione in un caso sono elencati nella scheda **Set di** revisione), si verificano le operazioni seguenti:

- La ricerca viene eseguita di nuovo. Ciò significa che i risultati della ricerca effettivi copiati nel set di revisione potrebbero essere diversi dai risultati stimati restituiti all'ultima esecuzione della ricerca.

- Tutti gli elementi nei risultati della ricerca vengono copiati dall'origine dati originale nei servizi live e copiati in un percorso Archiviazione di Azure sicuro nel cloud Microsoft.

- Tutti gli elementi (inclusi il contenuto e i metadati) vengono reindicizzati in modo che tutti i dati nel set di revisione siano completamente ricercabili durante la revisione dei dati del caso. La reindicizzazione dei dati comporta ricerche approfondite e veloci quando si esere ricerche nei dati nel set di revisione durante l'indagine del caso.

- Un file crittografato con una tecnologia di crittografia [Microsoft](encryption.md) e allegato a un messaggio di posta elettronica restituito nei risultati della ricerca viene decrittografato quando il messaggio di posta elettronica e il file allegato vengono aggiunti al set di recensioni. È possibile esaminare ed eseguire query sul file decrittografato nel set di revisione. Per aggiungere allegati di posta elettronica decrittografati a un set di revisioni, è necessario disporre del ruolo di decrittografia RMS. Per ulteriori informazioni, vedere [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

Per aggiungere dati a un set di  revisioni, fare clic su una ricerca nella scheda Ricerche e quindi fare clic su Aggiungi risultati per **rivedere il set** nella pagina a comparsa.

È possibile aggiungere un set di recensioni esistente o crearne uno nuovo.  Se si aggiunge un nuovo set di recensioni, specificare il nome e quindi fare clic su **Aggiungi** per visualizzare la pagina a comparsa.

![Selezionare un set di revisione e configurare le opzioni di raccolta](../media/AeD_AddToReviewSet.png)

L'aggiunta di dati a un insieme da rivedere è un processo a esecuzione prolungata. Questo processo include la raccolta di elementi dalle origini dati originali in Microsoft 365 (ad esempio, da cassette postali e siti), la copia nel percorso di Archiviazione di Azure (questo processo di copia è denominato anche *inserimento)* e quindi la reindicizzazione degli elementi. È possibile tenere traccia dello stato  nella scheda **Processi** o nella scheda Ricerche monitorando lo stato nella colonna Dati aggiunti **da rivedere.** Al termine dell'elaborazione del  set di revisione, fare clic sulla scheda Revisione set nel caso, quindi fare clic sul set di revisione per avviare il processo di filtro, revisione, tagging ed esportazione dei dati nel set di recensioni.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definire le opzioni per definire l'ambito della raccolta per la revisione

Quando si aggiunge il contenuto di una ricerca a un set di recensioni esistente o nuovo, sono disponibili le opzioni seguenti per raccogliere il contenuto per la revisione:

- **Includi versioni di SharePoint (beta):** utilizzare questa opzione per abilitare la raccolta di tutte le versioni di un documento di SharePoint in base ai limiti di versione e ai parametri di ricerca della raccolta. Se si seleziona questa opzione, le dimensioni degli elementi aggiunti al set di revisioni verranno notevolmente aumentate.

- **Opzioni di recupero delle** conversazioni : gli elementi aggiunti al set di revisione sono abilitati per le conversazioni in thread per consentire la revisione del contenuto nel contesto della conversazione precedente e precedente. Per ulteriori informazioni, vedere [Review conversations in Advanced eDiscovery](conversation-review-sets.md).

- **Abilita il recupero per gli allegati moderni**: utilizzare questa opzione per includere allegati moderni o file collegati nella raccolta per un'ulteriore revisione. Per ulteriori informazioni sulle proprietà disponibili per la ricerca relative agli allegati moderni, vedere [Campi dei metadati del documento in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="add-a-sample-to-a-review-set"></a>Aggiungere un esempio a un set di recensioni

Se si desidera convalidare più accuratamente i risultati di una ricerca prima di aggiungerli tutti a un set di recensioni, è possibile aggiungere un campione dei risultati della ricerca a un set di recensioni anziché aggiungere tutto.

Per aggiungere un esempio a un set di recensioni, fare clic su una ricerca nella **scheda** Ricerche e fare clic su **Esempio** nella pagina a comparsa. Nella pagina **Parametri di campionamento** scegliere una delle opzioni seguenti:

- **Livello di confidenza %** e Intervallo di confidenza **%** - Gli elementi aggiunti al set di recensioni saranno determinati dai parametri statistici impostati. Se in genere si utilizzano un livello di confidenza e un intervallo durante il campionamento dei risultati, specificarli nelle caselle di riepilogo a discesa. In caso contrario, utilizzare le impostazioni predefinite.

- **% campione casuale** - Gli elementi aggiunti al set di recensioni si basano su una selezione casuale della percentuale specificata del numero totale di elementi restituiti dalla ricerca.

Dopo aver selezionato e configurato una delle opzioni precedenti, scegliere un set di recensioni a cui aggiungere l'esempio e quindi fare clic su **Invia.** Anche in questo caso,  è possibile tenere  traccia dello stato nella scheda Processi o nella scheda Ricerche monitorando lo stato nella colonna Dati aggiunti **da rivedere.**

## <a name="optical-character-recognition"></a>Riconoscimento ottico dei caratteri

Quando aggiungi risultati di ricerca a un set di recensioni, la funzionalità OCR (Optical Character Recognition) in Advanced eDiscovery estrae automaticamente il testo dalle immagini e include il testo dell'immagine con i dati aggiunti a un set di recensioni. È possibile visualizzare il testo estratto nel visualizzatore di testo del file di immagine selezionato nel set di revisioni. In questo modo è possibile eseguire ulteriori revisioni e analisi del testo nelle immagini. OCR è supportato per file liberi, allegati di posta elettronica e immagini incorporate. Per un elenco dei formati di file di immagine supportati per OCR, visualizzare [Tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).

È necessario abilitare la funzionalità OCR per ogni caso creato in Advanced eDiscovery. Per ulteriori informazioni, vedere [Configure search and analytics settings.](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)
