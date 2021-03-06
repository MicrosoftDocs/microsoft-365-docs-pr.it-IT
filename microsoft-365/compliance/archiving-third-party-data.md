---
title: Archiviare i dati di terze parti
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come importare dati di terze parti da piattaforme di social media, piattaforme di messaggistica istantanea e piattaforme di collaborazione documenti Microsoft 365 cassette postali.
ms.openlocfilehash: c5eebef3e2c6021efc08ff1ed41ba28bacc92487
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339431"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>Archiviare dati di terze parti in Microsoft 365

Microsoft 365 consente agli amministratori di utilizzare i connettori dati per importare e archiviare dati di terze parti da piattaforme di social media, piattaforme di messaggistica istantanea e piattaforme di collaborazione documenti nelle cassette postali dell'organizzazione Microsoft 365 aziendale. Uno dei vantaggi principali dell'utilizzo dei connettori di dati per importare e archiviare dati di terze parti in Microsoft 365 è che è possibile applicare diverse soluzioni di conformità Microsoft 365 dopo l'importazione. Ciò consente di garantire che i dati non Microsoft dell'organizzazione siano conformi alle normative e agli standard che influiscono sull'organizzazione.

## <a name="third-party-data-connectors"></a>Connettori dati di terze parti

Il Centro conformità Microsoft 365 fornisce connettori di dati nativi di terze parti da Microsoft per importare dati da diverse origini dati, ad esempio LinkedIn, Instant Bloomberg e Twitter e i connettori di dati che supportano la soluzione di gestione dei rischi Insider. Oltre a questi connettori di dati, Microsoft collabora con i partner seguenti per fornire molti altri connettori dati di terze parti nell'Centro conformità Microsoft 365. L'organizzazione collabora con questi partner per configurare il servizio di archiviazione prima di creare un connettore dati corrispondente nella Centro conformità Microsoft 365.

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

I dati di terze parti elencati nelle sezioni successive (ad eccezione dei dati delle risorse umane e dei dati di badging fisici utilizzati per la soluzione di gestione dei rischi di Microsoft 365 Insider) vengono importati nelle cassette postali degli utenti. Le Microsoft 365 di conformità che supportano i dati di terze parti vengono applicate alla cassetta postale dell'utente in cui sono archiviati i dati.

### <a name="microsoft-data-connectors"></a>Connettori dati Microsoft

