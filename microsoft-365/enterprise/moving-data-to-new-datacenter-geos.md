---
title: Spostamento dei dati di base in un nuovo datacenter di Microsoft 365 GEOS
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a35176a-e585-4dec-a90b-36be8314667f
f1.keywords:
- NOCSH
description: Informazioni su New Office 365 datacenter GEOS e su come utilizzare l'opzione di residenza dei dati per richiedere lo spostamento dei dati di base in un nuovo geografico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c5e63a973ca6fdf6aaaaca884df306ff790c325
ms.sourcegitcommit: 1db81b85d327fe423695ce675ad325e538417211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349245"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a>Spostamento dei dati di base in un nuovo datacenter di Microsoft 365 GEOS

Si continua ad aprire nuovo datacenter GEOS per i servizi Microsoft 365. Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti in continua espansione. Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti. 

I dati dei clienti di base sono un termine che fa riferimento a un sottoinsieme di dati dei clienti, tra cui: 
- Contenuto delle cassette postali di Exchange Online (corpo del messaggio di posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica)
- Contenuto del sito di SharePoint Online e file archiviati all'interno del sito
- File caricati in OneDrive for business
- Messaggi di chat dei team, inclusi i messaggi privati, i messaggi di canale e le immagini utilizzate nelle chat
  
I clienti esistenti che dispongono di dati di base dei clienti archiviati in un datacenter geografico già esistente non sono interessati dal lancio di un nuovo Data Center Geo. Non sono presenti funzionalità esclusive, funzionalità o certificazioni di conformità con il nuovo Data Center Geo. Come clienti in uno qualsiasi di questi due GEOS, si verificheranno gli stessi controlli di qualità dei servizi, delle prestazioni e della sicurezza come in precedenza. Offriamo ai clienti esistenti elencati nella tabella riportata di seguito un'opzione per richiedere la migrazione anticipata dei dati del cliente principale dell'organizzazione a riposo per il nuovo datacenter Geo.
  
|**Clienti con paese di iscrizione tenant in**|**Centro dati geografico precedente**|**Nuovo datacenter Geo**|**Geografica disponibile da**|
|:-----|:-----|:-----|:-----|
|**Giappone**| Asia/Pacifico | Giappone | Dicembre 2014 |
|**Australia, Nuova Zelanda, Figi**| Asia/Pacifico | Australia | Marzo 2015 |
|**India**| Asia/Pacifico | India | Ottobre 2015 |
|**Canada**| Stati Uniti | Canada | Maggio 2016 |
|**Regno Unito**| Unione Europea | Regno Unito | Settembre 2016 |
|**Corea del Sud**| Asia/Pacifico | Corea del Sud | Aprile 2017 |
|**Francia**| Unione Europea | Francia | Marzo 2018 |
|**Emirati Arabi Uniti**| Unione Europea | Emirati Arabi Uniti | Giugno 2019 |
|**Sudafrica**| Unione Europea | Sudafrica | Luglio 2019 |
|**Svizzera, Liechtenstein**| Unione Europea | Svizzera | Dicembre 2019 |
|**Germania**| Unione Europea | Germania | Dicembre 2019 |
|**Norvegia**| Unione Europea | Norvegia | Aprile 2020 |
|**Brasile**| Americhe | Brasile | 2020 novembre |

Al 1 ° ottobre 2020 i clienti con un abbonamento a Office 365 Education incluso nel tenant non sono idonei per la migrazione.

Un elenco completo di tutti i datacenter GEOS, Datacenter e la posizione dei dati del cliente a riposo è disponibile come parte delle [mappe dei datacenter interattivi](https://office.com/datamaps). 
  
## <a name="data-residency-option"></a>Opzione di residenza dei dati

È disponibile un'opzione di data Residency per i clienti Microsoft 365 idonei che sono coperti dal centro dati GEOS elencato nella tabella precedente. Con questa opzione, i clienti idonei con i requisiti di residenza dei dati possono richiedere la migrazione dei dati del cliente principale dell'organizzazione a riposo al nuovo datacenter Geo.  Microsoft offrirà una scadenza di commit per tutti i clienti idonei che richiedono la migrazione durante la finestra di registrazione.  Esaminare la pagina [come richiedere lo spostamento dei dati](request-your-data-move.md) per ulteriori informazioni sulla finestra di registrazione aperta per il datacenter Geo e la procedura da eseguire per iscriversi al programma.  Gli spostamenti di dati possono richiedere fino a 24 mesi dopo il completamento del periodo di richieste.

Non sono presenti funzionalità esclusive, funzionalità o certificazioni di conformità con il nuovo Data Center Geo.
    
La complessità, la precisione e la scalabilità in cui è necessario eseguire lo spostamento dei dati in un ambiente automatizzato e gestito a livello globale impediscono la condivisione quando si prevede che lo spostamento dei dati venga completato per il tenant o per qualsiasi altro tenant. I clienti riceveranno una conferma nel centro messaggi per ogni servizio di partecipazione quando il relativo spostamento dei dati è stato completato. 
    
Gli spostamenti di dati rappresentano un'operazione del servizio back-end con un impatto minimo sugli utenti finali. Le caratteristiche che possono essere influenzate sono elencate nella pagina [durante e dopo lo spostamento dei dati](during-and-after-your-data-move.md) . Il contratto di servizio di [Microsoft Online Services (SLA, Service Level Agreement)](https://go.microsoft.com/fwlink/p/?LinkId=523897) per la disponibilità è pertanto insufficiente per consentire ai clienti di prepararsi o monitorarli durante lo spostamento. La notifica di qualsiasi manutenzione del servizio viene fatta se necessario. 

I dati si spostano nel nuovo datacenter Geo vengono completati senza costi aggiuntivi per il cliente.
    
## <a name="related-topics"></a>Argomenti correlati 
 
[Come richiedere lo spostamento dati](request-your-data-move.md)
    
[Domande frequenti sullo spostamento dati](data-move-faq.md)
  
[Nuovo datacenter GEOS per Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Servizi di Azure in base all'area geografica](https://azure.microsoft.com/regions/)
