---
title: Pianificare i dispositivi di rete che si connettono ai servizi di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 'Riepilogo: vengono descritte le considerazioni relative alla capacità di rete, agli acceleratori WAN e ai dispositivi di bilanciamento del carico utilizzati per la connessione a Office 365.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691203"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Pianificare i dispositivi di rete che si connettono ai servizi di Office 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*
  
Alcuni componenti hardware di rete possono avere limitazioni sul numero di sessioni simultanee supportate. Per le organizzazioni con più di 2.000 utenti, è consigliabile monitorare i propri dispositivi di rete per assicurarsi che siano in grado di gestire il traffico di servizio aggiuntivo di Office 365. Il software di monitoraggio SNMP (Simple Network Management Protocol) consente di eseguire questa operazione.

Questo articolo fa parte della [pianificazione della rete e dell'ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune).

Le impostazioni proxy Internet in uscita locali influiscono anche sulla connettività ai servizi di Office 365 per le applicazioni client. È inoltre necessario configurare i dispositivi proxy di rete in modo che consentano le connessioni per le applicazioni e gli URL dei servizi cloud Microsoft. Ogni organizzazione è diversa. Per avere un'idea del modo in cui Microsoft gestisce questo processo e la quantità di larghezza di banda fornita, [leggere il case study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
Negli articoli della Guida di Skype for business seguenti sono disponibili ulteriori informazioni sulle impostazioni di Skype for business:
  
- [Risoluzione dei problemi relativi agli errori di accesso di Skype for business online per gli amministratori](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Non è possibile connettersi a Skype for business o alcune funzionalità non funzionano, perché un firewall locale blocca la connessione](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Anche se molte di queste impostazioni sono specifiche per Skype for business, le indicazioni generali sulla configurazione di rete sono utili per tutti i servizi di Office 365.
  
## <a name="determining-network-capacity"></a>Determinazione della capacità di rete

Ogni dispositivo di rete che esiste su una connessione ha un limite di capacità. Tra questi dispositivi sono incluse le schede di rete client e server, i router, gli interruttori e gli hub che interconnettono. Capacità di rete adeguata significa che nessuno di essi è saturo. Il monitoraggio delle attività di rete è essenziale per garantire che i carichi effettivi su tutti i dispositivi di rete siano inferiori alla capacità massima. La capacità di rete influisce sulle prestazioni del dispositivo proxy.
  
In molti casi, il limite per la quantità di traffico dipende dalla larghezza della banda di connessione Internet. Le prestazioni deboli durante le ore di punta del traffico sono probabilmente causate da un utilizzo eccessivo del collegamento Internet. Questa situazione si applica anche a uno scenario di succursale, in cui i computer server proxy di succursale sono connessi al dispositivo proxy presso la sede centrale su un collegamento di rete WAN (Wide Area Network) lento.
  
Per testare la capacità di rete, monitorare l'attività di rete nell'interfaccia di rete del proxy. Se si tratta di più del 75% della larghezza di banda massima di qualsiasi interfaccia di rete, è consigliabile aumentare la larghezza di banda dell'infrastruttura di rete inadeguata. In alternativa, prendere in considerazione l'utilizzo di funzionalità avanzate, ad esempio la compressione HTTP.
  
## <a name="wan-accelerators"></a>Acceleratori WAN

Se nell'organizzazione vengono utilizzati dispositivi proxy di accelerazione WAN (Wide Area Network), è possibile che si verifichino problemi quando si accede ai servizi di Office 365. Potrebbe essere necessario ottimizzare il dispositivo o i dispositivi di rete per garantire che gli utenti abbiano un'esperienza coerente quando si accede a Office 365. Ad esempio, i servizi di Office 365 crittografano alcuni contenuti di Office 365 e l'intestazione TCP. Il dispositivo potrebbe non essere in grado di gestire questo tipo di traffico.
  
Leggere la nostra dichiarazione di supporto sull' [utilizzo di controller di ottimizzazione WAN o dispositivi di traffico/ispezione con Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Dispositivi hardware e software di bilanciamento del carico

È necessario che l'organizzazione utilizzi una soluzione di bilanciamento del carico hardware o di bilanciamento del carico di rete per distribuire le richieste ai server Active Directory Federation Services (AD FS) e/o ai server ibridi di Exchange. I dispositivi di bilanciamento del carico controllano il traffico di rete verso i server locali. Questi server sono fondamentali per contribuire a garantire la disponibilità del servizio Single Sign-on e della distribuzione ibrida di Exchange.
  
Viene fornita una soluzione NLB basata su software incorporata in Windows Server. Office 365 supporta questa soluzione per ottenere il bilanciamento del carico.
  
## <a name="firewalls-and-proxies"></a>Firewall e proxy

Per ulteriori informazioni sulla configurazione di firewall e proxy per la connessione a Office 365, vedere [Managing office 365 Endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [valutazione di Office 365 network connectivity](assessing-network-connectivity.md)e [Office 365 Endpoints FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) per ulteriori informazioni sui dispositivi e sulla selezione dei circuiti.
  
## <a name="see-also"></a>Vedere anche

[Guide all'installazione per i servizi di Office 365](setup-guides-for-microsoft-365.md)

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
