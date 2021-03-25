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
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206273"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Gestire i gruppi di ruoli in Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

Nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per aggiungere utenti ai gruppi di ruoli. L'aggiunta di un utente a un gruppo di ruoli concede all'utente le autorizzazioni per eseguire attività di amministrazione specifiche. È inoltre possibile rimuovere utenti dai gruppi di ruoli.

Per ulteriori informazioni sui ruoli e sui gruppi di ruoli, vedere [Autorizzazioni in EOP autonomo.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire l'interfaccia di amministrazione di Exchange ( EAC), vedere Interfaccia di amministrazione [di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per aprire PowerShell EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection. In particolare, è necessario **il ruolo Gestione** ruoli, assegnato al gruppo di ruoli **Gestione** organizzazione per impostazione predefinita. Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Problemi? Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-manage-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per gestire i gruppi di ruoli

### <a name="use-the-eac-to-view-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare i gruppi di ruoli

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** \> **Ruoli di amministratore**. Qui sono elencati tutti i gruppi di ruoli nell'organizzazione.

2. Selezionare un gruppo di ruoli. Nel riquadro Dettagli vengono visualizzati **i campi Nome,** **Descrizione,** **Ruoli assegnati** e **Gestito dal** gruppo di ruoli. È inoltre possibile visualizzare queste informazioni facendo clic su **Modifica** ![ icona ](../../media/ITPro-EAC-EditIcon.png) Modifica.

### <a name="use-the-eac-to-create-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare gruppi di ruoli

Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo). In caso contrario, è possibile copiare un gruppo di ruoli esistente e modificarlo.

