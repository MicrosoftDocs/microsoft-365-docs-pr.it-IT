---
title: Gestione di gruppi in EOP
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori nelle organizzazioni autonome di Exchange Online Protection (EOP) possono imparare a creare, modificare e rimuovere gruppi di distribuzione e gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell di Exchange Online Protection (EOP) autonomo.
ms.openlocfilehash: a395c0738093a00c0225aea22a6e556863eebee5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201878"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="2a0a3-103">Gestire gruppi in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2a0a3-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2a0a3-104">Nelle organizzazioni standalone di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile creare, modificare e rimuovere i seguenti tipi di gruppi:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="2a0a3-105">**Gruppi di distribuzione**: un insieme di utenti di posta o di altri gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="2a0a3-106">Ad esempio, teams o altri gruppi ad hoc che hanno la necessità di ricevere o inviare messaggi di posta elettronica in un'area di interesse comune.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="2a0a3-107">I gruppi di distribuzione sono esclusivamente per la distribuzione dei messaggi di posta elettronica e non sono entità di sicurezza (non possono avere le autorizzazioni assegnate).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="2a0a3-108">**Gruppi di sicurezza abilitati alla posta elettronica**: un insieme di utenti di posta elettronica e altri gruppi di sicurezza che hanno bisogno delle autorizzazioni di accesso per i ruoli di amministratore</span><span class="sxs-lookup"><span data-stu-id="2a0a3-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="2a0a3-109">Ad esempio, è possibile assegnare autorizzazioni di amministratore a un gruppo specifico di utenti in modo che possano configurare le impostazioni di protezione da posta indesiderata e antimalware.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="2a0a3-110">Per impostazione predefinita, i nuovi gruppi di sicurezza abilitati alla posta elettronica rifiutano i messaggi provenienti da mittenti esterni (non autenticati).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="2a0a3-111">Non aggiungere gruppi di distribuzione ai gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="2a0a3-112">È possibile gestire i gruppi nell'interfaccia di amministrazione di Exchange (EAC) e in EOP PowerShell autonomo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2a0a3-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2a0a3-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2a0a3-114">Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2a0a3-115">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2a0a3-116">Quando si gestiscono i gruppi in EOP standalone PowerShell, è possibile che si verifichi la limitazione.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="2a0a3-117">Nelle procedure di PowerShell di questo argomento viene utilizzato un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-117">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="2a0a3-118">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-118">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2a0a3-119">In particolare, è necessario il ruolo gruppi di distribuzione, assegnato ai gruppi di ruoli OrganizationManagement (Global Admins) e RecipientManagement per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-119">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="2a0a3-120">Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="2a0a3-121">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="2a0a3-122">Problemi?</span><span class="sxs-lookup"><span data-stu-id="2a0a3-122">Having problems?</span></span> <span data-ttu-id="2a0a3-123">Chiedere assistenza nel forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="2a0a3-124">Utilizzare l'interfaccia di amministrazione di Exchange per gestire i gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="2a0a3-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="2a0a3-125">Utilizzo dell'interfaccia di amministrazione di Exchange per la creazione di gruppi</span><span class="sxs-lookup"><span data-stu-id="2a0a3-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="2a0a3-126">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="2a0a3-127">Fare clic su **nuova** ![ icona nuova ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="2a0a3-128">**Gruppo di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="2a0a3-128">**Distribution group**</span></span>

   - <span data-ttu-id="2a0a3-129">**Gruppo di sicurezza abilitato alla posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="2a0a3-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="2a0a3-130">Nella pagina nuovo gruppo che si apre, configurare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="2a0a3-131">Sono necessarie le impostazioni contrassegnate con un <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="2a0a3-132"><sup>\*</sup>**Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nella riga a: quando il messaggio di posta elettronica viene inviato a questo gruppo e nell'elenco **gruppi** nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="2a0a3-133">Il nome visualizzato è obbligatorio, deve essere univoco e deve essere facile da usare per consentire agli utenti di riconoscere le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="2a0a3-134"><sup>\*</sup>**Alias**: utilizzare questa casella per digitare il nome dell'alias per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="2a0a3-135">L'alias non può superare i 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="2a0a3-136">Quando un utente digita l'alias nella riga a di un messaggio di posta elettronica, viene risolto nel nome visualizzato del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="2a0a3-137"><sup>\*</sup>**Indirizzo di posta elettronica**: l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo (@) e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="2a0a3-138">Per impostazione predefinita, il valore di **alias** viene utilizzato per il valore alias, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="2a0a3-139">Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="2a0a3-140">**Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="2a0a3-141"><sup>\*</sup>**Proprietari**: il proprietario di un gruppo può gestire l'appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="2a0a3-142">Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="2a0a3-143">Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="2a0a3-144">Per aggiungere proprietari, fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2a0a3-145">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="2a0a3-146">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2a0a3-147">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="2a0a3-148">Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="2a0a3-149">**Membri**: aggiungere e rimuovere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="2a0a3-150">Per aggiungere membri, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2a0a3-151">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="2a0a3-152">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2a0a3-153">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="2a0a3-154">Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="2a0a3-155">Al termine, fare clic su **Salva** per creare il gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="2a0a3-156">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="2a0a3-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="2a0a3-157">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="2a0a3-158">Nell'elenco dei gruppi, selezionare il gruppo di distribuzione o il gruppo di sicurezza abilitato alla posta elettronica che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="2a0a3-159">Nella pagina delle proprietà del gruppo di distribuzione visualizzata, fare clic su una delle schede seguenti per visualizzare o modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="2a0a3-160">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="2a0a3-161">Generale</span><span class="sxs-lookup"><span data-stu-id="2a0a3-161">General</span></span>

