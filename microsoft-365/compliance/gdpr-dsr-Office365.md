---
title: Richieste del servizio dati di Office 365 ai sensi del Regolamento generale sulla protezione dei dati (GDPR)
description: Informazioni sui diritti dell'utente in base al GDPR e sul modo in cui Office 365 aiuta le aziende a trovare e a usare i dati in risposta alle richieste DSR.
keywords: Office 365, DSR, Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 2559734241a8b30ec43b26fb0b096faba18138b9
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778151"
---
# <a name="office-365-data-subject-requests-for-the-gdpr"></a>Richieste dell'interessato per il GDPR in Office 365

## <a name="introduction-to-dsrs"></a>Introduzione alle richieste DSR

Il [Regolamento generale sulla protezione dei dati (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione Europea garantisce alle persone (denominate come *interessati* nel regolamento) il diritto di gestire i dati personali raccolti da un datore di lavoro o da un'altra organizzazione o agenzia (definiti come *titolari del trattamento dei dati* o semplicemente *titolari*). I dati personali sono ampiamente descritti nel GDPR come dati che si riferiscono a una persona fisica identificata o identificabile. Il Regolamento generale sulla protezione dei dati garantisce agli interessati diritti specifici sui propri dati personali. Tali diritti includono la possibilità di ottenere copie dei dati, richiedere di apportare modifiche ai dati, limitare il trattamento dei dati, eliminarli o riceverli in un formato elettronico affinché possano essere trasferiti a un altro titolare. Una richiesta formale da parte dell'interessato rivolta a un titolare in merito a un'operazione da effettuare sui propri dati personali è denominata *Richiesta DSR* (Data Subject Rights, Diritti dell'interessato) o DSR. Il titolare è tenuto a prendere immediatamente in considerazione ogni richiesta DSR e a fornire una risposta concreta effettuando l'operazione richiesta o fornendo una spiegazione del motivo per cui non è in grado di gestire la richiesta DSR. Un titolare deve confrontarsi con i propri consulenti legali o della conformità in merito alla disposizione adeguata di ogni richiesta DSR.

La guida descrive come usare i prodotti, i servizi e gli strumenti di amministrazione di Office 365 per individuare e gestire con facilità i dati personali per rispondere alle richieste DSR. In particolare, ciò include informazioni su come identificare i dati personali che risiedono nel cloud Microsoft, come accedervi e come usarli. Di seguito è riportata una rapida panoramica dei processi descritti in questa guida:

- **Scoprire:** usare gli strumenti di ricerca e individuazione per trovare più facilmente i dati dei clienti che potrebbero essere oggetto di una richiesta dell'interessato. Dopo aver raccolto dei documenti potenzialmente reattivi, è possibile eseguire una o più delle azioni DSR descritte nella seguente procedura per rispondere alla richiesta. In alternativa, si può determinare che la richiesta non soddisfa le linee guida dell'organizzazione relative alla risposta alle richieste degli interessati.
- **Accedere:** recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, crearne una copia che può essere disponibile per l'interessato.
- **Rettificare:** apportare modifiche o implementare le azioni richieste sui dati personali, ove applicabile.
- **Limitare:** limitare il trattamento dei dati personali, tramite la rimozione delle licenze per vari servizi di Azure o disattivando i servizi desiderati ove possibile. È anche possibile rimuovere i dati dal cloud Microsoft e mantenerli in locale o in un'altra posizione.
- **Eliminare:** rimuovere in modo definitivo i dati personali che risiedono nel cloud Microsoft.
- **Esportare:** fornire all'interessato una copia elettronica dei dati personali in un formato leggibile in modo automatizzato.

### <a name="terminology"></a>Terminologia

Di seguito vengono fornite le definizioni dei termini del GDPR importanti per la presente guida.

- **Titolare:** la persona fisica o giuridica, l'autorità pubblica, l'agenzia o altro ente che, autonomamente o unitamente ad altri soggetti, determina gli obiettivi e i mezzi del trattamento dei dati personali; laddove gli obiettivi e i mezzi di tale trattamento sono determinati da una normativa europea o di uno specifico Stato membro dell'UE, il titolare del trattamento dei dati o i criteri specifici per la sua designazione potrebbero essere forniti da tale normativa europea o di uno specifico Stato membro dell'UE.
- **Dati personali e interessato:** qualsiasi informazione relativa a una persona fisica identificata o identificabile (“interessato”); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, tramite dati specifici come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica.
- **Responsabile:** una persona fisica o giuridica, un'autorità pubblica o altro ente che si occupa del trattamento dei dati personali per conto del titolare.
- **Dati del cliente:** tutti i dati, compresi file di testo, audio, video o immagini e software, forniti a Microsoft dal cliente o per suo conto attraverso i servizi aziendali. I dati dei clienti includono (1) informazioni che consentono l'identificazione personale degli utenti finali (ad esempio, nomi utente e informazioni di contatto in Azure Active Directory) e contenuti per i clienti che un cliente stesso carica o crea in servizi specifici (ad esempio, contenuti per i clienti in un account di archiviazione di Azure, contenuti per i clienti in un database SQL di Azure o un'immagine della macchina virtuale di un cliente in Macchine virtuali di Azure).
- **Log generati dal sistema:** i log e i dati correlati generati da Microsoft che consentono a Microsoft di offrire servizi aziendali agli utenti. I log generati dal sistema contengono principalmente dati presentati con l'uso di pseudonimi come un identificatore univoco. In genere un numero generato dal sistema non può identificare individualmente una singola persona ma viene usato per fornire servizi aziendali agli utenti. I log generati dal sistema possono anche contenere informazioni identificabili riguardanti gli utenti finali, ad esempio un nome utente.

### <a name="how-to-use-this-guide"></a>Come usare questa guida

Per agevolare l'individuazione delle informazioni rilevanti per il proprio caso d'uso, questa guida è divisa in quattro parti.

