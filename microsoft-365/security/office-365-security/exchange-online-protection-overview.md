---
title: Panoramica di Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come Exchange Online Protection (EOP) può aiutare a proteggere l'organizzazione di posta elettronica locale in ambienti autonomi e ibridi.
ms.openlocfilehash: b546b60e242d7f4f7fd4c4550bb61b94052ff4d1
ms.sourcegitcommit: eb905c5b4d7e71fc930a207357295b0160c4f065
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2020
ms.locfileid: "48137018"
---
# <a name="exchange-online-protection-overview"></a>Panoramica su Exchange Online Protection

Exchange Online Protection (EOP) è il servizio di filtraggio basato sul cloud che consente di proteggere l'organizzazione da posta indesiderata e malware. EOP è incluso in tutte le organizzazioni Microsoft 365 con le cassette postali di Exchange Online. Tuttavia, EOP è disponibile anche negli scenari locali seguenti:

- **In uno scenario autonomo**: EOP fornisce la protezione della posta elettronica basata sul cloud per l'organizzazione di Exchange locale o per qualsiasi altra soluzione di posta elettronica SMTP locale.

- **In una distribuzione ibrida**: EOP può essere configurato per proteggere l'ambiente di posta elettronica e controllare il routing della posta quando si dispone di una combinazione di cassette postali locali e cloud.

In questi scenari, EOP è in grado di semplificare la gestione dell'ambiente di posta elettronica e di alleviare molti dei fardelli in cui vengono mantenuta l'hardware e il software locali.

Il resto di questo argomento illustra la modalità di funzionamento di EOP in ambienti autonomi e ibridi.

## <a name="how-eop-works"></a>Come funziona EOP

Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Grafica del messaggio di posta elettronica da Internet o dal feedback dei clienti che passa in EOP e tramite la connessione, il filtro antimalware, le regole del flusso di posta-Slash-Policy Filtering e il filtro del contenuto, prima del verdetto del messaggio indesiderato o della quarantena o del recapito della posta finale.":::

- Quando un messaggio in arrivo entra in EOP, inizialmente passa attraverso il filtro connessioni, che verifica la reputazione del mittente. La maggior parte della posta indesiderata viene interrotta a questo punto e rifiutata da EOP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy?view=o365-worldwide).

- Il messaggio viene quindi ispezionato per individuare eventuali segni di malware. Se il malware viene trovato nel messaggio o negli allegati, il messaggio viene instradato a un archivio di quarantena solo di amministratore. Per ulteriori informazioni sulla configurazione di anti-malware, vedere [qui](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).

- I messaggi continuano tramite il filtro dei criteri, in cui vengono valutati in base alle regole del flusso di posta personalizzate (note anche come regole di trasporto) create o applicate da un modello. Ad esempio, è possibile disporre di una regola che invia una notifica a un responsabile quando la posta arriva da un mittente specifico. I controlli di prevenzione della perdita di dati (DLP) si verificano anche a questo punto (Exchange Enterprise CAL with Services).

- Successivamente, il messaggio passa attraverso il filtro contenuto (noto anche come protezione da posta indesiderata). Un messaggio che questo filtro determina come posta indesiderata *o phishing* può essere inviato alla quarantena o alla cartella posta indesiderata di un utente, tra le altre opzioni. Per ulteriori informazioni, vedere Configurare i criteri di protezione dalla [posta indesiderata](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide) e [configurare i criteri di anti-phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-phishing-policies-eop?view=o365-worldwide).

Tutti i messaggi che passano tutti questi layer di protezione vengono recapitati al destinatario.

Per ulteriori informazioni, vedere [ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Piani e funzionalità di EOP per le organizzazioni di posta elettronica locali

I piani di sottoscrizione di EOP disponibili sono i seguenti:

- **EOP standalone**: ti iscrivi a EOP per proteggere l'organizzazione di posta elettronica locale.

- **Funzionalità di EOP in Exchange Online**: tutti gli abbonamenti che includono Exchange Online (standalone o come parte di Microsoft 365) utilizzano EOP per proteggere le cassette postali di Exchange Online.

- **Exchange Enterprise CAL with Services**: se si dispone di un'organizzazione di Exchange locale in cui sono state acquistate altre licenze di Exchange Enterprise CAL with Services, EOP è parte integrante dei servizi inclusi.

Per informazioni sui requisiti, i limiti importanti e la disponibilità delle funzionalità in tutti i piani di sottoscrizione di EOP, vedere la [Descrizione del servizio Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configurazione di EOP per le organizzazioni di posta elettronica locali

La configurazione di EOP può essere semplice, specialmente nel caso di una piccola organizzazione con poche regole di conformità. Tuttavia, se si ha una grande organizzazione con più domini, regole di conformità personalizzate o flusso di posta ibrido, la configurazione può richiedere più pianificazione e tempo.

Se EOP è già stato acquistato, vedere [Installazione del servizio EOP](set-up-your-eop-service.md) per assicurarsi di completare tutti i passaggi necessari per configurare EOP per proteggere l'ambiente di messaggistica.

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

## <a name="eop-help-for-admins"></a>Guida di EOP per gli amministratori

Il contenuto della Guida di EOP per gli amministratori comprende le seguenti categorie di primo livello:

- [Configure EOP, Day 1, for office 365 ATP Admins](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide): Configuring EOP Protection and Detection Tools at the Core of Office 365 Advanced Threat Protection.

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
