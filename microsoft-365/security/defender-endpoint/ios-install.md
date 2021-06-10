---
title: Distribuzione basata su app per Microsoft Defender for Endpoint in iOS
ms.reviewer: ''
description: Descrive come distribuire Microsoft Defender for Endpoint in iOS usando un'app
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, app, installazione, distribuzione, disinstallazione, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842289"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="f87cd-104">Distribuire Microsoft Defender per Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="f87cd-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f87cd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f87cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="f87cd-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f87cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f87cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f87cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f87cd-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f87cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f87cd-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f87cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f87cd-110">Questo argomento descrive la distribuzione di Defender for Endpoint in iOS Portale aziendale Intune dispositivi registrati.</span><span class="sxs-lookup"><span data-stu-id="f87cd-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="f87cd-111">Per altre informazioni sulla registrazione dei dispositivi Intune, vedi Registrare dispositivi [iOS/iPadOS in Intune.](/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="f87cd-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f87cd-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f87cd-112">Before you begin</span></span>

- <span data-ttu-id="f87cd-113">Assicurati di avere accesso [all'interfaccia di amministrazione di Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="f87cd-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="f87cd-114">Verificare che la registrazione iOS sia stata eseguita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f87cd-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="f87cd-115">Gli utenti devono disporre di una licenza defender per endpoint assegnata per poter usare Defender per Endpoint in iOS.</span><span class="sxs-lookup"><span data-stu-id="f87cd-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="f87cd-116">Per istruzioni [su come assegnare licenze, vedere](/azure/active-directory/users-groups-roles/licensing-groups-assign) Assegnare licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f87cd-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="f87cd-117">Microsoft Defender per Endpoint su iOS è disponibile [nell'Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="f87cd-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="f87cd-118">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f87cd-118">Deployment steps</span></span>

<span data-ttu-id="f87cd-119">Distribuire Defender per Endpoint in iOS tramite Portale aziendale Intune.</span><span class="sxs-lookup"><span data-stu-id="f87cd-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="f87cd-120">Aggiungere l'app di iOS Store</span><span class="sxs-lookup"><span data-stu-id="f87cd-120">Add iOS store app</span></span>

1. <span data-ttu-id="f87cd-121">[Nell'interfaccia di amministrazione di Microsoft Endpoint manager](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **App**  ->  **iOS/iPadOS**  ->  **Aggiungi**  ->  **app dello Store iOS** e fai clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-122">![Immagine di Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="f87cd-123">Nella pagina Aggiungi app fai clic su **Cerca nell'App Store** e digita **Microsoft Defender Endpoint** nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f87cd-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="f87cd-124">Nella sezione dei risultati della ricerca fai clic su *Microsoft Defender Endpoint* e fai clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="f87cd-125">Seleziona **iOS 11.0** come sistema operativo minimo.</span><span class="sxs-lookup"><span data-stu-id="f87cd-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="f87cd-126">Esamina le altre informazioni sull'app e fai clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="f87cd-127">Nella sezione *Assegnazioni* passare alla sezione **Obbligatorio** e selezionare **Aggiungi gruppo.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="f87cd-128">Puoi quindi scegliere i gruppi di utenti che vuoi usare come destinazione di Defender per Endpoint nell'app iOS.</span><span class="sxs-lookup"><span data-stu-id="f87cd-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="f87cd-129">Fare **clic su** Seleziona e quindi su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f87cd-130">Il gruppo di utenti selezionato deve essere costituito da utenti registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="f87cd-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-131">![Immagine di Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="f87cd-132">Nella sezione *Revisione e creazione* verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="f87cd-133">In pochi istanti, l'app Defender for Endpoint dovrebbe essere creata correttamente e dovrebbe essere visualizzata una notifica nell'angolo in alto a destra della pagina.</span><span class="sxs-lookup"><span data-stu-id="f87cd-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="f87cd-134">Nella pagina delle informazioni sull'app visualizzata, nella sezione **Monitor** seleziona **Stato** installazione dispositivo per verificare che l'installazione del dispositivo sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f87cd-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-135">![Immagine di Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="f87cd-136">Onboarding automatico del profilo VPN (onboarding semplificato)</span><span class="sxs-lookup"><span data-stu-id="f87cd-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="f87cd-137">Gli amministratori possono configurare la configurazione automatica del profilo VPN.</span><span class="sxs-lookup"><span data-stu-id="f87cd-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="f87cd-138">In questo modo verrà automaticamente creato il profilo VPN defender per endpoint senza che l'utente lo faccia durante l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="f87cd-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="f87cd-139">Si noti che la VPN viene utilizzata per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="f87cd-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="f87cd-140">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f87cd-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="f87cd-141">[Nell'interfaccia di amministrazione di Microsoft Endpoint manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **Profili** di configurazione  ->  **dei dispositivi**  ->  **Crea profilo.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="f87cd-142">Scegli **Piattaforma** come **iOS/iPadOS** e **Tipo di profilo** come **VPN.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="f87cd-143">Fai clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-143">Click **Create**.</span></span>
1. <span data-ttu-id="f87cd-144">Digitare un nome per il profilo e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="f87cd-145">Seleziona **VPN personalizzata** per Tipo di connessione e nella sezione Vpn di **base** immetti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f87cd-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="f87cd-146">Connection Name = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f87cd-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="f87cd-147">Indirizzo del server VPN = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="f87cd-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="f87cd-148">Metodo di autenticazione = "Nome utente e password"</span><span class="sxs-lookup"><span data-stu-id="f87cd-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="f87cd-149">Split Tunneling = Disabilita</span><span class="sxs-lookup"><span data-stu-id="f87cd-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="f87cd-150">Identificatore VPN = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="f87cd-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="f87cd-151">Nelle coppie chiave-valore immettere la chiave **AutoOnboard** e impostare il valore su **True.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="f87cd-152">Tipo di VPN automatica = VPN su richiesta</span><span class="sxs-lookup"><span data-stu-id="f87cd-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="f87cd-153">Fare **clic su** Aggiungi per **Regole** su richiesta e selezionare Voglio eseguire le operazioni seguenti = **Stabilire vpn**, Voglio limitare a = Tutti i **domini**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Screenshot della configurazione del profilo VPN](images/ios-deploy-8.png)

1. <span data-ttu-id="f87cd-155">Fare clic su Avanti e assegnare il profilo agli utenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f87cd-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="f87cd-156">Nella sezione *Revisione e creazione* verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="f87cd-157">Completare l'onboarding e controllare lo stato</span><span class="sxs-lookup"><span data-stu-id="f87cd-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="f87cd-158">Dopo aver installato Defender for Endpoint su iOS nel dispositivo, verrà visualizzata l'icona dell'app.</span><span class="sxs-lookup"><span data-stu-id="f87cd-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Schermata di uno smart phone Descrizione generata automaticamente](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="f87cd-160">Tocca l'icona dell'app Defender for Endpoint (MSDefender) e segui le istruzioni visualizzate per completare la procedura di onboarding.</span><span class="sxs-lookup"><span data-stu-id="f87cd-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="f87cd-161">I dettagli includono l'accettazione da parte dell'utente finale delle autorizzazioni iOS richieste da Defender per Endpoint in iOS.</span><span class="sxs-lookup"><span data-stu-id="f87cd-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="f87cd-162">Al completamento dell'onboarding, il dispositivo inizierà a essere visualizzato nell'elenco Dispositivi Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="f87cd-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-163">![Screenshot di un cellulare Descrizione generata automaticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="f87cd-164">Configurare Microsoft Defender per Endpoint per la modalità supervisione</span><span class="sxs-lookup"><span data-stu-id="f87cd-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="f87cd-165">L'app Microsoft Defender for Endpoint su iOS ha capacità specializzate nei dispositivi iOS/iPadOS supervisionati, date le maggiori funzionalità di gestione fornite dalla piattaforma su questi tipi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f87cd-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="f87cd-166">Per sfruttare queste funzionalità, l'app Defender for Endpoint deve sapere se un dispositivo è in modalità supervisione.</span><span class="sxs-lookup"><span data-stu-id="f87cd-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="f87cd-167">Configurare la modalità supervisionata tramite Intune</span><span class="sxs-lookup"><span data-stu-id="f87cd-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="f87cd-168">Intune consente di configurare l'app Defender per iOS tramite un criterio di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="f87cd-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f87cd-169">Questo criterio di configurazione dell'app per i dispositivi supervisionati è applicabile solo ai dispositivi gestiti e deve essere destinato a tutti i dispositivi iOS gestiti come procedura consigliata.</span><span class="sxs-lookup"><span data-stu-id="f87cd-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="f87cd-170">Accedi all'interfaccia [di Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) vai **a** App Criteri di configurazione  >  **app**  >  **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="f87cd-171">Fare clic **su Dispositivi gestiti**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-172">![Immagine di Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="f87cd-173">Nella pagina *Crea criteri di configurazione* app fornire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f87cd-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="f87cd-174">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="f87cd-174">Policy Name</span></span>
    - <span data-ttu-id="f87cd-175">Piattaforma: seleziona iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="f87cd-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="f87cd-176">App di destinazione: seleziona **Microsoft Defender Endpoint** dall'elenco</span><span class="sxs-lookup"><span data-stu-id="f87cd-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-177">![Immagine di Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="f87cd-178">Nella schermata successiva seleziona **Usa progettazione configurazione** come formato.</span><span class="sxs-lookup"><span data-stu-id="f87cd-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="f87cd-179">Specificare la proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="f87cd-179">Specify the following property:</span></span>
    - <span data-ttu-id="f87cd-180">Chiave di configurazione: issupervised</span><span class="sxs-lookup"><span data-stu-id="f87cd-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="f87cd-181">Tipo di valore: String</span><span class="sxs-lookup"><span data-stu-id="f87cd-181">Value type: String</span></span>
    - <span data-ttu-id="f87cd-182">Valore di configurazione: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="f87cd-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-183">![Immagine di Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="f87cd-184">Fare **clic su** Avanti per aprire la pagina Tag **ambito.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="f87cd-185">I tag di ambito sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="f87cd-185">Scope tags are optional.</span></span> <span data-ttu-id="f87cd-186">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="f87cd-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="f87cd-187">Nella **pagina Assegnazioni** selezionare i gruppi che riceveranno il profilo.</span><span class="sxs-lookup"><span data-stu-id="f87cd-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="f87cd-188">Per questo scenario, è consigliabile scegliere come destinazione **Tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="f87cd-189">Per ulteriori informazioni sull'assegnazione di profili, vedere [Assegnare profili utente e dispositivo.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="f87cd-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="f87cd-190">Quando si distribuisce ai gruppi di utenti, un utente deve accedere a un dispositivo prima dell'applicazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="f87cd-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="f87cd-191">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-191">Click **Next**.</span></span>

1. <span data-ttu-id="f87cd-192">Al termine della pagina Revisione **e** creazione scegliere **Crea.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="f87cd-193">Il nuovo profilo viene visualizzato nell'elenco dei profili di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f87cd-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="f87cd-194">Successivamente, per le funzionalità avanzate di anti-phishing, puoi distribuire un profilo personalizzato nei dispositivi iOS supervisionati.</span><span class="sxs-lookup"><span data-stu-id="f87cd-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="f87cd-195">Seguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f87cd-195">Follow the steps below:</span></span>
    - <span data-ttu-id="f87cd-196">Scaricare il profilo di configurazione da [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="f87cd-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="f87cd-197">Passare a **Dispositivi profili** di  ->  **configurazione iOS/iPadOS** Crea  ->    ->  **profilo**</span><span class="sxs-lookup"><span data-stu-id="f87cd-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f87cd-198">![Immagine di Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="f87cd-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="f87cd-199">Specificare un nome del profilo.</span><span class="sxs-lookup"><span data-stu-id="f87cd-199">Provide a name of the profile.</span></span> <span data-ttu-id="f87cd-200">Quando viene richiesto di importare un file del profilo di configurazione, selezionare quello scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f87cd-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="f87cd-201">Nella sezione **Assegnazione** seleziona il gruppo di dispositivi a cui vuoi applicare il profilo.</span><span class="sxs-lookup"><span data-stu-id="f87cd-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="f87cd-202">Come procedura consigliata, questa operazione deve essere applicata a tutti i dispositivi iOS gestiti.</span><span class="sxs-lookup"><span data-stu-id="f87cd-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="f87cd-203">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-203">Click **Next**.</span></span>
    - <span data-ttu-id="f87cd-204">Al termine della pagina Revisione **e** creazione scegliere **Crea.**</span><span class="sxs-lookup"><span data-stu-id="f87cd-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="f87cd-205">Il nuovo profilo viene visualizzato nell'elenco dei profili di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f87cd-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f87cd-206">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="f87cd-206">Next Steps</span></span>

[<span data-ttu-id="f87cd-207">Configurare Defender per le funzionalità di Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="f87cd-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
