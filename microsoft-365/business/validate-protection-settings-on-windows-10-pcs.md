---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informazioni su come verificare le impostazioni di protezione di applicazioni Microsoft 365 Business nei dispositivi Windows 10.
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868686"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Verificare le impostazioni di protezione delle app nei PC Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi aziendali

Dopo aver [configurato i criteri di protezione delle app](protection-settings-for-windows-10-devices.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti. Se è stata **attivata** l'impostazione **Impedisci agli utenti di copiare dati aziendali in file personali e forzali a salvare i file di lavoro in OneDrive for Business** per i dispositivi di proprietà dell'azienda, è possibile eseguire questo controllo nel dispositivo dell'utente dopo che si è connesso ad Azure Active Directory e ha eseguito l'accesso. 
  
 **Verificare le impostazioni di connessione**
  
1. Dopo aver accedere con le credenziali di Microsoft 365 Business e connettersi al Azure Active Directory, come illustrato in [configurare i dispositivi di Windows per utenti Business 365 Microsoft](set-up-windows-devices.md), passare a **Impostazioni Windows** \> **account** \> **accesso ufficio o scuola **. Scegliere **connessi a \<nome del tenant\> Azure Active Directory**e quindi fare clic su **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Nella pagina **Gestito da** \<nome tenant\> è possibile visualizzare le **Informazioni di connessione** che includono un **Indirizzo server di gestione** come quello visualizzato nella figura seguente. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Verificare che non sia possibile incollare dati aziendali in un'app non gestita**
  
1. Aprire Outlook 2016 installato da Microsoft 365 Business.
    
2. Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.
    
    Aprire Blocco note e provare a incollare il contenuto.
    
    Si riceverà un messaggio di errore che indica che l'app non può accedere al contenuto.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Lo stesso contenuto può però essere incollato in Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi personali

 **Verificare le impostazioni di connessione**
  
1. Nel dispositivo personale Windows 10 in cui si è connessi come utente locale, passare a **Impostazioni di Windows** e fare clic o toccare **Account** \> **Accedi all'azienda o all'istituto di istruzione**.
    
2. Scegliere **Connetti** in **Accedi all'azienda o all'istituto di istruzione**.
    
3. Immettere le credenziali di Microsoft 365 Business nella finestra di dialogo **Imposta un account aziendale o dell'istituto di istruzione** \> **Accedi**.
    
4. Nella pagina **Accedi all'azienda o all'istituto di istruzione** scegliere **Account aziendale o dell'istituto di istruzione**, quindi scegliere **Informazioni**.
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Nella pagina **Accedi all'azienda o all'istituto di istruzione** è possibile visualizzare le **Informazioni di connessione** che includono un **Indirizzo server di gestione** come quello visualizzato nella figura seguente e le parole  *wip*  e  *mam*  . 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Verificare che non sia possibile incollare dati aziendali in un'app non gestita**
  
1. Aprire Outlook 2016 e aggiungere l'account di Microsoft 365 Business, se necessario, quindi accedere con le credenziali di Microsoft 365 Business.
    
2. Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.
    
    Aprire Blocco note e provare a incollare il contenuto.
    
    Si riceverà un messaggio di errore che indica che l'app non può accedere al contenuto.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Lo stesso contenuto può però essere incollato in Word 2016.
    

