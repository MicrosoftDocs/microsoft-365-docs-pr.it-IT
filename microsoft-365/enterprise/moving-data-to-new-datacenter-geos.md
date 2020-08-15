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
ms.openlocfilehash: 9c1c838f52627e0ff2eee5b7fdbeef7aee55b137
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690926"
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
|**Canada**| Nord America | Canada | Maggio 2016 |
|**Regno Unito**| Europa | Regno Unito | Settembre 2016 |
|**Corea del Sud**| Asia/Pacifico | Corea del Sud | Aprile 2017 |
|**Francia**| Europa | Francia | Marzo 2018 |
|**Emirati Arabi Uniti**| Europa | Emirati Arabi Uniti | Giugno 2019 |
|**Sudafrica**| Europa | Sudafrica | Luglio 2019 |
|**Svizzera, Liechtenstein**| Europa | Svizzera | Dicembre 2019 |
|**Germania**| Europa | Germania | Dicembre 2019 |
|**Norvegia**| Europa | Norvegia | Aprile 2020 |
  
I nuovi clienti o i tenant di Office 365 creati dopo la disponibilità del nuovo datacenter Geo avranno i dati di base dei clienti archiviati a riposo nel nuovo datacenter Geo automaticamente.


>[!Note]
>Nel dicembre 2019 è stata avviata la regione datacenter Germania. I nuovi clienti di Microsoft 365 con un indirizzo di registrazione tedesco associato al tenant avranno i dati di base dei clienti archiviati a riposo in Germania. Intendiamo offrire la migrazione dall'Europa alla Germania per i clienti tedeschi in futuro. Oggi, i clienti di Microsoft Cloud Germany/Deutschland possono richiedere la migrazione ai servizi di Office 365 nelle nuove aree del datacenter tedesco. Per ulteriori informazioni [, vedere l'opzione di opt-in per la migrazione da Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 Services nelle nuove aree del datacenter tedesco](https://aka.ms/office365germanymoveoptin) .
>
  
Un elenco completo di tutti i datacenter GEOS, Datacenter e la posizione dei dati del cliente a riposo è disponibile come parte delle [mappe dei datacenter interattivi](https://office.com/datamaps). 
  
## <a name="data-residency-option"></a>Opzione di residenza dei dati

È disponibile un'opzione per la residenza dei dati per i clienti esistenti di Microsoft 365 che sono coperti dal Data Center GEOS elencato nella tabella precedente. Con questa opzione, i clienti con requisiti di residenza dei dati possono richiedere la migrazione precoce dei dati del cliente principale dell'organizzazione a riposo per il nuovo datacenter Geo.  Microsoft offrirà una scadenza impegnata a tutti i clienti idonei che richiedono la migrazione precoce durante la finestra di registrazione.  Esaminare la pagina [come richiedere lo spostamento dei dati](request-your-data-move.md) per ulteriori informazioni sulla finestra di registrazione per la propria Geo e la procedura da eseguire per iscriversi al programma.  Gli spostamenti di dati possono richiedere fino a 24 mesi dopo il completamento del periodo di richieste.

Non sono presenti funzionalità esclusive, funzionalità o certificazioni di conformità con il nuovo Data Center Geo.
    
La complessità, la precisione e la scalabilità in cui è necessario eseguire lo spostamento dei dati in un ambiente automatizzato e gestito a livello globale impediscono la condivisione quando si prevede che lo spostamento dei dati venga completato per il tenant o per qualsiasi altro tenant. I clienti riceveranno una conferma nel centro messaggi per ogni servizio di partecipazione quando il relativo spostamento dei dati è stato completato. 
    
Gli spostamenti di dati rappresentano un'operazione del servizio back-end con un impatto minimo sugli utenti finali. Le caratteristiche che possono essere influenzate sono elencate nella pagina [durante e dopo lo spostamento dei dati](during-and-after-your-data-move.md) . Il contratto di servizio di [Microsoft Online Services (SLA, Service Level Agreement)](https://go.microsoft.com/fwlink/p/?LinkId=523897) per la disponibilità è pertanto insufficiente per consentire ai clienti di prepararsi o monitorarli durante lo spostamento. La notifica di qualsiasi manutenzione del servizio viene fatta se necessario. 

I dati si spostano nel nuovo datacenter Geo vengono completati senza costi aggiuntivi per il cliente.
    
## <a name="related-topics"></a>Argomenti correlati 
 
[Come richiedere lo spostamento dati](request-your-data-move.md)
    
[Domande frequenti sullo spostamento dati](data-move-faq.md)
  
[Nuovo datacenter GEOS per Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Servizi di Azure in base all'area geografica](https://azure.microsoft.com/regions/)
