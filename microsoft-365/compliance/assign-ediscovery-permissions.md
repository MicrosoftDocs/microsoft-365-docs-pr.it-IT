---
title: Assegnare le autorizzazioni di eDiscovery nel centro sicurezza & Compliance
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
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Assegnare le autorizzazioni necessarie per eseguire le attività relative a eDiscovery utilizzando il Centro sicurezza & Compliance.
ms.openlocfilehash: 5a9036908d97a62897b7d52b875a46008a7a337c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083288"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Assegnare le autorizzazioni di eDiscovery nel centro sicurezza & Compliance

Se si desidera che gli utenti utilizzino gli strumenti correlati a eDiscovery nel centro sicurezza & conformità in Office 365, è necessario assegnare loro le autorizzazioni appropriate. Il modo più semplice per eseguire questa operazione consiste nell'aggiungere la persona del gruppo di ruoli appropriato nella pagina **autorizzazioni** nel centro sicurezza & conformità. In questo argomento vengono descritte le autorizzazioni necessarie per eseguire le attività relative alla ricerca di eDiscovery e al contenuto utilizzando il Centro sicurezza & Compliance. 
  
Il gruppo di ruoli principale di eDiscovery nel centro sicurezza & conformità è denominato **eDiscovery Manager**. Sono presenti due sottogruppi all'interno di questo gruppo di ruoli. 
  
- **eDiscovery** managers-un Manager di eDiscovery può utilizzare lo strumento di ricerca del contenuto nel centro sicurezza & conformità per cercare i percorsi di contenuto nell'organizzazione ed eseguire diverse azioni correlate alla ricerca, ad esempio l'anteprima e l'esportazione dei risultati della ricerca. I membri possono anche creare e gestire i casi di eDiscovery, aggiungere e rimuovere membri in un caso, creare case detiene ed eseguire ricerche di contenuto associate a un caso, nonché i dati dei casi di accesso in Office 365 Advanced eDiscovery.  Un Manager di eDiscovery può accedere e gestire solo i casi creati. Non possono accedere o gestire i casi creati da altri gestori di eDiscovery. 
    
