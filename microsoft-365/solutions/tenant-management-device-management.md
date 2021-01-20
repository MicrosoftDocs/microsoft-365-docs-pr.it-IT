---
title: Passaggio 5. Gestione di dispositivi e app per i tenant di Microsoft 365 per Enterprise
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
ms.custom:
- Ent_Solutions
description: Distribuire l'opzione corretta per la gestione di dispositivi e app per i tenant Microsoft 365.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908584"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="6a736-104">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="6a736-104">Step 5.</span></span> <span data-ttu-id="6a736-105">Gestione di dispositivi e app per i tenant di Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="6a736-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="6a736-106">Microsoft 365 for Enterprise include funzionalità che consentono di gestire i dispositivi e l'utilizzo di app su tali dispositivi all'interno dell'organizzazione con la gestione dei dispositivi mobili (MDM) e la gestione delle applicazioni mobili (MAM).</span><span class="sxs-lookup"><span data-stu-id="6a736-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="6a736-107">È possibile gestire i dispositivi iOS, Android, macOS e Windows per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati.</span><span class="sxs-lookup"><span data-stu-id="6a736-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="6a736-108">Ad esempio, è possibile impedire l'invio di messaggi di posta elettronica a persone esterne all'organizzazione o isolare i dati dell'organizzazione dai dati personali dei dispositivi personali del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="6a736-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="6a736-109">Di seguito è riportato un esempio di convalida e gestione degli utenti, dei loro dispositivi e del loro utilizzo delle applicazioni locali e di produttività cloud come Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="6a736-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Convalida e gestione di utenti, dispositivi e app](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="6a736-111">Per garantire la sicurezza e la protezione delle risorse dell'organizzazione, Microsoft 365 for Enterprise include funzionalità che consentono di gestire i dispositivi e l'accesso alle app.</span><span class="sxs-lookup"><span data-stu-id="6a736-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="6a736-112">Sono disponibili due opzioni per la gestione dei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="6a736-112">There are two options for device management:</span></span>

- <span data-ttu-id="6a736-113">Microsoft Intune, che è una soluzione completa per la gestione di dispositivi e app per le aziende.</span><span class="sxs-lookup"><span data-stu-id="6a736-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="6a736-114">Mobilità e sicurezza di base, un sottoinsieme di servizi di Intune incluso con tutti i prodotti Microsoft 365 per la gestione dei dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6a736-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="6a736-115">Per ulteriori informazioni, vedere [funzionalità di base per dispositivi mobili e sicurezza](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span><span class="sxs-lookup"><span data-stu-id="6a736-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="6a736-116">Se si dispone di Microsoft 365 E3 o E5, è consigliabile utilizzare Intune.</span><span class="sxs-lookup"><span data-stu-id="6a736-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="6a736-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6a736-117">Microsoft Intune</span></span>

<span data-ttu-id="6a736-118">È possibile utilizzare [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) per gestire l'accesso all'organizzazione tramite MDM o mam.</span><span class="sxs-lookup"><span data-stu-id="6a736-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="6a736-119">MDM è il momento in cui gli utenti "iscrivono" i propri dispositivi in Intune.</span><span class="sxs-lookup"><span data-stu-id="6a736-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="6a736-120">Dopo la registrazione di un dispositivo, si tratta di un dispositivo gestito che può ricevere i criteri, le regole e le impostazioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6a736-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="6a736-121">Ad esempio, è possibile installare app specifiche, creare un criterio password, installare una connessione VPN e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="6a736-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="6a736-122">Gli utenti che dispongono di dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6a736-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="6a736-123">Tuttavia, è comunque necessario proteggere le risorse e i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6a736-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="6a736-124">In questo scenario, è possibile proteggere le app utilizzando MAM.</span><span class="sxs-lookup"><span data-stu-id="6a736-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="6a736-125">Ad esempio, è possibile utilizzare un criterio MAM che richiede a un utente di immettere un PIN quando si accede a SharePoint nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a736-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="6a736-126">È inoltre possibile determinare come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6a736-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="6a736-127">Potrebbe essere opportuno trattare i dispositivi in modo diverso, a seconda dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6a736-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="6a736-128">Configurazioni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="6a736-128">Identity and device access configurations</span></span>

<span data-ttu-id="6a736-129">Microsoft fornisce una serie di configurazioni per [l'accesso a identità e dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) per garantire una forza lavoro sicura e produttiva.</span><span class="sxs-lookup"><span data-stu-id="6a736-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="6a736-130">Tali configurazioni includono l'utilizzo di:</span><span class="sxs-lookup"><span data-stu-id="6a736-130">These configurations include the use of:</span></span>

- <span data-ttu-id="6a736-131">Criteri di Accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="6a736-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="6a736-132">Criteri di conformità del dispositivo e di protezione delle app di Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6a736-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="6a736-133">Criteri di rischio per gli utenti di Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="6a736-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="6a736-134">Criteri aggiuntivi delle app Cloud</span><span class="sxs-lookup"><span data-stu-id="6a736-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="6a736-135">Di seguito è riportato un esempio dell'applicazione di queste impostazioni e dei criteri per convalidare e limitare gli utenti, i propri dispositivi e l'utilizzo delle applicazioni locali e di produttività cloud come Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="6a736-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Configurazioni di accesso a identità e dispositivi per i requisiti e le restrizioni degli utenti, dei dispositivi e dell'utilizzo delle app](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="6a736-137">Per l'accesso ai dispositivi e la gestione delle app, utilizzare le configurazioni disponibili in questi articoli:</span><span class="sxs-lookup"><span data-stu-id="6a736-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="6a736-138">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6a736-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="6a736-139">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="6a736-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="6a736-140">Risultati del passaggio 5</span><span class="sxs-lookup"><span data-stu-id="6a736-140">Results of Step 5</span></span>

<span data-ttu-id="6a736-141">Per la gestione di dispositivi e app per il tenant Microsoft 365, sono state determinate le impostazioni e i criteri di Intune per convalidare e limitare gli utenti, i loro dispositivi e l'utilizzo delle app di produttività locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="6a736-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="6a736-142">Di seguito è riportato un esempio di tenant con il dispositivo Intune e la gestione delle app con i nuovi elementi evidenziati.</span><span class="sxs-lookup"><span data-stu-id="6a736-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Esempio di tenant con dispositivo e gestione delle app di Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="6a736-144">In questa figura, il tenant ha:</span><span class="sxs-lookup"><span data-stu-id="6a736-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="6a736-145">I dispositivi di proprietà dell'organizzazione sono stati registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="6a736-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="6a736-146">Criteri del dispositivo e delle app di Intune per i dispositivi registrati e personali.</span><span class="sxs-lookup"><span data-stu-id="6a736-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="6a736-147">Manutenzione continua per la gestione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="6a736-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="6a736-148">Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a736-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="6a736-149">Gestire la registrazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a736-149">Manage device enrollment.</span></span>
- <span data-ttu-id="6a736-150">Rivedere le impostazioni e i criteri per le app, i dispositivi e i requisiti di sicurezza aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="6a736-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
