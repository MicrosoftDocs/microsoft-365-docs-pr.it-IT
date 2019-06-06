---
title: Richieste del soggetto dei dati per l'RGPD in Azure
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 7a294893d609747b5ab36c66319427608462b451
ms.sourcegitcommit: 6e2a54ec395eaef4c4658ca52322c3d0f184ca02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "34698338"
---
# <a name="azure-data-subject-requests-for-the-gdpr"></a>Richieste del soggetto dei dati per l'RGPD in Azure

## <a name="introduction-to-data-subject-requests-dsrs"></a>Introduzione alle richieste del soggetto dei dati (DSR)

Il [Regolamento generale sulla protezione dei dati (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione europea garantisce alle persone (denominate come *soggetti dei dati* nel regolamento) il diritto di gestire i dati personali raccolti da un datore di lavoro o da un'altra organizzazione o agenzia (definiti come *titolari del trattamento dei dati* o semplicemente *titolari*). I dati personali sono ampiamente descritti nel GDPR come dati che si riferiscono a una persona fisica identificata o identificabile. Il GDPR garantisce ai soggetti dei dati diritti specifici sui propri dati personali; tali diritti includono la possibilità di ottenere delle copie dei dati personali, richiedere di apportare delle modifiche ai dati, limitare il trattamento dei dati, eliminarli o riceverli in un formato elettronico affinché possano essere trasferiti a un altro titolare. Una richiesta formale di un soggetto dei dati rivolta a un titolare in merito a un'operazione da effettuare sui propri dati personali è denominata *Richiesta DSR* (Data Subject Rights, Diritti del soggetto dei dati) o DSR.

La guida descrive come utilizzare i prodotti, i servizi e gli strumenti di amministrazione Microsoft per aiutare i nostri clienti titolari del trattamento dei dati a individuare e gestire i dati personali per rispondere alle richieste DSR. In particolare, ciò include come identificare, accedere e usare i dati personali che risiedono nel cloud Microsoft. Di seguito è riportata una rapida panoramica dei processi descritti in questa guida:

- **Scoprire:** usare gli strumenti di ricerca e individuazione per trovare più facilmente i dati dei clienti che potrebbero essere oggetto di una richiesta dell'interessato. Dopo aver raccolto dei documenti potenzialmente reattivi, è possibile eseguire una o più delle azioni DSR descritte nella seguente procedura per rispondere alla richiesta. In alternativa, si può determinare che la richiesta non soddisfa le linee guida dell'organizzazione relative alla risposta alle richieste degli interessati.
- **Accedere:** recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, crearne una copia che può essere disponibile per l'interessato.
- **Rettificare:** apportare modifiche o implementare le azioni richieste sui dati personali, ove applicabile.
- **Limitare:** limitare il trattamento dei dati personali, tramite la rimozione delle licenze per vari servizi di Azure o disattivando i servizi desiderati ove possibile. È anche possibile rimuovere i dati dal cloud Microsoft e mantenerli in locale o in un'altra posizione.
- **Eliminare:** rimuovere in modo definitivo i dati personali che risiedono nel cloud Microsoft.
- **Esportare:** fornire all'interessato una copia elettronica dei dati personali in un formato leggibile in modo automatizzato.

Ogni sezione di questa guida illustra le procedure tecniche che un'organizzazione titolare del trattamento dei dati può adottare per rispondere a una richiesta DSR per i dati personali nel cloud Microsoft.

## <a name="terminology"></a>Terminologia

Di seguito vengono fornite le definizioni dei termini importanti nella presente guida.

- **Titolare:** la persona fisica o giuridica, l'autorità pubblica, l'agenzia o altro ente che, autonomamente o unitamente ad altri soggetti, determina gli obiettivi e i mezzi del trattamento dei dati personali; laddove gli obiettivi e i mezzi di tale trattamento sono determinati da una normativa europea o di uno specifico Stato membro dell'UE, il titolare del trattamento dei dati o i criteri specifici per la sua designazione potrebbero essere forniti da tale normativa europea o di uno specifico Stato membro dell'UE.
- **Dati personali e interessato:** qualsiasi informazione relativa a una persona fisica identificata o identificabile (“interessato”); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, tramite dati specifici come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica.
- **Responsabile:** una persona fisica o giuridica, un'autorità pubblica o altro ente che si occupa del trattamento dei dati personali per conto del titolare.
- **Dati dei clienti:** tutti i dati, compresi tutti i file di testo, audio o immagini e il software, che vengono forniti a Microsoft da, o per conto di, un cliente tramite l'uso del servizio aziendale. I dati dei clienti includono (1) informazioni che consentono l'identificazione personale degli utenti finali (ad esempio, nomi utente e informazioni di contatto in Azure Active Directory) e contenuti per i clienti che un cliente stesso carica o crea in servizi specifici (ad esempio, contenuti per i clienti in un account di archiviazione di Azure, contenuti per i clienti in un database SQL di Azure o un'immagine della macchina virtuale di un cliente in Macchine virtuali di Azure).
- **Log generati dal sistema:** log e dati relativi generati da Microsoft che consentono a Microsoft di fornire servizi aziendali agli utenti. I log generati dal sistema contengono dati principalmente presentati con l'uso di pseudonimi come identificatori univoci (in genere, un numero generato dal sistema con cui non è possibile identificare direttamente un soggetto, ma che viene usato per fornire i servizi aziendali agli utenti). I log generati dal sistema possono anche contenere informazioni personali sugli utenti finali, come un nome utente.

## <a name="how-to-use-this-guide"></a>Come usare questa guida

Questa guida è costituita da due parti:

- **Parte 1: rispondere alle richieste dei soggetti dei dati per i dati dei clienti** La Parte 1 di questa guida illustra come accedere, rettificare, eliminare ed esportare i dati dalle applicazioni in cui sono presenti dati creati dall'utente. Questa sezione descrive in modo dettagliato come gestire le richieste DSR rispetto ai contenuti per i clienti e alle informazioni personali degli utenti finali.
- **Parte 2: rispondere alle richieste degli interessati per i log generati dal sistema** Quando si usano i servizi aziendali Microsoft, Microsoft genera alcune informazioni, note come log generati dal sistema, per fornire il servizio. La Parte 2 di questa guida illustra come accedere, eliminare ed esportare tali informazioni per Azure.

## <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a>Informazioni sulle richieste DSR per Azure Active Directory e account del servizio Microsoft

Se si prendono in considerazione i servizi forniti ai clienti aziendali, l'esecuzione di DSR deve essere sempre chiara nell'ambito dei contesto di un tenant di Azure Active Directory (AAD) specifico. In particolare, le richieste DSR vengono sempre eseguite all'interno di un detarminato tenant di AAD. Se un utente fa parte di più tenant, è importante sottolineare che una determinata richiesta DSR viene eseguita *solo* nel contesto del tenant specifico nel quale è stata ricevuta la richiesta. Questo è un aspetto fondamentale da comprendere perché significa che l'esecuzione di una richiesta DSR da parte di un cliente aziendale **non** avrà effetto sui dati di un cliente aziendale adiacente.

Lo stesso vale anche per gli account del servizio Microsoft (MSA) nell'ambito dei servizi forniti da un cliente aziendale: l'esecuzione di una richiesta DSR rispetto a un account MSA *associato a un tenant di AAD* sarà relativa **solo** ai dati all'interno del tenant. Inoltre, quando si gestiscono account MSA all'interno di un tenant, è importante comprendere quanto descritto di seguito:

- Se un utente MSA crea una sottoscrizione di Azure, l'abbonamento verrà gestito come se fosse un tenant di AAD. Di conseguenza, le richieste DSR sono limitate all'interno del tenant come descritto in precedenza.
- Se si elimina una sottoscrizione di Azure creata con un account MSA, **non ci saranno effetti** sull'account MSA. Come accennato in precedenza, l'esecuzione di richieste DSR nell'ambito della sottoscrizione di Azure è limitata all'ambito del tenant stesso.

Le richieste DSR rispetto a un account MSA, **al di fuori di un determinato tenant**, vengono eseguite tramite il Consumer Privacy Dashboard. Per ulteriori informazioni, fare riferimento alla guida per le richieste dei soggetti dei dati di Windows.

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: guida sulle richieste DSR per i dati dei clienti

### <a name="executing-dsrs-against-customer-data"></a>Esecuzione delle richieste DSR rispetto ai dati dei clienti

Microsoft consente di accedere, eliminare ed esportare alcuni dati dei clienti tramite il portale di Azure e anche direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per i servizi specifici (noti anche come *esperienze nel prodotto*). Informazioni su tali esperienze nel prodotto sono disponibili nella documentazione di riferimento per i relativi servizi.

>[!IMPORTANT]  
> I servizi che supportano le richieste DSR nel prodotto richiedono l'uso diretto dell'API (Application Programming Interface) o dell'interfaccia utente (UI) del servizio, descrivendo le operazioni CRUD (Create, Read, Update, Delete) applicabili. Pertanto, l'esecuzione di richieste DSR in un determinato servizio deve essere effettuata unitamente all'esecuzione di una richiesta DSR all'interno del portale di Azure per completare una richiesta per uno specifico soggetto dei dati. Per ulteriori dettagli, consultare la documentazione di riferimento per i relativi servizi.

### <a name="step-1-discover"></a>Passaggio 1: scoprire

Il primo passaggio per rispondere a un DSR consiste nell'individuare i dati personali oggetto della richiesta. Questo primo passaggio, che consente nell’individuare ed esaminare i dati personali in questione, consente di determinare se un DSR soddisfa i requisiti dell'organizzazione per rispettare o rifiutare un DSR. Ad esempio, dopo aver trovato ed esaminato i dati personali in questione, è possibile che la richiesta non soddisfi i requisiti dell'organizzazione, perché in questo modo può influire negativamente sui diritti e sulle libertà altrui.

Dopo avere trovato i dati, è quindi possibile eseguire un'azione specifica per soddisfare la richiesta da parte dell'interessato.

[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) è un servizio di gestione delle identità e una directory multi-tenant basata sul cloud Microsoft. È possibile individuare informazioni personali degli utenti finali, come profili utente di clienti e dipendenti e informazioni professionali sugli utenti contenenti dati personali nell'ambiente di [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) tramite il [portale di Azure](https://portal.azure.com/).

Ciò è particolarmente utile per trovare o modificare i dati personali per un utente specifico. È anche possibile aggiungere o modificare il profilo utente e le informazioni professionali. È necessario accedere con un account amministratore globale della directory.

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a>Come si individuano o si visualizzano le informazioni professionali e il profilo utente?

1. Accedere al [portale di Azure](https://portal.azure.com/) con un account amministratore globale della directory.

2. Selezionare **Tutti i servizi**, immettere **Utenti e gruppi** nella casella di testo, quindi selezionare **Invio**.

     ![Selezionare Tutti i servizi.](media/azure-dsr_image3.png)

3. Nel pannello **Utenti e gruppi**, selezionare **Utenti**.

     ![Selezionare Utenti.](media/azure-dsr_image9.png)

4. Nel pannello **Utenti e gruppi - Utenti** selezionare un utente dall'elenco e quindi, nel pannello relativo all'utente selezionato, fare clic su **Profilo** per visualizzare le informazioni del profilo utente che potrebbero contenere dati personali.

    ![Selezionare Profilo.](media/azure-dsr_image5.png)

5. Se è necessario aggiungere o modificare le informazioni del profilo utente, è possibile farlo e quindi selezionare **Salva** nella barra dei comandi.

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

### <a name="step-2-access"></a>Passaggio 2: accedere

Dopo aver individuato i dati dei clienti che contengono dati personali potenzialmente reattivi a una richiesta DSR, l'utente e l'organizzazione devono decidere quali dati fornire all'interessato. È possibile fornire una copia del documento effettivo, una versione appositamente riadattata o uno screenshot delle parti considerate adatte alla condivisione. Per ognuna di queste risposte a una richiesta di accesso, sarà necessario recuperare una copia del documento o altro elemento contenente i dati sensibili.

Quando si invia una copia all'interessato, potrebbe essere necessario rimuovere o redigere informazioni personali su altri interessati ed eventuali informazioni riservate.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft fornisce un portale ed esperienze nel prodotto per consentire all'amministratore tenant del cliente aziendale di gestire le richieste di accesso DSR alle informazioni personali relative a un utente finale. Le richieste di accesso DSR consentono l'accesso ai dati personali dell'utente, tra cui: (a) informazioni che consentono l'identificazione di un utente finale e (b) i log generati dal sistema.

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

### <a name="step-3-rectify"></a>Passaggio 3: rettificare

Se un interessato ha chiesto di rettificare i dati personali che fanno parte dei dati dell'organizzazione, l'utente e l'organizzazione dovranno determinare se la richiesta possa essere accettata. La rettifica dei dati potrebbe includere operazioni quali la modifica, la revisione o la rimozione di dati personali da un documento o altro. Il modo migliore per farlo per i dati di FastTrack e il supporto tecnico Microsoft viene fornito di seguito.

#### <a name="azure-active-directory"></a>Azure Active Directory

I clienti aziendali hanno la possibilità di gestire le richieste di rettifica DSR, comprese le funzionalità di modifica limitate in base alla natura di un determinato servizio Microsoft. In qualità di responsabile del trattamento dei dati, Microsoft non consente di correggere i log generati dal sistema poiché riflette attività effettive e costituisce un record cronologico degli eventi all'interno dei servizi Microsoft. Per quanto riguarda Azure Active Directory, esistono funzionalità di modifica limitate per rettificare le informazioni personali su un utente finale, come descritto più avanti.

##### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a>Azure Active Directory: rettificare/correggere dati personali incompleti o inesatti

È possibile correggere, aggiornare o eliminare informazioni personali sugli utenti finali, come profili utente di clienti e dipendenti e informazioni professionali degli utenti contenenti dati personali come nome utente, titolo professionale, indirizzo o numero di telefono, nell'ambiente [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) tramite il [portale di Azure](https://portal.azure.com/). È necessario accedere con un account amministratore globale per la directory.

###### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a>Come si correggono o si aggiornano le informazioni professionali e il profilo utente in Azure Active Directory?

1. Accedere al [portale di Azure](https://portal.azure.com/) con un account amministratore globale della directory.

2. Selezionare **Tutti i servizi**, immettere **Utenti e gruppi** nella casella di testo, quindi selezionare **Invio**.

    ![Selezionare Tutti i servizi.](media/azure-dsr_image3.png)

3. Nel pannello **Utenti e gruppi**, selezionare **Utenti**.

    ![Selezionare Utenti.](media/azure-dsr_image9.png)

4. Nel pannello **Utenti e gruppi - Utenti** selezionare un utente dall'elenco e quindi, nel pannello relativo all'utente selezionato, fare clic su **Profilo** per visualizzare le informazioni sul profilo utente da correggere o aggiornare.

    ![Selezionare Profilo.](media/azure-dsr_image5.png)

5. Correggere o aggiornare le informazioni e quindi selezionare **Salva** nella barra dei comandi.

6. Nel pannello dell'utente selezionato, fare clic su **Informazioni lavoro** per visualizzare le informazioni professionali dell'utente da correggere o aggiornare.

    ![Selezionare Informazioni lavoro.](media/azure-dsr_image4.png)

7. Correggere o aggiornare le informazioni professionali dell'utente e quindi selezionare **Salva** nella barra dei comandi.

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

### <a name="step-4-restrict"></a>Passaggio 4: limitare

Gli interessati potrebbero richiedere la limitazione del trattamento dei loro dati personali. Microsoft fornisce il portale di Azure e le interfacce di programmazione dell'applicazione (API) o le interfacce utente (UI) esistenti. Tali esperienze consentono all'amministratore tenant del cliente aziendale di gestire tali richieste DSR con una combinazione di esportazione dei dati ed eliminazione dei dati. Un cliente potrebbe (1) esportare una copia elettronica dei dati personali dell'utente, compresi (a) account, (b) log generati dal sistema e (c) log associati, per poi (2) eliminare l'account e i dati associati che si trovano all'interno dei sistemi Microsoft.

### <a name="step-5-delete"></a>Passaggio 5: eliminare

Il "diritto alla cancellazione" con la rimozione dei dati personali dai dati dei clienti di un'organizzazione è una delle principali protezioni nel GDPR. La rimozione dei dati personali include la rimozione di tutti i dati personali e dei log generati dal sistema, tranne le informazioni del log di controllo. Se un utente viene **eliminato temporaneamente** (vedere i dettagli di seguito), l'account viene disabilitato per 30 giorni. Se durante il periodo di 30 giorni non viene eseguita alcuna ulteriore azione, l'utente viene **eliminato definitivamente** (anche in questo caso, vedere i dettagli di seguito). Dopo l’**eliminazione definitiva**, l'account dell’utente, i dati personali e i log generati dal sistema vengono rimossi entro 30 giorni. Se un amministratore tenant effettua immediatamente un’**eliminazione definitiva**, l'account dell’utente, i dati personali e i log generati dal sistema vengono rimossi entro 30 giorni.

> [!IMPORTANT]
> È necessario essere un amministratore tenant per eliminare un utente dal tenant.

#### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a>Eliminare un utente e i dati associati tramite il portale di Azure

Dopo aver ricevuto una richiesta di eliminazione per un interessato, è possibile utilizzare il portale di Azure per eliminare un utente, le informazioni personali associate e i log generati dal sistema.

L'eliminazione di questi dati comporta anche l'eliminazione dell'utente dal tenant. Gli utenti vengono prima eliminati temporaneamente, ovvero l'account può essere recuperato da un amministratore tenant entro 30 giorni dall'eliminazione temporanea. Dopo 30 giorni, l'account viene eliminato dal tenant automaticamente e in modo definitivo. Prima dei 30 giorni, è possibile eliminare manualmente dal Cestino un utente eliminato temporaneamente.

Di seguito viene descritto il processo di eliminazione degli utenti dal tenant.

1. Accedere al portale di Azure e individuare l'utente.

2. Eliminare l'utente. In questa fase, l'account dell'utente viene inviato al Cestino. **A questo punto, l'utente è eliminato temporaneamente, ovvero l'account è disabilitato ma non rimosso da Azure Active Directory.**

3. Accedere all'elenco Utenti eliminati di recente ed eliminare definitivamente l'utente. **A questo punto, l'utente è eliminato in modo permanente, ovvero l'account è stato rimosso da Azure Active Directory.**

###### <a name="to-delete-a-user-from-an-azure-tenant"></a>Per eliminare un utente da un tenant di Azure

1. Aprire il portale di Azure, selezionare il pannello **Azure Active Directory** e quindi selezionare **Utenti**.

    Viene visualizzato il pannello **Utenti - Tutti gli utenti**.

    ![Individuare l'utente](media/azure-dsr_image8.png)

2. Selezionare la casella accanto all'utente da eliminare, selezionare **Elimina utente**, quindi **Sì** nella casella che richiede se si desidera eliminare l'utente.

    ![Gestione degli utenti](media/azure-dsr_image9.png)

3. Nella casella di riepilogo **Mostra** selezionare **Utenti eliminati di recente**.

    ![Visualizzare un profilo utente](media/azure-dsr_image10.png)

4. Selezionare di nuovo il nome utente, selezionare **Elimina permanentemente**, quindi seleziona **Sì** nell'apposita casella per confermare.

>[!IMPORTANT]  
>Tenere presente che, facendo clic su **Sì**, si elimina in modo permanente e irrevocabile l'utente e tutti i dati e i log generati dal sistema ad esso associati. Se si effettua questa operazione per errore, sarà necessario riaggiungere manualmente l'utente al tenant. I dati e i log generati dal sistema ad esso associati non sono recuperabili.

   ![Visualizzare le informazioni utente professionali](media/azure-dsr_image11.png)

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

## <a name="step-6-export"></a>Passaggio 6: esportare

Il "diritto alla portabilità dei dati" consente a un interessato di richiedere una copia dei propri dati personali in un formato elettronico (ovvero un "formato che sia interoperabile, leggibile, di uso comune e strutturato") che possa essere trasmessa a un altro titolare del trattamento dei dati. Azure supporta questa caratteristica, consentendo all'organizzazione di esportare i dati in formato JSON nativo nel contenitore di Archiviazione di Azure specificato.

>[!IMPORTANT]
>È necessario essere un amministratore tenant per esportare i dati di un utente dal tenant.

### <a name="azure-active-directory"></a>Azure Active Directory

Per quanto riguarda i dati del cliente, Microsoft fornisce un portale ed esperienze nel prodotto per consentire all'amministratore tenant del cliente aziendale di gestire le richieste di esportazione per le informazioni personali relative a un utente finale.

### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

## <a name="part-2-system-generated-logs"></a>Parte 2: log generati dal sistema

Microsoft consente anche di accedere, eliminare ed esportare determinati log generati dal sistema associati all'uso che un utente fa di Azure.

>[!IMPORTANT]
> La possibilità di limitare o rettificare i log generati dal sistema non è supportata. I log generati dal sistema costituiscono le azioni effettive condotte all'interno del cloud Microsoft e i dati di diagnostica; le modifiche a tali dati possono compromettere il record cronologico delle azioni, aumentando i rischi per la sicurezza e le truffe.

### <a name="executing-dsrs-against-system-generated-logs"></a>Esecuzione di DSR rispetto ai log generati dal sistema

Microsoft consente di accedere, eliminare ed esportare determinati log generati dal sistema tramite il portale di Azure e anche direttamente tramite le interfacce programmatiche o le interfacce utente dei servizi specifici. Ulteriori informazioni in merito vengono fornite nella documentazione di riferimento dei relativi servizi.

>[!IMPORTANT]  
> I servizi che supportano le richieste DSR nel prodotto richiedono l'uso diretto dell'API (Application Programming Interface) o dell'interfaccia utente (UI) del servizio. Pertanto, l'esecuzione di una richiesta DSR nel prodotto **deve essere effettuata unitamente all'esecuzione di una richiesta DSR all'interno del portale di Azure per completare una richiesta per uno specifico soggetto dei dati. Per ulteriori dettagli, consultare la documentazione di riferimento per i relativi servizi.**

### <a name="step-1-access"></a>Passaggio 1: accedere

L'amministratore tenant è l'unica persona all'interno dell'organizzazione che può accedere ai log generati dal sistema associati all'utilizzo di Azure di un particolare utente. I dati recuperati per una richiesta di accesso verranno forniti in un formato leggibile e in file che consentiranno all'utente di conoscere i servizi ai quali sono associati i dati. Come indicato in precedenza, i dati recuperati non includono quelli che potrebbero compromettere la sicurezza del servizio.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft fornisce un portale ed esperienze nel prodotto per consentire all'amministratore tenant del cliente aziendale di gestire le richieste di accesso alle informazioni personali relative a un utente finale. Le richieste di accesso consentiranno l'accesso ai dati personali dell'utente, tra cui: (a) informazioni che consentono l'identificazione di un utente finale e (b) i log generati dal servizio. Il processo è identico a quello descritto nella sezione di Azure Active Directory nella Parte 1, Passaggio 2: Accesso.

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

### <a name="step-2-delete"></a>Passaggio 2: eliminare

L'amministratore è l'unica persona all'interno dell'organizzazione che può eseguire una richiesta di eliminazione DSR per un particolare utente in un tenant di Azure.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft fornisce un portale ed esperienze nel prodotto che consentono all'amministratore tenant del cliente aziendale di gestire le richieste di eliminazione DSR. Tali richieste seguono la stessa procedura descritta nella sezione Eliminare un utente e i dati associati tramite il portale di Azure della Parte 1, Passaggio 5: eliminare.

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

### <a name="step-3-export"></a>Passaggio 3: esportare

L'amministratore tenant è l'unica persona all'interno dell'organizzazione che può accedere ai log generati dal sistema associati all'utilizzo di Azure di un particolare utente. I dati recuperati per una richiesta di esportazione verranno forniti in un formato leggibile e in file che consentiranno all'utente di conoscere i servizi ai quali sono associati i dati. Come indicato in precedenza, i dati recuperati non includono quelli che potrebbero compromettere la sicurezza o la stabilità del servizio.

#### <a name="export-system-generated-logs-using-the-azure-portal"></a>Esportare i log generati dal sistema tramite il portale di Azure

Dopo aver ricevuto una richiesta di esportazione per un interessato, è possibile utilizzare il portale di Azure per esportare i log generati dal sistema associati a un determinato utente.

Di seguito viene descritto il processo di esportazione dei dati dal tenant.

1. Accedere al portale di Azure e creare una richiesta di esportazione per conto dell'utente.
2. Esportare i dati e inviare il file all'utente.

###### <a name="to-export-a-users-info-from-an-azure-tenant"></a>Per esportare le informazioni di un utente da un tenant di Azure

1. Aprire il portale di Azure, selezionare **Tutti i servizi**, digitare *criteri* nel filtro e quindi selezionare **Criteri**.

     ![Filtro Tutti i servizi ](media/azure-dsr_image12.png)

2. Nel pannello **Criteri**, selezionare **Privacy dell'utente**, quindi **Gestisci richieste utente** e infine **Aggiungi richiesta di esportazione**.

    ![Aggiungi richiesta di esportazione ](media/azure-dsr_image13.png)

3. Completare la **richiesta di esportazione dei dati**:

    ![Nuova richiesta di esportazione dati](media/azure-dsr_image14.png)

- **Utente.** Digitare l'indirizzo e-mail dell'utente di Azure Active Directory che ha richiesto l'esportazione.
- **Sottoscrizione.** Selezionare l'account utilizzato per creare il report relativo all'utilizzo delle risorse e fatturare i servizi. Si tratta anche della posizione dell'account di archiviazione di Azure.
- **Account di archiviazione.** Selezionare il percorso di archiviazione di Azure (Blob). Per maggiori informazioni, vedere l’articolo [Introduzione ad archiviazione di Microsoft Azure - archiviazione Blob](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).
- **Contenitore.** Creare un nuovo contenitore (o selezionarne uno esistente) come posizione di archiviazione per i dati sulla privacy dell'utente esportati.

4. Selezionare **Crea**.

La richiesta di esportazione passa allo stato **In sospeso**. È possibile visualizzare lo stato del report nel pannello **Privacy degli utenti - Panoramica**.

>[!IMPORTANT]  
>Poiché i dati personali possono provenire da più sistemi, è possibile che il completamento del processo di esportazione richieda fino a un mese.

#### <a name="service-specific-interfaces"></a>Interfacce specifiche dei servizi

Microsoft consente di individuare i dati dei clienti direttamente tramite le API (Application Programming Interface) o le interfacce utente (UI) pre-esistenti per servizi specifici. Maggiori dettagli in merito sono disponibili nella documentazione di riferimento dei relativi servizi, in cui vengono descritte le operazioni CRUD (Create, Read, Update, Delete) applicabili.

### <a name="notify-about-exporting-or-deleting-issues"></a>Notificare problemi riguardanti l'esportazione o l'eliminazione.

Se si verificano problemi durante l'esportazione o l'eliminazione di dati dal portale di Azure, accedere al pannello **Guida e Supporto** del portale di Azure e inviare un nuovo ticket in **Gestione della sottoscrizione > Altre richieste di sicurezza e conformità > Pannello privacy e richieste GDPR**.

## <a name="learn-more"></a>Altre informazioni

- [Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)