- **amministratori di eDiscovery** -un amministratore di eDiscovery è un membro del gruppo di ruoli di eDiscovery Manager ed è in grado di eseguire le stesse attività correlate alla ricerca di contenuto e alla gestione dei casi che può essere eseguito da un responsabile di eDiscovery. Inoltre, un amministratore di eDiscovery è in grado di: 
    
  - Accedere a tutti i casi elencati nella pagina **casi di eDiscovery** nel centro sicurezza & conformità. 

  - Accedere ai dati del caso in Advanced eDiscovery per tutti i casi nell'organizzazione.
    
  - Gestire qualsiasi caso di eDiscovery dopo essersi aggiunti come membri del caso.
  
  Vedere la sezione [ulteriori informazioni](#more-information) per motivi per i quali potrebbe essere opportuno che gli amministratori di eDiscovery nell'organizzazione. 

> [!NOTE]
> Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5.  
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere membri del gruppo di ruoli Gestione organizzazione (o essere assegnati al ruolo di gestione dei ruoli) per assegnare le autorizzazioni di eDiscovery nel centro sicurezza & conformità.
    
- È possibile utilizzare il cmdlet [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) in PowerShell per la sicurezza & Compliance Center per aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo responsabili di eDiscovery nel gruppo di ruoli di eDiscovery Manager. Tuttavia, non è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica al sottogruppo Administrators di eDiscovery. Per ulteriori dettagli, vedere la sezione [ulteriori informazioni](#more-information) . 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Assegnare le autorizzazioni di eDiscovery nel centro sicurezza & Compliance

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro del Centro sicurezza e conformità fare clic su **autorizzazioni**e quindi fare clic sulla casella di controllo accanto a **eDiscovery Manager**.
    
4. Nella pagina riquadro a comparsa di **eDiscovery Manager** , eseguire una delle operazioni seguenti in base alle autorizzazioni di eDiscovery che si desidera assegnare. 
    
  - **Per rendere un utente un Manager di eDiscovery** Accanto a **eDiscovery Manager**, fare clic su **modifica**. In **eDiscovery Manager selezionati**, fare clic su **modifica**, quindi ![fare clic](media/ITPro-EAC-AddIcon.gif) su Aggiungi icona **Aggiungi**. Selezionare l'utente o gli utenti che si desidera aggiungere come Manager di eDiscovery, quindi fare clic su **Aggiungi**. Al termine dell'aggiunta degli utenti, fare clic su **fine**. Nella pagina **modifica scegliere eDiscovery Manager** a comparsa fare clic su **Salva** per salvare le modifiche apportate all'appartenenza di eDiscovery Manager. 
    
  - **Per rendere un utente un amministratore di eDiscovery** Accanto a **eDiscovery Administrator**, fare clic su **modifica**. In **amministratori di eDiscovery selezionati**fare clic su **modifica**e quindi ![su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona **Aggiungi**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come amministratore di eDiscovery e quindi fare clic su **Aggiungi**. Al termine dell'aggiunta degli utenti, fare clic su **fine**. Fare clic su **Salva** per salvare le modifiche apportate all'appartenenza all'amministratore di eDiscovery nella pagina **modifica scegliere** il riquadro a comparsa amministratore di eDiscovery. 
    
> [!NOTE]
> È inoltre possibile utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per rendere un utente un amministratore di eDiscovery. Tuttavia, all'utente deve essere assegnato il ruolo di gestione dei casi prima che sia possibile utilizzare questo cmdlet per renderli un amministratore di eDiscovery. Per ulteriori informazioni, vedere [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
Nella pagina **autorizzazioni** nel centro sicurezza & conformità è anche possibile assegnare agli utenti le autorizzazioni relative a eDiscovery, aggiungendole ai gruppi di ruoli amministratore conformità, Gestione organizzazione e reviewer. Per una descrizione dei ruoli RBAC relativi a eDiscovery assegnati a ognuno di questi gruppi di ruoli, vedere i [ruoli RBAC relativi alla sezione eDiscovery](#rbac-roles-related-to-ediscovery) . 

## <a name="rbac-roles-related-to-ediscovery"></a>Ruoli RBAC relativi a eDiscovery

Nella tabella seguente sono elencati i ruoli RBAC relativi a eDiscovery nel centro sicurezza & compliance e sono indicati i gruppi di ruoli incorporati a cui ogni ruolo è assegnato per impostazione predefinita. 
    
|**Ruolo**|**Amministratore di conformità**|**Amministratore & di eDiscovery Manager**|**Gestione organizzazione**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gestione dei casi <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Ricerca di conformità <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Esportazione <br/> | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Tenere <br/>  |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Anteprima <br/>  | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Verifica <br/>  | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|Decrittografia RMS <br/>  ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Ricerca ed eliminazione <br/> | <br/> | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
Nelle sezioni seguenti vengono descritti i ruoli RBAC relativi a eDiscovery elencati nella tabella precedente.

### <a name="case-management"></a>Gestione dei casi

Questo ruolo consente agli utenti di creare, modificare, eliminare e controllare l'accesso ai casi di eDiscovery nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere [Manage eDiscovery Cases in the Security & Compliance Center](manage-ediscovery-cases.md). Come spiegato in precedenza, è necessario assegnare a un utente il ruolo di gestione dei casi prima di poter utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per renderli un amministratore di eDiscovery. 

### <a name="compliance-search"></a>Ricerca di conformità

Questo ruolo consente agli utenti di eseguire lo strumento di ricerca contenuto nel centro sicurezza & Compliance per cercare le cassette postali e le cartelle pubbliche, i siti di SharePoint Online, i siti di OneDrive for business, le conversazioni di Skype for business, i gruppi di Office 365 e Microsoft teams. Questo ruolo consente a un utente di ottenere una stima dei risultati della ricerca e creare rapporti di esportazione, ma sono necessari ulteriori ruoli per avviare azioni di ricerca del contenuto, ad esempio la visualizzazione in anteprima, l'esportazione o l'eliminazione dei risultati di ricerca.

Si noti che gli utenti assegnati al ruolo di ricerca di conformità ma non dispongono del ruolo di anteprima possono visualizzare in anteprima i risultati di una ricerca in cui l'azione di anteprima è stata avviata da un utente a cui è assegnato il ruolo di anteprima. Se l'utente non ha il ruolo di anteprima, è possibile visualizzare in anteprima i risultati per un massimo di 2 settimane dopo la creazione dell'azione iniziale.

Analogamente, gli utenti assegnati al ruolo di ricerca di conformità ma non dispongono del ruolo di esportazione possono scaricare i risultati di una ricerca in cui l'azione di esportazione è stata avviata da un utente a cui è stato assegnato il ruolo di esportazione. L'utente senza il ruolo di esportazione può scaricare i risultati di una ricerca per un massimo di 2 settimane dopo la creazione dell'azione iniziale di esportazione. Dopo di che non saranno in grado di scaricare i risultati, a meno che un utente con il ruolo di esportazione non riavvii l'esportazione.

Per ulteriori informazioni, vedere [Ricerca contenuto in Office 365](content-search.md). 

### <a name="export"></a>Esportazione

Il ruolo consente agli utenti di esportare i risultati di una ricerca di contenuto in un computer locale. Consente inoltre di preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. 

Per ulteriori informazioni sull'esportazione dei risultati della ricerca, vedere [Export Search Results from Security & Compliance Center](export-search-results.md).

### <a name="hold"></a>Tenere

Questo ruolo consente agli utenti di inserire il contenuto nelle cassette postali, nelle cartelle pubbliche, nei siti, nelle conversazioni di Skype for business e nei gruppi di Office 365. Quando il contenuto è in attesa, i proprietari di contenuto saranno comunque in grado di modificare o eliminare il contenuto originale, ma il contenuto verrà mantenuto fino alla rimozione del blocco o fino alla scadenza della durata del blocco. 

Per ulteriori informazioni sulle esenzioni, vedere:

- [casi di eDiscovery](ediscovery-cases.md) 
- [Panoramica dei criteri di conservazione](retention-policies.md)

### <a name="preview"></a>Anteprima

Questo ruolo consente agli utenti di visualizzare un elenco di elementi restituiti da una ricerca di contenuto. Sarà inoltre possibile aprire e visualizzare ogni elemento dall'elenco per visualizzarne il contenuto.

### <a name="review"></a>Verifica

Questo ruolo consente agli utenti di accedere ai dati del caso in Office 365 Advanced eDiscovery. Lo scopo principale di questo ruolo è offrire agli utenti l'accesso a Advanced eDiscovery. Gli utenti a cui è assegnato questo ruolo possono visualizzare e aprire l'elenco dei casi nella pagina eDiscovery nel centro sicurezza & conformità di cui sono membri. Dopo che l'utente ha eseguito l'accesso a un caso nel centro sicurezza & Compliance, è possibile fare clic su **passa a Advanced eDiscovery** per accedere ai dati del caso in Advanced eDiscovery e analizzarli. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di contenuto associata al caso o di eseguire altre attività di ricerca del contenuto o di gestione dei casi.

### <a name="rms-decrypt"></a>Decrittografia RMS

Questo ruolo consente agli utenti di decrittografare i messaggi di posta elettronica crittografati con RMS durante l'esportazione dei risultati di ricerca o la preparazione dei risultati di ricerca per l'analisi Per ulteriori informazioni sulla decrittografia dei risultati di ricerca durante l'esportazione, vedere [Export content search results](export-search-results.md).

### <a name="search-and-purge"></a>Ricerca ed eliminazione

Questo ruolo consente agli utenti di eseguire la rimozione di massa dei dati che corrispondono ai criteri di una ricerca di contenuto. Per ulteriori informazioni, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione di Office 365](search-for-and-delete-messages-in-your-organization.md). 


## <a name="more-information"></a>Ulteriori informazioni

- **Perché creare un amministratore di eDiscovery?** Come indicato in precedenza, un amministratore di eDiscovery è membro del gruppo di ruoli Gestore di eDiscovery e può visualizzare e accedere a tutti i casi di eDiscovery nell'organizzazione. La possibilità di accedere a tutti i casi di eDiscovery ha due importanti scopi: 
    
  - Se una persona che è l'unico membro di un caso di eDiscovery lascia l'organizzazione, nessuno (inclusi i membri del gruppo di ruoli Gestione organizzazione o un altro membro del gruppo di ruoli Gestore di eDiscovery) può accedere al caso di eDiscovery poiché non è membro di un caso. In questo caso, non esisterebbe alcun modo di accedere ai dati nel caso. Tuttavia, poiché un amministratore di eDiscovery può accedere a tutti i casi di eDiscovery nell'organizzazione, è possibile visualizzare il caso e aggiungere se stessi o un altro responsabile di eDiscovery come membro del caso.
    
  - Poiché un amministratore di eDiscovery può visualizzare e accedere a tutti i casi di eDiscovery, è in grado di controllare e controllare tutti i casi e le ricerche di conformità associate. Ciò può contribuire a impedire qualsiasi utilizzo improprio delle ricerche di conformità o dei casi di eDiscovery. Poiché gli amministratori di eDiscovery possono accedere alle informazioni potenzialmente riservate nei risultati di una ricerca di conformità, è necessario limitare il numero di utenti che sono amministratori di eDiscovery.
    
    Inoltre, gli amministratori di eDiscovery vengono aggiunti automaticamente come amministratori in Advanced eDiscovery. Questo significa che un utente deve essere un amministratore di eDiscovery per eseguire attività amministrative in eDiscovery avanzata, ad esempio la configurazione degli utenti, la creazione di case e l'importazione di dati in un caso.
    
- **È possibile aggiungere un gruppo come membro del gruppo di ruoli Gestione di eDiscovery?** Come illustrato in precedenza, è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo dei responsabili di eDiscovery nel gruppo di ruoli Gestione eDiscovery utilizzando il cmdlet **Add-RoleGroupMember** in PowerShell Center di sicurezza & Compliance. Ad esempio, è possibile eseguire il comando riportato di seguito per aggiungere un gruppo di sicurezza abilitato alla posta elettronica al gruppo di ruoli eDiscovery Manager. 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Si noti che un gruppo di distribuzione di Exchange o un gruppo di Office 365 non è supportato. È necessario utilizzare un gruppo di sicurezza abilitato alla posta elettronica, che è possibile creare in PowerShell di Exchange Online ` New-DistributionGroup -Type Security ` utilizzando il comando. È inoltre possibile creare un gruppo di sicurezza abilitato alla posta elettronica (e aggiungere membri) nell'interfaccia di amministrazione di Exchange o nell'interfaccia di amministrazione di Microsoft 365. Tenere presente che potrebbero essere necessari fino a 60 minuti dopo la creazione di una nuova sicurezza abilitata alla posta elettronica da aggiungere al gruppo di ruoli eDiscovery managers. 
    
    Anche come indicato in precedenza, non è possibile creare un gruppo di sicurezza abilitato alla posta elettronica con un amministratore di eDiscovery utilizzando il cmdlet **Add-eDiscoveryCaseAdmin** nel centro sicurezza & Compliance Center PowerShell. È possibile aggiungere solo singoli utenti come amministratori di eDiscovery. 
    
    Si noti che non è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro di un caso.
