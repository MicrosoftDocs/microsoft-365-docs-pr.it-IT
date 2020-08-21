---
title: Gestire i gruppi di ruoli in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Gli amministratori possono imparare a assegnare o rimuovere le autorizzazioni nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online Protection.
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825690"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Gestire i gruppi di ruoli in Exchange Online Protection autonomo

Nelle organizzazioni standalone di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per aggiungere utenti ai gruppi di ruoli. L'aggiunta di un utente a un gruppo di ruoli consente alle autorizzazioni degli utenti di eseguire attività amministrative specifiche. È inoltre possibile rimuovere gli utenti dai gruppi di ruoli.

Per ulteriori informazioni sui ruoli e sui gruppi di ruolo, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire l'interfaccia di amministrazione di Exchange (EAC), vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per aprire PowerShell EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. In particolare, è necessario il ruolo di gestione dei ruoli, assegnato al gruppo di ruoli OrganizationManagement (Global Admins) per impostazione predefinita. Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-the-eac-to-manage-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per gestire gruppi di ruoli

### <a name="use-the-eac-to-view-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare gruppi di ruoli

1. Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**. Qui sono elencati tutti i gruppi di ruoli nell'organizzazione.

2. Selezionare un gruppo di ruoli. Nel riquadro dei dettagli vengono visualizzati il **nome**, la **Descrizione**, i **ruoli assegnati**e **gestiti dal** gruppo di ruoli. È inoltre possibile visualizzare queste informazioni facendo clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare gruppi di ruoli

Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni (durante la creazione del gruppo o dopo). In alternativa, è possibile copiare un gruppo di ruoli esistente e modificarlo.

1. Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**e quindi eseguire una delle operazioni seguenti:

   - **Creare manualmente un nuovo gruppo di ruoli**: fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .

   - **Copia di un gruppo di ruoli esistente**: selezionare il gruppo di ruoli che si desidera copiare e quindi fare clic su **copia** copia ![ icona ](../../media/ITPro-EAC-CopyIcon.png) .

2. Nella finestra **nuovo gruppo di ruoli** che viene visualizzata, configurare le seguenti impostazioni:

    - **Nome**: immettere un nome univoco per il gruppo di ruoli.

    - **Descrizione**: immettere una descrizione facoltativa per il gruppo di ruoli.

    - **Ruoli**: fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) o **rimuovere** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) per selezionare o modificare i ruoli assegnati al gruppo di ruoli.

    - **Membri**: fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) o **rimuovere** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) per modificare l'appartenenza a un gruppo di ruoli.

3. Al termine, fare clic su **Salva** per creare il gruppo di ruoli.

### <a name="use-the-eac-to-modify-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare gruppi di ruoli

Nell'interfaccia di amministrazione di Exchange, andare a ruoli di amministratore **delle autorizzazioni** \> **Admin roles**, selezionare il gruppo di ruoli che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .

Le stesse opzioni sono disponibili quando si modificano i gruppi di ruoli come quando si creano gruppi di ruoli. È possibile:

- Modificare il nome e la descrizione.

- Aggiungere e rimuovere i ruoli di gestione (creare o rimuovere le assegnazioni di ruolo).

- Aggiungere e rimuovere membri.

**Nota**: alcuni gruppi di ruoli, ad esempio Gestione organizzazione, limitano i ruoli che è possibile rimuovere dal gruppo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange modificare l'elenco dei membri nei gruppi di ruoli

1. Nell'interfaccia di amministrazione di Exchange, andare a ruoli di amministratore **delle autorizzazioni** \> **Admin roles**, selezionare il gruppo di ruoli che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .

2. Nella pagina delle proprietà del gruppo di ruoli che si apre, nella sezione **membri** , eseguire una delle operazioni seguenti:

   - Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) . Nella pagina che viene visualizzata, individuare l'utente che Wou desidera aggiungere, quindi fare clic su **Add->**. Selezionare utenti e fare clic su **Add->** molte volte, se necessario. Al termine, fare clic su **OK**.

   - Selezionare gli utenti che si desidera rimuovere, quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Al termine, scegliere **Salva**.

   > [!NOTE]
   > Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.

### <a name="use-the-eac-to-remove-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere gruppi di ruoli

Non è possibile rimuovere i gruppi di ruoli incorporati, ma possono essere rimossi i gruppi di ruoli personalizzati che sono stati creati.

1. Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**.

