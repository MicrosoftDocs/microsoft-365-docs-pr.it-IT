---
title: Proteggere gli account di amministratore
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Informazioni su come configurare e proteggere gli account amministratore.
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398242"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="3beda-103">Proteggere gli account di amministratore</span><span class="sxs-lookup"><span data-stu-id="3beda-103">Protect your administrator accounts</span></span>

<span data-ttu-id="3beda-104">Poiché gli account amministratore dispongono di privilegi elevati, sono obiettivi preziosi per hacker e criminali informatici.</span><span class="sxs-lookup"><span data-stu-id="3beda-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="3beda-105">In questo articolo viene descritto:</span><span class="sxs-lookup"><span data-stu-id="3beda-105">This article describes:</span></span>

- <span data-ttu-id="3beda-106">Come configurare un account amministratore aggiuntivo per le emergenze.</span><span class="sxs-lookup"><span data-stu-id="3beda-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="3beda-107">Come proteggere questi account.</span><span class="sxs-lookup"><span data-stu-id="3beda-107">How to protect these accounts.</span></span>

<span data-ttu-id="3beda-108">Quando ti i sign up for Microsoft 365 e immetti le informazioni, diventi automaticamente l'amministratore globale. Un amministratore globale ha il controllo finale degli account utente e di tutte le altre impostazioni nell'interfaccia di amministrazione di Microsoft, ma esistono molti tipi diversi di account di amministratore con diversi gradi di accesso.</span><span class="sxs-lookup"><span data-stu-id="3beda-108">When you sign up for Microsoft 365 and enter your information, you automatically become the Global admin. A Global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="3beda-109">Per informazioni sui diversi livelli di accesso per ogni tipo di ruolo di amministratore, vedere about [admin roles.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="3beda-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="3beda-110">Creare altri account amministratore</span><span class="sxs-lookup"><span data-stu-id="3beda-110">Create additional admin accounts</span></span>

<span data-ttu-id="3beda-111">Utilizzare gli account amministratore solo per l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="3beda-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="3beda-112">Gli amministratori devono disporre di un account utente separato per l'uso regolare delle app Office e usare il proprio account amministrativo solo se necessario per gestire account e dispositivi e mentre lavorano su altre funzioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3beda-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="3beda-113">È anche buona idea rimuovere la licenza Microsoft 365 dagli account di amministratore in modo da non doverli pagare.</span><span class="sxs-lookup"><span data-stu-id="3beda-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="3beda-114">È necessario configurare almeno un altro account amministratore globale per concedere l'accesso di amministratore a un altro dipendente attendibile.</span><span class="sxs-lookup"><span data-stu-id="3beda-114">You'll want to set up at least one additional Global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="3beda-115">È inoltre possibile creare account amministratore distinti per la gestione degli utenti (questo ruolo è denominato **Amministratore gestione utenti**).</span><span class="sxs-lookup"><span data-stu-id="3beda-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="3beda-116">Per ulteriori informazioni, vedere [About admin roles](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="3beda-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="3beda-117">Per creare altri account amministratore:</span><span class="sxs-lookup"><span data-stu-id="3beda-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="3beda-118">Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **Utenti attivi** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="3beda-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Scegliere Utenti e quindi Utenti attivi nel riquadro di spostamento sinistro](../media/Activeusers.png)

 2. <span data-ttu-id="3beda-120">Nella pagina **Utenti attivi** seleziona **Aggiungi** utente nella parte superiore  della pagina e nel riquadro Nuovo utente immetti il nome e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="3beda-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="3beda-121">Espandere la **sezione Ruoli** e scegliere Amministratore **globale per** concedere all'utente l'accesso di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="3beda-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="3beda-122">È inoltre possibile **scegliere Amministratore personalizzato** e scegliere uno dei ruoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="3beda-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="3beda-123">Immettere un messaggio di posta elettronica alternativo nella **casella di testo Indirizzo di posta** elettronica alternativo.</span><span class="sxs-lookup"><span data-stu-id="3beda-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="3beda-124">È possibile utilizzare questo indirizzo per recuperare le informazioni sulla password se si viene bloccati. Per gli amministratori globali, verrà inviato anche un estratto conto a questo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="3beda-124">You can use this address to recover your password information if you get locked out. For Global admins, a billing statement will also be sent to this address.</span></span>

    ![Scegliere il ruolo di amministratore](../media/adminroles.png)

 4. <span data-ttu-id="3beda-126">Nella sezione **Licenze prodotto** spostare il selettore per Microsoft 365 Business **su** **Disattivato** e l'opzione Crea utente senza licenza **del** prodotto su **Su**.</span><span class="sxs-lookup"><span data-stu-id="3beda-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Scegliere la licenza del prodotto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="3beda-128">Creare un account amministratore per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="3beda-128">Create an emergency admin account</span></span>

