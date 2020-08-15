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
description: In questo articolo sono contenuti suggerimenti generali e collegamenti ad altre risorse che indicano come migliorare le prestazioni di Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691393"
---
# <a name="tune-exchange-online-performance"></a>Ottimizzare le prestazioni di Exchange Online

In questo articolo sono contenuti suggerimenti generali e collegamenti ad altre risorse che consentono di migliorare le prestazioni di Exchange Online, in particolare di fronte alla migrazione. Questo articolo fa parte del progetto di [pianificazione della rete e ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune) .
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Considerazioni da prendere in considerazione per migliorare le prestazioni di Exchange Online

Per migliorare la velocità di migrazione e ridurre i vincoli di larghezza di banda dell'organizzazione per Exchange Online, prendere in considerazione quanto segue:
  
- **Ridurre le dimensioni delle cassette postali.** Dimensioni inferiori della cassetta postale migliorano la velocità di migrazione. 
    
- **Utilizzare le funzionalità di spostamento delle cassette postali con una distribuzione ibrida di Exchange.** Con una distribuzione ibrida di Exchange, la posta offline (sotto forma di. File OST) non richiede un nuovo download durante la migrazione a Exchange Online. In questo modo vengono ridotti in modo significativo i requisiti di larghezza di banda per il download. 
    
- **Pianificare gli spostamenti delle cassette postali che si verificano durante i periodi di traffico Internet basso e basso utilizzo di Exchange locale.** Quando si sposta la pianificazione, le richieste di migrazione vengono inviate al proxy di replica delle cassette postali e potrebbero non avere luogo immediatamente. 
    
- **Utilizzare Lean popout per Outlook sul Web.** Lean popout fornisce versioni di alcuni messaggi di posta elettronica in Microsoft Edge o Internet Explorer più piccole e meno intensi per la memoria eseguendo il rendering di alcuni componenti sul server. Per ulteriori informazioni, vedere [use Lean popout per ridurre la memoria utilizzata per la lettura dei messaggi di posta elettronica](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Consulenza generale

- Accertarsi che la ricerca DNS per outlook.office.com entri nel MS-datacenter in una posizione logica di ingresso per la propria posizione.

- Ricercare la memorizzazione nella cache delle cassette postali e scegliere le opzioni appropriate (ri. periodo di memorizzazione nella cache, memorizzazione nella cache delle cassette postali condivise, eccetera).

- Mantenere i dati di Outlook da passare su connessioni VPN (in una sede centrale) prima che venga eseguito su Internet.

- Verificare che i dati delle cassette postali siano conformi alle limitazioni sulla cartella e sugli importi degli elementi.
    
Per ulteriori informazioni sulle prestazioni della migrazione di Exchange, vedere [Office 365 Migration performance and Best Practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).
  

