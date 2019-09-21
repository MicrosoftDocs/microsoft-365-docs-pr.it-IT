---
title: Ricerca e tagging
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: In Advanced eDiscovery, il modulo di ricerca e tagging consente di cercare, visualizzare in anteprima e organizzare i documenti nel caso. Attualmente, questo modulo è in versione beta.
ms.openlocfilehash: b3e660e6dca014323cfd06f10c14747751aeb386
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084170"
---
# <a name="search-and-tagging"></a>Ricerca e tagging

In Advanced eDiscovery, il modulo di ricerca e tagging consente di cercare, visualizzare in anteprima e organizzare i documenti nel caso. Attualmente, questo modulo è in versione beta. Per una breve dimostrazione di ricerca e tagging, vedere la pagina [Gestisci i dati con Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Eseguire una ricerca nei documenti nel caso

Dopo aver elaborato i documenti in un caso avanzato di eDiscovery (e, facoltativamente, eseguire il modulo Analyze o pertinenza), è possibile utilizzare la ricerca e il tagging per i documenti di ricerca e quindi organizzarli applicando tag case-specific (denominati anche etichette). È possibile definire una query di ricerca utilizzando le schede delle condizioni fornite o utilizzando un linguaggio di query di tipo KQL nella scheda condizione parole chiave. Sono supportate la sintassi KQL comune, ad esempio e, o, non e vicino (n), nonché il carattere jolly a più caratteri finale (*). 

Nella tabella seguente sono elencate le proprietà che è possibile cercare utilizzando una query di parole chiave di KQL. In alternativa, è possibile utilizzare una scheda di condizione per lo strumento di ricerca di eDiscovery avanzato per aggiungere una condizione (per le proprietà selezionate) a una query di ricerca.

|**Proprietà**|**Descrizione**|
|:-----|:-----|
|**caselabel** <br/> | Nome del tag creato/applicato quando un documento è contrassegnato. <br/> |
|**custode** <br/> | Il custode associato a un documento. soggette a limitazioni. <br/> |
|**Data** <br/> | Data di invio per la posta elettronica; la data di modifica per i documenti del sito. <br/> |
|**fileid** <br/> | ID file all'interno del caso. <br/> |
|**filetype** <br/> | L'estensione di file nativa. <br/> |
|**fileclass** <br/> | Posta elettronica, documento o allegato. <br/> |
|**senderauthor** <br/> | Il mittente per la posta elettronica; autore per i documenti del sito. <br/> |
|**dimensione** <br/> | Le dimensioni del file in KB. <br/> |
|**subjecttitle** <br/> | L'oggetto per la posta elettronica; il titolo per i documenti del sito. <br/> |
|**bcc** <br/> | Il campo Ccn di un messaggio di posta elettronica. <br/> |
|**cc** <br/> | Campo CC di un messaggio di posta elettronica. <br/> |
|**partecipanti** <br/> | L'indirizzo di posta elettronica di tutti i partecipanti a un thread di posta elettronica, inclusi i collegamenti mancanti. <br/> |
|**ricevuto** <br/> | La data di ricezione di un messaggio di posta elettronica. <br/> |
|**destinatari** <br/> | Destinatari di un messaggio di posta elettronica, incluso nei campi a, CC o Ccn. <br/> |
|**mittente** <br/> | Il mittente di un messaggio di posta elettronica. <br/> |
|**LastModifiedDate** <br/> | Data dell'Ultima modifica di un documento del sito. <br/> |
|**inviati** <br/> | La data di invio di un messaggio di posta elettronica. <br/> |
|**A** <br/> | Il destinatario elencato nel campo a di un messaggio di posta elettronica. <br/> |
|**autore** <br/> | Autore di un documento del sito. <br/> |
|**titolo** <br/> | Il titolo di un documento del sito. <br/> |
|**dominanttheme**\* <br/> | Il tema dominante di un elemento. <br/> |
|**tema**\* <br/> | Temi associati a un elemento. <br/> |
|**readpercentile_[issuenum]**\*\* <br/> | Il percentile di lettura di un elemento, per il problema definito da [issuenum]. <br/> |
|**relevancescore_[issuenum]**\*\* <br/> | Il Punteggio di pertinenza di un elemento, per il problema definito da [issuenum]. <br/> |
|**relevancetag_ [TagName]**\*\* <br/> | Se un elemento è stato contrassegnato manualmente per la pertinenza, il tag definito da [TagName]. <br/> |
|||

\*Disponibile solo se è stato eseguito il modulo temi.

\*\*Disponibile solo se è stato eseguito il modulo pertinenza.

In alternativa, è possibile utilizzare una scheda di condizione nello strumento di ricerca di eDiscovery avanzato per aggiungere una condizione (per le proprietà selezionate) a una query di ricerca. Nella schermata seguente vengono riportate le condizioni che è possibile aggiungere a una query. La colonna **gruppo** indica se la proprietà si applica ai messaggi di posta elettronica, ai documenti del sito o a entrambi (indicati dal valore *comune*). In questa colonna vengono inoltre identificate le proprietà disponibili per la ricerca che possono essere eseguite dopo l'esecuzione del modulo pertinenza.

![Condizioni di ricerca nello strumento di ricerca avanzato di eDiscovery](media/AeDSearchConditions.png)

Per ulteriori informazioni sulle proprietà disponibili per la ricerca, vedere [keyword query and Search Conditions](keyword-queries-and-search-conditions.md).
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione in rilevanza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Formazione di tagging e pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Verifica dell'analisi della pertinenza](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidere in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Verifica dell'analisi della pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

