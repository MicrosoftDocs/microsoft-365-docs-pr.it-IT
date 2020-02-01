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
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 47ce137f785c595992886c756ad85b80957272fe
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594976"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Convalidare le impostazioni di protezione delle app nei dispositivi Android o iOS

Seguire le istruzioni riportate nelle sezioni seguenti per convalidare le impostazioni di protezione delle app nei dispositivi Android o iOS.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Verificare che le impostazioni di protezione delle app funzionino sui dispositivi utente

Dopo avere [impostato le configurazioni delle app per dispositivi Android](app-protection-settings-for-android-and-ios.md) per proteggere le app, è possibile seguire queste procedure per verificare che le impostazioni scelte funzionino. 
  
Prima di tutto, assicurarsi che il criterio si applichi all'app in cui si intende convalidarla.
  
1. Nell'[interfaccia di amministrazione](https://portal.office.com) di Microsoft 365 Business scegliere **Criteri** \> **Modifica criterio**.
    
2. Scegliere **criteri applicazione per Android** per le impostazioni create al momento della configurazione o un altro criterio creato e verificare che sia applicato a Outlook, ad esempio. 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Verificare il criterio Richiedi un PIN o l'impronta digitale per accedere alle app di Office

Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi un PIN o l'impronta digitale per accedere alle app di Office** sia **attivata**.
  
