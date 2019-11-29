---
title: Richieste degli interessati per Intune nell'ambito del GDPR e del CCPA
description: Guida su come usare i prodotti, i servizi e gli strumenti di amministrazione Microsoft per aiutare i clienti titolari del trattamento dei dati a individuare e gestire i dati personali per rispondere alle richieste degli interessati e nell'ambito del CCPA.
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
author: dougeby
manager: angrobe
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
ms.openlocfilehash: 9e668f4571ed193bd23b1373c170d3c0be929013
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "39268554"
---
# <a name="intune-data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli interessati per Intune nell'ambito del GDPR e del CCPA

Il [regolamento generale sulla protezione dei dati (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell’Unione europea attribuisce alle persone (definite nel regolamento *soggetti interessati*) il diritto di gestire i dati personali raccolti da un datore di lavoro o da un altro tipo di organizzazione o organismo (definito *titolare del trattamento dei dati* o semplicemente *titolare del trattamento*). Nell'ambito del regolamento GDPR i dati personali hanno una definizione molto ampia, ovvero sono tutti i dati riferiti a una persona fisica identificata o identificabile. In base al regolamento GDPR, ai soggetti dei dati vengono assegnati diritti specifici relativamente ai dati personali, tra i quali il diritto di ottenerne copie, richiedere correzioni, limitarne l'elaborazione, eliminarli o riceverli in formato elettronico in modo che possano essere trasferiti a un altro titolare. Una richiesta formale da un soggetto interessato a un titolare del trattamento di agire sui dati personali viene definita una *Richiesta dell’interessato * o DSR.

Analogamente, il California Consumer Privacy Act (CCPA) fornisce obblighi e diritti in materia di privacy per i consumatori della California, inclusi diritti simili ai diritti dell'interessato del GDPR, ad esempio il diritto di eliminare, ricevere e accedere alle informazioni personali (portabilità).  Nell'ambito dei diritti che i consumatori possono esercitare, il CCPA prevede inoltre l'obbligo per determinate divulgazioni, di protezioni contro la discriminazione e requisiti di consenso o rifiuto esplicito per alcuni trasferimenti di dati classificati come "vendite". In generale, le vendite sono definite per includere la condivisione dei dati per un motivo importante. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](offering-ccpa.md) e le [Domande frequenti sul California Consumer Privacy Act](ccpa-faq.md).

Questa guida illustra su come usare i prodotti, i servizi e gli strumenti amministrativi di Microsoft per consentire ai clienti titolari di individuare i dati personali ed effettuare operazioni su di essi per rispondere alle richieste DSR. In particolare, spiega come reperire i dati o le informazioni personali che si trovano nel cloud di Microsoft, nonché come accedervi e agire su di essi. Ecco una rapida panoramica dei processi descritti in questa guida:

- **Individuazione:** usare gli strumenti di ricerca per trovare più facilmente i dati del cliente che possono essere oggetto di una richiesta dell’interessato. Dopo aver raccolto i documenti potenzialmente rilevanti, è possibile eseguire una o più delle azioni DSR descritte nei passaggi seguenti per rispondere alla richiesta del soggetto interessato. In alternativa, è possibile stabilire che la richiesta non soddisfa le linee guida della propria organizzazione in merito alla risposta alle richieste dell’interessato.
- **Accesso:** recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, crearne una copia che può essere disponibile per l'interessato.
- **Rettificare:** apportare modifiche o implementare le azioni richieste sui dati personali, ove applicabile.
- **Limitare**: limitare il trattamento dei dati personali, rimuovendo le licenze per vari servizi di Azure o disattivando i servizi desiderati, dove possibile. È anche possibile rimuovere i dati dal cloud di Microsoft e conservarli in locale o in un'altra posizione.
- **Eliminare:** rimuovere in modo definitivo i dati personali che risiedono nel cloud Microsoft.
- **Esportazione/ricezione (portabilità):** fornire all'interessato una copia elettronica dei dati o delle informazioni personali in un formato leggibile da una macchina. Secondo il CCPA, le informazioni personali sono qualsiasi informazione relativa a una persona identificata o identificabile. Non esiste distinzione tra i ruoli privati, pubblici o professionali di una persona. Il termine definito "informazioni personali" combacia con il termine "dati personali" del GDPR. Tuttavia, il CCPA include anche i dati relativi alla famiglia e al nucleo familiare. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](offering-ccpa.md) e le [Domande frequenti sul California Consumer Privacy Act](ccpa-faq.md).

Ogni sezione di questa guida illustra le procedure tecniche che un'organizzazione titolare del trattamento dei dati può adottare per rispondere a una richiesta DSR per i dati personali nel cloud Microsoft.

#### <a name="terminology"></a>Terminologia

Di seguito vengono fornite le definizioni dei termini importanti nella presente guida.

- **Titolare:** la persona fisica o giuridica, l'autorità pubblica, l'agenzia o altro ente che, autonomamente o unitamente ad altri soggetti, determina gli obiettivi e i mezzi del trattamento dei dati personali; laddove gli obiettivi e i mezzi di tale trattamento sono determinati da una normativa europea o di uno specifico Stato membro dell'UE, il titolare del trattamento dei dati o i criteri specifici per la sua designazione potrebbero essere forniti da tale normativa europea o di uno specifico Stato membro dell'UE.
- **Dati personali e interessato:** qualsiasi informazione relativa a una persona fisica identificata o identificabile (“interessato”); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, tramite dati specifici come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica.
- **Responsabile:** una persona fisica o giuridica, un'autorità pubblica o altro ente che si occupa del trattamento dei dati personali per conto del titolare.
- **Dati del cliente:** tutti i dati, compresi file di testo, audio, video o immagini e software, forniti a Microsoft dal cliente o per suo conto attraverso i servizi aziendali. I dati dei clienti includono (1) informazioni che consentono l'identificazione personale degli utenti finali (ad esempio, nomi utente e informazioni di contatto in Azure Active Directory) e contenuti per i clienti che un cliente stesso carica o crea in servizi specifici (ad esempio, contenuti per i clienti in un account di archiviazione di Azure, contenuti per i clienti in un database SQL di Azure o un'immagine della macchina virtuale di un cliente in Macchine virtuali di Azure).
- **Log generati dal sistema:** i log e i dati correlati generati da Microsoft che consentono a Microsoft di offrire servizi aziendali agli utenti. I log generati dal sistema contengono principalmente dati presentati con l'uso di pseudonimi come un identificatore univoco, in genere un numero generato dal sistema che non può identificare individualmente una singola persona ma viene usato per fornire servizi aziendali agli utenti. I log generati dal sistema possono anche contenere informazioni identificabili riguardanti gli utenti finali, ad esempio un nome utente.

#### <a name="how-to-use-this-guide"></a>Come usare questa guida

Questa guida è costituita da due parti:

- **Parte 1: rispondere alle richieste dei soggetti interessati per i dati dei clienti** La Parte 1 di questa guida illustra come accedere, rettificare, eliminare ed esportare i dati dalle applicazioni in cui sono presenti dati creati dall'utente.  Questa sezione descrive dettagliatamente come gestire le richieste dell’interessato sia per i contenuti del cliente che per le informazioni che consentono di identificare gli utenti finali.
- **Parte 2: rispondere alle richieste degli interessati per i log generati dal sistema:** quando si usano i servizi aziendali Microsoft, Microsoft genera alcune informazioni, note come log generati dal sistema, per fornire il servizio.  La Parte 2 di questa guida illustra come accedere, eliminare ed esportare tali informazioni per Azure.

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Informazioni sulle richieste DSR per Azure Active Directory e Microsoft Intune

Se si prendono in considerazione i servizi forniti ai clienti aziendali, l'esecuzione di DSR deve essere sempre chiara nell'ambito dei contesto di un tenant di Azure Active Directory (AAD) specifico. In particolare, le richieste DSR vengono sempre eseguite all'interno di un detarminato tenant di AAD. Se un utente fa parte di più tenant, è importante sottolineare che una determinata richiesta DSR viene eseguita *solo* nel contesto del tenant specifico nel quale è stata ricevuta la richiesta. Questo è un aspetto fondamentale da comprendere perché significa che l'esecuzione di una richiesta DSR da parte di un cliente aziendale **non** avrà effetto sui dati di un cliente aziendale adiacente.

Lo stesso vale anche per Microsoft Intune fornito a un cliente aziendale: l'esecuzione di una richiesta DSR rispetto a un account Intune *associato a un tenant di AAD* sarà relativa **solo** ai dati all'interno del tenant. Inoltre, quando si gestiscono account Intune all'interno di un tenant, è importante comprendere quanto descritto di seguito:

- Se un utente Intune crea una sottoscrizione di Azure, l'abbonamento verrà gestito come se fosse un tenant di AAD. Di conseguenza, le richieste DSR sono limitate all'interno del tenant come descritto in precedenza.
- Se si elimina una sottoscrizione di Azure creata con un account Intune, **non ci saranno effetti** sull'account Intune. Come accennato in precedenza, l'esecuzione di richieste DSR nell'ambito della sottoscrizione di Azure è limitata all'ambito del tenant stesso.

Le richieste DSR rispetto a un account Intune, **al di fuori di un determinato tenant**, vengono eseguite tramite la Dashboard di privacy dell'utente. Per ulteriori informazioni, fare riferimento alla guida per le richieste degli interessati di Windows.

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: guida sulle richieste DSR per i dati dei clienti

### <a name="executing-dsrs-against-customer-data"></a>Esecuzione delle richieste DSR rispetto ai dati dei clienti

Microsoft consente di accedere, eliminare ed esportare alcuni dati dei clienti tramite il portale di Azure e anche direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per i servizi specifici (noti anche come *esperienze nel prodotto*). Informazioni su tali esperienze nel prodotto sono disponibili nella documentazione di riferimento per i relativi servizi.

>[!IMPORTANT]  
>I servizi che supportano le richieste DSR nel prodotto richiedono l'uso diretto dell'API (Application Programming Interface) o dell'interfaccia utente (UI) del servizio, descrivendo le operazioni CRUD (Create, Read, Update, Delete) applicabili. Pertanto, l'esecuzione di richieste DSR in un determinato servizio deve essere effettuata unitamente all'esecuzione di una richiesta DSR all'interno del portale di Azure per completare una richiesta per uno specifico soggetto dei dati. Per ulteriori dettagli, consultare la documentazione di riferimento per i relativi servizi.

### <a name="step-1-discover"></a>Passaggio 1: scoprire

Il primo passo nella risposa a una richiesta DSR consiste nell'individuare i dati personali oggetto della richiesta. Questa fase (individuazione e analisi dei dati personali in questione) consente di determinare se una richiesta DSR soddisfa i requisiti dell'organizzazione per accettare o rifiutare una DSR. Ad esempio, dopo aver individuato e analizzato i dati personali in questione, si potrebbe stabilire che la richiesta non soddisfa i requisiti dell'organizzazione perché potrebbe ledere i diritti e le libertà altrui.

Dopo aver trovato i dati, è quindi possibile eseguire un'azione specifica per soddisfare la richiesta. Per ulteriori dettagli, vedere gli articoli seguenti:

- [Raccolta dati](https://docs.microsoft.com/intune/privacy-data-collect)
- [Trattamento e archiviazione dei dati](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Visualizzazione dei dati personali](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Passaggio 2: accedere

Dopo aver individuato i dati dei clienti che contengono dati personali potenzialmente reattivi a una richiesta DSR, l'utente e l'organizzazione devono decidere quali dati fornire all'interessato. È possibile fornire una copia del documento effettivo, una versione appositamente riadattata o uno screenshot delle parti considerate adatte alla condivisione. Per ognuna di queste risposte a una richiesta di accesso, sarà necessario recuperare una copia del documento o altro elemento contenente i dati sensibili.

Quando si invia una copia all'interessato, potrebbe essere necessario rimuovere o redigere informazioni personali su altri interessati ed eventuali informazioni riservate.

Di seguito viene descritto come ottenere una copia dei dati in risposta a una richiesta di accesso DSR.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft fornisce un portale ed esperienze nel prodotto per consentire all'amministratore tenant del cliente aziendale di gestire le richieste di accesso DSR alle informazioni personali relative a un utente finale. Le richieste di accesso DSR consentono l'accesso ai dati personali dell'utente, tra cui: (a) informazioni che consentono l'identificazione di un utente finale e (b) i log generati dal sistema.

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft Intune consente di [Individuare i dati dei clienti](#step-1-discover) direttamente tramite le interfacce utente (UI) o le interfacce di programmazione dell'applicazione preesistenti (API).

### <a name="step-3-rectify"></a>Passaggio 3: rettificare

Se un interessato ha chiesto di rettificare i dati personali che fanno parte dei dati dell'organizzazione, l'utente e l'organizzazione dovranno determinare se la richiesta possa essere accettata. La rettifica dei dati potrebbe includere operazioni quali la modifica, la revisione o la rimozione di dati personali da un documento o altro.

In quanto responsabile del trattamento dei dati, Microsoft non offre la possibilità di correggere i log generati dal sistema in quanto rappresentano attività concrete e costituiscono un record cronologico degli eventi svolti all'interno dei servizi Microsoft. Per quanto riguarda Intune, gli amministratori non possono aggiornare le informazioni specifiche relative ai dispositivi o alle app. Se un utente finale desidera correggere dei dati personali (come il nome dispositivo) dovrà farlo direttamente dal dispositivo interessato. Tali modifiche verranno sincronizzate al prossimo accesso a Intune.

### <a name="step-4-restrict"></a>Passaggio 4: limitare

Gli interessati potrebbero richiedere la limitazione del trattamento dei loro dati personali. Microsoft fornisce il portale di Azure e le interfacce di programmazione dell'applicazione (API) o le interfacce utente (UI) esistenti. Tali esperienze consentono all'amministratore del tenant del cliente aziendale di gestire tali richieste DSR con una combinazione di esportazione ed eliminazione dei dati. Per informazioni dettagliate vedere [Trattamento dei dati personali](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

### <a name="step-5-delete"></a>Passaggio 5: eliminare

Il "diritto di eliminazione" tramite la rimozione dei dati personali dai dati dei clienti di un'organizzazione è una protezione chiave del GDPR. La rimozione dei dati personali include la cancellazione di tutti i dati personali e dei log generati dal sistema, ad eccezione delle informazioni del log di controllo. Per informazioni dettagliate, vedere [Eliminare i dati personali degli utenti finali](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).

## <a name="part-2-system-generated-logs"></a>Parte 2: log generati dal sistema

I log di controllo forniscono agli amministratori tenant un record di attività che genera una modifica in Microsoft Intune. I log di controllo sono disponibili per molte attività di gestione e generalmente consentono di creare, aggiornare (modificare), eliminare e assegnare azioni. È possibile esaminare anche le attività remote che generano eventi di controllo. Questi log di controllo possono contenere dati personali degli utenti i cui dispositivi sono registrati in Intune. Gli amministratori non possono eliminare i log di controllo. Per informazioni dettagliate, vedere [Controllare i dati personali](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).

## <a name="notify-about-exporting-or-deleting-issues"></a>Notificare problemi riguardanti l'esportazione o l'eliminazione.

Se si verificano problemi durante l'esportazione o l'eliminazione di dati dal portale di Azure, accedere al pannello **Guida e Supporto** del portale di Azure e inviare un nuovo ticket in **Gestione della sottoscrizione > Altre richieste di sicurezza e conformità > Pannello privacy e richieste GDPR**.

## <a name="learn-more"></a>Altre informazioni

- [Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)