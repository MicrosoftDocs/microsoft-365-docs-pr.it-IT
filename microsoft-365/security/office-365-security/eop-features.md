---
title: Caratteristiche di EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: Nella tabella seguente viene fornito un elenco delle funzionalità disponibili nel servizio di filtro della posta elettronica ospitato in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ff3c889f3e4d6779b08584ba6537da36d6f2660e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205509"
---
# <a name="eop-features"></a>Funzionalità di Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

Nella tabella seguente viene fornito un elenco delle funzionalità disponibili nel servizio di filtro della posta elettronica ospitato in Exchange Online Protection (EOP).

> [!TIP]
> La [roadmap di Microsoft 365 per le aziende](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) è una buona risorsa per trovare informazioni sulle nuove funzionalità future. Per una visualizzazione più ampia sulle funzionalità disponibili con i diversi piani di abbonamento a EOP, vedere [Descrizione del servizio Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

****

|Funzionalità|Descrizione|
|---|---|
|**Protezione dalla posta indesiderata**||
|Rilevamento posta indesiderata in ingresso|Per ulteriori informazioni, vedere [Protezione da posta indesiderata in Microsoft 365.](anti-spam-protection.md) <p> Negli ambienti di EOP autonomi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (anche note come regole di trasporto) in Exchange locale per tradurre il verdetto filtro posta indesiderata in modo che la regola della posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per informazioni dettagliate, vedere [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Rilevamento posta indesiderata in uscita|La protezione da posta indesiderata in uscita è sempre abilitata se si utilizza il servizio per l'invio della posta in uscita. Per ulteriori informazioni, vedere [Protezione da posta indesiderata in uscita.](outbound-spam-controls.md)|
|Protezione backscatter|Per ulteriori informazioni, vedere [Backscatter ed EOP.](backscatter-messages-and-eop.md)|
|Filtro della posta in blocco|EOP usa la soglia di reclamo in blocco (BCL) per contrassegnare i messaggi di posta elettronica in blocco come posta indesiderata. Per ulteriori informazioni, vedere i seguenti argomenti: <p> [Differenza tra posta elettronica indesiderata e posta elettronica inviata in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [Livello di reclamo in blocco (BCL) in EOP](bulk-complaint-level-values.md) <p> [Configurare criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md)|
|Elenchi di protezione dagli URL dannosi|EOP usa alcuni elenchi di protezione URL aggiuntivi, che consentono di rilevare i collegamenti dannosi all'interno dei messaggi.|
|Protezione anti-phishing|EOP include 750.000 domini di spammer noti.|
|Protezione anti-spoofing|Per ulteriori informazioni, vedere [Protezione anti-spoofing.](anti-spoofing-protection.md)|
|**Gestione della posta indesiderata**||
|Configurare mittenti attendibili e mittenti bloccati|Per ulteriori informazioni, vedere [Create safe sender lists](create-safe-sender-lists-in-office-365.md) e Create blocked sender [lists](create-block-sender-lists-in-office-365.md).|
|Creare criteri di protezione da posta indesiderata personalizzati|Per una maggiore granularità, è possibile creare criteri di protezione da posta indesiderata personalizzati e applicarli a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma è possibile modificarne il livello di priorità (l'ordine di esecuzione). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).|
|Configurare le azioni sui messaggi filtrati dalla posta indesiderata|Ad esempio, è possibile eliminare i messaggi filtrati in base ai contenuti o inviarli nella cartella di posta indesiderata o in quarantena. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).|
|Filtro posta indesiderata internazionale|È possibile configurare il filtro di protezione da posta indesiderata per filtrare i messaggi scritti in lingue specifiche o inviati da paesi o aree geografiche specifiche. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).|
|Gestire la posta indesiderata tramite Outlook o Outlook sul Web (in precedenza noto come Outlook Web App)|Gli amministratori e gli utenti finali possono creare elenchi di mittenti attendibili ed elenchi di mittenti bloccati. Per ulteriori informazioni, vedere [Informazioni sulle impostazioni della posta indesiderata in Outlook.](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> Se si utilizza EOP per proteggere le cassette postali locali, assicurarsi di utilizzare la sincronizzazione della directory per assicurarsi che queste impostazioni siano sincronizzate con il servizio. Per ulteriori informazioni su come configurare la sincronizzazione delle directory, vedere "Utilizzare la sincronizzazione delle directory per gestire gli utenti di posta elettronica" in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).|
|Segnalare falsi positivi e falsi negativi a Microsoft.|Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).|
|Notifiche di quarantena della posta indesiderata dell'utente finale|Per ulteriori informazioni, vedere [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md) e [Configure end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications).|
|Visualizzare, trovare e gestire i messaggi nel portale di quarantena.|Per ulteriori informazioni, vedere [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md) oppure [Find and release quarantined messages as a user.](find-and-release-quarantined-messages-as-a-user.md)|
|Visualizzare le intestazioni dei messaggi di posta indesiderata in quarantena|Dopo aver visualizzato l'intestazione del messaggio in quarantena, è [](https://mha.azurewebsites.net/) anche possibile copiare e incollare il testo dell'intestazione nell'analizzatore dell'intestazione del messaggio per scoprire cosa è successo al messaggio.|
|**Protezione anti-malware**||
|Protezione anti-malware a più moduli|La protezione anti-malware a più moduli consente di proteggere automaticamente i clienti in qualsiasi momento.|
|La possibilità di disabilitare il filtro antimalware|Non è possibile disabilitare il filtro antimalware. Fornire un livello di protezione efficace e coerente per tutti i clienti è un aspetto fondamentale della strategia di protezione profonda necessaria per garantire la sicurezza dell'ambiente di messaggistica della posta elettronica. Di conseguenza, il filtro antimalware è abilitato automaticamente per tutti i clienti.|
|Ispezione malware del corpo e degli allegati del messaggio|Il servizio consente di analizzare il payload attivo nel corpo del messaggio e tutti gli allegati del messaggio per i rilevamenti di malware.|
|Notifiche avvisi malware predefinite o personalizzate|È possibile inviare un messaggio di notifica a mittenti o amministratori. Per ulteriori informazioni, vedere [Configure anti-malware policies](configure-anti-malware-policies.md).|
|Notifiche destinatario|Mettere in quarantena automaticamente il messaggio o mettere in quarantena il messaggio e recapitarlo con tutti gli allegati sostituiti da un singolo file di testo contenente testo standard o personalizzato. Per ulteriori informazioni, vedere [Configure anti-malware policies](configure-anti-malware-policies.md).|
|Filtro allegati comuni|È possibile abilitare e personalizzare un elenco di tipi di file che si presume siano sempre malware. Per ulteriori informazioni, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)|
|Protezione anti-spyware|La protezione antimalware comprende la protezione antivirus e anti-spyware.|
|Creare criteri di filtro antimalware personalizzati|Per maggiore granularità, è possibile creare criteri per il filtro del malware personalizzati e applicarli a utenti, gruppi o domini specifici della propria organizzazione. I criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma è possibile modificarne il livello di priorità (l'ordine di esecuzione). Per ulteriori informazioni, vedere [Configure anti-malware policies](configure-anti-malware-policies.md).|
|**Indirizzamento della posta e connettori**||
|Routing condizionale della posta|Per ulteriori informazioni, vedere [Scenario: Routing condizionale della posta in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|TLS opportunistico o forzato|Tls opportunistico o forzato è disponibile con i connettori. Tls opportunistico tenta una connessione TLS, ma utilizza una connessione SMTP se la connessione TLS non riesce. Force TLS applica le connessioni TLS, il che significa che il messaggio viene rifiutato se la connessione TLS non riesce. Per ulteriori informazioni su TLS, sicurezza e connettori, vedere [Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Routing per aree (limitazione del flusso di posta a un'area specifica)|Per ulteriori informazioni, vedere la sezione relativa ai datacenter di EOP in [Panoramica su Exchange Online Protection](exchange-online-protection-overview.md).|
|Strumento di controllo della connettività SMTP|Per ulteriori informazioni sull'utilizzo di questo strumento per testare il flusso di posta, vedere [Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).|
|Corrispondenza sottodomini|Per ulteriori informazioni sull'abilitazione del flusso di posta da e verso i sottodomini dei domini accettati, vedere [Flusso di posta in EOP.](mail-flow-in-eop.md)|
|**Regole del flusso di posta**||
|Filtro e azioni basati sui criteri|I criteri personalizzati si basano sulle regole del flusso di posta di Exchange (note anche come regole di trasporto). È possibile filtrare per dominio, parola chiave, nome file, tipo di file, riga dell'oggetto, corpo del messaggio, mittente, destinatario, intestazione e indirizzo IP. Per ulteriori informazioni, vedere [Mail flow rules (transport rules) in Exchange Online Protection.](mail-flow-rules-transport-rules-0.md)|
|Filtro per modelli di testo|Le regole del flusso di posta possono utilizzare una matrice o espressioni regolari per trovare una corrispondenza con il testo. È inoltre possibile utilizzare un'unica stringa o una matrice di stringhe per soddisfare molte proprietà del messaggio, ad esempio indirizzo, oggetto, corpo o nomi degli allegati. Per ulteriori informazioni, vedere [Mail flow rules (transport rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Dizionari personalizzati|Le regole del flusso di posta possono includere lunghi elenchi di testo e parole chiave, fornendo la stessa funzionalità di un dizionario personalizzato.|
|Regole criteri per dominio|L'ambito di una regola del flusso di posta può essere personalizzato in modo da corrispondere ai nomi di dominio del mittente o del destinatario, agli intervalli di indirizzi IP, alle parole chiave o ai modelli degli indirizzi, alle appartenenze ai gruppi e ad altre condizioni.|
|Scansione degli allegati|È possibile creare regole per analizzare il nome del file, l'estensione e i contenuti dell'allegato.|
|Invio di notifiche regole criteri al mittente|È possibile rifiutare i messaggi e inviare un rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito) al mittente tramite l'azione Rifiuta il messaggio con la spiegazione o Rifiuta il messaggio con il codice di stato **avanzato.**  Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Reindirizzare o copiare i messaggi|Le regole del flusso di posta possono reindirizzare, aggiungere destinatari tramite Cc o Ccn, aggiungere semplicemente destinatari e altre opzioni. Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Modificare la priorità delle regole in più regole|Usare l'interfaccia di amministrazione di Exchange per modificare l'ordine di elaborazione delle regole.|
|Filtrare i messaggi e quindi modificare il routing o gli attributi di un messaggio|È possibile filtrare i messaggi in base a una vasta gamma di condizioni e applicare una serie di azioni a ogni messaggio. Per ulteriori informazioni, vedere [Mail flow rules (transport rules) in Exchange Online Protection.](mail-flow-rules-transport-rules-0.md)|
|Modificare il livello di probabilità di posta indesiderata (SCL) di un messaggio in base alla regola.|È possibile esaminare un messaggio in transito e assegnare un livello di probabilità al messaggio di posta indesiderata in base ai criteri scelti. Per ulteriori informazioni, vedere [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).|
|Esaminare gli allegati dei messaggi|È possibile esaminare il contenuto di un allegato o le caratteristiche di un file allegato e definire un'azione da eseguire in base al contenuto rilevato. Per ulteriori informazioni, vedere [Using mail flow rules to inspect message attachments in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)|
|**Amministrazione**||
|Amministrazione basata su Web|Gli amministratori possono gestire il servizio nell'interfaccia di amministrazione di Exchange (EAC), supportata in 60 lingue. Per ulteriori informazioni, vedere [Interfaccia di amministrazione di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)|
|Sincronizzazione della directory|La sincronizzazione della directory è disponibile tramite lo strumento di sincronizzazione di Azure Active Directory. Per ulteriori informazioni, vedere la sezione "Utilizzare la sincronizzazione della directory per gestire gli utenti di posta" in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).  |
|DBEB (Directory Based Edge Blocking)|La funzionalità DBEB consente all'utente di rifiutare messaggi per destinatari non validi nel perimetro della rete di servizi. DBEB consente agli amministratori di aggiungere destinatari abilitati alla posta a Microsoft 365 e di bloccare tutti i messaggi inviati a indirizzi di posta elettronica non presenti in Microsoft 365. Per ulteriori informazioni sulla configurazione di DBEB, vedere [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).|
|PowerShell|La funzionalità EOP completa è disponibile in PowerShell EOP autonomo. Per ulteriori informazioni, vedere [Exchange Online Protection PowerShell.](/powershell/exchange/exchange-online-protection-powershell)|
|**Creazione di rapporti e registrazione**||
|Traccia dei messaggi|Gli amministratori possono seguire i messaggi di posta elettronica mentre passano attraverso il servizio. È possibile determinare se un messaggio di posta elettronica di destinazione è stato ricevuto, rifiutato, rinviato o recapitato dal servizio. Ciò consente all'amministratore di rispondere in modo preciso alle domande dei propri utenti, di risolvere i problemi del flusso di posta elettronica e di convalidare eventuali modifiche apportate ai criteri, riducendo la necessità di rivolgersi al supporto tecnico per assistenza. Per ulteriori informazioni, vedere [Traccia messaggio nel Centro sicurezza e conformità](message-trace-scc.md).|
|Rapporti basati su Web|I report di protezione della posta elettronica nel Centro sicurezza & conformità forniscono dati di messaggistica. Ad esempio, è possibile monitorare la quantità di posta indesiderata e malware rilevata o la frequenza di corrispondenza delle regole del flusso di posta. Grazie a questi rapporti interattivi, è possibile ottenere rapidamente un rapporto visivo dei dati di riepilogo e visualizzare i dettagli dei singoli messaggi, risalendo fino a 90 giorni addietro. Per ulteriori informazioni, vedere [Use mail protection reports to view data about malware, spam, and rule detections](/exchange/monitoring/use-mail-protection-reports).|
|Registrazione di controllo|Il report di un gruppo di ruoli amministratore e il log di controllo di amministratore sono disponibili per gli amministratori di EOP. Per ulteriori informazioni, vedere [Report di controllo in EOP](auditing-reports-in-eop.md).  |
|**Contratti di servizio e supporto**||
|SLA di efficienza spam|\> 99%|
|SLA rapporto falsi positivi|\< 1:250,000|
|SLA rilevamento e blocco dei virus|100% dei virus noti|
|SLA uptime mensili|99.999%|
|Assistenza tecnica telefonica e Web 7 giorni su 7, 24 ore su 24|Per ulteriori informazioni sulle opzioni di supporto e la guida di EOP, vedere [Guida e supporto tecnico per EOP](help-and-support-for-eop.md).|
|**Altre funzionalità**||
|Rete di server globale con ridondanza geografica|EOP viene eseguito in una rete globale di datacenter progettati per offrire la massima disponibilità. Per ulteriori informazioni, vedere la sezione relativa ai datacenter di EOP in [Panoramica su Exchange Online Protection](exchange-online-protection-overview.md).  |
|L'accodamento dei messaggi sul server locale non consente di accettare la posta|I messaggi in differimento rimangono nelle code per un giorno. I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario. In media, l'intervallo tra i tentativi di invio è di 5 minuti. Per ulteriori informazioni, vedere [Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.md).|
|Crittografia dei messaggi di Office 365 disponibile come servizio aggiuntivo|Per ulteriori informazioni, vedere [Crittografia in Office 365](../../compliance/encryption.md).|
|