1. Nell'interfaccia di amministrazione di Exchange, accedere **a Autorizzazioni** Ruoli \> **di amministratore** e quindi eseguire una delle operazioni seguenti:

   - **Creare manualmente un nuovo gruppo di ruoli**: fare clic su **Aggiungi** Icona ![ Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .

   - **Copiare un gruppo di ruoli esistente**: selezionare il gruppo di ruoli che si desidera copiare e quindi fare clic su **Copia** ![ icona ](../../media/ITPro-EAC-CopyIcon.png) Copia.

2. Nella finestra **Nuovo gruppo di** ruoli visualizzata configurare le impostazioni seguenti:

    - **Nome**: immettere un nome univoco per il gruppo di ruoli.

    - **Descrizione:** immettere una descrizione facoltativa per il gruppo di ruoli.

    - **Ruoli**: **fare clic su** Aggiungi icona Aggiungi o Rimuovi rimuovi per selezionare o modificare i ruoli assegnati al gruppo di ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ruoli.

    - **Membri**: fare clic **su Aggiungi** icona Aggiungi ![ o ](../../media/ITPro-EAC-AddIcon.png) **Rimuovi** icona Rimuovi per ![ modificare ](../../media/ITPro-EAC-RemoveIcon.gif) l'appartenenza al gruppo di ruoli.

3. Al termine, fare clic su **Salva** per creare il gruppo di ruoli.

### <a name="use-the-eac-to-modify-role-groups"></a>Modifica dei gruppi di ruoli tramite EAC

Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** \> **Ruoli di amministratore,** selezionare il gruppo di ruoli che si desidera modificare e quindi fare clic su **Modifica** Icona ![ Modifica ](../../media/ITPro-EAC-EditIcon.png) .

Le stesse opzioni sono disponibili quando si modificano i gruppi di ruoli come quando si creano gruppi di ruoli. È possibile:

- Modificare il nome e la descrizione.

- Aggiungere e rimuovere ruoli di gestione (creare o rimuovere assegnazioni di ruolo).

- Aggiungere e rimuovere membri.

**Nota:** alcuni gruppi di ruoli ,ad esempio Gestione organizzazione, limitano i ruoli che è possibile rimuovere dal gruppo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** Ruoli di amministratore, selezionare il gruppo di ruoli che si desidera modificare e quindi fare \> clic su **Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica.

2. Nella pagina delle proprietà del gruppo di ruoli visualizzata, nella **sezione Membri,** eseguire una delle operazioni seguenti:

   - Fare **clic su** Aggiungi Icona Aggiungi ![ ](../../media/ITPro-EAC-AddIcon.png) . Nella pagina visualizzata individuare l'utente che si desidera aggiungere e quindi fare clic **su aggiungi ->**. Selezionare gli utenti e **fare clic su aggiungi ->** più volte in base alle esigenze. Al termine, fare clic su **OK**.

   - Selezionare gli utenti che si desidera rimuovere e quindi fare clic su **Rimuovi Icona** ![ Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Al termine, scegliere **Salva**.

   > [!NOTE]
   > Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.

### <a name="use-the-eac-to-remove-role-groups"></a>Rimozione dei gruppi di ruoli tramite EAC

Non è possibile rimuovere i gruppi di ruoli predefiniti, ma è possibile rimuovere i gruppi di ruoli personalizzati creati.

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** \> **Ruoli di amministratore**.

2. Selezionare il gruppo di ruoli che si desidera rimuovere e quindi fare clic su **Elimina Icona** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Elimina.

3. Fare **clic su** Sì nella finestra di conferma visualizzata.

## <a name="use-powershell-to-manage-role-groups"></a>Utilizzare PowerShell per gestire i gruppi di ruoli

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Usare PowerShell EOP autonomo per visualizzare i gruppi di ruoli

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

Per ulteriori informazioni sulla sintassi e sui parametri, vedere [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Usare PowerShell EOP autonomo per creare gruppi di ruoli

Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo). In caso contrario, è possibile copiare un gruppo di ruoli esistente e modificarlo.

- Per creare manualmente un nuovo gruppo di ruoli, utilizzare la sintassi seguente:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Il _parametro Roles_ consente di specificare i ruoli di gestione da assegnare al gruppo di ruoli utilizzando la sintassi `"Role1","Role1",..."RoleN"` seguente. È possibile visualizzare i ruoli disponibili utilizzando il cmdlet **Get-ManagementRole.**

  - Il _parametro Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` . È possibile specificare utenti, gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

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

     Il _parametro Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` . È possibile specificare utenti, gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

     In questo esempio il gruppo di ruoli Gestione organizzazione viene copiato nel nuovo gruppo di ruoli denominato "Limited Organization Management". I membri del gruppo di ruolo sono Isabelle, Carter e Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Per informazioni dettagliate sulla sintassi e sui parametri, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Utilizzare PowerShell EOP autonomo per modificare l'elenco dei membri nei gruppi di ruoli

- I cmdlet **Add-RoleGroupMember** e **Remove-RoleGroupMember** aggiungono o rimuovono singoli membri uno alla volta. Il cmdlet **Update-RoleGroupMember** può sostituire o modificare l'elenco di membri esistente.

- I membri di un gruppo di ruoli possono essere utenti, gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).

Per modificare i membri di un gruppo di ruoli, utilizzare la sintassi seguente:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Per _sostituire_ l'elenco esistente di membri con i valori specificati, utilizzare la sintassi seguente: `"Member1","Member2",..."MemberN"` .

- Per _modificare in modo selettivo_ l'elenco esistente di membri, utilizzare la sintassi seguente: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In questo esempio tutti i membri correnti del gruppo di ruoli Help Desk vengono sostituiti con gli utenti specificati.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In questo esempio Viene aggiunto Daigoro Akai e viene rimossa Valeria Barrio dall'elenco dei membri del gruppo di ruoli Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Usare PowerShell EOP autonomo per rimuovere gruppi di ruoli

Non è possibile rimuovere i gruppi di ruoli predefiniti, ma è possibile rimuovere i gruppi di ruoli personalizzati creati.

Per rimuovere un gruppo di ruoli personalizzato, utilizzare la sintassi seguente:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

Questo esempio rimuove il gruppo di ruolo Formazione degli amministratori.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta copia di un gruppo di ruoli, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, accedere **a Autorizzazioni** Ruoli di amministratore e verificare che il gruppo di ruoli sia \> elencato (o non elencato). Selezionare il gruppo di ruoli e verificare le impostazioni nel riquadro Dettagli oppure fare clic **su Modifica** icona Modifica per verificare ![ le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.

- In PowerShell di Exchange Online, sostituire con il nome del gruppo di ruoli ed eseguire il comando seguente per verificare che il gruppo di ruoli esista (o non esista) e verificare \<Role Group Name\> le impostazioni:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```