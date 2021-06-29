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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194854"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="7950a-104">Microsoft Defender per endpoint su iOS</span><span class="sxs-lookup"><span data-stu-id="7950a-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7950a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7950a-105">**Applies to:**</span></span>
- [<span data-ttu-id="7950a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="7950a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7950a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7950a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7950a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7950a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7950a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7950a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7950a-110">**Microsoft Defender for Endpoint su iOS** offre protezione da phishing e connessioni di rete non sicure da siti Web, messaggi di posta elettronica e app.</span><span class="sxs-lookup"><span data-stu-id="7950a-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="7950a-111">Tutti gli avvisi saranno disponibili tramite un singolo riquadro di vetro nella Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="7950a-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="7950a-112">Il portale offre ai team di sicurezza una visualizzazione centralizzata delle minacce nei dispositivi iOS insieme ad altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="7950a-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="7950a-113">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender for Endpoint in iOS può causare problemi di prestazioni ed errori di sistema imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="7950a-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="7950a-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7950a-114">Pre-requisites</span></span>

<span data-ttu-id="7950a-115">**Per gli utenti finali**</span><span class="sxs-lookup"><span data-stu-id="7950a-115">**For End Users**</span></span>

- <span data-ttu-id="7950a-116">Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app.</span><span class="sxs-lookup"><span data-stu-id="7950a-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="7950a-117">Vedi [Requisiti di licenza per Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="7950a-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="7950a-118">**Per i dispositivi registrati:** i [](/mem/intune/user-help/enroll-your-device-in-intune-ios) dispositivi vengono registrati tramite l'app Portale aziendale Intune per applicare i criteri di conformità dei dispositivi intune.</span><span class="sxs-lookup"><span data-stu-id="7950a-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="7950a-119">Ciò richiede che all'utente finale sia assegnata una Microsoft Intune licenza.</span><span class="sxs-lookup"><span data-stu-id="7950a-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="7950a-120">Portale aziendale Intune'app può essere scaricata [dall'Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="7950a-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="7950a-121">Nota che Apple non consente di reindirizzare gli utenti a scaricare altre app dall'App Store e quindi questo passaggio deve essere eseguito dall'utente prima dell'onboarding nell'app Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7950a-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="7950a-122">**Per i dispositivi non registrati:** i dispositivi vengono registrati con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7950a-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="7950a-123">Ciò richiede che l'utente finale sia connesso [tramite Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="7950a-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="7950a-124">Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="7950a-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="7950a-125">**Per gli amministratori**</span><span class="sxs-lookup"><span data-stu-id="7950a-125">**For Administrators**</span></span>

- <span data-ttu-id="7950a-126">Accesso al Microsoft Defender Security Center portale.</span><span class="sxs-lookup"><span data-stu-id="7950a-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="7950a-127">Accesso a [Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431), per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7950a-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7950a-128">Microsoft Intune è l'unica soluzione UEM (Unified Endpoint Management) supportata per la distribuzione di Microsoft Defender for Endpoint e l'applicazione di Defender per i criteri di conformità dei dispositivi correlati all'endpoint in Intune.</span><span class="sxs-lookup"><span data-stu-id="7950a-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="7950a-129">**Requisiti di sistema**</span><span class="sxs-lookup"><span data-stu-id="7950a-129">**System Requirements**</span></span>

- <span data-ttu-id="7950a-130">Dispositivo iOS che esegue iOS 11.0 e successive.</span><span class="sxs-lookup"><span data-stu-id="7950a-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="7950a-131">iPad sono ufficialmente supportati dalla versione 1.1.15010101 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7950a-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="7950a-132">Il dispositivo viene registrato con [l'app Portale aziendale Intune](https://apps.apple.com/us/app/intune-company-portal/id719171358) o registrato con Azure Active Directory tramite [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="7950a-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="7950a-133">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="7950a-133">Installation instructions</span></span>

<span data-ttu-id="7950a-134">La distribuzione di Microsoft Defender per Endpoint su iOS può essere eseguita tramite Microsoft Endpoint Manager (MEM) e sono supportati sia i dispositivi supervisionati che i dispositivi senza supervisione.</span><span class="sxs-lookup"><span data-stu-id="7950a-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="7950a-135">Gli utenti finali possono anche installare direttamente l'app [dall'App Store di Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="7950a-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="7950a-136">Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint in iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="7950a-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="7950a-137">Risorse</span><span class="sxs-lookup"><span data-stu-id="7950a-137">Resources</span></span>

- <span data-ttu-id="7950a-138">Rimanere informati sulle prossime versioni [visitando Novità di Microsoft Defender per Endpoint su iOS](ios-whatsnew.md) o il [nostro blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="7950a-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="7950a-139">Fornire feedback tramite il sistema di feedback in-app o tramite [il portale SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="7950a-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="7950a-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7950a-140">Next steps</span></span>

- [<span data-ttu-id="7950a-141">Distribuire Microsoft Defender per Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="7950a-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="7950a-142">Configurare Microsoft Defender per le funzionalità di Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="7950a-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
