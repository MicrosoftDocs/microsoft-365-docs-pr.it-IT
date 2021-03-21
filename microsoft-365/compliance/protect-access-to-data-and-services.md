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
description: Informazioni su come proteggere l'accesso di utenti e dispositivi ai dati e ai servizi di Microsoft 365 e difendersi dalla perdita di dati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd8bbb62bc87ff59594e2fb2a3e21311c2452d9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925542"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="d1673-103">Proteggere l'accesso di utenti e dispositivi</span><span class="sxs-lookup"><span data-stu-id="d1673-103">Protect user and device access</span></span>

<span data-ttu-id="d1673-104">Proteggere l'accesso ai dati e ai servizi di Microsoft 365 è fondamentale per difendersi da attacchi informatici e proteggersi dalla perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="d1673-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="d1673-105">Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente e anche alle applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1673-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="d1673-106">Passaggio 1: esaminare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="d1673-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="d1673-107">Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d1673-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="d1673-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="d1673-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="d1673-109">Passaggio 2: Proteggere gli account amministratore e l'accesso</span><span class="sxs-lookup"><span data-stu-id="d1673-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="d1673-110">Gli account amministrativi utilizzati per amministrare l'ambiente Microsoft 365 includono privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="d1673-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="d1673-111">Si tratta di obiettivi importanti per hacker e cyberattacchi.</span><span class="sxs-lookup"><span data-stu-id="d1673-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="d1673-112">Iniziare utilizzando gli account di amministratore solo per l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d1673-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="d1673-113">Gli amministratori devono disporre di un account utente separato per uso normale e non amministrativo e utilizzare il proprio account amministrativo solo se necessario per completare un'attività associata alla funzione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="d1673-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="d1673-114">Proteggere gli account amministratore con l'autenticazione a più fattori e l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="d1673-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="d1673-115">Per ulteriori informazioni, vedere [Protezione degli account amministratore.](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="d1673-115">For more information, see [Protecting administrator accounts](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="d1673-116">Configurare quindi la gestione degli accessi con privilegi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1673-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="d1673-117">La gestione degli accessi privilegiati consente il controllo granulare dell'accesso sulle attività di amministrazione con privilegi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1673-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="d1673-118">Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare account di amministratore con privilegi esistenti con accesso permanente a dati sensibili o accesso a impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="d1673-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="d1673-119">Panoramica della gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="d1673-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="d1673-120">Configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="d1673-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="d1673-121">Un altro consiglio principale è l'utilizzo di workstation configurate in modo specifico per il lavoro amministrativo.</span><span class="sxs-lookup"><span data-stu-id="d1673-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="d1673-122">Si tratta di dispositivi dedicati usati solo per attività amministrative.</span><span class="sxs-lookup"><span data-stu-id="d1673-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="d1673-123">Vedere [Protezione dell'accesso con privilegi](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="d1673-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="d1673-124">Infine, è possibile ridurre l'impatto della mancanza accidentale di accesso amministrativo creando due o più account di accesso di emergenza nel tenant.</span><span class="sxs-lookup"><span data-stu-id="d1673-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="d1673-125">Vedere [Gestire gli account di accesso di emergenza in Azure AD.](/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="d1673-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="d1673-126">Passaggio 3: Configurare i criteri di identità e di accesso ai dispositivi consigliati</span><span class="sxs-lookup"><span data-stu-id="d1673-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="d1673-127">L'autenticazione a più fattori (MFA) e i criteri di accesso condizionale sono strumenti potenti per ridurre gli account compromessi e l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="d1673-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="d1673-128">È consigliabile implementare un set di criteri che sono stati testati insieme.</span><span class="sxs-lookup"><span data-stu-id="d1673-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="d1673-129">Per ulteriori informazioni, inclusi i passaggi di distribuzione, vedere [Configurazioni di identità e accesso ai dispositivi.](../security/office-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="d1673-129">For more information, including deployment steps, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="d1673-130">Questi criteri implementano le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1673-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="d1673-131">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="d1673-131">Mult-factor authentication</span></span>
- <span data-ttu-id="d1673-132">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="d1673-132">Conditional access</span></span>
- <span data-ttu-id="d1673-133">Protezione delle app di Intune (protezione delle app e dei dati per i dispositivi)</span><span class="sxs-lookup"><span data-stu-id="d1673-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="d1673-134">Conformità dei dispositivi Intune</span><span class="sxs-lookup"><span data-stu-id="d1673-134">Intune device compliance</span></span>
- <span data-ttu-id="d1673-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d1673-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="d1673-136">L'implementazione della conformità dei dispositivi intune richiede la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1673-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="d1673-137">La gestione dei dispositivi consente di verificare che siano integri e conformi prima di consentire loro l'accesso alle risorse nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d1673-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="d1673-138">Vedere [Registrare i dispositivi per la gestione in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="d1673-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="d1673-139">Passaggio 4: Configurare i criteri di accesso ai dispositivi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d1673-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="d1673-140">Microsoft consiglia di proteggere il contenuto nei siti di SharePoint con contenuti sensibili e altamente regolamentati con controlli di accesso ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d1673-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="d1673-141">Per ulteriori informazioni, vedere [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d1673-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>



