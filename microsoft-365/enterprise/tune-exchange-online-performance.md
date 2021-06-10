---
title: Ottimizzare le prestazioni di Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Questo articolo contiene suggerimenti generali e collegamenti ad altre risorse che illustrano come migliorare le prestazioni dei Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909443"
---
# <a name="tune-exchange-online-performance"></a>Ottimizzare le prestazioni di Exchange Online

Questo articolo contiene suggerimenti generali e collegamenti ad altre risorse che illustrano come migliorare le prestazioni di Exchange Online, in particolare prima di una migrazione. Questo articolo fa parte di Pianificazione della rete [e ottimizzazione delle](./network-planning-and-performance.md) prestazioni per Office 365 progetto.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Aspetti da considerare per migliorare le Exchange Online prestazioni

Per migliorare la velocità della migrazione e ridurre i vincoli di larghezza di banda dell'organizzazione Exchange Online, considerare quanto segue:
  
- **Ridurre le dimensioni delle cassette postali.** Le dimensioni ridotte delle cassette postali migliorano la velocità di migrazione. 
    
- **Utilizzare le funzionalità di spostamento delle cassette postali con una Exchange distribuzione ibrida.** Con una Exchange ibrida, la posta offline (sotto forma di . FILE OST) non richiede un nuovo download durante la migrazione a Exchange Online. In questo modo vengono ridotti in modo significativo i requisiti di larghezza di banda per il download. 
    
- **Pianificare gli spostamenti delle cassette postali in modo che si verifichino durante i periodi di traffico Internet basso e di bassa Exchange locale.** Durante la pianificazione degli spostamenti, le richieste di migrazione vengono inviate al proxy di replica delle cassette postali e potrebbero non essere effettuate immediatamente. 
    
- **Usare popout snelli per Outlook sul Web.** I popup snelli forniscono versioni più piccole e con un utilizzo minore della memoria di alcuni messaggi di posta elettronica in Microsoft Edge o Internet Explorer tramite il rendering di alcuni componenti nel server. Per ulteriori informazioni, vedere [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Consigli generali

- Assicurarsi che la ricerca DNS per outlook.office.com il centro dati MS in una posizione di immissione logica per la posizione.

- Ricercare la memorizzazione nella cache delle cassette postali e scegliere le opzioni appropriate (re. periodo di memorizzazione nella cache, memorizzazione nella cache delle cassette postali condivise e così via).

- Evitare che Outlook i dati personali superino le connessioni VPN (a un ufficio centrale) prima di passare attraverso Internet.

- Assicurarsi che i dati della cassetta postale rispettino le limitazioni relative alla cartella e agli importi degli elementi.
    
Per ulteriori informazioni sulle prestazioni Exchange migrazione, vedere Office 365 [prestazioni e procedure consigliate per la migrazione.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
