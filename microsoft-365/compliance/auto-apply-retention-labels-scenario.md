---
title: Usare le etichette di conservazione per gestire il ciclo di vita dei documenti archiviati in SharePoint
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Come usare le etichette di conservazione per gestire il ciclo di vita dei documenti in SharePoint tramite l’uso dei metadati, per classificare il contenuto, applicare automaticamente le etichette e usare la conservazione basata su eventi per avviare il periodo di conservazione.
ms.openlocfilehash: 250bf182c26616a3a2f9253471469d2cecbd8d2b
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560669"
---
# <a name="use-retention-labels-to-manage-the-lifecycle-of-documents-stored-in-sharepoint"></a>Usare le etichette di conservazione per gestire il ciclo di vita dei documenti archiviati in SharePoint

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Questo articolo descrive come gestire il ciclo di vita dei documenti archiviati in SharePoint attraverso l’utilizzo delle etichette di conservazione applicate in automatico e la conservazione basata su eventi.

La funzionalità di applicazione automatica utilizza i metadati di SharePoint per la classificazione dei documenti. L’esempio esposto in questo articolo si riferisce ai documenti relativi al prodotto, ma gli stessi concetti risultano validi anche per altri scenari. Per esempio, nel settore petrolifero e del gas naturale, è possibile utilizzarlo per gestire il ciclo di vita dei documenti relativi alle risorse fisiche come le piattaforme petrolifere e le registrazioni di log geofisici oppure le licenze di produzione. Nel settore dei servizi finanziari, è possibile gestire i documenti relativi a conti bancari, mutui o contratti di assicurazione. Nel settore pubblico, è possibile gestire i permessi di costruzione o i moduli fiscali.

In questo articolo, l'analisi partirà dall'architettura delle informazioni e dalla definizione delle etichette di conservazione. Poi classificheremo i documenti con l’applicazione automatica delle etichette. E infine genereremo gli eventi che avviano il periodo di conservazione.

## <a name="information-architecture"></a>Architettura delle informazioni

Il nostro scenario corrisponde a quello di un'azienda manifatturiera che usa SharePoint per archiviare tutti i documenti relativi ai prodotti che sviluppa. Tali documenti includono specifiche di prodotto, contratti con fornitori e manuali utenti. Quando un documento viene archiviato in SharePoint mediante i criteri di gestione dei contenuti aziendali, si definiscono i metadati specifici del documento, che vengono utilizzati per classificarlo. In termini di metadati, ogni documento ha le seguenti proprietà:

- **Tipo di documento** (come specifica di prodotto, contratto o manuale utente)

- **Nome del prodotto**

- **Stato** (bozza o finale)

Per tutti i documenti, i metadati formano una tipologia di contenuto di base denominata *Documento di produzione*.

![Tabella dei metadati della documentazione del prodotto](../media/SPRetention1.png)

> [!NOTE]
> In una fase successiva di questo scenario, i criteri di conservazione useranno le proprietà **Tipo di documento** e **Stato** per classificare e applicare in modo automatico le etichette di conservazione.

È possibile avere varie tipologie di contenuti che rappresentano differenti tipi di documenti, ma ora si concentri l'attenzione sulla documentazione del prodotto.

In questo scenario, si usa il Servizio metadati gestiti e l'Archivio termini per creare un set di termini per *Tipo di documento* e un altro set per *Nome del prodotto*. Per ogni set di termini, si crea un termine per ciascun valore. Nell'Archivio termini per la propria organizzazione di SharePoint, apparirà in modo simile a questo:

