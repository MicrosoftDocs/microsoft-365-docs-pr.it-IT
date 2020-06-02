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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come configurare i criteri di accesso condizionale per le campagne Microsoft 365 per aggiungere una maggiore sicurezza aggiuntiva.
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470648"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="ec79e-103">Configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="ec79e-103">Set up conditional access policies</span></span>

<span data-ttu-id="ec79e-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="ec79e-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="ec79e-105">I criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) aggiungono ulteriore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ec79e-105">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="ec79e-106">Microsoft fornisce una serie di criteri di accesso condizionale previsti che sono consigliati per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="ec79e-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="ec79e-107">I criteri di base sono un insieme di criteri predefiniti che consentono di proteggere le organizzazioni da numerosi attacchi comuni.</span><span class="sxs-lookup"><span data-stu-id="ec79e-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="ec79e-108">Questi attacchi comuni possono includere lo spray per la password, la riproduzione e il phishing.</span><span class="sxs-lookup"><span data-stu-id="ec79e-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="ec79e-109">Questi criteri richiedono agli amministratori e agli utenti di immettere una seconda forma di autenticazione (denominata autenticazione a più fattori o AMF) quando vengono soddisfatte determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="ec79e-109">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="ec79e-110">Ad esempio, se un utente ha effettuato l'accesso da un paese diverso, l'accesso potrebbe essere considerato rischioso e l'utente deve fornire un'ulteriore forma di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ec79e-110">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="ec79e-111">Attualmente, i criteri di base includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ec79e-111">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="ec79e-112">Richiedi l'autenticazione a più fattori **per gli amministratori** &ndash; Richiede l'autenticazione a più fattori per i ruoli di amministratore più privilegiati, tra cui l'amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="ec79e-112">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="ec79e-113">Protezione dell'utente **finale** &ndash; Richiede l'autenticazione a più fattori per gli utenti solo quando un accesso è rischioso.</span><span class="sxs-lookup"><span data-stu-id="ec79e-113">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="ec79e-114">**Blocca l'autenticazione legacy** &ndash; Le app client precedenti e alcune nuove app non utilizzano protocolli di autenticazione più recenti e sicuri.</span><span class="sxs-lookup"><span data-stu-id="ec79e-114">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="ec79e-115">Queste app precedenti possono ignorare i criteri di accesso condizionale e ottenere un accesso non autorizzato all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="ec79e-115">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="ec79e-116">Questo criterio blocca l'accesso da client che non supportano l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="ec79e-116">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="ec79e-117">**Richiedere l'autenticazione dell'AMF per la gestione dei servizi** &ndash; Richiede l'autenticazione a più fattori per l'accesso agli strumenti di gestione, incluso il portale di Azure (in cui vengono configurati i criteri di base).</span><span class="sxs-lookup"><span data-stu-id="ec79e-117">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="ec79e-118">Microsoft consiglia di abilitare tutti questi criteri di base.</span><span class="sxs-lookup"><span data-stu-id="ec79e-118">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="ec79e-119">Dopo aver abilitato questi criteri, agli amministratori e agli utenti verrà richiesto di eseguire la registrazione per l'autenticazione a più fattori di Azure.</span><span class="sxs-lookup"><span data-stu-id="ec79e-119">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="ec79e-120">Per ulteriori informazioni su questi criteri, vedere [What are Baseline Policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="ec79e-120">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="ec79e-121">Impostare i criteri di base</span><span class="sxs-lookup"><span data-stu-id="ec79e-121">Set up baseline policies</span></span>

1. <span data-ttu-id="ec79e-122">Accedere a [portale di Azure](https://portal.azure.com)e quindi passare a **Azure Active Directory** \> **accesso condizionale**di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ec79e-122">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="ec79e-123">I criteri di base sono elencati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ec79e-123">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="ec79e-124">![Pagina in cui sono elencati i criteri di base per l'accesso condizionale.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="ec79e-124">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="ec79e-125">Per ogni criterio, vedere le istruzioni specifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec79e-125">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="ec79e-126">Richiedi l'autenticazione a più fattori per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="ec79e-126">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="ec79e-127">Richiedi l'autenticazione per gli utenti</span><span class="sxs-lookup"><span data-stu-id="ec79e-127">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="ec79e-128">Bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="ec79e-128">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="ec79e-129">Richiedere l'autenticazione dell'AMF per la gestione dei servizi</span><span class="sxs-lookup"><span data-stu-id="ec79e-129">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="ec79e-130">È possibile configurare molti altri criteri, ad esempio la necessità di applicazioni client approvate.</span><span class="sxs-lookup"><span data-stu-id="ec79e-130">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="ec79e-131">Per ulteriori informazioni, vedere la [documentazione relativa all'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="ec79e-131">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
