---
title: Isolamento del tenant di Microsoft 365 in Microsoft Graph e Delve
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
description: In questo articolo viene fornita una spiegazione del funzionamento dell'isolamento del tenant di Microsoft 365 in Office Graph e in Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332389"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Isolamento del tenant di Microsoft 365 in Microsoft Graph e Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Isolamento del tenant in Microsoft Graph

[Microsoft Graph](https://developer.microsoft.com/graph) modella l'attività nei servizi di Microsoft 365, tra cui Exchange Online, SharePoint Online, Yammer, Skype for Business, Azure Active Directory e altro ancora, e nei servizi esterni, come altri servizi Microsoft o servizi di terze parti. I componenti di Microsoft Graph vengono utilizzati in microsoft 365. Microsoft Graph rappresenta una raccolta di contenuti e attività e le relazioni che si verificano nell'intera famiglia di prodotti Office. Usa sofisticate tecniche di apprendimento automatico per connettere le persone al contenuto pertinente, alle conversazioni e alle persone che le circondano. Ad esempio, l'indice tenant in SharePoint Online dispone di un indice di Microsoft Graph utilizzato per gestire le query di Delve, il motore di elaborazione dell'analisi in SharePoint Online viene utilizzato per archiviare segnali e calcolare dati analitici e Exchange Online calcola la cache dei destinatari di ogni utente come input nell'analisi del tenant.

Microsoft Graph contiene informazioni sugli oggetti dell'organizzazione, ad esempio persone e documenti, nonché le relazioni e le interazioni tra tali oggetti. Le relazioni e le interazioni sono rappresentate come *bordi.* Microsoft Graph è segmentato in base al tenant in modo che i bordi possano esistere solo tra *i nodi* nella stessa tenancy. Un *nodo* è un'entità con un URI (Uniform Resource Identifier), un tipo di nodo, un elenco di controllo di accesso e un set di facet contenenti *metadati* e bordi. A ogni nodo sono associati metadati e bordi, disposti in *facet* come nel modello di conoscenza comune. *I* metadati sono proprietà denominate archiviate in un nodo che possono essere utilizzate per la ricerca, il filtro o l'analisi all'interno di Microsoft Graph. Un *facet* è una raccolta logica di metadati e bordi in un nodo. Ogni facet descrive un aspetto di un nodo. 

Microsoft Graph non consente di importare tutti i dati in un singolo archivio. archivia invece metadati e relazioni sui dati che si trova altrove. Microsoft Graph è costituito da diversi archivi dati ed elementi di elaborazione:

- L'archivio grafico tenant offre archiviazione in blocco ottimizzata per l'analisi efficiente.
- La cache del contenuto attivo fornisce accesso casuale rapido ai nodi attivi e ai bordi per guidare le esperienze utente.
- Il router di input notifica ai componenti interni ed esterni le modifiche apportate al grafico del tenant.

L'analisi all'interno di ogni carico di lavoro deduce informazioni rilevanti per i calcoli a livello di tenant e le inserisce nel grafico del tenant. I motivi di analisi del tenant su tutte le attività in una tenancy per produrre informazioni dettagliate sui modelli di comportamento. Ad esempio, Exchange Online calcola la cache dei destinatari per ogni utente con dati analitici in grado di elaborare in modo efficiente la cassetta postale di ogni utente. Queste analisi per utente producono un set di *bordi RecipientCache* per ogni persona, che vengono a loro volta inseriti nel grafico del tenant. In questo modo la maggior parte dell'elaborazione dell'analisi viene conservata il più vicino possibile ai dati di origine.

## <a name="tenant-isolation-in-delve"></a>Isolamento del tenant in Delve

Come accennato in precedenza, Microsoft Graph offre esperienze che consentono agli utenti di individuare e collaborare alle attività correnti nella propria azienda e fornisce una piattaforma incentrata sulle entità per l'analisi per il motivo del contenuto e dell'attività tra i carichi di lavoro e oltre Microsoft 365. Delve è la prima esperienza di questo tipo basata su Microsoft Graph.
Delve è un'esperienza Web di Microsoft 365 che mostra i contenuti di Microsoft 365 e Yammer Enterprise agli utenti di Microsoft 365 tramite Microsoft Graph. L'esperienza Web visualizza i dati come bacheche diverse, ognuna con un determinato argomento, ad esempio Tendenze intorno a *me* *o Modificato da me.* Ogni bacheca è costituita da diverse schede documento che visualizzano testo di riepilogo e un'immagine del documento. La scheda consente agli utenti di eseguire operazioni come aprire il documento o una pagina di Yammer per il documento. Esiste una pagina per ogni persona in un tenant di Microsoft 365 che visualizza i documenti più rilevanti per questa persona e icone che possono richiamare Exchange Online o Skype for Business per interagire con tale persona. Poiché Delve è basato sull'API di Microsoft Graph, è associato dall'isolamento basato sul tenant di tale API.