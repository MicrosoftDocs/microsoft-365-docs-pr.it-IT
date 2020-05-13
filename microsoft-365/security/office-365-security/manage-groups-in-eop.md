---
title: Gestione di gruppi in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori nelle organizzazioni autonome di Exchange Online Protection (EOP) possono imparare a creare, modificare e rimuovere gruppi di distribuzione e gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell di Exchange Online Protection (EOP) autonomo.
ms.openlocfilehash: fc3f3807216b269a9868e87c5ec784d75385f878
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209020"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="cfdb2-103">Gestire gruppi in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cfdb2-103">Manage groups in EOP</span></span>

<span data-ttu-id="cfdb2-104">Nelle organizzazioni standalone di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile creare, modificare e rimuovere i seguenti tipi di gruppi:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="cfdb2-105">**Gruppi di distribuzione**: un insieme di utenti di posta o di altri gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="cfdb2-106">Ad esempio, teams o altri gruppi ad hoc che hanno la necessità di ricevere o inviare messaggi di posta elettronica in un'area di interesse comune.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="cfdb2-107">I gruppi di distribuzione sono esclusivamente per la distribuzione dei messaggi di posta elettronica e non sono entità di sicurezza (non possono avere le autorizzazioni assegnate).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="cfdb2-108">**Gruppi di sicurezza abilitati alla posta elettronica**: un insieme di utenti di posta elettronica e altri gruppi di sicurezza che hanno bisogno delle autorizzazioni di accesso per i ruoli di amministratore</span><span class="sxs-lookup"><span data-stu-id="cfdb2-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="cfdb2-109">Ad esempio, è possibile assegnare autorizzazioni di amministratore a un gruppo specifico di utenti in modo che possano configurare le impostazioni di protezione da posta indesiderata e antimalware.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="cfdb2-110">Per impostazione predefinita, i nuovi gruppi di sicurezza abilitati alla posta elettronica rifiutano i messaggi provenienti da mittenti esterni (non autenticati).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="cfdb2-111">Non aggiungere gruppi di distribuzione ai gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="cfdb2-112">.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-112">.</span></span>

