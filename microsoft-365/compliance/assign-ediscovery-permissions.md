---
title: Assegnare le autorizzazioni di eDiscovery nel Centro sicurezza & conformità
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
description: Assegnare le autorizzazioni necessarie per eseguire le attività correlate a eDiscovery utilizzando il Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d4be264791c4f3d37d7a88cb3d12d1023b3c347
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759890"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Assegnare le autorizzazioni di eDiscovery nel Centro sicurezza & conformità

Se si desidera che gli utenti utilizzino uno degli strumenti correlati a [eDiscovery](ediscovery.md) nel Centro sicurezza & conformità in Office 365 o nel Centro conformità Microsoft 365, è necessario assegnare loro le autorizzazioni appropriate. Il modo più semplice per eseguire questa operazione è  aggiungere la persona al gruppo di ruoli appropriato nella pagina Autorizzazioni del Centro sicurezza & conformità. In questo argomento vengono descritte le autorizzazioni necessarie per eseguire attività correlate a eDiscovery e Ricerca contenuto utilizzando il Centro sicurezza & conformità.
  
Il gruppo di ruoli principale correlato a eDiscovery nel Centro sicurezza & conformità è denominato **gestore di eDiscovery.** Esistono due sottogruppi all'interno di questo gruppo di ruoli.
  
- Responsabili di **eDiscovery:** un responsabile di eDiscovery può utilizzare lo strumento Ricerca contenuto nel Centro sicurezza & conformità per cercare i percorsi dei contenuti nell'organizzazione ed eseguire varie azioni correlate alla ricerca, ad esempio l'anteprima e l'esportazione dei risultati della ricerca. I membri possono anche creare e gestire casi in Core eDiscovery e Advanced eDiscovery, aggiungere e rimuovere membri a un caso, creare blocchi dei casi, eseguire ricerche associate a un caso e accedere ai dati del caso. I responsabili di eDiscovery possono accedere e gestire solo i casi creati. Non possono accedere o gestire i casi creati da altri responsabili di eDiscovery.
  
- Amministratori di **eDiscovery:** un amministratore di eDiscovery è un membro del gruppo di ruoli Gestore di eDiscovery ed è in grado di eseguire le stesse attività di ricerca del contenuto e di gestione dei casi che un manager di eDiscovery può eseguire. Inoltre, un amministratore di eDiscovery è in grado di:
  
  - Accedere a tutti i casi elencati nelle pagine **eDiscovery** ed **Advanced eDiscovery** nel Centro sicurezza & conformità.

  - Accedere ai dati dei casi in Advanced eDiscovery per qualsiasi caso nell'organizzazione.
  
  - Gestire qualsiasi caso di eDiscovery dopo che si è aggiunto come membro del caso.
  
  Per i motivi per cui potrebbe essere necessario che gli amministratori di eDiscovery nell'organizzazione, vedere [Ulteriori informazioni.](#more-information)

> [!NOTE]
> Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (il responsabile dei dati) deve essere assegnata una licenza di Office 365 E5 o Microsoft 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o Office 365 o Microsoft 365 E3 può essere assegnata una licenza del componente aggiuntivo Microsoft 365 E5 Compliance o Microsoft 365 eDiscovery and Audit. Gli amministratori, i responsabili della conformità o il personale legale assegnati ai casi come membri e che utilizzano Advanced eDiscovery per raccogliere, visualizzare e analizzare i dati non necessitano di una licenza E5. Per ulteriori informazioni sulle licenze di Advanced eDiscovery, vedere [Introduzione ad Advanced eDiscovery.](get-started-with-advanced-ediscovery.md)
  
## <a name="confirm-your-roles"></a>Confermare i ruoli

- È necessario essere membri del gruppo di ruoli Gestione organizzazione o essere assegnati al ruolo Gestione ruoli per assegnare le autorizzazioni di eDiscovery nel Centro sicurezza & conformità.

