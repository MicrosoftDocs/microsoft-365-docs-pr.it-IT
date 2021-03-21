---
title: Passaggio 4. Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Usare Microsoft Endpoint Manager per gestire dispositivi, PC e altri endpoint.
ms.openlocfilehash: db06c7d65da1939ffbb04db64ea901e211b074f6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918339"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="1be06-104">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="1be06-104">Step 4.</span></span> <span data-ttu-id="1be06-105">Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint</span><span class="sxs-lookup"><span data-stu-id="1be06-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="1be06-106">Con i lavoratori remoti, è necessario supportare un numero crescente di dispositivi personali.</span><span class="sxs-lookup"><span data-stu-id="1be06-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="1be06-107">La gestione degli endpoint è un approccio alla sicurezza basato su criteri che richiede che i dispositivi siano conformi a criteri specifici prima che gli venga consentito l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="1be06-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="1be06-108">Microsoft Endpoint Manager offre strumenti moderni per la gestione che garantiscono la sicurezza dei dati sia nel cloud sia in locale.</span><span class="sxs-lookup"><span data-stu-id="1be06-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="1be06-109">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) include servizi e strumenti che consentono di gestire dispositivi mobili, computer desktop, macchine virtuali, dispositivi incorporati e server combinando i servizi seguenti, probabilmente già noti e usati.</span><span class="sxs-lookup"><span data-stu-id="1be06-109">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![Componenti di gestione degli endpoint per Microsoft 365](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="1be06-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1be06-111">Microsoft Intune</span></span>

<span data-ttu-id="1be06-112">Microsoft Intune è un servizio basato sul cloud che è incentrato sulla gestione di dispositivi mobili (MDM) e sulla gestione di applicazioni mobili (MAM) incluso in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1be06-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="1be06-113">**MDM:** per i dispositivi di proprietà dell'organizzazione, è possibile esercitare un controllo completo che include impostazioni, caratteristiche e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1be06-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="1be06-114">I dispositivi sono "registrati" in Intune, dove ricevono criteri di Intune con regole e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1be06-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="1be06-115">Ad esempio, è possibile impostare PIN e password, creare una connessione VPN, configurare la protezione contro le minacce e così via.</span><span class="sxs-lookup"><span data-stu-id="1be06-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="1be06-116">**MAM:** i lavoratori remoti potrebbero non voler concedere il controllo completo sui propri dispositivi personali, noti anche come dispositivi di BYOD (bring-your-own).</span><span class="sxs-lookup"><span data-stu-id="1be06-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="1be06-117">È possibile fornire opzioni ai lavoratori remoti e continuare a proteggere l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1be06-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="1be06-118">Ad esempio, i lavoratori remoti possono registrare i propri dispositivi, per avere accesso completo alle risorse dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1be06-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="1be06-119">In alternativa, se desiderano accedere solo alla posta elettronica o a Microsoft Teams, gli utenti possono usare i criteri di protezione delle app che richiedono l'autenticazione a più fattori (MFA) per l'uso di queste app.</span><span class="sxs-lookup"><span data-stu-id="1be06-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="1be06-120">Per altre informazioni, vedere questa [panoramica di Microsoft Intune](/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="1be06-120">For more information, see this [overview of Microsoft Intune](/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="1be06-121">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1be06-121">Configuration Manager</span></span>

<span data-ttu-id="1be06-122">Configuration Manager è una soluzione di gestione locale per gestire desktop, server e computer portatili collegati nella rete aziendale o in Internet.</span><span class="sxs-lookup"><span data-stu-id="1be06-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="1be06-123">Usare Configuration Manager per distribuire app, aggiornamenti software e sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="1be06-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="1be06-124">È anche possibile monitorare la conformità, eseguire query, intervenire sui client in tempo reale e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="1be06-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="1be06-125">È possibile abilitare la soluzione per il cloud e integrarla con Intune, Azure AD, Microsoft Defender per endpoint e altri servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="1be06-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender for Endpoint, and other cloud services.</span></span> 

