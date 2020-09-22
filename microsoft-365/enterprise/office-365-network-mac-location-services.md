---
title: Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)
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
description: Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200782"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)

L'interfaccia di amministrazione di Microsoft 365 ora Mostra **informazioni dettagliate sulla rete e sulle prestazioni**, che sono raccolte dal tenant di Microsoft 365 e disponibili per la visualizzazione solo da parte di utenti amministrativi del tenant. La connettività di rete organizzativa è progettata per ogni percorso di Office tramite una posizione di uscita di rete su Internet. La connettività client Microsoft 365 utilizza tale route e quindi su Internet per i server front door di Microsoft Service. Identificare le posizioni di Office è fondamentale per poter mostrare queste informazioni sulla rete.

## <a name="location-in-network-measurements"></a>Posizione in misure di rete

L'amministratore di un'organizzazione può optare per la posizione per l'inclusione nelle misure di rete utilizzate da questa funzionalità. In questo modo, viene abilitata l'individuazione automatica della città in cui si trova ogni ufficio. Le informazioni sulla posizione non sono precise e sono offuscate a 300m e categorizzate in base alla città. Al momento in cui la posizione viene acquisita su un dispositivo Windows, viene visualizzata un'icona di **posizione in uso** nel vassoio degli strumenti e gli amministratori possono decidere di notificare gli utenti. Con questa elaborazione, la posizione viene trattata come la posizione dell'ufficio dell'organizzazione e non la posizione di un utente o di un dispositivo. È possibile visualizzare le informazioni di rete in queste città ubicate nell'ufficio individuate. Se si desidera una maggiore accuratezza dei suggerimenti, un amministratore può immettere indirizzi di posizione specifici di Office e le informazioni sulla rete verranno aggregate a quelle. I percorsi di Office non possono essere aggregati più strettamente di 300 metri.

## <a name="location-in-the-microsoft-365-admin-center"></a>Posizione nell'interfaccia di amministrazione di Microsoft 365

Nell'interfaccia di amministrazione di Microsoft 365, i controlli Bing Map vengono utilizzati per mostrare dove sono ubicate le posizioni dell'organizzazione e per visualizzare la topologia perimetrale di rete per una posizione di Office selezionata. Quando un amministratore aggiunge informazioni specifiche sull'indirizzo per i percorsi di Office, Bing Maps viene utilizzato anche per suggerire gli indirizzi per semplificare l'immissione dei dati.

## <a name="terms-of-use"></a>Condizioni per l'utilizzo

Qualsiasi contenuto fornito tramite Bing Maps, inclusi i geocodici, può essere utilizzato solo all'interno del prodotto tramite il quale viene fornito il contenuto. L'utilizzo da parte del cliente della caratteristica dei servizi di interfaccia di amministrazione di Microsoft 365, Powered by Bing Maps, è regolato dalle _condizioni di utilizzo dell'utente finale di Bing Maps_ disponibili all'indirizzo <https://go.microsoft.com/?linkid=9710837> e dall' _informativa sulla privacy di Microsoft_ disponibile all'indirizzo <https://go.microsoft.com/fwlink/?LinkID=248686.>

Questa funzionalità, fornita tramite Bing Maps, è supportata anche da **qui Technologies**. Il modo in cui Bing Maps utilizza i servizi di localizzazione forniti da qui Technologies è disciplinato dai _termini del servizio qui Technologies_ disponibili all'indirizzo <https://legal.here.com/en-gb/terms> .

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Informazioni sulle prestazioni di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-insights.md)

[Valutazione della rete Microsoft 365 (Preview)](office-365-network-mac-perf-score.md)

[Test di connettività Microsoft 365 nell'interfaccia di amministrazione di M365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)
