---
title: Esperienza utente in ambiente multi-geografico.
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Informazioni sull'esperienza utente riguardo SharePoint e OneDrive in ambiente multi-geografico per Microsoft 365.
ms.openlocfilehash: 558e5a1f7ff2f6f5485a9f32d6e2b43b552b7f17
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749576"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Esperienza utente in ambiente multi-geografico.

Ecco cosa gli utenti visualizzeranno in una configurazione OneDrive Multi-Geo:

## <a name="exchange-mailbox"></a>Cassette postali di Exchange

Viene effettuato il provisioning della cassetta postale di Exchange dell'utente alla posizione dati preferita e viene spostata automaticamente se viene modificato il PDL. Gli utenti possono usare normalmente Outlook e Outlook sul web senza alcun cambiamento nell’esperienza utente in un ambiente multi-geo.

## <a name="hub-sites"></a>Siti hub

I siti hub di SharePoint migliorano l'individuazione e l’interesse per il contenuto dei dipendenti, creando una rappresentazione completa e coerente di progetti, reparti e aree geografiche. In un ambiente multi-geo, siti da posizioni satellite possono essere facilmente associati con un sito hub indipendentemente dalla sua posizione geografica. Gli utenti possono eseguire ricerche e ottenere risultati attraverso l'hub con una singola ricerca, indipendentemente dalla posizione geografica dei siti.

## <a name="microsoft-365-app-launcher"></a>Icona di avvio delle app di Microsoft 365

L’icona di avvio delle app funziona con il multi-geo e indirizza ogni riquadro verso la posizione geografica appropriata del carico di lavoro. I riquadri di SharePoint e OneDrive indirizzeranno l'utente verso la località corrispondente alla posizione geografica predisposta per l'utente. Questo significa che se l'utente ha un OneDrive nella posizione centrale, il riquadro SharePoint lo indirizzerà verso SP Home nella posizione centrale, ma sarà effettuato il provisioning del sito del gruppo nella posizione corrispondente al proprio PDL. 

## <a name="office-applications"></a>Applicazioni di Office

Le applicazioni Office come Word, Excel e PowerPoint rileveranno automaticamente la posizione geografica corretta di OneDrive for Business per ciascun utente al momento dell'accesso. Non è necessario immettere l'URL geo-specifico per i siti di OneDrive o SharePoint.

## <a name="onedrive-for-business-sync-client"></a>Client di sincronizzazione OneDrive for Business

Il client di sincronizzazione OneDrive for Business (versione 17.3.6943.0625 e successive) rileverà automaticamente la posizione geografica corretta di OneDrive for Business per l'utente. Il supporto client Sync include la possibilità di sincronizzare siti basati su gruppi, indipendentemente dalla posizione geografica. Si noti che il client di sincronizzazione Groove non è supportato per multi-geo. 

## <a name="onedrive-for-business-location"></a>Posizione di OneDrive for Business

Gli utenti disporranno di OneDrive for Business fornito nel percorso dati preferito. Se un utente accede a un URL OneDrive che contiene una posizione geografica errata (come un segnalibro da una precedente posizione geografica), viene automaticamente reindirizzato a OneDrive nella posizione geografica appropriata.

## <a name="onedrive-ios-and-android"></a>OneDrive per iOS e Android 

L'app OneDrive per dispositivi mobili iOS e Android illustra i file di OneDrive e i file condivisi con l'utente indipendentemente dalla posizione geografica. La ricerca dalle app OneDrive mostra risultati pertinenti da tutte le posizioni geografiche. Scaricare la versione più recente di tali applicazioni.

Vedere [Usare OneDrive in iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) e [Usare OneDrive in Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) per ulteriori informazioni.

## <a name="onedrive-mobile-client"></a>OneDrive Mobile Client 

Il OneDrive Mobile Client è predisposto per multi-geo e mostrerà il contenuto pertinente e i risultati di tutte le posizioni geografiche.

## <a name="search"></a>Ricerca

Ogni posizione geografica ha un proprio indice di ricerca e Centro ricerche. Quando si esegue la ricerca, la query viene inviata a tutte le posizioni geografiche e i risultati restituiti vengono uniti e quindi classificati in modo che l'utente ottenga risultati unificati. Gli utenti ottengono risultati da tutte le località geografiche indipendentemente dalla posizione geografica. Vedere [Configurare la ricerca di OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) per ulteriori dettagli.

Di seguito sono elencati i client di ricerca supportati:

-   OneDrive for Business

-   Delve

-   Home page di SharePoint

-   Centro ricerche

-   Applicazioni di ricerca personalizzate che utilizzano l'API del servizio di ricerca di SharePoint

## <a name="sharepoint-home"></a>Home page di SharePoint 

In SharePoint Multi-Geo, la home page di SharePoint è ospitata nella posizione in cui l'utente si trova, in base alla sua posizione in OneDrive for business. Ad esempio: se il OneDrive dell'utente è ospitato in una posizione satellite europea, verrà visualizzata la home page di SharePoint dall’Europa. Home page di SharePoint include tutti i contenuti pertinenti per l'utente indipendentemente dalla posizione geografica. 

**Siti seguiti, notizie dai siti, siti recenti, siti frequenti e siti suggeriti**

Tutti questi componenti verranno visualizzati dall'utente indipendentemente dall'area geografica in cui è ospitato il contenuto, purché si disponga delle autorizzazioni per tale contenuto. 

**Collegamenti alle funzionalità**

Gli amministratori possono configurare i collegamenti alle funzionalità nella home page di SharePoint in base alle esigenze per ogni posizione geografica. In questo modo l'amministratore potrà inserire nella home page di SP di ogni area geografica il collegamenti appropriati per gli utenti di quella regione. 

## <a name="sharepoint-mobile-client"></a>SharePoint Mobile Client 

Il SharePoint Mobile Client è predisposto per multi-geo e mostrerà il contenuto pertinente e i risultati da tutte le posizioni geografiche.

## <a name="sharing"></a>Condivisione

L'esperienza di Selezione Utenti mostra tutti gli utenti indipendentemente dalla posizione geografica. Questo consente a un utente di condividere con un altro utente nella stessa posizione geografica o in qualsiasi altra località geografica del tenant. Il contenuto sarà visualizzato da posizioni geografiche diverse nella visualizzazione **Condivisi con me** del OneDrive for Business dell’utente ed è accessibile tramite l’esperienza Single Sign-On indipendentemente da quale posizione geografica è ospitato.

## <a name="teams-experience"></a>Funzionalità di Teams

Teams funziona con Multi-Geo. Indipendentemente dalla posizione geografica dell'utente vengono visualizzati i file di OneDrive e i file recenti. Menzioni @ funziona con utenti provenienti da tutte le posizioni geografiche.

## <a name="user-profiles"></a>Profili utente

Le informazioni sul profilo utente sono gestite nella posizione geografica dell'utente. Quando si seleziona un utente, si verrà indirizzati alla posizione geografica corretta per l'utente, in cui sarà possibile visualizzare i dettagli del profilo completo.

Se Delve è disattivato, verrà visualizzata l'esperienza del profilo classico in SharePoint, il quale non ha funzionalità Multi-Geo.


