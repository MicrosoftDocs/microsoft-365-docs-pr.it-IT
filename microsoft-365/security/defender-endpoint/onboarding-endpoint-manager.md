---
title: Onboarding con Microsoft Endpoint Manager
description: Scopri come eseguire l'onboard in Microsoft Defender for Endpoint usando Microsoft Endpoint Manager
keywords: onboarding, configurazione, distribuzione, distribuzione, gestore endpoint, mdatp, protezione avanzata dalle minacce, creazione della raccolta, risposta al rilevamento degli endpoint, protezione di nuova generazione, riduzione della superficie di attacco, microsoft endpoint manager
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9edcceca2f6cc7c2377eb388d7394a23dfbae99d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186258"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="0a6c4-104">Onboarding con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0a6c4-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a6c4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a6c4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0a6c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0a6c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a6c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="0a6c4-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0a6c4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0a6c4-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="0a6c4-110">Questo articolo fa parte della guida alla distribuzione e funge da esempio di metodo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="0a6c4-111">[Nell'argomento Pianificazione](deployment-strategy.md) sono stati forniti diversi metodi per l'onboard dei dispositivi al servizio.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="0a6c4-112">In questo argomento viene illustrata l'architettura nativa del cloud.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="0a6c4-113">![Immagine dell'architettura nativa del cloud ](images/cloud-native-architecture.png)
 *Diagramma delle architetture di ambiente*</span><span class="sxs-lookup"><span data-stu-id="0a6c4-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="0a6c4-114">Mentre Defender for Endpoint supporta l'onboarding di diversi endpoint e strumenti, questo articolo non li copre.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="0a6c4-115">Per informazioni sull'onboarding generale con altri strumenti e metodi di distribuzione supportati, vedere [Panoramica dell'onboarding.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="0a6c4-116">[Microsoft Endpoint Manager è](https://docs.microsoft.com/mem/endpoint-manager-overview) una piattaforma di soluzioni che unifica diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="0a6c4-117">Include [Microsoft Intune per](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) la gestione dei dispositivi basata su cloud.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="0a6c4-118">In questo argomento vengono guidati gli utenti in:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-118">This topic guides users in:</span></span>
- <span data-ttu-id="0a6c4-119">Passaggio 1: Onboarding dei dispositivi al servizio creando un gruppo in Microsoft Endpoint Manager (MEM) su cui assegnare le configurazioni</span><span class="sxs-lookup"><span data-stu-id="0a6c4-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="0a6c4-120">Passaggio 2: Configurazione delle funzionalità di Defender for Endpoint tramite Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0a6c4-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="0a6c4-121">Queste indicazioni sull'onboarding illustrano i passaggi di base seguenti da eseguire quando si usa Microsoft Endpoint Manager:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="0a6c4-122">Identificazione dei dispositivi o degli utenti di destinazione</span><span class="sxs-lookup"><span data-stu-id="0a6c4-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="0a6c4-123">Creazione di un gruppo di Azure Active Directory (utente o dispositivo)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="0a6c4-124">Creazione di un profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="0a6c4-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="0a6c4-125">In Microsoft Endpoint Manager ti guideremo nella creazione di un criterio separato per ogni funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="0a6c4-126">Risorse</span><span class="sxs-lookup"><span data-stu-id="0a6c4-126">Resources</span></span>


