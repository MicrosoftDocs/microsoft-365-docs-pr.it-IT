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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Informazioni su come gestire gli utenti di posta elettronica in Exchange Online Protection (EOP), tra cui l'utilizzo della sincronizzazione della directory, EAC e PowerShell per la gestione degli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658834"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="384dc-103">Gestire gli utenti di posta in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="384dc-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="384dc-104">Nelle organizzazioni standalone di Exchange Online Protection (EOP) prive di cassette postali di Exchange Online, gli utenti di posta elettronica sono il tipo fondamentale di account utente.</span><span class="sxs-lookup"><span data-stu-id="384dc-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="384dc-105">Un utente di posta dispone di credenziali dell'account nell'organizzazione di EOP autonoma e può accedere alle risorse (dispongono delle autorizzazioni assegnate).</span><span class="sxs-lookup"><span data-stu-id="384dc-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="384dc-106">L'indirizzo di posta elettronica di un utente di posta elettronica è esterno, ad esempio nell'ambiente di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="384dc-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="384dc-107">Quando si crea un utente di posta elettronica, l'account utente corrispondente è disponibile nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="384dc-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="384dc-108">Quando si crea un account utente nell'interfaccia di amministrazione di Microsoft 365, non è possibile utilizzare tale account per creare un utente di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="384dc-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="384dc-109">Il metodo consigliato per creare e gestire gli utenti di posta in EOP autonomo consiste nell'utilizzare la sincronizzazione della directory come descritto nella sezione [utilizzo della sincronizzazione della directory per la gestione degli utenti di posta elettronica](#use-directory-synchronization-to-manage-mail-users) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="384dc-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="384dc-110">Per le organizzazioni di EOP autonome con un numero limitato di utenti, è possibile aggiungere e gestire gli utenti di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) o in EOP standalone PowerShell come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="384dc-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="384dc-111">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="384dc-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="384dc-112">Per aprire l'interfaccia di amministrazione di Exchange (EAC), vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="384dc-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="384dc-113">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="384dc-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="384dc-114">Quando si creano utenti di posta elettronica in EOP PowerShell, è possibile che si verifichi la limitazione.</span><span class="sxs-lookup"><span data-stu-id="384dc-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="384dc-115">Inoltre, i cmdlet di PowerShell di EOP utilizzano un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.</span><span class="sxs-lookup"><span data-stu-id="384dc-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="384dc-116">Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="384dc-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="384dc-117">In particolare, sono necessari i ruoli per la creazione dei destinatari di **posta** (creazione) e i **destinatari di posta** (modifica), assegnati ai gruppi di ruoli Gestione **organizzazione** (amministratori globali) e **Gestione destinatari** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="384dc-117">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="384dc-118">Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="384dc-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="384dc-119">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo articolo, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="384dc-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="384dc-120">Problemi?</span><span class="sxs-lookup"><span data-stu-id="384dc-120">Having problems?</span></span> <span data-ttu-id="384dc-121">È possibile richiedere supporto nei forum di Exchange.</span><span class="sxs-lookup"><span data-stu-id="384dc-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="384dc-122">Visitare il forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="384dc-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="384dc-123">Utilizzare l'interfaccia di amministrazione di Exchange per gestire gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="384dc-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="384dc-124">Utilizzo dell'interfaccia di amministrazione di Exchange per creare utenti di posta</span><span class="sxs-lookup"><span data-stu-id="384dc-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="384dc-125">Nell'interfaccia di amministrazione di Exchange  , accedere a \> **contatti** destinatari</span><span class="sxs-lookup"><span data-stu-id="384dc-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="384dc-126">Fare clic su **nuova** ![ nuova icona ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="384dc-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="384dc-127">Nella pagina **nuovo utente di posta elettronica** che viene visualizzata, configurare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="384dc-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="384dc-128">Sono necessarie le impostazioni contrassegnate con un <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="384dc-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="384dc-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="384dc-129">**First name**</span></span>

   - <span data-ttu-id="384dc-130">**Iniziali**: la metà iniziale della persona.</span><span class="sxs-lookup"><span data-stu-id="384dc-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="384dc-131">**Cognome**</span><span class="sxs-lookup"><span data-stu-id="384dc-131">**Last name**</span></span>

   - <span data-ttu-id="384dc-132"><sup>\*</sup>**Nome visualizzato**: per impostazione predefinita, questa casella consente di visualizzare i valori delle caselle **nome**, **iniziali** e **Cognome** .</span><span class="sxs-lookup"><span data-stu-id="384dc-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="384dc-133">È possibile accettare questo valore o modificarlo.</span><span class="sxs-lookup"><span data-stu-id="384dc-133">You can accept this value or change it.</span></span> <span data-ttu-id="384dc-134">Il valore deve essere univoco e ha una lunghezza massima di 64 caratteri.</span><span class="sxs-lookup"><span data-stu-id="384dc-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="384dc-135"><sup>\*</sup>**Alias**: immettere un alias univoco, con un massimo di 64 caratteri, per l'utente</span><span class="sxs-lookup"><span data-stu-id="384dc-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="384dc-136">**Indirizzo di posta elettronica esterno**: immettere l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="384dc-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="384dc-137">Il dominio deve essere esterno all'organizzazione basata su cloud.</span><span class="sxs-lookup"><span data-stu-id="384dc-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="384dc-138"><sup>\*</sup>**ID utente**: immettere l'account che verrà utilizzato dalla persona per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="384dc-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="384dc-139">L'ID utente è costituito da un nome utente a sinistra del simbolo @ e da un dominio sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="384dc-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="384dc-140"><sup>\*</sup>**Nuova password** e <sup>\*</sup> **Conferma password**: immettere e immettere di nuovo la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="384dc-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="384dc-141">Verificare che la password sia conforme ai requisiti di lunghezza, complessità e cronologia delle password dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="384dc-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="384dc-142">Al termine fare clic su **Salva** per creare l'utente di posta.</span><span class="sxs-lookup"><span data-stu-id="384dc-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="384dc-143">Utilizzo di EAC per modificare gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="384dc-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="384dc-144">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="384dc-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="384dc-145">Selezionare l'utente di posta che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="384dc-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="384dc-146">Nella pagina delle proprietà dell'utente di posta che si apre, fare clic su una delle seguenti schede per visualizzare o modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="384dc-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="384dc-147">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="384dc-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="384dc-148">Generale</span><span class="sxs-lookup"><span data-stu-id="384dc-148">General</span></span>

