---
title: Richieste dell'interessato per il GDPR in Intune
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
author: dougeby
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
manager: angrobe
ms.collection: GDPR
ms.openlocfilehash: eeb50954f849b0c110a88cc7d768844847d99255
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868912"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>Richieste dell'interessato per il GDPR in Intune
Il Regolamento generale sulla protezione dei dati (RGPD) dell'Unione europea garantisce alle persone (denominate come *soggetti dei dati* nel regolamento) il diritto di gestire i dati personali raccolti da un datore di lavoro o da un'altra organizzazione o agenzia (definiti come *titolari del trattamento dei dati* o semplicemente *titolari*). I dati personali sono ampiamente descritti nell'RGPD come dati che si riferiscono a una persona fisica identificata o identificabile. L'RGPD garantisce ai soggetti dei dati diritti specifici sui propri dati personali; tali diritti includono la possibilità di ottenere delle copie dei dati personali, richiedere di apportare delle modifiche ai dati, limitare il trattamento dei dati, eliminarli o riceverli in un formato elettronico affinché possano essere trasferiti a un altro titolare. Una richiesta formale di un soggetto dei dati rivolta a un titolare in merito a un'operazione da effettuare sui propri dati personali è denominata *Richiesta DSR* (Data Subject Rights, Diritti del soggetto dei dati) o DSR.

La guida descrive come utilizzare i prodotti, i servizi e gli strumenti di amministrazione Microsoft per aiutare i nostri clienti titolari del trattamento dei dati a individuare e gestire i dati personali per rispondere alle richieste DSR. In particolare, ciò include come identificare, accedere e usare i dati personali che risiedono nel cloud Microsoft. Di seguito è riportata una rapida panoramica dei processi descritti in questa guida:

1.  ***Scoprire***: utilizzare gli strumenti di ricerca e individuazione per trovare più facilmente i dati dei clienti che potrebbero essere oggetto di una richiesta DSR. Dopo aver raccolto dei documenti potenzialmente reattivi, è possibile eseguire una o più delle azioni DSR descritte nella seguente procedura per rispondere alla richiesta. In alternativa, si potrebbe determinare che la richiesta non soddisfa le linee guida dell'organizzazione relative alla risposta alle richieste DSR.

2.  ***Accedere***: recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, fare una copia di tali dati che può essere disponibile per l'interessato.

3.  ***Rettificare***: apportare delle modifiche o implementare le azioni richieste per i dati personali, ove applicabile.

4.  ***Limitare***: limitare il trattamento dei dati personali, tramite la rimozione delle licenze per vari servizi di Azure o disattivando i servizi desiderati ove possibile. È anche possibile rimuovere i dati dal cloud Microsoft e mantenerli in locale o in un altro posto.

5.  ***Eliminare***: rimuovere in modo definitivo i dati personali che risiedevano nel cloud Microsoft.

6.  ***Esportare***: fornire una copia elettronica (in un formato leggibile) dei dati personali al soggetto dei dati.

Ogni sezione di questa guida illustra le procedure tecniche che un'organizzazione titolare del trattamento dei dati può adottare per rispondere a una richiesta DSR per i dati personali nel cloud Microsoft.

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
#### <a name="terminology"></a>Terminologia

Di seguito vengono fornite le definizioni dei termini importanti nella presente guida.

-   *Titolare*: la persona fisica o giuridica, l'autorità pubblica, l'agenzia o altro ente che, autonomamente o unitamente ad altri soggetti, determina gli obiettivi e i mezzi del trattamento dei dati personali; laddove gli obiettivi e i mezzi di tale trattamento sono determinati da una normativa europea o di uno specifico Stato membro dell'UE, il titolare del trattamento dei dati o i criteri specifici per la sua designazione potrebbero essere forniti da tale normativa europea o di uno specifico Stato membro dell'UE.

-   *Dati personali* e *interessato*: qualsiasi informazione relativa a una persona fisica identificata o identificabile ("soggetto dei dati"); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, tramite dati specifici come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica.

-   *Responsabile*: una persona fisica o giuridica, un'autorità pubblica o altro ente che si occupa del trattamento dei dati personali per conto del titolare.

