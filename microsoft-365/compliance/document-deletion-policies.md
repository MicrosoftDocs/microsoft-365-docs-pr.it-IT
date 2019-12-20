---
title: Panoramica dei criteri di eliminazione dei documenti
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: Alla tua organizzazione potrebbe essere richiesto di conservare i documenti per un periodo di tempo a causa di requisiti di conformità, legali o di altro tipo. Tuttavia, se l'organizzazione conserva i documenti più del necessario, si crea un rischio legale non necessario. Con un criterio di eliminazione dei documenti, è possibile ridurre in modo proattivo i rischi eliminando i documenti in un sito dopo un determinato periodo di tempo, ad esempio, è possibile eliminare i documenti nei siti di OneDrive for business degli utenti cinque anni dopo la creazione dei documenti.
ms.openlocfilehash: 85a8a4464a14cb2e0b9e901fbf3912c7ff3faa8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806049"
---
# <a name="overview-of-document-deletion-policies"></a>Panoramica dei criteri di eliminazione dei documenti

> [!IMPORTANT]
> Se si procede in avanti, si consiglia di utilizzare un criterio di conservazione o etichette create nel centro conformità Microsoft 365, Microsoft 365 Security Center o Office 365 &amp; Security Compliance Center anziché un criterio di eliminazione dei documenti. I criteri di eliminazione dei documenti continueranno a funzionare fianco a fianco con i criteri di conservazione, ma se è necessario mantenere o eliminare il contenuto in un punto qualsiasi di Office 365, è consigliabile utilizzare un criterio di conservazione. Per ulteriori informazioni, vedere [use a Retention Policy anziché these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).
  
Alla tua organizzazione potrebbe essere richiesto di conservare i documenti per un periodo di tempo a causa di requisiti di conformità, legali o di altro tipo. Tuttavia, se l'organizzazione conserva i documenti più del necessario, si crea un rischio legale non necessario. Con un criterio di eliminazione dei documenti, è possibile ridurre in modo proattivo i rischi eliminando i documenti in un sito dopo un determinato periodo di tempo, ad esempio, è possibile eliminare i documenti nei siti di OneDrive for business degli utenti cinque anni dopo la creazione dei documenti.
  
I criteri di eliminazione dei documenti sono potenti ma flessibili, ad esempio, è possibile:
  
- Consentire ai proprietari del sito di scegliere tra i criteri che crei e gestisci centralmente. Puoi anche consentire ai proprietari del sito di rifiutare il criterio se decidono che non è adatto ai propri contenuti.
    
- Applicare un solo criterio obbligatorio in tutti i siti di una raccolta di siti, come i siti di OneDrive for Business o anche applicare un criterio a tutte le raccolte di siti di un modello di raccolte di siti specifico, come il modello Siti del team.
    
- Fornire un criterio predefinito con una regola predefinita che verrà applicata automaticamente senza che i proprietari del sito debbano fare qualcosa.
    
- Creare un criterio che include numerose regole di eliminazione tra cui un proprietario del sito può scegliere.
    
