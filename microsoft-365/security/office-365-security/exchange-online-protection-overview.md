---
title: panoramica di Exchange Online Protection (EOP)
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
description: Informazioni su Exchange Online Protection (EOP) per proteggere l'organizzazione di posta elettronica locale in ambienti autonomi e ibridi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624733"
---
# <a name="exchange-online-protection-overview"></a>Panoramica su Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) è il servizio di filtro basato su cloud che consente di proteggere l'organizzazione da posta indesiderata, malware e altre minacce di posta elettronica. EOP è incluso in tutte le Microsoft 365 con Exchange Online cassette postali.

Nella parte restante di questo articolo viene illustrato il funzionamento di EOP.

> [!NOTE]
> EOP è inoltre disponibile da solo per proteggere le cassette postali locali e negli ambienti ibridi per proteggere le cassette postali Exchange locali. Per ulteriori informazioni, vedere [Standalone Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).

## <a name="how-eop-works"></a>Come funziona EOP

Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Grafica della posta elettronica da Internet o dai commenti dei clienti che passano a EOP e tramite Connessione, Antimalware, Mailflow Rules-slash-Policy Filtering e Filtro contenuto, prima del verdetto della posta indesiderata o della quarantena o del recapito della posta dell'utente finale.":::

- Quando un messaggio in arrivo entra in EOP, inizialmente passa attraverso il filtro connessioni, che controlla la reputazione del mittente. La maggior parte della posta indesiderata viene interrotta a questo punto e rifiutata da EOP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni](configure-the-connection-filter-policy.md).

- Il messaggio viene quindi esaminato per verificare la presenza di malware. Se viene rilevato malware nel messaggio o negli allegati, il messaggio viene instradato a un solo archivio di quarantena dell'amministratore. Per ulteriori informazioni sulla protezione da malware, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)

- I messaggi continuano attraverso il filtro dei criteri, in cui vengono valutati in base alle regole personalizzate del flusso di posta (note anche come regole di trasporto) create o applicate da un modello. Ad esempio, è possibile disporre di una regola che invia una notifica a un responsabile quando la posta arriva da un mittente specifico. I controlli di prevenzione della perdita dei dati (DLP) vengono eseguiti anche a questo punto (Exchange Enterprise CAL con i servizi).

- Successivamente, il messaggio passa attraverso il filtro di protezione da posta indesiderata in cui viene verificata la presenza di posta indesiderata, phishing o posta elettronica in blocco. I messaggi rilevati possono essere inviati in quarantena o nella cartella Posta indesiderata di un utente, tra le altre opzioni. Per ulteriori informazioni, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md) e [Configure anti-phishing policies.](configure-anti-phishing-policies-eop.md)

Tutti i messaggi che superano tutti questi livelli di protezione vengono recapitati al destinatario.

