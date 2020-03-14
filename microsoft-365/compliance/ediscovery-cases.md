---
title: Gestire i casi di eDiscovery nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 8dd335ab-29d0-41c3-8dd8-9f7c7481e60c
description: Utilizzare il Centro sicurezza & conformità per creare e gestire i casi di eDiscovery nell'organizzazione. È possibile assegnare membri al caso, inserire posizioni di contenuto in attesa, eseguire ricerche di contenuto associate al caso e esportare i risultati della ricerca. È inoltre possibile preparare i dati dei casi per un'ulteriore analisi in Office 365 Advanced eDiscovery.
ms.openlocfilehash: 92894e430faaf9d5c1a758f81c5abfeb5236e643
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634954"
---
# <a name="manage-ediscovery-cases-in-the-security--compliance-center"></a>Gestire i casi di eDiscovery nel Centro sicurezza e conformità

È possibile utilizzare i casi di eDiscovery nel centro conformità di Office 365 e Microsoft 365 per controllare gli utenti autorizzati a creare, accedere e gestire i casi di eDiscovery nell'organizzazione. Se l'organizzazione dispone di un abbonamento a Office 365 E5, è anche possibile utilizzare i casi di eDiscovery per analizzare i risultati della ricerca tramite Office 365 Advanced eDiscovery.
  
Un caso di eDiscovery consente di aggiungere membri a un caso, controllare i tipi di azione che i membri del caso specifico possono eseguire, conservare i percorsi di contenuti attinenti a un caso legale e associare più ricerche di contenuto a un caso singolo. È inoltre possibile esportare i risultati di una ricerca di contenuto associata a un caso oppure preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. I casi di eDiscovery sono un'ottima soluzione per limitare chi ha accesso a ricerche di contenuto e risultati della ricerca per un caso legale specifico nell'organizzazione.
  
Utilizzare il flusso di lavoro seguente per configurare e utilizzare i casi di eDiscovery nel centro sicurezza & compliance e Advanced eDiscovery.

