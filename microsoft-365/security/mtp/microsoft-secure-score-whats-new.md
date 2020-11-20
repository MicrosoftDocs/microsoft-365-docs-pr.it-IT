---
title: Novità di Microsoft Secure Score
description: In questo articolo vengono descritte le nuove modifiche apportate a Microsoft Secure score nel centro sicurezza Microsoft 365.
keywords: Microsoft Secure score, Secure score, Office 365 Secure score, Microsoft Security score, Microsoft 365 Security Center
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373996"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novità di Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza, sono state apportate alcune modifiche. Per informazioni sulle modifiche pianificate, vedere [What ' s Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

Microsoft Secure Score può essere trovato https://security.microsoft.com/securescore nel [Centro sicurezza Microsoft 365](overview-security-center.md).

## <a name="november-2020"></a>2020 novembre

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Sono state aggiunte 3 azioni di miglioramento correlate ai servizi per Microsoft Defender per endpoint (in precedenza Microsoft Defender ATP):

- Risolvere il percorso del servizio non quotato per i servizi Windows
- Modificare il percorso eseguibile del servizio in una posizione protetta comune
- Cambiare l'account del servizio per evitare la password memorizzata nella cache nel registro di sistema

## <a name="october-2020"></a>Ottobre 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Rimuovere l'azione di miglioramento relativa a Microsoft Defender per endpoint

- Impostare Microsoft Defender SmartScreen app di Windows Store per il controllo del contenuto Web per l'avviso

## <a name="august-2020"></a>Agosto 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Azione di miglioramento aggiornata per Azure Active Directory

- Abilitazione del criterio per bloccare l'autenticazione legacy

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilità con il Punteggio identità sicuro e l'API del grafico

Nella versione recente di Microsoft Secure Score è stato rilasciato un modello di Punteggio migliorato. Tali modifiche consentono una visualizzazione più flessibile e accurata della posizione di sicurezza. Tuttavia, questi aggiornamenti sono stati resi temporaneamente incompatibili con il Punteggio di Microsoft Secure e l'API del grafico.

Nel tempo, il Punteggio di sicurezza dell'identità e l'API del grafico adotteranno il nuovo modello di punteggio. Fino a quel momento, i clienti vedranno le differenze nei punteggi riportati da Microsoft Secure score, Identity Secure score e l'API del grafico. Vi chiediamo scusa per qualsiasi inconveniente che questo comporta, e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.

## <a name="updated-improvement-actions"></a>Azioni di miglioramento aggiornate

- Aggiunta delle azioni di miglioramento di Azure Active Directory
- Aggiunta di Microsoft Defender per azioni di miglioramento dell'identità
- Supporto di Microsoft Defender per la [minaccia](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) di endpoint & le indicazioni sulla sicurezza per la gestione delle vulnerabilità
    - Tutti i consigli di sicurezza rilasciati forniti da TVM sono ora disponibili

## <a name="updated-interface-and-functionality"></a>Interfaccia e funzionalità aggiornate

* Tutte le nuove visualizzazioni metriche e tendenze per le discussioni su OICOL e Lead Level
* Nuove modalità di monitoraggio e benchmark del Punteggio
* Migliorare il monitoraggio e la comprensione delle regressioni dei punteggi
* Filtrare, contrassegnare, ricercare e raggruppare le azioni di miglioramento
* Gestire gli obiettivi futuri utilizzando le proiezioni dei punteggi e le azioni pianificate
* E altro ancora!

## <a name="we-want-to-hear-from-you"></a>Si vuole sapere da voi

In caso di problemi, inviaci informazioni scrivendo nella community [sicurezza, Privacy & conformità](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Si sta monitorando la community e viene fornita assistenza.

## <a name="related-resources"></a>Risorse correlate

- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità in arrivo](microsoft-secure-score-whats-coming.md)
