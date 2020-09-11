---
title: Panoramica della sicurezza e della mobilità di base per Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Utilizzare la sicurezza e la mobilità di base per impostare i criteri di sicurezza del dispositivo e le regole di accesso.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430201"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="2aff8-103">Panoramica della sicurezza e della mobilità di base per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2aff8-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="2aff8-104">È possibile gestire e proteggere i dispositivi mobili quando sono connessi all'organizzazione Microsoft 365 utilizzando la sicurezza e la mobilità di base.</span><span class="sxs-lookup"><span data-stu-id="2aff8-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="2aff8-105">I dispositivi mobili, come smartphone e tablet, utilizzati per accedere alla posta elettronica di lavoro, al calendario, ai contatti e ai documenti, giocano un ruolo molto importante nell'assicurare ai dipendenti lo svolgimento del loro lavoro ovunque e in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="2aff8-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="2aff8-106">Pertanto, è importante contribuire alla protezione delle informazioni dell'organizzazione quando gli utenti utilizzano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2aff8-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="2aff8-107">È possibile utilizzare la sicurezza e la mobilità di base per impostare i criteri di sicurezza del dispositivo e le regole di accesso e per cancellare i dispositivi mobili se sono stati persi o rubati.</span><span class="sxs-lookup"><span data-stu-id="2aff8-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configurazione di base per dispositivi mobili e sicurezza":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="2aff8-109">Quali tipi di dispositivi è possibile gestire?</span><span class="sxs-lookup"><span data-stu-id="2aff8-109">What types of devices can you manage?</span></span>

<span data-ttu-id="2aff8-110">È possibile utilizzare la sicurezza e la mobilità di base per gestire numerosi tipi di dispositivi mobili, come Windows Phone, Android, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="2aff8-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="2aff8-111">Per gestire i dispositivi mobili utilizzati dagli utenti dell'organizzazione, ogni persona deve disporre di una licenza di Microsoft 365 applicabile e il dispositivo deve essere registrato in mobilità e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="2aff8-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="2aff8-112">Per sapere cosa supporta la sicurezza e la mobilità di base per ogni tipo di dispositivo, vedere [funzionalità di base per dispositivi mobili e sicurezza](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="2aff8-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="2aff8-113">Procedure di installazione per la sicurezza e la mobilità di base</span><span class="sxs-lookup"><span data-stu-id="2aff8-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="2aff8-114">Per attivare e configurare la sicurezza e la mobilità di base, è necessario che un amministratore globale di Microsoft 365 completi i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2aff8-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="2aff8-115">Per la procedura dettagliata, seguire le istruzioni riportate in [configurare la sicurezza e la mobilità di base](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="2aff8-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="2aff8-116">Di seguito è riportata una sintesi dei passaggi:</span><span class="sxs-lookup"><span data-stu-id="2aff8-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="2aff8-117">**Passaggio 1:** Attivare la sicurezza e la mobilità di base attenendosi alla procedura descritta in [set up Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="2aff8-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="2aff8-118">**Passaggio 2:** Configurare la sicurezza e la mobilità di base, ad esempio creando un certificato APNs per gestire i dispositivi iOS e aggiungendo un record DNS (Domain Name System) per il dominio per il supporto dei telefoni Windows.</span><span class="sxs-lookup"><span data-stu-id="2aff8-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="2aff8-119">**Passaggio 3:** Creare i criteri per i dispositivi e applicarli ai gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="2aff8-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="2aff8-120">Quando si esegue questa operazione, gli utenti ricevono un messaggio di registrazione nel dispositivo e, al termine della registrazione, i dispositivi sono limitati dai criteri che sono stati configurati.</span><span class="sxs-lookup"><span data-stu-id="2aff8-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="2aff8-121">Per altre informazioni, vedere [registrazione del dispositivo mobile utilizzando la sicurezza e la mobilità di base](enroll-your-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="2aff8-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni di base per i criteri di sicurezza e dispositivi mobili":::

## <a name="device-management-tasks"></a><span data-ttu-id="2aff8-123">Attività di gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="2aff8-123">Device management tasks</span></span>

<span data-ttu-id="2aff8-124">Dopo aver impostato la sicurezza e la mobilità di base e gli utenti hanno registrato i propri dispositivi, è possibile gestire i dispositivi, bloccare l'accesso o cancellare un dispositivo, se necessario.</span><span class="sxs-lookup"><span data-stu-id="2aff8-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="2aff8-125">Per ulteriori informazioni su alcune attività comuni di gestione dei dispositivi, tra cui il completamento delle attività, vedere [gestire i dispositivi registrati nella gestione dei dispositivi mobili per Microsoft 365](manage-enrolled-devices.md).</span><span class="sxs-lookup"><span data-stu-id="2aff8-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="2aff8-126">Altre modalità di gestione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="2aff8-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="2aff8-127">Se è necessaria solo la gestione delle app per dispositivi mobili, forse per gli utenti che aggiornano i progetti di lavoro sui propri sistemi, Intune fornisce un'altra opzione oltre alla registrazione e alla gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2aff8-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="2aff8-128">Un abbonamento a Intune consente di configurare i criteri MAM tramite il portale di Azure, anche se i dispositivi non sono registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="2aff8-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="2aff8-129">Per altre informazioni, vedere [Panoramica dei criteri di protezione delle app](https://go.microsoft.com/fwlink/?LinkId=2132517).</span><span class="sxs-lookup"><span data-stu-id="2aff8-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2aff8-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2aff8-130">Related topics</span></span>

[<span data-ttu-id="2aff8-131">Impostare Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="2aff8-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="2aff8-132">Registrazione del dispositivo mobile tramite la sicurezza e la mobilità di base</span><span class="sxs-lookup"><span data-stu-id="2aff8-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="2aff8-133">Gestire i dispositivi registrati nella gestione dei dispositivi mobili per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2aff8-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="2aff8-134">Ottenere informazioni dettagliate sui dispositivi gestiti da mobilità e sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="2aff8-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)