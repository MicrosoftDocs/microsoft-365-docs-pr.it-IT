---
title: Preparare la posizione di sicurezza per il primo incidente
description: Configurare la posizione Microsoft 365 sicurezza del tenant per il primo incidente in Microsoft 365 Defender.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 76bead8fd855e4119db6297d2ab1a3d08d64a48c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297165"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Preparare la posizione di sicurezza per il primo incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

La preparazione per la gestione degli eventi imprevisti prevede la configurazione di una protezione sufficiente della rete di un'organizzazione da diversi tipi di incidenti di sicurezza. Per ridurre il rischio di incidenti di sicurezza, il National Institute of Standards and Technology (NIST) consiglia diverse procedure di sicurezza, tra cui valutazioni dei rischi, protezione avanzata della sicurezza dell'host, configurazione sicura delle reti e prevenzione del malware. 

Microsoft 365 Defender può aiutare a risolvere diversi aspetti della prevenzione degli incidenti: 

- Implementazione di un framework [zero trust](https://docs.microsoft.com/security/zero-trust/)
- Determinare la posizione di sicurezza assegnando un punteggio con [Microsoft Secure Score](microsoft-secure-score.md)
- Prevenzione delle minacce tramite valutazioni delle vulnerabilità in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Informazioni sulle minacce alla sicurezza più recenti in modo da poterle preparare

## <a name="step-1-implement-zero-trust"></a>Passaggio 1. Implementare zero trust

[Zero Trust](https://docs.microsoft.com/security/zero-trust/) è una filosofia di sicurezza integrata e una strategia end-to-end che considera la natura complessa di qualsiasi ambiente moderno, inclusa la forza lavoro mobile e gli utenti, i dispositivi, le applicazioni e i dati, ovunque si trovino. Fornendo un singolo riquadro di vetro per gestire tutti i rilevamenti degli endpoint in modo coerente, Microsoft 365 [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) Defender può rendere più semplice per il team delle operazioni di sicurezza implementare i principi guida di Zero Trust. 

I componenti di Microsoft 365 Defender possono visualizzare le violazioni delle regole implementate per stabilire criteri di accesso condizionale per Zero Trust integrando i dati di Microsoft Defender for Endpoint (MDE) o di altri fornitori di sicurezza per dispositivi mobili come origine di informazioni per i criteri di conformità dei dispositivi e l'implementazione di criteri di accesso condizionale basati su dispositivo. 

Il rischio del dispositivo influisce direttamente sulle risorse accessibili dall'utente del dispositivo. Il rifiuto dell'accesso alle risorse in base a determinati criteri è il tema principale di Zero Trust e Microsoft 365 Defender fornisce le informazioni necessarie per determinare i criteri del livello di attendibilità. Ad esempio, Microsoft 365 Defender può fornire il livello di versione software di un dispositivo tramite la pagina Gestione minacce e vulnerabilità, mentre i criteri di accesso condizionale limitano i dispositivi con versioni obsolete o vulnerabili.

L'automazione è una parte fondamentale dell'implementazione e della gestione di un ambiente zero trust, riducendo al contempo il numero di avvisi che potrebbero causare eventi di risposta a eventi imprevisti( IR). I componenti di Microsoft 365 Defender possono essere automatizzati, ad esempio le azioni di correzione [(note](m365d-autoir.md) come indagini per un incidente nel centro sicurezza Microsoft 365), le azioni di notifica e persino la creazione di ticket di supporto, ad esempio in [ServiceNow.](https://microsoft.service-now.com/sp/)

## <a name="step-2-determine-your-organizations-security-posture"></a>Passaggio 2. Determinare la posizione di sicurezza dell'organizzazione

Successivamente, le organizzazioni possono usare [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender per determinare la posizione di sicurezza corrente e prendere in considerazione suggerimenti su come migliorarlo. Più alto è il punteggio, maggiori sono i suggerimenti per la sicurezza e le azioni di miglioramento adottate dall'organizzazione. I consigli relativi al punteggio sicuro possono essere presi in prodotti diversi e consentire alle organizzazioni di aumentare ancora di più i propri punteggi. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Esempio di Microsoft Secure Score nel Centro sicurezza Microsoft":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Passaggio 3. Valutare l'esposizione alle vulnerabilità dell'organizzazione

La prevenzione degli incidenti può contribuire a semplificare gli sforzi delle operazioni di sicurezza per concentrarsi sugli incidenti di sicurezza critici e importanti in corso. Le vulnerabilità software sono spesso un punto di ingresso prevenibile per gli attacchi che possono portare al furto di dati, alla perdita di dati o all'interruzione delle operazioni aziendali. Se non sono in corso attacchi, le operazioni di sicurezza [](../defender-endpoint/tvm-exposure-score.md) devono cercare di raggiungere e mantenere un livello accettabile di esposizione alle vulnerabilità nell'organizzazione.

Per controllare l'avanzamento dell'applicazione di patch al software, visita la pagina [Gestione](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) delle minacce e delle vulnerabilità in Defender for Endpoint, a cui puoi accedere da Microsoft 365 Defender tramite la **scheda Altre** risorse.

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Esempio della pagina Minacce e vulnerabilità nel Centro sicurezza Microsoft"::: 
 
## <a name="4-understand-emerging-threats"></a>4. Comprendere le minacce emergenti

Usa [l'analisi](threat-analytics.md) delle minacce Microsoft 365 centro sicurezza per mantenerti aggiornati con l'attuale panorama delle minacce alla sicurezza. I ricercatori esperti della sicurezza Microsoft creano report che descrivono in dettaglio le minacce informatiche più recenti, in modo da poter comprendere in che modo potrebbero influire sulla sottoscrizione, i dispositivi e gli utenti di Microsoft 365 utenti. Questi report possono includere:

- Attori delle minacce attive e le loro campagne
- Tecniche di attacco popolari e nuove
- Vulnerabilità critiche
- Superfici di attacco comuni
- Malware diffuso

Puoi implementare i consigli di una minaccia emergente per rafforzare la posizione di sicurezza e ridurre al minimo la superficie di attacco.

Prendere tempo nella pianificazione per controllare regolarmente la sezione [Threat Analytics](threat-analytics.md) del centro sicurezza Microsoft 365 sicurezza.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 1: informazioni su come analizzare e analizzare gli eventi imprevisti](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

Informazioni su come [analizzare e analizzare gli eventi imprevisti.](first-incident-analyze.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
