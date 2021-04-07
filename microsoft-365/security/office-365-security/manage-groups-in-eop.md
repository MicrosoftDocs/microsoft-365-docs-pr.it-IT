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
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori delle organizzazioni autonome di Exchange Online Protection (EOP) possono imparare a creare, modificare e rimuovere gruppi di distribuzione e gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell di Exchange Online Protection (EOP) autonomo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b9d83f2fb59ee8f8d2d3035045ed438d5ba45851
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599570"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="15ae6-103">Gestire gruppi in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="15ae6-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="15ae6-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="15ae6-104">**Applies to**</span></span>
-  [<span data-ttu-id="15ae6-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="15ae6-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="15ae6-106">Nelle organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile creare, modificare e rimuovere i seguenti tipi di gruppi:</span><span class="sxs-lookup"><span data-stu-id="15ae6-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="15ae6-107">**Gruppi di distribuzione**: raccolta di utenti di posta o altri gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="15ae6-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="15ae6-108">Ad esempio, team o altri gruppi ad hoc che devono ricevere o inviare messaggi di posta elettronica in un'area comune di interesse.</span><span class="sxs-lookup"><span data-stu-id="15ae6-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="15ae6-109">I gruppi di distribuzione sono esclusivamente per la distribuzione dei messaggi di posta elettronica e non sono entità di sicurezza (non possono disporre delle autorizzazioni assegnate).</span><span class="sxs-lookup"><span data-stu-id="15ae6-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="15ae6-110">**Gruppi di sicurezza abilitati alla posta**: raccolta di utenti di posta e altri gruppi di sicurezza che necessitano delle autorizzazioni di accesso per i ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="15ae6-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="15ae6-111">Ad esempio, è possibile assegnare a un gruppo specifico di utenti le autorizzazioni di amministratore in modo che possano configurare le impostazioni di protezione da posta indesiderata e antimalware.</span><span class="sxs-lookup"><span data-stu-id="15ae6-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="15ae6-112">Per impostazione predefinita, i nuovi gruppi di sicurezza abilitati alla posta rifiutano i messaggi provenienti da mittenti esterni (non autenticati).</span><span class="sxs-lookup"><span data-stu-id="15ae6-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="15ae6-113">Non aggiungere gruppi di distribuzione ai gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="15ae6-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="15ae6-114">È possibile gestire i gruppi nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell EOP autonomo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15ae6-115">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="15ae6-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="15ae6-116">Per aprire l'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="15ae6-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="15ae6-117">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="15ae6-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="15ae6-118">Quando si gestiscono i gruppi in PowerShell EOP autonomo, è possibile che si verifichino limitazioni.</span><span class="sxs-lookup"><span data-stu-id="15ae6-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="15ae6-119">Le procedure di PowerShell descritte in questo articolo utilizzano un metodo di elaborazione in batch che causa un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.</span><span class="sxs-lookup"><span data-stu-id="15ae6-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="15ae6-120">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="15ae6-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="15ae6-121">In particolare, è necessario il ruolo Gruppi  **di**  distribuzione, assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="15ae6-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="15ae6-122">Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="15ae6-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="15ae6-123">Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="15ae6-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="15ae6-124">Problemi?</span><span class="sxs-lookup"><span data-stu-id="15ae6-124">Having problems?</span></span> <span data-ttu-id="15ae6-125">Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="15ae6-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="15ae6-126">Utilizzare l'interfaccia di amministrazione di Exchange per gestire i gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="15ae6-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="15ae6-127">Utilizzo dell'interfaccia di amministrazione di Exchange per creare gruppi</span><span class="sxs-lookup"><span data-stu-id="15ae6-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="15ae6-128">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="15ae6-129">Fare **clic su** Nuovo icona Nuovo e quindi selezionare una delle opzioni ![ ](../../media/ITPro-EAC-AddIcon.png) seguenti:</span><span class="sxs-lookup"><span data-stu-id="15ae6-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="15ae6-130">**Gruppo di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="15ae6-130">**Distribution group**</span></span>

   - <span data-ttu-id="15ae6-131">**Gruppo di sicurezza abilitato alla posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="15ae6-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="15ae6-132">Nella pagina del nuovo gruppo visualizzata configurare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="15ae6-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="15ae6-133">Le impostazioni contrassegnate con <sup>\*</sup> un sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="15ae6-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="15ae6-134"><sup>\*</sup>**Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nella riga A:  quando la posta elettronica viene inviata a questo gruppo e nell'elenco Gruppi nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="15ae6-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="15ae6-135">Il nome visualizzato è obbligatorio, deve essere univoco e deve essere descrittivo in modo che gli utenti riconoscano il nome.</span><span class="sxs-lookup"><span data-stu-id="15ae6-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="15ae6-136"><sup>\*</sup>**Alias**: utilizzare questa casella per digitare il nome dell'alias per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="15ae6-137">L'alias non può superare i 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="15ae6-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="15ae6-138">Quando un utente digitare l'alias nella riga A di un messaggio di posta elettronica, viene risolto nel nome visualizzato del gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="15ae6-139"><sup>\*</sup>**Indirizzo di** posta elettronica : l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo at (@) e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="15ae6-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="15ae6-140">Per impostazione predefinita, il valore **di Alias** viene utilizzato per il valore dell'alias, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="15ae6-141">Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15ae6-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="15ae6-142">**Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro Dettagli nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="15ae6-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="15ae6-143"><sup>\*</sup>**Proprietari**: il proprietario di un gruppo può gestire l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="15ae6-144">Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario.</span><span class="sxs-lookup"><span data-stu-id="15ae6-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="15ae6-145">Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="15ae6-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="15ae6-146">Per aggiungere proprietari, fare clic **su Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15ae6-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="15ae6-147">Nella finestra di dialogo visualizzata individuare e selezionare un destinatario o un gruppo e quindi fare clic su **aggiungi ->**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="15ae6-148">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="15ae6-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="15ae6-149">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="15ae6-150">Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ Icona ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="15ae6-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="15ae6-151">**Membri**: aggiungere e rimuovere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="15ae6-152">Per aggiungere membri, fare clic **su Aggiungi** ![ Icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="15ae6-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="15ae6-153">Nella finestra di dialogo visualizzata individuare e selezionare un destinatario o un gruppo e quindi fare clic su **aggiungi ->**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="15ae6-154">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="15ae6-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="15ae6-155">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="15ae6-156">Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi Icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="15ae6-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="15ae6-157">Al termine, fare clic su **Salva** per creare il gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="15ae6-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="15ae6-158">Modifica dei gruppi di distribuzione tramite EAC</span><span class="sxs-lookup"><span data-stu-id="15ae6-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="15ae6-159">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="15ae6-160">Nell'elenco dei gruppi selezionare il gruppo di distribuzione o il gruppo di sicurezza abilitato alla posta elettronica che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="15ae6-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="15ae6-161">Nella pagina delle proprietà del gruppo di distribuzione visualizzata fare clic su una delle schede seguenti per visualizzare o modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="15ae6-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="15ae6-162">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="15ae6-163">Generale</span><span class="sxs-lookup"><span data-stu-id="15ae6-163">General</span></span>

<span data-ttu-id="15ae6-164">Utilizzare questa scheda per visualizzare o modificare le informazioni di base sul gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="15ae6-165">**Nome visualizzato**: questo nome viene visualizzato nella rubrica, nella riga A quando viene inviato un messaggio di posta elettronica a questo gruppo e nell'elenco **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="15ae6-166">Il nome visualizzato è obbligatorio e deve essere un nome descrittivo facilmente riconoscibile dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="15ae6-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="15ae6-167">Inoltre, deve essere univoco nel dominio in uso.</span><span class="sxs-lookup"><span data-stu-id="15ae6-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="15ae6-168">Se sono stati implementati criteri di denominazione dei gruppi, il nome visualizzato deve essere conforme al formato di denominazione definito dai criteri.</span><span class="sxs-lookup"><span data-stu-id="15ae6-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="15ae6-169">**Alias**: è la parte dell'indirizzo di posta elettronica visualizzata a sinistra del simbolo di at (@).</span><span class="sxs-lookup"><span data-stu-id="15ae6-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="15ae6-170">Se si modifica l'alias, verrà modificato anche l'indirizzo SMTP primario del gruppo in modo che contenga il nuovo alias.</span><span class="sxs-lookup"><span data-stu-id="15ae6-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="15ae6-171">Inoltre, l'indirizzo di posta elettronica con il precedente alias verrà conservato come indirizzo proxy del gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="15ae6-172">**Indirizzo di** posta elettronica : l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo at (@) e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="15ae6-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="15ae6-173">Per impostazione predefinita, il valore **di Alias** viene utilizzato per il valore dell'alias, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="15ae6-174">Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15ae6-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="15ae6-175">**Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro Dettagli nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="15ae6-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="15ae6-176">Ownership</span><span class="sxs-lookup"><span data-stu-id="15ae6-176">Ownership</span></span>

<span data-ttu-id="15ae6-177">Utilizzare questa scheda per assegnare i proprietari dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="15ae6-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="15ae6-178">Il proprietario di un gruppo può gestire l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-178">A group owner can manage group membership.</span></span> <span data-ttu-id="15ae6-179">Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario.</span><span class="sxs-lookup"><span data-stu-id="15ae6-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="15ae6-180">Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="15ae6-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="15ae6-181">Per aggiungere proprietari, fare clic **su Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="15ae6-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="15ae6-182">Nella finestra di dialogo visualizzata individuare e selezionare un destinatario e quindi fare clic su **aggiungi ->**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="15ae6-183">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="15ae6-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="15ae6-184">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="15ae6-185">Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ Icona ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="15ae6-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="15ae6-186">Appartenenza</span><span class="sxs-lookup"><span data-stu-id="15ae6-186">Membership</span></span>

<span data-ttu-id="15ae6-187">Utilizzare questa scheda per aggiungere o rimuovere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="15ae6-188">I proprietari del gruppo non devono essere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="15ae6-189">Per aggiungere membri, fare clic **su Aggiungi** ![ Icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="15ae6-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="15ae6-190">Nella finestra di dialogo visualizzata individuare e selezionare un destinatario o un gruppo e quindi fare clic su **aggiungi ->**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="15ae6-191">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="15ae6-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="15ae6-192">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="15ae6-193">Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi Icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="15ae6-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="15ae6-194">Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere gruppi</span><span class="sxs-lookup"><span data-stu-id="15ae6-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="15ae6-195">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="15ae6-196">Nell'elenco dei gruppi selezionare il gruppo di distribuzione che si desidera rimuovere e quindi fare clic su **Rimuovi** ![ Icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="15ae6-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="15ae6-197">Usare PowerShell per gestire i gruppi</span><span class="sxs-lookup"><span data-stu-id="15ae6-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="15ae6-198">Usare PowerShell EOP autonomo per visualizzare i gruppi</span><span class="sxs-lookup"><span data-stu-id="15ae6-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="15ae6-199">Per restituire un elenco riepilogativo di tutti i gruppi di distribuzione e di sicurezza abilitati alla posta elettronica in PowerShell EOP autonomo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="15ae6-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="15ae6-200">Per restituire l'elenco dei membri del gruppo, sostituire con il nome, l'alias o l'indirizzo di posta elettronica del gruppo \<GroupIdentity\> ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="15ae6-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="15ae6-201">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="15ae6-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="15ae6-202">Usare PowerShell EOP autonomo per creare gruppi</span><span class="sxs-lookup"><span data-stu-id="15ae6-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="15ae6-203">Per creare gruppi di distribuzione o gruppi di sicurezza abilitati alla posta elettronica in PowerShell EOP autonomo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="15ae6-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="15ae6-204">**Note**:</span><span class="sxs-lookup"><span data-stu-id="15ae6-204">**Notes**:</span></span>

- <span data-ttu-id="15ae6-205">Il _parametro Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="15ae6-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="15ae6-206">Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="15ae6-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="15ae6-207">Se non si utilizza il parametro _Alias,_ viene utilizzato il _parametro Name_ per il valore dell'alias.</span><span class="sxs-lookup"><span data-stu-id="15ae6-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="15ae6-208">Gli spazi vengono rimossi e i caratteri non supportati vengono convertiti in punti interrogativi (?).</span><span class="sxs-lookup"><span data-stu-id="15ae6-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="15ae6-209">Se non si utilizza il _parametro PrimarySmtpAddress,_ il valore dell'alias viene utilizzato nel _parametro PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="15ae6-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="15ae6-210">Se non si utilizza il parametro _Type,_ il valore predefinito è Distribution.</span><span class="sxs-lookup"><span data-stu-id="15ae6-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="15ae6-211">In questo esempio viene creato un gruppo di distribuzione denominato IT Administrators con le proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="15ae6-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="15ae6-212">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="15ae6-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="15ae6-213">Usare PowerShell EOP autonomo per modificare i gruppi</span><span class="sxs-lookup"><span data-stu-id="15ae6-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="15ae6-214">Per modificare i gruppi in PowerShell EOP autonomo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="15ae6-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="15ae6-215">In questo esempio viene utilizzato l'indirizzo SMTP primario (denominato anche indirizzo di risposta) per il gruppo Seattle Employees sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="15ae6-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="15ae6-216">In questo esempio i membri correnti del gruppo Security Team vengono sostituiti da Kitty Petersen e Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="15ae6-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="15ae6-217">In questo esempio viene aggiunto un nuovo utente denominato Tyson Fawcett al gruppo denominato Security Team mantenendo i membri correnti del gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="15ae6-218">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) [e Update-EOPDistributionGroupMember](/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="15ae6-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="15ae6-219">Rimuovere un gruppo tramite l'Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15ae6-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="15ae6-220">In questo esempio viene rimosso il gruppo di distribuzione denominato IT Administrators.</span><span class="sxs-lookup"><span data-stu-id="15ae6-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="15ae6-221">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-EOPDistributionGroup](/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="15ae6-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="15ae6-222">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="15ae6-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="15ae6-223">Per verificare la corretta creazione, modifica o rimozione di un gruppo di distribuzione o di un gruppo di sicurezza abilitato alla posta elettronica, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15ae6-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="15ae6-224">Nell'EAC, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="15ae6-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="15ae6-225">Verificare che il gruppo sia elencato (o non elencato) e verificare il **valore Tipo di** gruppo.</span><span class="sxs-lookup"><span data-stu-id="15ae6-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="15ae6-226">Selezionare il gruppo e visualizzare le informazioni nel riquadro Dettagli oppure fare clic **su Modifica** icona Modifica per visualizzare ![ le ](../../media/ITPro-EAC-AddIcon.png) impostazioni.</span><span class="sxs-lookup"><span data-stu-id="15ae6-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="15ae6-227">In PowerShell EOP autonomo, eseguire il comando seguente per verificare che il gruppo sia elencato (o non sia elencato):</span><span class="sxs-lookup"><span data-stu-id="15ae6-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="15ae6-228">Sostituire \<GroupIdentity\> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando seguente per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="15ae6-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="15ae6-229">Per visualizzare i membri del gruppo, sostituire con il nome, l'alias o l'indirizzo di posta elettronica del gruppo \<GroupIdentity\> ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="15ae6-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```