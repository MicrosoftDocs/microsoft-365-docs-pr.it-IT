---
title: Esaminare i dati nelle prove
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
description: Informazioni sui metodi per esaminare i dati dell'evidenza, ad esempio la visualizzazione in formato nativo, testo o quasi nativo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f094718bd14ee86ff8fdae482e86c22ecfbdc483
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034610"
---
# <a name="review-the-data-in-evidence"></a>Esaminare i dati nelle prove

I dati di un set di evidenze in un'analisi dei dati sono uno snapshot dei risultati della ricerca raccolti e aggiunti al set di evidenze. Quando si aggiungono i risultati della ricerca all'evidenza, viene attivato un processo per estrarre file, metadati e testo dagli elementi restituiti dalla ricerca. Successivamente, lo strumento indagini dati (Preview) crea un nuovo indice (tramite un processo denominato *Advanced indicizzazione*) di tutti i dati e aggiunge a un set di evidenze nella scheda **Evidence** . 

Per le indagini sensibili al tempo, in questo modo è possibile contenere rapidamente l'ambiente eliminando i dati effettivamente versati o dannosi che si trovano nell'origine dati originale, mentre allo stesso tempo è possibile esaminare l'evidenza ricreata in un ambiente in quarantena, che in questo caso è la copia dei dati nel set di evidenze. Dopo la raccolta e l'aggiunta dell'evidenza al set di evidenze, è possibile esaminare i singoli documenti nel formato nativo, nel formato di testo o in un formato quasi nativo che è possibile utilizzare per annotare e redigere i documenti. È inoltre possibile eseguire query per limitare il set di dati in base a intervallo di tempo, tipi di file, proprietari di dati e molte altre proprietà e condizioni di ricerca. Ad esempio, utilizzando le condizioni di autore, mittente o destinatario, è possibile identificare rapidamente le persone coinvolte nell'incidente e se i dati dell'organizzazione sono stati condivisi con utenti esterni. Per ulteriori informazioni sulla ricerca di dati in un set di evidenze, vedere [query the data in evidence](evidence-query.md).

Per raggruppare i documenti e ottenere assistenza per la revisione, selezionare un set di evidenze nella scheda **Evidence** e quindi fare clic su **Gestisci prova**. Nel riquadro **analisi** fare clic su **Ricostruisci analisi per l'intero set**. Verrà eseguito l'analisi avanzata, ad esempio il rilevamento duplicato, il threading di posta elettronica e l'analizzatore dei temi. Successivamente, è possibile visualizzare i temi generali dei dati e anche organizzare i documenti tramite thread di posta elettronica, vicino a duplicati e duplicati esatti per facilitare l'indagine. Per ulteriori informazioni, vedere [Run Analytics to investigate Faster](run-analytics-to-investigate-faster.md).

## <a name="view-documents-in-evidence"></a>Visualizzare i documenti in evidenza

Indagini sui dati (Preview) consente di visualizzare il contenuto in diversi visualizzatori, in cui ogni visualizzatore ha uno scopo diverso. Questi visualizzatori sono:

- Metadati dei file
- Visualizzazione nativa
- Visualizzazione testo
- Visualizzazione annotazioni

Per accedere a uno di questi visualizzatori, è sufficiente selezionare un documento in un set di evidenze.

## <a name="file-metadata"></a>Metadati dei file

In questa visualizzazione vengono visualizzate varie proprietà dei metadati associate al documento selezionato. È possibile attivare o disattivare questa visualizzazione facendo clic su **metadati file**. Quando si esegue la revisione di un documento, è possibile visualizzare i metadati dei file e comunque cambiarli tra i diversi visualizzatori.

Di seguito è riportato un esempio dei metadati di file per un documento. Per ulteriori informazioni sui campi dei metadati, vedere [documento dei campi di metadati nelle indagini sui dati (Preview)](document-metadata-fields.md).

![Pannello metadati file](../media/Reviewimage2.png)

## <a name="native-view"></a>Visualizzazione nativa

Il Visualizzatore nativo Visualizza la visualizzazione più accurata di un documento nel formato nativo. La visualizzazione nativa è supportata per centinaia di tipi di file ed è destinata a visualizzare i documenti in una delle più vere esperienze native possibili. Per i file di Microsoft Office, il Visualizzatore nativo utilizza la versione Web delle app di Office. In questo modo è possibile visualizzare il contenuto, ad esempio i commenti in documenti di Office, formule e righe/colonne nascoste in Excel, e la visualizzazione note in PowerPoint.

![Visualizzazione nativa
](../media/Reviewimage3.png)

## <a name="text-view"></a>Visualizzazione testo

Il Visualizzatore di testo consente di visualizzare il testo estratto di un file. Ignora tutte le immagini e la formattazione incorporate, ma questa visualizzazione è molto utile se si sta tentando di esaminare e comprendere rapidamente il contenuto di un documento. La visualizzazione del testo include anche queste caratteristiche:

  - Un contatore di linea, che rende più facile fare riferimento a parti specifiche di un documento.

  - Ricerca hit highlighting che evidenzia i termini del documento e della barra di scorrimento

  - Una visualizzazione diff fornisce una visualizzazione di confronto in cui vengono evidenziate le differenze di testo quando si visualizzano i documenti utilizzando il riquadro **quasi duplicati** .

**Esempio di contatore di riga e di evidenziazione dei risultati della ricerca in testo e barra di scorrimento**

![Visualizzazione testo
](../media/Reviewimage4.png)

**Esempio di visualizzazione diff**

![Visualizzazione diff
](../media/Reviewimage5.png)

## <a name="annotate-view"></a>Visualizzazione annotazioni

La visualizzazione annotazioni fornisce caratteristiche che consentono di applicare il markup su un documento durante il processo di revisione. sono inclusi gli strumenti seguenti:

  - **Redazioni area** : è possibile disegnare una casella opaca nel documento che nasconde contenuto sensibile.

  - **Matita** – è possibile disegnare a mano libera su un documento per attirare l'attenzione su determinate parti del contenuto.

  - **Seleziona annotazioni** : è possibile selezionare ed eliminare le annotazioni in un documento.

  - **Toggle Transparency Annotation** – è possibile alternare la trasparenza delle annotazioni (tra opaco e semitrasparente) in modo da poter visualizzare il contenuto dietro l'annotazione. Questo include l'attivazione della trasparenza delle annotazioni e dei redazioni di matite.

La visualizzazione annotazioni fornisce anche la funzionalità di spostamento seguente:

  - **Pagina precedente**, **pagina successiva**e **passare ai** controlli di spostamento della pagina da utilizzare per i documenti a più pagine.

  - **Zoom** : aumenta o diminuisce le dimensioni dei documenti nella visualizzazione annotazioni.

  - **Ruota** – ruota i documenti in senso orario.

  - **Ricerca** : cercare le parole chiave in un documento e quindi utilizzare i controlli precedenti e successivi per visualizzare i risultati evidenziati all'interno del documento.

**Esempio di visualizzazione annotazioni**

![Visualizzazione annotazioni](../media/Reviewimage1.png)

> [!NOTE]
> Le annotazioni vengono applicate a una copia del documento che è stato aggiunto al set di evidenze. I documenti originali del servizio Live non vengono annotati.
