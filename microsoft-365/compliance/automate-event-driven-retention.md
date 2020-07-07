---
title: Automatizzare la conservazione basata su eventi
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
search.appverid:
- MOE150
- MET150
description: Questo argomento illustra come configurare i flussi di processo aziendale in modo da automatizzare la conservazione attraverso gli eventi usando l'API REST di Microsoft 365.
ms.openlocfilehash: 15d2dd8417cf0a22b8db63f64c0bbb288e74880c
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046064"
---
# <a name="automate-event-based-retention"></a>Automatizzare la conservazione basata su eventi

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.

To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.

To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.

Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.

## <a name="about-event-based-retention"></a>Informazioni sulla conservazione basata su eventi

An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.

For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:

- **The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.

- **The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.

The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).

## <a name="set-up-event-based-retention"></a>Configurare la conservazione basata su eventi

Questa sezione descrive le operazioni da eseguire prima della conservazione del contenuto.

### <a name="identify-roles"></a>Identificare i ruoli

Identificare i diversi ruoli in un'organizzazione che eseguono attività di Gestione record e che sarebbero i responsabili della conservazione efficace ed efficiente dei documenti aziendali.

  | Utente | Ruolo |
  | - | - |
  | Amministratore | Crea tipi di eventi di conservazione, etichette di conservazione e repository dei record in SharePoint |
  | Responsabile della gestione dei record                                  | Fornisce linee guida su criteri di conservazione e pianificazioni della conservazione, oltre a informazioni dettagliate sulla conformità   |
  | Amministratore di sistema (azienda)                          | Configura e gestisce i sistemi esterni in modo da utilizzare Microsoft 365                       |
  | Information Worker                               | Gestisce il ciclo di vita del proprio processo aziendale (risorse umane, finanza, IT ecc.)                 |

### <a name="set-up-the-security--compliance-center"></a>Configurare il Centro sicurezza e conformità
  
1. L'amministratore di conformità crea un tipo di evento, &ndash;ad esempio Licenziamento dipendente, Scadenza contratto oppure Fine produzione. Vedere il processo dettagliato in [Conservazione basata su eventi](event-driven-retention.md).
    
2. L'amministratore di conformità crea un'etichetta di conservazione in base a un evento e la associa a un tipo di evento.
    
    Ci sono quattro tipi di trigger per le etichette di conservazione:
            
    1. Data creazione
                
    2. Data ultima modifica
                
    3. Data etichetta (quando il contenuto è stato etichettato)
                
    4. Basata su eventi
    
3. L'amministratore di conformità pubblica l'etichetta.

### <a name="set-up-sharepoint"></a>Configurare SharePoint
   
Per creare un repository dei record, l'amministratore di conformità deve:

1. Creare un sito di SharePoint.