<span data-ttu-id="384dc-149">Utilizzare la scheda **generale** per visualizzare o modificare le informazioni di base sull'utente di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="384dc-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="384dc-150">**Nome**</span><span class="sxs-lookup"><span data-stu-id="384dc-150">**First name**</span></span>

- <span data-ttu-id="384dc-151">**Iniziali**</span><span class="sxs-lookup"><span data-stu-id="384dc-151">**Initials**</span></span>

- <span data-ttu-id="384dc-152">**Cognome**</span><span class="sxs-lookup"><span data-stu-id="384dc-152">**Last name**</span></span>

- <span data-ttu-id="384dc-153">**Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nelle righe a e da: nel messaggio di posta elettronica e nell'elenco dei contatti nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="384dc-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="384dc-154">Questo nome non può contenere spazi vuoti prima o dopo il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="384dc-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="384dc-155">**ID utente**: questo è l'account dell'utente in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="384dc-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="384dc-156">Non è possibile modificare questo valore qui.</span><span class="sxs-lookup"><span data-stu-id="384dc-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="384dc-157">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="384dc-157">Contact information</span></span>

<span data-ttu-id="384dc-158">Utilizzare la scheda **informazioni di contatto** per visualizzare o modificare le informazioni di contatto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="384dc-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="384dc-159">Le informazioni di questa pagina vengono visualizzate nella Rubrica.</span><span class="sxs-lookup"><span data-stu-id="384dc-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="384dc-160">**Via**</span><span class="sxs-lookup"><span data-stu-id="384dc-160">**Street**</span></span>
- <span data-ttu-id="384dc-161">**Città**</span><span class="sxs-lookup"><span data-stu-id="384dc-161">**City**</span></span>
- <span data-ttu-id="384dc-162">**Stato/Provincia**</span><span class="sxs-lookup"><span data-stu-id="384dc-162">**State/Province**</span></span>
- <span data-ttu-id="384dc-163">**CAP**</span><span class="sxs-lookup"><span data-stu-id="384dc-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="384dc-164">**Paese/area geografica**</span><span class="sxs-lookup"><span data-stu-id="384dc-164">**Country/Region**</span></span>
- <span data-ttu-id="384dc-165">**Ufficio**</span><span class="sxs-lookup"><span data-stu-id="384dc-165">**Work phone**</span></span>
- <span data-ttu-id="384dc-166">**Cellulare**</span><span class="sxs-lookup"><span data-stu-id="384dc-166">**Mobile phone**</span></span>
- <span data-ttu-id="384dc-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="384dc-167">**Fax**</span></span>
- <span data-ttu-id="384dc-168">**Altre opzioni**</span><span class="sxs-lookup"><span data-stu-id="384dc-168">**More options**</span></span>

  - <span data-ttu-id="384dc-169">**Ufficio**</span><span class="sxs-lookup"><span data-stu-id="384dc-169">**Office**</span></span>
  - <span data-ttu-id="384dc-170">**Abitazione**</span><span class="sxs-lookup"><span data-stu-id="384dc-170">**Home phone**</span></span>
  - <span data-ttu-id="384dc-171">**Pagina Web**</span><span class="sxs-lookup"><span data-stu-id="384dc-171">**Web page**</span></span>
  - <span data-ttu-id="384dc-172">**Note**</span><span class="sxs-lookup"><span data-stu-id="384dc-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="384dc-173">Organizzazione</span><span class="sxs-lookup"><span data-stu-id="384dc-173">Organization</span></span>

