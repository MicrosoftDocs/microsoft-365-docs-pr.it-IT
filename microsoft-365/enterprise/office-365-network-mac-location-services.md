---
title: Microsoft 365 Servizi percorso connettività di rete
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Servizi percorso connettività di rete
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470449"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 Servizi percorso connettività di rete

L Microsoft 365 admin center mostra ora Informazioni dettagliate di rete e consigli sulle **prestazioni,** che sono metriche delle prestazioni live raccolte dal tenant Microsoft 365 locale. Queste metriche possono essere visualizzate solo dagli utenti amministrativi nel tenant. La connettività di rete dell'organizzazione è progettata in base alla posizione dell'ufficio tramite una posizione di uscita di rete verso Internet. Microsoft 365 connettività client utilizza tale route e quindi attraverso Internet ai server front-door del servizio Microsoft. L'identificazione delle posizioni degli uffici è fondamentale per poter visualizzare queste informazioni dettagliate sulla rete.

## <a name="location-in-network-measurements"></a>Posizione nelle misurazioni di rete

L'amministratore di un'organizzazione può acconsentire esplicitamente alla posizione da includere nelle misurazioni di rete utilizzate da questa funzionalità. In questo modo viene abilitata l'individuazione automatica della città in cui si trova ogni ufficio. Le informazioni sulla posizione non sono precise e vengono offuscate a 300 metri e classificate per città. Nel momento in cui la posizione viene acquisita in un dispositivo Windows, il dispositivo mostrerà un'icona Posizione **in** uso nella barra degli strumenti. Gli amministratori potrebbero voler comunicare agli utenti l'aspetto di questa icona. Con questa elaborazione, la posizione viene trattata come sede dell'organizzazione e non come posizione di una persona o di un dispositivo. Le informazioni dettagliate sulla rete possono essere mostrate in queste città di posizione degli uffici individuate. Se si desidera una maggiore accuratezza nei suggerimenti, è possibile immettere indirizzi di sede specifici. Le informazioni dettagliate sulla rete verranno invece aggregate in tali posizioni. Office le posizioni non possono essere aggregate più di 300 metri.

## <a name="location-in-the-microsoft-365-admin-center"></a>Posizione nell'Microsoft 365 admin center

Nell'Microsoft 365 admin center, i controlli Bing mappa vengono usati per mostrare dove si trova l'ufficio dell'organizzazione. I controlli mostrano anche la topologia perimetrale di rete per una posizione di ufficio selezionata. Quando un amministratore aggiunge dettagli specifici dell'indirizzo per le posizioni dell'ufficio, Bing Maps viene usato anche per suggerire gli indirizzi per semplificare l'immissione dei dati.

## <a name="terms-of-use"></a>Condizioni per l'utilizzo

Qualsiasi contenuto fornito tramite Bing Maps, inclusi i geocodici, può essere utilizzato solo all'interno del prodotto tramite il quale viene fornito il contenuto. L'utilizzo da parte del cliente della funzionalità dei servizi di posizione dell'interfaccia di amministrazione di Microsoft 365, basata su Bing Maps, è disciplinato dalle Condizioni per l'utilizzo di _Bing Maps End-User_ disponibili all'indirizzo e dall'Informativa <https://go.microsoft.com/?linkid=9710837> sulla privacy [Microsoft.](https://go.microsoft.com/fwlink/?LinkID=248686)

Questa funzionalità, fornita tramite Bing Maps, è supportata anche da **TomTom.** Ulteriori informazioni sui prodotti e i servizi di TomTom sono disponibili all'indirizzo [https://www.tomtom.com/legal](https://www.tomtom.com/legal) .

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'Microsoft 365 admin center (anteprima)](office-365-network-mac-perf-overview.md)

[Microsoft 365 informazioni dettagliate sulle prestazioni di rete (anteprima)](office-365-network-mac-perf-insights.md)

[Microsoft 365 di rete (anteprima)](office-365-network-mac-perf-score.md)

[Microsoft 365 di connettività nell'Microsoft 365 di amministrazione (anteprima)](office-365-network-mac-perf-onboarding-tool.md)
