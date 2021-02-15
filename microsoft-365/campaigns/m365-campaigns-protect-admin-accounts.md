---
title: Proteggere gli account amministratore
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Informazioni su come configurare e proteggere gli account amministratore.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044489"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="51865-103">Proteggere gli account amministratore</span><span class="sxs-lookup"><span data-stu-id="51865-103">Protect your administrator accounts</span></span>

<span data-ttu-id="51865-104">Poiché gli account amministratore dispongono di privilegi elevati, sono obiettivi importanti per hacker e cyber-criminali.</span><span class="sxs-lookup"><span data-stu-id="51865-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="51865-105">In questo articolo viene descritto:</span><span class="sxs-lookup"><span data-stu-id="51865-105">This article describes:</span></span>

- <span data-ttu-id="51865-106">Come configurare un account amministratore aggiuntivo per le emergenze.</span><span class="sxs-lookup"><span data-stu-id="51865-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="51865-107">Come proteggere questi account.</span><span class="sxs-lookup"><span data-stu-id="51865-107">How to protect these accounts.</span></span>

<span data-ttu-id="51865-108">Quando si effettua l'iscrizione a Microsoft 365 e si immettono le informazioni, si diventa automaticamente l'amministratore globale. Un amministratore globale ha il controllo finale degli account utente e di tutte le altre impostazioni nell'interfaccia di amministrazione di Microsoft, ma esistono molti tipi diversi di account amministratore con diversi gradi di accesso.</span><span class="sxs-lookup"><span data-stu-id="51865-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="51865-109">Per [informazioni sui diversi](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) livelli di accesso per ogni tipo di ruolo di amministratore, vedere i ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="51865-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="51865-110">Creare account amministratore aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="51865-110">Create additional admin accounts</span></span>

<span data-ttu-id="51865-111">Usa gli account amministratore solo per l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="51865-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="51865-112">Gli amministratori devono disporre di un account utente separato per l'uso regolare delle app di Office e utilizzare il proprio account amministrativo solo se necessario per gestire account e dispositivi e durante l'utilizzo di altre funzioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="51865-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="51865-113">È anche una buona idea rimuovere la licenza di Microsoft 365 dagli account di amministratore in modo da non doverli pagare.</span><span class="sxs-lookup"><span data-stu-id="51865-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="51865-114">È necessario configurare almeno un account amministratore globale aggiuntivo per concedere l'accesso di amministratore a un altro dipendente attendibile.</span><span class="sxs-lookup"><span data-stu-id="51865-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="51865-115">È inoltre possibile creare account amministratore separati per la gestione degli utenti (questo ruolo è denominato **Amministratore gestione utenti).**</span><span class="sxs-lookup"><span data-stu-id="51865-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="51865-116">Per ulteriori informazioni, vedere [sui ruoli di amministratore.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="51865-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="51865-117">Per creare altri account amministratore:</span><span class="sxs-lookup"><span data-stu-id="51865-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="51865-118">Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **attivi nel** riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="51865-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. <span data-ttu-id="51865-120">Nella pagina **Utenti attivi** selezionare Aggiungi utente nella parte superiore  della pagina e nel riquadro Nuovo utente immettere il nome e altre informazioni. </span><span class="sxs-lookup"><span data-stu-id="51865-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="51865-121">Espandere la **sezione Ruoli** e scegliere Amministratore **globale per** concedere all'utente l'accesso come amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="51865-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="51865-122">È inoltre possibile scegliere **Amministratore personalizzato** e scegliere uno dei ruoli visualizzati.</span><span class="sxs-lookup"><span data-stu-id="51865-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="51865-123">Immettere un messaggio di posta elettronica alternativo nella **casella di testo Indirizzo di posta** elettronica alternativo.</span><span class="sxs-lookup"><span data-stu-id="51865-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="51865-124">È possibile utilizzare questo indirizzo per recuperare le informazioni sulla password in caso di blocco. Per gli amministratori globali, a questo indirizzo verrà inviato anche un estratto conto.</span><span class="sxs-lookup"><span data-stu-id="51865-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Scegliere il ruolo di amministratore](../media/adminroles.png)

 4. <span data-ttu-id="51865-126">Nella sezione **Licenze di prodotto** spostare il selettore per Microsoft **365 Business** su **Disattivato** e l'opzione Crea utente senza licenza **del** prodotto su **On.**</span><span class="sxs-lookup"><span data-stu-id="51865-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Scegliere la licenza del prodotto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="51865-128">Creare un account amministratore per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="51865-128">Create an emergency admin account</span></span>

