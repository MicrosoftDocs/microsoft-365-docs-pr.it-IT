---
title: Panoramica del dashboard di sicurezza
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Usa il nuovo dashboard di sicurezza per esaminare Office 365 stato di Threat Protection e visualizzare e agire sugli avvisi di sicurezza.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1504c84f0657dd049b63908d56c4ec6cca4871de
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055163"
---
# <a name="security-dashboard-in-the-security--compliance-center"></a>Dashboard di sicurezza nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Funzioni di base e come aprire il dashboard di sicurezza

Il Centro sicurezza & conformità consente <https://protection.office.com> all'organizzazione di gestire la protezione e la conformità dei dati. Presupponendo di disporre delle autorizzazioni necessarie, il dashboard di sicurezza consente di esaminare lo stato di Threat Protection, nonché di visualizzare e agire sugli avvisi di sicurezza.

Guarda il video per ottenere una panoramica e quindi leggi questo articolo per altre informazioni.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

A seconda di ciò che include la sottoscrizione dell'organizzazione, il dashboard di sicurezza include diversi widget, ad esempio Riepilogo gestione delle minacce, Stato di Protezione dalle minacce, Rilevamenti settimanali globali delle minacce, Malware e altro ancora, come descritto nelle sezioni seguenti.

Per visualizzare il dashboard di sicurezza nel Centro sicurezza & conformità, passare a Dashboard di **gestione delle** \> **minacce**. Per passare direttamente al dashboard di sicurezza, utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .

