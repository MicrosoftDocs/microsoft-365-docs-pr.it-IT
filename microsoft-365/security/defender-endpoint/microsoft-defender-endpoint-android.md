---
title: Microsoft Defender ATP su Android
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender ATP per Android
keywords: microsoft, defender, atp, android, installazione, distribuire, disinstallazione, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 32c42691b3a2b43f9740da26084bf45af0ee80f5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687782"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="5310b-104">Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="5310b-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5310b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5310b-105">**Applies to:**</span></span>
- [<span data-ttu-id="5310b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5310b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5310b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5310b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5310b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5310b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5310b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5310b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5310b-110">Questo argomento descrive come installare, configurare, aggiornare e usare Defender per Endpoint per Android.</span><span class="sxs-lookup"><span data-stu-id="5310b-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="5310b-111">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender per Endpoint per Android può causare problemi di prestazioni ed errori di sistema imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="5310b-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="5310b-112">Come installare Microsoft Defender per Endpoint in Android</span><span class="sxs-lookup"><span data-stu-id="5310b-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="5310b-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5310b-113">Prerequisites</span></span>

-   <span data-ttu-id="5310b-114">**Per gli utenti finali**</span><span class="sxs-lookup"><span data-stu-id="5310b-114">**For end users**</span></span>

    -   <span data-ttu-id="5310b-115">Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app.</span><span class="sxs-lookup"><span data-stu-id="5310b-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="5310b-116">Vedere [Requisiti di licenza di Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="5310b-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="5310b-117">L'app Portale aziendale intune può essere scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) ed è disponibile nel dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="5310b-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="5310b-118">Inoltre, i dispositivi possono [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) essere registrati tramite l'app Portale aziendale intune per applicare i criteri di conformità dei dispositivi intune.</span><span class="sxs-lookup"><span data-stu-id="5310b-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="5310b-119">Ciò richiede che all'utente finale sia assegnata una licenza di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5310b-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="5310b-120">Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="5310b-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="5310b-121">**Per gli amministratori**</span><span class="sxs-lookup"><span data-stu-id="5310b-121">**For Administrators**</span></span>

    -   <span data-ttu-id="5310b-122">Accesso al portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="5310b-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5310b-123">Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender per Endpoint in Android.</span><span class="sxs-lookup"><span data-stu-id="5310b-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="5310b-124">Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender per Endpoint per i criteri di conformità dei dispositivi android correlati in Intune.</span><span class="sxs-lookup"><span data-stu-id="5310b-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="5310b-125">Accedere [all'interfaccia di amministrazione di Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5310b-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="5310b-126">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="5310b-126">System Requirements</span></span>

-   <span data-ttu-id="5310b-127">Dispositivi Android che eseguono Android 6.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="5310b-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="5310b-128">L'app Portale aziendale intune viene scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e installata.</span><span class="sxs-lookup"><span data-stu-id="5310b-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="5310b-129">La registrazione dei dispositivi è necessaria per applicare i criteri di conformità dei dispositivi di Intune.</span><span class="sxs-lookup"><span data-stu-id="5310b-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="5310b-130">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="5310b-130">Installation instructions</span></span>

<span data-ttu-id="5310b-131">Microsoft Defender per Endpoint su Android supporta l'installazione in entrambe le modalità dei dispositivi registrati, le modalità Legacy Device Administrator e Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5310b-131">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="5310b-132">**Attualmente, i dispositivi di proprietà personale con profilo di lavoro e registrazioni di dispositivi utente completamente gestiti di proprietà aziendale sono supportati in Android Enterprise. Il supporto per altre modalità Android Enterprise verrà annunciato quando sarà pronto.**</span><span class="sxs-lookup"><span data-stu-id="5310b-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="5310b-133">La distribuzione di Microsoft Defender per Endpoint su Android è tramite Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="5310b-133">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="5310b-134">Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint su Android con Microsoft Intune.](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="5310b-134">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="5310b-135">**Microsoft Defender per Endpoint su Android è ora disponibile su [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="5310b-135">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="5310b-136">Puoi connetterti a Google Play da Intune per distribuire l'app Microsoft Defender for Endpoint, tra le modalità amministratore del dispositivo e entrollment Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5310b-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="5310b-137">Come configurare Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="5310b-137">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="5310b-138">Le indicazioni su come configurare Le funzionalità di Microsoft Defender per Endpoint su Android sono disponibili in [Configure Microsoft Defender for Endpoint on Android features.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="5310b-138">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="5310b-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5310b-139">Related topics</span></span>
- [<span data-ttu-id="5310b-140">Distribuire Microsoft Defender per Endpoint su Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5310b-140">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="5310b-141">Configurare Le funzionalità di Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="5310b-141">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