![Assicurarsi che il PIN o l'impronta digitale per accedere alle app di Office sia impostato su attivato.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.
    
2. Verrà inoltre richiesto di immettere un PIN o di utilizzare un'impronta digitale.
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Verificare il criterio Reimposta il PIN dopo il numero di tentativi non riusciti

Nel riquadro **modifica criterio** fare clic su **modifica** accanto a **controllo di accesso ai documenti di Office**, quindi **gestire la modalità di accesso degli utenti ai file di Office nei dispositivi mobili**e verificare che il **pin di reset dopo il numero di tentativi non riusciti** sia impostato su un numero. Questo è 5 per impostazione predefinita. 
  
1. Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.
    
2. Immettere un PIN non corretto per il numero di volte specificato dal criterio. Verrà visualizzato un messaggio che indica che è stato **raggiunto il limite di tentativi** per reimpostare il PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Scegliere **Reimposta PIN**. Verrà richiesto di eseguire l'accesso con le credenziali aziendali Microsoft 365 dell'utente e quindi di impostare un nuovo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Verificare il criterio Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business

Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **attivata**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.
    
2. Aprire un messaggio di posta elettronica che contiene un allegato e toccare l'icona della freccia in giù accanto alle informazioni sull'allegato.
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Vedrai che **non è possibile salvare nel dispositivo** nella parte inferiore dello schermo. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Attualmente il salvataggio in OneDrive for Business non è abilitato per Android, quindi si vedrà solo che il salvataggio in locale è bloccato. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Verificare il criterio Richiedi all'utente di accedere di nuovo se le app di Office sono rimaste inattive per il periodo di tempo specificato

Nel riquadro **modifica criterio** fare clic su **modifica** accanto a **controllo di accesso ai documenti di Office**, quindi **gestire la modalità di accesso degli utenti ai file di Office nei dispositivi mobili**e verificare che gli utenti siano autorizzati a accedere di **nuovo dopo che le app di Office sono rimaste inattive per** un determinato numero di minuti. Questo è 30 minuti per impostazione predefinita. 
  
1. Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.
    
2. Dovrebbe essere visualizzata la posta in arrivo di Outlook. Non usare il dispositivo Android per almeno 30 minuti o comunque per un periodo di tempo superiore a quello specificato nel criterio. Il dispositivo probabilmente diventerà inattivo.
    
3. Accedere di nuovo a Outlook sul dispositivo Android.
    
4. Verrà richiesto di immettere il PIN prima di poter accedere di nuovo a Outlook.
    
### <a name="validate-protect-work-files-with-encryption"></a>Verificare il criterio Proteggi i file di lavoro con la crittografia

Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** sia **attivata** e che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **disattivata**.
  
1. Nel dispositivo Android dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.
    
2. Aprire un messaggio di posta elettronica contenente alcuni allegati di file di immagine.
    
3. Toccare l'icona della freccia in giù accanto alle informazioni sull'allegato per salvarlo.
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Potrebbe essere visualizzata la richiesta di consentire a Outlook di accedere a foto, contenuti multimediali e file archiviati nel dispositivo. Toccare **Consenti**.
    
5. Nella parte inferiore dello schermo scegliere **Salva nel dispositivo** e aprire l'app **Galleria**. 
    
6. Dovrebbe essere visualizzata una foto crittografata (o più foto, se sono stati salvati più file di immagine allegati) nell'elenco. Nell'elenco Foto potrebbe essere visualizzata come un quadrato grigio con un punto esclamativo bianco all'interno di un cerchio bianco al centro del quadrato grigio.
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Verificare che le impostazioni di protezione delle app funzionino nei dispositivi degli utenti

Dopo avere [impostato le configurazioni delle app per dispositivi iOS](app-protection-settings-for-android-and-ios.md) per proteggere le app, è possibile seguire queste procedure per verificare che le impostazioni scelte funzionino. 
  
Prima di tutto, assicurarsi che il criterio si applichi all'app in cui si intende convalidarla.
  
1. Nell'[interfaccia di amministrazione](https://portal.office.com) di Microsoft 365 Business scegliere **Criteri** \> **Modifica criterio**.
    
2. Scegliere **criteri applicazione per iOS** per le impostazioni create al momento dell'installazione o un altro criterio creato e verificare che sia applicato a Outlook, ad esempio. 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Verificare il criterio di richiesta di un PIN per accedere alle app di Office

Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Controllo dell'accesso ai documenti di Office**, espandere **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** e verificare che l'opzione **Richiedi un PIN o l'impronta digitale per accedere alle app di Office** sia **attivata**.
  
![Assicurarsi che il PIN o l'impronta digitale per accedere alle app di Office sia impostato su attivato.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.
    
2. Verrà inoltre richiesto di immettere un PIN o di utilizzare un'impronta digitale.
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Verificare il criterio Reimposta il PIN dopo il numero di tentativi non riusciti

Nel riquadro **modifica criterio** fare clic su **modifica** accanto a **controllo di accesso ai documenti di Office**, quindi **gestire la modalità di accesso degli utenti ai file di Office nei dispositivi mobili**e verificare che il **pin di reset dopo il numero di tentativi non riusciti** sia impostato su un numero. Questo è 5 per impostazione predefinita. 
  
1. Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente.
    
2. Immettere un PIN non corretto per il numero di volte specificato dal criterio. Verrà visualizzato un messaggio che indica che è stato **raggiunto il limite di tentativi** per reimpostare il PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Scegliere **OK**. Verrà richiesto di eseguire l'accesso con le credenziali aziendali Microsoft 365 dell'utente e quindi di impostare un nuovo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Verificare il criterio Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business

Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **attivata**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.
    
2. Aprire un messaggio di posta elettronica che contiene un allegato, aprire l'allegato e scegliere **Salva** nella parte inferiore dello schermo. 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. Dovrebbe essere visualizzata solo un'opzione per OneDrive for Business. In caso contrario, toccare **Aggiungi account** e selezionare **OneDrive for business** dalla schermata **Aggiungi account di archiviazione** . Quando richiesto, specificare le credenziali di Microsoft 365 Business dell'utente finale per accedere. 
    
    Toccare **Salva** e selezionare **OneDrive for Business**.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Verificare il criterio Richiedi all'utente di accedere di nuovo se le app di Office sono rimaste inattive per il periodo di tempo specificato

Nel riquadro **modifica criterio** fare clic su **modifica** accanto a **controllo di accesso ai documenti di Office**, quindi **gestire la modalità di accesso degli utenti ai file di Office nei dispositivi mobili**e verificare che gli utenti siano autorizzati a accedere di **nuovo dopo che le app di Office sono rimaste inattive per** un determinato numero di minuti. Questo è 30 minuti per impostazione predefinita. 
  
1. Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.
    
2. Dovrebbe essere visualizzata la posta in arrivo di Outlook. Non usare il dispositivo iOS per almeno 30 minuti o comunque per un periodo di tempo superiore a quello specificato nel criterio. Il dispositivo probabilmente diventerà inattivo.
    
3. Accedere di nuovo a Outlook sul dispositivo iOS.
    
4. Verrà richiesto di immettere il PIN prima di poter accedere di nuovo a Outlook.
    
### <a name="validate-protect-work-files-with-encryption"></a>Verificare il criterio Proteggi i file di lavoro con la crittografia

Nel riquadro **Modifica criterio** scegliere **Modifica** accanto a **Protezione in caso di smarrimento o furto dei dispositivi**, espandere **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** e verificare che l'opzione **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** sia **attivata** e che l'opzione **Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business** sia **disattivata**.
  
1. Nel dispositivo iOS dell'utente aprire Outlook e accedere con le credenziali di Microsoft 365 Business dell'utente, quindi immettere il PIN se richiesto.
    
2. Aprire un messaggio di posta elettronica contenente alcuni allegati di file di immagine.
    
3. Toccare l'allegato e quindi toccare l'opzione **Salva** sotto di esso. 
    
4. Aprire l'app **Foto** dalla schermata iniziale. Dovrebbe essere visualizzata una foto (o più foto, se sono stati salvati più file di immagine allegati) salvata, ma crittografata. 
    
---