<span data-ttu-id="cfdb2-113">È possibile gestire i gruppi nell'interfaccia di amministrazione di Exchange (EAC) e in EOP PowerShell autonomo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cfdb2-114">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cfdb2-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cfdb2-115">Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="cfdb2-116">Per connettersi a PowerShell di EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cfdb2-117">Quando si gestiscono i gruppi in EOP standalone PowerShell, è possibile che si verifichi la limitazione.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="cfdb2-118">Nelle procedure di PowerShell di questo argomento viene utilizzato un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="cfdb2-119">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="cfdb2-120">In particolare, è necessario il ruolo gruppi di distribuzione, assegnato ai gruppi di ruoli OrganizationManagement (Global Admins) e RecipientManagement per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="cfdb2-121">Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="cfdb2-122">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="cfdb2-123">Problemi?</span><span class="sxs-lookup"><span data-stu-id="cfdb2-123">Having problems?</span></span> <span data-ttu-id="cfdb2-124">Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="cfdb2-125">Utilizzare l'interfaccia di amministrazione di Exchange per gestire i gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="cfdb2-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="cfdb2-126">Utilizzo dell'interfaccia di amministrazione di Exchange per la creazione di gruppi</span><span class="sxs-lookup"><span data-stu-id="cfdb2-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="cfdb2-127">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="cfdb2-128">Fare clic su **nuova** ![ icona nuova ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="cfdb2-129">**Gruppo di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="cfdb2-129">**Distribution group**</span></span>

   - <span data-ttu-id="cfdb2-130">**Gruppo di sicurezza abilitato alla posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="cfdb2-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="cfdb2-131">Nella pagina nuovo gruppo che si apre, configurare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="cfdb2-132">Sono necessarie le impostazioni contrassegnate con un <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="cfdb2-133"><sup>\*</sup>**Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nella riga a: quando il messaggio di posta elettronica viene inviato a questo gruppo e nell'elenco **gruppi** nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="cfdb2-134">Il nome visualizzato è obbligatorio, deve essere univoco e deve essere facile da usare per consentire agli utenti di riconoscere le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="cfdb2-135"><sup>\*</sup>**Alias**: utilizzare questa casella per digitare il nome dell'alias per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="cfdb2-136">L'alias non può superare i 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="cfdb2-137">Quando un utente digita l'alias nella riga a di un messaggio di posta elettronica, viene risolto nel nome visualizzato del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="cfdb2-138"><sup>\*</sup>**Indirizzo di posta elettronica**: l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo (@) e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="cfdb2-139">Per impostazione predefinita, il valore di **alias** viene utilizzato per il valore alias, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="cfdb2-140">Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="cfdb2-141">**Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="cfdb2-142"><sup>\*</sup>**Proprietari**: il proprietario di un gruppo può gestire l'appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="cfdb2-143">Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="cfdb2-144">Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="cfdb2-145">Per aggiungere proprietari, fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="cfdb2-146">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="cfdb2-147">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="cfdb2-148">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="cfdb2-149">Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="cfdb2-150">**Membri**: aggiungere e rimuovere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="cfdb2-151">Per aggiungere membri, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="cfdb2-152">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="cfdb2-153">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="cfdb2-154">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="cfdb2-155">Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="cfdb2-156">Al termine, fare clic su **Salva** per creare il gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="cfdb2-157">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="cfdb2-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="cfdb2-158">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="cfdb2-159">Nell'elenco dei gruppi, selezionare il gruppo di distribuzione o il gruppo di sicurezza abilitato alla posta elettronica che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="cfdb2-160">Nella pagina delle proprietà del gruppo di distribuzione visualizzata, fare clic su una delle schede seguenti per visualizzare o modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="cfdb2-161">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="cfdb2-162">Generale</span><span class="sxs-lookup"><span data-stu-id="cfdb2-162">General</span></span>

<span data-ttu-id="cfdb2-163">Utilizzare questa scheda per visualizzare o modificare le informazioni di base sul gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="cfdb2-164">**Nome visualizzato**: questo nome viene visualizzato nella rubrica, nella riga a quando il messaggio di posta elettronica viene inviato a questo gruppo e nell' **elenco gruppi**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="cfdb2-165">Il nome visualizzato è obbligatorio e deve essere un nome descrittivo facilmente riconoscibile dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="cfdb2-166">Inoltre, deve essere univoco nel dominio in uso.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="cfdb2-167">Se sono stati implementati criteri di denominazione dei gruppi, il nome visualizzato deve essere conforme al formato di denominazione definito dai criteri.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="cfdb2-168">**Alias**: questa è la parte dell'indirizzo di posta elettronica che viene visualizzata a sinistra del simbolo di chiocciola (@).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="cfdb2-169">Se si modifica l'alias, verrà modificato anche l'indirizzo SMTP primario del gruppo in modo che contenga il nuovo alias.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="cfdb2-170">Inoltre, l'indirizzo di posta elettronica con il precedente alias verrà conservato come indirizzo proxy del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="cfdb2-171">**Indirizzo di posta elettronica**: l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo (@) e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="cfdb2-172">Per impostazione predefinita, il valore di **alias** viene utilizzato per il valore alias, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="cfdb2-173">Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="cfdb2-174">**Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="cfdb2-175">Ownership</span><span class="sxs-lookup"><span data-stu-id="cfdb2-175">Ownership</span></span>

<span data-ttu-id="cfdb2-176">Utilizzare questa scheda per assegnare i proprietari del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="cfdb2-177">Il proprietario di un gruppo può gestire l'appartenenza A un gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-177">A group owner can manage group membership.</span></span> <span data-ttu-id="cfdb2-178">Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="cfdb2-179">Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="cfdb2-180">Per aggiungere proprietari, fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="cfdb2-181">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario e quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="cfdb2-182">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="cfdb2-183">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="cfdb2-184">Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="cfdb2-185">Appartenenza</span><span class="sxs-lookup"><span data-stu-id="cfdb2-185">Membership</span></span>

<span data-ttu-id="cfdb2-186">Utilizzare questa scheda per aggiungere o rimuovere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="cfdb2-187">Non è necessario che i proprietari del gruppo siano membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="cfdb2-188">Per aggiungere membri, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="cfdb2-189">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="cfdb2-190">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="cfdb2-191">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="cfdb2-192">Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="cfdb2-193">Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere i gruppi</span><span class="sxs-lookup"><span data-stu-id="cfdb2-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="cfdb2-194">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="cfdb2-195">Nell'elenco dei gruppi, selezionare il gruppo di distribuzione che si desidera rimuovere, quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="cfdb2-196">Utilizzo di PowerShell per gestire i gruppi</span><span class="sxs-lookup"><span data-stu-id="cfdb2-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="cfdb2-197">Utilizzo di PowerShell EOP autonomo per visualizzare i gruppi</span><span class="sxs-lookup"><span data-stu-id="cfdb2-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="cfdb2-198">Per restituire un elenco riepilogativo di tutti i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica in EOP PowerShell autonomo, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="cfdb2-199">Per restituire l'elenco dei membri del gruppo, sostituire \< groupIdentity \> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="cfdb2-200">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) e [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="cfdb2-201">Utilizzo di PowerShell EOP autonomo per creare gruppi</span><span class="sxs-lookup"><span data-stu-id="cfdb2-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="cfdb2-202">Per creare gruppi di distribuzione o gruppi di sicurezza abilitati alla posta elettronica in EOP PowerShell autonomo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="cfdb2-203">**Note**:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-203">**Notes**:</span></span>

- <span data-ttu-id="cfdb2-204">Il parametro _Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="cfdb2-205">Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="cfdb2-206">Se non si utilizza il parametro _alias_ , il parametro _Name_ viene utilizzato per il valore alias.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="cfdb2-207">Gli spazi vengono rimossi e i caratteri non supportati vengono convertiti in punti interrogativi (?).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="cfdb2-208">Se non si utilizza il parametro _PrimarySmtpAddress_ , il valore alias viene utilizzato nel parametro _PrimarySmtpAddress_ .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="cfdb2-209">Se non si utilizza il parametro _Type_ , il valore predefinito è Distribution.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="cfdb2-210">In questo esempio viene creato un gruppo di distribuzione denominato amministratori IT con le proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="cfdb2-211">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="cfdb2-212">Utilizzo di PowerShell EOP autonomo per modificare i gruppi</span><span class="sxs-lookup"><span data-stu-id="cfdb2-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="cfdb2-213">Per modificare i gruppi in EOP autonomo PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="cfdb2-214">In questo esempio viene utilizzata la modifica dell'indirizzo SMTP primario (denominato anche indirizzo di risposta) del gruppo Seattle Employees in sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="cfdb2-215">In questo esempio vengono sostituiti i membri correnti del gruppo del team di sicurezza con Kitty Petersen e Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="cfdb2-216">In questo esempio viene aggiunto un nuovo utente denominato Tyson Fawcett al gruppo denominato Security Team mantenendo i membri correnti del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="cfdb2-217">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="cfdb2-218">Rimuovere un gruppo tramite Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="cfdb2-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="cfdb2-219">In questo esempio viene rimosso il gruppo di distribuzione denominato amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="cfdb2-220">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="cfdb2-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="cfdb2-221">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="cfdb2-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="cfdb2-222">Per verificare la corretta creazione, modifica o rimozione di un gruppo di distribuzione o di un gruppo di sicurezza abilitato alla posta elettronica, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="cfdb2-223">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="cfdb2-224">Verificare che il gruppo sia elencato (o non elencato) e verificare il valore del **tipo di gruppo** .</span><span class="sxs-lookup"><span data-stu-id="cfdb2-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="cfdb2-225">Selezionare il gruppo e visualizzare le informazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) per visualizzare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cfdb2-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="cfdb2-226">In EOP standalone PowerShell, eseguire il comando riportato di seguito per verificare che il gruppo sia elencato (o non sia elencato):</span><span class="sxs-lookup"><span data-stu-id="cfdb2-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="cfdb2-227">Sostituire \< groupIdentity \> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="cfdb2-228">Per visualizzare i membri del gruppo, sostituire \< groupIdentity \> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cfdb2-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
