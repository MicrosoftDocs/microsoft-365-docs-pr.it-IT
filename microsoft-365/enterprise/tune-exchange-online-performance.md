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
description: In questo articolo sono contenuti suggerimenti generali e collegamenti ad altre risorse che spiegano come migliorare le prestazioni di Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691393"
---
# <a name="tune-exchange-online-performance"></a>Ottimizzare le prestazioni di Exchange Online

In questo articolo sono contenuti suggerimenti generali e collegamenti ad altre risorse che spiegano come migliorare le prestazioni di Exchange Online, in particolare prima di una migrazione. Questo articolo fa parte del progetto Pianificazione della rete e ottimizzazione delle prestazioni [per office 365.](https://aka.ms/tune)
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Aspetti da considerare per migliorare le prestazioni di Exchange Online

Per migliorare la velocità della migrazione e ridurre i vincoli di larghezza di banda dell'organizzazione per Exchange Online, considerare quanto segue:
  
- **Ridurre le dimensioni delle cassette postali.** Le dimensioni più piccole delle cassette postali migliorano la velocità di migrazione. 
    
- **Utilizzare le funzionalità di spostamento delle cassette postali con una distribuzione ibrida di Exchange.** Con una distribuzione ibrida di Exchange, la posta offline (sotto forma di . File OST) non richiede un nuovo download durante la migrazione a Exchange Online. In questo modo vengono ridotti in modo significativo i requisiti di larghezza di banda per il download. 
    
- **Pianificare gli spostamenti delle cassette postali in modo che si verifichino durante i periodi di traffico Internet ridotto e di utilizzo di Exchange locale basso.** Durante la pianificazione degli spostamenti, le richieste di migrazione vengono inviate al proxy di replica delle cassette postali e potrebbero non avere luogo immediatamente. 
    
- **Utilizzare popup snelli per Outlook sul Web.** I popout snelli forniscono versioni più piccole e meno a elevato utilizzo di memoria di alcuni messaggi di posta elettronica in Microsoft Edge o Internet Explorer tramite il rendering di alcuni componenti nel server. Per ulteriori informazioni, vedere [Use lean popouts to reduce memory used when reading mail messages.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)


## <a name="general-advice"></a>Consigli generali

- Assicurarsi che la ricerca DNS outlook.office.com il centro dati MS in una posizione di immissione logica per la posizione.

- Ricercare la memorizzazione nella cache delle cassette postali e scegliere le opzioni appropriate (re. periodo di memorizzazione nella cache, memorizzazione nella cache delle cassette postali condivise e così via).

- Evitare che i dati di Outlook superino le connessioni VPN (a una sede centrale) prima di passare attraverso Internet.

- Assicurarsi che i dati della cassetta postale rispettino le limitazioni relative alla cartella e agli elementi.
    
Per ulteriori informazioni sulle prestazioni della migrazione di Exchange, vedere Prestazioni e procedure consigliate per la migrazione [a Office 365.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
  

