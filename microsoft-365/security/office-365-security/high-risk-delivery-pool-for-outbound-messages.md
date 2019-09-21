---
title: Pool di recapito ad alto rischio per i messaggi in uscita
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Se il sistema di posta elettronica di un cliente è stato compromesso da malware o da un attacco di posta indesiderata e Invia la posta indesiderata in uscita tramite il servizio di filtraggio ospitato, questo può comportare l'elenco degli indirizzi IP dei server di Data Center di Office 365 che sono elencati nel blocco di terze parti elenchi.
ms.openlocfilehash: 5b9241dead5b40e9f216ecd3023d6f8b86fb0205
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083454"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Pool di recapito ad alto rischio per i messaggi in uscita

Se il sistema di posta elettronica di un cliente è stato compromesso da malware o da un attacco di posta indesiderata e Invia la posta indesiderata in uscita tramite il servizio di filtraggio ospitato, questo può comportare l'elenco degli indirizzi IP dei server di Data Center di Office 365 che sono elencati nel blocco di terze parti elenchi. Server di destinazione che non utilizzano il servizio di filtraggio ospitato, ma utilizzano questi elenchi di blocco, rifiutare tutti i messaggi di posta elettronica inviati da tutti gli indirizzi IP del filtro host che sono stati aggiunti a tali elenchi. Per evitare questo, tutti i messaggi in uscita che superano la soglia di posta indesiderata vengono inviati tramite un pool di recapito ad alto rischio. Questo pool di posta elettronica in uscita secondario viene utilizzato solo per inviare messaggi che potrebbero essere di bassa qualità. In questo modo, è possibile proteggere il resto della rete dall'invio di messaggi che hanno maggiori probabilità di provocare il blocco dell'indirizzo IP di invio.
  
L'utilizzo di un pool di recapito ad alto rischio dedicato contribuisce a garantire che il pool in uscita normale invii solo messaggi noti come di qualità elevata. L'utilizzo di questo pool IP secondario consente di ridurre la probabilità che il pool IP esterno normale venga aggiunto a un elenco bloccato. La possibilità che il pool di recapito ad alto rischio venga posizionato su un elenco bloccato resta un rischio. Questo è il funzionamento predefinito.
  
Messaggi in cui il dominio di invio non ha un record di indirizzo (un record), che fornisce l'indirizzo IP del dominio, e nessun record MX, che consente di indirizzare la posta ai server che devono ricevere la posta per un determinato dominio nel DNS, vengono sempre instradati attraverso il pool di recapito ad alto rischio a prescindere dalla disposizione di posta indesiderata.
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>Informazioni sui messaggi di notifica sullo stato del recapito (DSN)

Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i messaggi "rimbalzati" o "non riusciti" (DSN).
  
Le cause possibili di un eccessivo numero di messaggi DSN sono:
  
- Una campagna di spoofing su uno dei clienti che utilizzano il servizio
    
- Un attacco directory harvest
    
- Un attacco di posta indesiderata
    
- Un server SMTP non autorizzato
    
Tutti questi problemi possono determinare un improvviso aumento del numero di messaggi DSN elaborati dal servizio. Molte volte, questi messaggi DSN sembrano essere posta indesiderata ad altri server e servizi di posta elettronica.
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)
  

