---
title: Assegnare le autorizzazioni di eDiscovery nel centro sicurezza & Compliance
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
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Assegnare le autorizzazioni necessarie per eseguire le attività relative a eDiscovery utilizzando il Centro sicurezza & Compliance.
ms.openlocfilehash: 76ec07909fab35dfbead806befe2565f4e2054ae
ms.sourcegitcommit: 21977f5cb6b01aee5cae54979717530b2a31a46a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "44411033"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Assegnare le autorizzazioni di eDiscovery nel centro sicurezza & Compliance

Se si desidera che gli utenti utilizzino gli [strumenti correlati a eDiscovery](ediscovery.md) nel centro sicurezza & compliance in Office 365 o nel centro conformità di Microsoft 365, è necessario assegnare loro le autorizzazioni appropriate. Il modo più semplice per eseguire questa operazione consiste nell'aggiungere la persona del gruppo di ruoli appropriato nella pagina **autorizzazioni** nel centro sicurezza & conformità. In questo argomento vengono descritte le autorizzazioni necessarie per eseguire le attività relative alla ricerca di eDiscovery e al contenuto utilizzando il Centro sicurezza & Compliance.
  
Il gruppo di ruoli principale di eDiscovery nel centro sicurezza & conformità è denominato **eDiscovery Manager**. Sono presenti due sottogruppi all'interno di questo gruppo di ruoli. 
  
- **eDiscovery** managers-un Manager di eDiscovery può utilizzare lo strumento di ricerca del contenuto nel centro sicurezza & conformità per cercare i percorsi di contenuto nell'organizzazione ed eseguire diverse azioni correlate alla ricerca, ad esempio l'anteprima e l'esportazione dei risultati della ricerca. I membri possono inoltre creare e gestire i casi di eDiscovery di base e i casi di eDiscovery avanzati, aggiungere e rimuovere membri in un caso, creare case, eseguire ricerche associate a un caso e accedere ai dati del caso. i responsabili di eDiscovery possono accedere e gestire solo i casi creati. Non possono accedere o gestire i casi creati da altri gestori di eDiscovery.
  