<span data-ttu-id="2a0a3-162">Utilizzare questa scheda per visualizzare o modificare le informazioni di base sul gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="2a0a3-163">**Nome visualizzato**: questo nome viene visualizzato nella rubrica, nella riga a quando il messaggio di posta elettronica viene inviato a questo gruppo e nell' **elenco gruppi**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="2a0a3-164">Il nome visualizzato è obbligatorio e deve essere un nome descrittivo facilmente riconoscibile dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="2a0a3-165">Inoltre, deve essere univoco nel dominio in uso.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="2a0a3-166">Se sono stati implementati criteri di denominazione dei gruppi, il nome visualizzato deve essere conforme al formato di denominazione definito dai criteri.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="2a0a3-167">**Alias**: questa è la parte dell'indirizzo di posta elettronica che viene visualizzata a sinistra del simbolo di chiocciola (@).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="2a0a3-168">Se si modifica l'alias, verrà modificato anche l'indirizzo SMTP primario del gruppo in modo che contenga il nuovo alias.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="2a0a3-169">Inoltre, l'indirizzo di posta elettronica con il precedente alias verrà conservato come indirizzo proxy del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="2a0a3-170">**Indirizzo di posta elettronica**: l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo (@) e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="2a0a3-171">Per impostazione predefinita, il valore di **alias** viene utilizzato per il valore alias, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="2a0a3-172">Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="2a0a3-173">**Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="2a0a3-174">Ownership</span><span class="sxs-lookup"><span data-stu-id="2a0a3-174">Ownership</span></span>

<span data-ttu-id="2a0a3-175">Utilizzare questa scheda per assegnare i proprietari del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="2a0a3-176">Il proprietario di un gruppo può gestire l'appartenenza A un gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-176">A group owner can manage group membership.</span></span> <span data-ttu-id="2a0a3-177">Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="2a0a3-178">Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="2a0a3-179">Per aggiungere proprietari, fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2a0a3-180">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario e quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="2a0a3-181">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2a0a3-182">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="2a0a3-183">Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="2a0a3-184">Appartenenza</span><span class="sxs-lookup"><span data-stu-id="2a0a3-184">Membership</span></span>

