---
title: Informazioni sulle etichette di riservatezza
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Usare le etichette di riservatezza di Microsoft Information Protection (MIP) per classificare e proteggere il contenuto riservato.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: e1de507dd5ec9508df0318c8ba2ef30af795e25b
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430793"
---
# <a name="learn-about-sensitivity-labels"></a>Informazioni sulle etichette di riservatezza

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Se si stanno cercando informazioni sulle etichette di riservatezza che vengono visualizzate nelle app di Office, vedere [Applciare etichette di riservatezza a file ed e-mail in Office](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).
>
> Le informazioni fornite in questa pagina sono destinate agli amministratori IT che possono creare e configurare queste etichette.

Per svolgere il proprio lavoro, i membri dell'organizzazione collaborano con altri utenti, sia interni che esterni all'organizzazione stessa. Questo significa che i contenuti non sono più protetti da un firewall, ma possono spostarsi tra dispositivi, applicazioni e servizi. E quando si spostano, è preferibile che lo facciano in modo sicuro e protetto, nel rispetto dei criteri aziendali e di conformità dell'organizzazione.

Le etichette di riservatezza della soluzione Microsoft Information Protection consentono di classificare e proteggere i dati dell'organizzazione, garantendo al contempo che la produttività degli utenti e la loro capacità di collaborare non vengano ostacolate.

Esempio che mostra le etichette di riservatezza disponibili in Excel dalla scheda **Home** sulla barra multifunzione. In questo esempio l'etichetta applicata viene visualizzata sulla barra di stato:

![Etichetta di riservatezza sulla barra multifunzione e sulla barra di stato di Excel](../media/Sensitivity-label-in-Excel.png)

Per applicare le etichette di riservatezza, gli utenti devono aver eseguito l'accesso con l'account aziendale o dell'istituto di istruzione di Microsoft 365.

