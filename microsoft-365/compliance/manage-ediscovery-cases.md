---
title: Gestire i casi di eDiscovery nel Centro sicurezza e conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
ms.assetid: 9a00b9ea-33fd-4772-8ea6-9d3c65e829e6
description: Utilizzare il Centro sicurezza & conformità per creare le esenzioni di eDiscovery e per accedere e gestire i casi di eDiscovery nell'organizzazione.
ms.openlocfilehash: a2c276b80f5f713ad8c044aa8f1339413bb3f0bd
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686555"
---
# <a name="manage-ediscovery-cases-in-the-security--compliance-center"></a>Gestire i casi di eDiscovery nel Centro sicurezza e conformità

È possibile utilizzare i casi di eDiscovery nel centro sicurezza & Compliance per controllare gli utenti autorizzati a creare, accedere e gestire i casi di eDiscovery nell'organizzazione. Se l'organizzazione dispone di un abbonamento a Office 365 E5, è anche possibile utilizzare i casi di eDiscovery per analizzare i risultati della ricerca tramite Office 365 Advanced eDiscovery.
  
Un caso di eDiscovery consente di aggiungere membri a un caso, controllare i tipi di azione che i membri del caso specifico possono eseguire, conservare i percorsi di contenuti attinenti a un caso legale e associare più ricerche di contenuto a un caso singolo. È inoltre possibile esportare i risultati di una ricerca di contenuto associata a un caso oppure preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. I casi di eDiscovery sono un'ottima soluzione per limitare chi ha accesso a ricerche di contenuto e risultati della ricerca per un caso legale specifico nell'organizzazione.
  
Utilizzare il flusso di lavoro seguente per configurare e usare i casi di eDiscovery nel centro sicurezza & compliance e Advanced eDiscovery.
  
