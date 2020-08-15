---
title: Isolamento del tenant Microsoft 365 in Microsoft Graph and approfondire
ms.author: josephd
author: JoeDavies-MSFT
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
description: In questo articolo, trovare una spiegazione di come funziona l'isolamento del tenant di Microsoft 365 in Office Graph e in approfondire.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab9b216656e076cc3ba02a4ef6c75b25b94547fe
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691285"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Isolamento del tenant Microsoft 365 in Microsoft Graph and approfondire

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Isolamento tenant in Microsoft Graph

L'attività dei modelli di [Microsoft Graph](https://developer.microsoft.com/graph) in Microsoft 365 Services, tra cui Exchange Online, SharePoint Online, Yammer, Skype for business, Azure Active Directory e altro ancora, e nei servizi esterni, ad esempio altri servizi Microsoft o servizi di terze parti. I componenti di Microsoft Graph vengono utilizzati in Microsoft 365. Il grafico Microsoft rappresenta un insieme di contenuto e attività e le relazioni tra di esse che si verificano nell'intera famiglia di prodotti Office. Utilizza sofisticate tecniche di apprendimento automatico per connettere le persone ai contenuti, alle conversazioni e alle persone rilevanti che li circondano. Ad esempio, l'indice tenant in SharePoint Online ha un indice di Microsoft Graph utilizzato per fornire query approfondite, il motore di elaborazione dell'analisi in SharePoint Online viene utilizzato per archiviare i segnali e calcolare gli Insight e Exchange Online calcola la cache dei destinatari di ogni utente come input nell'analisi del tenant.

Microsoft Graph contiene informazioni sugli oggetti dell'organizzazione, ad esempio persone e documenti, nonché sulle relazioni e le interazioni tra questi oggetti. Le relazioni e le interazioni sono rappresentate come *spigoli*. Il grafico Microsoft viene segmentato dal tenant in modo che i bordi possano esistere solo tra i *nodi* dello stesso contratto di locazione. Un *nodo* è un'entità con un URI (Uniform Resource Identifier), un tipo di nodo, un elenco di controllo di accesso e un set di facet che contengono *metadati* e spigoli. A ciascun nodo sono associati metadati e spigoli, disposti in *facet* come nel modello di conoscenza comune. I *metadati* sono proprietà denominate archiviate in un nodo che è possibile utilizzare per la ricerca, il filtro o l'analisi all'interno di Microsoft Graph. Un *facet* è una raccolta logica di metadati e spigoli su un nodo. Ogni facet descrive un aspetto di un nodo. 

Microsoft Graph non porta tutti i dati in un unico repository; piuttosto, memorizza i metadati e le relazioni sui dati che vivono altrove. Microsoft Graph è costituito da diversi archivi dati e componenti di elaborazione:

- L'archivio grafico tenant fornisce archiviazione di massa ottimizzata per analisi efficienti.
- La cache del contenuto attivo fornisce un accesso casuale rapido ai nodi e ai bordi attivi per guidare le esperienze degli utenti.
- Il router di input notifica ai componenti interni ed esterni le modifiche apportate al grafico tenant.

L'analisi all'interno di ogni carico di lavoro deduce informazioni rilevanti per i calcoli a livello di tenant e li inserisce nel grafico tenant. I motivi di analisi tenant su tutte le attività in una locazione per produrre informazioni su modelli di comportamento. Ad esempio, Exchange Online calcola la cache dei destinatari per ogni utente con analisi che ragionano efficacemente sulla cassetta postale di ogni utente. Queste analisi per utente producono un insieme di *spigoli RecipientCache* su ogni persona, che a sua volta vengono spinte nel grafico tenant. In questo modo il processo di analisi viene mantenuto il più vicino possibile ai dati di origine.

## <a name="tenant-isolation-in-delve"></a>Isolamento del tenant nell'approfondimento

Come accennato in precedenza, Microsoft Graph Powers experiences che aiuta gli utenti a individuare e collaborare alle attività correnti nell'organizzazione e fornisce una piattaforma basata su entità per l'analisi per ragionare sul contenuto e sulle attività tra i carichi di lavoro e oltre Microsoft 365. Approfondire è la prima esperienza di questo tipo alimentata da Microsoft Graph.
Approfondire è un'esperienza Web di Microsoft 365 che consente di visualizzare il contenuto da Microsoft 365 e Yammer Enterprise agli utenti di Microsoft 365 tramite Microsoft Graph. L'esperienza Web consente di visualizzare i dati come schede diverse, ognuna con un determinato argomento, ad esempio i *trend attorno a me* o *modificati da me*. Ogni scheda è costituita da diverse schede documento che visualizzano testo di riepilogo e un'immagine del documento. La scheda consente agli utenti di eseguire operazioni come aprire il documento o una pagina di Yammer per il documento. Vi è una pagina per ogni persona in un tenant di Microsoft 365 che Visualizza i documenti più rilevanti per questa persona e le icone che possono richiamare Exchange Online o Skype for business per interagire con quella persona. Poiché il servizio di approfondimento è basato sull'API di Microsoft Graph, è associato all'isolamento basato sul tenant di quell'API.