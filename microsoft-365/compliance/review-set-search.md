---
title: Eseguire query sul contenuto di un set di recensioni
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
description: Informazioni su come creare ed eseguire una query in un set di recensioni per organizzare il contenuto per una revisione più efficiente in un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736421"
---
# <a name="query-and-filter-content-in-a-review-set"></a>Eseguire query e filtrare il contenuto in un set di recensioni

Nella maggior parte dei casi, sarà utile approfondire il contenuto di un set di recensioni e organizzarlo per facilitare una revisione più efficiente. L'utilizzo di filtri e query in un set di revisioni consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.

## <a name="default-filters"></a>Filtri predefiniti

In un set di recensioni sono presenti cinque filtri predefiniti precaricati nel set di recensioni:

- Parole chiave
- Data
- Mittente/Autore
- Oggetto/Titolo
- Tag

![Tipi di filtro predefiniti](../media/DefaultFilterTypes.png)

Fare clic su ogni filtro per espanderlo e assegnare un valore. Fare clic all'esterno del filtro per applicare automaticamente il filtro al set di revisioni. Lo screenshot seguente mostra il filtro Data configurato per visualizzare i documenti in un intervallo di date.

![Filtro predefinito espanso](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a>Aggiungere o rimuovere filtri

Per aggiungere o rimuovere i filtri visualizzati per il set di recensioni, selezionare **Filtri** per aprire il riquadro dei filtri, visualizzato in una pagina a comparsa. 

![Pannello filtro](../media/FilterPanel.png)

I filtri disponibili sono organizzati in quattro sezioni:

- **Ricerca:** filtri che forniscono funzionalità di ricerca diverse.

- **Analisi &** codifica predittiva : Filtri per le proprietà generate e aggiunte ai documenti quando si esegue il processo analitico di document **& tramite posta** elettronica o si utilizzano modelli di codifica predittivi.

- **ID: filtri** per tutte le proprietà ID dei documenti.

- **Proprietà elemento**: Filtri per le proprietà del documento. 

Espandi ogni sezione e seleziona o deseleziona i filtri per aggiungerli o rimuoverli nel set di filtri. Quando si aggiunge un filtro, questo viene visualizzato nel set di filtri. 

![Elenco delle sezioni e delle proprietà del filtro nel riquadro dei filtri](../media/FilterPanel2.png)

> [!NOTE]
> Quando espandi una sezione nel riquadro dei filtri, noterai che sono selezionati i tipi di filtro predefiniti. Puoi mantenerle selezionate o deselezionarle e rimosse dal set di filtri. 

## <a name="filter-types"></a>Tipi di filtro

Ogni campo ricercabile in un set di recensioni dispone di un filtro corrispondente che è possibile utilizzare per filtrare gli elementi in base a un campo specifico.

Esistono più tipi di filtri:

- **Testo libero**: viene applicato un filtro a testo libero ai campi di testo, ad esempio "Subject". È possibile elencare più termini di ricerca separandoli con una virgola.

- **Date**: viene utilizzato un filtro data per i campi data, ad esempio "Data ultima modifica".

- **Opzioni di** ricerca : un filtro delle opzioni di ricerca fornisce un elenco di valori possibili (ogni valore viene visualizzato con una casella di controllo che è possibile selezionare) per campi specifici nella revisione. Questo filtro viene utilizzato per i campi, ad esempio "Sender", in cui è presente un numero limitato di valori possibili nel set di revisione.

- **Parola** chiave: una condizione di parola chiave è un'istanza specifica della condizione a testo libero che è possibile utilizzare per cercare termini. È inoltre possibile utilizzare un linguaggio di query simile a KQL in questo tipo di filtro. Per ulteriori informazioni, vedere le sezioni Linguaggio query e Generatore di query avanzato in questo argomento.

## <a name="include-and-exclude-filter-relationships"></a>Includere ed escludere relazioni filtro

È possibile modificare la relazione di inclusione ed esclusione per un determinato filtro. Ad esempio, nel filtro Tag puoi escludere gli elementi contrassegnati  con un tag specifico selezionando Uguale a nessuno nel filtro a discesa. 

![Escludi filtro tag](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a>Salvare i filtri come query

Dopo aver soddisfatto i filtri, è possibile salvare la combinazione di filtri come query di filtro. In questo modo è possibile applicare il filtro nelle sessioni di revisione future.

Per salvare un filtro, selezionare **Salva la query e** assegnare un nome. È possibile eseguire query di filtro salvate  in precedenza selezionando l'elenco a discesa Query di filtro salvate e selezionando una query di filtro da applicare per esaminare i documenti impostati. 

![Salvare una query di filtro](../media/SaveFilterQuery.png)

Per eliminare una query di filtro, aprire il riquadro dei filtri e selezionare l'icona cestino accanto alla query.

![Eliminare una query di filtro](../media/DeleteFilterQuery.png)

## <a name="query-language"></a>Linguaggio di query

Oltre a utilizzare i filtri, è anche possibile utilizzare un linguaggio di query simile a KQL nel filtro Parole chiave per creare la query di ricerca del set di recensioni. Il linguaggio di query per le query di set di revisione supporta gli operatori Boolean standard, ad **esempio AND**, **OR**, **NOT** e **NEAR.** Supporta inoltre un carattere jolly a carattere singolo (?) e un carattere jolly a più caratteri (*).

## <a name="advanced-query-builder"></a>Generatore di query avanzato

È inoltre possibile creare query più avanzate per cercare documenti in un set di revisioni.

1. Apri il pannello dei filtri, seleziona **Filtri** ed espandi la **sezione** Ricerca.

  ![Aggiungere un filtro KQL](../media/AddKQLFilter.png)

2. Selezionare il **filtro KQL** e fare clic **su Apri generatore di query.**

   In questo pannello è possibile creare query KQL complesse utilizzando il generatore di query. È possibile aggiungere condizioni o gruppi di condizioni che sono costituito da più condizioni connesse logicamente da **relazioni AND** **o OR.**

   ![Utilizzare il generatore di query per configurare query di filtro complesse](../media/ComplexQuery.png)
