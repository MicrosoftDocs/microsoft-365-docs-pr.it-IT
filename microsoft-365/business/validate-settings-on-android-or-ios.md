---
title: Convalidare le impostazioni di protezione delle app nei dispositivi Android o iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Informazioni su come convalidare le impostazioni di protezione delle app di Microsoft 365 Business Premium nei dispositivi Android o iOS.
ms.openlocfilehash: d4b8ec3ff3a15c25133b20d437249611530977a5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403371"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="6b42a-103">Convalidare le impostazioni di protezione delle app nei dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="6b42a-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="6b42a-104">Segui le istruzioni nelle sezioni seguenti per convalidare le impostazioni di protezione delle app nei dispositivi Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="6b42a-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="6b42a-105">Android</span><span class="sxs-lookup"><span data-stu-id="6b42a-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="6b42a-106">Verificare che le impostazioni di protezione delle app funzionino nei dispositivi degli utenti</span><span class="sxs-lookup"><span data-stu-id="6b42a-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="6b42a-107">Dopo avere [impostato le configurazioni delle app per dispositivi Android](app-protection-settings-for-android-and-ios.md) per proteggere le app, è possibile seguire queste procedure per verificare che le impostazioni scelte funzionino.</span><span class="sxs-lookup"><span data-stu-id="6b42a-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="6b42a-108">Prima di tutto, assicurati che i criteri siano applicabili all'app in cui lo convaliderai.</span><span class="sxs-lookup"><span data-stu-id="6b42a-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="6b42a-109">Nell'interfaccia di amministrazione di Microsoft 365 Business [Premium](https://portal.office.com)passare a **Criteri** \> **di modifica dei criteri.**</span><span class="sxs-lookup"><span data-stu-id="6b42a-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="6b42a-110">Scegliere **Criteri applicazione per Android** per le impostazioni create durante l'installazione o un altro criterio creato e verificare che sia applicato per Outlook, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="6b42a-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="6b42a-112">Verificare il criterio Richiedi un PIN o l'impronta digitale per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="6b42a-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="6b42a-113">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi un PIN o l'impronta digitale per accedere alle app di Office** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Verificare che l'opzione Richiedi UN PIN o un'impronta digitale per accedere alle app di Office sia impostata su Sì.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="6b42a-115">Nel dispositivo Android dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6b42a-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="6b42a-116">Ti verrà richiesto anche di immettere un PIN o di usare un'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="6b42a-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="6b42a-118">Verificare il criterio Reimposta il PIN dopo il numero di tentativi non riusciti</span><span class="sxs-lookup"><span data-stu-id="6b42a-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="6b42a-119">Nel **riquadro** Modifica criteri  scegliere Modifica accanto al controllo di accesso ai documenti di **Office,** espandere Gestisci la modalità di accesso degli utenti ai file di **Office** nei dispositivi mobili e assicurarsi che reimpostazione **PIN** dopo il numero di tentativi non riusciti sia impostato su un numero.</span><span class="sxs-lookup"><span data-stu-id="6b42a-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="6b42a-120">Questo valore è 5 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6b42a-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="6b42a-121">Nel dispositivo Android dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6b42a-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="6b42a-122">Immettere un PIN non corretto per il numero di volte specificato dal criterio.</span><span class="sxs-lookup"><span data-stu-id="6b42a-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="6b42a-123">Verrà visualizzata una richiesta che indica che è stato raggiunto **il limite di tentativi del PIN** per reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="6b42a-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="6b42a-125">Scegliere **Reimposta PIN**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-125">Press **Reset PIN**.</span></span> <span data-ttu-id="6b42a-126">Ti verrà richiesto di accedere con le credenziali di Microsoft 365 Business Premium dell'utente e quindi ti verrà richiesto di impostare un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="6b42a-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="6b42a-127">Verificare il criterio Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="6b42a-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="6b42a-128">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="6b42a-130">Nel dispositivo Android dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente e immettere un PIN, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="6b42a-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="6b42a-131">Aprire un messaggio di posta elettronica che contiene un allegato e toccare l'icona della freccia in giù accanto alle informazioni sull'allegato.</span><span class="sxs-lookup"><span data-stu-id="6b42a-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="6b42a-133">You'll see **Cannot save to device** on the bottom of the screen.</span><span class="sxs-lookup"><span data-stu-id="6b42a-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="6b42a-135">Attualmente il salvataggio in OneDrive for Business non è abilitato per Android, quindi si vedrà solo che il salvataggio in locale è bloccato.</span><span class="sxs-lookup"><span data-stu-id="6b42a-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="6b42a-136">Verificare il criterio Richiedi all'utente di accedere di nuovo se le app di Office sono rimaste inattive per il periodo di tempo specificato</span><span class="sxs-lookup"><span data-stu-id="6b42a-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="6b42a-137">Nel  riquadro Modifica criteri  scegliere Modifica accanto al controllo di accesso ai documenti di **Office,** espandere Gestisci la modalità di accesso degli utenti ai file di **Office** nei dispositivi mobili e assicurarsi che l'opzione Richiedi agli utenti di accedere di nuovo dopo che le app di **Office** sono state inattive sia impostata su un numero di minuti.</span><span class="sxs-lookup"><span data-stu-id="6b42a-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="6b42a-138">Questo valore è di 30 minuti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6b42a-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="6b42a-139">Nel dispositivo Android dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente e immettere un PIN, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="6b42a-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="6b42a-p105">Dovrebbe essere visualizzata la posta in arrivo di Outlook. Non usare il dispositivo Android per almeno 30 minuti o comunque per un periodo di tempo superiore a quello specificato nel criterio. Il dispositivo probabilmente diventerà inattivo.</span><span class="sxs-lookup"><span data-stu-id="6b42a-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="6b42a-143">Accedere di nuovo a Outlook sul dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="6b42a-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="6b42a-144">Verrà richiesto di immettere il PIN prima di poter accedere di nuovo a Outlook.</span><span class="sxs-lookup"><span data-stu-id="6b42a-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="6b42a-145">Verificare il criterio Proteggi i file di lavoro con la crittografia</span><span class="sxs-lookup"><span data-stu-id="6b42a-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="6b42a-146">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** sia **attivata** e che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="6b42a-147">Nel dispositivo Android dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente e immettere un PIN, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="6b42a-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="6b42a-148">Aprire un messaggio di posta elettronica contenente alcuni file di immagine allegati.</span><span class="sxs-lookup"><span data-stu-id="6b42a-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="6b42a-149">Toccare l'icona della freccia in giù accanto alle informazioni sull'allegato per salvarlo.</span><span class="sxs-lookup"><span data-stu-id="6b42a-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="6b42a-p106">Potrebbe essere visualizzata la richiesta di consentire a Outlook di accedere a foto, contenuti multimediali e file archiviati nel dispositivo. Toccare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="6b42a-153">Nella parte inferiore dello schermo scegliere **Salva nel dispositivo** e aprire l'app **Galleria**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="6b42a-p107">Dovrebbe essere visualizzata una foto crittografata (o più foto, se sono stati salvati più file di immagine allegati) nell'elenco. Nell'elenco Foto potrebbe essere visualizzata come un quadrato grigio con un punto esclamativo bianco all'interno di un cerchio bianco al centro del quadrato grigio.</span><span class="sxs-lookup"><span data-stu-id="6b42a-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="6b42a-157">iOS</span><span class="sxs-lookup"><span data-stu-id="6b42a-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="6b42a-158">Verificare che le impostazioni di protezione delle app funzionino nei dispositivi degli utenti</span><span class="sxs-lookup"><span data-stu-id="6b42a-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="6b42a-159">Dopo avere [impostato le configurazioni delle app per dispositivi iOS](app-protection-settings-for-android-and-ios.md) per proteggere le app, è possibile seguire queste procedure per verificare che le impostazioni scelte funzionino.</span><span class="sxs-lookup"><span data-stu-id="6b42a-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="6b42a-160">Prima di tutto, assicurati che i criteri siano applicabili all'app in cui lo convaliderai.</span><span class="sxs-lookup"><span data-stu-id="6b42a-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="6b42a-161">Nell'interfaccia di amministrazione di Microsoft 365 Business [Premium](https://portal.office.com)passare a **Criteri** \> **di modifica dei criteri.**</span><span class="sxs-lookup"><span data-stu-id="6b42a-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="6b42a-162">Scegliere **Criteri applicazione per iOS** per le impostazioni create durante l'installazione o un altro criterio creato e verificare che sia applicato per Outlook, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="6b42a-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="6b42a-164">Verificare il criterio di richiesta di un PIN per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="6b42a-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="6b42a-165">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi un PIN o l'impronta digitale per accedere alle app di Office** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Verificare che l'opzione Richiedi UN PIN o un'impronta digitale per accedere alle app di Office sia impostata su Sì.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="6b42a-167">Nel dispositivo iOS dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6b42a-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="6b42a-168">Ti verrà richiesto anche di immettere un PIN o di usare un'impronta digitale.</span><span class="sxs-lookup"><span data-stu-id="6b42a-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="6b42a-170">Verificare il criterio Reimposta il PIN dopo il numero di tentativi non riusciti</span><span class="sxs-lookup"><span data-stu-id="6b42a-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="6b42a-171">Nel **riquadro** Modifica criteri  scegliere Modifica accanto al controllo di accesso ai documenti di **Office,** espandere Gestisci la modalità di accesso degli utenti ai file di **Office** nei dispositivi mobili e assicurarsi che reimpostazione **PIN** dopo il numero di tentativi non riusciti sia impostato su un numero.</span><span class="sxs-lookup"><span data-stu-id="6b42a-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="6b42a-172">Questo valore è 5 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6b42a-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="6b42a-173">Nel dispositivo iOS dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6b42a-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="6b42a-174">Immettere un PIN non corretto per il numero di volte specificato dal criterio.</span><span class="sxs-lookup"><span data-stu-id="6b42a-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="6b42a-175">Verrà visualizzata una richiesta che indica che è stato raggiunto **il limite di tentativi del PIN** per reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="6b42a-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="6b42a-177">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-177">Press **OK**.</span></span> <span data-ttu-id="6b42a-178">Ti verrà richiesto di accedere con le credenziali di Microsoft 365 Business Premium dell'utente e quindi ti verrà richiesto di impostare un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="6b42a-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="6b42a-179">Verificare il criterio Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="6b42a-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="6b42a-180">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **attivata**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="6b42a-182">Nel dispositivo iOS dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente e immettere un PIN, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="6b42a-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="6b42a-183">Aprire un messaggio di posta elettronica che contiene un allegato, aprire l'allegato e scegliere **Salva** nella parte inferiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="6b42a-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="6b42a-185">Dovrebbe essere visualizzata solo un'opzione per OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="6b42a-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="6b42a-186">In caso contrario, toccare **Aggiungi account** e selezionare **OneDrive for Business** nella schermata Aggiungi account **di** archiviazione.</span><span class="sxs-lookup"><span data-stu-id="6b42a-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="6b42a-187">Fornisci a Microsoft 365 Business Premium dell'utente finale l'accesso quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="6b42a-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="6b42a-188">Toccare **Salva** e selezionare **OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="6b42a-189">Verificare il criterio Richiedi all'utente di accedere di nuovo se le app di Office sono rimaste inattive per il periodo di tempo specificato</span><span class="sxs-lookup"><span data-stu-id="6b42a-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="6b42a-190">Nel  riquadro Modifica criteri  scegliere Modifica accanto al controllo di accesso ai documenti di **Office,** espandere Gestisci la modalità di accesso degli utenti ai file di **Office** nei dispositivi mobili e assicurarsi che l'opzione Richiedi agli utenti di accedere di nuovo dopo che le app di **Office** sono state inattive sia impostata su un numero di minuti.</span><span class="sxs-lookup"><span data-stu-id="6b42a-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="6b42a-191">Questo valore è di 30 minuti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6b42a-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="6b42a-192">Nel dispositivo iOS dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente e immettere un PIN, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="6b42a-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="6b42a-p113">Dovrebbe essere visualizzata la posta in arrivo di Outlook. Non usare il dispositivo iOS per almeno 30 minuti o comunque per un periodo di tempo superiore a quello specificato nel criterio. Il dispositivo probabilmente diventerà inattivo.</span><span class="sxs-lookup"><span data-stu-id="6b42a-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="6b42a-196">Accedere di nuovo a Outlook sul dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="6b42a-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="6b42a-197">Verrà richiesto di immettere il PIN prima di poter accedere di nuovo a Outlook.</span><span class="sxs-lookup"><span data-stu-id="6b42a-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="6b42a-198">Verificare il criterio Proteggi i file di lavoro con la crittografia</span><span class="sxs-lookup"><span data-stu-id="6b42a-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="6b42a-199">Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** sia **attivata** e che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="6b42a-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="6b42a-200">Nel dispositivo iOS dell'utente, aprire Outlook e accedere con le credenziali di Microsoft 365 Business Premium dell'utente e immettere un PIN, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="6b42a-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="6b42a-201">Aprire un messaggio di posta elettronica contenente alcuni file di immagine allegati.</span><span class="sxs-lookup"><span data-stu-id="6b42a-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="6b42a-202">Toccare l'allegato e quindi toccare l'opzione **Salva** sotto di esso.</span><span class="sxs-lookup"><span data-stu-id="6b42a-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="6b42a-p114">Aprire l'app **Foto** dalla schermata iniziale. Dovrebbe essere visualizzata una foto (o più foto, se sono stati salvati più file di immagine allegati) salvata, ma crittografata.</span><span class="sxs-lookup"><span data-stu-id="6b42a-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

