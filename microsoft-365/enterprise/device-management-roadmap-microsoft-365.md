---
title: Roadmap di gestione dei dispositivi per Microsoft 365
keywords: Microsoft 365, Microsoft 365 per le aziende, documentazione di Microsoft 365, gestione dei dispositivi mobili, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Guida di orientamento per configurare la gestione dei dispositivi per Microsoft 365.
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749540"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="df08b-104">Roadmap di gestione dei dispositivi per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df08b-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="df08b-105">Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e le relative app all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df08b-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="df08b-106">La gestione dei dispositivi mobili consente di proteggere e proteggere le risorse dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df08b-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="df08b-107">Esistono due opzioni per la gestione dei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="df08b-107">There are two options for device management:</span></span>

- [<span data-ttu-id="df08b-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="df08b-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="df08b-109">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="df08b-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="df08b-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="df08b-110">Microsoft Intune</span></span>

<span data-ttu-id="df08b-111">È possibile usare Microsoft Intune per gestire l'accesso all'organizzazione tramite la gestione dei dispositivi mobili o delle applicazioni mobili.</span><span class="sxs-lookup"><span data-stu-id="df08b-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="df08b-112">La gestione dei dispositivi mobili si verifica quando gli utenti "registrano" i propri dispositivi in Intune.</span><span class="sxs-lookup"><span data-stu-id="df08b-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="df08b-113">Dopo la registrazione di un dispositivo, si tratta di un dispositivo gestito. pertanto, può ricevere i criteri, le regole e le impostazioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df08b-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="df08b-114">Ad esempio, puoi installare app specifiche, creare criteri password, installare una connessione VPN e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="df08b-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="df08b-115">Gli utenti con i propri dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df08b-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="df08b-116">È comunque necessario proteggere le risorse e i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df08b-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="df08b-117">In questo scenario puoi proteggere le tue app usando la gestione delle applicazioni per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="df08b-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="df08b-118">Ad esempio, è possibile utilizzare un criterio di gestione delle applicazioni per dispositivi mobili che richiede a un utente di immettere un PIN quando accede a SharePoint Online nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df08b-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="df08b-119">Potrai anche determinare come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df08b-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="df08b-120">Potresti voler trattare i dispositivi in modo diverso, a seconda del loro uso.</span><span class="sxs-lookup"><span data-stu-id="df08b-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="df08b-121">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="df08b-121">Basic Mobility and Security</span></span>

<span data-ttu-id="df08b-122">Questo è integrato in Microsoft 365 e consente di proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e Telefoni Windows.</span><span class="sxs-lookup"><span data-stu-id="df08b-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="df08b-123">È possibile creare e gestire criteri di sicurezza, cancellare tutti i dati in remoto e visualizzare report dettagliati sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="df08b-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="df08b-124">Scegliere tra le due opzioni</span><span class="sxs-lookup"><span data-stu-id="df08b-124">Choose between the two options</span></span>

<span data-ttu-id="df08b-125">Per una migliore valutazione dell'opzione di gestione dei dispositivi più adatta, vedere Scegliere tra [Basic Mobility Security e Intune.](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)</span><span class="sxs-lookup"><span data-stu-id="df08b-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="df08b-126">In base alla valutazione, inizia a gestire i dispositivi con:</span><span class="sxs-lookup"><span data-stu-id="df08b-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="df08b-127">Intune</span><span class="sxs-lookup"><span data-stu-id="df08b-127">Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="df08b-128">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="df08b-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="df08b-129">Consigli sull’identità e sull’accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="df08b-129">Identity and device access recommendations</span></span>

<span data-ttu-id="df08b-130">Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo.</span><span class="sxs-lookup"><span data-stu-id="df08b-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="df08b-131">Per l'accesso ai dispositivi, usa i suggerimenti e le impostazioni in questi articoli:</span><span class="sxs-lookup"><span data-stu-id="df08b-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="df08b-132">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="df08b-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="df08b-133">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="df08b-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="df08b-134">Come Contoso ha fatto la gestione dei dispositivi per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df08b-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="df08b-135">Per informazioni su come un'azienda multinazionale fittizia ma rappresentativa ha distribuito l'infrastruttura di gestione dei dispositivi mobili con i servizi cloud di Microsoft 365, vedere Gestione dei dispositivi mobili [per Contoso.](contoso-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="df08b-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
