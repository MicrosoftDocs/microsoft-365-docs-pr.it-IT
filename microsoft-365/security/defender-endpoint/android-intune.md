---
title: Distribuire Microsoft Defender ATP per Android con Microsoft Intune
description: Descrive come distribuire Microsoft Defender ATP per Android con Microsoft Intune
keywords: microsoft, defender, atp, android, installazione, distribuzione, disinstallazione,
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
ms.openlocfilehash: e557f60346b2f68354df621b6e4812eac775d812
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165670"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-android-with-microsoft-intune"></a><span data-ttu-id="0d6a8-104">Distribuire Microsoft Defender per Endpoint per Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0d6a8-104">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0d6a8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="0d6a8-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="0d6a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0d6a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d6a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0d6a8-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0d6a8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0d6a8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="0d6a8-110">Scopri come distribuire Defender per Endpoint per Android nei dispositivi registrati nel portale aziendale di Intune.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="0d6a8-111">Per altre informazioni sulla registrazione dei dispositivi Intune, vedi [Registrare il dispositivo.](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="0d6a8-112">**Defender for Endpoint per Android è ora disponibile su [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="0d6a8-113">Puoi connetterti a Google Play da Intune per distribuire l'app Defender for Endpoint tra le modalità di entrollment di Amministratore dispositivo e Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="0d6a8-114">Gli aggiornamenti dell'app sono automatici tramite Google Play.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="0d6a8-115">Distribuire nei dispositivi registrati dall'amministratore di dispositivi</span><span class="sxs-lookup"><span data-stu-id="0d6a8-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="0d6a8-116">**Distribuire Defender per Endpoint per Android nel portale aziendale di Intune - Dispositivi registrati dall'amministratore del dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="0d6a8-117">Informazioni su come distribuire Defender per Endpoint per Android nel portale aziendale di Intune - Dispositivi registrati dall'amministratore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="0d6a8-118">Aggiungi come app di Android Store</span><span class="sxs-lookup"><span data-stu-id="0d6a8-118">Add as Android store app</span></span>

