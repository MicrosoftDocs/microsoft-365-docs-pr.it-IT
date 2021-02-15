---
title: Attivare o disattivare Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Informazioni su come accedere a Microsoft Bookings in Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126592"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="3f4c9-103">Attivare o disattivare Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="3f4c9-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="3f4c9-104">Bookings può essere attivato o disattivato per l'intera organizzazione o per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="3f4c9-105">Quando si attiva Bookings per gli utenti, questi possono creare una pagina prenotazioni, creare un calendario e consentire ad altri utenti di prenotare tempo con loro.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="3f4c9-106">I controlli di amministrazione descritti in queste sezioni non sono disponibili per i clienti di Office 365 Gestito da 21Vianet (Cina).</span><span class="sxs-lookup"><span data-stu-id="3f4c9-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="3f4c9-107">Attivare o disattivare Bookings per l'organizzazione tramite l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f4c9-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="3f4c9-108">Accedere all'interfaccia di amministrazione di Microsoft 365 come amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="3f4c9-109">Nell'interfaccia di amministrazione passare a  **Impostazioni**   \> **organizzazione e** selezionare **Prenotazioni.**</span><span class="sxs-lookup"><span data-stu-id="3f4c9-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="3f4c9-110">Selezionare la casella di controllo Consenti **all'organizzazione di usare Bookings** per abilitare o disabilitare Prenotazioni per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f4c9-111">La disattivazione di Bookings disabiliterà tutti gli accessi al servizio, inclusa la creazione e la gestione delle pagine di Bookings.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="3f4c9-112">Selezionare **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="3f4c9-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="3f4c9-113">Attivare o disattivare Prenotazioni per l'organizzazione tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f4c9-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="3f4c9-114">Per attivare o disattivare Bookings per l'organizzazione utilizzando il cmdlet [PowerShell Set-OrganizationConfig,](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3f4c9-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="3f4c9-115">Attivare o disattivare Prenotazioni per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="3f4c9-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="3f4c9-116">È possibile disabilitare Prenotazioni per singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="3f4c9-117">Passare all'interfaccia di amministrazione di Microsoft 365, quindi selezionare **Utenti** \> **attivi.**</span><span class="sxs-lookup"><span data-stu-id="3f4c9-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="3f4c9-118">Selezionare l'utente desiderato, quindi **selezionare Licenze e app.**</span><span class="sxs-lookup"><span data-stu-id="3f4c9-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="3f4c9-119">Espandi **App** e deseleziona la casella di controllo per Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="3f4c9-120">Richiedere l'approvazione del personale prima di condividere le informazioni sulla disponibilità</span><span class="sxs-lookup"><span data-stu-id="3f4c9-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="3f4c9-121">Gli amministratori possono richiedere ai dipendenti dell'organizzazione di acconsentire esplicitamente prima che le informazioni sulla disponibilità siano condivise tramite Bookings e prima che possano essere prenotabili tramite una pagina di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="3f4c9-122">Questa impostazione è disponibile nell'interfaccia di  amministrazione di Microsoft 365 in \> **Impostazioni** \> **Prenotazioni.**</span><span class="sxs-lookup"><span data-stu-id="3f4c9-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="3f4c9-123">Quando questa impostazione è abilitata, i dipendenti aggiunti come personale nei calendari di prenotazione troveranno un collegamento Approva/Rifiuta nella notifica tramite posta elettronica che ricevono.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="3f4c9-124">Questa funzionalità è in fase di implementazione graduale a livello mondiale per i clienti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="3f4c9-125">Se questa opzione non viene visualizzata nell'interfaccia di amministrazione di Microsoft 365, tornare a breve.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="3f4c9-126">Bloccare le opzioni di condivisione social network</span><span class="sxs-lookup"><span data-stu-id="3f4c9-126">Block social sharing options</span></span>

<span data-ttu-id="3f4c9-127">Gli amministratori possono controllare la modalità di condivisione delle pagine di prenotazione nei social network.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="3f4c9-128">Questa impostazione è disponibile nell'interfaccia di  amministrazione di Microsoft 365 in \> **Impostazioni** \> **Prenotazioni.**</span><span class="sxs-lookup"><span data-stu-id="3f4c9-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="3f4c9-129">Questa funzionalità è in fase di implementazione graduale a livello mondiale per i clienti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="3f4c9-130">Se questa opzione non viene visualizzata nell'interfaccia di amministrazione di Microsoft 365, tornare a breve.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="3f4c9-131">Consenti solo agli utenti selezionati di creare calendari di Bookings</span><span class="sxs-lookup"><span data-stu-id="3f4c9-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="3f4c9-132">Utilizzando le restrizioni dei criteri, è possibile impedire agli utenti con licenza di creare calendari di Bookings.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="3f4c9-133">È innanzitutto necessario abilitare Bookings per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="3f4c9-134">Tutti gli utenti dell'organizzazione avranno licenze bookings, ma solo quelli inclusi nel criterio possono creare calendari di Bookings e avere il controllo completo su chi può accedere ai calendari creati.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="3f4c9-135">Gli utenti inclusi in questo criterio possono creare nuovi calendari di Bookings e possono essere aggiunti come membri del personale in qualsiasi capacità (incluso il ruolo di amministratore) ai calendari di Bookings esistenti.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="3f4c9-136">Gli utenti che non sono inclusi in questo criterio non potranno creare nuovi calendari di Bookings e, se tentano di farlo, riceveranno un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="3f4c9-137">È necessario eseguire i seguenti comandi utilizzando PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="3f4c9-138">Per ulteriori informazioni sull'esecuzione dei cmdlet di Exchange Online, vedere [Connettersi a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f4c9-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f4c9-139">I passaggi seguenti presuppongono che non siano stati creati altri criteri cassetta postale di Outlook Web App (OWA) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="3f4c9-140">Creare un nuovo criterio cassetta postale per gli utenti a cui consentire di creare calendari di Bookings.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="3f4c9-141">La creazione del calendario di Bookings è consentita per impostazione predefinita dai nuovi criteri cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="3f4c9-142">Per ulteriori informazioni, vedere [New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="3f4c9-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="3f4c9-143">Assegnare questo criterio agli utenti rilevanti eseguendo questo comando per ogni utente a cui si desidera concedere l'autorizzazione per la creazione di calendari di Bookings.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="3f4c9-144">Per ulteriori informazioni, vedere [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="3f4c9-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="3f4c9-145">Facoltativo: eseguire questo comando se si desidera disabilitare Prenotazioni per tutti gli altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f4c9-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="3f4c9-146">Per ulteriori informazioni, vedere [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="3f4c9-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="3f4c9-147">Per ulteriori informazioni sui criteri OWA cassetta postale, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="3f4c9-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="3f4c9-148">Creare un criterio cassetta postale di Outlook sul Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f4c9-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="3f4c9-149">Applicare o rimuovere un criterio cassetta postale di Outlook sul Web su una cassetta postale in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f4c9-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
