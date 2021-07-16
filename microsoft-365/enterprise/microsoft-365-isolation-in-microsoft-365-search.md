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
description: In questo articolo, trovare una spiegazione del funzionamento dell'isolamento del tenant per separare i dati del tenant in Microsoft 365 Ricerca.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464085"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Isolamento del tenant per la funzionalità di ricerca di Microsoft 365

SharePoint La ricerca online usa un modello di separazione dei tenant che bilancia l'efficienza delle strutture di dati condivise con la protezione dalle perdite di informazioni tra tenant. Con questo modello, impediamo alle funzionalità di ricerca di:

- Restituzione dei risultati delle query contenenti documenti di altri tenant
- Esposizione di informazioni sufficienti nei risultati delle query che un utente esperto potrebbe dedurre informazioni su altri tenant
- Visualizzazione dello schema o delle impostazioni di un altro tenant
- La combinazione delle informazioni di elaborazione dell'analisi tra tenant o archivio comporta un tenant errato
- Utilizzo di voci di dizionario da un altro tenant

Per ogni tipo di dati del tenant, usiamo uno o più livelli di protezione nel codice per evitare perdite accidentali di informazioni. I dati più critici hanno il maggior numero di livelli di protezione per assicurarsi che un singolo difetto non causa perdite di informazioni effettive o percepite.

## <a name="tenant-separation-for-the-search-index"></a>Separazione tenant per l'indice di ricerca

L'indice di ricerca viene archiviato su disco nei server che ospitano i componenti di indicizzazione e i tenant condividono i file di indice. I documenti indicizzati di un tenant sono visibili solo per le query per tale tenant. Tre meccanismi indipendenti impediscono la perdita di informazioni:

- Filtro ID tenant
- Prefisso del termine ID tenant
- Controlli ACL

Tutti e tre i meccanismi devono avere esito negativo per la ricerca per restituire i documenti al tenant sbagliato.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtro ID tenant e Prefisso termine ID tenant

La ricerca prefissi ogni termine indicizzato nell'indice full-text con l'ID tenant. Ad esempio, quando il termine " foo " è *indicizzato* per un tenant con ID "*123*", la voce nell'indice full-text è "*123foo".*

Ogni query viene convertita per includere l'ID tenant utilizzando un processo denominato filtro ID tenant. Ad esempio, la query "*foo*" viene convertita in "<*guid*>. *foo* AND *tenantID*:<*guid*>", dove <guid *>* rappresenta il tenant che esegue la query. Questa conversione di query si verifica all'interno di ogni nodo di indice e nessuna query né l'elaborazione del contenuto possono influenzarla. Poiché l'ID tenant viene aggiunto a ogni query, non è possibile dedurre la frequenza di un termine in altri tenant esaminando la classificazione delle corrispondenze migliori in un tenant.

Il prefisso dei termini dell'ID tenant si verifica solo nell'indice full-text. Le ricerche in campi, ad esempio "*title:foo*", passano a un indice di ricerca sintetica in cui i termini non sono preceduti dall'ID tenant. Le ricerche campite vengono invece precedute dal nome del campo. Ad esempio, la query "*title:foo*" viene convertita in "*fields.title:foo AND fields.tenantID*:<*guid*>". Poiché la frequenza di un termine non influisce sulla classificazione degli accessi nell'indice di ricerca sintetica, non è necessaria la separazione del tenant per prefisso di termine. Per una ricerca in campo come "*title:foo*", la separazione del contenuto del tenant dipende dal filtro dell'ID tenant in base alla conversione di query.

## <a name="document-access-control-list-checks"></a>Controlli elenco di controllo di accesso ai documenti

La ricerca controlla l'accesso ai documenti tramite gli ACL salvati nell'indice di ricerca. Ogni elemento viene indicizzato con un set di termini in un campo ACL speciale. Il campo ACL contiene un termine per gruppo o utente che può visualizzare il documento. A ogni query viene associato un elenco di termini di voce di controllo di accesso (ACE), uno per ogni gruppo a cui appartiene l'utente autenticato.

Ad esempio, una query come "<*guid>.* *foo AND tenantID*:<*guid*>" diventa: "<*guid*>. *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Poiché gli identificatori di utenti e gruppi e quindi le voci di controllo di accesso sono univoci, questo offre un ulteriore livello di sicurezza tra i tenant per i documenti visibili solo ad alcuni utenti. Lo stesso vale per la speciale ACE "Tutti tranne gli utenti esterni" che concede l'accesso agli utenti normali nel tenant. Tuttavia, poiché le voci di controllo di accesso per "Tutti" sono le stesse per tutti i tenant, la separazione dei tenant per i documenti pubblici dipende dal filtro degli ID tenant. Sono supportate anche le voci di controllo di accesso negate. L'aumento delle query aggiunge una clausola che rimuove un documento dal risultato quando esiste una corrispondenza con una ACE negata.

In Exchange Online ricerca, l'indice viene partizionato sull'ID cassetta postale per le cassette postali dei singoli utenti anziché sull'ID tenant (ID sottoscrizione) come in SharePoint Online. Il meccanismo di partizionamento è lo stesso SharePoint Online, ma non è disponibile alcun filtro ACL.
