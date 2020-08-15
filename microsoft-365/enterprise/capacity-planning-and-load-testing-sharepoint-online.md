---
title: Pianificazione della capacità e test di carico di SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: In questo articolo viene descritto come distribuire SharePoint Online senza eseguire il test di carico tradizionale, poiché non è consentito.
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691398"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Pianificazione della capacità e test di carico di SharePoint Online
In questo articolo viene descritto come eseguire la distribuzione in SharePoint Online senza il test di carico tradizionale, in quanto i test di carico non sono consentiti in SharePoint Online. SharePoint Online è un servizio cloud e le funzionalità di carico, integrità e bilanciamento del carico generale del servizio sono gestite da Microsoft.
  
L'approccio migliore per garantire il successo del lancio del sito consiste nel seguire i principi di base, le procedure e i suggerimenti evidenziati nel [piano di avvio del lancio del portale](planportallaunchroll-out.md).

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Panoramica del modo in cui SharePoint Online esegue la pianificazione della capacità 
Uno dei principali vantaggi di SharePoint online in una distribuzione locale è l'elasticità del cloud e le ottimizzazioni per gli utenti nelle aree distribuite. L'ambiente su larga scala è configurato per il servizio di milioni di utenti su base giornaliera, pertanto è importante gestire efficacemente la capacità mediante l'equilibratura e l'espansione delle farm.
  
Anche se la crescita è spesso imprevedibile per qualsiasi tenant di una farm, la somma aggregata delle richieste è prevedibile nel tempo. Identificando le tendenze di sviluppo in SharePoint Online, è possibile pianificare la futura espansione.
  
Al fine di utilizzare in modo efficiente la capacità e gestire la crescita imprevista, in qualsiasi farm, è presente un'automazione che consente di tenere traccia e monitorare vari elementi del servizio. Vengono utilizzate più metriche, in cui una delle principali è il carico della CPU, che viene utilizzato come segnale per la scalabilità verticale dei Front End Server. Inoltre, si consiglia di utilizzare un [approccio phased/Wave](planportallaunchroll-out.md), in quanto gli ambienti SQL verranno scalati in base al carico e alla crescita nel tempo e, seguendo le fasi e le onde, è possibile distribuire correttamente tale carico e crescita. 

La capacità non è solo l'aggiunta di ulteriori componenti hardware su base continuativa, ma anche la gestione e il controllo di tale capacità per garantire che sia in grado di gestire le richieste di carico valide. È consigliabile che i clienti seguano le indicazioni consigliate per garantire la migliore esperienza. Significa anche che sono presenti modelli di limitazione e controlli sul posto per garantire che non si consentano comportamenti "abusivi" nel servizio. Anche se non tutti i comportamenti "cattivi" sono intenzionali, è necessario garantire che vengano limitati gli effetti del comportamento. Per ulteriori informazioni sulla limitazione e su come evitarlo, vedere l'articolo su [come evitare di essere limitato](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) .

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Perché non è possibile caricare il test di SharePoint Online
Con gli ambienti locali, il test di carico viene utilizzato per convalidare il presupposto della scala e infine individuare il punto di interruzione di una farm. saturando il carico. 

Con SharePoint Online, è necessario eseguire le operazioni in modo diverso poiché la scala è relativamente fluida e regola, limita e controlla il carico, in base a determinati sistemi euristici. Poiché si tratta di un ambiente multi-tenant su vasta scala, è necessario proteggere tutti i tenant della stessa farm, in modo da limitare automaticamente eventuali test di carico. Tuttavia, se si tenta di caricare il test, oltre a essere limitato, si riceveranno risultati deludenti e potenzialmente indesiderati perché la farm che si è verificata oggi avrà probabilmente avuto modifiche in scala durante la finestra di testing o in poche ore dopo il test, in quanto le azioni di scala e di bilanciamento della farm vengono eseguite su base continuativa.

Invece di tentare di caricare SharePoint come servizio, concentrarsi su seguendo le procedure consigliate e seguire le istruzioni per la [creazione, l'avvio e la gestione di un portale integro](https://go.microsoft.com/fwlink/?linkid=2105838) .
