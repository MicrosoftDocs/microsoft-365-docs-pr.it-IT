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
description: Con le etichette di conservazione, si può basare un periodo di conservazione sul momento in cui si verifica un determinato tipo di evento. L'evento attiva l'inizio del periodo di conservazione e a tutto il contenuto in cui è applicata un'etichetta per quel tipo di evento vengono applicate le azioni di conservazione dell'etichetta. La conservazione basata su eventi viene usata generalmente nell'ambito di un processo di gestione dei record.
ms.openlocfilehash: da5e10735e8980199a829ac50d096052abe93d14
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074525"
---
# <a name="overview-of-event-driven-retention"></a>Panoramica della conservazione basata su eventi

Quando si conserva il contenuto, il periodo di conservazione si basa spesso sull'età del contenuto: ad esempio, è possibile conservare i documenti per sette anni dopo la loro creazione e quindi eliminarli. Tuttavia, con le etichette di conservazione in Office 365, è possibile basare un periodo di conservazione su quando si verifica un determinato tipo di evento. L'evento attiva l'inizio del periodo di conservazione e tutto il contenuto con un'etichetta di conservazione applicata per quel tipo di evento riceve le azioni di conservazione dell'etichetta applicate su di esso.
  
Ad esempio, è possibile usare etichette con conservazione basata su eventi per:
  
- **Dipendenti che lasciano l'organizzazione.** Si supponga che i documenti dei dipendenti debbano essere conservati per 10 anni dal momento in cui un dipendente lascia l'organizzazione. Trascorsi 10 anni, tutti i documenti relativi all'assunzione, alle prestazioni e alla cessazione di tale dipendente devono essere smaltiti. L'evento che attiva il periodo di conservazione di 10 anni è il dipendente che lascia l'organizzazione. 
    
- **Scadenza contratto** Si supponga che tutti i record relativi ai contratti debbano essere conservati per cinque anni dal momento in cui scade il contratto. L'evento che fa scattare il periodo di conservazione di cinque anni è la scadenza del contratto. 
    
- **Durata del prodotto** L'organizzazione potrebbe avere requisiti di conservazione relativi all'ultima data di produzione dei prodotti per i contenuti, come le specifiche tecniche. In questo caso, l'ultima data di produzione è l'evento che attiva il periodo di conservazione. 
    
La conservazione basata su eventi viene generalmente utilizzata come parte di un processo di gestione dei record. Ciò significa che:
  
- Anche le etichette basate sugli eventi solitamente classificano il contenuto come un record. Per ulteriori informazioni, vedere [Utilizzo di Ricerca contenuto per trovare tutto il contenuto con un'etichetta di conservazione specifica applicata](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- Un documento che è stato dichiarato come record ma il cui trigger di evento non è ancora stato eseguito viene conservato a tempo indeterminato (i record non possono essere eliminati in modo permanente) finché un evento non attiva il periodo di conservazione di quel documento.
    
- Le etichette basate su eventi di solito attivano una revisione per l'eliminazione alla fine del periodo di conservazione, in modo che un Record Manager possa esaminare e eliminare manualmente il contenuto. Per ulteriori informazioni, vedere [Panoramica delle revisioni per l'eliminazione](disposition-reviews.md).
    
Un'etichetta basata su un evento ha le stesse funzionalità di qualsiasi etichetta in Office 365. Per ulteriori informazioni, vedere [Panoramica delle etichette](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Informazioni sulla relazione tra tipi di eventi, etichette, eventi e ID delle risorse

Per utilizzare correttamente la conservazione basata su eventi, è importante comprendere la relazione tra tipi di eventi, etichette, eventi e ID delle risorse come illustrato qui. Una spiegazione segue il diagramma.
  
