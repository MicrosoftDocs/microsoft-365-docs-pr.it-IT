---
title: Microsoft Defender per endpoint su iOS
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender for Endpoint in iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, panoramica, installazione, distribuzione, disinstallazione, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a051742775c3d4e8b36bf0ba7a4fd2502763014
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694462"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="f24d5-104">Microsoft Defender per endpoint su iOS</span><span class="sxs-lookup"><span data-stu-id="f24d5-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f24d5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f24d5-105">**Applies to:**</span></span>
- [<span data-ttu-id="f24d5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f24d5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f24d5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f24d5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f24d5-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f24d5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f24d5-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f24d5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f24d5-110">**Microsoft Defender for Endpoint su iOS** offrirà protezione da phishing e connessioni di rete non sicure da siti Web, messaggi di posta elettronica e app.</span><span class="sxs-lookup"><span data-stu-id="f24d5-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="f24d5-111">Tutti gli avvisi saranno disponibili tramite un singolo riquadro di vetro nella Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="f24d5-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f24d5-112">Il portale offre ai team di sicurezza una visualizzazione centralizzata delle minacce nei dispositivi iOS insieme ad altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="f24d5-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="f24d5-113">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender for Endpoint in iOS può causare problemi di prestazioni ed errori di sistema imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="f24d5-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="f24d5-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f24d5-114">Pre-requisites</span></span>

<span data-ttu-id="f24d5-115">**Per gli utenti finali**</span><span class="sxs-lookup"><span data-stu-id="f24d5-115">**For End Users**</span></span>

- <span data-ttu-id="f24d5-116">Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app.</span><span class="sxs-lookup"><span data-stu-id="f24d5-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="f24d5-117">Vedi [Requisiti di licenza per Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f24d5-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="f24d5-118">I dispositivi vengono registrati tramite [l'app](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Portale aziendale Intune per applicare i criteri di conformità dei dispositivi intune.</span><span class="sxs-lookup"><span data-stu-id="f24d5-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="f24d5-119">Ciò richiede che all'utente finale sia assegnata una Microsoft Intune licenza.</span><span class="sxs-lookup"><span data-stu-id="f24d5-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="f24d5-120">Portale aziendale Intune'app può essere scaricata [dall'Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="f24d5-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="f24d5-121">Nota che Apple non consente di reindirizzare gli utenti a scaricare altre app dall'App Store e quindi questo passaggio deve essere eseguito dall'utente prima dell'onboarding nell'app Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f24d5-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="f24d5-122">Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="f24d5-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="f24d5-123">**Per gli amministratori**</span><span class="sxs-lookup"><span data-stu-id="f24d5-123">**For Administrators**</span></span>

- <span data-ttu-id="f24d5-124">Accesso al Microsoft Defender Security Center portale.</span><span class="sxs-lookup"><span data-stu-id="f24d5-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f24d5-125">Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender for Endpoint in iOS.</span><span class="sxs-lookup"><span data-stu-id="f24d5-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="f24d5-126">Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender for Endpoint nei criteri di conformità dei dispositivi correlati a iOS in Intune.</span><span class="sxs-lookup"><span data-stu-id="f24d5-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint on iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="f24d5-127">Accesso a [Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431), per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f24d5-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="f24d5-128">**Requisiti di sistema**</span><span class="sxs-lookup"><span data-stu-id="f24d5-128">**System Requirements**</span></span>

- <span data-ttu-id="f24d5-129">Dispositivi iOS che eseguono iOS 11.0 e superiori.</span><span class="sxs-lookup"><span data-stu-id="f24d5-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="f24d5-130">iPad sono ufficialmente supportati dalla versione 1.1.15010101 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f24d5-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="f24d5-131">Il dispositivo viene [](https://apps.apple.com/us/app/intune-company-portal/id719171358)registrato con l Portale aziendale Intune app .</span><span class="sxs-lookup"><span data-stu-id="f24d5-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="f24d5-132">**Microsoft Defender per Endpoint su iOS è disponibile su [Apple App Store.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="f24d5-132">**Microsoft Defender for Endpoint on iOS is available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="f24d5-133">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="f24d5-133">Installation instructions</span></span>

<span data-ttu-id="f24d5-134">La distribuzione di Microsoft Defender per Endpoint su iOS è tramite Microsoft Intune (MDM) e sono supportati sia i dispositivi supervisionati che i dispositivi non supervisionati.</span><span class="sxs-lookup"><span data-stu-id="f24d5-134">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="f24d5-135">Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint in iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="f24d5-135">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="f24d5-136">Risorse</span><span class="sxs-lookup"><span data-stu-id="f24d5-136">Resources</span></span>

- <span data-ttu-id="f24d5-137">Rimanere informati sulle prossime versioni [visitando Novità di Microsoft Defender per Endpoint su iOS](ios-whatsnew.md) o il [nostro blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="f24d5-137">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="f24d5-138">Fornire feedback tramite il sistema di feedback in-app o tramite [il portale SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f24d5-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="f24d5-139">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f24d5-139">Next steps</span></span>

- [<span data-ttu-id="f24d5-140">Distribuire Microsoft Defender per Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="f24d5-140">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="f24d5-141">Configurare Microsoft Defender per le funzionalità di Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="f24d5-141">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
