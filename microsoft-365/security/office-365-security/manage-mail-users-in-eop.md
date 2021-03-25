---
title: Gestire gli utenti di posta in Exchange Online Protection autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Informazioni su come gestire gli utenti di posta elettronica in Exchange Online Protection (EOP), tra cui l'utilizzo della sincronizzazione della directory, EAC e PowerShell per gestire gli utenti.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205045"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="52573-103">Gestire gli utenti di posta in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="52573-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="52573-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="52573-104">**Applies to**</span></span>
-  [<span data-ttu-id="52573-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="52573-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="52573-106">Nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, gli utenti di posta elettronica sono il tipo fondamentale di account utente.</span><span class="sxs-lookup"><span data-stu-id="52573-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="52573-107">Un utente di posta elettronica dispone delle credenziali dell'account nell'organizzazione EOP autonoma e può accedere alle risorse (a cui sono assegnate le autorizzazioni).</span><span class="sxs-lookup"><span data-stu-id="52573-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="52573-108">L'indirizzo di posta elettronica di un utente di posta elettronica è esterno, ad esempio nell'ambiente di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="52573-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="52573-109">Quando si crea un utente di posta elettronica, l'account utente corrispondente è disponibile nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52573-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="52573-110">Quando si crea un account utente nell'interfaccia di amministrazione di Microsoft 365, non è possibile utilizzare tale account per creare un utente di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="52573-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="52573-111">Il metodo consigliato per creare e gestire gli utenti di posta in EOP autonomo è quello di utilizzare la sincronizzazione della directory come descritto nella sezione Utilizzare la [sincronizzazione della directory](#use-directory-synchronization-to-manage-mail-users) per gestire gli utenti di posta elettronica più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="52573-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="52573-112">Per le organizzazioni EOP autonome con un numero limitato di utenti, è possibile aggiungere e gestire gli utenti di posta nell'interfaccia di amministrazione di Exchange (EAC) o in PowerShell EOP autonomo come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="52573-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52573-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="52573-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52573-114">Per aprire l'interfaccia di amministrazione di Exchange ( EAC), vedere Interfaccia di amministrazione [di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="52573-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="52573-115">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="52573-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="52573-116">Quando si creano utenti di posta elettronica in PowerShell di EOP, è possibile che si verifichino limitazioni.</span><span class="sxs-lookup"><span data-stu-id="52573-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="52573-117">Inoltre, i cmdlet di PowerShell di EOP utilizzano un metodo di elaborazione batch che determina un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.</span><span class="sxs-lookup"><span data-stu-id="52573-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="52573-118">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="52573-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="52573-119">In particolare, è necessario disporre dei ruoli Creazione destinatario di posta **(creazione)** e Destinatari  di posta **(modifica),** assegnati ai gruppi di ruoli **Gestione** organizzazione (amministratori globali) e Gestione destinatari per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="52573-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="52573-120">Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="52573-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="52573-121">Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="52573-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="52573-122">Problemi?</span><span class="sxs-lookup"><span data-stu-id="52573-122">Having problems?</span></span> <span data-ttu-id="52573-123">È possibile richiedere supporto nei forum di Exchange.</span><span class="sxs-lookup"><span data-stu-id="52573-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="52573-124">Visitare il forum [di Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="52573-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="52573-125">Utilizzare l'interfaccia di amministrazione di Exchange per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="52573-126">Utilizzo dell'interfaccia di amministrazione di Exchange per creare utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="52573-127">Nell'interfaccia di amministrazione di Exchange, accedere **a Destinatari** \> **Contatti**</span><span class="sxs-lookup"><span data-stu-id="52573-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="52573-128">Fare **clic su** Nuova icona Nuovo ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="52573-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="52573-129">Nella pagina **Nuovo utente di** posta elettronica visualizzata configurare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="52573-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="52573-130">Le impostazioni contrassegnate con <sup>\*</sup> un sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="52573-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="52573-131">**Nome**</span><span class="sxs-lookup"><span data-stu-id="52573-131">**First name**</span></span>

   - <span data-ttu-id="52573-132">**Iniziali**: iniziale centrale della persona.</span><span class="sxs-lookup"><span data-stu-id="52573-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="52573-133">**Cognome**</span><span class="sxs-lookup"><span data-stu-id="52573-133">**Last name**</span></span>

   - <span data-ttu-id="52573-134"><sup>\*</sup>**Nome visualizzato**: per impostazione predefinita, questa casella mostra i valori delle caselle **Nome,** Iniziali **e Cognome.**</span><span class="sxs-lookup"><span data-stu-id="52573-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="52573-135">È possibile accettare questo valore o modificarlo.</span><span class="sxs-lookup"><span data-stu-id="52573-135">You can accept this value or change it.</span></span> <span data-ttu-id="52573-136">Il valore deve essere univoco e ha una lunghezza massima di 64 caratteri.</span><span class="sxs-lookup"><span data-stu-id="52573-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="52573-137"><sup>\*</sup>**Alias**: immettere un alias univoco, utilizzando fino a 64 caratteri, per l'utente</span><span class="sxs-lookup"><span data-stu-id="52573-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="52573-138">**Indirizzo di posta elettronica esterno:** immettere l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="52573-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="52573-139">Il dominio deve essere esterno all'organizzazione basata su cloud.</span><span class="sxs-lookup"><span data-stu-id="52573-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="52573-140"><sup>\*</sup>**ID utente:** immettere l'account che verrà utilizzato dalla persona per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="52573-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="52573-141">L'ID utente è costituito da un nome utente a sinistra del simbolo (@) (@) e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="52573-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="52573-142"><sup>\*</sup>**Nuova password** e <sup>\*</sup> **Conferma password**: immettere e immettere di nuovo la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="52573-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="52573-143">Verificare che la password sia conforme ai requisiti di lunghezza, complessità e cronologia della password dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52573-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="52573-144">Al termine fare clic su **Salva** per creare l'utente di posta.</span><span class="sxs-lookup"><span data-stu-id="52573-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="52573-145">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="52573-146">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="52573-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="52573-147">Selezionare l'utente di posta elettronica che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="52573-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="52573-148">Nella pagina delle proprietà dell'utente di posta elettronica visualizzata fare clic su una delle schede seguenti per visualizzare o modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="52573-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="52573-149">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="52573-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="52573-150">Generale</span><span class="sxs-lookup"><span data-stu-id="52573-150">General</span></span>

<span data-ttu-id="52573-151">Utilizzare la **scheda Generale** per visualizzare o modificare le informazioni di base sull'utente di posta.</span><span class="sxs-lookup"><span data-stu-id="52573-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="52573-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="52573-152">**First name**</span></span>

- <span data-ttu-id="52573-153">**Iniziali**</span><span class="sxs-lookup"><span data-stu-id="52573-153">**Initials**</span></span>

- <span data-ttu-id="52573-154">**Cognome**</span><span class="sxs-lookup"><span data-stu-id="52573-154">**Last name**</span></span>

- <span data-ttu-id="52573-155">**Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nelle righe A: e Da: nei messaggi di posta elettronica e nell'elenco dei contatti nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="52573-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="52573-156">Questo nome non può contenere spazi vuoti prima o dopo il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="52573-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="52573-157">**ID utente:** questo è l'account dell'utente in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52573-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="52573-158">Non è possibile modificare questo valore qui.</span><span class="sxs-lookup"><span data-stu-id="52573-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="52573-159">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="52573-159">Contact information</span></span>

<span data-ttu-id="52573-160">Utilizzare la **scheda Informazioni di** contatto per visualizzare o modificare le informazioni di contatto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="52573-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="52573-161">Le informazioni di questa pagina vengono visualizzate nella Rubrica.</span><span class="sxs-lookup"><span data-stu-id="52573-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="52573-162">**Via**</span><span class="sxs-lookup"><span data-stu-id="52573-162">**Street**</span></span>
- <span data-ttu-id="52573-163">**Città**</span><span class="sxs-lookup"><span data-stu-id="52573-163">**City**</span></span>
- <span data-ttu-id="52573-164">**Stato/Provincia**</span><span class="sxs-lookup"><span data-stu-id="52573-164">**State/Province**</span></span>
- <span data-ttu-id="52573-165">**CAP**</span><span class="sxs-lookup"><span data-stu-id="52573-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="52573-166">**Paese/area geografica**</span><span class="sxs-lookup"><span data-stu-id="52573-166">**Country/Region**</span></span>
- <span data-ttu-id="52573-167">**Ufficio**</span><span class="sxs-lookup"><span data-stu-id="52573-167">**Work phone**</span></span>
- <span data-ttu-id="52573-168">**Cellulare**</span><span class="sxs-lookup"><span data-stu-id="52573-168">**Mobile phone**</span></span>
- <span data-ttu-id="52573-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="52573-169">**Fax**</span></span>
- <span data-ttu-id="52573-170">**Altre opzioni**</span><span class="sxs-lookup"><span data-stu-id="52573-170">**More options**</span></span>

  - <span data-ttu-id="52573-171">**Ufficio**</span><span class="sxs-lookup"><span data-stu-id="52573-171">**Office**</span></span>
  - <span data-ttu-id="52573-172">**Abitazione**</span><span class="sxs-lookup"><span data-stu-id="52573-172">**Home phone**</span></span>
  - <span data-ttu-id="52573-173">**Pagina Web**</span><span class="sxs-lookup"><span data-stu-id="52573-173">**Web page**</span></span>
  - <span data-ttu-id="52573-174">**Note**</span><span class="sxs-lookup"><span data-stu-id="52573-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="52573-175">Organizzazione</span><span class="sxs-lookup"><span data-stu-id="52573-175">Organization</span></span>

<span data-ttu-id="52573-176">Utilizzare la **scheda** Organizzazione per registrare informazioni dettagliate sul ruolo dell'utente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52573-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="52573-177">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="52573-177">**Title**</span></span>
- <span data-ttu-id="52573-178">**Department**</span><span class="sxs-lookup"><span data-stu-id="52573-178">**Department**</span></span>
- <span data-ttu-id="52573-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="52573-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="52573-180">Rimozione degli utenti di posta tramite EAC</span><span class="sxs-lookup"><span data-stu-id="52573-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="52573-181">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="52573-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="52573-182">Selezionare l'utente di posta che si desidera rimuovere e quindi fare clic su **Rimuovi** ![ Icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="52573-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="52573-183">Utilizzare PowerShell per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="52573-184">Usare PowerShell EOP autonomo per visualizzare gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="52573-185">Per restituire un elenco riepilogativo di tutti gli utenti di posta elettronica in PowerShell EOP autonomo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="52573-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="52573-186">Per visualizzare informazioni dettagliate su un utente di posta specifico, sostituire con il nome, l'alias o il nome dell'account dell'utente di posta \<MailUserIdentity\> elettronica ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="52573-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="52573-187">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-Recipient](/powershell/module/exchange/get-recipient) e [Get-User](/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="52573-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="52573-188">Utilizzare PowerShell EOP autonomo per creare utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="52573-189">Per creare utenti di posta elettronica in PowerShell EOP autonomo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="52573-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="52573-190">**Note**:</span><span class="sxs-lookup"><span data-stu-id="52573-190">**Notes**:</span></span>

- <span data-ttu-id="52573-191">Il _parametro Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="52573-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="52573-192">Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="52573-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="52573-193">Se non si utilizza il parametro _Alias,_ viene utilizzato il lato sinistro del parametro _MicrosoftOnlineServicesID_ per l'alias.</span><span class="sxs-lookup"><span data-stu-id="52573-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="52573-194">Se non si utilizza il _parametro ExternalEmailAddress,_ viene utilizzato il valore _MicrosoftOnlineServicesID_ per l'indirizzo di posta elettronica esterno.</span><span class="sxs-lookup"><span data-stu-id="52573-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="52573-195">In questo esempio viene creato un utente di posta con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52573-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="52573-196">Il nome è JeffreyZeng e il nome visualizzato è Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="52573-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="52573-197">Il nome è Jeffrey e il cognome è Zeng.</span><span class="sxs-lookup"><span data-stu-id="52573-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="52573-198">L'alias è jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="52573-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="52573-199">L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="52573-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="52573-200">Il nome dell'account jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="52573-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="52573-201">La password è Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="52573-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="52573-202">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-EOPMailUser.](/powershell/module/exchange/new-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="52573-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="52573-203">Utilizzare PowerShell EOP autonomo per modificare gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="52573-204">Per modificare gli utenti di posta elettronica esistenti in PowerShell EOP autonomo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="52573-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="52573-205">In questo esempio viene impostato l'indirizzo di posta elettronica esterno per Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="52573-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="52573-206">In questo esempio viene impostata la proprietà Company per tutti gli utenti di posta di Contoso.</span><span class="sxs-lookup"><span data-stu-id="52573-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="52573-207">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="52573-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="52573-208">Utilizzare PowerShell EOP autonomo per rimuovere gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="52573-209">Per rimuovere gli utenti di posta elettronica in PowerShell EOP autonomo, sostituire con il nome, l'alias o il nome dell'account dell'utente di posta \<MailUserIdentity\> elettronica ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="52573-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="52573-210">In questo esempio viene rimosso l'utente di posta per Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="52573-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="52573-211">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="52573-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="52573-212">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="52573-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="52573-213">Per verificare di aver creato, modificato o rimosso correttamente gli utenti di posta elettronica in EOP autonomo, utilizzare una delle procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="52573-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="52573-214">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="52573-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="52573-215">Verificare che l'utente di posta sia elencato (o non sia elencato).</span><span class="sxs-lookup"><span data-stu-id="52573-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="52573-216">Selezionare l'utente di posta elettronica e visualizzare le informazioni nel riquadro Dettagli oppure fare clic **su Modifica** icona Modifica per visualizzare ![ le ](../../media/ITPro-EAC-AddIcon.png) impostazioni.</span><span class="sxs-lookup"><span data-stu-id="52573-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="52573-217">In PowerShell EOP autonomo, eseguire il comando seguente per verificare che l'utente di posta sia elencato (o non sia elencato):</span><span class="sxs-lookup"><span data-stu-id="52573-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="52573-218">Sostituire con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire i \<MailUserIdentity\> comandi seguenti per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="52573-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="52573-219">Utilizzare la sincronizzazione della directory per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="52573-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="52573-220">In EOP autonomo, la sincronizzazione della directory è disponibile per i clienti con Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="52573-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="52573-221">È possibile sincronizzare tali account con Azure Active Directory (Azure AD), dove le copie degli account sono archiviate nel cloud.</span><span class="sxs-lookup"><span data-stu-id="52573-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="52573-222">Quando si sincronizzano gli account utente esistenti con Azure  Active Directory, è possibile visualizzare tali utenti nel riquadro Destinatari dell'interfaccia di amministrazione di Exchange (EAC) o in PowerShell EOP autonomo.</span><span class="sxs-lookup"><span data-stu-id="52573-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="52573-223">**Note**:</span><span class="sxs-lookup"><span data-stu-id="52573-223">**Notes**:</span></span>

- <span data-ttu-id="52573-224">Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365, ma non verranno sincronizzati con Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="52573-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="52573-225">Tuttavia questi non verranno sincronizzati con Active Directory in locale poiché la sincronizzazione della directory sincronizza solamente i destinatari dall'Active Directory locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="52573-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="52573-226">Si consiglia di utilizzare la sincronizzazione della directory con le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="52573-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="52573-227">**Elenchi Mittenti attendibili di Outlook** e Mittenti bloccati : quando vengono sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro posta indesiderata nel servizio.</span><span class="sxs-lookup"><span data-stu-id="52573-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="52573-228">In questo modo gli utenti possono gestire il proprio elenco Mittenti attendibili e Mittenti bloccati con singole voci di mittente e dominio.</span><span class="sxs-lookup"><span data-stu-id="52573-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="52573-229">Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="52573-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="52573-230">**Directory Based Edge Blocking (DBEB):** per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="52573-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="52573-231">**Accesso dell'utente finale alla** quarantena : per accedere ai messaggi in quarantena, i destinatari devono disporre di un ID utente e di una password validi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="52573-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="52573-232">Per ulteriori informazioni sulla quarantena, vedere [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="52573-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="52573-233">Regole del flusso di posta (note anche come regole di **trasporto):** quando si utilizza la sincronizzazione della directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud ed è quindi possibile creare regole del flusso di posta per utenti e/o gruppi specifici senza doverli aggiungere manualmente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="52573-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="52573-234">Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) tramite la sincronizzazione delle directory.</span><span class="sxs-lookup"><span data-stu-id="52573-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="52573-235">Ottenere le autorizzazioni necessarie e prepararsi per la sincronizzazione della directory, come descritto in Che cos'è l'identità [ibrida con Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="52573-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="52573-236">Sincronizzare le directory con Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="52573-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="52573-237">Attivare la sincronizzazione della directory come descritto in [Sincronizzazione di Azure AD Connect: informazioni e personalizzazione della sincronizzazione.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="52573-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="52573-238">Installare e configurare un computer locale per l'esecuzione di AAD Connect, come descritto in [Prerequisiti per Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="52573-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="52573-239">[Selezionare il tipo di installazione da usare per Azure AD Connect:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="52573-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="52573-240">Express</span><span class="sxs-lookup"><span data-stu-id="52573-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="52573-241">Personalizzata</span><span class="sxs-lookup"><span data-stu-id="52573-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="52573-242">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="52573-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="52573-p121">Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto.</span><span class="sxs-lookup"><span data-stu-id="52573-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="52573-246">Dopo aver configurato la sincronizzazione, verificare che AAD Connect sia sincronizzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="52573-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="52573-247">In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale.</span><span class="sxs-lookup"><span data-stu-id="52573-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>