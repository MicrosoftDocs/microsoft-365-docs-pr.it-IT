---
title: Configurare i criteri di accesso condizionale
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come richiedere il master e configurare i criteri di accesso condizionale per Microsoft 365 for business.
ms.openlocfilehash: 08a77615d6801eef52465c450c2559a9d786befb
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558275"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="0a039-103">Richiedere l'autenticazione a più fattori e configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="0a039-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="0a039-104">È possibile proteggere l'accesso ai dati con l'autenticazione a più fattori e i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="0a039-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="0a039-105">Questi aggiungono ulteriore sicurezza sostanziale.</span><span class="sxs-lookup"><span data-stu-id="0a039-105">These add substantial additional security.</span></span> <span data-ttu-id="0a039-106">Microsoft fornisce una serie di criteri di accesso condizionale previsti che sono consigliati per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="0a039-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="0a039-107">I criteri di base sono un insieme di criteri predefiniti che consentono di proteggere le organizzazioni da numerosi attacchi comuni.</span><span class="sxs-lookup"><span data-stu-id="0a039-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="0a039-108">Questi attacchi comuni possono includere lo spray per la password, la riproduzione e il phishing.</span><span class="sxs-lookup"><span data-stu-id="0a039-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="0a039-109">Questi criteri richiedono agli amministratori e agli utenti di immettere una seconda forma di autenticazione (chiamata autenticazione a più fattori o AMF) quando vengono soddisfatte determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="0a039-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="0a039-110">Ad esempio, se un utente dell'organizzazione tenta di accedere a Microsoft 365 da un paese diverso o da un dispositivo sconosciuto, l'accesso potrebbe essere considerato rischioso.</span><span class="sxs-lookup"><span data-stu-id="0a039-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="0a039-111">L'utente deve fornire una forma supplementare di autenticazione, ad esempio un'impronta digitale o un codice, per dimostrare la propria identità.</span><span class="sxs-lookup"><span data-stu-id="0a039-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="0a039-112">Attualmente, i criteri di base includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0a039-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="0a039-113">Configurata nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="0a039-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="0a039-114">**Richiede** l'autenticazione a più fattori per i ruoli di amministratore più privilegiati, incluso l'amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0a039-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="0a039-115">**Protezione dell'utente finale** : richiede l'autenticazione a più fattori per gli utenti solo quando un accesso è rischioso.</span><span class="sxs-lookup"><span data-stu-id="0a039-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="0a039-116">Configurare il portale di Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="0a039-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="0a039-117">**Blocca l'autenticazione legacy** : le app client meno recenti e alcune nuove app non utilizzano più nuovi protocolli di autenticazione più sicuri.</span><span class="sxs-lookup"><span data-stu-id="0a039-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="0a039-118">Queste app precedenti possono ignorare i criteri di accesso condizionale e ottenere un accesso non autorizzato all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0a039-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="0a039-119">Questo criterio blocca l'accesso da client che non supportano l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="0a039-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="0a039-120">**Richiede** l'autenticazione a più fattori per l'accesso agli strumenti di gestione, incluso il portale di Azure (in cui vengono configurati i criteri di base).</span><span class="sxs-lookup"><span data-stu-id="0a039-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="0a039-121">Microsoft consiglia di abilitare tutti questi criteri di base.</span><span class="sxs-lookup"><span data-stu-id="0a039-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="0a039-122">Dopo aver abilitato questi criteri, agli amministratori e agli utenti verrà richiesto di registrarsi per l'autenticazione a più fattori di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0a039-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multi-Factor authentication.</span></span>

<span data-ttu-id="0a039-123">Per ulteriori informazioni su questi criteri, vedere [What are Baseline Policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="0a039-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="0a039-124">Richiedere la MFA</span><span class="sxs-lookup"><span data-stu-id="0a039-124">Require MFA</span></span>

<span data-ttu-id="0a039-125">Per richiedere che tutti gli utenti eseguano l'accesso con una seconda forma di ID:</span><span class="sxs-lookup"><span data-stu-id="0a039-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="0a039-126">Accedere all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> e scegliere **Setup**.</span><span class="sxs-lookup"><span data-stu-id="0a039-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="0a039-127">Nella pagina configurazione scegliere **Visualizza** nella scheda **Rendi più sicura** .</span><span class="sxs-lookup"><span data-stu-id="0a039-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Rendere più sicura la scheda di accesso.](../media/setupmfa.png)
3. <span data-ttu-id="0a039-129">Nella pagina make Sign-in More Secure scegliere **Get Started**.</span><span class="sxs-lookup"><span data-stu-id="0a039-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="0a039-130">Nel riquadro di sicurezza di accesso rinforzato selezionare le caselle di controllo accanto a **Richiedi autenticazione a più fattori per gli amministratori** e **richiedere agli utenti di registrarsi per l'autenticazione a più fattori e bloccare l'accesso se viene rilevato un rischio**.</span><span class="sxs-lookup"><span data-stu-id="0a039-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="0a039-131">Assicurarsi di escludere l'account di amministratore [Emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) o "Break-Glass" dal requisito AMF nella casella **Trova utenti** .</span><span class="sxs-lookup"><span data-stu-id="0a039-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Rinforzare la pagina di sicurezza sing-in.](../media/requiremfa.png)

5. <span data-ttu-id="0a039-133">Scegliere **create Policy** nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="0a039-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="0a039-134">Impostare i criteri di base</span><span class="sxs-lookup"><span data-stu-id="0a039-134">Set up baseline policies</span></span>

1. <span data-ttu-id="0a039-135">Andare al [portale di Azure](https://portal.azure.com), quindi passare a accesso condizionale di **Azure Active Directory** \> **Conditional Access** per creare un **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="0a039-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="0a039-136">Per ogni criterio, vedere le istruzioni specifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a039-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="0a039-137">Richiedi l'autenticazione a più fattori per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="0a039-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="0a039-138">Richiedi l'autenticazione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="0a039-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="0a039-139">Bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="0a039-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="0a039-140">Richiedere l'autenticazione dell'AMF per la gestione dei servizi</span><span class="sxs-lookup"><span data-stu-id="0a039-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)
    
> [!NOTE]
> <span data-ttu-id="0a039-141">I criteri di anteprima non esistono più e gli utenti dovranno creare i propri criteri.</span><span class="sxs-lookup"><span data-stu-id="0a039-141">Preview policies no longer exist and users will need to create their own policies.</span></span>


<span data-ttu-id="0a039-142">È possibile configurare criteri aggiuntivi, ad esempio per le app client approvate.</span><span class="sxs-lookup"><span data-stu-id="0a039-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="0a039-143">Per ulteriori informazioni, vedere la [documentazione relativa all'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="0a039-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
