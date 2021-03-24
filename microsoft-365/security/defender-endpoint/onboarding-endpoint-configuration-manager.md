---
title: Onboarding con Microsoft Endpoint Configuration Manager
description: Scopri come eseguire l'onboard in Microsoft Defender for Endpoint usando Microsoft Endpoint Configuration Manager
keywords: onboarding, configurazione, distribuzione, distribuzione, gestione configurazione endpoint, mdatp, protezione avanzata dalle minacce, creazione della raccolta, risposta al rilevamento degli endpoint, protezione di nuova generazione, riduzione della superficie di attacco, Gestione configurazione endpoint Microsoft
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
ms.openlocfilehash: 6e6f3cfbf471e7b99e2ce5215491e32c955e3833
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061048"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="d7436-104">Onboarding con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d7436-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d7436-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d7436-105">**Applies to:**</span></span>
- [<span data-ttu-id="d7436-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d7436-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d7436-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7436-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d7436-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d7436-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d7436-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d7436-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="d7436-110">Questo articolo fa parte della guida alla distribuzione e funge da esempio di metodo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="d7436-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="d7436-111">[Nell'argomento Pianificazione](deployment-strategy.md) sono stati forniti diversi metodi per l'onboard dei dispositivi al servizio.</span><span class="sxs-lookup"><span data-stu-id="d7436-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="d7436-112">In questo argomento viene illustrata l'architettura di co-gestione.</span><span class="sxs-lookup"><span data-stu-id="d7436-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="d7436-113">![Immagine dell'architettura nativa del cloud ](images/co-management-architecture.png)
 *Diagramma delle architetture di ambiente*</span><span class="sxs-lookup"><span data-stu-id="d7436-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="d7436-114">Mentre Defender for Endpoint supporta l'onboarding di diversi endpoint e strumenti, questo articolo non li copre.</span><span class="sxs-lookup"><span data-stu-id="d7436-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="d7436-115">Per informazioni sull'onboarding generale con altri strumenti e metodi di distribuzione supportati, vedere [Panoramica dell'onboarding.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="d7436-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="d7436-116">In questo argomento vengono guidati gli utenti in:</span><span class="sxs-lookup"><span data-stu-id="d7436-116">This topic guides users in:</span></span>
- <span data-ttu-id="d7436-117">Passaggio 1: Onboarding dei dispositivi Windows nel servizio</span><span class="sxs-lookup"><span data-stu-id="d7436-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="d7436-118">Passaggio 2: Configurazione delle funzionalità di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d7436-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="d7436-119">Queste indicazioni sull'onboarding illustrano i passaggi di base seguenti da eseguire quando si usa Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="d7436-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="d7436-120">**Creazione di una raccolta in Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="d7436-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="d7436-121">**Configurazione delle funzionalità di Microsoft Defender for Endpoint tramite Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="d7436-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="d7436-122">In questa distribuzione di esempio vengono trattati solo i dispositivi Windows.</span><span class="sxs-lookup"><span data-stu-id="d7436-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="d7436-123">Passaggio 1: onboardare i dispositivi Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d7436-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="d7436-124">Creazione della raccolta</span><span class="sxs-lookup"><span data-stu-id="d7436-124">Collection creation</span></span>
<span data-ttu-id="d7436-125">Per eseguire l'onboardboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager, la distribuzione può essere utilizzata come destinazione di una raccolta esistente oppure può essere creata una nuova raccolta per il testing.</span><span class="sxs-lookup"><span data-stu-id="d7436-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="d7436-126">L'onboarding con strumenti come Criteri di gruppo o il metodo manuale non installa alcun agente nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d7436-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="d7436-127">All'interno della console di Microsoft Endpoint Configuration Manager il processo di onboarding verrà configurato come parte delle impostazioni di conformità all'interno della console.</span><span class="sxs-lookup"><span data-stu-id="d7436-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="d7436-128">Qualsiasi sistema che riceve questa configurazione necessaria manterrà tale configurazione finché il client di Configuration Manager continuerà a ricevere questo criterio dal punto di gestione.</span><span class="sxs-lookup"><span data-stu-id="d7436-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="d7436-129">Segui i passaggi seguenti per eseguire l'onboardboard degli endpoint usando Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d7436-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="d7436-130">Nella console di Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Device \> Collections**.</span><span class="sxs-lookup"><span data-stu-id="d7436-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager1](images/configmgr-device-collections.png)

2. <span data-ttu-id="d7436-132">Fai clic **con il pulsante destro del** mouse su Raccolta dispositivi e scegli Crea raccolta **dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="d7436-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="d7436-134">**Fornisci un nome** e una raccolta di **limitazione,** quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="d7436-136">Selezionare **Aggiungi regola** e scegliere Regola di **query**.</span><span class="sxs-lookup"><span data-stu-id="d7436-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="d7436-138">Fare **clic su** Avanti nella Creazione guidata **appartenenza diretta** e fare clic su Modifica istruzione **query.**</span><span class="sxs-lookup"><span data-stu-id="d7436-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="d7436-140">Seleziona **Criteri** e quindi scegli l'icona a forma di stella.</span><span class="sxs-lookup"><span data-stu-id="d7436-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager6](images/configmgr-criteria.png)

7. <span data-ttu-id="d7436-142">Mantieni il tipo di criterio come valore **semplice,** scegli  dove come Sistema operativo - numero di **build,** operatore maggiore o uguale a e valore **14393** e fai clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="d7436-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager7](images/configmgr-simple-value.png)

8. <span data-ttu-id="d7436-144">Selezionare **Avanti** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="d7436-144">Select **Next** and **Close**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="d7436-146">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d7436-146">Select **Next**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager9](images/configmgr-confirm.png)


<span data-ttu-id="d7436-148">Dopo aver completato questa attività, ora hai una raccolta di dispositivi con tutti gli endpoint di Windows 10 nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d7436-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="d7436-149">Passaggio 2: Configurare Le funzionalità di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d7436-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="d7436-150">Questa sezione illustra come configurare le funzionalità seguenti usando Microsoft Endpoint Configuration Manager nei dispositivi Windows:</span><span class="sxs-lookup"><span data-stu-id="d7436-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="d7436-151">**Rilevamento endpoint e risposta**</span><span class="sxs-lookup"><span data-stu-id="d7436-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="d7436-152">**Protezione di nuova generazione**</span><span class="sxs-lookup"><span data-stu-id="d7436-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="d7436-153">**Riduzione della superficie d'attacco**</span><span class="sxs-lookup"><span data-stu-id="d7436-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="d7436-154">Rilevamento endpoint e risposta</span><span class="sxs-lookup"><span data-stu-id="d7436-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="d7436-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d7436-155">Windows 10</span></span>
<span data-ttu-id="d7436-156">Da Microsoft Defender Security Center è possibile scaricare il criterio ".onboarding" che può essere usato per creare il criterio in System Center Configuration Manager e distribuirlo nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d7436-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="d7436-157">Da un portale di Microsoft Defender Security Center seleziona [Impostazioni e quindi Onboarding.](https://securitycenter.windows.com/preferences2/onboarding)</span><span class="sxs-lookup"><span data-stu-id="d7436-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="d7436-158">In Metodo di distribuzione selezionare la versione supportata di **Microsoft Endpoint Configuration Manager.**</span><span class="sxs-lookup"><span data-stu-id="d7436-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Immagine della procedura guidata di onboarding di Microsoft Defender per endpoint10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="d7436-160">Seleziona **Scarica pacchetto.**</span><span class="sxs-lookup"><span data-stu-id="d7436-160">Select **Download package**.</span></span>

    ![Immagine della procedura guidata di onboarding di Microsoft Defender per endpoint11](images/mdatp-download-package.png)

4. <span data-ttu-id="d7436-162">Salvare il pacchetto in un percorso accessibile.</span><span class="sxs-lookup"><span data-stu-id="d7436-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="d7436-163">In Microsoft Endpoint Configuration Manager, passare a: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span><span class="sxs-lookup"><span data-stu-id="d7436-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="d7436-164">Fai clic con il pulsante destro del mouse su **Microsoft Defender ATP Policies** e scegli Create Microsoft Defender **ATP Policy.**</span><span class="sxs-lookup"><span data-stu-id="d7436-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager12](images/configmgr-create-policy.png)

7. <span data-ttu-id="d7436-166">Immetti il nome e la descrizione, verifica che **l'onboarding** sia selezionato, quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Immagine della procedura guidata di Microsoft Endpoint Configuration Manager13](images/configmgr-policy-name.png)


8. <span data-ttu-id="d7436-168">Fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="d7436-168">Click **Browse**.</span></span>

9. <span data-ttu-id="d7436-169">Passare al percorso del file scaricato dal passaggio 4 precedente.</span><span class="sxs-lookup"><span data-stu-id="d7436-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="d7436-170">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d7436-170">Click **Next**.</span></span>
11. <span data-ttu-id="d7436-171">Configurare l'agente con gli esempi appropriati (**Nessuno** o **Tutti i tipi di file**).</span><span class="sxs-lookup"><span data-stu-id="d7436-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Immagine delle impostazioni di configurazione1](images/configmgr-config-settings.png)

12. <span data-ttu-id="d7436-173">Selezionare la telemetria appropriata (**Normal** o **Expedited**), quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d7436-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Immagine delle impostazioni di configurazione2](images/configmgr-telemetry.png)

14. <span data-ttu-id="d7436-175">Verificare la configurazione, quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-175">Verify the configuration, then click **Next**.</span></span>

     ![Immagine delle impostazioni di configurazione3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="d7436-177">Al **termine** della procedura guidata, fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="d7436-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="d7436-178">Nella console di Microsoft Endpoint Configuration Manager fai clic con il pulsante destro del mouse sul criterio Defender for Endpoint appena creato e scegli **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="d7436-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Immagine delle impostazioni di configurazione4](images/configmgr-deploy.png)

17. <span data-ttu-id="d7436-180">Nel riquadro destro seleziona la raccolta creata in precedenza e fai clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="d7436-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Immagine delle impostazioni di configurazione5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="d7436-182">Versioni precedenti di Windows Client (Windows 7 e Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="d7436-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="d7436-183">Segui i passaggi seguenti per identificare l'ID dell'area di lavoro dell'endpoint e la chiave dell'area di lavoro, che saranno necessari per l'onboarding delle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="d7436-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="d7436-184">Da un portale di Microsoft Defender Security Center seleziona **Impostazioni > onboarding.**</span><span class="sxs-lookup"><span data-stu-id="d7436-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="d7436-185">In Sistema operativo scegliere **Windows 7 SP1 e 8.1.**</span><span class="sxs-lookup"><span data-stu-id="d7436-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="d7436-186">Copiare **l'ID dell'area** **di lavoro e la chiave dell'area** di lavoro e salvarli.</span><span class="sxs-lookup"><span data-stu-id="d7436-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="d7436-187">Verranno utilizzati più avanti nel processo.</span><span class="sxs-lookup"><span data-stu-id="d7436-187">They will be used later in the process.</span></span>

    ![Immagine dell'onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="d7436-189">Installare Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="d7436-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="d7436-190">MMA è attualmente (a partire da gennaio 2019) supportato nei seguenti sistemi operativi Windows:</span><span class="sxs-lookup"><span data-stu-id="d7436-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="d7436-191">SKU server: Windows Server 2008 SP1 o versione più recente</span><span class="sxs-lookup"><span data-stu-id="d7436-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="d7436-192">SKU client: Windows 7 SP1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="d7436-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="d7436-193">L'agente MMA dovrà essere installato nei dispositivi Windows.</span><span class="sxs-lookup"><span data-stu-id="d7436-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="d7436-194">Per installare l'agente, alcuni sistemi dovranno scaricare l'aggiornamento per l'esperienza del cliente e la telemetria [diagnostica](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) per raccogliere i dati con MMA.</span><span class="sxs-lookup"><span data-stu-id="d7436-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="d7436-195">Queste versioni di sistema includono ma potrebbero non essere limitate a:</span><span class="sxs-lookup"><span data-stu-id="d7436-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="d7436-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d7436-196">Windows 8.1</span></span>

    -   <span data-ttu-id="d7436-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d7436-197">Windows 7</span></span>

    -   <span data-ttu-id="d7436-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d7436-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="d7436-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d7436-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="d7436-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d7436-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="d7436-201">In particolare, per Windows 7 SP1, è necessario installare le patch seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7436-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="d7436-202">Installare [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="d7436-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="d7436-203">Installare .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) **o** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span><span class="sxs-lookup"><span data-stu-id="d7436-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="d7436-204">Non installare entrambi nello stesso sistema.</span><span class="sxs-lookup"><span data-stu-id="d7436-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="d7436-205">Se si usa un proxy per connettersi a Internet, vedere la sezione Configurare le impostazioni proxy.</span><span class="sxs-lookup"><span data-stu-id="d7436-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="d7436-206">Al termine, gli endpoint onboarded dovrebbero essere visualizzati nel portale entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="d7436-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="d7436-207">Protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="d7436-207">Next generation protection</span></span> 
<span data-ttu-id="d7436-208">L'Antivirus Microsoft Defender è una soluzione antimalware integrata che fornisce protezione di nuova generazione per computer desktop, portatili e server.</span><span class="sxs-lookup"><span data-stu-id="d7436-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="d7436-209">Nella console di Microsoft Endpoint Configuration Manager, accedere a **Assets and Compliance \> Overview Endpoint \> Protection \> Antimalware Polices** e scegliere **Create Antimalware Policy.**</span><span class="sxs-lookup"><span data-stu-id="d7436-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Immagine dei criteri antimalware](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="d7436-211">Selezionare **Analisi pianificate,** Impostazioni **analisi,** Azioni **predefinite,** Protezione in tempo **reale,** Impostazioni di **esclusione,** **Avanzate,** Sostituzioni delle **minacce,** Servizio di **protezione cloud** e Aggiornamenti di Intelligence per la **sicurezza** e scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="d7436-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Immagine del riquadro di protezione di nuova generazione1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="d7436-213">In alcuni settori o in alcuni clienti aziendali selezionati potrebbero essere necessarie specifiche per la configurazione dell'antivirus.</span><span class="sxs-lookup"><span data-stu-id="d7436-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="d7436-214">Analisi rapida e analisi completa e analisi personalizzata</span><span class="sxs-lookup"><span data-stu-id="d7436-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="d7436-215">Per altri dettagli, vedi [Framework di configurazione della sicurezza di Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="d7436-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Immagine del riquadro di protezione di nuova generazione2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Immagine del riquadro di protezione di nuova generazione3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Immagine del riquadro di protezione di nuova generazione4](images/a28afc02c1940d5220b233640364970c.png)

    ![Immagine del riquadro di protezione di nuova generazione5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Immagine del riquadro di protezione di nuova generazione6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Immagine del riquadro di protezione di nuova generazione7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Immagine del riquadro di protezione di nuova generazione8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Immagine del riquadro di protezione di nuova generazione9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="d7436-224">Fai clic con il pulsante destro del mouse sul criterio antimalware appena creato e scegli **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="d7436-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Immagine del riquadro di protezione di nuova generazione10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="d7436-226">Aggiungi il nuovo criterio antimalware alla raccolta di Windows 10 e fai clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="d7436-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Immagine del riquadro di protezione di nuova generazione11](images/configmgr-select-collection.png)

<span data-ttu-id="d7436-228">Dopo aver completato questa attività, hai configurato correttamente Windows Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="d7436-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="d7436-229">Riduzione della superficie d'attacco</span><span class="sxs-lookup"><span data-stu-id="d7436-229">Attack surface reduction</span></span>
<span data-ttu-id="d7436-230">Il pilastro di riduzione della superficie di attacco di Defender per Endpoint include il set di funzionalità disponibile in Exploit Guard.</span><span class="sxs-lookup"><span data-stu-id="d7436-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="d7436-231">Regole di riduzione della superficie di attacco (ASR), Accesso controllato alle cartelle, Protezione di rete e Protezione da exploit.</span><span class="sxs-lookup"><span data-stu-id="d7436-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="d7436-232">Tutte queste funzionalità forniscono una modalità di controllo e una modalità di blocco.</span><span class="sxs-lookup"><span data-stu-id="d7436-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="d7436-233">In modalità di controllo non vi è alcun impatto sull'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d7436-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="d7436-234">Tutto ciò che fa è raccogliere dati di telemetria aggiuntivi e renderli disponibili in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="d7436-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="d7436-235">L'obiettivo di una distribuzione è quello di spostare i controlli di sicurezza in modalità blocco passo-passo.</span><span class="sxs-lookup"><span data-stu-id="d7436-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="d7436-236">Per impostare le regole asr in modalità di controllo:</span><span class="sxs-lookup"><span data-stu-id="d7436-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="d7436-237">Nella console di Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** e scegliere **Create Exploit Guard Policy.**</span><span class="sxs-lookup"><span data-stu-id="d7436-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Immagine della console di Microsoft Endpoint Configuration Manager0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="d7436-239">Seleziona **Riduzione superficie di attacco.**</span><span class="sxs-lookup"><span data-stu-id="d7436-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="d7436-240">Impostare le regole su **Controlla e** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Immagine della console di Microsoft Endpoint Configuration Manager1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="d7436-242">Confermare il nuovo criterio di Exploit Guard facendo clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Immagine della console di Microsoft Endpoint Configuration Manager2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="d7436-244">Dopo aver creato il criterio, fare clic **su Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="d7436-244">Once the policy is created click **Close**.</span></span>

    ![Immagine della console di Microsoft Endpoint Configuration Manager3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Immagine della console di Microsoft Endpoint Manager1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="d7436-247">Fai clic con il pulsante destro del mouse sul criterio appena creato e scegli **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="d7436-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Immagine della console di Microsoft Endpoint Configuration Manager4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="d7436-249">Impostare il criterio come destinazione per la raccolta di Windows 10 appena creata e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="d7436-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Immagine della console di Microsoft Endpoint Configuration Manager5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="d7436-251">Dopo aver completato questa attività, le regole asr sono state configurate correttamente in modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="d7436-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="d7436-252">Di seguito sono riportati altri passaggi per verificare se le regole di risoluzione dei problemi vengono applicate correttamente agli endpoint.</span><span class="sxs-lookup"><span data-stu-id="d7436-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="d7436-253">(L'operazione potrebbe richiedere alcuni minuti)</span><span class="sxs-lookup"><span data-stu-id="d7436-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="d7436-254">Da un Web browser passare a <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="d7436-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="d7436-255">Seleziona **Gestione configurazione** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d7436-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="d7436-256">Fai **clic su Vai alla gestione della superficie di** attacco nel pannello Di gestione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="d7436-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Immagine della gestione della superficie di attacco](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="d7436-258">Fare **clic sulla scheda** Configurazione in Rapporti sulle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="d7436-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="d7436-259">Mostra la panoramica della configurazione delle regole asr e lo stato delle regole asr in ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d7436-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Screenshot delle regole di riduzione della superficie di attacco1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="d7436-261">Fare clic su ogni dispositivo per visualizzare i dettagli di configurazione delle regole di registrazione asr.</span><span class="sxs-lookup"><span data-stu-id="d7436-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Screenshot delle regole di riduzione della superficie di attacco2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="d7436-263">Per [ulteriori dettagli, vedere Optimize ASR rule deployment and detections.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)</span><span class="sxs-lookup"><span data-stu-id="d7436-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="d7436-264">Impostare le regole di Protezione di rete in modalità di controllo:</span><span class="sxs-lookup"><span data-stu-id="d7436-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="d7436-265">Nella console di Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** e scegliere **Create Exploit Guard Policy.**</span><span class="sxs-lookup"><span data-stu-id="d7436-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![A screenshot System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="d7436-267">Selezionare **Protezione di rete**.</span><span class="sxs-lookup"><span data-stu-id="d7436-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="d7436-268">Impostare l'impostazione su **Controlla e** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![A screenshot System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="d7436-270">Confermare il nuovo criterio di Exploit Guard facendo clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Screenshot Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="d7436-272">Una volta creato il criterio, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="d7436-272">Once the policy is created click on **Close**.</span></span>

    ![Screenshot Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="d7436-274">Fai clic con il pulsante destro del mouse sul criterio appena creato e scegli **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="d7436-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="d7436-276">Seleziona il criterio per la raccolta di Windows 10 appena creata e scegli **OK.**</span><span class="sxs-lookup"><span data-stu-id="d7436-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="d7436-278">Dopo aver completato questa attività, la configurazione di Protezione di rete in modalità di controllo è stata completata.</span><span class="sxs-lookup"><span data-stu-id="d7436-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="d7436-279">Per impostare le regole di accesso controllato alle cartelle in modalità di controllo:</span><span class="sxs-lookup"><span data-stu-id="d7436-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="d7436-280">Nella console di Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** e scegliere **Create Exploit Guard Policy.**</span><span class="sxs-lookup"><span data-stu-id="d7436-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="d7436-282">Selezionare **Accesso controllato alle cartelle**.</span><span class="sxs-lookup"><span data-stu-id="d7436-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="d7436-283">Impostare la configurazione su **Controlla e** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="d7436-285">Confermare il nuovo criterio di Exploit Guard facendo clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="d7436-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="d7436-287">Una volta creato il criterio, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="d7436-287">Once the policy is created click on **Close**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="d7436-289">Fai clic con il pulsante destro del mouse sul criterio appena creato e scegli **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="d7436-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="d7436-291">Impostare il criterio come destinazione per la raccolta di Windows 10 appena creata e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="d7436-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Screenshot di Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="d7436-293">L'accesso controllato alle cartelle è stato configurato correttamente in modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="d7436-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="d7436-294">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="d7436-294">Related topic</span></span>
- [<span data-ttu-id="d7436-295">Onboarding con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d7436-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