- **[Parte 1. Risposta a richieste DSR per i dati del cliente](#part-1-responding-to-dsrs-for-customer-data):** i *dati del cliente* vengono creati e archiviati in Office 365 nelle operazioni quotidiane dell'azienda. Esempi delle applicazioni di Office 365 più comuni che consentono di creare dati sono Word, Excel, PowerPoint, Outlook e OneNote. Office 365 è inoltre costituito da applicazioni come SharePoint Online, Teams e Forms che consentono una migliore collaborazione con altri utenti. La Parte 1 di questa guida descrive il modo in cui è possibile individuare, accedere, rettificare, restringere, eliminare ed esportare dati dalle applicazioni di Office 365 che sono state usate per creare e archiviare dati nei servizi online di Office 365. Si rivolge a prodotti e servizi per i quali Microsoft funge da responsabile del trattamento dei dati per l'organizzazione, pertanto la funzionalità DSR viene resa disponibile all'amministratore del tenant.
- **[Parte 2. Risposta alle DSR in merito alle informazioni dettagliate generate da Office 365](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365):** Office 365 fornisce alcune informazioni tramite servizi come Delve, MyAnalytics e Workplace Analytics. La Parte 2 di questa guida illustra il modo in cui queste informazioni vengono generate e come rispondere alle DSR correlate.
- **[Parte 3. Risposta alle richieste DSR per log generati dal sistema](#part-3-responding-to-dsrs-for-system-generated-logs):** quando si usano i servizi aziendali di Office 365, Microsoft genera alcune informazioni come i log di servizio che registrano l'utilizzo o le prestazioni delle funzionalità nei servizi online. La maggior parte dei dati generati dal servizio contiene identificatori pseudonimi generati da Microsoft, quindi nel documento si fa riferimento a questa categoria come *log generati dal sistema*. Anche se questi dati non possono essere attribuiti a un interessato specifico senza l'uso di informazioni aggiuntive, alcuni possono rientrare nella definizione generale del GDPR di "dati personali". La Parte 3 di questa guida illustra come accedere, eliminare ed esportare log generati dal sistema.
- **[Parte 4. Risorse aggiuntive di supporto per le DSR](#part-4-additional-resources-to-assist-you-with-dsrs):** la Parte 4 di questa guida elenca gli scenari limitati in cui Microsoft è il titolare del trattamento quando vengono usati determinati prodotti e servizi di Office 365.

> [!NOTE]
> Nella maggior parte dei casi, quando nell'organizzazione si usano prodotti e servizi di Microsoft Office 365, l'amministratore è il titolare del trattamento dati e Microsoft è il responsabile. In quanto titolare del trattamento dati, si è responsabili di rispondere direttamente all'interessato. A questo scopo, le Parti 1-3 di questa guida illustrano in dettaglio le funzionalità tecniche a disposizione dell'organizzazione per rispondere a una richiesta DSR. In alcuni scenari limitati, tuttavia, è Microsoft il titolare del trattamento dati quando le persone usano determinati prodotti e servizi Office 365. In questi casi, le informazioni nella Parte 4 forniscono indicazioni sul modo in cui gli interessati possono inviare richieste DSR a Microsoft.

### <a name="office-365-national-clouds"></a>Cloud nazionali di Office 365

I servizi di Microsoft Office 365 sono disponibili anche nei seguenti ambienti cloud nazionali: [Office 365 Germany](https://support.office.com/article/learn-about-office-365-germany-8a5a4bbc-667a-4cac-8769-d8ac9015db4c), [Office 365 gestito da 21Vianet (Cina)](https://support.office.com/article/Learn-about-Office-365-operated-by-21Vianet-A8AB5061-3346-4DA0-BB7C-5260822B53AE) e [Office 365 US Government](https://technet.microsoft.com/library/mt774581.aspx). La maggior parte del materiale sussidiario per la gestione delle richieste degli interessati descritta nel presente documento si applica a questi ambienti cloud nazionali. Data la natura isolata di tali ambienti, esistono tuttavia delle eccezioni. Se rilevanti per una determinata sottosezione, le eccezioni sono indicate nella nota corrispondente.

### <a name="hybrid-deployments"></a>Distribuzioni ibride

L'organizzazione di Office 365 può comprendere offerte di Microsoft che sono una combinazione di servizi basati sul cloud e prodotti server in locale. In generale, una distribuzione ibrida è la condivisione di account utente (gestione delle identità) e risorse (come cassette postali, siti Web e dati) presenti nel cloud e in locale. Gli scenari ibridi comuni includono:

- Distribuzioni ibride di Exchange, dove alcuni utenti hanno cassette postali in locale e altri utenti hanno cassette postali di Exchange Online.
- Distribuzioni ibride di SharePoint, dove server del sito e file server sono in locale e gli account di OneDrive for Business sono in Office 365.
- Il sistema di gestione delle identità in locale (Active Directory) sincronizzato con Azure Activity Directory, che è il servizio directory sottostante in Office 365.

Quando si risponde a una richiesta DSR, potrebbe essere necessario determinare se i dati relativi a una richiesta DSR si trovano nel cloud Microsoft o nell'organizzazione locale e, di conseguenza, adottare la procedura appropriata per rispondere alla richiesta. La presente guida alle richieste dell'interessato in Office 365 fornisce indicazioni per la gestione dei dati basati sul cloud. Per istruzioni sui dati nell'organizzazione locale vedere [GDPR per server locali di Office](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

## <a name="part-1-responding-to-dsrs-for-customer-data"></a>Parte 1. Risposta a richieste DSR per i dati del cliente

Le indicazioni per rispondere alle richieste DSR per i dati del cliente si dividono nelle quattro sezioni seguenti:

- [Utilizzo dello strumento Ricerca contenuto di eDiscovery per rispondere alle richieste DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)
- [Utilizzo della funzionalità in-app per rispondere alle richieste DSR](#using-in-app-functionality-to-respond-to-dsrs)
- [Risposta alle richieste di rettifica DSR](#responding-to-dsr-rectification-requests)
- [Risposta alle richieste di restrizione DSR](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>Come determinare le applicazioni di Office 365 che potrebbero rientrare nell'ambito di una DSR per i dati dei clienti

Per determinare dove cercare i dati personali o cosa cercare, è utile identificare le applicazioni di Office 365 che gli utenti dell'organizzazione possono usare per creare e archiviare i dati in Office 365. Sapere che questo circoscrive le applicazioni di Office 365, che sono nell'ambito di un DSR, aiuta a determinare come cercare e accedere ai dati personali correlati a un DSR. In particolare, questo significa che è possibile usare lo strumento Ricerca Contenuto o, se è necessario, la funzionalità integrata dell'applicazione in cui sono stati creati i dati.

Un modo rapido per identificare le applicazioni di Office 365 usate nell'organizzazione per creare i dati dei clienti consiste nel determinare quali applicazioni sono incluse nell'abbonamento a Office 365 dell'organizzazione. È possibile a tal fine accedere agli account utente nel portale di amministrazione di Office 365 e cercare le informazioni sulla licenza del prodotto. Vedere [Assegnare licenze agli utenti in Office 365 per le aziende](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>Utilizzo dello strumento Ricerca contenuto di eDiscovery per rispondere alle richieste DSR

Quando si cercano dati personali in un grande set di dati creati e archiviati dall'organizzazione con Office 365, è opportuno prima di tutto considerare quali applicazioni potrebbero essere state usate con maggiore probabilità per creare i dati che si stanno cercando. Microsoft stima che oltre il 90% dei dati di un'organizzazione archiviati in Office 365 venga creato in Word, Excel, PowerPoint, OneNote e Outlook. I documenti creati in queste applicazioni di Office, anche se acquistate tramite Office 365 ProPlus o una licenza di SharePoint Online, vengono molto probabilmente archiviati in un sito di SharePoint Online, in un account utente di OneDrive for Business o nella cassetta postale di Exchange Online di un utente. Ciò significa che è possibile usare lo strumento Ricerca contenuto di eDiscovery per cercare (ed eseguire altre azioni correlate alle DSR) nei siti di SharePoint Online, negli account OneDrive for Business e nelle cassette postali di Exchange Online (inclusi i siti e le cassette postali associati a Gruppi di Office 365, Microsoft Teams, EDU Assignments e StaffHub) per trovare documenti ed elementi della cassetta postale che potrebbero essere rilevanti per la DSR che si sta analizzando. È possibile usare lo strumento Ricerca contenuto anche per individuare dati di clienti creati in altre applicazioni di Office 365.

Nella tabella seguente sono elencate le applicazioni di Office 365 che gli utenti usano per creare contenuti creati dai clienti e che possono essere individuati con Ricerca Contenuto. In questa sezione della Guida DSR sono disponibili informazioni su come individuare, accedere, esportare ed eliminare i dati creati con le applicazioni di Office 365.

***Tabella 1. Applicazioni in cui è possibile usare Ricerca contenuto per trovare i dati dei clienti***

| | |
| :---: | :---:|
![Icona del calendario](media/O365-DSR-Doc-Final_image3.png) <br> Calendario | ![Icona di SharePoint](media/o365-sharepoint-64x64.png) <br> SharePoint  |
| ![Icona Excel](media/o365-excel-64x64.png) <br> Excel | ![Icona di Skype for Business](media/o365-skypeforbusiness-64x64.png) <br> Skype for Business |
| ![Icona di Office Lens](media/o365-lens-64x64.png) <br> Office Lens | ![Icona attività](media/O365-DSR-Doc-Final_image8.png) <br> Attività |
| ![Icona OneDrive](media/o365-OneDrive-64x64.png) <br> OneDrive for Business |![icona di Teams](media/o365-teams-64x64.png) <br> Teams |
| ![Icona di OneNote](media/o365-onenote-64x64.png) <br> OneNote| ![Icona To-Do](media/o365-todo-64x64.png) <br> To-Do |
| ![icona di Outlook](media/o365-outlook-64x64.png) <br> Outlook/Exchange | ![Icona del video](media/O365-DSR-Doc-Final_image14.png) <br> Video |
| ![Icona persone](media/O365-DSR-Doc-Final_image15.png) <br> Persone | ![Icona Visio](media/o365-visio-64x64.png) <br> Visio |
| ![Icona PowerPoint](media/o365-powerpoint-64x64.png) <br> PowerPoint | ![Icona Word](media/o365-word-64x64.png) <br> Word
||

> [!NOTE]
> Lo strumento Ricerca contenuto di eDiscovery non è disponibile in [Office 365 gestito da 21Vianet (Cina)](https://support.office.com/article/Learn-about-Office-365-operated-by-21Vianet-A8AB5061-3346-4DA0-BB7C-5260822B53AE). Ciò significa che non può essere utilizzato per cercare ed esportare i dati dei clienti nelle applicazioni di Office 365 mostrate nella Tabella 1. Tuttavia, è possibile utilizzare lo strumento eDiscovery sul posto in Exchange Online per cercare contenuti nelle cassette postali utente. È inoltre possibile utilizzare il Centro eDiscovery in SharePoint Online per cercare contenuti nei siti di SharePoint e negli account di OneDrive. In alternativa, è possibile chiedere aiuto al titolare di un documento per individuare e modificare, eliminare o esportare contenuti, se necessario. Per ulteriori informazioni, vedere:</br><br> • [Creazione di una ricerca eDiscovery sul posto](https://technet.microsoft.com/library/dd353189(v=exchg.150).aspx)<br> • [Configurazione del Centro eDiscovery in SharePoint Online](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>Usare Ricerca contenuto per trovare dati personali

Il primo passaggio per rispondere a un DSR consiste nell'individuare i dati personali oggetto del DSR. Si tratta di usare gli strumenti di Office 365 eDiscovery per cercare dati personali tra tutti quelli della propria organizzazione in Office 365, o passare direttamente all'applicazione nativa in cui sono stati creati i dati. Questo primo passaggio, che consente nell’individuare ed esaminare i dati personali in questione, consente di determinare se un DSR soddisfa i requisiti dell'organizzazione per rispettare o rifiutare una richiesta dei diritti dell’interessato. Ad esempio, dopo aver trovato ed esaminato i dati personali in questione, è possibile che la richiesta non soddisfi i requisiti dell'organizzazione, perché in questo modo può influire negativamente sui diritti e sulle libertà altrui, o poiché i dati personali sono contenuti in un record aziendale la propria organizzazione ha un interesse commerciale legittimo nel conservarli.

Come indicato in precedenza, Microsoft stima che oltre il 90% dei dati di un'organizzazione venga creato con applicazioni di Office, ad esempio Word ed Excel. Ciò significa che è possibile usare Ricerca contenuto nel Centro ricerca e conformità per cercare i dati più pertinenti alla richiesta DSR.

Questa guida presuppone che l'amministratore o la persona che sta cercando i dati personali che potrebbero essere utili a una richiesta DSR abbia familiarità o esperienza con lo strumento Ricerca contenuto nel Centro sicurezza e conformità. Per indicazioni generali sull'uso di Ricerca contenuto, vedere [Ricerca contenuto in Office 365](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4). Assicurarsi che la persona che esegue le ricerche disponga delle autorizzazioni necessarie nel Centro sicurezza e conformità. Questa persona deve essere aggiunta come membro del gruppo di ruoli Manager di eDiscovery nel Centro sicurezza e conformità; vedere [Assegnare autorizzazioni nel Centro sicurezza e conformità di Office 365](https://support.office.com/article/Assign-eDiscovery-permissions-in-the-Office-365-Security-Compliance-Center-5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7). Prendere in considerazione l'idea di aggiungere altre persone nell'organizzazione che sono coinvolte nell'analisi delle richieste DSR al gruppo di ruoli Manager di eDiscovery, affinché possano eseguire le azioni necessarie nello strumento Ricerca contenuto, ad esempio visualizzare l'anteprima ed esportare i risultati della ricerca. A meno che non vengano configurati limiti di conformità (come descritto [qui](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)), tenere tuttavia presente che un Manager eDiscovery può eseguire ricerche in tutti i percorsi di contenuti nell'organizzazione, inclusi quelli che potrebbero non essere correlati all'analisi della richiesta DSR.

Dopo avere trovato i dati, è quindi possibile eseguire un'azione specifica per soddisfare la richiesta da parte dell'interessato.

> [!NOTE]
> In Office 365 Germany, il Centro sicurezza e conformità è situato in https://protection.office.de.

#### <a name="searching-content-locations"></a>Ricerca in percorsi di contenuti

Con lo strumento Ricerca contenuto è possibile cercare i tipi seguenti di percorsi di contenuti.

- Cassette postali di Exchange Online. Questo include le cassette postali associate a Gruppi di Office 365 e Microsoft Teams
- Cartelle pubbliche di Exchange Online
- Siti SharePoint Online. Questo include i siti associati a Gruppi di Office 365 e Microsoft Teams
- Account OneDrive for Business

> [!NOTE]
> Questa guida presuppone che tutti i dati che potrebbero essere rilevanti per un'indagine DSR siano archiviati in Office 365, in altre parole, archiviati nel cloud Microsoft. I dati archiviati in un computer locale di un utente o in locale nei file server dell'organizzazione non rientrano nell'ambito di un'indagine DSR sui dati archiviati in Office 365. Per indicazioni su come rispondere alle richieste DSR per i dati nelle organizzazioni locali, vedere [GDPR per i server locali di Office](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

#### <a name="tips-for-searching-content-locations"></a>Suggerimenti sulla ricerca nei percorsi di contenuti

- Iniziare la ricerca di tutti i percorsi di contenuti nell'organizzazione (che è possibile cercare con una singola ricerca) per determinare rapidamente quali percorsi di contenuti contengono elementi corrispondenti alla query di ricerca. È quindi possibile eseguire di nuovo la ricerca e restringere l'ambito di ricerca alle posizioni specifiche che contengono elementi rilevanti.
- Usare le statistiche della ricerca per identificare i percorsi principali che contengono gli elementi che corrispondono alla query di ricerca. Vedere [Visualizzare statistiche delle parole chiave per i risultati di Ricerca contenuto](https://support.office.com/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).
- Eseguire ricerche nel log di controllo di Office 365 sulle attività recenti in file e cartelle eseguite dall'utente oggetto del DSR. La ricerca nel log di controllo restituisce un elenco di record di controllo che contiene il nome e la posizione delle risorse con cui l'utente ha interagito di recente. Potrebbe essere possibile usare queste informazioni per creare una query di ricerca contenuto. Vedere [Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità di Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

#### <a name="building-search-queries-to-find-personal-data"></a>Creare query di ricerca per trovare dati personali

Il DSR che si sta analizzando contiene molto probabilmente degli identificatori che è possibile usare nella query di ricerca con parole chiave per cercare i dati personali. Ecco alcuni identificatori comuni che possono essere usati in una query di ricerca per trovare i dati personali:

- Indirizzo e-mail o alias
- Numero di telefono
- Indirizzo postale
- Numero ID dipendente
- Numero del documento di identità o versione europea di un codice fiscale

La richiesta DSR che si sta analizzando avrà probabilmente un identificatore e altri dettagli relativi ai dati personali oggetto della richiesta che è possibile usare in una query di ricerca.

Cercando solo un indirizzo di posta elettronica o un ID dipendente, probabilmente si otterranno molti risultati. Per restringere l'ambito della ricerca in modo che restituisca il contenuto più pertinente per il DSR, è possibile aggiungere delle condizioni alla query di ricerca. Quando si aggiunge una condizione, la parola chiave e una condizione di ricerca sono connesse logicamente dall'operatore booleano **AND**. Ciò significa che nei risultati della ricerca*entrambe* la parola chiave e la condizione compariranno nei risultati di ricerca.

La tabella seguente elenca alcune condizioni che è possibile usare per restringere l'ambito di una ricerca. La tabella elenca anche i valori che è possibile usare per ogni condizione affinché cerchi tipi di documenti ed elementi della cassetta postale specifici.

***Tabella 2. Restringere l'ambito della ricerca tramite l'uso di condizioni***

||||
| :--- | :--- |:--- |
|**Condizione**|**Descrizione** |**Esempio di valori della condizione**|
| Tipo di file | Estensione di un documento o di un file. Usare questa condizione per cercare documenti di Office e file creati con applicazioni di Office 365. Usare questa condizione per la ricerca di documenti in siti di SharePoint Online e account di OneDrive for Business.<br/>La proprietà del documento corrispondente è filetype. <br/>Per un elenco completo delle estensioni di file che è possibile cercare, vedere Estensioni di nomi di file e tipi di file analizzati sottoposti a ricerca per indicizzazione predefiniti in SharePoint](https://technet.microsoft.com/library/jj219530.aspx).|&nbsp;&bull;&nbsp;&nbsp;csv — Cerca file con valori delimitati da  virgole (CSV). I file di Excel possono essere salvati in formato CSV e i file CSV possono essere facilmente importati in Excel<br><br>&bull;&nbsp;&nbsp;docx — Cerca file di Word <br><br>&bull;&nbsp;&nbsp;mpp — Cerca file di Project<br/><br>&bull;&nbsp;&nbsp;one — Cerca file di OneNote <br><br>&bull;&nbsp;&nbsp;pdf — Cerca file salvati in formato PDF <br><br>&bull;&nbsp;&nbsp;pptx — Cerca file di PowerPoint <br><br>&bull;&nbsp;&nbsp;xlxs — Cerca file di Excel <br><br>&bull;&nbsp;&nbsp;vsd — Cerca file di Visio <br><br>&bull;&nbsp;&nbsp;wmv — Cerca file video di Windows Media <br>|
| Tipo di messaggio | Il tipo di messaggio di posta elettronica da cercare. Usare questa condizione per eseguire ricerche nelle cassette postali di contatti (persone), riunioni (Calendario di Outlook) o Conversazioni Skype for Business. La proprietà di posta elettronica corrispondente è*kind*.|&bull;&nbsp;&nbsp;*contacts — Cerca l’elenco Contatti (Persone) di una cassetta postale <br><br>&bull;&nbsp;&nbsp;* email — Cerca messaggi di posta elettronica. <br><br>&bull;&nbsp;&nbsp;*messaggi istantanei — consente di eseguire ricerche nelle conversazioni di Skype for Business<br><br>&bull;&nbsp;&nbsp;* riunioni — esegue ricerche di appuntamenti e convocazioni di riunione (Calendario di Outlook) <br><br>&bull;&nbsp;&nbsp;*tasks — Cerca l'elenco Attività (Attività); con questo valore vengono restituite anche le attività create in Microsoft To-Do.<br>|
| Tag di conformità |L'etichetta assegnata a un messaggio e-mail o un documento. Le etichette servono a classificare le e-mail e i documenti per la governance dei dati e ad applicare regole di conservazione in base alla classificazione definita dall'etichetta. Usare questa condizione per cercare elementi a cui è stata assegnata automaticamente o manualmente un'etichetta.<br/>Questa condizione è utile per le analisi delle richieste DSR poiché l'organizzazione può usare le etichette per classificare il contenuto relativo alla privacy dei dati o a dati personali o informazioni riservate. Vedere la sezione "Uso di Ricerca contenuto per trovare tutto il contenuto a cui è applicata una specifica etichetta" in [Panoramica delle etichette - Office 365](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).|compliancetag="personal data"|
||||

Esistono molte altre proprietà di e-mail e di documento e condizioni di ricerca che è possibile usare per creare query di ricerca più complesse. Per altre informazioni, vedere le sezioni seguenti nell'argomento della Guida [Query con parole chiave e condizioni di ricerca per la ricerca di contenuto](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).

- [Proprietà di e-mail disponibili per la ricerca](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3)
- [Proprietà (documento) di siti disponibili per la ricerca](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3)
- [Condizioni di ricerca](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>Ricerca di dati personali negli elenchi, nelle discussioni e nei moduli di SharePoint

Oltre a eseguire la ricerca di dati personali nei documenti, è possibile usare Ricerca contenuto anche per cercare altri tipi di dati creati con app native di SharePoint Online. Sono inclusi i dati creati tramite gli elenchi, le discussioni e i moduli di SharePoint. Quando si esegue una Ricerca contenuto e si cerca nei siti di SharePoint Online (o negli account OneDrive for Business), nei risultati della ricerca vengono restituiti dati di elenchi, discussioni e moduli corrispondenti ai criteri di ricerca.

##### <a name="examples-of-search-queries"></a>Esempi di query di ricerca

Di seguito sono riportati alcuni esempi di query di ricerca che usano parole chiave e condizioni per cercare dati personali in risposta a un DSR. Gli esempi mostrano due versioni della query: una che mostra la sintassi della parola chiave (in cui è inclusa la condizione nella casella delle parole chiave) e una che mostra la versione basata su GUI della query con condizioni.

##### <a name="example-1"></a>Esempio 1

Questo esempio restituisce file di Excel, situati in siti di SharePoint Online e in account OneDrive for Business, che contengono l’indirizzo di posta elettronica specificato. Se l'indirizzo di posta elettronica viene visualizzato nei metadati dei file, è possibile che i file vengano restituiti.

***Sintassi della parola chiave***

```
pilar@contoso.com AND filetype="xlxs"
```

***GUI***

![](media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>Esempio 2

Questo esempio restituisce file di Word o di Excel, in siti di SharePoint Online e in account OneDrive for Business, che contengono l'ID dipendente specificato o la data di nascita specificata.

(98765 OR "01-20-1990") AND (filetype="xlxs" OR filetype="docx")

***GUI***

![](media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>Esempio 3

Questo esempio restituisce i messaggi e-mail che contengono il numero ID specificato, ovvero un numero di previdenza sociale francese (INSEE)

```
"1600330345678 97" AND kind="email"
```

***GUI***

![](media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>Uso di elementi parzialmente indicizzati in Ricerca contenuto

Gli elementi indicizzati parzialmente, detti anche *elementi non indicizzati*, sono elementi e documenti di cassette postali di Exchange Online nei siti di SharePoint Online e OneDrive for Business che per qualche motivo non sono stati indicizzati per la ricerca, pertanto non sono ricercabili con ricerca contenuto. La maggior parte dei messaggi di posta elettronica e i documenti del sito vengono indicizzati correttamente perché corrispondono ai [limiti di indicizzazione per Office 365.](https://support.office.com/article/limits-for-content-search-in-the-office-365-security-compliance-center-78fe3147-1979-4c41-83bb-aeccf244368d??) I motivi per cui i messaggi di posta elettronica o i file non vengono indicizzati per la ricerca includono:

- Il tipo di file [non è riconosciuto o supportato per l'indicizzazione.](https://support.office.com/article/partially-indexed-items-in-content-search-in-office-365-d1691de4-ca0d-446f-a0d0-373a4fc8487b??) Nonostanyte il tipo di file sia supportato per l'indicizzazione si è verificato un errore di indicizzazione per un file specifico
- I messaggi e-mail hanno un file allegato senza un gestore valido, ad esempio un file immagine (che rappresenta la causa più comune di elementi di e-mail parzialmente indicizzati).
- I file allegati ai messaggi e-mail sono troppo grandi o troppo numerosi.

È consigliabile approfondire l'argomento degli elementi parzialmente indicizzati per poterli usare per rispondere alle richieste DSR. Per altre informazioni, vedere:

- [Partially indexed items in Content Search in Office 365](https://support.office.com/article/partially-indexed-items-in-content-search-in-office-365-d1691de4-ca0d-446f-a0d0-373a4fc8487b??) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)
- [Investigating partially indexed items in Office 365 eDiscovery](https://support.office.com/article/investigating-partially-indexed-items-in-office-365-ediscovery-4e8ff113-6361-41e2-915a-6338a7e2a1ed) (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)
- [Exporting unindexed items](https://support.office.com/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278#unidexeditems) (Esportazione di elementi non indicizzati)

#### <a name="tips-for-working-with-partially-indexed-items"></a>Suggerimenti su come usare gli elementi parzialmente indicizzati

È possibile che i dati relativi a un'analisi di una richiesta DSR si trovino in un elemento parzialmente indicizzato. Ecco alcuni suggerimenti su come usare gli elementi parzialmente indicizzati:

- Dopo l'esecuzione di una ricerca, il numero di elementi parzialmente stimati viene visualizzato nelle statistiche di ricerca. Questa stima non include elementi parzialmente indicizzati in SharePoint Online e OneDrive for Business. Esportare i report per una ricerca di contenuto per ottenere informazioni sugli elementi parzialmente indicizzati. Il **report non indicizzato items.csv** contiene informazioni sugli elementi non indicizzati, inclusa la posizione dell'elemento, l'URL se l'elemento è in SharePoint Online o OneDrive for Business e la riga oggetto (per i messaggi) o il nome del documento. Per ulteriori informazioni, vedere [Esportare i risultati di Ricerca contenuto](https://support.office.com/article/Export-a-Content-Search-report-5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9).

- Le statistiche e l'elenco degli elementi parzialmente indicizzati restituiti con i risultati di una Ricerca contenuto sono tutti gli elementi parziali dei percorsi di contenuto in cui è stata effettuata la ricerca.

- Per recuperare gli elementi parzialmente indicizzati potenzialmente utili per un'indagine DSR, è possibile eseguire una delle operazioni seguenti:

##### <a name="export-all-partially-indexed-items"></a>Esportare tutti gli elementi parzialmente indicizzati

Si esportano i risultati di una ricerca contenuto e degli elementi parzialmente indicizzati dal percorso di contenuto in cui sono state eseguite ricerche. È anche possibile esportare solo gli elementi indicizzati parzialmente. È quindi possibile aprirle nell'applicazione nativa ed esaminare il contenuto. È necessario usare questa opzione per esportare gli elementi di SharePoint Online e OneDrive for Business. Vedere [Esportare i risultati di Ricerca contenuto dal Centro sicurezza e conformità di Office 365](https://support.office.com/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278).

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>Esportare un set specifico di elementi parzialmente indicizzati dalle cassette postali

Anziché esportare tutti gli elementi delle cassette postali indicizzate parzialmente da una ricerca, è possibile rieseguire una ricerca contenuto per cercare un elenco specifico di elementi parzialmente indicizzati e quindi esportarli. È possibile eseguire questa operazione solo per gli elementi della cassetta postale. Vedere [Preparare un file CSV per una ricerca di contenuto mirata in Office 365](https://support.office.com/article/prepare-a-csv-file-for-a-targeted-content-search-in-office-365-82c97bb4-2b64-4edc-804d-cedbda525d22).

### <a name="next-steps"></a>Passaggi successivi

Dopo aver trovato i dati personali pertinenti per il DSR, assicurarsi di mantenere la ricerca contenuto specifica usata per trovare i dati. È probabile che la ricerca venga riutilizzata per eseguire altri passaggi nel processo di risposta DSR, come [ ottenerne una copia](#providing-a-copy-of-personal-data),[esportarla](#exporting-personal-data) o [eliminarla definitivamente](#deleting-personal-data).

### <a name="additional-considerations-for-selected-applications"></a>Considerazioni aggiuntive sulle applicazioni selezionate

Le sezioni seguenti descrivono aspetti da tenere in considerazione quando si cercano dati nelle applicazioni di Office 365 seguenti.

- [Office Lens](#office-lens)
- [Impostazioni degli ambienti OneDrive for Business e SharePoint](#onedrive-for-business-and-sharepoint-online-experience-settings)
- [Microsoft Teams per l'istruzione](#microsoft-teams-for-education)
- [Microsoft To-Do](#microsoft-to-do)
- [Skype for Business](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

Una persona che usa Office Lens (un'app di fotocamera supportata da dispositivi con iOS, Android e Windows) può scattare una foto di lavagne, documenti cartacei, biglietti da visita e altri elementi che contengono molto testo. Office Lens usa la tecnologia Optical Character Recognition, che estrae il testo di un'immagine e la Salva in un documento di Office, come Word, PowerPoint e OneNote, o in un file PDF. Gli utenti possono quindi caricare il file che contiene il testo dell'immagine nell'account di OneDrive for Business in Office 365. Ciò significa che è possibile usare lo strumento ricerca contenuto per cercare, accedere, eliminare ed esportare dati nei file creati da un'immagine di Office Lens. Per altre informazioni su Office Lens, vedere:

- [Office Lens per iOS](https://support.office.com/article/Office-Lens-for-iOS-fbdca5f4-1b1b-4391-a931-dc1c2582397b)
- [Office Lens per Android](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)
- [Office Lens per Windows](https://support.office.com/article/Office-Lens-for-Windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>Impostazioni degli ambienti OneDrive for Business e SharePoint

Oltre ai file creati dall'utente archiviati negli account OneDrive for Business e nei siti di SharePoint Online, questi servizi archiviano informazioni sull'utente che vengono usate per abilitare varie esperienze. Gli utenti nell'organizzazione possono accedere a molte di queste informazioni usando funzionalità all'interno del prodotto. Le informazioni seguenti includono indicazioni su come accedere, visualizzare ed esportare i dati delle applicazioni OneDrive for Business e SharePoint Online.

##### <a name="sharepoint-user-profiles"></a>Profili utente di SharePoint

Il profilo Delve consente agli utenti di mantenere le proprietà archiviate nel profilo utente di SharePoint Online, tra cui data di nascita, numero di cellulare (e altre informazioni di contatto), informazioni personali, progetti, competenze ed esperienze, studi e istruzione, interessi e hobby.

###### <a name="end-users"></a>Utenti finali

Gli utenti finali possono individuare, accedere e correggere i dati dei profili utente di SharePoint Online con l'esperienza del profilo Delve. Per altre informazioni, vedere [Visualizzare e aggiornare il profilo personale in Office Delve](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba).

Un altro modo per gli utenti di accedere ai dati del proprio profilo SharePoint è quello di andare alla pagina di **modifica del profilo** nel proprio account OneDrive for Business, a cui si può accedere dal percorso **EditProfile.aspx** nell'URL dell'account OneDrive for Business. Per un utente <strong>user1@contoso.com</strong>, ad esempio, l'account di OneDrive for Business dell'utente è disponibile in:

```
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`
```

L'URL della pagina di modifica del profilo è:

```
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`
```

Le proprietà di origine di Azure Active Directory non possono essere modificate in SharePoint Online. Tuttavia, gli utenti possono accedere alla pagina dell' **account personale** selezionando la propria **foto** nell'intestazione di Office 365, quindi selezionando **account personale**. Se si modificano le proprietà, è possibile che gli utenti possano collaborare con gli amministratori per individuare, accedere o rettificare una proprietà del profilo utente.

###### <a name="admins"></a>Amministratori

Un amministratore può accedere e rettificare le proprietà del profilo nell'interfaccia di amministrazione di SharePoint. Nell’**interfaccia di amministrazione di SharePoint**, fare clic sulla scheda **profili utente**. Fare clic su**Gestisci profili utente**, immettere il nome di un utente e fare clic su **Trova**. L’amministratore può fare clic con il pulsante destro del mouse e scegliere **Modifica profilo personale**. Le proprietà di origine di Azure Active Directory non possono essere modificate in SharePoint Online.

Un amministratore può esportare tutte le proprietà del profilo di un utente usando il cmdlet **Export-SPOUserProfile** in PowerShell di SharePoint Online. Vedere [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps).

Per ulteriori informazioni sui profili utente, vedere [Gestire i profili utente nell'interfaccia di amministrazione di SharePoint](https://support.office.com/article/Manage-user-profiles-in-the-SharePoint-admin-center-494bec9c-6654-41f0-920f-f7f937ea9723).

##### <a name="user-information-list-on-sharepoint-online-sites"></a>Elenco Informazioni utente nei siti di SharePoint Online

Un sottoinsieme del profilo utente di SharePoint di un utente viene sincronizzato con l'elenco di informazioni utente di tutti i siti di visitati o di cui si dispone delle autorizzazioni di accesso. Questa operazione viene usata dalle esperienze di SharePoint Online, ad esempio le colonne di persone nelle raccolte documenti, per visualizzare le informazioni di base sull'utente, ad esempio il nome dell'autore di un documento. I dati contenuti in un elenco di informazioni utente corrispondono alle informazioni archiviate nel profilo utente di SharePoint e verranno automaticamente rettificate se l'origine viene cambiata. Per gli utenti eliminati, questi dati rimangono nei siti con cui hanno interagito per l'integrità referenziale dei campi colonna di SharePoint. 

Gli amministratori possono controllare quali proprietà sono replicabili all'interno dell'interfaccia di amministrazione di SharePoint. A tal fine devono eseguire le operazioni seguenti:

1. Accedere all'**interfaccia di amministrazione di SharePoint** e fare clic sulla scheda **Profili utente**.
2. Fare clic su **Gestisci proprietà utente** per visualizzare un elenco di proprietà.
3. Fare clic con il pulsante destro del mouse su una proprietà qualsiasi, selezionare **Modifica** e modificare le varie impostazioni.
4. In **Impostazioni criteri** la proprietà replicabile controlla se la proprietà verrà rappresentata o meno nell'elenco Informazioni utente. Non tutte le proprietà supportano questa impostazione.

Un amministratore può esportare tutte le proprietà di Informazioni utente per un utente di un determinato sito usando il cmdlet **Export-SPOUserInfo** in PowerShell di SharePoint Online. Vedere [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps).

##### <a name="onedrive-for-business-experience-settings"></a>Impostazioni dell'ambiente OneDrive for Business

L'ambiente OneDrive for Business di un utente memorizza le informazioni per aiutare a trovare e a esplorare i contenuti di interesse. La maggior parte di queste informazioni è accessibile agli utenti finali tramite le funzionalità incluse nel prodotto. Un amministratore può esportare le informazioni usando uno [Script di PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) e i comandi del [modello a oggetti client (CSOM) di SharePoint](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code).

Vedere [Esportare le impostazioni di esperienza OneDrive for Business](https://docs.microsoft.com/sharepoint/export-odfb-lists) per ulteriori informazioni sulle impostazioni, su come vengono memorizzate e su come esportarle.

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>Ricerca in OneDrive for Business e SharePoint Online

L'esperienza di ricerca nell'app in OneDrive for Business e SharePoint Online consente di archiviare le query di ricerca di un utente per 30 giorni per aumentare la rilevanza dei risultati della ricerca. Un amministratore può esportare le query di ricerca per un utente usando il cmdlet **Export-SPOQueryLogs** in PowerShell di SharePoint Online. Vedere [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps).

#### <a name="microsoft-teams-for-education"></a>Microsoft Teams per l'istruzione

Microsoft Teams per l'istruzione offre due funzionalità di collaborazione aggiuntive che consentono a insegnanti e studenti di creare e archiviare dati personali: Attività e Blocco appunti di OneNote per la classe. È possibile usare Ricerca di contenuto per individuare i dati in entrambe le funzionalità.

##### <a name="assignments"></a>Attività

I file degli studenti associati a un'attività vengono memorizzati in una raccolta di documenti nel corrispondente sito di SharePoint Online dei team. Gli amministratori IT possono usare lo strumento Ricerca contenuto per cercare i file degli studenti che sono correlati alle attività. Un amministratore può ad esempio cercare tutti i siti di SharePoint Online nell'organizzazione e usare il nome e la classe di uno studente o il nome dell'attività nella query di ricerca per individuare i dati rilevanti per una richiesta DSR.

Esistono altri dati correlati alle Attività che non vengono memorizzati nel sito di SharePoint Online del team di classe e che pertanto non possono essere individuati con Ricerca contenuto. Questi dati includono:

- I file che l'insegnante assegna agli studenti nell'ambito dell'attività
- I voti degli studenti e i commenti dell'insegnante
- L'elenco di documenti inviati per un'attività da ogni studente
- Metadati di un'attività

Per questo tipo di dati, un amministratore IT o il proprietario dei dati (ad esempio un insegnante) potrebbe dover accedere all'attività nel team di classe per trovare i dati rilevanti per la richiesta DSR.

##### <a name="onenote-class-notebook"></a>Blocco appunti di OneNote per la classe

La funzionalità Blocco appunti di OneNote per la classe è disponibile nel sito di SharePoint Online del team di classe. Ogni studente della classe dispone di un blocco appunti privato che viene condiviso con l'insegnante. Sono disponibili anche una raccolta di documenti in cui l'insegnante può condividere i documenti con gli studenti e uno spazio di collaborazione per tutti gli studenti della classe. I dati correlati a queste funzionalità possono essere individuati con Ricerca contenuto.

Ecco le indicazioni specifiche per eseguire la ricerca di un blocco appunti della classe.

1. Eseguire una Ricerca contenuto usando i criteri di ricerca seguenti:

   - Cercare tutti i siti di SharePoint Online

   - Includere il nome del team di classe come parola chiave di ricerca, ad esempio, "9C Biology".

2. Visualizzare in anteprima i risultati della ricerca per individuare l'elemento corrispondente al blocco appunti della classe.
3. Selezionare l'elemento e quindi copiare il percorso della cartella che viene visualizzato nel riquadro dei dettagli. Questa è la cartella radice del blocco appunti della classe.
4. Modificare la ricerca creata nel passaggio 1 e sostituire il nome della classe nella query con parole chiave con il percorso della cartella del blocco appunti della classe, anteporre al percorso della cartella la proprietà del sito **path**, ad esempio **path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/"**. Ricordarsi di includere la barra finale e di racchiudere il tutto tra virgolette.
5. Aggiungere una condizione di ricerca e selezionare la condizione Tipo di file e usarne una per il valore del tipo di file. I file di OneNote vengono restituiti nei risultati della ricerca. La sintassi della parola chiave risultante avrà un aspetto simile al seguente:[](#building-search-queries-to-find-personal-data)
    ```
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```
6.  Eseguire di nuovo la Ricerca contenuto. Nei risultati della ricerca dovrebbero essere inclusi tutti i file di OneNote per il blocco appunti per la classe del team di classe.

#### <a name="microsoft-to-do"></a>Microsoft To-Do

Le cose da fare (denominate *attività* salvate in *elenchi attività*) in Microsoft To-Do vengono salvate come attività nella cassetta postale di Exchange Online di un utente. Ciò significa che è possibile usare lo strumento Ricerca contenuto per cercare, accedere, eliminare ed esportare le attività. Per altre informazioni, vedere [Configurare Microsoft To-Do](https://support.office.com/article/Set-up-Microsoft-To-Do-490c1a8c-2333-4952-8125-841afadb9620).

#### <a name="skype-for-business"></a>Skype for Business

Ecco alcune informazioni aggiuntive su come accedere, visualizzare ed esportare i dati personali in Skype for Business.

- I file allegati a una riunione vengono mantenuti nella riunione effettiva per 180 giorni e successivamente diventano inaccessibili. Questi file sono disponibili ai partecipanti di una riunione quando accettano la convocazione di riunione e quindi visualizzano o scaricano il file allegato. Vedere la sezione "Usare gli allegati nella riunione" in [Precaricare gli allegati per una riunione Skype for Business](https://support.office.com/article/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251).
- Le conversazioni di Skype for Business vengono conservate nella cartella Cronologia conversazioni delle cassette postali degli utenti. È possibile usare Ricerca contenuto per cercare nelle cassette postali i dati nelle conversazioni di Skype.
- Un interessato può esportare i propri contatti in Skype for Business. A tale fine, deve fare clic con il pulsante destro del mouse su un gruppo di contatti in Skype for Business e quindi fare clic su **Copia**. Può quindi incollare l'elenco di indirizzi e-mail in un documento di testo o di Word.
- Se la cassetta postale di Exchange Online di un partecipante alla riunione viene impostata su Blocco per controversia legale o viene assegnata a un criterio di conservazione di Office 365, i file allegati a una riunione vengono conservati nella cassetta postale dei partecipanti. È possibile usare Ricerca contenuto per cercare i file nella cassetta postale del partecipante, se non è scaduto il periodo di conservazione dei file. Per altre informazioni su come conservare i file, vedere [Retaining large files attached to a Skype for Business meeting](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting) (Conservazione di file di grandi dimensioni allegati a una riunione di Skype for Business).

## <a name="providing-a-copy-of-personal-data"></a>Creazione di una copia dei dati personali

Dopo avere individuato i dati personali potenzialmente pertinenti a una richiesta DSR, spetta all'amministratore e all'organizzazione decidere quali dati inviare all'interessato. È possibile inviare una copia del documento effettivo, una versione appositamente redatta o uno screenshot delle parti considerate condivisibili. Per ognuna di queste risposte a una richiesta di accesso, è necessario recuperare una copia del documento o altro elemento contenente i dati sensibili.

Quando si invia una copia all'interessato, potrebbe essere necessario rimuovere o redigere informazioni personali su altri interessati ed eventuali informazioni riservate.

### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>Usare Ricerca contenuto per ottenere una copia dei dati personali

Esistono due modi per usare lo strumento Ricerca contenuto per ottenere una copia di un documento o di un elemento di cassetta postale individuato tramite una ricerca.

- Visualizzare in anteprima i risultati della ricerca e quindi scaricare una copia del documento o dell'elemento. Questa è un'ottima soluzione per scaricare un numero limitato di elementi o file.
- Esportare i risultati della ricerca e quindi scaricare una copia di tutti gli elementi restituiti dalla ricerca. Questo metodo è più complesso, ma è un ottimo metodo per scaricare molti elementi che rispondono al DSR. Nell'esportazione dei risultati della ricerca sono inclusi anche report utili. È possibile usare questi report per ottenere altre informazioni su ogni elemento. Il **report results.csv** è utile perché contiene molte informazioni sugli elementi esportati, come la posizione esatta dell'elemento (ad esempio la cassetta postale per i messaggi di posta elettronica o l'URL di documenti o elenchi nei siti di SharePoint online e OneDrive for Business). Queste informazioni consentono di identificare il proprietario dell'elemento, nel caso in cui sia necessario contattarlo durante il processo di indagine DSR. Per altre informazioni sulle relazioni incluse quando si esportano i risultati della ricerca, vedere [Esportare un report di ricerca contenuto.](https://support.office.com/article/Export-a-Content-Search-report-5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9)

#### <a name="preview-and-download-items"></a>Visualizzare in anteprima gli elementi e scaricarli

Dopo aver eseguito una nuova ricerca o aver aperto una ricerca esistente, è possibile visualizzare in anteprima ogni elemento che corrisponde alla query di ricerca per verificare che sia correlato al DSR su cui si sta lavorando. Include anche elenchi e pagine Web di SharePoint che vengono restituiti nei risultati della ricerca. È anche possibile scaricare il file originale, se è necessario fornirli all’interessato. In entrambi i casi, è possibile acquisire uno screenshot in modo da soddisfare la richiesta dell’interessato a ottenere le informazioni.

Alcuni tipi di elementi non possono essere visualizzati in anteprima. Se un tipo di elemento o di file non è supportato per l'anteprima, è possibile scaricare un singolo elemento nel computer locale o in un'unità di rete mappata o un altro percorso di rete. È possibile visualizzare in anteprima solo i[tipi di file supportati.](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4)

Per visualizzare in anteprima gli elementi e scaricarli:

1. Aprire Ricerca contenuto nel Centro sicurezza e conformità.
2. Se i risultati non vengono visualizzati, fare clic su **Anteprima risultati**.
3. Fare clic su un elemento per visualizzarlo.
4. Fare clic su **Download original file** (Scarica file originale) per scaricare l'elemento nel computer locale. È necessario scaricare anche gli elementi che non possono essere visualizzati in anteprima.

Per altre informazioni sulla visualizzazione in anteprima dei risultati della ricerca, vedere [Anteprima dei risultati della ricerca](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4).

#### <a name="export-and-download-items"></a>Esportare e scaricare gli elementi

È anche possibile esportare i risultati di una ricerca contenuto per ottenere una copia di messaggi e-mail, documenti, elenchi e pagine Web contenente i dati personali, anche se questo approccio è più complesso rispetto alla visualizzazione in anteprima degli elementi. Per informazioni dettagliate sull'[esportazione dei risultati di una ricerca contenuto](#export-and-download-content-using-content-search), vedere la sezione successiva.

## <a name="exporting-personal-data"></a>Esportazione dei dati personali

Il "diritto alla portabilità dei dati" consente all'interessato di richiedere una copia elettronica dei dati personali in un "formato leggibile su computer, di uso comune e strutturato" e di richiedere che l'organizzazione trasmetta questi file elettronici a un altro titolare del trattamento dei dati. Microsoft supporta questo diritto in due modi:

- Offrendo applicazioni di Office 365 che salvano i dati in un formato elettronico, comunemente usato, nativo e leggibile al computer. Per altre informazioni sui formati di file di Office, vedere [formati di file di Office - documenti tecnici](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx).
- Consentendo all'organizzazione di esportare i dati nel formato di file nativo o in un formato (ad esempio CSV, TXT e JSON) che possa essere facilmente importato in un'altra applicazione.

Per soddisfare una richiesta di esportazione DSR, è possibile esportare i documenti di Office nel formato di file nativo ed esportare dati da altre applicazioni di Office 365.

### <a name="export-and-download-content-using-content-search"></a>Esportare e scaricare contenuto tramite Ricerca contenuto

Quando si esportano i risultati di una Ricerca contenuto, è possibile scaricare gli elementi di posta elettronica come file PST o come singoli elementi (file con estensione msg). Quando si esportano documenti ed elenchi dai siti di SharePoint Online e OneDrive for Business, vengono esportate copie nei formati di file nativo. Gli elenchi di SharePoint, ad esempio, vengono esportati come file CSV e le pagine Web vengono esportate come file con estensione aspx o html.

> [!NOTE]
> L'esportazione di elementi della cassetta postale di un utente tramite Ricerca contenuto richiede che l'utente (proprietario della cassetta postale da cui si stanno esportando gli elementi) disponga di una licenza di Exchange Online piano 2. 

Per esportare e scaricare gli elementi:

1. Aprire Ricerca contenuto nel Centro sicurezza e conformità.
2. Nella pagina di ricerca a comparsa fare clic su ![](media/o365-dsr_image21.png) **Altro** e quindi su **Esporta risultati**. È possibile esportare anche un report.
3. Completare le sezioni nella pagina a comparsa **Esporta risultati**. Assicurarsi di usare la barra di scorrimento per visualizzare tutte le opzioni di esportazione.
4. Tornare alla pagina Ricerca contenuto nel Centro sicurezza e conformità e fare clic sulla scheda **Esporta**.
5. Fare clic su **Aggiorna** per aggiornare la pagina.
6. Nella colonna**Nome** fare clic sul processo di esportazione creato.  Il nome del processo di esportazione è il nome della ricerca contenuto aggiunta all’ ** \_esportazione**.
7. Nella pagina esportazioni al volo, in**Chiave di esportazione**,**fare clic su copia negli Appunti**. Si utilizzerà questa chiave per scaricare i risultati della ricerca nel passaggio 10.
8. Nella parte superiore della pagina a comparsa fare clic su ![](media/o365-dsr_image21.png) **Scarica risultati**.
9. Se viene chiesto di installare lo **strumento di esportazione di eDiscovery di Microsoft Office 365**, fare clic su **Installa**.
10. Nello **strumento di esportazione di eDiscovery** incollare nella casella appropriata la chiave di esportazione copiata nel passaggio 7.
11. Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare i file dei risultati della ricerca.
12. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer.

Al termine del processo di esportazione, è possibile accedere ai file nel percorso del computer locale in cui sono stati scaricati. I risultati di una ricerca di contenuto vengono scaricati in una cartella che ha lo stesso nome della Ricerca contenuto. I documenti di siti vengono copiati in una sottocartella denominata **SharePoint**. Gli elementi della cassetta postale vengono copiati in una sottocartella denominata **Exchange**.

Per le istruzioni dettagliate, vedere [Esportare i risultati di Ricerca contenuto dal Centro sicurezza e conformità di Office 365](https://support.office.com/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278).

### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>Download di documenti ed elenchi da SharePoint Online e OneDrive for Business

Un altro modo per esportare i dati da SharePoint Online e OneDrive for Business consiste nello scaricare i documenti e gli elenchi direttamente da un sito di SharePoint Online o un account OneDrive for Business. È necessario disporre delle autorizzazioni per accedere a un sito e quindi accedervi e scaricare i contenuti. Vedere:

- [Scaricare file e cartelle da OneDrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)
- [Esportare gli elenchi di SharePoint in Excel](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

Per alcune richieste di esportazione DSR, è consigliabile consentire agli interessati di scaricare personalmente il contenuto. In questo modo gli interessati possono accedere a un sito o a una cartella condivisa di SharePoint Online e fare clic su **Sincronizza** per sincronizzare tutti i contenuti nella raccolta documenti o nelle cartelle selezionate. Vedere:

- [Consentire agli utenti di sincronizzare i file di SharePoint con il nuovo client di sincronizzazione di OneDrive](https://support.office.com/article/Enable-users-to-sync-SharePoint-files-with-the-new-OneDrive-sync-client-22e1f635-fb89-49e0-a176-edab26f69614)
- [Sincronizzare i file di SharePoint con il nuovo client di sincronizzazione di OneDrive](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>Eliminazione dei dati personali

Il "diritto di cancellazione" dei dati personali dai dati dei clienti di un'organizzazione è un fattore di protezione chiave nel GDPR. La rimozione dei dati personali include l'eliminazione di interi documenti o file o l'eliminazione di dati specifici all'interno di un documento o di un file (che si rivela essere un'azione e un processo analogo a quelli descritti nella sezione di Rettifica di questa guida).

Durante l'analisi o la preparazione all'eliminazione di dati personali in risposta a una richiesta DSR, ecco alcuni aspetti importanti per capire come funziona l'eliminazione (o la conservazione) dei dati in Office 365.

- Differenza tra eliminazione temporanea ed eliminazione definitiva - Nei servizi di Office 365 come Exchange Online, SharePoint Online e OneDrive for Business esistono i concetti di *eliminazione temporanea* e di *eliminazione definitiva*, che sono correlati alla recuperabilità di un elemento eliminato (in genere per un periodo limitato) prima che venga rimosso dal cloud Microsoft senza possibilità di ripristinarlo. In questo contesto, un elemento eliminato temporaneamente può essere recuperato da un utente e/o da un amministratore per un periodo di tempo limitato prima dell'eliminazione definitiva. Quando un elemento viene eliminato in modo definitivo, viene contrassegnato per la rimozione permanente e ripulito quando viene elaborato dal servizio di Office 365 corrispondente. Di seguito viene descritto il funzionamento dell'eliminazione temporanea e definitiva per gli elementi nelle cassette postali e nei siti, a prescindere che sia il proprietario dei dati o un amministratore a eseguire l'operazione:

    - **Cassette postali:** un elemento viene eliminato temporaneamente quando viene eliminato dalla cartella Posta eliminata o quando un utente lo elimina premendo **MAIUSC+CANC**. Quando un elemento viene eliminato temporaneamente, viene spostato nella cartella Elementi ripristinabili della cassetta postale. L'utente ha la possibilità di recuperare l'elemento finché il periodo di conservazione dell'elemento eliminato non scade. In Office 365, il periodo di conservazione degli elementi eliminati è di 14 giorni, ma può essere esteso fino a 30 giorni da un amministratore. Alla scadenza del periodo di conservazione, l'elemento viene eliminato definitivamente e spostato in una cartella nascosta, denominata cartella delle *Ripuliture*. L'elemento verrà eliminato definitivamente (ripulito) da Office 365 alla successiva elaborazione della cassetta postale. Le cassette postali vengono elaborate una volta ogni sette giorni.

    - **Siti di SharePoint Online e OneDrive for Business**: quando un file o un documento viene eliminato, viene spostato nel Cestino del sito, anche noto come *Cestino di primo livello* e simile al Cestino di Windows. L'elemento rimane nel Cestino per 93 giorni (il periodo di conservazione degli elementi eliminati nei siti in Office 365). Dopo tale periodo, l'elemento viene automaticamente spostato nel Cestino della raccolta siti, noto anche come *Cestino di secondo livello*. Si noti che gli utenti o gli amministratori con le autorizzazioni appropriate possono eliminare elementi anche dal Cestino di primo livello. L'elemento diventa a questo punto un elemento eliminato temporaneamente. Può ancora essere ripristinato da un amministratore della raccolta siti in SharePoint Online o dall'utente o l'amministratore in OneDrive for Business. Quando un elemento viene eliminato dal Cestino di secondo livello (manualmente o automaticamente), diventa un elemento eliminato definitivamente e non è accessibile da parte dell'utente o di un amministratore. Il periodo di conservazione è di 93 giorni sia per il Cestino di primo livello che per quello di secondo livello. Questo significa che il periodo di conservazione nel Cestino di secondo livello inizia quando l'elemento viene eliminato la prima volta. Di conseguenza, il periodo di conservazione massimo totale è 93 giorni per entrambi i cestini.

> [!NOTE]
> La comprensione delle azioni che determinano l'eliminazione temporanea o definitiva di un elemento aiuta a stabilire come eliminare i dati conformemente ai requisiti GDPR quando si risponde a una richiesta di eliminazione.

- * * Disposizioni legali e criteri di conservazione — in Office 365, un "blocco" può essere applicato a cassette postali e siti. In breve, questo significa che nulla è stato rimosso definitivamente (eliminazione definitiva), se una cassetta postale o un sito è bloccato, fino alla scadenza del periodo di conservazione di un elemento o finché il blocco non viene rimosso. Questo aspetto è importante nel contesto dell'eliminazione del contenuto del cliente in risposta a un DSR: se un elemento è stato eliminato in modo definitivo da un percorso di contenuto bloccato, l'elemento non viene rimosso definitivamente da Office 365. Ciò significa che potrebbe essere recuperato da un amministratore IT. Se l'organizzazione ha un requisito o criteri secondo cui i dati devono essere eliminati in modo definitivo e non possono essere recuperati in Office 365 in risposta al DSR, il blocco deve essere rimosso da una cassetta postale o un sito per eliminare definitivamente i dati in Office 365. È molto probabile che le linee guida dell'organizzazione per rispondere ai DSR abbiano un processo per determinare se una specifica richiesta di eliminazione DSR o un blocco legale ha la precedenza. Se un blocco viene rimosso al fine di eliminare degli elementi, è possibile reimplementarlo dopo l'eliminazione dell'elemento.

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>Eliminazione di documenti in SharePoint Online e OneDrive for Business

Dopo avere trovato il documento che deve essere eliminato in un sito di SharePoint Online o in un account OneDrive for Business (seguendo le istruzioni della sezione Individuazione della presente guida), un responsabile della privacy dei dati o un amministratore IT deve disporre delle autorizzazioni necessarie per accedere al sito ed eliminare il documento. Se appropriato, anche il proprietario del documento può essere autorizzato a eliminare il documento.

Di seguito viene descritto il processo di alto livello per l'eliminazione di documenti dai siti.

1. Accedere al sito e individuare il documento.
2. Eliminare il documento. Quando si elimina un documento da un sito, il documento viene inviato al Cestino di primo livello.
3. Passare al Cestino di primo livello (il Cestino del sito) ed eliminare lo stesso documento eliminato nel passaggio precedente. Il documento viene inviato al Cestino di secondo livello. **Il documento risulta così eliminato temporaneamente**.
4. Passare al Cestino di secondo livello (il Cestino della raccolta siti) ed eliminare lo stesso documento eliminato dal Cestino di primo livello. **Il documento risulta così eliminato definitivamente.**

> [!IMPORTANT]
> Non è possibile eliminare un documento che si trova in un sito con blocco (con una delle funzionalità di blocco a fini giudiziari o i criteri di conservazione di Office 365). Nel caso in cui una richiesta di eliminazione DSR abbia precedenza su un blocco a fini giudiziari, il blocco dovrà essere rimosso dal sito prima di poter eliminare definitivamente un documento.

Per le istruzioni dettagliate, vedere gli argomenti seguenti.

- [Eliminare un file, una cartella o un collegamento da una raccolta documenti di SharePoint](https://support.office.com/article/Delete-a-file-folder-or-link-from-a-SharePoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52#ID0EAADAAA=Online)
- [Eliminare elementi o svuotare il Cestino di un sito di SharePoint](https://support.office.com/article/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e#ID0EAADAAA=Online)
- [Eliminare elementi dal Cestino raccolta siti](https://support.office.com/article/Delete-items-from-the-site-collection-Recycle-Bin-dd5c00c2-aef6-4458-9d04-80b185077653#ID0EAADAAA=Online)
- Sezione "Accedere ai documenti di OneDrive for Business dell'ex dipendente" in [Accedere ai dati di un ex utente ed eseguirne il backup](https://support.office.com/article/get-access-to-and-back-up-a-former-user-s-data-a6f7f9ad-e3f5-43de-ade5-e5a0d7531604)
- [Eliminare i file o cartelle in OneDrive for Business](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)
- [Eliminare un elenco in SharePoint](https://support.office.com/article/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d#ID0EAADAAA=Online)
- [Eliminare elementi dell'elenco in SharePoint Online](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>Eliminazione di un sito di SharePoint

Si potrebbe determinare che il modo migliore per rispondere a una richiesta di eliminazione DSR sia di eliminare un intero sito di SharePoint, con conseguente eliminazione di tutti i dati presenti nel sito. È possibile eseguire questa operazione usando i cmdlet di PowerShell di SharePoint Online.

- Usare il cmdlet [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) per eliminare il sito e spostarlo nel Cestino di SharePoint Online (eliminazione temporanea).
- Usare il cmdlet [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) per eliminare il sito in modo permanente (eliminazione definitiva).

Non è possibile eliminare un sito che si trova in un blocco eDiscovery o è assegnato a un criterio di conservazione. I siti devono essere rimossi dai criteri di conservazione o di conservazione di eDiscovery per poterli eliminare.

### <a name="deleting-a-onedrive-for-business-site"></a>Eliminazione di un sito di OneDrive for Business

Analogamente ai siti di SharePoint, è possibile stabilire di eliminare il sito di OneDrive for Business di un utente in risposta a una richiesta di eliminazione DSR. Se si elimina l'account di Office 365 di un utente, il sito di OneDrive for Business viene conservato (ed è ripristinabile) per 30 giorni. Dopo questo periodo, il sito viene spostato nel Cestino di SharePoint Online (eliminazione temporanea) e dopo 93 giorni viene rimosso definitivamente (eliminazione definitiva). Per accelerare questo processo, è possibile usare il cmdlet [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) per spostare il sito di OneDrive for Business nel Cestino e poi usare il cmdlet [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) per eliminarlo definitivamente. Come avviene con i siti di SharePoint Online, non è possibile eliminare il sito di OneDrive for Business di un utente a cui sono stati associati blocchi di eDiscovery o criteri di conservazione prima che l'account dell'utente venisse eliminato.

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>Eliminazione delle impostazioni degli ambienti OneDrive for Business e SharePoint Online

Oltre ai file creati dall'utente conservati in account OneDrive for Business e in siti di SharePoint Online, questi servizi conservano le informazioni sull'utente che vengono usate per abilitare esperienze diverse. Queste informazioni sono state trattate in precedenza in questo documento. Per informazioni su come accedere, visualizzare ed esportare i dati dell’applicazione di OneDrive for Business e SharePoint Online, vedere la sezione [Considerazioni aggiuntive per le applicazioni selezionate](#additional-considerations-for-selected-applications) in [Utilizzo dello strumento Ricerca contenuto di eDiscovery per rispondere alle richieste dell'interessato](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs).

#### <a name="deleting-a-sharepoint-user-profile"></a>Eliminazione di un profilo utente di SharePoint

Il profilo utente di SharePoint viene eliminato definitivamente 30 giorni dopo l'eliminazione dell'account utente in Azure Active Directory. È tuttavia possibile eliminare definitivamente l'account utente. Questa operazione rimuove il profilo utente di SharePoint. Per altre informazioni, vedere la sezione [Eliminazione di un utente](#deleting-a-user) di questa guida.

Un amministratore può velocizzare l'eliminazione del profilo utente per un utente usando il cmdlet **Remove-SPOUserProfile** in PowerShell di SharePoint Online. Vedere [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps). Ciò richiede almeno l'eliminazione temporanea dell'utente in Azure Active Directory.

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>Eliminazione di elenchi Informazioni utente nei siti di SharePoint Online

Per gli utenti che hanno lasciato l'organizzazione, questi dati rimangono nei siti con cui hanno interagito per l'integrità referenziale dei campi delle colonne di SharePoint. Un amministratore può eliminare tutte le proprietà di Informazioni utente per un utente in un determinato sito usando il comando **Remove-SPOUserInfo** in PowerShell di SharePoint Online. Vedere [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps) per informazioni sull'esecuzione di questo cmdlet di PowerShell.

Per impostazione predefinita, questo comando conserva il nome visualizzato dell'utente ed elimina le proprietà come il numero di telefono, indirizzo e-mail, competenze e conoscenze o altre proprietà che sono state copiate dal profilo utente di SharePoint Online. Un amministratore può usare il parametro **RedactUser** per specificare un nome visualizzato alternativo per l'utente nell'elenco di informazioni utente. Questo problema interessa diverse parti dell'esperienza utente e comporta una perdita di informazioni quando si esamina la cronologia dei file nel sito.

La funzionalità di correzione, infine, non rimuove tutti i metadati o il contenuto di riferimento a un utente dai documenti. Il modo di raggiungere questa correzione di contenuto dei file è descritto nella sezione [Apportare modifiche al contenuto in OneDrive for Business e SharePoint Online](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online) di questa guida. Questo metodo consiste nello scaricare, eliminare e quindi caricare una copia corretta del file.

#### <a name="deleting-onedrive-for-business-experience-settings"></a>Eliminazione di impostazioni dell'ambiente OneDrive for Business

Per eliminare tutte le informazioni e le impostazioni dell'ambiente di OneDrive for Business, è consigliabile rimuovere il sito OneDrive for Business dell'utente, dopo aver riassegnato i file conservati ad altri utenti. Un amministratore può eliminare questi elenchi usando lo [Script di PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) e i comandi del [modello a oggetti client (CSOM) di SharePoint](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code). Vedere [Eliminare le impostazioni dell'ambiente OneDrive for Business](https://docs.microsoft.com/sharepoint/delete-odfb-lists) per ulteriori informazioni sulle impostazioni, su come vengono memorizzate e su come eliminarle.

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>Query di ricerca in OneDrive for Business e SharePoint Online

Le query di ricerca di un utente create nell'esperienza di ricerca di OneDrive for Business e SharePoint Online vengono automaticamente eliminate dopo 30 giorni dalla data di creazione.

### <a name="deleting-items-in-exchange-online-mailboxes"></a>Eliminazione di elementi nelle cassette postali di Exchange Online

Potrebbe essere necessario eliminare gli elementi nelle cassette postali di Exchange Online per soddisfare una richiesta di eliminazione DSR. È possibile eliminare gli elementi della cassetta postale in due modi, a seconda del fatto che gli elementi di destinazione vengano eliminati temporaneamente o definitivamente. Come i documenti nei siti di SharePoint Online o OneDrive for Business, gli elementi in una cassetta postale bloccati non possono essere eliminati definitivamente da Office 365. Il blocco deve essere rimosso prima che l'elemento possa essere eliminato. Anche in questo caso, è necessario determinare se il contenuto della cassetta postale o della richiesta di eliminazione del DSR avrà la precedenza.

#### <a name="soft-delete-mailbox-items"></a>Eliminare temporaneamente elementi della cassetta postale

È possibile usare la funzionalità azione Ricerca contenuto per eliminare gli elementi restituiti da una Ricerca contenuto. Come spiegato in precedenza, gli elementi eliminati temporaneamente, viene spostato nella cartella Elementi ripristinabili della cassetta postale.

Ecco una breve panoramica del processo:

1. Creare ed eseguire una ricerca contenuto per trovare gli elementi che si vogliono eliminare dalla cassetta postale utente. Potrebbe essere necessario eseguire di nuovo la ricerca in modo da limitare i risultati della ricerca in modo che vengano restituiti solo gli elementi che si vogliono eliminare nei risultati della ricerca.
2. Usare il comando **New-ComplianceSearchAction** **-Purge** in PowerShell di Office 365 per eliminare temporaneamente gli elementi restituiti dalla Ricerca contenuto creata nel passaggio precedente.

Per istruzioni dettagliate, vedere [Cercare ed eliminare messaggi di posta elettronica nell'organizzazione di Office 365](https://support.office.com/article/Search-for-and-delete-email-messages-in-your-Office-365-organization-Admin-Help-3526fd06-b45f-445b-aed4-5ebd37b3762a).

#### <a name="hard-delete-mailbox-items"></a>Eliminare definitivamente elementi della cassetta postale

Se occorre eliminare definitivamente elementi della cassetta postale in risposta a una richiesta di eliminazione DSR, è possibile usare il comando **Search-Mailbox -DeleteContent** in PowerShell di Exchange Online. Se si usa questa modalità, considerare di usare Ricerca contenuto per sviluppare e definire una query di ricerca in modo che nei risultati vengano restituiti solo gli elementi da eliminare. È quindi possibile usare la sintassi di questa query quando si esegue il comando **Search-Mailbox -DeleteContent**.

Per istruzioni dettagliate, vedere [Cercare ed eliminare messaggi](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx).

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>Eliminare definitivamente gli elementi in una cassetta postale con blocco

Come spiegato in precedenza, se si eliminano definitivamente elementi in una cassetta postale con blocco, gli elementi non vengono rimossi dalla cassetta. Vengono spostati in una cartella nascosta nella cartella Elementi ripristinabili (la cartella **Puliture**) e vi restano per tutta la durata del blocco, che può scadere o essere rimosso. Se si verifica uno di questi eventi, gli elementi vengono ripuliti da Office 365 la volta successiva che la cassetta postale viene elaborata.

L'organizzazione potrebbe determinare che l'eliminazione definitiva degli elementi alla scadenza del blocco soddisfi i requisiti per una richiesta di eliminazione DSR. Se tuttavia si determina che gli elementi della cassetta postale debbano essere eliminati immediatamente da Office 365, è necessario rimuovere il blocco dalla cassetta postale e successivamente eliminare definitivamente gli elementi dalla cassetta postale. Per istruzioni dettagliate, vedere [Eliminare gli elementi nella cartella Elementi ripristinabili di cassette postali basate su cloud bloccate](https://support.office.com/article/Delete-items-in-the-Recoverable-Items-folder-of-cloud-based-mailboxes-on-hold-Admin-Help-a85e1c87-a48e-4715-bfa9-d5275cde67b0).

> [!NOTE]
> Per eliminare definitivamente elementi della cassetta postale per soddisfare una richiesta di eliminazione DSR seguendo la procedura indicata nell'argomento precedente, potrebbe essere necessario eliminare temporaneamente tali elementi mentre la cassetta postale è ancora bloccata in modo da spostarli nella cartella Elementi ripristinabili.

## <a name="deleting-a-user"></a>Eliminazione di un utente

Oltre all'eliminazione dei dati personali in risposta a una richiesta di eliminazione DSR, è possibile soddisfare il " diritto all'oblio" dell'interessato eliminandone l'account utente di Office 365. Ecco alcuni motivi per cui si potrebbe voler eliminare un utente:

- L'interessato ha lasciato o è in procinto di lasciare l'organizzazione.
- L'interessato ha chiesto di eliminare i log generati dal sistema che sono stati raccolti sul suo conto. Esempi di dati raccolti nei log generati dal sistema includono i dati di utilizzo dei servizi e delle app di Office 365, le informazioni sulle ricerche eseguite dall'interessato e i dati generati per prodotto e servizi come prodotto della funzionalità di sistema e dell'interazione da parte di utenti o altri sistemi. Per altre informazioni, vedere [Parte 3. Risposta alle richieste DSR per log generati dal sistema](#part-3-responding-to-dsrs-for-system-generated-logs) in questa guida.
- Impedire definitivamente all'interessato di accedere ai dati o di elaborarli in Office 365 (al contrario della limitazione di accesso temporanea con le modalità descritte nella sezione [Risposta alle richieste di restrizione DSR](#responding-to-dsr-restriction-requests)).

Dopo avere eliminato un account utente di Office 365:

- L'utente non può più accedere a Office 365 o accedere a qualsiasi delle risorse di Office 365 dell'organizzazione, ad esempio l'account OneDrive for Business, i siti di SharePoint Online o la cassetta postale di Exchange Online.
- I dati personali, ad esempio indirizzo e-mail, alias, numero di telefono e indirizzo postale, associati all'account utente vengono eliminati
- Alcune app di Office 365 rimuovono le informazioni sull'utente. Ad esempio, in Microsoft Flow, l'utente eliminato viene rimosso dall'elenco dei proprietari per un passaggio condiviso.
- I log generati dal sistema relativi all'interessato verranno eliminati 30 giorni dopo la data di eliminazione dell'account utente. Per ulteriori informazioni, vedere la sezione [Eliminazione di log generati dal sistema](#deleting-system-generated-logs).

> [!IMPORTANT]
> Dopo avere eliminato un account utente, l'utente perde la possibilità di accedere a Office 365 e la possibilità di accedere a tutti i prodotti o i servizi a cui prima si affidava per l'account di lavoro o di istruzione. Questo utente non è inoltre più in grado di avviare richieste DSR tramite Microsoft direttamente nei casi in cui Microsoft è il titolare del trattamento dei dati. Per altre informazioni, vedere la sezione [Prodotti e servizi autenticati con un ID di organizzazione per cui Microsoft è titolare del trattamento dei dati](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller) nella parte 4 di questa guida.

> [!NOTE]
> Se si è un cliente attualmente coinvolto in una migrazione di FastTrack, eliminando l'account utente di Office 365 non sarà eliminata la copia dei dati utilizzata dal team di Microsoft FastTrack, che viene conservata con il solo scopo di completare la migrazione. Se durante la migrazione si desidera che il team di Microsoft FastTrack elimini anche la copia dei dati, è possibile [inviare una richiesta](https://go.microsoft.com/fwlink/?linkid=874544). In condizioni normali di attività, Microsoft FastTrack eliminerà tutte le copie dei dati una volta completata la migrazione.

Come con le eliminazioni temporanea e definitiva dei dati descritte nella sezione precedente relativa all'eliminazione dei dati personali, anche quando si elimina un account utente esiste uno stato di eliminazione temporanea e uno di eliminazione definitiva.

- Quando si elimina inizialmente un account utente (eliminando l'utente nell'interfaccia di amministrazione o nel portale di Azure), questo viene eliminato temporaneamente e spostato nel Cestino in Azure per un tempo massimo di 30 giorni. A questo punto, è possibile ripristinare l'account utente.
- Se si elimina definitivamente l'account utente, questo viene rimosso dal Cestino in Azure. L'account utente a questo punto non può più essere ripristinato e tutti i dati ad esso associati vengono rimossi definitivamente dal cloud Microsoft. I log generati dal sistema relativi all'interessato verranno eliminati dopo l'eliminazione definitiva dell'account utente.

Ecco il processo ad alto livello per l'eliminazione di un utente dall'organizzazione Office 365.

1. Accedere all'interfaccia di amministrazione o al portale di Azure e individuare l'utente.

2. Eliminare l'utente. Quando inizialmente si elimina un utente, l'account utente viene inviato al Cestino. L'utente a questo punto è eliminato temporaneamente. L'account viene conservato nelle eliminazioni temporanee per 30 giorni, pertanto resta ripristinabile. Dopo tale periodo, l'account viene automaticamente eliminato in modo definitivo. Per istruzioni specifiche, vedere [Eliminare gli utenti da Azure Active Directory](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory).<br><br> È anche possibile eliminare temporaneamente un account utente nell'interfaccia di amministrazione. Vedere [Eliminare un utente dall'organizzazione](https://support.office.com/article/Delete-a-user-from-your-organization-D5155593-3BAC-4D8D-9D8B-F4513A81479E).

3. Se non si vuole aspettare 30 giorni prima che l'account utente venga eliminato definitivamente, è possibile eliminarlo del tutto manualmente. Per eseguire questa operazione nel portale di Azure, passare all'elenco utenti eliminati di recente ed eliminare definitivamente l'utente. A questo punto, l'utente viene eliminato in modo definitivo. Per istruzioni, vedere [Come rimuovere definitivamente un utente eliminato di recente](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore).

Non è possibile eliminare definitivamente un utente tramite l'interfaccia di amministrazione di Office 365.

> [!NOTE]
> In Office 365 gestito da 21Vianet (Cina), non è possibile eliminare definitivamente un utente come descritto in precedenza. Per eliminare definitivamente un utente, è possibile inviare una richiesta attraverso il portale di amministrazione di Office 365 a questo [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Accedere a **Commercio** e quindi selezionare **Abbonamento** -> **Privacy** ->  **GDPR** e immettere le informazioni obbligatorie.

### <a name="removing-exchange-online-data"></a>Rimozione di dati in Exchange Online

Una cosa da capire quando si elimina un utente è quello che accade alla cassetta postale di Exchange Online dell'utente. Dopo l'eliminazione dell'account utente (al passaggio 3 nel processo precedente), la cassetta postale dell'utente eliminato non viene eliminata automaticamente da Office 365. Sono necessari fino a 60 giorni dopo l'eliminazione definitiva dell'account utente per rimuoverlo definitivamente da Office 365. Ecco il ciclo di vita della cassetta postale dopo che l'account utente viene eliminato e una descrizione dello stato dei dati della cassetta postale durante quel periodo:

- **Dal giorno 1 al giorno 30**: la cassetta postale può essere ripristinata completamente ripristinando l'account utente eliminato temporaneamente.
- **Dal giorno 31 al giorno 60**: per 30 giorni dopo la data di eliminazione definitiva dell'account utente, un amministratore dell'organizzazione può recuperare i dati della cassetta postale e importarli in un'altra cassetta postale. Le organizzazioni di Office 365 possono quindi recuperare i dati delle cassette postali, se necessario.
- **Dal giorno 61 al giorno 90**: un amministratore non può più recuperare i dati della cassetta postale. Tali dati verranno contrassegnati per la rimozione permanente e dovranno trascorrere fino a ulteriori 30 giorni perché i dati della cassetta postale vengano rimossi da Office 365.

Se il ciclo di vita della cassetta postale non corrisponde ai requisiti dell'organizzazione per rispondere a una richiesta di eliminazione DSR, è possibile [contattare il Supporto tecnico Microsoft](https://support.microsoft.com/) *dopo* avere eliminato definitivamente l'account utente e richiedere a Microsoft di avviare manualmente la rimozione permanente dei dati della cassetta postale. Questo processo per rimuovere definitivamente i dati delle cassette postali inizia automaticamente dopo il giorno 61 nel ciclo di vita, pertanto non ci sarebbe alcun motivo di contattare Microsoft dopo questo periodo nel ciclo di vita.

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>Utilizzo della funzionalità in-app per rispondere alle richieste DSR

Sebbene la maggior parte dei dati dei clienti venga creata e prodotta con le applicazioni descritte nella sezione precedente, Office 365 offre anche molte altre applicazioni che i clienti possono usare per creare e archiviare i dati dei clienti. La funzionalità Ricerca contenuto tuttavia non offre al momento la possibilità di individuare i dati create in queste altre applicazioni di Office 365. Per trovare i dati generati da queste applicazioni, l'amministratore o il proprietario dei dati deve usare le funzionalità nel prodotto per trovare i dati che potrebbero essere rilevanti per una richiesta DSR. La tabella seguente elenca queste applicazioni di Office 365. Fare clic sull'icona dell'applicazione per passare alla sezione di questa guida che descrive come rispondere alle richieste DSR per i dati creati nell'applicazione.

***Tabella 3: Applicazioni in cui le funzionalità in-app possono essere usate per trovare i dati dei clienti***

||||
|:-----:|:-----:|:-----:|:-----:|
| ![Icona Access](media/o365-access-64x64.png) <br> [Access](#access) | ![Icona Office](media/O365-DSR-Doc_image22.png) <br> [App aziendali<br> per Office 365](#business-apps-for-office-365) | ![Icona Office](media/O365-DSR-Doc_image22.png) <br> [Funzionalità didattiche](#education)|
| ![Icona del flusso](media/o365-flow-64x64.png) <br> [Flusso](#flow) | ![Icona maschere](media/o365-forms-64x64.png) <br> [Maschere](#forms) |![Icona di Kaizala](media/o365-kaizala-64x64.png) <br> [Kaizala](#kaizala) |
| ![Icona Planner](media/o365-planner-64x64.png) <br> [Planner](#planner) |![Icona di PowerApps](media/o365-powerapps-64x64.png) <br> [Power Apps](#powerapps) |![Icona di Power BI](media/o365-powerbi-64x64.png) <br> [Power BI](#power-bi) |
|![Icona progetto](media/o365-project-64x64.png) <br> [Progetto](#project-online) |![Icona di Publisher](media/o365-publisher-64x64.png) <br> [Publisher](#publisher) |![Icona di StaffHub](media/o365-staffhub-64x64.png) <br> [StaffHub](#staffhub) |
|![Icona di Stream](media/o365-stream-64x64.png) <br> [Stream](#stream) |![Icona Sway](media/o365-sway-64x64.png) <br> [Sway](#sway) | ![Icona lavagna](media/O365-DSR-Doc_image36.png) <br> [Lavagna](#whiteboard) |
||![Icona di Yammer](media/o365-yammer-64x64.png) <br> [Yammer](#yammer) |
|||

### <a name="access"></a>Access

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Access per trovare, accedere, esportare ed eliminare i dati personali.

##### <a name="discover"></a>Individuazione

Esistono diversi modi per cercare record in un database di Access che potrebbero essere utili per rispondere a una richiesta DSR. Per un'indagine DSR, è possibile cercare i record correlati all'interessato o cercare i record che contengono dati specifici. Ad esempio, si può cercare o passare a un record corrispondente all'interessato. In alternativa, è possibile cercare i record che contengono dati specifici, come i dati personali dell'interessato. Per ulteriori informazioni, vedere:

- [Individuare record in un database di Access](https://support.office.com/article/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 
- [Creare una query di selezione semplice](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Accesso

Dopo aver trovato i record o i campi rilevanti per la richiesta DSR, è possibile acquisire una screenshot dei dati o esportarli in un file di Excel, un file di Word o un file di testo. È anche possibile creare e stampare un report in base a un'origine record o una query di selezione creata per trovare i dati. Vedere:

- [Introduzione ai report in Access](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)
- [Esportare dati in Excel](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)
- [Esportare dati in un documento di Word](https://support.office.com/article/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)
- [Esportare dati in un file di testo](https://support.office.com/article/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>Esportazione

Come descritto in precedenza, è possibile esportare i dati da un database di Access in formati di file diversi. Il formato di file di esportazione scelto può essere determinato dalla richiesta di esportazione DSR specifica di un oggetto dati. Vedere [importazione ed esportazione](https://support.office.com/article/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f) di un elenco di argomenti che descrivono come esportare i dati di Access in formati di file diversi.

##### <a name="delete"></a>Eliminazione

È possibile eliminare un intero record o solo un campo da un database di Access. Il modo più rapido per eliminare un record da un database di Access consiste nell'aprire la tabella in visualizzazione foglio dati, selezionare il record (riga) o solo i dati di un campo che si vuole eliminare e quindi premere CANC. È anche possibile usare una query di selezione creata per trovare i dati e quindi convertirla in una query di eliminazione. Vedere:

- [Eliminare uno o più record da un database](https://support.office.com/article/delete-one-or-more-records-from-a-database-002b850d-1efa-473d-9297-0994ce46c66a)
- [Creare ed eseguire una query di eliminazione](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>App aziendali per Office 365

Questa sezione spiega come usare le funzionalità in-app in ognuna delle seguenti App aziendali per Office 365 per rispondere alle richieste DSR.

- [Bookings](#bookings)
- [Listings](#listings)
- [Connections](#connections)
- [Outlook Customer Manager](#outlook-customer-manager)
- [Invoicing](#invoicing)

#### <a name="bookings"></a>Bookings

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Bookings per trovare, accedere, esportare ed eliminare i dati personali. Ciò vale sia per l'app di Bookings autonome che per le prenotazioni quando si accede attraverso il centro business.

Microsoft Bookings consente agli amministratori, agli utenti o al personale, con una licenza di Bookings nella propria organizzazione, di configurare le pagine per le prenotazioni affinché i clienti possano pianificare e modificare appuntamenti, ricevere e-mail di conferma, e-mail con aggiornamenti, cancellazioni e promemoria. I proprietari dell'azienda e il personale, inoltre, possono prenotare eventi per conto dei clienti con Bookings. 

I seguenti tipi di dati vengono creati da clienti, amministratori o membri del personale:

- **Informazioni di contatto di clienti, partner e amici.** Questi dati contengono nome, numero di telefono, indirizzo e-mail, indirizzo e note.

    - I contatti per tutti gli utenti possono essere creati manualmente con i client Android, iOS e Web di Bookings.
    
    - I contatti per tutti gli utenti possono essere importati dal dispositivo mobile di C1 in Bookings con i client Android e iOS di Bookings.
    
    - Inoltre, i contatti vengono creati automaticamente al momento della creazione delle prenotazioni con il flusso di lavoro di prenotazione per tutti gli utenti registrati (se la prenotazione viene creata da un utente per conto del cliente o se viene creata dal cliente con la pagina di prenotazione del proprietario).

- **Eventi di prenotazione**. Sono riunioni tra il titolare dell'azienda o il personale designato e un cliente; tali riunioni vengono create dal titolare dell'azienda o dal cliente tramite la pagina di prenotazione pubblica del titolare dell'azienda. Questi dati includono nome, indirizzo, indirizzo e-mail, numero di telefono e qualsiasi altra informazione sul cliente raccolta dal titolare dell'azienda al momento della prenotazione.

- **Conferme/cancellazioni/aggiornamenti tramite e-mail**. Si tratta di messaggi e-mail generati e inviati dal sistema per eventi di prenotazione specifici. Contengono dati personali sui membri del personale che fornirà il servizio e includono dati personali sul cliente che sono stati inseriti dal titolare dell'azienda o dal cliente al momento della prenotazione.

Tutto il contenuto del cliente è archiviato nella cassetta postale di Exchange Online che ospita le prenotazioni dell'organizzazione. Il contenuto viene conservato per tutto il tempo in cui il proprietario e il cliente sono attivi nel servizio, a meno che non chiedano esplicitamente che i dati vengano eliminati o di lasciare il servizio. Il contenuto può essere eliminato con l'interfaccia utente di prodotto, con un cmdlet o tramite l'eliminazione della cassetta postale di prenotazione appropriata. Dopo l'avvio dell'azione di eliminazione, i dati vengono eliminati entro il periodo di tempo impostato dal proprietario dell'azienda. 

Se un cliente decide di abbandonare il servizio, il contenuto del cliente viene eliminato dopo 90 giorni. Per altre informazioni su quando il contenuto delle cassette postali viene eliminato dopo che un account utente è stato eliminato, vedere [Rimuovere i dati di Exchange Online](#removing-exchange-online-data).

#### <a name="end-user-identifiable-information"></a>Informazioni personali dell'utente finale

Le informazioni personali dell'utente finale (EUII) includono dati personali e di contatto sui membri del personale pianificati in Bookings. Vengono aggiunte alle pagine dei dettagli sul personale quando il titolare dell'azienda configura Bookings ed esegue aggiornamenti dopo la configurazione. Includono il nome, le iniziali, l'indirizzo e-mail e ol numero di telefono del membro del personale. Questi dati vengono archiviati nella cassetta postale di Exchange Online che ospita Bookings.

Questi dati vengono mantenuti finché il membro del personale è attivo nel servizio, a meno che non vengano esplicitamente eliminati dal titolare dell'azienda o da un amministratore tramite l'interfaccia utente nell'app o eliminando la relativa cassetta postale. Quando l'amministratore inizia l'eliminazione dei dettagli del personale, o se il membro del personale lascia il servizio, i dettagli vengono eliminati conformemente ai criteri di conservazione del contenuto della cassetta postale di Exchange Online impostati dal titolare dell'azienda o dall'amministratore.

##### <a name="discoveraccess"></a>Individuazione/Accesso

Bookings raccoglie e memorizza i seguenti tipi di dati:

- **Informazioni sul profilo aziendale:** i contenuti dei clienti relativi all'azienda che usano Bookings vengono raccolti tramite il modulo di informazioni aziendali di Bookings e vengono sincronizzati con profilo Business nel Business Center se un cliente usa Bookings in combinazione con il Business Center. L'unica informazione personale dell'utente finale associata a questi dati è un indirizzo e-mail del C1: le e-mail con aggiornamenti e le notifiche sulle prenotazioni vengono inviate a tale indirizzo.
- **Contatti dei clienti: ** i contatti possono essere creati manualmente nei client Bookings Web, iOS e Android oppure possono essere importati da un dispositivo mobile. I contatti, inoltre, vengono creati automaticamente durante l'uso della pagina di prenotazione self-service. Includono le informazioni personali dell'utente finale e sono archiviati nella cassetta postale di Bookings.
- **Dettagli del personale: ** i contenuti dei clienti includono dati relativi ai membri del personale che possono fornire i servizi creati dai client Bookings Web, iOS e Android. I dettagli del personale possono contenere nome, indirizzo e-mail e numero di telefono.
- **Eventi di prenotazione: ** si tratta di riunioni dei clienti e relativi contenuti dei clienti creati dall'azienda usando un'app Web client o Android/iOS oppure creati dal cliente tramite una pagina di prenotazione pubblica (o una Pagina Facebook). Questi eventi possono includere nome, indirizzo, indirizzo e-mail, numero di telefono e dettagli sugli appuntamenti.
- **Richieste di riunione, conferme/cancellazioni/aggiornamenti e promemoria via e-mail:** si tratta di messaggi di posta elettronica inviati dal sistema insieme alle prenotazioni. Contengono dati sul personale e sui clienti che sono stati inseriti al momento della prenotazione.

##### <a name="export"></a>Esportazione

Per esportare i dati corrispondenti al titolare dell'azienda, al personale e ai clienti, è possibile utilizzare il portale sulla privacy Business Center. Vedere [Esportare o eliminare i dati degli utenti con il portale sulla privacy Business Center](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Eliminazione

È possibile eliminare i seguenti tipi di dati di Bookings in risposta a una richiesta di eliminazione DSR:

- **Contatti e informazioni sul profilo aziendale:** è possibile eliminare la cassetta postale di Bookings nell'interfaccia di amministrazione. Dopo aver eliminato la cassetta postale, è possibile ripristinarla entro 30 giorni. Dopo 30 giorni, l'account e la cassetta postale corrispondente vengono eliminati definitivamente. Per informazioni dettagliate sull'eliminazione di un account utente, vedere la sezione [Eliminazione di un utente](#deleting-a-user).
- **Dettagli del personale:** è possibile eliminare i membri del personale dal dashboard di Bookings. Per eliminare definitivamente i dettagli del personale, è possibile eliminarne l'account di Office 365.
- **Eventi di Bookings:** è possibile eliminare gli eventi di Bookings dal calendario di Bookings, che consente di rimuovere le informazioni del cliente.
- **Richieste di riunione, conferme/cancellazioni/aggiornamenti e promemoria via e-mail:** è possibile eliminare tutto ciò dal calendario di Bookings per rimuovere le informazioni del cliente.

Gli amministratori e i titolari dell'azienda possono anche eliminare i dati dei clienti tramite il portale sulla privacy Business Center. Vedere [Esportare o eliminare i dati degli utenti con il portale sulla privacy Business Center](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

Inoltre, è possibile eliminare il titolare dell'azienda e i dati del personale, nonché il corrispondente account utente di Office 365. Vedere la sezione [Eliminazione di un utente](#deleting-a-user).

#### <a name="listings"></a>Listings

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Listings per trovare, accedere, esportare ed eliminare i dati personali.

##### <a name="discover"></a>Individuazione

Il proprietario di Listings può connettere la propria azienda a Google, Bing, Yelp e Facebook per ottenere una visualizzazione aggregata di valutazioni e recensioni.  Listings raccoglie e memorizza i seguenti tipi di dati:

- Valutazioni e recensioni di Google
- Valutazioni e recensioni di Bing
- Valutazioni e recensioni di Yelp
- Valutazioni e recensioni di Facebook

##### <a name="access"></a>Accesso
I proprietari di Listings possono accedere alla dashboard di Listings per visualizzare valutazioni e recensioni.

##### <a name="export"></a>Esportazione

Per esportare i dati del titolare dell'azienda, del personale e dei clienti, utilizzare il portale sulla privacy Business Center. Vedere [Esportare o eliminare i dati degli utenti con il portale sulla privacy Business Center](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Eliminazione

Se un proprietario di Listings desidera eliminare le proprie informazioni di Listings, può disconnettersi dal provider nella pagina di Listings. In seguito alla disconnessione, le sue informazioni di Listings verranno eliminate.

#### <a name="connections"></a>Connections

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Connections per trovare, accedere, esportare ed eliminare i dati personali.

##### <a name="discover"></a>Individuazione

Connections raccoglie e memorizza i seguenti tipi di dati: 

- I clienti e i contatti vengono creati dall'azienda con il client Web o con l'app per dispositivi mobili (iOS, Android) oppure con l'app quando si invia un contatto commerciale a una campagna di marketing tramite posta elettronica. I dati dei clienti includono nome, indirizzo, indirizzo e-mail e codice fiscale. I contatti vengono condivisi nelle app del Business Center.
- I clienti possono registrarsi nella pagina di registrazione di Connections e salvare le proprie informazioni personali.
- Collegamenti da campagne di posta elettronica

##### <a name="access"></a>Accesso

Un proprietario di Connections può accedere al dashboard di Connections e visualizzare le campagne di posta elettronica che ha inviato.

##### <a name="export"></a>Esportazione

Per esportare i dati del titolare dell'azienda, del personale e dei clienti, utilizzare il portale sulla privacy Business Center. Vedere [Esportare o eliminare i dati degli utenti con il portale sulla privacy Business Center](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Eliminazione

Dopo che un proprietario di Connections invia una campagna tramite messaggi e-mail, non può eliminare la campagna. Se sono presenti bozze della campagna che desidera eliminare, può accedere al dashboard di Connections ed eliminarle.

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager

Le sezioni seguenti illustrano come usare la funzionalità in-app di Outlook Customer Manager per trovare i dati personali, accedervi, esportali ed eliminarli.

##### <a name="discover"></a>Individuazione

Outlook Customer Manager raccoglie e memorizza le informazioni utente per il proprietario di Outlook Customer Manager e i clienti e i contatti commerciali.

- Dati del proprietario. Includono nome, indirizzo e indirizzo e-mail. I documenti e i file che un proprietario condivide con un cliente vengono archiviati in OneDrive for Business, SharePoint Online e come attività in Outlook.
- Dati dei clienti e dei contatti commerciali. I dati dei clienti possono includere nome, indirizzo e indirizzo e-mail. I dati dei clienti e dei contatti vengono creati dall'azienda in Outlook o Outlook Web App. I contatti vengono condivisi nel Business Center. I documenti e i file che un cliente condivide con un'azienda vengono archiviati in OneDrive for Business, SharePoint Online e come attività in Outlook.

Outlook Customer Manager, inoltre, archivia le attività e i dati statistici sui clienti in Exchange.

##### <a name="access"></a>Accesso

I proprietari di Outlook Customer Manager possono accedere a Outlook o Outlook Web App e quindi al dashboard di Outlook Customer Manager per visualizzare le interazioni che hanno avuto con i loro clienti.

##### <a name="export"></a>Esportazione

Per esportare i dati del titolare dell'azienda e dei clienti, utilizzare il portale sulla privacy di Outlook Customer Manager. Per informazioni dettagliate, vedere [Esportare o eliminare i dati degli utenti con il portale sulla privacy Outlook Customer Manager](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Eliminazione

Per eliminare i dati dei clienti, utilizzare il portale sulla privacy di Outlook Customer Manager. Vedere [Esportare o eliminare i dati degli utenti con il portale sulla privacy Outlook Customer Manager](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

#### <a name="invoicing"></a>Invoicing

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Invoicing per trovare, accedere, esportare ed eliminare i dati personali.

##### <a name="discover"></a>Individuazione

Invoicing raccoglie e memorizza i seguenti tipi di dati:

- **Contatti:** vengono creati dall'azienda quando si crea una fattura o un preventivo per un contatto commerciale/cliente. I contatti vengono condivisi nel Business Center. I dati dei clienti includono nome, indirizzo, indirizzo e-mail e codice fiscale.
- **Fatture:** vengono create e inviate ai clienti e comportano un debito nei confronti dell'azienda e obblighi fiscali.
- **Preventivi:** l'azienda può anche inviare preventivi ai clienti. Se un cliente accetta un preventivo, quest'ultimo viene convertito in una fattura. Un preventivo viene convertito in una fattura dopo che viene accettato dal cliente. I record dei preventivi non vengono conservati in seguito alla loro conversione in fattura.

##### <a name="access"></a>Access

Gli utenti possono accedere al dashboard di Invoicing nel Business Center per visualizzare le bozze delle fatture che hanno creato e le fatture che sono state inviate ai clienti.

##### <a name="export"></a>Esportazione

Per esportare i dati relativi alla fatturazione dei clienti, utilizzare il portale sulla privacy Business Center. Vedere [Esportare o eliminare i dati degli utenti con il portale sulla privacy Business Center](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Eliminazione

Dopo la creazione e l'invio di una fattura, quest'ultima non può essere eliminata a causa della legislazione contabile. Il proprietario di Invoicing può richiedere che Microsoft elimini le proprie informazioni (tutte o in parte) da Office 365.

In alternativa, è possibile eliminare l'account utente del proprietario di Invoicing in Office 365. Vedere la sezione [Eliminazione di un utente](#deleting-a-user).

### <a name="education"></a>Istruzione

Questa sezione spiega come usare le funzionalità in-app delle seguenti app di Microsoft Education per rispondere alle richieste DSR.

- Attività
- Blocco appunti per la classe

#### <a name="assignments"></a>Attività

Le sezioni seguenti illustrano come usare la funzionalità in-app di Attività per trovare, accedere, esportare ed eliminare i dati personali.

##### <a name="discoveraccess"></a>Individuazione/Accesso

Attività memorizza le informazioni generate dagli insegnanti e dagli studenti. Alcune di queste informazioni vengono archiviate in SharePoint, mentre alcune vengono archiviate in una posizione diversa da SharePoint.

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>Trovare i dati di Attività archiviati in SharePoint

I file degli studenti associati a un invio per Attività vengono archiviati in una raccolta documenti (denominata **Lavoro degli studenti**) e i file associati ad Attività creati dagli insegnanti (e accessibili per gli studenti) vengono archiviati in un'altra raccolta documenti (denominata **File di classe**). Entrambe le raccolte documenti si trovano nel sito di SharePoint del team di classe corrispondente.

Un amministratore può usare lo strumento ricerca contenuto nel Centro sicurezza & conformità di Office 365 per cercare i file degli studenti (nelle raccolte lavoro studente e file della classe) correlati agli invii di assegnazioni e file relativi alle assegnazioni. Ad esempio, un amministratore può eseguire ricerche in tutti i siti di SharePoint dell'organizzazione e usare il nome dello studente e il nome della classe o dell'assegnazione nella query di ricerca per trovare i dati rilevanti per una richiesta di DSR.

Analogamente, un amministratore può cercare i file degli insegnanti correlati alle attività per i file che un insegnante ha distribuito agli studenti. Ad esempio, un amministratore potrebbe cercare in tutti i siti di SharePoint nell'organizzazione e usare il nome e la classe dell'insegnante o il nome dell'attività nella query di ricerca per individuare i dati rilevanti per una richiesta DSR.

Vedere la sezione [Utilizzo dello strumento Ricerca contenuto di eDiscovery per rispondere alle richieste DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) in questa guida.

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>Trovare i dati di Attività non archiviati in SharePoint

I seguenti tipi di dati di Attività non vengono archiviati nel sito di SharePoint del team di classe, pertanto non possono essere individuati tramite Ricerca contenuto.  Questi dati includono:

- I voti degli studenti e i commenti dell'insegnante
- L'elenco di documenti inviati per un'attività da ogni studente
- I dettagli delle attività, ad esempio la data di scadenza dell'assegnazione

Per trovare i dati che potrebbero essere rilevanti per una richiesta DSR, un amministratore o un insegnante deve accedere all'attività nel sito del team di classe. Un amministratore può aggiungere se stesso come proprietario della classe e visualizzare tutte le attività per tale team di classe.

Anche se uno studente non fa più parte di una classe, i dati potrebbero essere ancora presenti nel corso e contrassegnati come "non più iscritti". In questo caso, uno studente che invia una richiesta di DSR deve fornire all'amministratore l'elenco dei corsi che sono stati formalmente iscritti.

##### <a name="export"></a>Esportazione

È possibile esportare i dati di Attività per uno studente specifico per tutte le classi in cui è iscritto tramite uno script di PowerShell. Vedere:

- [Utilizzo di script per esportare ed eliminare i dati degli utenti da Attività](https://support.office.com/article/04473375-6c00-4dda-bfe5-b55a772958fe).
- [Esportare i dati degli studenti e degli insegnanti da Attività](https://support.office.com/article/e8c36e0e-fb6e-42c5-97fd-66f90f92a13a).

Se lo studente è stato rimosso dal sito del team di classe, l'amministratore può riaggiungerlo nel sito prima di eseguire lo script per l'esportazione. In alternativa, l'amministratore può usare il file di input per lo script per identificare tutte le classi alle quali lo studente sia mai stato iscritto. È anche possibile utilizzare lo script di esportazione di Attività per esportare i dati degli invii per tutte le attività alle quali ha accesso un insegnante.

##### <a name="delete"></a>Eliminazione

È possibile eliminare i dati di Attività per uno studente specifico per tutte le classi in cui è iscritto tramite uno script di PowerShell. Eseguire questa operazione prima di rimuovere lo studente dalla classe. Vedere:

- [Utilizzo di script per esportare ed eliminare i dati degli utenti da Attività](https://support.office.com/article/04473375-6c00-4dda-bfe5-b55a772958fe).

- [Eliminare i dati degli studenti da Attività](https://support.office.com/article/a368853a-9565-4320-8e86-2f9423e932a4).

Se lo studente è stato rimosso dal sito del team di classe, l'amministratore può riaggiungerlo nel sito prima di eseguire lo script per l'esportazione. In alternativa, l'amministratore può usare il file di input per lo script per identificare tutte le classi alle quali lo studente sia mai stato iscritto. Non è possibile utilizzare lo script di eliminazione di Attività per eliminare i dati degli insegnanti perché tutte le attività sono condivise nel sito del team di classe. In alternativa, un amministratore potrebbe aggiungere se stesso al sito del team di classe e quindi eliminare un'attività specifica.

**Blocco appunti per la classe:** la ricerca di contenuto in Blocco appunti per la classe è stata illustrata in precedenza nella presente guida. Vedere la sezione [Blocco appunti di OneNote per la classe](#onenote-class-notebook). È inoltre possibile usare lo strumento Ricerca contenuto per esportare i dati da un Blocco appunti per la classe. In alternativa, un amministratore o l'interessato può esportare i dati da un Blocco appunti per la classe. Vedere [Salvare una copia di un Blocco appunti per la classe.](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec)

### <a name="flow"></a>Flow

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Flow per trovare, accedere, esportare ed eliminare i dati personali.

#### <a name="discover"></a>Individuazione

Gli utenti possono usare Flow per eseguire attività correlate ai dati, ad esempio la sincronizzazione di file tra applicazioni, la copia di file da un servizio di Office 365 a un altro e la raccolta di dati da un'app di Office 365 e la relativa archiviazione in un'altra app. Un utente può ad esempio configurare Flow in modo da salvare gli allegati delle e-mail di Outlook nel proprio account OneDrive for Business. In questo esempio, si può usare lo strumento Ricerca contenuto per cercare nella cassetta postale dell'utente l'e-mail contenente l'allegato o cercare il file nell'account OneDrive for Business dell'utente. Questo è un esempio in cui i dati gestiti da Flow sono individuabili nel servizi di Office 365 connessi da un flusso di lavoro di Flow.

Gli utenti possono usare Flow anche per copiare o caricare file da Office 365 in un servizio esterno, ad esempio Dropbox. In questi casi, una richiesta DSR concernente i dati in un servizio esterno dovrebbe essere inoltrata al servizio esterno, che è preposto all'elaborazione dei dati in questo tipo di scenario.

Se un amministratore riceve una richiesta DSR, può aggiungersi come proprietario dei flussi di un utente. Questo consente a un amministratore di svolgere funzioni, tra cui l'esportazione delle definizioni di flussi, l'esecuzione di storie ed eseguire le riassegnazioni di autorizzazioni per il passaggio. Vedere [Gestire i flussi nell'interfaccia di](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)amministrazione di.

La possibilità di un amministratore di aggiungersi come proprietario di un flusso richiede un account con le autorizzazioni seguenti:

- Licenza per Flow/PowerApps piano 2 (a pagamento o versione di valutazione)

- [Amministratore globale di Office 365\ ](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504)

    oppure

- [Amministratore globale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

L'amministratore dotato di questi privilegi può usare l'interfaccia di amministrazione di Flow per accedere a tutti i flussi nell'organizzazione.

Per aggiungersi come proprietario di un flusso:

1. Passare a <https://admin.flow.microsoft.com>.
2. Accedere con le credenziali di Office 365.
3. Nella pagina **Environments** fare clic sull'ambiente per i flussi a cui si vuole accedere. Le organizzazioni di Office 365 hanno un ambiente predefinito.
4. Nella pagina dell'ambiente selezionato fare clic su **Risorse** e quindi su **Flussi**. Viene visualizzato un elenco di tutti i flussi nell'ambiente.
5. Fare clic su **Visualizza dettagli** per il flusso a cui ci si desidera aggiungere come membri.
6. In **Proprietari** fare clic su **Gestisci condivisione**.
7. Nella pagina a comparsa **Condividi** aggiungersi come membro e quindi salvare la modifica.

Dopo essere diventati proprietari, andare su **Flusso** \> **I miei flussi** \> **Flussi del team** per accedere ai flussi. Da qui è possibile scaricare il percorso o esportare il flusso. Vedere:

- [Download flow run history](https://flow.microsoft.com/blog/download-history-recurrence/) (Scaricare la cronologia delle esecuzioni del flusso)
- [Export and import your flows across environments with packaging](https://flow.microsoft.com/blog/import-export-bap-packages/) (Esportare e importare i flussi tra ambienti con creazione di pacchetti)

#### <a name="access"></a>Access

Un utente può accedere alle definizioni e alle cronologie di esecuzione dei propri flussi.

- **Definizioni del flusso:** un utente può esportare la definizione di un flusso (che viene esportato come pacchetto di Flow, in formato JSON in un file compresso). Vedere [Export and import your flows across environments with packaging](https://flow.microsoft.com/blog/import-export-bap-packages/) (Esportare e importare i flussi tra ambienti con creazione di pacchetti).
- **Cronologie di esecuzione del flusso:** un utente può scaricare la cronologia delle esecuzioni di ognuno dei flussi. La cronologia delle esecuzioni di un flusso viene scaricata come file CSV, che può essere aperto in Excel per usare i filtri o la ricerca. Gli utenti possono inoltre scaricare la cronologia delle esecuzioni di più flussi. Vedere [Download flow run history](https://flow.microsoft.com/blog/download-history-recurrence/) (Scaricare la cronologia delle esecuzioni del flusso).

#### <a name="delete"></a>Eliminazione

Un amministratore può aggiungersi come proprietario dei flussi di un utente nell'Interfaccia di amministrazione di Flow. Se un utente lascia l'organizzazione e il relativo account di Office 365 viene eliminato, i flussi di cui era l'unico proprietario verranno conservati. L'attribuzione dei flussi a un amministratore aiuta l'organizzazione a trasferire i flussi a nuovi proprietari e a evitare interruzioni nell'attività aziendale per flussi che potrebbero essere usati per processi aziendali condivisi. Un amministratore deve quindi determinare se eliminare i flussi appartenuti all'utente o assegnarli a nuovi proprietari e quindi intraprendere l'azione.

Per i flussi condivisi, quando un utente viene eliminato dall'organizzazione, il relativo nome viene rimosso dall'elenco dei proprietari.

#### <a name="export"></a>Esportazione

Un amministratore può esportare la definizione e la cronologia delle esecuzioni dei flussi di un utente. L'amministratore deve a tal fine aggiungersi come proprietario del flusso dell'utente nell'Interfaccia di amministrazione di Flow.

- **Definizioni del flusso:** dopo essersi aggiunto come proprietario di un flusso, l'amministratore può accedere a **Flow** \> **Flussi personali** \> **Flussi del team** per esportare la definizione del flusso (che viene esportata come pacchetto di Flow, in formato JSON in un file compresso). Vedere [Export and import your flows across environments with packaging](https://flow.microsoft.com/blog/import-export-bap-packages/) (Esportare e importare i flussi tra ambienti con creazione di pacchetti).

- **Cronologie di esecuzione del flusso:** un amministratore deve analogamente aggiungersi come proprietario di un flusso per esportarne la cronologia delle esecuzioni. La cronologia delle esecuzioni del flusso viene scaricata come file CSV, che può essere aperto in Excel per usare i filtri o la ricerca. È inoltre possibile scaricare la cronologia delle esecuzioni di più flussi, fintanto che se ne è proprietari. Vedere [Download flow run history](https://flow.microsoft.com/blog/download-history-recurrence/) (Scaricare la cronologia delle esecuzioni del flusso).

#### <a name="connections-and-custom-connectors-in-flow"></a>Connessioni e connettori personalizzati in Flow

Connessioni richiede agli utenti di fornire le credenziali per connettersi a API, applicazioni SaaS e sistemi sviluppati personalizzati. Queste connessioni appartengono all'utente che ha stabilito la connessione e possono essere [gestite](https://docs.microsoft.com/flow/add-manage-connections) nel prodotto. Dopo che i flussi sono stati riassegnati, un amministratore può usare i cmdlet di PowerShell per elencare ed eliminare queste connessioni come parte dell'eliminazione dei dati dell'utente.

I connettori personalizzati consentono alle organizzazioni di estendere le funzionalità del fluso connettendosi ai sistemi in cui non è disponibile un connettore. L'autore di un connettore personalizzato può [condividere ](https://docs.microsoft.com/flow/register-custom-api) il connettore con altri utenti dell'organizzazione. Dopo la ricezione di una richiesta di eliminazione DSR, un amministratore deve considerare la possibilità di riassegnare la proprietà di questi connettori per evitare interruzioni aziendali. Per accelerare questo processo, un amministratore può usare i cmdlet di PowerShell per elencare, riassegnare o eliminare i connettori personalizzati.

### <a name="forms"></a>Forms

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Forms per trovare, accedere, esportare ed eliminare i dati personali.

#### <a name="discover"></a>Individuazione

Gli utenti di Forms possono accedere a <https://forms.office.com> e selezionare **Moduli personali** per vedere i moduli creati. Possono inoltre selezionare **Shared with me** (Condivisi con me) per visualizzare i moduli che altri utenti hanno condiviso tramite un collegamento. Se sono presenti molti moduli tra cui scegliere, gli utenti possono usare la barra di ricerca nel prodotto per cercarli in base al titolo o all'autore. Per determinare se in Microsoft Forms possono risiedere i dati personali adatti a rispondere a una richiesta DSR, si può chiedere all'interessato di cercare l'elenco **Shared with me** (Condivisi con me) per determinare quali utenti ("proprietari di moduli") hanno inviato moduli all'interessato. Si può quindi chiedere ai proprietari di moduli di selezionare **Condividi** nella barra di spostamento superiore e di inviare un collegamento a un modulo specifico in modo da poterlo visualizzare e determinare se è materiale adatto alla richiesta DSR.

#### <a name="access"></a>Access

Dopo aver trovato Moduli interessanti, è possibile accedere alle risposte al modulo facendo clic sulla scheda **Risposte**. Altre informazioni su come [controllare i risultati del quiz](https://support.office.com/article/c4a9b45c-d62f-4eb7-b5db-ad81892c7c07) o [i risultati del modulo](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Per rivedere i risultati delle risposte in Excel, selezionare la scheda**Risposte** e quindi fare clic su **Apri in Excel**. Se si vuole inviare all'Oggetto dati una copia del modulo, è possibile acquisire screenshot delle domande e delle risposte pertinenti visualizzate nell'applicazione in formato RTF o inviare all'Oggetto dati una copia di Excel dei risultati. Se si usa Excel e si vuole condividere con l'oggetto dati solo parti del risultato del sondaggio, è possibile eliminare determinate righe o colonne o redigere le sezioni rimanenti prima di condividere i risultati. In alternativa, è possibile passare a **Condividi \> per ottenere un collegamento da duplicare**(in Condividi come modello), per fornire all'Oggetto dati una replica dell'intero modulo.

#### <a name="delete"></a>Eliminazione

Un'indagine, un quiz, un questionario o un sondaggio può essere eliminato definitivamente dal proprietario. Se si vuole onorare una richiesta DSR di "diritto all'oblio" ed eliminare un modulo completamente, individuarlo nell'elenco dei moduli, selezionare i tre puntini (ellisse) nell'angolo superiore destro della finestra di anteprima del modulo e quindi fare clic su **Elimina**. Dopo che è stato eliminato, un modulo non può essere ripristinato. Per informazioni, vedere [Delete a form](https://support.office.com/article/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0) (Eliminare un modulo).

#### <a name="export"></a>Esportazione

Per esportare le domande e le risposte di un modulo in un file di Excel, aprire il modulo, selezionare la scheda **Risposte** e quindi selezionare **Apri in Excel**.

### <a name="kaizala"></a>Kaizala

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Kaizala per trovare i dati personali, accedervi, esportali ed eliminarli.

#### <a name="discover"></a>Individuazione

Un amministratore può accedere ai dati dell'organizzazione di un utente, che sono condivisi nei gruppi aziendali, dal portale di gestione di Kaizala. I dati dell'organizzazione vengono conservati per un periodo di tempo determinato dai criteri di conservazione dell'organizzazione. Oltre ai dati degli utenti, i server Kaizala archiviano anche i seguenti tipi di dati dell'organizzazione:

- Elenco di membri che fanno parte dei gruppi dell'organizzazione
- Dati sui messaggi dei gruppi dell'organizzazione, ovvero i messaggi e le risposte condivisi tra i gruppi dell'organizzazione
- Un elenco degli utenti delle organizzazioni
- Dai sull'utilizzo di prodotti e servizi acquisiti per tutti gli utenti nell'organizzazione.
- Azioni di Kaizala create dall'organizzazione
- Dati dei connettori di Kaizala

L'interessato può accedere ai propri dati di consumo tramite l'apposita app per dispositivi mobili Kaizala. I dati di consumo includono i seguenti tipi di dati:

- Dati che appartengono a gruppi privati su Kaizala (archiviati nei server Kaizala per 90 giorni)
- Informazioni sul profilo utente e contatti dell'utente
- Elenco di membri che fanno parte degli stessi gruppi dell'utente
- Messaggi e risposte dei gruppi condivisi tra i gruppi
- Elenco contatti dell'utente (archiviato nel servizio Kaizala)
- Transazioni effettuate dall'utente su Kaizala (applicabile solo agli utenti di Kaizala in India)
- Dati sull'utilizzo di prodotti e servizi per l'utente

#### <a name="access"></a>Accesso

Gli utenti Kaizala possono accedere ai dispositivi mobili per visualizzare i contenuti di Kaizala che hanno creato nel dispositivo in uso. Per determinare se l'app per dispositivi mobili Kaizala possa ospitare dati personali rilevanti per una richiesta DSR, è possibile chiedere all'interessato di cercare nella propria app Kaizala le informazioni richieste.

#### <a name="export"></a>Esportazione

Quando gli utenti nell'organizzazione usano Kaizala, vengono generati i dati di consumo e, se l'utente fa parte di un gruppo dell'organizzazione, potrebbero essere generati i dati dell'organizzazione. Gli amministratori possono esportare i dati dell'organizzazione di un utente dal portale di gestione di Kaizala. Gli utenti di Kaizala possono esportare i propri dati privati dall'app per dispositivi mobili Kaizala. In entrambi i casi, tenere presente che i dati sull'utilizzo di prodotti e servizi vengono esportati anche quando un amministratore o un utente esporta i dati di Kaizala. Per informazioni dettagliate, vedere:

- [Esportare o eliminare i dati dell'organizzazione di un utente in Kaizala](https://support.office.com/article/export-or-delete-a-user-s-organizational-data-in-kaizala-150ec214-a070-4e8a-8509-82f46d84bbb6)
- [Esportare o eliminare i propri dati nell'app per dispositivi mobili Kaizala](https://support.office.com/article/export-or-delete-your-data-in-the-kaizala-mobile-app-65f83dbc-4f10-4644-9b2d-9945c967684e)

#### <a name="delete"></a>Eliminazione

Un amministratore di Kaizala può rimuovere un account utente di Kaizala nel portale di gestione di Kaizala. Dopo l'eliminazione di un account utente, l'utente viene rimosso da tutti i gruppi che appartengono all'organizzazione e i dati dell'organizzazione vengono eliminati dal dispositivo dell'utente. 

Per rimuovere tutti i dati personali dal dispositivo mobile dell'utente, l'utente Kaizala può eliminare il proprio account Kaizala. Dopo l'eliminazione dell'account, tutti i relativi contenuti di Kaizala (tra cui chat, foto e altri dati) vengono eliminati dal dispositivo.

Per dettagli, vedere:

- [Esportare o eliminare i dati dell'organizzazione di un utente in Kaizala](https://support.office.com/article/export-or-delete-a-user-s-organizational-data-in-kaizala-150ec214-a070-4e8a-8509-82f46d84bbb6)
- [Esportare o eliminare i propri dati nell'app per dispositivi mobili Kaizala](https://support.office.com/article/export-or-delete-your-data-in-the-kaizala-mobile-app-65f83dbc-4f10-4644-9b2d-9945c967684e)

### <a name="planner"></a>Planner

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Planner per trovare, accedere, esportare ed eliminare i dati personali.

#### <a name="discover"></a>Individuazione

I piani di Planner sono associati a un gruppo di Office 365 e i file per i Gruppi di Office 365 sono archiviati in un sito di SharePoint Online associato per il gruppo. Ciò significa che è possibile usare Ricerca contenuto per trovare i file di Planner eseguendo una ricerca nel sito del gruppo di Office 365. A tale scopo, è necessario avere l'URL del gruppo di Office 365. Vedere [Ricerca di gruppi di Microsoft Teams e Office 365](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) nella sezione di aiuto relativa a “Ricerca di contenuto in Office 356” per ottenere informazioni sui Gruppi di Office 365 che consentono di cercare i file di Planner nella pagina di SharePoint corrispondente.

#### <a name="access"></a>Access

Come spiegato in precedenza, è possibile cercare il sito di SharePoint Online e la cassetta postale associati a un piano. È quindi possibile visualizzare in anteprima o scaricare i risultati della ricerca correlati per accedere ai dati.

#### <a name="delete"></a>Eliminazione

È possibile eliminare manualmente le informazioni personali di un utente attribuendosi le autorizzazioni per accedere ai piani a cui appartiene l'utente oppure accedendo con le credenziali dell'utente per apportare le modifiche. Vedere [Delete user data in Microsoft Planner](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f) (Eliminare i dati dell'utente in Microsoft Planner).

#### <a name="export"></a>Esportazione

È possibile usare uno script di PowerShell per esportare i dati di un utente da Planner. Quando si esportano i dati, viene esportato un file JSON separato per ogni piano a cui appartiene l'utente. Vedere [Export user data from Microsoft Planner](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08) (Esportare i dati dell'utente da Microsoft Planner).

### <a name="power-bi"></a>Power BI

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Power BI per trovare, accedere, esportare ed eliminare i dati personali.

#### <a name="discover"></a>Individuazione
È possibile cercare contenuti in diverse aree di lavoro in Power BI, inclusi dashboard, report, cartelle di lavoro e set di dati. Ogni tipo di area di lavoro contiene un campo di ricerca che è possibile utilizzare per cercare tale area di lavoro. Vedere [Ricerca, individuazione e ordinamento di contenuti nel servizio Power BI](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort).

#### <a name="access"></a>Access

È possibile stampare dashboard, report e oggetti visivi nei report di Power BI per creare una copia fisica. Non è possibile stampare interi report. È possibile stampare solo una pagina alla volta. Per eseguire questa operazione, passare a un report, usare il campo di ricerca per trovare dati specifici e quindi stamparlo. Vedere [la pagina di stampa del servizio Power BI.](https://docs.microsoft.com/power-bi/service-print)

#### <a name="delete"></a>Eliminazione

Per eliminare dashboard, report e cartelle di lavoro, vedere [Eliminare qualsiasi elemento nel servizio Power BI](https://docs.microsoft.com/power-bi/service-delete).

L'eliminazione di un dashboard, un report o una cartella di lavoro non elimina il set di dati sottostanti. Poiché Power BI si basa su una connessione dinamica ai dati di origine sottostanti per completezza e precisione, l'eliminazione dei dati personali deve essere eseguita nell'origine. Se ad esempio è stato creato un report di Power BI connesso a Dynamics 365 for Sales come origine dati dinamica, eventuali correzioni devono essere apportate ai dati in Dynamics 365 for Sales.

Dopo che i dati sono stati eliminati, è possibile usare le funzionalità di [aggiornamento dati pianificato](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) di Power BI per aggiornare il set di dati memorizzato in Power BI. Dopo l'aggiornamento, i dati eliminati non saranno più disponibili in alcun report o dashboard che hanno usato tali dati. Per garantire la conformità ai requisiti di PILR, è consigliabile disporre di criteri per assicurarsi che i dati vengano aggiornati con una cadenza appropriata.

#### <a name="export"></a>Esportazione

Per facilitare una richiesta di portabilità dei dati, è possibile esportare i dashboard e i report di Power BI:

- È possibile esportare i dati sottostanti per i report e dashboard in un file di Excel statico. Vedere il video in [Stampa dal servizio Power BI](https://docs.microsoft.com/power-bi/service-print). Con Excel è possibile modificare i dati personali da includere nella richiesta di portabilità e quindi salvarli in un formato di uso comune e leggibile al computer, ad esempio in un file con estensione csv o xml.
- È possibile esportare (scaricare) un report dal servizio Power BI in Office 365 in un file con estensione pbix se originariamente il report è stato pubblicato usando Power BI Desktop. È quindi possibile importare il file in Power BI Desktop e pubblicarlo (esportarlo) nel servizio Power BI di un'altra organizzazione. Vedere [Esportare un report dal servizio Power BI in Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix).

### <a name="powerapps"></a>PowerApps

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Power Apps per trovare, accedere, esportare ed eliminare i dati personali. Questi passaggi delineano il modo in cui un amministratore può trasferire le app e le risorse dipendenti ai nuovi proprietari per limitare le interruzioni aziendali.

#### <a name="discover"></a>Individuazione

PowerApps è un servizio per la creazione di app che può essere condiviso e usato all'interno dell'organizzazione. Nell'ambito del processo di creazione o di esecuzione di un'app, un utente finisce per archiviare diversi tipi di dati e risorse nel servizio PowerApps, tra cui app, ambienti, connessioni, connettori personalizzati e autorizzazioni.

Per semplificare una richiesta DSR correlata a PowerApps, è possibile usare le operazioni di amministrazione esposte nell'[Interfaccia di amministrazione di PowerApps](https://admin.powerapps.com/) e i [cmdlet di PowerShell per amministratori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).  Per accedere a questi strumenti, è necessario disporre di un account con le autorizzazioni seguenti:

- Una licenza di Piano 2 di PowerApps a pagamento o una licenza di valutazione di Piano 2 d PowerApps. È possibile iscriversi [qui](http://web.powerapps.com/trial)per ottenere una licenza di valutazione di 30 giorni.
- [Amministratore globale di Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) o
- [Amministratore globale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

Per altre informazioni su come trovare i dati personali, vedere [Discover PowerApps personal data](https://go.microsoft.com/fwlink/?linkid=871880) (Individuare i dati personali in PowerApps).

Il servizio PowerApps include anche il servizio dati comune per le app, che consente agli utenti di archiviare i dati in entità standard e personalizzate in un database del servizio dati comune. È possibile visualizzare i dati archiviati in queste entità [dal portale di PowerApps Maker](https://web.powerapps.com) e usare le funzionalità di ricerca avanzate di [Ricerca avanzata](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) per cercare dati specifici nell'entità. Per altre informazioni su come individuare i dati personali nel servizio dati comune, vedere [Individuare i dati personali dei servizi dati comuni](https://go.microsoft.com/fwlink/?linkid=871881).

#### <a name="access"></a>Access

Gli amministratori possono attribuirsi privilegi per accedere ed eseguire le app e le risorse associate (inclusi i flussi, le connessioni e i connettori personalizzati) usando l'[Interfaccia di amministrazione di PowerApps](https://admin.powerapps.com/) o i [cmdlet di PowerShell per amministratori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

Dopo aver ottenuto l'accesso all'app dell'utente, è possibile usare un Web browser per aprire l'app. Dopo avere aperto l'app, è possibile acquisire uno screenshot dei dati. Vedere [Use PowerApps in a web browser](https://docs.microsoft.com/powerapps/run-app-browser) (Usare PowerApps in un Web browser).

#### <a name="delete"></a>Eliminazione

Poiché PowerApps consente agli utenti di creare un'applicazione line-of-business che può essere una parte fondamentale delle operazioni giornaliere dell'organizzazione, quando un utente lascia l'organizzazione e il suo account di Office 365 viene eliminato, l'amministratore deve stabilire se eliminare le app di proprietà dell'utente o riassegnarle ai nuovi proprietari. L'attribuzione delle app a un amministratore aiuta l'organizzazione a trasferire i flussi a nuovi proprietari e a evitare interruzioni nell'attività aziendale per app che potrebbero essere usate per processi aziendali condivisi.

Per i dati condivisi, ad esempio le app, gli amministratori devono decidere se eliminare definitivamente i dati condivisi dell'utente o conservarli acquisendone la proprietà o assegnandoli ad altri utenti nell'organizzazione. Vedere [Delete PowerApps personal data](https://go.microsoft.com/fwlink/?linkid=871883) (Eliminare i dati personali in PowerApps).

Tutti i dati archiviati da un utente in un'entità in un database Common Data Service per le app devono essere esaminati e (se lo si desidera) essere eliminati da un amministratore usando le funzionalità nel prodotto. Vedere [Delete Common Data Service user personal data](https://go.microsoft.com/fwlink/?linkid=871886) (Eliminare i dati personali di un utente di Common Data Service).

#### <a name="export"></a>Esportazione

Gli amministratori possono esportare i dati personali archiviati per un utente all'interno del servizio PowerApps usando l'[Interfaccia di amministrazione di PowerApps](https://admin.powerapps.com/) e i [cmdlet di PowerShell per amministratori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871804). Vedere [Export PowerApps personal data](https://go.microsoft.com/fwlink/?linkid=871883) (Esportare i dati personali di PowerApps).

È possibile usare anche le funzionalità di [ricerca avanzata](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) nel prodotto per cercare i dati personali di un utente in una qualsiasi entità. Per informazioni dettagliate sull'esportazione dei dati personali in Common Data Service, vedere [Export Common Data Service personal data](https://go.microsoft.com/fwlink/?linkid=871889) (Esportare i dati personali di Common Data Service).

#### <a name="connections-and-custom-connectors-in-powerapps"></a>Connessioni e connettori personalizzati in PowerApps

Connessioni richiede agli utenti di fornire le credenziali per connettersi a API, applicazioni SaaS e sistemi sviluppati personalizzati. Queste connessioni appartengono all'utente che ha stabilito la connessione e possono essere [gestite](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) nel prodotto. Dopo che le PowerApps sono state riassegnate, un amministratore può usare i cmdlet di PowerShell per elencare ed eliminare queste connessioni come parte dell'eliminazione dei dati dell'utente.

I connettori personalizzati consentono alle organizzazioni di estendere le funzionalità di PowerApps connettendosi ai sistemi in cui non è disponibile un connettore. L'autore di un connettore personalizzato può [condividere ](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps) il connettore con altri utenti dell'organizzazione. Dopo la ricezione di una richiesta di eliminazione DSR, un amministratore deve considerare la possibilità di riassegnare la proprietà di questi connettori per evitare interruzioni aziendali. Per accelerare questo processo, un amministratore può usare i cmdlet di PowerShell per elencare, riassegnare o eliminare i connettori personalizzati.

### <a name="project-online"></a>Project Online

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Project Online per trovare i dati personali, accedervi, esportali ed eliminarli.

#### <a name="discover-and-access"></a>Individuazione e accesso

È possibile usare ricerca contenuto per cercare nel sito di SharePoint Online associato a un progetto (al momento della creazione di un progetto, è disponibile un'opzione per creare un sito di SharePoint Online associato); Ricerca contenuto non esegue la ricerca nei dati di un progetto effettivo in Project Online, ma solo nel sito associato. Anche se Ricerca contenuto cerca i metadati relativi ai progetti, come le persone menzionate nell'oggetto, questo può essere utile per trovare e accedere al progetto che contiene i dati relativi al DSR.

> [!TIP]
> L'URL della raccolta siti nella propria organizzazione in cui i siti sono associati ai progetti è **https://\<organizzazione\>.sharepoint.com/sites/pwa**; ad esempio **https://contoso.sharepoint.com/pwa**. È possibile usare questa raccolta siti specifica come percorso di Ricerca contenuto e cercare il nome del progetto nella query di ricerca. Un amministratore IT può anche usare la pagina Raccolte siti nell'interfaccia di amministrazione di SharePoint per ottenere un elenco di raccolte siti PWA nell'organizzazione.

#### <a name="delete"></a>Eliminazione

È possibile eliminare le informazioni relative a un utente dall'ambiente Project Online. Vedere [Delete user data from Project Online](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7) (Eliminazione di dati utente da Project Online).

#### <a name="export"></a>Esportazione

È possibile esportare il contenuto di un utente specifico dall'ambiente di Project Online. Tali dati vengono esportati in più file in formato JSON. Per istruzioni dettagliate, vedere [Export user data from Project Online](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d) (Esportare i dati utente da Project Online). Per informazioni dettagliate sui file esportati, vedere [Project Online export json object definitions](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7) (Definizioni di oggetti json di esportazione da Project Online).

### <a name="publisher"></a>Publisher

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Publisher per trovare, accedere, esportare ed eliminare i dati personali.

#### <a name="discover"></a>Individuazione

È possibile utilizzare la funzionalità di ricerca in-app per trovare del testo in un file di Publisher nello stesso modo in cui è possibile farlo nella maggior parte delle applicazioni di Office. Vedere [Cercare e sostituire testo](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268).

#### <a name="access"></a>Accesso

Una volta trovati i dati, è possibile acquisirne uno screenshot o copiarli e incollarli in un file Word o di testo e fornire tale file all'interessato. È inoltre possibile salvare una pubblicazione come file Word, PDF o XPS. Vedere:

  - [Salvare una pubblicazione come documento di Word](https://support.office.com/article/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [Salvare con nome o convertire una pubblicazione in PDF o XPS con Publisher](https://support.office.com/article/657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>Esportazione

È possibile fornire all'interessato il file di Publisher oppure, come spiegato in precedenza, è possibile salvare una pubblicazione come file Word, PDF o XPS. Vedere:

  - [Salvare una pubblicazione come documento di Word](https://support.office.com/article/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [Salvare con nome o convertire una pubblicazione in PDF o XPS con Publisher](https://support.office.com/article/657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>Eliminazione

È possibile eliminare il contenuto da una pubblicazione, eliminare intere pagine o eliminare un intero file Publisher. Vedere [Aggiungere o eliminare pagine](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08).

### <a name="staffhub"></a>StaffHub

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft StaffHub per trovare i dati personali, accedervi, esportali ed eliminarli.

#### <a name="discover"></a>Individuazione

La maggior parte dei dati in StaffHub è disponibile per tutti i membri e i responsabili del team di StaffHub. Per visualizzare i dati in StaffHub, chiedere a un responsabile oppure a un membro del team di accedere all'indirizzo <https://staffhub.office.com> per cercare dati potenzialmente rilevanti per la richiesta DSR o di essere aggiunti come membri del team in modo che sia possibile esaminare direttamente le informazioni di StaffHub per cercare dati potenzialmente sensibili.

#### <a name="access"></a>Access

Dopo che il contenuto pertinente di StaffHub è stato trovato, è possibile visualizzare e acquisire le schermate di dati rilevanti da inviare all'interessato dall'applicazione oppure scaricare il contenuto stesso.

- **Pianificazione delle informazioni:** nella scheda **Schedule** (Pianificazione) in StaffHub sono disponibili le opzioni **People View** (Visualizzazione persone) e **Shifts View** (Visualizzazione turni) che consentono di visualizzare le pianificazioni giornaliere, settimanali e mensili in base ai membri del team oppure ai turni di lavoro. Tali visualizzazioni possono essere stampate o scaricate in Excel selezionando i tre punti (puntini di sospensione) nell'angolo superiore sinistro dell'app Web StaffHub e facendo clic su **Export Schedule** (Esporta pianificazione).
- **File condivisi:** tutti i file di StaffHub sono archiviati in SharePoint Online ed è quindi possibile individuarli, eseguirvi l'accesso ed esportarli tramite Ricerca contenuto, come descritto in precedenza. I file possono essere visualizzati anche in StaffHub nella scheda **Files** (File).
- **Messaggistica:** per accedere ai messaggi, è attualmente possibile attenersi alla procedura di accesso ai dati specifici dell'utente descritta di seguito. In futuro, tutti i messaggi di StaffHub verranno archiviati in Microsoft Teams e pertanto è possibile usare lo strumento Ricerca contenuto per accedervi.
- **Dati specifici dell'utente:** i dati specifici dell'utente sono costituiti da impostazioni utente, feed attività utente e cronologia delle richieste dei turni utente e nessuno di tali elementi può essere visualizzato dai membri del team o dagli amministratori. Per accedere ai dati specifici dell'utente o per esportarli, è necessario che l'interessato esegua l'accesso al proprio account StaffHub per ottenerli. In alternativa, se l'interessato ha lasciato l'organizzazione, è possibile ottenere tali dati chiedendo all'amministratore di reimpostare la password dell'utente per conto dell'interessato in modo che gli amministratori possano accedere all'account specifico.
- **Kronos:** StaffHub supporta le connessioni a [Kronos](http://www.kronos.com/), uno strumento di gestione del personale di terze parti. StaffHub e Kronos elaborano i dati dell'organizzazione in modo indipendente e in base a condizioni individuali firmate con ogni parte. Se la richiesta DSR si riferisce a dati conservati da Kronos, è necessario contattare Kronos per ottenere assistenza per DSR e viceversa.

#### <a name="delete"></a>Eliminazione

- La maggior parte del contenuto dati in-app gestito in StaffHub può essere eliminato da un responsabile del team direttamente dall'app. Come accennato in precedenza nella sezione Individuazione per StaffHub, è possibile essere aggiunti a un team come responsabili ed eliminare i dati.
- Quando si elimina un account utente in modo permanente, entro 30 giorni StaffHub elimina il numero di telefono, l'indirizzo di posta elettronica e l'immagine del profilo dell'utente.

#### <a name="export"></a>Esportazione

Vedere la sezione [Accesso](#access-12) per StaffHub.

### <a name="stream"></a>Stream

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Stream per trovare i dati personali, accedervi, esportali ed eliminarli.

#### <a name="discover"></a>Individuazione

Per individuare il contenuto generato o caricato in Stream che potrebbe essere pertinente a una richiesta di oggetto dati, un amministratore del flusso può eseguire un report utente per determinare quali video, descrizioni video, gruppi, canali o commenti un utente di Stream potrebbe aver caricato, creato o pubblicato. Per istruzioni su come generare un report, vedere [Gestire i dati degli utenti in Microsoft Stream.](https://docs.microsoft.com/stream/managing-user-data) L'output del report è in formato HTML e contiene collegamenti ipertestuali che possono essere usati per passare ai video di interesse potenziale. Se si vuole visualizzare un video con un set di autorizzazioni personalizzato e non si fa parte degli utenti originali per cui è stato progettato il video, è possibile visualizzarlo in modalità amministratore. Vedere [Funzionalità di amministrazione in Microsoft Stream.](https://docs.microsoft.com/stream/manage-content-permissions)  

#### <a name="access"></a>Access

A seconda della natura delle richieste DSR, è possibile utilizzare una copia del report descritto in precedenza per soddisfare una richiesta DSR. Il report degli utenti include il nome utente e l'ID univoco di Stream, un elenco di video caricati dall'utente, un elenco di video visualizzati dagli utenti, a un elenco di canali creati dall'utente, un elenco di tutti i gruppi di cui è membro l'utente e un elenco di tutti i commenti che l'utente ha lasciato sui video. Il report, inoltre, mostra se l'utente ha visualizzato ogni video elencato nel report. Se si desidera consentire all'interessato di accedere a un video per soddisfare una richiesta DSR, è possibile condividere il video.

#### <a name="export"></a>Esportazione

Vedere la sezione Accesso per Stream. 

#### <a name="delete"></a>Eliminazione

Per eliminare o modificare video o altri contenuti di Stream, un amministratore di Stream può attivare la visualizzazione in modalità amministratore per eseguire la funzione necessaria. Vedere [Funzionalità di amministratore in Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions). Se un utente ha lasciato l'organizzazione e desidera far rimuovere il proprio nome visualizzato accanto ai video che ha caricato, è possibile rimuovere il suo nome o sostituirlo con un altro. Vedere [Gestione di utenti eliminati in Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users).

### <a name="sway"></a>Sway

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Sway per trovare i dati personali, accedervi, esportali ed eliminarli.

#### <a name="discover"></a>Individuazione

Il contenuto creato con Sway (che si trova in [www.sway.com](http://www.sway.com)) può essere visto solo dal proprietario e da quelli a cui l'autore ha consentito di visualizzare lo Sway. Vedere [Impostazioni privacy in Sway](https://support.office.com/article/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217). Per determinare se Sway è una posizione in cui è probabile che i dati personali siano in grado di rispondere al DSR, è possibile chiedere agli utenti dell'organizzazione e dell'organizzazione che potrebbero avere generato contenuto sui dati soggetti alla ricerca dei propri Sway e condividere con gli altri Sway che possono contenere dati personali che rispondono alla richiesta di un oggetto dati. Per informazioni su come condividere uno Sway, vedere "Condividere uno Sway dall'account aziendale" nell'articolo [Condividere il proprio Sway.](https://support.office.com/article/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998)

#### <a name="access"></a>Access

Se i dati personali sono stati trovati in uno Sway che si vuole condividere con l'oggetto dati, è possibile fornire all'oggetto dati l'accesso ai dati con uno dei vari modi. È possibile fornire all'oggetto dati una copia della versione online di Sway, come descritto sopra. È possibile acquisire screenshot della parte appropriata dello Sway che si vuole condividere. In alternativa, è possibile stampare o scaricare lo Sway in Word o convertirlo in un PDF. Come scaricare uno Sway è descritto più avanti nella sezione "esportazione" riportata sotto.

#### <a name="delete"></a>Eliminazione

Per informazioni su come eliminare uno sway, vedere la sezione relativa in [Privacy settings in Sway](https://support.office.com/article/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217) (Impostazioni della privacy in Sway).

#### <a name="export"></a>Esportazione

Per esportare uno sway, aprire lo sway da scaricare, selezionare la serie di punti (puntini di sospensione) nell'angolo superiore destro, selezionare **Export** (Esporta) e quindi scegliere **Word** o **PDF**.

### <a name="whiteboard"></a>Whiteboard

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Whiteboard per trovare i dati personali, accedervi, esportarli ed eliminarli.

- [Whiteboard 2016 in Surface Hub](#whiteboard-2016-on-surface-hub)
- [Whiteboard in tutte le altre piattaforme](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Whiteboard 2016 in Surface Hub

In questa sezione viene descritto come rispondere alle richieste DSR per i dati creati con l'app Whiteboard 2016 incorporata in Surface Hub.

##### <a name="discover"></a>Individuazione

I file di Whiteboard (.wbx) vengono archiviati nell'account OneDrive for Business degli utenti. È possibile chiedere all'interessato o ad altri utenti se le lavagne che hanno creato possano contenere dati personali rilevanti per una richiesta DSR. Possono condividere una lavagna oppure è possibile ottenerne una copia da fornire all'interessato.

Per accedere e trasferire lavagne: 

1. Accedere all'account OneDrive for Business dell'utente. Vedere la sezione "Accedere ai documenti di OneDrive for Business dell'ex dipendente" in [Accedere ai dati di un ex utente ed eseguirne il backup](https://support.office.com/article/get-access-to-and-back-up-a-former-user-s-data-a6f7f9ad-e3f5-43de-ade5-e5a0d7531604).
2. Accedere alla cartella Dati dell'app Whiteboard nell'account OneDrive for Business dell'utente e copiare i file .wbx delle lavagne che si desidera trasferire.
3. Accedere all'account OneDrive for Business dell'interessato e quindi alla cartella Dati dell'app Whiteboard.
4. Incollare i file .wbx copiati nel passaggio precedente.

##### <a name="access"></a>Accesso

Se si trovano dati personali in una lavagna rilevanti per una richiesta di accesso DSR, è possibile consentire all'interessato di accedere a una lavagna in diversi modi:

- Acquisire screenshot delle parti importanti di una lavagna.
- Caricare una copia del file .wbx nell'account OneDrive for Business dell'interessato. Vedere la sezione precedente per la procedura di accesso e trasferimento di file .wbx.
- Esportare una copia di una lavagna come file .png.

##### <a name="export"></a>Esportazione

Se si è ottenuta una copia di una lavagna, è possibile esportarla. 

1. Avviare Whiteboard in Surface Hub.
2. Toccare il pulsante Condividi e quindi selezionare Esporta una copia. È possibile esportare una lavagna in un file di OneNote (.one) o in un file di immagine (.png).

##### <a name="delete"></a>Eliminazione

Accedere all'account OneDrive for Business dell'utente e quindi eliminare le lavagne.

1. Accedere all'account OneDrive for Business dell'interessato. Vedere la sezione "Accedere ai documenti di OneDrive for Business dell'ex dipendente" in [Accedere ai dati di un ex utente ed eseguirne il backup](https://support.office.com/article/get-access-to-and-back-up-a-former-user-s-data-a6f7f9ad-e3f5-43de-ade5-e5a0d7531604).
2. Accedere alla cartella Dati dell'app Whiteboard e quindi eliminarne i contenuti.

#### <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>Whiteboard per PC, Surface Hub e altre piattaforme

Se un amministratore riceve una richiesta DSR per i dati nella nuova app Whiteboard, può utilizzare Whiteboard PowerShell per aggiungere se stesso (o altri utenti) come proprietario delle lavagne di un utente. Ciò consente a un amministratore di eseguire determinate azioni, tra cui accedere, esportare ed eliminare lavagne. Usare il cmdlet **Set-WhiteboardOwner** per aggiungere se stessi o un altro utente come proprietario di una lavagna oppure usare il cmdlet **Invoke-TransferAllWhiteboards** per trasferire la proprietà di tutte le lavagne per uno specifico utente a un nuovo proprietario. Per informazioni sull'utilizzo di questi cmdlet e sull'installazione del modulo Whiteboard PowerShell, vedere i materiali di riferimento sui cmdlet di Microsoft Whiteboard. Una volta ottenuta la proprietà di una lavagna, vedere [Materiali di riferimento per i cmdlet di Microsoft Whiteboard](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps).

Una volta ottenuta la proprietà di una lavagna, vedere l’[articolo di supporto di Whiteboard](https://go.microsoft.com/fwlink/?linkid=872780) per istruzioni dettagliate sull'accesso, l'esportazione e l'eliminazione di lavagne.

### <a name="yammer"></a>Yammer

Le sezioni seguenti illustrano come usare la funzionalità in-app di Microsoft Yammer per trovare i dati personali, accedervi, esportali ed eliminarli.

#### <a name="discover"></a>Individuazione

Dall'interfaccia di amministrazione di Yammer, un amministratore verificato di Yammer, ossia un amministratore globale o un amministratore verificato di Office 365, impostato in Yammer, può esportare i dati relativi a un determinato utente. L'esportazione include i messaggi e i file pubblicati e modificati dall'utente e le informazioni sugli argomenti e i gruppi creati dall'utente. Dopo l'esecuzione di un'esportazione di dati specifica di un utente, l'amministratore riceverà anche un messaggio di posta in arrivo con i dati relativi alle attività degli account utente che potranno fornire all'utente se lo desidera. Per istruzioni dettagliate, vedere [Yammer Enterprise: privacy](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf).

Le esportazioni specifiche dell'utente sono relative a una singola rete e di conseguenza, se l'utente appartiene a una rete esterna a Yammer, l'amministratore deve esportare i dati anche per la rete esterna, oltre che per quella interna.

Per accedere ai dati non inclusi nell'esportazione, in relazione all'utente è possibile acquisire schermate per il profilo, le impostazioni, le appartenenze a gruppi, i messaggi con segnalibro, gli utenti e gli argomenti seguiti. Gli utenti o gli amministratori possono raccogliere queste informazioni.  Gli utenti o gli amministratori possono raccogliere queste informazioni. Per altre informazioni, vedere [Yammer Enterprise: Privacy](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf).

#### <a name="access"></a>Access

È possibile visualizzare i dati nei file esportati, ad esempio il testo completo dei messaggi e il contenuto dei file stessi. È anche possibile selezionare i collegamenti nei file esportati per accedere direttamente ai messaggi e ai file pubblicati in Yammer, nonché ai gruppi e agli argomenti creati dall'utente, ai messaggi per cui l'utente ha inserito un "like", ai messaggi in cui l'utente è stato menzionato con il simbolo @, ai sondaggi cui l'utente ha partecipato e ai collegamenti che l'utente ha aggiunto.

L'esportazione dei dati per utente non include gli elementi seguenti.

- Profilo utente
    - Se l'utente ha un'identità in Yammer, dispone del controllo completo del profilo. Per informazioni su come visualizzare e modificare il profilo, vedere [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851) (Modificare il profilo e le impostazioni personali in Yammer).
    
    - Se l'utente ha un'identità in Office 365, il profilo utente di Yammer viene recuperato automaticamente da Office 365, che ottiene le informazioni sul profilo da Azure Active Directory (AAD). Gli utenti di Yammer possono modificare temporaneamente i propri profili in Yammer, ma tali modifiche vengono sovrascritte quando viene apportata una modifica in AAD e di conseguenza è necessario visualizzare e modificare i dati di directory in AAD. Per altre informazioni, vedere [Manage Yammer users across their lifecycle from Office 365](https://support.office.com/article/Manage-Yammer-users-across-their-life-cycle-from-Office-365-6c4c8fff-6444-404a-bffc-f9da0bcc3039) (Gestire gli utenti di Yammer nel relativo ciclo vita da Office 365) e [Aggiungere o modificare informazioni sul profilo per un utente in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   Impostazioni utente

- L'utente può visualizzare e modificare le proprie impostazioni. Per informazioni su come visualizzare e modificare le impostazioni utente, vedere [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851) (Modificare il profilo e le impostazioni personali in Yammer). Un amministratore può visualizzare queste informazioni e acquisire le schermate, ma non modificarle. Passare alle impostazioni di Yammer \> **People** (Persone) e quindi fare clic sul nome dell'utente.<br/>
    - Appartenenza ai gruppi dell'utente, messaggi con segnalibri, utenti e argomenti seguiti.
    
    - L'utente può visualizzare queste informazioni. Per altre informazioni, vedere [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380) (Suggerimenti per rimanere organizzati in Yammer). Un amministratore può visualizzare queste informazioni e acquisire schermate, ma non modificarle. Passare alle impostazioni di Yammer \> **People** (Persone) e quindi fare clic sul nome dell'utente.

#### <a name="export"></a>Esportazione

Per istruzioni su come esportare i dati, vedere [Manage GDPR data subject requests in Yammer Enterprise](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf) (Gestire le richieste degli interessati per Yammer Enterprise nell'ambito del GDPR). È necessario eseguire un'esportazione per ogni rete Yammer di cui l'utente è membro.

Yammer include impostazioni di conservazione dei dati che possono essere eliminate temporaneamente o eliminano i dati quando un utente elimina un messaggio o un file. Se è impostato su cancellazione temporanea, i dati che un utente ha eliminato verranno inclusi nell'esportazione. Se l'impostazione di conservazione dei dati di Yammer è impostata su eliminazione definitiva, le informazioni eliminate non vengono più archiviate in Yammer, quindi non verranno incluse nell'esportazione.

#### <a name="delete"></a>Eliminazione

Yammer consente agli amministratori verificati di eseguire un'eliminazione conforme al GDPR tramite l'interfaccia di amministrazione di Yammer se ricevono un richiesta DSR. Questa opzione, definita Erase User (Cancella utente), sospende l'utente per 14 giorni e ne rimuove tutti i dati personali, ad eccezione di file e messaggi. Se l'utente è un utente guest, questa operazione deve essere eseguita per ogni rete esterna di cui l'utente guest è membro.

> [!NOTE]
> Se un amministratore deve rimuovere i file e messaggi di un utente durante l'intervallo di 14 giorni, deve eseguire un'esportazione a livello utente per identificare i file e i messaggi e quindi decidere quali eliminare tramite un'eliminazione nel prodotto o tramite uno script di PowerShell. Dopo il periodo di 14 giorni, gli amministratori non possono più associare l'utente né ai file né ai messaggi.

Quando un utente viene eliminato con l'opzione Elimina, viene inviata una notifica alla posta in arrivo di Yammer di tutti gli amministratori di rete e gli amministratori verificati. L'opzione Elimina utente elimina il profilo Yammer dell'utente senza eliminare il profilo di Office 365 o Azure Active Directory.

Per istruzioni dettagliate sulla procedura di rimozione di un utente, vedere [Manage GDPR data subject requests in Yammer Enterprise](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf) (Gestire le richieste degli interessati per Yammer Enterprise nell'ambito del GDPR).

## <a name="responding-to-dsr-rectification-requests"></a>Risposta alle richieste di rettifica DSR

Se un oggetto dati ha richiesto di rettificare i dati personali che risiedono nei dati di dell'organizzazione archiviati in Office 365, l'utente e l'organizzazione devono decidere se è opportuno rispettare la richiesta. Se si sceglie di rispettare la richiesta, la modifica dei dati può comportare l'esecuzione di azioni come la modifica, la redazione o la rimozione di dati personali da un documento o da un altro tipo o elemento. Il modo più semplice per eseguire questa operazione consiste nel chiedere al proprietario dei dati/documento di usare l'applicazione di Office 365 appropriata per apportare le modifiche necessarie. In alternativa, è possibile fare in modo che un amministratore IT dell'organizzazione apporti le modifiche. È probabile che sia necessario che l'amministratore IT (o altre persone dell'organizzazione con i privilegi appropriati, come un amministratore della raccolta di siti di SharePoint Online), possa assegnare a sé stesso o a qualcun altro che lavora al DSR le autorizzazioni necessarie per ottenere accesso al documento o al percorso di contenuto in cui si trova il documento per apportare la modifica direttamente al documento.

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>Richiesta che il proprietario dei dati apporti la modifica approvata

Il modo più diretto per correggere i dati personali consiste nel chiedere al proprietario dei dati di apportare la modifica. Dopo aver individuato i dati oggetto della richiesta DSR, è possibile specificare le informazioni seguenti in modo che sia possibile apportare la modifica.

- Il percorso e il nome del file, per documenti e altri file, dell'elemento che deve essere modificato. L'individuazione dei dati in questione fa parte del [processo di individuazione](#using-content-search-to-find-personal-data) descritto in precedenza.
- Modifica approvata che deve essere eseguita dal proprietario dei dati

È consigliabile implementare un processo di conferma in cui le persone coinvolte nell'indagine DSR verifichino che la modifica richiesta sia stata eseguita.

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>Ottenere l'accesso a un sito di SharePoint Online oppure a un account di OneDrive for Business per apportare modifiche

Se per il proprietario dei dati non è possibile implementare la richiesta di rettifica dell'interessato, un amministratore IT o l'amministratore di SharePoint dell'organizzazione può accedere al percorso del contenuto e apportare le modifiche necessarie. In alternativa, un amministratore può assegnare a un altro responsabile di privacy dei dati le autorizzazioni necessarie.

#### <a name="sharepoint-online"></a>SharePoint Online

Per assegnare le autorizzazioni di proprietario o di amministratore a un sito di SharePoint Online in modo che sia possibile accedere e modificare il documento, vedere

- [Manage administrators for a site collection](https://support.office.com/article/Manage-administrators-for-a-site-collection-9A7E46F9-3FC4-4297-955A-82CB292A5BE0) (Gestire gli amministratori per una raccolta siti)

- [Edit and manage permissions for a SharePoint list or library](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782) (Modificare e gestire autorizzazioni per un elenco o una raccolta di SharePoint)

#### <a name="onedrive-for-business"></a>OneDrive for Business

Un amministratore globale di Office 365 può accedere a un account OneDrive for Business dell'utente usando il .

1. Accedere a Office 365 con le credenziali di amministratore globale.
2. Passare all’interfaccia di amministrazione.
3. Passare a **Utenti attivi** e selezionare l'utente.
4. Espandere **OneDrive for Business Settings** (Impostazioni di OneDrive for Business) nel riquadro dei dettagli e quindi fare clic su **Accedi ai file**.
5. Fare clic sull'URL per accedere all'account OneDrive for Business dell'utente.

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>Ottenere l'accesso a una cassetta postale di Exchange Online per apportare modifiche ai dati

Un amministratore globale di Office 365 può assegnare a se stesso le autorizzazioni necessarie per aprire e modificare (o eliminare) gli elementi nella cassetta postale di un altro utente, come se ne fosse proprietario. Un amministratore globale può anche assegnare le autorizzazioni a un altro utente. In particolare, l'amministratore globale deve aggiungere l'autorizzazione di **lettura e gestione**, che corrisponde all'accesso completo in Exchange Online. Per informazioni dettagliate, vedere:

- [Assegnare le autorizzazioni per la cassetta postale a un altro utente in Office 365](https://support.office.com/article/Give-mailbox-permissions-to-another-user-in-Office-365-Admin-Help-1DBCF12F-A9DE-4D1D-B0B3-A227F8A736D8)
- [Accedere alla cassetta postale di un'altra persona](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

Se la cassetta postale dell'utente è stata bloccata a fini giudiziari o è stata assegnata a un criterio di conservazione, tutte le versioni di una cassetta postale verranno conservate finché non scadrà il periodo di conservazione o la cassetta postale verrà rimossa. Ciò significa che se un elemento della cassetta postale viene modificato in risposta a una richiesta di rettifica DSR, viene mantenuta e archiviata una copia dell'elemento originale (prima della modifica) in una cartella nascosta della cartella elementi ripristinabili nella cassetta postale dell'utente.

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>Apportare modifiche al contenuto in OneDrive for Business e SharePoint Online

I proprietari dei dati o gli amministratori IT possono modificare pagine, elenchi e documenti di SharePoint Online. Quando si apportano modifiche al contenuto di SharePoint, tenere presenti gli aspetti seguenti:

- L'aggiornamento di un documento salva una nuova versione del documento, che conterrà la revisione. Le versioni precedenti del documento non verranno aggiornate. Ciò significa che è possibile che i dati oggetto di una richiesta di rettifica DSR persistano nelle versioni meno recenti dell'argomento. Le versioni precedenti di un argomento possono essere eliminate e quindi rimosse definitivamente da Office 365. Vedere la sezione in questa guida [Eliminazione di documenti in SharePoint Online e OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business).
- Per completare la redazione di un file di SharePoint in modo da rimuovere tutte le tracce di un interessato dal file, incluse tutte le versioni del file e tutte le attività registrate eseguite dall'interessato, è necessario eseguire queste operazioni:

    1. Scaricare una copia del file nel computer locale.
    2. Eliminare definitivamente il file da SharePoint Online, rimuovendolo e quindi eliminandolo dal Cestino di primo e di secondo livello. Vedere la sezione [Eliminazione di documenti in SharePoint Online e OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) in questa guida.
    3. Apportare le revisioni alla copia del documento nel computer locale.
    4. Caricare il file modificato nel percorso originale di SharePoint Online.

- È possibile modificare i dati negli elenchi di SharePoint. Vedere [Add, edit, or delete list items](https://support.office.com/article/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde) (Aggiungere, modificare o eliminare elementi di un elenco).

Gli amministratori IT possono anche correggere alcune proprietà personali associate a un documento.

Le informazioni utente del profilo utente di SharePoint o di Office 365 sono spesso associate a documenti di OneDrive for Business e SharePoint Online per rappresentare la persona, ad esempio il nome dell'utente in una colonna relativa all'autore o all'autore della modifica per un documento o per una voce di elenco. È possibile correggere queste informazioni utente in diversi modi, a seconda dell'origine:

- Rettificare le proprietà degli utenti in Active Directory locale. Per i clienti che sincronizzano le proprietà degli utenti, come il nome visualizzato dell'utente, il nome e così via, da un AD locale, tali proprietà devono essere rettificate in questa posizione. Le proprietà mappate in modo appropriato sono riportate in Office 365 e quindi in OneDrive for Business e SharePoint Online.
- Rettificare le proprietà dell'utente nell'interfaccia di amministrazione. Le modifiche apportate alle informazioni sull'account vengono applicate automaticamente nelle esperienze di OneDrive for Business e SharePoint Online. Per informazioni, vedere [Aggiungere o modificare informazioni sul profilo per un utente in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=864809). Per le proprietà di origine in Office 365, non è possibile apportare modifiche nel lato di SharePoint.
- Rettificare le proprietà utente nel profilo utente di SharePoint nell'interfaccia di amministrazione di SharePoint. Nella scheda dei profili utente dell'interfaccia di amministrazione di SharePoint, gli amministratori possono fare clic su **Gestione profili utente**, eseguire la ricerca delle proprietà dell'utente e quindi scegliere di modificarle.
- Rettificare le proprietà utente in un'origine personalizzata. Le proprietà personalizzate del profilo di SharePoint possono essere sincronizzate in un'origine personalizzata tramite Microsoft Identity Manager (MIM) o un altro metodo.

Questa operazione non influisce su tutte le esperienze, che potrebbero conservare informazioni meno recenti. Ad esempio, il nome dell'utente come testo nel documento.

### <a name="making-changes-to-content-in-power-bi"></a>Apportare modifiche al contenuto di Power BI

Power BI si basa su dati di origine sottostanti usati nei relativi dashboard e report per essere completi e accurati, quindi la correzione di dati di origine inaccurati o incompleti deve essere eseguita in questo punto. Se ad esempio è stato creato un report di Power BI connesso a Dynamics 365 for Sales come origine dati in tempo reale, è necessario apportare eventuali correzioni ai dati in Dynamics 365 for Sales.

Una volta apportate queste modifiche, è possibile sfruttare le funzionalità di [aggiornamento pianificato dei dati](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) per aggiornare il set di dati memorizzato in Power BI in modo che i dati modificati vengano applicati negli asset di Power BI correlati. Per soddisfare i requisiti GDPR, è necessario disporre di criteri per garantire che l'aggiornamento dei dati venga eseguito con una frequenza appropriata.

### <a name="making-changes-to-content-in-yammer"></a>Apportare modifiche al contenuto in Yammer

Per i messaggi, un utente può modificare un determinato messaggio per rettificare eventuali imprecisioni. È possibile richiedere un elenco di tutti i messaggi a un amministratore verificato di Yammer e quindi fare clic su un collegamento nel file per esaminare ogni messaggio.

Per i file, un utente può modificare un determinato file per rettificare eventuali imprecisioni. È possibile richiedere un elenco di tutti i file pubblicati a un amministratore verificato di Yammer e quindi accedervi in Yammer. I file esportati nella cartella appropriata possono essere visualizzati tramite una ricerca per numero di file. Per un file denominato 12345678.ppx nell'esportazione, è possibile ad esempio inserire 1235678.ppx nella casella di ricerca in Yammer. In alternativa, accedere a <strong> https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\> </strong>, ad esempio <strong> https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678 </strong>.

Per i dati accessibili tramite le impostazioni del profilo utente, l'utente può apportare le modifiche necessarie.

- Profilo utente

    - Se l'utente ha un'identità in Yammer, dispone del controllo completo del profilo. Per informazioni su come visualizzare e modificare il profilo, vedere [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851) (Modificare il profilo e le impostazioni personali in Yammer).
    - Se l'utente ha un'identità di Office 365, il profilo utente di Yammer viene estratto automaticamente da Office 365, che ottiene le informazioni del profilo da Azure Active Directory (AAD). Gli utenti di Yammer possono modificare temporaneamente i profili in Yammer, ma le modifiche vengono sovrascritte quando è presente una modifica in AAD, quindi la posizione migliore per visualizzare e modificare i dati della directory è AAD. È necessario che l'utente chieda che AAD venga aggiornato. Per altre informazioni, vedere Gestire gli utenti di Yammer nell'intero ciclo di vita da Office 365 e Aggiungere o modificare le informazioni sul profilo di un utente in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

- Impostazioni utente

    - L'utente può modificare le proprie impostazioni. Per informazioni su come visualizzare e modificare le impostazioni utente, vedere [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851) (Modificare il profilo e le impostazioni personali in Yammer).
    - Appartenenza ai gruppi dell'utente, messaggi con segnalibri, utenti e argomenti seguiti. L'utente può modificare queste informazioni. Per altre informazioni, vedere [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380) (Suggerimenti per rimanere organizzati in Yammer).

## <a name="responding-to-dsr-restriction-requests"></a>Risposta alle richieste di restrizione DSR

Di seguito vengono indicati i modi per applicare restrizioni al trattamento dei dati in Office 365:

- Rimuovere la licenza di un'applicazione di Office 365 per impedire agli utenti di accedere ai dati tramite l'applicazione
- Impedire agli utenti di accedere al proprio account di OneDrive for Business
- Disabilitare l'elaborazione dei dati in un servizio di Office 365
- Rimuovere temporaneamente i dati di SharePoint Online e OneDrive for Business e conservarli in locale
- Limitare temporaneamente l'accesso a un sito di SharePoint Online
- Impedire agli utenti di accedere a Office 365

Se in un secondo momento l'organizzazione determina che una restrizione non è più applicabile, è possibile eliminarla consentendo le operazioni messe in atto per applicarla, ad esempio riassegnare le licenze, riattivare un servizio o permettendo agli utenti di accedere a Office 365.

### <a name="removing-the-license-for-an-office-365-application"></a>Rimozione di una licenza per un'applicazione di Office 365

Come descritto in precedenza, per impostazione predefinita le licenze per tutte le applicazioni di Office 365 incluse nell'abbonamento a Office 365 dell'organizzazione sono assegnate a tutti gli utenti. Se necessario, per limitare l'accesso ai dati soggetti a un DSR, un amministratore IT può usare il portale di amministrazione di Office 365 temporaneamente disattivare la licenza di un utente per un'applicazione. Se un utente prova a usare l'applicazione, riceverà una notifica di prodotto senza licenza o un messaggio che informa che non ha più accesso. Per ulteriori dettagli vedere [Rimuovere licenze dagli utenti in Office 365 per le aziende](https://support.office.com/article/Remove-licenses-from-users-in-Office-365-for-business-9B497C85-D0A4-4735-80FA-D3565BC05BD1).

**Note:**

- Per impedire a un utente di accedere a Yammer, è necessario prima [applicare l'identità di Office 365 per un utente di Yammer](https://support.office.com/article/Enforce-office-365-identity-for-Yammer-users-008f940b-6bec-47fc-bcc6-9c6133467562) e quindi rimuovere la licenza Yammer dell'utente.

- Per gli scenari in cui è presente Power BI Embedded, è possibile limitare l'accesso all'applicazione del fornitore di software indipendente (ISV) in cui il contenuto è incorporato.

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>Impedire agli utenti di accedere al proprio account di OneDrive for Business

La rimozione della licenza di SharePoint Online di un utente non gli impedisce di accedere al proprio account di OneDrive for Business, se presente. Assegnare a se stessi le autorizzazioni di amministrazione per l'account OneDrive for Business dell'utente. A questo scopo, è possibile rimuovere l'utente come proprietario della raccolta siti di un account di OneDrive for Business. In particolare, è necessario rimuovere l'utente dall'amministratore della raccolta siti principale e dai gruppi di amministratori della raccolta siti nel suo profilo utente. Vedere la sezione "Aggiungere e rimuovere amministratori in un account di OneDrive for Business" in [Gestire i profili utente nell'interfaccia di amministrazione di SharePoint.](https://support.office.com/article/Manage-user-profiles-in-the-SharePoint-admin-center-494bec9c-6654-41f0-920f-f7f937ea9723)

### <a name="turning-off-an-office-365-service"></a>Disabilitazione di un servizio di Office 365

Un altro modo per rispondere a una richiesta di DSR per limitare l'elaborazione dei dati consiste nel disattivare un servizio Office 365. Questo effetto influisce su tutti gli utenti dell'intera organizzazione e impedirà a tutti di usare il servizio o di accedere ai dati nel servizio.

Il modo più vantaggioso per disabilitare un servizio consiste nell'usare PowerShell di Office 365 e nel rimuovere le licenze corrispondenti per tutti gli utenti dell'organizzazione. In questo modo si impedisce a chiunque di accedere ai dati presenti in tale servizio. Per istruzioni dettagliate, vedere [Disattivare l'accesso ai servizi con PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) e seguire le procedure per disabilitare i servizi di Office 365 per gli utenti da un unico piano di gestione delle licenze.

> [!NOTE]
> Per Yammer, oltre a rimuovere la licenza di Yammer dagli account utente, è necessario anche disabilitare la possibilità per gli utenti di accedere a Yammer con le credenziali relative (applicando l'uso delle credenziali di Office 365). Per istruzioni dettagliate, vedere [Disattivare l'accesso a Yammer per gli utenti di Office 365](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a).

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>Rimozione temporanea dei dati dai siti di SharePoint Online o di OneDrive for Business

Un altro modo di limitare l'elaborazione dei dati personali consiste nel rimuoverli temporaneamente da Office 365 in risposta a una richiesta DSR. Quando l'organizzazione determina che la restrizione non è più applicabile, è possibile importare nuovamente i dati in Office 365.

Poiché la maggior parte dei documenti di Office si trovano in un sito di SharePoint Online o di OneDrive for Business, di seguito viene indicato un processo di alto livello per la rimozione dei documenti e la successiva reimportazione.

1. Ottenere una copia del documento oggetto della richiesta di restrizione. Può essere necessario richiedere l'accesso al sito o rivolgersi all'amministratore globale di Office 365 o all'amministratore della raccolta di siti di inviare una copia del documento.
2. Archiviare il documento in un percorso locale (ad esempio un file server o una condivisione file) oppure in un percorso diverso dal tenant di Office 365 nel cloud Microsoft.
3. Eliminare definitivamente il documento originale da Office 365. Questo è un processo costituito da tre passaggi:

    a. Eliminare la copia originale del documento. Quando si elimina un documento da un sito, il documento viene inviato al Cestino del sito (denominato anche come *Cestino di primo livello*).

    b. Passare al Cestino del sito ed eliminare la copia del documento. Quando si elimina un documento dal Cestino del sito, il documento viene inviato al Cestino della raccolta siti (denominato anche *Cestino di secondo livello*). Vedere [Delete a file, folder, or link from a SharePoint document library](https://support.office.com/article/Delete-a-file-folder-or-link-from-a-SharePoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52) (Eliminare un file, una cartella o un collegamento da una raccolta documenti di SharePoint).

    c. Passare al Cestino della raccolta siti ed eliminare la copia del documento per rimuoverlo definitivamente da Office 365. Vedere [Delete items from the site collection recycle bin](https://support.office.com/article/Delete-items-from-the-site-collection-Recycle-Bin-dd5c00c2-aef6-4458-9d04-80b185077653) (Eliminare elementi dal Cestino della raccolta siti).

4. Quando la restrizione non è più applicabile, la copia del documento archiviato in locale può essere caricata nuovamente nel sito in Office 365.

> [!IMPORTANT]
> La procedura precedente non funziona se il documento si trova in un sito bloccato (in base a una delle funzionalità di conservazione o di blocco a fini giudiziari in Office 365). Nel caso in cui una richiesta di restrizione per una richiesta DSR abbia la precedenza rispetto a un blocco a fini giudiziari, prima che il documento possa essere eliminato in modo definitivo il blocco deve essere rimosso dal sito. Per i documenti eliminati, viene rimossa definitivamente anche la cronologia dei documenti.

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>Restrizione temporanea dell'accesso ai siti di SharePoint Online

Un amministratore di SharePoint Online può temporaneamente impedire a tutti gli utenti di accedere a una raccolta siti di SharePoint Online bloccando la raccolta siti (usando il comando **Set -SPOSite-LockStatet** in PowerShell di SharePoint Online). Ciò impedisce agli utenti di accedere alla raccolta siti e a tutti i contenuti o dati che si trovano nel sito. Se si stabilisce che gli utenti devono essere in grado di accedere al sito, l'amministratore può sbloccare il sito. Per informazioni su come eseguire questo cmdlet di PowerShell, vedere [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite).

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>Impedire agli utenti di accedere a Office 365

Un amministratore IT può anche impedire a un utente di accedere a Office 365 e in questo caso l'utente non può accedere ad alcun servizio online di Office 365 né trattare alcun dato archiviato in Office 365. Vedere [Bloccare l'accesso di un ex dipendente ai dati di Office 365](https://support.office.com/article/Remove-a-former-employee-from-Office-365-44d96212-4d90-4027-9aa9-a95eddb367d1).

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>Parte 2: risposta alle richieste DSR con rispetto alle informazioni generate da Office 365

La famiglia di servizi Office 365 di Microsoft include servizi online che offrono informazioni a utenti e organizzazioni che hanno scelto di usarli.

- Delve e MyAnalytics offrono informazioni approfondite agli utenti singoli
- Workplace Analytics offre informazioni approfondite alle organizzazioni

Tali servizi sono descritti nelle sezioni seguenti:

### <a name="delve"></a>Delve

In Delve gli utenti possono gestire il proprio profilo di Office 365 e individuare persone e documenti che potrebbero essere rilevanti per loro. Gli utenti vedranno solo i documenti a cui hanno accesso. Per una serie di articoli utili su ricerche approfondite, vedere[Office Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca).

#### <a name="access-and-export"></a>Accesso ed esportazione

Gli amministratori non possono accedere né esportare i dati Delve degli utenti. Ciò significa che gli utenti devono accedere ai dati di Delve ed esportarli in modo autonomo. La maggior parte dei tipi di dati è accessibile e può essere esportata direttamente da Delve, ma alcuni tipi di dati sono disponibili solo tramite altri servizi.

##### <a name="data-available-in-the-delve-user-interface"></a>Dati disponibili nell'interfaccia utente di Delve

- **Dati del profilo:** si tratta di informazioni del profilo dell'elenco indirizzi globale dell'organizzazione in Azure Active Directory, oltre a informazioni facoltative su se stessi che gli utenti hanno scelto di aggiungere. Per accedere o esportare dati del profilo in Delve, fare clic su **Me** \> **Aggiorna profilo**. È possibile copiare il contenuto direttamente dalla pagina o
- **Dati del blog:** si tratta dei post di blog pubblicati da un utente. Per accedere ai dati del blog o per esportarli, fare clic su **Me** \> **Tutti i post**. È possibile copiare il contenuto direttamente dalla pagina o acquisire uno screenshot.
- **Dati dei contatti recenti:** si tratta di persone dell'organizzazione che Delve ha stabilito essere più rilevanti per l'utente in un determinato momento. Quando un utente fa clic su **Me**\> **Visualizza tutto** nel riquadro "Fai clic su una persona per vedere a cosa sta lavorando", Delve mostra le persone più rilevanti per un utente in un determinato momento.

##### <a name="data-available-through-an-export-link-in-delve"></a>Dati disponibili tramite un collegamento di esportazione in Delve

- **Dati di elenco contatti:** sono le persone che gli utenti hanno visualizzato in Delve. L'elenco **Persone** viene visualizzato nel riquadro sinistro della home page. Gli utenti possono esportare un elenco delle ultime persone che hanno visualizzato in Delve.
- **Preferiti:** si tratta di bacheche e documenti che l'utente ha contrassegnato come Preferiti. La pagina **Preferiti** contiene bacheche e documenti che l'utente ha aggiunto come Preferiti. Gli utenti possono esportare un elenco delle bacheche e dei documenti preferiti correnti.
- **Dati sulle impostazioni della funzionalità:** si tratta di azioni o configurazioni di Delve dovute all'uso di Delve da parte di un utente. Gli utenti possono esportare un elenco completo di tali impostazioni.

Per accedere o esportare i dati di cui sopra, l'utente può fare clic sull'icona a forma di ingranaggio nell'angolo superiore destro in Delve, e quindi fare clic su **Feature settings** > **Export data** (Impostazioni della funzionalità > Esporta dati). Le informazioni vengono esportate in formato JSON.

##### <a name="data-thats-available-through-other-services"></a>Dati disponibili tramite altri servizi

- **Dati di documenti rilevanti:** si tratta di documenti e allegati di posta elettronica rilevanti per l'utente. Delve organizza dinamicamente i documenti e i messaggi di posta elettronica in base alle attività dell'utente e alle persone con cui collabora in Office 365. Quando un utente apre Delve o fa clic su **Home**, Delve mostra i documenti o gli allegati più importanti per l'utente in un determinato momento. Per accedere a documenti e allegati o per esportarli, è possibile passare al servizio Office 365 tramite il quale il documento o l'allegato è stato reso disponibile (ad esempio Office.com, SharePoint Online, OneDrive for Business oppure Exchange Online).
- **Dati su documenti e allegati di posta elettronica recenti:** si tratta di documenti e allegati di posta elettronica che l'utente ha modificato. Quando un utente fa clic su **Me** \> **Visualizza tutto** nel riquadro "Torna ai documenti e agli allegati di posta elettronica recenti", Delve mostra i documenti e gli allegati di posta elettronica più recenti che l'utente ha modificato in un determinato momento. Per accedere a documenti e allegati o per esportarli, è possibile passare al servizio Office 365 tramite il quale il documento o l'allegato è stato reso disponibile; ad esempio, Office.com, SharePoint Online, OneDrive for Business oppure Exchange Online.
- **Dati sui documenti dei colleghi:** si tratta di documenti che Delve ha stabilito essere più rilevanti per l'utente in un determinato momento. Quando un utente fa clic su **Me** \> **Visualizza tutto** nel riquadro "Scopri i documenti dei colleghi", Delve mostra i documenti più rilevanti per un utente in un determinato momento. Per accedere a documenti o per esportarli, è possibile passare al servizio Office 365 tramite il quale il documento o l'allegato è stato reso disponibile; ad esempio, Office.com, SharePoint Online, OneDrive for Business oppure Exchange Online.

#### <a name="rectify"></a>Rettifica

In Delve gli utenti possono modificare le informazioni seguenti:

- **Informazioni sul profilo:** un utente può fare clic su **Me** \> **Aggiorna profilo** per aggiornare le proprie informazioni. In base alle impostazioni dell'organizzazione nell'elenco indirizzi globale, gli utenti potrebbero non essere in grado di modificare tutte le informazioni del profilo, ad esempio il nome o la posizione lavorativa.
- **Impostazioni della funzionalità:** un utente può fare clic sull'icona a forma di ingranaggio nell'angolo superiore destro in Delve e quindi fare clic su **Impostazioni della funzionalità** \> per modificare le impostazioni desiderate.

#### <a name="restrict"></a>Restrizione

Per limitare l'elaborazione di dati in Delve nell'organizzazione, è possibile disabilitare Office Graph. Per altre informazioni, vedere [qui](https://support.office.com/article/office-delve-for-office-365-admins-54f87a42-15a4-44b4-9df0-d36287d9531b#bkmk_delveonoff).

#### <a name="delete"></a>Eliminazione

In Delve gli utenti possono eliminare le informazioni seguenti:

- **Informazioni sul profilo:** per eliminare le informazioni sul profilo, è possibile fare clic su **Me** \> **Aggiorna profilo** e quindi eliminare il testo in formato libero. In base alle impostazioni dell'organizzazione nell'elenco indirizzi globale, gli utenti potrebbero non essere in grado di eliminare tutte le informazioni del profilo, ad esempio il nome o la posizione lavorativa.
- **Documenti e allegati di posta elettronica:** per eliminare un documento o un allegato, gli utenti devono accedere al servizio in cui il documento o l'allegato è archiviato (ad esempio SharePoint Online, OneDrive for Business oppure Exchange Online) ed eliminare il documento.

### <a name="myanalytics"></a>MyAnalytics

MyAnalytics offre statistiche che consentono agli utenti di comprendere come trascorrono il tempo dedicato al lavoro. Per aiutare gli utenti a comprendere meglio i dati visualizzati nel dashboard personale e il modo in cui vengono calcolati, indirizzarli all'argomento della Guida [MyAnalytics personal dashboard](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard) (Dashboard personale di MyAnalytics).

#### <a name="access-and-export"></a>Accesso ed esportazione

Se l'organizzazione usa MyAnalytics, Microsoft genera informazioni approfondite per tutti gli utenti. Tutti gli approfondimenti MyAnalytics sono derivati dalle intestazioni di posta elettronica e riunione nella cassetta postale dell'utente. Gli utenti possono accedere [al dashboard di MyAnalytics](https://delve.office.com) durante l'accesso al proprio account di Office 365 per visualizzare le informazioni che vengono generate sul modo in cui dedicano il proprio tempo al lavoro. È possibile creare screenshot di approfondimenti di MyAnalytics, se vogliono avere copie permanenti delle loro informazioni.

#### <a name="rectify"></a>Rettifica

Tutte le informazioni generate da MyAnalytics derivano dagli elementi di posta elettronica e di calendario dell'utente. Di conseguenza, non è possibile rettificare alcun elemento diverso da quelli di posta elettronica o di calendario di origine.

#### <a name="restrict"></a>Restrizione

Per limitare l'elaborazione per un utente specifico, è possibile esprimere il rifiuto in modo esplicito in MyAnalytics. Per altre informazioni, vedere [Configure MyAnalytics user settings](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-mya-user-settings) (Configurare le impostazioni utente di MyAnalytics).

#### <a name="delete"></a>Eliminazione

Tutto il contenuto delle cassette postali, ad esempio i dati di MyAnalytics, viene rimosso quando un account utente viene eliminato in modo definitivo da Active Directory. Per ulteriori informazioni, vedere la sezione [Eliminazione di un utente](#deleting-a-user) nella presente guida.

### <a name="workplace-analytics"></a>Workplace Analytics

Workplace Analytics consente alle organizzazioni di integrare i dati di Office 365 con i propri dati aziendali per ottenere informazioni approfondite sulla produttività a livello di organizzazione, sui modelli di collaborazione e sul coinvolgimento dei dipendenti. [Questo articolo](https://docs.microsoft.com/workplace-analytics/overview/privacy-and-data-access) illustra il controllo che l'organizzazione ha sui dati elaborati da Workplace Analytics e sugli utenti che possono accedere ai dati stessi.

Per gestire le richieste DSR in Workplace Analytics: 

1. Determinare se l'organizzazione usa Workplace Analytics. Per altre informazioni, vedere [Assign licenses to users in Office 365 for Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users) (Assegnare licenze agli utenti in Office 365 per le aziende). Se l'organizzazione non usa Workplace Analytics, non sono disponibili ulteriori azioni.

2. Se l'organizzazione usa Workplace Analytics, verificare a quali utenti nell'organizzazione è stato assegnato il ruolo di amministratore di Workplace Analytics.  È anche necessario determinare se la cassetta postale dell'interessato dispone della licenza di Workplace Analytics. Se necessario, chiedere all'amministratore di Workplace Analytics di contattare il supporto tecnico Microsoft per gestire le richieste DSR seguenti: 

#### <a name="access-and-export"></a>Accesso ed esportazione

I rapporti di Workplace Analytics creati dall'utente potrebbero contenere o meno dati personali di utenti che l'organizzazione ha concesso in licenza per Workplace Analytics, a seconda delle informazioni che l'organizzazione ha usato per integrare i dati di Office 365. L'amministratore di Workplace Analytics deve rivedere tali report per determinare se contegono i dati personali di un utente. Se il report contiene i dati personali di un utente, è necessario decidere se si vuole fornire all'utente una copia del report. Workplace Analytics consente di esportare il report. 

#### <a name="rectify"></a>Rettifica

Come illustrato in precedenza, Workplace Analytics usa i dati di Office 365 con i dati aziendali forniti per generare report di interesse. Impossibile rettificare i dati di Office 365; è basato sulle attività di posta elettronica e calendario di un utente. Tuttavia, i dati dell'organizzazione caricati inWorkplace Analytics per generare il report possono essere corretti. Per eseguire questa operazione, è necessario correggere i dati di origine, caricarli ed eseguire di nuovo il report per generare un nuovo report di Workplace Analytics.

#### <a name="restrict"></a>Restrizione

Per limitare il trattamento per un utente specifico, è possibile rimuoverne la licenza di Workplace Analytics.

#### <a name="delete"></a>Eliminazione

Se un interessato desidera essere rimosso da un report o da un insieme di report di Workplace Analytics, è possibile eliminare il report stesso. L'amministratore è tenuto a eliminare gli utenti dai dati dell'organizzazione utilizzati per generare il report, e a ricaricare i dati. Tutti i dati relativi all'utente vengono rimossi quando un account utente viene eliminato definitivamente da Azure Active Directory. 

Per rimuovere i dati personali di un interessato, un amministratore globale di Office 365 può eseguire le operazioni seguenti: 

1. Rimuovere la licenza di Workplace Analytics dall'interessato.
2. Eliminare la voce Azure Active Directory (AAD) per l'interessato. Per ulteriori informazioni, vedere [Eliminare un utente](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user).
3. Contattare il supporto tecnico e far aprire un ticket per una richiesta DSR di eliminazione di un utente. In tale ticket, identificare l'interessato tramite il relativo nome dell'entità utente (UPN).
4. Esportare una copia dei dati sulle risorse umane dal sistema delle risorse umane dell'azienda (vedere l'apposito [articolo](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data#step-three--export-data)), rimuovere le informazioni dell'interessato dal file dei dati sulle risorse umane, quindi caricare il file dei dati delle risorse umane modificato in formato .csv in Workplace Analytics; vedere [Upload organizational data](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data) (Caricare i dati dell'organizzazione).

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>Parte 3. Risposta alle richieste DSR per log generati dal sistema

Microsoft offre la possibilità di accedere, esportare ed eliminare log generati dal sistema che possono essere considerati personali secondo una definizione ampia di "dati personali" del GDPR. Esempi di log generati dal sistema che possono essere considerati personali ai sensi del GDPR includono:

- Dati di utilizzo di prodotti e servizi, ad esempio log di attività dell'utente
- Richieste di ricerca degli utenti e dati della query
- Dati generati da prodotti e servizi, come risultato della funzionalità del sistema e dell'interazione da parte di utenti o di altri sistemi

La possibilità di limitare o rettificare i dati nei log generati dal sistema non è supportata. I dati nei log generati dal sistema costituiscono le azioni effettive eseguite del cloud Microsoft e i dati di diagnostica e le modifiche a tali dati possono compromettere il record cronologico delle azioni, aumentando i rischi per la sicurezza e le truffe.

### <a name="accessing-and-exporting-system-generated-logs"></a>Accesso ed esportazione di log generati dal sistema

Gli amministratori possono accedere ai log generati dal sistema associati all'uso da parte di un utente specifico dei servizi e delle applicazioni di Office 365. Per accedere ed esportare i log generati dal sistema:

1. Accedere a [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) ed effettuare l'accesso con le credenziali di amministratore globale di Office 365.

2. Nell'elenco a discesa **Privacy** nella parte superiore della pagina fare clic su **Richiesta DSR**.

3. Nella pagina **Richiesta DSR**, in **Log generati dal sistema**, fare clic su **Esportazione log di dati**.

    Viene visualizzata **Esportazione log di dati**. Viene visualizzato un elenco di richieste di esportazione dati inviate dall'organizzazione.

4. Per creare una richiesta per un utente, fare clic su **Crea richiesta di esportazione dati**.

Dopo aver creato una richiesta, questa verrà elencata nella pagina **Esportazione log di dati** in cui è possibile tenere traccia del relativo stato. Una volta completata la richiesta, è possibile fare clic su un collegamento per accedere ai log generati dal sistema, che verranno esportati nella posizione di archiviazione di Azure di dell'organizzazione entro 30 giorni dalla creazione della richiesta. I dati vengono salvati in un formato di file comune, leggibile dal computer, come JSON o XML. Se non si dispone di un account di Azure e di una posizione di archiviazione di Azure, è necessario creare un account di Azure e/o una posizione di archiviazione di Azure per l'organizzazione in modo che lo strumento di esportazione del log dei dati possa esportare i log generati dal sistema. Per ulteriori informazioni, vedere [Introduzione ad Archiviazione di Azure](https://docs.microsoft.com/azure/storage/common/storage-introduction).

> [!NOTE]
> Quando si crea una richiesta di esportazione dei dati, i dati generati dal sistema per alcune applicazioni non verranno esportati tramite lo strumento Esportazione log di dati. Per esportare i dati per tali applicazioni, vedere [Additional steps to export system-generated log data](https://docs.microsoft.com/microsoft-365/compliance/gdpr-system-generated-log-data) (Ulteriore procedura di esportazione dei dati del log generato dal sistema).

Di seguito viene fornito un riepilogo sull'accesso e sull'esportazione dei log generati dal sistema tramite lo strumento Esportazione log di dati:

- **Quanto tempo impiega lo strumento di esportazione di log di dati di Microsoft per completare una richiesta?:** ciò può dipendere da diversi fattori. Generalmente l'operazione deve essere completata in uno o due giorni, ma può richiedere fino a 30 giorni.

- **In quale formato sarà l'output?:** l'output è fornito in file leggibili strutturati come XML, CSV o JSON.

- **Chi ha accesso allo strumento di esportazione di log di dati per inviare le richieste di accesso a log generati dal sistema?:** gli amministratori globali di Office 365 hanno accesso all'utilità di gestione dei log del GDPR.

- **Quali dati vengono restituiti dallo strumento di esportazione di log di dati?:** lo strumento di esportazione di log di dati restituisce log generati dal sistema che vengono archiviati da Microsoft. I dati esportati includono vari servizi Microsoft, tra cui Office 365, Azure e Dynamics.

- **Come vengono restituiti i dati all'utente?:** i dati vengono esportati nel percorso di archiviazione di Azure dell'organizzazione. Spetta agli amministratori dell'organizzazione stabilire come questi dati verranno mostrati/restituiti agli utenti.

- **Che aspetto avranno i dati nei log generato dal sistema?:** esempio di un record di log generato dal sistema in formato JSON:

   ```
   [{
            "DateTime": "2017-04-28T12:09:29-07:00",
             "AppName": "SharePoint",
             "Action": "OpenFile",
             "IP": "154.192.13.131",
             "DevicePlatform": "Windows 1.0.1607"
   }]
   ```

> [!NOTE]
> Alcune funzionalità non consentono l'esportazione o l'eliminazione dei log generati dal sistema contenenti informazioni riservate per mantenere l'integrità di tali informazioni per motivi di sicurezza e controllo.

I dati di utilizzo dei prodotti e dei servizi per alcuni dei servizi usati più di frequente, ad esempio Exchange Online, SharePoint Online, Skype for Business, Yammer e i Gruppi di Office 365, possono essere recuperati anche eseguendo una ricerca nel log di controllo di Office 365 nel Centro di sicurezza e conformità. Per altre informazioni, vedere [Usare lo strumento di ricerca nel log di controllo di Office 365](#use-the-office-365-audit-log-search-tool-in-dsr-investigations) nelle indagini DSR nell'appendice A. L'uso del log di controllo può essere di interesse perché è possibile assegnare autorizzazioni ad altri utenti dell'organizzazione, ad esempio al responsabile della conformità per eseguire ricerche nel log di controllo per accedere ai dati.

#### <a name="national-clouds"></a>Cloud nazionali

Un amministratore IT globale deve eseguire le operazioni seguenti per esportare i dati del log generato dal sistema nei cloud nazionali indicati di seguito:

- Office 365 Germany: [accedere a Microsoft Service Trust Portal per la Germania](https://aka.ms/MicrosoftSTPGermany) e completare i passaggi descritti in precedenza.

- Office 365 US Government: [accedere al portale di amministrazione di Office 365](https://portal.office365.us) e inviare una richiesta al Supporto tecnico Microsoft.

- Office 365 gestito da 21Vianet (Cina): [accedere al portale di amministrazione di Office 365 gestito da 21Vianet](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage) e quindi accedere a **Commercio** > **Abbonamento** > **Privacy** > **GDPR** e immettere le informazioni richieste.

### <a name="deleting-system-generated-logs"></a>Eliminazione di log generati dal sistema

Per eliminare i log generati dal sistema recuperati attraverso una richiesta di accesso, è necessario rimuovere l'utente dal servizio ed eliminare definitivamente il suo account Azure Active Directory. Per istruzioni su come eliminare definitivamente un utente, vedere la sezione [Eliminazione di un utente](#deleting-a-user). È importante tenere presente che l'operazione di eliminazione definitiva di un account utente è irreversibile una volta avviata.

Se si elimina definitivamente un account utente, i dati dell'utente verranno rimossi dai registri generati dal sistema per quasi tutti i servizi di Office 365 entro 30 giorni. Una delle eccezioni è che l'eliminazione definitiva dell'account utente impiega più di 30 giorni in Exchange Online. Data la natura critica del contenuto di Exchange Online ed evitare perdite accidentali di dati. Il sistema è stato progettato in modo da inserire intenzionalmente i dati in uno stato di conservazione per un massimo di 60 giorni dopo l'eliminazione definitiva di un account utente. Per eliminare definitivamente i dati di Exchange Online di un utente in un periodo di 30 giorni, eliminare definitivamente l'account utente in Azure Active Directory e quindi contattare il [supporto tecnico Microsoft](https://support.microsoft.com/) e richiedere che i dati di Exchange Online dell'utente siano manualmente rimosso all'esterno del processo di eliminazione pianificato. Per altre informazioni, vedere [Rimuovere i dati di Exchange Online](#removing-exchange-online-data), illustrati in precedenza in questa guida

L'eliminazione di un account utente non rimuove i log generati dal sistema per Yammer e Kaizala. Per rimuovere i dati da queste applicazioni, vedere uno degli argomenti seguenti:

- Yammer - [Manage GDPR data subject requests in Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise) (Gestire le richieste degli interessati per Yammer Enterprise nell'ambito del GDPR)
- Kaizala - [Export or delete a user's organizational data in Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data) (Esportare o eliminare i dati dell'organizzazione di un utente in Kaizala)

#### <a name="national-clouds"></a>Cloud nazionali

Un amministratore IT globale deve eseguire le operazioni seguenti per eliminare i dati del log generato dal sistema nei cloud nazionali indicati di seguito:

- Office 365 Germany: quando l'account utente viene eliminato definitivamente, anche i log generati dal sistema vengono eliminati. 
- Office 365 US Government: inviare una richiesta al Supporto tecnico Microsoft tramite il [Portale di amministrazione di Office 365](http://portal.office365.us).
- Office 365 gestito da 21Vianet (Cina): inviare una richiesta al Supporto tecnico Microsoft tramite il portale di amministrazione di Office 365 a questo [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Accedere a **Commercio**, quindi selezionare **Abbonamento** -> **Privacy** -> **GDPR** e immettere le informazioni richieste.

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>Parte 4: risorse aggiuntive per rispondere alle richieste DSR

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>Guide alle richieste DSR per altri servizi aziendali Microsoft

Questa guida è dedicata all'argomento su come trovare e agire sui dati personali per rispondere a DSRs quando si usano i prodotti, i servizi e gli strumenti amministrativi di Office 365. Passare al portale di [attendibilità dei servizi Microsoft](https://servicetrust.microsoft.com/) per accedere alle guide simili per altri servizi Microsoft Enterprise.

### <a name="microsoft-support"></a>Supporto tecnico Microsoft

I "dati relativi al supporto" sono i dati inviati a Microsoft quando l'organizzazione o gli utenti interagiscono con Microsoft per ricevere assistenza in relazione a Office 365 o ad altri prodotti e servizi Microsoft (ad esempio, per risolvere un comportamento non previsto del prodotto). Alcuni di questi dati possono contenere dati personali. Per altre informazioni, vedere [Microsoft Support and Professional Services Data Subject Requests for the GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services) (Richieste degli interessati per servizi professionali e supporto tecnico Microsoft nell'ambito del GDPR).

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>Prodotti e servizi autenticati con un ID organizzazione per cui Microsoft è un titolare del trattamento dei dati

Le parti 1-3 di questa guida si occupano di prodotti e servizi per i quali Microsoft funge da responsabile del trattamento dei dati per l'organizzazione, pertanto la funzionalità DSR viene resa disponibile all'amministratore del tenant. Ci sono varie circostanze in cui gli utenti dell'organizzazione possono usare il proprio account aziendale o dell'Istituto di istruzione (noto anche come "ID di Azure Active Directory" o "AAD") per accedere ai prodotti e ai servizi Microsoft per cui Microsoft è un responsabile dei dati. Per tutti i prodotti e i servizi di questo tipo, è necessario che gli utenti inizino a indirizzare le proprie richieste DSR direttamente a Microsoft e Microsoft soddisferà tali richieste direttamente all'utente. La progettazione, i prodotti e i servizi che interessano lo spazio di archiviazione del contenuto creato dall'utente consentono agli utenti di accedere, esportare, rettificare ed eliminare il contenuto creato dall'utente nell'ambito delle funzionalità intrinseche dei prodotti. Scenari in cui è possibile applicare questa procedura:

- **Servizi online connessi opzionali:** Office 365 ProPlus rende disponibili per l'utente alcuni servizi online connessi opzionali. L'elenco di servizi e controlli relativi all'utente è fornito [qui](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8). È possibile decidere se si desidera consentire agli utenti finali di usare questi servizi. Per altre informazioni, vedere [In che modo gli amministratori possono gestire i servizi di trattamento dei dati in Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus). Se tali servizi opzionali trattano i dati personali, Microsoft è il titolare del trattamento dei dati per questi servizi.
- **Commenti e suggerimenti degli utenti**: se gli utenti scelgono di inviare commenti e suggerimenti su prodotti e servizi Microsoft, Microsoft è titolare del trattamento dei dati per tali commenti nella misura in cui contengono dati personali dell'utente. Microsoft risponde a qualsiasi richiesta dell'interessato per i commenti e i suggerimenti raccolti da Microsoft (inclusi quelli gestiti da responsabili secondari Microsoft) ad eccezione dei casi in cui Microsoft abbia indicato esplicitamente agli utenti di non includere dati personali dell'utente durante il processo di raccolta dei commenti. Eccezioni: se Microsoft ha indicato esplicitamente agli utenti di non includere dati personali durante il processo di raccolta dei commenti, Microsoft si basa su tale istruzione e presuppone che non sia stato specificato alcun dato personale. Gli utenti che hanno creato un account diverso con il provider di servizi di commenti e suggerimenti di terze parti devono gestire la richiesta DSR direttamente con tali provider.
- **Autenticazione di Windows con l'account aziendale o dell'istituto di istruzione:** se l'organizzazione ha acquistato licenze di Windows e gli utenti eseguono l'autenticazione all'organizzazione Windows con il proprio account aziendale o dell'istituto di istruzione, Microsoft si comporta come titolare del trattamento dei dati. Per altre informazioni, vedere [Windows Data Subject Requests for the GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-windows) (Richieste dell'interessato per Windows nell'ambito del GDPR).
- **Prodotti o servizi acquistati dall'utente:** se si consente agli utenti, che agiscono singolarmente, di acquistare prodotti o servizi che usano AAD per l'autenticazione (ad esempio componenti aggiuntivi di Office add-on o applicazioni disponibili in Microsoft Store), Microsoft può essere un titolare del trattamento dei dati. Per tali prodotti o servizi Microsoft, gli utenti devono contattare direttamente Microsoft per avviare una richiesta DSR.

> [!IMPORTANT]
> Se si elimina un utente abilitato tramite Azure Active Directory, l'utente (precedente) perderà la possibilità di accedere a qualsiasi prodotto o servizio su cui si basava per un account aziendale o dell'istituto di istruzione. Microsoft non sarà nemmeno in grado di autenticare l'utente in relazione a una richiesta DSR per prodotti o servizi per cui Microsoft è un titolare del trattamento dei dati. Se si vuole consentire agli utenti di avviare la richieste DSR rispetto a tali servizi, è importante indicare all'utente di operare in tal senso prima di eliminare l'account AAD dell'utente.

### <a name="personal-accounts"></a>Account personali

Se gli utenti hanno usato account Microsoft (ovvero account personali) per acquistare prodotti e servizi da Microsoft per uso personale e per cui Microsoft è un titolare del trattamento dei dati, possono avviare richieste DSR tramite il [dashboard sulla privacy di Microsoft](https://account.microsoft.com/account/privacy).

### <a name="third-party-products"></a>Prodotti di terze parti

Se l'organizzazione o gli utenti che agiscono singolarmente hanno acquistato prodotti o servizi di terze parti e usano il proprio account aziendale o dell'istituto di istruzione Microsoft per l'autenticazione, tutte le richieste dell'interessato devono essere dirette alla terze parti applicabili.

## <a name="appendix-a-preparing-for-dsr-investigations"></a>Appendice A: preparazione per le indagini DSR

Per preparare l'organizzazione a svolgere indagini DSR tramite servizi di Office 365, tenere presente quanto segue:

- Usare lo strumento di gestione dei casi DSR eDiscovery nel Centro sicurezza e conformità di Office 365 per gestire indagini DSR
- Configurare i limiti di conformità per limitare l'ambito delle ricerche contenuto
- Usare lo strumento di ricerca log di controllo di Office 365 nelle indagini DSR

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>Usare lo strumento di gestione dei casi DSR per gestire le indagini DSR

Per gestire le indagini DSR, è consigliabile usare lo strumento di gestione dei casi DSR nel Centro sicurezza e conformità. Tale strumento consente di eseguire queste operazioni:

- Creare un caso distinto per ogni indagine DSR.

- Usare il predefinito per cercare tutto il contenuto correlato a uno specifico oggetto dei dati. Quando si crea un caso e si avvia la ricerca, vengono cercate i percorsi di contenuto:

   - Tutte le cassette postali nell'organizzazione (comprese quelle associate a Microsoft Teams e Gruppi di Office 365)
   - Tutti i siti di SharePoint Online e gli account di OneDrive for Business nell'organizzazione
   - Tutti i siti di Microsoft Teams e i siti dei gruppi di Office 365 nell'organizzazione
   - Tutte le cartelle pubbliche in Exchange Online

- Modificare la query di ricerca predefinita ed eseguire nuovamente la ricerca per restringere i risultati della ricerca.

- Controllare chi ha accesso al caso aggiungendo persone come membri dello stesso. Solo i membri possono accedere al caso e possono solo vedere i propri nell'elenco di casi nella pagina casi DSR nel centro sicurezza & conformità. Inoltre, è possibile assegnare autorizzazioni diverse a diversi membri dello stesso caso. Ad esempio, è possibile consentire ad alcuni membri di visualizzare solo il caso e i risultati di una ricerca contenuto e consentire ad altri membri di creare ricerche ed esportare i risultati della ricerca.

- Creare processi di esportazione per esportare i risultati della ricerca in risposta a una richiesta di esportazione DSR. È possibile esportare tutto il contenuto restituito dalla ricerca contenuto. Vengono esportati anche altri dati di Office 365 correlati a un oggetto dati.

- Creare processi di esportazione per esportare i risultati della ricerca in risposta a una richiesta di esportazione DSR. È possibile esportare tutto il contenuto restituito dalla ricerca contenuto. È anche possibile esportare i log generati dal sistema per il servizio di roaming di Office.

- Eliminare i casi in cui il processo di indagine DSR è completato. Vengono rimosse tutte le ricerche di contenuto e i processi di esportazione associati al caso.

Per iniziare a usare i casi DSR, vedere [Gestire richieste dell'interessato per il GDPR con lo strumento dei casi DSR nel Centro sicurezza e conformità di Office 365](https://support.office.com/article/manage-dsr-cases-in-the-office-365-security-compliance-center-ce9eb942-3589-42cb-88fd-1576ecb09c5c).

> [!IMPORTANT]
> Un amministratore di eDiscovery può visualizzare e gestire tutti i casi DSR nell'organizzazione. Per ulteriori informazioni sui diversi ruoli correlati a eDiscovery, vedere [Assegnare autorizzazioni eDiscovery a potenziali membri del caso](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions).

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>Configurare i limiti di conformità per limitare l'ambito delle ricerche contenuto

I limiti di conformità vengono implementati tramite le funzionalità di filtro delle autorizzazioni di ricerca nel Centro sicurezza e conformità. Tali limiti consentono di creare limiti logici di ricerca all'interno dell'organizzazione per controllare i percorsi di contenuto (ad esempio cassette postali di Exchange Online e siti di SharePoint Online) in cui un responsabile della conformità o un amministratore IT può eseguire la ricerca. I limiti sono utili per organizzazioni multinazionali che devono rispettare confini geografici, per organizzazioni governative che devono tenere separati i diversi organismi e per organizzazioni aziendali separate in business unit o reparti. Per tutti questi scenari, i limiti di conformità possono essere usati nelle indagini DSR per limitare le cassette postali e siti in cui le persone coinvolte possono eseguire le ricerche.

I limiti di conformità possono essere usati con i casi eDiscovery per limitare i percorsi di contenuto in cui è possibile eseguire ricerche in un'indagine solo ai percorsi in un organismo o in una business unit.

Di seguito viene indicata una panoramica generale su come implementare i limiti di conformità (con i casi eDiscovery) per le indagini DSR.

1. Determinare gli organismi dell'organizzazione che verranno designati come limiti di conformità.

2. Determinare quale attributo di oggetto utente in Azure Active Directory verrà usato per definire il limite di conformità. È possibile, ad esempio, scegliere l'attributo paese, codice paese o reparto, in modo che i membri del gruppo di ruoli di amministratore creato nel passaggio successivo possano eseguire la ricerca solo nei percorsi di contenuto degli utenti che hanno un valore specifico per tale attributo. In questo modo è possibile limitare gli utenti che possono eseguire ricerche di contenuto in un organismo specifico.

> [!NOTE]
> Attualmente non è necessario eseguire un ulteriore passaggio per OneDrive for Business e inviare una richiesta al supporto tecnico Microsoft per sincronizzare l'attributo con gli account di OneDrive for Business.

4. Creare un gruppo di ruoli di amministratore nel Centro sicurezza e conformità di Office 365 per ogni limite di conformità. È consigliabile creare questi gruppi di ruoli copiando il gruppo di ruoli di responsabili eDiscovery predefiniti e quindi rimuovendo i ruoli in base alle esigenze.

5. Aggiungere membri a ognuno dei gruppi di ruoli specifici come Manager di eDiscovery. I membri sono le persone responsabili per le indagini e le risposte alle richieste DSR, in genere amministratori IT, responsabili della privacy dei dati e della conformità e rappresentanti delle risorse umane.

6. Creare un filtro di autorizzazioni per la ricerca per ogni limite di conformità in modo che i membri del gruppo di ruoli amministratore corrispondente possano eseguire ricerche nelle cassette postali e nei siti di per gli utenti all'interno di tale perimetro/conformità. Il filtro delle autorizzazioni di ricerca consente ai membri del gruppo di ruoli corrispondente di cercare solo i percorsi di contenuto con il valore dell'attributo oggetto utente corrispondente al limite di agenzia/conformità.

Per istruzioni dettagliate, vedere [Set up compliance boundaries for eDiscovery investigations in Office 365](https://support.office.com/article/1b45c82f-26c8-44fb-9f3b-b45436fe2271) (Impostare i limiti di conformità per indagini eDiscovery in Office 365).

### <a name="use-the-office-365-audit-log-search-tool-in-dsr-investigations"></a>Usare lo strumento di ricerca log di controllo di Office 365 nelle indagini DSR

Gli amministratori IT possono usare lo strumento di ricerca nel log di controllo in Centro sicurezza e conformità per identificare documenti, file e altre risorse di Office 365 che gli utenti hanno creato, modificato o eliminato oppure a cui hanno eseguito l'accesso. La ricerca di questo tipo di attività può essere utile nelle indagini DSR. In SharePoint Online e OneDrive for Business, ad esempio, gli eventi di controllo vengono registrati quando gli utenti eseguono queste attività:

- Accesso a un file
- Modifica di un file
- Spostamento di un file
- Upload o download di un file

È possibile eseguire una ricerca nel log di controllo per attività specifiche, tipi di attività, attività eseguite da un utente specifico e altri criteri di ricerca. Oltre alle attività di SharePoint Online e OneDrive for Business, è anche possibile cercare le attività in flussi, Power BI e Microsoft Teams. I record di controllo vengono conservati per 90 giorni. Di conseguenza, non sarà possibile cercare le attività utente che si sono verificate più di 90 giorni fa. Per un elenco completo delle attività controllate e come eseguire una ricerca nel log di controllo, vedere [Eseguire ricerche nel log di controllo nel centro sicurezza & conformità di Office 365](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance).

> [!TIP]
> Per aggirare il limite di 90 giorni descritto in precedenza e mantenere una cronologia di esecuzione dei record di controllo dell'organizzazione, è possibile esportare periodicamente tutte le attività (ad esempio ogni 30 giorni) per disporre costantemente dei record di controllo dell'organizzazione.

## <a name="appendix-b-change-log"></a>Appendice B: log delle modifiche

La tabella seguente elenca le modifiche alla Guida DSR di Office 365 dalla sua pubblicazione iniziale del 25 maggio 2018.

|Data  |Sezione/App |Modifica  |
|:---------|:---------|:---------|
|18/9/2018 | [Whiteboard](#whiteboard) |Whiteboard Preview non è più in anteprima ed è rilasciato al pubblico. Di conseguenza, la sezione su Whiteboard Preview è stata rinominata "Whiteboard per PC, Surface Hub e altre piattaforme”. Le procedure per l'accesso, l’esportazione e l’eliminazione dei dati sono state rimosse da questa sezione e sostituite con un collegamento all'articolo di supporto di Whiteboard.|
|08/11/2018 | [Workplace Analytics](#workplace-analytics) |Aggiunta di istruzioni dettagliate alla sezione Eliminazione sulla rimozione di un interessato da Workplace Analytics e sulla rimozione di informazioni su un interessato da un report di Workplace Analytics.|
|12/11/2018| Tutto| Correzione di segnalibri e collegamenti con errore ad argomenti esterni.|
|1/9/2019|[StaffHub](#staffhub)|Nella sezione Eliminazione è stata aggiornata la descrizione di quello che succede quando un account utente viene eliminato definitivamente.|
|08/05/2019| [Publisher](#publisher)|Sono stati aggiunti dei contenuti sulla risposta alle richieste dell'interessato per Publisher.|
|11/7/2019| [MyAnalytics](#myanalytics)|La possibilità da parte di un amministratore di usare lo strumento caso DSR nel Centro sicurezza e conformità di Office 365 per esportare i dati di analisi di dati è stata rimossa perché tutti gli utenti possono ora visualizzare i dati nell'App Analytics. |
||||