<span data-ttu-id="1be06-126">Per altre informazioni, vedere questa [panoramica di Configuration Manager](/mem/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="1be06-126">For more information, see this [overview of Configuration Manager](/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="1be06-127">Co-gestione</span><span class="sxs-lookup"><span data-stu-id="1be06-127">Co-management</span></span>

<span data-ttu-id="1be06-128">La co-gestione integra l'investimento esistente in Configuration Manager locale con il cloud, tramite l'uso di Intune e di altri servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1be06-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="1be06-129">È possibile scegliere Configuration Manager o Intune come autorità di gestione per carichi di lavoro diversi.</span><span class="sxs-lookup"><span data-stu-id="1be06-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="1be06-130">La co-gestione usa funzionalità cloud basate su Intune, tra cui l'accesso condizionale e l'applicazione della conformità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1be06-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="1be06-131">Alcune attività restano in locale, mentre altre vengono eseguite nel cloud.</span><span class="sxs-lookup"><span data-stu-id="1be06-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="1be06-132">Per altre informazioni, vedere questa [panoramica della co-gestione](/mem/configmgr/comanage/overview).</span><span class="sxs-lookup"><span data-stu-id="1be06-132">For more information, see this [overview of co-management](/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="1be06-133">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="1be06-133">Desktop Analytics</span></span>

<span data-ttu-id="1be06-134">Desktop Analytics è un servizio basato sul cloud che si integra con Configuration Manager e fornisce dati analitici e intelligence utili per prendere decisioni informate sui client Windows.</span><span class="sxs-lookup"><span data-stu-id="1be06-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="1be06-135">Combina i dati dell'organizzazione con i dati aggregati di milioni di altri dispositivi connessi ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1be06-135">It combines data from your organization with data aggregated from millions of other devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="1be06-136">Con Desktop Analytics, è possibile:</span><span class="sxs-lookup"><span data-stu-id="1be06-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="1be06-137">Creare un inventario delle app eseguite nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1be06-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="1be06-138">Valutare la compatibilità delle app con gli aggiornamenti delle caratteristiche più recenti di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1be06-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="1be06-139">Individuare i problemi di compatibilità e ricevere suggerimenti di mitigazione in base alle informazioni dettagliate sui dati abilitati per il cloud.</span><span class="sxs-lookup"><span data-stu-id="1be06-139">Identify compatibility issues and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="1be06-140">Creare gruppi pilota che rappresentino l'intera applicazione e le proprietà del driver in un insieme minimo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1be06-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="1be06-141">Distribuire Windows 10 ai dispositivi pilota e gestiti dalla produzione.</span><span class="sxs-lookup"><span data-stu-id="1be06-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="1be06-142">Per altre informazioni, vedere questa [panoramica di Desktop Analytics](/mem/configmgr/desktop-analytics/overview).</span><span class="sxs-lookup"><span data-stu-id="1be06-142">For more information, see this [overview of Desktop Analytics](/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="1be06-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="1be06-143">Windows Autopilot</span></span>

<span data-ttu-id="1be06-144">Windows Autopilot è una piattaforma per la distribuzione di Windows in modalità self-service con gestione automatizzata.</span><span class="sxs-lookup"><span data-stu-id="1be06-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="1be06-145">Include una raccolta di tecnologie usate per impostare e preconfigurare nuovi dispositivi, preparandoli per l'uso.</span><span class="sxs-lookup"><span data-stu-id="1be06-145">It includes a collection of technologies you use to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="1be06-146">È anche possibile usare Windows Autopilot per reimpostare, riconfigurare e ripristinare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1be06-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="1be06-147">Windows Autopilot consente al reparto IT di preconfigurare dispositivi gestendo poche infrastrutture o persino nessuna, con un processo semplice e immediato.</span><span class="sxs-lookup"><span data-stu-id="1be06-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="1be06-148">Dal punto di vista dell'utente, bastano poche semplici operazioni per rendere il proprio dispositivo pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="1be06-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="1be06-149">Dal punto di vista dell'IT, l'unica interazione richiesta all'utente finale consiste nel connettersi a una rete e verificare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="1be06-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="1be06-150">Per altre informazioni, vedere questa [panoramica di Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).</span><span class="sxs-lookup"><span data-stu-id="1be06-150">For more information, see this [overview of Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="1be06-151">Risorse amministrative tecniche per la gestione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="1be06-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="1be06-152">Roadmap di gestione dei dispositivi per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1be06-152">Device management roadmap for Microsoft 365</span></span>](../enterprise/device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="1be06-153">Come registrare tipi diversi di dispositivi per la gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="1be06-153">How to enroll different types of devices for mobile device management</span></span>](/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="1be06-154">Come formare gli utenti finali su Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1be06-154">How to educate your end users about Microsoft Intune</span></span>](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a><span data-ttu-id="1be06-155">Risultati del Passaggio 4</span><span class="sxs-lookup"><span data-stu-id="1be06-155">Results of Step 4</span></span>

<span data-ttu-id="1be06-156">Si usano le caratteristiche e le funzionalità di Endpoint Manager per gestire dispositivi mobili, computer desktop, macchine virtuali dispositivi incorporati e server.</span><span class="sxs-lookup"><span data-stu-id="1be06-156">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="1be06-157">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="1be06-157">Next step</span></span>

<span data-ttu-id="1be06-158">[![Passaggio 5: distribuire le app e i servizi per la produttività dei lavoratori remoti](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span><span class="sxs-lookup"><span data-stu-id="1be06-158">[![Step 5: Deploy remote worker productivity apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span></span>

<span data-ttu-id="1be06-159">Proseguire con il [Passaggio 5](empower-people-to-work-remotely-teams-productivity-apps.md) per incoraggiare i lavoratori remoti a utilizzare le app di produttività Microsoft 365, come Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1be06-159">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>