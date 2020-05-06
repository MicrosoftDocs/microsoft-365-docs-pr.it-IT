---
title: Gestione utenti di posta in EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Informazioni su come gestire gli utenti di posta elettronica in Exchange Online Protection (EOP), tra cui l'utilizzo della sincronizzazione della directory, EAC e PowerShell per la gestione degli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a4555bf4b6a716839c327c692f0e44b590f8175
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035557"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="d968e-103">Gestire utenti di posta in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d968e-103">Manage mail users in EOP</span></span>

<span data-ttu-id="d968e-p101">La definizione degli utenti di posta è una parte importante della gestione del servizio Exchange Online Protection (EOP). In EOP è possibile gestire gli utenti in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="d968e-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>

- <span data-ttu-id="d968e-p102">**Utilizzare la sincronizzazione della directory per gestire gli utenti di posta**: se in azienda sono presenti account utente in un ambiente di Active Directory locale, è possibile sincronizzarli con Azure Active Directory (AD), dove una copia di tali account è memorizzata nel cloud. Durante la sincronizzazione degli account utente esistenti su Azure Active Directory, è possibile visualizzare tali utenti nel riquadro **Destinatari** nell'interfaccia di amministrazione di Exchange (EAC). Si consiglia di utilizzare la sincronizzazione delle directory.</span><span class="sxs-lookup"><span data-stu-id="d968e-p102">**Use directory synchronization to manage mail users**: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud. When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC). Using directory synchronization is recommended.</span></span>

- <span data-ttu-id="d968e-p103">**Utilizzare il valore EAC per gestire gli utenti di posta**: aggiungere e gestire gli utenti di posta direttamente in EAC. Si tratta del modo più semplice per aggiungere utenti di posta elettronica ed è utile per aggiungere un utente alla volta.</span><span class="sxs-lookup"><span data-stu-id="d968e-p103">**Use the EAC to manage mail users**: Add and manage mail users directly in the EAC. This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="d968e-111">**Utilizzare PowerShell per gestire gli utenti di posta elettronica**: aggiungere e gestire gli utenti di posta elettronica in PowerShell di Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="d968e-111">**Use PowerShell to manage mail users**: Add and manage mail users by in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="d968e-112">Questo metodo è utile per aggiungere più record e creare script.</span><span class="sxs-lookup"><span data-stu-id="d968e-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="d968e-113">È possibile aggiungere utenti nell'interfaccia di amministrazione di Microsoft 365, ma questi utenti non possono essere utilizzati come destinatari della posta.</span><span class="sxs-lookup"><span data-stu-id="d968e-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d968e-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d968e-114">Before you begin</span></span>

