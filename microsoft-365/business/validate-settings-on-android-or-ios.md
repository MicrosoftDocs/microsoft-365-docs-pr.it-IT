---
title: ConValidare le impostazioni di protezione delle app nei dispositivi Android o iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 'Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.  '
ms.openlocfilehash: 5ab16d481bd11ec31a1387a7e94d8b08bb3e0abe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287338"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="1043a-103">ConValidare le impostazioni di protezione delle app nei dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="1043a-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="1043a-104">Seguire le istruzioni riportate nelle schede per convalidare le impostazioni di protezione delle app nei dispositivi Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="1043a-104">Follow the instructions in the tabs to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="androidtab"></a>[<span data-ttu-id="1043a-105">Android</span><span class="sxs-lookup"><span data-stu-id="1043a-105">Android</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="1043a-106">Verificare che le impostazioni di protezione delle app funzionino nei dispositivi degli utenti</span><span class="sxs-lookup"><span data-stu-id="1043a-106">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="1043a-107">Dopo avere [impostato le configurazioni delle app per dispositivi Android](app-protection-settings-for-android-and-ios.md) per proteggere le app, è possibile seguire queste procedure per verificare che le impostazioni scelte funzionino.</span><span class="sxs-lookup"><span data-stu-id="1043a-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="1043a-108">Accertarsi prima di tutto che i criteri si applichino all'app in cui dovranno essere verificati.</span><span class="sxs-lookup"><span data-stu-id="1043a-108">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="1043a-109">Nell'[interfaccia di amministrazione](https://portal.office.com) di Microsoft 365 Business scegliere **Criteri** \> **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="1043a-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="1043a-110">Scegliere **Criteri per le applicazioni per Android** per le impostazioni create al momento della configurazione oppure scegliere un altro criterio creato e verificare che sia applicato a Outlook, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="1043a-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="1043a-112">Verificare il criterio Richiedi un PIN o l'impronta digitale per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="1043a-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="1043a-113">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi un PIN o l'impronta digitale per accedere alle app di Office** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="1043a-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="1043a-115">Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1043a-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="1043a-116">Verrà anche chiesto di immettere un PIN o di usare l'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="1043a-116">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="1043a-118">Verificare il criterio Reimposta il PIN dopo il numero di tentativi non riusciti</span><span class="sxs-lookup"><span data-stu-id="1043a-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="1043a-119">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Reimposta il PIN dopo il numero di tentativi non riusciti** sia impostata su un numero. Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="1043a-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="1043a-120">Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1043a-120">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="1043a-p101">Immettere un PIN non corretto per il numero di volte specificato dal criterio. Verrà visualizzato l'avviso **È stato raggiunto il limite di tentativi per il PIN** con la richiesta di reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="1043a-p101">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="1043a-p102">Scegliere **Reimposta PIN**. Verrà chiesto di accedere con le credenziali di Microsoft 365 Business dell'utente e quindi di impostare un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="1043a-p102">Press **Reset PIN**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="1043a-126">Verificare il criterio Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1043a-126">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="1043a-127">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="1043a-127">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="1043a-129">Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.</span><span class="sxs-lookup"><span data-stu-id="1043a-129">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1043a-130">Aprire un messaggio di posta elettronica che contiene un allegato e toccare l'icona della freccia in giù accanto alle informazioni sull'allegato.</span><span class="sxs-lookup"><span data-stu-id="1043a-130">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="1043a-132">Nella parte inferiore dello schermo verrà visualizzato il messaggio **Non è possibile salvare nel dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1043a-132">You will see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="1043a-134">Attualmente il salvataggio in OneDrive for Business non è abilitato per Android, quindi si vedrà solo che il salvataggio in locale è bloccato.</span><span class="sxs-lookup"><span data-stu-id="1043a-134">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="1043a-135">Verificare il criterio Richiedi all'utente di accedere di nuovo se le app di Office sono rimaste inattive per il periodo di tempo specificato</span><span class="sxs-lookup"><span data-stu-id="1043a-135">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="1043a-136">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per** sia impostata su un numero di minuti. Il valore predefinito è 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="1043a-136">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="1043a-137">Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.</span><span class="sxs-lookup"><span data-stu-id="1043a-137">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1043a-p103">Dovrebbe essere visualizzata la posta in arrivo di Outlook. Non usare il dispositivo Android per almeno 30 minuti o comunque per un periodo di tempo superiore a quello specificato nel criterio. Il dispositivo probabilmente diventerà inattivo.</span><span class="sxs-lookup"><span data-stu-id="1043a-p103">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="1043a-141">Accedere di nuovo a Outlook nel dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="1043a-141">Re-access Outlook on the Android device.</span></span>
    
4. <span data-ttu-id="1043a-142">Verrà chiesto di immettere il PIN per poter accedere di nuovo a Outlook.</span><span class="sxs-lookup"><span data-stu-id="1043a-142">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="1043a-143">Verificare il criterio Proteggi i file di lavoro con la crittografia</span><span class="sxs-lookup"><span data-stu-id="1043a-143">Validate Protect work files with encryption</span></span>

<span data-ttu-id="1043a-144">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** sia **attivata** e che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="1043a-144">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="1043a-145">Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.</span><span class="sxs-lookup"><span data-stu-id="1043a-145">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1043a-146">Aprire un messaggio di posta elettronica che contiene alcuni file di immagine allegati.</span><span class="sxs-lookup"><span data-stu-id="1043a-146">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="1043a-147">Toccare l'icona della freccia in giù accanto alle informazioni sull'allegato per salvarlo.</span><span class="sxs-lookup"><span data-stu-id="1043a-147">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="1043a-p104">Potrebbe essere visualizzata la richiesta di consentire a Outlook di accedere a foto, contenuti multimediali e file archiviati nel dispositivo. Toccare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="1043a-p104">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="1043a-151">Nella parte inferiore dello schermo scegliere **Salva nel dispositivo** e aprire l'app **Galleria**.</span><span class="sxs-lookup"><span data-stu-id="1043a-151">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="1043a-p105">Dovrebbe essere visualizzata una foto crittografata (o più foto, se sono stati salvati più file di immagine allegati) nell'elenco. Nell'elenco Foto potrebbe essere visualizzata come un quadrato grigio con un punto esclamativo bianco all'interno di un cerchio bianco al centro del quadrato grigio.</span><span class="sxs-lookup"><span data-stu-id="1043a-p105">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[<span data-ttu-id="1043a-155">iOS</span><span class="sxs-lookup"><span data-stu-id="1043a-155">iOS</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="1043a-156">Verificare che le impostazioni di protezione delle app funzionino nei dispositivi degli utenti</span><span class="sxs-lookup"><span data-stu-id="1043a-156">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="1043a-157">Dopo avere [impostato le configurazioni delle app per dispositivi iOS](app-protection-settings-for-android-and-ios.md) per proteggere le app, è possibile seguire queste procedure per verificare che le impostazioni scelte funzionino.</span><span class="sxs-lookup"><span data-stu-id="1043a-157">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="1043a-158">Accertarsi prima di tutto che i criteri si applichino all'app in cui dovranno essere verificati.</span><span class="sxs-lookup"><span data-stu-id="1043a-158">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="1043a-159">Nell'[interfaccia di amministrazione](https://portal.office.com) di Microsoft 365 Business scegliere **Criteri** \> **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="1043a-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="1043a-160">Scegliere **Criteri per le applicazioni per iOS** per le impostazioni create al momento della configurazione oppure scegliere un altro criterio creato e verificare che sia applicato a Outlook, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="1043a-160">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="1043a-162">Verificare il criterio di richiesta di un PIN per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="1043a-162">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="1043a-163">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi un PIN o l'impronta digitale per accedere alle app di Office** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="1043a-163">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="1043a-165">Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1043a-165">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="1043a-166">Verrà anche chiesto di immettere un PIN o di usare l'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="1043a-166">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="1043a-168">Verificare il criterio Reimposta il PIN dopo il numero di tentativi non riusciti</span><span class="sxs-lookup"><span data-stu-id="1043a-168">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="1043a-169">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Reimposta il PIN dopo il numero di tentativi non riusciti** sia impostata su un numero. Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="1043a-169">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="1043a-170">Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1043a-170">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="1043a-p106">Immettere un PIN non corretto per il numero di volte specificato dal criterio. Verrà visualizzato l'avviso **È stato raggiunto il limite di tentativi per il PIN** con la richiesta di reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="1043a-p106">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="1043a-p107">Scegliere **OK**. Verrà chiesto di accedere con le credenziali di Microsoft 365 Business dell'utente e quindi di impostare un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="1043a-p107">Press **OK**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="1043a-176">Verificare il criterio Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1043a-176">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="1043a-177">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="1043a-177">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="1043a-179">Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.</span><span class="sxs-lookup"><span data-stu-id="1043a-179">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1043a-180">Aprire un messaggio di posta elettronica che contiene un allegato, aprire l'allegato e scegliere **Salva** nella parte inferiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="1043a-180">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="1043a-p108">Dovrebbe essere visualizzata solo un'opzione per OneDrive for Business. In caso contrario, toccare **Aggiungi account** e selezionare **OneDrive for Business** nella schermata **Aggiungi account di archiviazione**. Quando richiesto, specificare le credenziali di Microsoft 365 Business dell'utente finale per accedere.</span><span class="sxs-lookup"><span data-stu-id="1043a-p108">You should only see an option for OneDrive for Business. If not If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen. Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="1043a-185">Toccare **Salva** e selezionare **OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="1043a-185">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="1043a-186">Verificare il criterio Richiedi all'utente di accedere di nuovo se le app di Office sono rimaste inattive per il periodo di tempo specificato</span><span class="sxs-lookup"><span data-stu-id="1043a-186">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="1043a-187">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per** sia impostata su un numero di minuti. Il valore predefinito è 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="1043a-187">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="1043a-188">Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.</span><span class="sxs-lookup"><span data-stu-id="1043a-188">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1043a-p109">Dovrebbe essere visualizzata la posta in arrivo di Outlook. Non usare il dispositivo iOS per almeno 30 minuti o comunque per un periodo di tempo superiore a quello specificato nel criterio. Il dispositivo probabilmente diventerà inattivo.</span><span class="sxs-lookup"><span data-stu-id="1043a-p109">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="1043a-192">Accedere di nuovo a Outlook nel dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="1043a-192">Re-access Outlook on the iOS device.</span></span>
    
4. <span data-ttu-id="1043a-193">Verrà chiesto di immettere il PIN per poter accedere di nuovo a Outlook.</span><span class="sxs-lookup"><span data-stu-id="1043a-193">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="1043a-194">Verificare il criterio Proteggi i file di lavoro con la crittografia</span><span class="sxs-lookup"><span data-stu-id="1043a-194">Validate Protect work files with encryption</span></span>

<span data-ttu-id="1043a-195">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** sia **attivata** e che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="1043a-195">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="1043a-196">Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.</span><span class="sxs-lookup"><span data-stu-id="1043a-196">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1043a-197">Aprire un messaggio di posta elettronica che contiene alcuni file di immagine allegati.</span><span class="sxs-lookup"><span data-stu-id="1043a-197">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="1043a-198">Toccare l'allegato e quindi toccare l'opzione **Salva** sotto di esso.</span><span class="sxs-lookup"><span data-stu-id="1043a-198">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="1043a-p110">Aprire l'app **Foto** dalla schermata iniziale. Dovrebbe essere visualizzata una foto (o più foto, se sono stati salvati più file di immagine allegati) salvata, ma crittografata.</span><span class="sxs-lookup"><span data-stu-id="1043a-p110">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