- È possibile utilizzare il cmdlet [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) in PowerShell per Centro sicurezza & conformità per aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo Manager di eDiscovery nel gruppo di ruoli Gestore di eDiscovery. Tuttavia, non è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica al sottogruppo Amministratori di eDiscovery. Per informazioni dettagliate, vedere [Ulteriori informazioni.](#more-information) 
  
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Assegnare le autorizzazioni di eDiscovery nel Centro sicurezza & conformità

1. Passare a [https://protection.office.com](https://protection.office.com).
  
2. Accedere usando l'account di lavoro o della scuola.
  
3. Nel riquadro sinistro del Centro sicurezza e conformità selezionare Autorizzazioni **e** quindi selezionare la casella di controllo accanto a Gestore **di eDiscovery.**
  
4. Nella pagina **a comparsa di Gestione eDiscovery** eseguire una delle operazioni seguenti in base alle autorizzazioni di eDiscovery che si desidera assegnare.
  
    **Per impostare un utente come responsabile di eDiscovery:** Accanto a **Gestore di eDiscovery,** selezionare **Modifica.** Nella sezione **Choose eDiscovery Manager** selezionare il collegamento **ipertestuale Choose eDiscovery Manager** e quindi selezionare Add Icon ![ ](../media/ITPro-EAC-AddIcon.gif) **Add**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come manager di eDiscovery e quindi selezionare **Aggiungi**. Dopo aver aggiunto gli utenti, selezionare **Fine.** Quindi, nella pagina **a comparsa Modifica scegliere Gestore di eDiscovery,** selezionare **Salva** per salvare le modifiche apportate all'appartenenza al gestore di eDiscovery.
  
    **Per impostare un utente come amministratore di eDiscovery:** Accanto a **Gestore di eDiscovery,** selezionare **Modifica.** Nella sezione **Choose eDiscovery Administrator,** Under **eDiscovery Administrators,** select **Choose eDiscovery Administrator,** select **Edit,** and then select ![ Add Icon ](../media/ITPro-EAC-AddIcon.gif) **Add**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come amministratore **di eDiscovery,** quindi  **aggiungi**. Dopo aver aggiunto gli utenti, selezionare **Fine.** Quindi, nella pagina a comparsa Modifica scegliere l'amministratore di **eDiscovery,** selezionare **Salva** per salvare le modifiche apportate all'appartenenza dell'amministratore di eDiscovery.
  
> [!NOTE]
> È inoltre possibile utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per rendere un utente un amministratore di eDiscovery. Tuttavia, all'utente deve essere assegnato il ruolo Gestione casi prima di poter utilizzare questo cmdlet per renderlo un amministratore di eDiscovery. Per ulteriori informazioni, vedere [Add-eDiscoveryCaseAdmin.](https://go.microsoft.com/fwlink/p/?LinkID=798217) 
  
Nella pagina **Autorizzazioni** del Centro sicurezza & conformità è inoltre possibile assegnare agli utenti autorizzazioni correlate a eDiscovery aggiungendole ai gruppi di ruoli Amministratore conformità, Gestione organizzazione e Revisore. Per una descrizione dei ruoli RBAC correlati a eDiscovery assegnati a ognuno di questi gruppi di ruoli, vedere [Ruoli RBAC correlati a eDiscovery.](#rbac-roles-related-to-ediscovery)

## <a name="rbac-roles-related-to-ediscovery"></a>Ruoli RBAC correlati a eDiscovery

Nella tabella seguente sono elencati i ruoli RBAC correlati a eDiscovery nel Centro sicurezza & conformità e vengono indicati i gruppi di ruoli predefiniti a cui è assegnato ogni ruolo per impostazione predefinita.
  
| Ruolo | Amministratore di conformità | Amministratore & eDiscovery Manager | Gestione organizzazione | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gestione dei casi <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |
|Comunicazione <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Ricerca di conformità <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |
|Responsabile <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Esportazione <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |
|Anteprima <br/>  | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> | <br/> |
|Revisione <br/>  | <br/> |![Segno di spunta](../media/checkmark.png) <br/> | <br/> |![Segno di spunta](../media/checkmark.png) <br/> |
|Decrittografia RMS <br/>  ||![Segno di spunta](../media/checkmark.png) <br/> |||
|Ricerca ed eliminazione <br/> | <br/> | <br/> |![Segno di spunta](../media/checkmark.png)           <br/> | <br/> |
||||
  
Nelle sezioni seguenti viene descritto ognuno dei ruoli RBAC correlati a eDiscovery elencati nella tabella precedente.

### <a name="case-management"></a>Gestione dei casi

Questo ruolo consente agli utenti di creare, modificare, eliminare e controllare l'accesso ai casi di Core eDiscovery e Advanced eDiscovery nel Centro sicurezza & conformità. Come spiegato in precedenza, a un utente deve essere assegnato il ruolo Gestione casi prima di poter utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per renderlo un amministratore di eDiscovery.

Per altre informazioni, vedere:

- [Introduzione a Core eDiscovery](get-started-core-ediscovery.md)

- [Introduzione ad Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicazione

Questo ruolo consente agli utenti di gestire tutte le comunicazioni con i manager identificati in un caso di Advanced eDiscovery. Ciò include la creazione di notifiche di blocco, promemoria di blocco e escalation alla gestione. L'utente può anche tenere traccia del riconoscimento del responsabile delle notifiche di blocco e gestire l'accesso al portale dei responsabile usato da ogni responsabile per tenere traccia delle comunicazioni per i casi in cui sono stati identificati come responsabile.

Per ulteriori informazioni, vedere [Utilizzare le comunicazioni in Advanced eDiscovery.](managing-custodian-communications.md)

### <a name="compliance-search"></a>Ricerca di conformità

Questo ruolo consente agli utenti di eseguire lo strumento Ricerca contenuto nel Centro sicurezza & conformità per eseguire ricerche nelle cassette postali e nelle cartelle pubbliche, nei siti di SharePoint Online, nei siti di OneDrive for Business, nelle conversazioni skype for business, nei gruppi di Microsoft 365 e nei gruppi di Microsoft Teams e Yammer. Questo ruolo consente a un utente di ottenere una stima dei risultati della ricerca e di creare report di esportazione, ma sono necessari ruoli aggiuntivi per avviare azioni di ricerca contenuto, ad esempio l'anteprima, l'esportazione o l'eliminazione dei risultati della ricerca.

Gli utenti a cui è assegnato il ruolo Ricerca di conformità ma che non dispongono del ruolo Anteprima possono visualizzare in anteprima i risultati di una ricerca in cui l'azione di anteprima è stata avviata da un utente a cui è assegnato il ruolo Anteprima. L'utente senza il ruolo Anteprima può visualizzare in anteprima i risultati per un massimo di due settimane dopo la creazione dell'azione di anteprima iniziale.

Analogamente, gli utenti a cui è assegnato il ruolo Ricerca di conformità ma che non dispongono del ruolo Di esportazione possono scaricare i risultati di una ricerca in cui l'azione di esportazione è stata avviata da un utente a cui è assegnato il ruolo di esportazione. L'utente senza il ruolo di esportazione può scaricare i risultati di una ricerca per un massimo di due settimane dopo la creazione dell'azione di esportazione iniziale. In seguito, non potranno scaricare i risultati a meno che un utente con il ruolo di esportazione non riavvii l'esportazione.

Per ulteriori informazioni, vedere [Ricerca contenuto in Office 365.](content-search.md)

### <a name="custodian"></a>Responsabile

Questo ruolo consente agli utenti di identificare e gestire i responsabile per i casi di Advanced eDiscovery e di utilizzare le informazioni di Azure Active Directory e di altre origini per trovare le origini dati associate ai manager. In un caso, l'utente può associare altre origini dati, ad esempio cassette postali, siti di SharePoint e Teams. L'utente può anche conservare legalmente le origini dati associate ai responsabile per conservare il contenuto nel contesto di un caso.

Per ulteriori informazioni, vedere [Collaborare con i responsabile in Advanced eDiscovery.](managing-custodians.md)

### <a name="export"></a>Esportazione

Il ruolo consente agli utenti di esportare i risultati di una ricerca di contenuto in un computer locale. Consente inoltre di preparare i risultati della ricerca per l'analisi in Advanced eDiscovery.

Per ulteriori informazioni sull'esportazione dei risultati della ricerca, vedere Esportare i risultati della ricerca dal [Centro sicurezza & conformità.](export-search-results.md)

### <a name="hold"></a>Hold

Questo ruolo consente agli utenti di mettere il contenuto in blocco nelle cassette postali, nelle cartelle pubbliche, nei siti, nelle conversazioni di Skype for Business e nei gruppi di Microsoft 365. Quando il contenuto è in attesa, i proprietari del contenuto possono comunque modificare o eliminare il contenuto originale, ma il contenuto verrà conservato fino alla rimozione o alla scadenza della durata del blocco.

Per ulteriori informazioni sulle esenzioni, vedere:

- [Creare un blocco in Core eDiscovery](create-ediscovery-holds.md) 

- [Creare un blocco in Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Anteprima

Questo ruolo consente agli utenti di visualizzare un elenco di elementi restituiti da una ricerca di contenuto. Possono inoltre aprire e visualizzare ogni elemento dell'elenco per visualizzarne il contenuto.

### <a name="review"></a>Revisione

Questo ruolo consente agli utenti di accedere ai set di revisione in [Advanced eDiscovery.](overview-ediscovery-20.md) Gli utenti a cui è assegnato questo ruolo possono visualizzare e aprire l'elenco dei casi nella pagina **eDiscovery > Avanzate** nel Centro conformità Microsoft 365 di cui sono membri. Dopo aver accesso a un caso di Advanced eDiscovery, l'utente può selezionare **Rivedere i set** per accedere ai dati del caso. Questo ruolo non consente all'utente di visualizzare in anteprima i risultati di una ricerca di raccolta associata al caso o di eseguire altre attività di ricerca o gestione dei casi. Gli utenti con questo ruolo possono accedere solo ai dati in un insieme da rivedere.

### <a name="rms-decrypt"></a>Decrittografia RMS

Questo ruolo consente agli utenti di visualizzare i messaggi di posta elettronica protetti da diritti quando visualizzano in anteprima i risultati della ricerca ed esportano i messaggi di posta elettronica protetti da diritti decrittografati. Questo ruolo consente inoltre agli utenti di visualizzare (ed esportare) un file crittografato con una tecnologia di crittografia [Microsoft](encryption.md) quando il file crittografato viene allegato a un messaggio di posta elettronica incluso nei risultati di una ricerca eDiscovery. Inoltre, questo ruolo consente agli utenti di esaminare ed eseguire query su allegati di posta elettronica crittografati aggiunti a un insieme di recensioni in Advanced eDiscovery. Per ulteriori informazioni sulla decrittografia in eDiscovery, vedere Decrittografia negli strumenti di eDiscovery di [Microsoft 365.](ediscovery-decryption.md)

### <a name="search-and-purge"></a>Ricerca ed eliminazione

Questo ruolo consente agli utenti di eseguire la rimozione in blocco dei dati corrispondenti ai criteri di una ricerca di contenuto. Per ulteriori informazioni, vedere [Cercare ed eliminare i messaggi di posta elettronica nell'organizzazione.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Ulteriori informazioni

- **Perché creare un amministratore di eDiscovery?** Come indicato in precedenza, un amministratore di eDiscovery è membro del gruppo di ruoli Gestore di eDiscovery e può visualizzare e accedere a tutti i casi di eDiscovery nell'organizzazione. La possibilità di accedere a tutti i casi di eDiscovery ha due importanti scopi:

  - Se una persona che è l'unico membro di un caso di eDiscovery lascia l'organizzazione, nessuno (inclusi i membri del gruppo di ruoli Gestione organizzazione o un altro membro del gruppo di ruoli Gestore di eDiscovery) può accedere al caso di eDiscovery poiché non è membro di un caso. In questo caso, non esisterebbe alcun modo di accedere ai dati nel caso. Tuttavia, poiché un amministratore di eDiscovery può accedere a tutti i casi di eDiscovery nell'organizzazione, può visualizzare il caso e aggiungere se stesso o un altro responsabile di eDiscovery come membro del caso.

  - Poiché un amministratore di eDiscovery può visualizzare e accedere a tutti i casi di Core eDiscovery e Advanced eDiscovery, può controllare e supervisionare tutti i casi e le ricerche di conformità associate. Ciò consente di evitare un uso improprio delle ricerche di conformità o dei casi di eDiscovery. Poiché gli amministratori di eDiscovery possono accedere a informazioni potenzialmente riservate nei risultati di una ricerca di conformità, è consigliabile limitare il numero di persone che sono amministratori di eDiscovery.

- **È possibile aggiungere un gruppo come membro del gruppo di ruoli Gestore di eDiscovery?** Come spiegato in precedenza, è possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro del sottogruppo Manager di eDiscovery nel gruppo di ruoli Gestore di eDiscovery utilizzando il cmdlet **Add-RoleGroupMember** in PowerShell per Centro sicurezza & conformità. Ad esempio, è possibile eseguire il comando seguente per aggiungere un gruppo di sicurezza abilitato alla posta elettronica al gruppo di ruoli Gestore di eDiscovery. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    I gruppi di distribuzione di Exchange e i gruppi di Microsoft 365 non sono supportati. È necessario utilizzare un gruppo di sicurezza abilitato alla posta elettronica, che è possibile creare in PowerShell di Exchange Online eseguendo `New-DistributionGroup -Type Security` . È inoltre possibile creare un gruppo di sicurezza abilitato alla posta elettronica (e aggiungere membri) nell'interfaccia di amministrazione di Exchange o nell'interfaccia di amministrazione di Microsoft 365. La creazione di una nuova protezione abilitata alla posta elettronica potrebbe richiedere fino a 60 minuti prima che sia disponibile per l'aggiunta al gruppo di ruoli Responsabili di eDiscovery. 

    Come indicato in precedenza, non è possibile impostare un gruppo di sicurezza abilitato alla posta elettronica come amministratore di eDiscovery utilizzando il cmdlet **Add-eDiscoveryCaseAdmin** in PowerShell per Centro sicurezza & conformità. È possibile aggiungere singoli utenti solo come amministratori di eDiscovery.

    Non è inoltre possibile aggiungere un gruppo di sicurezza abilitato alla posta elettronica come membro di un caso.
