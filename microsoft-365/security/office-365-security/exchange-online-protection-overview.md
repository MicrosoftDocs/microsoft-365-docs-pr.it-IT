---
title: Panoramica di Exchange Online Protection (EOP)
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
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come Exchange Online Protection (EOP) può aiutare a proteggere l'organizzazione di posta elettronica locale in ambienti autonomi e ibridi.
ms.openlocfilehash: 37b38df9e94bee93202be02c01a220afa9470b8a
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204804"
---
# <a name="exchange-online-protection-overview"></a>Panoramica su Exchange Online Protection

Exchange Online Protection (EOP) è il servizio di filtraggio basato sul cloud che consente di proteggere l'organizzazione da posta indesiderata e malware. EOP è incluso in tutte le organizzazioni Microsoft 365 con le cassette postali di Exchange Online.

Tuttavia, EOP è disponibile anche negli scenari locali seguenti:

- **In uno scenario autonomo**: EOP fornisce la protezione della posta elettronica basata sul cloud per l'organizzazione di Exchange locale o per qualsiasi altra soluzione di posta elettronica SMTP locale.

- **In una distribuzione ibrida**: EOP può essere configurato per proteggere l'ambiente di posta elettronica e controllare il routing della posta quando si dispone di una combinazione di cassette postali locali e cloud.

In questi scenari, EOP è in grado di semplificare la gestione dell'ambiente di posta elettronica e di alleviare molti dei fardelli in cui vengono mantenuta l'hardware e il software locali.

Il resto di questo argomento illustra la modalità di funzionamento di EOP in ambienti autonomi e ibridi.

## <a name="how-eop-works"></a>Come funziona EOP

Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:

![Diagramma del processo di posta elettronica](../../media/emailprocessingineop1.png)

- Un messaggio in arrivo passa inizialmente tramite il filtro connessioni, che controlla la reputazione del mittente e controlla il messaggio per il malware. La maggior parte della posta indesiderata viene interrotta a questo punto e viene eliminata da EOP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni](configure-the-connection-filter-policy.md).

- I messaggi continuano tramite il filtro dei criteri, in cui i messaggi vengono valutati in base alle regole del flusso di posta personalizzate (note anche come regole di trasporto) create o applicate da un modello. Ad esempio, è possibile disporre di una regola che invia una notifica a un responsabile quando la posta arriva da un mittente specifico. I controlli di prevenzione della perdita di dati (DLP) si verificano anche a questo punto (Exchange Enterprise CAL with Services).

- Successivamente, i messaggi passano attraverso il filtro di protezione dalla posta indesiderata (noto anche come filtro contenuto). Un messaggio che è determinato come posta indesiderata può essere inviato alla cartella posta indesiderata di un utente o alla quarantena, tra le altre opzioni. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).

- Dopo che un messaggio ha superato tutti questi livelli di protezione, viene recapitato al destinatario.

