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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sui report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 9a8eb8e35ef73eb27604eef4bf701982b1d51710
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845553"
---
# <a name="reporting-and-message-trace-in-eop"></a>Creazione di report e traccia dei messaggi in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP offre numerosi rapporti diversi che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità.

## <a name="usage-reports"></a>Report sull'uso

**Attività gruppi microsoft 365** : consente di visualizzare informazioni sul numero di gruppi di Microsoft 365 creati e utilizzati.

**Attività di posta elettronica** : consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e per utenti specifici.

**Utilizzo delle app di posta elettronica** : consente di visualizzare le informazioni sulle app di posta elettronica utilizzate. Questi dati includono il numero totale di connessioni per ogni applicazione e le versioni di Outlook con cui si stabilisce la connessione.

**Utilizzo delle cassette postali** : consente di visualizzare informazioni sull'archiviazione utilizzata, sul consumo di quote, sul numero di elementi e sull'ultima attività (invio o lettura) per le cassette postali.

Per ulteriori informazioni, vedere le risorse seguenti:

- [Report di Microsoft 365 nell'interfaccia di amministrazione-gruppi Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di posta elettronica](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo delle app di posta elettronica](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo delle cassette postali](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Rapporti di conformità & di sicurezza nell'interfaccia di amministrazione di Microsoft 365

Questi report avanzati forniscono un'esperienza di report interattiva per gli amministratori di EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori dettagli.

**Defender per office 365** : visualizzare informazioni sui collegamenti sicuri e sugli allegati sicuri che fanno parte di Microsoft Defender per Office 365.

**EOP** : consente di visualizzare informazioni su rilevamenti di malware, posta contraffatta, rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.

[Visualizzare i report per il difensore per Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Report personalizzati tramite Microsoft Graph

Creare report a livello di programmazione che sono disponibili nell'interfaccia di amministrazione tramite Microsoft Graph. Per ulteriori informazioni, vedere [Panoramica di Microsoft Graph](https://docs.microsoft.com/graph/overview) e utilizzo dei [report sull'utilizzo di Office 365 in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="message-trace"></a>Traccia dei messaggi

Consente di seguire il percorso dei messaggi all'interno di EOP. È possibile stabilire se un messaggio di posta elettronica è stato ricevuto, rifiutato, ritardato o recapitato dal servizio. Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.

È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.

Vedere [Message Trace in the Security & Compliance Center](message-trace-scc.md).

## <a name="audit-logging"></a>Registrazione di controllo

Consente di tenere traccia di modifiche specifiche apportate all'organizzazione dagli amministratori. Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità. Vedere [rapporti di controllo in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapporti e latenza e disponibilità dei dati dei messaggi

La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.

****

|Tipo di rapporto|Dati disponibili per (periodo passato)|Latenza|
|---|---|---|
|Rapporti di riepilogo sulla protezione della posta|90 giorni|L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.|
|Rapporti dettagliati sulla protezione della posta|90 giorni|Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni. <br/><br/> Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|
|Dati di traccia dei messaggi|90 giorni|Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.<br/><br/> Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|
|

> [!NOTE]
> La disponibilità e la latenza dei dati sono le stesse se richieste tramite l'interfaccia di amministrazione o Remote PowerShell.
