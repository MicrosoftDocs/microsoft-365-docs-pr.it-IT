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
ms.openlocfilehash: a925b251ff79aec5acaa0b2c1da2aee3f5a6d70d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930164"
---
# <a name="exchange-online-protection-overview"></a>Panoramica su Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) è il servizio di filtro basato su cloud che protegge l'organizzazione da posta indesiderata, malware e altre minacce di posta elettronica. EOP è incluso in tutte le Microsoft 365 con Exchange Online cassette postali.

> [!NOTE]
> EOP è inoltre disponibile da solo per proteggere le cassette postali locali e negli ambienti ibridi per proteggere le cassette postali Exchange locali. Per ulteriori informazioni, vedere [Standalone Exchange Online Protection](/exchange/standalone-eop/standalone-eop).

I passaggi per configurare le funzionalità di sicurezza di EOP e un confronto con la sicurezza aggiunta che ottieni in Microsoft Defender per Office 365, vedi Proteggere dalle [minacce](protect-against-threats.md). Le impostazioni consigliate per le funzionalità di EOP sono disponibili in Impostazioni consigliate per [EOP](recommended-settings-for-eop-and-office365.md)e Microsoft Defender per Office 365 sicurezza .

Nella parte restante di questo articolo viene illustrato il funzionamento di EOP e le funzionalità disponibili in EOP.

## <a name="how-eop-works"></a>Come funziona EOP

Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Grafica della posta elettronica da Internet o dai commenti dei clienti che passano a EOP e tramite Connessione, Antimalware, Mailflow Rules-slash-Policy Filtering e Filtro contenuto, prima del verdetto della posta indesiderata o della quarantena o del recapito della posta dell'utente finale.":::

1. Quando un messaggio in arrivo entra in EOP, inizialmente passa attraverso il filtro connessioni, che controlla la reputazione del mittente. La maggior parte della posta indesiderata viene interrotta a questo punto e rifiutata da EOP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni](configure-the-connection-filter-policy.md).

2. Il messaggio viene quindi esaminato per verificare la presenza di malware. Se viene rilevato malware nel messaggio o negli allegati, il messaggio viene instradato a un solo archivio di quarantena dell'amministratore. Per ulteriori informazioni sulla protezione da malware, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)

3. Il messaggio continua attraverso il filtro dei criteri, in cui viene valutato rispetto a qualsiasi regola del flusso di posta (nota anche come regole di trasporto) creata. Ad esempio, una regola può inviare una notifica a un responsabile quando un messaggio arriva da un mittente specifico.

   In un'organizzazione locale con Exchange Enterprise cal con licenze di servizi, anche i controlli di prevenzione della perdita dei dati [(DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) in EOP vengono eseguiti a questo punto.

4. Il messaggio passa attraverso il filtro contenuto (anti-spam e anti-spoofing) in cui i messaggi dannosi vengono identificati come posta indesiderata, posta indesiderata ad alta probabilità, phishing, phishing ad alta probabilità o in blocco (criteri di protezione da posta indesiderata) o spoofing (impostazioni di spoofing nei criteri anti-phishing). È possibile configurare l'azione da eseguire sul messaggio in base al verdetto di filtro (quarantena, spostamento nella cartella Posta indesiderata e così via). Per ulteriori informazioni, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md) e [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)

Un messaggio che supera correttamente tutti questi livelli di protezione viene recapitato ai destinatari.

