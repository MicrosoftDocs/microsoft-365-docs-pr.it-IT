---
title: Panoramica della conservazione basata su eventi
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: In genere, nell’ambito di una soluzione di gestione dei record, è possibile configurare un’etichetta di conservazione per avviare il periodo di conservazione in base a un evento identificato.
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817805"
---
# <a name="overview-of-event-driven-retention"></a>Panoramica della conservazione basata su eventi

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them. But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
Ad esempio, è possibile usare etichette con conservazione basata su eventi per:
  
- **Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization. After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed. The event that triggers the 10-year retention period is the employee leaving the organization. 
    
- **Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- Labels based on events also usually classify content as a record. For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- Un documento che è stato dichiarato come record ma il cui trigger di evento non è ancora stato eseguito viene conservato a tempo indeterminato (i record non possono essere eliminati in modo permanente) finché un evento non attiva il periodo di conservazione di quel documento.
    
- Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content. For more information, see [Disposition of content](disposition.md).
    
Un’etichetta basata su un evento ha le stesse funzionalità di qualsiasi etichetta in Microsoft 365. Per altre informazioni, vedere [Informazioni sulle etichette di conservazione](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Informazioni sulla relazione tra tipi di eventi, etichette, eventi e ID delle risorse

Per usare correttamente la conservazione basata su eventi, è importante comprendere la relazione tra tipi di eventi, etichette di conservazione, eventi e ID delle risorse come illustrato nei diagrammi e nella spiegazione seguenti: 
  
![Diagramma del tipo di evento, etichette, eventi e ID delle risorse](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagramma del tipo di evento, etichette, eventi e ID delle risorse](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Vengono create etichette di conservazione per diversi tipi di contenuto, che vengono poi associate a un tipo di evento. Ad esempio, le etichette di conservazione per tipi diversi di file e record di prodotti sono associate a un tipo di evento denominato Durata del prodotto, in quanto tali record devono essere conservati per 10 anni dal momento in cui il prodotto raggiunge la fine del ciclo di vita.
    
2. Gli utenti (in genere i responsabili dei record) applicano queste etichette di conservazione al contenuto e (per i documenti di SharePoint e OneDrive) immettono un ID risorsa per ogni elemento. In questo esempio l'ID risorsa è un codice o nome del prodotto usato dall'organizzazione. In questo modo, ai record di ogni prodotto viene assegnata un'etichetta di conservazione e ogni record ha una proprietà che contiene un ID risorsa. Il diagramma rappresenta **tutto il contenuto** per tutti i record dei prodotti in un'organizzazione e ogni elemento contiene l'ID risorsa del prodotto a cui appartiene il record. 
    
3. Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:
    
  - Un ID risorsa (per i documenti di SharePoint e OneDrive)
    
  - Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.
    
  - The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.
    
4. Dopo aver creato un evento, la data dell'evento viene sincronizzata con tutto il contenuto che ha un'etichetta di conservazione di quel tipo di evento e che contiene la parola chiave o l'ID risorsa specificato. Come qualsiasi etichetta di conservazione, la sincronizzazione può richiedere fino a 7 giorni. Come mostrato nel diagramma precedente, questo evento ha attivato il periodo di conservazione di tutti gli elementi cerchiati in rosso. In altre parole, quando il prodotto raggiunge la fine del ciclo di vita, questo evento attiva il periodo di conservazione per i record del prodotto.
    
È importante tenere presente che se non si specificano parole chiave o un ID risorsa per un evento, l’evento attiverà il periodo di conservazione di **tutti i contenuti** con un'etichetta relativa a quel tipo di evento. Nel diagramma precedente, ad esempio, verrebbe avviata la conservazione di tutto il contenuto. Questo potrebbe non essere il risultato previsto. 
  
Tenere infine presente che ogni etichetta di conservazione ha le proprie impostazioni di conservazione. In questo esempio, queste specificano tutte 10 anni ma un evento può attivare etichette con diversi periodi di conservazione.
  
## <a name="how-to-set-up-event-driven-retention"></a>Come configurare la conservazione basata su eventi

Flusso di lavoro di alto livello per la conservazione basata su eventi:
  
![Diagramma del flusso di lavoro per la configurazione di conservazione basata su eventi](../media/event-based-retention-process.png)
  
> [!TIP]
> Vedere [Gestire il ciclo di vita dei documenti di SharePoint con le etichette di conservazione](auto-apply-retention-labels-scenario.md) per uno scenario dettagliato sull'uso delle proprietà gestite in SharePoint per applicare automaticamente etichette di conservazione e implementare la conservazione basata su eventi.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Passaggio 1: creare un'etichetta il cui periodo di conservazione sia basato su un evento

Nel pannello di navigazione sinistro del Centro conformità di Microsoft 365, selezionare **Governance delle informazioni** > **Etichette** > **Crea un’etichetta**. Se **Governance delle informazioni** non compare nel pannello di navigazione, scorrere in basso e selezionare **Mostra tutto**.
  
When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event. This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page. 
  
La conservazione basata su eventi viene generalmente usata per i contenuti classificati come record. Per questo motivo, quando si creano etichette di conservazione basate su un evento, in genere, si sceglie l'opzione **Usare l'etichetta per classificare il contenuto come "Record"**.
  
Inoltre, la conservazione basata su eventi richiede impostazioni di conservazione che:
  
- Conservino il contenuto.
    
- Eliminino il contenuto automaticamente o attivino una revisione per l'eliminazione alla fine del periodo di conservazione.
    
![Opzione per basare un'etichetta su un evento](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>Passaggio 2: scegliere un tipo di evento per l'etichetta

Nelle impostazioni dell’etichetta, dopo avere selezionato l’opzione per basare l’etichetta su **un evento**, sarà presente l’opzione **Scegliere un tipo di evento**. Un tipo di evento è semplicemente una descrizione generale di un evento a cui si vuole associare un’etichetta.
  
Ad esempio, se si crea un tipo di evento denominato Durata del prodotto, verranno create le etichette di conservazione basate su eventi con i nomi che descrivono i tipi di contenuti a cui si desidera applicare le etichette, ad esempio "File di sviluppo prodotto" o "Record decisione prodotto aziendale".
  
Una volta scelto un tipo di evento e creata l'etichetta di conservazione, il tipo di evento non può essere modificato.
  
![Opzioni per creare o scegliere un tipo di evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Passaggio 3: pubblicare o applicare automaticamente le etichette di conservazione basate su eventi

Come per qualsiasi etichetta di conservazione, è necessario [pubblicare o applicare automaticamente](create-retention-labels.md) un'etichetta basata su eventi perché venga applicata manualmente o automaticamente al contenuto.

> [!NOTE]
> Se si seleziona un'etichetta di conservazione basata su eventi dalla scheda **Gestione record** > **Piano file** o dalla scheda **Governance dei dati** > **Etichette**, il pulsante **Applica automaticamente un'etichetta** non sarà disponibile.
> 
> Anziché questo pulsante, usare l'opzione **Applica automaticamente un'etichetta** sopra l'elenco di etichette o criteri da una delle posizioni seguenti:
> - Scheda **Gestione record** > **Criteri etichetta**
> - Scheda **Governance dati** > **Etichette** o scheda **Criteri etichette**


![Opzioni per pubblicare o applicare automaticamente un'etichetta di conservazione](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>Passaggio 4: immettere un ID risorsa

After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:
  
- Codici prodotto da utilizzare per conservare i contenuti solo per un prodotto specifico.
    
- Codici prodotto da utilizzare per conservare i contenuti solo per un progetto specifico.
    
- ID dipendente da utilizzare per conservare i contenuti solo per una persona specifica.
    
Tenere presente che un ID risorsa è solo un'altra proprietà del documento in SharePoint e OneDrive for Business. L’organizzazione potrebbe usare già altre proprietà del documento e altri ID per classificare il contenuto. In questo caso, è possibile usare anche quelle proprietà e quei valori quando si crea l'evento (vedere il Passaggio 6 di seguito). L'aspetto importante è che l'organizzazione deve usare una certa combinazione proprietà:valore nelle proprietà del documento per associare l'elemento a un tipo di evento.
  
![Casella di testo per immettere un ID risorsa](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Passaggio 5: creare un evento

Quando si verifica un’istanza particolare di quel tipo di evento, ad esempio quando un prodotto raggiunge la fine del ciclo di vita, accedere alla pagina **Gestione record** > **Eventi** nel Centro conformità di Microsoft 365, e creare un evento. È necessario attivare manualmente un evento creandolo.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Passaggio 6: scegliere lo stesso tipo di evento utilizzato per l'etichetta nel Passaggio 2

Quando si crea l'evento, scegliere lo stesso tipo di evento usato per l'etichetta di conservazione nel passaggio 2, ad esempio Durata del prodotto. Il periodo di conservazione verrà attivato solo per il contenuto a cui sono applicate le etichette di conservazione di quel tipo di evento.
  
![Opzione in Impostazioni evento per scegliere un tipo di evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Passaggio 7: immettere parole chiave o un ID risorsa

A questo punto si limiterà l’ambito del contenuto, specificando gli ID risorsa per il contenuto di SharePoint e OneDrive o le parole chiave per il contenuto di Exchange. Per gli ID risorsa, la conservazione verrà applicata solo al contenuto con la coppia proprietà:valore specificata. Se non si immette un ID risorsa, a **tutti i contenuti** con etichette di quel tipo di evento verrà applicata la stessa data di conservazione. 
  
Tenere presente che un ID risorsa è solo un’altra proprietà del documento in SharePoint e OneDrive for Business. Se si usa la proprietà ID risorsa, immettere ComplianceAssetID: \<value\> nella casella relativa agli ID risorsa mostrati sotto.
  
Your organization might have applied other properties and IDs to the documents related to this event type. For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ". In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.
  
For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
Infine, scegliere la data in cui si è verificato l'evento; questa data viene utilizzata come inizio del periodo di conservazione. Dopo aver creato un evento, la data dell'evento viene sincronizzata con tutto i contenuti che hanno un'etichetta di conservazione per il tipo di evento, l'ID risorsa e le parole chiave. Come qualsiasi etichetta di conservazione, la sincronizzazione può richiedere fino a 7 giorni.
  
![Pagina Impostazioni evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Utilizzare Ricerca contenuto per trovare tutti i contenuti con un'etichetta o un ID risorsa specifici

Dopo che le etichette di conservazione sono state assegnate al contenuto, è possibile usare la funzionalità di ricerca di contenuto per trovare tutti i contenuti classificati con un'etichetta di conservazione specifica o che contengono un ID risorsa specifico.
  
Quando si crea una ricerca di contenuto:
  
- Per trovare tutto il contenuto con un'etichetta di conservazione specifica, selezionare la condizione **Tag di conformità**, quindi immettere il nome completo dell'etichetta o parte di esso e usare un carattere jolly. 
    
- Per trovare tutto il contenuto con un ID risorsa specifico, inserire la proprietà **ComplianceAssetID** e un valore, come ComplianceAssetID:\<value\>. 
    
Per ulteriori informazioni, vedere [Query delle parole chiave e condizioni di ricerca per ricerca contenuto](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Autorizzazioni

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
Per ulteriori informazioni, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatizzare gli eventi con PowerShell

In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs. However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).

È anche possibile usare uno script di PowerShell per automatizzare la conservazione basata su eventi dalle applicazioni aziendali. Cmdlet di PowerShell disponibili per la conservazione basata su eventi:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

