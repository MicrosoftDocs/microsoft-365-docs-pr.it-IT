---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Convalidare le impostazioni di protezione delle app di Microsoft 365 Business Premium nei dispositivi Windows 10 e verificare che gli utenti non siano in grado di copiare i dati aziendali in file personali o app non gestite.
ms.openlocfilehash: e319ffa5149f055b5de45078facc8899acffc223
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579863"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Verificare le impostazioni di protezione delle app nei PC Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi aziendali

Dopo aver [configurato i criteri di protezione delle app](protection-settings-for-windows-10-devices.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti. Se è  stata attivata l'impostazione Impedisci agli utenti di copiare i dati aziendali nei file personali e di forzarli a salvare i file di lavoro in **OneDrive for Business** per i dispositivi di proprietà dell'azienda, è possibile controllare questa opzione nel dispositivo dell'utente dopo essersi connessi ad Azure AD e aver eseguito l'accesso. 
  
 **Verificare le impostazioni di connessione**
  
1. Dopo l'accesso con le credenziali di Microsoft 365 Business Premium e la connessione ad Azure AD come descritto in Configurare i dispositivi Windows per gli utenti di [Microsoft 365 Business Premium,](set-up-windows-devices.md)passare a Impostazioni di **Windows** Account Accesso all'azienda o all'istituto di \>  \> **istruzione.** Scegliere **Connesso ad Azure \<tenant name\> AD** e quindi **Info.**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Nella pagina **Gestito da** puoi visualizzare le informazioni di connessione che includono un indirizzo del server di gestione come quello mostrato \<tenant name\> nella figura seguente.   
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Verificare che non sia possibile incollare i dati aziendali in un'app non gestita**
  
1. Aprire Outlook 2016 installato da Microsoft 365 Business Premium.
    
2. Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.
    
    Aprire Blocco note e provare a incollare il contenuto.
    
    Riceverai un errore che indica che l'app non può accedere al contenuto.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Lo stesso contenuto può però essere incollato in Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi personali

 **Verificare le impostazioni di connessione**
  
1. Nel dispositivo personale di Windows 10 in cui hai effettuato l'accesso come utente locale, vai a Impostazioni di **Windows** e tocca o fai clic **su** Account Accedi all'ambiente di lavoro o \> **all'istituto di istruzione.**
    
2. Scegliere **Connetti** in **Accedi all'azienda o all'istituto di istruzione**.
    
3. Immetti le credenziali di Microsoft 365 Business Premium nella finestra di dialogo Configura un account aziendale o **dell'istituto di istruzione** \> **Accedi.**
    
4. Nella pagina **Accedi all'azienda o all'istituto di istruzione** scegliere **Account aziendale o dell'istituto di istruzione**, quindi scegliere **Informazioni**.
    
    ![Toccare o fare clic su Informazioni nella finestra di dialogo Account aziendale o dell'istituto di istruzione.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Nella pagina **Accedi** all'istituto di  istruzione o all'istituto di istruzione puoi visualizzare le informazioni di connessione che includono un indirizzo del **server** di gestione come quello mostrato nella figura seguente e che include le parole *wip* e *mam* all'interno. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Verificare che non sia possibile incollare i dati aziendali in un'app non gestita**
  
1. Aprire Outlook 2016 e aggiungere l'account Microsoft 365 Business Premium, se necessario, e accedere con le credenziali di Microsoft 365 Business Premium.
    
2. Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.
    
    Aprire Blocco note e provare a incollare il contenuto.
    
    Riceverai un errore che indica che l'app non può accedere al contenuto.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Lo stesso contenuto può però essere incollato in Word 2016.
    

