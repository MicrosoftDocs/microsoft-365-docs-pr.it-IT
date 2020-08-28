---
title: Novità di Microsoft Secure Score
description: In questo articolo vengono descritte le nuove modifiche apportate a Microsoft Secure score nel centro sicurezza Microsoft 365.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
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
ms.openlocfilehash: 8b0fda2d8a0b7d9cb6b2c6a4cca2e8e34a876fec
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289424"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novità di Microsoft Secure Score

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza, sono state apportate alcune modifiche. Per informazioni sulle modifiche pianificate, vedere [What ' s Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

## <a name="august-2020"></a>Agosto 2020

### <a name="update-improvement-action-for-azure-active-directory"></a>Azione di miglioramento dell'aggiornamento per Azure Active Directory

- Abilitazione del criterio per bloccare l'autenticazione legacy

## <a name="july-2020"></a>Luglio 2020

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Aggiunta di azioni di miglioramento per la protezione avanzata dalle minacce di Azure

- Percorsi di spostamento laterali rischiosi
- Attributi dell'account non sicuri
- Abilitare le funzionalità di sicurezza per le relazioni di trust di Active Directory
- Rimuovere gli attributi di cronologia SID non sicuri dalle entità

## <a name="june-2020"></a>Giugno 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Azione di miglioramento rimossa per Microsoft Defender Advanced Threat Protection

* Attivazione delle regole di riduzione della superficie di attacco

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Sono state aggiunte azioni di miglioramento per Microsoft Defender Advanced Threat Protection

* Impedire a Adobe Reader di creare processi figlio
* Utilizzare Advanced Protection against ransomware
* Blocca tutte le applicazioni di Office dalla creazione dei processi figlio
* Bloccare le applicazioni di Office dalla creazione di contenuto eseguibile
* Blocca JavaScript o VBScript dall'avvio del contenuto eseguibile scaricato
* Bloccare l'esecuzione di script potenzialmente offuscati
* Bloccare i contenuti eseguibili dal client di posta elettronica e webmail
* Bloccare l'applicazione di comunicazione di Office dalla creazione dei processi figlio
* Blocca processi non attendibili e non firmati che vengono eseguiti da USB
* Blocca la persistenza tramite la sottoscrizione di eventi WMI
* Blocca le applicazioni di Office dall'inserimento di codice in altri processi
* Bloccare l'esecuzione di file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile
* Bloccare le creazioni dei processi originati da comandi di PSExec e WMI
* Bloccare la sottrazione di credenziali dal sottosistema di autorità di sicurezza locale di Windows (lsass.exe)
* Bloccare le chiamate API Win32 dalle macro di Office

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilità con il Punteggio identità sicuro e l'API del grafico

Nella versione recente di Microsoft Secure Score è stato rilasciato un modello di Punteggio migliorato. Tali modifiche consentono una visualizzazione più flessibile e accurata della posizione di sicurezza. Tuttavia, questi aggiornamenti sono stati resi temporaneamente incompatibili con il Punteggio di Microsoft Secure e l'API del grafico.

Nel tempo, il Punteggio di sicurezza dell'identità e l'API del grafico adotteranno il nuovo modello di punteggio. Fino a quel momento, i clienti vedranno le differenze nei punteggi riportati da Microsoft Secure score, Identity Secure score e l'API del grafico. Vi chiediamo scusa per qualsiasi inconveniente che questo comporta, e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.

## <a name="updated-improvement-actions"></a>Azioni di miglioramento aggiornate

- Aggiunta delle azioni di miglioramento di Azure Active Directory
- Aggiunta delle azioni di miglioramento di Azure Advanced Threat Protection
- Supporto per le indicazioni sulla sicurezza del trifosfato di adenosina di Microsoft Defender [& vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
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
