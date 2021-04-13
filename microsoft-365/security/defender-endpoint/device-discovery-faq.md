---
title: Domande frequenti sull'individuazione dei dispositivi
description: Trovare le risposte alle domande frequenti sull'individuazione dei dispositivi
keywords: individuazione dei dispositivi, individuazione, passiva, proattiva, rete, visibilità, server, workstation, onboard, dispositivi non gestiti
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7165d943fd39e298894531f1dabdec408144898d
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698439"
---
# <a name="device-discovery-frequently-asked-questions"></a>Domande frequenti sull'individuazione dei dispositivi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Trova le risposte alle domande frequenti (FAQ) sull'individuazione dei dispositivi.

## <a name="what-is-basic-discovery-mode"></a>Che cos'è la modalità di individuazione di base?
Questa modalità consente a tutti i dispositivi di Microsoft Defender for Endpoint onboarded di raccogliere dati di rete e individuare i dispositivi adiacenti. Gli endpoint onboarded raccolgono passivamente gli eventi nella rete ed estraggono le informazioni sul dispositivo da essi. Non verrà avviato alcun traffico di rete. Gli endpoint onboarded estraggono semplicemente i dati da ogni traffico di rete visualizzato da un dispositivo onboarded. Questi dati utilizzati per elencare i dispositivi non gestiti nella rete.

## <a name="can-i-disable-basic-discovery"></a>È possibile disabilitare l'individuazione di base?
Puoi disattivare l'individuazione dei dispositivi tramite la [pagina Funzionalità](advanced-features.md) avanzate. Tuttavia, si perderà la visibilità sui dispositivi non gestiti nella rete. 

## <a name="what-is-standard-discovery-mode"></a>Che cos'è la modalità di individuazione standard?
 In questa modalità gli endpoint onboarded in Microsoft Defender for Endpoint possono eseguire attivamente il probe dei dispositivi osservati nella rete per arricchire i dati raccolti (con quantità trascurabile di traffico di rete). Questa modalità è altamente consigliata per creare un inventario dei dispositivi affidabile e coerente. Se si sceglie di disabilitare questa modalità e si seleziona Modalità di individuazione di base, è probabile che si oda solo una visibilità limitata degli endpoint non gestiti nella rete.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Posso controllare quali dispositivi eseguono l'individuazione standard?
 Puoi personalizzare l'elenco dei dispositivi usati per eseguire l'individuazione standard. Puoi abilitare l'individuazione standard in tutti i dispositivi onboarded che supportano anche questa funzionalità (attualmente solo dispositivi Windows 10) oppure selezionare un sottoinsieme o un sottoinsieme dei dispositivi specificando i tag del dispositivo. In questo caso, tutti gli altri dispositivi verranno configurati per eseguire solo l'individuazione di base. La configurazione è disponibile nella pagina delle impostazioni di individuazione dei dispositivi.

## <a name="which-onboarded-devices-can-perform-discovery"></a>Quali dispositivi onboarded possono eseguire l'individuazione?
 I dispositivi onboarded in esecuzione in Windows 10 versione 1809 o successiva possono eseguire l'individuazione.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>Cosa succede se i dispositivi onboarded sono connessi alla rete domestica o al punto di accesso pubblico?
 Il motore di individuazione distingue tra gli eventi di rete ricevuti nella rete aziendale e l'esterno della rete aziendale. Correlando gli identificatori di rete tra tutti i client del tenant, gli eventi sono differenziati tra quelli ricevuti da reti private e reti aziendali. I dispositivi di rete privata non verranno elencati nell'inventario e non verranno attivamente sondati.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>Quali protocolli si stanno acquisendo e analizzando?
 Per impostazione predefinita, tutti i dispositivi onboarded in esecuzione su Windows 10 versione 1809 o successiva acquisisce e analizzano i protocolli seguenti: ARP, CDP, DHCP, DHCPv6, IP (intestazioni), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (intestazioni), UDP (intestazioni), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Quali protocolli vengono utilizzati per il probe attivo nell'individuazione standard?
 Quando un dispositivo è configurato per eseguire l'individuazione standard, i servizi esposti vengono sondati utilizzando i protocolli seguenti: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Come è possibile escludere le destinazioni dal sondaggio con l'individuazione standard?
 Se nella rete sono presenti dispositivi che non devono essere controllati attivamente, è anche possibile definire un elenco di esclusioni per impedirne l'analisi. La configurazione è disponibile nella pagina delle impostazioni di individuazione dei dispositivi.

## <a name="can-i-exclude-devices-from-being-discovered"></a>È possibile escludere i dispositivi dall'individuare?
 Poiché l'individuazione dei dispositivi usa metodi passivi per individuare i dispositivi nella rete, qualsiasi dispositivo che comunica con i dispositivi onboarded nella rete aziendale può essere individuato ed elencato nell'inventario. Puoi escludere solo i dispositivi dal probe attivo.

## <a name="how-frequent-is-the-active-probing"></a>Quanto è frequente il sondaggio attivo?
 I dispositivi verranno attivamente sondati quando vengono osservate modifiche alle caratteristiche dei dispositivi e una volta alla settimana per assicurarsi che le informazioni esistenti siano aggiornate.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Lo strumento di sicurezza ha generato un avviso UnicastScanner.ps1'attività di scansione delle porte avviata da esso, cosa devo fare?
 Gli script di sondaggio attivi sono firmati da Microsoft e sono sicuri. È possibile aggiungere il percorso seguente all'elenco di esclusione: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Qual è la quantità di traffico generata dal probe attivo di individuazione standard?
 Il probe attivo può generare fino a 5K di traffico tra il dispositivo onboarded e il dispositivo di cui è stato eseguito il probe, ogni tentativo di sondaggio

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>Perché esiste una discrepanza tra i dispositivi "possono essere onboarded" nell'inventario dei dispositivi e il numero di "dispositivi da onboardare" nel riquadro del dashboard?
Potresti notare differenze tra il numero di dispositivi elencati in "può essere onboarded" nell'inventario dei dispositivi, il suggerimento di sicurezza "Onboard to Microsoft Defender for Endpoint" e il widget dashboard "dispositivi da onboardare".

 Il suggerimento per la sicurezza e il widget del dashboard sono per i dispositivi che sono stabili nella rete; esclusi i dispositivi effimeri, i dispositivi guest e altri. L'idea è quella di consigliare nei dispositivi permanenti, che implicano anche il punteggio di sicurezza complessivo dell'organizzazione.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>Posso eseguire l'onboard di dispositivi non gestiti trovati?
 Sì. Gli endpoint non gestiti nella rete introducono vulnerabilità e rischi per la rete. L'onboarding al servizio può aumentare la visibilità della sicurezza su di essi. 


