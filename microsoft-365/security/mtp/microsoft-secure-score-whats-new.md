---
title: Novità di Microsoft Secure Score
description: Descrive le nuove modifiche apportate a Microsoft Secure Score nel Centro sicurezza Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: 039ec1c3f9b0ba233f950d11b9d58be341b28121
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930595"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novità di Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Per rendere Microsoft Secure Score un migliore rappresentante delle proprie condizioni di sicurezza, sono state apportate alcune modifiche. Per informazioni sulle modifiche pianificate, vedere Che cosa è in arrivo [in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

Microsoft Secure Score è disponibile nel Centro sicurezza https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

## <a name="january-2021"></a>Gennaio 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Aggiunta del nostro primo consiglio di sicurezza per Microsoft Teams

I clienti di Microsoft Teams potranno vedere "Impedire agli utenti anonimi di partecipare alle riunioni" come nuova azione di miglioramento in Secure Score.

## <a name="december-2020"></a>Dicembre 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Sono state aggiunte sei azioni di miglioramento relative agli account per Microsoft Defender for Endpoint (in precedenza Microsoft Defender ATP):

- Impostare "Lunghezza minima password" su "14 o più caratteri"
- Impostare "Imponi cronologia password" su "24 o più password"
- Impostare "Validità massima password" su "60 o meno giorni, ma non su 0"
- Impostare "Validità minima password" su "1 o più giorni".
- Disabilitare l'account administrator predefinito
- Disabilitare l'account Guest predefinito

## <a name="november-2020"></a>Novembre 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>È stata rimossa la possibilità di creare ticket ServiceNow tramite Secure Score 

La possibilità di creare ticket ServiceNow tramite Secure Score passando a **Share > ServiceNow** non è più disponibile. Grazie per il feedback e il supporto continuo durante la determinazione dei passaggi successivi.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Sono state aggiunte tre azioni di miglioramento relative ai servizi per Microsoft Defender for Endpoint (in precedenza Microsoft Defender ATP):

- Correggere il percorso del servizio senza virgolette per i servizi di Windows
- Modificare il percorso eseguibile del servizio in un percorso protetto comune
- Modificare l'account di servizio per evitare password memorizzate nella cache nel Registro di sistema di Windows

## <a name="october-2020"></a>Ottobre 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Rimuovere l'azione di miglioramento relativa a Microsoft Defender per Endpoint

- Impostare il controllo del contenuto Web delle app di Windows Store di Microsoft Defender SmartScreen in modo da avvisare

## <a name="august-2020"></a>Agosto 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Aggiornamento dell'azione di miglioramento per Azure Active Directory

- Abilitare i criteri per bloccare l'autenticazione legacy

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilità con Identity Secure Score e l'API Graph

Nella recente versione di Microsoft Secure Score è stato rilasciato un modello di punteggio migliorato. Queste modifiche consentono una visualizzazione più flessibile e precisa della posizione di sicurezza. Tuttavia, questi aggiornamenti hanno reso Microsoft Secure Score temporaneamente incompatibile con Identity Secure Score e l'API Graph.

Nel tempo, Identity Secure Score e l'API Graph adottano il nuovo modello di punteggio. Fino a quel momento, i clienti potranno vedere differenze nei punteggi riportati da Microsoft Secure Score, Identity Secure Score e l'API Graph. Ci scusiamo per eventuali inconvenienti e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.

## <a name="updated-improvement-actions"></a>Azioni di miglioramento aggiornate

- Sono state aggiunte azioni di miglioramento di Azure Active Directory
- Aggiunta di azioni di miglioramento di Microsoft Defender per l'identità
- Suggerimenti per la sicurezza del supporto per Microsoft Defender per Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Tutti i consigli sulla sicurezza rilasciati forniti da TVM sono ora disponibili

## <a name="updated-interface-and-functionality"></a>Interfaccia e funzionalità aggiornate

* Tutte le nuove metriche e le nuove visualizzazioni delle tendenze per il CISO e le discussioni a livello di lead
* Nuovi modi per tenere traccia e valutare il punteggio
* Migliore tracciamento e comprensione delle regressioni dei punteggi
* Filtrare, contrassegnare, cercare e raggruppare le azioni di miglioramento
* Gestire gli obiettivi futuri usando proiezioni del punteggio e azioni pianificate
* E altro ancora!

## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

In caso di problemi, contattaci pubblicando il post nella community [sicurezza, privacy & conformità.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Stiamo monitorando la community e forniremo assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Tenere traccia della cronologia di Microsoft Secure Score e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