- **amministratori di eDiscovery** -un amministratore di eDiscovery è un membro del gruppo di ruoli di eDiscovery Manager ed è in grado di eseguire le stesse attività correlate alla ricerca di contenuto e alla gestione dei casi che può essere eseguito da un responsabile di eDiscovery. Inoltre, un amministratore di eDiscovery è in grado di:
  
  - Accedere a tutti i casi elencati nelle pagine di **eDiscovery** e **Advanced eDiscovery** nel centro sicurezza & Compliance.

  - Accedere ai dati del caso in Advanced eDiscovery per tutti i casi nell'organizzazione.
  
  - Gestire qualsiasi caso di eDiscovery dopo essersi aggiunti come membri del caso.
  
  Vedere la sezione [ulteriori informazioni](#more-information) per motivi per i quali potrebbe essere opportuno che gli amministratori di eDiscovery nell'organizzazione.

> [!NOTE]
> Per analizzare i dati di un utente tramite Advanced eDiscovery, è necessario che all'utente (custode dei dati) venga assegnata una licenza di Office 365 E5 o Microsoft 365 E5. In alternativa, gli utenti che dispongono di una licenza di Office 365 E1 o di Office 365 o Microsoft 365 E3 possono essere assegnati a una licenza Microsoft 365 E5 o a Microsoft 365 eDiscovery e di controllo del componente aggiuntivo. Gli amministratori, i responsabili della conformità o il personale legale assegnato ai casi come membri e utilizzano Advanced eDiscovery per raccogliere, visualizzare e analizzare i dati non hanno bisogno di una licenza E5. Per ulteriori informazioni sulle licenze avanzate di eDiscovery, vedere [Introduzione a Advanced eDiscovery](get-started-with-advanced-ediscovery.md).
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario essere membri del gruppo di ruoli Gestione organizzazione o essere assegnati al ruolo di gestione ruolo per assegnare le autorizzazioni di eDiscovery nel centro sicurezza & conformità.
    
- È possibile utilizzare il cmdlet [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) in PowerShell per la sicurezza & Compliance Center per aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo responsabili di eDiscovery nel gruppo di ruoli di eDiscovery Manager. Tuttavia, non è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica al sottogruppo Administrators di eDiscovery. Per informazioni dettagliate, vedere la sezione [ulteriori informazioni](#more-information) . 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Assegnare le autorizzazioni di eDiscovery nel centro sicurezza & Compliance

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere usando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro del Centro sicurezza e conformità, selezionare **autorizzazioni**, quindi selezionare la casella di controllo accanto a **eDiscovery Manager**.
    
4. Nella pagina riquadro a comparsa di **eDiscovery Manager** , eseguire una delle operazioni seguenti in base alle autorizzazioni di eDiscovery che si desidera assegnare. 
  
    **Per rendere un utente un responsabile di eDiscovery:** Accanto a **eDiscovery Manager**, selezionare **modifica**. Nella sezione **Choose eDiscovery Manager** selezionare il collegamento ipertestuale **eDiscovery Manager** e quindi fare clic su Aggiungi ![ icona ](../media/ITPro-EAC-AddIcon.gif) **Aggiungi**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come Manager di eDiscovery e quindi fare clic su **Aggiungi**. Dopo aver aggiunto gli utenti, fare clic su **fine**. Quindi, nella pagina **modifica scegliere** il riquadro a comparsa di eDiscovery Manager selezionare **Salva** per salvare le modifiche apportate all'appartenenza di eDiscovery Manager.
  
    **Per rendere un utente un amministratore di eDiscovery:** Accanto a **eDiscovery Manager**, selezionare **modifica**. Nella sezione **selezione amministratore di eDiscovery** , in **eDiscovery Administrators**, selezionare **Choose eDiscovery Administrator**, Select **Edit**e quindi ![ Add Icon ](../media/ITPro-EAC-AddIcon.gif) **Add**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come **amministratore di eDiscovery**e quindi **aggiungere**. Dopo aver aggiunto gli utenti, fare clic su **fine**. Quindi, nella pagina **modifica scegliere** il riquadro a comparsa di amministratore di eDiscovery, selezionare **Salva** per salvare le modifiche apportate all'appartenenza all'amministratore di eDiscovery.
      
> [!NOTE]
> È inoltre possibile utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per rendere un utente un amministratore di eDiscovery. Tuttavia, all'utente deve essere assegnato il ruolo di gestione dei casi prima che sia possibile utilizzare questo cmdlet per renderli un amministratore di eDiscovery. Per ulteriori informazioni, vedere [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
Nella pagina **autorizzazioni** nel centro sicurezza & conformità è inoltre possibile assegnare agli utenti le autorizzazioni relative a eDiscovery aggiungendole ai gruppi di ruoli amministratore conformità, Gestione organizzazione e revisore. Per una descrizione dei ruoli RBAC relativi a eDiscovery assegnati a ognuno di questi gruppi di ruoli, vedere i [ruoli RBAC relativi alla sezione eDiscovery](#rbac-roles-related-to-ediscovery) . 

## <a name="rbac-roles-related-to-ediscovery"></a>Ruoli RBAC relativi a eDiscovery

Nella tabella seguente sono elencati i ruoli RBAC relativi a eDiscovery nel centro sicurezza & compliance e sono indicati i gruppi di ruoli incorporati a cui ogni ruolo è assegnato per impostazione predefinita. 
    
|**Ruolo**|**Amministratore di conformità**|**Amministratore & di eDiscovery Manager**|**Gestione organizzazione**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gestione dei casi <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Comunicazione <br/> | <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Ricerca di conformità <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Custode <br/> | <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Esporta <br/> | <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Anteprima <br/>  | <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Revisione <br/>  | <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|Decrittografia RMS <br/>  ||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Ricerca ed eliminazione <br/> | <br/> | <br/> |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
Nelle sezioni seguenti vengono descritti i ruoli RBAC relativi a eDiscovery elencati nella tabella precedente.

### <a name="case-management"></a>Gestione dei casi

Questo ruolo consente agli utenti di creare, modificare, eliminare e controllare l'accesso a eDiscovery di base e i casi avanzati di eDiscovery nel centro sicurezza & conformità. Come spiegato in precedenza, è necessario assegnare a un utente il ruolo di gestione dei casi prima di poter utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per renderli un amministratore di eDiscovery.

Per altre informazioni, vedere:

- [Introduzione a Core eDiscovery](get-started-core-ediscovery.md)

- [Introduzione ad Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicazione

Questo ruolo consente agli utenti di gestire tutte le comunicazioni con i depositari identificati in un caso di eDiscovery avanzato. Ciò include la creazione di notifiche di blocco, il promemoria di blocco e l'escalation alla gestione. L'utente può anche tenere conto dei messaggi di conferma delle notifiche di esenzione e gestire l'accesso al portale di custode utilizzato da ogni custode per tenere conto delle comunicazioni per i casi in cui sono stati identificati come depositari.

Per ulteriori informazioni, vedere [work with Communications in Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Ricerca di conformità

Questo ruolo consente agli utenti di eseguire lo strumento di ricerca contenuto nel centro sicurezza & conformità per cercare le cassette postali e le cartelle pubbliche, i siti di SharePoint Online, i siti di OneDrive for business, le conversazioni di Skype for business, i gruppi Microsoft 365 e Microsoft teams e i gruppi Yammer. Questo ruolo consente a un utente di ottenere una stima dei risultati della ricerca e creare rapporti di esportazione, ma sono necessari ulteriori ruoli per avviare azioni di ricerca del contenuto, ad esempio la visualizzazione in anteprima, l'esportazione o l'eliminazione dei risultati di ricerca.

Gli utenti a cui è assegnato il ruolo di ricerca di conformità ma che non dispongono del ruolo anteprima possono visualizzare in anteprima i risultati di una ricerca in cui l'azione di anteprima è stata avviata da un utente a cui è stato assegnato il ruolo di anteprima. Se l'utente non ha il ruolo di anteprima, è possibile visualizzare in anteprima i risultati per un massimo di due settimane dopo la creazione dell'azione iniziale.

Analogamente, gli utenti a cui è assegnato il ruolo di ricerca di conformità ma non dispongono del ruolo di esportazione possono scaricare i risultati di una ricerca in cui l'azione di esportazione è stata avviata da un utente a cui è stato assegnato il ruolo di esportazione. L'utente senza il ruolo di esportazione può scaricare i risultati di una ricerca per un massimo di due settimane dopo la creazione dell'azione iniziale di esportazione. Successivamente, non è possibile scaricare i risultati a meno che un utente con il ruolo di esportazione riavvii l'esportazione.

Per ulteriori informazioni, vedere [Ricerca contenuto in Office 365](content-search.md).

### <a name="custodian"></a>Custode

Questo ruolo consente agli utenti di identificare e gestire i depositari per i casi avanzati di eDiscovery e di utilizzare le informazioni di Azure Active Directory e di altre origini per individuare origini dati associate ai depositari. L'utente può associare altre origini dati, ad esempio le cassette postali, i siti di SharePoint e i team con depositari in un caso. L'utente può anche inserire un blocco legale sulle origini dati associate ai depositari per conservare il contenuto nel contesto di un caso.

Per ulteriori informazioni, vedere [lavorare con i depositari in Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Esporta

Il ruolo consente agli utenti di esportare i risultati di una ricerca di contenuto in un computer locale. Consente inoltre di preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. 

Per ulteriori informazioni sull'esportazione dei risultati della ricerca, vedere [Export Search Results from Security & Compliance Center](export-search-results.md).

### <a name="hold"></a>Hold

Questo ruolo consente agli utenti di inserire il contenuto nelle cassette postali, nelle cartelle pubbliche, nei siti, nelle conversazioni di Skype for business e nei gruppi Microsoft 365. Quando il contenuto è in attesa, i proprietari di contenuto possono comunque modificare o eliminare il contenuto originale, ma il contenuto viene mantenuto finché il blocco non viene rimosso o fino alla scadenza della durata del blocco. 

Per ulteriori informazioni sulle esenzioni, vedere:

- [Creare un'esenzione in core eDiscovery](create-ediscovery-holds.md) 

- [Creare un'esenzione in Advanced eDiscovery](add-custodians-to-case.md#step-4-place-custodians-on-hold)

### <a name="preview"></a>Anteprima

Questo ruolo consente agli utenti di visualizzare un elenco di elementi restituiti da una ricerca di contenuto. È inoltre possibile aprire e visualizzare ogni elemento dall'elenco per visualizzarne il contenuto.

### <a name="review"></a>Revisione

Questo ruolo consente agli utenti di accedere ai dati del caso in [Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md) (noto anche come *Advanced eDiscovery V1*). Lo scopo principale di questo ruolo è offrire agli utenti l'accesso a Advanced eDiscovery (Classic). Gli utenti a cui è assegnato questo ruolo possono visualizzare e aprire l'elenco dei casi nella pagina **eDiscovery** nel centro sicurezza & Compliance di cui sono membri. Dopo che l'utente ha eseguito l'accesso a un caso nel centro sicurezza & Compliance, è possibile selezionare **passa a Advanced eDiscovery** per accedere ai dati del caso in Advanced eDiscovery (Classic) e analizzarli. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di contenuto associata al caso o di eseguire altre attività di ricerca contenuto o di gestione dei casi.

> [!NOTE]
> A questo punto, gli utenti a cui è stato assegnato il ruolo di revisione (o sono membri del gruppo di ruolo Reviewer) non possono accedere ai dati in [Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md) (noto anche come *Advanced eDiscovery V2*). Per aggiungere membri a un caso in Advanced eDiscovery V2 in modo che possano esaminare i dati dei casi, un utente deve essere membro del gruppo di ruoli Gestione eDiscovery.

### <a name="rms-decrypt"></a>Decrittografia RMS

Questo ruolo consente agli utenti di decrittografare i messaggi di posta elettronica protetti da diritti quando si esportano i risultati della ricerca o la preparazione dei risultati di ricerca per analisi Per ulteriori informazioni sulla decrittografia dei risultati di ricerca durante l'esportazione, vedere [Export content search results](export-search-results.md).

### <a name="search-and-purge"></a>Ricerca ed eliminazione

Questo ruolo consente agli utenti di eseguire la rimozione di massa dei dati che corrispondono ai criteri di una ricerca di contenuto. Per ulteriori informazioni, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione](search-for-and-delete-messages-in-your-organization.md). 

## <a name="more-information"></a>Ulteriori informazioni

- **Perché creare un amministratore di eDiscovery?** Come indicato in precedenza, un amministratore di eDiscovery è membro del gruppo di ruoli Gestore di eDiscovery e può visualizzare e accedere a tutti i casi di eDiscovery nell'organizzazione. La possibilità di accedere a tutti i casi di eDiscovery ha due importanti scopi: 

  - Se una persona che è l'unico membro di un caso di eDiscovery lascia l'organizzazione, nessuno (inclusi i membri del gruppo di ruoli Gestione organizzazione o un altro membro del gruppo di ruoli Gestore di eDiscovery) può accedere al caso di eDiscovery poiché non è membro di un caso. In questo caso, non esisterebbe alcun modo di accedere ai dati nel caso. Tuttavia, poiché un amministratore di eDiscovery può accedere a tutti i casi di eDiscovery nell'organizzazione, è possibile visualizzare il caso e aggiungere se stessi o un altro responsabile di eDiscovery come membro del caso.

  - Poiché un amministratore di eDiscovery è in grado di visualizzare e accedere a tutti i casi di eDiscovery e Advanced eDiscovery, è in grado di controllare e controllare tutti i casi e le ricerche di conformità associate. Ciò può contribuire a impedire qualsiasi utilizzo improprio delle ricerche di conformità o dei casi di eDiscovery. Poiché gli amministratori di eDiscovery possono accedere alle informazioni potenzialmente riservate nei risultati di una ricerca di conformità, è necessario limitare il numero di utenti che sono amministratori di eDiscovery.

- **È possibile aggiungere un gruppo come membro del gruppo di ruoli Gestione di eDiscovery?** Come illustrato in precedenza, è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo dei responsabili di eDiscovery nel gruppo di ruoli Gestione eDiscovery utilizzando il cmdlet **Add-RoleGroupMember** in PowerShell Center di sicurezza & Compliance. Ad esempio, è possibile eseguire il comando riportato di seguito per aggiungere un gruppo di sicurezza abilitato alla posta elettronica al gruppo di ruoli eDiscovery Manager. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    I gruppi di distribuzione di Exchange e i gruppi Microsoft 365 non sono supportati. È necessario utilizzare un gruppo di sicurezza abilitato alla posta elettronica, che è possibile creare in PowerShell di Exchange Online utilizzando il `New-DistributionGroup -Type Security` comando. È inoltre possibile creare un gruppo di sicurezza abilitato alla posta elettronica (e aggiungere membri) nell'interfaccia di amministrazione di Exchange o nell'interfaccia di amministrazione di Microsoft 365. La creazione di una nuova sicurezza abilitata alla posta elettronica potrebbe richiedere fino a 60 minuti per essere disponibile per l'aggiunta al gruppo di ruoli eDiscovery managers. 

    Anche come indicato in precedenza, non è possibile creare un gruppo di sicurezza abilitato alla posta elettronica con un amministratore di eDiscovery utilizzando il cmdlet **Add-eDiscoveryCaseAdmin** nel centro sicurezza & Compliance Center PowerShell. È possibile aggiungere solo singoli utenti come amministratori di eDiscovery.

    Non è inoltre possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro di un caso.
