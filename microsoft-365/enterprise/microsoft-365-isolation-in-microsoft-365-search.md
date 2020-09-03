---
title: Isolamento del tenant per la funzionalità di ricerca di Microsoft 365
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
description: In questo articolo, trovare una spiegazione di come funziona l'isolamento tenant per separare i dati del tenant in Microsoft 365 search.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332401"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Isolamento del tenant per la funzionalità di ricerca di Microsoft 365

La ricerca di SharePoint Online utilizza un modello di separazione tenant che bilancia l'efficienza delle strutture di dati condivise con una protezione dalle informazioni che fuoriescono tra i tenant. Con questo modello, vengono impedite le funzionalità di ricerca:

- Restituzione dei risultati delle query che contengono documenti provenienti da altri tenant
- Esposizione di informazioni sufficienti nei risultati delle query che un utente esperto può dedurre informazioni su altri tenant
- Visualizzazione dello schema o delle impostazioni di un altro tenant
- Missaggio delle informazioni di elaborazione dell'analisi tra i tenant o i risultati dell'archiviazione nel tenant errato
- Utilizzo di voci di dizionario da un altro tenant

Per ogni tipo di dati del tenant, è possibile utilizzare uno o più livelli di protezione nel codice per evitare che si verifichino perdite accidentali di informazioni. I dati più critici hanno la maggior parte dei livelli di protezione per assicurarsi che un singolo difetto non provochi perdite di informazioni effettive o percepite.

## <a name="tenant-separation-for-the-search-index"></a>Separazione tenant per l'indice di ricerca

L'indice di ricerca è archiviato su disco nei server che ospitano i componenti di indicizzazione e i tenant condividono i file di indice. I documenti indicizzati di un tenant sono visibili solo per le query per il tenant. Tre meccanismi indipendenti impediscono la perdita di informazioni:

- Filtro ID tenant
- Prefisso dei termini dell'ID tenant
- Controlli ACL

Tutti e tre i meccanismi devono avere esito negativo affinché la ricerca restituisca i documenti al tenant errato.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtro ID tenant e prefisso dei termini dell'ID tenant

Prefissi di ricerca ogni termine indicizzato nell'indice full-text con l'ID del tenant. Ad esempio, quando il termine "*foo*" è indicizzato per un tenant con ID "*123*", la voce nell'indice full-text è "*123foo".*

Ogni query viene convertita in modo da includere l'ID tenant utilizzando un processo denominato filtro ID tenant. Ad esempio, la query "*foo*" viene convertita in "<*GUID*>. *foo* E *tenantID*: <*GUID*> ", dove <*GUID*> rappresenta il tenant che esegue la query. Questa conversione di query si verifica all'interno di ogni nodo di indice e né query né elaborazione del contenuto possono influire su di essa. Poiché l'ID tenant viene aggiunto a ogni query, la frequenza di un termine in altri tenant non può essere desunta guardando la migliore classificazione di corrispondenza in un tenant.

Il prefisso dei termini dell'ID tenant si verifica solo nell'indice full-text. Le ricerche in campo, ad esempio "*title: foo*", passano a un indice di ricerca sintetico in cui i termini non sono preceduti dall'ID tenant. Al contrario, le ricerche in campo sono prefissate con il nome del campo. Ad esempio, la query "*title: foo*" viene convertita in "*Fields. title: foo e Fields. tenantID*: <*GUID*>." Poiché la frequenza di un termine non influenza la classificazione degli hit nell'indice di ricerca sintetico, non è necessario che la separazione dei tenant venga prefissata per termine. Per una ricerca in campo come "*title: foo*", la separazione del contenuto del tenant dipende dal filtro dell'ID tenant tramite la conversione delle query.

## <a name="document-access-control-list-checks"></a>Controlli dell'elenco di controllo di accesso ai documenti

La ricerca controlla l'accesso ai documenti tramite gli elenchi ACL salvati nell'indice di ricerca. Ogni elemento viene indicizzato con un set di termini in un campo ACL speciale. Il campo ACL contiene un termine per gruppo o utente che può visualizzare il documento. Ogni query viene aumentata con un elenco di termini ACE (Access Control Entry), uno per ogni gruppo a cui appartiene l'utente autenticato.

Ad esempio, una query come "<*guid*>. *foo e tenantID*: <*GUID*> "diventa:" <*GUID*>. *foo e tenantID*: <*GUID* >  *e* (*docACL:* < *ace1* >  *o docACL*: <*ace2* >  *o docACL*: <*ACE3* >  *...*) "

Poiché gli identificatori di utenti e gruppi e quindi gli ACE sono univoci, questo fornisce un livello di sicurezza supplementare tra i tenant per i documenti visibili solo ad alcuni utenti. Lo stesso vale per l'ACE speciale "tutti tranne gli utenti esterni" che concede l'accesso agli utenti abituali del tenant. Tuttavia, poiché gli ACE per "tutti" sono uguali per tutti i tenant, la separazione dei tenant per i documenti pubblici dipende dal filtro dell'ID tenant. Anche le voci ACE Deny sono supportate. L'incremento di query aggiunge una clausola che consente di rimuovere un documento dal risultato quando è presente una corrispondenza con una ACE di negazione.

In ricerca di Exchange Online, l'indice è partizionato sull'ID cassetta postale per le cassette postali dell'utente anziché sull'ID tenant (ID sottoscrizione) come in SharePoint Online. Il meccanismo di partizionamento è identico a quello di SharePoint Online, ma non è presente alcun filtro ACL.
