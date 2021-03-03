---
title: Passaggio 5. Gestione di dispositivi e app per i tenant di Microsoft 365 per le aziende
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuire l'opzione corretta per la gestione di dispositivi e app per i tenant di Microsoft 365.
ms.openlocfilehash: 96412cb52540e87341fa67e20382951db7becfbe
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406373"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="e93a0-104">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="e93a0-104">Step 5.</span></span> <span data-ttu-id="e93a0-105">Gestione di dispositivi e app per i tenant di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="e93a0-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="e93a0-106">Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e l'uso delle app in tali dispositivi all'interno dell'organizzazione con gestione di dispositivi mobili (MDM) e gestione di applicazioni mobili (MAM).</span><span class="sxs-lookup"><span data-stu-id="e93a0-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="e93a0-107">Puoi gestire i dispositivi iOS, Android, macOS e Windows per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati.</span><span class="sxs-lookup"><span data-stu-id="e93a0-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="e93a0-108">Ad esempio, è possibile impedire l'invio di messaggi di posta elettronica a persone esterne all'organizzazione o isolare i dati dell'organizzazione dai dati personali nei dispositivi personali dei lavoratori.</span><span class="sxs-lookup"><span data-stu-id="e93a0-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="e93a0-109">Ecco un esempio di convalida e gestione degli utenti, dei loro dispositivi e dell'uso di app di produttività locali e cloud come Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e93a0-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Convalida e gestione di utenti, dispositivi e app](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="e93a0-111">Per proteggere e proteggere le risorse dell'organizzazione, Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e il loro accesso alle app.</span><span class="sxs-lookup"><span data-stu-id="e93a0-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="e93a0-112">Esistono due opzioni per la gestione dei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="e93a0-112">There are two options for device management:</span></span>

- <span data-ttu-id="e93a0-113">Microsoft Intune, una soluzione completa per la gestione di dispositivi e app per le aziende.</span><span class="sxs-lookup"><span data-stu-id="e93a0-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="e93a0-114">Sicurezza e mobilità di base, che è un sottoinsieme dei servizi intune inclusi in tutti i prodotti Microsoft 365 per la gestione dei dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e93a0-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="e93a0-115">Per ulteriori informazioni, vedere [Capabilities of Basic Mobility and Security.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)</span><span class="sxs-lookup"><span data-stu-id="e93a0-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="e93a0-116">Se si dispone di Microsoft 365 E3 o E5, è consigliabile usare Intune.</span><span class="sxs-lookup"><span data-stu-id="e93a0-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="e93a0-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e93a0-117">Microsoft Intune</span></span>

<span data-ttu-id="e93a0-118">Si usa [Microsoft Intune per](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) gestire l'accesso all'organizzazione tramite MDM o MAM.</span><span class="sxs-lookup"><span data-stu-id="e93a0-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="e93a0-119">MDM si verifica quando gli utenti "registrano" i propri dispositivi in Intune.</span><span class="sxs-lookup"><span data-stu-id="e93a0-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="e93a0-120">Dopo la registrazione, un dispositivo è gestito e può ricevere i criteri, le regole e le impostazioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e93a0-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="e93a0-121">Ad esempio, puoi installare app specifiche, creare criteri password, installare una connessione VPN e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="e93a0-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="e93a0-122">Gli utenti con i propri dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e93a0-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="e93a0-123">È comunque necessario proteggere le risorse e i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e93a0-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="e93a0-124">In questo scenario, puoi proteggere le tue app usando MAM.</span><span class="sxs-lookup"><span data-stu-id="e93a0-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="e93a0-125">Ad esempio, è possibile utilizzare un criterio MAM che richiede a un utente di immettere un PIN quando accede a SharePoint nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e93a0-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="e93a0-126">Potrai anche determinare come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e93a0-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="e93a0-127">Potresti voler trattare i dispositivi in modo diverso, a seconda del loro uso.</span><span class="sxs-lookup"><span data-stu-id="e93a0-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="e93a0-128">Configurazioni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="e93a0-128">Identity and device access configurations</span></span>

<span data-ttu-id="e93a0-129">Microsoft fornisce un set di configurazioni per [l'identità e l'accesso](../security/office-365-security/microsoft-365-policies-configurations.md) ai dispositivi per garantire una forza lavoro sicura e produttiva.</span><span class="sxs-lookup"><span data-stu-id="e93a0-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="e93a0-130">Queste configurazioni includono l'uso di:</span><span class="sxs-lookup"><span data-stu-id="e93a0-130">These configurations include the use of:</span></span>

- <span data-ttu-id="e93a0-131">Criteri di Accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="e93a0-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="e93a0-132">Criteri di conformità dei dispositivi e di protezione delle app di Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e93a0-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="e93a0-133">Criteri di rischio utente di Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="e93a0-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="e93a0-134">Criteri aggiuntivi delle app cloud</span><span class="sxs-lookup"><span data-stu-id="e93a0-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="e93a0-135">Ecco un esempio dell'applicazione di queste impostazioni e criteri per convalidare e limitare gli utenti, i loro dispositivi e l'uso di app di produttività locali e cloud come Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e93a0-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Configurazioni di identità e accesso ai dispositivi per i requisiti e le restrizioni per gli utenti, i dispositivi e l'uso delle app](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="e93a0-137">Per l'accesso ai dispositivi e la gestione delle app, usa le configurazioni negli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e93a0-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="e93a0-138">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e93a0-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="e93a0-139">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="e93a0-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="e93a0-140">Risultati del passaggio 5</span><span class="sxs-lookup"><span data-stu-id="e93a0-140">Results of Step 5</span></span>

<span data-ttu-id="e93a0-141">Per la gestione di dispositivi e app per il tenant di Microsoft 365, sono stati determinati le impostazioni e i criteri di Intune per convalidare e limitare gli utenti, i dispositivi e l'uso delle app di produttività locale e cloud.</span><span class="sxs-lookup"><span data-stu-id="e93a0-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="e93a0-142">Ecco un esempio di tenant con gestione di app e dispositivi Intune con i nuovi elementi evidenziati.</span><span class="sxs-lookup"><span data-stu-id="e93a0-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Esempio di tenant con gestione di app e dispositivi Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="e93a0-144">In questa figura, il tenant ha:</span><span class="sxs-lookup"><span data-stu-id="e93a0-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="e93a0-145">Dispositivi di proprietà dell'organizzazione registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="e93a0-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="e93a0-146">Criteri di dispositivi e app intune per i dispositivi registrati e personali.</span><span class="sxs-lookup"><span data-stu-id="e93a0-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="e93a0-147">Manutenzione continua per la gestione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="e93a0-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="e93a0-148">Su base continuativa, potrebbe essere necessario:</span><span class="sxs-lookup"><span data-stu-id="e93a0-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="e93a0-149">Gestire la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e93a0-149">Manage device enrollment.</span></span>
- <span data-ttu-id="e93a0-150">Rivedere le impostazioni e i criteri per altre app, dispositivi e requisiti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e93a0-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
