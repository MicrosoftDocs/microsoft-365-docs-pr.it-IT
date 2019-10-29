---
title: Infrastruttura di Windows 10 Enterprise per Microsoft 365 Enterprise
description: Fornisce una guida di alto livello sui passaggi necessari per distribuire Windows 10 Enterprise sui PC come parte di Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, distribuzione
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: b1f655e5befd16058870542f2e595d36599006fd
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746708"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="c4fe8-104">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4fe8-104">Phase 3: Windows 10 Enterprise</span></span>

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="c4fe8-106">Microsoft 365 Enterprise include Windows 10 Enterprise, che offre gli strumenti per fare di più e mantenere la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="c4fe8-107">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="c4fe8-108">**È integrato per semplicità** : sfrutta la potenza del cloud per contribuire a ridurre la complessità della gestione dell'ambiente dei dispositivi IT moderni di oggi, indipendentemente dalle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="c4fe8-109">**Sicurezza intelligente** : è la versione più sicura di Windows mai, con funzionalità di sicurezza intelligenti progettate per collaborare per una migliore protezione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="c4fe8-110">**Consente la creatività** e il lavoro di squadra: Sblocca la creatività e il lavoro di squadra per offrire un'esperienza più produttiva che sia gli utenti che lo ameranno.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="c4fe8-111">È necessario comprendere i diversi modi in cui è possibile distribuire il sistema operativo Windows 10 e scegliere quello giusto per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="c4fe8-112">A seconda dell'abbonamento a Microsoft 365 Enterprise, esistono anche servizi e funzionalità di sicurezza di Windows 10 che è necessario configurare per ottenere il massimo da Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="c4fe8-113">Per distribuire insieme Windows 10 Enterprise e Office 365 ProPlus e passare a un [desktop moderno](https://www.microsoft.com/microsoft-365/modern-desktop), vedere il [Centro di distribuzione desktop moderno](https://aka.ms/howtoshift).</span><span class="sxs-lookup"><span data-stu-id="c4fe8-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="c4fe8-114">Distribuzione di Windows 10</span><span class="sxs-lookup"><span data-stu-id="c4fe8-114">Windows 10 deployment</span></span>

<span data-ttu-id="c4fe8-115">È possibile distribuire Windows 10 Enterprise per l'organizzazione in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="c4fe8-116">Di seguito viene illustrato come configurare e distribuire un'immagine di Windows 10 Enterprise tramite questi scenari di distribuzione moderni.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="c4fe8-117">Scenario di distribuzione</span><span class="sxs-lookup"><span data-stu-id="c4fe8-117">Deployment scenario</span></span> | <span data-ttu-id="c4fe8-118">Quando usarlo</span><span class="sxs-lookup"><span data-stu-id="c4fe8-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="c4fe8-119">Utilizzo di System Center Configuration Manager come aggiornamento sul posto</span><span class="sxs-lookup"><span data-stu-id="c4fe8-119">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="c4fe8-120">Selezionare questa opzione se è necessario aggiornare i computer Windows 7 o Windows 8,1 alla <a href="https://aka.ms/windows-10-release-information" target="_blank">versione corrente</a> di Windows 10 Enterprise e i computer sono attualmente gestiti con <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current Branch)</a>.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="c4fe8-121">Utilizzo di Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="c4fe8-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="c4fe8-122">Selezionare questa opzione se si stanno configurando nuovi computer Windows che dispongono di Windows 10 Enterprise, versione 1703 o successiva preinstallata.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="c4fe8-123">Gli utenti finali avvierà il programma di installazione utilizzando la configurazione desiderata immettendo le proprie credenziali dell'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="c4fe8-124">Se questi scenari di distribuzione non soddisfano le esigenze dell'organizzazione, è possibile conoscere altri scenari e comprendere le funzionalità e le limitazioni di ognuno negli [scenari di distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="c4fe8-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="c4fe8-125">È anche possibile <a href="https://aka.ms/planforwin10deployment" target="_blank">pianificare la distribuzione di Windows 10</a> autonomamente.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="c4fe8-126">Per ulteriori informazioni su Windows 10, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4fe8-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="c4fe8-127">Pagina del prodotto Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4fe8-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="c4fe8-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c4fe8-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="c4fe8-129">Distribuire e aggiornare Windows 10</span><span class="sxs-lookup"><span data-stu-id="c4fe8-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="c4fe8-130">Servizi e funzionalità aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="c4fe8-130">Additional services and features</span></span>
<span data-ttu-id="c4fe8-131">Nell'ambito della distribuzione di Windows 10 Enterprise, è possibile aggiungere questi servizi e funzionalità aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="c4fe8-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="c4fe8-132">Windows Analytics</span></span>

<span data-ttu-id="c4fe8-133">Windows utilizza i dati di diagnostica per fornire informazioni dettagliate, utili per ottenere approfondimenti sull'efficienza operativa e sull'integrità dei dispositivi Windows 10 nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="c4fe8-134">Preparazione per l'aggiornamento: la preparazione all'aggiornamento consente di passare a Windows 10 e di rimanere aggiornati con i nuovi aggiornamenti delle funzionalità di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="c4fe8-135">Update Compliance-la conformità degli aggiornamenti è destinata all'amministratore IT che desidera ottenere una visione olistica di tutti i dispositivi Windows 10, senza ulteriori requisiti di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="c4fe8-136">Integrità del dispositivo: è possibile utilizzare l'integrità del dispositivo per rilevare e correggere in modo proattivo i problemi di impatto dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="c4fe8-137">Per ulteriori informazioni, vedere [Panoramica di Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .</span><span class="sxs-lookup"><span data-stu-id="c4fe8-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="c4fe8-138">Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="c4fe8-138">Windows security</span></span>

<span data-ttu-id="c4fe8-139">Windows 10 fornisce funzionalità che consentono di proteggere le minacce, la protezione dei dispositivi e la guida per il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="c4fe8-140">Con Windows 10, è possibile ottenere funzionalità di sicurezza critiche che proteggono il dispositivo fin dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="c4fe8-141">Microsoft 365 E3 aggiunge funzionalità di sicurezza quali Windows Hello for business, Windows Defender Application Control e Windows Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="c4fe8-142">Con Microsoft 365 E5, è possibile ottenere tutta la protezione dalla sicurezza di Microsoft 365 E3 oltre alle funzionalità di sicurezza basate sul cloud e Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c4fe8-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="c4fe8-143">Per ulteriori informazioni sulle funzionalità di sicurezza disponibili con Windows 10 Enterprise e su come è possibile distribuire, gestire, configurare e risolvere i problemi relativi a tre funzionalità di ecurity principali, vedere [passaggio 5: distribuire le funzionalità di sicurezza di Windows 10 Enterprise](windows10-enable-security-features.md).</span><span class="sxs-lookup"><span data-stu-id="c4fe8-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c4fe8-144">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4fe8-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c4fe8-145">Sbircia all'interno di Microsoft e Scopri come la società [ha distribuito Windows 10 Enterprise e utilizza Strong Authentication, Intune e Microsoft Defender ATP](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span><span class="sxs-lookup"><span data-stu-id="c4fe8-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c4fe8-146">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4fe8-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c4fe8-147">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha [distribuito Windows 10 Enterprise](contoso-win10.md).</span><span class="sxs-lookup"><span data-stu-id="c4fe8-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="c4fe8-149">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c4fe8-149">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="c4fe8-151">Preparare l'organizzazione per Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4fe8-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
