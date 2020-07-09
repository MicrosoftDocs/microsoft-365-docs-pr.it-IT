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
ms.openlocfilehash: a0e0025d23bda36d8b9e6315cb932e58d4237a5c
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068125"
---
# <a name="overview-of-event-driven-retention"></a>Panoramica della conservazione basata su eventi

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
Esempi per l'uso della conservazione basata su eventi:
  
- **Dipendenti che lasciano l'organizzazione** Si supponga che i record dei dipendenti debbano essere conservati per 10 anni dal momento in cui lasciano l'organizzazione. Trascorsi 10 anni, tutti i documenti relativi all'assunzione, alle prestazioni e alla cessazione del rapporto lavorativo di quel dipendente devono essere eliminati. L'evento che attiva il periodo di conservazione di 10 anni è l'uscita del dipendente dall'organizzazione. 
    
- **Scadenza del contratto** Si supponga che tutti i record relativi ai contratti debbano essere conservati per cinque anni dalla data di scadenza del contratto. L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- Anche le etichette basate su eventi classificano il contenuto come record. Per altre informazioni, vedere [Informazioni sui record](records.md).
    
- Un documento che è stato dichiarato come record, ma il cui trigger di evento non si è ancora verificato, viene conservato a tempo indeterminato (i record non possono essere eliminati definitivamente) finché un evento non attiva il periodo di conservazione di quel documento.
    
- Le etichette di conservazione basate su eventi di solito attivano una revisione per l'eliminazione alla fine del periodo di conservazione, in modo che un responsabile dei record possa rivedere ed eliminare manualmente il contenuto. Per altre informazioni, vedere [Eliminazione dei contenuti](disposition.md).
    
Un'etichetta di conservazione basata su un evento ha le stesse funzionalità di qualsiasi etichetta di conservazione in Microsoft 365. Per altre informazioni, vedere [Informazioni sulle etichette di conservazione](labels.md).

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

Per creare e configurare l'etichetta di conservazione, usare le istruzioni in [Creare e configurare etichette di conservazione](create-retention-labels.md#create-and-configure-retention-labels) e, quando si attiva la conservazione, scegliere l'opzione per conservare o eliminare il contenuto in base a un evento. Questo significa che le impostazioni di conservazione non verranno attivate fino al passaggio 5, quando si creerà un evento nella pagina **Eventi**. 
  
La conservazione basata su eventi viene in genere usata per il contenuto classificato come record, quindi questo è il momento giusto per verificare se occorre selezionare anche l'opzione per contrassegnare il contenuto come record.
  
La conservazione basata su eventi richiede impostazioni di conservazione che:
  
- Conservino il contenuto.
    
- Eliminino il contenuto automaticamente o attivino una revisione per l'eliminazione alla fine del periodo di conservazione.
    