2. Selezionare il gruppo di ruoli che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Fare clic su **Sì** nella finestra di conferma che viene visualizzata.

## <a name="use-powershell-to-manage-role-groups"></a>Utilizzo di PowerShell per gestire i gruppi di ruoli

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Utilizzo di PowerShell EOP autonomo per visualizzare i gruppi di ruoli

Per visualizzare un gruppo di ruoli, utilizzare la sintassi seguente:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i gruppi di ruoli.

```PowerShell
Get-RoleGroup
```

In questo esempio vengono restituite informazioni dettagliate per il gruppo di ruoli denominato Recipient Administrators.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In questo esempio vengono restituiti tutti i gruppi di ruoli in cui l'utente Julia è membro. È necessario utilizzare il valore distinto (DN) per Julia, che può essere trovato eseguendo il comando: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Per ulteriori informazioni sulla sintassi e sui parametri, vedere [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Utilizzo di PowerShell EOP autonomo per creare gruppi di ruoli

Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo). In alternativa, è possibile copiare un gruppo di ruoli esistente e modificarlo.

- Per creare manualmente un nuovo gruppo di ruoli, utilizzare la sintassi seguente:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Il parametro _roles_ consente di specificare i ruoli di gestione da assegnare al gruppo di ruoli utilizzando la sintassi seguente `"Role1","Role1",..."RoleN"` . È possibile visualizzare i ruoli disponibili utilizzando il cmdlet **Get-ManagementRole** .

  - Il parametro _Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` . È possibile specificare gli utenti, i gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

  In questo esempio viene creato un nuovo gruppo di ruoli denominato "Limited Recipient Management" con le seguenti impostazioni:

  - Il ruolo Destinatari di posta viene assegnato al gruppo di ruoli.

  - Gli utenti Kim e Martin vengono aggiunti come membri.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Per copiare un gruppo di ruoli esistente, eseguire le operazioni seguenti:

  1. Archiviare il gruppo di ruoli che si desidera copiare in una variabile utilizzando la seguente sintassi:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Creare il nuovo gruppo di ruoli utilizzando la sintassi seguente:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Il parametro _Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` . È possibile specificare gli utenti, i gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

     In questo esempio il gruppo di ruoli Gestione organizzazione viene copiato nel nuovo gruppo di ruoli denominato "Gestione organizzazione limitata". I membri del gruppo di ruoli sono Isabelle, Carter e Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Per informazioni dettagliate sulla sintassi e sui parametri, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Utilizzo di EOP autonomo PowerShell modificare l'elenco dei membri nei gruppi di ruoli

- I cmdlet **Add-RoleGroupMember** e **Remove-RoleGroupMember** aggiungono o rimuovono singoli membri uno alla volta. Il cmdlet **Update-RoleGroupMember** è in grado di sostituire o modificare l'elenco dei membri esistente.

- I membri di un gruppo di ruoli possono essere utenti, gruppi di protezione universali abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

Per modificare i membri di un gruppo di ruoli, utilizzare la sintassi seguente:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Per _sostituire_ l'elenco esistente di membri con i valori specificati, utilizzare la sintassi seguente: `"Member1","Member2",..."MemberN"` .

- Per _modificare in modo selettivo_ l'elenco di membri esistente, utilizzare la sintassi seguente: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In questo esempio vengono sostituiti tutti i membri correnti del gruppo di ruolo Help Desk con gli utenti specificati.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

Questo esempio aggiunge Daigoro Akai e rimuove Valeria Barrio dall'elenco dei membri del gruppo di ruolo Help desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Utilizzo di PowerShell EOP autonomo per rimuovere i gruppi di ruoli

Non è possibile rimuovere i gruppi di ruoli incorporati, ma possono essere rimossi i gruppi di ruoli personalizzati che sono stati creati.

Per rimuovere un gruppo di ruoli personalizzato, utilizzare la sintassi seguente:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

Questo esempio rimuove il gruppo di ruolo Formazione degli amministratori.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta copia di un gruppo di ruoli, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**e verificare che il gruppo di ruoli sia elencato (o non elencato). Selezionare il gruppo di ruoli e verificare le impostazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) per verificare le impostazioni.

- In Exchange Online PowerShell, sostituire \<Role Group Name\> con il nome del gruppo di ruolo ed eseguire il comando riportato di seguito per verificare che il gruppo di ruoli esista (o non esista) e verificare le impostazioni:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
