---
title: Richieste del soggetto dei dati per l'RGPD in Dynamics 365
description: Guida su come usare i prodotti, i servizi e gli strumenti di amministrazione Microsoft per aiutare i clienti titolari del trattamento dei dati a individuare e gestire i dati personali per rispondere alle richieste degli interessati.
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 72277ec2dfe7681aa5f596e655d5e275bbb64dd1
ms.sourcegitcommit: 5615e790dc53ccc74f3c475ca43d69ca56be348a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2019
ms.locfileid: "36041180"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr"></a>Richieste del soggetto dei dati per l'RGPD in Dynamics 365

Il [Regolamento generale sulla protezione dei dati (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione Europea garantisce alle persone (denominate come *soggetti dei dati* nel regolamento) il diritto di gestire i dati personali raccolti da un datore di lavoro o da un'altra organizzazione o agenzia (definiti come *titolari del trattamento dei dati* o semplicemente *titolari*). I dati personali sono descritti nell'RGPD come dati che si riferiscono a una persona fisica identificata o identificabile. L'RGPD garantisce ai soggetti dei dati diritti specifici sui propri dati personali; tali diritti includono la possibilità di ottenere delle copie dei dati personali, richiedere di apportare delle modifiche ai dati, limitare il trattamento dei dati, eliminarli o riceverli in un formato elettronico affinché possano essere trasferiti a un altro titolare. Una richiesta formale di un soggetto dei dati rivolta a un titolare in merito a un'operazione da effettuare sui propri dati personali è denominata *Richiesta DSR* (Data Subject Rights, Diritti del soggetto dei dati) o DSR.

La guida descrive come utilizzare i prodotti, i servizi e gli strumenti di amministrazione Microsoft per aiutare i nostri clienti titolari del trattamento dei dati a individuare e gestire i dati personali per rispondere alle richieste degli interessati. In particolare, ciò include come identificare, accedere e usare i dati personali che risiedono nel cloud Microsoft. Ecco una rapida panoramica dei processi descritti in questa guida:

- **Individuazione**: usare gli strumenti di ricerca e individuazione per trovare più facilmente i dati dei clienti che potrebbero essere oggetto di una richiesta dell'interessato. Dopo aver raccolto dei documenti potenzialmente reattivi, è possibile eseguire una o più delle azioni DSR descritte nella seguente procedura per rispondere alla richiesta. In alternativa, si può determinare che la richiesta non soddisfa le linee guida dell'organizzazione relative alla risposta alle richieste degli interessati.
- **Accesso:** recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, crearne una copia che può essere disponibile per l'interessato.
- **Rettifica:** apportare modifiche o implementare le azioni richieste sui dati personali, ove applicabile.
- **Limitazione**: limitare il trattamento dei dati personali, rimuovendo le licenze per vari servizi online o disattivando i servizi desiderati, dove possibile.
- **Eliminazione:** rimuovere in modo definitivo i dati personali che risiedono nel cloud Microsoft.
- **Esportazione:** fornire all'interessato una copia elettronica dei dati personali in un formato leggibile in modo automatizzato.

Ogni sezione di questa guida illustra le procedure tecniche che un'organizzazione titolare del trattamento dei dati può adottare per rispondere a una richiesta DSR per i dati personali nel cloud Microsoft

### <a name="gdpr-terminology"></a>Terminologia del GDPR

Di seguito vengono fornite le definizioni dei termini importanti nella presente guida:

- **Titolare:** la persona fisica o giuridica, l'autorità pubblica, l'agenzia o altro ente che, autonomamente o unitamente ad altri soggetti, determina gli obiettivi e i mezzi del trattamento dei dati personali; laddove gli obiettivi e i mezzi di tale trattamento sono determinati da una normativa europea o di uno specifico Stato membro dell'UE, il titolare del trattamento dei dati o i criteri specifici per la sua designazione potrebbero essere forniti da tale normativa europea o di uno specifico Stato membro dell'UE.
- **Dati personali e interessato:** qualsiasi informazione relativa a una persona fisica identificata o identificabile (“interessato”); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, tramite dati specifici come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica.
- **Responsabile:** una persona fisica o giuridica, un'autorità pubblica o altro ente che si occupa del trattamento dei dati personali per conto del titolare.
- **Dati del cliente:** tutti i dati, compresi file di testo, audio, video o immagini e software, forniti a Microsoft dal cliente o per suo conto attraverso i servizi aziendali. I dati dei clienti includono (1) informazioni che consentono l'identificazione personale degli utenti finali (ad esempio, nomi utente e informazioni di contatto in Azure Active Directory) e contenuti per i clienti che un cliente stesso carica o crea in servizi specifici (ad esempio, contenuti per i clienti in un account di archiviazione di Azure, contenuti per i clienti in un database SQL di Azure o un'immagine della macchina virtuale di un cliente in Macchine virtuali di Azure).
- **Log generati dal sistema:** i log e i dati correlati generati da Microsoft che consentono a Microsoft di offrire servizi aziendali agli utenti. I log generati dal sistema contengono principalmente dati presentati con l'uso di pseudonimi come un identificatore univoco, in genere un numero generato dal sistema che non può identificare individualmente una singola persona ma viene usato per fornire servizi aziendali agli utenti. I log generati dal sistema possono anche contenere informazioni identificabili riguardanti gli utenti finali, ad esempio un nome utente.

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>Come questa guida consente di adempiere alle proprie responsabilità di titolare del trattamento dei dati

La guida, suddivisa in due parti, descrive come usare prodotti, servizi e strumenti di amministrazione di Dynamics 365 per aiutare l'utente a individuare e gestire i dati nel cloud Microsoft per rispondere alle richieste degli interessati che esercitano i diritti previsti dal GDPR. La prima parte riguarda i dati personali inclusi nei dati del cliente e la seconda parte riguarda altri dati personali con pseudonimi acquisiti nei log generati dal sistema.

- **Parte 1: rispondere alle richieste degli interessati relative ai dati personali, inclusi i dati del cliente.** La parte 1 di questa guida spiega come accedere, risolvere, limitare, eliminare ed esportare i dati personali da applicazioni di Dynamics 365 (software-as-a-service), elaborati come parte dei dati del cliente forniti al servizio online.
- **Parte 2: rispondere alle richieste DSR per dati con pseudonimi.** Quando si usano servizi aziendali Dynamics 365, Microsoft genera alcune informazioni (denominate in questo documento come *log generati dal sistema*) per fornire il servizio, che è limitato al footprint di utilizzo lasciato dall'utente finale per identificare le azioni nel sistema. Sebbene questi dati non possano essere attribuiti a un soggetto dei dati specifico senza l'ausilio di informazioni aggiuntive, alcuni possono essere considerati personali in base all'RGPD. La parte 2 di questa guida spiega come accedere, eliminare ed esportare i log generati dal sistema creati da Dynamics 365.

### <a name="preparing-for-data-subject-rights-investigations"></a>Preparazione per indagini sui diritti degli interessati.

Quando gli interessati esercitano i propri diritti ed effettuano richieste, considerare quanto segue:

- Identificare correttamente la persona e il ruolo (ad esempio se si tratta di un dipendente, cliente o fornitore) attraverso le informazioni fornite dall'interessato durante la richiesta. Tali informazioni potrebbero essere un nome, un ID dipendente, un numero cliente o altro identificatore.
- Registrare i dati e l'ora della richiesta (sono disponibili 30 giorni per completare la richiesta).
- Dichiarare che la richiesta soddisfa i requisiti dell'organizzazione nel rispettare o rifiutare una richiesta dell'interessato. Ad esempio, assicurarsi che l'esecuzione della richiesta non sia in conflitto con altri obblighi legali, normativi o finanziari e che non pregiudichi i diritti e la libertà altrui.
- Verificare di disporre delle informazioni relative alla richiesta.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Parte 1: rispondere alle richieste degli interessati relative ai dati personali inclusi nei dati del cliente

Negli articoli seguenti sono disponibili informazioni che consentono di pianificare e rispondere alle richieste degli interessati relative ai dati personali inclusi nei dati del cliente elaborati in Dynamics 365. È importante tenere presente che i dati personali possono essere presenti in altre categorie di dati elaborati da Microsoft nel corso del servizio di una sottoscrizione a servizi online (ad esempio i dati dell'amministratore o del supporto definiti nell'informativa sulla privacy di Microsoft). Questo documento si limita a fornire supporto per l'individuazione e la gestione delle richieste degli interessati che riguardano i dati personali presenti nei dati del cliente forniti a Dynamics 365.

Dynamics 365 è un servizio online che offre più funzioni di elaborazione dati di un software sotto forma di software come servizio (SaaS). Di conseguenza, Dynamics 365 offre un'ampia gamma di funzionalità per l'elaborazione di ampie raccolte di dati, che possono variare in base alla natura, allo scopo o ad altri attributi specifici (ad esempio, dati delle vendite, transazioni, contabilità, informazioni delle risorse umane e così via). Alla luce di tali varietà, Dynamics 365 offre più moduli, campi, schemi, endpoint e logica per elaborare i dati del cliente, che rispecchiano i vari modi in cui le richieste degli interessati possono essere rivolte a ogni applicazione. In questa guida è possibile osservare i diversi modi per soddisfare le specifiche richieste degli interessati, selezionando le descrizioni tecniche di ogni applicazione Dynamics 365.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Trovare i dati del cliente

Il primo passaggio per rispondere a una richiesta dell'interessato consiste nel cercare e identificare i dati del cliente che costituiscono l'oggetto della richiesta.

Per usare i dati personali presenti nelle applicazioni di lavoro in Dynamics 365 - Customer Engagement, è importante classificarli correttamente. Dynamics 365 - Customer Engagement offre la flessibilità necessaria per creare un'estensione dell'applicazione relativa alla classificazione dei dati. Una corretta classificazione consente di identificare le informazioni come dati personali, facilitandone l'individuazione e il recupero durante le operazioni di risposta alle richieste degli interessati. Può anche essere utile per esigenze di conformità a requisiti normativi sulla raccolta e gestione dei dati personali.

Microsoft offre funzionalità che possono essere utili per rispondere alle richieste degli interessati e per accedere ai dati del cliente. Tuttavia, spetta dell'utente assicurare che i dati personali siano collocati e classificati in modo appropriato.

***Dynamics 365 for Customer Engagement*** offre diversi metodi per cercare dati personali nei record, ad esempio: ricerca avanzata, ricerca per pertinenza e ricerca per record. Tutte queste funzioni consentono di identificare (trovare) i dati personali.

- [Ricerca avanzata](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [Ricerca per pertinenza](https://docs.microsoft.com/dynamics365/customer-engagement/basics/relevance-search-results), che può essere salvata per riferimento futuro tramite Ricerca per pertinenza dashboard, che può essere salvata per riferimento futuro tramite dashboard
- [Ricerca per record](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) tra più tipi di record

In Dynamics 365 for Marketing, sono disponibili le seguenti funzionalità aggiuntive:

1. [Creare report Power BI](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) per filtrare e identificare i dati del cliente.
2. Utilizzare Insight Views su contatti e oggetti di esecuzione marketing per identificare punti dati aggiuntivi che possono contenere i dati del cliente.

***Dynamics 365 Customer Service Insights*** offre un elenco di risorse utili per [trovare i dati del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery) e rispondere alle richieste dei clienti relative al GDPR. 

***Dynamics 365 for Finance and Operations*** offre diversi modi per cercare i dati del cliente. In qualità di amministratore tenant è possibile effettuare le seguenti operazioni per cercare i dati del cliente:

- Organizzare i dati del cliente al fine di poter individuare rapidamente i dati personali. A tale scopo, vedere [come classificare l'inventario dati](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory).
- Usare il [rapporto di ricerca persone](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) per trovare e raccogliere dati personali dell'utente.
- [Estendere il rapporto di ricerca persone](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) creando una nuova entità o estendendone una esistente.
- Usare le funzionalità di ricerca e filtro per trovare dati personali specifici ed esportarli tramite la funzionalità di esportazione di Microsoft Office o stampare le informazioni in un PDF con le estensioni del browser.
- Creare un modulo personalizzato che consente di individuare ed esportare i dati personali.
- Creare un portale esterno o sito Web che consente a un cliente autenticato di visualizzare i propri dati personali.

***Dynamics 365 Business Central*** offre diversi modi per cercare i dati del cliente. Per informazioni dettagliate, vedere [Ricerca, filtro e ordinamento di dati](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters).

***Dynamics 365 for Talent*** fornisce funzionalità di ricerca avanzata e filtro per trovare dati personali, mentre la funzionalità di esportazione di Microsoft Office consente di esportare o stampare le informazioni in un PDF con le estensioni del browser.

- Usare il [rapporto di ricerca persone](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) per trovare e raccogliere i dati del cliente.
- [Estendere il rapporto di ricerca persone](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) creando una nuova entità o estendendone una esistente.

### <a name="providing-a-copy-of-customer-data"></a>Fornire una copia dei dati dei clienti

I dati del cliente in ***Dynamics 365 for Customer Engagement*** possono essere esportati usando le funzionalità complete di esportazione entità. I dati del cliente possono essere esportati in un file di Excel statico per facilitare una richiesta di portabilità dei dati. Con Excel è possibile modificare i dati personali da includere nella richiesta di portabilità e quindi salvarli in un formato leggibile di uso comune, ad esempio .csv o .xml.

Inoltre, per Dynamics 365 for Marketing è fornita un'[API dedicata](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) che consente ai clienti di creare estensioni che permettono di recuperare record aggiuntivi di interazioni cliente acquisite che possono contenere dati personali. L'API carica tutte le informazioni pertinenti dal sistema di back-end e le assembla in un unico documento portatile.

***Dynamics 365 Customer Service Insights*** consente di [fornire una copia dei dati del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) usando l'esportazione dei dati.

I dati del cliente in ***Dynamics 365 for Finance and Operations*** possono essere esportati usando le funzionalità complete di esportazione entità. Con le [*entità di gestione e integrazione dei dati*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), gli amministratori tenant possono usare entità disponibili, crearne di nuove o estendere le entità esistenti per un'esportazione dei dati personali in Excel ripetibile o per numerosi altri formati comuni con [*processi di importazione ed esportazione dati*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  In alternativa, molti elenchi possono essere esportati in un file di Excel statico per facilitare una richiesta di portabilità dei dati. Quando i dati del cliente vengono esportati in Excel, è possibile modificare i dati personali da includere nella richiesta di portabilità e quindi salvare il file in un formato leggibile di uso comune, ad esempio .csv o .xml. È inoltre possibile disabilitare il *rapporto di ricerca persone* per fornire agli interessati i dati che sono stati classificati come dati personali.

In ***Dynamics 365 - Business Central*** è possibile usare due caratteristiche per inviare una copia dei dati del cliente all'interessato:

È possibile esportare i dati del cliente in un file di Excel. In Excel è possibile modificare i dati del cliente da includere nella richiesta di portabilità e salvarli in un formato leggibile di uso comune, ad esempio .csv o .xml. Per informazioni dettagliate, vedere [Esportazione dei dati aziendali in Excel](https://docs.microsoft.com/it-IT/dynamics365/business-central/about-export-data).

In ***Dynamics 365 for Talent***, è possibile utilizzare [Estendere il rapporto di ricerca persone](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) per raccogliere informazioni per una richiesta di una copia dei dati personali dell'interessato.

### <a name="rectifying-customer-data"></a>Rettificare i dati del cliente

***Dynamics 365 for Customer Engagement*** offre i seguenti metodi per correggere i dati del cliente incompleti o non corretti o per cancellarli:

- Cercare i dati del cliente tramite le funzionalità descritte in "Ricerca di dati del cliente" e modificare direttamente i dati nei moduli Customer Engagement. Le modifiche possono essere eseguite a livello di riga singola oppure si possono modificare direttamente più righe.
- Modificare più record Customer Engagement in blocco tramite il componente aggiuntivo di Microsoft Office per esportare i dati in Microsoft Excel, apportare le modifiche desiderate e quindi importare i dati modificati da Excel in Dynamics 365 for Customer Engagement.

Inoltre, per Dynamics 365 for Marketing è anche possibile:

- Aggiornare i dati personali nella pagina di destinazione, modificando direttamente una o più righe
- Preparare una pagina di [centri di sottoscrizione](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) contenente tutti i campi di contatto modificabili che possono essere inclusi. In questo modo gli utenti finali possono aggiornare le proprie informazioni il più possibile.

***Dynamics 365 Customer Service Insights*** offre inoltre alle organizzazioni le funzionalità per [rettificare o modificare i dati del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary#a=note-about-requests-to-rectify-personal-data).

In ***Dynamics 365 for Finance and Operations***, è inoltre possibile usare [*strumenti di personalizzazione*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), ma la decisione e l'implementazione spettano comunque all'utente.

***Dynamics 365 Business Central*** offre due modi per correggere i dati del cliente che sono incompleti o non corretti.

Per una rapida modifica in blocco di più record Business Central, esportare gli elenchi in Excel con il [componente aggiuntivo di Excel per Business Central](https://docs.microsoft.com/it-IT/dynamics365/business-central/finance-analyze-excel#the--excel-add-in), correggere più record e quindi pubblicare i dati modificati da Excel in Business Central. Per informazioni dettagliate, vedere [Esportazione dei dati aziendali in Excel](https://docs.microsoft.com/it-IT/dynamics365/business-central/about-export-data).

È possibile modificare i dati del cliente archiviati in un campo, ad esempio le informazioni relative a un cliente nella scheda del cliente, modificando manualmente l'elemento dati che contiene dati personali di destinazione. Per informazioni dettagliate, vedere [Immissione di dati](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Breve nota sulla modifica delle voci nelle transazioni commerciali

I record di transazione, ad esempio le voci generali, del cliente e dei documenti fiscali, sono essenziali per l'integrità di un sistema di pianificazione delle risorse dell'organizzazione. I dati personali che fanno parte della transazione finanziaria o di altro tipo resteranno "così come sono" in conformità alle leggi finanziarie (ad esempio, alle norme fiscali), alla politica di prevenzione delle frodi (ad esempio, controllo di sicurezza) o alle certificazioni di settore. Di conseguenza, Dynamics 365 for Finance and Operations e Dynamics 365 Business Central limitano la modifica dei dati in tali record.

Archiviando dati personali nei record di transazione aziendali, l'unico modo per correggere, eliminare o limitare l'elaborazione dei dati personali per soddisfare la richiesta del soggetto dei dati è quello di usare le [funzionalità di personalizzazione](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index) di Dynamics 365 Business Central. [](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)La decisione di soddisfare una richiesta di modifica dei dati dell'interessato e la successiva implementazione è di responsabilità dell'utente.

### <a name="restricting-the-processing-of-customer-data"></a>Limitazione del trattamento dei dati del cliente

Quando si riceve una richiesta da un interessato volta a limitare l'elaborazione dei dati del cliente, è possibile estrarre facilmente i dati del cliente dal servizio online e archiviarli in un contenitore separato (ad esempio in un archivio locale o in un servizio di Web separato con funzionalità di isolamento dei dati) e isolato dalle funzioni di elaborazione fornite dalle applicazioni cloud.

È disponibile un meccanismo alternativo, ad esempio il blocco di elaborazione dei dati di ***Dynamics 365 Business Central***, in cui gli utenti possono bloccare i record dello specifico interessato. Per informazioni dettagliate, vedere [Limitazione dell'elaborazione dei dati per un oggetto dati](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Quando un record è contrassegnato come bloccato, Dynamics 365 Business Central sospende l'elaborazione dei dati del cliente dell'interessato. Non è possibile creare nuove transazioni con un record bloccato, ad esempio, non è possibile creare una nuova fattura per un cliente, quando il cliente o l'agente di vendita è bloccato.

### <a name="deleting-customer-data"></a>Eliminare i dati del cliente

Quando un interessato chiede di eliminare i dati del cliente, esistono diversi modi per eseguire questa operazione:

- Modificare più record Dynamics 365 in blocco tramite il componente aggiuntivo di Microsoft Office per esportare i dati in Microsoft Excel, apportare le modifiche desiderate e quindi importare di nuovo i dati modificati da Excel nel servizio online.
- È possibile eliminare i dati del cliente archiviati in un campo qualsiasi, individuando i dati da eliminare ed eliminando manualmente l'elemento dati che contiene i dati del cliente di destinazione, ad esempio eliminando definitivamente il record del contatto che rappresenta l'interessato e altri record che contengono dati personali

Inoltre, in Dynamics 365 for Marketing, l'eliminazione di un contatto garantisce che vengano rimossi anche i dati di interazione con le informazioni personali. Per i campi o le entità personalizzate, è necessario personalizzare il sistema per assicurarsi che elimini tutti i dati del cliente dai record correlati e/o li scolleghi dal record del contatto in modo che tutte le informazioni personali vengano rimosse. Per altre informazioni, vedere la [guida per sviluppatori (marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

***Dynamics 365 Customer Service Insights*** offre inoltre alle organizzazioni funzionalità per [eliminare i dati del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete).

In alternativa, in ***Dynamics 365 for Finance and Operations*** è possibile usare [*strumenti di personalizzazione*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page) per cancellare e modificare i dati del cliente.

Quando in ***Dynamics 365 Business Central*** un interessato chiede di eliminare i propri dati personali inclusi nei dati del cliente, esistono diversi modi per soddisfare questa richiesta:

- Per una rapida modifica in blocco di più record Business Central, esportare i dati in Excel con il [componente aggiuntivo di Excel per Business Central](https://docs.microsoft.com/it-IT/dynamics365/business-central/finance-analyze-excel#the--excel-add-in), eliminare più record e quindi pubblicare le modifiche da Excel di nuovo in Business Central. Per informazioni dettagliate, vedere [Esportazione dei dati aziendali in Excel](https://docs.microsoft.com/it-IT/dynamics365/business-central/about-export-data).
- È possibile eliminare i dati del cliente archiviati in un campo qualsiasi, eliminando manualmente l'elemento dati che contiene i dati del cliente di destinazione. Per informazioni dettagliate, vedere [Immissione di dati](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- È possibile eliminare i dati del cliente direttamente, ad esempio eliminando un contatto e quindi eseguendo il processo batch Delete Canceled Interaction Log Entries per eliminare le interazioni di quel contatto.
- È possibile [eliminare documenti](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents) contenenti dati del cliente, ad esempio note e fatture di acquisto e vendita pubblicate.

Oltre all'eliminazione in blocco o individuale di record distinti, tenere presente che solo gli utenti che hanno cessato la collaborazione possono essere eliminati completamente da ***Dynamics 365 for Talent***. [Seguire la procedura riportata di seguito per eliminare gli utenti che hanno cessato la collaborazione](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Esportazione dei dati del cliente

Per rispondere a una richiesta di portabilità dei dati, è possibile esportare i dati del cliente in ***Dynamics 365 for Customer Engagement*** usando le funzionalità complete di esportazione entità. I dati del cliente possono essere esportati in un file di Excel statico per facilitare una richiesta di portabilità dei dati. Con Excel è possibile modificare i dati personali da includere nella richiesta di portabilità e quindi salvarli in un formato leggibile di uso comune, ad esempio .csv o .xml.

Inoltre, per Dynamics 365 for Marketing è fornita un'[API dedicata](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) che consente ai clienti di creare estensioni che permettono di recuperare record aggiuntivi di interazioni cliente acquisite che possono contenere dati personali. L'API carica tutte le informazioni pertinenti dal sistema di back-end e le assembla in un unico documento portatile.

Per ***Dynamics 365 Customer Service Insights*** è possibile [esportare i dati del cliente](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) usando il portale di gestione di Azure.

***Dynamics 365 for Finance and Operations*** offre [entità di gestione e integrazione dei dati](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity) che consentono di usare entità disponibili, entità appena create o entità estese per un'esportazione dei dati personali in Excel ripetibile o per numerosi altri formati comuni usando [processi di importazione ed esportazione dati](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  In alternativa, molti elenchi possono essere esportati in un file di Excel statico per facilitare una richiesta di portabilità dei dati. Quando i dati del cliente vengono esportati in Excel in questo modo, è possibile modificare i dati personali da includere nella richiesta di portabilità e quindi salvare il file in un formato leggibile di uso comune, ad esempio .csv o .xml.

Dynamics 365 for Finance and Operations e ***Dynamics 365 for Talent*** offrono il rapporto di ricerca persone per fornire dati ai soggetti dei dati classificati come dati personali. 

***Dynamics 365 Business Central*** offre le caratteristiche seguenti:

- È possibile esportare i dati del cliente in un file di Excel. In Excel è possibile modificare i dati del cliente da includere nella richiesta di portabilità e salvarli in un formato leggibile di uso comune, ad esempio .csv o .xml. Per informazioni dettagliate, vedere [Esportazione dei dati aziendali in Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- È possibile esportare i dati del cliente in un file di Excel. In Excel è possibile modificare i dati del cliente da includere nella richiesta di portabilità e salvarli in un formato leggibile di uso comune, ad esempio .csv o .xml. Per informazioni dettagliate, vedere [Esportazione dei dati aziendali in Excel](https://docs.microsoft.com/it-IT/dynamics365/business-central/about-export-data).

### <a name="microsoft-social-engagement"></a>Microsoft Social Engagement

Poiché Microsoft Social Engagement elabora dati personali disponibili nei dati del cliente e nel contenuto di social networking, questa applicazione offre un solo modo per rispondere alle richieste degli interessati, in quanto si riferisce a dati personali recuperati da social network. Il contenuto di social networking è contenuto disponibile pubblicamente e raccolto dalle reti di supporti di social networking (come Twitter, Facebook e YouTube) e dai servizi di indicizzazione e aggregazione dei dati in risposta alle query di ricerca eseguite dal cliente in Microsoft Social Engagement. Il contenuto di social networking non fa parte dei dati del cliente. Altre limitazioni relative all'elaborazione, all'utilizzo e all'archiviazione del contenuto di social networking sono descritte nelle condizioni dei Microsoft Online Services.

### <a name="finding-personal-data"></a>Trovare i dati personali

Il primo passaggio nell'operazione di risposta a una richiesta del soggetto dei dati è quello di cercare e identificare i dati personali oggetto di tale richiesta. Microsoft Social Engagement archivia i dati seguenti:

#### <a name="for-social-media-users"></a>Per gli utenti di supporti di social networking

- Dati dell'utente di supporti di social networking (cui si fa riferimento come *autore* in Social Engagement) che Social Engagement acquisisce da piattaforme di social networking. Possono includere nome, nome utente, immagine del profilo, posizione, sito Web e biografia se specificati dall'autore.
- Tag autore usati per raggruppare e classificare gli autori, ad esempio opinionisti, concorrenti o fan.

#### <a name="for-employees"></a>Per i dipendenti

- Profili utente che includono nome del dipendente, informazioni di contatto e immagine del profilo e che sono gestiti in Office 365.
- Indirizzi di posta elettronica forniti da dipendenti che hanno creato avvisi post e di tendenza.
- Account di supporti di social networking (cui si fa riferimento come *profili di social networking* in Social Engagement) autenticati in Social Engagement da dipendenti per comunicare con altri utenti su una piattaforma di social networking. Possono essere a disposizione di un dipendente o dell'organizzazione e includere dati che i dipendenti forniscono quando registrano un account su una piattaforma di social networking. Tali profili rappresentano l'organizzazione sui supporti di social networking e sono utilizzati per interagire con i post per conto dell'organizzazione dall'applicazione Social Engagement.
- I nomi utente in Power BI se l'organizzazione usa il [pacchetto di contenuto Social Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) affinché Power BI analizzi le prestazioni del team su supporti di social networking.

Questa prima fase (individuazione e analisi dei dati personali in questione) consente di determinare se la richiesta dell'interessato soddisfa i requisiti dell'organizzazione per accettarla o rifiutarla. Ad esempio, dopo aver individuato e analizzato i dati personali, si potrebbe stabilire che la richiesta non soddisfa i requisiti dell'organizzazione perché potrebbe ledere i diritti e le libertà altrui.

#### <a name="social-media-users-authors"></a>Utenti di supporti di social networking (autori)

- Per individuare i dati personali, eseguire i primi quattro passaggi descritti in [Individuare ed eliminare un autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#find-and-delete-an-author).
- I dipendenti possono creare regole Social Engagement che eseguono ricerche su piattaforme di social networking per alcuni contenuti definiti; tali regole di ricerca possono contenere i nomi degli autori. Per assicurarsi di individuare queste regole, esaminare le regole di ricerca di account di social networking per l'account appropriato, ad esempio [Twitter](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-twitter-rule), [Instagram](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-an-instagram-rule) e [YouTube](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-includetnyoutubeincludestn-youtubemd-rule).
- Per trovare i tag autore, prima di tutto [filtrare i post](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/use-filters#add-edit-or-remove-a-filter) per [autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/understand-filters#authors), quindi [visualizzare i tag autore](https://go.microsoft.com/fwlink/?linkid=864795).

##### <a name="your-employees"></a>I dipendenti

Per individuare:

- Un profilo utente, vedere l'[interfaccia di amministrazione](https://portal.office.com/adminportal/home). Nell'**interfaccia di amministrazione** selezionare **Utenti**. Nella pagina **Utenti attivi** cercare l'utente nell'elenco. In Social Engagement, andare in **Impostazioni \> Gestione utenti** per visualizzare le informazioni sincronizzate automaticamente da Office 365.
- Il destinatario di un avviso, eseguire i primi due passaggi descritti in [Gestire i destinatari degli avvisi come amministratore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).
- I dati del profilo social immessi dai dipendenti, andare in **Impostazioni \> Profili social**. (Per ulteriori informazioni, vedere [Gestire profili social](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles).)
- I nomi utente in Power BI, aprire il dashboard Power BI di Social Engagement e filtrare per nome del dipendente.

### <a name="providing-a-copy-of-personal-data"></a>Fornire una copia dei dati personali

L'RGPD garantisce ai soggetti dei dati il diritto di ottenere una copia dei dati personali su richiesta. Dopo aver individuato i contenuti del cliente contenenti dati che potrebbero rispondere alla richiesta, spetta all'utente e all'organizzazione decidere se fornirne una copia al soggetto dei dati.

#### <a name="social-media-users-authors"></a>Utenti di supporti di social networking (autori)

- Per esportare i dati personali degli autori, seguire la procedura descritta in [Esportare le informazioni sull'autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) per esportare i dati in un file Excel.
- Per estrarre i tag autore aggiunti a un autore specifico, è possibile [esportare i dati dei tag autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data).

##### <a name="your-employees"></a>I dipendenti

Per esportare:

- i dati del cliente dai profili utente, vedere l'[Interfaccia di amministrazione](https://portal.office.com/adminportal/home). Nell'**interfaccia di amministrazione** selezionare **Utenti**. Nella pagina **Utenti attivi**, cercare l'utente di cui si vogliono esportare i dati. Eliminare tutti gli utenti tranne l'utente di destinazione e quindi selezionare **Esporta** per esportare i dati in un file CSV in cui è possibile utilizzare Excel per visualizzare le informazioni.
- Indirizzi di posta elettronica del destinatario di un avviso (solo i dati del cliente di un avviso). Seguire la procedura descritta in [Gestire i destinatari degli avvisi come amministratore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Selezionare **Esporta** per scaricare un elenco Excel degli avvisi che includono questo destinatario.
- I nomi utente di Power BI: [creazione di report in Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) mostra i nomi utente nei report sulle prestazioni del team sui supporti di social networking. Per esportare i dati, filtrare per utente nel dashboard di PowerBI o [report](https://docs.microsoft.com/power-bi/power-bi-report-add-filter) ed [esportare i dati](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data).

### <a name="rectifying-personal-data"></a>Rettificare i dati personali

Per correggere dati personali incompleti o inesatti:

#### <a name="social-media-users-authors"></a>Utenti di supporti di social networking (autori)

- È necessario chiedere al proprietario (autore) dei dati di apportare modifiche alla piattaforma di social networking (ad esempio Twitter, WordPress o Tumblr). Il soggetto dei dati è proprietario dei dati nell'account del supporto di social networking, pertanto è l'unico che può modificarli. Quando l'autore effettua la modifica, Social Engagement sincronizza automaticamente i dettagli modificati.
- Tag autore, seguire la procedura descritta in [Modificare tag autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#change-author-tags).

##### <a name="your-employees"></a>Dipendenti

- I profili utente: per apportare modifiche ai dati del cliente in un profilo utente, vedere [Cambiare un nome utente e un indirizzo di posta elettronica in Office 365](https://support.office.com/article/change-a-user-name-and-email-address-in-office-365-fb5ac074-e203-4e1f-9843-b9d1a3e03297) e [Aggiungere la foto del profilo in Office 365](https://support.office.com/article/add-your-profile-photo-to-office-365-2eaf93fd-b3f1-43b9-9cdc-bdcd548435b7). Le modifiche vengono sincronizzate automaticamente in Social Engagement. Per individuarle, passare a **Impostazioni** \> **Gestione utenti**.

- Destinatari degli avvisi: è possibile [modificare un avviso](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#change-an-alert).

### <a name="restricting-the-processing-of-personal-data"></a>Limitazione del trattamento dei dati personali

#### <a name="social-media-users-authors"></a>Utenti di social media (autori)

Per interrompere l'elaborazione dei dati del cliente di autori in Social Engagement, [eliminare l'autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).

Ciò bloccherà l'elaborazione futura dei dati di questo soggetto dei dati e tutti i post futuri, inoltre eliminerà tutti i dati relativi e creati da questo autore. Ogni volta che Social Engagement acquisisce nuovi post, controlla automaticamente se l'autore è stato eliminato in precedenza ed elimina i post degli autori eliminati. Ciò non ha alcun effetto sull'account utente della piattaforma di social networking.

##### <a name="your-employees"></a>I dipendenti

- Per interrompere l'elaborazione dei dati del cliente di dipendenti, è possibile [rimuoverne la licenza](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1) in Office 365. Ciò consente di eliminare tutti gli elementi relativi a Social Engagement, ad esempio i ruoli utente e i profili, tutte le impostazioni personalizzate definite dall'utente, avvisi, mappe di attività e flussi. Gli argomenti di ricerca e i profili social non vengono eliminati (gli amministratori ereditano la proprietà dei profili social degli utenti eliminati e possono eliminarli su richiesta).
- Per impedire l'invio di messaggi di avviso tramite posta elettronica, è possibile rimuovere un indirizzo di posta elettronica da tutti gli avvisi cui questo è stato aggiunto, seguendo la procedura descritta in [Gestire i destinatari degli avvisi come amministratore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).

### <a name="deleting-personal-data"></a>Eliminazione dei dati personali

L'RGPD garantisce ai soggetti dei dati il diritto di richiedere al titolare l'eliminazione dei dati personali in alcune circostanze. Il "diritto di essere dimenticato" tramite la rimozione di tali dati da un'organizzazione è un fattore di protezione chiave nell'RGPD.

#### <a name="social-media-users-authors"></a>Utenti di supporti di social networking (autori)

Per eliminare definitivamente tutti i dati personali dell'autore in Social Engagement, eliminare l'intero profilo social dell'autore. Vedere [](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors)[Eliminare un autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author).  

Una volta eseguita questa operazione, non vi è modo di annullarla. Verranno eliminati tutti i dati relativi e creati da questo autore su Social Engagement e ciò bloccherà l'elaborazione futura dei dati di questo soggetto dei dati e tutti i post futuri. Ogni volta che Social Engagement acquisisce nuovi post, controlla automaticamente se l'autore è stato eliminato in precedenza ed elimina i post degli autori eliminati. Ciò non ha alcun effetto sull'account utente della piattaforma di social networking.

Per eliminare i tag autore, vedere [Rimuovere tag autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#remove-author-tags).

>[!NOTE]
>Se viene chiesto di rimuovere le informazioni di un autore specifico, è consigliabile verificare l'identità dell'autore per convalidare la richiesta. Per verificare l'identità, è possibile richiedere un messaggio privato dall'autore dal suo account di social networking.

Social Engagement ha implementato feed di conformità da diverse piattaforme di social networking (ad esempio Twitter, WordPress, Tumblr) per agire sui segnali come l'eliminazione di post attivata direttamente sulle piattaforme di social networking. Questa caratteristica viene attivata automaticamente con tutte le installazioni di Social Engagement e non richiede l'intervento dell'utente. Social Engagement fornisce inoltre un meccanismo che consente a servizi (come ad esempio Dynamics 365 for Customer Engagement) basati su contenuto di social networking di Customer Engagement di ereditare i segnali.

##### <a name="your-employees"></a>I dipendenti

Per eliminare definitivamente tutti i dati del cliente di un dipendente, è possibile [rimuoverne la licenza](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1) in Office 365.

- Ciò consente di eliminare tutti gli elementi relativi a Social Engagement, ad esempio i ruoli utente e i profili, tutte le impostazioni personalizzate definite dall'utente, avvisi, mappe di attività e flussi. Gli argomenti di ricerca e i profili social non vengono eliminati (gli amministratori ereditano la proprietà dei profili social degli utenti eliminati e possono eliminarli su richiesta).
- Le modifiche vengono sincronizzate automaticamente in Social Engagement. Per individuarle, passare a **Impostazioni \> Gestione utenti**.
- Quando vengono eliminati i dati personali, le voci del dipendente in un report di Engagement di PowerBI sono rese anonime.

È possibile [eliminare un profilo social](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles#delete-a-social-profile).

Per eliminare un indirizzo di posta elettronica da tutti gli avvisi cui questo è stato aggiunto, seguire la procedura descritta in [Gestire i destinatari degli avvisi come amministratore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator).[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)

### <a name="exporting-personal-data"></a>Esportazione dei dati personali

È possibile fornire agli interessati i propri dati personali in formato elettronico.

#### <a name="social-media-users-authors"></a>Utenti di supporti di social networking (autori)

Per esportare i dati personali degli autori, seguire la procedura descritta in [Esportare le informazioni sull'autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information) per esportare i dati in un file Excel.

Per estrarre i tag autore aggiunti a un autore specifico, è possibile [esportare i dati dei tag autore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data).

##### <a name="your-employees"></a>I dipendenti

Per esportare:

- i dati del cliente dai profili utente, vedere l'[Interfaccia di amministrazione](https://portal.office.com/adminportal/home). Nell'**interfaccia di amministrazione** selezionare **Utenti**. Nella pagina **Utenti attivi**, cercare l'utente di cui si vogliono esportare i dati. Eliminare tutti gli utenti tranne l'utente di destinazione e quindi selezionare **Esporta** per esportare i dati in un file CSV in cui è possibile utilizzare Excel per visualizzare le informazioni.
- Indirizzi di posta elettronica del destinatario di un avviso (solo i dati personali di un avviso). Seguire la procedura descritta in [Gestire i destinatari degli avvisi come amministratore](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator). Quindi selezionare **Esporta** per il download dell'elenco Excel di avvisi che includono questo destinatario.
- I nomi utente di Power BI: [creazione di report in Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) mostra i nomi utente nei report sulle prestazioni del team sui supporti di social networking. Per esportare i dati, filtrare per utente nel dashboard di PowerBI o [report](https://docs.microsoft.com/power-bi/power-bi-report-add-filter) ed [esportare i dati](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data)

## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Parte 2: rispondere alle richieste DSR per i log generati dal sistema

Microsoft offre la possibilità di accedere, esportare ed eliminare log generati dal sistema che possono essere considerati personali secondo una definizione ampia di "dati personali" dell'RGDP. Esempi di log generati dal sistema che possono essere considerati personali ai sensi dell'RGDP includono:

- Dati di utilizzo di prodotti e servizi, ad esempio log di attività dell'utente
- Richieste di ricerca degli utenti e dati della query
- Dati generati da prodotti e servizi, come risultato della funzionalità del sistema e dell'interazione da parte di utenti o di altri sistemi

Tenere presente che la possibilità di limitare o rettificare dati nei log generati dal sistema non è supportata. I dati nei log generati dal sistema costituiscono le azioni effettive eseguite del cloud Microsoft e i dati di diagnostica e le modifiche a tali dati possono compromettere il record cronologico delle azioni, aumentando i rischi per la sicurezza e le truffe.

### <a name="accessing-and-exporting-system-generated-logs"></a>Accesso ed esportazione di log generati dal sistema

Gli amministratori possono accedere ai log generati dal sistema associati all'uso da parte di un utente specifico dei servizi e delle applicazioni di Dynamics 365. Per accedere ed esportare i log generati dal sistema:

1. Passare a [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) ed eseguire l'accesso con le credenziali di amministratore globale di Dynamics 365.
2. Nell'elenco a discesa **Privacy** nella parte superiore della pagina, fare clic su **Richiesta DSR**.
3. Nella pagina **Richiesta DSR**, in **Log generati dal sistema**, fare clic su **Esportazione log di dati**.
    > [!NOTE]
    > Viene visualizzato **Esportazione log di dati**. Si noti che viene visualizzato un elenco di richieste di esportazione dati inviate dall'organizzazione.
4. Per creare una nuova richiesta per un utente, fare clic su **Crea richiesta di esportazione dati**.

Dopo aver creato una nuova richiesta, questa verrà inserita nella pagina **Esportazione log di dati**, in cui è possibile tenere traccia del suo stato. Una volta completata una richiesta, è possibile fare clic su un collegamento per accedere ai log generati dal sistema che verranno esportati in un percorso di archiviazione di Azure dell'organizzazione entro 30 giorni dalla creazione della richiesta. I dati verranno salvati in formati di file leggibili di uso comune, ad esempio JSON o XML. Se non si dispone di un account Azure e di un percorso di archiviazione di Azure, sarà necessario creare l'account e/o il percorso di archiviazione per l'organizzazione affinché lo strumento Esportazione log di dati possa esportare i log generati dal sistema.

Azure supporta questa caratteristica, consentendo all'organizzazione di esportare i dati in formato JSON nativo nel contenitore di archiviazione di Azure specificato[. Vedere l'articolo di introduzione su Archiviazione BLOB di Archiviazione di Microsoft Azure](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).

> [!IMPORTANT]
> È necessario essere un amministratore tenant per esportare i dati di un utente dal tenant.

La tabella seguente riepiloga l'accesso e l'esportazione dei log generati dal sistema:

| | |
|:----|:---|
| | |
|**Quanto tempo impiega lo strumento di esportazione di log di dati di Microsoft per completare una richiesta?**| Ciò può dipendere da diversi fattori. Nella maggior parte dei casi l'operazione deve essere completata in uno o due giorni, ma può richiedere fino a 30 giorni. |
|**In quale formato sarà l'output?**| L'output sarà fornito in file leggibili strutturati come XML, CSV o JSON. |
|**Quali dati vengono restituiti dallo strumento di esportazione di log di dati?**| Lo strumento di esportazione di log di dati restituisce log generati dal sistema che vengono archiviati da Microsoft. I dati esportati includono vari servizi Microsoft, tra cui Office 365, Azure e Dynamics. |
|***Chi ha accesso allo strumento di esportazione dei log di dati per inviare richieste di accesso a log generati dal sistema?**| Gli amministratori globali di Dynamics 365 avranno accesso all'utilità di gestione file registro dell'RGDP. |
|**Come vengono restituiti i dati all'utente?**| I dati verranno esportati nel percorso di archiviazione di Azure dell'organizzazione. Spetterà agli amministratori dell'organizzazione stabilire come questi dati verranno visualizzati/restituiti agli utenti. |
|**Che aspetto avranno i dati nei log generati dal sistema?**| Esempio di un record di log generato dal sistema in formato JSON: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

> [!NOTE]
> Alcune funzionalità non consentono l'esportazione o l'eliminazione dei log generati dal sistema contenenti informazioni riservate per mantenere l'integrità di tali informazioni per motivi di sicurezza e controllo.

### <a name="deleting-system-generated-logs"></a>Eliminazione di log generati dal sistema

Per eliminare i log generati dal sistema recuperati attraverso una richiesta di accesso, è necessario rimuovere l'utente dal servizio ed eliminare definitivamente il suo account Azure Active Directory. Per istruzioni su come eliminare definitivamente un utente, vedere la sezione [Eliminazione di un utente](https://microsoft-my.sharepoint.com/personal/kated_microsoft_com/Documents/DSR%20Guide%20v4%20-(newly%20created%20for%20O365%20only).docx#_Deleting_a_user). È importante tenere presente che l'operazione di eliminazione definitiva di un account utente è irreversibile una volta avviata.

Eliminazione definitiva di un account utente con rimozione dei dati dell'utente dai log generati dal sistema per quasi tutti i servizi di Dynamics 365 entro 30 giorni.

## <a name="learn-more"></a>Ulteriori informazioni

- [Centro protezione Microsoft](https://www.microsoft.com/en-us/TrustCenter/Privacy/gdpr/default.aspx)
