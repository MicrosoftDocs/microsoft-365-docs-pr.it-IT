---
title: Utilizzare Microsoft Search per trovare argomenti in Microsoft Viva Topics
ms.author: chuckedmonson
author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Informazioni su come cercare argomenti in Microsoft Viva.
ms.openlocfilehash: 3bd247bfacc6a85bb19c8f4eeedb5aad8662e60e
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908066"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Utilizzare Microsoft Search per trovare argomenti in Microsoft Viva Topics

Anche se gli utenti di Viva Topics possono trovare argomenti attraverso le evidenziazioni degli argomenti nei propri siti SharePoint, possono trovarli anche tramite Microsoft Search. 

## <a name="topic-answer"></a>Risposta argomento

Quando si cerca un argomento specifico dalla pagina iniziale di SharePoint, in Office.com o da un sito di SharePoint con ambito per l'organizzazione, se esiste e viene trovato un argomento, il risultato verrà visualizzato nel formato di suggerimento per la risposta all'argomento.

Verrà visualizzata la risposta all'argomento:

- Nome dell'argomento
- Nomi alternativi: nomi alternativi o acronimi dell'argomento.
- Definizione: descrizione dell'argomento fornito dalla IA o aggiunto manualmente da una persona.
- Persone suggerite o aggiunte: persone suggerite dall'IA o aggiunte all'argomento da una persona
- Risorse suggerite o aggiunte: file, pagine o siti suggeriti dall'IA o aggiunti all'argomento da una persona. 

   ![Argomento nella ricerca](../media/knowledge-management/search-topic-answer.png) 

La pagina dell'argomento può essere visualizzata nei risultati della ricerca anche se la scheda di risposta dell'argomento non viene visualizzata.

I risultati della ricerca in Word, PowerPoint, Outlook e Excel inoltre la risposta dell'argomento quando ne viene trovata una.

## <a name="acronyms"></a>Acronimi

In Viva Topics è possibile modificare manualmente un argomento in modo da includere un acronimo come *nome alternativo.* In questo modo un utente che esegue una ricerca solo con l'acronimo dell'argomento può trovare la risposta all'argomento tramite Microsoft Search.

[L'acronimo Answers](/microsoftsearch/manage-acronyms) è una funzionalità fornita da Microsoft Search ed è gestita separatamente da Viva Topics.

## <a name="bookmarks-and-topics"></a>Segnalibri e argomenti

[I segnalibri](/microsoftsearch/manage-bookmarks) sono una funzionalità di Microsoft Search che consente agli utenti di trovare rapidamente siti e strumenti importanti con una semplice ricerca (ad esempio, uno strumento di prenotazione di viaggi in un sito esterno all'esterno del tenant di Microsoft 365). Vengono creati dagli amministratori della ricerca nell'Microsoft 365 di amministrazione. 

Per gli utenti che cercano informazioni sulla prenotazione di un viaggio di lavoro:

- Se alcuni utenti conoscono il nome dello strumento di viaggio (ad esempio, "Concur"), è più semplice creare un segnalibro per passare direttamente al sito esterno.

- Per gli utenti che in genere ricercano "viaggi", crea un argomento su "Viaggi" con le informazioni che si aspettano di visualizzare. Prendere in considerazione l'aggiunta di un collegamento al sito esterno Concur nella descrizione dell'argomento. Se invece il collegamento è a un sito di prenotazione viaggi interno ospitato nel tenant di Microsoft 365, puoi aggiungerlo alle "Risorse aggiunte".
 
### <a name="search-results-priority"></a>Priorità dei risultati della ricerca 

Nell'esperienza di ricerca dell'utente, quando un utente cerca un termine come "viaggio", viene visualizzato un segnalibro al posto di un argomento, se è disponibile un segnalibro.

## <a name="see-also"></a>Vedere anche

[Panoramica di Viva Topics](topic-experiences-overview.md)