- <span data-ttu-id="d968e-115">Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d968e-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="d968e-p105">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere voce "Utente, Contatti e Gruppi ruolo" in [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d968e-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="d968e-118">Tenere presente che quando si creano utenti di posta elettronica utilizzando i cmdlet di PowerShell di Exchange Online Protection, è possibile che si verifichi la limitazione.</span><span class="sxs-lookup"><span data-stu-id="d968e-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="d968e-119">I comandi di PowerShell riportati in questo argomento utilizzano un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.</span><span class="sxs-lookup"><span data-stu-id="d968e-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="d968e-120">Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online Protection, vedere [Connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d968e-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d968e-121">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="d968e-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="d968e-122">Problemi?</span><span class="sxs-lookup"><span data-stu-id="d968e-122">Having problems?</span></span> <span data-ttu-id="d968e-123">Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="d968e-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="d968e-124">Utilizzare la sincronizzazione della directory per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="d968e-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="d968e-125">Nella presente sezione vengono fornite informazioni sulla gestione degli utenti di posta elettronica utilizzando la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="d968e-125">This section provides information about managing email users by using directory synchronization.</span></span>

<span data-ttu-id="d968e-126">**Note**:</span><span class="sxs-lookup"><span data-stu-id="d968e-126">**Notes**:</span></span>

- <span data-ttu-id="d968e-127">Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365, ma non verranno sincronizzati con Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="d968e-127">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="d968e-128">Questo perché la sincronizzazione della directory Sincronizza solo i destinatari **dall'** Active Directory locale **al** cloud.</span><span class="sxs-lookup"><span data-stu-id="d968e-128">This is because directory synchronization only syncs recipients **from** your on-premises Active Directory **to** the cloud.</span></span>

- <span data-ttu-id="d968e-129">La sincronizzazione della directory è consigliata per l'utilizzo con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="d968e-129">Directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="d968e-130">**Elenchi di mittenti attendibili e mittenti bloccati di Outlook**: quando vengono sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro di posta indesiderata nel servizio.</span><span class="sxs-lookup"><span data-stu-id="d968e-130">**Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="d968e-131">Ciò consente agli utenti di gestire i propri elenchi di utenti attendibili o bloccati a livello di organizzazione o a livello di singolo utente.</span><span class="sxs-lookup"><span data-stu-id="d968e-131">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span>

  - <span data-ttu-id="d968e-132">**Blocking Edge basato su directory (DBEB)**: per ulteriori informazioni su DBEB, vedere [use directory based Edge Blocking to Reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="d968e-132">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="d968e-133">**Quarantena della posta indesiderata dell'utente finale**: per accedere alla quarantena della posta indesiderata dell'utente finale, gli utenti finali devono disporre di un ID utente e una password validi.</span><span class="sxs-lookup"><span data-stu-id="d968e-133">**End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid user ID and password.</span></span> <span data-ttu-id="d968e-134">I clienti EOP che proteggono le cassette postali locali devono essere utenti di posta elettronica validi.</span><span class="sxs-lookup"><span data-stu-id="d968e-134">EOP customers protecting on-premises mailboxes must be valid email users.</span></span>

  - <span data-ttu-id="d968e-135">**Regole del flusso di posta**: quando si utilizza la sincronizzazione della directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud ed è quindi possibile creare regole del flusso di posta (note anche come regole di trasporto) che devono essere indirizzate a utenti e/o gruppi specifici senza dover aggiungerle manualmente tramite l'EAC o Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d968e-135">**Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="d968e-136">Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) tramite la sincronizzazione delle directory.</span><span class="sxs-lookup"><span data-stu-id="d968e-136">Note that [dynamic distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="d968e-137">Ottenere le autorizzazioni necessarie e prepararsi per la sincronizzazione della directory, come descritto in [che cos'è Hybrid Identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="d968e-137">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="d968e-138">Per sincronizzare le directory degli utenti con Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="d968e-138">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="d968e-139">Per sincronizzare gli utenti con Azure Active Directory (AAD), è necessario prima di tutto **attivare la sincronizzazione della directory**, come descritto in [Azure ad Connect Sync: understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="d968e-139">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="d968e-140">La successiva è l'installazione e la configurazione di un computer locale per l'esecuzione di AAD Connect (se non è già presente una--una cosa degna di essere verificata in anticipo).</span><span class="sxs-lookup"><span data-stu-id="d968e-140">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="d968e-141">La [configurazione di AAD Connect, l'argomento Express Way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) spiega come configurare e sincronizzare gli account da locale AD Azure ad con AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="d968e-141">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="d968e-142">Tuttavia, prima di eseguire tale operazione, accertarsi di [rispettare i prerequisiti](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)e [scegliere il tipo di installazione](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="d968e-142">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="d968e-143">Il collegamento precedente è un breve articolo relativo all'installazione espressa.</span><span class="sxs-lookup"><span data-stu-id="d968e-143">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="d968e-144">Se necessario, è possibile trovare anche articoli su [installazioni personalizzate](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)o [l'autenticazione pass-through](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) .</span><span class="sxs-lookup"><span data-stu-id="d968e-144">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d968e-p113">Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto.</span><span class="sxs-lookup"><span data-stu-id="d968e-p113">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="d968e-148">Dopo aver configurato la sincronizzazione, accertarsi di verificare che EOP sia sincronizzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d968e-148">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="d968e-149">In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale.</span><span class="sxs-lookup"><span data-stu-id="d968e-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="d968e-150">Utilizzare il valore EAC per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="d968e-150">Use the EAC to manage mail users</span></span>

<span data-ttu-id="d968e-151">In questa sezione vengono fornite informazioni sull'aggiunta e la gestione degli utenti di posta elettronica direttamente in EAC.</span><span class="sxs-lookup"><span data-stu-id="d968e-151">This section provides information about adding and managing email users directly in the EAC.</span></span>

### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="d968e-152">Utilizzo dell'interfaccia di amministrazione di Exchange per aggiungere un utente di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d968e-152">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="d968e-153">Per creare un utente di posta elettronica, andare a **Destinatari** \> **Contatti** in EAC, quindi fare clic su **Nuovo +**.</span><span class="sxs-lookup"><span data-stu-id="d968e-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="d968e-154">Nella pagina **Nuovo utente di posta**, immettere le informazioni dell'utente, incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d968e-154">On the **New mail user** page, enter the user's information, including the following:</span></span>

   ****

   |<span data-ttu-id="d968e-155">**Proprietà utente della posta**</span><span class="sxs-lookup"><span data-stu-id="d968e-155">**Mail user property**</span></span>|<span data-ttu-id="d968e-156">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d968e-156">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="d968e-157">**Nome**, **Iniziali**, and **Cognome**</span><span class="sxs-lookup"><span data-stu-id="d968e-157">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="d968e-158">Digitare il nome completo dell'utente nelle caselle appropriate.</span><span class="sxs-lookup"><span data-stu-id="d968e-158">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="d968e-159">**Nome visualizzato**</span><span class="sxs-lookup"><span data-stu-id="d968e-159">**Display name**</span></span>|<span data-ttu-id="d968e-p115">Digitare un nome, utilizzando un massimo di 64 caratteri. Per impostazione predefinita, questa casella contiene i nomi nelle caselle **Nome**, **Iniziali** e **Cognome**. Il nome visualizzato è obbligatorio.  </span><span class="sxs-lookup"><span data-stu-id="d968e-p115">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="d968e-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d968e-163">**Alias**</span></span>|<span data-ttu-id="d968e-p116">Digitare un alias univoco per l'utente, utilizzando un massimo di 64 caratteri. L'alias è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d968e-p116">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="d968e-166">**Indirizzo di posta elettronica esterno**</span><span class="sxs-lookup"><span data-stu-id="d968e-166">**External email address**</span></span>|<span data-ttu-id="d968e-167">Digitare l'indirizzo di posta elettronica esterno dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d968e-167">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="d968e-168">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="d968e-168">**User id**</span></span>|<span data-ttu-id="d968e-p117">Digitare il nome utilizzato dall'utente di posta per accedere al servizio. Il nome di accesso dell'utente è costituito da un nome utente a sinistra del simbolo @ e da un suffisso a destra del simbolo. In genere, il suffisso è costituito dal nome di dominio in cui risiede l'account utente.</span><span class="sxs-lookup"><span data-stu-id="d968e-p117">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="d968e-172">**Nuova password**</span><span class="sxs-lookup"><span data-stu-id="d968e-172">**New password**</span></span>|<span data-ttu-id="d968e-p118">Digitare la password utilizzata dall'utente di posta per accedere al servizio. Verificare che la password immessa sia conforme ai requisiti di lunghezza, complessità e cronologia del dominio in cui viene creato l'account utente.</span><span class="sxs-lookup"><span data-stu-id="d968e-p118">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="d968e-175">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="d968e-175">**Confirm password**</span></span>|<span data-ttu-id="d968e-176">Digitare nuovamente la password per confermarla.</span><span class="sxs-lookup"><span data-stu-id="d968e-176">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="d968e-p119">Fare clic su **Salva** per creare il nuovo utente di posta elettronica. Il nuovo utente viene visualizzato nell'elenco utenti.</span><span class="sxs-lookup"><span data-stu-id="d968e-p119">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="d968e-179">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare o rimuovere un utente di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d968e-179">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="d968e-180">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="d968e-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="d968e-181">Nell'elenco degli utenti, fare clic sull'utente che si desidera visualizzare o modificare, quindi selezionare **modifica** ![icona](../../media/ITPro-EAC-EditIcon.gif) modifica per aggiornare le impostazioni utente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d968e-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="d968e-182">È possibile modificare il nome utente, l'alias o le informazioni di contatto e registrare le informazioni dettagliate sul ruolo dell'utente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d968e-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="d968e-183">È inoltre possibile selezionare un utente e quindi scegliere **Rimuovi** ![icona](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="d968e-183">You can also select a user and then choose **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span>

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="d968e-184">Utilizzare PowerShell di Exchange Online Protection per gestire gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d968e-184">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="d968e-185">In questa sezione vengono fornite informazioni sull'aggiunta e sulla gestione degli utenti di posta elettronica mediante l'utilizzo di Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="d968e-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>

### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="d968e-186">Utilizzo di EOP PowerShell per aggiungere un utente di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d968e-186">Use EOP PowerShell to add a mail user</span></span>

<span data-ttu-id="d968e-187">In questo esempio viene utilizzato il cmdlet [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) per creare un account utente abilitato alla posta elettronica per Jeffrey Zeng in EOP con i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="d968e-187">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>

- <span data-ttu-id="d968e-188">Il nome è Jeffrey e il cognome è Zeng.</span><span class="sxs-lookup"><span data-stu-id="d968e-188">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="d968e-189">Il nome è Jeffrey e il nome visualizzato è Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="d968e-189">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="d968e-190">L'alias è jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="d968e-190">The alias is jeffreyz.</span></span>

- <span data-ttu-id="d968e-191">L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="d968e-191">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="d968e-192">Il nome di accesso di Microsoft 365 è jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d968e-192">The Microsoft 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="d968e-193">La password è Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="d968e-193">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="d968e-194">Per verificare la corretta esecuzione, eseguire il comando riportato di seguito per visualizzare le informazioni sul nuovo utente di posta elettronica Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="d968e-194">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="d968e-195">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span><span class="sxs-lookup"><span data-stu-id="d968e-195">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="d968e-196">Utilizzo di EOP PowerShell per modificare le proprietà di un utente di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d968e-196">Use EOP PowerShell to edit the properties of a mail user</span></span>

<span data-ttu-id="d968e-197">Utilizzare i cmdlet di [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) e [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) per visualizzare o modificare le proprietà degli utenti di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d968e-197">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>

<span data-ttu-id="d968e-198">In questo esempio viene impostato l'indirizzo di posta elettronica esterno per Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="d968e-198">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="d968e-199">In questo esempio viene impostata la proprietà Company per tutti gli utenti di posta di Contoso.</span><span class="sxs-lookup"><span data-stu-id="d968e-199">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="d968e-200">Per verificare che l'operazione abbia avuto esito positivo, utilizzare il cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) per verificare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d968e-200">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="d968e-201">(Tenere presente che è possibile visualizzare più proprietà per più contatti di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="d968e-201">(Note that you can view multiple properties for multiple mail contacts.)</span></span>

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="d968e-202">Nell'esempio precedente in cui la proprietà Company è stata impostata su Contoso per tutti gli utenti di posta, utilizzare il comando seguente per verificare le modifiche:</span><span class="sxs-lookup"><span data-stu-id="d968e-202">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="d968e-203">Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili.</span><span class="sxs-lookup"><span data-stu-id="d968e-203">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>

### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="d968e-204">Utilizzo di EOP PowerShell per rimuovere un utente di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d968e-204">Use EOP PowerShell to remove a mail user</span></span>

<span data-ttu-id="d968e-205">In questo esempio viene utilizzato il cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) per eliminare l'utente Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="d968e-205">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
<span data-ttu-id="d968e-206">Per verificare che l'operazione abbia avuto esito positivo, eseguire il cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) per verificare che l'utente di posta non sia più presente.</span><span class="sxs-lookup"><span data-stu-id="d968e-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>

```PowerShell
Get-Recipient Jeffrey | Format-List
```