![Opzione per basare un'etichetta su un evento](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a>Passaggio 2: scegliere un tipo di evento per l'etichetta

Nelle impostazioni dell’etichetta, dopo avere selezionato l’opzione per basare l’etichetta su **un evento**, sarà presente l’opzione **Scegliere un tipo di evento**. Un tipo di evento è semplicemente una descrizione generale di un evento a cui si vuole associare un’etichetta.
  
Ad esempio, se si crea un tipo di evento denominato Durata del prodotto, verranno create le etichette di conservazione basate su eventi con i nomi che descrivono i tipi di contenuti a cui si desidera applicare le etichette, ad esempio "File di sviluppo prodotto" o "Record decisione prodotto aziendale".

Selezionare uno dei tipi di evento predefiniti oppure crearne uno personalizzato e selezionarlo.

Dopo aver scelto un tipo di evento e salvato l'etichetta di conservazione, il tipo di evento non può essere modificato.
  
![Opzioni per creare o scegliere un tipo di evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Passaggio 3: pubblicare o applicare automaticamente le etichette di conservazione basate su eventi

Come per qualsiasi etichetta di conservazione, è necessario [pubblicare o applicare automaticamente](create-retention-labels.md) un'etichetta basata su eventi per poterla applicare a documenti o messaggi di posta elettronica.

> [!NOTE]
> Se si seleziona un'etichetta di conservazione basata su eventi dalla scheda **Gestione record** > **Piano file** o dalla scheda **Governance dei dati** > **Etichette**, il pulsante **Applica automaticamente un'etichetta** non sarà disponibile.
> 
> Anziché questo pulsante, usare l'opzione **Applica automaticamente un'etichetta** sopra l'elenco di etichette o criteri da una delle posizioni seguenti:
> - Scheda **Gestione record** > **Criteri etichetta**
> - Scheda **Governance dati** > **Etichette** o scheda **Criteri etichette**


![Opzioni per pubblicare o applicare automaticamente un'etichetta di conservazione](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>Passaggio 4: immettere un ID risorsa

Dopo avere applicato al contenuto un'etichetta basata su eventi, è possibile immettere un ID risorsa per ogni elemento. Ad esempio, l'organizzazione può usare:
  
- Codici prodotto da utilizzare per conservare i contenuti solo per un prodotto specifico.
    
- Codici prodotto da utilizzare per conservare i contenuti solo per un progetto specifico.
    
- ID dipendente da utilizzare per conservare i contenuti solo per una persona specifica.
    
L'ID risorsa è semplicemente un'ulteriore proprietà di un documento disponibile in SharePoint e OneDrive. L’organizzazione potrebbe usare già altre proprietà del documento e altri ID per classificare il contenuto. In questo caso, è possibile usare anche quelle proprietà e quei valori quando si crea l'evento (vedere il Passaggio 6 di seguito). L'aspetto importante è che si deve usare una certa combinazione *proprietà:valore* nelle proprietà del documento per associare l'elemento a un tipo di evento.
  
![Casella di testo per immettere un ID risorsa](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Passaggio 5: creare un evento

Quando si verifica un'istanza particolare di quel tipo di evento, ad esempio quando un prodotto raggiunge la fine del ciclo di vita, accedere alla pagina **Gestione record** > **Eventi** nel Centro conformità di Microsoft 365 e creare un evento. Per attivare un evento occorre crearlo.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Passaggio 6: scegliere lo stesso tipo di evento utilizzato per l'etichetta nel Passaggio 2

Quando si crea l'evento, scegliere lo stesso tipo di evento usato per l'etichetta di conservazione nel passaggio 2, ad esempio Durata del prodotto. Il periodo di conservazione verrà attivato solo per il contenuto a cui sono applicate le etichette di conservazione di quel tipo di evento.
  
![Opzione in Impostazioni evento per scegliere un tipo di evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Passaggio 7: immettere parole chiave o un ID risorsa

A questo punto si limiterà l’ambito del contenuto, specificando gli ID risorsa per il contenuto di SharePoint e OneDrive o le parole chiave per il contenuto di Exchange. Per gli ID risorsa, la conservazione verrà applicata solo al contenuto con la coppia *proprietà:valore* specificata. Se non si immette un ID risorsa, a tutti i contenuti con etichette di quel tipo di evento verrà applicata la stessa data di conservazione.

Ad esempio: se si usa la proprietà ID risorsa, immettere `ComplianceAssetID:<value>` nella casella relativa agli ID risorsa mostrati sotto.
  
È possibile che l'organizzazione abbia applicato altre proprietà e altri ID ai documenti correlati al tipo di evento. Ad esempio, se è necessario individuare i record di un prodotto specifico, l'ID può essere una combinazione della proprietà personalizzata ProductID e del valore "XYZ" In questo caso, si immetterà `ProductID:XYZ` nella casella per gli ID risorsa mostrata nell'immagine seguente.
  
Per gli elementi di Exchange includere parole chiave. È possibile usare una query con gli operatori di ricerca come AND, OR e NOT. Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).
  
Infine, scegliere la data in cui si è verificato l'evento; questa data viene utilizzata come inizio del periodo di conservazione. Dopo aver creato un evento, la data dell'evento viene sincronizzata con tutto i contenuti che hanno un'etichetta di conservazione per il tipo di evento, l'ID risorsa e le parole chiave. Come per qualsiasi etichetta di conservazione, la sincronizzazione può richiedere fino a sette giorni.
  
![Pagina Impostazioni evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

Dopo la creazione di un evento, le impostazioni di conservazione vengono applicate al contenuto già etichettato e indicizzato. Se l'etichetta di conservazione viene aggiunta al nuovo contenuto dopo la creazione dell'evento, è necessario creare un nuovo evento con gli stessi dettagli.

L'eliminazione di un evento non annulla le impostazioni di conservazione attualmente in vigore per il contenuto già etichettato. Per fare questo, creare un nuovo evento con gli stessi dettagli, ma lasciare vuota la data. 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Usare Ricerca contenuto per trovare tutto il contenuto con un'etichetta o un ID risorsa specifico

Dopo che le etichette di conservazione sono state assegnate al contenuto, è possibile usare la funzionalità di ricerca di contenuto per trovare tutti i contenuti classificati con un'etichetta di conservazione specifica o che contengono un ID risorsa specifico:
  
- Per trovare tutto il contenuto con un'etichetta di conservazione specifica, selezionare la condizione **Etichetta di conformità**, quindi immettere il nome completo dell'etichetta o parte di esso e usare un carattere jolly. 
    
- Per trovare tutto il contenuto con un ID risorsa specifico, inserire la proprietà **ComplianceAssetID** e un valore, usando il formato `ComplianceAssetID:<value>`. 
    
Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Autorizzazioni

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
Per ulteriori informazioni, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatizzare gli eventi con PowerShell

Il Centro conformità Microsoft 365 consente di creare eventi manualmente e non supporta l'attivazione automatica di un evento quando questo avviene. Tuttavia, è possibile usare un'API REST per attivare automaticamente gli eventi. Per altre informazioni, vedere [Automatizzare la conservazione basata su eventi](automate-event-driven-retention.md).

È anche possibile usare uno script di PowerShell per automatizzare la conservazione basata su eventi dalle applicazioni aziendali. Cmdlet di PowerShell disponibili per la conservazione basata su eventi:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

