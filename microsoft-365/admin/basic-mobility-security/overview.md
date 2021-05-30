---
title: Panoramica della mobilità e della sicurezza di base per Microsoft 365
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
description: Usa Dispositivi mobili e sicurezza di base per impostare i criteri di sicurezza dei dispositivi e le regole di accesso.
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706311"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="534c6-103">Panoramica della mobilità e della sicurezza di base per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="534c6-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="534c6-104">Puoi gestire e proteggere i dispositivi mobili quando sono connessi all'organizzazione Microsoft 365 tramite Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="534c6-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="534c6-105">I dispositivi mobili, come smartphone e tablet, utilizzati per accedere alla posta elettronica di lavoro, al calendario, ai contatti e ai documenti, giocano un ruolo molto importante nell'assicurare ai dipendenti lo svolgimento del loro lavoro ovunque e in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="534c6-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="534c6-106">È pertanto fondamentale proteggere le informazioni dell'organizzazione quando gli utenti usano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="534c6-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="534c6-107">Puoi usare Dispositivi mobili e sicurezza di base per impostare i criteri di sicurezza e le regole di accesso dei dispositivi e cancellare i dispositivi mobili in caso di sperpero o furto.</span><span class="sxs-lookup"><span data-stu-id="534c6-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configurazione di base per dispositivi mobili e sicurezza":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="534c6-109">Quali tipi di dispositivi è possibile gestire?</span><span class="sxs-lookup"><span data-stu-id="534c6-109">What types of devices can you manage?</span></span>

<span data-ttu-id="534c6-110">Puoi usare Dispositivi mobili e sicurezza di base per gestire molti tipi di dispositivi mobili come Windows Phone, Android, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="534c6-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="534c6-111">Per gestire i dispositivi mobili usati dagli utenti dell'organizzazione, ogni persona deve disporre di una licenza Microsoft 365 applicabile e il dispositivo deve essere registrato in Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="534c6-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="534c6-112">Per sapere quali dispositivi mobili e sicurezza di base supportano per ogni tipo di dispositivo, vedi [Funzionalità di mobilità e sicurezza di base.](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="534c6-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="534c6-113">Passaggi di installazione per Dispositivi mobili e sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="534c6-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="534c6-114">Un Microsoft 365 globale deve completare i passaggi seguenti per attivare e configurare La mobilità e la sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="534c6-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="534c6-115">Per la procedura dettagliata, seguire le istruzioni in [Set up Basic Mobility and Security.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="534c6-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="534c6-116">Ecco un riepilogo dei passaggi:</span><span class="sxs-lookup"><span data-stu-id="534c6-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="534c6-117">**Passaggio 1:** Attivare Dispositivi mobili e sicurezza di base seguendo la procedura descritta in  [Set up Basic Mobility and Security.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="534c6-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="534c6-118">**Passaggio 2:** Configurare dispositivi mobili e sicurezza di base creando ad esempio un certificato APNs per gestire i dispositivi iOS e aggiungendo un record DNS (Domain Name System) per il dominio per supportare i telefoni Windows.</span><span class="sxs-lookup"><span data-stu-id="534c6-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="534c6-119">**Passaggio 3:** Crea criteri dispositivo e applicali a gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="534c6-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="534c6-120">Quando si esegue questa operazione, gli utenti ottengono un messaggio di registrazione nel dispositivo e, dopo aver completato la registrazione, i dispositivi sono limitati dai criteri impostati per loro.</span><span class="sxs-lookup"><span data-stu-id="534c6-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="534c6-121">Per altre info, vedi [Registrare il dispositivo mobile usando Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="534c6-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni di base dei criteri di sicurezza e dispositivi mobili":::

## <a name="device-management-tasks"></a><span data-ttu-id="534c6-123">Attività di gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="534c6-123">Device management tasks</span></span>

<span data-ttu-id="534c6-124">Dopo aver configurato Dispositivi mobili e sicurezza di base e aver registrato i dispositivi degli utenti, puoi gestire i dispositivi, bloccare l'accesso o cancellare un dispositivo, se necessario.</span><span class="sxs-lookup"><span data-stu-id="534c6-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="534c6-125">Per altre informazioni su alcune attività comuni di gestione dei dispositivi, inclusa la posizione in cui completare le attività, vedi Gestire i dispositivi registrati in Gestione dispositivi mobili [per Microsoft 365](manage-enrolled-devices.md).</span><span class="sxs-lookup"><span data-stu-id="534c6-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="534c6-126">Altri modi per gestire dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="534c6-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="534c6-127">Se hai solo bisogno di gestione delle app per dispositivi mobili (MAM), ad esempio per gli utenti che aggiornano progetti di lavoro nei propri dispositivi, Intune offre un'altra opzione oltre alla registrazione e alla gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="534c6-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="534c6-128">Una sottoscrizione di Intune consente di configurare i criteri MAM tramite il portale di Azure, anche se i dispositivi degli utenti non sono registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="534c6-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="534c6-129">Per altre info, vedi [Panoramica dei criteri di protezione delle app.](/mem/intune/apps/app-protection-policy)</span><span class="sxs-lookup"><span data-stu-id="534c6-129">For more info, see [App protection policies overview](/mem/intune/apps/app-protection-policy).</span></span>

## <a name="related-content"></a><span data-ttu-id="534c6-130">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="534c6-130">Related content</span></span>

<span data-ttu-id="534c6-131">[Configurare dispositivi mobili e sicurezza di base](set-up.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="534c6-131">[Set up Basic Mobility and Security](set-up.md) (article)</span></span>\
<span data-ttu-id="534c6-132">[Registrare il dispositivo mobile con Dispositivi mobili e sicurezza](enroll-your-mobile-device.md) di base (articolo)</span><span class="sxs-lookup"><span data-stu-id="534c6-132">[Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md) (article)</span></span>\
<span data-ttu-id="534c6-133">[Gestire i dispositivi registrati in Gestione dispositivi mobili per Microsoft 365](manage-enrolled-devices.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="534c6-133">[Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md) (article)</span></span>\
<span data-ttu-id="534c6-134">[Informazioni dettagliate sui dispositivi gestiti da Dispositivi mobili e sicurezza di base](get-details-about-managed-devices.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="534c6-134">[Get details about devices managed by Basic Mobility and Security](get-details-about-managed-devices.md) (article)</span></span>