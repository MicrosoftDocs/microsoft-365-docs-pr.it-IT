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
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come Exchange Online Protection (EOP) consente di proteggere l'organizzazione di posta elettronica locale in ambienti autonomi e ibridi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8e3d44cb39e3569179d4155e32a8c11e0a5be56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286886"
---
# <a name="exchange-online-protection-overview"></a>Panoramica su Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) è il servizio di filtro basato su cloud che consente di proteggere l'organizzazione da posta indesiderata e malware. EOP è incluso in tutte le organizzazioni di Microsoft 365 con cassette postali di Exchange Online. Tuttavia, EOP è disponibile anche nei seguenti scenari locali:

- **In uno scenario** autonomo: EOP fornisce protezione della posta elettronica basata sul cloud per l'organizzazione Exchange locale o per qualsiasi altra soluzione di posta elettronica SMTP locale.

- **In una distribuzione ibrida:** EOP può essere configurato per proteggere l'ambiente di posta elettronica e controllare il routing della posta quando si dispone di una combinazione di cassette postali locali e cloud.

In questi scenari, EOP può semplificare la gestione dell'ambiente di posta elettronica e ridurre molti degli oneri associati alla gestione di hardware e software locali.

Nella parte restante di questo argomento viene illustrato il funzionamento di EOP in ambienti autonomi e ibridi.

## <a name="how-eop-works"></a>Come funziona EOP

Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Immagine della posta elettronica da Internet o dai commenti dei clienti che passano in EOP e tramite Connessione, Antimalware, Regole flusso di posta -filtro barra-Criteri e Filtro contenuto, prima del verdetto della posta indesiderata o della quarantena o del recapito della posta dell'utente finale.":::

- Quando un messaggio in arrivo entra in EOP, inizialmente passa attraverso il filtro connessioni, che controlla la reputazione del mittente. La maggior parte della posta indesiderata viene interrotta a questo punto e rifiutata da EOP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni](configure-the-connection-filter-policy.md).

- Il messaggio viene quindi esaminato per verificare la presenza di segni di malware. Se viene rilevato malware nel messaggio o negli allegati, il messaggio viene instradato a un solo archivio di quarantena dell'amministratore. Per altre informazioni sulla configurazione dell'antimalware, vedere [qui.](configure-anti-malware-policies.md)

- I messaggi continuano attraverso il filtro dei criteri, in cui vengono valutati in base alle regole del flusso di posta personalizzate (note anche come regole di trasporto) create o applicate da un modello. Ad esempio, è possibile disporre di una regola che invia una notifica a un responsabile quando la posta arriva da un mittente specifico. I controlli di prevenzione della perdita dei dati (DLP) vengono eseguiti anche a questo punto (Exchange Enterprise CAL with Services).

- Successivamente, il messaggio passa attraverso il filtro contenuto (noto anche come protezione da posta indesiderata). Un messaggio che questo filtro determina come posta indesiderata o *phish* può essere inviato in quarantena o nella cartella Posta indesiderata di un utente, tra le altre opzioni. Per ulteriori informazioni, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies.](configure-anti-phishing-policies-eop.md)

Tutti i messaggi che superano tutti questi livelli di protezione vengono recapitati al destinatario.

Per ulteriori informazioni, vedere Ordine [e precedenza della protezione della posta elettronica.](how-policies-and-protections-are-combined.md)

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Piani e funzionalità di EOP per le organizzazioni di posta elettronica locali

I piani di sottoscrizione EOP disponibili sono:

- **EOP autonomo:** è possibile iscriversi a EOP per proteggere l'organizzazione di posta elettronica locale.

- **Funzionalità di EOP in Exchange Online:** qualsiasi sottoscrizione che includa Exchange Online (autonomo o come parte di Microsoft 365) utilizza EOP per proteggere le cassette postali di Exchange Online.

- **Exchange Enterprise CAL with Services**: se si dispone di un'organizzazione Exchange locale in cui sono state acquistate licenze Exchange Enterprise CAL with Services aggiuntive, EOP fa parte dei servizi inclusi.

