---
title: Novità di Microsoft Secure Score
description: Descrive le nuove modifiche apportate a Microsoft Secure Score nel centro sicurezza Microsoft 365 sicurezza.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: b3f86dfbc1ae89eff61c680737061b01998a527b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933866"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novità di Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Per rendere Microsoft Secure Score un migliore rappresentante della tua posizione di sicurezza, abbiamo apportato alcune modifiche. Per informazioni sulle modifiche pianificate, vedere [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

Microsoft Secure Score è disponibile nel centro sicurezza https://security.microsoft.com/securescore [Microsoft 365 sicurezza.](overview-security-center.md)
    
## <a name="february-2021"></a>Febbraio 2021

### <a name="compatibility-with-graph-api"></a>Compatibilità con Graph API

Gli elementi consigliati di Microsoft Secure Score forniti tramite Graph API saranno visualizzati e ponderati come i consigli attualmente visualizzati nel Centro sicurezza Microsoft 365 sicurezza.

## <a name="january-2021"></a>Gennaio 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>È stata aggiunta la prima raccomandazione sulla sicurezza per Microsoft Teams

Microsoft Teams clienti potranno vedere "Impedire agli utenti anonimi di partecipare alle riunioni" come nuova azione di miglioramento in Punteggio sicuro.

## <a name="december-2020"></a>Dicembre 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Sono state aggiunte sei azioni di miglioramento relative agli account per Microsoft Defender per Endpoint:

- Impostare "Lunghezza minima password" su "14 o più caratteri"
- Imposta "Imponi cronologia password" su "24 o più password"
- Impostare "Validità massima password" su "60 o meno giorni, ma non su 0"
- Imposta "Validità minima password" su "1 o più giorni"
- Disabilitare l'account administrator predefinito
- Disabilitare l'account Guest predefinito

## <a name="november-2020"></a>Novembre 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>È stata rimossa la possibilità di creare ticket ServiceNow tramite Secure Score 

La possibilità di creare ticket ServiceNow tramite Secure Score passando a **Share > ServiceNow** non è più disponibile. Grazie per il feedback e il supporto continuo durante la determinazione dei passaggi successivi.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Sono state aggiunte tre azioni di miglioramento correlate ai servizi per Microsoft Defender per Endpoint:

- Correggere il percorso del servizio senza virgolette per Windows servizi
- Modificare il percorso eseguibile del servizio in un percorso protetto comune
- Modificare l'account di servizio per evitare la password memorizzata nella cache nel Registro di sistema di Windows

## <a name="october-2020"></a>Ottobre 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Rimuovere l'azione di miglioramento correlata a Microsoft Defender for Endpoint

- Impostare il Microsoft Defender SmartScreen Windows del contenuto Web dell'app di Store per avvisare

## <a name="august-2020"></a>Agosto 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Aggiornamento dell'azione di miglioramento per Azure Active Directory

- Abilitare i criteri per bloccare l'autenticazione legacy

## <a name="incompatibility-with-identity-secure-score"></a>Incompatibilità con Identity Secure Score

Nella recente versione di Microsoft Secure Score è stato rilasciato un modello di punteggio migliorato. Queste modifiche consentono una visualizzazione più flessibile e accurata della posizione di sicurezza. Tuttavia, questi aggiornamenti hanno reso Microsoft Secure Score temporaneamente incompatibile con Identity Secure Score.

Nel tempo, Identity Secure Score adotta il nuovo modello di punteggio. Fino ad allora, i clienti potranno vedere differenze nei punteggi riportati da Microsoft Secure Score e Identity Secure Score. Ci scusiamo per eventuali inconvenienti e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.

## <a name="updated-improvement-actions"></a>Azioni di miglioramento aggiornate

- Sono state aggiunte Azure Active Directory per il miglioramento delle prestazioni
- Aggiunta di Microsoft Defender per le azioni di miglioramento dell'identità
- Suggerimenti sulla sicurezza per Microsoft Defender for Endpoint [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Tutti i consigli sulla sicurezza rilasciati forniti da TVM sono ora disponibili

## <a name="updated-interface-and-functionality"></a>Interfaccia e funzionalità aggiornate

* Tutte le nuove metriche e le nuove visualizzazioni delle tendenze per ciso e discussioni a livello di lead
* Nuovi modi per tenere traccia e valutare il punteggio
* Monitoraggio e comprensione migliori per le regressioni dei punteggi
* Filtrare, contrassegnare, cercare e raggruppare le azioni di miglioramento
* Gestire gli obiettivi futuri usando proiezioni di punteggio e azioni pianificate
* E altro ancora!

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, contattaci pubblicando la community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Stiamo monitorando la community e forniremo assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)