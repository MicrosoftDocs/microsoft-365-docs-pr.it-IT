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
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Gli amministratori possono imparare ad assegnare o rimuovere autorizzazioni nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b53023521f477b5e864424ec648ccf7e5b749d0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166988"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Gestire i gruppi di ruoli in Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](https://go.microsoft.com/fwlink/?linkid=2148611)

Nelle organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per aggiungere utenti ai gruppi di ruoli. L'aggiunta di un utente a un gruppo di ruoli concede all'utente le autorizzazioni per eseguire attività amministrative specifiche. È inoltre possibile rimuovere utenti dai gruppi di ruoli.

Per ulteriori informazioni sui ruoli e sui gruppi di ruoli, vedere [Autorizzazioni in EOP autonomo.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire l'interfaccia di amministrazione di Exchange ( EAC), vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Per aprire PowerShell EOP autonomo, vedere [Connettersi a PowerShell di Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection. In particolare, è necessario **il ruolo Gestione** ruoli, assegnato al gruppo di ruoli Gestione organizzazione per impostazione predefinita.  Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Problemi? Chiedere assistenza nel forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-the-eac-to-manage-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per gestire i gruppi di ruoli

### <a name="use-the-eac-to-view-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare i gruppi di ruoli

1. Nell'interfaccia di amministrazione di Exchange, accedere ai **ruoli di** amministratore \> **delle autorizzazioni.** Qui sono elencati tutti i gruppi di ruoli nell'organizzazione.

2. Selezionare un gruppo di ruoli. Nel riquadro Dei dettagli vengono visualizzati **il nome,** **la** descrizione, i **ruoli assegnati** e gestiti **dal** gruppo di ruoli. È inoltre possibile visualizzare queste informazioni facendo clic **sull'icona** ![ ](../../media/ITPro-EAC-EditIcon.png) Modifica.

### <a name="use-the-eac-to-create-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare gruppi di ruoli

Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo). In caso contrario, è possibile copiare un gruppo di ruoli esistente e modificarlo.

1. Nell'interfaccia di amministrazione di Exchange, accedere **ai ruoli di** amministratore delle autorizzazioni e quindi eseguire una delle operazioni \> seguenti:

   - **Creare manualmente un nuovo gruppo di ruoli:** fare clic **sull'icona** ![ ](../../media/ITPro-EAC-AddIcon.png) Aggiungi.

   - **Copiare un gruppo di ruoli esistente:** selezionare il gruppo di ruoli che si desidera copiare, quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-CopyIcon.png) Copia.

2. Nella finestra **Nuovo gruppo di** ruoli visualizzata, configurare le impostazioni seguenti:

    - **Nome**: immettere un nome univoco per il gruppo di ruoli.

    - **Descrizione:** immettere una descrizione facoltativa per il gruppo di ruoli.

    - **Ruoli**: fare **clic sull'icona** Aggiungi o Rimuovi per selezionare o modificare i ruoli assegnati ![ al gruppo di ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ruoli.

    - **Membri**: fare clic **sull'icona** Aggiungi o Rimuovi ![ per modificare ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) l'appartenenza al gruppo di ruoli.

3. Al termine, fare clic su **Salva** per creare il gruppo di ruoli.

### <a name="use-the-eac-to-modify-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare i gruppi di ruoli

Nell'interfaccia di amministrazione di Exchange, accedere ai **ruoli di** amministratore delle autorizzazioni, selezionare il gruppo di ruoli che si desidera modificare, quindi fare clic \>  **sull'icona** ![ Modifica ](../../media/ITPro-EAC-EditIcon.png) modifica.

Le stesse opzioni sono disponibili quando si modificano i gruppi di ruoli come quando si creano i gruppi di ruoli. È possibile:

- Modificare il nome e la descrizione.

- Aggiungere e rimuovere ruoli di gestione (creare o rimuovere assegnazioni di ruolo).

- Aggiungere e rimuovere membri.

**Nota:** alcuni gruppi di ruoli (ad esempio, Gestione organizzazione) limitano i ruoli che è possibile rimuovere dal gruppo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli

1. Nell'interfaccia di amministrazione di Exchange, accedere **ai** ruoli di amministratore delle autorizzazioni, selezionare il gruppo di ruoli che si desidera modificare, quindi fare clic \>  **sull'icona** ![ Modifica ](../../media/ITPro-EAC-EditIcon.png) modifica.

2. Nella pagina delle proprietà del gruppo di ruoli visualizzata, nella **sezione** Membri, eseguire una delle operazioni seguenti:

   - Fare **clic su Aggiungi** ![ ](../../media/ITPro-EAC-AddIcon.png) icona. Nella pagina visualizzata individuare l'utente che si desidera aggiungere e quindi fare clic **su aggiungi ->**. Selezionare gli utenti e **fare clic su aggiungi ->** più volte in base alle esigenze. Al termine, fare clic su **OK**.

   - Selezionare gli utenti che si desidera rimuovere e quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.

