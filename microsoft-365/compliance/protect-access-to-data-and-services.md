---
title: Proteggere l'accesso di utenti e dispositivi
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: pagina di destinazione per la protezione dell'accesso ai dati e ai servizi di O365
ms.openlocfilehash: eec1963f73b4b1e014f3605ae8fc5afee4ae039b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601703"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="81c5c-103">Proteggere l'accesso di utenti e dispositivi</span><span class="sxs-lookup"><span data-stu-id="81c5c-103">Protect user and device access</span></span>

<span data-ttu-id="81c5c-104">La protezione dell'accesso ai dati e ai servizi di Office 365 è cruciale per la difesa da attacchi cibernetici e per la protezione dalla perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="81c5c-104">Protecting access to your Office 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="81c5c-105">Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente e persino alle applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81c5c-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="81c5c-106">Passaggio 1: esaminare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="81c5c-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="81c5c-107">Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="81c5c-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="81c5c-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="81c5c-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="81c5c-109">Passaggio 2: proteggere gli account di amministratore e l'accesso</span><span class="sxs-lookup"><span data-stu-id="81c5c-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="81c5c-110">Gli account amministrativi utilizzati per amministrare l'ambiente di Office 365 includono privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="81c5c-110">The administrative accounts you use to administer your Office 365 environment include elevated privileges.</span></span> <span data-ttu-id="81c5c-111">Questi sono obiettivi validi per hacker e cyberattackers.</span><span class="sxs-lookup"><span data-stu-id="81c5c-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="81c5c-112">Iniziare utilizzando solo gli account amministratore per l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="81c5c-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="81c5c-113">Gli amministratori devono disporre di un account utente distinto per l'utilizzo regolare e non amministrativo e utilizzare il proprio account amministrativo solo quando necessario per completare un'attività associata alla loro funzione processi.</span><span class="sxs-lookup"><span data-stu-id="81c5c-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="81c5c-114">Proteggere gli account di amministratore con l'autenticazione a più fattori e l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="81c5c-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="81c5c-115">Per ulteriori informazioni, vedere [protecting Administrator Accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="81c5c-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="81c5c-116">Successivamente, configurare la gestione degli accessi con privilegi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="81c5c-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="81c5c-117">La gestione degli accessi con privilegi consente il controllo di accesso granulare sulle attività amministrative privilegiate in Office 365.</span><span class="sxs-lookup"><span data-stu-id="81c5c-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="81c5c-118">Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare gli account di amministrazione privilegiati esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="81c5c-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="81c5c-119">Panoramica della gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="81c5c-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="81c5c-120">Configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="81c5c-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="81c5c-121">Un'altra raccomandazione principale consiste nell'utilizzare le workstation appositamente configurate per il lavoro amministrativo.</span><span class="sxs-lookup"><span data-stu-id="81c5c-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="81c5c-122">Si tratta di dispositivi dedicati che vengono utilizzati solo per le attività amministrative.</span><span class="sxs-lookup"><span data-stu-id="81c5c-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="81c5c-123">Vedere [protezione dell'accesso con privilegi](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="81c5c-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="81c5c-124">Infine, è possibile ridurre l'impatto della mancanza di accesso amministrativo accidentale creando due o più account di accesso di emergenza nel tenant.</span><span class="sxs-lookup"><span data-stu-id="81c5c-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="81c5c-125">Vedere [gestire gli account di accesso per gli interventi di emergenza in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="81c5c-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="81c5c-126">Passaggio 3: configurare i criteri di identità e accesso ai dispositivi consigliati</span><span class="sxs-lookup"><span data-stu-id="81c5c-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="81c5c-127">L'autenticazione a più fattori e i criteri di accesso condizionale sono strumenti potenti per attenuare gli account compromessi e gli accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="81c5c-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="81c5c-128">È consigliabile implementare un insieme di criteri che sono stati testati insieme.</span><span class="sxs-lookup"><span data-stu-id="81c5c-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="81c5c-129">Per ulteriori informazioni, incluse le procedure di distribuzione, vedere [Identity and Device Access Configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span><span class="sxs-lookup"><span data-stu-id="81c5c-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="81c5c-130">Questi criteri implementano le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="81c5c-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="81c5c-131">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="81c5c-131">Mult-factor authentication</span></span>
- <span data-ttu-id="81c5c-132">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="81c5c-132">Conditional access</span></span>
- <span data-ttu-id="81c5c-133">Protezione delle app di Intune (app e protezione dei dati per i dispositivi)</span><span class="sxs-lookup"><span data-stu-id="81c5c-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="81c5c-134">Conformità del dispositivo Intune</span><span class="sxs-lookup"><span data-stu-id="81c5c-134">Intune device compliance</span></span>
- <span data-ttu-id="81c5c-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="81c5c-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="81c5c-136">L'implementazione della conformità del dispositivo Intune richiede la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="81c5c-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="81c5c-137">La gestione dei dispositivi consente di assicurarsi che siano integre e conformi prima di consentire loro di accedere alle risorse nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="81c5c-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="81c5c-138">Vedere [registrazione dei dispositivi per la gestione in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="81c5c-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="81c5c-139">Passaggio 4: configurare i criteri di accesso ai dispositivi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="81c5c-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="81c5c-140">Microsoft consiglia di proteggere il contenuto nei siti di SharePoint con contenuti sensibili e altamente regolamentati con i controlli di accesso ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="81c5c-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="81c5c-141">Per ulteriori informazioni, vedere [consigli sui criteri per la protezione di siti e file di SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="81c5c-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

