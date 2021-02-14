---
title: Microsoft 365 Network Connectivity Location Services (anteprima)
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
description: Microsoft 365 Network Connectivity Location Services (anteprima)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200782"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Microsoft 365 Network Connectivity Location Services (anteprima)

L'interfaccia di amministrazione di Microsoft 365 ora mostra informazioni dettagliate di rete e consigli sulle **prestazioni,** che sono metriche delle prestazioni in tempo reale raccolte dal tenant di Microsoft 365 e disponibili per la visualizzazione solo da parte degli utenti amministrativi nel tenant. La connettività di rete dell'organizzazione è progettata in base alla posizione dell'ufficio tramite una posizione di uscita di rete verso Internet. La connettività client di Microsoft 365 utilizza tale route e quindi attraverso Internet ai server front-door del servizio Microsoft. L'identificazione delle posizioni degli uffici è fondamentale per poter visualizzare queste informazioni dettagliate sulla rete.

## <a name="location-in-network-measurements"></a>Posizione nelle misurazioni di rete

L'amministratore di un'organizzazione può scegliere di includere la posizione nelle misurazioni di rete usate da questa funzionalità. Ciò consente l'individuazione automatica della città in cui si trova ogni ufficio. Le informazioni sulla posizione non sono precise e vengono offuscate a 300 metri e categorizzate per città. Nel momento in cui la posizione viene acquisita in un dispositivo Windows, verrà visualizzata un'icona Posizione **in** uso nella barra degli strumenti e gli amministratori potrebbero voler notificare questa operazione agli utenti. Con questa elaborazione, la posizione viene trattata come sede dell'organizzazione e non come posizione di una persona o di un dispositivo. Le informazioni dettagliate sulla rete possono essere visualizzate in queste città di uffici individuate. Se si desidera una maggiore accuratezza dei suggerimenti, un amministratore può immettere indirizzi di posizione dell'ufficio specifici e le informazioni dettagliate sulla rete verranno aggregate a tali indirizzi. Le posizioni degli uffici non possono essere aggregate più di 300 metri.

## <a name="location-in-the-microsoft-365-admin-center"></a>Posizione nell'interfaccia di amministrazione di Microsoft 365

Nell'interfaccia di amministrazione di Microsoft 365, i controlli delle mappe di Bing vengono usati per mostrare dove si trova l'ufficio dell'organizzazione e per mostrare la topologia perimetrale di rete per una posizione di ufficio selezionata. Quando un amministratore aggiunge dettagli specifici dell'indirizzo per le sedi degli uffici, Bing Maps viene usato anche per suggerire indirizzi per semplificare l'immissione dei dati.

## <a name="terms-of-use"></a>Condizioni per l'utilizzo

Qualsiasi contenuto fornito tramite Bing Maps, inclusi i geocodici, può essere usato solo all'interno del prodotto attraverso il quale viene fornito il contenuto. L'uso da parte del cliente della funzionalità dei servizi di posizione dell'interfaccia di amministrazione di Microsoft 365, con tecnologia Bing Maps, è disciplinato dalle Condizioni per l'utilizzo dell'utente finale di _Bing Maps_ disponibili all'indirizzo e dall'Informativa sulla <https://go.microsoft.com/?linkid=9710837> privacy _Microsoft_ disponibile all'indirizzo <https://go.microsoft.com/fwlink/?LinkID=248686.>

Questa funzionalità, fornita tramite Bing Maps, è supportata anche da **Here Technologies.** Il modo Bing Maps sfruttare i servizi di posizione forniti da Here Technologies è disciplinato dalle Condizioni del servizio _Here Technologies_ disponibili all'indirizzo <https://legal.here.com/en-gb/terms> .

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Informazioni dettagliate sulle prestazioni di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-insights.md)

[Valutazione della rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-score.md)

[Test della connettività di Microsoft 365 nell'interfaccia di amministrazione di M365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)
