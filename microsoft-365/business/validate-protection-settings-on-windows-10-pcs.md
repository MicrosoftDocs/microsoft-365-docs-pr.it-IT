---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Convalidare le impostazioni di protezione delle app di Microsoft 365 Business Premium nei dispositivi Windows 10 e verificare che gli utenti non possano copiare i dati aziendali in file personali o app non gestite.
ms.openlocfilehash: 20b2e43ae53486c046440ff1066d241ec9661888
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635745"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Verificare le impostazioni di protezione delle app nei PC Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi aziendali

Dopo aver [configurato i criteri di protezione delle app](protection-settings-for-windows-10-devices.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti. Se è stata **attivata l'** opzione **Impedisci agli utenti di copiare i dati dell'azienda in file personali e forzarli a salvare i file di lavoro in OneDrive for business** per i dispositivi di proprietà della società, è possibile controllare questo sul dispositivo dell'utente dopo che è stato connesso a Azure ad e che è stato eseguito l'accesso. 
  
 **Verificare le impostazioni di connessione**
  
1. Dopo aver eseguito l'accesso con le credenziali di Microsoft 365 Business Premium e la connessione ad Azure ad, come descritto in [configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium](set-up-windows-devices.md), passare a **account** \> di accesso a **Windows Settings** \> **work or School**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Nella pagina **gestito da** \<nome\> tenant, è possibile visualizzare le **informazioni di connessione** che includono un **indirizzo del server di gestione** come quello illustrato nella figura seguente. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Verificare che non sia possibile incollare i dati della società in un'app non gestita**
  
1. Aprire Outlook 2016 che è stato installato da Microsoft 365 Business Premium.
    
2. Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.
    
    Aprire Blocco note e provare a incollare il contenuto.
    
    Verrà visualizzato un messaggio di errore che indica che l'app non può accedere al contenuto.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Lo stesso contenuto può però essere incollato in Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi personali

 **Verificare le impostazioni di connessione**
  
1. Nel dispositivo personale Windows 10 in cui si è connessi come utenti locali, andare a impostazioni di **Windows**, quindi fare clic o toccare **account** \> **o accedere a School**.
    
2. Scegliere **Connetti** in **Accedi all'azienda o all'istituto di istruzione**.
    
3. Immettere le credenziali Microsoft 365 Business Premium nell' **accesso**alla finestra di \> **dialogo Configura un account aziendale o dell'Istituto di istruzione** .
    
4. Nella pagina **Accedi all'azienda o all'istituto di istruzione** scegliere **Account aziendale o dell'istituto di istruzione**, quindi scegliere **Informazioni**.
    
    ![Fare clic o toccare informazioni nella finestra di dialogo account aziendale o dell'Istituto di istruzione.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Nella pagina **accesso al lavoro o all'Istituto di istruzione** , è possibile visualizzare le **informazioni di connessione** che includono un indirizzo del **server di gestione** come quello illustrato nella figura seguente e include le parole *WIP* e *Mam* all'interno. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Verificare che non sia possibile incollare i dati della società in un'app non gestita**
  
1. Aprire Outlook 2016 e aggiungere l'account Premium di Microsoft 365 business, se necessario, ed eseguire l'accesso con le credenziali di Microsoft 365 Business Premium.
    
2. Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.
    
    Aprire Blocco note e provare a incollare il contenuto.
    
    Verrà visualizzato un messaggio di errore che indica che l'app non può accedere al contenuto.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Lo stesso contenuto può però essere incollato in Word 2016.
    

