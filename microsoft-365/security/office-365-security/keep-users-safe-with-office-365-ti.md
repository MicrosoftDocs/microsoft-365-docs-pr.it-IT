---
title: Mantenere la propria organizzazione sicura con le funzionalità di analisi e risposta alle minacce di Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection:
- M365-security-compliance
description: Informazioni su come le funzionalità di analisi e risposta alle minacce di Office 365 consentono all'organizzazione di rilevare intrusioni e minacce e di attenuare e recuperare rapidamente le minacce.
ms.openlocfilehash: 2f709c555974444b8f2a09d87705043d65240090
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599103"
---
# <a name="keep-your-organization-safe-with-office-365-threat-investigation-and-response-capabilities"></a>Mantenere la propria organizzazione sicura con le funzionalità di analisi e risposta alle minacce di Office 365

Si sa quale degli utenti di Office 365 sono sotto attacco o sono stati compromessi in modo peggiore? Si sa come attenuare e recuperare gli attacchi che mirano agli utenti? Lo sapevate che è possibile fare esattamente questo con le funzionalità di sicurezza già disponibili per l'utente in Office 365 E5?

Le funzionalità di [ricerca e risposta alle minacce di office 365](office-365-ti.md) sono incluse nell'abbonamento a Office 365 E5 (come parte di [Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2). Queste funzionalità hanno consentito a Microsoft di ridurre il tempo medio per la risoluzione degli incidenti di social engineering del 80% e una maggiore velocità effettiva del caso. Recentemente sono state aggiunte nuove funzionalità per migliorare il modo in cui è possibile rilevare e recuperare dalle minacce. Leggere questo articolo per scoprire in che modo le funzionalità di analisi e risposta alle minacce possono aiutare il team delle operazioni di sicurezza a essere più efficace ed efficiente.

## <a name="detect-intrusions-and-threats"></a>Rilevare intrusioni e minacce

[Esplora](threat-explorer.md) minacce (noto anche come Explorer) consente agli amministratori della sicurezza e agli analisti di identificare e comprendere le minacce attive nell'organizzazione. Anche le impostazioni di protezione più complesse possono essere eluse da configurazioni utente apparentemente innocue come gli elenchi di indirizzi attendibili per il mittente. Explorer aiuta gli amministratori globali o di sicurezza di Office 365 a determinare rapidamente se gli utenti sono stati compromessi da minacce, ad esempio malware o phishing. In questo modo la priorità è quella che gli account utente sono più a rischio per una minaccia e la risposta necessaria.

Explorer consente inoltre agli amministratori di esplorare le relazioni tra utenti e posta elettronica. Sai di una mail particolare che è stata pessima? Cercarlo per vedere cosa gli utenti hanno ricevuto la posta, quindi seguire la serie di eventi e vedere cosa hanno fatto gli utenti a sua volta.

![Schermata di Threat Explorer in Office 365, codice a colori per la famiglia di malware](../media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)

## <a name="quickly-mitigate-and-recover-from-threats"></a>Attenuazione e ripristino rapidamente dalle minacce

Dopo che gli amministratori della sicurezza hanno individuato un evento sospetto o dannoso nel tenant, possono rapidamente contenere e rispondere a tale minaccia con il **Framework Incident**. Raggruppare i messaggi indesiderati con un solo clic e rimuovere rapidamente i messaggi di posta elettronica dalle cassette postali dell'utente.

 **Update:** È stata aggiunta la possibilità di eliminare i messaggi di posta elettronica (soft o hard Delete) direttamente dal Framework Incident. In precedenza gli amministratori potevano solo spostare i messaggi nella cartella posta indesiderata di un utente, in cui gli utenti potevano recuperare l'elemento. Con le funzionalità di eliminazione appena rilasciate, è ora possibile verificare che un messaggio dannoso o indesiderato sia stato rimosso definitivamente.

![Schermata del messaggio di posta elettronica della lista di correzione degli incidenti](../media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)

## <a name="leverage-the-threat-telemetry-of-microsoft"></a>Sfruttare la telemetria di minaccia di Microsoft

Le funzionalità di ricerca e risposta alle minacce di Office 365 sono alimentate con dati del [grafico Microsoft Intelligent Security](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph/). Il grafico acquisisce il segnale di minaccia più recente da oltre 1 miliardo dispositivi Windows, 450 miliardi mensili e 400 miliardi messaggi di posta elettronica mensili in Office 365. Questo segnale di minacce senza eguali è ciò che fornisce alla massima visibilità il team delle operazioni di sicurezza per una visualizzazione più completa delle minacce che influiscono sull'organizzazione.

## <a name="next-steps"></a>Passaggi successivi

- Per ulteriori informazioni, vedere [protezione avanzata dalle minacce di Office 365](office-365-atp.md).

- Per ulteriori informazioni sulle funzionalità di ricerca e risposta alle minacce di Office 365 in questa sessione registrata, è [preceduto il attacchi cibernetici con Office 365](https://myignite.microsoft.com/videos/53723).

- Se non si dispone già di Office 365 Advanced Threat Protection piano 2, provare o acquistare subito. Vedere [Office 365 Advanced Threat Protection: piani e prezzi](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content).

- Estendere la protezione con [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