<span data-ttu-id="51865-129">Devi anche creare un account di backup non configurato con l'autenticazione a più fattori (MFA) in modo da non bloccarti accidentalmente (ad esempio, se perdi il telefono che stai usando come seconda forma di verifica).</span><span class="sxs-lookup"><span data-stu-id="51865-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="51865-130">Verificare che la password per questo account sia una frase o una lunghezza di almeno 16 caratteri.</span><span class="sxs-lookup"><span data-stu-id="51865-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="51865-131">Questo account viene spesso definito "account break-glass".</span><span class="sxs-lookup"><span data-stu-id="51865-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="51865-132">Creare un account utente per se stessi</span><span class="sxs-lookup"><span data-stu-id="51865-132">Create a user account for yourself</span></span>

<span data-ttu-id="51865-133">Utilizzare l'account utente per partecipare alla collaborazione con l'organizzazione, inclusa la verifica della posta.</span><span class="sxs-lookup"><span data-stu-id="51865-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="51865-134">Ciò significa che le credenziali di amministratore potrebbero essere simili ad *Alice.Chavez <span></span> @Contoso.org* e il normale account utente potrebbe essere simile ad *Alice <span></span> @Contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="51865-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="51865-135">Per creare un nuovo account utente:</span><span class="sxs-lookup"><span data-stu-id="51865-135">To create a new user account:</span></span>

1. <span data-ttu-id="51865-136">Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **attivi nel** riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="51865-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="51865-137">Nella pagina **Utenti attivi** selezionare Aggiungi utente nella parte superiore  della pagina e nel riquadro Nuovo utente immettere il nome e altre informazioni. </span><span class="sxs-lookup"><span data-stu-id="51865-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="51865-138">Espandere la **sezione Ruoli** e scegliere **Utente (nessun accesso amministrativo)**.</span><span class="sxs-lookup"><span data-stu-id="51865-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="51865-139">Nella sezione **Licenze di prodotto** spostare il selettore per Microsoft **365 Business** su **On.**</span><span class="sxs-lookup"><span data-stu-id="51865-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="51865-140">Registrare ognuno di questi account per l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="51865-140">Register each of these accounts for multi-factor authentication</span></span>

<span data-ttu-id="51865-141">Verificare che questi account utilizzino [l'autenticazione a più fattori.](m365-campaigns-multifactor-authenication.md)</span><span class="sxs-lookup"><span data-stu-id="51865-141">Make sure these accounts are using [multifactor authentication](m365-campaigns-multifactor-authenication.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="51865-142">Consigli aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="51865-142">Additional recommendations</span></span>

- <span data-ttu-id="51865-143">Assicurarsi che gli account amministratore siano impostati anche per l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="51865-143">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="51865-144">Verrà illustrato come eseguire questa operazione in Configurare [i criteri di accesso condizionale.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="51865-144">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="51865-145">Prima di usare gli account amministratore, chiudi tutte le sessioni e le app del browser non correlate, inclusi gli account di posta elettronica personali.</span><span class="sxs-lookup"><span data-stu-id="51865-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="51865-146">Puoi anche usare le finestre del browser private o in incognito.</span><span class="sxs-lookup"><span data-stu-id="51865-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="51865-147">Dopo aver completato le attività di amministrazione, assicurarsi di disconnettersi dalla sessione del browser.</span><span class="sxs-lookup"><span data-stu-id="51865-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