![Diagramma del tipo di evento, etichette, eventi e ID delle risorse](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagramma del tipo di evento, etichette, eventi e ID delle risorse](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Creare etichette per diversi tipi di contenuti e quindi associarle a un tipo di evento. Ad esempio, le etichette per tipi diversi di file e record di prodotti sono associate a un tipo di evento denominato Durata del prodotto, in quanto tali record devono essere conservati per 10 anni dal momento in cui il prodotto raggiunge la fine del ciclo di vita.
    
2. Gli utenti (in genere i Record Manager) applicano tali etichette al contenuto e immettono un ID risorsa per ciascun elemento (per i documenti di SharePoint e OneDrive). In questo esempio, l'ID risorsa è un nome del prodotto o un codice utilizzato dall'organizzazione. Pertanto, ai record di ogni prodotto viene assegnata un'etichetta e ogni record ha una proprietà contenente un ID risorsa. Il diagramma rappresenta **tutto il contenuto** per tutti i record di prodotto in un'organizzazione e ogni articolo porta l'ID risorsa del prodotto di cui è il record. 
    
3. La durata del prodotto è il tipo di evento; un prodotto specifico che raggiunge la fine del ciclo di vita è un evento. Quando si verifica un evento di quel tipo (in questo caso, quando un prodotto raggiunge la fine del suo ciclo di vita), si crea un evento che specifica:
    
  - Un ID risorsa (per i documenti di SharePoint e OneDrive)
    
  - Parole chiave (per gli articoli di Exchange). In questo esempio, l'organizzazione utilizza un codice prodotto nei messaggi contenenti i record del prodotto, pertanto la parola chiave per gli elementi di Exchange è uguale all'ID risorsa per i documenti di SharePoint e OneDrive.
    
  - La data in cui si è verificato l'evento. Questa data viene utilizzata come inizio del periodo di conservazione. Questa data può essere la data attuale, una futura o una passata.
    
4. Dopo aver creato un evento, tale data dell'evento viene sincronizzata con tutto il contenuto che ha un'etichetta di quel tipo di evento e che contiene l'ID risorsa o la parola chiave specificati. Come qualsiasi etichetta, questa sincronizzazione può richiedere fino a 7 giorni. Nel diagramma sopra riportato, il periodo di conservazione di tutti gli elementi cerchiati in rosso è attivato da questo evento. In altre parole, quando questo prodotto raggiunge la fine del suo ciclo di vita, quell'evento attiva il periodo di conservazione per i record di quel prodotto.
    
Se non si specifica un ID risorsa o una parole chiave per un evento, **tutto il contenuto** con un'etichetta di quel tipo di evento avrà il suo periodo di conservazione innescato dall'evento. Ciò significa che nel diagramma di cui sopra, tutto il contenuto inizierà a essere conservato, anche se questa operazione non era prevista. 
  
Infine, tenere presente che ogni etichetta ha le proprie impostazioni di conservazione. In questo esempio, tutti gli elementi specificano 10 anni, ma è possibile che un evento attivi etichette con periodi di conservazione diversi.
  
## <a name="how-to-set-up-event-driven-retention"></a>Come configurare la conservazione basata su eventi

Di seguito viene illustrato il flusso di lavoro principale per la conservazione basata su eventi. I passaggi più dettagliati sono riportati in basso.
  
![Diagramma del flusso di lavoro per la configurazione di conservazione basata su eventi](../media/161146d9-e0fc-4248-abc1-a18045eaad5c.png)
  
> [!TIP]
> Vedere [Gestire il ciclo di vita dei documenti di SharePoint con etichette di conservazione](auto-apply-retention-labels-scenario.md) per uno scenario dettagliato sull'uso delle proprietà gestite in SharePont per applicare automaticamente etichette di conservazione e implementare la conservazione basata su eventi.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Passaggio 1: creare un'etichetta il cui periodo di conservazione sia basato su un evento

Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365, del Centro sicurezza Microsoft 365 o del Centro sicurezza e conformità di Office 365 scegliere **ClassificazioneEtichette di conservazione scheda Etichette> Crea un'etichetta.
  
Quando si crea l'etichetta, attivare la conservazione, quindi scegliere l'opzione mostrata di seguito per conservare o eliminare il contenuto in base a un evento. Ciò significa che le impostazioni di conservazione non avranno effetto fino al Passaggio 5, quando verrà creato un evento nella pagina **Eventi**. 
  
La conservazione basata su eventi viene in genere utilizzata per contenuti classificati come record. Per questo motivo, quando si creano etichette basate su un evento, si sceglie solitamente l'opzione **Usa etichetta per classificare il contenuto come "Record"**.
  
Inoltre, la conservazione basata su eventi richiede impostazioni di conservazione che:
  
- Conservino il contenuto.
    
- Eliminino il contenuto automaticamente o attivino una revisione per l'eliminazione alla fine del periodo di conservazione.
    
![Opzione per basare un'etichetta su un evento](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>Passaggio 2: scegliere un tipo di evento per l'etichetta

Nelle impostazioni dell'etichetta, dopo aver scelto l'opzione per basare l'etichetta su **un evento**, verrà visualizzata l'opzione **Scegli un tipo di evento**. Un tipo di evento è semplicemente una descrizione generale di un evento a cui si desidera associare un'etichetta.
  
Ad esempio, se si crea un tipo di evento denominato Durata del prodotto, verranno create le etichette basate sugli eventi con i nomi che descrivono i tipi di contenuti a cui si desidera applicare le etichette, ad esempio "File di sviluppo prodotto" o "Record decisione prodotto aziendale".
  
Una volta scelto un tipo di evento e creata l'etichetta, il tipo di evento non può essere modificato.
  
![Opzioni per creare o scegliere un tipo di evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-label"></a>Passaggio 3: pubblicare o applicare automaticamente l'etichetta

Come per qualsiasi etichetta, è necessario pubblicare o applicare automaticamente un'etichetta basata su eventi perché venga applicata manualmente o automaticamente al contenuto. È possibile effettuare questa operazione nella pagina **Classificazione** > **Etichette di conservazione**.
  
![Opzioni per pubblicare o applicare automaticamente un'etichetta di conservazione](../media/options-to-publish-auto-apply-retention-label.png)

### <a name="step-4-enter-an-asset-id"></a>Passaggio 4: immettere un ID risorsa

Dopo aver applicato al contenuto un'etichetta basata sugli eventi, è possibile immettere un ID risorsa per ogni elemento. Ad esempio, la propria organizzazione potrebbe utilizzare:
  
- Codici prodotto da utilizzare per conservare i contenuti solo per un prodotto specifico.
    
- Codici prodotto da utilizzare per conservare i contenuti solo per un progetto specifico.
    
- ID dipendente da utilizzare per conservare i contenuti solo per una persona specifica.
    
ID risorsa è semplicemente un'altra proprietà dei documenti in SharePoint e OneDrive for Business. La propria organizzazione potrebbe già utilizzare altri ID e proprietà dei documenti per classificare il contenuto. In tal caso, è possibile anche utilizzare tali proprietà e valori quando si crea un evento. Vedere il Passaggio 6 di seguito. L'organizzazione deve utilizzare una combinazione di proprietà e valore nelle proprietà del documento per associare quell'elemento a un tipo di evento.
  
![Casella di testo per immettere un ID risorsa](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Passaggio 5: creare un evento

Quando si verifica un'istanza particolare di quel tipo di evento, ad esempio quando un prodotto raggiunge la fine del ciclo di vita, accedere alla pagina **Gestione record** > **Eventi** nel Centro sicurezza e conformità e creare un evento. È necessario attivare manualmente un evento creandolo.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Passaggio 6: scegliere lo stesso tipo di evento utilizzato per l'etichetta nel Passaggio 2

Quando si crea l'evento, scegliere lo stesso tipo di evento utilizzato dall'etichetta nel Passaggio 2, ad esempio Durata del prodotto. Solo il contenuto con le etichette applicate a quel tipo di evento avrà il periodo di conservazione attivato.
  
![Opzione in Impostazioni evento per scegliere un tipo di evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Passaggio 7: immettere parole chiave o un ID risorsa

Restringere quindi l'ambito del contenuto specificando gli ID delle risorse per i contenuti di SharePoint e OneDrive o le parole chiave per il contenuto di Exchange. Per gli ID delle risorse, la conservazione verrà applicata solo al contenuto con la coppia di proprietà e valore specificata. Se non viene inserito un ID risorsa, a **tutto il contenuto** con le etichette di quel tipo di evento viene applicata la stessa data di conservazione. 
  
L'ID risorsa è semplicemente un'altra proprietà del documento in SharePoint e OneDrive for Business. Se si utilizza la proprietà ID risorsa, è necessario inserire ComplianceAssetID:\<value\> nella casella per gli ID delle risorse mostrati di seguito.
  
L'organizzazione potrebbe aver applicato altre proprietà e ID ai documenti relativi a questo tipo di evento. Ad esempio, se è necessario rilevare i record di un prodotto specifico, l'ID potrebbe essere una combinazione della proprietà personalizzata ProductID e del valore "XYZ". In questo caso, inserire ProductID:XYZ nella casella per gli ID delle risorse mostrati di seguito.
  
Per gli elementi di Exchange, è possibile includere parole chiave. È possibile perfezionare la query utilizzando operatori di ricerca come AND, OR e NOT. Per ulteriori informazioni sugli operatori, vedere [Query con parole chiave e condizioni di ricerca per Ricerca contenuto](keyword-queries-and-search-conditions.md).
  
Infine, scegliere la data in cui si è verificato l'evento. Questa data viene utilizzata come inizio del periodo di conservazione. Dopo aver creato un evento, quella data dell'evento viene sincronizzata con tutti i contenuti con un'etichetta di quel tipo di evento, ID risorsa e parole chiave. Come qualsiasi etichetta, questa sincronizzazione può richiedere fino a 7 giorni.
  
![Pagina Impostazioni evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Utilizzare Ricerca contenuto per trovare tutti i contenuti con un'etichetta o un ID risorsa specifici

Dopo che le etichette sono state assegnate al contenuto, è possibile usare la funzionalità di ricerca di contenuto per trovare tutti i contenuti classificati con un'etichetta specifica o che contengono un ID risorsa specifico.
  
Quando si crea una ricerca di contenuto:
  
- Per trovare tutto il contenuto con un'etichetta specifica, selezionare la condizione **Tag di conformità**, quindi immettere il nome completo dell'etichetta o parte di esso e utilizzare un carattere jolly. 
    
- Per trovare tutto il contenuto con un ID risorsa specifico, inserire la proprietà **ComplianceAssetID** e un valore, come ComplianceAssetID:\<value\>. 
    
Per ulteriori informazioni, vedere [Query delle parole chiave e condizioni di ricerca per ricerca contenuto](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Autorizzazioni

Per accedere alla pagina **Eventi**, i revisori devono essere membri di un gruppo di ruoli con il ruolo **Gestione eliminazione** e **Solo visualizzazione log di controllo**. Si consiglia di creare un nuovo gruppo di ruoli denominato Revisori eliminazione, aggiungendo questi due ruoli, e quindi membri, a quel gruppo di ruoli. 
  
Per ulteriori informazioni, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatizzare gli eventi con PowerShell

Nell'interfaccia di amministrazione è possibile creare eventi solo manualmente e non è possibile attivare automaticamente un evento quando si verifica. Tuttavia, è possibile usare un'API REST per attivare eventi automaticamente. Per altre informazioni, vedere [Automatizzare la conservazione basata su eventi](automate-event-driven-retention.md).

È anche possibile usare uno script di PowerShell per automatizzare la conservazione basata su eventi dalle applicazioni aziendali. Ecco i cmdlet di PowerShell disponibili per la conservazione basata su eventi:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

