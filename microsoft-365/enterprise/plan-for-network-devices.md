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
description: 'Riepilogo: vengono descritte le considerazioni relative alla capacità di rete, agli acceleratori WAN e ai dispositivi di bilanciamento del carico utilizzati per connettersi a Office 365.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691203"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Pianificare i dispositivi di rete che si connettono ai servizi di Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.
  
Alcuni componenti hardware di rete potrebbero avere limitazioni sul numero di sessioni simultanee supportate. Per le organizzazioni con più di 2.000 utenti, è consigliabile monitorare i dispositivi di rete per assicurarsi che siano in grado di gestire il traffico aggiuntivo del servizio Office 365. Il software di monitoraggio SNMP (Simple Network Management Protocol) consente di eseguire questa operazione.

Questo articolo fa parte della pianificazione [della rete e dell'ottimizzazione delle prestazioni per Office 365.](https://aka.ms/tune)

Le impostazioni del proxy Internet in uscita locale influiscono anche sulla connettività ai servizi di Office 365 per le applicazioni client. È inoltre necessario configurare i dispositivi proxy di rete per consentire le connessioni per gli URL e le applicazioni dei servizi cloud Microsoft. Ogni organizzazione è diversa. Per avere un'idea di come Microsoft gestisce questo processo e della quantità di larghezza di banda di cui viene eseguito il provisioning, [leggere il case study.](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)
  
I seguenti articoli della Guida di Skype for Business hanno altre informazioni sulle impostazioni di Skype for Business:
  
- [Risoluzione dei problemi di accesso a Skype for Business online per gli amministratori](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Non è possibile connettersi a Skype for Business o alcune funzionalità non funzionano perché un firewall locale blocca la connessione](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Anche se molte di queste impostazioni sono specifiche di Skype for Business, le indicazioni generali sulla configurazione di rete sono utili per tutti i servizi di Office 365.
  
## <a name="determining-network-capacity"></a>Determinazione della capacità di rete

Ogni dispositivo di rete presente in una connessione ha il limite di capacità. Questi dispositivi includono le schede di rete client e server, i router, i commutatori e gli hub che li interconnettono. Una capacità di rete adeguata significa che nessuno di essi è saturato. Il monitoraggio dell'attività di rete è essenziale per garantire che i carichi effettivi su tutti i dispositivi di rete siano inferiori alla capacità massima. La capacità di rete influisce sulle prestazioni del dispositivo proxy.
  
In molti casi, il limite per la quantità di traffico dipende dalla larghezza della banda di connessione Internet. Le prestazioni scarse durante le ore di punta del traffico sono probabilmente causate dall'utilizzo eccessivo del collegamento Internet. Questa situazione si applica anche a uno scenario di succursale, in cui i computer server proxy della succursale sono connessi al dispositivo proxy nella sede centrale della succursale tramite un collegamento WAN (Wide Area Network) lento.
  
Per testare la capacità di rete, monitorare l'attività di rete nell'interfaccia di rete proxy. Se si tratta di più del 75% della larghezza di banda massima di qualsiasi interfaccia di rete, valutare la possibilità di aumentare la larghezza di banda dell'infrastruttura di rete inadeguata. In caso contrario, è consigliabile usare funzionalità avanzate, ad esempio la compressione HTTP.
  
## <a name="wan-accelerators"></a>Acceleratori WAN

Se l'organizzazione utilizza dispositivi proxy di accelerazione WAN (Wide Area Network), è possibile che si verifichino problemi durante l'accesso ai servizi di Office 365. Potrebbe essere necessario ottimizzare il dispositivo o i dispositivi di rete per garantire agli utenti un'esperienza coerente quando accedono a Office 365. Ad esempio, i servizi di Office 365 crittografano alcuni contenuti di Office 365 e l'intestazione TCP. Il dispositivo potrebbe non essere in grado di gestire questo tipo di traffico.
  
Leggere la nostra dichiarazione di supporto sull'uso del controller di ottimizzazione [WAN o dei dispositivi traffico/ispezione con Office 365.](https://support.microsoft.com/kb/2690045)
  
## <a name="hardware-and-software-load-balancing-devices"></a>Dispositivi hardware e software di bilanciamento del carico

L'organizzazione deve utilizzare un servizio di bilanciamento del carico hardware (HLB) o una soluzione bilanciamento del carico di rete (NLB) per distribuire le richieste ai server Active Directory Federation Services (AD FS) e/o ai server ibridi di Exchange. I dispositivi di bilanciamento del carico controllano il traffico di rete verso i server locali. Questi server sono fondamentali per garantire la disponibilità di Single #A0 e della distribuzione ibrida di Exchange.
  
Microsoft fornisce una soluzione di bilanciamento del carico di rete basata su software integrata in Windows Server. Office 365 supporta questa soluzione per ottenere il bilanciamento del carico.
  
## <a name="firewalls-and-proxies"></a>Firewall e proxy

Per ulteriori dettagli sulla configurazione di firewall e proxy per la connessione a Office 365, vedere Gestione degli endpoint di [Office 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)Valutazione della connettività di rete di [Office 365](assessing-network-connectivity.md)e Domande frequenti sugli endpoint di [Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) per ulteriori informazioni sui dispositivi e sulla selezione dei circuiti.
  
## <a name="see-also"></a>Vedere anche

[Guide alla configurazione per i servizi di Office 365](setup-guides-for-microsoft-365.md)

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
