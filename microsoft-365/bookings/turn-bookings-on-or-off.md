---
title: Attivazione o disattivazione delle prenotazioni Microsoft
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Informazioni su come accedere a Microsoft bookings in Microsoft 365.
ms.openlocfilehash: 815aa3a859db15364aa18d3550001a28d085b711
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419733"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="dd76b-103">Attivazione o disattivazione delle prenotazioni Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd76b-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="dd76b-104">Le prenotazioni possono essere attivate o disattivate per l'intera organizzazione o per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="dd76b-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="dd76b-105">Quando si attivano le prenotazioni per gli utenti, è possibile creare una pagina di prenotazione, creare un calendario e consentire ad altre persone di prenotare tempo con loro.</span><span class="sxs-lookup"><span data-stu-id="dd76b-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="dd76b-106">I controlli di amministratore descritti in queste sezioni non sono disponibili per Office 365 gestito da clienti di 21Vianet (Cina).</span><span class="sxs-lookup"><span data-stu-id="dd76b-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="dd76b-107">Attivazione o disattivazione delle prenotazioni per la propria organizzazione tramite l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd76b-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="dd76b-108">Accedere all'interfaccia di amministrazione di Microsoft 365 come amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="dd76b-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="dd76b-109">Nell'interfaccia di amministrazione, andare a impostazioni **Impostazioni**   \> **Settings** e selezionare **prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="dd76b-109">In the admin center, go to **Settings** \> **Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="dd76b-110">Selezionare la casella di controllo per **consentire all'organizzazione di utilizzare le prenotazioni** per abilitare o disabilitare le prenotazioni per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dd76b-111">La disattivazione delle prenotazioni disattiverà tutti gli accessi al servizio, inclusa la creazione e la gestione delle pagine di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="dd76b-112">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="dd76b-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="dd76b-113">Attivazione o disattivazione delle prenotazioni per la propria organizzazione tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd76b-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="dd76b-114">Per abilitare o disabilitare le prenotazioni per l'organizzazione utilizzando il cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)di PowerShell, [connettersi a PowerShell di Exchange Online]() ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dd76b-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell]() and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="dd76b-115">Attivazione o disattivazione delle prenotazioni per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="dd76b-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="dd76b-116">È possibile disabilitare le prenotazioni per singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="dd76b-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="dd76b-117">Accedere all'interfaccia di amministrazione di Microsoft 365, quindi **selezionare utenti** \> **attivi**.</span><span class="sxs-lookup"><span data-stu-id="dd76b-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="dd76b-118">Selezionare l'utente desiderato, quindi selezionare **licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="dd76b-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="dd76b-119">Espandi le **app** e deseleziona la casella di controllo per Microsoft bookings.</span><span class="sxs-lookup"><span data-stu-id="dd76b-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="dd76b-120">Richiedi approvazione del personale prima della condivisione delle informazioni sulla disponibilità</span><span class="sxs-lookup"><span data-stu-id="dd76b-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="dd76b-121">Gli amministratori possono richiedere ai dipendenti dell'organizzazione l'opt-in prima che le informazioni sulla disponibilità siano condivise tramite le prenotazioni e prima che possano essere prenotabili tramite una pagina di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="dd76b-122">Questa impostazione è disponibile nell'interfaccia di amministrazione di Microsoft 365 **Settings** nelle \> **Settings** \> **prenotazioni**delle impostazioni delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dd76b-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="dd76b-123">Quando questa impostazione è abilitata, i dipendenti aggiunti come personale nei calendari di prenotazione troveranno un collegamento Approva/Rifiuta nella notifica di posta elettronica che ricevono.</span><span class="sxs-lookup"><span data-stu-id="dd76b-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="dd76b-124">Questa funzionalità è gradualmente distribuita a livello mondiale nei clienti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd76b-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="dd76b-125">Se questa opzione non è disponibile nell'interfaccia di amministrazione di Microsoft 365, eseguire il controllo di nuovo a breve.</span><span class="sxs-lookup"><span data-stu-id="dd76b-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="dd76b-126">Bloccare le opzioni di condivisione sociale</span><span class="sxs-lookup"><span data-stu-id="dd76b-126">Block social sharing options</span></span>

<span data-ttu-id="dd76b-127">Gli amministratori possono controllare il modo in cui le pagine di prenotazione sono condivise sui social network.</span><span class="sxs-lookup"><span data-stu-id="dd76b-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="dd76b-128">Questa impostazione è disponibile nell'interfaccia di amministrazione di Microsoft 365 **Settings** nelle \> **Settings** \> **prenotazioni**delle impostazioni delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dd76b-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="dd76b-129">Questa funzionalità è gradualmente distribuita a livello mondiale nei clienti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd76b-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="dd76b-130">Se questa opzione non è disponibile nell'interfaccia di amministrazione di Microsoft 365, eseguire il controllo di nuovo a breve.</span><span class="sxs-lookup"><span data-stu-id="dd76b-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="dd76b-131">Consenti solo agli utenti selezionati di creare calendari di prenotazione</span><span class="sxs-lookup"><span data-stu-id="dd76b-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="dd76b-132">Se si utilizzano restrizioni ai criteri, è possibile limitare gli utenti autorizzati a creare calendari di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="dd76b-133">Prima di tutto, è necessario abilitare le prenotazioni per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="dd76b-134">Tutti gli utenti dell'organizzazione disporranno delle licenze di prenotazione, ma solo quelle incluse nel criterio possono creare calendari di prenotazione e avere il controllo completo su chi può accedere ai calendari creati.</span><span class="sxs-lookup"><span data-stu-id="dd76b-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="dd76b-135">Gli utenti inclusi in questo criterio possono creare nuovi calendari di prenotazione e possono essere aggiunti come membri del personale in qualsiasi capacità (incluso il ruolo di amministratore) ai calendari delle prenotazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="dd76b-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="dd76b-136">Gli utenti che non sono inclusi in questo criterio non saranno in grado di creare nuovi calendari di prenotazione e riceveranno un messaggio di errore se si tenta di eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="dd76b-137">È necessario eseguire i comandi seguenti usando PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd76b-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="dd76b-138">Per ulteriori informazioni sull'esecuzione dei cmdlet di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="dd76b-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd76b-139">Nella procedura riportata di seguito si presuppone che non siano stati creati altri criteri cassetta postale di Outlook Web App (OWA) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="dd76b-140">Creare un nuovo criterio cassetta postale per gli utenti che devono essere autorizzati a creare calendari di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="dd76b-141">(La creazione del calendario delle prenotazioni è consentita per impostazione predefinita dai nuovi criteri cassetta postale).</span><span class="sxs-lookup"><span data-stu-id="dd76b-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="dd76b-142">Per ulteriori informazioni, vedere [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="dd76b-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="dd76b-143">Assegnare questo criterio agli utenti rilevanti eseguendo questo comando per ogni utente che si desidera concedere l'autorizzazione per creare calendari di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="dd76b-144">Per ulteriori informazioni, vedere [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="dd76b-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="dd76b-145">Facoltativo: eseguire questo comando se si desidera disabilitare le prenotazioni per tutti gli altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd76b-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="dd76b-146">Per ulteriori informazioni, vedere [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="dd76b-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="dd76b-147">Per ulteriori informazioni sui criteri cassetta postale di OWA, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd76b-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="dd76b-148">Creare un criterio cassetta postale di Outlook sul Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd76b-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="dd76b-149">Applicare o rimuovere un criterio cassetta postale di Outlook sul Web in una cassetta postale in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd76b-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)