Per ulteriori informazioni, vedere [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Piani e funzionalità di EOP per le organizzazioni di posta elettronica locali

I piani di sottoscrizione EOP disponibili sono:

- **EOP autonomo:** si registra in EOP per proteggere l'organizzazione di posta elettronica locale.

- **Funzionalità di EOP in Exchange Online**: qualsiasi sottoscrizione che include Exchange Online (autonoma o come parte di Microsoft 365) utilizza EOP per proteggere le cassette postali Exchange Online.

- **Exchange Enterprise CAL with Services**: Se si dispone di un'organizzazione di Exchange locale in cui sono state acquistate ulteriori licenze cal Exchange Enterprise con licenze servizi, EOP fa parte dei servizi inclusi.

Per informazioni sui requisiti, i limiti importanti e la disponibilità delle funzionalità in tutti i piani di sottoscrizione EOP, vedere la [Exchange Online Protection servizio.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

> [!NOTE]
> Se si dispone di una Microsoft 365 o Office 365 che include Exchange Online cassette postali, si dispone di EOP. Per la procedura per configurare le funzionalità di sicurezza di EOP nell'abbonamento e per informazioni sulla sicurezza aggiunta che un abbonamento a Microsoft Defender per Office 365 può fornire, vedere Proteggere dalle [minacce.](protect-against-threats.md) Le impostazioni consigliate per la funzionalità EOP per l'installazione sono disponibili in Impostazioni consigliate per [EOP](recommended-settings-for-eop-and-office365.md)e Microsoft Defender per Office 365 sicurezza .

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configurazione di EOP per le organizzazioni di posta elettronica locali

La configurazione di EOP può essere semplice, specialmente nel caso di una piccola organizzazione con poche regole di conformità. Tuttavia, se si ha una grande organizzazione con più domini, regole di conformità personalizzate o flusso di posta ibrido, la configurazione può richiedere più pianificazione e tempo.

Se EOP è già stato acquistato, vedere [Installazione del servizio EOP](/exchange/standalone-eop/set-up-your-eop-service) per assicurarsi di completare tutti i passaggi necessari per configurare EOP per proteggere l'ambiente di messaggistica.

### <a name="eop-datacenters"></a>Datacenter EOP

EOP viene eseguito in una rete globale di centri dati progettati per offrire la massima disponibilità. Ad esempio, se un datacenter non è disponibile, i messaggi di posta elettronica vengono automaticamente instradati a un altro datacenter senza interruzione del servizio. I server in ogni datacenter accettano i messaggi per conto dell'utente, fornendo un livello di separazione tra l'organizzazione e Internet, riducendo così il carico sui server. Attraverso questa rete altamente disponibile, Microsoft può garantire che la posta elettronica raggiunga l'organizzazione in modo tempestivo.

EOP esegue il bilanciamento del carico tra i datacenter ma solo all'intero di un'area geografica. In caso di provisioning in un'unica area geografica, tutti i messaggi saranno elaborati utilizzando il routing della posta per tale area geografica. L'elenco seguente mostra il modo in cui funziona il routing della posta regionale per i datacenter EOP:

- In Europa, Medio Oriente e Africa (EMEA), tutte le cassette postali di Exchange Online si trovano in datacenter situati in EMEA e tutti i messaggi vengono instradati tramite datacenter in EMEA per il filtraggio EOP.
- In Asia-Pacific (APAC), tutte le cassette postali Exchange Online si trovano in datacenter APAC e i messaggi vengono attualmente instradati attraverso datacenter APAC per il filtro EOP.
- Nelle Americhe, i servizi vengono distribuiti nelle posizioni seguenti:
  - Sud America: Exchange Online cassette postali si trovano in datacenter in Brasile e Cile. Tutti i messaggi vengono instradati attraverso data center locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel datacenter in cui si trova il tenant.
  - Canada: Exchange Online cassette postali si trovano in datacenter in Canada. Tutti i messaggi vengono instradati attraverso data center locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel datacenter in cui si trova il tenant.
  - Stati Uniti: Exchange Online cassette postali si trovano nei datacenter statunitensi. Tutti i messaggi vengono instradati attraverso data center locali per il filtro EOP. I messaggi in quarantena vengono archiviati nel datacenter in cui si trova il tenant.
- Per GCC (Government Community Cloud) tutte le cassette postali di Exchange Online si trovano in datacenter degli Stati Uniti e tutti i messaggi vengono instradati tramite datacenter statunitensi per il filtraggio EOP.

## <a name="eop-help-for-admins"></a>Guida di EOP per gli amministratori

Il contenuto della Guida di EOP per gli amministratori comprende le seguenti categorie di primo livello:

- [Configurare EOP, giorno 1,](protect-against-threats.md)per Microsoft Defender per gli amministratori di Office 365 : Configurazione degli strumenti di protezione e rilevamento EOP alla base di Microsoft Defender per Office 365.

- [Funzionalità di EOP](eop-features.md): fornisce un elenco delle funzionalità disponibili in EOP.

- [Configurare il servizio EOP](/exchange/standalone-eop/set-up-your-eop-service): vengono illustrate le procedure per la configurazione del servizio EOP e collegamenti a ulteriori informazioni.

- [Passare a EOP da Google Postini, Barracuda Spam and Virus Firewall o Cisco IronPort:](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)descrive il processo per il passaggio a EOP da un altro prodotto di protezione della posta elettronica.

- [Manage recipients in standalone EOP](/exchange/standalone-eop/manage-recipients-in-eop): Descrive come gestire utenti e gruppi di posta in EOP autonomo.

- Flusso di posta [in EOP](mail-flow-in-eop.md): descrive come configurare scenari personalizzati del flusso di posta utilizzando i connettori, come gestire i domini associati al servizio e come abilitare la funzionalità dbEB (Directory Based Edge Blocking).

- [Impostazioni consigliate per EOP e Microsoft Defender per](recommended-settings-for-eop-and-office365.md)Office 365 sicurezza : descrive le impostazioni di configurazione consigliate e le considerazioni per dopo aver configurato ed eseguito il provisioning del servizio.

- [Report di controllo in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports): descrive come utilizzare i report di controllo per tenere traccia delle modifiche alla configurazione del servizio.

- Protezione da posta indesiderata e [antimalware in EOP](anti-spam-and-anti-malware-protection.md): descrive il filtro della posta indesiderata e il filtro antimalware e mostra come personalizzarli per soddisfare al meglio le esigenze dell'organizzazione. Descrive inoltre le attività che gli amministratori e gli utenti finali possono eseguire sui messaggi in quarantena.

- [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Descrive i report e gli strumenti di risoluzione dei problemi disponibili.

- [Exchange'interfaccia](/exchange/exchange-admin-center) di amministrazione in Exchange Online o nell'interfaccia di amministrazione di [Exchange in EOP](/exchange/standalone-eop/exchange-admin-center-eop)autonomo : descrive come accedere all'interfaccia di gestione dell'interfaccia di amministrazione di Exchange per gestire le funzionalità EOP correlate.

- [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): fornisce informazioni su PowerShell remoto, che consente di gestire il servizio EOP dalla riga di comando.

- [Guida e supporto tecnico per EOP](help-and-support-for-eop.md) Fornisce informazioni su come ottenere assistenza e supporto tecnico.