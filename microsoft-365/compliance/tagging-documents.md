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
description: L'aggiunta di tag ai documenti in un set di revisioni consente di rimuovere il contenuto non necessario e di identificare il contenuto pertinente in Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736273"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Contrassegnare i documenti in un set di revisioni in Advanced eDiscovery

L'organizzazione del contenuto in un set di revisione è importante per completare vari flussi di lavoro nel processo di eDiscovery. Tra questi vi sono anche:

- Eliminare contenuto non necessario

- Identificazione del contenuto pertinente

- Identificazione del contenuto che deve essere esaminato da un esperto o da un avvocato

Quando esperti, avvocati o altri utenti esaminano il contenuto in un set di recensioni, le loro opinioni relative al contenuto possono essere acquisite utilizzando tag. Ad esempio, se lo scopo è eliminare il contenuto non necessario, un utente può contrassegnare i documenti con un tag, ad esempio "non reattivo". Dopo aver esaminato e taggato il contenuto, è possibile creare una ricerca nel set di recensioni per escludere qualsiasi contenuto contrassegnato come "non reattivo". Questo processo elimina il contenuto non reattivo dai passaggi successivi del flusso di lavoro di eDiscovery. Il riquadro di tagging in un set di revisione può essere personalizzato per ogni caso in modo che i tag supportino il flusso di lavoro di revisione previsto per il caso.

> [!NOTE]
> L'ambito dei tag è un Advanced eDiscovery caso. Ciò significa che un caso può avere un solo set di tag che i revisori possono usare per contrassegnare i documenti del set di revisione. Non è possibile configurare un set diverso di tag da utilizzare in set di revisione diversi nello stesso caso.

## <a name="tag-types"></a>Tipi di tag

Advanced eDiscovery fornisce due tipi di tag:

- **Tag a scelta** singola : limita i revisori alla selezione di un singolo tag all'interno di un gruppo. Questi tipi di tag possono essere utili per garantire che i revisori non selezionano tag in conflitto, ad esempio "reattivi" e "non reattivi". I tag a scelta singola vengono visualizzati come pulsanti di opzione.

- **Tag a scelta multipla**: consente alle recensioni di selezionare più tag all'interno di un gruppo. Questi tipi di tag vengono visualizzati come caselle di controllo.

## <a name="tag-structure"></a>Struttura tag

Oltre ai tipi di tag, la struttura dell'organizzazione dei tag nel pannello tag può essere usata per rendere più intuitivo l'applicazione di tag ai documenti. I tag sono raggruppati per sezioni. La ricerca dei set di recensioni supporta la possibilità di eseguire ricerche per tag e per sezione tag. Ciò significa che puoi creare una ricerca di set di recensioni per recuperare i documenti contrassegnati con qualsiasi tag in una sezione.

![Sezioni di tag nel pannello tag](../media/TagTypes.png)

Puoi organizzare ulteriormente i tag annidandoli all'interno di una sezione. Ad esempio, se lo scopo è identificare e contrassegnare il contenuto con privilegi, è possibile utilizzare la annidamento per chiarire che un revisore può contrassegnare un documento come "privilegiato" e selezionare il tipo di privilegio controllando il tag annidato appropriato.

![Tag annidati all'interno di una sezione tag](../media/NestingTags.png)

## <a name="create-tags"></a>Creare tag

Prima di applicare tag ai documenti nel set di revisioni, è necessario creare una struttura di tag.

1. Aprire un set di revisioni e passare alla barra dei comandi e selezionare **Tag per query.**

2. Nel pannello di tagging seleziona **Gestisci opzioni tag**

3. Seleziona **Aggiungi sezione tag.**

4. Digitare il titolo di un gruppo di tag e una descrizione facoltativa e quindi fare clic su **Salva.**

5. Seleziona il menu a discesa con tre puntini accanto al titolo del gruppo di tag e fai clic **sulla casella di** controllo Aggiungi o sul pulsante di opzione **Aggiungi.**

6. Digitare un nome e una descrizione per la casella di controllo o il pulsante di opzione.

7. Ripeti questo processo per creare nuove sezioni di tag, opzioni di tag e caselle di controllo.

   ![Configurare la struttura dei tag](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a>Applicazione di tag

Con la struttura dei tag impostata, i revisori possono applicare tag ai documenti di un set di revisioni. Esistono due modi diversi per applicare i tag:

- Tag file

- Tag per query

### <a name="tag-files"></a>Tag file

Indipendentemente dal fatto che si selezioni un singolo elemento o più elementi in un set di revisioni, è possibile applicare tag alla selezione facendo clic su **Tag file** nella barra dei comandi. Nel pannello di tagging puoi selezionare un tag e applicarlo automaticamente ai documenti selezionati.

![Contrassegnare i file selezionati](../media/TagFile2.png)

> [!NOTE]
> I tag verranno applicati solo agli elementi selezionati nell'elenco di elementi.

### <a name="tag-by-query"></a>Tag per query

L'applicazione di tag tramite query consente di applicare tag a tutti gli elementi visualizzati da una query di filtro attualmente applicata nel set di revisioni.

1. Deselezionare tutti gli elementi nel set di revisione e passare alla barra dei comandi e selezionare **Contrassegna per query**.

2. Nel riquadro di tagging seleziona il tag che vuoi applicare.

3. **Nell'elenco a discesa Selezione tag** sono disponibili tre opzioni che determinano a quali elementi applicare il tag.

   - **Elementi che corrispondono a query applicata**: applica tag a elementi specifici che soddisfano le condizioni della query di filtro.

   - **Includi elementi famiglia associati**: applica tag a elementi specifici che soddisfano le condizioni della query di filtro e gli elementi della famiglia associati. *Gli elementi della* famiglia sono elementi che condividono lo stesso valore di metadati FamilyId.  

   - **Includi elementi di conversazione associati**: applica tag agli elementi che soddisfano le condizioni di query del filtro e agli elementi di conversazione associati. *Gli elementi di* conversazione sono elementi che condividono gli stessi valori dei metadati ConversationId.

   ![Selezione tag](../media/TagByQuery2.png)

4. Fare **clic su Avvia processo di tagging** per attivare il processo di tagging.

## <a name="tag-filter"></a>Filtro tag

Utilizzare il filtro tag nel set di revisione per trovare o escludere rapidamente elementi dai risultati della query in base alla modalità di applicazione di tag a un elemento. 

1. Seleziona **Filtri** per espandere il pannello dei filtri.

2. Selezionare ed espandere **Proprietà elemento**.

3. Scorrere verso il basso per trovare il filtro denominato **Tag,** selezionare la casella di controllo e quindi fare clic su **Fine.**

4. Per includere o escludere elementi con un tag specifico da una query, eseguire una delle operazioni seguenti:

   - **Includi elementi:** seleziona il valore del tag e seleziona Uguale a **uno qualsiasi** nel menu a discesa.

      Oppure

   - **Escludi** elementi : seleziona il valore del tag e seleziona Uguale **a nessuno nel** menu a discesa.

     ![Elementi di esclusione filtro tag](../media/TagFilterExclude.png)

> [!NOTE]
> Assicurati di aggiornare la pagina per assicurarti che il filtro tag visualizzi le modifiche più recenti alla struttura dei tag.
