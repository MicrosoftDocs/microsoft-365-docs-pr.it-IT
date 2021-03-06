---
title: Risposta e supporto COVID-19 di Contoso per il lavoro ibrido
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo Contoso Corporation ha risposto alla pandemia COVID-19 e ha progettato l'infrastruttura di installazione e aggiornamento software per il lavoro ibrido.
ms.openlocfilehash: 2d28b0513221f6c14526baba69bf0f5986154805
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788380"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Risposta e supporto COVID-19 di Contoso per il lavoro ibrido

Contoso aveva sempre supportato i lavoratori remoti, che accedevano alle risorse locali tramite un server VPN centrale nella sede di Parigi. Contoso ha emesso a tutti i lavoratori remoti un portatile gestito. I lavoratori locali avevano una combinazione di computer desktop e portatili.

## <a name="contosos-response-to-covid-19"></a>Risposta di Contoso a COVID-19

Con l'inizio della pandemia COVID-19, improvvisamente tutti i lavoratori, ma essenziali, erano lavoratori remoti. Contoso ha risposto spostando la forza lavoro a lavorare da casa e svolgendo le attività principali tramite l'accesso remoto alle risorse locali e online utilizzando Microsoft 365 cloud.

Contoso disponeva di server VPN di accesso remoto nella sede centrale di Parigi per supportare il 25% della forza lavoro già remota, ma si è spostata rapidamente per aumentare la capacità di accesso remoto per supportare il 90% della forza lavoro. Contoso ha distribuito server VPN di accesso remoto in ogni sede satellite in modo che i lavoratori remoti utilizzino un punto di ingresso vicino a livello regionale per l'accesso alla rete Intranet di Contoso.

Contoso ha inoltre aggiornato la configurazione dei client VPN installati su portatili, tablet e smartphone per lo split tunneling in modo che il traffico per il set di endpoint di Office 365 optimize ignorava la connessione VPN e fosse stato inviato direttamente tramite Internet. Per ulteriori informazioni, vedere [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).

Ecco la configurazione risultante con i dispositivi VPN installati nella sede centrale di Parigi e in ognuna delle sedi satellite. 

![Infrastruttura VPN di Contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Un lavoratore remoto con il client VPN installato usa DNS per trovare l'ufficio più vicino a livello regionale e si connette al dispositivo VPN installato lì. Con il split tunneling, il traffico Microsoft 365 gli endpoint Optimize vengono inviati direttamente al percorso di rete Microsoft 365 regionale più vicino. Tutto l'altro traffico viene inviato tramite la connessione VPN al dispositivo VPN.

## <a name="contosos-support-for-hybrid-work"></a>Supporto di Contoso per il lavoro ibrido

Dopo aver apportato le modifiche iniziali per supportare la maggior parte dei lavoratori remoti durante i blocchi regionali, Contoso ha apportato modifiche all'infrastruttura per supportare il lavoro ibrido in cui un lavoratore potrebbe essere:

- Sempre remoto.
- Sempre in sede.
- Combinazione di locale e remoto.

Microsoft 365 funzionalità di identità, sicurezza e conformità sono progettate per zero trust e per funzionare indipendentemente dalla posizione dell'utente e del dispositivo. Per ulteriori informazioni, vedere [Zero Trust.](https://www.microsoft.com/security/business/zero-trust)

Tuttavia, la gestione di nuove installazioni e aggiornamenti del software dipende dalla posizione del dispositivo, perché il software da installare potrebbe derivare da un'origine locale o Internet. Gli architetti IT di Contoso hanno progettato le nuove installazioni e gli aggiornamenti dell'infrastruttura in base alla posizione del dispositivo, anziché al lavoratore.

Hanno designato due tipi di dispositivi: dedicati in locale e roaming.

### <a name="dedicated-on-premises"></a>Dedicato in locale

Un dispositivo locale dedicato è un computer desktop o server che non lascia mai la rete Intranet di Contoso e non dispone di un client VPN installato. Questi dispositivi locali continuano a usare Microsoft Endpoint Configuration Manager e i relativi punti di distribuzione per le installazioni e gli aggiornamenti di Windows 10, Microsoft 365 Apps for enterprise e il browser Edge.

### <a name="roaming"></a>Roaming

Un dispositivo mobile può lasciare la rete Intranet di Contoso e include i portatili rilasciati a molti dipendenti dell'ufficio e a tutti i lavoratori remoti e ad altri dispositivi di proprietà dell'organizzazione, ad esempio smartphone e tablet con il client VPN Contoso installato. 

Poiché questi dispositivi possono essere connessi a Internet in qualsiasi momento, usano Intune o altri servizi basati su cloud per le installazioni e gli aggiornamenti di Windows 10, Microsoft 365 Apps for enterprise e Edge. Non usano i punti di distribuzione di Configuration Manager locali esistenti.

Ciò significa che alcune delle installazioni e degli aggiornamenti per il dispositivo mobile verranno eseguite su Internet mentre sono locali e connessi alla rete Intranet. Tuttavia, gli architetti IT di Contoso hanno deciso che la semplicità di configurazione era più importante dell'ottimizzazione della larghezza di banda Intranet su Internet, soprattutto quando la maggior parte dei lavoratori remoti è raramente connessa alla rete Intranet.

Ecco l'infrastruttura risultante.

![Infrastruttura di installazione e aggiornamento di Contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Il comportamento di installazione e aggiornamento viene determinato rendendo gli account computer dei dispositivi membri di uno di questi gruppi:

- OnPremDevices

  Il client di Configuration Manager nel dispositivo usa i punti di distribuzione per le installazioni e gli aggiornamenti.

- RoamingDevices

  Intune e altre impostazioni nel dispositivo specificano l'uso della rete Microsoft 365 per le installazioni e gli aggiornamenti.

## <a name="new-onboarding-process"></a>Nuovo processo di onboarding

Per un nuovo dispositivo locale dedicato rilasciato a un nuovo lavoratore o a un nuovo server in un datacenter, quando il lavoratore accede, il client di Configuration Manager in base all'appartenenza del dispositivo al gruppo OnPremDevices scarica e installa gli aggiornamenti più recenti per Windows 10, Microsoft 365 Apps for enterprise e Edge dai punti di distribuzione di Configuration Manager locali. Al termine, il dispositivo locale dedicato è pronto per l'uso e usa questi punti di distribuzione per gli aggiornamenti in corso.

Per un nuovo dispositivo remoto rilasciato a un nuovo lavoratore, quando il lavoratore esegue l'accesso, il dispositivo, in base all'appartenenza al gruppo RoamingDevices, contatta il servizio cloud Intune e altri servizi e scarica e installa gli aggiornamenti più recenti per Windows 10, Microsoft 365 Apps for enterprise ed Edge. Al termine, il dispositivo remoto è pronto per l'uso e utilizza il client VPN installato per l'accesso alle risorse locali e alla rete Microsoft 365 per gli aggiornamenti in corso.

## <a name="next-step"></a>Passaggio successivo

[Configurare l'infrastruttura per il lavoro ibrido](empower-people-to-work-remotely.md) nell'organizzazione.
