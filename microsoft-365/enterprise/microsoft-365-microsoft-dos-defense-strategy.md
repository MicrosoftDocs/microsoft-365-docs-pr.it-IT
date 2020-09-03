---
title: Strategia di difesa Denial-of-Service di Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo, è possibile trovare una panoramica della strategia di difesa Microsoft per gli attacchi DoS (Denial of Service).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3fc436dfe8a63575c8bbeefeed0653c329780247
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332281"
---
# <a name="microsoft-365-denial-of-service-defense-strategy"></a>Strategia di difesa Denial-of-Service di Microsoft 365

La strategia di Microsoft per la protezione contro gli attacchi DoS (Denial of Service) basati sulla rete è univoca grazie alla scalabilità e all'impronta globale. Questa scala consente a Microsoft di utilizzare strategie e tecniche che possono corrispondere a poche organizzazioni, provider o organizzazioni di clienti. La pietra miliare della strategia DoS è la nostra presenza globale. Microsoft si impegna con provider Internet, provider di peering (pubblici e privati) e società private in tutto il mondo. Questo fornisce a Microsoft una presenza Internet significativa e consente a Microsoft di assorbire gli attacchi su un'area di grandi dimensioni.

Dato questo tipo di carattere univoco, Microsoft utilizza processi di rilevamento e attenuazione che differiscono da quelli utilizzati dalle grandi imprese. La strategia si basa su una separazione tra il rilevamento e la riduzione globale distribuita attraverso numerosi spigoli di rete. Molte aziende utilizzano soluzioni di terze parti per rilevare e mitigare gli attacchi ai server perimetrali. Come è cresciuta la capacità del perimetro di Microsoft, è emerso che il significato di qualsiasi attacco a spigoli singoli o particolari era basso. A causa di questa configurazione univoca, Microsoft ha separato i componenti di rilevamento e attenuazione. Microsoft distribuisce sistemi di rilevamento a più livelli per rilevare attacchi più vicini ai propri punti di saturazione, mantenendo la mitigazione globale sul server perimetrale. Questa strategia garantisce la possibilità di gestire più attacchi simultanei.

Una delle difese più efficienti e low cost utilizzate da Microsoft contro gli attacchi DoS è la riduzione delle superfici di attacco dei servizi. Il traffico indesiderato viene eliminato sul perimetro della rete anziché analizzarlo, elaborarlo e ripulire i dati in linea.

All'interfaccia con la rete pubblica, Microsoft utilizza dispositivi di sicurezza speciali per il firewall, la traduzione degli indirizzi di rete e le funzioni di filtro IP. Microsoft utilizza anche il routing multi-path (ECMP) globale a costo uguale. Il routing globale di ECMP è un Framework di rete per garantire che siano presenti più percorsi globali per raggiungere un servizio. Con questi percorsi multipli, gli attacchi ai servizi sono limitati all'area da cui proviene l'attacco. Le altre aree devono essere inalterate da questo attacco, in quanto gli utenti finali utilizzeranno altri percorsi per raggiungere il servizio nelle aree geografiche. Microsoft ha sviluppato anche sistemi di rilevamento e correlazione DoS interni che utilizzano dati di flusso, metriche delle prestazioni e altre informazioni. Si tratta di un servizio cloud iperscala in Microsoft Azure, che analizza i dati raccolti da vari punti su reti e servizi Microsoft. Un team di risposta agli incidenti DoS tra i carichi di lavoro identifica i ruoli e le responsabilità tra i team, i criteri per le escalation e i protocolli per l'aggancio di vari team e per la gestione degli incidenti. Queste soluzioni forniscono una protezione basata sulla rete dagli attacchi DoS.

Infine, i carichi di lavoro basati sul cloud sono configurati con soglie ottimizzate in base al protocollo e all'utilizzo della larghezza di banda necessario per proteggere in modo univoco il carico di lavoro.
