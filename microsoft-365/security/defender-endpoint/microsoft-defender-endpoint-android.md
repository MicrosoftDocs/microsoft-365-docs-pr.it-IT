---
title: Microsoft Defender per Endpoint su Android
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender per Endpoint in Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installazione, distribuzione, disinstallazione, intune
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
ms.openlocfilehash: ceccd9e3c8a8137f672e7be519675034a84c7881
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055115"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="abc26-104">Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="abc26-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="abc26-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="abc26-105">**Applies to:**</span></span>
- [<span data-ttu-id="abc26-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="abc26-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="abc26-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abc26-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="abc26-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="abc26-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="abc26-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="abc26-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="abc26-110">Questo argomento descrive come installare, configurare, aggiornare e usare Defender per Endpoint in Android.</span><span class="sxs-lookup"><span data-stu-id="abc26-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="abc26-111">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Defender per Endpoint su Android può causare problemi di prestazioni ed errori di sistema imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="abc26-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="abc26-112">Come installare Microsoft Defender per Endpoint in Android</span><span class="sxs-lookup"><span data-stu-id="abc26-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="abc26-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="abc26-113">Prerequisites</span></span>

-   <span data-ttu-id="abc26-114">**Per gli utenti finali**</span><span class="sxs-lookup"><span data-stu-id="abc26-114">**For end users**</span></span>

    -   <span data-ttu-id="abc26-115">Licenza di Microsoft Defender for Endpoint assegnata agli utenti finali dell'app.</span><span class="sxs-lookup"><span data-stu-id="abc26-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="abc26-116">Vedere [Requisiti di licenza di Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="abc26-116">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="abc26-117">Portale aziendale Intune'app può essere scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) ed è disponibile nel dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="abc26-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="abc26-118">Inoltre, i dispositivi possono [](/mem/intune/user-help/enroll-device-android-company-portal) essere registrati tramite l'app Portale aziendale Intune per applicare i criteri di conformità dei dispositivi intune.</span><span class="sxs-lookup"><span data-stu-id="abc26-118">Additionally, device(s) can be [enrolled](/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="abc26-119">Ciò richiede che all'utente finale sia assegnata una Microsoft Intune licenza.</span><span class="sxs-lookup"><span data-stu-id="abc26-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="abc26-120">Per ulteriori informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="abc26-120">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="abc26-121">**Per gli amministratori**</span><span class="sxs-lookup"><span data-stu-id="abc26-121">**For Administrators**</span></span>

    -   <span data-ttu-id="abc26-122">Accesso al Microsoft Defender Security Center portale.</span><span class="sxs-lookup"><span data-stu-id="abc26-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="abc26-123">Microsoft Intune è l'unica soluzione MDM (Mobile Device Management) supportata per la distribuzione di Microsoft Defender per Endpoint in Android.</span><span class="sxs-lookup"><span data-stu-id="abc26-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="abc26-124">Attualmente sono supportati solo i dispositivi registrati per l'applicazione di Defender per Endpoint nei criteri di conformità dei dispositivi correlati ad Android in Intune.</span><span class="sxs-lookup"><span data-stu-id="abc26-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="abc26-125">Accedere [Microsoft Endpoint Manager'interfaccia di](https://go.microsoft.com/fwlink/?linkid=2109431)amministrazione , per distribuire l'app ai gruppi di utenti registrati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abc26-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="abc26-126">Requisiti di rete</span><span class="sxs-lookup"><span data-stu-id="abc26-126">Network Requirements</span></span>

- <span data-ttu-id="abc26-127">Perché Microsoft Defender for Endpoint su Android funzioni quando si è connessi a una rete, sarà necessario configurare il firewall/proxy per consentire l'accesso a Microsoft Defender per gli URL del servizio [endpoint.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="abc26-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="abc26-128">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="abc26-128">System Requirements</span></span>

-   <span data-ttu-id="abc26-129">Telefoni cellulari con Android 6.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="abc26-129">Mobile phones running Android 6.0 and above.</span></span> <span data-ttu-id="abc26-130">**I tablet e altri dispositivi mobili che eseguono Android non sono attualmente supportati.**</span><span class="sxs-lookup"><span data-stu-id="abc26-130">**Tablets and other mobile devices running Android are not currently supported.**</span></span> 

-   <span data-ttu-id="abc26-131">Portale aziendale Intune'app viene scaricata [da Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e installata.</span><span class="sxs-lookup"><span data-stu-id="abc26-131">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="abc26-132">La registrazione dei dispositivi è necessaria per applicare i criteri di conformità dei dispositivi di Intune.</span><span class="sxs-lookup"><span data-stu-id="abc26-132">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="abc26-133">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="abc26-133">Installation instructions</span></span>

<span data-ttu-id="abc26-134">Microsoft Defender per Endpoint su Android supporta l'installazione in entrambe le modalità dei dispositivi registrati, l'amministratore dei dispositivi legacy e le modalità Enterprise Android.</span><span class="sxs-lookup"><span data-stu-id="abc26-134">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="abc26-135">**Attualmente, i dispositivi di proprietà personale con profilo di lavoro e le registrazioni di dispositivi utente completamente gestiti di proprietà aziendale sono supportati in Android Enterprise. Il supporto per altre modalità Enterprise Android verrà annunciato quando sarà pronto.**</span><span class="sxs-lookup"><span data-stu-id="abc26-135">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="abc26-136">La distribuzione di Microsoft Defender per Endpoint su Android è tramite Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="abc26-136">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="abc26-137">Per altre informazioni, vedi [Distribuire Microsoft Defender per Endpoint su Android con Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="abc26-137">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="abc26-138">**Microsoft Defender per Endpoint su Android è ora disponibile su [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="abc26-138">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="abc26-139">Puoi connetterti a Google Play da Intune per distribuire l'app Microsoft Defender for Endpoint, tra le modalità di entrollment di Amministratore dispositivi e Android Enterprise di entrollment.</span><span class="sxs-lookup"><span data-stu-id="abc26-139">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="abc26-140">Come configurare Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="abc26-140">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="abc26-141">Le indicazioni su come configurare Le funzionalità di Microsoft Defender per Endpoint su Android sono disponibili in [Configure Microsoft Defender for Endpoint on Android features.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="abc26-141">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="abc26-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="abc26-142">Related topics</span></span>
- [<span data-ttu-id="abc26-143">Distribuzione di Microsoft Defender per Endpoint per Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="abc26-143">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="abc26-144">Configurare funzionalità di Microsoft Defender per Endpoint su funzionalità Android</span><span class="sxs-lookup"><span data-stu-id="abc26-144">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