<span data-ttu-id="384dc-174">Utilizzare la scheda **organizzazione** per registrare informazioni dettagliate sul ruolo dell'utente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="384dc-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="384dc-175">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="384dc-175">**Title**</span></span>
- <span data-ttu-id="384dc-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="384dc-176">**Department**</span></span>
- <span data-ttu-id="384dc-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="384dc-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="384dc-178">Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere utenti di posta</span><span class="sxs-lookup"><span data-stu-id="384dc-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="384dc-179">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="384dc-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="384dc-180">Selezionare l'utente di posta che si desidera rimuovere, quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="384dc-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="384dc-181">Utilizzo di PowerShell per gestire gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="384dc-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="384dc-182">Utilizzo di PowerShell EOP autonomo per visualizzare gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="384dc-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="384dc-183">Per restituire un elenco riepilogativo di tutti gli utenti di posta elettronica in EOP PowerShell autonomo, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="384dc-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="384dc-184">Per visualizzare informazioni dettagliate su un utente di posta elettronica specifico, sostituire \<MailUserIdentity\> con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="384dc-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="384dc-185">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="384dc-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="384dc-186">Utilizzo di PowerShell EOP autonomo per creare utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="384dc-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="384dc-187">Per creare utenti di posta elettronica in EOP standalone PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="384dc-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="384dc-188">**Note**:</span><span class="sxs-lookup"><span data-stu-id="384dc-188">**Notes**:</span></span>

- <span data-ttu-id="384dc-189">Il parametro _Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="384dc-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="384dc-190">Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="384dc-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="384dc-191">Se non si utilizza il parametro _alias_ , il lato sinistro del parametro _MicrosoftOnlineServicesID_ viene utilizzato per l'alias.</span><span class="sxs-lookup"><span data-stu-id="384dc-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="384dc-192">Se non si utilizza il parametro _ExternalEmailAddress_ , viene utilizzato il valore _MicrosoftOnlineServicesID_ per l'indirizzo di posta elettronica esterno.</span><span class="sxs-lookup"><span data-stu-id="384dc-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="384dc-193">In questo esempio viene creato un utente di posta elettronica con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="384dc-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="384dc-194">Il nome è JeffreyZeng e il nome visualizzato è Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="384dc-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="384dc-195">Il nome è Jeffrey e il cognome è Zeng.</span><span class="sxs-lookup"><span data-stu-id="384dc-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="384dc-196">L'alias è jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="384dc-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="384dc-197">L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="384dc-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="384dc-198">Il nome dell'account è jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="384dc-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="384dc-199">La password è Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="384dc-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="384dc-200">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="384dc-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="384dc-201">Utilizzo di PowerShell EOP autonomo per modificare gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="384dc-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="384dc-202">Per modificare gli utenti di posta elettronica esistenti in EOP standalone PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="384dc-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="384dc-203">In questo esempio viene impostato l'indirizzo di posta elettronica esterno per Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="384dc-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="384dc-204">In questo esempio viene impostata la proprietà Company per tutti gli utenti di posta di Contoso.</span><span class="sxs-lookup"><span data-stu-id="384dc-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="384dc-205">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="384dc-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="384dc-206">Utilizzo di PowerShell EOP autonomo per rimuovere gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="384dc-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="384dc-207">Per rimuovere gli utenti di posta elettronica in EOP standalone PowerShell, sostituire \<MailUserIdentity\> con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="384dc-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="384dc-208">In questo esempio viene rimosso l'utente di posta elettronica per Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="384dc-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="384dc-209">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="384dc-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="384dc-210">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="384dc-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="384dc-211">Per verificare la corretta creazione, modifica o rimozione degli utenti di posta elettronica in EOP autonomo, utilizzare una delle seguenti procedure:</span><span class="sxs-lookup"><span data-stu-id="384dc-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="384dc-212">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="384dc-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="384dc-213">Verificare che l'utente di posta elettronica sia elencato (o non sia elencato).</span><span class="sxs-lookup"><span data-stu-id="384dc-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="384dc-214">Selezionare l'utente di posta elettronica e visualizzare le informazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) per visualizzare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="384dc-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="384dc-215">In EOP standalone PowerShell, eseguire il comando riportato di seguito per verificare che l'utente di posta elettronica sia elencato (o non sia elencato):</span><span class="sxs-lookup"><span data-stu-id="384dc-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="384dc-216">Sostituire \<MailUserIdentity\> con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire i comandi seguenti per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="384dc-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="384dc-217">Utilizzare la sincronizzazione della directory per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="384dc-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="384dc-218">In EOP autonomo, la sincronizzazione della directory è disponibile per i clienti con Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="384dc-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="384dc-219">È possibile sincronizzare tali account in Azure Active Directory (Azure AD), in cui vengono archiviate le copie degli account nel cloud.</span><span class="sxs-lookup"><span data-stu-id="384dc-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="384dc-220">Quando si sincronizzano gli account utente esistenti in Azure Active Directory, è possibile visualizzarli nel riquadro **destinatari** dell'interfaccia di amministrazione di Exchange (EAC) o in EOP standalone PowerShell.</span><span class="sxs-lookup"><span data-stu-id="384dc-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="384dc-221">**Note**:</span><span class="sxs-lookup"><span data-stu-id="384dc-221">**Notes**:</span></span>

