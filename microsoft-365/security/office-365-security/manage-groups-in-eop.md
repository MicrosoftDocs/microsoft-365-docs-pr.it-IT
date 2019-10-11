---
title: Gestione di gruppi in EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: È possibile utilizzare Exchange Online Protection (EOP) per creare gruppi abilitati alla posta elettronica per un'organizzazione di Exchange. È inoltre possibile utilizzare EOP per definire o aggiornare le proprietà del gruppo che specificano l'appartenenza, gli indirizzi di posta elettronica e altri aspetti dei gruppi.
ms.openlocfilehash: 1efbb32635d6dd2a66c1039b04f57c4910d927c4
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441523"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="b8c9f-104">Gestire gruppi in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b8c9f-104">Manage groups in EOP</span></span>

 <span data-ttu-id="b8c9f-p102">È possibile utilizzare Exchange Online Protection (EOP) per creare gruppi abilitati alla posta elettronica per un'organizzazione di Exchange. È inoltre possibile utilizzare EOP per definire o aggiornare le proprietà del gruppo che specificano l'appartenenza, gli indirizzi di posta elettronica e altri aspetti dei gruppi. È possibile creare gruppi di distribuzione e gruppi di sicurezza, a seconda delle proprie esigenze. È possibile creare tali gruppi utilizzando l'interfaccia di amministrazione di Exchange o tramite Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="b8c9f-109">Tipi di gruppi abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="b8c9f-110">È possibile creare due tipi di gruppi per la propria organizzazione di Exchange:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-110">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="b8c9f-111">I gruppi di distribuzione sono insiemi di utenti di posta elettronica, ad esempio un team o un altro gruppo ad hoc, che devono ricevere o inviare messaggi di posta elettronica relativi a un'area comune di interesse.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-111">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="b8c9f-112">I gruppi di distribuzione servono esclusivamente per la distribuzione di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="b8c9f-113">In EOP, un gruppo di distribuzione fa riferimento a qualsiasi gruppo abilitato alla posta elettronica, a prescindere che abbia o meno un contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="b8c9f-114">I gruppi di sicurezza sono insiemi di utenti di posta elettronica che richiedono autorizzazioni di accesso per i ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-114">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="b8c9f-115">Ad esempio, si potrebbe voler assegnare a un gruppo specifico di utenti autorizzazioni di ruolo di amministratore in modo che possano configurare impostazioni di protezione dalla posta indesiderata e antimalware.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8c9f-p105">Per impostazione predefinita, tutti i nuovi gruppi di sicurezza abilitati alla posta elettronica richiedono l'autenticazione di tutti i mittenti. Questo impedisce ai mittenti esterni di inviare messaggi ai gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b8c9f-118">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b8c9f-118">Before you begin</span></span>