> [!NOTE]
> Per visualizzare il dashboard di sicurezza, è necessario essere un amministratore globale, un amministratore della sicurezza o un lettore di sicurezza. Alcuni widget richiedono autorizzazioni aggiuntive per la visualizzazione. Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md)[.

## <a name="threat-management-summary"></a>Riepilogo gestione delle minacce

Il widget Riepilogo gestione minacce indica a colpo d'occhio come l'organizzazione è stata protetta dalle minacce negli ultimi sette (7) giorni.

![Dashboard di sicurezza - Widget Riepilogo gestione minacce](../../media/SecDash-ThreatMgmtSummary.png)

Le informazioni che verranno visualizzate nel riepilogo di Gestione delle minacce dipendono da ciò che include l'abbonamento. Nella tabella seguente vengono descritte le informazioni incluse per Office 365 E3 e Office 365 E5.

<br>

****

|Office 365 E3|Office 365 E5|
|---|---|
|Messaggi di malware bloccati<br>Messaggi di phishing bloccati<br>Messaggi segnalati dagli utenti<br><br><br><br>|Messaggi di malware bloccati<br>Messaggi di phishing bloccati<br>Messaggi segnalati dagli utenti<br>Malware zero-day bloccato<br>Messaggi di phishing avanzati rilevati<br>URL dannosi bloccati|
|

Per visualizzare o accedere al widget Riepilogo gestione minacce, devi disporre delle autorizzazioni per visualizzare Defender per Office 365 report. Per altre informazioni, vedi [Quali autorizzazioni sono necessarie per visualizzare defender per Office 365 report?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Stato di Threat Protection

Il widget Stato di Threat Protection mostra l'efficacia della protezione dalle minacce con una visualizzazione dettagliata e di tendenza del phish e del malware.

![Widget Stato protezione dalle minacce](../../media/tpswidget.png)

I dettagli dipendono dal fatto che la sottoscrizione Microsoft 365 includa [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) con o senza [Microsoft Defender per Office 365](defender-for-office-365.md).

<br>

****

|Se l'abbonamento include...|Vedrai questi dettagli|
|---|---|
|EOP ma non Microsoft Defender per Office 365|Posta elettronica dannosa rilevata e bloccata da EOP.<p> Vedere [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Microsoft Defender per Office 365|Contenuti dannosi e messaggi di posta elettronica dannosi rilevati e bloccati da EOP e Defender per Office 365 <p> Conteggio aggregato dei messaggi di posta elettronica univoci con contenuto dannoso bloccato dal motore antimalware, eliminazione automatica a [zero](zero-hour-auto-purge.md)ore e defender per le funzionalità di Office 365 (inclusi collegamenti [Cassaforte,](safe-links.md)allegati [Cassaforte](safe-attachments.md)e [anti-phishing in Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)). <p> Vedere [Rapporto sullo stato di Protezione dalle minacce](view-reports-for-mdo.md#threat-protection-status-report).|
|

Per visualizzare o accedere al widget Stato di Threat Protection, devi disporre delle autorizzazioni per visualizzare Defender per Office 365 report. Per altre informazioni, vedi [Quali autorizzazioni sono necessarie per visualizzare i report defender Office 365?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Rilevamenti di minacce settimanali globali

Il widget Global Weekly Threat Detections mostra il numero di minacce rilevate nei messaggi di posta elettronica negli ultimi sette (7) giorni.

![Widget Global Weekly Threat Detections](../../media/globalweeklythreatdetections.png)

Le metriche vengono calcolate come descritto nella tabella seguente:

<br>

****

|Metrica|Modalità di calcolo|
|---|---|
|Messaggi analizzati|Numero di messaggi di posta elettronica analizzati moltiplicati per il numero di destinatari|
|Minacce arrestate|Numero di messaggi di posta elettronica identificati come contenenti malware moltiplicati per il numero di destinatari|
|Bloccato da [Defender per Office 365](defender-for-office-365.md)|Numero di messaggi di posta elettronica bloccati da Defender Office 365 moltiplicato per il numero di destinatari|
|Rimosso dopo il recapito|Numero di messaggi rimossi per [l'eliminazione](zero-hour-auto-purge.md) automatica a zero ore moltiplicato per il numero di destinatari|
|

## <a name="malware"></a>Malware

I widget di malware mostrano i dettagli sulle tendenze del malware e sui tipi di famiglia di malware negli ultimi sette (7) giorni.

![Tendenze malware e tipi di famiglia](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Dati analitici

Insights non solo i problemi principali da esaminare, ma includono anche consigli e azioni da prendere in considerazione.

![Informazioni dettagliate intelligenti](../../media/smartinsights.png)

Ad esempio, è possibile che i messaggi di posta elettronica di phishing vengano recapitati perché alcuni utenti hanno disabilitato le opzioni di posta indesiderata. Per ulteriori informazioni sul funzionamento delle informazioni dettagliate, vedere Report e informazioni dettagliate nel [Centro sicurezza & conformità.](reports-and-insights-in-security-and-compliance.md)

## <a name="threat-investigation-and-response"></a>Analisi e risposta alle minacce

Se l'abbonamento dell'organizzazione include [Microsoft Defender per Office 365 Piano 2,](office-365-ti.md)il dashboard di sicurezza include una sezione che include strumenti avanzati di analisi delle minacce e di risposta. Questi strumenti includono [funzionalità di analisi e risposta automatizzate.](automated-investigation-response-office.md) L'analisi e la risposta automatizzate possono essere utili in scenari come la gestione rapida [di account utente compromessi.](address-compromised-users-quickly.md)

Per altre informazioni, vedi Introduzione all'uso di Analisi e risposta automatizzata [(AIR) in Office 365](office-365-air.md).

## <a name="trends"></a>Tendenze

Nella parte inferiore del dashboard di sicurezza è presente una **sezione Tendenze,** che riepiloga le tendenze del flusso di posta elettronica per l'organizzazione. I report forniscono informazioni sulla posta elettronica classificata come posta indesiderata, malware, tentativi di phishing e buona posta elettronica. Fare clic su un riquadro per visualizzare informazioni più dettagliate nel report.

![La sezione Tendenze riepiloga le tendenze del flusso di posta elettronica per l'organizzazione](../../media/trends.png)

Inoltre, se la sottoscrizione dell'organizzazione include [Defender per Office 365 Piano 2,](office-365-ti.md)in questa sezione sarà disponibile anche un report **Avvisi** di gestione delle minacce recenti che consente al team di sicurezza di visualizzare e intervenire sugli avvisi di sicurezza ad alta priorità.

Per visualizzare o accedere al widget Posta elettronica inviata e ricevuta, è necessario disporre delle autorizzazioni per visualizzare Defender per Office 365 report. Per altre informazioni, vedi [Quali autorizzazioni sono necessarie per visualizzare defender per Office 365 report?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Per visualizzare o accedere al widget Avvisi di gestione delle minacce recenti, è necessario disporre delle autorizzazioni per visualizzare gli avvisi. Per ulteriori informazioni, vedere [Autorizzazioni RBAC necessarie per visualizzare gli avvisi.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)

## <a name="related-articles"></a>Articoli correlati

[Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità](view-email-security-reports.md)

[Visualizzare i report per Microsoft Defender per Office 365](view-reports-for-mdo.md)

[Defender per Office 365](defender-for-office-365.md)

[Office 365 Indagine e risposta alle minacce](office-365-ti.md)
