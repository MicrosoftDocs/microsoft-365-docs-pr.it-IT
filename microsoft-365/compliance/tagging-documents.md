---
title: Contrassegnare i documenti in un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: L'aggiunta di tag ai documenti in un insieme da rivedere consente di rimuovere il contenuto non necessario e di identificare il contenuto pertinente in un caso di Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285282"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Contrassegnare i documenti in una recensione impostata in Advanced eDiscovery

L'organizzazione del contenuto in un insieme da rivedere è importante per completare vari flussi di lavoro nel processo di eDiscovery. Ciò include:

- Eliminare contenuti non necessari

- Identificazione del contenuto pertinente
 
- Identificazione dei contenuti che devono essere esaminati da un esperto o da un avvocato

Quando esperti, avvocati o altri utenti esaminano il contenuto in un insieme di recensioni, le loro opinioni relative al contenuto possono essere acquisite tramite tag. Ad esempio, se lo scopo è eliminare il contenuto non necessario, un utente può contrassegnare i documenti con un tag, ad esempio "non reattivo". Dopo che il contenuto è stato esaminato e contrassegnato, è possibile creare una ricerca di insieme da rivedere per escludere qualsiasi contenuto contrassegnato come "non reattivo", eliminando questo contenuto dai passaggi successivi del flusso di lavoro di eDiscovery. Il pannello di tag può essere personalizzato per ogni caso in modo che i tag possano supportare il flusso di lavoro di revisione previsto.

## <a name="tag-types"></a>Tipi di tag

Advanced eDiscovery offre due tipi di tag:

- **Tag a scelta singola:** limita gli utenti a selezionare un singolo tag all'interno di un gruppo. Ciò può essere utile per garantire che gli utenti non selezionano tag in conflitto, ad esempio "reattivi" e "non reattivi". Questi elementi verranno visualizzati come pulsanti di opzione.

- **Tag a scelta multipla:** consente agli utenti di selezionare più tag all'interno di un gruppo. Questi elementi verranno visualizzati come caselle di controllo.

## <a name="tag-structure"></a>Struttura tag

Oltre ai tipi di tag, è possibile usare la struttura di organizzazione dei tag nel pannello tag per rendere più intuitivo il tagging dei documenti. I tag sono raggruppati per sezioni. La ricerca di set di recensioni supporta la possibilità di eseguire ricerche in base al tag e alla sezione tag. Ciò significa che è possibile creare una ricerca di insieme da rivedere per recuperare i documenti contrassegnati con qualsiasi tag in una sezione.

![Sezioni tag nel pannello tag](../media/Tagtypes.png)

I tag possono essere ulteriormente organizzati annidandoli all'interno di una sezione. Ad esempio, se lo scopo è identificare e contrassegnare il contenuto con privilegi, la annidamento può essere usata per chiarire che un utente può contrassegnare un documento come "Privilegiato" e selezionare il tipo di privilegio controllando il tag annidato appropriato.

![Tag annidati all'interno di una sezione tag](../media/Nestingtags.png)

## <a name="applying-tags"></a>Applicazione di tag

Esistono diversi modi per applicare un tag al contenuto.

### <a name="tagging-a-single-document"></a>Applicazione di tag a un singolo documento

Quando si visualizza un documento in un insieme di revisioni, è possibile visualizzare i tag che possono essere utilizzati da una revisione facendo clic sul **pannello Tagging.**

![Fare clic sul pannello Tag per visualizzare il pannello tag](../media/Singledoctag.png)

In questo modo sarà possibile applicare tag al documento visualizzato nel visualizzatore.

### <a name="bulk-tagging"></a>Aggiunta di tag in blocco

Il tagging in blocco può essere eseguito selezionando più file nella griglia dei risultati e quindi usando i tag nel pannello Tagging in modo simile al **tagging** di singoli documenti. L'annullamento del tagging in blocco può essere eseguito selezionando i tag due volte. Il primo clic applica il tag e la seconda selezione garantisce che il tag sia cancellato per tutti i file selezionati.

![Screenshot della descrizione di un telefono cellulare generata automaticamente](../media/Bulktag.png)

> [!NOTE]
> Quando si esegue il tagging in blocco, il pannello di tagging visualizza un conteggio dei file contrassegnati per ogni tag nel pannello.

### <a name="tagging-in-other-review-panels"></a>Aggiunta di tag in altri pannelli delle recensioni

Durante la revisione dei documenti, è possibile utilizzare gli altri pannelli delle revisioni per esaminare altre caratteristiche dei documenti nella griglia dei risultati. Ciò include la revisione di altri documenti correlati, thread di posta elettronica, quasi duplicati e duplicati hash. Ad esempio, quando si rivendono documenti  correlati (utilizzando il riquadro revisione della famiglia di documenti), è possibile ridurre significativamente i tempi di revisione contrassegnando in blocco i documenti correlati. Ad esempio, se un messaggio di posta elettronica contiene diversi allegati e si desidera garantire che l'intera famiglia sia contrassegnata in modo coerente.

Ad esempio, ecco come visualizzare il pannello **Tagging** quando si usa il pannello **Revisione famiglia** di documenti:

1. Con il riquadro delle revisioni aperto per un documento selezionato(ad  esempio, visualizzando l'elenco dei contenuti correlati nel riquadro revisione della famiglia di documenti, fare clic su Tag **documenti** nel riquadro di revisione della famiglia di documenti.

   Il riquadro di tagging viene visualizzato come finestra popup.

2. Scegliere uno o più tag per applicare il documento selezionato. 

3. Per contrassegnare tutti i documenti, selezionare tutti i documenti nel riquadro Famiglia di documenti, fare clic su Tag documenti e quindi scegliere i tag da applicare all'intera famiglia di documenti. 

![Screenshot di un post di social media Descrizione generata automaticamente](../media/Relatedtag.png)