3. Al termine, fare clic su **Salva**.

   > [!NOTE]
   > Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.

### <a name="use-the-eac-to-remove-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere i gruppi di ruoli

Non è possibile rimuovere i gruppi di ruoli incorporati, ma è possibile rimuovere i gruppi di ruoli personalizzati creati.

1. Nell'interfaccia di amministrazione di Exchange, accedere ai **ruoli di** amministratore \> **delle autorizzazioni.**

2. Selezionare il gruppo di ruoli che si desidera rimuovere, quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Elimina.

3. Fare clic su **Sì** nella finestra di conferma visualizzata.

## <a name="use-powershell-to-manage-role-groups"></a>Utilizzare PowerShell per gestire i gruppi di ruoli

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Utilizzare PowerShell EOP autonomo per visualizzare i gruppi di ruoli

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

In questo esempio vengono restituiti tutti i gruppi di ruoli in cui l'utente Julia è membro. È necessario utilizzare il valore DistinguishedName (DN) per Julia, che è possibile trovare eseguendo il comando: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Per ulteriori informazioni sulla sintassi e sui parametri, vedere [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Utilizzare PowerShell EOP autonomo per creare gruppi di ruoli

Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo). In caso contrario, è possibile copiare un gruppo di ruoli esistente e modificarlo.

- Per creare manualmente un nuovo gruppo di ruoli, utilizzare la sintassi seguente:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Il _parametro Roles_ consente di specificare i ruoli di gestione da assegnare al gruppo di ruoli utilizzando la sintassi `"Role1","Role1",..."RoleN"` seguente. È possibile visualizzare i ruoli disponibili utilizzando il cmdlet **Get-ManagementRole.**

  - Il _parametro Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` . È possibile specificare utenti, gruppi di protezione universali (USG) abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

  In questo esempio viene creato un nuovo gruppo di ruoli denominato "Limited Recipient Management" con le impostazioni seguenti:

  - Il ruolo Destinatari di posta viene assegnato al gruppo di ruoli.

  - Gli utenti Kim e Martin vengono aggiunti come membri.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Per copiare un gruppo di ruoli esistente, eseguire la procedura seguente:

  1. Archiviare il gruppo di ruoli che si desidera copiare in una variabile utilizzando la seguente sintassi:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Creare il nuovo gruppo di ruoli utilizzando la sintassi seguente:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Il _parametro Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` . È possibile specificare utenti, gruppi di protezione universali (USG) abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

     In questo esempio il gruppo di ruoli Gestione organizzazione viene copiato nel nuovo gruppo di ruoli denominato "Limited Organization Management". I membri del gruppo di ruoli sono Isabelle, Carter e Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Per informazioni dettagliate sulla sintassi e sui parametri, [Vedere New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Utilizzare PowerShell EOP autonomo per modificare l'elenco dei membri nei gruppi di ruoli

- I cmdlet **Add-RoleGroupMember** **e Remove-RoleGroupMember** aggiungono o rimuovono singoli membri uno alla volta. Il cmdlet **Update-RoleGroupMember** può sostituire o modificare l'elenco di membri esistente.

- I membri di un gruppo di ruoli possono essere utenti, gruppi di protezione universali (USG) abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

Per modificare i membri di un gruppo di ruoli, utilizzare la sintassi seguente:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Per _sostituire_ l'elenco di membri esistente con i valori specificati, utilizzare la sintassi seguente: `"Member1","Member2",..."MemberN"` .

- Per _modificare in modo selettivo_ l'elenco di membri esistente, utilizzare la sintassi seguente: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In questo esempio vengono sostituiti tutti i membri correnti del gruppo di ruoli Help Desk con gli utenti specificati.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In questo esempio Viene aggiunta Daigoro Akai e viene rimossa Valeria Barrio dall'elenco dei membri del gruppo di ruoli Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Update-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Utilizzare PowerShell EOP autonomo per rimuovere i gruppi di ruoli

Non è possibile rimuovere i gruppi di ruoli incorporati, ma è possibile rimuovere i gruppi di ruoli personalizzati creati.

Per rimuovere un gruppo di ruoli personalizzato, utilizzare la sintassi seguente:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

Questo esempio rimuove il gruppo di ruolo Formazione degli amministratori.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta copia di un gruppo di ruoli, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, accedere ai **ruoli di** amministratore delle autorizzazioni e verificare che il gruppo di ruoli sia \> elencato (o non elencato). Selezionare il gruppo di ruoli e verificare le impostazioni nel riquadro Dei dettagli oppure fare clic **sull'icona** ![ Modifica per verificare le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.

- In PowerShell di Exchange Online, sostituire con il nome del gruppo di ruoli ed eseguire il comando seguente per verificare che il gruppo di ruoli esista (o non esista) e verificare \<Role Group Name\> le impostazioni:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