- <span data-ttu-id="b8c9f-p106">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Gruppi di distribuzione e sicurezza" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="b8c9f-121">Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-121">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b8c9f-122">Tenere presente che durante la creazione e la gestione dei gruppi tramite i cmdlet di PowerShell di Exchange Online Protection, è possibile che si verifichi la limitazione.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-122">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="b8c9f-123">Nelle procedure di PowerShell di questo argomento viene utilizzato un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-123">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b8c9f-124">Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online Protection, vedere [Connessione a Exchange Online Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-124">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="b8c9f-125">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b8c9f-126">Problemi?</span><span class="sxs-lookup"><span data-stu-id="b8c9f-126">Having problems?</span></span> <span data-ttu-id="b8c9f-127">Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="b8c9f-127">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="b8c9f-128">Creare un gruppo nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="b8c9f-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="b8c9f-129">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-129">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b8c9f-130">Fare \*\*\*\* ![clic su nuova](../media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi fare clic su **gruppo di distribuzione** o **gruppo di sicurezza**in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-130">Click **New** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="b8c9f-131">Nella pagina **nuovo** gruppo di distribuzione o **nuovo gruppo di sicurezza** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-131">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="b8c9f-132">**Nome visualizzato**: digitare un nome visualizzato univoco per l'organizzazione e significativo per gli utenti di EOP.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-132">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="b8c9f-133">Il nome visualizzato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-133">The display name is required.</span></span>

   - <span data-ttu-id="b8c9f-134">**Alias**: digitare un alias di gruppo contenente fino a 64 caratteri univoci per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-134">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="b8c9f-135">EOP gli utenti digita l'alias nella riga a: dei messaggi di posta elettronica e l'alias viene risolto nel nome visualizzato del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-135">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="b8c9f-136">Se si modifica l'alias, anche l'indirizzo SMTP primario per il gruppo cambia e conterrà il nuovo alias.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-136">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="b8c9f-137">L'alias è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-137">The alias is required.</span></span>

   - <span data-ttu-id="b8c9f-138">**Descrizione**: digitare una descrizione del gruppo in modo che gli utenti conoscano lo scopo del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-138">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="b8c9f-139">**Proprietari**: per impostazione predefinita, la persona che crea il gruppo è il proprietario.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-139">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="b8c9f-140">È possibile aggiungere un proprietario scegliendo **Aggiungi** ![icona](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-140">You can add an owner by choosing **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="b8c9f-141">Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-141">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b8c9f-142">I proprietari non sono tenuti a essere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-142">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="b8c9f-143">**Membri**: utilizzare questa sezione per aggiungere membri del gruppo e per specificare se è necessaria l'approvazione per gli utenti di partecipare o lasciare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-143">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="b8c9f-144">Per aggiungere membri al gruppo, fare clic su **Aggiungi** ![icona](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-144">To add members to the group, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="b8c9f-145">Scegliere **OK** per tornare alla pagina originale.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-145">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="b8c9f-p112">Al termine, scegliere **Salva** per creare il gruppo. Il nuovo gruppo verrà visualizzato nell'elenco dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-p112">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="b8c9f-148">Modificare o rimuovere un gruppo nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="b8c9f-148">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="b8c9f-149">In EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-149">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b8c9f-150">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-150">Do one of the following steps:</span></span>

   - <span data-ttu-id="b8c9f-151">Per modificare un gruppo: nell'elenco dei gruppi fare clic sul gruppo che si desidera visualizzare o modificare, quindi fare clic su **modifica** ![icona](../media/ITPro-EAC-EditIcon.gif)modifica.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-151">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="b8c9f-152">È possibile aggiornare le impostazioni generali, aggiungere o rimuovere proprietari del gruppo e aggiungere o rimuovere i membri del gruppo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-152">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="b8c9f-153">Per rimuovere un gruppo: selezionare il gruppo e fare \*\*\*\* ![clic su Rimuovi](../media/ITPro-EAC-RemoveIcon.gif)icona Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-153">To remove a group: Select the group and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="b8c9f-154">Dopo avere apportato tutte le modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-154">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b8c9f-155">Creare, modificare o rimuovere un gruppo utilizzando Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="b8c9f-155">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b8c9f-156">In questa sezione vengono fornite informazioni sulla creazione di gruppi e sulla modifica delle relative proprietà in PowerShell di Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-156">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="b8c9f-157">Inoltre, viene illustrato come rimuovere un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-157">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b8c9f-158">Creare un gruppo utilizzando Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="b8c9f-158">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b8c9f-p115">In questo esempio viene utilizzato il cmdlet [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) per creare un gruppo di distribuzione con alias itadmin e nome Amministratori IT. Inoltre, vengono aggiunti utenti come membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-p115">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="b8c9f-161">**Nota**: per creare un gruppo di sicurezza invece di un gruppo di distribuzione, utilizzare `Security` il valore per il parametro *Type* .</span><span class="sxs-lookup"><span data-stu-id="b8c9f-161">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="b8c9f-162">Per verificare che il gruppo amministratori IT sia stato creato correttamente, eseguire il comando riportato di seguito per visualizzare le informazioni sul nuovo gruppo:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-162">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="b8c9f-163">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-163">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="b8c9f-164">Per ottenere un elenco di membri del gruppo, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-164">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="b8c9f-165">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-165">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="b8c9f-166">Per ottenere un elenco completo di tutti i gruppi, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-166">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b8c9f-167">Modificare le proprietà di un gruppo utilizzando Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="b8c9f-167">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b8c9f-168">Un vantaggio dell'utilizzo di PowerShell invece dell'interfaccia di amministrazione di Exchange è la possibilità di modificare le proprietà per più gruppi.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-168">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="b8c9f-169">Di seguito sono riportati alcuni esempi di utilizzo di PowerShell di Exchange Online Protection per modificare le proprietà del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-169">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="b8c9f-170">In questo esempio viene utilizzata la modifica dell'indirizzo SMTP primario (denominato anche indirizzo di risposta) del gruppo Seattle Employees in sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-170">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="b8c9f-171">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-171">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="b8c9f-172">Per verificare di aver correttamente modificato le proprietà per il gruppo, eseguire il seguente comando per verificare il nuovo valore:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-172">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="b8c9f-173">In questo esempio vengono aggiornati tutti i membri del gruppo Seattle Employees.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-173">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="b8c9f-174">Utilizzare una virgola per tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-174">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="b8c9f-175">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-175">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="b8c9f-176">Per ottenere l'elenco di tutti i membri del gruppo Seattle Employees, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b8c9f-176">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b8c9f-177">Rimuovere un gruppo tramite Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="b8c9f-177">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b8c9f-178">In questo esempio viene rimosso il gruppo di distribuzione denominato amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-178">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="b8c9f-179">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="b8c9f-179">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="b8c9f-180">Per verificare che il gruppo sia stato rimosso, eseguire il comando riportato di seguito e verificare che il gruppo (in questo caso "amministratori IT") sia stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="b8c9f-180">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
