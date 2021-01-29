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
description: Informazioni su come richiedere l'autenticazione a più fattori e configurare i criteri di accesso condizionale per Microsoft 365 per le aziende.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044501"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="93380-103">Richiedere l'autenticazione a più fattori e configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="93380-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="93380-104">È possibile proteggere l'accesso ai dati con l'autenticazione a più fattori e i criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="93380-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="93380-105">Questi elementi aggiungono una sicurezza aggiuntiva sostanziale.</span><span class="sxs-lookup"><span data-stu-id="93380-105">These add substantial additional security.</span></span> <span data-ttu-id="93380-106">Microsoft fornisce un set di criteri di accesso condizionale di base consigliati per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="93380-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="93380-107">I criteri di base sono un insieme di criteri predefiniti che consentono di proteggere le organizzazioni da molti attacchi comuni.</span><span class="sxs-lookup"><span data-stu-id="93380-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="93380-108">Questi attacchi comuni possono includere password spray, replay e phishing.</span><span class="sxs-lookup"><span data-stu-id="93380-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="93380-109">Questi criteri richiedono ad amministratori e utenti di immettere una seconda forma di autenticazione (denominata autenticazione a più fattori o MFA) in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="93380-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="93380-110">Ad esempio, se un utente dell'organizzazione tenta di accedere a Microsoft 365 da un paese diverso o da un dispositivo sconosciuto, l'accesso potrebbe essere considerato rischioso.</span><span class="sxs-lookup"><span data-stu-id="93380-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="93380-111">L'utente deve fornire una forma aggiuntiva di autenticazione (ad esempio un'impronta digitale o un codice) per dimostrare la propria identità.</span><span class="sxs-lookup"><span data-stu-id="93380-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="93380-112">Attualmente, i criteri di base includono i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="93380-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="93380-113">Configurare nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="93380-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="93380-114">**Richiedi autenticazione a più** fattori per gli amministratori: richiede l'autenticazione a più fattori per i ruoli di amministratore con privilegi più elevati, incluso l'amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="93380-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="93380-115">**Protezione dell'utente finale:** richiede l'autenticazione a più fattori per gli utenti solo quando un accesso è rischioso.</span><span class="sxs-lookup"><span data-stu-id="93380-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="93380-116">Configurare nel portale di Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="93380-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="93380-117">**Bloccare l'autenticazione legacy:** le app client meno recenti e alcune nuove app non usano protocolli di autenticazione più recenti e più sicuri.</span><span class="sxs-lookup"><span data-stu-id="93380-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="93380-118">Queste app precedenti possono ignorare i criteri di accesso condizionale e ottenere l'accesso non autorizzato all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="93380-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="93380-119">Questo criterio blocca l'accesso dai client che non supportano l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="93380-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="93380-120">**Richiedi L'autenticazione a più** fattori per la gestione dei servizi: richiede l'autenticazione a più fattori per l'accesso agli strumenti di gestione, incluso il portale di Azure (in cui è possibile configurare i criteri di base).</span><span class="sxs-lookup"><span data-stu-id="93380-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="93380-121">È consigliabile abilitare tutti questi criteri di base.</span><span class="sxs-lookup"><span data-stu-id="93380-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="93380-122">Dopo aver abilitato questi criteri, agli amministratori e agli utenti verrà richiesto di registrarsi per l'autenticazione a più fattori di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="93380-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="93380-123">Per ulteriori informazioni su questi criteri, vedere [Che cosa sono i criteri di base?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="93380-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="93380-124">Richiedere la MFA</span><span class="sxs-lookup"><span data-stu-id="93380-124">Require MFA</span></span>

<span data-ttu-id="93380-125">Per richiedere a tutti gli utenti di accedere con un secondo formato di ID:</span><span class="sxs-lookup"><span data-stu-id="93380-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="93380-126">Accedere all'interfaccia di amministrazione e <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> scegliere **Installazione.**</span><span class="sxs-lookup"><span data-stu-id="93380-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="93380-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span><span class="sxs-lookup"><span data-stu-id="93380-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Rendere l'accesso più sicuro.](../media/setupmfa.png)
3. <span data-ttu-id="93380-129">Nella pagina Rendi più sicuro l'accesso scegliere **Introduzione.**</span><span class="sxs-lookup"><span data-stu-id="93380-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="93380-130">Nel riquadro Rafforzare la sicurezza di accesso selezionare  le caselle di controllo accanto a Richiedi autenticazione a più fattori per gli amministratori e Richiedi agli utenti di registrarsi per l'autenticazione a più fattori e bloccare l'accesso se vengono rilevati **rischi.**</span><span class="sxs-lookup"><span data-stu-id="93380-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="93380-131">Assicurati di escludere l'account [amministratore](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) di emergenza o "break-glass" dal requisito MFA nella **casella Trova** utenti.</span><span class="sxs-lookup"><span data-stu-id="93380-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![Pagina Rafforzare la sicurezza del componente aggiuntivo.](../media/requiremfa.png)

5. <span data-ttu-id="93380-133">Scegliere **Crea criterio** nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="93380-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="93380-134">Configurare i criteri di base</span><span class="sxs-lookup"><span data-stu-id="93380-134">Set up baseline policies</span></span>

1. <span data-ttu-id="93380-135">Passare al portale [di Azure](https://portal.azure.com)e quindi passare ad Accesso condizionale di Azure **Active Directory** per creare un \>  nuovo **criterio.**</span><span class="sxs-lookup"><span data-stu-id="93380-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="93380-136">Per ogni criterio, vedere le istruzioni specifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="93380-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="93380-137">Richiedere l'autenticazione a più fattori per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="93380-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="93380-138">Richiedere l'autenticazione a più fattori per gli utenti</span><span class="sxs-lookup"><span data-stu-id="93380-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="93380-139">Bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="93380-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="93380-140">Richiedere l'autenticazione a più fattori per la gestione dei servizi</span><span class="sxs-lookup"><span data-stu-id="93380-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="93380-141">I criteri di anteprima non esistono più e gli utenti dovranno creare i propri criteri.</span><span class="sxs-lookup"><span data-stu-id="93380-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="93380-142">Puoi configurare criteri aggiuntivi, ad esempio richiedere app client approvate.</span><span class="sxs-lookup"><span data-stu-id="93380-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="93380-143">Per ulteriori informazioni, vedere la [documentazione relativa all'accesso condizionale.](https://docs.microsoft.com/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="93380-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
