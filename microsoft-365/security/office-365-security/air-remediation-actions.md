---
title: Azioni di correzione successive all'analisi automatizzata in Microsoft Defender per Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni sulle azioni di correzione successive all'analisi automatizzata in Microsoft Defender per Office 365.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 7727d74642c7eb1798322c7c5c1845806f83ba7c
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357456"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Azioni di correzione successive all'analisi automatizzata in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Azioni correttive

[Le funzionalità di analisi e risposta automatizzate](office-365-air.md) (Air) in [Microsoft Defender per Office 365](office-365-atp.md) includono determinate azioni di correzione. Ogni volta che un'indagine automatizzata è in esecuzione o è stata completata, in genere vengono visualizzate una o più azioni di correzione che richiedono l'approvazione del team delle operazioni di sicurezza. Tali azioni di correzione possono includere quanto segue:

- Eliminazione temporanea di messaggi di posta elettronica o cluster
- Blocco di URL (al momento del clic)
- Disattivazione dell'inoltro della posta elettronica esterna
- Disattivazione delega

> [!NOTE]
> In Microsoft Defender per Office 365, le indagini automatizzate non determinano le operazioni di correzione eseguite automaticamente. Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di operazioni di sicurezza dell'organizzazione.

## <a name="threats-and-remediation-actions"></a>Minacce e azioni di correzione

Nella tabella seguente sono riepilogate le minacce e le azioni correttive appropriate in Microsoft Defender per Office 365. In alcuni casi, un'analisi automatizzata non determina un'azione di correzione specifica. Il team delle operazioni di sicurezza può esaminare e intraprendere le azioni appropriate come descritto nella tabella seguente.

****

|Categoria|Rischio/pericolo|Azione di correzione|
|---|---|---|
|Posta elettronica|Malware|Eliminazione di messaggi di posta elettronica/cluster soft <p> Se più di un pugno di messaggi di posta elettronica in un cluster contiene malware, il cluster è considerato dannoso.|
|Posta elettronica|URL dannoso<br/>(Un URL dannoso è stato rilevato da [collegamenti sicuri in Microsoft Defender per Office 365](atp-safe-links.md).|Eliminazione di messaggi di posta elettronica/cluster soft <p> Il messaggio di posta elettronica che contiene un URL dannoso è considerato dannoso.|
|Posta elettronica|Phishing|Eliminazione di messaggi di posta elettronica/cluster soft <p> Se più di un pugno di messaggi di posta elettronica in un cluster contiene tentativi di phishing, il cluster è considerato phishing.|
|Posta elettronica|Phishing zapped <br/>(I messaggi di posta elettronica sono stati recapitati e [zapping](zero-hour-auto-purge.md)).|Eliminazione di messaggi di posta elettronica/cluster soft <p> I report sono disponibili per la visualizzazione dei messaggi zapped. [Vedere se zap ha spostato un messaggio e domande frequenti](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|Posta elettronica|Mancato messaggio di posta elettronica di phishing [riportato](enable-the-report-message-add-in.md) da un utente|[Analisi automatizzata attivata dal rapporto dell'utente](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Posta elettronica|Anomalia del volume <br/>Le quantità di posta elettronica recenti superano i 7-10 giorni precedenti per i criteri di corrispondenza.|L'analisi automatizzata non determina un'azione in sospeso specifica. <p> L'anomalia del volume non è una minaccia chiara, ma è solo un'indicazione dei volumi di posta elettronica più grandi nei giorni scorsi rispetto agli ultimi 7-10 giorni. Anche se questo può indicare potenziali problemi, è necessaria la conferma in termini di verdetti maligni o di una revisione manuale dei messaggi di posta elettronica/cluster. Vedere [trovare messaggi di posta elettronica sospetti recapitati](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|Posta elettronica|Non sono state trovate minacce <br/>Il sistema non ha trovato minacce basate su file, URL o analisi dei verdetti del cluster di posta elettronica.|L'analisi automatizzata non determina un'azione in sospeso specifica. <p> Le minacce rilevate e [zapped](zero-hour-auto-purge.md) dopo il completamento di un'analisi non vengono riflesse nei risultati numerici di un'indagine, ma tali minacce sono visualizzabili in [Esplora minacce](threat-explorer.md).|
|Utente|Un utente ha fatto clic su un URL dannoso <br/>(Un utente ha individuato una pagina che è stata successivamente configurata come dannosa o un utente ha ignorato una pagina di avviso per i [collegamenti sicuri](atp-safe-links.md#warning-pages-from-safe-links) per accedere a una pagina dannosa).|L'analisi automatizzata non determina un'azione in sospeso specifica. <p> Utilizzare Esplora minacce per [visualizzare i dati relativi agli URL e fare clic su verdetti](threat-explorer.md#view-data-about-phishing-urls-and-click-verdict). <p> Se l'organizzazione utilizza [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/), valutare se [l'utente](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) deve determinare se il proprio account è stato compromesso.|
|Utente|Un utente sta inviando malware/phishing|L'analisi automatizzata non determina un'azione in sospeso specifica. <p> L'utente potrebbe essere Reporting malware/phishing oppure potrebbe essere [spoofing l'utente](anti-spoofing-protection.md) come parte di un attacco. Utilizzare [Esplora minacce](threat-explorer.md) per visualizzare e gestire messaggi di posta elettronica contenenti [malware](threat-explorer-views.md#email--malware) o [phishing](threat-explorer-views.md#email--phish).|
|Utente|Inoltro della posta elettronica <br/>Le regole di inoltro delle cassette postali sono configurate, che possono essere utilizzate per i dati exfiltration.|Rimuovi regola di inoltro <p> Utilizzare le informazioni sul [flusso di posta](mail-flow-insights-v2.md), incluso il [rapporto messaggi auto-inoltrati](mfi-auto-forwarded-messages-report.md), per visualizzare i dettagli più specifici relativi alla posta elettronica inoltrata.|
|Utente|Regole di delega della posta elettronica <br/>(L'account di un utente dispone di una delega configurata).|Rimuovi regola di delega <p> Se l'organizzazione utilizza [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/), valutare l'eventualità di esaminare [l'utente](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) che riceve l'autorizzazione di delega.|
|Utente|Esfiltrazione di dati<br/>(Un utente ha violato la posta elettronica o i [criteri DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)di condivisione file).|L'analisi automatizzata non determina un'azione in sospeso specifica. <p> [Visualizzare i report DLP e](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)intervenire.|
|Utente|Invio anomalo della posta elettronica <br/>(Un utente ha inviato di recente più messaggi di posta elettronica rispetto ai 7-10 giorni precedenti).|L'analisi automatizzata non determina un'azione in sospeso specifica. <p> L'invio di un sacco di messaggi di posta elettronica non è dannoso da solo; è possibile che l'utente abbia appena inviato la posta elettronica a un gruppo numeroso di destinatari per un evento. Per esaminare, utilizzare le [informazioni sul flusso di posta](mail-flow-insights-v2.md), incluso il [rapporto Mappa del flusso di posta](mfi-mail-flow-map-report.md) , per determinare cosa succede e agire.|
|

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata in Microsoft Defender per Office 365](air-view-investigation-results.md)

- [Visualizzare le azioni di correzione in sospeso o completate dopo un'analisi automatizzata in Microsoft Defender per Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Articoli correlati

- [Informazioni sull'analisi automatizzata in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Informazioni sulle funzionalità aggiuntive in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