Nella tabella seguente sono elencati i connettori dati di terze parti nativi disponibili nella Centro conformità Microsoft 365. La tabella riepiloga inoltre le soluzioni di conformità che è possibile applicare dopo l'importazione e l'archiviazione di dati di terze parti in Microsoft 365. Vedere la [sezione Panoramica delle soluzioni](#overview-of-compliance-solutions-that-support-third-party-data) di conformità che supportano i dati di terze parti per una descrizione più dettagliata di ogni soluzione di conformità e su come supporta i dati di terze parti.

Fare clic sul collegamento nella colonna **Dati di terze** parti per seguire le istruzioni dettagliate per la creazione di un connettore per tale tipo di dati.

|Dati di terze parti  |Conservazione per controversia legale|eDiscovery  |Impostazioni di conservazione  |Gestione dei record  |Conformità delle comunicazioni  |Gestione dei rischi Insider  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg Message](archive-bloomberg-message-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Risorse umane](import-hr-data.md) ||||||![Segno di spunta](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Badging fisico](import-physical-badging-data.md) ||||||![Segno di spunta](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Connettori dati Veritas

Nella tabella di questa sezione sono elencati i connettori di dati di terze parti disponibili in collaborazione con Veritas. La tabella riepiloga inoltre le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione in Microsoft 365. Vedere la [sezione Panoramica delle soluzioni](#overview-of-compliance-solutions-that-support-third-party-data) di conformità che supportano i dati di terze parti per una descrizione più dettagliata di ogni soluzione di conformità e su come supporta i dati di terze parti.

Prima di poter archiviare dati di terze parti in Microsoft 365, è necessario collaborare con Veritas per configurare il servizio di archiviazione (denominato *Merge1)* per l'organizzazione. Per ulteriori informazioni, fare clic sul collegamento nella colonna **Dati** di terze parti per seguire le istruzioni dettagliate per la creazione di un connettore per tale tipo di dati.

|Dati di terze parti  |Conservazione per controversia legale|eDiscovery  |Impostazioni di conservazione  |Gestione dei record  |Conformità delle comunicazioni  |Gestione dei rischi Insider  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Cisco Jabber su MS SQL](archive-ciscojabberonmssql-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Cisco Bladeber su Oracle](archive-ciscojabberonoracle-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Cisco Jabber su PostgreSQL](archive-ciscojabberonpostgresql-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[.EML](archive-eml-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Connessione FX](archive-fxconnect-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Database MS SQL](archive-mssqldatabaseimporter-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Pivot](archive-pivot-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[RingCentral](archive-ringcentral-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Skype for Business](archive-skypeforbusiness-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Margine di flessibilità eDiscovery](archive-slack-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Delimitato da testo](archive-text-delimited-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Webex Teams](archive-webexteams-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Pagine Web](archive-webpagecapture-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Workplace from Facebook](archive-workplacefromfacebook-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Riunioni Zoom](archive-zoommeetings-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>Connettori dati TeleMessage

Nella tabella di questa sezione sono elencati i connettori di dati di terze parti disponibili in collaborazione con TeleMessage. La tabella riepiloga inoltre le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione in Microsoft 365. Vedere la [sezione Panoramica delle soluzioni](#overview-of-compliance-solutions-that-support-third-party-data) di conformità che supportano i dati di terze parti per una descrizione più dettagliata di ogni soluzione di conformità e su come supporta i dati di terze parti.

Prima di poter archiviare dati di terze parti in Microsoft 365, è necessario collaborare con TeleMessage per configurare il servizio di archiviazione per l'organizzazione. Per ulteriori informazioni, fare clic sul collegamento nella colonna **Dati** di terze parti per seguire le istruzioni dettagliate per la creazione di un connettore per tale tipo di dati.

I connettori di dati TeleMessage sono disponibili anche in GCC nel cloud Microsoft 365 us government. Per ulteriori informazioni, vedere la sezione [Connettori di dati](#data-connectors-in-the-us-government-cloud) nel cloud del governo statunitense in questo articolo.

|Dati di terze parti  |Conservazione per controversia legale|eDiscovery  |Impostazioni di conservazione  |Gestione dei record  |Conformità delle comunicazioni  |Gestione dei rischi Insider  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[AT&T Network](archive-att-network-archiver-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Bell Network](archive-bell-network-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Enterprise Number](archive-enterprise-number-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[O2 Network](archive-o2-network-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Segnale](archive-signal-archiver-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Telegram](archive-telegram-archiver-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Rete TELUS](archive-telus-network-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Rete Verizon](archive-verizon-network-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[WeChat](archive-wechat-data.md)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>Connettori dati 17a-4

Nella tabella di questa sezione sono elencati i connettori di dati di terze parti disponibili in collaborazione con 17a-4 LLC. La tabella riepiloga inoltre le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione in Microsoft 365. Vedere la [sezione Panoramica delle soluzioni](#overview-of-compliance-solutions-that-support-third-party-data) di conformità che supportano i dati di terze parti per una descrizione più dettagliata di ogni soluzione di conformità e su come supporta i dati di terze parti.

Prima di poter archiviare dati di terze parti in Microsoft 365, è necessario collaborare con Veritas per configurare il servizio di archiviazione (denominato *DataParser)* per l'organizzazione. Per ulteriori informazioni, fare clic sul collegamento nella colonna **Dati** di terze parti per seguire le istruzioni dettagliate per la creazione di un connettore per tale tipo di dati.

|Dati di terze parti  |Conservazione per controversia legale|eDiscovery  |Impostazioni di conservazione  |Gestione dei record  |Conformità delle comunicazioni  |Gestione dei rischi Insider  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Bloomberg](archive-17a-4-bloomberg-data.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Fuze](archive-17a-4-fuze-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Connessione FX](archive-17a-4-fxconnect-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[ICE Chat](archive-17a-4-ice-im-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[LivePerson Conversational Cloud](archive-17a-4-liveperson-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Quip](archive-17a-4-quip-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Slack](archive-17a-4-slack-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
|[Zoom](archive-17a-4-zoom-data.md)    |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>Connettori dati CellTrust

Nella tabella di questa sezione sono elencati i connettori di dati di terze parti disponibili in collaborazione con CellTrust. La tabella riepiloga inoltre le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione in Microsoft 365. Vedere la [sezione Panoramica delle soluzioni](#overview-of-compliance-solutions-that-support-third-party-data) di conformità che supportano i dati di terze parti per una descrizione più dettagliata di ogni soluzione di conformità e su come supporta i dati di terze parti.

Prima di poter archiviare dati di terze parti in Microsoft 365, è necessario collaborare con CellTrust per configurare il servizio di archiviazione (denominato *CellTrust SL2)* per l'organizzazione. Per ulteriori informazioni, fare clic sul collegamento nella colonna **Dati** di terze parti per istruzioni dettagliate per la creazione di un connettore SL2 CellTrust.

|Dati di terze parti  |Conservazione per controversia legale|eDiscovery  |Impostazioni di conservazione  |Gestione dei record  |Conformità delle comunicazioni  |Gestione dei rischi Insider  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||
||||||||

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Panoramica delle soluzioni di conformità che supportano dati di terze parti

Le sezioni seguenti descrivono alcuni degli aspetti che le soluzioni Microsoft 365 conformità possono aiutare a gestire i dati di terze parti elencati nella tabella precedente.

### <a name="litigation-hold"></a>Conservazione per controversia legale

Si posiziona un [blocco per controversia legale](create-a-litigation-hold.md) su una cassetta postale utente per conservare i dati di terze parti. Quando si crea un'esenzione, è possibile specificare una durata del blocco (denominata anche conservazione basata sul *tempo)* in modo che i dati di terze parti eliminati e modificati vengono conservati per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. In alternativa, è possibile conservare il contenuto a tempo indeterminato (denominato blocco *infinito)* o fino a quando non viene rimossa la conservazione per controversia legale.

### <a name="ediscovery"></a>eDiscovery

I tre principali strumenti di eDiscovery in Microsoft 365 ricerca contenuto, Core eDiscovery e Advanced eDiscovery.

- **[Ricerca contenuto](content-search.md).** È possibile utilizzare lo strumento di ricerca contenuto per cercare nelle cassette postali i dati di terze parti importati. È possibile utilizzare le query e le condizioni di ricerca per restringere i risultati della ricerca e esportare i risultati della ricerca.

- **[Core eDiscovery](get-started-core-ediscovery.md).** Questo strumento si basa sulla funzionalità di ricerca ed esportazione di base consentendo di creare casi che consentono di controllare chi può accedere ai dati del caso, di mantenere le cassette postali degli utenti o il contenuto delle cassette postali che soddisfano i criteri di ricerca. Ciò significa che è possibile inserire un blocco di eDiscovery sui dati di terze parti importati nelle cassette postali degli utenti.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Questo potente strumento espande la funzionalità dei casi di Core eDiscovery consentendo di aggiungere i custodi a un caso, mettendo i dati del custode in attesa e quindi caricando i dati di terze parti di un responsabile in una revisione per ulteriori analisi, ad esempio temi e rilevamento duplicati. Dopo aver caricato i dati di terze parti in un set di revisione, è possibile eseguire query e filtrare i dati in un set di risultati ristretto.

   Sia Core eDiscovery che Advanced eDiscovery consentono di gestire dati di terze parti che potrebbero essere rilevanti per le indagini legali o interne dell'organizzazione.

### <a name="retention-settings"></a>Impostazioni di conservazione

È possibile applicare un criterio [di](retention.md) conservazione alle cassette postali degli utenti per conservare ed eliminare i dati di terze parti (e altro contenuto delle cassette postali) dopo la scadenza del periodo di conservazione. È inoltre possibile utilizzare i criteri di conservazione per [](disposition.md) eliminare dati di terze parti di una determinata età o utilizzare etichette di conservazione per attivare una revisione dell'eliminazione alla scadenza del periodo di conservazione per i dati di terze parti.

### <a name="records-management"></a>Gestione dei record

La [funzionalità di gestione](records-management.md) dei record in Microsoft 365 consente di dichiarare i dati di terze parti come record. Questa operazione può essere eseguita manualmente dagli utenti che applicano un'etichetta di conservazione che contrassegna come record i dati di terze parti nella cassetta postale. In caso contrario, è possibile applicare automaticamente le etichette di conservazione identificando informazioni riservate, parole chiave o tipi di contenuto nei dati di terze parti.

### <a name="communication-compliance"></a>Conformità delle comunicazioni

È possibile utilizzare [conformità delle comunicazioni](communication-compliance.md) per esaminare i dati di terze parti per verificare che siano conformi agli standard di dati dell'organizzazione. A tale scopo, è possibile rilevare, acquisire ed eseguire azioni di correzione per i messaggi inappropriati nell'organizzazione. Ad esempio, è possibile monitorare i dati di terze parti importati per il linguaggio offensivo, le informazioni riservate e la conformità normativa.

### <a name="insider-risk-management"></a>Gestione dei rischi Insider

I segnali provenienti da dati di terze parti, come i dati selettivi sulle risorse umane, possono essere utilizzati dalla soluzione di gestione dei rischi [Insider](insider-risk-management.md) per ridurre al minimo i rischi interni consentendoti di rilevare, analizzare e agire su attività rischiose nell'organizzazione. Ad esempio, i dati importati dal connettore di dati hr vengono utilizzati come indicatori di rischio per rilevare il furto di dati dei dipendenti in partenza.

## <a name="data-connectors-in-the-us-government-cloud"></a>Connettori dati nel cloud per enti pubblici statunitensi

Come accennato in precedenza, i connettori dati forniti da TeleMessage sono disponibili nel cloud del governo statunitense. Nella tabella seguente sono indicati gli ambienti governativi specifici che supportano ogni connettore di dati TeleMessage. Per ulteriori informazioni sui cloud del governo statunitense, [vedere Microsoft 365 US Government.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)

|Connettore dati TeleMessage  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Android Archiver | Sì | No | No |
|AT&T SMS/MMS Network Archiver | Sì | No | No |
|Bell SMS/MMS Network Archiver | Sì | No | No |
|Enterprise Number Archiver | Sì | No | No |
|O2 SMS e Voice Network Archiver | Sì         | No | No |
|TELUS SMS Network Archiver | Sì | No | No |
|Verizon SMS/MMS Network Archiver | Sì | No | No |
|WhatsApp Archiver | Sì | No | No |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Collaborazione con un partner Microsoft per archiviare dati di terze parti

Un'altra opzione per l'importazione e l'archiviazione di dati di terze parti è che l'organizzazione lavori con un partner Microsoft. Se un tipo di dati di terze parti non è supportato dai connettori di dati disponibili nel Centro conformità Microsoft, è possibile collaborare con un partner in grado di fornire un connettore personalizzato che verrà configurato per estrarre regolarmente elementi dall'origine dati di terze parti e quindi connettersi al cloud Microsoft da un'API di terze parti e importare tali elementi in Microsoft 365. Il connettore partner converte inoltre il contenuto di un elemento dall'origine dati di terze parti in un messaggio di posta elettronica e quindi lo importa in una cassetta postale in Microsoft 365.

Per un elenco dei partner che è possibile utilizzare e il processo dettagliato per questo metodo, vedere Collaborare con un partner per archiviare dati di terze parti [in Microsoft 365](work-with-partner-to-archive-third-party-data.md).