1. <span data-ttu-id="0d6a8-119">[Nell'interfaccia di amministrazione di Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) vai ad **App** \> **app Android** \> **Aggiungi app di \> Android Store** e scegli **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager per aggiungere un'applicazione store android](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="0d6a8-121">Nella pagina **Aggiungi app** e nella sezione *Informazioni app* immetti:</span><span class="sxs-lookup"><span data-stu-id="0d6a8-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="0d6a8-122">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-122">**Name**</span></span> 
   - <span data-ttu-id="0d6a8-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-123">**Description**</span></span>
   - <span data-ttu-id="0d6a8-124">**Publisher** come Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="0d6a8-125">**URL dell'App Store** come https://play.google.com/store/apps/details?id=com.microsoft.scmx (DEFENDER for Endpoint app Google Play Store URL)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="0d6a8-126">Altri campi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-126">Other fields are optional.</span></span> <span data-ttu-id="0d6a8-127">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-127">Select **Next**.</span></span>

   ![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager per aggiungere informazioni sull'app](images/mda-addappinfo.png)

3. <span data-ttu-id="0d6a8-129">Nella sezione *Assegnazioni* passare alla sezione **Obbligatorio** e selezionare **Aggiungi gruppo.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="0d6a8-130">Puoi quindi scegliere i gruppi di utenti di destinazione dell'app Defender per Endpoint per Android.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="0d6a8-131">Scegliere **Seleziona** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="0d6a8-132">Il gruppo di utenti selezionato deve essere costituito da utenti registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Immagine dei gruppi di utenti selezionati dell'interfaccia di amministrazione di Microsoft Endpoint Manager](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="0d6a8-134">Nella sezione **Revisione e creazione** verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="0d6a8-135">In pochi istanti, l'app Defender for Endpoint viene creata correttamente e viene visualizzata una notifica nell'angolo in alto a destra della pagina.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Immagine della notifica dell'interfaccia di amministrazione di Microsoft Endpoint Manager dell'app endpoint defender](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="0d6a8-137">Nella pagina delle informazioni sull'app visualizzata, nella sezione **Monitor** seleziona **Stato** installazione dispositivo per verificare che l'installazione del dispositivo sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-138">![Immagine dell'installazione del dispositivo dell'interfaccia di amministrazione di Microsoft Endpoint Manager](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0d6a8-139">Completare l'onboarding e controllare lo stato</span><span class="sxs-lookup"><span data-stu-id="0d6a8-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0d6a8-140">Dopo aver installato Defender for Endpoint per Android nel dispositivo, vedrai l'icona dell'app.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![Icona nel dispositivo mobile](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="0d6a8-142">Tocca l'icona dell'app Microsoft Defender ATP e segui le istruzioni visualizzate per completare l'onboarding dell'app.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="0d6a8-143">I dettagli includono l'accettazione da parte dell'utente finale delle autorizzazioni Android richieste da Defender per Endpoint per Android.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="0d6a8-144">Al completamento dell'onboarding, il dispositivo inizierà a essere visualizzato nell'elenco Dispositivi in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Immagine del dispositivo in Defender for Endpoint Portal](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="0d6a8-146">Distribuire nei dispositivi registrati Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="0d6a8-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="0d6a8-147">Defender per Endpoint per Android supporta i dispositivi registrati android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="0d6a8-148">Per altre informazioni sulle opzioni di registrazione supportate da Intune, vedi [Opzioni di registrazione.](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="0d6a8-149">**Attualmente, i dispositivi di proprietà personale con profilo di lavoro e le registrazioni di dispositivi utente completamente gestiti di proprietà dell'azienda sono supportati per la distribuzione.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-for-android-as-a-managed-google-play-app"></a><span data-ttu-id="0d6a8-150">Aggiungere Microsoft Defender per Endpoint per Android come app Google Play gestita</span><span class="sxs-lookup"><span data-stu-id="0d6a8-150">Add Microsoft Defender for Endpoint for Android as a Managed Google Play app</span></span>

<span data-ttu-id="0d6a8-151">Segui i passaggi seguenti per aggiungere l'app Microsoft Defender for Endpoint al tuo Google Play gestito.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="0d6a8-152">[Nell'interfaccia di amministrazione di Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) vai ad **App** \> **App Android** \> **Aggiungi** e seleziona App Google **Play gestita.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-153">![Immagine dell'interfaccia di amministrazione di Microsoft Endpoint Manager gestita da Google Play](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="0d6a8-154">Nella pagina gestita di Google Play che viene caricata successivamente, vai alla casella di ricerca e cerca **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="0d6a8-155">La ricerca dovrebbe visualizzare l'app Microsoft Defender for Endpoint in Managed Google Play.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="0d6a8-156">Fai clic sull'app Microsoft Defender for Endpoint dal risultato della ricerca App.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Immagine della ricerca app nell'interfaccia di amministrazione di Microsoft Endpoint Manager](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="0d6a8-158">Nella pagina Descrizione app che verrà visualizzata successivamente, dovresti essere in grado di visualizzare i dettagli dell'app in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="0d6a8-159">Esaminare le informazioni nella pagina e quindi selezionare **Approva**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-160">![Screenshot di un google play gestito](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="0d6a8-161">Ti verranno presentate le autorizzazioni che Defender for Endpoint ottiene perché funzioni.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="0d6a8-162">Esaminali e quindi seleziona **Approva**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-162">Review them and then select **Approve**.</span></span>

    ![Screenshot dell'approvazione dell'app Defender for Endpoint preview](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="0d6a8-164">Verrà visualizzata la pagina Impostazioni approvazione.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="0d6a8-165">La pagina conferma la tua preferenza per gestire le nuove autorizzazioni dell'app che Defender per Endpoint per Android potrebbe richiedere.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="0d6a8-166">Esamina le scelte e seleziona l'opzione preferita.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="0d6a8-167">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-167">Select **Done**.</span></span>

    <span data-ttu-id="0d6a8-168">Per impostazione predefinita, google play gestito seleziona *Mantieni approvato quando l'app richiede nuove autorizzazioni*</span><span class="sxs-lookup"><span data-stu-id="0d6a8-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-169">![Immagine della scheda notifiche](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="0d6a8-170">Dopo aver selezionato la gestione delle autorizzazioni, seleziona **Sincronizza** per sincronizzare Microsoft Defender per Endpoint con l'elenco delle app.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-171">![Immagine della pagina di sincronizzazione](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="0d6a8-172">La sincronizzazione verrà completata tra pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-172">The sync will complete in a few minutes.</span></span>

    ![Immagine dell'app Android](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="0d6a8-174">Seleziona il **pulsante** Aggiorna nella schermata delle app Android e Microsoft Defender ATP dovrebbe essere visibile nell'elenco delle app.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-175">![Immagine dell'elenco delle app Android](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="0d6a8-176">Defender for Endpoint supporta i criteri di configurazione delle app per i dispositivi gestiti tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="0d6a8-177">Questa funzionalità può essere sfruttata per applicare automaticamente le autorizzazioni Android applicabili, in modo che l'utente finale non deve accettare queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="0d6a8-178">Nella pagina **App** vai a Criteri > criteri di configurazione **delle app > Aggiungi > dispositivi gestiti**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Immagine dei dispositivi gestiti android dell'interfaccia di amministrazione di Microsoft Endpoint Manager](images/android-mem.png)

    1. <span data-ttu-id="0d6a8-180">Nella pagina **Crea criteri di configurazione app** immetti i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d6a8-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="0d6a8-181">Nome: Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="0d6a8-182">Scegli **Android Enterprise** come piattaforma.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="0d6a8-183">Scegliere **Solo profilo di lavoro** come tipo di profilo.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="0d6a8-184">Fai **clic su Seleziona app,** scegli Microsoft Defender **ATP,** **seleziona OK** e quindi **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="0d6a8-185">![Immagine della pagina crea criteri di configurazione dell'app](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="0d6a8-186">Nella pagina **Impostazioni** passare alla sezione Autorizzazioni fare clic su Aggiungi per visualizzare l'elenco delle autorizzazioni supportate.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="0d6a8-187">Nella sezione Aggiungi autorizzazioni selezionare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d6a8-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="0d6a8-188">Archiviazione esterna (lettura)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-188">External storage (read)</span></span>
       - <span data-ttu-id="0d6a8-189">Archiviazione esterna (scrittura)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-189">External storage (write)</span></span>

       <span data-ttu-id="0d6a8-190">Infine scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="0d6a8-191">![Immagine dei criteri di configurazione per la creazione di app in Android](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="0d6a8-192">A questo punto dovrebbero essere elencate entrambe le autorizzazioni e ora è possibile eseguire l'autogrant entrambe scegliendo autogrant nell'elenco **a** discesa Stato autorizzazione e quindi **selezionare Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0d6a8-193">![Immagine della concessione automatica android per la creazione di criteri di configurazione dell'app](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="0d6a8-194">Nella pagina **Assegnazioni** seleziona il gruppo di utenti a cui verrebbe assegnato questo criterio di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="0d6a8-195">Fare **clic su Seleziona gruppi per includere** e selezionare il gruppo applicabile e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="0d6a8-196">Il gruppo selezionato qui è in genere lo stesso gruppo a cui assegni Microsoft Defender per l'app Endpoint Android.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0d6a8-197">![Immagine del criterio di configurazione per la creazione di app](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="0d6a8-198">Nella pagina **Revisione e creazione** visualizzata successivamente, esaminare tutte le informazioni e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="0d6a8-199">I criteri di configurazione dell'app per Defender per Endpoint che esereranno automaticamente l'autorizzazione di archiviazione vengono ora assegnati al gruppo di utenti selezionato.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="0d6a8-200">![Immagine di android review create app config policy](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="0d6a8-201">Seleziona **App Microsoft Defender ATP** nell'elenco \> **Proprietà** \> **Assegnazioni** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Immagine dell'elenco delle app](images/mda-properties.png)


11. <span data-ttu-id="0d6a8-203">Assegna l'app come app *Obbligatoria* a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="0d6a8-204">Viene installato automaticamente nel profilo *di lavoro* durante la successiva sincronizzazione del dispositivo tramite l'app Portale aziendale.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="0d6a8-205">Per eseguire questa assegnazione, passare  alla sezione Obbligatorio \> **Aggiungi,** selezionare il gruppo di utenti e fare clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-206">![Immagine della pagina di modifica dell'applicazione](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="0d6a8-207">Nella pagina **Modifica** applicazione esaminare tutte le informazioni immesse in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="0d6a8-208">Seleziona quindi **Rivedi + Salva** e quindi **salva di** nuovo per iniziare l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="0d6a8-209">Configurazione automatica della VPN always-on</span><span class="sxs-lookup"><span data-stu-id="0d6a8-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="0d6a8-210">Defender for Endpoint supporta i criteri di configurazione dei dispositivi per i dispositivi gestiti tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="0d6a8-211">Questa funzionalità può essere sfruttata per la configurazione automatica della **VPN Always-on** nei dispositivi registrati android Enterprise, quindi l'utente finale non deve configurare il servizio VPN durante l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="0d6a8-212">In **Dispositivi** seleziona Profili **di configurazione** Crea piattaforma profilo Android Enterprise Seleziona restrizioni dispositivo in una delle seguenti  >    >    >   condizioni, in base al tipo di registrazione del dispositivo </span><span class="sxs-lookup"><span data-stu-id="0d6a8-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="0d6a8-213">**Profilo di lavoro completamente gestito, dedicato e Corporate-Owned aziendale**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="0d6a8-214">**Profilo di lavoro di proprietà personale**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="0d6a8-215">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-215">Select **Create**.</span></span>
 
   > ![Immagine del profilo di configurazione dei dispositivi Crea](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="0d6a8-217">**Impostazioni di configurazione** Specificare un **nome e** una **descrizione per** identificare in modo univoco il profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Immagine del profilo di configurazione dei dispositivi Nome e descrizione](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="0d6a8-219">Selezionare **Connettività** e configurare VPN:</span><span class="sxs-lookup"><span data-stu-id="0d6a8-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="0d6a8-220">Abilita **Configurazione VPN always-on** un client VPN nel profilo di lavoro per connettersi e riconnettersi automaticamente alla VPN quando possibile.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="0d6a8-221">È possibile configurare un solo client VPN per la VPN always-on in un determinato dispositivo, quindi assicurati di non distribuire più di un criterio VPN always-on in un singolo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="0d6a8-222">Selezionare **Personalizzato** nell'elenco a discesa client VPN Vpn personalizzata in questo caso è Defender for Endpoint VPN che viene usato per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="0d6a8-223">L'app Microsoft Defender ATP deve essere installata nel dispositivo dell'utente per poter funzionare con la configurazione automatica di questa VPN.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="0d6a8-224">Immetti **l'ID** pacchetto dell'app Microsoft Defender ATP in Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="0d6a8-225">Per l'URL dell'app Defender https://play.google.com/store/apps/details?id=com.microsoft.scmx , l'ID pacchetto è **com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="0d6a8-226">**Modalità di blocco** Non configurato (predefinito)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Immagine del profilo di configurazione dei dispositivi che abilita VPN always-on](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="0d6a8-228">**Assegnazione** Nella pagina  **Assegnazioni** seleziona il gruppo di utenti a cui verrebbe assegnato questo criterio   di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="0d6a8-229">Fare **clic su Seleziona gruppi** da includere e selezionare il gruppo applicabile e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="0d6a8-230">Il gruppo selezionato qui è in genere lo stesso gruppo a cui assegni Microsoft Defender per l'app Endpoint Android.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Immagine del profilo di configurazione dei dispositivi Assegnazione](images/4autosetupofvpn.png)

5. <span data-ttu-id="0d6a8-232">Nella pagina **Revisione e creazione** visualizzata successivamente, esaminare tutte le informazioni e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="0d6a8-233">Il profilo di configurazione del dispositivo è ora assegnato al gruppo di utenti selezionato.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Immagine del profilo di configurazione dei dispositivi Revisione e creazione](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0d6a8-235">Completare l'onboarding e controllare lo stato</span><span class="sxs-lookup"><span data-stu-id="0d6a8-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0d6a8-236">Confermare lo stato di installazione di Microsoft Defender per Endpoint per Android facendo clic su **Stato installazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-236">Confirm the installation status of Microsoft Defender for Endpoint for Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="0d6a8-237">Verifica che il dispositivo sia visualizzato qui.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0d6a8-238">![Immagine dello stato di installazione del dispositivo](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="0d6a8-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="0d6a8-239">Nel dispositivo puoi convalidare lo stato di onboarding andando al **profilo di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="0d6a8-240">Verifica che Defender for Endpoint sia disponibile e che tu sia registrato nei dispositivi di proprietà **personale con profilo di lavoro.**</span><span class="sxs-lookup"><span data-stu-id="0d6a8-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="0d6a8-241">Se sei registrato in un dispositivo utente completamente gestito di proprietà dell'azienda, nel dispositivo sarà disponibile un singolo profilo in cui puoi verificare che Defender for Endpoint sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Immagine dell'app nel dispositivo mobile](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="0d6a8-243">Quando l'app è installata, apri l'app e accetta le autorizzazioni e quindi l'onboarding dovrebbe avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Immagine del dispositivo mobile con l'app Microsoft Defender for Endpoint](images/mda-devicesafe.png)

4. <span data-ttu-id="0d6a8-245">In questa fase il dispositivo viene correttamente onboarded su Defender per Endpoint per Android.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="0d6a8-246">Puoi verificarlo in [Microsoft Defender Security Center](https://securitycenter.microsoft.com) accedendo alla **pagina** Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0d6a8-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Immagine di Microsoft Defender for Endpoint Portal](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="0d6a8-248">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0d6a8-248">Related topics</span></span>
- [<span data-ttu-id="0d6a8-249">Panoramica di Microsoft Defender per Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="0d6a8-249">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="0d6a8-250">Configurare le funzionalità di Microsoft Defender per Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="0d6a8-250">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)