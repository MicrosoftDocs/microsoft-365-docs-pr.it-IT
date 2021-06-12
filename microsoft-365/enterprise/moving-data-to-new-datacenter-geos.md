---
title: Spostamento di dati di base in Microsoft 365 geo del datacenter
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
description: Informazioni sulle nuove Office 365 geo del datacenter e su come usare l'opzione di residenza dei dati per richiedere uno spostamento dei dati di base in una nuova posizione geografica.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 797ac69e2c60c2e4c3ece38b376406027ff65e36
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908306"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a>Spostamento di dati di base in Microsoft 365 geo del datacenter

Microsoft continua ad aprire nuovi dati geografici del datacenter per Microsoft 365 servizi. Questi nuovi geo datacenter aggiungono capacità e risorse di calcolo per supportare la crescita continua della domanda e dell'utilizzo dei clienti. Inoltre, i nuovi dati geografici del datacenter offrono la residenza dei dati in-geo per i dati principali dei clienti. 

Dati di base dei clienti è un termine che si riferisce a un sottoinsieme di dati dei clienti, tra cui: 
- Exchange Online della cassetta postale (corpo della posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica)
- SharePoint Contenuto del sito online e file archiviati in tale sito
- File caricati in OneDrive for Business
- Teams messaggi di chat, inclusi messaggi privati, messaggi di canale e immagini utilizzati nelle chat
  
I clienti esistenti che hanno i dati dei clienti di base archiviati in un data center geo già esistente non sono influenzati dall'avvio di un nuovo data center geo. Non introduciamo funzionalità, funzionalità o certificazioni di conformità univoche con il nuovo data center geo. Come cliente in uno di questi due geo, si sperimenterà la stessa qualità del servizio, prestazioni e controlli di sicurezza come hai fatto in precedenza. Offriamo ai clienti esistenti elencati nella tabella seguente un'opzione per richiedere la migrazione anticipata dei dati principali dei clienti dell'organizzazione nel nuovo data center geo.
  
|**Clienti con paese di iscrizione tenant**|**Geo datacenter precedente**|**Nuovo data center geo**|**Geo disponibile da**|
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
|**Brasile**| Americhe | Brasile | Novembre 2020 |

A partire dal 1° ottobre 2020 i clienti con una sottoscrizione Office 365 Education inclusi nel tenant non sono idonei per la migrazione.

Un elenco completo di tutti i dati geografici, i datacenter e la posizione dei dati dei clienti in pausa è disponibile come parte delle [mappe dei datacenter interattivi.](https://office.com/datamaps) 
  
## <a name="data-residency-option"></a>Opzione di residenza dei dati

Forniamo un'opzione di residenza dei dati ai clienti Microsoft 365 idonei coperti dai dati geografici del datacenter elencati nella tabella precedente. Con questa opzione, i clienti idonei con requisiti di residenza dei dati possono richiedere la migrazione dei dati principali dei clienti dell'organizzazione in pausa al nuovo data center geo.  Microsoft offrirà una scadenza impegnata a tutti i clienti idonei che richiedono la migrazione durante la finestra di registrazione.  Esaminare la [pagina Come richiedere lo](request-your-data-move.md) spostamento dei dati per ulteriori dettagli sulla finestra di registrazione aperta per il centro dati geografico e sui passaggi per la registrazione al programma.  Gli spostamenti di dati possono richiedere fino a 24 mesi dopo il termine del periodo di richiesta.

Non introduciamo funzionalità, funzionalità o certificazioni di conformità univoche con il nuovo data center geo.
    
La complessità, la precisione e la scala con cui è necessario eseguire spostamenti di dati all'interno di un ambiente gestito a livello globale e automatizzato ci impediscono di condividere quando si prevede che uno spostamento di dati verrà completato per il tenant o qualsiasi altro tenant singolo. I clienti riceveranno una conferma nel Centro messaggi per ogni servizio partecipante al termine del relativo spostamento dei dati. 
    
Gli spostamenti di dati sono un'operazione di servizio back-end con un impatto minimo per gli utenti finali. Le funzionalità che possono essere influenzate sono elencate nella [pagina Durante e dopo lo spostamento dei](during-and-after-your-data-move.md) dati. Aderiamo al [contratto Microsoft Online Services service level agreement (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) per la disponibilità, quindi non è necessario che i clienti si preparino o monitorino durante lo spostamento. Se necessario, viene notificata qualsiasi manutenzione del servizio. 

Gli spostamenti di dati nel nuovo datacenter geografico vengono completati senza costi aggiuntivi per il cliente.
    
## <a name="related-topics"></a>Argomenti correlati 
 
[Come richiedere lo spostamento dati](request-your-data-move.md)
    
[Domande frequenti sullo spostamento dati](data-move-faq.yml)
  
[Nuovi geo datacenter per Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Servizi di Azure per area geografica](https://azure.microsoft.com/regions/)

[Teams in una tenancy Microsoft 365 multi-geo](/microsoftteams/teams-experience-o365odb-spo-multi-geo)
