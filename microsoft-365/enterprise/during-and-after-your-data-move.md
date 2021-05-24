---
title: Durante e dopo lo spostamento dati
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Gli spostamenti dei dati sono operazioni back-end che si verificano quando Microsoft sposta i servizi e i dati associati per il tenant in un nuovo datacenter geografico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d3d44ffc1650989e5c39f5f79cb6a07065f9e9f1
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625258"
---
# <a name="during-and-after-your-data-move"></a>Durante e dopo lo spostamento dati

Gli spostamenti di dati sono un'operazione back-end con un impatto minimo per gli utenti finali. Non è necessaria alcuna azione mentre Microsoft sposta ogni servizio e i dati associati per il tenant in un nuovo datacenter geografico. Il trasferimento e la convalida dei dati vengono eseguiti in background in anticipo con un impatto minimo per gli utenti.
  
> [!NOTE]
> Gli spostamenti vengono eseguiti in momenti diversi per ogni servizio. Di conseguenza, vedrai le funzionalità ridotte descritte per ogni servizio in un momento diverso. 
  
Guarda il Microsoft 365 messaggi per la conferma quando gli spostamenti per ogni Exchange Online, SharePoint Online e Teams chat completa. Come illustrato nella tabella seguente, possono essere necessario fino a 24 mesi dopo la fine del periodo di registrazione per completare gli spostamenti dei dati principali dei clienti in pausa nel nuovo data center geo.   

|**Clienti con paese di iscrizione**|**Tutti gli spostamenti completati da**|
|:-----|:-----|
|Australia, Nuova Zelanda, Figi  <br/> |1 luglio 2022  <br/> |
|Giappone  <br/> |1 luglio 2022  <br/> |
|India  <br/> |1 luglio 2022  <br/> |
|Canada  <br/> |1 luglio 2022  <br/> |
|Corea del Sud  <br/> |1 luglio 2022  <br/> |
|Regno Unito  <br/> |1 luglio 2022  <br/> |
|Francia  <br/> |1 luglio 2022  <br/> |
|Emirati Arabi Uniti  <br/> |1 luglio 2022  <br/> |
|Sudafrica  <br/> |1 luglio 2022  <br/> |
|Svizzera, Liechtenstein  <br/> |1 luglio 2022  <br/> |
|Norvegia  <br/> |1 novembre 2022  <br/> |
|Germania  <br/> |1 maggio 2023  <br/> |
|Brasile  <br/> |1 giugno 2023  <br/> |

## <a name="exchange-online"></a>Exchange Online

Poiché richiede tempo per spostare ogni utente nel nuovo datacenter geo per un singolo tenant, alcuni utenti saranno ancora nel vecchio datacenter geo durante lo spostamento, mentre altri saranno nel nuovo datacenter geo. Ciò significa che alcune funzionalità che implicano l'accesso a più cassette postali potrebbero non funzionare completamente durante un periodo del processo di spostamento, che può durare settimane. Queste funzionalità sono descritte nelle sezioni seguenti.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Aprire "Cartella condivisa" in Outlook Web Access

Alcuni utenti aprono una cartella di posta condivisa da un'altra cassetta postale (in cui l'utente dispone delle autorizzazioni di lettura o scrittura) in Outlook Web Access utilizzando la funzionalità "Cartella condivisa". Nella tabella seguente viene descritto il funzionamento dell'accesso alle cartelle condivise durante lo spostamento di una cassetta postale. Tenere presente che gli utenti con autorizzazioni complete per una cassetta postale condivisa possono aprire la cassetta postale utilizzando Outlook Web Access durante lo spostamento. 
  
|**Configurazione**|**Descrizione**|
|:-----|:-----|
|L'utente dispone dell'autorizzazione per la cartella delle cassette postali per un'altra cassetta postale  <br/> |Potenzialmente limitato.  <br/> Se l'utente A e la cassetta postale B non sono nella stessa posizione geografica durante lo spostamento del tenant, l'utente A non può aprire la cartella della cassetta postale B in Outlook Web Access se l'utente A dispone solo dell'autorizzazione per una cartella specifica nella cassetta postale B.  <br/> Per aggiungere una cartella condivisa, fai clic con il pulsante destro del mouse sul nome utente nel riquadro di spostamento sinistro e scegli **Aggiungi cartella condivisa.**  <br/> |
|Utente con autorizzazione cassetta postale completa per un'altra cassetta postale  <br/> |Completamente supportato.  <br/> Se l'utente A dispone dell'autorizzazione "Accesso completo" per la cassetta postale B, l'utente A può fare clic sulla cartella condivisa nel riquadro di spostamento sinistro in Outlook Web Access per aprire una finestra con la cassetta postale B.  Un utente può aprire una cassetta postale condivisa Outlook Web Access durante lo spostamento senza alcun impatto negativo. La limitazione si applica solo alla condivisione a livello di cartella in una cassetta postale.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Quando SharePoint online viene spostato, vengono spostati anche i dati per i servizi seguenti:
  