[Step 1: Assign eDiscovery permissions to potential case members](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Passaggio 2: creare un nuovo caso](#step-2-create-a-new-case)

[Passaggio 3: aggiungere membri a un caso](#step-3-add-members-to-a-case)

[Passaggio 4: posizionare i percorsi di contenuto in attesa](#step-4-place-content-locations-on-hold)

[Passaggio 5: creare ed eseguire una ricerca di contenuto associata a un caso](#step-5-create-and-run-a-content-search-associated-with-a-case)

[Passaggio 6: esportare i risultati di una ricerca di contenuto associata a un caso](#step-6-export-the-results-of-a-content-search-associated-with-a-case)

[Passaggio 7: preparare i risultati della ricerca per Advanced eDiscovery](#step-7-prepare-search-results-for-advanced-ediscovery)

[Passaggio 8: passare alla causa in Advanced eDiscovery](#step-8-go-to-the-case-in-advanced-ediscovery)

[Optional Passaggio 9: chiudere un caso](#optional-step-9-close-a-case)

[Optional Passaggio 10: riaprire un caso chiuso](#optional-step-10-re-open-a-closed-case)

[Ulteriori informazioni](#more-information)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Passaggio 1: Assegnare autorizzazioni di eDiscovery a potenziali membri del caso

Il primo passaggio consiste nell'assegnare le autorizzazioni appropriate relative a eDiscovery alle persone, in modo da poterle aggiungere a un caso di eDiscovery nel passaggio 2. È necessario essere membri del gruppo di ruoli Gestione organizzazione (o essere assegnati al ruolo di gestione dei ruoli) nel centro sicurezza & conformità per assegnare le autorizzazioni di eDiscovery. Nell'elenco seguente vengono descritti i gruppi di ruoli correlati a eDiscovery nel centro sicurezza & Compliance. 
  
- **Revisore.** Questo gruppo di ruoli ha le autorizzazioni più restrittive relative a eDiscovery. Lo scopo principale di questo gruppo di ruoli è consentire ai membri di visualizzare e accedere ai dati del caso in [Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md) (noto anche come *Advanced eDiscovery V1*). I membri di questo gruppo possono visualizzare e aprire solo l'elenco dei casi nella pagina **eDiscovery** nel centro sicurezza & conformità di cui sono membri. Dopo che l'utente ha eseguito l'accesso a un caso nel centro sicurezza e conformità, è possibile fare clic su **passa a Advanced eDiscovery** per accedere ai dati del caso in Advanced eDiscovery e analizzarli. Non è possibile creare casi, aggiungere membri a un caso, creare esenzioni, creare ricerche, visualizzare in anteprima i risultati della ricerca, esportare i risultati della ricerca o preparare i risultati per Advanced eDiscovery. 

   > [!NOTE]
   > A questo punto, gli utenti membri del gruppo di ruoli reviewer non possono accedere ai dati in [Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md) (noto anche come *Advanced eDiscovery V2*). Per aggiungere membri a un caso in Advanced eDiscovery V2 in modo che possano esaminare i dati dei casi, un utente deve essere membro del gruppo di ruoli Gestione eDiscovery.
    
- **eDiscovery Manager.** I membri di questo gruppo di ruoli possono creare e gestire casi di eDiscovery. Possono aggiungere e rimuovere membri, inserire posizioni di contenuto in attesa, creare e modificare le ricerche di contenuto associate a un caso, esportare i risultati di una ricerca di contenuto e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. In questo gruppo di ruoli sono presenti due sottogruppi. La differenza tra questi sottogruppi dipende dall'ambito.
    
  - **eDiscovery Manager.** Può solo visualizzare e gestire i casi di eDiscovery che ha creato o di cui è membro. Se un altro Manager di eDiscovery crea un caso ma non aggiunge un secondo Manager di eDiscovery come membro del caso, il secondo responsabile di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina **eDiscovery** del centro sicurezza & Compliance. i responsabili di eDiscovery possono inoltre accedere ai propri casi in Advanced eDiscovery per eseguire attività di analisi. 
    
  - **Amministratore di eDiscovery *.** Può eseguire tutte le attività di gestione dei casi di un gestore di eDiscovery. Inoltre, un amministratore di eDiscovery è in grado di:
    
    - Visualizzare tutti i casi elencati nella pagina **eDiscovery**. 
    
    - Gestire qualsiasi caso nell'organizzazione dopo che si è aggiunto come membro del caso.
    
    - Accedere ai dati del caso in Advanced eDiscovery per tutti i casi nell'organizzazione.
    
    Vedere la sezione [More information](#more-information) per conoscere i motivi per cui si potrebbe voler diventare un amministratore di eDiscovery nell'organizzazione. 

Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [assign eDiscovery Permissions](assign-ediscovery-permissions.md).
  
 **Per assegnare autorizzazioni di eDiscovery:**
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel centro sicurezza & conformità fare clic su **autorizzazioni**e quindi eseguire una delle operazioni seguenti in base alle autorizzazioni di eDiscovery che si desidera assegnare.
    
    - Per assegnare le autorizzazioni per il revisore, selezionare il gruppo di ruoli **reviewer** e quindi fare clic su **modifica**accanto a **membri**. Fare clic su **Scegli membri**, fare clic ![su **modifica**, fare clic su Aggiungi icona](../media/ITPro-EAC-AddIcon.gif) **,** selezionare l'utente che si desidera aggiungere al gruppo di ruoli reviewer e quindi fare clic su **Aggiungi**.
    
    - Per assegnare le autorizzazioni di eDiscovery Manager, selezionare il gruppo di ruoli **gestione eDiscovery** , quindi fare clic su **modifica**accanto a **eDiscovery Manager**. Fare clic su **Scegli eDiscovery Manager**, fare clic ![su **modifica**, fare clic su Aggiungi icona](../media/ITPro-EAC-AddIcon.gif) * * Aggiungi * *, selezionare l'utente che si desidera aggiungere come Manager di eDiscovery e quindi fare clic su **Aggiungi**.
    
    - Per assegnare le autorizzazioni di amministratore di eDiscovery, selezionare il gruppo di ruoli **gestione di eDiscovery** e quindi fare clic su **modifica**accanto a **amministratore di eDiscovery**. Fare clic su **Scegli amministratore di eDiscovery**, fare ![clic su](../media/ITPro-EAC-AddIcon.gif) **modifica**, fare clic su Aggiungi icona, selezionare l'utente che si **desidera aggiungere come**amministratore di eDiscovery e quindi fare clic su **Aggiungi**.
    
4. Dopo aver aggiunto tutti gli utenti, fare clic su **fine**, fare clic su **Salva** per salvare le modifiche apportate al gruppo di ruoli e quindi fare clic su **Chiudi**.

## <a name="step-2-create-a-new-case"></a>Passaggio 2: creare un nuovo caso

Il passaggio successivo consiste nel creare un caso di eDiscovery. È necessario essere un membro del gruppo di ruoli Gestore di eDiscovery per creare casi di eDiscovery. Come spiegato in precedenza, dopo aver creato un caso nel centro sicurezza & Compliance, l'utente (e altri membri del caso) potranno accedere allo stesso caso in Advanced eDiscovery se l'organizzazione dispone di un abbonamento a Office 365 E5.
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery**, quindi fare ![clic su](../media/ITPro-EAC-AddIcon.gif) Aggiungi icona **creare un caso**.
    
4. Nella pagina **nuovo caso** , assegnare un nome al caso, digitare una descrizione facoltativa, quindi fare clic su **Salva**. Il nome del caso deve essere univoco nell'organizzazione.
    
    ![Creare un caso](../media/7f78f83b-1525-4c77-9888-4b6bda1e148d.png)
  
    Il nuovo caso viene visualizzato nell'elenco dei casi nella pagina **eDiscovery** . È possibile posizionare il puntatore del mouse su un nome di case per visualizzare le informazioni relative al caso, incluso lo stato del caso (**attivo** o **chiuso**), la descrizione del caso (creato nel passaggio precedente) e quando il caso è stato modificato per ultimo e chi lo ha modificato.
    
    > [!TIP]
    > Dopo aver creato un nuovo caso, è possibile rinominarlo in qualsiasi momento. Basta fare clic sul nome del caso nella pagina **eDiscovery** . Nella pagina **Gestisci** il riquadro a comparsa di questo caso, modificare il nome visualizzato nella casella in **nome**e quindi salvare la modifica. 
## <a name="step-3-add-members-to-a-case"></a>Passaggio 3: aggiungere membri a un caso

Dopo aver creato un caso, il passaggio successivo consiste nell'aggiungere membri al caso. Il responsabile di eDiscovery che ha creato il caso viene aggiunto automaticamente come membro. Come spiegato in precedenza, i membri devono assegnare le autorizzazioni appropriate di eDiscovery, in modo che possano accedere al caso dopo averli aggiunti.
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 

2. Fare clic sul nome del caso in cui si desidera aggiungere i membri.

    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** . 

    ![Gestione di una pagina del riquadro a comparsa del caso](../media/11f35ceb-6c98-4580-a3bc-ad688e9c7af9.png)
  
3. In **Gestisci membri**fare ![clic su](../media/ITPro-EAC-AddIcon.gif) **Aggiungi icona Aggiungi** per aggiungere membri al caso. 

    È inoltre possibile scegliere di aggiungere un gruppo di ruoli al caso. In **Gestisci gruppi**di ruoli ![fare clic](../media/ITPro-EAC-AddIcon.gif) su **Aggiungi icona Aggiungi**.

    > [!NOTE]
    > I gruppi di ruoli controllano chi può assegnare membri a un caso di eDiscovery. Questo significa che è possibile assegnare solo i gruppi di ruoli a cui si è membri di un caso.

4. Nell'elenco di utenti o gruppi di ruoli che possono essere aggiunti come membri del caso, fare clic sulla casella di controllo accanto ai nomi degli utenti o dei gruppi di ruoli che si desidera aggiungere.

    > [!TIP]
    > Se si dispone di un elenco elevato di utenti che possono essere aggiunti come membri, utilizzare la casella di **ricerca** per cercare una persona specifica nell'elenco. 
  
5. Dopo aver selezionato gli utenti o i gruppi di ruoli da aggiungere come membri del gruppo, fare clic su **Aggiungi**.
    
    In **Gestisci questo caso**, fare clic su **Salva** per salvare il nuovo elenco dei membri del caso. 
    
6. Fare clic su **Salva** per salvare il nuovo elenco dei membri del caso. 
  
## <a name="step-4-place-content-locations-on-hold"></a>Passaggio 4: posizionare i percorsi di contenuto in attesa

È possibile utilizzare un caso eDiscovery per creare blocchi al fine di conservare contenuti che potrebbero essere attinenti al caso. È possibile applicare un blocco alle cassette postali e ai siti di OneDrive for business di persone che sono depositarie nel caso. È inoltre possibile inserire un blocco nel sito di gruppo cassetta postale, sito di SharePoint e OneDrive for business per un gruppo di Office 365. Analogamente, è possibile applicare un blocco alle cassette postali e ai siti associati a Microsoft teams o ai gruppi di Yammer. Quando si posizionano le posizioni di contenuto in attesa, il contenuto viene mantenuto fino a quando non viene rimosso il blocco dal percorso del contenuto o fino a quando non viene eliminato il blocco.

> [!NOTE]
> Dopo aver attivato il blocco del contenuto, sono necessarie fino a 24 ore per rendere effettive le esenzioni. 

Quando si crea un'esenzione, sono disponibili le opzioni seguenti per l'ambito del contenuto conservato nei percorsi di contenuto specificati:
  
- È possibile creare un'esenzione infinita in cui tutto il contenuto viene messo in attesa. In alternativa, è possibile creare un blocco basato su query che contenga solo il contenuto che corrisponde a una query di ricerca.
    
- È possibile specificare un intervallo di date che contenga solo il contenuto che è stato inviato, ricevuto o creato all'interno di tale intervallo di date. In alternativa, è possibile conservare tutto il contenuto indipendentemente dal momento in cui è stato inviato, ricevuto o creato.
    
> [!NOTE]
> È possibile disporre di un massimo di 10.000 criteri di blocco in tutti i casi di eDiscovery nell'organizzazione. 
  
Per creare un'esenzione per un caso di eDiscovery:
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera creare le esenzioni. 
    
3. Nella **Home** page del caso, fare clic sulla scheda **blocco** . 
    
    ![Fare clic sulla scheda blocco](../media/3fef2db4-36de-4517-a34d-82f47b82d9bf.png)
  
4. Nella pagina **blocco** fare clic ![su Aggiungi icona](../media/ITPro-EAC-AddIcon.gif) **Crea**.
    
5. Nella pagina **denominare il blocco** , assegnare un nome al blocco. Il nome del blocco deve essere univoco nell'organizzazione. 
    
    ![Assegnare un nome univoco alla propria esenzione](../media/7e15ea63-abd1-4f14-a29c-7ecfb9571d2c.png)
  
6. Optional Nella casella **Descrizione** aggiungere una descrizione dell'esenzione. 
    
7. Fare clic su **Avanti**.
    
8. Scegliere i percorsi di contenuto che si desidera inserire in attesa. È possibile inserire le cassette postali, i siti e le cartelle pubbliche in attesa.
    
    ![Scegliere i percorsi dei contenuti da mettere in attesa](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **Posta elettronica di Exchange** -fare clic su **Scegli utenti, gruppi o team** e quindi fare di nuovo clic su **Scegli utenti, gruppi o team** . per specificare le cassette postali da inserire in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione (per inserire un'esenzione nelle cassette postali dei membri del gruppo) per effettuare il blocco. È inoltre possibile inserire un blocco sulla cassetta postale associata per un team di Microsoft, un gruppo di Yammer o un gruppo di Office 365. Selezionare la casella di controllo utente, gruppo, team, fare clic su **Scegli**e quindi su **fine**.
    
    > [!NOTE]
    > Quando si fa clic su **Scegli utenti, gruppi o team** per specificare le cassette postali da inserire in attesa, lo strumento di selezione delle cassette postali visualizzato è vuoto. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere persone a questo elenco, digitare un nome, almeno 3 caratteri, nella casella di ricerca. 

   b. **Siti di SharePoint** -fare clic su **Scegli siti** , quindi fare di nuovo clic su **Choose sites** per specificare i siti di SharePoint e OneDrive for business in attesa. Digitare l'URL per ogni sito che si desidera conservare. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un team di Microsoft, un gruppo di Yammer o un gruppo di Office 365. Fare clic su **Scegli**e quindi su **fine**.
    
    Vedere la sezione [ulteriori informazioni](#more-information) per suggerimenti su come mettere in attesa Microsoft teams, gruppi di Yammer e gruppi di Office 365. 
    
    > [!NOTE]
    > Nel caso raro che il nome dell'entità utente (UPN, User Principal Name) di una persona venga modificato, l'URL per il relativo account OneDrive verrà modificato anche per incorporare il nuovo UPN. In questo caso, è necessario modificare il blocco aggiungendo il nuovo URL di OneDrive dell'utente e rimuovendo quello precedente. 
  
   c. **Cartelle pubbliche di Exchange.** Spostare il controllo](../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) Toggle Toggle ![switch nella posizione **All** per inserire in attesa tutte le cartelle pubbliche nell'organizzazione di Exchange Online. Non è possibile scegliere cartelle pubbliche specifiche da mantenere in attesa. Lasciare l'opzione toggle impostata su **None** se non si desidera inserire un blocco nelle cartelle pubbliche.
    
9. Dopo aver aggiunto i percorsi di contenuto all'esenzione, fare clic su **Avanti**.
    
10. Per creare un blocco basato su query con condizioni, completare quanto segue. In caso contrario, fare clic su **Avanti** .
    
    ![Creare un blocco basato su query con condizioni](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    
       a. Nella casella sotto **parole chiave**Digitare una query di ricerca nella casella in modo che solo il contenuto che soddisfa i criteri di ricerca venga messo in attesa. È possibile specificare le parole chiave, le proprietà del messaggio o le proprietà del documento, ad esempio i nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio **e**, **o**o **meno**. Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà messo in attesa.
    
    b. Fare ![clic su](../media/ITPro-EAC-AddIcon.gif) **Aggiungi icona per aggiungere una** o più condizioni per limitare la query di ricerca per il blocco. Ogni condizione aggiunge una clausola alla query di ricerca di KQL che viene creata e eseguita quando si crea il blocco. Ad esempio, è possibile specificare un intervallo di date in modo che i documenti di posta elettronica o di sito creati entro la data di intervallo siano stati inseriti in attesa. Una condizione è collegata logicamente alla query con parola chiave (specificata nella relativa casella) dall'operatore **AND**. Questo significa che gli elementi devono soddisfare sia la query di parole chiave che la condizione da inserire in attesa.

    Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).
    
11. Dopo aver configurato un blocco basato su query, fare clic su **Avanti**.
    
12. Rivedere le impostazioni e quindi fare clic su **Crea blocco**.
    
### <a name="hold-statistics"></a>Statistiche di blocco

Dopo un po' di tempo, le informazioni relative al nuovo blocco vengono visualizzate nel riquadro dei dettagli nella pagina **esenzioni** per il blocco selezionato. Queste informazioni includono il numero di cassette postali e i siti in attesa e le statistiche sul contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi che sono stati messi in attesa e l'ultima volta che sono state calcolate le statistiche di blocco. Queste statistiche di blocco consentono di identificare la quantità di contenuto correlata al caso di eDiscovery. 
  
![Statistiche di blocco](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Tenere presenti le considerazioni seguenti sulle statistiche di archiviazione:
  
- Il numero totale di elementi in attesa indica il numero di elementi provenienti da tutte le origini di contenuto che vengono bloccate. Se è stata creata una conservazione basata su query, questa statistica indica il numero di elementi che corrispondono alla query.
    
- Il numero di elementi in attesa include anche gli elementi non indicizzati trovati nei percorsi di contenuto. Se si crea un blocco basato su query, tutti gli elementi non indicizzati nei percorsi di contenuto vengono inseriti in attesa. Sono inclusi gli elementi non indicizzati che non corrispondono ai criteri di ricerca di un blocco basato su query e di elementi non indicizzati che potrebbero non essere compresi in una condizione dell'intervallo di date. Questo è diverso da quello che succede quando si esegue una ricerca di contenuto, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o sono esclusi da una condizione dell'intervallo di date non sono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzati, vedere [gli elementi parzialmente indicizzati in ricerca contenuto in Office 365](partially-indexed-items-in-content-search.md).
    
- È possibile ottenere le statistiche di blocco più recenti facendo clic su **Aggiorna statistiche** per rieseguire una stima di ricerca che calcola il numero corrente di elementi in attesa. Se necessario **, fare clic su**![Aggiorna](../media/O365-MDM-Policy-RefreshIcon.gif) icona di aggiornamento sulla barra degli strumenti per aggiornare le statistiche di blocco nel riquadro dei dettagli. 
    
- È normale che il numero di elementi in attesa aumenti nel tempo, in quanto gli utenti la cui cassetta postale o sito è in attesa vengono in genere inviati o ricevuti da un nuovo messaggio di posta elettronica e dalla creazione di nuovi documenti di SharePoint e OneDrive for business.
    
> [!NOTE]
> Se un sito di SharePoint o un account OneDrive viene spostato in un'area geografica diversa in un ambiente multi-geografico, le statistiche per il sito non verranno incluse nelle statistiche di esenzione. Tuttavia, il contenuto del sito rimarrà ancora in attesa. Inoltre, se un sito viene spostato in un'altra area, l'URL visualizzato nell'esenzione non verrà aggiornato. È necessario modificare il blocco e aggiornare l'URL. 
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a>Passaggio 5: creare ed eseguire una ricerca di contenuto associata a un caso

Dopo aver creato un caso di eDiscovery, e archiviato i depositari correlati al caso, è possibile creare ed eseguire una o più ricerche di contenuto associate al caso. Le ricerche di contenuto associate a un caso non sono elencate nella pagina di **ricerca** nel centro sicurezza & conformità. Ciò significa che possono accedere alle ricerche di contenuto associate a un caso solo i membri del caso che sono anche membri del gruppo di ruoli Gestore di eDiscovery. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera creare una ricerca di contenuto. 
    
3. Nella **Home** page del caso, fare clic sulla scheda **Cerca** . 
    
    ![Scheda ricerca](../media/2e15fe32-1a2e-4588-ad0b-5d96f77cece9.png)
  
4. Nella pagina **ricerca** fare clic ![su Aggiungi nuova](../media/ITPro-EAC-AddIcon.gif) icona di **ricerca**. 
    
5. Nella pagina **Nuova ricerca**, è possibile aggiungere parole chiave e condizioni per creare la query di ricerca. 
    
    ![Nuova ricerca](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
6. È possibile specificare le parole chiave, le proprietà dei messaggi, ad esempio le date inviate e ricevute, o le proprietà del documento, ad esempio i nomi di file o la data dell'Ultima modifica di un documento. È possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio **and**, **or**, **not**, **near**o **ONEAR**. È inoltre possibile cercare informazioni sensibili (ad esempio numeri di codice fiscale) nei documenti o cercare documenti condivisi esternamente. Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà incluso nei risultati della ricerca. 
    
7. È possibile fare clic sulla casella di controllo **Mostra elenco parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono connesse dall'operatore **or** nella query di ricerca creata. 
    
    ![Elenco di parole chiave](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    Perché usare l'elenco di parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. Questo è utile per identificare rapidamente le parole chiave più e meno efficaci. È possibile usare anche una frase chiave, racchiusa tra parentesi, in una riga. Per altre informazioni sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave per i risultati di Ricerca contenuto](view-keyword-statistics-for-content-search.md).
    
    Per ulteriori informazioni sull'utilizzo dell'elenco delle parole chiave, vedere [creazione di una query di ricerca](content-search.md#building-a-search-query).
    
8. In **condizioni**, aggiungere condizioni a una query di ricerca per restringere una ricerca e restituire un set di risultati più raffinato. Ogni condizione consente di aggiungere una clausola alla query di ricerca KQL creata ed eseguita quando si avvia la ricerca. Una condizione è logicamente connessa alla query con parole chiave (specificata nella casella delle parole chiave) mediante l'operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia la condizione. Ecco come le condizioni consentono di circoscrivere i risultati. 
    
    Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
9. In **percorsi: posizioni in attesa**, scegliere i percorsi di contenuto che si desidera ricercare. È possibile cercare le cassette postali, i siti e le cartelle pubbliche nella stessa ricerca.
    
    ![Posizioni, posizioni in attesa](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Tutte le posizioni** : selezionare questa opzione per eseguire la ricerca in tutti i percorsi di contenuto dell'organizzazione. Quando si seleziona questa opzione, è possibile scegliere di effettuare una ricerca in tutte le cassette postali di Exchange (incluse le cassette postali per tutti i team Microsoft, i gruppi di Yammer e i gruppi di Office 365), tutti i siti di SharePoint e OneDrive for business (inclusi i siti per tutti gli utenti di Microsoft Teams, gruppi di Yammer e gruppi di Office 365) e tutte le cartelle pubbliche.
    
    - **Tutte le posizioni in attesa.** Selezionare questa opzione per cercare tutti i percorsi di contenuto che sono stati inseriti in attesa nel caso. Se il caso contiene più esenzioni, i percorsi di contenuto di tutte le esenzioni verranno ricercati quando si seleziona questa opzione. Inoltre, se un percorso di contenuto è stato posizionato in un blocco basato su query, vengono ricercati solo gli elementi che sono in attesa quando si esegue la ricerca di contenuto che si sta creando in questo passaggio. Ad esempio, se un utente è stato inserito in una conservazione basata su query che conserva gli elementi inviati o creati prima di una data specifica, solo gli elementi verranno ricercati utilizzando i criteri di ricerca della ricerca contenuto. Questa operazione viene eseguita collegando la query di blocco del caso e la query di ricerca del contenuto da parte di un operatore **and** . Vedere la sezione [ulteriori informazioni](#more-information) alla fine di questo articolo per ulteriori informazioni sulla ricerca di contenuto del caso. 
    
    - **Posizioni specifiche.** Selezionare questa opzione per selezionare le cassette postali e i siti in cui si desidera eseguire la ricerca. Quando si seleziona questa opzione e si fa clic su **modifica**, viene visualizzato un elenco di posizioni. È possibile scegliere di cercare tutti gli utenti, i gruppi, i team o i percorsi del sito.
    
      ![Selezionare posizioni specifiche](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
      È inoltre possibile scegliere di effettuare una ricerca in tutte le cartelle pubbliche dell'organizzazione, ma se si seleziona questa opzione e si esegue una ricerca in qualsiasi posizione di contenuto in attesa, qualsiasi query proveniente da un blocco di caso basato su query non verrà applicata alla query di ricerca. In altre parole, viene cercato tutto il contenuto di una posizione, non solo il contenuto che viene conservato da un blocco di caso basato su query.
    
      È possibile rimuovere i percorsi di contenuto precompilati oppure aggiungerne di nuovi. Se si sceglie questa opzione, è inoltre possibile eseguire la ricerca in tutti i percorsi di contenuto per un servizio specifico, ad esempio la ricerca in tutte le cassette postali di Exchange, oppure cercare percorsi di contenuto specifici per un servizio. È anche possibile scegliere se eseguire la ricerca nelle cartelle pubbliche dell'organizzazione.
    
      Tenere presente queste considerazioni quando si aggiungono percorsi di contenuto alla ricerca:
    
      - Quando si fa clic su **Scegli utenti, gruppi o team** per specificare le cassette postali da cercare, lo strumento di selezione delle cassette postali visualizzato è vuoto. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere destinatari all'elenco, fare clic su **Scegli utenti, gruppi o team**, digitare un nome, almeno 3 caratteri, nella casella di ricerca, selezionare la casella di controllo accanto al nome, quindi fare clic su **Scegli**. 
    
      - È possibile aggiungere cassette postali inattive, Microsoft teams, gruppi di Yammer, gruppi di Office 365 e gruppi di distribuzione all'elenco delle cassette postali da cercare. Non sono supportati i gruppi di distribuzione dinamici. Se si aggiungono Microsoft teams, gruppi di Yammer o gruppi di Office 365, viene eseguita la ricerca nella cassetta postale del gruppo o del team. le cassette postali dei membri del gruppo non vengono cercate.
    
      - Per aggiungere siti fare clic su **Scegli siti**, fare di nuovo clic su **Scegli siti** e quindi digitare l'URL per ogni sito che si desidera ricercare. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un team di Microsoft, un gruppo di Yammer o un gruppo di Office 365. 
    
10. Dopo aver selezionato i percorsi di contenuto in cui eseguire la ricerca, fare clic su **fine** e quindi su **Salva**.
    
11. Nella pagina **nuova ricerca** , fare clic su **Salva** e quindi digitare un nome per la ricerca. Le ricerche di contenuto associate a un caso devono avere nomi univoci all'interno dell'organizzazione di Office 365. 
    
12. Fare clic su **Salva &amp; esecuzione** per salvare le impostazioni di ricerca. 
    
13. Immettere un nome univoco per la ricerca e fare clic su **Salva** per avviare la ricerca. 
    
    La ricerca ha inizio. Dopo un po' di tempo, una stima dei risultati della ricerca viene visualizzata nel riquadro dei dettagli. La stima include la dimensione totale e il numero di elementi che corrispondono ai criteri di ricerca. La stima della ricerca include anche il numero di elementi non indicizzati nei percorsi di contenuto di cui è stata eseguita la ricerca. Il numero di elementi non indicizzati (che non corrispondono ai criteri di ricerca) verrà incluso nelle statistiche della ricerca visualizzate nel riquadro dei dettagli. Se un elemento non indicizzato corrisponde alla query di ricerca (perché altre proprietà del messaggio o del documento soddisfano i criteri di ricerca), non verrà incluso nel numero stimato di elementi non indicizzati. Se un elemento non indicizzato è escluso dai criteri di ricerca, non verrà incluso nella stima degli elementi non indicizzati.
    
  Una volta completata la ricerca, è possibile visualizzare in anteprima i risultati della ricerca. Se necessario **, fare clic su**![Aggiorna](../media/O365-MDM-Policy-RefreshIcon.gif) l'icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli. 
    
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a>Passaggio 6: esportare i risultati di una ricerca di contenuto associata a un caso

Dopo aver eseguito correttamente una ricerca, è possibile esportare i risultati della ricerca. Quando si esportano i risultati della ricerca, gli elementi della cassetta postale vengono scaricati nei file PST o come singoli messaggi. Quando si esporta contenuto da siti di SharePoint e OneDrive for business, vengono esportate copie dei documenti di Office native e di altri documenti. Viene esportato anche un file manifesto (in formato XML) che contiene informazioni su tutti i risultati della ricerca.
  
È possibile esportare i risultati di una [singola ricerca associata a un caso](#export-the-results-of-a-single-search-associated-with-a-case) oppure esportare i risultati di [più ricerche associate a un caso](#export-the-results-of-multiple-searches-associated-with-a-case).
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a>Esportare i risultati di una singola ricerca associata a un caso

1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso da cui si desidera esportare la ricerca. 
    
3. Nella **Home** page del caso, fare clic su **Cerca**.
    
4. Nell'elenco delle ricerche del caso, fare clic sulla ricerca di cui si desidera esportare i risultati della ricerca, fare ![clic su Esporta](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **altre**icone dei risultati di ricerca e quindi selezionare **Esporta risultati** dall'elenco a discesa. 
    
    Viene visualizzata la pagina dei **risultati di esportazione** . 
    
    ![Pagina Export results](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    Il flusso di lavoro per l’esportazione dei risultati di una ricerca di contenuto associata a un caso è lo stesso di quando si esportano i risultati della ricerca per una ricerca sulla pagina **Ricerca contenuto**. Per istruzioni dettagliate, vedere [Export content search results](export-search-results.md).
    
    > [!NOTE]
    > Quando si esportano i risultati della ricerca, è possibile abilitare la deduplicazione in modo che venga esportata una sola copia di un messaggio di posta elettronica anche se sono state trovate più istanze dello stesso messaggio nelle cassette postali di cui è stata eseguita la ricerca. Per ulteriori informazioni sulla deduplicazione e sulla modalità di identificazione degli elementi duplicati, vedere [de-duplication nei risultati della ricerca di eDiscovery](de-duplication-in-ediscovery-search-results.md). 
  
5. Fare clic sulla scheda **Esporta** per visualizzare l'elenco dei processi di esportazione esistenti per questo caso. 
    
    ![Scheda Esporta](../media/1b84c45e-4ec9-4ecd-9e07-eaf8fc4cc307.png)
  
    Potrebbe essere **necessario fare clic su**![aggiorna l'](../media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare l'elenco dei processi di esportazione in modo che venga visualizzato il processo di esportazione creato. I processi di esportazione hanno lo stesso nome della ricerca di contenuto corrispondente con **_Export** accodati alla fine del nome della ricerca. 
    
6. Fare clic sul processo di esportazione appena creato per visualizzare le informazioni sullo stato nel riquadro dei dettagli. Queste informazioni includono la percentuale di elementi che sono stati trasferiti in un'area di archiviazione di Azure nel cloud Microsoft.
    
    Dopo aver trasferito tutti gli elementi, fare clic su **Scarica risultati** per scaricare i risultati della ricerca nel computer locale. Per ulteriori informazioni, vedere passaggio 2 in [Export content search results](export-search-results.md)
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a>Esportare i risultati di più ricerche associate a un caso

Come alternativa all'esportazione dei risultati di una singola ricerca di contenuto associata a un caso, è possibile esportare i risultati di più ricerche dallo stesso caso in una singola esportazione. L'esportazione dei risultati di più ricerche è più semplice e veloce rispetto all'esportazione dei risultati di una ricerca alla volta.
  
> [!NOTE]
> Non è possibile esportare i risultati di più ricerche se una di queste ricerche è stata configurata per la ricerca in tutti i contenuti del caso. esportare solo i risultati di più ricerche per le ricerche associate a un caso di eDiscovery. Non è possibile esportare i risultati di più ricerche elencate nella pagina **Ricerca contenuto** nel centro sicurezza & conformità. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera esportare i risultati della ricerca. 
    
3. Nella **Home** page del caso, fare clic su **Cerca**.
    
4. Nell'elenco delle ricerche per il caso, selezionare due o più ricerche da cui si desidera esportare i risultati della ricerca.
    
    > [!NOTE]
    > Per selezionare più ricerche, premere CTRL quando si fa clic su ogni ricerca. In alternativa, è possibile selezionare più ricerche adiacenti facendo clic sulla prima ricerca, tenendo premuto il tasto MAIUSC e quindi facendo clic sull'ultima ricerca. 
  
5. Dopo aver selezionato le ricerche, viene visualizzata la pagina **azioni in blocco** . 
    
    ![Nella pagina azioni in blocco fare clic su Esporta risultati](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
    
6. Fare ![clic su Esporta i](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) risultati dell' **esportazione**dell'icona risultati della ricerca.

7. Nella pagina **Export results** , assegnare un nome univoco all'esportazione, selezionare opzioni di output e scegliere in che modo verrà esportato il contenuto. Fare clic su **Esporta**.
    
    Il flusso di lavoro per esportare i risultati da più ricerche di contenuto associate a un caso equivale all'esportazione dei risultati della ricerca per una singola ricerca. Per istruzioni dettagliate, vedere [Export content search results](export-search-results.md).
    
    > [!NOTE]
    > Quando si esportano i risultati della ricerca da più ricerche associate a un caso, è anche possibile abilitare la deduplicazione in modo che venga esportata una sola copia di un messaggio di posta elettronica anche se sono state trovate più istanze dello stesso messaggio nel cassette postali di cui è stata eseguita la ricerca in una o più ricerche. Per ulteriori informazioni sulla deduplicazione e sulla modalità di identificazione degli elementi duplicati, vedere [de-duplication nei risultati della ricerca di eDiscovery](de-duplication-in-ediscovery-search-results.md). 
  
8. Dopo aver avviato l'esportazione, fare clic sulla scheda **Esporta** per visualizzare l'elenco dei processi di esportazione per questo caso. 
    
    ![Scheda Esporta, più ricerche](../media/b9505e1b-559f-4a8c-96b3-a3f734753926.png)
  
    Potrebbe essere **necessario fare clic su** ![aggiorna l'](../media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare l'elenco dei processi di esportazione per visualizzare il processo di esportazione creato. Le ricerche incluse nel processo di esportazione sono elencate nella colonna **ricerche** . 
    
8. Fare clic sul processo di esportazione appena creato per visualizzare le informazioni sullo stato nel riquadro dei dettagli. Queste informazioni includono la percentuale di elementi che sono stati trasferiti in un'area di archiviazione di Azure nel cloud Microsoft.
    
9. Dopo aver trasferito tutti gli elementi, fare clic su **Scarica risultati** per scaricare i risultati della ricerca nel computer locale. Per ulteriori informazioni, vedere il passaggio 2 in [Export content search results](export-search-results.md).
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Ulteriori informazioni sull'esportazione dei risultati di più ricerche

- Quando si esportano i risultati di più ricerche, le query di ricerca provenienti da tutte le ricerche vengono combinate **tramite gli operatori e** quindi viene avviata la ricerca combinata. I risultati stimati della ricerca combinata vengono visualizzati nel riquadro dei dettagli del processo di esportazione selezionato. I risultati della ricerca vengono quindi trasferiti nell'area di archiviazione di Azure nel cloud Microsoft. Anche lo stato del trasferimento viene visualizzato nel riquadro dei dettagli. Come indicato in precedenza, dopo che tutti i risultati della ricerca sono stati trasferiti, è possibile scaricarli nel computer locale. 
    
- Il numero massimo di parole chiave delle query di ricerca per tutte le ricerche che si desidera esportare è 500. (questo è lo stesso limite per una singola ricerca contenuto). Ciò è dovuto al fatto che il processo di esportazione combina tutte le query di ricerca utilizzando l'operatore **or** . Se si supera questo limite, verrà restituito un errore. In questo caso, è necessario esportare i risultati da meno ricerche o semplificare le query di ricerca delle ricerche che si desidera esportare. 
    
- I risultati della ricerca esportati sono organizzati dall'origine di contenuto in cui è stato trovato l'elemento. Questo significa che un'origine di contenuto nei risultati di esportazione potrebbe avere elementi restituiti da ricerche diverse. Ad esempio, se si è scelto di esportare i messaggi di posta elettronica in un unico file PST per ogni cassetta postale, il file PST potrebbe avere risultati da più ricerche.
    
- Se lo stesso elemento di posta elettronica o documento proveniente dallo stesso percorso di contenuto viene restituito da più di una delle ricerche esportate, verrà esportata solo una copia dell'elemento.
    
- Non è possibile modificare un'esportazione per più ricerche dopo averlo creato. Ad esempio, non è possibile aggiungere o rimuovere le ricerche dall'esportazione. È necessario creare un processo di esportazione per modificare i risultati di ricerca esportati. Dopo la creazione di un processo di esportazione, è possibile scaricare i risultati solo in un computer, riavviare l'esportazione o eliminare il processo di esportazione.
    
- Se si riavvia l'esportazione, tutte le modifiche apportate alle query delle ricerche che compongono il processo di esportazione non influiscono sui risultati della ricerca che verranno recuperati. Quando si riavvia un'esportazione, viene eseguito di nuovo lo stesso processo di query di ricerca combinato eseguito al momento della creazione del processo di esportazione.
    
- Se si riavvia una esportazione dalla pagina **esportazioni** in un caso di eDiscovery, i risultati della ricerca trasferiti nell'area di archiviazione di Azure sovrascrivono i risultati precedenti. I risultati precedenti sono stati trasferiti non saranno disponibili per il download. 
    
- La preparazione dei risultati di più ricerche per l'analisi in Advanced eDiscovery non è disponibile. È possibile preparare solo i risultati di una singola ricerca per l'analisi in Advanced eDiscovery.

## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a>Passaggio 7: preparare i risultati della ricerca per Advanced eDiscovery

Se l'organizzazione dispone di un abbonamento a Office 365 E5, è possibile preparare i risultati delle ricerche di contenuto associate a un caso di analisi in Advanced eDiscovery. Dopo aver preparato i risultati della ricerca, è possibile passare a Advanced eDiscovery (vedere [Step 8: go to the case in Advanced eDiscovery](#step-8-go-to-the-case-in-advanced-ediscovery)) ed elaborare i dati dei risultati di ricerca per un'ulteriore analisi in Advanced eDiscovery.
  
Quando si preparano i risultati della ricerca per Advanced eDiscovery, la funzionalità di riconoscimento ottico dei caratteri (OCR) estrae automaticamente il testo dalle immagini. OCR è supportato per file sciolti, allegati di posta elettronica e immagini incorporate. In questo modo è possibile applicare le funzionalità analitiche del testo avanzate di eDiscovery (quasi duplicati, Threading di posta elettronica, temi e codifica predittiva) a qualsiasi testo nei file di immagine.
  
> [!NOTE]
> Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. 
    
3. Nella **Home** page del caso, fare clic su **ricerca**, quindi selezionare la ricerca.
    
4. Nel riquadro dei dettagli, fare ![clic su Esporta](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **altre**icone dei risultati della ricerca, quindi fare clic su **prepara per Advanced eDiscovery**.
    
    ![Preparare i risultati per Advanced eDiscovery](../media/b6548ff0-a6e9-42b1-9ae4-5c15146f5690.png)
  
5. Nella pagina **preparazione per la eDiscovery avanzata** scegliere di preparare una delle operazioni seguenti: 
    
    - Tutti gli elementi, esclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi.
    
    - Tutti gli elementi, compresi quelli che dispongono di un formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi.
    
    - Solo gli elementi con un formato irriconoscibile, sono crittografati o non sono stati indicizzati per altri motivi.
    
6. Optional Fare clic sulla casella **di controllo Includi versioni per i file di SharePoint** . 
    
7. Fare clic su **Prepara**.
    
    I risultati della ricerca sono pronti per l'analisi con Advanced eDiscovery.
    
8. Fare clic su **Chiudi** per chiudere il riquadro dei dettagli. 
    
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a>Passaggio 8: passare alla causa in Advanced eDiscovery

Dopo aver creato un caso nel centro sicurezza & conformità, è possibile passare allo stesso caso in Advanced eDiscovery.
  
Per accedere a un caso in Advanced eDiscovery:
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera accedere in Advanced eDiscovery. 
    
3. Nella **Home** page del caso, fare clic su **passa a Advanced eDiscovery**.
    
    ![Selezionare Cambia in Advanced eDiscovery](../media/d7e31558-e79c-4782-b841-2b735568a576.png)
  
    Viene visualizzata la barra **di avanzamento per la connessione a Advanced eDiscovery** . Quando si è connessi a Advanced eDiscovery, nella pagina viene visualizzato un elenco di contenitori. 
    
    ![Barra di avanzamento avanzata di eDiscorvery](../media/4a84273d-765b-44b8-9006-c20e810ea393.png)
  
    Questi contenitori rappresentano i risultati della ricerca preparati per l'analisi in Advanced eDiscovery nel passaggio 7. Il nome del contenitore ha lo stesso nome della ricerca di contenuto nel caso nel centro sicurezza & conformità. I contenitori presenti nell'elenco sono quelli che sono stati preparati. Se un utente diverso ha preparato i risultati della ricerca per Advanced eDiscovery, i contenitori corrispondenti non verranno inclusi nell'elenco.
    
4. Per caricare i dati dei risultati di ricerca da un contenitore a un caso in Advanced eDiscovery, selezionare un contenitore e fare clic su **processo**.
    
    Per informazioni su come elaborare i contenitori, vedere [eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md).
    
> [!TIP]
> Fare clic su **passa a eDiscovery** per tornare allo stesso caso nel centro sicurezza & conformità. 
  
## <a name="optional-step-9-close-a-case"></a>Optional Passaggio 9: chiudere un caso

Quando viene completata la causa legale o l'indagine supportata da un caso di eDiscovery, è possibile chiudere il caso. Ecco cosa succede quando si chiude un caso:
  
- Se il caso contiene eventuali posizioni di contenuto in attesa, tali esenzioni saranno disattivate. Potrebbe risultare che il contenuto venga eliminato o rimosso definitivamente, dall'utente o da un processo automatizzato, ad esempio un criterio di eliminazione.
    
- La chiusura di un caso disattiva solo le esenzioni associate a quel caso. Se altre esenzioni sono posizionate in una posizione di contenuto, ad esempio un blocco per controversia legale. un criterio di conservazione o un'esenzione da un caso di eDiscovery diverso) tali esenzioni verranno comunque mantenute.
    
- Il caso è ancora elencato nella pagina eDiscovery nel centro sicurezza & Compliance. Vengono mantenuti i dettagli, le esenzioni, le ricerche e i membri di un caso chiuso.
    
- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare i risultati della ricerca e preparare il risultato della ricerca per l'analisi in Advanced eDiscovery. La differenza principale tra casi attivi e chiusi consiste nel fatto che le esenzioni sono disattivate quando un caso viene chiuso.
    
Per chiudere un caso:
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic sul nome del caso che si desidera chiudere.
    
    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** . 
    
3. In **Manage case status**fare ![clic su Rimuovi il](../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) **caso di chiusura**del pulsante di visualizzazione.
    
    Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate al caso saranno disattivate.
    
4. Fare clic su **Sì** per chiudere il caso. 
    
    Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **attivo** a **chiusura**.
    
5. Chiudere la pagina **Gestisci questo caso** . 
    
6. Nella pagina **eDiscovery** fare ![](../media/O365-MDM-Policy-RefreshIcon.gif) **clic su Aggiorna icona Aggiorna** per aggiornare lo stato del caso chiuso. Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti. 
    
    Al termine del processo, lo stato della distinzione tra maiuscole e minuscole viene modificato in **chiuso** nella pagina **eDiscovery** . Fare di nuovo clic sul nome del caso per visualizzare la pagina Gestisci il riquadro a comparsa di **questo caso** , che contiene informazioni su quando il caso è stato chiuso e chi l'ha chiusa. 
     
## <a name="optional-step-10-re-open-a-closed-case"></a>Optional Passaggio 10: riaprire un caso chiuso

Quando si riapre un caso, tutte le esenzioni sul posto quando il caso è stato chiuso non verranno ripristinate automaticamente. Dopo la riapertura del caso, è necessario andare alla pagina di **attesa** e girare le stive precedenti. Per abilitare un'esenzione, selezionarla e fare clic **su attiva** nel riquadro dei dettagli. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic sul nome del caso che si desidera riaprire.
    
    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** . 
    
3. In **Manage case status**fare clic su **riapri caso**.
    
    Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate al caso in cui è stata chiusa non verranno attivate automaticamente.
    
4. Fare clic su **Sì** per riaprire il caso. 
    
    Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **chiuso** a **attivo**.
    
5. Chiudere la pagina **Gestisci questo caso** . 
    
6. Nella pagina **eDiscovery** fare ![](../media/O365-MDM-Policy-RefreshIcon.gif) **clic su Aggiorna icona Aggiorna** per aggiornare lo stato del caso riaperto. Per il completamento del processo di riapertura, potrebbero essere necessari fino a 60 minuti. 
    
    Al termine del processo, lo stato del caso viene modificato in **attivo** nella pagina **eDiscovery** . 
  
## <a name="optional-step-11-delete-a-case"></a>Optional Passaggio 11: eliminazione di un caso

È inoltre possibile eliminare i casi attivi e chiusi. Quando si elimina un caso, tutte le ricerche e le esportazioni nel caso vengono eliminate ed è stata rimossa dall'elenco dei casi nella pagina **eDiscovery** nel centro sicurezza & conformità. Non è possibile riaprire un caso eliminato. 

Prima di poter eliminare un caso (che sia attivo o chiuso), è necessario prima eliminare *tutti* gli appigli associati al caso. Che include l'eliminazione di esenzioni con stato **disattivata**. 

Per eliminare un'esenzione:

1. Andare alla scheda **esenzioni** nel caso in cui si desidera eliminare.

2. Fare clic sul blocco che si desidera eliminare.

3. Nella pagina a comparsa fare clic su **Elimina blocco**.

Per eliminare un caso:

1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic sul nome del caso che si desidera eliminare.

3. In **Gestione stato caso** nella pagina riquadro a comparsa fare clic su **Elimina caso**.

Se il caso in cui si sta tentando di eliminare contiene ancora le esenzioni, verrà visualizzato un messaggio di errore. Sarà necessario eliminare tutte le esenzioni associate al caso e quindi riprovare per eliminare il caso.

## <a name="more-information"></a>Altre informazioni

- **Esistono limiti per i casi di eDiscovery o per i detiene associati a un caso di eDiscovery?** Nella tabella seguente sono elencati i limiti per i casi di eDiscovery e le esenzioni del caso.
    
  |**Descrizione del limite**|**Tipo di limite**|
  |:-----|:-----|
  |Numero massimo di casi per un'organizzazione  <br/> |Nessun limite  <br/> |
  |Numero massimo di case conservate per un'organizzazione  <br/> |10.000  <br/> |
  |Numero massimo di cassette postali in un singolo blocco maiuscole/minuscole  <br/> |1,000  <br/> |
  |Numero massimo di siti di SharePoint e OneDrive for business in un unico blocco del caso  <br/> |100  <br/> |
   
- **Che dire dei casi creati nella pagina di gestione dei casi in Advanced eDiscovery?** È possibile accedere a un elenco dei casi di eDiscovery avanzati precedenti facendo clic sul collegamento nella parte inferiore della pagina **eDiscovery** nel centro sicurezza & conformità. Tuttavia, per eseguire qualsiasi operazione in un caso meno recente, è necessario contattare il supporto di Office 365 e richiedere che il caso venga spostato in un nuovo caso di eDiscovery nel centro sicurezza & Compliance. 
    
- **Perché creare un amministratore di eDiscovery?** Come indicato in precedenza, un amministratore di eDiscovery è membro del gruppo di ruoli Gestore di eDiscovery e può visualizzare e accedere a tutti i casi di eDiscovery nell'organizzazione. La possibilità di accedere a tutti i casi di eDiscovery ha due importanti scopi:
    
  - Se una persona che è l'unico membro di un caso di eDiscovery lascia l'organizzazione, nessuno (inclusi i membri del gruppo di ruoli Gestione organizzazione o un altro membro del gruppo di ruoli Gestore di eDiscovery) può accedere al caso di eDiscovery poiché non è membro di un caso. In questo caso, non esisterebbe alcun modo di accedere ai dati nel caso. Tuttavia, poiché un amministratore di eDiscovery può accedere a tutti i casi di eDiscovery nell'organizzazione, è possibile visualizzare il caso nel centro sicurezza & compliance e aggiungere se stessi o un altro responsabile di eDiscovery come membro del caso.
    
  - Poiché un amministratore di eDiscovery può visualizzare e accedere a tutti i casi di eDiscovery, è in grado di controllare e controllare tutti i casi e le ricerche di contenuto associate. Ciò può aiutare a evitare l'errato utilizzo di ricerche di contenuto o casi di eDiscovery. Inoltre, poiché gli amministratori di eDiscovery possono accedere a informazioni potenzialmente riservate nei risultati di una ricerca di contenuto, è opportuno limitare il numero di persone che sono amministratori di eDiscovery.
    
    Infine, come spiegato in precedenza, gli amministratori di eDiscovery nel centro sicurezza & Compliance vengono aggiunti automaticamente come amministratori in Advanced eDiscovery. Questo significa che una persona che è un amministratore di eDiscovery può eseguire attività amministrative in eDiscovery avanzata, ad esempio la configurazione degli utenti, la creazione di case e l'aggiunta di dati ai casi.
    
- **Quali sono i requisiti per la gestione delle licenze per il blocco dei percorsi di contenuto?** In generale, le organizzazioni richiedono un abbonamento a Office 365 E3 o versioni successive per inserire posizioni di contenuto in attesa. Per attivare il blocco delle cassette postali, è necessaria una licenza di Exchange Online piano 2 per la cassetta postale che si desidera inserire in attesa.
    
- **Cos'altro è necessario sapere sulla ricerca di tutti i contenuti del caso nel passaggio 5?** Come spiegato in precedenza, è possibile eseguire una ricerca nei percorsi di contenuto che sono stati inseriti in attesa nel caso. Quando si esegue questa operazione, solo il contenuto che corrisponde ai criteri di blocco è search. Se non è presente alcun criterio di conservazione, viene cercato tutto il contenuto. Se il contenuto è in un blocco basato su query, viene restituito solo il contenuto che corrisponde a entrambi i criteri di conservazione (dal blocco posto nel passaggio 4) e i criteri di ricerca (dalla ricerca nel passaggio 5).
    
    Di seguito sono riportate alcune considerazioni da tenere presenti quando si esegue la ricerca di tutti i contenuti del caso:
    
  - Se una posizione di contenuto fa parte di più riserve nello stesso caso, le query di blocco vengono combinate da un operatore **or** quando si esegue una ricerca nel percorso del contenuto utilizzando l'opzione tutti i contenuti di caso. Analogamente, se una posizione di contenuto fa parte di due diverse esenzioni, in cui una è basata su query e l'altra è una conservazione infinita (in cui tutto il contenuto viene messo in attesa), tutto il contenuto è una ricerca a causa del blocco infinito. 
    
  - Se si tratta di una ricerca di contenuto per un caso ed è stata configurata per la ricerca in tutti i contenuti del caso e quindi si modifica un blocco (aggiungendo o rimuovendo una posizione di contenuto o cambiando la query di blocco), la configurazione di ricerca verrà aggiornata con tali modifiche. Tuttavia, è necessario eseguire di nuovo la ricerca dopo che il blocco è stato modificato per aggiornare i risultati della ricerca.
    
  - Se più case sono posizionate in un percorso di contenuto in un caso di eDiscovery e si seleziona per eseguire la ricerca in tutti i contenuti del caso, il numero massimo di parole chiave per la query di ricerca è 500. Ciò è dovuto al fatto che la ricerca di contenuto combina tutte le esenzioni basate su query utilizzando l'operatore **or** . Se sono presenti più di 500 parole chiave nelle query di archiviazione combinata e nella query di ricerca del contenuto, viene cercato tutto il contenuto della cassetta postale, non solo il contenuto che corrisponde a qualsiasi caso basato su query. 
    
  - Se il blocco di un caso ha lo stato di **attivazione**, è comunque possibile eseguire la ricerca nei percorsi del contenuto del caso mentre il blocco è attivo.
    
  - Come indicato in precedenza, se una ricerca è configurata per la ricerca in tutti i contenuti del caso, non è possibile includere tale ricerca se si desidera esportare i risultati di più ricerche. Se una ricerca è configurata per la ricerca in tutti i contenuti del caso, è necessario esportare i risultati di tale singola ricerca.
    
- **Se una cassetta postale, un sito di SharePoint o un account di OneDrive che è in attesa viene spostato in un'area geografica diversa in un ambiente multi-geografico, il blocco verrà applicato ancora?** In tutti i casi, il contenuto di un account della cassetta postale, del sito o di OneDrive verrà comunque mantenuto. Tuttavia, le statistiche di archiviazione non includeranno più gli elementi provenienti da una posizione di contenuto che è stata spostata in un'altra area. Per includere statistiche di archiviazione per una posizione di contenuto che è stata spostata, è necessario modificare il blocco e aggiornare l'URL (o l'indirizzo SMTP di una cassetta postale) in modo che il percorso del contenuto venga di nuovo incluso nelle statistiche di blocco. 
    
- **Informazioni su come archiviare i gruppi di Office 365 e Microsoft teams.** Microsoft teams è basato sui gruppi di Office 365. Pertanto, l'inserimento di tali contenuti in un caso di eDiscovery è simile. Tenere presente quanto segue quando si immettono in attesa gruppi di Office 365 e Microsoft teams. 
    
  - Per inserire il contenuto presente nei gruppi di Office 365 e Microsoft teams in attesa, è necessario specificare la cassetta postale e il sito di SharePoint associato a un gruppo o a un team.
    
  - Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà di un gruppo di Office 365 o di un team di Microsoft. Questo è un ottimo metodo per ottenere l'URL del sito associato a un gruppo di Office 365 o a un team di Microsoft. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Office 365 denominato Senior Leadership Team: 
    
       ```text
       Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

       DisplayName            : Senior Leadership Team
       Alias                  : seniorleadershipteam
       PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
       SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
       ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroup**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura. 
  
  - Quando viene eseguita la ricerca della cassetta postale di un utente, qualsiasi gruppo di Office 365 o Microsoft Team di cui l'utente è membro non verrà cercato. Analogamente, quando si inserisce un gruppo di Office 365 o un blocco di Microsoft Team, solo la cassetta postale di gruppo e il sito del gruppo vengono inseriti in blocco. Le cassette postali e i siti di OneDrive for business dei membri del gruppo non vengono conservati a meno che non vengano aggiunti in modo esplicito all'esenzione. Pertanto, se si ha la necessità di disporre di un gruppo di Office 365 o di un team di Microsoft per un motivo legale, è consigliabile aggiungere le cassette postali e i siti di OneDrive for business per i membri del team e del gruppo nello stesso blocco.
    
  - Per ottenere un elenco dei membri di un gruppo di Office 365 o di un team di Microsoft, è possibile visualizzare le proprietà nella pagina **Home \> gruppi** nell'interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online: 
    
    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
    ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura. 
  
  - Le conversazioni che fanno parte di un canale Microsoft teams vengono memorizzate nella cassetta postale associata al team di Microsoft. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. Pertanto, è necessario inserire la cassetta postale di Microsoft Team e il sito di SharePoint in attesa per conservare le conversazioni e i file in un canale.
    
    In alternativa, le conversazioni che fanno parte dell'elenco chat in Microsoft teams vengono memorizzate nella cassetta postale dell'utente che partecipa alla chat. E i file che un utente condivide nelle conversazioni chat sono archiviati nel sito di OneDrive for business dell'utente che condivide il file. Pertanto, è necessario posizionare i singoli utenti e le cassette postali di OneDrive for business in attesa per conservare le conversazioni e i file nell'elenco chat. Questo è il motivo per cui è consigliabile applicare un blocco alle cassette postali dei membri di un team di Microsoft oltre a mettere in attesa la cassetta postale del team (e il sito).
    
    > [!IMPORTANT]
    > Gli utenti che partecipano a conversazioni che fanno parte dell'elenco chat in Microsoft teams devono disporre di una cassetta postale di Exchange Online (basata su cloud) per mantenere le conversazioni chat quando la cassetta postale viene inserita in un blocco di eDiscovery. Questo perché le conversazioni che fanno parte dell'elenco chat sono memorizzate nelle cassette postali basate sul cloud dei partecipanti alla chat. Se un partecipante alla chat non dispone di una cassetta postale di Exchange Online, non sarà in grado di mantenere le conversazioni chat. Ad esempio, in una distribuzione ibrida di Exchange, gli utenti che dispongono di una cassetta postale locale potrebbero essere in grado di partecipare a conversazioni che fanno parte dell'elenco chat in Microsoft teams. Tuttavia, in questo caso, il contenuto di queste conversazioni non può essere mantenuto perché gli utenti non dispongono di cassette postali basate sul cloud. 
  
  - Ogni canale di Microsoft Team o team contiene un wiki per la partecipazione alle note e la collaborazione. Il contenuto Wiki viene salvato automaticamente in un file con formato MHT. Il file è archiviato nella raccolta documenti di dati Wiki di Teams nel sito di SharePoint del team. È possibile inserire il contenuto nel wiki in attesa inserendo il sito di SharePoint del team in attesa.
    
    > [!NOTE]
    > La possibilità di conservare il contenuto wiki per un canale Microsoft Team o team (quando si posiziona il sito di SharePoint del team in attesa) è stata rilasciata il 22 giugno 2017. Se un sito del team è in attesa, il contenuto del wiki verrà mantenuto a partire da tale data. Tuttavia, se un sito del team è in attesa e il contenuto del wiki è stato eliminato entro il 22 giugno 2017, il contenuto del wiki non è stato mantenuto. 

- **Come trovare l'URL per i siti di OneDrive for business?** Per raccogliere un elenco degli URL per i siti di OneDrive for business nell'organizzazione, in modo da poterli aggiungere a un'esenzione o a una ricerca associata a un caso di eDiscovery, vedere [creare un elenco di tutte le posizioni di OneDrive nell'organizzazione](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Lo script in questo articolo crea un file di testo che contiene un elenco di tutti i siti di OneDrive. Per eseguire questo script, è necessario installare e usare SharePoint Online Management Shell. Assicurarsi di aggiungere l'URL del dominio MySite dell'organizzazione a ogni sito OneDrive che si desidera includere nella ricerca. Si tratta del dominio che contiene tutti i siti di OneDrive, ad esempio, `https://contoso-my.sharepoint.com`. Di seguito viene riportato un esempio di sito OneDrive di un utente: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
