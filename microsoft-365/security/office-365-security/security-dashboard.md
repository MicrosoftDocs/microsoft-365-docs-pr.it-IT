---
title: Panoramica del dashboard di sicurezza
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: Utilizzare il nuovo dashboard di sicurezza per esaminare lo stato di protezione dalle minacce di Office 365 e visualizzare e agire sugli avvisi di sicurezza.
ms.openlocfilehash: 8f86aa654c79bac2409d64b43d0cf7bb563c1412
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083965"
---
# <a name="security-dashboard"></a>Dashboard di sicurezza

## <a name="overview"></a>Panoramica

Il [centro &amp; sicurezza e conformità](../../compliance/go-to-the-securitycompliance-center.md) consente all'organizzazione di gestire la protezione dei dati e la conformità. Se si dispone delle autorizzazioni necessarie, il dashboard di sicurezza consente di esaminare lo stato della protezione dalle minacce, nonché di visualizzare e agire sugli avvisi di sicurezza. 
  
Guarda il video per ottenere una panoramica e quindi leggi questo articolo per ulteriori informazioni.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]
  
A seconda di come è inclusa la sottoscrizione di Office 365 dell'organizzazione, il dashboard di sicurezza include diversi widget, come riepilogo della gestione delle minacce, stato di protezione delle minacce, rilevamenti di minacce globali settimanali, malware e altro ancora, come descritto nell' sezioni seguenti.
  
Per visualizzare il dashboard di sicurezza, nel [centro &amp; sicurezza e conformità di Office 365](../../compliance/go-to-the-securitycompliance-center.md)accedere a **Threat Management** \> **Dashboard**.
  
> [!NOTE]
> Per visualizzare il dashboard di sicurezza, è necessario essere un amministratore globale di Office 365, un amministratore della sicurezza o un lettore di sicurezza. Alcuni widget richiedono ulteriori autorizzazioni per la visualizzazione. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="threat-management-summary"></a>Riepilogo di gestione delle minacce

Il widget di riepilogo per la gestione delle minacce fornisce una breve panoramica sul modo in cui l'organizzazione è stata protetta dalle minacce negli ultimi sette (7) giorni.

![Dashboard di sicurezza-widget Riepilogo di gestione delle minacce](../media/SecDash-ThreatMgmtSummary.png)

Le informazioni visualizzate nel Riepilogo di gestione delle minacce dipendono dal tipo di sottoscrizione incluso. Nella tabella seguente vengono descritte le informazioni incluse in Office 365 E3 e Office 365 E5.


|Office 365 E3  |Office 365 E5  |
|---------|---------|
|Messaggi di malware bloccati<br/>Messaggi di phishing bloccati<br>Messaggi segnalati dagli utenti<br><br><br><br> |Messaggi di malware bloccati<br>Messaggi di phishing bloccati<br>Messaggi segnalati dagli utenti<br>Malware zero-day bloccato<br>Messaggi di phishing avanzati rilevati<br>URL dannosi bloccati |

