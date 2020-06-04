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
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545935"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Che cosa viene in Microsoft Secure Score?

Per rendere [Microsoft Secure Score](microsoft-secure-score-new.md) un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro. Il Punteggio e il punteggio massimo possono variare. Tuttavia, ciò non implica una modifica della posizione di sicurezza.

Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score-new.md#whats-new)

## <a name="june-2020"></a>2020 giugno

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Rimuovi azione di miglioramento per Microsoft Defender Advanced Threat Protection

* Attivazione delle regole di riduzione della superficie di attacco

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Aggiungere azioni di miglioramento per Microsoft Defender Advanced Threat Protection

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
* Bloccare la sottrazione di credenziali dal sottosistema di autorità di sicurezza locale di Windows (Lsass. exe)
* Bloccare le chiamate API Win32 dalle macro di Office