2. Eseguire una delle operazioni seguenti:
        
   - Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
          
   - Configura un set di documenti in SharePoint. Per ulteriori informazioni, vedere [Introduzione ai set di documenti](https://support.microsoft.com/it-IT/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).
      
3. Assegna un ID risorsa a ogni set di documenti dei dipendenti. Un ID risorsa è il nome o codice di un prodotto usato dall'organizzazione, ad esempio il Numero dipendente può essere un ID risorsa. Assegnando l'ID risorsa alla cartella, ogni elemento nella cartella eredita automaticamente lo stesso ID risorsa. Di conseguenza, il periodo di conservazione di tutti gli elementi nella cartella sarà generato dallo stesso evento.

## <a name="ways-to-trigger-event-based-retention"></a>Modi per attivare la conservazione basata su eventi

Esistono due modi in cui è possibile attivare la conservazione basata su eventi:

- **Uso dell'interfaccia di amministrazione** Si tratta di un processo che può essere sfruttato per conservare meno contenuto alla volta o per ridurre la frequenza di attivazione della conservazione e renderla, ad esempio, mensile o annuale. Per ulteriori informazioni su questo processo, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md). Tuttavia, questo metodo di attivazione della conservazione può richiedere tempo e causare errori, e diminuire così la scalabilità. Di conseguenza, una soluzione automatica e semplice per attivare la conservazione può aumentare la sicurezza e la conformità dei dati.

- **Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.

Sono disponibili due opzioni per usare l'API REST:

- **Microsoft Flow o delle applicazioni simili** possono essere usate per attivare automaticamente la ricorrenza di un evento. Microsoft Flow è un agente di orchestrazione per la connessione ad altri sistemi. L'uso di Microsoft Flow non richiede una soluzione personalizzata.

- **PowerShell o un client HTTP per le chiamate all'API REST**: usare PowerShell (versione 6 o successive) per chiamare l'API REST di Microsoft 365 per creare eventi. 

Un'API Rest è un endpoint di servizio che supporta set di operazioni HTTP (metodi), che forniscono l'accesso alle risorse del servizio per la creazione, il ripristino, l’aggiornamento e l’eliminazione. Per altre informazioni, vedere [Componenti di una richiesta/risposta dell'API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In questo caso, con l'API REST di Microsoft 365, è possibile creare e recuperare gli eventi usando le operazioni (metodi) POST e GET.

## <a name="example-scenarios"></a>Scenari di esempio

Considerare i seguenti scenari.

### <a name="scenario-1-employees-leaving-the-organization"></a>Scenario 1: Dipendenti che lasciano l'organizzazione 

Un’organizzazione crea e archivia numerosi documenti relativi all’impiego di ogni singolo dipendente. Questi documenti sono gestiti e conservati durante il periodo di lavoro di ogni dipendente. Tuttavia, quando il dipendente lascia l'organizzazione o quando termina il periodo di lavoro, l'organizzazione è tenuta a rispettare i requisiti legali e aziendali e a mantenere i documenti di tale dipendente per un lasso di tempo concordato.

Quindi, se più dipendenti lasciassero l'organizzazione ogni giorno, l'organizzazione dovrebbe attivare quotidianamente l'intervallo di conservazione per centinaia o migliaia di documenti.

Oltre a tutto questo, occorre calcolare il periodo di conservazione per ciascun dipendente in base alla formula Data licenziamento dipendente + numero di giorni, mesi o anni in base al tipo di record del dipendente. Ad esempio, il periodo di conservazione dei documenti relativi alla retribuzione del lavoratore e ai benefit dipendenti potrebbe differire.

Il diagramma di seguito illustra come possano essere presenti più etichette associate a un singolo evento. In questo caso, tutti i file con l’etichetta Assicurazione contro gli infortuni sul lavoro e tutti i file con l’etichetta Benefit dipendenti sono associati a un singolo evento, ossia il licenziamento del dipendente dall'organizzazione. Ognuno dei vari file ha intervalli di conservazione diversi. Quindi, quando un dipendente lascia l'organizzazione, i file raggruppati sotto ogni etichetta hanno un periodo di conservazione diverso. L'attivazione di tutti questi intervalli di conservazione, diversi per ogni tipo di file o etichetta e per ogni dipendente, è un'operazione molto complessa. Ancora di più lo è eseguire questa operazione per più dipendenti.

![Diagramma del tipo di evento, evento ed etichette](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

Di conseguenza, un processo automatizzato per attivare i diversi intervalli di conservazione per più dipendenti consente di risparmiare tempo, è privo di errori ed estremamente efficiente.

**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**

![Diagramma di ruoli e azioni per lo scenario in cui il dipendente lascia l'organizzazione](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - L'amministratore crea le cartelle del dipendente nel set di documenti, ad esempio Angela Barbariol, Luca Udinesi.

  - L'amministratore aggiunge i documenti dei dipendenti, ad esempio Benefit, Paghe, Assicurazione contro gli infortuni sul lavoro, a ogni cartella dipendente.

  - L'amministratore assegna l'ID risorsa a ogni cartella dipendente. 

  - L'amministratore SCC accede al Centro sicurezza e conformità.

  - L'amministratore SCC crea tipi di eventi correlati al dipendente, come "Licenziamento del dipendente", "Assunzione del dipendente".

  - L'amministratore SCC crea l'etichetta "Conservazione dipendente".

  - L'etichetta "Conservazione dipendente" viene pubblicata e applicata manualmente o automaticamente ai documenti dei dipendenti in SharePoint.

  - Un sistema di gestione delle risorse umane come Workday può eseguire periodicamente Microsoft Flow per gestire i documenti dei dipendenti.

  - Se un dipendente ha lasciato l'organizzazione, Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del dipendente specifico.

#### <a name="using-microsoft-flow"></a>Uso di Microsoft Flow

Passaggio 1: Creare un flusso per creare un evento usando le API REST di Microsoft 365

![Usare Flow per creare un evento](../media/automate-event-driven-retention-flow-1.png)

![Usare Flow per chiamare l'API REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>Creare un evento

Codice di esempio per chiamare l'API REST

- **Metodo**: POST
- **URL**: https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
- **Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml
- **Corpo**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- **Autenticazione**: di base
- **Nome utente**: "Complianceuser"
- **Password**: "Compliancepassword"


##### <a name="available-parameters"></a>Parametri disponibili


|Parametri|Descrizione|Note|
|--- |--- |--- |
|<d:Name></d:Name>|Immettere un nome univoco per l'evento,|Non può contenere spazi e i seguenti caratteri: % * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|Immettere il nome del tipo di evento (o Guid)|Example: “Employee termination”. Event type has to be associated with a retention label.|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|Immettere "ComplianceAssetId:" + ID dipendente|Esempio: "ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|Data e ora evento|Formato: aaaa-MM-ggTHH:mm:ssZ, esempio: 2018-12-01T00:00:00Z
|

##### <a name="response-codes"></a>Codici di risposta

| Codice di risposta | Descrizione       |
| ----------------- | --------------------- |
| 302               | Reindirizzare              |
| 201               | Creato               |
| 403               | Autorizzazione non riuscita  |
| 401               | Autenticazione non riuscita |

##### <a name="get-events-based-on-time-range"></a>Ricevere gli eventi in base all'intervallo di tempo

- **Metodo**: ottieni

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml

- **Autenticazione**: di base

- **Nome utente**: "Complianceuser"

- **Password**: "Compliancepassword"


##### <a name="response-codes"></a>Codici di risposta

| Codice di risposta | Descrizione                   |
| ----------------- | --------------------------------- |
| 200               | OK, un elenco di eventi in atom+ xml |
| 404               | Non trovato                         |
| 302               | Reindirizzare                          |
| 401               | Autorizzazione non riuscita              |
| 403               | Autenticazione non riuscita             |

##### <a name="get-an-event-by-id"></a>Ottenere un evento in base all'ID

- **Metodo**: ottieni

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml

- **Autenticazione**: di base

- **Nome utente**: "Complianceuser"

- **Password**: "Compliancepassword"



##### <a name="response-codes"></a>Codici di risposta

| Codice di risposta | Descrizione                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, il corpo della risposta contiene l'evento in atom+xml |
| 404               | Non trovato                                            |
| 302               | Reindirizzare                                             |
| 401               | Autorizzazione non riuscita                                 |
| 403               | Autenticazione non riuscita                                |

##### <a name="get-an-event-by-name"></a>Ottenere un evento in base al nome

- **Metodo**: ottieni

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml

- **Autenticazione**: di base

- **Nome utente**: "Complianceuser"

- **Password**: "Compliancepassword"


##### <a name="response-codes"></a>Codici di risposta

| Codice di risposta | Descrizione                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | OK, il corpo della risposta contiene l'evento in atom+xml |
| 404               | Non trovato                                            |
| 302               | Reindirizzare                                             |
| 401               | Autorizzazione non riuscita                                 |
| 403               | Autenticazione non riuscita                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a>Uso di PowerShell (versione 6 o successiva) o un client HTTP

Passaggio 1: Connettersi a PowerShell.

Passaggio 2: Eseguire lo script seguente.

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a>Verificare il risultato in entrambe le opzioni

Passaggio 1: Passare al Centro sicurezza e conformità.

Passaggio 2: Scegliere **Eventi** in **Governance delle informazioni**.

Passaggio 3: Verificare di aver creato l'evento.

È possibile usare le opzioni precedenti per automatizzare la conservazione basata sugli eventi anche per gli scenari seguenti.

### <a name="scenario-2-contracts-expiring"></a>Scenario 2: Contratti in scadenza

Un'organizzazione può avere più record per un singolo contratto con clienti, fornitori e partner. Questi documenti possono trovarsi in una raccolta documenti come SharePoint. Il termine di un contratto determina l'inizio del periodo di conservazione dei documenti associati al contratto. Ad esempio, tutti i record relativi ai contratti devono essere conservati per cinque anni dalla data di scadenza del contratto. L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto.

Un sistema di Customer Relationship Management (CRM) può interagire con Microsoft 365 e attivare la conservazione dei documenti contrattuali.

**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**

![Diagramma di ruoli e attività per scenari di scadenza contratto](../media/automate-event-driven-retention-contract-expiration.png)

  - L'amministratore crea una raccolta di SharePoint con varie cartelle per ogni tipo di contratto.

  - L'amministratore aggiunge i documenti contrattuali, ad esempio Contratti di licenza e Contratti di sviluppo, a ogni cartella di contratto.

  - L'amministratore assegna l'ID risorsa a ogni cartella di contratto.

  - L'amministratore SCC accede al Centro sicurezza e conformità.

  - L'amministratore SCC crea tipi di eventi correlati al contratto, come "Creazione contratto" o "Scadenza contratto".

  - L'amministratore SCC crea l'etichetta "Scadenza contratto".

  - L'etichetta "Scadenza contratto" viene pubblicata e applicata manualmente o automaticamente ai documenti contrattuali in SharePoint.

  - Il sistema di gestione dei contratti può eseguire periodicamente Microsoft Flow o un'applicazione simile per gestire i documenti contrattuali.

  - Se un contratto scade, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del contratto specifico.

### <a name="scenario-3-end-of-product-manufacturing"></a>Scenario 3: Fine produzione

A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.

Un sistema ERP (Enterprise Resource Planning) può utilizzare Microsoft 365 e Microsoft Flow per attivare la conservazione.

**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**

![Diagramma di ruoli e attività per uno scenario di ciclo di vita del prodotto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - L'amministratore crea delle cartelle di prodotto nel set di documenti, ad esempio Prodotto 1, Prodotto 2, ecc.

  - L'amministratore aggiunge i documenti del prodotto, ad esempio Specifiche di produzione, Prezzi del prodotto, Licenze del prodotto a ogni cartella.

  - L'amministratore assegna l'ID risorsa a ogni cartella di prodotto.

  - L'amministratore SCC accede al Centro sicurezza e conformità.

  - L'amministratore SCC crea tipi di eventi correlati al prodotto, come "Inizio produzione", "Fine produzione".

  - L'amministratore SCC crea l'etichetta "Fine produzione".

  - L'etichetta "Fine produzione" viene pubblicata e applicata manualmente o automaticamente ai documenti del prodotto in SharePoint.

  - I sistemi ERP possono eseguire periodicamente Microsoft Flow o applicazioni simili per gestire i documenti del prodotto.

  - Se un prodotto esce fuori produzione, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del prodotto specifico.

## <a name="appendix"></a>Appendice

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>Uso dei risultati della risposta Redirect 302 per chiamare l'API REST

1. Chiamare un evento di conservazione POST usando l'URL dell'API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (sono necessarie le autorizzazioni di Amministratore globale)

2. Controllare il codice di risposta. Se è 302, ottenere l'URL reindirizzato dalla proprietà Posizione dell'intestazione della risposta.

3. Chiamare nuovamente l'evento di conservazione POST usando l'URL reindirizzato.

## <a name="credits"></a>Riconoscimenti

Questo argomento è stato rivisto da:

Antonio Maio<br/>MVP App e servizi di Microsoft Office<br/> Antonio.Maio@Protiviti.com
