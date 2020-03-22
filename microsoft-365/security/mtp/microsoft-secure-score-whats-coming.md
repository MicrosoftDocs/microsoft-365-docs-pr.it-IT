---
title: Che cosa viene in Microsoft Secure Score?
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, in che modo vengono calcolati i dettagli e quali amministratori della sicurezza possono aspettarsi.
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
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895442"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Che cosa viene in Microsoft Secure Score?

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro. Il Punteggio e il punteggio massimo possono variare. Tuttavia, ciò non implica una modifica della posizione di sicurezza.

Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>21 aprile 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili o che non forniscono una rappresentazione utile della posizione di sicurezza

Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.

- Eliminare/bloccare gli account non utilizzati negli ultimi 30 giorni
- Designare meno di 5 amministratori globali
- Applicare la protezione IRM ai documenti
- Applicare i criteri di prevenzione della perdita di dati

### <a name="adding-additional-control-support-in-the-preview-version"></a>Aggiunta di un ulteriore supporto di controllo nella versione di anteprima
- Non consentire agli utenti di concedere il consenso alle applicazioni non gestite (attualmente disponibili nella versione rilasciata)

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a>Supporto per altre azioni di miglioramento della sicurezza delle app di Microsoft Cloud
- Disabilitare il servizio spooler di stampa nei controller di dominio
- Modificare le deleghe Kerberos non sicure per impedire la rappresentazione
- Proteggere e gestire le password di amministratore locale con i giri Microsoft
- Ridurre il rischio del percorso laterale per le entità sensibili
- Rimuovere gli account dormienti dai gruppi sensibili
- Rimuovere gli attributi di cronologia SID non sicuri dalle entità
- Risolvere gli attributi degli account non sicuri
- Interrompere l'esposizione delle credenziali del testo
- Interrompere la comunicazione con i protocolli legacy
- Interrompere l'utilizzo di crittografia debole

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Supporto per i suggerimenti per la sicurezza di Microsoft Defender ATP Threat & vulnerabilità (TVM)
- Tutti i suggerimenti per la sicurezza rilasciati forniti da TVM saranno ora disponibili anche in Microsoft Secure Score
