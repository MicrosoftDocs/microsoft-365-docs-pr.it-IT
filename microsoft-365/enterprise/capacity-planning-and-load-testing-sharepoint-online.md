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
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691398"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Pianificazione della capacità e test di carico di SharePoint Online
In questo articolo viene descritto come è possibile eseguire la distribuzione in SharePoint Online senza test di carico tradizionale, poiché il test di carico non è consentito in SharePoint Online. SharePoint Online è un servizio cloud e le funzionalità di carico, integrità e equilibrio complessivo del carico nel servizio sono gestite da Microsoft.
  
L'approccio migliore per garantire il successo dell'avvio del sito consiste nel seguire i principi, le procedure e i consigli di base evidenziati nel piano di implementazione del lancio [del portale.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Panoramica del modo in cui SharePoint Online esegue la pianificazione della capacità 
Uno dei principali vantaggi di SharePoint Online rispetto a una distribuzione locale è l'elasticità del cloud e le ottimizzazioni per gli utenti nelle aree distribuite. L'ambiente su larga scala è configurato per gestire quotidianamente milioni di utenti, pertanto è importante gestire la capacità in modo efficace bilanciando ed espandendo le farm.
  
Anche se la crescita è spesso imprevedibile per qualsiasi tenant in una farm, la somma aggregata delle richieste è prevedibile nel tempo. Identificando le tendenze di crescita in SharePoint Online, è possibile pianificare un'espansione futura.
  
Per utilizzare in modo efficiente la capacità e gestire una crescita imprevista, in qualsiasi farm è disponibile un'automazione che tiene traccia e monitora vari elementi del servizio. Vengono utilizzate più metriche, una delle principali è il carico della CPU, che viene usato come segnale per la scalabilità verticale dei server front-end. Inoltre, è consigliabile un approccio basato su [fasi/ondate,](planportallaunchroll-out.md)in quanto gli ambienti SQL verranno ridimensionati in base al carico e alla crescita nel tempo e, seguendo le fasi e le ondate, è possibile una corretta distribuzione di tale carico e crescita. 

La capacità non si tratta semplicemente di aggiungere più hardware su base continua, ma riguarda anche la gestione e il controllo di tale capacità per garantire la manutenzione di richieste di carico valide. È consigliabile che i clienti seguano le indicazioni consigliate per garantire la migliore esperienza. Ciò significa anche che sono presenti controlli e modelli di limitazione per garantire che non sia consentito un comportamento "offensivo" nel servizio. Anche se non tutto il comportamento "negativo" è intenzionale, dobbiamo essere certi di limitare l'effetto di tale comportamento. Per ulteriori informazioni sulla limitazione e su come evitarla, vedere l'articolo sulle linee guida per evitare [limitazioni.](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Perché non è possibile eseguire il test di carico di SharePoint Online
Con gli ambienti locali, il test di carico viene utilizzato per convalidare il presupposto della scalabilità e trovare il punto di interruzione di una farm; saturarlo con il carico. 

Con SharePoint Online è necessario eseguire le operazioni in modo diverso perché la scala è relativamente fluida e regola, limitazione e carico dei controlli, in base a determinate euristiche. Essendo un ambiente multi-tenant su larga scala, è necessario proteggere tutti i tenant nella stessa farm, pertanto verranno automaticamente limitate eventuali test di carico. Se tuttavia si tenta di caricare il test, oltre a essere limitato, si riceveranno risultati insoddienti e potenzialmente fuorvianti perché la farm testata oggi probabilmente avrà subito modifiche di scala durante la finestra di test o entro ore successive al test, in quanto le azioni di bilanciamento della scala e della farm vengono eseguite su base continuativa.

Invece di provare a caricare SharePoint come servizio, concentrarsi piuttosto sul seguire le procedure consigliate e seguire le indicazioni sulla [creazione,](https://go.microsoft.com/fwlink/?linkid=2105838) l'avvio e la gestione di un portale integro.
