---
title: Azioni di correzione nell'analisi e nella risposta automatizzate di Microsoft 365
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
ms.collection: M365-security-compliance
description: Informazioni sulle azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 8dfb203cfdae179d8d88842a2d2b55aeab2e17fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634653"
---
# <a name="remediation-actions-in-microsoft-365"></a>Azioni di correzione in Microsoft 365

## <a name="remediation-actions"></a>Azioni correttive

[Le funzionalità di ricerca e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) piano 2 includono determinate azioni di correzione. Ogni volta che un'indagine automatizzata è in esecuzione o è stata completata, in genere vengono visualizzate una o più operazioni di correzione che richiedono l'approvazione da parte del team di operazioni di sicurezza per procedere. Tali azioni di correzione possono includere quanto segue:

- Eliminazione temporanea di messaggi di posta elettronica o cluster
- Blocco di URL (al momento del clic)
- Disattivazione dell'inoltro della posta elettronica esterna
- Disattiva delega

> [!NOTE]
> In Office 365 ATP, le indagini automatizzate non vengono rimediate automaticamente. Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di sicurezza dell'organizzazione.

## <a name="threats-and-remediation-actions"></a>Minacce e azioni di correzione

Nella tabella seguente sono riepilogate le minacce e le azioni correttive appropriate in Office 365 ATP. In alcuni casi, un'analisi automatizzata non determina un'azione di correzione specifica. Il team delle operazioni di sicurezza può esaminare e intraprendere le azioni appropriate come descritto nella tabella seguente.

||||
|---|---|---|
|**Categoria**|**Rischio/pericolo**|**Azione di correzione**|
|Posta elettronica|Malware| Eliminazione di messaggi di posta elettronica/cluster soft <br/><br/>Se più di un pugno di messaggi di posta elettronica in un cluster contiene malware, il cluster è considerato dannoso.|
|Posta elettronica|URL dannoso<br/>(È stato rilevato un URL dannoso da [Office 365 ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works)).|Eliminazione di messaggi di posta elettronica/cluster soft <br/><br/>Il messaggio di posta elettronica che contiene un URL dannoso è considerato dannoso.|
|Posta elettronica|Phishing| Eliminazione di messaggi di posta elettronica/cluster soft <br/><br/>Se più di un pugno di messaggi di posta elettronica in un cluster contiene tentativi di phishing, il cluster è considerato phishing.|
|Posta elettronica|Phishing zapped <br/>(I messaggi di posta elettronica sono stati recapitati e [zapping](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)).|Eliminazione di messaggi di posta elettronica/cluster soft <br/><br/>I report sono disponibili per la visualizzazione dei messaggi zapped. [Vedere se zap ha spostato un messaggio e domande frequenti](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message).|
|Posta elettronica|Mancato messaggio di posta elettronica di phishing [riportato](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) da un utente| [Analisi automatizzata attivata dal rapporto dell'utente](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Posta elettronica|Anomalia del volume <br/>Le quantità di posta elettronica recenti superano i 7-10 giorni precedenti per i criteri di corrispondenza.|L'analisi automatizzata non determina un'azione in sospeso specifica. <br/><br/>L'anomalia del volume non è una minaccia chiara, ma è solo un'indicazione dei volumi di posta elettronica più grandi nei giorni scorsi rispetto agli ultimi 7-10 giorni. Anche se questo può indicare potenziali problemi, è necessaria la conferma in termini di verdetti maligni o di una revisione manuale dei messaggi di posta elettronica/cluster. Vedere [trovare ed eliminare messaggi di posta elettronica sospetti che sono stati recapitati](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|Posta elettronica|Non sono state trovate minacce <br/>Il sistema non ha trovato minacce basate su file, URL o analisi dei verdetti del cluster di posta elettronica.|L'analisi automatizzata non determina un'azione in sospeso specifica. <br/><br/>Le minacce rilevate e [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) dopo il completamento di un'analisi non vengono riflesse nei risultati numerici di un'indagine, ma tali minacce sono visualizzabili in [Esplora minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Utente|Un utente ha fatto clic su un URL dannoso <br/>(Un utente ha individuato una pagina che è stata successivamente configurata come dannosa o un utente ha ignorato una pagina di avviso per i [collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) per accedere a una pagina dannosa).|L'analisi automatizzata non determina un'azione in sospeso specifica. <br/><br/>Utilizzare Esplora minacce per [visualizzare i dati relativi agli URL e fare clic su verdetti](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Se l'organizzazione utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/), è consigliabile esaminare [l'utente](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) per determinare se il proprio account è stato compromesso.|
|Utente|Un utente sta inviando malware/phishing|L'analisi automatizzata non determina un'azione in sospeso specifica. <br/><br/>L'utente potrebbe essere Reporting malware/phishing oppure potrebbe essere [spoofing l'utente](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) come parte di un attacco. Utilizzare [Esplora minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) per visualizzare e gestire messaggi di posta elettronica contenenti [malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) o [phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish).|
|Utente|Inoltro della posta elettronica <br/>Le regole di inoltro delle cassette postali sono configurate, che possono essere utilizzate per i dati exfiltration.|Rimuovi regola di inoltro <br/><br/>Utilizzare le informazioni sul [flusso di posta](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), incluso il [rapporto messaggi auto-inoltrati](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report), per visualizzare i dettagli più specifici relativi alla posta elettronica inoltrata.|
|Utente|Regole di delega della posta elettronica <br/>(L'account di un utente dispone di una delega configurata).|Rimuovi regola di delega <br/><br/> Se l'organizzazione utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/), valutare l'eventualità di [esaminare l'utente](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) che riceve l'autorizzazione di delega.|
|Utente|Data exfiltration<br/>(Un utente ha violato la posta elettronica o i [criteri DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)di condivisione file).|L'analisi automatizzata non determina un'azione in sospeso specifica. <br/><br/>[Visualizzare i report DLP e](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)intervenire.|
|Utente|Invio anomalo della posta elettronica <br/>(Un utente ha inviato di recente più messaggi di posta elettronica rispetto ai 7-10 giorni precedenti).|L'analisi automatizzata non determina un'azione in sospeso specifica. <br/><br/>L'invio di un sacco di messaggi di posta elettronica non è dannoso da solo; è possibile che l'utente abbia appena inviato la posta elettronica a un gruppo numeroso di destinatari per un evento. Per esaminare, utilizzare le [informazioni sul flusso di posta](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), incluso il [rapporto Mappa del flusso di posta](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) , per determinare cosa succede e agire.|
|

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata in Microsoft 365](air-view-investigation-results.md)

- [Visualizzare le azioni di correzione in sospeso o completate dopo un'analisi automatizzata in Microsoft 365](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>Articoli correlati

- [Analisi automatizzata in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Informazioni su Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)