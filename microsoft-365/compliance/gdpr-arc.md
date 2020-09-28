---
title: Elenchi di controllo di preparazione della conformità al GDPR
description: In questo articolo viene illustrato l'uso degli elenchi di controllo di preparazione della conformità per accedere alle informazioni per l'applicazione del GDPR quando si usano prodotti e servizi Microsoft.
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6952545060a524ef92af6e1e7a063da7091b0860
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214811"
---
# <a name="support-your-gdpr-program-with-accountability-readiness-checklists"></a>Supportare il programma GDPR con elenchi di controllo di preparazione della conformità

Il regolamento generale sulla protezione dei dati (GDPR) introduce nuove regole per le organizzazioni che offrono beni e servizi alle persone che risiedono nell'Unione europea (UE) o che raccolgono e analizzano i dati dei residenti nell'UE in qualunque luogo si trovi l'utente o la sua azienda. Altri dettagli sono disponibili [nell'argomento relativo al Riepilogo sul GDPR](gdpr.md).

## <a name="accountability-readiness-checklists"></a>Elenchi di controllo di preparazione della conformità

Gli elenchi di controllo di preparazione della conformità vengono forniti per accedere in modo pratico alle informazioni necessarie per l'applicazione del GDPR quando si usano prodotti e servizi Microsoft. L'elenco di controllo elenca i potenziali obblighi che possono essere imposti ai sensi del GDPR e indica le informazioni che possono essere usate per supportare la conformità delle organizzazioni.

Esiste una guida specifica per quattro famiglie di prodotti e servizi Microsoft:

- [Office 365](gdpr-arc-Office365.md)
- [Dynamics 365](gdpr-arc-Dynamics365.md)
- [Azure](gdpr-arc-Azure.md)
- [Servizi professionali e supporto tecnico Microsoft](gdpr-arc-prof-services.md)

È possibile gestire gli elementi di questo elenco di controllo con [Compliance Manager](compliance-manager.md) usando il codice e il nome dei controlli nel riquadro del GDPR che comprende i controlli gestiti dai clienti.

Gli elenchi di controllo includono le quattro categorie di base di considerazioni per un programma sulla privacy che supporta il GDPR elencate di seguito, insieme ai requisiti di esempio.

1. Condizioni per la raccolta e l'elaborazione dei dati:

    - Quando si ottiene il consenso?  
    - Identificare e documentare la finalità  
    - Valutazione dell'impatto sulla privacy

2. Diritti del soggetto interessato  

    - Definizione delle informazioni degli interessati  
    - Meccanismo per modificare o revocare il consenso

3. Privacy by design e by default  

    - Limitazione della raccolta  
    - Conformità ai livelli di identificazione  
    - File temporanei

4. Protezione e sicurezza dei dati  

    - Informazioni sull'organizzazione e il contesto  
    - Pianificazione  
    - Criteri di sicurezza delle informazioni

## <a name="customer-agreements"></a>Contratti dei clienti