Per ulteriori informazioni, vedere [ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

### <a name="eop-datacenters"></a>Datacenter EOP

EOP viene eseguito in una rete globale di centri dati progettati per offrire la massima disponibilità. Ad esempio, se un datacenter non è disponibile, i messaggi di posta elettronica vengono automaticamente instradati a un altro datacenter senza interruzione del servizio. I server di ogni data center accettano messaggi per conto di, fornendo un livello di separazione tra l'organizzazione e Internet, riducendo così il carico sui server. Attraverso questa rete altamente disponibile, Microsoft può garantire che la posta elettronica raggiunga l'organizzazione in modo tempestivo.

EOP esegue il bilanciamento del carico tra i datacenter ma solo all'intero di un'area geografica. In caso di provisioning in un'unica area geografica, tutti i messaggi saranno elaborati utilizzando il routing della posta per tale area geografica. L'elenco seguente mostra il modo in cui funziona il routing della posta regionale per i datacenter EOP:

- In Europa, Medio Oriente e Africa (EMEA), tutte le cassette postali di Exchange Online si trovano in datacenter situati in EMEA e tutti i messaggi vengono instradati tramite datacenter in EMEA per il filtraggio EOP.

- In Asia-Pacifico (APAC), tutte le cassette postali di Exchange Online si trovano in datacenter APAC e i messaggi sono attualmente instradati attraverso i datacenter di APAC per il filtro EOP.

- Nelle Americhe i servizi sono distribuiti nei seguenti percorsi:

  - Sud America: le cassette postali di Exchange Online si trovano in datacenter in Brasile e Cile. Tutti i messaggi vengono instradati attraverso i centri dati locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel centro dati in cui si trova il tenant.

  - Canada: le cassette postali di Exchange Online si trovano in datacenter in Canada. Tutti i messaggi vengono instradati attraverso i centri dati locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel centro dati in cui si trova il tenant.

  - Stati Uniti: le cassette postali di Exchange Online si trovano nei data center degli Stati Uniti. Tutti i messaggi vengono instradati attraverso i centri dati locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel centro dati in cui si trova il tenant.

- Per GCC (Government Community Cloud) tutte le cassette postali di Exchange Online si trovano in datacenter degli Stati Uniti e tutti i messaggi vengono instradati tramite datacenter statunitensi per il filtraggio EOP.

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Piani e funzionalità di EOP per le organizzazioni di posta elettronica locali

I piani di sottoscrizione di EOP disponibili sono i seguenti:

- **EOP standalone**: ti iscrivi a EOP per proteggere l'organizzazione di posta elettronica locale.

- **Funzionalità di EOP in Exchange Online**: tutti gli abbonamenti che includono Exchange Online (standalone o come parte di Microsoft 365) utilizzano EOP per proteggere le cassette postali di Exchange Online.

- **Exchange Enterprise CAL with Services**: se si dispone di un'organizzazione di Exchange locale in cui sono state acquistate altre licenze di Exchange Enterprise CAL with Services, EOP è parte integrante dei servizi inclusi.

Per informazioni sui requisiti, i limiti importanti e la disponibilità delle funzionalità in tutti i piani di sottoscrizione di EOP, vedere la [Descrizione del servizio Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configurazione di EOP per le organizzazioni di posta elettronica locali

La configurazione di EOP può essere semplice, specialmente nel caso di una piccola organizzazione con poche regole di conformità. Tuttavia, se si ha una grande organizzazione con più domini, regole di conformità personalizzate o flusso di posta ibrido, la configurazione può richiedere più pianificazione e tempo.

Se EOP è già stato acquistato, vedere [Installazione del servizio EOP](set-up-your-eop-service.md) per assicurarsi di completare tutti i passaggi necessari per configurare EOP per proteggere l'ambiente di messaggistica.

## <a name="eop-help-for-admins"></a>Guida di EOP per gli amministratori

Il contenuto della Guida di EOP per gli amministratori comprende le seguenti categorie di primo livello:

- [Panoramica di Exchange Online Protection](exchange-online-protection-overview.md): introduce la modalità di funzionamento di EOP e fornisce collegamenti a ulteriori informazioni.

- [Caratteristiche di EOP](eop-features.md): fornisce un elenco delle funzionalità disponibili in EOP.

- [Set up your EOP Service](set-up-your-eop-service.md): viene descritta la procedura per configurare il servizio EOP e i collegamenti a ulteriori informazioni.

- [Passare a EOP da Google Postini, Barracuda Spam and virus firewall o Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): viene descritto il processo di passaggio a EOP da un altro prodotto di protezione della posta elettronica.

- [Manage Recipients in standalone EOP](manage-recipients-in-eop.md): viene descritto come gestire gli utenti e i gruppi di posta elettronica in EOP.

- [Flusso di posta in EOP: in](mail-flow-in-eop.md)questo articolo viene descritto come configurare scenari del flusso di posta personalizzato utilizzando i connettori, come gestire i domini associati al servizio e come abilitare la funzionalità DBEB (directory based Edge Blocking).

- [Procedure](best-practices-for-configuring-eop.md)consigliate per la configurazione di EOP: vengono descritte le impostazioni di configurazione e le considerazioni consigliate per una volta configurato e provisioning del servizio.

- [Rapporti di controllo in EOP autonomo](auditing-reports-in-eop.md): viene descritto come utilizzare i rapporti di controllo per verificare le modifiche alla configurazione del servizio.

- [Protezione da posta indesiderata e antimalware in EOP](anti-spam-and-anti-malware-protection.md): vengono descritti i filtri per la posta indesiderata e il filtro antimalware e viene illustrato come personalizzarli in modo da soddisfare al meglio le esigenze dell'organizzazione. Descrive inoltre le attività che gli amministratori e gli utenti finali possono eseguire sui messaggi in quarantena.

- [Reporting and Message Trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): vengono descritti i report e gli strumenti per la risoluzione dei problemi disponibili.

- Interfaccia di [amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md): viene descritto come accedere e navigare tramite il centro di gestione di amministrazione di Exchange (EAC) per gestire il servizio EOP.

- [PowerShell di Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): fornisce informazioni su PowerShell remoto, che consente di gestire il servizio EOP dalla riga di comando.

- [Guida e supporto tecnico per EOP](help-and-support-for-eop.md) Fornisce informazioni su come ottenere assistenza e supporto tecnico.
