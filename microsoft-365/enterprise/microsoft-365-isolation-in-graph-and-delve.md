---
title: Microsoft 365 Isolamento tenant in Microsoft Graph e Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo, trovare una spiegazione del funzionamento Microsoft 365'isolamento del tenant nell'Office Graph e in Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464088"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365 Isolamento tenant in Microsoft Graph e Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Isolamento tenant in Microsoft Graph

[Microsoft Graph](https://developer.microsoft.com/graph) modella l'attività nei servizi di Microsoft 365, inclusi Exchange Online, SharePoint Online, Yammer, Skype for Business, Azure Active Directory e altro ancora, nonché nei servizi esterni, ad esempio altri servizi di servizi Microsoft o di terze parti. I Graph microsoft Microsoft 365. Microsoft Graph rappresenta una raccolta di contenuti e attività e le relazioni tra di essi che si verificano nell'intera Office suite. Usa sofisticate tecniche di machine learning per connettere le persone ai contenuti, alle conversazioni e alle persone pertinenti che le circondano. Ad esempio, l'indice tenant in SharePoint Online dispone di un indice di Microsoft Graph utilizzato per gestire le query Delve, il motore di elaborazione dell'analisi in SharePoint Online viene utilizzato per archiviare i segnali e calcolare le informazioni dettagliate e Exchange Online calcola la cache dei destinatari di ogni utente come input nell'analisi del tenant.

Microsoft Graph contiene informazioni sugli oggetti dell'organizzazione, ad esempio persone e documenti, nonché le relazioni e le interazioni tra questi oggetti. Le relazioni e le interazioni sono rappresentate come *bordi.* Microsoft Graph è segmentato in base al tenant in modo che i bordi possano esistere solo tra *i nodi* nella stessa tenancy. Un *nodo* è un'entità con un URI (Uniform Resource Identifier), un tipo di nodo, un elenco di controllo di accesso e un set di facet contenenti *metadati* e bordi. A ogni nodo sono associati metadati e bordi, disposti in *facet come* nel Modello di conoscenza comune. *I* metadati sono proprietà denominate archiviate in un nodo che possono essere utilizzate per la ricerca, il filtro o l'analisi all'interno di Microsoft Graph. Un *facet* è una raccolta logica di metadati e bordi in un nodo. Ogni facet descrive un aspetto di un nodo. 

Microsoft Graph non consente di importare tutti i dati in un singolo archivio. archivia invece metadati e relazioni sui dati che si trova altrove. Microsoft Graph è costituito da diversi archivi dati e componenti di elaborazione:

- Lo Store Graph Tenant fornisce l'archiviazione in blocco ottimizzata per l'analisi efficiente.
- La cache del contenuto attivo fornisce un accesso casuale rapido al nodo attivo e ai bordi per guidare le esperienze utente.
- Il router di input notifica ai componenti interni ed esterni le modifiche apportate al grafico del tenant.

L'analisi all'interno di ogni carico di lavoro deduce dati analitici rilevanti per i calcoli a livello di tenant e li inserisce nel grafico del tenant. Motivi di analisi del tenant su tutte le attività in una tenancy per produrre informazioni dettagliate sui modelli di comportamento. Ad esempio, Exchange Online la cache dei destinatari per ogni utente con dati analitici in grado di calcolare in modo efficiente la cassetta postale di ogni utente. Queste analisi per utente producono un set di *Bordi RecipientCache* su ogni persona, che vengono a loro volta inseriti nel grafico del tenant. In questo modo la maggior parte dell'elaborazione dell'analisi viene conservata il più vicino possibile ai dati di origine.

## <a name="tenant-isolation-in-delve"></a>Isolamento tenant in Delve

Come accennato in precedenza, Microsoft Graph offre esperienze che consentono agli utenti di individuare e collaborare alle attività correnti nella propria azienda e fornisce una piattaforma incentrata sulle entità per l'analisi per il motivo del contenuto e delle attività tra carichi di lavoro e oltre Microsoft 365. Delve è la prima esperienza di questo tipo basata su Microsoft Graph.
Delve è un'Microsoft 365 Web che consente di visualizzare il contenuto da Microsoft 365 Yammer Enterprise a Microsoft 365 utenti tramite Microsoft Graph. L'esperienza Web visualizza i dati come schede diverse, ognuna con un determinato argomento, ad esempio Tendenze intorno a *me* o *Modificato da me*. Ogni bacheca è costituita da diverse schede documento che visualizzano testo di riepilogo e un'immagine del documento. La scheda consente agli utenti di eseguire operazioni quali l'apertura del documento o Yammer pagina del documento. È disponibile una pagina per ogni persona in un tenant di Microsoft 365 che visualizza i documenti più rilevanti per questa persona e icone che possono richiamare Exchange Online o Skype for Business per interagire con tale persona. Poiché Delve è basata sull'API di Microsoft Graph, è associata all'isolamento basato sul tenant di tale API.