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
description: In questo articolo viene descritto come è possibile eseguire la distribuzione in SharePoint Online senza eseguire test di carico tradizionali poiché non è consentito.
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905225"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Pianificazione della capacità e test di carico di SharePoint Online
In questo articolo viene descritto come è possibile eseguire la distribuzione a SharePoint Online senza test di carico tradizionali, poiché il test di carico non è consentito in SharePoint Online. SharePoint Online è un servizio cloud e le funzionalità di carico, l'integrità e il bilanciamento generale del carico nel servizio sono gestiti da Microsoft.
  
L'approccio migliore per garantire il successo dell'avvio del sito consiste nel seguire i principi, le procedure e i suggerimenti di base evidenziati nel piano di implementazione del lancio [del portale.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Panoramica di come SharePoint online esegue la pianificazione della capacità 
Uno dei principali vantaggi di SharePoint Online rispetto a una distribuzione locale è l'elasticità del cloud e le ottimizzazioni per gli utenti nelle aree distribuite. L'ambiente su larga scala è configurato per gestire milioni di utenti ogni giorno, quindi è importante gestire la capacità in modo efficace bilanciando ed espandendo le farm.
  
Anche se la crescita è spesso imprevedibile per qualsiasi tenant in una farm, la somma aggregata delle richieste è prevedibile nel tempo. Identificando le tendenze di crescita in SharePoint Online, possiamo pianificare l'espansione futura.
  
Per utilizzare in modo efficiente la capacità e gestire una crescita imprevista, in qualsiasi farm è disponibile un'automazione che tiene traccia e monitora vari elementi del servizio. Vengono utilizzate più metriche, una delle principali è il carico della CPU, che viene utilizzata come segnale per la scalabilità verticale dei server front-end. Inoltre, è consigliabile un approccio [phased/wave,](planportallaunchroll-out.md)in quanto gli ambienti SQL verranno ridimensionati in base al carico e alla crescita nel tempo e seguendo le fasi e le onde è possibile la corretta distribuzione di tale carico e crescita. 

La capacità non riguarda solo l'aggiunta continua di ulteriori componenti hardware, ma anche la gestione e il controllo di tale capacità per garantire la manutenzione di richieste di carico valide. È consigliabile che i clienti seguano le indicazioni consigliate per garantire la migliore esperienza. Significa anche che sono presenti modelli e controlli di limitazione per garantire che non sia consentito un comportamento "offensivo" nel servizio. Anche se non tutto il comportamento "negativo" è intenzionale, dobbiamo essere certi di limitare l'effetto di tale comportamento. Per ulteriori informazioni sulla limitazione e su [](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) come evitarla, vedere l'articolo sulle linee guida per evitare limitazioni.

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Perché non è possibile caricare test SharePoint Online
Con gli ambienti locali, il test di carico viene utilizzato per convalidare il presupposto della scalabilità e infine trovare il punto di interruzione di una farm. saturando con il carico. 

Con SharePoint Online dobbiamo fare le cose in modo diverso perché la scala è relativamente fluida e regola, limitazione e carico dei controlli, in base a determinate euristiche. Essendo un ambiente multi-tenant su larga scala, è necessario proteggere tutti i tenant nella stessa farm, in modo da limitazione automatica di tutti i test di carico. Se tuttavia si tenta di eseguire il test di carico, oltre a essere limitato, si riceveranno risultati deludenti e potenzialmente fuorvianti perché la farm testata oggi probabilmente avrà subito modifiche di scala durante la finestra di test o entro poche ore dal testing, poiché le azioni di bilanciamento della scala e della farm vengono eseguite in modo continuativo.

Invece di provare a eseguire test di SharePoint come servizio, concentrarsi sul seguire le procedure consigliate e seguire le indicazioni [creazione,](/sharepoint/portal-health) avvio e manutenzione di un portale integro.