Per visualizzare o accedere al widget di riepilogo di gestione delle minacce, è necessario disporre delle autorizzazioni per visualizzare i report di Advanced Threat Protection. Per ulteriori informazioni, vedere [quali autorizzazioni sono necessarie per visualizzare i rapporti ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="threat-protection-status"></a>Stato di protezione dalle minacce

Il widget dello stato di protezione delle minacce Mostra l'efficacia della protezione dalle minacce con una visualizzazione dettagliata di phishing e malware. 

![Widget sullo stato della protezione dalle minacce](../media/tpswidget.png)

I dettagli dipendono dal fatto che la sottoscrizione di Office 365 includa [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) con o senza [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).


|Se l'abbonamento è incluso in... |Vedrai questi dettagli |
|---------|---------|
|EOP ma non Office 365 ATP     |Messaggi di posta elettronica dannosi che sono stati rilevati e bloccati da EOP<br> Vedere [Threat Protection status report (EOP)](../../compliance/view-email-security-reports.md#threat-protection-status-report).| |
|Office 365 ATP |Contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da EOP e Office 365 ATP<br>Numero aggregato di messaggi di posta elettronica univoci con contenuti dannosi bloccati dal motore antimalware, da [zero-hour auto Purge](zero-hour-auto-purge.md)e dalle funzionalità ATP (inclusi [collegamenti sicuri](atp-safe-links.md), [allegati sicuri](atp-safe-attachments.md)e [anti-phishing ATP](atp-anti-phishing.md)).<br>Vedere [rapporto sullo stato della protezione dalle minacce (ATP)](view-reports-for-atp.md#threat-protection-status-report). | 

Per visualizzare o accedere al widget dello stato di protezione dalle minacce, è necessario disporre delle autorizzazioni per visualizzare i report di Advanced Threat Protection. Per ulteriori informazioni, vedere [quali autorizzazioni sono necessarie per visualizzare i rapporti ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="global-weekly-threat-detections"></a>Rilevamenti di minacce globali settimanali
 
Il widget globale settimanale per i rilevamenti di minacce indica quante minacce sono state rilevate nei messaggi di posta elettronica negli ultimi sette (7) giorni.

![Widget globale settimanale per i rilevamenti di minacce](../media/globalweeklythreatdetections.png)

Le metriche vengono calcolate come descritto nella tabella seguente:

|Metrica  |Modalità di calcolo  |
|---------|---------|
|Messaggi analizzati |Numero di messaggi di posta elettronica analizzati moltiplicati per il numero di destinatari |
|Minacce interrotte  |Numero di messaggi di posta elettronica identificati come contenenti malware moltiplicato per il numero di destinatari |
|Bloccato da [ATP](office-365-atp.md) |Numero di messaggi di posta elettronica bloccati da ATP moltiplicati per il numero di destinatari |
|Rimossi dopo il recapito |Numero di messaggi rimossi da [zero-hour auto Purge](zero-hour-auto-purge.md) moltiplicato per il numero di destinatari |

## <a name="malware"></a>Malware

I widget malware mostrano informazioni sui trend di malware e sui tipi di famiglia di malware negli ultimi sette (7) giorni.

![Tendenze di malware e tipi di famiglia](../media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>Approfondimenti

Insights non solo i problemi principali che è necessario esaminare, ma anche suggerimenti e azioni da prendere in considerazione. 

![Intuizioni intelligenti](../media/smartinsights.png)

Ad esempio, si potrebbe vedere che i messaggi di posta elettronica di phishing vengono recapitati perché alcuni utenti hanno disabilitato le opzioni di posta indesiderata. Per ulteriori informazioni sul funzionamento delle intuizioni, vedere [Reports and Insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md).
  
## <a name="threat-investigation-and-response"></a>Analisi e risposta alle minacce

Se l'abbonamento dell'organizzazione include [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), il dashboard di sicurezza ha una sezione che include l'analisi avanzata delle minacce e gli strumenti di risposta. Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questa sezione per comprendere le campagne emergenti, esaminare le minacce e gestire gli incidenti. 
  
![Threat Intelligence aiuta a comprendere gli attacchi indirizzati alla propria organizzazione](../media/threatintelwidget.png)
  
  
## <a name="trends"></a>Tendenze

Nella parte inferiore del dashboard di sicurezza è presente una sezione **Trends** , in cui vengono riepilogate le tendenze del flusso di posta elettronica per l'organizzazione. I rapporti forniscono informazioni sui messaggi di posta elettronica categorizzati come posta indesiderata, malware, tentativi di phishing e una buona posta elettronica. Fare clic su un riquadro per visualizzare informazioni più dettagliate nel report. 
  
![La sezione Trends riepiloga le tendenze del flusso di posta elettronica per l'organizzazione](../media/trends.png)
  
Inoltre, se la sottoscrizione di Office 365 dell'organizzazione include [office 365 Advanced Threat Protection Plan 2](office-365-ti.md), in questa sezione è disponibile anche un rapporto **avvisi di gestione delle minacce di recente** che consente al team di sicurezza di visualizzare e intraprendere un'azione avvisi di sicurezza ad alta priorità. 

Per visualizzare o accedere al widget messaggi di posta elettronica inviati e ricevuti, è necessario disporre delle autorizzazioni per visualizzare i report di Advanced Threat Protection. Per ulteriori informazioni, vedere [quali autorizzazioni sono necessarie per visualizzare i rapporti ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

Per visualizzare o accedere al widget recenti avvisi di gestione delle minacce, è necessario disporre delle autorizzazioni per visualizzare gli avvisi. Per ulteriori informazioni, vedere le [autorizzazioni RBAC necessarie per visualizzare gli avvisi](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).
  
## <a name="related-topics"></a>Argomenti correlati

[Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità](../../compliance/view-email-security-reports.md)
  
[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  
[Protezione avanzata dalle minacce di Office 365](office-365-atp.md)
  
[Indagine e risposta alle minacce di Office 365](office-365-ti.md)
  

