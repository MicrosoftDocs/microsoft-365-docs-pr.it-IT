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
description: In questo articolo viene fornita una spiegazione del funzionamento dell'isolamento del tenant per separare i dati del tenant in Ricerca di Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332401"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Isolamento del tenant per la funzionalità di ricerca di Microsoft 365

La ricerca di SharePoint Online utilizza un modello di separazione dei tenant che bilancia l'efficienza delle strutture di dati condivise con la protezione dalla perdita di informazioni tra tenant. Con questo modello, le funzionalità di ricerca non possono:

- Restituzione di risultati di query contenenti documenti di altri tenant
- Esposizione di informazioni sufficienti nei risultati delle query che un utente esperto può dedurre informazioni su altri tenant
- Visualizzazione dello schema o delle impostazioni da un altro tenant
- La combinazione delle informazioni di elaborazione dell'analisi tra tenant o archivio determina il tenant errato
- Utilizzo di voci di dizionario da un altro tenant

Per ogni tipo di dati del tenant, usiamo uno o più livelli di protezione nel codice per evitare perdite accidentali di informazioni. I dati più critici hanno il maggior numero di livelli di protezione per assicurarsi che un singolo difetto non comporta una perdita di informazioni effettiva o percepita.

## <a name="tenant-separation-for-the-search-index"></a>Separazione tenant per l'indice di ricerca

L'indice di ricerca è archiviato su disco nei server che ospitano i componenti di indicizzazione e i tenant condividono i file di indice. I documenti indicizzati di un tenant sono visibili solo per le query per tale tenant. Tre meccanismi indipendenti impediscono la perdita di informazioni:

- Filtro ID tenant
- Prefisso del termine ID tenant
- Controlli ACL

Tutti e tre i meccanismi devono avere esito negativo perché la ricerca restituisca i documenti al tenant errato.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtro ID tenant e prefisso dei termini dell'ID tenant

La ricerca prefissi ogni termine indicizzato nell'indice full-text con l'ID tenant. Ad esempio, quando il termine "*foo*" è indicizzato per un tenant con ID "*123*", la voce nell'indice full-text è "*123foo".*

Ogni query viene convertita per includere l'ID tenant usando un processo denominato filtro ID tenant. Ad esempio, la query "*foo*" viene convertita in "<*guid*>. *foo* AND *tenantID*:<*guid*>", dove <*guid*> rappresenta il tenant che esegue la query. Questa conversione di query si verifica all'interno di ogni nodo di indice e non può influire né sulle query né sull'elaborazione del contenuto. Poiché l'ID tenant viene aggiunto a ogni query, non è possibile dedurre la frequenza di un termine in altri tenant esaminando la classificazione delle corrispondenze migliori in un tenant.

La prefissi dei termini dell'ID tenant si verifica solo nell'indice full-text. Le ricerche in campo, ad esempio "*title:foo*", passano a un indice di ricerca sintetica in cui i termini non sono preceduti dall'ID tenant. Le ricerche campite vengono invece precedute dal nome del campo. Ad esempio, la query "*title:foo*" viene convertita in "*fields.title:foo AND fields.tenantID*:<*guid*>." Poiché la frequenza di un termine non influisce sulla classificazione dei risultati nell'indice di ricerca sintetica, non è necessario separare il tenant per prefisso di termine. Per una ricerca in campo come "*title:foo*", la separazione del contenuto del tenant dipende dal filtro dell'ID tenant in base alla conversione di query.

## <a name="document-access-control-list-checks"></a>Controlli dell'elenco di controllo di accesso ai documenti

La ricerca controlla l'accesso ai documenti tramite gli elenchi di controllo di accesso salvati nell'indice di ricerca. Ogni elemento viene indicizzato con un set di termini in un campo ACL speciale. Il campo ACL contiene un termine per gruppo o utente che può visualizzare il documento. Ogni query è arricchita da un elenco di termini della voce di controllo di accesso (ACE), uno per ogni gruppo a cui appartiene l'utente autenticato.

Ad esempio, una query come "<*guid*>. *foo AND tenantID*:<*guid*>" diventa: "<*guid*>. *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Poiché gli identificatori di utenti e gruppi e di conseguenza le voci di controllo di accesso sono univoci, ciò offre un ulteriore livello di sicurezza tra i tenant per i documenti visibili solo per alcuni utenti. Lo stesso vale per la speciale ACE "Tutti tranne gli utenti esterni" che concede l'accesso agli utenti normali nel tenant. Tuttavia, poiché le voci di controllo di accesso per "Tutti" sono le stesse per tutti i tenant, la separazione dei tenant per i documenti pubblici dipende dal filtro degli ID tenant. Sono supportate anche le voci di controllo di accesso negate. L'aumento della query aggiunge una clausola che rimuove un documento dal risultato quando esiste una corrispondenza con una ACE negata.

Nella ricerca di Exchange Online, l'indice è partizionato sull'ID cassetta postale per le cassette postali dei singoli utenti anziché sull'ID tenant (ID sottoscrizione) come in SharePoint Online. Il meccanismo di partizionamento è lo stesso di SharePoint Online, ma non è disponibile alcun filtro ACL.
