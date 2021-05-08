---
title: Azioni di correzione in Microsoft Defender per Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automatizzato, indagine, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
description: Informazioni sulle azioni di correzione dopo un'indagine automatizzata in Microsoft Defender per Office 365.
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3be0a270bff2d75623fe5e0d6e004dd82aabf1f4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275097"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Azioni di correzione in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Azioni correttive

Le funzionalità di protezione dalle minacce in [Microsoft Defender per Office 365](defender-for-office-365.md) includono determinate azioni di correzione. Tali azioni di correzione possono includere:

- Eliminazione temporanea di messaggi di posta elettronica o cluster
- Blocco di URL (al momento del clic)
- Disattivazione dell'inoltro della posta elettronica esterna
- Disattivazione delega

In Microsoft Defender per Office 365, le azioni di correzione non vengono eseguite automaticamente. Al contrario, le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team delle operazioni di sicurezza dell'organizzazione.

## <a name="threats-and-remediation-actions"></a>Minacce e azioni correttive

Microsoft Defender per Office 365 include azioni di correzione per affrontare varie minacce. Le indagini automatizzate spesso comportano una o più azioni di correzione da rivedere e approvare. In alcuni casi, un'indagine automatizzata non comporta un'azione di correzione specifica. Per analizzare ulteriormente ed eseguire le azioni appropriate, utilizzare le indicazioni riportate nella tabella seguente.

|Categoria|Minaccia/rischio|Azioni di correzione|
|:---|:---|:---|
|Posta elettronica|Malware|Eliminazione recidiva della posta elettronica/cluster <p> Se più di una serie di messaggi di posta elettronica in un cluster contengono malware, il cluster viene considerato dannoso.|
|Posta elettronica|URL dannoso<br/>(È stato rilevato un URL dannoso [da Collegamenti sicuri).](safe-links.md)|Eliminazione recidiva della posta elettronica/cluster <br/>URL di blocco (verifica del momento del clic)<p> La posta elettronica che contiene un URL dannoso è considerata dannosa.|
|Posta elettronica|Phishing|Eliminazione recidiva della posta elettronica/cluster <p> Se più di una serie di messaggi di posta elettronica in un cluster contengono tentativi di phishing, l'intero cluster viene considerato un tentativo di phishing.|
|Posta elettronica|Phish zapped <br>(I messaggi di posta elettronica sono stati recapitati e quindi [zapped](zero-hour-auto-purge.md).)|Eliminazione recidiva della posta elettronica/cluster <p>I report sono disponibili per visualizzare i messaggi zapped. [Vedere se ZAP ha spostato un messaggio e domande frequenti](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|Posta elettronica|Messaggio di posta elettronica di phish [perso](enable-the-report-message-add-in.md) segnalato da un utente|[Indagine automatizzata attivata dal report dell'utente](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Posta elettronica|Anomalia del volume <br> Le quantità di posta elettronica recenti superano i 7-10 giorni precedenti per i criteri di corrispondenza.|L'indagine automatizzata non comporta un'azione in sospeso specifica. <p>L'anomalia del volume non è una minaccia chiara, ma è semplicemente un'indicazione di volumi di posta elettronica più grandi negli ultimi giorni rispetto agli ultimi 7-10 giorni. <p>Anche se un volume elevato di posta elettronica può indicare potenziali problemi, è necessaria una conferma in termini di verdetti dannosi o di una revisione manuale dei messaggi di posta elettronica/cluster. Vedi [Trovare messaggi di posta elettronica sospetti recapitati.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|Posta elettronica|Nessuna minaccia trovata <br> Il sistema non ha trovato minacce basate su file, URL o analisi dei verdetti del cluster di posta elettronica.|L'indagine automatizzata non comporta un'azione in sospeso specifica. <p>Le minacce trovate [e zapped](zero-hour-auto-purge.md) al termine di un'indagine non si riflettono nei risultati numerici di un'indagine, ma tali minacce sono visualizzabili in [Esplora minacce.](threat-explorer.md)|
|Utente|Un utente ha fatto clic su un URL dannoso <br> Un utente si è connesso a una pagina che in seguito [](safe-links.md#warning-pages-from-safe-links) è stata trovata dannosa oppure un utente ha ignorato una pagina di avviso collegamenti sicuri per accedere a una pagina dannosa.|L'indagine automatizzata non comporta un'azione in sospeso specifica. <p>Blocco di URL (al momento del clic) <p>Usa Esplora minacce per [visualizzare i dati sugli URL e fai clic su verdetti.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Se l'organizzazione usa [Microsoft Defender for Endpoint,](/windows/security/threat-protection/)valuta la possibilità di analizzare l'utente per determinare se il suo account è compromesso. [](/microsoft-365/security/defender-endpoint/investigate-user)|
|Utente|Un utente invia malware/phish|L'indagine automatizzata non comporta un'azione in sospeso specifica. <p> L'utente potrebbe segnalare malware/phish o qualcuno potrebbe eseguire [lo spoofing dell'utente](anti-spoofing-protection.md) come parte di un attacco. Usa [Esplora minacce per](threat-explorer.md) visualizzare e gestire i messaggi di posta elettronica [contenenti malware](threat-explorer-views.md#email--malware) o [virus](threat-explorer-views.md#email--phish).|
|Utente|Inoltro della posta elettronica <br> Le regole di inoltro delle cassette postali sono configurate, che possono essere utilizzate per l'esfiltrazione dei dati.|Rimuovere la regola di inoltro <p> Utilizzare [informazioni dettagliate sul flusso di](mail-flow-insights-v2.md)posta, incluso il [report](mfi-auto-forwarded-messages-report.md)Messaggi inoltrati automaticamente, per visualizzare dettagli più specifici sulla posta elettronica inoltrata.|
|Utente|Regole di delega della posta elettronica <br> L'account di un utente ha la delega impostata.|Rimuovere la regola di delega <p> Se l'organizzazione usa [Microsoft Defender for Endpoint,](/windows/security/threat-protection/)valuta la possibilità di analizzare l'utente che riceve l'autorizzazione di delega. [](/microsoft-365/security/defender-endpoint/investigate-user)|
|Utente|Esfiltrazione di dati <br> (Un utente ha violato i criteri DLP per la condivisione di file o di posta [elettronica](../../compliance/dlp-learn-about-dlp.md) |L'indagine automatizzata non comporta un'azione in sospeso specifica. <p> [Visualizzare i report DLP ed eseguire un'azione.](../../compliance/view-the-dlp-reports.md)|
|Utente|Invio anomalo della posta elettronica <br> Un utente ha inviato di recente più messaggi di posta elettronica rispetto ai 7-10 giorni precedenti.|L'indagine automatizzata non comporta un'azione in sospeso specifica. <p> L'invio di un volume elevato di posta elettronica non è dannoso da solo. l'utente potrebbe aver semplicemente inviato un messaggio di posta elettronica a un gruppo di destinatari di grandi dimensioni per un evento. Per analizzare, usare [informazioni dettagliate sul](mail-flow-insights-v2.md)flusso di posta, incluso il [report](mfi-mail-flow-map-report.md) mappa del flusso di posta per determinare cosa sta succedendo ed eseguire un'azione.|

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata in Microsoft Defender per Office 365](air-view-investigation-results.md)
- [Visualizzare le azioni di correzione in sospeso o completate dopo un'indagine automatizzata in Microsoft Defender per Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Articoli correlati

- [Informazioni sull'indagine automatizzata in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Informazioni sulle funzionalità in Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
