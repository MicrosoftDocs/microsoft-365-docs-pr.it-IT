---
title: Impostare i criteri di accesso condizionale per le campagne Microsoft 365
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come configurare i criteri di accesso condizionale per le campagne Microsoft 365.
ms.openlocfilehash: 335fbd7e771b1595e1846529daed76e5ddd3a8f5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593386"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="1fa05-103">Impostare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="1fa05-103">Set up conditional access policies</span></span>

<span data-ttu-id="1fa05-104">I criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) aggiungono ulteriore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1fa05-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="1fa05-105">Microsoft fornisce una serie di criteri di accesso condizionale previsti che sono consigliati per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="1fa05-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="1fa05-106">I criteri di base sono un insieme di criteri predefiniti che consentono di proteggere le organizzazioni da numerosi attacchi comuni.</span><span class="sxs-lookup"><span data-stu-id="1fa05-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="1fa05-107">Questi attacchi comuni possono includere lo spray per la password, la riproduzione e il phishing.</span><span class="sxs-lookup"><span data-stu-id="1fa05-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="1fa05-108">Questi criteri richiedono agli amministratori e agli utenti di immettere una seconda forma di autenticazione (denominata autenticazione a più fattori o AMF) quando vengono soddisfatte determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="1fa05-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="1fa05-109">Ad esempio, se un utente ha effettuato l'accesso da un paese diverso, l'accesso potrebbe essere considerato rischioso e l'utente deve fornire un'ulteriore forma di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1fa05-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="1fa05-110">Attualmente, i criteri di base includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1fa05-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="1fa05-111">**Richiedi** &ndash; l'autenticazione a più fattori per i ruoli di amministratore più privilegiati, tra cui l'amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1fa05-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="1fa05-112">La &ndash; **protezione dell'utente finale** richiede l'autenticazione a più fattori per gli utenti solo quando un accesso è rischioso.</span><span class="sxs-lookup"><span data-stu-id="1fa05-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="1fa05-113">**Blocca l'autenticazione** &ndash; legacy le applicazioni client precedenti e alcune nuove app non utilizzano protocolli di autenticazione più recenti e sicuri.</span><span class="sxs-lookup"><span data-stu-id="1fa05-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="1fa05-114">Queste app precedenti possono ignorare i criteri di accesso condizionale e ottenere un accesso non autorizzato all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1fa05-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="1fa05-115">Questo criterio blocca l'accesso da client che non supportano l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="1fa05-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="1fa05-116">**Richiedi** &ndash; l'autenticazione a più fattori per l'accesso agli strumenti di gestione, incluso il portale di Azure (in cui vengono configurati i criteri di base).</span><span class="sxs-lookup"><span data-stu-id="1fa05-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="1fa05-117">Microsoft consiglia di abilitare tutti questi criteri di base.</span><span class="sxs-lookup"><span data-stu-id="1fa05-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="1fa05-118">Dopo aver abilitato questi criteri, agli amministratori e agli utenti verrà richiesto di eseguire la registrazione per l'autenticazione a più fattori di Azure.</span><span class="sxs-lookup"><span data-stu-id="1fa05-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="1fa05-119">Per ulteriori informazioni su questi criteri, vedere [What are Baseline Policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="1fa05-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="1fa05-120">Impostare i criteri di base</span><span class="sxs-lookup"><span data-stu-id="1fa05-120">Set up baseline policies</span></span>

1. <span data-ttu-id="1fa05-121">Accedere a [portale di Azure](https://portal.azure.com)e quindi passare a **accesso condizionale**di **Azure Active Directory** \> .</span><span class="sxs-lookup"><span data-stu-id="1fa05-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="1fa05-122">I criteri di base sono elencati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="1fa05-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="1fa05-123">![Pagina in cui sono elencati i criteri di base per l'accesso condizionale.](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="1fa05-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="1fa05-124">Per ogni criterio, vedere le istruzioni specifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fa05-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="1fa05-125">Richiedi l'autenticazione a più fattori per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="1fa05-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="1fa05-126">Richiedi l'autenticazione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="1fa05-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="1fa05-127">Blocca l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="1fa05-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="1fa05-128">Richiedere l'autenticazione dell'AMF per la gestione dei servizi</span><span class="sxs-lookup"><span data-stu-id="1fa05-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="1fa05-129">È possibile configurare molti altri criteri, ad esempio la necessità di applicazioni client approvate.</span><span class="sxs-lookup"><span data-stu-id="1fa05-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="1fa05-130">Per ulteriori informazioni, vedere la [documentazione relativa all'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="1fa05-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