- <span data-ttu-id="384dc-222">Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365, ma non verranno sincronizzati con Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="384dc-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="384dc-223">Tuttavia questi non verranno sincronizzati con Active Directory in locale poiché la sincronizzazione della directory sincronizza solamente i destinatari dall'Active Directory locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="384dc-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="384dc-224">Si consiglia di utilizzare la sincronizzazione della directory con le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="384dc-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="384dc-225">Elenchi di **Mittenti attendibili di Outlook e elenchi di mittenti bloccati**: quando vengono sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro di posta indesiderata nel servizio.</span><span class="sxs-lookup"><span data-stu-id="384dc-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="384dc-226">Questo consente agli utenti di gestire l'elenco dei mittenti attendibili e l'elenco dei mittenti bloccati con le singole voci del mittente e del dominio.</span><span class="sxs-lookup"><span data-stu-id="384dc-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="384dc-227">Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="384dc-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="384dc-228">**Blocking Edge basato su directory (DBEB)**: per ulteriori informazioni su DBEB, vedere [use directory based Edge Blocking to Reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="384dc-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="384dc-229">**Accesso degli utenti finali alla quarantena**: per accedere ai messaggi in quarantena, i destinatari devono disporre di un ID utente e di una password validi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="384dc-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="384dc-230">Per ulteriori informazioni sulla quarantena, vedere [trovare e rilasciare i messaggi in quarantena come utente](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="384dc-230">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="384dc-231">**Regole del flusso di posta (note anche come regole di trasporto)**: quando si utilizza la sincronizzazione della directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud ed è quindi possibile creare le regole del flusso di posta che devono essere indirizzate a utenti e/o gruppi specifici senza dover aggiungerle manualmente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="384dc-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="384dc-232">Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) tramite la sincronizzazione delle directory.</span><span class="sxs-lookup"><span data-stu-id="384dc-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="384dc-233">Ottenere le autorizzazioni necessarie e prepararsi per la sincronizzazione della directory, come descritto in [che cos'è Hybrid Identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="384dc-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="384dc-234">Sincronizzare le directory con Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="384dc-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="384dc-235">Attivare la sincronizzazione della directory come descritto in [Azure ad Connect Sync: understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="384dc-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="384dc-236">Installare e configurare un computer locale per l'esecuzione di AAD Connect come descritto in [Prerequisites for Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="384dc-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="384dc-237">[Selezionare il tipo di installazione da utilizzare per Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="384dc-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="384dc-238">Express</span><span class="sxs-lookup"><span data-stu-id="384dc-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="384dc-239">Personalizzata</span><span class="sxs-lookup"><span data-stu-id="384dc-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="384dc-240">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="384dc-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="384dc-p121">Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto.</span><span class="sxs-lookup"><span data-stu-id="384dc-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="384dc-244">Dopo aver configurato la sincronizzazione, accertarsi di verificare che AAD Connect sia sincronizzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="384dc-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="384dc-245">In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale.</span><span class="sxs-lookup"><span data-stu-id="384dc-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