-   *Dati dei clienti*: tutti i dati, compresi tutti i file di testo, audio o immagini, e il software, che vengono forniti a Microsoft da, o per conto di, un cliente tramite l'uso del servizio aziendale. I dati dei clienti includono (1) informazioni che consentono l'identificazione personale degli utenti finali (ad esempio, nomi utente e informazioni di contatto in Azure Active Directory) e contenuti per i clienti che un cliente stesso carica o crea in servizi specifici (ad esempio, contenuti per i clienti in un account di archiviazione di Azure, contenuti per i clienti in un Azure SQL Database o un'immagine della macchina virtuale di un cliente in Macchine virtuali di Azure).

-   *Log generati dal sistema*: log e dati relativi generati da Microsoft che consentono a Microsoft di fornire servizi aziendali agli utenti. I log generati dal sistema contengono dati principalmente presentati con l'uso di pseudonimi come identificatori univoci (in genere, un numero generato dal sistema con cui non è possibile identificare direttamente un soggetto, ma che viene utilizzato per fornire i servizi aziendali agli utenti). I log generati dal sistema possono anche contenere informazioni personali sugli utenti finali, come un nome utente.  

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

#### <a name="how-to-use-this-guide"></a>Come utilizzare questa guida

Questa guida è costituita da due parti:

**Parte 1: rispondere alle richieste dei soggetti dei dati per i dati dei clienti** — Nella Parte 1 di questa guida viene illustrato come accedere, rettificare, eliminare ed esportare i dati dalle applicazioni in cui sono presenti dati creati dall'utente. In questa sezione viene descritto in modo dettagliato come gestire le richieste DSR rispetto ai contenuti per i clienti e alle informazioni personali degli utenti finali.

**Parte 2: rispondere alle richieste dei soggetti dei dati per i log generati dal sistema** — Quando si utilizzano i servizi aziendali Microsoft, Microsoft genera alcune informazioni, note come lig generati dal sistema, per fornire il servizio. Nella Parte 2 di questa guida viene illustrato come accedere, eliminare ed esportare tali informazioni per Azure.

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>







### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Informazioni sulle richieste DSR per Azure Active Directory e Microsoft Intune

Se si prendono in considerazione i servizi forniti ai clienti aziendali, l'esecuzione di DSR deve essere sempre chiara nell'ambito dei contesto di un tenant di Azure Active Directory (AAD) specifico. In particolare, le richieste DSR vengono sempre eseguite all'interno di un detarminato tenant di AAD. Se un utente fa parte di più tenant, è importante sottolineare che una determinata richiesta DSR viene eseguita *solo* nel contesto del tenant specifico nel quale è stata ricevuta la richiesta. Questo è un aspetto fondamentale da comprendere perché significa che l'esecuzione di una richiesta DSR da parte di un cliente aziendale **non** avrà effetto sui dati di un cliente aziendale adiacente.

Lo stesso vale anche per Microsoft Intune fornito a un cliente aziendale: l'esecuzione di una richiesta DSR rispetto a un account Intune *associato a un tenant di AAD* sarà relativa **solo** ai dati all'interno del tenant. Inoltre, quando si gestiscono account Intune all'interno di un tenant, è importante comprendere quanto descritto di seguito:

-   Se un utente Intune crea una sottoscrizione di Azure, l'abbonamento verrà gestito come se fosse un tenant di AAD. Di conseguenza, le richieste DSR sono limitate all'interno del tenant come descritto in precedenza.

-   Se si elimina una sottoscrizione di Azure creata con un account Intune, **non ci saranno effetti** sull'account Intune. Come accennato in precedenza, l'esecuzione di richieste DSR nell'ambito della sottoscrizione di Azure è limitata all'ambito del tenant stesso.

Le richieste DSR rispetto a un account Intune, **al di fuori di un determinato tenant**, vengono eseguite tramite la Dashboard di privacy dell'utente. Per ulteriori informazioni, fare riferimento alla guida per le richieste degli interessati di Windows.

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: guida sulle richieste DSR per i dati dei clienti

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a>Esecuzione delle richieste DSR rispetto ai dati dei clienti

Microsoft consente di accedere, eliminare ed esportare alcuni dati dei clienti tramite il portale di Azure e anche direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per i servizi specifici (noti anche come *esperienze nel prodotto*). Informazioni su tali esperienze nel prodotto sono disponibili nella documentazione di riferimento per i relativi servizi.

>[!Important]  
>I servizi che supportano le richieste DSR nel prodotto richiedono l'uso diretto dell'API (Application Programming Interface) o dell'interfaccia utente (UI) del servizio, descrivendo le operazioni CRUD (Create, Read, Update, Delete) applicabili. Pertanto, l'esecuzione di richieste DSR in un determinato servizio deve essere effettuata unitamente all'esecuzione di una richiesta DSR all'interno del portale di Azure per completare una richiesta per uno specifico soggetto dei dati. Per ulteriori dettagli, consultare la documentazione di riferimento per i relativi servizi.

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-1-discover"></a>Passaggio 1: scoprire

Il primo passo nella risposa a una richiesta DSR consiste nell'individuare i dati personali oggetto della richiesta. Questa fase (individuazione e analisi dei dati personali in questione) consente di determinare se una richiesta DSR soddisfa i requisiti dell'organizzazione per accettare o rifiutare una DSR. Ad esempio, dopo aver individuato e analizzato i dati personali in questione, si potrebbe stabilire che la richiesta non soddisfa i requisiti dell'organizzazione perché potrebbe ledere i diritti e le libertà altrui.

Dopo aver trovato i dati, è quindi possibile eseguire un'azione specifica per soddisfare la richiesta. Per ulteriori dettagli, vedere gli articoli seguenti:
- [Raccolta dati](https://docs.microsoft.com/intune/privacy-data-collect)
- [Trattamento e archiviazione dei dati](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Visualizzazione dei dati personali](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Passaggio 2: accedere
Dopo aver individuato i dati dei clienti che contengono dati personali potenzialmente reattivi a una richiesta DSR, l'utente e l'organizzazione devono decidere quali dati fornire all'interessato. È possibile fornire una copia del documento effettivo, una versione appositamente riadattata o uno screenshot delle parti considerate adatte alla condivisione. Per ognuna di queste risposte a una richiesta di accesso, sarà necessario recuperare una copia del documento o altro elemento contenente i dati sensibili.

Quando si fornisce una copia all'interessato, potrebbe essere necessario rimuovere o correggere informazioni personali su altri soggetti dei dati ed eventuali informazioni riservate.

<span id="_Using_Content_Search_1" class="anchor"></span>Di seguito viene descritto come ottenere una copia dei dati in risposta a una richiesta di accesso DSR.

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>Microsoft mette a disposizione un portale ed esperienze nel prodotto per offrire all'amministratore tenant del cliente aziendale la possibilità di gestire richieste di accesso DSR. Tali richieste consentono di accedere ai dati personali dell'utente, tra cui: (a) informazioni personali su un utente finale e (b) log generati dal sistema.

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft Intune consente di [Individuare i dati dei clienti](#step-1-discover) direttamente tramite le interfacce utente (UI) o le interfacce di programmazione dell'applicazione preesistenti (API).

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-3-rectify"></a>Passaggio 3: rettificare

Se un interessato ha chiesto di rettificare i dati personali che fanno parte dei dati dell'organizzazione, l'utente e l'organizzazione dovranno determinare se la richiesta possa essere accettata. La rettifica dei dati potrebbe includere operazioni quali la modifica, la revisione o la rimozione di dati personali da un documento o altro. 

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>


 In quanto responsabile del trattamento dei dati, Microsoft non offre la possibilità di correggere i log generati dal sistema in quanto rappresentano attività concrete e costituiscono un record cronologico degli eventi svolti all'interno dei servizi Microsoft. Per quanto riguarda Intune, gli amministratori non possono aggiornare le informazioni specifiche relative ai dispositivi o alle app. Se un utente finale desidera correggere dei dati personali (come il nome dispositivo) dovrà farlo direttamente dal dispositivo interessato. Tali modifiche verranno sincronizzate al prossimo accesso a Intune.

### <a name="step-4-restrict"></a>Passaggio 4: limitare

<span id="_Delete" class="anchor"></span>Gli interessati potrebbero richiedere la limitazione del trattamento dei loro dati personali. Microsoft fornisce il portale di Azure e le interfacce di programmazione dell'applicazione (API) o le interfacce utente (UI) pre-esistenti. Tali esperienze consentono all'amministratore tenant del cliente aziendale di gestire tali richieste DSR con una combinazione di esportazione dei dati ed eliminazione dei dati. Per ulteriori dettagli, vedere [Trattamento dei dati personali](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
### <a name="step-5-delete"></a>Passaggio 5: eliminare

Il "diritto di eliminazione" tramite la rimozione dei dati personali dai dati dei clienti di un'organizzazione è una protezione chiave del GDPR. La rimozione dei dati personali include la cancellazione di tutti i dati personali e dei log generati dal sistema, ad eccezione delle informazioni del log di controllo. Per informazioni dettagliate, vedere [Eliminare i dati personali degli utenti finali](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).


<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>Parte 2: log generati dal sistema
I log di controllo forniscono agli amministratori tenant un record di attività che genera una modifica in Microsoft Intune. I log di controllo sono disponibili per molte attività di gestione e generalmente consentono di creare, aggiornare (modificare), eliminare e assegnare azioni. È possibile esaminare anche le attività remote che generano eventi di controllo. Questi log di controllo possono contenere dati personali degli utenti i cui dispositivi sono registrati in Intune. Gli amministratori non possono eliminare i log di controllo. Per informazioni dettagliate, vedere [Controllare i dati personali](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).


## <a name="notify-about-exporting-or-deleting-issues"></a>Notificare problemi riguardanti l'esportazione o l'eliminazione.
Se si verificano problemi durante l'esportazione o l'eliminazione di dati dal portale di Azure, accedere al pannello **Guida e Supporto** del portale di Azure e inviare un nuovo ticket in **Gestione della sottoscrizione > Altre richieste di sicurezza e conformità > Pannello privacy e richieste GDPR**.

#### <a name="learn-more"></a>Altre informazioni
[Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)