---
title: Proteggere gli account di amministratore
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Informazioni su come configurare e proteggere gli account di amministratore.
ms.openlocfilehash: 6160f7458dc9a4c343c48f07d87776529c4f1326
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594821"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="d243b-103">Proteggere gli account di amministratore</span><span class="sxs-lookup"><span data-stu-id="d243b-103">Protect your administrator accounts</span></span>

<span data-ttu-id="d243b-104">Poiché gli account di amministrazione sono dotati di privilegi elevati, sono obiettivi di valore per gli hacker e i criminali informatici.</span><span class="sxs-lookup"><span data-stu-id="d243b-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="d243b-105">In questo articolo viene descritto:</span><span class="sxs-lookup"><span data-stu-id="d243b-105">This article describes:</span></span>

- <span data-ttu-id="d243b-106">Informazioni su come configurare un account di amministratore aggiuntivo per le emergenze.</span><span class="sxs-lookup"><span data-stu-id="d243b-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="d243b-107">Come proteggere tali account.</span><span class="sxs-lookup"><span data-stu-id="d243b-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="d243b-108">Quando ti iscrivi a Microsoft 365 business e immetti le tue informazioni, diventi automaticamente l'amministratore globale. Un amministratore globale ha il controllo definitivo degli account utente e di tutte le altre impostazioni nell'interfaccia di amministrazione di Microsoft, ma esistono diversi tipi di account di amministrazione con vari gradi di accesso.</span><span class="sxs-lookup"><span data-stu-id="d243b-108">When you sign up for Microsoft 365 Business and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="d243b-109">Vedere [About admin Roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per informazioni sui diversi livelli di accesso per ogni tipo di ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d243b-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="d243b-110">Creare account di amministratore aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="d243b-110">Create additional admin accounts</span></span>

<span data-ttu-id="d243b-111">Utilizzare gli account di amministrazione solo per l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d243b-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="d243b-112">Gli amministratori devono disporre di un account utente separato per l'utilizzo regolare delle app di Office e utilizzare il proprio account amministrativo solo quando necessario per gestire gli account e i dispositivi e durante la lavorazione di altre funzioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d243b-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="d243b-113">È inoltre consigliabile rimuovere la licenza di Microsoft 365 business dagli account di amministrazione in modo che non sia necessario pagarli.</span><span class="sxs-lookup"><span data-stu-id="d243b-113">It's also a good idea to remove the Microsoft 365 Business license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="d243b-114">Sarà necessario configurare almeno un account di amministratore globale aggiuntivo per concedere l'accesso all'amministratore a un altro dipendente attendibile.</span><span class="sxs-lookup"><span data-stu-id="d243b-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="d243b-115">È inoltre possibile creare account amministratore distinti per la gestione degli utenti (questo ruolo è denominato **amministratore Gestione utenti**).</span><span class="sxs-lookup"><span data-stu-id="d243b-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="d243b-116">Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="d243b-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="d243b-117">Per creare account di amministratore aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="d243b-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="d243b-118">Passare all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Amministrazione</a> e quindi scegliere **utenti** \> **attivi utenti** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="d243b-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Scegliere utenti e quindi utenti attivi nel NAV sinistro](media/Activeusers.png)

2. <span data-ttu-id="d243b-120">Nella pagina **utenti attivi** selezionare **Aggiungi un utente** nella parte superiore della pagina e nel **nuovo pannello utente** immettere il nome e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d243b-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="d243b-121">Espandere la sezione **ruoli** e scegliere **amministratore globale** per concedere all'utente l'accesso all'amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d243b-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="d243b-122">È inoltre possibile scegliere **amministratore personalizzato** e scegliere uno qualsiasi dei ruoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="d243b-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="d243b-123">Immettere un messaggio di posta elettronica alternativo nella casella di testo **indirizzo di posta elettronica alternativo** .</span><span class="sxs-lookup"><span data-stu-id="d243b-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="d243b-124">È possibile utilizzare questo indirizzo per recuperare le informazioni sulla password se si viene bloccati. Per gli amministratori globali, verrà inviata anche un'istruzione di fatturazione a questo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d243b-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Scegliere il ruolo di amministratore](media/adminroles.png)
    
4. <span data-ttu-id="d243b-126">Nella sezione **licenze di prodotto** spostare il selettore di **Microsoft 365 business** su **disattivato** e la **licenza Crea utente senza prodotto** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="d243b-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Scegliere la licenza del prodotto](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="d243b-128">Creare un account di amministratore di emergenza</span><span class="sxs-lookup"><span data-stu-id="d243b-128">Create an emergency admin account</span></span>

<span data-ttu-id="d243b-129">È inoltre necessario creare un account di backup non configurato con l'autenticazione a più fattori (AMF), in modo da non bloccarsi accidentalmente (ad esempio, se si perde il telefono che si sta utilizzando come seconda forma di verifica).</span><span class="sxs-lookup"><span data-stu-id="d243b-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="d243b-130">Verificare che la password per l'account sia una frase o almeno 16 caratteri.</span><span class="sxs-lookup"><span data-stu-id="d243b-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="d243b-131">Questo è spesso definito come un "account break-Glass".</span><span class="sxs-lookup"><span data-stu-id="d243b-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="d243b-132">Creare un account utente autonomo</span><span class="sxs-lookup"><span data-stu-id="d243b-132">Create a user account for yourself</span></span>

<span data-ttu-id="d243b-133">Utilizzare l'account utente per partecipare alla collaborazione con l'organizzazione, inclusa la verifica della posta.</span><span class="sxs-lookup"><span data-stu-id="d243b-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="d243b-134">Questo significa che le credenziali di amministratore potrebbero essere simili a *Alice<span></span>. Chavez @Contoso. org* e l'account utente normale potrebbe essere simile a *Alice<span></span>@Contoso. com*.</span><span class="sxs-lookup"><span data-stu-id="d243b-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="d243b-135">Per creare un nuovo account utente:</span><span class="sxs-lookup"><span data-stu-id="d243b-135">To create a new user account:</span></span>
1. <span data-ttu-id="d243b-136">Passare all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Amministrazione</a> e quindi scegliere **utenti** \> **attivi utenti** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="d243b-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="d243b-137">Nella pagina **utenti attivi** selezionare **Aggiungi un utente** nella parte superiore della pagina e nel **nuovo pannello utente** immettere il nome e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d243b-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="d243b-138">Espandere la sezione **ruoli** e scegliere **utente (senza accesso amministrativo)**.</span><span class="sxs-lookup"><span data-stu-id="d243b-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="d243b-139">Nella sezione **licenze di prodotto** spostare il selettore di **Microsoft 365 business** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="d243b-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="d243b-140">Registrare ognuno di questi account per l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="d243b-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="d243b-141">Suggerimenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="d243b-141">Additional recommendations</span></span>

- <span data-ttu-id="d243b-142">Assicurarsi che anche gli account di amministrazione siano configurati per l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="d243b-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="d243b-143">Verrà illustrato come eseguire questa operazione in configurare i [criteri di accesso condizionale](m365-campaigns-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="d243b-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="d243b-144">Prima di utilizzare gli account di amministrazione, chiudere tutte le app e le sessioni del browser non correlate, compresi gli account di posta elettronica personali.</span><span class="sxs-lookup"><span data-stu-id="d243b-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="d243b-145">È inoltre possibile utilizzare le finestre del browser private o in incognito.</span><span class="sxs-lookup"><span data-stu-id="d243b-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="d243b-146">Dopo aver completato le attività amministrative, accertarsi di disconnettersi dalla sessione del browser.</span><span class="sxs-lookup"><span data-stu-id="d243b-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>