Per informazioni sui requisiti, i limiti importanti e la disponibilità delle funzionalità in tutti i piani di sottoscrizione EOP, vedere la descrizione del [servizio Exchange Online Protection.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configurazione di EOP per le organizzazioni di posta elettronica locali

La configurazione di EOP può essere semplice, specialmente nel caso di una piccola organizzazione con poche regole di conformità. Tuttavia, se si ha una grande organizzazione con più domini, regole di conformità personalizzate o flusso di posta ibrido, la configurazione può richiedere più pianificazione e tempo.

Se EOP è già stato acquistato, vedere [Installazione del servizio EOP](set-up-your-eop-service.md) per assicurarsi di completare tutti i passaggi necessari per configurare EOP per proteggere l'ambiente di messaggistica.

### <a name="eop-datacenters"></a>Datacenter EOP

EOP viene eseguito in una rete globale di centri dati progettati per offrire la massima disponibilità. Ad esempio, se un datacenter non è disponibile, i messaggi di posta elettronica vengono automaticamente instradati a un altro datacenter senza interruzione del servizio. I server in ogni datacenter accettano i messaggi per conto dell'utente, fornendo un livello di separazione tra l'organizzazione e Internet, riducendo così il carico sui server. Attraverso questa rete altamente disponibile, Microsoft può garantire che la posta elettronica raggiunga l'organizzazione in modo tempestivo.

EOP esegue il bilanciamento del carico tra i datacenter ma solo all'intero di un'area geografica. In caso di provisioning in un'unica area geografica, tutti i messaggi saranno elaborati utilizzando il routing della posta per tale area geografica. L'elenco seguente mostra il modo in cui funziona il routing della posta regionale per i datacenter EOP:

- In Europa, Medio Oriente e Africa (EMEA), tutte le cassette postali di Exchange Online si trovano in datacenter situati in EMEA e tutti i messaggi vengono instradati tramite datacenter in EMEA per il filtraggio EOP.

- In Asia-Pacific (APAC), tutte le cassette postali di Exchange Online si trovano in datacenter APAC e i messaggi vengono attualmente instradati attraverso datacenter APAC per il filtro EOP.

- Nelle Americhe, i servizi vengono distribuiti nelle posizioni seguenti:

  - Sud America: le cassette postali di Exchange Online si trovano in datacenter in Brasile e Cile. Tutti i messaggi vengono instradati attraverso datacenter locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel datacenter in cui si trova il tenant.

  - Canada: le cassette postali di Exchange Online si trovano in datacenter in Canada. Tutti i messaggi vengono instradati attraverso datacenter locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel datacenter in cui si trova il tenant.

  - Stati Uniti: le cassette postali di Exchange Online si trovano nei datacenter degli Stati Uniti. Tutti i messaggi vengono instradati attraverso datacenter locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel datacenter in cui si trova il tenant.

- Per GCC (Government Community Cloud) tutte le cassette postali di Exchange Online si trovano in datacenter degli Stati Uniti e tutti i messaggi vengono instradati tramite datacenter statunitensi per il filtraggio EOP.

## <a name="eop-help-for-admins"></a>Guida di EOP per gli amministratori

Il contenuto della Guida di EOP per gli amministratori comprende le seguenti categorie di primo livello:

- [Configurare EOP, giorno 1,](protect-against-threats.md)per gli amministratori di Microsoft Defender per Office 365: configurazione degli strumenti di protezione e rilevamento EOP alla base di Microsoft Defender per Office 365.

- [Funzionalità di EOP](eop-features.md): fornisce un elenco delle funzionalità disponibili in EOP.

- [Configurare il servizio EOP:](set-up-your-eop-service.md)fornisce la procedura per configurare il servizio EOP e collegamenti a ulteriori informazioni.

- [Passare a EOP da Google Postini, Barracuda Spam and Virus Firewall o Cisco IronPort:](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)descrive il processo per il passaggio a EOP da un altro prodotto di protezione della posta elettronica.

- [Gestire i destinatari in EOP autonomo](manage-recipients-in-eop.md): Descrive come gestire utenti e gruppi di posta in EOP.

- Flusso di posta [in EOP](mail-flow-in-eop.md): Descrive come configurare scenari di flusso di posta personalizzati utilizzando i connettori, come gestire i domini associati al servizio e come abilitare la funzionalità Directory Based Edge Blocking (DBEB).

- [Procedure consigliate per la configurazione di EOP](best-practices-for-configuring-eop.md): Vengono descritte le impostazioni di configurazione consigliate e le considerazioni relative alla configurazione e al provisioning del servizio.

- [Rapporti di controllo in EOP](auditing-reports-in-eop.md)autonomo: descrive come utilizzare i report di controllo per tenere traccia delle modifiche di configurazione del servizio.

- [Protezione antispam e antimalware in EOP:](anti-spam-and-anti-malware-protection.md)descrive il filtro posta indesiderata e il filtro antimalware e mostra come personalizzarli per soddisfare al meglio le esigenze dell'organizzazione. Descrive inoltre le attività che gli amministratori e gli utenti finali possono eseguire sui messaggi in quarantena.

- [Creazione di report e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): descrive i rapporti e gli strumenti per la risoluzione dei problemi disponibili.

- Interfaccia di amministrazione [di Exchange in EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autonomo: descrive come accedere e spostarsi nell'interfaccia di gestione dell'interfaccia di amministrazione di Exchange per gestire il servizio EOP.

- [PowerShell di Exchange Online Protection:](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)fornisce informazioni su PowerShell remoto, che consente di gestire il servizio EOP dalla riga di comando.

- [Guida e supporto tecnico per EOP](help-and-support-for-eop.md) Fornisce informazioni su come ottenere assistenza e supporto tecnico.