È possibile creare e gestire i criteri di eliminazione dei documenti tramite il centro criteri di eliminazione del documento. In alternativa, è possibile creare il centro criteri manualmente [creando la raccolta siti](https://go.microsoft.com/fwlink/p/?LinkID=404342) e scegliendo **centro criteri di conformità** nella scheda **organizzazione** . Ogni tenant può disporre di un solo centro criteri di eliminazione dei documenti. 
  
![Home page del Centro criteri per l'eliminazione dei documenti](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a>Quando utilizzare i criteri di eliminazione dei documenti

Oltre ai criteri di eliminazione dei documenti, Office 365 fornisce questi criteri di conservazione per il contenuto del sito:
  
- [Gestione record](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [Criteri di gestione delle informazioni per tipi di contenuto, elenchi e raccolte](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [Criteri sito](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
Ogni tipo di criterio è adatto per un tipo specifico di dati o di siti. Ad esempio, la tua organizzazione potrebbe avere un sito altamente strutturato che usa tipi di contenuti, come ad esempio un sito finanziario di contratti o una knowledge base di articoli. In questo caso, puoi utilizzare i criteri del tipo di contenuto. Oppure, la tua organizzazione potrebbe dover conservare documenti legali. In tal caso, potresti usare i tipi di contenuti e un Centro record per implementare un piano di file.
  
I criteri di eliminazione dei documenti non sostituiscono i criteri di gestione dei record o di gestione delle informazioni, che funzionano meglio con i tipi di contenuto strutturati. Invece, devi usare criteri di eliminazione dei documenti quando devi gestire ampiamente l'eliminazione automatica di dati non strutturati come i siti di OneDrive for Business e del team.
  
![Diagramma con opzione di conservazione per contenuto siti](media/IP-Retention-policies-for-site-content.png)
  
Se applichi un criterio di eliminazione dei documenti a un sito che usa già criteri di tipi di contenuto o criteri per la gestione delle informazioni per un elenco o una libreria, tali criteri vengono ignorati e viene applicato il criterio di eliminazione dei documenti. Ciò significa che devi fare in modo che un sito usi solo i criteri destinati a contenuti strutturati o non strutturati, non entrambi. Per ulteriori informazioni sul modo in cui i criteri di eliminazione di documenti sovrascrivono altri criteri, vedi [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).
  
A differenza di altri criteri, i criteri di eliminazione dei documenti funzionano solo con le librerie di documenti, non con gli elenchi.
  
## <a name="deletion-policies-and-rules"></a>Regole e criteri di eliminazione

Un criterio di eliminazione dei documenti contiene una o più regole che specificano:
  
- Il periodo di tempo fino all'eliminazione.
    
- Se calcolare la data di eliminazione dalla data di creazione o dalla data dell'ultima modifica.
    
- Se eliminare il documento in modo permanente o spostarlo nel Cestino.
    
Se un criterio contiene più di una regola, i proprietari del sito possono selezionare la regola più adatta al proprio contenuto.
  
![Pagina Nuova regola di eliminazione](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a>Criteri e assegnazioni

Dopo aver creato un criterio di eliminazione dei documenti, è possibile assegnarlo a un modello di raccolta siti, ad esempio, è possibile assegnare un criterio al modello di OneDrive for business in modo che includa il sito di OneDrive di ogni utente. Quando si assegna un criterio a un modello di raccolta siti, questo si applica a tutte le raccolte siti già create da tale modello, oltre alle raccolte siti create da tale modello in futuro.
  
![Pagina di scelta di un modello con opzione OneDrive](media/IP-Choose-a-template.png)
  
Puoi anche assegnare il criterio a una raccolta di siti specifica, sostituendo tutti i criteri che potrebbero essere stati assegnati al modello di tale raccolta di siti. Ad esempio, potresti assegnare criteri al modello Siti del team, ma poi sostituirli applicando un diverso set di criteri a una raccolta di siti specifica creata da tale modello.
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a>Un criterio obbligatorio o diversi criteri tra cui scegliere

Quando assegni un criterio, puoi scegliere di renderlo obbligatorio, in modo che possa essere assegnato solo questo criterio, che poi verrà applicato a tutti i siti nella raccolta di siti. I proprietari del sito non possono rifiutare un criterio obbligatorio, il che significa che i documenti nel sito saranno soggetti al criterio di eliminazione indipendentemente da quale esso sia.
  
Invece di rendere un solo criterio obbligatorio, puoi anche assegnare diversi criteri a una raccolta di siti, in modo da consentire al proprietario del sito di scegliere quale criterio applicare al proprio sito o di rifiutarli tutti. Ad esempio, puoi creare un criterio per documenti aziendali generici e un altro criterio per documenti finanziaria con un periodo di conservazione diverso. Un proprietari di sito spesso sa bene il tipo di contenuto presente nel suo sito e quindi sa quale criterio di eliminazione di documenti applicare. A ogni sito può essere applicato un solo criterio.
  
### <a name="one-rule-or-several-rules-to-choose-from"></a>Una o più regole diverse tra cui scegliere

A sua volta, ogni criterio può contenere molte regole, ad esempio un criterio di eliminazione per i documenti aziendali generali può avere due regole:
  
- I documenti che non necessitano di una conservazione basata su obblighi giuridici o in corso devono essere conservati per più di un anno dalla creazione.
    
- I documenti necessari per l'uso aziendale continuo e attivo che sono necessari per più di un anno, non devono essere conservati per più di tre anni dalla creazione.
    
Un proprietario di sito può stabilire se il sito contiene documenti aziendali generici, selezionare questo criterio di eliminazione, quindi selezionare la regola appropriata nel criterio. È possibile selezionare una regola solo dai criteri attualmente applicati al sito (non da qualsiasi criterio) e la regola viene applicata a tutte le raccolte documenti del sito.
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a>La relazione tra raccolte siti, criteri e regole

La relazione di base è la seguente:
  
Una raccolta di siti o un modello di raccolta di siti può contenere uno o più criteri assegnati e ognuno di questi criteri può avere una o più regole. Tuttavia, può essere presente un solo criterio attivo per sito e può essere presente una sola regola di eliminazione attiva in qualsiasi momento per le raccolte all'interno del sito.
  
![Diagramma con relazione tra criteri](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a>I criteri di eliminazione dei documenti vengono ereditati

Come le autorizzazioni, la navigazione e altre funzionalità del sito, i criteri di eliminazione dei documenti vengono ereditati. I proprietari del sito possono selezionare un criterio di eliminazione dei documenti per il proprio sito e tutti i siti secondari erediteranno il criterio dal sito principale. Un proprietario di un sito secondario può interrompere l'ereditarietà selezionando un'altra combinazione criterio - regola e il criterio verrà applicato a tutti i siti secondari finché l'ereditarietà non verrà di nuovo interrotta.
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a>Assegnare per la prima volta criteri di eliminazione dei documenti

È importante comprendere che il periodo di tempo specificato per un criterio di eliminazione dei documenti significa che il tempo dopo la creazione o la modifica del documento non è il momento in cui è stato assegnato il criterio. È possibile, ad esempio, creare un criterio di eliminazione dei documenti che elimini definitivamente il documento due anni dopo la creazione e quindi assegnare tale criterio a un modello di raccolta siti da cui sono state create diverse raccolte siti quattro o cinque anni fa. In questo caso, è probabile che le raccolte siti esistenti contengano molti documenti che sono già precedenti ai due anni specificati dai criteri di eliminazione, il che significa che molti contenuti verranno eliminati subito dopo aver assegnato il criterio di eliminazione dei documenti per il primo tempo.
  
Quando assegni il criterio per la prima volta, tutti i documenti nel sito vengono valutati e, se soddisfano il criterio, verranno eliminati. Questo vale per tutti i documenti esistenti, non solo per quelli creati dal momento dell'assegnazione del criterio. Ricorda inoltre che il periodo di tempo fa riferimento all'età di ogni documento, non al periodo dalla prima assegnazione del criterio.
  
Pertanto, prima di assegnare un criterio a un sito per la prima volta, dovresti prima prendere in considerazione l'età del contenuto esistente e il modo in cui il criterio potrebbe agire su tale contenuto. Potresti inoltre voler comunicare il nuovo criterio ai proprietari del sito prima di assegnarlo, per dargli il tempo di valutare il possibile impatto.
  
## <a name="time-lag-for-propagating-policies"></a>Intervallo di tempo per la propagazione dei criteri

Dopo aver assegnato i criteri a una raccolta di siti, i proprietari del sito usano il link **Criteri di eliminazione dei documenti** nella pagina **Impostazioni del sito** per visualizzare e applicare i criteri disponibili per il sito. 
  
Il collegamento **criteri di eliminazione dei documenti** non verrà visualizzato a meno che non siano stati assegnati criteri alla raccolta siti. Inoltre, il collegamento non viene visualizzato subito dopo che i criteri sono stati assegnati al sito, ma può richiedere fino a 24 ore da quando i criteri vengono assegnati quando viene visualizzato il collegamento **criteri di eliminazione dei documenti** . 
  
## <a name="permissions"></a>Autorizzazioni

I membri del team di conformità che useranno il Centro criteri per l'eliminazione dei documenti necessitano delle autorizzazioni per il centro criteri e per le raccolte dei siti alle quali verranno applicati i criteri. Ti consigliamo di:
  
1. Creare un gruppo di sicurezza che contenga tutti gli utenti del centro criteri di eliminazione dei documenti, molto probabilmente il team di gestione di criteri di conformità. Per ulteriori informazioni, vedere [gestire i gruppi di sicurezza abilitati alla posta elettronica](https://go.microsoft.com/fwlink/p/?LinkID=404345) . 
    
2. Nel Centro criteri per l'eliminazione dei documenti, assegna le autorizzazioni per i proprietari delle raccolte di siti al gruppo di sicurezza. Per ulteriori informazioni, vedere [autorizzazioni per gli amministratori di raccolte siti](https://go.microsoft.com/fwlink/p/?LinkID=404346) . 
    
3. In ogni raccolta di siti alla quale devi assegnare criteri di eliminazione dei documenti, assegna le autorizzazioni per i proprietari delle raccolte di siti al gruppo di sicurezza.
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a>Come funzionano i criteri di eliminazione dei documenti con i criteri di conservazione

Un criterio di conservazione garantisce che tutti i contenuti vengano conservati per un periodo di tempo specifico, mentre un criterio di eliminazione dei documenti garantisce che i contenuti vengano eliminati dopo uno specifico periodo di tempo.
  
Se devi conservare i documenti per un periodo di tempo fisso, puoi usare un criterio di conservazione insieme a un criterio di eliminazione. Ad esempio, potresti conservare documenti per tre anni dalla loro modifica, quindi impostare un criterio di eliminazione per eliminarli tre anni dopo l'ultima modifica.
  
Tieni presente che un criterio di eliminazione non può sostituire uno di conservazione. Se a un sito è applicato un criterio di conservazione e un criterio di eliminazione elimina un documento, il documento verrà conservato nella raccolta di archiviazione come se il documento fosse stato eliminato manualmente.
  
## <a name="see-also"></a>Vedere anche

[Applicare o rimuovere un criterio di eliminazione del documento per un sito](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[Creare un criterio di eliminazione dei documenti](create-a-document-deletion-policy.md)


