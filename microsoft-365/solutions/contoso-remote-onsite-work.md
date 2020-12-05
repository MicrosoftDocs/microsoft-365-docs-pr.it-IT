---
title: Risposta e supporto di Contoso COVID-19 per il lavoro remoto e onsite
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo la Contoso Corporation ha risposto alla pandemia di COVID-19 e ha ingegnerizzato l'infrastruttura di installazione e aggiornamento del software per il lavoro remoto e onsite.
ms.openlocfilehash: d04b4efcdd4dd04315ad37311cdd2cfbc2e64e88
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580674"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Risposta e supporto di Contoso COVID-19 per il lavoro remoto e onsite

Contoso aveva sempre supportato i propri dipendenti remoti, che accedevano alle risorse locali tramite un server VPN centrale nella sede di Parigi. Contoso aveva emesso tutti i dipendenti remoti un computer portatile gestito. I lavoratori locali avevano una combinazione di computer desktop e laptop.

## <a name="contosos-response-to-covid-19"></a>Risposta di Contoso a COVID-19

Con l'insorgenza della pandemia di COVID-19, tutti gli addetti sono stati all'improvviso operatori remoti. Contoso ha risposto spostando la propria forza lavoro in modo da funzionare da casa e condurre le attività primarie tramite l'accesso remoto alle risorse locali e online utilizzando i servizi cloud di Microsoft 365.

Contoso disponeva di server VPN di accesso remoto nell'ufficio della sede di Parigi per supportare il 25% della sua forza lavoro già remota, ma è stato spostato rapidamente per aumentare la capacità di accesso remoto a supporto del 90% del personale. Contoso ha distribuito i server VPN di accesso remoto in ogni ufficio satellite in modo che i dipendenti remoti utilizzino un punto di ingresso vicino a livello regionale per l'accesso alla rete Intranet contoso.

Contoso ha inoltre aggiornato la configurazione dei client VPN installati su laptop, tablet e smartphone per il tunneling suddiviso in modo che il traffico per l'insieme di endpoint di Office 365 non sia stato ignorato dalla connessione VPN ed è stato inviato direttamente su Internet. Per ulteriori informazioni, vedere [ottimizzare la connettività di Office 365 per gli utenti remoti tramite il tunneling Split VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

Ecco la configurazione risultante con i dispositivi VPN installati nella sede di Parigi e in ciascuno degli uffici satellite. 

![Infrastruttura VPN di contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Un lavoratore remoto con il client VPN installato utilizza il DNS per trovare l'ufficio più vicino regionalmente e si connette al dispositivo VPN installato. Con split tunneling, il traffico verso Microsoft 365 Optimize endpoint viene inviato direttamente al percorso di rete Microsoft 365 più vicino a livello regionale. Tutti gli altri traffici vengono inviati tramite la connessione VPN al dispositivo VPN.

## <a name="contosos-support-for-remote-and-onsite-work"></a>Supporto di Contoso per il lavoro remoto e onsite

Dopo aver apportato le modifiche iniziali per supportare principalmente i lavoratori remoti durante le operazioni di blocco regionali, Contoso ha apportato modifiche all'infrastruttura per il supporto di attività remote e onsite in cui un lavoratore potrebbe essere:

- Sempre a distanza.
- Sempre onsite.
- Una combinazione di onsite e remote.

Le funzionalità di identità, sicurezza e conformità di Microsoft 365 sono progettate per la relazione di trust zero e per funzionare indipendentemente dalla posizione dell'utente e del dispositivo in uso. Per ulteriori informazioni, vedere [zero Trust](https://www.microsoft.com/security/business/zero-trust).

Tuttavia, la gestione delle nuove installazioni e degli aggiornamenti del software dipende dalla posizione del dispositivo perché il software da installare potrebbe provenire da un'origine locale o da una rete Internet. Gli architetti IT di Contoso hanno creato la nuova infrastruttura di installazione e aggiornamento in base alla posizione del dispositivo anziché al lavoratore.

Sono stati designati due tipi di dispositivi: dedicate in locale e in roaming.

### <a name="dedicated-on-premises"></a>Dedicato in locale

Un dispositivo locale dedicato è un computer desktop o server che non lascia mai la rete Intranet Contoso e non dispone di un client VPN installato. Questi dispositivi locali continuano a usare Microsoft endpoint Configuration Manager e i relativi punti di distribuzione per le installazioni e gli aggiornamenti di Windows 10, Microsoft 365 Apps for Enterprise e del browser perimetrale.

### <a name="roaming"></a>Roaming

Un dispositivo di roaming può lasciare la rete Intranet Contoso e include i computer portatili rilasciati a numerosi impiegati e a tutti i lavoratori remoti e ad altri dispositivi di proprietà dell'organizzazione, ad esempio smartphone e tablet con il client VPN contoso installato. 

Poiché questi dispositivi possono essere connessi a Internet in qualsiasi momento, usano Intune o altri servizi basati su cloud per installazioni e aggiornamenti di Windows 10, Microsoft 365 Apps for Enterprise e Edge. Non utilizzano i punti di distribuzione di gestione configurazione locali esistenti.

Questo significa che alcune delle installazioni e degli aggiornamenti per il dispositivo di roaming verranno eseguite su Internet mentre sono in locale e connesse alla rete Intranet. Ma contoso IT Architects ha deciso che la semplicità di configurazione era più importante dell'ottimizzazione della larghezza di banda Intranet su Internet, soprattutto quando la maggior parte dei worker remoti raramente sono connessi alla rete Intranet.

Di seguito viene visualizzata l'infrastruttura risultante.

![Infrastruttura di installazione e aggiornamento di contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Il comportamento di installazione e aggiornamento viene determinato rendendo gli account computer dei dispositivi membri di uno di questi gruppi:

- OnPremDevices

  Il client Configuration Manager sul dispositivo utilizza i punti di distribuzione per le installazioni e gli aggiornamenti.

- RoamingDevices

  Intune e altre impostazioni del dispositivo specificano l'utilizzo della rete Microsoft 365 per le installazioni e gli aggiornamenti.

## <a name="new-onboarding-process"></a>Nuovo processo di onboarding

Per un nuovo dispositivo locale dedicato emesso a un nuovo lavoratore o per un nuovo server in un datacenter, quando il lavoratore accede, il client di Configuration Manager basato sull'appartenenza del dispositivo nel gruppo OnPremDevices Scarica e installa gli aggiornamenti più recenti per Windows 10, Microsoft 365 Apps for Enterprise e Edge dai punti di distribuzione di Configuration Manager locali. Al termine dell'operazione, il dispositivo locale dedicato è pronto per l'uso e utilizza questi punti di distribuzione per gli aggiornamenti in corso.

Per un nuovo dispositivo remoto rilasciato a un nuovo lavoratore, quando il lavoratore accede, il dispositivo, in base alla sua appartenenza al gruppo RoamingDevices, contatta il servizio cloud di Intune e altri servizi e download e installa gli aggiornamenti più recenti per Windows 10, Microsoft 365 Apps for Enterprise e Edge. Al termine dell'operazione, il dispositivo remoto è pronto per l'uso e utilizza il client VPN installato per l'accesso alle risorse locali e la rete Microsoft 365 per gli aggiornamenti in corso.

## <a name="next-step"></a>Passaggio successivo

[Autorizzare gli utenti remoti](empower-people-to-work-remotely.md) nell'organizzazione.
