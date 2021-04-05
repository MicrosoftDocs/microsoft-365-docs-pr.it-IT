---
title: Esaminare gli eventi di connessione che si verificano dietro i proxy di inoltro.
description: Scopri come usare il monitoraggio avanzato del livello HTTP tramite la protezione di rete in Microsoft Defender ATP, che rappresenta una destinazione reale, anziché un proxy.
keywords: proxy, protezione di rete, proxy di inoltro, eventi di rete, controllo, blocco, nomi di dominio, dominio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 28d8a113ed77e9624bd914571b1af4a7ece2aa5c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587564"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Esaminare gli eventi di connessione che si verificano dietro i proxy di inoltro.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Defender for Endpoint supporta il monitoraggio delle connessioni di rete da diversi livelli dello stack di rete. Un caso difficile è quando la rete utilizza un proxy di inoltro come gateway a Internet.

Il proxy agisce come se fosse l'endpoint di destinazione.  In questi casi, i monitor delle connessioni di rete semplici controllano le connessioni con il proxy corretto, ma con un valore di indagine inferiore. 

Defender for Endpoint supporta il monitoraggio avanzato a livello HTTP tramite la protezione di rete. Quando è attivata, viene visualizzato un nuovo tipo di evento che espone i nomi di dominio di destinazione reali.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Usare la protezione di rete per monitorare la connessione di rete dietro un firewall
Il monitoraggio della connessione di rete dietro un proxy di inoltro è possibile a causa di eventi di rete aggiuntivi che hanno origine dalla protezione di rete. Per vederli in una sequenza temporale del dispositivo, attiva la protezione di rete (almeno in modalità di controllo). 

La protezione di rete può essere controllata utilizzando le modalità seguenti:

- **Blocca** <br> Agli utenti o alle app verrà impedito di connettersi a domini pericolosi. Sarà possibile visualizzare questa attività in Microsoft Defender Security Center.
- **Audit** <br> Agli utenti o alle app non verrà impedito di connettersi a domini pericolosi. Tuttavia, questa attività continuerà a essere visualizzata in Microsoft Defender Security Center.


Se si disattiva la protezione di rete, agli utenti o alle app non verrà impedito di connettersi a domini pericolosi. Non verrà visualizzata alcuna attività di rete in Microsoft Defender Security Center.

Se non lo si configura, il blocco della rete verrà disattivato per impostazione predefinita.

Per ulteriori informazioni, vedere [Enable network protection](enable-network-protection.md).

## <a name="investigation-impact"></a>Impatto dell'indagine
Quando la protezione di rete è attivata, vedrai che nella sequenza temporale di un dispositivo l'indirizzo IP continuerà a rappresentare il proxy, mentre l'indirizzo di destinazione reale viene visualizzato.

![Immagine degli eventi di rete nella sequenza temporale del dispositivo](images/atp-proxy-investigation.png)

Altri eventi attivati dal livello di protezione di rete sono ora disponibili per visualizzare i nomi di dominio reali anche dietro un proxy.

Informazioni sull'evento:

![Immagine di un singolo evento di rete](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Ricerca di eventi di connessione tramite ricerca avanzata 
Tutti i nuovi eventi di connessione sono disponibili anche per la ricerca avanzata. Poiché questi eventi sono eventi di connessione, puoi trovarli nella tabella DeviceNetworkEvents sotto il `ConnecionSuccess` tipo di azione.

L'utilizzo di questa query semplice mostrerà tutti gli eventi pertinenti:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Immagine della query di ricerca avanzata](images/atp-proxy-investigation-ah.png)

Puoi anche filtrare gli eventi correlati alla connessione al proxy stesso. 

Utilizzare la query seguente per filtrare le connessioni al proxy:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a>Argomenti correlati
- [Applicazione della protezione di rete con Criteri di gruppo - CSP criteri](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
