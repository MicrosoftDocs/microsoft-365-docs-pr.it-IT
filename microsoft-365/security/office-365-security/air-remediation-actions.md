---
title: Azioni correttive in Microsoft Defender per Office 365
keywords: AIR, autoIR, ATP, automatizzato, indagine, risposta, correzione, minacce, avanzate, minaccia, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni sulle azioni di correzione dopo l'indagine automatizzata in Microsoft Defender per Office 365.
ms.date: 02/09/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bef2fbd1e9e3d3525f9c274b5f9127acfb218396
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287126"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Azioni correttive in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="remediation-actions"></a>Azioni correttive

Le funzionalità di protezione dalle minacce in [Microsoft Defender per Office 365](office-365-atp.md) includono alcune azioni correttive. Tali azioni di correzione possono includere:

- Eliminazione temporanea di messaggi di posta elettronica o cluster
- Blocco di URL (al momento del clic)
- Disattivazione dell'inoltro della posta elettronica esterna
- Disattivazione delega

In Microsoft Defender per Office 365, le azioni di correzione non vengono eseguite automaticamente. Al contrario, le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team delle operazioni di sicurezza dell'organizzazione.

## <a name="threats-and-remediation-actions"></a>Minacce e azioni correttive

Microsoft Defender per Office 365 include azioni correttive per affrontare varie minacce. Le indagini automatizzate spesso comportano una o più azioni correttive da rivedere e approvare. In alcuni casi, un'indagine automatizzata non comporta un'azione correttiva specifica. Per analizzare ulteriormente ed eseguire le azioni appropriate, utilizzare le indicazioni riportate nella tabella seguente.

|Categoria|Minaccia/rischio|Azioni correttive|
|:---|:---|:---|
|Posta elettronica|Malware|Eliminazione recisa della posta elettronica/cluster <p> Se più di una serie di messaggi di posta elettronica in un cluster contengono malware, il cluster è considerato dannoso.|
|Posta elettronica|URL dannoso<br/>(È stato rilevato un URL dannoso [da Collegamenti sicuri).](atp-safe-links.md)|Eliminazione recisa della posta elettronica/cluster <br/>URL di blocco (verifica dell'ora del clic)<p> I messaggi di posta elettronica che contengono un URL dannoso sono considerati dannosi.|
|Posta elettronica|Phishing|Eliminazione recisa della posta elettronica/cluster <p> Se più di una serie di messaggi di posta elettronica in un cluster contengono tentativi di phishing, l'intero cluster viene considerato un tentativo di phishing.|
|Posta elettronica|Phish zapped <br>I messaggi di posta elettronica sono stati recapitati e [quindi zapped.](zero-hour-auto-purge.md)|Eliminazione recisa della posta elettronica/cluster <p>I rapporti sono disponibili per visualizzare i messaggi eliminati. [Verificare se ZAP ha spostato un messaggio e le domande frequenti.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|Posta elettronica|Messaggio di posta elettronica di phish [perso segnalato](enable-the-report-message-add-in.md) da un utente|[Indagine automatizzata attivata dal report dell'utente](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Posta elettronica|Anomalia del volume <br> Le quantità di posta elettronica recenti superano i 7-10 giorni precedenti per i criteri corrispondenti.|L'indagine automatizzata non comporta un'azione specifica in sospeso. <p>L'anomalia del volume non è una chiara minaccia, ma è semplicemente un'indicazione di volumi di posta elettronica più grandi negli ultimi giorni rispetto agli ultimi 7-10 giorni. <p>Anche se un volume elevato di messaggi di posta elettronica può indicare potenziali problemi, è necessaria una conferma in termini di verdetti dannosi o di una revisione manuale dei messaggi di posta elettronica o dei cluster. Vedere [Trovare i messaggi di posta elettronica sospetti recapitati.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|Posta elettronica|Nessuna minaccia trovata <br> Il sistema non ha trovato minacce in base a file, URL o analisi dei verdetti del cluster di posta elettronica.|L'indagine automatizzata non comporta un'azione specifica in sospeso. <p>Le minacce rilevate [e zapped](zero-hour-auto-purge.md) dopo il completamento di un'indagine non vengono riflesse nei risultati numerici di un'indagine, ma tali minacce sono visualizzabili in [Esplora minacce.](threat-explorer.md)|
|Utente|Un utente ha fatto clic su un URL dannoso <br> Un utente si è connesso a una pagina che in seguito [](atp-safe-links.md#warning-pages-from-safe-links) è stata trovata dannosa oppure ha ignorato una pagina di avviso collegamenti sicuri per accedere a una pagina dannosa.|L'indagine automatizzata non comporta un'azione specifica in sospeso. <p>Blocco di URL (al momento del clic) <p>Usare Esplora minacce per [visualizzare i dati relativi agli URL e fare clic su verdetti.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Se l'organizzazione usa [Microsoft Defender per Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/)valuta la possibilità di analizzare l'utente per determinare se il suo account è compromesso. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)|
|Utente|Un utente invia malware/phish|L'indagine automatizzata non comporta un'azione specifica in sospeso. <p> L'utente potrebbe segnalare malware/phish oppure qualcuno potrebbe effettuare [lo spoofing](anti-spoofing-protection.md) dell'utente come parte di un attacco. Usare [Esplora minacce per](threat-explorer.md) visualizzare e gestire i messaggi di posta elettronica [contenenti malware](threat-explorer-views.md#email--malware) o [malware.](threat-explorer-views.md#email--phish)|
|Utente|Inoltro della posta elettronica <br> Le regole di inoltro delle cassette postali sono configurate, che possono essere utilizzate per l'esfiltrazione dei dati.|Rimuovere la regola di inoltro <p> Utilizzare [informazioni dettagliate sul flusso di](mail-flow-insights-v2.md)posta, incluso il [rapporto](mfi-auto-forwarded-messages-report.md)Messaggi inoltrati automaticamente, per visualizzare dettagli più specifici sulla posta elettronica inoltrata.|
|Utente|Regole di delega della posta elettronica <br> L'account di un utente ha la delega impostata.|Rimuovere la regola di delega <p> Se l'organizzazione usa [Microsoft Defender per Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/)valuta la possibilità di analizzare l'utente che riceve l'autorizzazione di delega. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)|
|Utente|Esfiltrazione di dati <br> (Un utente ha violato i criteri DLP di condivisione file o di posta [elettronica.)](../../compliance/data-loss-prevention-policies.md)|L'indagine automatizzata non comporta un'azione specifica in sospeso. <p> [Visualizzare i report DLP ed eseguire un'azione.](../../compliance/view-the-dlp-reports.md)|
|Utente|Invio anomalo della posta elettronica <br> Un utente ha inviato di recente più messaggi di posta elettronica rispetto ai 7-10 giorni precedenti.|L'indagine automatizzata non comporta un'azione specifica in sospeso. <p> L'invio di una grande quantità di posta elettronica non è dannoso da solo; l'utente potrebbe aver semplicemente inviato un messaggio di posta elettronica a un gruppo di destinatari di grandi dimensioni per un evento. Per analizzare, utilizzare informazioni [dettagliate sul flusso di](mail-flow-insights-v2.md)posta, incluso il [report](mfi-mail-flow-map-report.md) mappa del flusso di posta per determinare cosa sta succedendo ed eseguire un'azione.|

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata in Microsoft Defender per Office 365](air-view-investigation-results.md)
- [Visualizzare le azioni di correzione in sospeso o completate dopo un'indagine automatizzata in Microsoft Defender per Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Articoli correlati

- [Informazioni sull'indagine automatizzata in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Informazioni sulle funzionalità in Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)