<span data-ttu-id="0a6c4-127">Ecco i collegamenti necessari per il resto del processo:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="0a6c4-128">Portale MEM</span><span class="sxs-lookup"><span data-stu-id="0a6c4-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="0a6c4-129">Centro sicurezza PC</span><span class="sxs-lookup"><span data-stu-id="0a6c4-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="0a6c4-130">Linee di base della sicurezza di Intune</span><span class="sxs-lookup"><span data-stu-id="0a6c4-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="0a6c4-131">Per ulteriori informazioni su Microsoft Endpoint Manager, vedere queste risorse:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="0a6c4-132">Pagina Di Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0a6c4-132">Microsoft Endpoint Manager page</span></span>](https://docs.microsoft.com/mem/)
- [<span data-ttu-id="0a6c4-133">Post di blog sulla convergenza di Intune e ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="0a6c4-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="0a6c4-134">Video introduttivo su MEM</span><span class="sxs-lookup"><span data-stu-id="0a6c4-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="0a6c4-135">Passaggio 1: onboardare i dispositivi creando un gruppo in MEM su cui assegnare le configurazioni</span><span class="sxs-lookup"><span data-stu-id="0a6c4-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="0a6c4-136">Identificare i dispositivi o gli utenti di destinazione</span><span class="sxs-lookup"><span data-stu-id="0a6c4-136">Identify target devices or users</span></span>
<span data-ttu-id="0a6c4-137">In questa sezione verrà creato un gruppo di test a cui assegnare le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="0a6c4-138">Intune usa i gruppi di Azure Active Directory (Azure AD) per gestire dispositivi e utenti.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="0a6c4-139">Gli amministratori di Intune possono configurare i gruppi in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="0a6c4-140">Per altre informazioni, vedi [Aggiungere gruppi per organizzare utenti e dispositivi.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="0a6c4-141">Creare un gruppo</span><span class="sxs-lookup"><span data-stu-id="0a6c4-141">Create a group</span></span>

1.  <span data-ttu-id="0a6c4-142">Aprire il portale MEM.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="0a6c4-143">Aprire **Gruppi > Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-144">![Immagine del portale di Microsoft Endpoint Manager1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="0a6c4-145">Immettere i dettagli e creare un nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-146">![Immagine del portale di Microsoft Endpoint Manager2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="0a6c4-147">Aggiungi l'utente o il dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="0a6c4-148">Dal riquadro **Gruppi > Tutti i** gruppi, aprire il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="0a6c4-149">Selezionare  **Membri > Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="0a6c4-150">Trova l'utente o il dispositivo di test e selezionalo.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-151">![Immagine del portale di Microsoft Endpoint Manager3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="0a6c4-152">Il gruppo di test ora dispone di un membro da testare.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="0a6c4-153">Passaggio 2: Creare criteri di configurazione per configurare Le funzionalità di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0a6c4-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="0a6c4-154">Nella sezione seguente verranno creati diversi criteri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="0a6c4-155">In primo luogo, un criterio di configurazione consente di selezionare i gruppi di utenti o dispositivi di cui eseguire l'onboarded in Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="0a6c4-156">Rilevamento endpoint e risposta</span><span class="sxs-lookup"><span data-stu-id="0a6c4-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="0a6c4-157">Si continuerà quindi creando diversi tipi di criteri di sicurezza degli endpoint:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="0a6c4-158">Protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="0a6c4-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="0a6c4-159">Riduzione della superficie d'attacco</span><span class="sxs-lookup"><span data-stu-id="0a6c4-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="0a6c4-160">Rilevamento endpoint e risposta</span><span class="sxs-lookup"><span data-stu-id="0a6c4-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="0a6c4-161">Aprire il portale MEM.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="0a6c4-162">Passare a **Endpoint security > Endpoint detection and response**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="0a6c4-163">Fare clic **su Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-164">![Immagine del portale di Microsoft Endpoint Manager4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="0a6c4-165">In **Piattaforma seleziona Windows 10** e versioni successive, Profilo - Rilevamento e risposta endpoint > Crea .</span><span class="sxs-lookup"><span data-stu-id="0a6c4-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="0a6c4-166">Immettere un nome e una descrizione, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-167">![Immagine di Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="0a6c4-168">Selezionare le impostazioni in base alle esigenze, quindi **selezionare Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-169">![Immagine del portale di Microsoft Endpoint Manager6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a6c4-170">In questo caso, questo è stato popolato automaticamente come Defender per Endpoint è già stato integrato con Intune.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="0a6c4-171">Per altre informazioni sull'integrazione, vedi [Abilitare Microsoft Defender per Endpoint in Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="0a6c4-172">L'immagine seguente è un esempio di ciò che vedrai quando Microsoft Defender per Endpoint NON è integrato con Intune:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Immagine del portale di Microsoft Endpoint Manager7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="0a6c4-174">Aggiungere i tag di ambito, se necessario, quindi **selezionare Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-175">![Immagine del portale di Microsoft Endpoint Manager8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="0a6c4-176">Aggiungere un gruppo di test facendo clic su **Seleziona gruppi da includere** e scegliere il gruppo, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-177">![Immagine del portale di Microsoft Endpoint Manager9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="0a6c4-178">Rivedere e accettare, quindi selezionare  **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-179">![Immagine del portale di Microsoft Endpoint Manager10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="0a6c4-180">È possibile visualizzare i criteri completati.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-181">![Immagine del portale di Microsoft Endpoint Manager11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="0a6c4-182">Protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="0a6c4-182">Next-generation protection</span></span>

1.  <span data-ttu-id="0a6c4-183">Aprire il portale MEM.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="0a6c4-184">Passare a **Endpoint security > Antivirus > Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-185">![Immagine del portale di Microsoft Endpoint Manager12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="0a6c4-186">Seleziona **Piattaforma - Windows 10 e versioni successive - Windows e profilo - Microsoft Defender Antivirus > Crea**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="0a6c4-187">Immetti nome e descrizione, quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-188">![Immagine del portale di Microsoft Endpoint Manager13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="0a6c4-189">Nella pagina **Impostazioni di configurazione:** imposta le configurazioni necessarie per Microsoft Defender Antivirus (Protezione cloud, esclusioni, Real-Time Protection e correzione).</span><span class="sxs-lookup"><span data-stu-id="0a6c4-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-190">![Immagine del portale di Microsoft Endpoint Manager14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="0a6c4-191">Aggiungere i tag di ambito, se necessario, quindi **selezionare Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-192">![Immagine del portale di Microsoft Endpoint Manager15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="0a6c4-193">Selezionare i gruppi da includere, assegnarli al gruppo di test, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-194">![Immagine del portale di Microsoft Endpoint Manager16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="0a6c4-195">Rivedere e creare, quindi selezionare  **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-196">![Immagine del portale di Microsoft Endpoint Manager17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="0a6c4-197">Verrà visualizzato il criterio di configurazione creato.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-198">![Immagine del portale di Microsoft Endpoint Manager18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="0a6c4-199">Riduzione della superficie di attacco - Regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="0a6c4-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="0a6c4-200">Aprire il portale MEM.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="0a6c4-201">Passare a **Endpoint security > Attack surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="0a6c4-202">Selezionare  **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="0a6c4-203">Seleziona **Piattaforma - Windows 10 e versioni successive - Profilo - Regole di** riduzione della superficie > Crea .</span><span class="sxs-lookup"><span data-stu-id="0a6c4-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-204">![Immagine del portale di Microsoft Endpoint Manager19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="0a6c4-205">Immettere un nome e una descrizione, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-206">![Immagine del portale di Microsoft Endpoint Manager20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="0a6c4-207">Nella pagina **Impostazioni di configurazione**: Imposta le configurazioni necessarie per le regole di riduzione della superficie di attacco, quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a6c4-208">We will be configuring all of the Attack surface reduction rules to Audit.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="0a6c4-209">Per ulteriori informazioni, vedere [Regole di riduzione della superficie di attacco.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-210">![Immagine del portale di Microsoft Endpoint Manager21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="0a6c4-211">Aggiungi tag ambito in base alle esigenze, quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-212">![Immagine del portale di Microsoft Endpoint Manager22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="0a6c4-213">Selezionare i gruppi da includere e assegnare al gruppo di test, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-214">![Immagine del portale di Microsoft Endpoint Manager23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="0a6c4-215">Esaminare i dettagli, quindi selezionare  **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-216">![Immagine del portale di Microsoft Endpoint Manager24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="0a6c4-217">Visualizzare il criterio.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-218">![Immagine del portale di Microsoft Endpoint Manager25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="0a6c4-219">Riduzione della superficie di attacco - Protezione Web</span><span class="sxs-lookup"><span data-stu-id="0a6c4-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="0a6c4-220">Aprire il portale MEM.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="0a6c4-221">Passare a **Endpoint security > Attack surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="0a6c4-222">Selezionare  **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="0a6c4-223">Selezionare **Windows 10 e versioni successive - Protezione Web > Crea**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-224">![Immagine del portale di Microsoft Endpoint Manager26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="0a6c4-225">Immettere un nome e una descrizione, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-226">![Immagine del portale di Microsoft Endpoint Manager27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="0a6c4-227">Nella pagina **Impostazioni di configurazione**: Impostare le configurazioni necessarie per Protezione Web, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0a6c4-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a6c4-228">È in esecuzione la configurazione di Protezione Web per il blocco.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="0a6c4-229">Per ulteriori informazioni, vedere [Protezione Web](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0a6c4-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-230">![Immagine del portale di Microsoft Endpoint Manager28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="0a6c4-231">Aggiungere **tag di ambito come richiesto > Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-232">![Immagine del portale di Microsoft Endpoint Manager29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="0a6c4-233">Selezionare **Assegna al gruppo di test > Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-234">![Immagine del portale di Microsoft Endpoint Manager30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="0a6c4-235">Seleziona **Revisione e crea > crea**.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-236">![Immagine del portale di Microsoft Endpoint Manager31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="0a6c4-237">Visualizzare il criterio.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-238">![Immagine del portale di Microsoft Endpoint Manager32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="0a6c4-239">Convalidare le impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="0a6c4-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="0a6c4-240">Verificare che i criteri siano stati applicati</span><span class="sxs-lookup"><span data-stu-id="0a6c4-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="0a6c4-241">Dopo l'assegnazione del criterio di configurazione, l'applicazione del criterio di configurazione avrà un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="0a6c4-242">Per informazioni sulla tempistica, vedere [Informazioni sulla configurazione di Intune.](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="0a6c4-243">Per verificare che il criterio di configurazione sia stato applicato al dispositivo di test, seguire la procedura seguente per ogni criterio di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="0a6c4-244">Apri il portale MEM e passa al criterio pertinente, come illustrato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="0a6c4-245">L'esempio seguente mostra le impostazioni di protezione di nuova generazione.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-246">[![Immagine del portale di Microsoft Endpoint Manager33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="0a6c4-247">Selezionare Il **criterio di configurazione** per visualizzare lo stato dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-248">[![Immagine del portale di Microsoft Endpoint Manager34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="0a6c4-249">Seleziona  **Stato dispositivo** per visualizzare lo stato.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-250">[![Immagine del portale di Microsoft Endpoint Manager35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="0a6c4-251">Selezionare  **Stato utente** per visualizzare lo stato.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-252">[![Immagine del portale di Microsoft Endpoint Manager36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="0a6c4-253">Seleziona  **Stato per impostazione** per visualizzare lo stato.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="0a6c4-254">Questa visualizzazione è molto utile per identificare eventuali impostazioni in conflitto con un altro criterio.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-255">[![Immagine del portale di Microsoft Endpoint Manager37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="0a6c4-256">Rilevamento endpoint e risposta</span><span class="sxs-lookup"><span data-stu-id="0a6c4-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="0a6c4-257">Prima di applicare la configurazione, il servizio Defender for Endpoint Protection non deve essere avviato.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-258">[![Immagine del pannello Servizi1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="0a6c4-259">Dopo l'applicazione della configurazione, il servizio Defender for Endpoint Protection deve essere avviato.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-260">[![Immagine del pannello Servizi2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="0a6c4-261">Dopo l'esecuzione dei servizi nel dispositivo, il dispositivo viene visualizzato in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-262">[![Immagine di Microsoft Defender Security Center ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="0a6c4-263">Protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="0a6c4-263">Next-generation protection</span></span>

1.  <span data-ttu-id="0a6c4-264">Prima di applicare il criterio in un dispositivo di test, dovresti essere in grado di gestire manualmente le impostazioni, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-265">![Immagine dell'impostazione page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="0a6c4-266">Dopo l'applicazione del criterio, non dovrebbe essere possibile gestire manualmente le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a6c4-267">Nell'immagine seguente **Attivare la protezione** con distribuzione cloud e **Attivare** la protezione in tempo reale vengono visualizzati come gestiti.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0a6c4-268">![Immagine della pagina di impostazione2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="0a6c4-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="0a6c4-269">Riduzione della superficie di attacco - Regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="0a6c4-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="0a6c4-270">Prima di applicare il criterio su un dispositivo di test, penna una finestra di PowerShell e digita `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="0a6c4-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="0a6c4-271">Questo dovrebbe rispondere con le righe seguenti senza contenuto:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="0a6c4-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="0a6c4-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="0a6c4-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Immagine della riga di comando 1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="0a6c4-276">Dopo aver applicato il criterio in un dispositivo di test, apri windows PowerShell e digita `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="0a6c4-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="0a6c4-277">Questo dovrebbe rispondere con le righe seguenti con il contenuto come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0a6c4-277">This should respond with the following lines with content as shown below:</span></span>

    ![Immagine della riga di comando2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="0a6c4-279">Riduzione della superficie di attacco - Protezione Web</span><span class="sxs-lookup"><span data-stu-id="0a6c4-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="0a6c4-280">Nel dispositivo di test, aprire una finestra di PowerShell e digitare `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="0a6c4-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="0a6c4-281">Dovrebbe rispondere con uno 0, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-281">This should respond with a 0 as shown below.</span></span>

    ![Immagine della riga di comando3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="0a6c4-283">Dopo aver applicato il criterio, apri un Windows PowerShell e digita `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="0a6c4-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="0a6c4-284">Dovrebbe rispondere con un valore 1, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0a6c4-284">This should respond with a 1 as shown below.</span></span>

    ![Immagine della riga di comando4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
