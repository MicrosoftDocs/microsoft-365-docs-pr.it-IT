---
title: Assegnare le autorizzazioni di eDiscovery nel Centro conformità Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Assegnare le autorizzazioni necessarie per eseguire attività correlate a eDiscovery utilizzando il Centro conformità Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e75a18c338d2634ae3be93514ee518d9e91860
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194674"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>Assegnare le autorizzazioni di eDiscovery nel Centro conformità Microsoft 365

Se si desidera che gli utenti utilizzino uno degli strumenti correlati a [eDiscovery](ediscovery.md) nel Centro conformità Microsoft 365, è necessario assegnare loro le autorizzazioni appropriate. Il modo più semplice per eseguire questa operazione è aggiungere la persona al gruppo di ruoli appropriato nella **pagina Autorizzazioni** nel Centro conformità. In questo argomento vengono descritte le autorizzazioni necessarie per eseguire le attività di eDiscovery.
  
Il gruppo di ruoli principale correlato a eDiscovery in Centro conformità Microsoft 365 è denominato **eDiscovery Manager.** Questo gruppo di ruoli include due sottogruppi.
  
- **Responsabili di eDiscovery** : un responsabile di eDiscovery può utilizzare gli strumenti di ricerca di eDiscovery per cercare i percorsi di contenuto nell'organizzazione ed eseguire diverse azioni correlate alla ricerca, ad esempio l'anteprima e l'esportazione dei risultati della ricerca. I membri possono inoltre creare e gestire i casi in Core eDiscovery e Advanced eDiscovery, aggiungere e rimuovere membri a un caso, creare blocchi dei casi, eseguire ricerche associate a un caso e accedere ai dati del caso. I manager di eDiscovery possono solo accedere e gestire i casi creati personalmente e non quelli creati da altri manager eDiscovery.
  
- **Amministratori di eDiscovery**: l'amministratore di eDiscovery fa parte del gruppo di ruoli manager di eDiscovery e può eseguire le stesse attività correlate a Ricerca contenuto e gestione dei casi eseguibili da un manager di eDiscovery. Inoltre, un amministratore di eDiscovery è in grado di:
  
  - Accedere a tutti i casi elencati nelle **pagine Core eDiscovery** **e Advanced eDiscovery** nel Centro conformità Microsoft 365.

  - Accedere ai dati dei casi in Advanced eDiscovery per qualsiasi caso dell'organizzazione.
  
  - Gestire ogni caso di eDiscovery dopo essersi aggiunto come membro di tale caso.
  
  Per i motivi per cui potrebbe essere necessario che gli amministratori di eDiscovery nell'organizzazione, vedere [Ulteriori informazioni](#more-information).

> [!NOTE]
> Per analizzare i dati di un utente Advanced eDiscovery, all'utente (il responsabile dei dati) deve essere assegnata una licenza Office 365 E5 o Microsoft 365 E5 licenza. In alternativa, agli utenti con una licenza Office 365 E1 o Office 365 o Microsoft 365 E3 è possibile assegnare una licenza del componente aggiuntivo Microsoft 365 E5 Compliance o Microsoft 365 eDiscovery e controllo. Gli amministratori, i responsabili della conformità o il personale legale assegnato ai casi come membri e che usano Advanced eDiscovery per raccogliere, visualizzare e analizzare i dati non necessitano di una licenza E5. Per ulteriori informazioni sulle Advanced eDiscovery licenze, vedere [Sottoscrizioni e licenze in Advanced eDiscovery](overview-ediscovery-20.md#subscriptions-and-licensing).
  
## <a name="before-you-assign-permissions"></a>Prima di assegnare le autorizzazioni

- È necessario essere membri del gruppo di ruoli Gestione organizzazione o essere assegnati al ruolo Gestione ruoli per assegnare le autorizzazioni di eDiscovery nel Centro conformità Microsoft 365.