<span data-ttu-id="2a0a3-185">Utilizzare questa scheda per aggiungere o rimuovere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="2a0a3-186">Non è necessario che i proprietari del gruppo siano membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="2a0a3-187">Per aggiungere membri, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2a0a3-188">Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="2a0a3-189">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2a0a3-190">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="2a0a3-191">Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="2a0a3-192">Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere i gruppi</span><span class="sxs-lookup"><span data-stu-id="2a0a3-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="2a0a3-193">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="2a0a3-194">Nell'elenco dei gruppi, selezionare il gruppo di distribuzione che si desidera rimuovere, quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="2a0a3-195">Utilizzo di PowerShell per gestire i gruppi</span><span class="sxs-lookup"><span data-stu-id="2a0a3-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="2a0a3-196">Utilizzo di PowerShell EOP autonomo per visualizzare i gruppi</span><span class="sxs-lookup"><span data-stu-id="2a0a3-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="2a0a3-197">Per restituire un elenco riepilogativo di tutti i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica in EOP PowerShell autonomo, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="2a0a3-198">Per restituire l'elenco dei membri del gruppo, sostituire \<GroupIdentity\> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="2a0a3-199">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="2a0a3-200">Utilizzo di PowerShell EOP autonomo per creare gruppi</span><span class="sxs-lookup"><span data-stu-id="2a0a3-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="2a0a3-201">Per creare gruppi di distribuzione o gruppi di sicurezza abilitati alla posta elettronica in EOP PowerShell autonomo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="2a0a3-202">**Note**:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-202">**Notes**:</span></span>

- <span data-ttu-id="2a0a3-203">Il parametro _Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="2a0a3-204">Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="2a0a3-205">Se non si utilizza il parametro _alias_ , il parametro _Name_ viene utilizzato per il valore alias.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="2a0a3-206">Gli spazi vengono rimossi e i caratteri non supportati vengono convertiti in punti interrogativi (?).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="2a0a3-207">Se non si utilizza il parametro _PrimarySmtpAddress_ , il valore alias viene utilizzato nel parametro _PrimarySmtpAddress_ .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="2a0a3-208">Se non si utilizza il parametro _Type_ , il valore predefinito è Distribution.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="2a0a3-209">In questo esempio viene creato un gruppo di distribuzione denominato amministratori IT con le proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="2a0a3-210">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="2a0a3-211">Utilizzo di PowerShell EOP autonomo per modificare i gruppi</span><span class="sxs-lookup"><span data-stu-id="2a0a3-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="2a0a3-212">Per modificare i gruppi in EOP autonomo PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="2a0a3-213">In questo esempio viene utilizzata la modifica dell'indirizzo SMTP primario (denominato anche indirizzo di risposta) del gruppo Seattle Employees in sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="2a0a3-214">In questo esempio vengono sostituiti i membri correnti del gruppo del team di sicurezza con Kitty Petersen e Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="2a0a3-215">In questo esempio viene aggiunto un nuovo utente denominato Tyson Fawcett al gruppo denominato Security Team mantenendo i membri correnti del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="2a0a3-216">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="2a0a3-217">Rimuovere un gruppo tramite Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="2a0a3-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="2a0a3-218">In questo esempio viene rimosso il gruppo di distribuzione denominato amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="2a0a3-219">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="2a0a3-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2a0a3-220">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="2a0a3-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="2a0a3-221">Per verificare la corretta creazione, modifica o rimozione di un gruppo di distribuzione o di un gruppo di sicurezza abilitato alla posta elettronica, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="2a0a3-222">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="2a0a3-223">Verificare che il gruppo sia elencato (o non elencato) e verificare il valore del **tipo di gruppo** .</span><span class="sxs-lookup"><span data-stu-id="2a0a3-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="2a0a3-224">Selezionare il gruppo e visualizzare le informazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) per visualizzare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2a0a3-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="2a0a3-225">In EOP standalone PowerShell, eseguire il comando riportato di seguito per verificare che il gruppo sia elencato (o non sia elencato):</span><span class="sxs-lookup"><span data-stu-id="2a0a3-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="2a0a3-226">Sostituire \<GroupIdentity\> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="2a0a3-227">Per visualizzare i membri del gruppo, sostituire \<GroupIdentity\> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2a0a3-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
