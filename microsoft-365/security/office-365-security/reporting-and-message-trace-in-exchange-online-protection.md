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
description: In questo articolo vengono appresi i report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86c9eb0ee050c4c1a40ef7f29ea3d01dc202be9a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166676"
---
# <a name="reporting-and-message-trace-in-eop"></a>Creazione di report e traccia dei messaggi in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, EOP offre molti rapporti diversi che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità.

## <a name="usage-reports"></a>Report sull'uso

**Attività dei gruppi di Microsoft 365:** visualizzare informazioni sul numero di gruppi di Microsoft 365 creati e usati.

**Attività di posta** elettronica : consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e da utenti specifici.

**Utilizzo dell'app di** posta elettronica: consente di visualizzare informazioni sulle app di posta elettronica usate. Questi dati includono il numero totale di connessioni per ogni applicazione e le versioni di Outlook con cui si stabilisce la connessione.

**Utilizzo delle cassette** postali : consente di visualizzare informazioni sull'archiviazione utilizzata, sul consumo delle quote, sul numero di elementi e sull'ultima attività (attività di invio o lettura) per le cassette postali.

Per ulteriori informazioni, vedere le risorse seguenti:

- [Report di Microsoft 365 nell'interfaccia di amministrazione - Gruppi di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di posta elettronica](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle app di posta elettronica](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Report sulla & sicurezza nell'interfaccia di amministrazione di Microsoft 365

Questi report migliorati offrono un'esperienza di creazione di report interattiva per gli amministratori di EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori dettagli.

**Defender per Office 365:** visualizzare informazioni su collegamenti sicuri e allegati sicuri che fanno parte di Microsoft Defender per Office 365.

**EOP:** consente di visualizzare informazioni sui rilevamenti di malware, messaggi falsificati, rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.

[Visualizzare i report per Defender per Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Report personalizzati con Microsoft Graph

Creare report disponibili nell'interfaccia di amministrazione a livello di programmazione tramite Microsoft Graph. Per ulteriori informazioni, vedere [Panoramica di Microsoft Graph](https://docs.microsoft.com/graph/overview) e Utilizzo dei report sull'utilizzo di Office [365 in Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/report)

## <a name="message-trace"></a>Traccia dei messaggi

Consente di seguire il percorso dei messaggi all'interno di EOP. È possibile stabilire se un messaggio di posta elettronica è stato ricevuto, rifiutato, ritardato o recapitato dal servizio. Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.

È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.

Vedere [Traccia messaggio nel Centro sicurezza & conformità.](message-trace-scc.md)

## <a name="audit-logging"></a>Registrazione di controllo

Consente di tenere traccia di modifiche specifiche apportate all'organizzazione dagli amministratori. Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità. Vedere [Report di controllo in EOP.](auditing-reports-in-eop.md)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapporti e latenza e disponibilità dei dati dei messaggi

La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.

****

|Tipo di rapporto|Dati disponibili per (periodo passato)|Latenza|
|---|---|---|
|Rapporti di riepilogo sulla protezione della posta|90 giorni|L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.|
|Rapporti dettagliati sulla protezione della posta|90 giorni|Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni. <p> Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|
|Dati di traccia dei messaggi|90 giorni|Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.<p> Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.|
|

> [!NOTE]
> La disponibilità e la latenza dei dati sono le stesse richieste tramite l'interfaccia di amministrazione o PowerShell remoto.
