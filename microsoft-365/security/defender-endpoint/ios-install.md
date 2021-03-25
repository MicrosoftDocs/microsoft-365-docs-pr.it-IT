---
title: Distribuzione basata su app per Microsoft Defender ATP per iOS
ms.reviewer: ''
description: Descrive come distribuire Microsoft Defender ATP per iOS usando un'app
keywords: microsoft, defender, atp, ios, app, installazione, distribuzione, disinstallazione, intune
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
ms.openlocfilehash: 7887f26cb8ca7e0e769249a10f008308149aaa42
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186690"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="f4403-104">Distribuire Microsoft Defender per Endpoint per iOS</span><span class="sxs-lookup"><span data-stu-id="f4403-104">Deploy Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4403-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f4403-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4403-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f4403-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4403-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4403-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f4403-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f4403-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f4403-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f4403-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f4403-110">Questo argomento descrive la distribuzione di Defender per Endpoint per iOS nei dispositivi registrati nel portale aziendale di Intune.</span><span class="sxs-lookup"><span data-stu-id="f4403-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="f4403-111">Per altre informazioni sulla registrazione dei dispositivi Intune, vedi Registrare dispositivi [iOS/iPadOS in Intune.](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="f4403-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f4403-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f4403-112">Before you begin</span></span>

- <span data-ttu-id="f4403-113">Assicurati di avere accesso [all'interfaccia di amministrazione di Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="f4403-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="f4403-114">Verificare che la registrazione iOS sia stata eseguita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f4403-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="f4403-115">Gli utenti devono disporre di una licenza defender per endpoint assegnata per poter usare Defender per Endpoint per iOS.</span><span class="sxs-lookup"><span data-stu-id="f4403-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="f4403-116">Per istruzioni [su come assegnare licenze, vedere](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) Assegnare licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f4403-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="f4403-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) per iOS è ora disponibile [nell'Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="f4403-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="f4403-118">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f4403-118">Deployment steps</span></span>

<span data-ttu-id="f4403-119">Distribuire Defender per Endpoint per iOS tramite il portale aziendale di Intune.</span><span class="sxs-lookup"><span data-stu-id="f4403-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="f4403-120">Aggiungere l'app di iOS Store</span><span class="sxs-lookup"><span data-stu-id="f4403-120">Add iOS store app</span></span>

1. <span data-ttu-id="f4403-121">[Nell'interfaccia di amministrazione di Microsoft Endpoint manager](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **App**  ->  **iOS/iPadOS**  ->  **Aggiungi**  ->  **app dello Store iOS** e fai clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="f4403-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-122">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="f4403-123">Nella pagina Aggiungi app fai clic su **Cerca nell'App Store** e digita **Microsoft Defender ATP** nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f4403-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender ATP** in the search bar.</span></span> <span data-ttu-id="f4403-124">Nella sezione dei risultati della ricerca fai clic su *Microsoft Defender ATP* e fai clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="f4403-124">In the search results section, click on *Microsoft Defender ATP* and click **Select**.</span></span>

1. <span data-ttu-id="f4403-125">Seleziona **iOS 11.0** come sistema operativo minimo.</span><span class="sxs-lookup"><span data-stu-id="f4403-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="f4403-126">Esamina le altre informazioni sull'app e fai clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f4403-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="f4403-127">Nella sezione *Assegnazioni* passare alla sezione **Obbligatorio** e selezionare **Aggiungi gruppo.**</span><span class="sxs-lookup"><span data-stu-id="f4403-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="f4403-128">Puoi quindi scegliere i gruppi di utenti di destinazione dell'app Defender per Endpoint per iOS.</span><span class="sxs-lookup"><span data-stu-id="f4403-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="f4403-129">Fare **clic su** Seleziona e quindi su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f4403-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4403-130">Il gruppo di utenti selezionato deve essere costituito da utenti registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="f4403-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-131">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="f4403-132">Nella sezione *Revisione e creazione* verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f4403-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="f4403-133">In pochi istanti, l'app Defender for Endpoint dovrebbe essere creata correttamente e dovrebbe essere visualizzata una notifica nell'angolo in alto a destra della pagina.</span><span class="sxs-lookup"><span data-stu-id="f4403-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="f4403-134">Nella pagina delle informazioni sull'app visualizzata, nella sezione **Monitor** seleziona **Stato** installazione dispositivo per verificare che l'installazione del dispositivo sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f4403-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-135">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="f4403-136">Completare l'onboarding e controllare lo stato</span><span class="sxs-lookup"><span data-stu-id="f4403-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="f4403-137">Dopo aver installato Defender for Endpoint per iOS nel dispositivo, verrà visualizzata l'icona dell'app.</span><span class="sxs-lookup"><span data-stu-id="f4403-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Schermata di uno smart phone Descrizione generata automaticamente](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="f4403-139">Tocca l'icona dell'app Defender for Endpoint e segui le istruzioni visualizzate per completare la procedura di onboarding.</span><span class="sxs-lookup"><span data-stu-id="f4403-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="f4403-140">I dettagli includono l'accettazione da parte dell'utente finale delle autorizzazioni iOS richieste da Defender per Endpoint per iOS.</span><span class="sxs-lookup"><span data-stu-id="f4403-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="f4403-141">Al completamento dell'onboarding, il dispositivo inizierà a essere visualizzato nell'elenco Dispositivi in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="f4403-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-142">![Screenshot di un cellulare Descrizione generata automaticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="f4403-143">Configurare Microsoft Defender per Endpoint per la modalità supervisione</span><span class="sxs-lookup"><span data-stu-id="f4403-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="f4403-144">L'app Microsoft Defender for Endpoint per iOS ha capacità specializzate nei dispositivi iOS/iPadOS supervisionati, date le maggiori funzionalità di gestione fornite dalla piattaforma su questi tipi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f4403-144">The Microsoft Defender for Endpoint for iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="f4403-145">Per sfruttare queste funzionalità, l'app Defender for Endpoint deve sapere se un dispositivo è in modalità supervisione.</span><span class="sxs-lookup"><span data-stu-id="f4403-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="f4403-146">Configurare la modalità supervisionata tramite Intune</span><span class="sxs-lookup"><span data-stu-id="f4403-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="f4403-147">Intune consente di configurare l'app Defender per iOS tramite un criterio di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="f4403-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f4403-148">Questo criterio di configurazione dell'app per i dispositivi supervisionati è applicabile solo ai dispositivi gestiti e deve essere destinato a tutti i dispositivi iOS gestiti come procedura consigliata.</span><span class="sxs-lookup"><span data-stu-id="f4403-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="f4403-149">Accedi all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e vai a **App** Criteri di configurazione  >  **app**  >  **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4403-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="f4403-150">Fare clic **su Dispositivi gestiti**.</span><span class="sxs-lookup"><span data-stu-id="f4403-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-151">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="f4403-152">Nella pagina *Crea criteri di configurazione* app fornire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4403-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="f4403-153">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="f4403-153">Policy Name</span></span>
    - <span data-ttu-id="f4403-154">Piattaforma: seleziona iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="f4403-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="f4403-155">App mirata: seleziona **Microsoft Defender ATP** nell'elenco</span><span class="sxs-lookup"><span data-stu-id="f4403-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-156">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="f4403-157">Nella schermata successiva seleziona **Usa progettazione configurazione** come formato.</span><span class="sxs-lookup"><span data-stu-id="f4403-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="f4403-158">Specificare la proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="f4403-158">Specify the following property:</span></span>
    - <span data-ttu-id="f4403-159">Chiave di configurazione: issupervised</span><span class="sxs-lookup"><span data-stu-id="f4403-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="f4403-160">Tipo di valore: String</span><span class="sxs-lookup"><span data-stu-id="f4403-160">Value type: String</span></span>
    - <span data-ttu-id="f4403-161">Valore di configurazione: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="f4403-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-162">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="f4403-163">Fare **clic su** Avanti per aprire la pagina Tag **ambito.**</span><span class="sxs-lookup"><span data-stu-id="f4403-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="f4403-164">I tag di ambito sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="f4403-164">Scope tags are optional.</span></span> <span data-ttu-id="f4403-165">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="f4403-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="f4403-166">Nella **pagina Assegnazioni** selezionare i gruppi che riceveranno il profilo.</span><span class="sxs-lookup"><span data-stu-id="f4403-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="f4403-167">Per questo scenario, è consigliabile scegliere come destinazione **Tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f4403-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="f4403-168">Per ulteriori informazioni sull'assegnazione di profili, vedere [Assegnare profili utente e dispositivo.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="f4403-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="f4403-169">Quando si distribuisce ai gruppi di utenti, un utente deve accedere a un dispositivo prima dell'applicazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="f4403-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="f4403-170">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4403-170">Click **Next**.</span></span>

1. <span data-ttu-id="f4403-171">Al termine della pagina Revisione **e** creazione scegliere **Crea.**</span><span class="sxs-lookup"><span data-stu-id="f4403-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="f4403-172">Il nuovo profilo viene visualizzato nell'elenco dei profili di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f4403-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="f4403-173">Successivamente, per le funzionalità avanzate di anti-phishing, puoi distribuire un profilo personalizzato nei dispositivi iOS supervisionati.</span><span class="sxs-lookup"><span data-stu-id="f4403-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="f4403-174">Seguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f4403-174">Follow the steps below:</span></span>
    - <span data-ttu-id="f4403-175">Scaricare il profilo di configurazione da [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="f4403-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="f4403-176">Passare a **Dispositivi profili** di  ->  **configurazione iOS/iPadOS** Crea  ->    ->  **profilo**</span><span class="sxs-lookup"><span data-stu-id="f4403-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4403-177">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="f4403-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="f4403-178">Specificare un nome del profilo.</span><span class="sxs-lookup"><span data-stu-id="f4403-178">Provide a name of the profile.</span></span> <span data-ttu-id="f4403-179">Quando viene richiesto di importare un file del profilo di configurazione, selezionare quello scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f4403-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="f4403-180">Nella sezione **Assegnazione** seleziona il gruppo di dispositivi a cui vuoi applicare il profilo.</span><span class="sxs-lookup"><span data-stu-id="f4403-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="f4403-181">Come procedura consigliata, questa operazione deve essere applicata a tutti i dispositivi iOS gestiti.</span><span class="sxs-lookup"><span data-stu-id="f4403-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="f4403-182">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4403-182">Click **Next**.</span></span>
    - <span data-ttu-id="f4403-183">Al termine della pagina Revisione **e** creazione scegliere **Crea.**</span><span class="sxs-lookup"><span data-stu-id="f4403-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="f4403-184">Il nuovo profilo viene visualizzato nell'elenco dei profili di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f4403-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4403-185">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="f4403-185">Next Steps</span></span>

[<span data-ttu-id="f4403-186">Configurare Defender per le funzionalità di Endpoint per iOS</span><span class="sxs-lookup"><span data-stu-id="f4403-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
