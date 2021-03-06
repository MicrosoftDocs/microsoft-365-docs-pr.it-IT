---
title: Creazione di report e traccia messaggio
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono riportati i report e gli strumenti di risoluzione dei problemi disponibili per gli amministratori di Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc49a92d5fb1fb0368b14eef7524638542f38deb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054378"
---
# <a name="reporting-and-message-trace-in-eop"></a>Creazione di report e traccia dei messaggi in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, EOP offre molti report diversi che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità.

## <a name="usage-reports"></a>Report sull'uso

- **Microsoft 365 gruppi di** lavoro : consente di visualizzare informazioni sul numero di Microsoft 365 che vengono creati e utilizzati. Per ulteriori informazioni, vedere [Microsoft 365 report nell'interfaccia di amministrazione - Microsoft 365 gruppi](../../admin/activity-reports/office-365-groups.md).
- **Attività di posta** elettronica : consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e da utenti specifici. Per ulteriori informazioni, vedere [Microsoft 365 report nell'interfaccia di amministrazione - Attività di posta elettronica.](../../admin/activity-reports/email-activity.md)
- **Utilizzo dell'app di** posta elettronica : consente di visualizzare informazioni sulle app di posta elettronica usate. Questo include il numero totale di connessioni per ogni app e le versioni di Outlook che si connettono. Per ulteriori informazioni, vedere report [Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle app di posta elettronica.](../../admin/activity-reports/email-apps-usage.md)
- **Utilizzo delle cassette** postali: consente di visualizzare informazioni sull'archiviazione utilizzata, sul consumo di quote, sul conteggio degli elementi e sull'ultima attività (attività di invio o lettura) per le cassette postali. Per ulteriori informazioni, vedere [Microsoft 365 report nell'interfaccia di amministrazione - Utilizzo delle cassette postali.](../../admin/activity-reports/mailbox-usage.md)

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Report di sicurezza nel portale Microsoft 365 defender

Questi report migliorati offrono un'esperienza di creazione di report interattiva per gli amministratori di EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori dettagli.

- **Defender for Office 365**: consente di visualizzare informazioni sui Cassaforte e Cassaforte allegati che fanno parte di Microsoft Defender per Office 365. Per ulteriori informazioni, vedere [View Defender for Office 365 reports in the Microsoft 365 Defender portal.](view-reports-for-mdo.md)
- **EOP:** consente di visualizzare informazioni sui rilevamenti di malware, posta contraffatta, rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione. Per ulteriori informazioni, vedere [View email security reports in the Microsoft 365 Defender portal.](view-email-security-reports.md)

## <a name="custom-reports-using-microsoft-graph"></a>Report personalizzati con Microsoft Graph

Creare a livello di programmazione report disponibili nell'interfaccia di amministrazione tramite Microsoft Graph. Per ulteriori informazioni, vedere [Overview of Microsoft Graph](/graph/overview) and Working with Office 365 usage reports in Microsoft [Graph](/graph/api/resources/report).

## <a name="message-trace"></a>Traccia dei messaggi

Consente di seguire il percorso dei messaggi all'interno di EOP. È possibile stabilire se un messaggio di posta elettronica è stato ricevuto, rifiutato, ritardato o recapitato dal servizio. Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.

È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.

Vedere [Traccia messaggi nel portale Microsoft 365 Defender messaggi](message-trace-scc.md).

## <a name="audit-logging"></a>Registrazione di controllo

Consente di tenere traccia di modifiche specifiche apportate all'organizzazione dagli amministratori. Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità. Vedere [Report di controllo in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapporti e latenza e disponibilità dei dati dei messaggi

La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.

<br>

****

|Tipo di rapporto|Dati disponibili per (periodo passato)|Latenza|
|---|---|---|
|Rapporti riepilogati sulla protezione della posta|90 giorni|L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.|
|Rapporti dettagliati sulla protezione della posta|90 giorni|Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni. <p> Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|
|Dati di traccia dei messaggi|90 giorni|Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.<p> Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|
|

> [!NOTE]
> La disponibilità e la latenza dei dati sono le stesse richieste tramite l'interfaccia di amministrazione o PowerShell remoto.
