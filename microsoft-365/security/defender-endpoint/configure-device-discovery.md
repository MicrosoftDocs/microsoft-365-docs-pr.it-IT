---
title: Configurare device discovery
description: Informazioni su come configurare l'individuazione dei dispositivi Microsoft 365 Defender l'individuazione di base o standard
keywords: basic, standard, configure endpoint discovery, device discovery
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7125a6953b9be46af9073b50c9268ce65dc0cd30
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339528"
---
# <a name="configure-device-discovery"></a>Configurare device discovery

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

L'individuazione può essere configurata per essere in modalità standard o di base. Usa l'opzione standard per trovare attivamente i dispositivi nella rete, in modo da garantire meglio l'individuazione degli endpoint e fornire una classificazione dei dispositivi più completa. 

Puoi personalizzare l'elenco dei dispositivi usati per eseguire l'individuazione standard. Puoi abilitare l'individuazione standard in tutti i dispositivi onboarded che supportano anche questa funzionalità (attualmente - solo dispositivi Windows 10) oppure selezionare un sottoinsieme o sottoinsiemi dei dispositivi specificando i tag del dispositivo.

> [!IMPORTANT]
> Per l'anteprima, devi prima attivare le funzionalità di anteprima in Microsoft 365 Defender.
> Puoi quindi accedere alla configurazione di individuazione dei dispositivi nel centro sicurezza Microsoft 365 sicurezza. L'elenco dei dispositivi non gestiti e i suggerimenti per la sicurezza saranno disponibili sia nel Centro sicurezza Microsoft 365 Defender che Microsoft 365, mentre i riquadri del dashboard saranno disponibili solo nel centro sicurezza Microsoft 365.

Eseguire i passaggi di configurazione seguenti nel Centro sicurezza Microsoft 365 sicurezza:

1. Passare a **Impostazioni > individuazione dei dispositivi**.
2. Seleziona la modalità di individuazione da usare nei dispositivi onboarded.
3. Se hai scelto di usare l'individuazione standard, seleziona i dispositivi da usare per il sondaggio attivo: tutti i dispositivi o in un sottoinsieme specificando i tag del dispositivo.
4. Fare clic su **Salva**.

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Escludere i dispositivi dalla ricerca attiva nell'individuazione standard

Se nella rete sono presenti dispositivi che non devono essere analizzati attivamente (ad esempio, i dispositivi usati come honeypot per un altro strumento di sicurezza), puoi anche definire un elenco di esclusioni per impedirne l'analisi. Tieni presente che i dispositivi possono ancora essere individuati usando la modalità di individuazione di base. Questi dispositivi verranno individuati passivamente, ma non verranno sondati attivamente. 

## <a name="select-networks-to-monitor"></a>Selezionare le reti da monitorare

 Microsoft Defender for Endpoint analizza una rete e determina se è una rete aziendale che deve essere monitorata o una rete non aziendale che può essere ignorata. Le reti aziendali vengono in genere scelte per il monitoraggio. Tuttavia, puoi ignorare questa decisione scegliendo di monitorare le reti non aziendali in cui vengono trovati i dispositivi onboarded. 

Puoi configurare la posizione in cui è possibile eseguire l'individuazione dei dispositivi specificando le reti da monitorare. Quando una rete viene monitorata, l'individuazione dei dispositivi può essere eseguita su di essa. 

Nella pagina Reti monitorate viene visualizzato un elenco delle reti in cui è possibile eseguire **l'individuazione dei** dispositivi. 

> [!NOTE]
> Solo le prime 50 reti (in base al numero di dispositivi associati) saranno disponibili nell'elenco di rete. 

L'elenco delle reti monitorate viene ordinato in base al numero totale di dispositivi visualizzati nella rete negli ultimi 7 giorni.

È possibile applicare un filtro per visualizzare uno dei seguenti stati di individuazione della rete:

- **Reti monitorate: reti** in cui viene eseguito l'individuazione dei dispositivi.
- **Reti ignorate:** questa rete verrà ignorata e l'individuazione dei dispositivi non verrà eseguita su di essa.
- **All** : verranno visualizzate sia le reti monitorate che le reti ignorate.

### <a name="configure-the-network-monitor-state"></a>Configurare lo stato di Network Monitor

Puoi controllare dove avviene l'individuazione dei dispositivi. Le reti monitorate sono il punto in cui verrà eseguita l'individuazione dei dispositivi e in genere sono reti aziendali. È inoltre possibile scegliere di ignorare le reti o selezionare la classificazione di individuazione iniziale dopo aver modificato uno stato.

Scegliere la classificazione di individuazione iniziale significa applicare lo stato di Network Monitor predefinito. Se si seleziona lo stato predefinito di Network Monitor creato dal sistema, le reti identificate come aziendali, verranno monitorate e quelle identificate come non aziendali verranno ignorate automaticamente.

1. Selezionare **Impostazioni > individuazione dei dispositivi**.
2. Selezionare **Reti monitorate.**
3. Visualizzare l'elenco delle reti.
4. Selezionare i tre puntini accanto al nome di rete.
5. Scegliere se si desidera monitorare, ignorare o utilizzare la classificazione di individuazione iniziale.

    > [!WARNING]
    >
    > - La scelta di monitorare una rete non identificata da Microsoft Defender for Endpoint come rete aziendale può causare l'individuazione dei dispositivi all'esterno della rete aziendale e quindi rilevare dispositivi di casa o altri dispositivi non aziendali.
    > - La scelta di ignorare una rete interromperà il monitoraggio e l'individuazione dei dispositivi in tale rete. I dispositivi già individuati non verranno rimossi dall'inventario, ma non verranno più aggiornati e i dettagli verranno conservati fino alla scadenza del periodo di conservazione dei dati di Defender for Endpoint.
    > - Prima di scegliere di monitorare le reti non aziendali, è necessario assicurarsi di disporre dell'autorizzazione necessaria.

6. Confermare che si desidera apportare la modifica. 

## <a name="explore-devices-in-the-network"></a>Esplorare i dispositivi nella rete

È possibile utilizzare la query di ricerca avanzata seguente per ottenere più contesto su ogni nome di rete descritto nell'elenco delle reti. La query elenca tutti i dispositivi onboarded connessi a una determinata rete negli ultimi 7 giorni.

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a>Vedere anche

- [Panoramica di Device discovery](device-discovery.md)
- [Domande frequenti su Individuazione dispositivi](device-discovery-faq.md)
