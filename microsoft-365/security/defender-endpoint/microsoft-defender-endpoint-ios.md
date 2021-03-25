---
title: Panoramica di Microsoft Defender ATP per iOS
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender ATP per iOS
keywords: microsoft, defender, atp, ios, panoramica, installazione, distribuzione, disinstallazione, intune
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
ms.openlocfilehash: 6e5aae9dcb361caf9133c1270a16711fc43033bb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066285"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="2dbab-104">Microsoft Defender for Endpoint per iOS</span><span class="sxs-lookup"><span data-stu-id="2dbab-104">Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2dbab-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2dbab-105">**Applies to:**</span></span>
- [<span data-ttu-id="2dbab-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2dbab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2dbab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2dbab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2dbab-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2dbab-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2dbab-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2dbab-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2dbab-110">**Microsoft Defender for Endpoint per iOS** offrirà protezione da phishing e connessioni di rete non sicure da siti Web, messaggi di posta elettronica e app.</span><span class="sxs-lookup"><span data-stu-id="2dbab-110">**Microsoft Defender for Endpoint for iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="2dbab-111">Tutti gli avvisi saranno disponibili tramite un singolo riquadro di vetro in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="2dbab-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="2dbab-112">Il portale offre ai team di sicurezza una visualizzazione centralizzata delle minacce nei dispositivi iOS insieme ad altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="2dbab-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="2dbab-113">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender for Endpoint per iOS può causare problemi di prestazioni ed errori di sistema imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="2dbab-113">Running other third-party endpoint protection products alongside Defender for Endpoint for iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="2dbab-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2dbab-114">Pre-requisites</span></span>

<span data-ttu-id="2dbab-115">**Per gli utenti finali**</span><span class="sxs-lookup"><span data-stu-id="2dbab-115">**For End Users**</span></span>

- <span data-ttu-id="2dbab-116">Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app.</span><span class="sxs-lookup"><span data-stu-id="2dbab-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="2dbab-117">Vedi [Requisiti di licenza per Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="2dbab-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="2dbab-118">I dispositivi vengono registrati tramite [l'app](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Portale aziendale intune per applicare i criteri di conformità dei dispositivi intune.</span><span class="sxs-lookup"><span data-stu-id="2dbab-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="2dbab-119">Ciò richiede che all'utente finale sia assegnata una licenza di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2dbab-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="2dbab-120">L'app Portale aziendale intune può essere scaricata [dall'App Store di Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="2dbab-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="2dbab-121">Nota che Apple non consente di reindirizzare gli utenti a scaricare altre app dall'App Store e quindi questo passaggio deve essere eseguito dall'utente prima dell'onboarding nell'app Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2dbab-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="2dbab-122">Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="2dbab-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="2dbab-123">**Per gli amministratori**</span><span class="sxs-lookup"><span data-stu-id="2dbab-123">**For Administrators**</span></span>

- <span data-ttu-id="2dbab-124">Accesso al portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="2dbab-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2dbab-125">Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender for Endpoint per iOS.</span><span class="sxs-lookup"><span data-stu-id="2dbab-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for iOS.</span></span> <span data-ttu-id="2dbab-126">Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender for Endpoint per i criteri di conformità dei dispositivi correlati a iOS in Intune.</span><span class="sxs-lookup"><span data-stu-id="2dbab-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint for iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="2dbab-127">Accesso [all'interfaccia di amministrazione di Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2dbab-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="2dbab-128">**Requisiti di sistema**</span><span class="sxs-lookup"><span data-stu-id="2dbab-128">**System Requirements**</span></span>

- <span data-ttu-id="2dbab-129">Dispositivi iOS che eseguono iOS 11.0 e superiori.</span><span class="sxs-lookup"><span data-stu-id="2dbab-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="2dbab-130">I dispositivi iPad sono ufficialmente supportati dalla versione 1.1.15010101 e così via.</span><span class="sxs-lookup"><span data-stu-id="2dbab-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="2dbab-131">Il dispositivo viene registrato con [l'app Portale aziendale intune](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span><span class="sxs-lookup"><span data-stu-id="2dbab-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="2dbab-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) per iOS è ora disponibile su [Apple App Store.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="2dbab-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="2dbab-133">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="2dbab-133">Installation instructions</span></span>

<span data-ttu-id="2dbab-134">La distribuzione di Microsoft Defender per Endpoint per iOS è tramite Microsoft Intune (MDM) e sono supportati sia i dispositivi supervisionati che i dispositivi senza supervisione.</span><span class="sxs-lookup"><span data-stu-id="2dbab-134">Deployment of Microsoft Defender for Endpoint for iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="2dbab-135">Per altre informazioni, vedi [Distribuire Microsoft Defender for Endpoint per iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="2dbab-135">For more information, see [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="2dbab-136">Risorse</span><span class="sxs-lookup"><span data-stu-id="2dbab-136">Resources</span></span>

- <span data-ttu-id="2dbab-137">Rimanere informati sulle prossime versioni visitando il [nostro blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="2dbab-137">Stay informed about upcoming releases by visiting our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="2dbab-138">Fornire feedback tramite il sistema di feedback in-app o tramite [il portale SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2dbab-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="2dbab-139">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2dbab-139">Next steps</span></span>

- [<span data-ttu-id="2dbab-140">Distribuire Microsoft Defender per Endpoint per iOS</span><span class="sxs-lookup"><span data-stu-id="2dbab-140">Deploy Microsoft Defender for Endpoint for iOS</span></span>](ios-install.md)
- [<span data-ttu-id="2dbab-141">Configurare Le funzionalità di Microsoft Defender per Endpoint per iOS</span><span class="sxs-lookup"><span data-stu-id="2dbab-141">Configure Microsoft Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)