- **Condizioni dei servizi online**: gli impegni contrattuali di Microsoft in relazione al GDPR sono disponibili nelle [Condizioni dei servizi online](https://go.microsoft.com/fwlink/p/?linkid=2052208).
- **Condizioni dei prodotti Microsoft**: Microsoft estende gli [impegni delle condizioni del GDPR](https://go.microsoft.com/fwlink/p/?linkid=2052213) a tutti i clienti con contratti multilicenza.
- **Addendum per la protezione dei dati**: i servizi Microsoft[ estendono gli impegni ](https://go.microsoft.com/fwlink/p/?linkid=2052215)ai clienti di Microsoft Consulting Services e altri.

## <a name="gdpr-compliance-controls"></a>Controlli per la conformità al GDPR

- **Usare Compliance Manager**: esaminare e incorporare i controlli che Microsoft utilizza per supportare gli obblighi nel GDPR con [Compliance Manager](compliance-manager.md).
- **Mapping di controllo del GDPR**: accedere a un [mapping completo](https://go.microsoft.com/fwlink/p/?linkid=2052220) dei controlli di Microsoft agli obblighi del GDPR.

## <a name="records-of-processing-for-processors"></a>Registri del trattamento per i responsabili del trattamento

Vista l’ampiezza dei servizi online che forniamo in qualità di responsabili del trattamento ai clienti del titolare del trattamento, ci aspettiamo che i clienti identifichino i servizi per i quali cercano i registri del trattamento e che recuperino i log pertinenti negli strumenti online offerti. Un esempio è quello dei registri del trattamento per Azure, in cui ai clienti si richiede di identificare i tipi di attività di trattamento per le quali cercano i registri.

### <a name="azure-logs"></a>Log di Azure

In genere, i clienti sono interessati ai log di attività e, potenzialmente, ai log di diagnostica:

- **Log di attività**: i [log di attività](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) forniscono informazioni dettagliate sulle operazioni eseguite sulle risorse di un abbonamento. I log di attività possono aiutare a determinare l’iniziatore, l'ora di occorrenza e lo stato di un'operazione.
- **Log di diagnostica**: i [log di diagnostica](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) sono tutti i log emessi da ogni risorsa. Questi log includono i log di eventi del sistema di Windows, i log di archiviazione di Azure, i log di controllo di Key Vault e i log di accesso e firewall del gateway applicazione.
- **Archiviazione dei log**: tutti i log di diagnostica scrivono su un account di archiviazione di Azure centralizzato e crittografato per l'archiviazione. Il periodo di conservazione è configurabile dall'utente, fino a 730 giorni, per soddisfare i requisiti di conservazione specifici dell'organizzazione. Questi log si connettono ai log del Monitoraggio di Azure per l’elaborazione, l’archiviazione e la creazione di report tramite dashboard.

### <a name="other-logs"></a>Altri log

Inoltre, le soluzioni di monitoraggio seguenti vengono installate nell’ambito di questa architettura. È responsabilità del cliente configurare queste soluzioni per allinearsi con i controlli di sicurezza FedRAMP:

- [Valutazione AD](https://docs.microsoft.com/azure/azure-monitor/insights/ad-assessment): la soluzione Controllo integrità di Active Directory valuta il rischio e l'integrità degli ambienti server a intervalli regolari e fornisce un elenco con priorità di suggerimenti specifici per l'infrastruttura del server distribuito.
- [Valutazione antimalware](https://docs.microsoft.com/azure/security-center/security-center-services?tabs=features-windows#supported-endpoint-protection-solutions-): report della soluzione antimalware su malware, minacce e stato di protezione.
- [Automazione di Azure](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker): la soluzione Automazione di Azure consente di archiviare, eseguire e gestire runbook.
- [Sicurezza e controllo](https://docs.microsoft.com/azure/security-center/security-center-introduction): il dashboard di Sicurezza e controllo offre una conoscenza di alto livello sullo stato di sicurezza delle risorse, fornendo metriche sui domini di sicurezza, problemi rilevanti, rilevamenti, intelligence sulle minacce e query di sicurezza comuni.
- [Valutazione SQL](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment): la soluzione Controllo integrità di SQL valuta il rischio e l'integrità degli ambienti server a intervalli regolari e fornisce ai clienti un elenco con priorità di suggerimenti specifici per l'infrastruttura del server distribuito.
- [Gestione aggiornamenti](https://docs.microsoft.com/azure/automation/update-management/update-mgmt-overview): la soluzione Gestione aggiornamenti consente ai clienti di gestire gli aggiornamenti della sicurezza dei sistemi operativi, incluso lo stato degli aggiornamenti disponibili e il processo di installazione degli aggiornamenti necessari.
- [Integrità agente](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth): la soluzione Integrità agente indica il numero di agenti distribuiti e la relativa distribuzione geografica, nonché il numero di agenti che non rispondono e il numero di agenti che inviano dati operativi.
- [Log di attività di Azure](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): la soluzione Analisi log attività fornisce supporto per l'analisi dei log attività di Azure in tutti gli abbonamenti ad Azure di un cliente.
- [Rilevamento modifiche](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): la soluzione Rilevamento modifiche consente ai clienti di identificare con facilità le modifiche nell'ambiente.

Per informazioni sulle misure tecniche e di sicurezza per Azure, si consiglia ai clienti del titolare del trattamento di visitare la [Documentazione sulla sicurezza di Azure](https://docs.microsoft.com/azure/security/). Poiché Microsoft non sa se i dati dei clienti sono dati personali o meno, Azure elabora tutti i dati dei clienti come se si trattasse di dati personali, in modo che un cliente possa considerare tutto il materiale rilevante.

### <a name="processor-information"></a>Informazioni sul responsabile del trattamento

Un altro prodotto per il quale potrebbe essere richiesto ai nostri clienti un registro del trattamento per i responsabili del trattamento è Office 365. Per le informazioni relative a Office 365, vedere l’articolo [Ricerca log di controllo nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

È anche possibile vedere le informazioni relative a Dynamics 365 tramite il Centro sicurezza e conformità.  Per visualizzare la pagina del Centro sicurezza e conformità, assicurarsi di avere la licenza corretta. Altre informazioni sulla gestione delle licenze nell’articolo [Descrizione del servizio Centro sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Per cercare gli eventi di Dynamics 365, visitare il log di controllo unificato nel [Centro sicurezza e conformità](https://protection.office.com/unifiedauditlog).

### <a name="professional-services-information"></a>Informazioni su Professional Services 

Per quanto riguarda Professional Services, i dati di supporto di Professional Services sono forniti dal cliente al tecnico del supporto tramite il rappresentante del cliente.  Questo può verificarsi quando un cliente invia una richiesta di servizio attraverso il portale di prodotti online, l'hub servizi o tramite telefono.

Le informazioni vengono archiviate nei sistemi CRM e vengono usate solo per le finalità seguenti:

- Eseguire i Professional Services, inclusa la fornitura di assistenza tecnica, pianificazione professionale, consigli, orientamento, migrazione dei dati, distribuzione e servizi di sviluppo di soluzioni/software.  
- Risoluzione dei problemi (prevenzione, rilevamento, analisi, mitigazione e correzione di problemi, inclusi gli eventi di sicurezza); e 
- Miglioramento costante, per il mantenimento dei Professional Services, tra cui l'installazione degli aggiornamenti più recenti e l’adozione di miglioramenti riguardo all'affidabilità, all'efficacia, alla qualità e alla sicurezza. 

Vista l’ampiezza delle operazioni di supporto, Microsoft gestisce un sistema CRM basato su gruppi di prodotti. I registri del trattamento saranno contenuti all'interno di tali sistemi.
La cronologia dei trattamenti si riflette nei registri mantenuti all’interno dei sistemi CRM.  Nella maggior parte dei casi, la cronologia delle richieste di servizio è disponibile nei portali o nell’hub di servizio.
Per i dettagli specifici che non sono disponibili nei portali o per qualsiasi altra domanda relativa al trattamento dei dati, contattare il responsabile tecnico degli account o contattare il [Supporto tecnico Microsoft](https://support.microsoft.com/contactus/).

## <a name="learn-more"></a>Altre informazioni

- [Centro protezione Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
