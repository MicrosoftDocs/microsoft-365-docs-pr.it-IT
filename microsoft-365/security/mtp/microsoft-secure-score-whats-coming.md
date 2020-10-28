---
title: Cosa viene a Microsoft Secure Score
description: In questo articolo vengono descritte le nuove modifiche apportate a Microsoft Secure score nel centro sicurezza Microsoft 365.
keywords: Microsoft Secure score, Secure score, Office 365 Secure score, Microsoft Security score, Microsoft 365 Security Center, azioni di miglioramento
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779249"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>Cosa viene a Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Sono state apportate alcune modifiche nel prossimo futuro per rendere [Microsoft Secure Score](microsoft-secure-score.md) un migliore rappresentante della propria posizione di sicurezza e migliorare l'usabilità. Il Punteggio e il punteggio massimo possibile possono variare.

## <a name="proposed-changes"></a>Modifiche proposte

### <a name="november-2020"></a>2020 novembre

La rimozione della possibilità di creare i ticket di ServiceNow tramite il Punteggio sicuro è in grado di **condividere > ServiceNow** .

- Il periodo di anteprima per il connettore ServiceNow termina. Questa funzionalità non sarà più disponibile entro la fine di 2020. La ringrazio per i commenti e il supporto continuo, mentre si determinano i passaggi successivi.

Aggiunta di 18 azioni di miglioramento relative a Microsoft Defender per endpoint (in precedenza Microsoft Defender ATP):

Suggerimenti correlati alla riduzione della superficie di attacco (ASR):
- Bloccare i contenuti eseguibili dal client di posta elettronica e webmail
- Blocca tutte le applicazioni di Office dalla creazione dei processi figlio
- Bloccare le applicazioni di Office dalla creazione di contenuto eseguibile
- Blocca le applicazioni di Office dall'inserimento di codice in altri processi
- Blocca JavaScript o VBScript dall'avvio del contenuto eseguibile scaricato
- Bloccare l'esecuzione di script potenzialmente offuscati
- Bloccare le chiamate API Win32 dalle macro di Office
- Bloccare l'esecuzione di file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile
- Utilizzare Advanced Protection against ransomware
- Bloccare la sottrazione di credenziali dal sottosistema di autorità di sicurezza locale di Windows (lsass.exe)
- Bloccare le creazioni dei processi originati da comandi di PSExec e WMI
- Blocca processi non attendibili e non firmati che vengono eseguiti da USB
- Bloccare l'applicazione di comunicazione di Office dalla creazione dei processi figlio
- Impedire a Adobe Reader di creare processi figlio
- Blocca la persistenza tramite la sottoscrizione di eventi WMI

Suggerimenti relativi ai servizi:
- Risolvere il percorso del servizio non quotato per i servizi Windows
- Modificare il percorso eseguibile del servizio in una posizione protetta comune
- Cambiare l'account del servizio per evitare la password memorizzata nella cache nel registro di sistema

## <a name="related-resources"></a>Risorse correlate

- [Panoramica del Punteggio Microsoft Secure](microsoft-secure-score.md)
- [Valutazione del profilo di sicurezza](microsoft-secure-score-improvement-actions.md)
- [Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi](microsoft-secure-score-history-metrics-trends.md)
- [Novità](microsoft-secure-score-whats-new.md)