Per ulteriori informazioni, vedere [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

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

### <a name="eop-features"></a>Funzionalità di Exchange Online Protection

In questa sezione viene fornita una panoramica generale delle principali funzionalità disponibili in EOP.

Per informazioni sui requisiti, i limiti importanti e la disponibilità delle funzionalità in tutti i piani di sottoscrizione EOP, vedere la [Exchange Online Protection servizio.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**Note**:

- EOP usa alcuni elenchi di protezione URL aggiuntivi, che consentono di rilevare i collegamenti dannosi all'interno dei messaggi.
- EOP utilizza un vasto elenco di domini noti per l'invio di posta indesiderata.
- EOP usa più motori antimalware per proteggere automaticamente i nostri clienti in qualsiasi momento.
- EOP esamina il payload attivo nel corpo del messaggio e tutti gli allegati dei messaggi alla ricerca di malware.
- Per i valori consigliati per i criteri di protezione, vedere [Impostazioni consigliate per EOP e Microsoft Defender per Office 365 sicurezza](recommended-settings-for-eop-and-office365.md).
- Per istruzioni rapide su come configurare i criteri di protezione, vedere [Protezione dalle minacce.](protect-against-threats.md)

<br>

****
|Funzionalità|Commenti|
|---|---|
|**Protezione**||
|Antimalware|[Protezione antimalware in EOP](anti-malware-protection.md) <p> [Domande frequenti sulla protezione antimalware](anti-malware-protection-faq-eop.yml) <p> [Configurare i criteri antimalware in EOP](configure-anti-malware-policies.md)|
|Posta indesiderata in ingresso|[Protezione da posta indesiderata in EOP](anti-spam-protection.md) <p> [Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.yml) <p> [Configurare criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)|
|Posta indesiderata in uscita|[Protezione da posta indesiderata in uscita in EOP](outbound-spam-controls.md) <p> [Configurare il filtro posta indesiderata in uscita in EOP](configure-the-outbound-spam-policy.md) <p> [Controllare l'inoltro automatico della posta elettronica esterna in Microsoft 365](external-email-forwarding.md)|
|Filtro connessioni|[Configurazione del filtro connessioni](configure-the-connection-filter-policy.md)|
|Anti-phishing|[Criteri anti-phishing in Microsoft 365](set-up-anti-phishing-policies.md) <p> [Configurare i criteri anti-phishing in Exchange Online Protection](configure-anti-phishing-policies-eop.md)|
|Protezione anti-spoofing|[Informazioni di intelligence di spoofing in EOP](learn-about-spoof-intelligence.md) <p> [Gestire l'elenco di tenant consentiti/bloccati](tenant-allow-block-list.md)|
|Eliminazione automatica a zero ore (ZAP) per i messaggi di malware, posta indesiderata e phishing recapitati|[ZAP in Exchange Online](zero-hour-auto-purge.md)|
|Preimpostare i criteri di sicurezza.|[Criteri di sicurezza predefiniti in EOP e Microsoft Defender per Office 365](preset-security-policies.md) <p> [Analizzatore della configurazione per i criteri di protezione in EOP e Microsoft Defender per Office 365](configuration-analyzer-for-security-policies.md)|
|Elenco tenant consentiti/bloccati|[Gestire l'elenco di tenant consentiti/bloccati](tenant-allow-block-list.md)|
|Elenchi di indirizzi bloccati per i mittenti dei messaggi|[Creare elenchi di mittenti bloccati in EOP](create-block-sender-lists-in-office-365.md)|
|Consenti elenchi per i mittenti dei messaggi|[Creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[Usare il blocco Edge basato su directory per rifiutare i messaggi inviati a destinatari non validi](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**Quarantena e invii**||
|Invio dell'amministratore|[Usare l'invio dell'amministratore per inviare posta indesiderata sospetta, phish, URL e file a Microsoft](admin-submission.md)|
|Invii utente (cassetta postale personalizzata)|[Criteri per gli invii di utenti](user-submission.md)|
|Quarantena - amministratori|[Gestire i messaggi e i file messi in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md) <p> [Domande frequenti sui messaggi in quarantena](quarantine-faq.yml) <p> [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md) <p> [Intestazioni dei messaggi della protezione da posta indesiderata in Microsoft 365](anti-spam-message-headers.md) <p> È possibile analizzare le intestazioni dei messaggi in quarantena utilizzando [l'analizzatore dell'intestazione dei messaggi all'indirizzo](https://mha.azurewebsites.net/).|
|Quarantena - utenti finali|[Trovare e rilasciare i messaggi messi in quarantena come utente di EOP](find-and-release-quarantined-messages-as-a-user.md) <p> [Usare le notifiche di posta indesiderata degli utenti per rilasciare e segnalare i messaggi in quarantena](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**Flusso di posta**||
|Regole del flusso di posta|[Regole del flusso di posta (regole di trasporto) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Azioni della regola del flusso di posta in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Gestire le regole del flusso di posta in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Procedure delle regole del flusso di posta in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|Domini accettati|[Gestione dei domini accettati in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|Connettori|[Configurare il flusso di posta utilizzando i connettori in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|Filtro avanzato per i connettori|[Filtro avanzato per i connettori in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**Monitoraggio**||
|Traccia dei messaggi|[Traccia dei messaggi](message-trace-scc.md) <p> [Traccia dei messaggi nell'Exchange di amministrazione](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|Rapporti di collaborazione & e-mail|[Visualizzare report di sicurezza delle e-mail](view-email-security-reports.md)|
|Rapporti del flusso di posta|[Visualizzare report del flusso di posta](view-mail-flow-reports.md) <p> [Rapporti del flusso di posta nell'Exchange di amministrazione](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|Informazioni dettagliate sul flusso di posta|[Informazioni dettagliate sul flusso di posta](mail-flow-insights-v2.md) <p> [Informazioni dettagliate sul flusso di posta Exchange'interfaccia di amministrazione](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|Report di controllo|[Report di controllo nell'Exchange di amministrazione](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|Criteri di avviso|[Criteri di avviso](../../compliance/alert-policies.md)|
|**Contratti di servizio e supporto**||
|SLA di efficienza spam|\> 99%|
|SLA rapporto falsi positivi|\< 1:250,000|
|SLA rilevamento e blocco dei virus|100% dei virus noti|
|SLA uptime mensili|99.999%|
|Assistenza tecnica telefonica e Web 7 giorni su 7, 24 ore su 24|[Guida e supporto per EOP](help-and-support-for-eop.md).|
|**Altre funzionalità**||
|Rete di server globale con ridondanza geografica|EOP viene eseguito in una rete globale di datacenter progettati per offrire la massima disponibilità. Per ulteriori informazioni, vedere la sezione [Datacenter EOP](#eop-datacenters) più indietro in questo articolo.|
|L'accodamento dei messaggi sul server locale non consente di accettare la posta|I messaggi in differimento rimangono nelle code per un giorno. I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario. In media, l'intervallo tra i tentativi di invio è di 5 minuti. Per ulteriori informazioni, vedere [Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.yml).|
|Office 365 Message Encryption disponibile come componente aggiuntivo|Per ulteriori informazioni, vedere [Crittografia in Office 365](../../compliance/encryption.md).|
|||