> [!NOTE]
> Per i tenant del governo degli Stati Uniti, le etichette di riservatezza sono ora supportate per tutte le piattaforme:
> - Per gli ambienti GCC e GCC High: note sulla versione per [Office per Windows](/officeupdates/current-channel#version-2101-january-26) e [Office per Mac](/officeupdates/release-notes-office-for-mac#feature-updates-2)
> - Per ambienti DoD: note sulla versione per [Office per Windows](/officeupdates/current-channel#version-2103-march-30)
>
> Se si usa il client e lo scanner di etichettatura unificata di Azure Information Protection per questi ambienti, vedere [Descrizione del servizio Azure Information Protection Premium Government](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).

È possibile usare le etichette di riservatezza per:
  
- **Fornire impostazioni di protezione che includono crittografia e contrassegni di contenuto.** Ad esempio, applicare un'etichetta "Riservato" a un documento o a un messaggio di posta elettronica. L'etichetta crittografa il contenuto e applica la filigrana "Riservato". I contrassegni di contenuto includono intestazioni, piè di pagina e filigrane e la crittografia consente anche di limitare le azioni che gli utenti autorizzati possono eseguire sul contenuto.

- **Proteggere il contenuto nelle app di Office su piattaforme e dispositivi diversi.** Supportato da Word, Excel, PowerPoint e Outlook nelle app desktop di Office e in Office sul Web. Supportato in Windows, macOS, iOS e Android.

- **Proteggere il contenuto in app e servizi di terze parti** con Microsoft Cloud App Security. Con Cloud App Security è possibile rilevare, classificare, etichettare e proteggere i contenuti in servizi e app di terze parti, ad esempio SalesForce, Box o DropBox, anche se l'applicazione o servizio di terze parti non legge o supporta le etichette di riservatezza.

- **Proteggere i contenitori** tra cui Teams, i Gruppi di Microsoft 365 e i siti di SharePoint. Ad esempio, configurare le impostazioni di privacy, l'accesso degli utente esterni, la condivisione esterna e l'accesso da dispositivi non gestiti.

- **Estendere le etichette di riservatezza a Power BI**: quando si attiva questa funzionalità, è possibile applicare e visualizzare le etichette in Power BI e proteggere i dati quando vengono salvati all'esterno del servizio.

- **Estendere le etichette di riservatezza alle risorse in Azure Purview**: quando si attiva questa funzionalità, attualmente in anteprima, è possibile applicare le etichette di riservatezza a risorse come colonne SQL, file in Archiviazione BLOB di Azure e così via. 

- **Estendere le etichette di riservatezza ad app e servizi di terze parti.** Con l'SDK di Microsoft Information Protection, le app e i servizi di terze parti possono leggere le etichette di riservatezza e applicare impostazioni di protezione.

- **Classificare il contenuto senza usare nessuna impostazione di protezione.** È anche possibile assegnare un'etichetta semplicemente come risultato della classificazione del contenuto. Questo offre agli utenti un mapping visivo della classificazione per i nomi delle etichette dell'organizzazione ed è possibile usare le etichette per generare report sull'utilizzo e visualizzare i dati delle attività per il contenuto riservato. In base a queste informazioni, è sempre possibile decidere in un secondo momento di applicare le impostazioni di protezione.

In tutti i casi, le etichette di riservatezza in Microsoft 365 possono aiutare a identificare le azioni corrette da eseguire per ogni contenuto. Con le etichette di riservatezza è possibile classificare i dati all'interno dell'organizzazione e applicare impostazioni di protezione in base alla classificazione.

Per altre informazioni su questi e altri scenari supportati dalle etichette di riservatezza, vedere [Scenari comuni per le etichette di riservatezza](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels). Vengono continuamente sviluppate nuove funzionalità che supportano le etichette di riservatezza, dunque può essere utile consultare la [roadmap di Microsoft 365](https://aka.ms/MIPC/Roadmap).

## <a name="what-a-sensitivity-label-is"></a>Cos'è un'etichetta di riservatezza

Un'etichetta di riservatezza è come un timbro applicato al contenuto e ha queste caratteristiche:

- **Personalizzabile.** È possibile creare categorie per diversi livelli di contenuto riservato nell'organizzazione, in base alle proprie specifiche esigenze. Ad esempio, si può iniziare con etichette come Personale, Pubblico, Generale, Riservato ed Estremamente riservato.

- **Testo non crittografato.** Poiché un'etichetta è archiviata come testo non crittografato nei metadati di file e messaggi di posta elettronica, le app e i servizi di terze parti possono leggerla e quindi applicare le proprie azioni di protezione, se necessario.

- **Persistente.** Poiché l'etichetta è archiviata nei metadati di file e messaggi di posta elettronica, l'etichetta si sposta con il contenuto, indipendentemente dal percorso in cui viene salvato o archiviato. L'identificazione univoca delle etichette diventa la base per applicare e applicare i criteri configurati.

Agli utenti, un'etichetta di riservatezza appare come un contrassegno nelle app che usano e può essere facilmente integrata nei flussi di lavoro esistenti.

A ogni elemento che supporta le etichette di riservatezza può esserne applicata solo una. Ai documenti e messaggi di posta elettronica può essere applicata sia un’etichetta di riservatezza che un’[etichetta di conservazione](retention.md#retention-labels).

> [!div class="mx-imgBorder"]
> ![Etichetta di riservatezza applicata a un messaggio di posta elettronica](../media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>Operazioni eseguibili dalle etichette di riservatezza

Quando si applica un'etichetta di riservatezza a un messaggio di posta elettronica o a un documento, al contenuto vengono applicate le impostazioni di protezione configurate per quell'etichetta. È possibile configurare un'etichetta di riservatezza in modo da:

- **Crittografare** i messaggi di posta elettronica e i documenti per impedire agli utenti non autorizzati di accedere ai dati. È inoltre possibile scegliere quali utenti o gruppi hanno le autorizzazioni necessarie per eseguire determinate azioni e per quanto tempo. Ad esempio, si può scegliere di consentire a tutti gli utenti dell'organizzazione di modificare un documento, mentre un gruppo specifico di un'altra organizzazione può solo visualizzarlo. In alternativa, anziché assegnare autorizzazioni definite dall'amministratore, è possibile consentire agli utenti di assegnare le autorizzazioni al contenuto quando vi applicano l'etichetta. 
    
    Per altre informazioni sulle impostazioni di **Crittografia** quando si crea o si modifica un'etichetta di riservatezza, vedere [Limitare l'accesso al contenuto usando la crittografia nelle etichette di riservatezza](encryption-sensitivity-labels.md).

- **Contrassegnare il contenuto** quando si usano app di Office con l'aggiunta di filigrane personalizzate, intestazioni o piè di pagina a messaggi di posta elettronica o documenti cui è stata applicata l'etichetta. Le filigrane possono essere applicate solo ai documenti, non ai messaggi di posta elettronica. Intestazione e filigrana di esempio:
    
    ![Filigrana e intestazione applicate a un documento](../media/Sensitivity-label-watermark-header.png)
    
    Se è necessario verificare se sono stati applicati contrassegni al contenuto, Vedere [Quando le app di Office applicano il contrassegno e la crittografia](sensitivity-labels-office-apps.md#when-office-apps-apply-content-marking-and-encryption).
    
    Alcune app, ma non tutte, supportano l'applicazione di contrassegni dinamici mediante l'uso di variabili. Ad esempio, inserire il nome dell'etichetta o il nome del documento nell'intestazione, nel piè di pagina o nella filigrana. Per altre informazioni, vedere [Contrassegni dinamici con variabili](sensitivity-labels-office-apps.md#dynamic-markings-with-variables).
    
    Lunghezza stringa: le filigrane sono limitate a 255 caratteri. Le intestazioni e i piè di pagina hanno un limite di 1024 caratteri, tranne che in Excel. Excel ha un limite totale di 255 caratteri per le intestazioni e i piè di pagina, ma questo limite include i caratteri non visibili, come i codici di formattazione. Se viene raggiunto questo limite, la stringa immessa non viene visualizzata in Excel.

- **Proteggere il contenuto in contenitori come siti e gruppi** quando si abilita la capacità di [usare le etichette di riservatezza con Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](sensitivity-labels-teams-groups-sites.md).
    
    Non è possibile configurare le impostazioni di protezione per i gruppi e i siti finché non si abilita questa funzionalità. La configurazione dell’etichetta non comporta l’applicazione automatica delle etichette a documenti o messaggi di posta elettronica, ma le impostazioni dell’etichetta proteggono il contenuto tramite il controllo dell'accesso al contenitore in cui si archivia tale contenuto. Queste impostazioni includono le impostazioni di privacy, l'accesso utente esterno, la condivisione esterna e l’accesso da dispositivi non gestiti.

- **Applicare l'etichetta automaticamente ai file e ai messaggi di posta elettronica o consigliare un'etichetta.** Scegliere come identificare i tipi di informazioni sensibili che si desidera etichettare e l'etichetta può essere applicata automaticamente oppure richiedere agli utenti di applicare l'etichetta consigliata. Se si consiglia un'etichetta, viene visualizzato il messaggio che si sceglie. Ad esempio:
    
    ![Messaggio in cui si richiede di assegnare un'etichetta obbligatoria](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    Per altre informazioni sulle impostazioni di **applicazione automatica di etichette ai file e ai messaggi di posta elettronica** quando si crea o modifica un’etichetta di riservatezza, vedere [Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md) per le app Office e [Etichettare automaticamente i file in Azure Purview](/azure/purview/create-sensitivity-label).

### <a name="label-scopes"></a>Ambiti di etichetta

Quando si crea un'etichetta di riservatezza, viene chiesto di configurare l'ambito dell'etichetta che determina due fattori:
- quali impostazioni di etichetta possono essere configurate per quell'etichetta
- dove l'etichetta sarà visibile per gli utenti

La configurazione dell'ambito consente di avere etichette di riservatezza che sono uniche per documenti e messaggi di posta elettronica e non possono essere selezionate per i contenitori. Allo stesso modo, le etichette di riservatezza solo per i contenitori non possono essere selezionate per documenti e messaggi di posta elettronica. Caratteristica nuova e attualmente in anteprima è anche possibile selezionare l'ambito per le risorse di Azure Purview:

![Opzioni di ambito delle etichette di riservatezza](../media/sensitivity-labels-scopes.png)

Per impostazione predefinita, è sempre selezionato l'ambito **File e messaggi di posta elettronica**. Gli altri ambiti sono selezionati sono selezionati per impostazione predefinita quando le funzionalità sono abilitate per il tenant:

- **Gruppi e siti**: [abilitare le etichette di riservatezza per i contenitori e sincronizzare le etichette](sensitivity-labels-teams-groups-sites.md#how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels)

- **Risorse di Azure Purview (anteprima)**: [etichettare automaticamente i contenuti in Azure Purview](/azure/purview/create-sensitivity-label).

Se si modificano le impostazioni predefinite in modo che non siano selezionate tutti gli ambiti, viene visualizzata la prima pagina delle impostazioni di configurazione per gli ambiti non selezionati, ma non è possibile configurare le impostazioni. Ad esempio, se non è selezionato l'ambito per i file e i messaggi di posta elettronica, non è possibile selezionare le opzioni nella pagina successiva:

![Opzioni non disponibili per le etichette di riservatezza](../media/sensitivity-labels-unavailable-settings.png)

Per le pagine che non hanno opzioni disponibili, selezionare **Avanti** per continuare. In alternativa, selezionare **Indietro** per cambiare l'ambito dell'etichetta.

### <a name="label-priority-order-matters"></a>Priorità dell’etichetta (l’ordine è importante)

Quando si creano le etichette di riservatezza nella propria interfaccia di amministrazione, queste vengono visualizzate in un elenco nella scheda **Riservatezza** nella pagina **Etichette**. In questo elenco, l'ordine delle etichette è importante perché ne riflette la priorità. È importante che l'etichetta con il grado di riservatezza più restrittivo, come Riservatezza elevata, sia visualizzata nella **parte inferiore** dell'elenco e che l'etichetta con il grado di riservatezza meno restrittivo, ad esempio Pubblico, sia visualizzata nella **parte superiore**.

È possibile applicare una sola etichetta di riservatezza a un elemento, ad esempio un documento, un messaggio di posta elettronica o un contenitore. Se si imposta un'opzione per richiedere ali utenti di fornire una giustificazione per modificare un'etichetta applicando una classificazione inferiore, l'ordine di questo elenco identifica le classificazioni inferiori. Tuttavia, questa opzione non si applica alle sottoetichette.

L'ordinamento delle sottoetichette viene però usato con l'[etichettatura automatica](apply-sensitivity-label-automatically.md). Quando si configurano le etichette in modo da applicarle automaticamente o come suggerimento, diverse etichette possono avere più corrispondenze. Per determinare l'etichetta da applicare o consigliare si usa l'ordinamento delle etichette, ovvero viene selezionata l'etichetta a riservatezza meno elevata e, se applicabile, anche la sottoetichetta a riservatezza meno elevata.

![Possibilità di creare una sottoetichetta](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>Sottoetichette (raggruppamento etichette)

Con le sottoetichette, è possibile raggruppare una o più etichette sotto un'etichetta padre che viene visualizzata da un utente in un'applicazione di Office. Ad esempio, in Riservato, l'organizzazione potrebbe usare varie etichette diverse per tipi specifici di quella classificazione. In questo esempio, l'etichetta Riservato è una semplice etichetta di testo senza alcuna impostazione di protezione e, poiché contiene sottoetichette, non può essere applicata al contenuto. Gli utenti devono invece scegliere Riservato per visualizzare le sottoetichette e quindi scegliere una sottoetichetta da applicare al contenuto.

Le sottoetichette sono solo un modo per presentare le etichette agli utenti in gruppi logici. Non ereditano le impostazioni dell'etichetta padre che le contiene. Quando si pubblica una sottoetichetta per un utente, tale utente può applicare tale sottoetichetta al contenuto ma non può applicare l'etichetta padre.

Non scegliere un'etichetta padre come etichetta predefinita o configurare un'etichetta padre da applicare (o consigliare) automaticamente, altrimenti l'etichetta padre non verrà applicata al contenuto.

Esempio di come vengono visualizzate le sottoetichette per gli utenti:

![Sottoetichette raggruppate nella barra multifunzione](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>Modificare o eliminare un'etichetta di riservatezza

Se si elimina un'etichetta di riservatezza dall'interfaccia di amministrazione, l'etichetta non viene rimossa dal contenuto e le impostazioni di protezione continuano a essere applicate al contenuto.

Se si modifica un'etichetta di riservatezza, sarà applicata al contenuto la versione dell'etichetta originalmente applicata su di esso.

## <a name="what-label-policies-can-do"></a>Operazioni eseguibili dai criteri di etichetta

Dopo aver creato le etichette di riservatezza, è necessario pubblicarle per renderle disponibili agli utenti e ai servizi dell'organizzazione. Sarà quindi possibile applicare le etichette di riservatezza a messaggi di posta elettronica e documenti di Office e ad altri elementi che le supportano. 

A differenza delle etichette di conservazione, che vengono pubblicate in posizioni, ad esempio tutte le cassette postali di Exchange, le etichette di riservatezza vengono pubblicate a utenti o gruppi. Le app che supportano le etichette di riservatezza possono quindi mostrarle a tali utenti e gruppi come etichette applicate oppure come etichette che possono essere applicate.

Quando si configura un criterio di etichetta, è possibile:

- **Scegliere gli utenti e i gruppi che vedranno le etichette.** Le etichette possono essere pubblicate per qualsiasi utente specifico, gruppo di sicurezza abilitato per la posta elettronica, gruppo di distribuzione o gruppo di Microsoft 365, che può avere [appartenenza dinamica](/azure/active-directory/users-groups-roles/groups-create-rule) in Azure AD.

- **Specificare un'etichetta predefinita** per nuovi documenti, messaggi di posta elettronica senza etichetta e nuovi contenitori (dopo aver [abilitato etichette di riservatezza per Microsoft Teams, Gruppi di Microsoft 365 e siti SharePoint](sensitivity-labels-teams-groups-sites.md)). È possibile specificare la stessa etichetta per tutti e tre i tipi di elementi oppure etichette diverse. Quando si specifica un'etichetta predefinita per i documenti, il client di etichettatura unificata di Azure Information Protection la applica anche ai documenti esistenti senza etichetta. Gli utenti possono sempre modificare l'etichetta predefinita, se non è quella giusta per il documento o la posta elettronica.
    
    Considerare l'uso di un'etichetta predefinita per impostare un livello di impostazioni di sicurezza di base da applicare a tutto il contenuto. Tuttavia, in mancanza di formazione per gli utenti e di altri controlli, questa impostazione può anche risultare nell'applicazione di etichette non corrette. In genere non è consigliabile selezionare un'etichetta che applica la crittografia come etichetta predefinita dei documenti. Ad esempio, molte organizzazioni devono inviare e condividere documenti con utenti esterni che potrebbero non avere app che supportano la crittografia o che potrebbero non usare un  account che può essere autorizzato. Per altre informazioni su questo scenario, vedere [Condivisione di documenti crittografati con utenti esterni](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).

- **Richiedere una motivazione per la modifica di un'etichetta.** Se un utente prova a rimuovere un'etichetta o a sostituirla con un'etichetta che ha un numero d'ordine inferiore, è possibile richiedere all'utente di fornire una motivazione per eseguire questa operazione. Ad esempio, un utente apre un documento con l'etichetta Riservato (numero d'ordine 3) e sostituisce tale etichetta con un'altra denominata Pubblico (numero d'ordine 1). Per le app Office, la richiesta di giustificazione viene attivata per ogni sessione dell'app quando si usa l'etichettatura predefinita e per ogni file quando si usa il client di etichettatura unificata Azure Information Protection. Gli amministratori possono leggere il motivo della motivazione insieme alla modifica dell'etichetta in [Esplora attività](data-classification-activity-explorer.md).

    ![Finestra in cui gli utenti immettono una motivazione](../media/Sensitivity-label-justification-required.png)

- **Richiedere agli utenti di applicare un'etichetta** per documenti e messaggi di posta elettronica, solo documenti, per contenitori e contenuti di Power BI. Questa opzione, nota anche come etichettatura obbligatoria, assicura l'applicazione di un'etichetta prima che gli utenti possano salvare documenti, inviare messaggi di posta elettronica, creare nuovi gruppi o siti e quando gli utenti utilizzano contenuti non etichettati per Power BI.
    
    Per i documenti e i messaggi di posta elettronica, l'etichetta può essere assegnata manualmente dall'utente, automaticamente in seguito a una condizione configurata oppure assegnata per impostazione predefinita ( l'opzione per l'etichetta predefinita descritta in precedenza). Esempio di messaggio di richiesta mostrato in Outlook quando un utente deve assegnare un'etichetta:

    ![Messaggio visualizzato in Outlook per richiedere all'utente di applicare l'etichetta obbligatoria](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    Per altre informazioni sull'etichettatura obbligatoria per documenti e posta elettronica, vedere [Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents).
    
    Per i contenitori, l'etichetta deve essere assegnata al momento della creazione del gruppo o del sito.
    
    Per ulteriori informazioni sull'etichettatura obbligatoria per Power BI, vedere [Criterio di etichetta obbligatoria per Power BI](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy).
    
    Valutare l'uso di questa opzione per ampliare la portata dell'etichettatura. Tuttavia, in mancanza di formazione per gli utenti, queste impostazioni possono risultare nell'applicazione di etichette non corrette. Inoltre, a meno che non si imposti anche un'etichetta corrispondente predefinita, l'etichettatura obbligatoria può infastidire gli utenti con messaggi di richiesta frequenti.

- **Fornire il collegamento a una pagina della Guida personalizzata.** Se gli utenti non conoscono il significato delle etichette di riservatezza o non sanno come usarle, è possibile fornire un URL che consente di accedere a maggiori informazioni, visualizzato nella parte inferiore del menu **Etichetta di riservatezza** nelle app Office:

    ![Collegamento a ulteriori informazioni sul pulsante Riservatezza della barra multifunzione](../media/Sensitivity-label-learn-more.png)

Quando si crea un criterio di etichetta che assegna nuove etichette di riservatezza a utenti e gruppi, gli utenti iniziano a vedere le etichette nelle app di Office. Possono essere necessarie fino a 24 ore perché le ultime modifiche siano replicate in tutta l’organizzazione.

Non c'è limite al numero di etichette di riservatezza che è possibile creare e pubblicare, salvo un'eccezione: se l'etichetta applica la crittografia che specifica gli utenti e le autorizzazioni, sono supportate un massimo di 500 etichette. Tuttavia, come procedura consigliata per ridurre al minimo i sovraccarichi per gli amministratori e le difficoltà per gli utenti, cercare di creare un numero limitato di etichette. Le distribuzioni nel mondo reale hanno evidenziato un'efficacia notevolmente ridotta nei casi in cui gli utenti hanno più di cinque etichette principali, oppure più di cinque sottoetichette per ogni etichetta principale.

### <a name="label-policy-priority-order-matters"></a>Priorità dei criteri di etichetta (l’ordine è importante)

Per rendere disponibili le etichette di riservatezza agli utenti, è possibile pubblicarle in un criterio di etichetta di riservatezza, incluso in un elenco della scheda **Criteri di riservatezza** nella pagina **Criteri etichetta**. Come le etichette di riservatezza (vedere [Priorità dell'etichetta (l'ordine è importante)](#label-priority-order-matters)), l'ordine dei criteri di etichetta di riservatezza è importante perché ne rispecchia la priorità. Il criterio di etichetta con priorità più bassa viene visualizzato nella parte **superiore**, mentre il criterio di etichetta con priorità più alta viene visualizzato nella parte **inferiore**.

Un criterio di etichetta è costituito da:

- Un set di etichette.
- Gli utenti e i gruppi a cui verrà assegnato il criterio con le etichette.
- L'ambito del criterio e le impostazioni del criterio per quell'ambito, ad esempio etichetta predefinita per i file e i messaggi di posta elettronica.

È possibile includere un utente in più criteri di etichetta. L'utente riceverà tutte le etichette di riservatezza e le impostazioni di tali criteri. Se si verifica un conflitto nelle impostazioni di più criteri, viene applicata l'impostazione del criterio con la priorità più alta (posizione più bassa). In altre parole, per ogni impostazione prevale la priorità più alta.

Se il comportamento previsto per l'etichetta o l'impostazione dei criteri di etichetta per un utente o un gruppo non viene applicato, controllare l'ordine dei criteri per le etichette di riservatezza. Potrebbe essere necessario spostare i criteri verso il basso. Per riordinare i criteri di etichetta, selezionare un criterio di etichetta di riservatezza > scegliere i puntini di sospensione a destra > **Sposta su** o **Sposta giù**.

![Opzione Sposta nella pagina dei criteri di etichetta di riservatezza](../media/sensitivity-label-policy-priority.png)

> [!NOTE]
> Bisogna tenere conto che quando si verifica un conflitto nelle impostazioni per un utente a cui sono assegnati più criteri, viene applicata l'impostazione del criterio con la priorità più alta (posizione più bassa).

## <a name="sensitivity-labels-and-azure-information-protection"></a>Etichette di riservatezza e Azure Information Protection

Se si usano le etichette di riservatezza in Microsoft 365 Apps in computer Windows, è possibile scegliere di usare l'etichettatura integrata nelle app di Office o il client di Azure Information Protection.

Per impostazione predefinita, l'etichettatura integrata è disattivata nelle app quando è installato il client di Azure Information Protection. Per altre informazioni, incluse indicazioni su come modificare questo comportamento predefinito, vedere [Client di etichettatura incorporato di Office e client Azure Information Protection](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client).

Anche quando si usa l'etichettatura integrata nelle app di Office, è possibile usare il client di etichettatura unificato di Azure Information Protection con le etichette di riservatezza per quanto segue:

- Uno strumento di analisi per individuare le informazioni sensibili archiviate in locale e quindi, se necessario, etichettare quel contenuto

- Opzioni disponibili nel menu di scelta rapida in Esplora file per consentire agli utenti di applicare etichette a tutti i tipi di file

- Un visualizzatore per visualizzare i file crittografati per i documenti di testo, immagine o PDF

- Un modulo di PowerShell per individuare le informazioni sensibili nei file in locale e applicare o rimuovere etichette e crittografia da tali file.

Se non si ha familiarità con Azure Information Protection o se l’utente è un cliente di Azure Information Protection che ha recentemente eseguito la migrazione delle etichette, vedere [Scegliere la soluzione di etichettatura di Windows](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) nella documentazione di Azure Information Protection.

### <a name="azure-information-protection-labels"></a>Etichette di Azure Information Protection

> [!NOTE]
> La gestione delle etichette di Azure Information Protection nel portale di Azure è stata deprecata il **31 marzo 2021**. Per altre informazioni, vedere l'avviso ufficiale di [funzionalità deprecata](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179).

Se il tenant non è ancora presente nella [piattaforma di etichettatura unificata](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform), è necessario prima attivare l'etichettatura unificata per poter usare le etichette di riservatezza. Per istruzioni, vedere [Come eseguire la migrazione di etichette di Azure Information Protection a etichette di riservatezza unificate](/azure/information-protection/configure-policy-migrate-labels). 

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a>Etichette di riservatezza e Microsoft Information Protection SDK

Dato che un'etichetta di riservatezza è archiviata nei metadati di un documento, le app e i servizi di terze parti possono leggere e scrivere in questi dati di etichettatura per integrare la distribuzione dell'etichettatura. Inoltre, gli sviluppatori di software possono usare [Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk) per supportare pienamente le funzionalità di etichettatura e crittografia su più piattaforme. Per altre informazioni, vedere l'[annuncio della disponibilità generale sul blog della Tech Community](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). 

Sono anche disponibili informazioni sulle [soluzioni dei partner integrate con Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).

## <a name="deployment-guidance"></a>Guida alla distribuzione

Per la pianificazione della distribuzione e il materiale sussidiario che include informazioni sulla licenza, autorizzazioni, strategia di distribuzione, un elenco di scenari supportati e la documentazione per l'utente finale, vedere [Introduzione alle etichette di riservatezza](get-started-with-sensitivity-labels.md).

Per informazioni su come usare le etichette di riservatezza per rispettare le normative sulla privacy dei dati, vedere [Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).