- One Drive for Business
    
- Microsoft 365 Servizi video
    
- Office in un browser
    
- Microsoft 365 Apps for enterprise
    
- Visio Pro per Microsoft 365
    
Dopo aver completato lo spostamento dei dati SharePoint Online, potresti vedere alcuni degli effetti seguenti.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Servizi video

- Lo spostamento dei dati per il video richiede più tempo degli spostamenti per il resto del contenuto in SharePoint Online.
    
- Dopo lo SharePoint contenuto online, ci sarà un intervallo di tempo in cui i video non sono in grado di essere riprodotti.
    
- Stiamo rimuovendo le copie transcod coded dal datacenter precedente e le stiamo transcodendo di nuovo nel nuovo datacenter.
    
### <a name="search"></a>Ricerca

Nel corso dello spostamento dei dati di SharePoint Online, viene eseguita la migrazione dell'indice di ricerca e delle impostazioni di ricerca in una nuova posizione. Finché non abbiamo **completato lo** spostamento dei dati SharePoint Online, continueremo a servire gli utenti dall'indice nella posizione originale. Nella nuova posizione, la ricerca inizia automaticamente la ricerca per indicizzazione del contenuto dopo aver completato lo spostamento dei dati SharePoint Online. Da questo punto in poi serviamo gli utenti dall'indice migrato. Le modifiche apportate al contenuto che si sono verificate dopo la migrazione non vengono incluse nell'indice migrato fino a quando la ricerca per indicizzazione non le raccoglie. La maggior parte dei clienti non nota che i risultati sono meno nuovi subito dopo aver completato lo spostamento dei dati di SharePoint Online, ma alcuni clienti potrebbero avere una minore aggiornamento nelle prime 24-48 ore 
  
Sono interessate le funzionalità di ricerca seguenti:
  
- Risultati della ricerca e Web part ricerca: i risultati non includono le modifiche che si sono verificate dopo la migrazione fino a quando non vengono selezionate dalla ricerca per indicizzazione. 
    
- Delve: Delve non include le modifiche che si sono verificate dopo la migrazione fino a quando la ricerca per indicizzazione non le raccoglie.
    
- Report popolarità e ricerca per il sito: i conteggi per i report di Excel nella nuova posizione includono solo i conteggi migrati e i conteggi dei report di utilizzo eseguiti dopo aver completato lo spostamento dei dati di SharePoint Online. I conteggi del periodo provvisorio vengono persi e non possono essere recuperati. Questo periodo è in genere un paio di giorni. Alcuni clienti potrebbero avere perdite più brevi o più lunghe.
    
- Portale video: i conteggi di visualizzazione e le statistiche per il portale video dipendono dalle statistiche per i report di Excel, pertanto i conteggi delle visualizzazione e le statistiche per il portale video vengono persi per lo stesso periodo di tempo dei report Excel.
    
- eDiscovery: gli elementi modificati durante la migrazione non vengono visualizzati finché la ricerca per indicizzazione non raccoglie le modifiche.
    
- Protezione dalla perdita dei dati (DLP): i criteri non vengono applicati agli elementi che cambiano fino a quando la ricerca per indicizzazione non raccoglie le modifiche.

Come parte della migrazione, l'area predefinita verrà cambiata e tutto il nuovo contenuto verrà archiviato in pausa nella nuova area predefinita. Il contenuto esistente verrà spostato in background senza alcun impatto per l'utente fino a 90 giorni dopo la prima modifica alla posizione dati di SharePoint Online nell'interfaccia di amministrazione.

## <a name="microsoft-teams"></a>Microsoft Teams

Oltre a Exchange Online, SharePoint Online e OneDrive for Business, Microsoft eseguirà la migrazione Teams dati del servizio chat nel datacenter locale.

- Teams messaggi di chat, inclusi i messaggi privati e i messaggi di canale.
- Teams immagini usate nelle chat.

Teams file vengono archiviati in SharePoint Online e Teams file di chat vengono archiviati in OneDrive for Business. La segreteria telefonica, il calendario, la cronologia chat e i contatti vengono archiviati in Exchange Online. In molti casi, Exchange Online, SharePoint Online e OneDrive for Business sono già utilizzati dal cliente nel centro dati geografico locale e fanno parte del programma di migrazione di Microsoft 365 per i paesi dei clienti idonei.

## <a name="skype-for-business"></a>Skype for Business

Skype for Business non sono più disponibili.  [Skype for Business Online verrà ritirato](/lifecycle/announcements/skype-for-business-online-retirement) il 31 luglio 2021. Dopo tale periodo, il servizio non sarà più accessibile. 
  
## <a name="related-topics"></a>Argomenti correlati 
 
[Come richiedere lo spostamento dati](request-your-data-move.md)
    
[Domande frequenti sullo spostamento dati](data-move-faq.md)
  
[Nuovi geo datacenter per Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Servizi di Azure per area geografica](https://azure.microsoft.com/regions/)
