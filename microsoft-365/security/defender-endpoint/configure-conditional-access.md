---
title: Configurare l'accesso condizionale in Microsoft Defender ATP
description: Informazioni sui passaggi da eseguire in Intune, Microsoft Defender Security Center e Azure per implementare l'accesso condizionale
keywords: accesso condizionale, condizionale, accesso, rischio del dispositivo, livello di rischio, integrazione, integrazione intune
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165862"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3cda2-104">Configurare l'accesso condizionale in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="3cda2-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3cda2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3cda2-105">**Applies to:**</span></span>
- [<span data-ttu-id="3cda2-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3cda2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3cda2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cda2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3cda2-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3cda2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3cda2-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3cda2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="3cda2-110">In questa sezione vengono descritti tutti i passaggi necessari per implementare correttamente l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="3cda2-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="3cda2-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3cda2-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="3cda2-112">È importante notare che i dispositivi registrati in Azure AD non sono supportati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="3cda2-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="3cda2-113">Sono supportati solo i dispositivi registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="3cda2-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="3cda2-114">È necessario assicurarsi che tutti i dispositivi siano registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="3cda2-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="3cda2-115">Puoi usare una delle opzioni seguenti per registrare i dispositivi in Intune:</span><span class="sxs-lookup"><span data-stu-id="3cda2-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="3cda2-116">Amministratore IT: per ulteriori informazioni su come abilitare la registrazione automatica, vedere [Registrazione di Windows](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="3cda2-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="3cda2-117">Utente finale: per altre informazioni su come registrare il dispositivo Windows 10 in Intune, vedere Registrare il dispositivo [Windows 10 in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="3cda2-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="3cda2-118">Alternativa per l'utente finale: per ulteriori informazioni sull'aggiunta a un dominio di Azure AD, vedere [Procedura: Pianificare l'implementazione dell'aggiunta ad Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)</span><span class="sxs-lookup"><span data-stu-id="3cda2-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="3cda2-119">È necessario eseguire alcuni passaggi in Microsoft Defender Security Center, nel portale di Intune e nel portale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3cda2-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="3cda2-120">È importante notare i ruoli necessari per accedere a questi portali e implementare l'accesso condizionale:</span><span class="sxs-lookup"><span data-stu-id="3cda2-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="3cda2-121">**Microsoft Defender Security Center:** dovrai accedere al portale con un ruolo di amministratore globale per attivare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="3cda2-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="3cda2-122">**Intune:** è necessario accedere al portale con diritti di amministratore della sicurezza con autorizzazioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="3cda2-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="3cda2-123">**Portale di Azure AD:** è necessario accedere come amministratore globale, amministratore della sicurezza o amministratore di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="3cda2-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="3cda2-124">Avrai bisogno di un ambiente Microsoft Intune, con Intune gestito e i dispositivi Windows 10 aggiunti ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3cda2-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="3cda2-125">Eseguire la procedura seguente per abilitare l'accesso condizionale:</span><span class="sxs-lookup"><span data-stu-id="3cda2-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="3cda2-126">Passaggio 1: attivare la connessione a Microsoft Intune da Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="3cda2-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="3cda2-127">Passaggio 2: attivare l'integrazione di Defender for Endpoint in Intune</span><span class="sxs-lookup"><span data-stu-id="3cda2-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="3cda2-128">Passaggio 3: Creare i criteri di conformità in Intune</span><span class="sxs-lookup"><span data-stu-id="3cda2-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="3cda2-129">Passaggio 4: Assegnare il criterio</span><span class="sxs-lookup"><span data-stu-id="3cda2-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="3cda2-130">Passaggio 5: Creare un criterio di accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3cda2-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="3cda2-131">Passaggio 1: attivare la connessione a Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3cda2-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="3cda2-132">Nel riquadro di spostamento, selezionare **Impostazioni**  >  **Funzionalità avanzate** Connessione di Microsoft  >  **Intune.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="3cda2-133">Attiva l'impostazione di Microsoft **Intune.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="3cda2-134">Fare **clic su Salva preferenze.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="3cda2-135">Passaggio 2: attivare l'integrazione di Defender for Endpoint in Intune</span><span class="sxs-lookup"><span data-stu-id="3cda2-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="3cda2-136">Accedere al [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="3cda2-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="3cda2-137">Selezionare **Conformità dispositivo** Microsoft Defender  >  **ATP**.</span><span class="sxs-lookup"><span data-stu-id="3cda2-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="3cda2-138">Imposta **Connetti dispositivi Windows 10.0.15063+** a Microsoft Defender Advanced Threat Protection su **On.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="3cda2-139">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3cda2-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="3cda2-140">Passaggio 3: Creare i criteri di conformità in Intune</span><span class="sxs-lookup"><span data-stu-id="3cda2-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="3cda2-141">Nel portale [di Azure](https://portal.azure.com)seleziona Tutti **i servizi,** filtra **in Intune** e seleziona **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="3cda2-142">Selezionare **Criteri di conformità** dei  >  **dispositivi** Crea  >  **criterio**.</span><span class="sxs-lookup"><span data-stu-id="3cda2-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="3cda2-143">Immettere un **nome** e una **descrizione.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="3cda2-144">In **Piattaforma** seleziona **Windows 10 e versioni successive.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="3cda2-145">Nelle impostazioni **integrità dispositivo** imposta Richiedi che **il** dispositivo sia al livello di minaccia del dispositivo o al livello di minaccia del dispositivo al livello preferito:</span><span class="sxs-lookup"><span data-stu-id="3cda2-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="3cda2-146">**Protetto**: questo livello è il più sicuro.</span><span class="sxs-lookup"><span data-stu-id="3cda2-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="3cda2-147">Il dispositivo non può avere minacce esistenti e accedere comunque alle risorse aziendali.</span><span class="sxs-lookup"><span data-stu-id="3cda2-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="3cda2-148">Se vengono rilevate minacce, il dispositivo viene valutato come non conforme.</span><span class="sxs-lookup"><span data-stu-id="3cda2-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="3cda2-149">**Low**: il dispositivo è conforme se esistono solo minacce di basso livello.</span><span class="sxs-lookup"><span data-stu-id="3cda2-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="3cda2-150">I dispositivi con livelli di minaccia medio o alto non sono conformi.</span><span class="sxs-lookup"><span data-stu-id="3cda2-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="3cda2-151">**Medio:** il dispositivo è conforme se le minacce rilevate nel dispositivo sono basse o medie.</span><span class="sxs-lookup"><span data-stu-id="3cda2-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="3cda2-152">Se vengono rilevate minacce di alto livello, il dispositivo viene determinato come non conforme.</span><span class="sxs-lookup"><span data-stu-id="3cda2-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="3cda2-153">**Alto:** questo livello è il meno sicuro e consente tutti i livelli di minaccia.</span><span class="sxs-lookup"><span data-stu-id="3cda2-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="3cda2-154">Pertanto, i dispositivi con livelli di minaccia alti, medi o bassi sono considerati conformi.</span><span class="sxs-lookup"><span data-stu-id="3cda2-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="3cda2-155">Selezionare **OK** e **Crea** per salvare le modifiche e creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="3cda2-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="3cda2-156">Passaggio 4: Assegnare il criterio</span><span class="sxs-lookup"><span data-stu-id="3cda2-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="3cda2-157">Nel portale [di Azure](https://portal.azure.com)seleziona Tutti **i servizi,** filtra **in Intune** e seleziona **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="3cda2-158">Seleziona **Criteri di conformità**  >  **dei** dispositivi> i criteri di conformità di Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="3cda2-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="3cda2-159">Selezionare **Attività**.</span><span class="sxs-lookup"><span data-stu-id="3cda2-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="3cda2-160">Includi o escludi i gruppi di Azure AD per assegnare loro il criterio.</span><span class="sxs-lookup"><span data-stu-id="3cda2-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="3cda2-161">Per distribuire il criterio ai gruppi, selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="3cda2-162">I dispositivi utente destinati ai criteri vengono valutati per la conformità.</span><span class="sxs-lookup"><span data-stu-id="3cda2-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="3cda2-163">Passaggio 5: Creare un criterio di accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3cda2-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="3cda2-164">Nel portale [di Azure,](https://portal.azure.com)aprire **Azure Active Directory** Conditional  >  **Access**  >  **New policy**.</span><span class="sxs-lookup"><span data-stu-id="3cda2-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="3cda2-165">Immettere un nome **di** criterio e selezionare **Utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="3cda2-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="3cda2-166">Utilizzare le opzioni Includi o Escludi per aggiungere i gruppi per il criterio e selezionare **Fatto.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="3cda2-167">Seleziona **App cloud** e scegli le app da proteggere.</span><span class="sxs-lookup"><span data-stu-id="3cda2-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="3cda2-168">Ad esempio, scegliere **Seleziona app** e selezionare **Office 365 SharePoint Online** ed Office **365 Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="3cda2-169">Selezionare **Fine** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3cda2-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="3cda2-170">Seleziona **Condizioni**  >  **App client** per applicare il criterio ad app e browser.</span><span class="sxs-lookup"><span data-stu-id="3cda2-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="3cda2-171">Ad esempio, selezionare **Sì** e quindi abilitare **le app browser** e per dispositivi mobili e i client **desktop.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="3cda2-172">Selezionare **Fine** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3cda2-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="3cda2-173">Seleziona **Concedi** per applicare l'accesso condizionale in base alla conformità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3cda2-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="3cda2-174">Ad esempio, seleziona **Concedi accesso**  >  **Richiedi che il dispositivo sia contrassegnato come conforme.**</span><span class="sxs-lookup"><span data-stu-id="3cda2-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="3cda2-175">Scegliere **Seleziona** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3cda2-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="3cda2-176">Selezionare **Abilita criterio** e quindi Crea **per** salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3cda2-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="3cda2-177">Per altre informazioni, vedi [Abilitare Microsoft Defender ATP con accesso condizionale in Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="3cda2-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="3cda2-178">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3cda2-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3cda2-179">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3cda2-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)