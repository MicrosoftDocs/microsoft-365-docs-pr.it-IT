---
title: Creare un criterio di eliminazione dei documenti
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Alle organizzazioni viene spesso richiesto di conservare i documenti per un determinato periodo di tempo a causa di norme legate alla conformità, legali o di altro tipo. Tuttavia, conservare i documenti per un periodo superiore a quello richiesto può esporre l'organizzazione a un rischio legale.
ms.openlocfilehash: 0144b12c05fcd4c8f973ee7e6b6df373f5b609a5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077926"
---
# <a name="create-a-document-deletion-policy"></a>Creare un criterio di eliminazione dei documenti

> [!IMPORTANT]
> Se si avanza, è consigliabile utilizzare un criterio di conservazione o le etichette di conservazione create nel centro conformità Microsoft 365, Microsoft 365 Security Center o Office 365 Security &amp; Compliance Center anziché un criterio di eliminazione dei documenti. I criteri di eliminazione dei documenti continueranno a funzionare fianco a fianco con i criteri di conservazione, ma se è necessario mantenere o eliminare il contenuto in un punto qualsiasi di Office 365, è consigliabile utilizzare un criterio di conservazione. Per ulteriori informazioni, vedere [use a Retention Policy anziché these features](retention-policies.md#use-a-retention-policy-instead-of-these-features). 
  
Alle organizzazioni viene spesso richiesto di conservare i documenti per un determinato periodo di tempo a causa di norme legate alla conformità, legali o di altro tipo. Tuttavia, conservare i documenti per un periodo superiore a quello richiesto può esporre l'organizzazione a un rischio legale.
  
Con un criterio di eliminazione dei documenti, è possibile ridurre in modo proattivo i rischi eliminando i documenti in un sito dopo un determinato periodo di tempo, ad esempio, è possibile eliminare i documenti nei siti di OneDrive for business degli utenti cinque anni dopo la creazione dei documenti. 
  
Dopo aver creato un criterio di eliminazione dei documenti, puoi assegnarlo a un modello di raccolta siti, in modo che il criterio sia disponibile per tutte le raccolte di siti create da tale modello. Puoi anche assegnare il criterio a una raccolta di siti specifica, sostituendo tutti i criteri che potrebbero essere stati assegnati al modello di tale raccolta di siti.
  
![Home page del Centro criteri per l'eliminazione dei documenti](../media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a>Modelli dei criteri

È possibile creare dei criteri per l'eliminazione dei documenti da zero o utilizzare uno dei criteri di esempio. Il centro criteri di conformità include dei criteri di esempio che è possibile utilizzare così come sono. In alternativa, è possibile usarli come punto di partenza per poi rinominarli o modificarli.
  
![Criteri di eliminazione del documento di esempio](../media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a>Esempi di come utilizzare i criteri di eliminazione dei documenti

Una raccolta di siti o un modello di raccolta di siti può contenere uno o più criteri assegnati e ognuno di questi criteri può avere una o più regole. Tuttavia, può essere presente un solo criterio attivo per sito e può essere presente una sola regola di eliminazione attiva in qualsiasi momento per le raccolte all'interno del sito.
  
![Diagramma con relazione tra criteri](../media/IP-Two-policies-four-rules.png)
  
Inoltre, puoi selezionare un criterio come obbligatorio o predefinito e puoi selezionare una regola di eliminazione come regola predefinita: 
  
- **Criteri obbligatori** Quando un criterio viene contrassegnato come obbligatorio, è possibile assegnare un solo criterio alla raccolta siti o al modello. Il criterio deve essere contrassegnato come predefinito e verrà applicato a tutti i siti. I proprietari dei siti non possono escludere il criterio.
    
- **Criterio predefinito** Quando un criterio è impostato come predefinito, il criterio viene automaticamente attivo in tutti i siti a cui viene assegnata senza alcuna azione richiesta dal proprietario del sito.
    
- **Regola predefinita** Quando una regola di eliminazione viene impostata come predefinita, viene applicata automaticamente a tutte le raccolte nei siti che utilizzano il criterio.
    
Nei seguenti esempi viene spiegato quando occorre usare un criterio obbligatorio o criteri e regole predefinite.
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a>Esempio 1: applicare un solo criterio con una sola regola a un modello di raccolta di siti

Potresti voler applicare un criterio di eliminazione dei documenti in un'ampia gamma di contenuto non strutturato, come i siti di OneDrive for Business o del team. Se vuoi essere sicuro che un solo criterio di eliminazione dei documenti sia attivo in tutti i siti creati da un modello di raccolta siti, puoi:
  
1. Creare un unico criterio con una sola regola di eliminazione predefinita.
    
2. Impostare il criterio come obbligatorio e predefinito.
    
3. Assegnare il criterio a un modello di raccolta siti.
    
In questo esempio, la regola di eliminazione predefinita verrà applicata a tutti le librerie in tutte le raccolte di siti create dal modello, e i proprietari del sito non potranno rifiutare esplicitamente il criterio. Questo è il modo più semplice per applicare su vasta scala e rigidamente un criterio di eliminazione dei documenti.
  
![Diagramma con un solo criterio obbligatorio](../media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a>Esempio 2: applicare un solo criterio con diverse regole a un modello di raccolta siti

I proprietari del sito spesso conoscono bene il tipo di contenuto presente nel sito, quindi potresti scegliere di consentire ai proprietari del sito di selezionare la regola di eliminazione più adatta al loro sito. Potresti inoltre voler consentire ai proprietari del sito di rifiutare completamente un criterio.
  
Allo stesso tempo, puoi comunque creare e gestire centralmente i criteri. Puoi anche selezionare un criterio e una regola come predefiniti, in modo che un criterio sia sempre valido finché il proprietario non ne sceglie uno diverso o lo rifiuti. Se vuoi offrire tale flessibilità ai proprietari del sito, puoi:
  
1. Creare un solo criterio con diverse regole di eliminazione e impostare una regola come predefinita.
    
2. Impostare il criterio come criterio predefinito.
    
3. Assegnare il criterio a un modello di raccolta siti.
    
I proprietari del sito possono selezionare una delle regole di eliminazione alternative, rifiutare il criterio o non fare nulla ed essere soggetti al criterio e alla regola predefiniti.
  
![Diagramma con un criterio con molte regole](../media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a>Esempio 3: applicare diversi criteri con una o più regole a una raccolta siti

Questo esempio offre la massima flessibilità ai proprietari del sito perché possono scegliere tra diversi criteri e dopo aver selezionato un criterio, possono spesso scegliere tra diverse regole. Un criterio e una regola vengono impostati come predefiniti, in modo che un criterio sia sempre valido finché il proprietario del sito non ne sceglie uno diverso o lo rifiuti. Tieni presente che se non imposti un criterio e una regola come predefiniti, nessun criterio o nessuna regola saranno attivi per le librerie di documenti nel sito finché il proprietario del sito non li selezionerà e applicherà.
  
Diversamente dai due esempi precedenti, questi criteri vengono assegnati a una raccolta di siti specifica, non al modello di raccolta di siti. Ciò significa che i criteri possono essere ancora più specificatamente personalizzati in base al contenuto in una raccolta di siti specifica.
  
I criteri e le regole sono ereditate. I proprietari del sito possono selezionare una regola e un criterio per il proprio sito e tutti i siti secondari erediteranno il criterio dal sito principale. Tuttavia, un proprietario di un sito secondario può interrompere l'ereditarietà selezionando un altro criterio e un'altra regola, che a loro volta verranno applicati a tutti i siti secondari finché l'ereditarietà non verrà di nuovo interrotta.
  
Per impostare questo scenario, puoi:
  
1. Creare diversi criteri che contengono una o più regole.
    
2. Impostare un criterio e una regola come predefiniti.
    
3. Assegnare i criteri a una raccolta siti specifica.
    
Inoltre, i criteri e le regole vengono creati in base a una raccolta di siti specifica, dove i proprietari del sito possono interrompere l'ereditarietà selezionando il criterio e la regola più adatti al proprio sito.
  
![Diagramma con molti criteri e regole](../media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a>Creare un criterio di eliminazione dei documenti

1. Nel centro conformità di &amp; Office 365Security, accedere a \> **conservazione** **della gestione dei dati** . In **Elimina**fare clic su **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**. Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.
    
    La prima volta che si passa dal centro &amp; sicurezza e conformità al centro criteri di eliminazione dei documenti, il centro criteri viene creato automaticamente per l'utente. In alternativa, è possibile creare manualmente il centro criteri [creando la raccolta siti](https://go.microsoft.com/fwlink/p/?LinkID=404342) e scegliendo **centro criteri di conformità** nella scheda **organizzazione** . 
    
2. Scegliere i **criteri di eliminazione**.
    
    ![Opzione Elimina criteri](../media/IP-Deletion-Policies-option.png)
  
3. Scegli **nuovo elemento**.
    
4. Inserisci un nome e una descrizione per il criterio. I proprietari del sito possono selezionare un criterio per il proprio sito in base al nome o alla descrizione, quindi ti consigliamo di inserire abbastanza informazioni per permettergli di scegliere il criterio corretto.
    
5. Per creare una regola, scegli **Nuova**.
    
6. Inserisci un nome e scegli le seguenti opzioni:
    
  - Scegliere se la regola eliminerà definitivamente i documenti o li sposterà nel Cestino. Il Cestino è una rete di sicurezza aggiuntiva prima che l'elemento venga eliminato in modo permanente da un sito. Per ulteriori informazioni sul Cestino, vedere [empty the Recycle bin o restore your files](https://go.microsoft.com/fwlink/p/?LinkID=404348).
    
  - Scegli se la data di eliminazione deve essere creata dalla data di creazione del documento a da quella dell'ultima modifica.
    
  - Inserisci un numero di giorni, mesi o anni come periodo di tempo dopo il quale un documento deve essere eliminato.
    
  - Scegli se la regola è una regola predefinita. La prima regola creata viene automaticamente impostata come la regola predefinita. Una regola predefinita viene automaticamente applicata a tutte le librerie nei siti che usano il criterio.
    
![Pagina Nuova regola di eliminazione](../media/IP-New-deletion-rule.png)
  
7. Fare clic su **Salva**.
    
8. Crea regole aggiuntive se vuoi che i proprietari del sito possano scegliere diverse regole da applicare al proprio sito. Verrà applicata la regola predefinita, se presente, se il proprietario del sito non esegue alcuna azione.
    
9. Per rimuovere una regola da un criterio, selezionare la regola, fare clic su **Elimina**e quindi su **OK**.
    
    > [!NOTE]
    > Se si elimina una regola e il criterio non contiene una regola predefinita, non verrà applicata alcuna regola per tale criterio, in altre parole, non verranno eliminati documenti. 
  
![Messaggio di conferma dell'eliminazione di una regola da un criterio](../media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a>Assegnare il criterio di eliminazione dei documenti a un modello di raccolta di siti

Assegnando un criterio a un modello di raccolta di siti, puoi rendere disponibile il criterio per tutte le raccolte di siti create dal tale modello, comprese le raccolte di siti esistenti e le raccolte di siti create nel futuro.
  
È importante comprendere che il periodo di tempo specificato per un criterio di eliminazione dei documenti significa che il tempo dopo la creazione o la modifica del documento non è il momento in cui è stato assegnato il criterio. Quando assegni il criterio per la prima volta, tutti i documenti nel sito vengono valutati e, se soddisfano il criterio, verranno eliminati. Questo vale per tutti i documenti esistenti, non solo per quelli creati dal momento dell'assegnazione del criterio.
  
1. Nel centro sicurezza &amp; e conformità, accedere a \> **conservazione** **della gestione dei dati** . In **Elimina**fare clic su **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**. Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.
    
2. Scegli **Assegnazioni dei criteri per i modelli**.
    
    ![Opzione Assegnazioni criteri per modelli](../media/IP-Policy-Assignments-for-Templates-option.png)
  
3. Scegli **nuovo elemento**.
    
4. Effettua una delle operazioni seguenti:
    
  - Per assegnare il criterio a un modello di raccolta di siti come il modello Siti del team, seleziona **Assegna a un modello di raccolta di siti**, quindi seleziona il modello di raccolta di siti.
    
  - Per assegnare il criterio agli utenti di un'unità per le aziende, scegliere **assegna a OneDrive for Business template**, evidenziato di seguito.
    
    > [!NOTE]
    > Quando assegni un criterio a un modello di raccolta di siti, tale criterio sarà disponibile sia per le raccolte di siti esistenti create dal modello, sia per quelle che verranno create in futuro. 
  
![Pagina di scelta di un modello con opzione OneDrive](../media/IP-Choose-a-template.png)
  
5. Fare clic su **Salva**.
    
    > [!NOTE]
    > A ogni modello può essere assegnato solo un set di criteri. Se viene visualizzato un messaggio di errore che indica che a questo modello sono già stati assegnati criteri, scegliere **Annulla** \> **assegna a raccolta siti** nella \> barra di spostamento a sinistra selezionare una raccolta siti per visualizzare e gestire il set di criteri già assegnati. 
  
6. Scegli **Gestisci criteri assegnati**, seleziona i criteri che vuoi assegnati, quindi scegli se un criterio deve essere contrassegnato come predefinito. Quando configuri un criterio predefinito, tutti i siti in cui è assegnato il criterio hanno automaticamente il criterio attivo senza che il proprietario del sito debba fare nulla.
    
    ![Pagina di aggiunta e gestione criteri](../media/IP-Add-and-manage-policies-page.png)
  
7. Fare clic su **Salva**.
    
8. Se vuoi applicare il criterio nei siti senza consentire ai proprietari del sito di rifiutarlo, scegli **Contrassegna il criterio come obbligatorio**. Quando rendi un criterio obbligatorio, solo il singolo criterio può essere assegnato al modello di raccolta di siti. Il criterio deve essere contrassegnato anche come predefinito.
    
    Se questa opzione è in grigio, scegli **Gestisci criteri assegnati** e controlla che almeno un criterio sia assegnato e impostato come predefinito. 
    
9. Fare clic su **Salva**.
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a>Assegnare il criterio di eliminazione dei documenti a una raccolta di siti

Assegnando un criterio a una raccolta di siti specifica, rendi disponibile il criterio solo per tale raccolta di siti specifica. Ciò significa che puoi meglio adattare i criteri al contenuto della raccolta di siti. Inoltre, i criteri assegnati a una raccolta di siti specifica sostituiranno tutti i criteri assegnati al modello di tale raccolta di siti. Ad esempio, un criterio assegnato alla raccolta di siti Reparto vendite (creato dal modello Siti del team) sostituirà tutti i criteri assegnati al modello Siti del team.
  
È importante comprendere che il periodo di tempo specificato per un criterio di eliminazione dei documenti significa che il tempo dopo la creazione o la modifica del documento non è il momento in cui è stato assegnato il criterio. Quando assegni il criterio per la prima volta, tutti i documenti nel sito vengono valutati e, se soddisfano il criterio, verranno eliminati. Questo vale per tutti i documenti esistenti, non solo per quelli creati dal momento dell'assegnazione del criterio.
  
1. Nel centro sicurezza &amp; e conformità, accedere a \> **conservazione** **della gestione dei dati** . In **Elimina**scegliere **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**. Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.
    
2. Scegli **Assegnazioni dei criteri per le raccolte di siti**.
    
    ![Opzione Assegnazioni criteri per raccolte di siti](../media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. Scegli **nuovo elemento**.
    
4. Scegliere **Scegli una raccolta siti**. Cercare la raccolta siti in base al nome o all'URL, selezionare la raccolta siti e fare clic su **Salva**.
    
    > [!NOTE]
    > A ogni raccolta di siti può essere assegnato solo un set di criteri. Se viene visualizzato un messaggio di errore che indica che la raccolta siti è già stata assegnata ai criteri, scegliere **Annulla** \> **assegna a raccolta siti** e selezionare una raccolta siti per visualizzare e gestire il set di criteri già assegnati. 
  
![Pagina di scelta raccolta di siti](../media/IP-Choose-a-site-collection-page.png)
  
5. Scegli **Gestisci criteri assegnati**, seleziona i criteri che vuoi assegnati, quindi scegli se un criterio deve essere contrassegnato come predefinito. Quando configuri un criterio predefinito, tutti i siti in cui è assegnato il criterio hanno automaticamente il criterio attivo senza che il proprietario del sito debba fare nulla.
    
    ![Pagina di aggiunta e gestione criteri](../media/IP-Add-and-manage-policies-page.png)
  
6. Fare clic su **Salva**.
    
7. Se vuoi applicare il criterio nei siti senza consentire ai proprietari del sito di rifiutarlo, scegli **Contrassegna il criterio come obbligatorio**. Quando rendi un criterio obbligatorio, solo il singolo criterio può essere assegnato alla raccolta di siti. Il criterio deve essere contrassegnato anche come predefinito.
    
    Se questa opzione è in grigio, scegli **Gestisci criteri assegnati** e controlla che almeno un criterio sia assegnato e impostato come predefinito. 
    
8. Fare clic su **Salva**.
    
## <a name="delete-a-policy-assignment"></a>Eliminare l'assegnazione di un criterio

Quando elimini un'assegnazione, i criteri assegnati non verranno più applicati ai siti nella raccolta di siti o nel modello di raccolta di siti.
  
1. Nel centro sicurezza &amp; e conformità, accedere a \> **conservazione** **della gestione dei dati** . In **Elimina**scegliere **Gestisci criteri di eliminazione dei documenti per SharePoint Online e OneDrive for business**. Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.
    
2. Scegliere una delle opzioni **Assegnazioni dei criteri per i modelli** o **Assegnazioni dei criteri per le raccolte di siti**.
    
3. Selezionare l'elemento di assegnazione e fare clic su **Elimina elemento**.
    
    ![Comando Elimina elemento per assegnazione criterio](../media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a>Eliminare un criterio

Non è possibile eliminare un criterio in uso. Prima di poter eliminare un criterio, è innanzitutto necessario eliminare tutte le assegnazioni alle raccolte siti e ai modelli di raccolta siti che includono tale criterio, vedere la sezione precedente.
  
1. Nel centro &amp; \> sicurezza e conformità scegliere **conservazione** della \> **gestione** \> dei dati nel riquadro di spostamento a sinistra in **Delete** \> **Manage document deletion Policies for SharePoint Online e OneDrive for business**. Il Centro criteri di eliminazione dei documenti si apre in una nuova scheda del browser.
    
2. Scegliere * * criteri di eliminazione * *.
    
    ![Opzione Elimina criteri](../media/IP-Deletion-Policies-option.png)
  
3. Seleziona il criterio.
    
4. Nella scheda \> **** \> elementi della barra multifunzione **rimuovere i criteri**.
    
    ![Pulsante Rimuovi criterio sulla barra multifunzione](../media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. Se il criterio è in uso, verrà chiesto se si desidera rimuovere il criterio da tutte le raccolte siti in cui viene utilizzato. Se si è sicuri, scegliere **OK**.
    
    ![Messaggio di conferma eliminazione criterio](../media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a>Vedere anche

[Panoramica dei criteri di eliminazione dei documenti](document-deletion-policies.md)

[Applicare o rimuovere un criterio di eliminazione del documento per un sito](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