[Step 1: Assign eDiscovery permissions to potential case members](manage-ediscovery-cases.md#step1_1)
  
[Passaggio 2: creare un nuovo caso](manage-ediscovery-cases.md#step2_1)
  
[Passaggio 3: aggiungere membri a un caso](manage-ediscovery-cases.md#step2a_1)
  
[Passaggio 4: posizionare i percorsi di contenuto in attesa](manage-ediscovery-cases.md#step3_1)
  
[Passaggio 5: creare ed eseguire una ricerca di contenuto associata a un caso](manage-ediscovery-cases.md#step4_1)
  
[Passaggio 6: esportare i risultati di una ricerca di contenuto associata a un caso](manage-ediscovery-cases.md#step5_1)
  
[Passaggio 7: preparare i risultati della ricerca per Advanced eDiscovery](manage-ediscovery-cases.md#step7_1)
  
[Passaggio 8: passare alla causa in Advanced eDiscovery](manage-ediscovery-cases.md#gotoAeD_1)
  
[Optional Passaggio 9: chiudere un caso](manage-ediscovery-cases.md#closecase_1)
  
[Optional Passaggio 10: riaprire un caso chiuso](manage-ediscovery-cases.md#reopencase_1)
  
[Ulteriori informazioni](manage-ediscovery-cases.md#moreinfo_1)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Passaggio 1: Assegnare autorizzazioni di eDiscovery a potenziali membri del caso
<a name="step1_1"> </a>

Il primo passaggio consiste nell'assegnare le autorizzazioni appropriate relative a eDiscovery alle persone, in modo da poterle aggiungere a un caso di eDiscovery nel passaggio 2. È necessario essere membri del gruppo di ruoli Gestione organizzazione (o essere assegnati al ruolo di gestione dei ruoli) nel centro sicurezza & conformità per assegnare le autorizzazioni di eDiscovery. Nell'elenco seguente vengono descritti i gruppi di ruoli correlati a eDiscovery nel centro sicurezza & Compliance.
  
- **Revisione di un revisore** Questo gruppo di ruoli ha le autorizzazioni più restrittive relative a eDiscovery. I membri di questo gruppo possono visualizzare e aprire solo l'elenco dei casi nella pagina **eDiscovery** nel centro sicurezza & conformità di cui sono membri. Non è possibile creare casi, aggiungere membri a un caso, creare esenzioni, creare ricerche, esportare i risultati della ricerca o preparare i risultati per Advanced eDiscovery. Tuttavia, i membri possono accedere ai casi in Advanced eDiscovery per eseguire attività di analisi. 
    
- **eDiscovery Manager** I membri di questo gruppo di ruoli possono creare e gestire i casi di eDiscovery. Possono aggiungere e rimuovere membri, inserire posizioni di contenuto in attesa, creare e modificare le ricerche di contenuto associate a un caso, esportare i risultati di una ricerca di contenuto e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. In questo gruppo di ruoli sono disponibili due sottogruppi. La differenza tra questi sottogruppi dipende dall'ambito.
    
  - **eDiscovery Manager** È possibile visualizzare e gestire i casi di eDiscovery in cui creano o sono membri di. Se un altro Manager di eDiscovery crea un caso ma non aggiunge un secondo Manager di eDiscovery come membro del caso, il secondo responsabile di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina **eDiscovery** del centro sicurezza & Compliance. i responsabili di eDiscovery possono inoltre accedere ai propri casi in Advanced eDiscovery per eseguire attività di analisi. 
    
  - **amministratore di eDiscovery** È in grado di eseguire tutte le attività di gestione dei casi che un Manager di eDiscovery può eseguire. Inoltre, un amministratore di eDiscovery è in grado di:
    
  - Visualizzare tutti i casi elencati nella pagina **eDiscovery**. 
    
  - Gestire qualsiasi caso di eDiscovery nell'organizzazione dopo che si è aggiunto come membro del caso.
    
  - Eseguire le attività amministrative in Advanced eDiscovery, ad esempio i dati dei casi di elaborazione per l'analisi, la configurazione delle impostazioni dei casi e l'esportazione di dati da Advanced eDiscovery. Ciò è dovuto al fatto che una persona che è un amministratore di eDiscovery nel centro sicurezza & conformità viene aggiunta automaticamente come amministratore in Advanced eDiscovery.
    
    Vedere la sezione [More information](manage-ediscovery-cases.md#moreinfo_1) per conoscere i motivi per cui si potrebbe voler diventare un amministratore di eDiscovery nell'organizzazione. 
    
> [!IMPORTANT]
> Se una persona non è un membro di uno di questi gruppi di ruoli correlati a eDiscovery o non è un membro di un gruppo di ruoli a cui è assegnato il ruolo Reviewer, non è possibile aggiungerli come membri di un caso di eDiscovery. 
  
 **Per assegnare autorizzazioni di eDiscovery:**
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel centro sicurezza & conformità fare clic su **autorizzazioni**e quindi eseguire una delle operazioni seguenti in base alle autorizzazioni di eDiscovery che si desidera assegnare.
    
  - Per assegnare le autorizzazioni per il revisore, selezionare il gruppo di ruoli **reviewer** e quindi fare clic su **modifica**accanto a **membri** . Fare clic su **Scegli membri**, fare ![clic su Aggiungi icona](media/ITPro-EAC-AddIcon.gif) Aggiungi selezionare l'utente che si desidera aggiungere al gruppo di ruoli reviewer e quindi fare clic su **Aggiungi**. ****
    
  - Per assegnare le autorizzazioni di eDiscovery Manager, selezionare il gruppo di ruoli **gestione eDiscovery** , quindi fare clic su **modifica**accanto a **eDiscovery Manager**. Fare clic su **Scegli eDiscovery Manager**, fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) * * Aggiungi * *, selezionare l'utente che si desidera aggiungere come Manager di eDiscovery e quindi fare clic su **Aggiungi**.
    
  - Per assegnare le autorizzazioni di amministratore di eDiscovery, selezionare il gruppo di ruoli **gestione di eDiscovery** e quindi fare clic su **modifica**accanto a **amministratore di eDiscovery**. Fare clic su **Scegli amministratore**di ![eDiscovery,](media/ITPro-EAC-AddIcon.gif) fare clic su **Aggiungi icona Aggiungi**, selezionare l'utente che si desidera aggiungere come amministratore di eDiscovery e quindi fare clic su **Aggiungi**.
    
4. Dopo aver aggiunto tutti gli utenti, fare clic su **fine**, fare clic su **Salva** per salvare le modifiche apportate al gruppo di ruoli e quindi fare clic su **Chiudi**.
    

  
## <a name="step-2-create-a-new-case"></a>Passaggio 2: creare un nuovo caso
<a name="step2_1"> </a>

Il passaggio successivo consiste nel creare un nuovo caso di eDiscovery. È necessario essere un membro del gruppo di ruoli Gestore di eDiscovery per creare casi di eDiscovery. Come spiegato in precedenza, dopo aver creato un nuovo caso nel centro sicurezza & Compliance, l'utente (e altri membri del caso) sarà in grado di accedere allo stesso caso in Advanced eDiscovery se l'organizzazione ha un abbonamento a Office 365 E5.
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery**, quindi fare ![clic su](media/ITPro-EAC-AddIcon.gif) Aggiungi icona **creare un caso**.
    
4. Nella pagina **nuovo caso** , assegnare un nome al caso, digitare una descrizione facoltativa, quindi fare clic su **Salva**. Tenere presente che il nome del caso deve essere univoco nell'organizzazione.
    
    ![Pagina nuovo caso](media/538f66b8-eb6e-4c4c-83d8-7154fd85883a.png)
  
    Il nuovo caso viene visualizzato nell'elenco dei casi nella pagina **eDiscovery** . Si noti che è possibile posizionare il puntatore del mouse su un nome di case per visualizzare le informazioni sul caso, incluso lo stato del caso ( **attivo** o **chiuso**), la descrizione del caso (creato nel passaggio precedente) e quando il caso è stato modificato per ultimo e chi lo ha modificato.
    
    > [!TIP]
    > Dopo aver creato un nuovo caso, è possibile rinominarlo in qualsiasi momento. Basta fare clic sul nome del caso nella pagina **eDiscovery** . Nella pagina **Gestisci** il riquadro a comparsa di questo caso, modificare il nome visualizzato nella casella in **nome**e quindi salvare la modifica. 
  
## <a name="step-3-add-members-to-a-case"></a>Passaggio 3: aggiungere membri a un caso
<a name="step2a_1"> </a>

Dopo aver creato un nuovo caso, il passaggio successivo consiste nell'aggiungere membri al caso. Come spiegato in precedenza, solo gli utenti membri dei gruppi di ruoli revisore o Manager di eDiscovery possono essere aggiunti come membri del caso. Si noti che il responsabile di eDiscovery che ha creato il caso viene aggiunto automaticamente come membro.
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic sul nome del caso in cui si desidera aggiungere i membri.
    
    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** . 
    
    ![Fare clic sul nome del caso per visualizzare la pagina Gestisci questo caso](media/2364dc08-a3dc-4724-acf4-7a68c8588e6f.png)
  
3. In **Gestisci membri**fare ![clic su](media/ITPro-EAC-AddIcon.gif) **Aggiungi icona Aggiungi** per aggiungere membri al caso. 
    
4. Nell'elenco di utenti che possono essere aggiunti come membri del caso, fare clic sulla casella di controllo accanto al nome degli utenti che si desidera aggiungere al caso.
    
    > [!TIP]
    > Se si dispone di un elenco elevato di utenti che possono essere aggiunti come membri, utilizzare la casella di **ricerca** per cercare una persona specifica nell'elenco. 
  
5. Dopo aver selezionato gli utenti da aggiungere come membri del gruppo, fare clic su **Aggiungi**.
    
    In **Gestisci questo caso**, fare clic su **Salva** per salvare il nuovo elenco dei membri del caso. 
    
6. Fare clic su **Salva** per salvare il nuovo elenco dei membri del caso. 
  
## <a name="step-4-place-content-locations-on-hold"></a>Passaggio 4: posizionare i percorsi di contenuto in attesa
<a name="step3_1"> </a>

È possibile utilizzare un caso eDiscovery per creare blocchi al fine di conservare contenuti che potrebbero essere attinenti al caso. È possibile applicare un blocco alle cassette postali e ai siti di OneDrive for business di persone che sono depositarie nel caso. È inoltre possibile inserire un blocco nel sito di gruppo cassetta postale, sito di SharePoint e OneDrive for business per un gruppo di Office 365. Analogamente, è possibile applicare un'esenzione alla cassetta postale e al sito associati a Microsoft teams. Quando si posizionano le posizioni di contenuto in attesa, il contenuto viene mantenuto fino a quando non viene rimosso il blocco dal percorso del contenuto o fino a quando non viene eliminato il blocco.
  
Quando si crea un'esenzione, sono disponibili le opzioni seguenti per l'ambito del contenuto conservato nei percorsi di contenuto specificati:
  
- È possibile creare un'esenzione infinita in cui tutto il contenuto viene messo in attesa. In alternativa, è possibile creare un blocco basato su query che contenga solo il contenuto che corrisponde a una query di ricerca.
    
- È possibile specificare un intervallo di date che contenga solo il contenuto che è stato inviato, ricevuto o creato all'interno di tale intervallo di date. In alternativa, è possibile conservare tutto il contenuto indipendentemente dal momento in cui è stato inviato, ricevuto o creato.
    
> [!NOTE]
> È possibile disporre di un massimo di 10.000 criteri di blocco in tutti i casi di eDiscovery nell'organizzazione. 
  
Per creare un'esenzione per un caso di eDiscovery:
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera creare le esenzioni. 
    
3. Nella **Home** page del caso, fare clic su **Hold**.
    
    ![Fare clic su esenzione per visualizzare la pagina delle esenzioni del caso.](media/25c0300a-bd33-4443-a121-d595b1a3e00f.png)
  
4. Nella pagina **blocco** fare clic su **nuova**![icona](media/ITPro-EAC-AddIcon.gif)Aggiungi.
    
5. Nella pagina **Crea un nuovo blocco**, assegnare un nome al blocco. Il nome del blocco deve essere univoco nell'organizzazione. 
    
6. Scegliere i percorsi di contenuto che si desidera inserire in attesa. È possibile inserire le cassette postali, i siti e le cartelle pubbliche in attesa.
    
    ![Scegliere i percorsi dei contenuti da mettere in attesa](media/a00c952c-f91f-4708-b5a4-6213e4c413c7.png)
  
1. **Cassette postali** Fare ****![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona per specificare le cassette postali da inserire in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione (per inserire un'esenzione nelle cassette postali dei membri del gruppo) per effettuare il blocco. È inoltre possibile inserire un blocco sulla cassetta postale associata per un gruppo di Office 365 o un team di Microsoft. 
    
    > [!NOTE]
    > Quando si fa ****![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona per specificare le cassette postali da inserire in attesa, lo strumento di selezione delle cassette postali visualizzato è vuoto. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere persone a questo elenco, digitare un nome (almeno 3 caratteri) nella casella di ricerca **e fare clic**![su icona](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)ricerca ricerca. 
  
2. **Siti** Fare ****![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona per specificare i siti di SharePoint e OneDrive for business da inserire in attesa. Digitare l'URL per ogni sito che si desidera conservare. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un gruppo di Office 365 o un team di Microsoft. 
    
    Vedere la sezione [ulteriori informazioni](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da.aspx#moreinfo_1) per suggerimenti su come mettere in attesa i gruppi di Office 365 e Microsoft teams. 
    
    > [!NOTE]
    > Nel caso raro che il nome dell'entità utente (UPN, User Principal Name) di una persona venga modificato, l'URL per il relativo account OneDrive verrà modificato anche per incorporare il nuovo UPN. In questo caso, è necessario modificare il blocco aggiungendo il nuovo URL di OneDrive dell'utente e rimuovendo quello precedente. 
  
3. **Cartelle pubbliche** Fare clic su **blocca tutte le cartelle pubbliche** per conservare tutte le cartelle pubbliche nell'organizzazione di Exchange Online. Si noti che non è possibile scegliere le cartelle pubbliche specifiche da mettere in attesa. Lasciare selezionata l'opzione **non mantenere le cartelle pubbliche** se non si desidera inserire un blocco nelle cartelle pubbliche. 
    
7. Dopo aver aggiunto i percorsi di contenuto all'esenzione, fare clic su **Avanti**.
    
8. Per creare un blocco basato su query con condizioni, completare quanto segue. In caso contrario, è sufficiente fare clic su **fine** per contenere tutto il contenuto. 
    
    ![Creare un blocco basato su query specificando le parole chiave e le condizioni](media/a5bb802e-2e96-4f12-8b33-1ddd671638e4.png)
  
    Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).
    
1. Nella casella in **che cosa si desidera cercare?**, digitare una query di ricerca nella casella in modo che solo il contenuto che soddisfa i criteri di ricerca venga messo in attesa. È possibile specificare le parole chiave, le proprietà del messaggio o le proprietà del documento, ad esempio i nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio **e**, **o**o **meno**. Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà messo in attesa. 
    
2. In **condizioni**fare clic su **Aggiungi condizione** per aggiungere una o più condizioni per limitare la query di ricerca per il blocco. Ogni condizione aggiunge una clausola alla query di ricerca di KQL che viene creata e eseguita quando si crea il blocco. Ad esempio, è possibile specificare un intervallo di date in modo che i documenti di posta elettronica o di sito creati entro la data di intervallo siano stati inseriti in attesa. Una condizione è collegata logicamente alla query con parola chiave (specificata nella relativa casella) dall'operatore **AND**. Questo significa che gli elementi devono soddisfare sia la query di parole chiave che la condizione da inserire in attesa. 
    
9. Dopo aver configurato un blocco basato su query, fare clic su **fine** per creare il blocco. 
  
### <a name="hold-statistics"></a>Statistiche di blocco

Dopo un po' di tempo, le informazioni relative al nuovo blocco vengono visualizzate nel riquadro dei dettagli nella pagina **esenzioni** per il blocco selezionato. Queste informazioni includono il numero di cassette postali e i siti in attesa e le statistiche sul contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi che sono stati messi in attesa e l'ultima volta che sono state calcolate le statistiche di blocco. Queste statistiche di blocco consentono di identificare la quantità di contenuto correlata al caso di eDiscovery. 
  
![Le statistiche di blocco vengono visualizzate nel riquadro dei dettagli per il blocco selezionato](media/e46359a3-cba1-4771-bbf5-bc53b4a2cb14.png)
  
Tenere presenti le considerazioni seguenti sulle statistiche di archiviazione:
  
- Il numero totale di elementi in attesa indica il numero di elementi provenienti da tutte le origini di contenuto che vengono bloccate. Se è stata creata una conservazione basata su query, questa statistica indica il numero di elementi che corrispondono alla query.
    
- Il numero di elementi in attesa include anche gli elementi non indicizzati trovati nei percorsi di contenuto. Si noti che se si crea un blocco basato su query, tutti gli elementi non indicizzati nei percorsi di contenuto vengono inseriti in attesa. Sono inclusi gli elementi non indicizzati che non corrispondono ai criteri di ricerca di un blocco basato su query e di elementi non indicizzati che potrebbero non essere compresi in una condizione dell'intervallo di date. Questo è diverso da quello che succede quando si esegue una ricerca di contenuto, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o sono esclusi da una condizione dell'intervallo di date non sono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzati, vedere [elementi non indicizzati in ricerca contenuto in Office 365](partially-indexed-items-in-content-search.md).
    
- È possibile ottenere le statistiche di blocco più recenti facendo clic su **Aggiorna statistiche** per rieseguire una stima di ricerca che calcola il numero corrente di elementi in attesa. Se necessario **, fare clic su**![Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) icona di aggiornamento sulla barra degli strumenti per aggiornare le statistiche di blocco nel riquadro dei dettagli. 
    
- È normale che il numero di elementi in attesa aumenti nel tempo, in quanto gli utenti la cui cassetta postale o sito è in attesa vengono in genere inviati o ricevuti da un nuovo messaggio di posta elettronica e dalla creazione di nuovi documenti di SharePoint e OneDrive for business.
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a>Passaggio 5: creare ed eseguire una ricerca di contenuto associata a un caso
<a name="step4_1"> </a>

Dopo aver creato un caso di eDiscovery, e archiviato i depositari correlati al caso, è possibile creare ed eseguire una o più ricerche di contenuto associate al caso. Le ricerche di contenuto associate a un caso non sono elencate nella pagina di **ricerca** nel centro sicurezza & conformità. Ciò significa che possono accedere alle ricerche di contenuto associate a un caso solo i membri del caso che sono anche membri del gruppo di ruoli Gestore di eDiscovery. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera creare una ricerca di contenuto. 
    
3. Nella **Home** page del caso, fare clic su **Cerca**.
    
    ![Nella Home page del caso, fare clic su Cerca](media/bd358eb3-12d4-4f0c-8317-d192286813d0.png)
  
4. Nella pagina **ricerca** fare clic su **nuova**![icona](media/ITPro-EAC-AddIcon.gif)Aggiungi.
    
5. Nella pagina **nuova ricerca** , digitare un nome per la ricerca. Le ricerche di contenuto associate a un caso devono avere nomi univoci all'interno dell'organizzazione di Office 365. 
    
6. Scegliere i percorsi di contenuto di cui si desidera eseguire la ricerca. È possibile cercare le cassette postali, i siti e le cartelle pubbliche nella stessa ricerca.
    
    ![Percorsi di contenuto di ricerca, tutti i percorsi di contenuto o seleziona percorsi di contenuto specifici](media/08c523dc-cba8-4fce-aee6-f86251204393.png)
  
1. **Tutti i contenuti del caso** Selezionare questa opzione per cercare tutti i percorsi di contenuto che sono stati inseriti in attesa nel caso. Se il caso contiene più esenzioni, i percorsi di contenuto di tutte le esenzioni verranno ricercati quando si seleziona questa opzione. Inoltre, se un percorso di contenuto è stato posizionato in un blocco basato su query, vengono ricercati solo gli elementi che sono in attesa quando si esegue la ricerca di contenuto che si sta creando in questo passaggio. Ad esempio, se un utente è stato inserito in una conservazione basata su query che conserva gli elementi inviati o creati prima di una data specifica, solo gli elementi verranno ricercati utilizzando i criteri di ricerca della ricerca contenuto. Questa operazione viene eseguita collegando la query di blocco del caso e la query di ricerca del contenuto da parte di un operatore **and** . Vedere la sezione [ulteriori informazioni](manage-ediscovery-cases.md#moreinfo_1) alla fine di questo articolo per ulteriori informazioni sulla ricerca di contenuto del caso. 
    
2. **Cerca ovunque** Selezionare questa opzione per eseguire la ricerca in tutti i percorsi di contenuto dell'organizzazione. Quando si seleziona questa opzione, è possibile scegliere di effettuare una ricerca in tutte le cassette postali di Exchange (incluse le cassette postali per tutti i gruppi di Office 365 e Microsoft Teams), tutti i siti di SharePoint e OneDrive for business (che include i siti per tutti i gruppi di Office 365 e Microsoft Teams) e tutte le cartelle pubbliche.
    
3. **Selezione percorso personalizzato** Selezionare questa opzione per selezionare le cassette postali e i siti in cui si desidera eseguire la ricerca. Quando si seleziona questa opzione, l'elenco delle cassette postali e dei siti viene prepopolato con i percorsi di contenuto che sono stati inseriti nel caso. È inoltre possibile scegliere di effettuare una ricerca in tutte le cartelle pubbliche dell'organizzazione.
    
    ![Cerca in tutti i contenuti del caso, Cerca in tutte le posizioni o Cerca un percorso personalizzato](media/7ca97ab4-52d5-46a5-9e24-e3a4d1001595.png)
  
    Tuttavia, se si seleziona questa opzione e si esegue una ricerca in qualsiasi posizione di contenuto che è in attesa, qualsiasi query proveniente da un blocco di caso basato su query non verrà applicata alla query di ricerca. In altre parole, viene cercato tutto il contenuto di una posizione, non solo il contenuto che viene conservato da un blocco di caso basato su query.
    
    È possibile rimuovere i percorsi di contenuto precompilati oppure aggiungerne di nuovi. Se si sceglie questa opzione, è inoltre possibile eseguire la ricerca in tutti i percorsi di contenuto per un servizio specifico, ad esempio la ricerca in tutte le cassette postali di Exchange, oppure cercare percorsi di contenuto specifici per un servizio. È anche possibile scegliere se eseguire la ricerca nelle cartelle pubbliche dell'organizzazione.
    
    Tenere presente queste considerazioni quando si aggiungono percorsi di contenuto alla ricerca:
    
  - Quando si fa ****![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona per specificare le cassette postali da cercare, lo strumento di selezione delle cassette postali visualizzato è vuoto. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere destinatari all'elenco, digitare un nome, almeno 3 caratteri, nella casella di ricerca **e fare clic**![su icona](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)ricerca ricerca.
    
  - È possibile aggiungere le cassette postali inattive, i gruppi di Office 365, Microsoft teams e i gruppi di distribuzione all'elenco delle cassette postali da cercare. Non sono supportati i gruppi di distribuzione dinamici. Se si aggiungono gruppi di Office 365 o Microsoft teams, viene eseguita la ricerca nella cassetta postale del gruppo o del team. le cassette postali dei membri del gruppo non vengono cercate.
    
  - Se non si desidera includere cassette postali o siti in una ricerca, selezionare **scegliere le cassette postali specifiche per** la ricerca oppure **scegliere siti specifici per la ricerca**, ma non aggiungere cassette postali o siti all'elenco.
    
  - Per aggiungere siti, ****![fare clic su](media/ITPro-EAC-AddIcon.gif) Aggiungi icona e quindi digitare l'URL per ogni sito di cui si desidera eseguire la ricerca. È inoltre possibile aggiungere l'URL per il sito di SharePoint per i gruppi di Office 365 e Microsoft teams. 
    
7. Dopo aver selezionato i percorsi di contenuto in cui eseguire la ricerca, fare clic su **Avanti**.
    
8. Nella pagina **Nuova ricerca**, è possibile aggiungere parole chiave e condizioni per creare la query di ricerca. <br/>![Criteri e condizioni di ricerca](media/9064147e-feac-4090-bbf6-2298ad7622c6.png)
  
9. Nella casella in **Cosa vuoi cercare?**, digitare una query di ricerca. È possibile specificare parole chiave, proprietà dei messaggi come le date di invio o ricezione o proprietà dei documenti come il nome file o la data dell'ultima modifica apportata. È possibile utilizzare una query più complessa che utilizza un operatore booleano, ad esempio **e**, **o**, **non**, **vicino**o **ONEAR**. È inoltre possibile cercare informazioni sensibili (ad esempio numeri di codice fiscale) nei documenti o cercare documenti condivisi esternamente. Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà incluso nei risultati della ricerca. 
    
10. È possibile fare clic sulla casella di controllo **Mostra elenco parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono connesse dall'operatore **or** nella query di ricerca creata. 
    
    ![Parole chiave di ricerca](media/c3ef511a-e0a3-4b5d-9779-36803270a193.png)
  
    Perché usare l'elenco di parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. Questo è utile per identificare rapidamente le parole chiave più e meno efficaci. È possibile usare anche una frase chiave, racchiusa tra parentesi, in una riga. Per altre informazioni sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave per i risultati di Ricerca contenuto](view-keyword-statistics-for-content-search.md).
    
    Per ulteriori informazioni sull'utilizzo dell'elenco delle parole chiave, vedere [ulteriori informazioni](run-a-content-search-in-the-security-and-compliance-center.md#moreinfo).
    
11. Fare clic su **Controlla query per errori di battitura** per controllare la query per i caratteri non supportati e per gli operatori booleani che potrebbero non essere capitalizzati. I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o la restituzione di risultati indesiderati. Per altre informazioni sui caratteri non supportati controllati, vedere [Verificare la presenza di errori nella query Ricerca contenuto](check-your-content-search-query-for-errors.md).
    
12. In **condizioni**, aggiungere condizioni a una query di ricerca per restringere una ricerca e restituire un set di risultati più raffinato. Ogni condizione consente di aggiungere una clausola alla query di ricerca KQL creata ed eseguita quando si avvia la ricerca. Una condizione è logicamente connessa alla query con parole chiave (specificata nella casella delle parole chiave) mediante l'operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia la condizione. Ecco come le condizioni consentono di circoscrivere i risultati. 
    
    Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
13. Fare clic su **Ricerca** per salvare le impostazioni di ricerca e avviare la ricerca. 
    
    Viene avviata la ricerca. Dopo un po' di tempo, una stima dei risultati della ricerca viene visualizzata nel riquadro dei dettagli. La stima include la dimensione totale e il numero di elementi che corrispondono ai criteri di ricerca. La stima della ricerca include anche il numero di elementi non indicizzati nei percorsi di contenuto di cui è stata eseguita la ricerca. Il numero di elementi non indicizzati (che non corrispondono ai criteri di ricerca) verrà incluso nelle statistiche della ricerca visualizzate nel riquadro dei dettagli. Se un elemento non indicizzato corrisponde alla query di ricerca (perché altre proprietà del messaggio o del documento soddisfano i criteri di ricerca), non verrà incluso nel numero stimato di elementi non indicizzati. Se un elemento non indicizzato è escluso dai criteri di ricerca, non verrà incluso nella stima degli elementi non indicizzati.
    
    Una volta completata la ricerca, è possibile visualizzare in anteprima i risultati della ricerca. Se necessario **, fare clic su**![Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) l'icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli. 
  
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a>Passaggio 6: esportare i risultati di una ricerca di contenuto associata a un caso
<a name="step5_1"> </a>

Dopo aver eseguito correttamente una ricerca, è possibile esportare i risultati della ricerca. Quando si esportano i risultati della ricerca, gli elementi della cassetta postale vengono scaricati nei file PST o come singoli messaggi. Quando si esporta contenuto da siti di SharePoint e OneDrive for business, vengono esportate copie dei documenti di Office native e di altri documenti. Viene esportato anche un file manifesto (in formato XML) che contiene informazioni su tutti i risultati della ricerca.
  
È possibile esportare i risultati di un' [esportazione dei risultati di una singola ricerca associata a un caso](manage-ediscovery-cases.md#singlesearch_1) oppure è possibile esportare i risultati dell' [esportazione dei risultati di più ricerche associate a un caso](manage-ediscovery-cases.md#multiplesearches_1).
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a>Esportare i risultati di una singola ricerca associata a un caso
<a name="singlesearch_1"> </a>

1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso da cui si desidera esportare la ricerca. 
    
3. Nella **Home** page del caso, fare clic su **Cerca**.
    
4. Nell'elenco delle ricerche per il caso, fare clic sulla ricerca di cui si desidera esportare i risultati della ricerca, **fare clic**![su Esporta esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)dei risultati della ricerca, quindi fare clic su **Esporta i risultati**.
    
    Viene visualizzata la pagina **Esportare i risultati della ricerca**. Il flusso di lavoro per l’esportazione dei risultati di una ricerca di contenuto associata a un caso è lo stesso di quando si esportano i risultati della ricerca per una ricerca sulla pagina **Ricerca contenuto**. Per istruzioni dettagliate, vedere [Export Search Results from the Security & Compliance Center](export-search-results.md).
    
    > [!NOTE]
    > Quando si esportano i risultati della ricerca, è possibile abilitare la deduplicazione in modo che venga esportata una sola copia di un messaggio di posta elettronica anche se sono state trovate più istanze dello stesso messaggio nelle cassette postali di cui è stata eseguita la ricerca. Per ulteriori informazioni sulla deduplicazione e sulla modalità di identificazione degli elementi duplicati, vedere [de-duplication nei risultati della ricerca di eDiscovery](de-duplication-in-ediscovery-search-results.md). 
  
5. Dopo aver avviato l'esportazione, fare clic su **Esporta** per visualizzare l'elenco dei processi di esportazione esistenti per questo caso. 
    
    ![Fare clic su Esporta per visualizzare un elenco dei processi di esportazione](media/b7b95bf7-134e-471e-961e-f86c1bb633eb.png)
  
    Potrebbe essere **necessario fare clic su**![aggiorna l'](media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare l'elenco dei processi di esportazione per visualizzare il processo di esportazione appena creato. Si noti che i processi di esportazione hanno lo stesso nome della ricerca di contenuto corrispondente con **_Export** accodati alla fine del nome della ricerca. 
    
6. Fare clic sul processo di esportazione appena creato per visualizzare le informazioni sullo stato nel riquadro dei dettagli. Queste informazioni includono la percentuale di elementi che sono stati trasferiti in un'area di archiviazione di Azure nel cloud Microsoft.
    
    Dopo aver trasferito tutti gli elementi, fare clic su **Scarica risultati esportati** per scaricare i risultati della ricerca nel computer locale. Per ulteriori informazioni, vedere il passaggio 2 in [Export Search Results from the Security & Compliance Center](export-search-results.md)
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a>Esportare i risultati di più ricerche associate a un caso
<a name="multiplesearches_1"> </a>

Come alternativa all'esportazione dei risultati di una singola ricerca di contenuto associata a un caso, è possibile esportare i risultati di più ricerche dallo stesso caso in una singola esportazione. L'esportazione dei risultati di più ricerche è più semplice e veloce rispetto all'esportazione dei risultati di una ricerca alla volta.
  
> [!NOTE]
> Non è possibile esportare i risultati di più ricerche se una di queste ricerche è stata configurata per la ricerca in tutti i contenuti del caso. esportare solo i risultati di più ricerche per le ricerche associate a un caso di eDiscovery. Non è possibile esportare i risultati di più ricerche elencate nella pagina **Ricerca contenuto** nel centro sicurezza & conformità. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso da cui si desidera esportare la ricerca. 
    
3. Nella **Home** page del caso, fare clic su **Cerca**.
    
4. Nell'elenco delle ricerche per il caso, selezionare due o più ricerche da cui si desidera esportare i risultati della ricerca.
    
    > [!NOTE]
    > Per selezionare più ricerche, premere **CTRL** quando si fa clic su ogni ricerca. In alternativa, è possibile selezionare più ricerche adiacenti facendo clic sulla prima ricerca, tenendo premuto il tasto **MAIUSC** e quindi facendo clic sull'ultima ricerca. 
  
5. Dopo aver selezionato le ricerche, fare clic su **Esporta**![esportazione dei](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)risultati della ricerca, quindi fare clic su **Esporta i risultati**.
    
6. Viene visualizzata la pagina * * Export results for *n* searches * *, dove *n* è il numero di ricerche per cui si stanno esportando i risultati. Si noti che è necessario assegnare un nome al processo di esportazione. 
    
    Il flusso di lavoro per esportare i risultati da più ricerche di contenuto associate a un caso equivale all'esportazione dei risultati della ricerca per una singola ricerca. Per istruzioni dettagliate, vedere [Export Search Results from the Security & Compliance Center](export-search-results.md).
    
    > [!NOTE]
    > Quando si esportano i risultati della ricerca da più ricerche associate a un caso, è anche possibile abilitare la deduplicazione in modo che venga esportata una sola copia di un messaggio di posta elettronica anche se sono state trovate più istanze dello stesso messaggio nel cassette postali di cui è stata eseguita la ricerca in una o più ricerche. Per ulteriori informazioni sulla deduplicazione e sulla modalità di identificazione degli elementi duplicati, vedere [de-duplication nei risultati della ricerca di eDiscovery](de-duplication-in-ediscovery-search-results.md). 
  
7. Dopo aver avviato l'esportazione, fare clic su **Esporta** per visualizzare l'elenco dei processi di esportazione che per questo caso. 
    
    ![Fare clic su Esporta per visualizzare un elenco dei processi di esportazione](media/b7b95bf7-134e-471e-961e-f86c1bb633eb.png)
  
    Potrebbe essere **necessario fare clic su**![aggiorna l'](media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare l'elenco dei processi di esportazione per visualizzare il processo di esportazione appena creato. Si noti che le ricerche incluse nel processo di esportazione sono elencate nella colonna **ricerche** . 
    
8. Fare clic sul processo di esportazione appena creato per visualizzare le informazioni sullo stato nel riquadro dei dettagli. Queste informazioni includono la percentuale di elementi che sono stati trasferiti in un'area di archiviazione di Azure nel cloud Microsoft.
    
9. Dopo aver trasferito tutti gli elementi, fare clic su **Scarica risultati esportati** per scaricare i risultati della ricerca nel computer locale. Per ulteriori informazioni, vedere il passaggio 2 in [Export Search Results from the Security & Compliance Center](export-search-results.md)
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Ulteriori informazioni sull'esportazione dei risultati di più ricerche

- Quando si esportano i risultati di più ricerche, le query di ricerca provenienti da tutte le ricerche vengono combinate **tramite gli operatori e** quindi viene avviata la ricerca combinata. I risultati stimati della ricerca combinata vengono visualizzati nel riquadro dei dettagli del processo di esportazione selezionato. I risultati della ricerca vengono quindi trasferiti nell'area di archiviazione di Azure nel cloud Microsoft. Anche lo stato del trasferimento viene visualizzato nel riquadro dei dettagli. Come indicato in precedenza, dopo che tutti i risultati della ricerca sono stati trasferiti, è possibile scaricarli nel computer locale. 
    
- Il numero massimo di parole chiave delle query di ricerca per tutte le ricerche che si desidera esportare è 500. (questo è lo stesso limite per una singola ricerca contenuto). Ciò è dovuto al fatto che il processo di esportazione combina tutte le query di ricerca utilizzando l'operatore **or** . Se si supera questo limite, verrà restituito un errore. In questo caso, sarà necessario esportare i risultati da meno ricerche o semplificare le query di ricerca delle ricerche che si desidera esportare. 
    
- I risultati della ricerca esportati sono organizzati dall'origine di contenuto in cui è stato trovato l'elemento. Questo significa che un'origine di contenuto nei risultati di esportazione potrebbe avere elementi restituiti da ricerche diverse. Ad esempio, se si è scelto di esportare i messaggi di posta elettronica in un unico file PST per ogni cassetta postale, il file PST potrebbe avere risultati da più ricerche.
    
- Se lo stesso elemento di posta elettronica o documento proveniente dallo stesso percorso di contenuto viene restituito da più di una delle ricerche esportate, verrà esportata solo una copia dell'elemento.
    
- Non è possibile modificare un'esportazione per più ricerche dopo averlo creato. Ad esempio, non è possibile aggiungere o rimuovere le ricerche dall'esportazione. Sarà necessario creare un nuovo processo di esportazione per modificare i risultati di ricerca esportati. Dopo la creazione di un processo di esportazione, è possibile scaricare i risultati solo in un computer, riavviare l'esportazione o eliminare il processo di esportazione.
    
- Se si riavvia l'esportazione, tutte le modifiche apportate alle query delle ricerche che compongono il processo di esportazione non influiscono sui risultati della ricerca che verranno recuperati. Quando si riavvia un'esportazione, viene eseguito di nuovo lo stesso processo di query di ricerca combinato eseguito al momento della creazione del processo di esportazione.
    
- Se si riavvia una esportazione dalla pagina **esportazioni** in un caso di eDiscovery, i risultati della ricerca trasferiti nell'area di archiviazione di Azure sovrascrivono i risultati precedenti. i risultati precedenti sono stati trasferiti non saranno disponibili per il download. 
    
- La preparazione dei risultati di più ricerche per l'analisi in Advanced eDiscovery non è disponibile. È possibile preparare solo i risultati di una singola ricerca per l'analisi in Advanced eDiscovery.
  
## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a>Passaggio 7: preparare i risultati della ricerca per Advanced eDiscovery
<a name="step7_1"> </a>

Se l'organizzazione dispone di un abbonamento a Office 365 E5, è possibile preparare i risultati delle ricerche di contenuto associate a un caso di analisi in Advanced eDiscovery. Dopo aver preparato i risultati della ricerca, è possibile passare a Advanced eDiscovery (vedere [Step 8: go to the case in Advanced eDiscovery](manage-ediscovery-cases.md#gotoAeD_1)) ed elaborare i dati dei risultati di ricerca per un'ulteriore analisi in Advanced eDiscovery.
  
Quando si preparano i risultati della ricerca per Advanced eDiscovery, la funzionalità di riconoscimento ottico dei caratteri (OCR) estrae automaticamente il testo dalle immagini. OCR è supportato per file sciolti, allegati di posta elettronica e immagini incorporate. In questo modo è possibile applicare le funzionalità analitiche del testo avanzate di eDiscovery (quasi duplicati, Threading di posta elettronica, temi e codifica predittiva) a qualsiasi testo nei file di immagine.
  
> [!NOTE]
> Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. 
    
3. Nella **Home** page del caso, fare clic su **ricerca**, quindi selezionare la ricerca.
    
4. Nel riquadro dei dettagli, in **Analyze results with Advanced eDiscovery**, fare clic su **prepara i risultati per l'analisi**.
    
5. Nella pagina **Prepara i risultati per l'analisi**, eseguire le operazioni seguenti:  
    
  - Scegliere di preparare gli elementi indicizzati, gli elementi indicizzati e non indicizzati oppure solo gli elementi non indicizzati per l'analisi in Advanced eDiscovery.
    
  - Scegliere se includere tutte le versioni dei documenti trovati in SharePoint che soddisfano i criteri di ricerca. Questa opzione viene visualizzata solo se le origini contenuto della ricerca includono i siti.
    
  - Specificare se si desidera che un messaggio di notifica venga inviato (o copiato) a una persona al termine del processo di preparazione e che i dati siano pronti per essere elaborati in Advanced eDiscovery.
    
6. Fare clic su **Prepara**.
    
    I risultati della ricerca sono pronti per l'analisi con Advanced eDiscovery.
    
7. Nel riquadro dei dettagli, fare clic su **Controlla stato preparazione** per visualizzare le informazioni sul processo di preparazione. Al termine del processo di preparazione, è possibile passare al caso in Advanced eDiscovery per elaborare i dati per l'analisi. 
  
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a>Passaggio 8: passare alla causa in Advanced eDiscovery
<a name="gotoAeD_1"> </a>

Dopo aver creato un caso nel centro sicurezza & conformità, è possibile passare allo stesso caso in Advanced eDiscovery.
  
Per accedere a un caso in Advanced eDiscovery:
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera accedere in Advanced eDiscovery. 
    
3. Nella **Home** page del caso, fare clic su **passa a Advanced eDiscovery**.
    
    ![Fare clic su passa a Advanced eDiscovery per aprire il caso in Advanced eDiscovery](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Viene visualizzata la barra **di avanzamento per la connessione a Advanced eDiscovery** . Quando si è connessi a Advanced eDiscovery, nella pagina viene visualizzato un elenco di contenitori. 
    
    ![Il caso viene visualizzato in Advanced eDiscovery](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
    Questi contenitori rappresentano i risultati della ricerca preparati per l'analisi in Advanced eDiscovery nel passaggio 7. Si noti che il nome del contenitore ha lo stesso nome della ricerca di contenuto nel caso nel centro sicurezza & conformità. I contenitori presenti nell'elenco sono quelli che sono stati preparati. Se un utente diverso ha preparato i risultati della ricerca per Advanced eDiscovery, i contenitori corrispondenti non verranno inclusi nell'elenco.
    
4. Per caricare i dati dei risultati di ricerca da un contenitore a un caso in Advanced eDiscovery, selezionare un contenitore e fare clic su **processo**.
    
    Per informazioni su come elaborare i contenitori, vedere [eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md).
    
> [!TIP]
> Fare clic su **passa a eDiscovery** per tornare allo stesso caso nel centro sicurezza & conformità. 
  
## <a name="optional-step-9-close-a-case"></a>Optional Passaggio 9: chiudere un caso
<a name="closecase_1"> </a>

Quando viene completata la causa legale o l'indagine supportata da un caso di eDiscovery, è possibile chiudere il caso. Ecco cosa succede quando si chiude un caso:
  
- Se il caso contiene eventuali posizioni di contenuto in attesa, tali esenzioni saranno disattivate. Potrebbe risultare che il contenuto venga eliminato o rimosso definitivamente, dall'utente o da un processo automatizzato, ad esempio un criterio di eliminazione.
    
- La chiusura di un caso disattiva solo le esenzioni associate a quel caso. Se altre esenzioni sono posizionate in una posizione di contenuto, ad esempio un blocco per controversia legale. un criterio di conservazione o un'esenzione da un caso di eDiscovery diverso) tali esenzioni verranno comunque mantenute.
    
- Il caso è ancora elencato nella pagina eDiscovery nel centro sicurezza & Compliance. Vengono mantenuti i dettagli, le esenzioni, le ricerche e i membri di un caso chiuso.
    
- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare i risultati della ricerca e preparare il risultato della ricerca per l'analisi in Advanced eDiscovery. La differenza principale tra casi attivi e chiusi consiste nel fatto che le esenzioni sono disattivate quando un caso viene chiuso.
    
Per chiudere un caso:
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic sul nome del caso che si desidera chiudere.
    
    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** . 
    
3. In **Manage case status**fare ![clic su Rimuovi il](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) **caso di chiusura**del pulsante di visualizzazione.
    
4. Nella pagina **Dettagli** fare clic su **Chiudi maiuscole e minuscole**.
    
    Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate al caso saranno disattivate.
    
5. Fare clic su **Sì** per chiudere il caso. 
    
    Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **attivo** a **chiusura**.
    
6. Chiudere **gestire questo caso**.
    
7. Nella pagina **eDiscovery** fare ![](media/O365-MDM-Policy-RefreshIcon.gif) **clic su Aggiorna icona Aggiorna** per aggiornare lo stato del caso chiuso. Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti. 
    
    Al termine del processo, lo stato della distinzione tra maiuscole e minuscole viene modificato in **Chiudi** nella pagina **eDiscovery** . Fare di nuovo clic sul nome del caso per visualizzare la pagina Gestisci il riquadro a comparsa di **questo caso** , che contiene informazioni su quando il caso è stato chiuso e chi l'ha chiusa. 
  
## <a name="optional-step-10-re-open-a-closed-case"></a>Optional Passaggio 10: riaprire un caso chiuso
<a name="reopencase_1"> </a>

Quando si riapre un caso, tutte le esenzioni sul posto quando il caso è stato chiuso non verranno ripristinate automaticamente. Dopo che il caso è stato riaperto, è necessario andare alla pagina di **blocco** e accendere le esenzioni precedenti. Per abilitare un'esenzione, selezionarla e fare clic **su attiva** nel riquadro dei dettagli. 
  
1. Nel centro sicurezza & conformità, fare clic su **eDiscovery** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Fare clic sul nome del caso che si desidera riaprire.
    
    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** . 
    
3. In **Manage case status**fare clic su **riapri caso**.
    
    Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate alla distinzione tra maiuscole e minuscole non verranno attivate automaticamente.
    
4. Fare clic su **Sì** per riaprire il caso. 
    
    Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **chiuso** a **attivo**.
    
5. Chiudere **gestire questo caso**.
    
6. Nella pagina **eDiscovery** fare ![](media/O365-MDM-Policy-RefreshIcon.gif) **clic su Aggiorna icona Aggiorna** per aggiornare lo stato del caso riaperto. Per il completamento del processo di riapertura, potrebbero essere necessari fino a 60 minuti. 
    
    Al termine del processo, lo stato del caso viene modificato in **attivo** nella pagina **eDiscovery** . 
  
## <a name="more-information"></a>Altre informazioni
<a name="moreinfo_1"> </a>

- Esistono **limiti per i casi di eDiscovery o per i detiene associati a un caso di eDiscovery?** Nella tabella seguente sono elencati i limiti per i casi di eDiscovery e le esenzioni del caso.
    
|**Descrizione del limite**|**Tipo di limite**|
|:-----|:-----|
|Numero massimo di casi per un'organizzazione  <br/> |Nessun limite  <br/> |
|Numero massimo di case conservate per un'organizzazione  <br/> |10.000  <br/> |
|Numero massimo di cassette postali in un singolo blocco maiuscole/minuscole  <br/> |1,000  <br/> |
|Numero massimo di siti di SharePoint e OneDrive for business in un unico blocco del caso  <br/> |100  <br/> |
   
- **Che dire dei casi creati nella pagina di gestione dei casi in Advanced eDiscovery?** È possibile accedere a un elenco dei casi di eDiscovery avanzati precedenti facendo clic sul collegamento nella parte inferiore della pagina **eDiscovery** nel centro sicurezza & conformità. Tuttavia, per eseguire qualsiasi operazione in un caso meno recente, è necessario contattare il supporto di Office 365 e richiedere che il caso venga spostato in un nuovo caso di eDiscovery nel centro sicurezza & Compliance. 
    
- **Perché creare un amministratore di eDiscovery?** Come spiegato in precedenza, un amministratore di eDiscovery è membro del gruppo di ruoli Gestione eDiscovery che può visualizzare e accedere a tutti i casi di eDiscovery nell'organizzazione. La possibilità di accedere a tutti i casi di eDiscovery ha due importanti scopi:
    
  - Se una persona che è l'unico membro di un caso di eDiscovery lascia l'organizzazione, nessuno (inclusi i membri del gruppo di ruoli Gestione organizzazione o un altro membro del gruppo di ruoli Gestore di eDiscovery) può accedere al caso di eDiscovery poiché non è membro di un caso. In questo caso, non esisterebbe alcun modo di accedere ai dati nel caso. Tuttavia, poiché un amministratore di eDiscovery può accedere a tutti i casi di eDiscovery nell'organizzazione, è possibile visualizzare il caso nel centro sicurezza & compliance e aggiungere se stessi o un altro responsabile di eDiscovery come membro del caso.
    
  - Poiché un amministratore di eDiscovery può visualizzare e accedere a tutti i casi di eDiscovery, è in grado di controllare e controllare tutti i casi e le ricerche di contenuto associate. Ciò può aiutare a evitare l'errato utilizzo di ricerche di contenuto o casi di eDiscovery. Inoltre, poiché gli amministratori di eDiscovery possono accedere a informazioni potenzialmente riservate nei risultati di una ricerca di contenuto, è opportuno limitare il numero di persone che sono amministratori di eDiscovery.
    
    Infine, come spiegato in precedenza, gli amministratori di eDiscovery nel centro sicurezza & Compliance vengono aggiunti automaticamente come amministratori in Advanced eDiscovery. Questo significa che una persona che è un amministratore di eDiscovery può eseguire attività amministrative in eDiscovery avanzata, ad esempio la configurazione degli utenti, la creazione di case e l'aggiunta di dati ai casi.
    
- **Quali sono i requisiti per la gestione delle licenze per il blocco dei percorsi di contenuto?** In generale, le organizzazioni richiedono un abbonamento a Office 365 E3 o versioni successive per inserire posizioni di contenuto in attesa. Per inserire le cassette postali in attesa, è necessaria una licenza di Exchange Online piano 2. Per ulteriori informazioni, vedere le [domande frequenti](https://support.office.com/article/9d1a29ae-b7b4-4a27-9c8c-84289023dcae.aspx#Q5).

- **Cos'altro è necessario sapere sulla ricerca di tutti i contenuti del caso nel passaggio 5?** Come spiegato in precedenza, è possibile eseguire una ricerca nei percorsi di contenuto che sono stati inseriti in attesa nel caso. Quando si esegue questa operazione, solo il contenuto che corrisponde ai criteri di blocco è search. Se non è presente alcun criterio di conservazione, viene cercato tutto il contenuto. Se il contenuto è in un blocco basato su query, viene restituito solo il contenuto che corrisponde a entrambi i criteri di conservazione (dal blocco posto nel passaggio 4) e i criteri di ricerca (dalla ricerca nel passaggio 5).
    
    Di seguito sono riportate alcune considerazioni da tenere presenti quando si esegue la ricerca di tutti i contenuti del caso:
    
  - Se una posizione di contenuto fa parte di più riserve nello stesso caso, le query di blocco vengono combinate da un operatore **or** quando si esegue una ricerca nel percorso del contenuto utilizzando l'opzione tutti i contenuti di caso. Analogamente, se una posizione di contenuto fa parte di due diverse esenzioni, in cui una è basata su query e l'altra è una conservazione infinita (in cui tutto il contenuto viene messo in attesa), tutto il contenuto sarà ricerca a causa del blocco infinito. 
    
  - Se si tratta di una ricerca di contenuto per un caso ed è stata configurata per la ricerca in tutti i contenuti del caso e quindi si modifica un blocco (aggiungendo o rimuovendo una posizione di contenuto o cambiando la query di blocco), la configurazione di ricerca verrà aggiornata con tali modifiche. Tuttavia, è necessario eseguire di nuovo la ricerca dopo che il blocco è stato modificato per aggiornare i risultati della ricerca.
    
  - Se più case sono posizionate in un percorso di contenuto in un caso di eDiscovery e si seleziona per eseguire la ricerca in tutti i contenuti del caso, il numero massimo di parole chiave per la query di ricerca è 500. Ciò è dovuto al fatto che la ricerca di contenuto combina tutte le esenzioni basate su query utilizzando l'operatore **or** . Se sono presenti più di 500 parole chiave nelle query di archiviazione combinata e nella query di ricerca del contenuto, viene cercato tutto il contenuto della cassetta postale, non solo il contenuto che corrisponde a qualsiasi caso basato su query. 
    
  - Se il blocco di un caso ha lo stato di **attivazione**, è comunque possibile eseguire la ricerca nei percorsi del contenuto del caso mentre il blocco è attivo.
    
  - Come indicato in precedenza, se una ricerca è configurata per la ricerca in tutti i contenuti del caso, non è possibile includere tale ricerca se si desidera esportare i risultati di più ricerche. Se una ricerca è configurata per la ricerca in tutti i contenuti del caso, sarà necessario esportare i risultati di tale singola ricerca.
    
- **Informazioni su come archiviare i gruppi di Office 365 e Microsoft teams.** Microsoft teams è basato sui gruppi di Office 365. Pertanto, la loro conservazione in un caso di eDiscovery è molto simile. Tenere presente quanto segue quando si immettono in attesa gruppi di Office 365 e Microsoft teams. 
    
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
  
  - Quando viene eseguita la ricerca della cassetta postale di un utente, qualsiasi gruppo di Office 365 o Microsoft Team di cui l'utente è membro non verrà cercato. Analogamente, quando si inserisce un gruppo di Office 365 o un blocco di Microsoft Team, solo la cassetta postale di gruppo e il sito del gruppo vengono conservati in blocco; le cassette postali e i siti di OneDrive for business dei membri del gruppo non vengono conservati a meno che non vengano aggiunti in modo esplicito all'esenzione. Pertanto, se si ha la necessità di disporre di un gruppo di Office 365 o di un team di Microsoft per un motivo legale, è consigliabile aggiungere le cassette postali e i siti di OneDrive for business per i membri del gruppo e del team nello stesso blocco.
    
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
  
- **Come trovare l'URL per i siti di OneDrive for business?** Per raccogliere un elenco degli URL per i siti di OneDrive for business nell'organizzazione, in modo da poterli aggiungere a un'esenzione o a una ricerca associata a un caso di eDiscovery, vedere [creare un elenco di tutte le posizioni di OneDrive nell'organizzazione](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Lo script in questo articolo crea un file di testo che contiene un elenco di tutti i siti di OneDrive. Per eseguire questo script, è necessario installare e utilizzare SharePoint Online Management Shell. Assicurarsi di aggiungere l'URL del dominio MySite dell'organizzazione a ogni sito OneDrive che si desidera includere nella ricerca. Si tratta del dominio che contiene tutti i siti di OneDrive, ad esempio, `https://contoso-my.sharepoint.com`. Di seguito viene riportato un esempio di sito OneDrive di un utente: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