- È possibile utilizzare il cmdlet [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) in PowerShell del Centro sicurezza & conformità per aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo Manager eDiscovery nel gruppo di ruoli Manager eDiscovery. Tuttavia, non è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica al sottogruppo Amministratori di eDiscovery. Per informazioni dettagliate, [vedere More information](#more-information). 
  
## <a name="assign-ediscovery-permissions"></a>Assegnare autorizzazioni di eDiscovery

1. Accedere a <https://compliance.microsoft.com> e accedere con un account che può assegnare le autorizzazioni.
  
2. Nel riquadro sinistro dell'Centro conformità Microsoft 365 selezionare **Autorizzazioni.**

3. Nella pagina **Autorizzazioni & ruoli,** in **Centro conformità** fare clic su **Ruoli.**

4. Nella pagina **Ruoli centro conformità** selezionare Gestione **eDiscovery**.
  
5. Nella pagina **a comparsa gestione eDiscovery** eseguire una delle operazioni seguenti in base alle autorizzazioni di eDiscovery che si desidera assegnare.
  
    **Per impostare un utente come responsabile di eDiscovery:** Accanto a **Gestione eDiscovery** selezionare **Modifica.** Nella pagina **della procedura guidata Choose eDiscovery Manager** fare clic su Aggiungi icona ![ ](../media/ITPro-EAC-AddIcon.gif) **Aggiungi**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come manager di eDiscovery e quindi selezionare **Aggiungi**. Al termine dell'aggiunta degli utenti, selezionare **Fine.** Quindi, nella pagina **della procedura guidata Modifica Scegliere gestione eDiscovery,** selezionare **Salva** per salvare le modifiche apportate all'appartenenza a eDiscovery Manager.
  
    **Per impostare un utente come amministratore di eDiscovery:** Accanto a **Amministratore di eDiscovery,** selezionare **Modifica**. Nella pagina **Scegliere l'amministratore di eDiscovery** fare clic ![ su Aggiungi icona ](../media/ITPro-EAC-AddIcon.gif) **Aggiungi**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come amministratore **di eDiscovery** e quindi  **aggiungi**. Al termine dell'aggiunta degli utenti, selezionare **Fine.** Nella pagina Modifica della **procedura guidata Scegli amministratore di eDiscovery** selezionare **Salva** per salvare le modifiche apportate all'appartenenza all'amministratore di eDiscovery.
  
> [!NOTE]
> È inoltre possibile utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per rendere un utente un amministratore di eDiscovery. Tuttavia, all'utente deve essere assegnato il ruolo Gestione casi prima di poter utilizzare questo cmdlet per renderlo un amministratore di eDiscovery. Per ulteriori informazioni, vedere [Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin). 
  
Nella pagina **Autorizzazioni** del Centro conformità Microsoft 365, è inoltre possibile assegnare agli utenti autorizzazioni correlate a eDiscovery aggiungendole ai gruppi di ruoli Amministratore conformità, Gestione organizzazione e Revisore. Per una descrizione dei ruoli RBAC correlati a eDiscovery assegnati a ognuno di questi gruppi di ruoli, vedere [Ruoli RBAC correlati a eDiscovery](#rbac-roles-related-to-ediscovery).

## <a name="rbac-roles-related-to-ediscovery"></a>Ruoli RBAC correlati a eDiscovery

Nella tabella seguente sono elencati i ruoli RBAC correlati a eDiscovery nel Centro conformità Microsoft 365 e vengono indicati i gruppi di ruoli incorporati a cui ogni ruolo è assegnato per impostazione predefinita.
  
| Ruolo | Amministratore di conformità | Amministratore & eDiscovery | Gestione organizzazione | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gestione dei casi <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |
|Comunicazione <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Ricerca di conformità <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |
|Custode <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Esportazione <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |
|Anteprima <br/>  | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Revisione <br/>  | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> |
|Decrittografia RMS <br/>  ||![Segno di spunta](../media/checkmark.png) <br/> |||
|Ricerca ed eliminazione <br/> | <br/> | <br/> |![Segno di spunta](../media/checkmark.png)           <br/> | <br/> |
||||
  
Nelle sezioni seguenti vengono descritti tutti i ruoli RBAC correlati a eDiscovery elencati nella tabella precedente.

### <a name="case-management"></a>Gestione dei casi

Questo ruolo consente agli utenti di creare, modificare, eliminare e controllare l'accesso a Core eDiscovery e Advanced eDiscovery casi nel Centro conformità Microsoft 365. Come spiegato in precedenza, a un utente deve essere assegnato il ruolo Gestione casi prima di poter utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per renderlo un amministratore di eDiscovery.

Per altre informazioni, vedere:

- [Introduzione a Core eDiscovery](get-started-core-ediscovery.md)

- [Introduzione ad Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicazione

Questo ruolo consente agli utenti di gestire tutte le comunicazioni con i custodi identificati in un Advanced eDiscovery caso. Ciò include la creazione di notifiche di blocco, promemoria di blocco e escalation alla gestione. L'utente può anche tenere traccia del riconoscimento del responsabile delle notifiche di blocco e gestire l'accesso al portale di custodia utilizzato da ogni responsabile per tenere traccia delle comunicazioni per i casi in cui sono stati identificati come depositario.

Per ulteriori informazioni, vedere [Utilizzare le comunicazioni in Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Ricerca di conformità

Questo ruolo consente agli utenti di eseguire lo strumento ricerca contenuto nel Centro conformità Microsoft 365 per cercare cassette postali e cartelle pubbliche, siti di SharePoint Online, siti OneDrive for Business, conversazioni Skype for Business, gruppi di Microsoft 365 e Microsoft Teams e gruppi di Yammer. Questo ruolo consente a un utente di ottenere una stima dei risultati della ricerca e di creare report di esportazione, ma sono necessari altri ruoli per avviare azioni di ricerca del contenuto, ad esempio l'anteprima, l'esportazione o l'eliminazione dei risultati della ricerca.

In Ricerca contenuto ed eDiscovery di base, gli utenti a cui è assegnato il ruolo Ricerca di conformità ma che non dispongono del ruolo Anteprima possono visualizzare in anteprima i risultati di una ricerca in cui l'azione di anteprima è stata avviata da un utente a cui è assegnato il ruolo Anteprima. L'utente senza il ruolo Anteprima può visualizzare in anteprima i risultati per un massimo di due settimane dopo la creazione dell'azione di anteprima iniziale.

Analogamente, gli utenti in Ricerca contenuto e Core eDiscovery a cui è assegnato il ruolo Ricerca di conformità ma che non dispongono del ruolo Esporta possono scaricare i risultati di una ricerca in cui l'azione di esportazione è stata avviata da un utente a cui è assegnato il ruolo Esporta. L'utente senza il ruolo Esporta può scaricare i risultati di una ricerca fino a due settimane dopo la creazione dell'azione di esportazione iniziale. Successivamente, non possono scaricare i risultati a meno che un utente con il ruolo Esporta non riavvii l'esportazione.

Il periodo di tolleranza di due settimane per l'anteprima e l'esportazione dei risultati della ricerca (senza i ruoli di ricerca ed esportazione corrispondenti) non si applica Advanced eDiscovery. Agli utenti devono essere assegnati i ruoli Anteprima ed Esporta per visualizzare in anteprima ed esportare il contenuto in Advanced eDiscovery.

### <a name="custodian"></a>Custode

Questo ruolo consente agli utenti di identificare e gestire i Advanced eDiscovery e di utilizzare le informazioni di Azure Active Directory e altre origini per trovare le origini dati associate ai depositati. L'utente può associare altre origini dati, ad esempio cassette postali, SharePoint siti e Teams ai custodi in un caso. L'utente può anche conservare legalmente le origini dati associate ai custodi per conservare il contenuto nel contesto di un caso.

Per ulteriori informazioni, vedere [Utilizzare i custodi in Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Esportazione

Il ruolo consente agli utenti di esportare i risultati di una ricerca contenuto in un computer locale. Consente inoltre di preparare i risultati della ricerca per l'analisi in Advanced eDiscovery.

Per ulteriori informazioni sull'esportazione dei risultati della ricerca, vedere [Export search results from Centro conformità Microsoft 365](export-search-results.md).

### <a name="hold"></a>Hold

Questo ruolo consente agli utenti di mantenere il contenuto in cassette postali, cartelle pubbliche, siti, Skype for Business conversazioni e Microsoft 365 gruppi. Quando il contenuto è bloccato, i proprietari possono comunque modificare o eliminare il contenuto originale, ma questo verrà conservato fino alla rimozione o alla scadenza del blocco.

Per ulteriori informazioni sui blocchi, vedere:

- [Creare un blocco in Core eDiscovery](create-ediscovery-holds.md) 

- [Creare un'esenzione in Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Anteprima

Questo ruolo consente agli utenti di visualizzare un elenco di elementi restituiti da una ricerca contenuto. Possono anche aprire e visualizzare i singoli elementi dell'elenco per visualizzarne il contenuto.

### <a name="review"></a>Revisione

Questo ruolo consente agli utenti di accedere ai set di [revisione in Advanced eDiscovery](overview-ediscovery-20.md). Gli utenti assegnati a questo ruolo possono visualizzare e aprire l'elenco dei casi nella pagina **eDiscovery > Advanced** nel Centro conformità Microsoft 365 di cui sono membri. Dopo che l'utente accede a Advanced eDiscovery caso, può selezionare **Rivedi set per** accedere ai dati del caso. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di raccolta associata al caso o di eseguire altre attività di ricerca o gestione dei casi. Gli utenti con questo ruolo possono accedere solo ai dati in un set di revisione.

### <a name="rms-decrypt"></a>Decrittografia RMS

Questo ruolo consente agli utenti di visualizzare i messaggi di posta elettronica protetti da diritti quando visualizzano in anteprima i risultati della ricerca ed esportano i messaggi di posta elettronica protetti da diritti decrittografati. Questo ruolo consente inoltre agli utenti di visualizzare (ed esportare) un file crittografato con una tecnologia di crittografia [Microsoft](encryption.md) quando il file crittografato viene allegato a un messaggio di posta elettronica incluso nei risultati di una ricerca eDiscovery. Inoltre, questo ruolo consente agli utenti di esaminare ed eseguire query su allegati di posta elettronica crittografati aggiunti a un set di recensioni in Advanced eDiscovery. Per ulteriori informazioni sulla decrittografia in eDiscovery, vedere [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

### <a name="search-and-purge"></a>Ricerca ed eliminazione

Questo ruolo consente agli utenti di eseguire la rimozione in blocco dei dati corrispondenti ai criteri di una ricerca di contenuto. Per ulteriori informazioni, vedere [Cercare ed eliminare messaggi di posta elettronica nell'organizzazione.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Ulteriori informazioni

- **Perché creare un amministratore di eDiscovery?** Come indicato in precedenza, un amministratore di eDiscovery è membro del gruppo di ruoli Gestore di eDiscovery e può visualizzare e accedere a tutti i casi di eDiscovery nell'organizzazione. La possibilità di accedere a tutti i casi di eDiscovery ha due importanti scopi:

  - Se una persona che è l'unico membro di un caso di eDiscovery lascia l'organizzazione, nessuno (inclusi i membri del gruppo di ruoli Gestione organizzazione o un altro membro del gruppo di ruoli Gestore di eDiscovery) può accedere al caso di eDiscovery poiché non è membro di un caso. In questo caso, non esisterebbe alcun modo di accedere ai dati nel caso. Tuttavia, poiché un amministratore di eDiscovery può accedere a tutti i casi di eDiscovery nell'organizzazione, può visualizzare il caso e aggiungere se stesso o un altro responsabile di eDiscovery come membro del caso.

  - Poiché un amministratore di eDiscovery può visualizzare e accedere a tutti i casi di base di eDiscovery e Advanced eDiscovery, può controllare e supervisionare tutti i casi e le ricerche di conformità associate. In questo modo si evita un uso improprio delle ricerche di conformità o dei casi di eDiscovery. Poiché gli amministratori di eDiscovery possono accedere a informazioni potenzialmente riservate nei risultati di una ricerca di conformità, è consigliabile limitare il numero di persone che sono amministratori di eDiscovery.

- **È possibile aggiungere un gruppo come membro del gruppo di ruoli Manager eDiscovery?** Come spiegato in precedenza, è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo Manager di eDiscovery nel gruppo di ruoli Gestione eDiscovery utilizzando il cmdlet **Add-RoleGroupMember** in PowerShell del Centro sicurezza & conformità. Ad esempio, è possibile eseguire il comando seguente per aggiungere un gruppo di sicurezza abilitato alla posta elettronica al gruppo di ruoli Manager eDiscovery. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange i gruppi di distribuzione e Microsoft 365 non sono supportati. È necessario utilizzare un gruppo di sicurezza abilitato alla posta elettronica, che è possibile creare in Exchange Online PowerShell eseguendo `New-DistributionGroup -Type Security` . È inoltre possibile creare un gruppo di sicurezza abilitato alla posta elettronica (e aggiungere membri) nell'interfaccia di amministrazione di Exchange o nella interfaccia di amministrazione di Microsoft 365. La creazione di una nuova sicurezza abilitata alla posta elettronica potrebbe richiedere fino a 60 minuti per essere disponibile per l'aggiunta al gruppo di ruoli Responsabili di eDiscovery. 

    Come indicato in precedenza, non è possibile impostare un gruppo di sicurezza abilitato alla posta elettronica come amministratore di eDiscovery utilizzando il cmdlet **Add-eDiscoveryCaseAdmin** in PowerShell & Centro sicurezza e conformità. È possibile aggiungere singoli utenti solo come amministratori di eDiscovery.

    Non è inoltre possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro di un caso.