<span data-ttu-id="3beda-129">Devi anche creare un account di backup che non sia configurato con l'autenticazione a più fattori (MFA) in modo da non bloccarti accidentalmente (ad esempio, se perdi il telefono che stai usando come seconda forma di verifica).</span><span class="sxs-lookup"><span data-stu-id="3beda-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="3beda-130">Assicurarsi che la password per questo account sia una frase o almeno 16 caratteri.</span><span class="sxs-lookup"><span data-stu-id="3beda-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="3beda-131">Questo viene spesso definito "account break-glass".</span><span class="sxs-lookup"><span data-stu-id="3beda-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="3beda-132">Creare un account utente per se stessi</span><span class="sxs-lookup"><span data-stu-id="3beda-132">Create a user account for yourself</span></span>

<span data-ttu-id="3beda-133">Utilizzare l'account utente per partecipare alla collaborazione con l'organizzazione, inclusa la verifica della posta.</span><span class="sxs-lookup"><span data-stu-id="3beda-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="3beda-134">Ciò significa che le credenziali di amministratore potrebbero essere simili  *a Alice.Chavez <span></span> @Contoso.org* e il tuo account utente normale potrebbe essere simile a *Alice <span></span> @Contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="3beda-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="3beda-135">Per creare un nuovo account utente:</span><span class="sxs-lookup"><span data-stu-id="3beda-135">To create a new user account:</span></span>

1. <span data-ttu-id="3beda-136">Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **Utenti attivi** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="3beda-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="3beda-137">Nella pagina **Utenti attivi** seleziona **Aggiungi** utente nella parte superiore  della pagina e nel riquadro Nuovo utente immetti il nome e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="3beda-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="3beda-138">Espandere la **sezione** Ruoli e scegliere **Utente (nessun accesso amministrativo)**.</span><span class="sxs-lookup"><span data-stu-id="3beda-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="3beda-139">Nella sezione **Licenze prodotto** spostare il selettore **per** Microsoft 365 Business su **Su**.</span><span class="sxs-lookup"><span data-stu-id="3beda-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="turn-on-security-defaults"></a><span data-ttu-id="3beda-140">Attivare le impostazioni predefinite di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3beda-140">Turn on security defaults</span></span>

<span data-ttu-id="3beda-141">Le impostazioni predefinite di sicurezza consentono di proteggere l'organizzazione da attacchi correlati all'identità fornendo impostazioni di sicurezza preconfigurate gestite da Microsoft per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3beda-141">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="3beda-142">Queste impostazioni includono l'abilitazione dell'autenticazione a più fattori (MFA) per tutti gli amministratori e gli account utente.</span><span class="sxs-lookup"><span data-stu-id="3beda-142">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="3beda-143">Per ulteriori informazioni sulle impostazioni predefinite di sicurezza e per informazioni su come abilitarle, vedere [Attivare le impostazioni predefinite di sicurezza.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="3beda-143">For more information about security defaults and to learn how to enable them on, see [Turn on security defaults](m365-campaigns-conditional-access.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="3beda-144">Suggerimenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="3beda-144">Additional recommendations</span></span>

- <span data-ttu-id="3beda-145">Prima di usare gli account di amministratore, chiudi tutte le app e le sessioni del browser non correlate, inclusi gli account di posta elettronica personali.</span><span class="sxs-lookup"><span data-stu-id="3beda-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="3beda-146">Puoi anche usare le finestre del browser private o in incognito.</span><span class="sxs-lookup"><span data-stu-id="3beda-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="3beda-147">Dopo aver completato le attività di amministrazione, assicurati di disconnettersi dalla sessione del browser.</span><span class="sxs-lookup"><span data-stu-id="3beda-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