![Set di termini di esempio per la documentazione del prodotto nell'Archivio termini](../media/SPRetention2.png)

Le *tipologie di contenuto* possono essere create e pubblicate con l'[Hub tipo di contenuto](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b). È anche possibile creare e pubblicare un tipo di contenuto utilizzando strumenti di provisioning del sito come l'apposito [framework PnP](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework) o lo [schema JSON di progettazione del sito](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type).

Ciascun prodotto dispone di un sito di SharePoint dedicato, contenente una raccolta documenti con le corrette tipologie di contenuto abilitate. Tutti i documenti vengono archiviati in questa raccolta.

![Raccolta dei documenti per la documentazione del prodotto.](../media/SPRetention3.png)

> [!NOTE]
> Invece di avere un sito di SharePoint per ogni prodotto, l'azienda manifatturiera di questo scenario potrebbe usare un Microsoft Teams per ogni prodotto per supportare la collaborazione tra i membri del team, ad esempio con una chat permanente, e usare la scheda **File** per la gestione dei documenti all'interno di Teams. In questo articolo, il focus è diretto esclusivamente ai documenti, quindi si userà soltanto un sito.

Ecco visualizzata la raccolta di documenti per il prodotto Spinning Widget:

![Raccolta dei documenti del prodotto Spinning Widget](../media/SPRetention4.png)

Ora che è stata definita l'architettura delle informazioni di base per la gestione dei documenti, si passerà all'esame della strategia di conservazione ed eliminazione dei documenti che usano i metadati e alla loro classificazione.

## <a name="retention-and-disposition"></a>Conservazione ed eliminazione

I criteri di conformità e governance dei dati dell'azienda manifatturiera stabiliscono le modalità di mantenimento ed eliminazione di tali dati. I documenti relativi al prodotto devono essere conservati per tutto il tempo della produzione e per un determinato periodo aggiuntivo. Il periodo aggiuntivo in questione cambia a seconda che si tratti di specifiche di prodotto, contratti o manuali utenti. La tabella seguente indica i requisiti di conservazione ed eliminazione:

| **Tipo di documento**          | **Conservazione**                          | **Eliminazione**                              |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| Specifiche del prodotto      | 5 anni dopo l'interruzione della produzione  | Elimina                                       |
| Contratti di prodotto          | 10 anni dopo l'interruzione della produzione | Revisione                                       |
| Manuali per gli utenti                | 5 anni dopo l'interruzione della produzione  | Elimina                                       |
| Tutti gli altri tipi di documenti | Non conservare attivamente  | Eliminare i documenti vecchi di 3 anni <br /><br /> Un documento si considera vecchio di 3 anni se non ha subito modifiche durante gli ultimi 3 anni. |
|||

Utilizziamo il Centro conformità Microsoft 365 per creare le seguenti [etichette di conservazione](retention.md#retention-labels):

  - Specifica di prodotto

  - Contratto di prodotto

  - Manuale utente

In questo articolo, si illustreranno le modalità di creazione e applicazione automatica dell'etichetta di conservazione Specifica di prodotto. Per implementare lo scenario completo, procedere anche alla creazione e applicazione automatica delle etichette di conservazione per le altre due tipologie di documento.

### <a name="settings-for-the-product-specification-retention-label"></a>Impostazioni per l'etichetta di conservazione Specifica di prodotto

Ecco il [piano di archiviazione](file-plan-manager.md) per l'etichetta di conservazione Specifica di prodotto:

- **Nome:** Specifica di prodotto

- **Descrizione per gli amministratori:** conservare fino a 5 anni dopo l’arresto della produzione; eliminazione automatica; conservazione basata su eventi, con tipo di evento *Cessazione del prodotto*.

- **Descrizione per gli utenti:** mantenere per 5 anni dopo l’arresto della produzione.

- **Azione di conservazione:** conservare ed eliminare.

- **Durata di conservazione:** 5 anni (1.825 giorni).

- **Etichetta record**: configurare l’etichetta di conservazione per classificare un contenuto come [*record*](records.md). (I documenti classificati come *record* non possono essere modificati o eliminati dagli utenti.)

- **Descrittori del piano di archiviazione:** (per semplificare lo scenario, non viene inserito alcun descrittore di archiviazione).

La schermata seguente mostra le impostazioni quando si crea l'etichetta di conservazione Specifica di prodotto nel Centro conformità Microsoft 365. È possibile creare la tipologia di evento *Cessazione del prodotto* al momento della creazione dell'etichetta di conservazione. Vedere la procedura nella sezione seguente.

![Impostazioni di conservazione per l'etichetta Specifica di prodotto](../media/SPRetention5.png)

> [!NOTE]
> Per evitare un'attesa di 5 anni per l'eliminazione dei documenti, impostare la durata di conservazione su ***1 giorno*** se si ricrea questo scenario in un ambiente di test.

### <a name="create-an-event-type-when-you-create-a-retention-label"></a>Creare un tipo di evento quando si crea un'etichetta di conservazione

1. Dall'elenco a discesa **Conserva o elimina il contenuto in base a**, selezionare **un evento**.

2. Selezionare **Scegli un tipo di evento**.
    
    ![Creare un nuovo tipo di evento per la finestra di dialogo Specifica di prodotto](../media/SPRetention6.png)

3. Nella pagina **Scegli un tipo di evento**, selezionare **Scegli un tipo di evento**, quindi fare clic su **Crea nuovi tipi di evento**.

4. Creare un tipo di evento denominato ***Cessazione del prodotto***, inserire una descrizione e selezionare **Fine**.

5. Tornare alla pagina **Scegli il tipo di evento**, selezionare il tipo di evento appena creato **Cessazione del prodotto**, poi selezionare **Aggiungi**.

   Ecco come appaiono le impostazioni per l'etichetta di conservazione Specifica di prodotto. 

   ![Impostazioni per la nuova etichetta Specifica di prodotto](../media/SPRetention7.png)

6. Selezionare **Crea l'etichetta**. 
> [!TIP]
> Per informazioni più dettagliate sui vari passaggi, consultare [Creare un'etichetta il cui periodo di conservazione è basato su un evento](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event).

Ora si passerà all'analisi dell'applicazione automatica dell'etichetta di conservazione al contenuto delle specifiche di prodotto.

## <a name="auto-apply-retention-labels-to-classify-content"></a>Applicare automaticamente le etichette di conservazione per classificare il contenuto

Ora si procederà con l'[applicazione automatica](apply-retention-labels-automatically.md) delle etichette di conservazione create, usando Keyword Query Language (KQL). KQL è il linguaggio che viene utilizzato per la creazione di query di ricerca. Con KQL è possibile compiere ricerche in base a parole chiave o proprietà gestite. Per maggiori informazioni, vedere le [informazioni di riferimento sulla sintassi KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

In pratica, si vuole dire a Microsoft 365 che “applichi l'etichetta di conservazione *Specifica di prodotto* a tutti i documenti che hanno ***Finale*** come **Stato** e ***Specifica di prodotto*** come **Tipo di documento**”. Si ricordi che **Stato** e **Tipo di documento** sono le colonne del sito definite per il tipo di contenuto Documentazione di prodotto nella sezione [Architettura delle informazioni](#information-architecture). Per compiere questa operazione, è necessario configurare lo schema di ricerca.

Quando SharePoint indicizza i contenuti, per ogni colonna del sito genera automaticamente delle proprietà sottoposte a ricerca per indicizzazione. In questo scenario, l'interesse si concentra sulle proprietà **Tipo di documento** e **Stato**. Affinché la ricerca crei delle proprietà sottoposte a ricerca per indicizzazione, all'interno della raccolta risulterà necessaria la presenza di documenti che costituiscano il tipo di contenuto corretto e che le colonne del sito siano compilate.

Nell'interfaccia di amministrazione di SharePoint, aprire le configurazioni di ricerca e selezionare **Gestisci schema di ricerca** per visualizzare e configurare le proprietà sottoposte a ricerca per indicizzazione.

![Proprietà sottoposte a ricerca per indicizzazione nello schema di ricerca](../media/SPRetention8.png)

Se si digita ***stato*** nella casella **Proprietà sottoposte a ricerca per indicizzazione** e si seleziona la freccia verde, si visualizza un risultato simile a questo:

![La proprietà sottoposta a ricerca per indicizzazione ows_Status](../media/SPRetention9.png)

La proprietà **ows\_\_Status**, notare il doppio carattere di sottolineatura, è l'oggetto di interesse. Questa esegue il mapping alla proprietà **Stato** del tipo di contenuto Documento di produzione.

Ora, se si digita ***ows\_doc*** e si seleziona la freccia verde, si visualizza qualcosa di simile a questo:

![La proprietà sottoposta a ricerca per indicizzazione ows_Doc_Type](../media/SPRetention10.png)

La proprietà **ows\_Doc\_x0020\_Type** è la seconda proprietà di interesse in questo scenario. Questa esegue il mapping alla proprietà **Tipo di documento** della tipologia di contenuto Documento di produzione.

> [!TIP]
> Per identificare il nome di una proprietà sottoposta a ricerca per indicizzazione per questo scenario, passare alla raccolta che contiene i documenti di produzione. Quindi accedere alle relative impostazioni. Per **Colonne**, selezionare il nome della colonna, ad esempio, **Stato** o **Tipo di documento**, per aprire la pagina della colonna del sito. Il parametro *Campo* nell'URL della pagina contiene il nome del campo. Tale nome del campo, con prefisso "ows_", è il nome della proprietà sottoposta a ricerca per indicizzazione. Ad esempio, l'URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` corrisponde alla proprietà sottoposta a ricerca per indicizzazione di *ows\_\_Status*.

Se le proprietà sottoposte a ricerca per indicizzazione non sono visualizzate nella sezione Gestisci schema di ricerca all'interno dell'interfaccia di amministrazione di SharePoint:

- Forse i documenti non sono stati indicizzati. È possibile forzare una reindicizzazione della raccolta andando su **Impostazioni della raccolta documenti**  > **Impostazioni avanzate**.

- Se la raccolta documenti si trova in un sito moderno, verificare che l'amministratore di SharePoint sia anche un amministratore della raccolta siti.

Per ulteriori informazioni sulle proprietà sottoposte a ricerca per indicizzazione e sulle proprietà gestite, vedere [Proprietà gestite create automaticamente in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint).

### <a name="map-crawled-properties-to-pre-defined-managed-properties"></a>Mappare le proprietà sottoposte a ricerca per indicizzazione alle proprietà gestite predefinite

KQL non può fare uso delle proprietà sottoposte a ricerca per indicizzazione nelle query di ricerca. A tal fine, deve utilizzare una proprietà gestita. In un tipico scenario di ricerca, si crea dunque una proprietà gestita e la si mappa alla proprietà sottoposta a ricerca per indicizzazione di cui si ha bisogno. Tuttavia, per l'applicazione automatica delle etichette di conservazione, è possibile solo specificare le proprietà gestite predefinite in KQL e non quelle personalizzate. Nel sistema esiste un set di proprietà gestite predefinite per le stringhe da *RefinableString00* a *RefinableString199* che è possibile usare. Per un elenco completo, vedere [Proprietà gestite non utilizzate predefinite](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties). Tali proprietà gestite predefinite vengono generalmente utilizzate per la definizione dei criteri di affinamento della ricerca.

Affinché la query KQL applichi automaticamente l'etichetta di conservazione corretta al contenuto del documento di prodotto, è necessario eseguire il mapping delle proprietà sottoposte a ricerca per indicizzazione **ows\_Doc\_x0020\_Type* e *ows\_\_Status** a due proprietà gestite per affinamento ricerca. Nell'ambiente di test per questo scenario, si evita l'uso di **RefinableString00** e **RefinableString01**. Questa condotta è stata determinata osservando le **Proprietà gestite** nella sezione **Gestisci schema di ricerca** all'interno dell'interfaccia di amministrazione di SharePoint.

![Proprietà gestite nello schema di ricerca](../media/SPRetention12.png)

Notare che la colonna **Proprietà sottoposte a ricerca per indicizzazione** mostrata nella schermata precedente è vuota.

Per eseguire il mapping della proprietà sottoposta a ricerca per indicizzazione **ows\_Doc\_x0020\_Type**, procedere come segue:

1. Nella casella del filtro **Proprietà gestita**, digitare ***RefinableString00*** e selezionare la freccia verde.

2. Nell'elenco dei risultati, selezionare il link **RefinableString00**, poi scorrere verso il basso fino alla sezione **Mapping alle proprietà sottoposte a ricerca per indicizzazione**.  

3. Selezionare **Aggiungi mapping** e poi digitare ***ows\_Doc\_x0020\_Type*** nella casella **Cerca un nome di proprietà sottoposta a ricerca per indicizzazione** all'interno della finestra **Selezione proprietà sottoposte a ricerca per indicizzazione**. Selezionare **Trova**.  

4. Nell'elenco dei risultati, selezionare **ows\_Doc\_x0020\_Type** e poi **OK**.

   Nella sezione **Proprietà sottoposte a ricerca per indicizzazione**, si dovrebbe visualizzare qualcosa di simile a quanto mostrato in questa schermata:

   ![Selezionare Aggiungi mapping nella sezione Proprietà sottoposte a ricerca per indicizzazione](../media/SPRetention13.png)

5. Per salvare il mapping, scorrere fino alla parte inferiore della pagina e selezionare **OK**.

Ripetere questi passaggi per eseguire il mapping di **RefinableString01** e **ows\_\_Status**.

A questo punto, si dovrebbe avere il mapping delle due proprietà gestite alle due proprietà sottoposte a ricerca per indicizzazione:

![Proprietà gestite visualizzate come mappate alle proprietà sottoposte a ricerca per indicizzazione](../media/SPRetention14.png)

Verificare che sia tutto configurato correttamente eseguendo una Ricerca contenuti organizzazione. Aprire un browser e andare su *https://\<your_tenant>sharepoint.com/search*. Nella casella di ricerca, digitare ***RefinableString00:"Specifica di prodotto"*** e premere Invio. Questa ricerca dovrebbero mostrare tutti i documenti che contengono tale **Specifica di prodotto** come ***Tipo di documento***.

A questo punto, digitare **RefinableString00:"Specifica di prodotto" AND RefinableString01:Final** nella casella di ricerca, quindi premere Invio. In questo modo, dovrebbero essere mostrati tutti i documenti che contengono tale **Specifica di prodotto** come ***Tipo di documento*** e che hanno ***Finale*** come **Stato**.

### <a name="create-auto-apply-label-policies"></a>Creare i criteri per applicare automaticamente le etichette

Dopo aver verificato il funzionamento della query KQL, si potranno creare i criteri di etichetta che fanno uso di una query KQL per l'applicazione automatica dell'etichetta di conservazione della Specifica di prodotto ai documenti appropriati.

1. Nel [Centro conformità](https://compliance.microsoft.com/homepage) passare a **Gestione dei record** > **Criteri etichetta** > **Applica automaticamente un'etichetta**.

   ![Selezionare “Applica automaticamente un'etichetta” nella pagina Etichette](../media/SPRetention16.png)

2. Nella pagina della procedura guidata **Scegliere un'etichetta da applicare automaticamente**, selezionare**Scegliere un'etichetta da applicare automaticamente**.

3. Nell'elenco di etichette selezionare **Specifica di prodotto**. Selezionare **Aggiungi** e **Avanti**.

4. Selezionare **Applicare l'etichetta al contenuto che include parole o frasi specifiche o proprietà**, poi selezionare**Avanti**.

   ![Selezionare Applicare l'etichetta al contenuto che include parole o frasi specifiche o proprietà](../media/SPRetention17.png)

   Nel passaggio successivo, si dovrà fornire la stessa query di ricerca KQL testata nella sezione precedente. Tale query mostra come risultato tutti i documenti Specifica di prodotto che hanno *Finale* come Stato. Quando utilizziamo la medesima query nei criteri di etichetta, l'etichetta di conservazione Specifica di prodotto sarà applicata automaticamente a tutti i documenti corrispondenti.

5. Nella casella **Editor di query con parole chiave**, digitare ***RefinableString00:"Specifica di prodotto" AND RefinableString01:Final***, poi selezionare **Avanti**.

   ![Specificare la query nella casella Editor di query con parole chiave](../media/SPRetention19.png)

6. Inserire un nome per il criterio di etichetta, ad esempio, ***Applicare automaticamente l'etichetta Specifica di prodotto***, e una descrizione facoltativa, poi selezionare **Avanti**.

7. Nella pagina della procedura guidata **Scegli posizioni**, selezionare le posizioni dei contenuti a cui si desidera applicare il criterio. Per questo scenario, il criterio verrà applicato solo alle posizioni di SharePoint, poiché tutti i documenti di produzione sono archiviati nelle raccolte documenti di SharePoint. Selezionare **Consenti la scelta di posizioni specifiche**, quindi disattiva l'interruttore di stato per la **posta elettronica di Exchange**, gli **account di OneDrive** e i **gruppi di Microsoft 365**. Verificare che lo stato per i siti di SharePoint sia attivato. 

    ![Scegliere siti specifici per l'applicazione automatica delle etichette](../media/SPRetentionSPlocations.png)

   > [!TIP]
   > Anziché applicare il criterio a tutti i siti di SharePoint, è possibile selezionare **Selezione siti** e aggiungere gli URL per i siti di SharePoint specifici.

8. Selezionare **Avanti** per mostrare la pagina **Controllare le impostazioni**.

    ![Impostazioni per l'applicazione automatica dell'etichetta](../media/SPRetention18.png)

9. Per creare il criterio di etichetta, selezionare **Applica automaticamente**.

   >[!NOTE]
   >Sono necessari fino a 7 giorni per applicare automaticamente l'etichetta Specifica di prodotto a tutti i documenti che corrispondono alla query di ricerca KQL.

### <a name="verify-that-the-retention-label-was-automatically-applied"></a>Verificare che l'etichetta di conservazione sia stata applicata automaticamente

Dopo 7 giorni, usare [Esplora attività](data-classification-activity-explorer.md) nel Centro conformità per verificare che il criterio di etichetta creato abbia applicato automaticamente le etichette di conservazione ai documenti di prodotto.

Verificare anche le proprietà dei documenti all'interno della Raccolta documenti. Nel riquadro delle informazioni, si può notare che l'etichetta di conservazione è applicata a un documento selezionato.

![Verificare che l'etichetta sia stata applicata osservando le proprietà del documento nella Raccolta documenti](../media/SPRetention21.png)

Siccome le etichette di conservazione erano state applicate automaticamente ai documenti, tali documenti risultano protetti dall’eliminazione poiché l'etichetta di conservazione è stata configurata in modo che i documenti venissero dichiarati come *record*. Come esempio di questa protezione, viene mostrato il seguente messaggio di errore quando si tenta di eliminare uno di questi documenti:

![Un messaggio di errore indica che non è possibile eliminare i documenti perché l'etichetta dichiara costituiscono dei record.](../media/SPRetention22.png)

## <a name="generate-the-event-that-triggers-the-retention-period"></a>Generare l'evento che attiva il periodo di conservazione

Ora che le etichette di conservazione sono state applicate, il focus passa all'evento che indicherà la fine della produzione di un particolare prodotto. Questo evento attiva l'inizio del periodo di conservazione definito nelle etichette di conservazione. Ad esempio, per i documenti delle specifiche di prodotto, il periodo di conservazione quinquennale inizia quando viene attivato l'evento "Fine della produzione".

È possibile creare manualmente l'evento nel Centro conformità Microsoft 365 passando a **Gestione dei record** > **Eventi**. Scegliere il tipo di evento, impostare gli ID risorsa corretti e immettere una data per l'evento. Per ulteriori informazioni, vedere [Avviare la conservazione al verificarsi di un evento](event-driven-retention.md).

Ma per questo scenario l'evento verrà generato automaticamente da un sistema di produzione esterno. Il sistema è un semplice elenco di SharePoint che indica se un prodotto è in produzione. L’evento sarà attivato da un flusso [Power Automate](https://docs.microsoft.com/flow/getting-started) che è associato all'elenco. In uno scenario reale, è possibile utilizzare vari sistemi per generare l'evento, ad esempio un sistema HR o CRM. Power Automate include numerose interazioni pronte all'uso e blocchi predefiniti per i carichi di lavoro di Microsoft 365, ad esempio Microsoft Exchange, SharePoint, Teams e Dynamics 365, oltre ad app di terze parti, come Twitter, Box, Salesforce e Workdays. Questa caratteristica consente di integrare facilmente Power Automate all’interno di vari sistemi. Per ulteriori informazioni, vedere [Automatizzare la conservazione basata su eventi](automate-event-driven-retention.md).

La schermata seguente mostra l'elenco di SharePoint che verrà utilizzato per attivare l'evento:

![L’elenco che attiverà l'evento di conservazione](../media/SPRetention23.png)

Attualmente, vi sono due prodotti in produzione come indicato dal valore ***Sì*** nella colonna **In produzione**. Se in questa colonna il valore corrispondente a un prodotto è impostato su ***No***, il flusso associato all'elenco genererà automaticamente l'evento. L’evento attiva l'inizio del periodo di conservazione per l'etichetta di conservazione che era stata applicata automaticamente ai documenti di prodotto corrispondenti.

Per questo scenario, si utilizza il seguente flusso per attivare l'evento:

![Configurazione del flusso che attiverà l'evento](../media/SPRetention24.png)

Per creare questo flusso, iniziare da un connettore di SharePoint e selezionare il trigger **Quando viene creato o modificato un elemento**. Specificare l'indirizzo del sito e il nome dell'elenco. Quindi aggiungere una condizione associata al valore ***No*** della colonna **In produzione** (o al valore *Falso* nella scheda condizione). A questo punto, aggiungere un'azione basata sul modello HTTP predefinito. Per configurare l'azione HTTP, usare i valori della sezione seguente. È possibile copiare i valori delle proprietà **URI** e **Corpo** dalla sezione seguente e incollarli nel modello.

- **Metodo**: POST
- **URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml
- **Corpo**:
    
    ```HTML
    <?xml version='1.0' encoding='utf-8' standalone='yes'>
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata' xmlns='https://www.w3.org/2005/Atom'>
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent'>
    <updated>9/9/2017 10:50:00 PM</updated>
    <content type='application/xml'>
    <m:properties>
    <d:Name>Cessation Production @{triggerBody()?['Product_x0020_Name']?['Value']}</d:Name>
    <d:EventType>Product Cessation&lt;</d:EventType>
    <d:SharePointAssetIdQuery>ProductName:&quot;@{triggerBody()?['Product_x0020_Name']?['Value']}<d:SharePointAssetIdQuery>
    <d:EventDateTime>@{formatDateTime(utcNow(),'yyyy-MM-dd')}</d:EventDateTime>
    </m:properties>
    </content&gt>
    </entry>
    ```

L’elenco descrive i parametri della proprietà **Corpo** relativi all'azione da configurarsi per questo scenario:

- **Name**: questo parametro specifica il nome dell'evento che verrà creato all'interno del Centro conformità Microsoft 365. Per questo scenario, il nome è "Cessazione produzione *xxx*", dove *xxx* è il valore della proprietà gestita **ProductName** precedentemente creata.
- **EventType**: il valore di questo parametro corrisponde al tipo di evento a cui si applicherà l'evento creato. Questo tipo di evento è stato definito al momento della creazione dell'etichetta di conservazione. Per questo scenario, il tipo di evento è "Cessazione del prodotto".
- **SharePointAssetIdQuery**: questo parametro definisce l'ID risorsa per l'evento. La conservazione basata su eventi richiede che ogni documento abbia un identificatore univoco. È possibile usare gli ID risorsa per identificare i documenti a cui si applica un particolare evento oppure, come nel caso di questo scenario, una colonna di metadati, il **Nome del prodotto**. A tale scopo, è necessario creare una nuova proprietà gestita **ProductName** che può essere usata nella query KQL. (In alternativa, è possibile usare **RefinableString00** anziché creare una nuova proprietà gestita). È necessario anche eseguire il mapping di questa nuova proprietà gestita alla proprietà sottoposta a ricerca per indicizzazione **ows_Product_x0020_Name**. Ecco una schermata di tale proprietà gestita.

    ![Proprietà gestita di conservazione](../media/SPRetention25.png)

- **EventDateTime**: questo parametro definisce la data in cui si verifica l'evento. Utilizzare il formato data corrente:<br/><br/>*formatDateTime(utcNow(),'yyyy-MM-dd'*)

### <a name="putting-it-all-together"></a>Riassumendo

Adesso è stata creata e applicata automaticamente l'etichetta di conservazione e il flusso è stato configurato e creato. Se il valore nella colonna **In produzione** per il prodotto Spinning Widget nell’elenco Prodotti viene modificato da ***Sì*** a ***No***, il flusso viene attivato per generare l’evento. Per vedere tale evento nel Centro conformità, passare a **Gestione record** > **Eventi**.

![L’evento che è stato attivato dal flusso viene visualizzato nella pagina Eventi nel Centro conformità.](../media/SPRetention28.png)

Selezionare l'evento per visualizzarne i dettagli nella pagina a comparsa. Notare che anche se l'evento è stato creato, il relativo stato indica che non è stato elaborato alcun sito o documento di SharePoint.

![Dettagli evento](../media/SPRetention29.png)

Dopo un periodo di tempo, lo stato dell’evento indica l'elaborazione di un sito e di un documento di SharePoint.  

![I dettagli dell'evento mostrano che i documenti sono stati elaborati.](../media/SPRetention31.png)
 
Questo indica che sarà stato avviato il periodo di conservazione per l'etichetta applicata al documento del prodotto Spinning Widget, sulla base della data dell'evento *Cessazione produzione Spinning Widget*. Ipotizzando che lo scenario sia stato implementato nell'ambiente di test configurando un periodo di conservazione pari a un giorno, è possibile passare alla raccolta dei propri documenti di prodotto alcuni giorni dopo la creazione dell'evento e verificare l'effettiva eliminazione di tale documento, in seguito al processo di eliminazione in SharePoint.

### <a name="more-about-asset-ids"></a>Altre informazioni sugli ID risorsa

Come descritto nell’articolo [Avviare la conservazione al verificarsi di un evento](event-driven-retention.md), è importante comprendere la relazione tra le tipologie di evento, le etichette di conservazione, gli eventi e gli ID risorsa. L'ID risorsa è semplicemente una proprietà di un documento in SharePoint e OneDrive. Consente di identificare quei documenti per cui l'evento darà avvio al periodo di conservazione. Come impostazione predefinita, SharePoint dispone di una proprietà **ID risorsa** utilizzabile per la conservazione basata su eventi:

![La proprietà ID risorsa visualizzata su una pagina dei dettagli delle proprietà del documento.](../media/SPRetention26.png)

Come mostra la schermata seguente, la proprietà gestita ID risorsa è denominata **ComplianceAssetId**.

![Proprietà gestita ComplianceAssetId](../media/SPRetention27.png)

Invece di usare la proprietà **ID risorsa predefinita** come mostrato in questo scenario, è possibile utilizzare qualsiasi altra proprietà. Tuttavia, è importante tenere presente che se per un evento non si specificano le parole chiave o un ID risorsa, l'evento attiverà il periodo di conservazione per tutto il contenuto avente un'etichetta corrispondente a quel tipo di evento.

### <a name="using-advanced-search-in-sharepoint"></a>Usare la ricerca avanzata in SharePoint

Nella schermata precedente, si può vedere anche che esiste un'altra proprietà gestita relativa alle etichette di conservazione denominata **ComplianceTag** che è mappata a una proprietà sottoposta a ricerca per indicizzazione. Anche la proprietà gestita **ComplianceAssetId** è mappata a una proprietà sottoposta a ricerca per indicizzazione. Questo significa che è possibile usare queste proprietà gestite nella ricerca avanzata per recuperare tutti i documenti contrassegnati con un'etichetta di conservazione.

## <a name="credits"></a>Riconoscimenti

Questo scenario è stato realizzato da: 

Frederic Lapierre<br/>Principal Consultant presso Servizi Microsoft
