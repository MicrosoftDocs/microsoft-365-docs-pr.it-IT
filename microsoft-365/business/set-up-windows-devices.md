---
title: Configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium
f1.keywords:
- CSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Informazioni su come configurare i dispositivi Windows che eseguono Windows 10 Pro per gli utenti di Microsoft 365 Business Premium, consentendo la gestione centralizzata e i controlli di sicurezza.
ms.openlocfilehash: efe81a5547496f502232e1db2f3f092165475641
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635453"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Prerequisiti per configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium

Prima di poter configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium, assicurarsi che tutti i dispositivi Windows eseguano Windows 10 Pro, versione 1703 (Creators Update). Windows 10 Pro è un prerequisito per la distribuzione di Windows 10 business, che è un insieme di servizi cloud e funzionalità di gestione dei dispositivi che integrano Windows 10 Pro e consentono di gestire i controlli di sicurezza e gestione centralizzati di Microsoft 365 Business Premium.
  
Se si dispone di dispositivi Windows che eseguono Windows 7 Pro, Windows 8 Pro o Windows 8,1 Pro, l'abbonamento Microsoft 365 Business Premium dà diritto a un aggiornamento di Windows 10.
  
Per altre informazioni su come eseguire l'aggiornamento di dispositivi Windows Pro a Windows 10 Pro Creators Update, seguire i passaggi descritti in questo argomento: [Eseguire l'aggiornamento di dispositivi Windows a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
  
Vedere [verificare che il dispositivo sia connesso a Azure](#verify-the-device-is-connected-to-azure-ad) ad per verificare che l'aggiornamento sia stato effettuato o che l'aggiornamento abbia avuto esito positivo.

Guardare un breve video sulla connessione di Windows a Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Unire i dispositivi Windows 10 a Azure AD dell'organizzazione.

Quando tutti i dispositivi Windows nell'organizzazione sono stati aggiornati a Windows 10 Pro Creators Update o sono già in esecuzione l'aggiornamento di Windows 10 Pro Creator, è possibile aggiungere questi dispositivi a Azure Active Directory dell'organizzazione. Una volta che i dispositivi sono Stati Uniti, verranno aggiornati automaticamente a Windows 10 business, che fa parte dell'abbonamento a Microsoft 365 Business Premium.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Per un dispositivo Windows 10 Pro nuovo o appena aggiornato

Per un nuovo dispositivo che esegue Windows 10 Pro Creators Update oppure appena aggiornato a Windows 10 Pro Creators Update ma che non è ancora stato configurato con Windows 10, seguire questa procedura.
  
1. Seguire la procedura di installazione di Windows 10 finché non viene visualizzata la pagina **Che configurazione vuoi eseguire?**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. In questa sezione, scegliere **Configura per un'organizzazione** e quindi immettere il nome utente e la password per Microsoft 365 Business Premium. 
    
3. Completare la configurazione del dispositivo con Windows 10.
    
   Al termine, l'utente verrà connesso a Azure Active Directory dell'organizzazione. Per accertarsene, vedere [Verificare che il dispositivo sia connesso a Azure AD](#verify-the-device-is-connected-to-azure-ad). 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Per un dispositivo già configurato e che esegue Windows 10 Pro

 **Collegare gli utenti a Azure Active Directory:**
  
1. Nel PC Windows dell'utente, che esegue Windows 10 Pro, versione 1703 (Creators Update) (vedere i [prerequisiti](pre-requisites-for-data-protection.md)), fare clic sul logo Windows e quindi sull'icona Impostazioni.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. In **Impostazioni** passare ad **Account**.
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. Nella pagina **Le tue info** fare clic su **Accedi all'azienda o all'istituto di istruzione** \> **Connetti**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. Nella finestra di dialogo **Imposta un account aziendale o dell'istituto di istruzione**, in **Azioni alternative**, scegliere **Aggiungi il dispositivo ad Azure Active Directory**.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. Nella pagina **Esegui l'accesso** immettere l'account aziendale o dell'istituto di iscrizione \> **Avanti**.
  
   Nella pagina **Immettere la password** immettere la password \> **Accedi**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. Nella pagina controlla che **sia la tua organizzazione** , verifica che le informazioni siano corrette e fai clic su **Unisci**.
  
   Nella pagina **È tutto pronto** fare clic su **Fatto**.
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Se sono stati caricati file in OneDrive for Business, sincronizzarli nuovamente. Se è stato utilizzato uno strumento di terze parti per eseguire la migrazione di profili e file, sincronizzarli anche con il nuovo profilo.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Verificare che il dispositivo sia connesso a Azure AD

Per verificare lo stato della sincronizzazione, nella pagina **Accedi all'azienda o all'istituto di istruzione** in **Impostazioni** fare clic nell'area **Connesso a** _ \<organization name\> _ per visualizzare i pulsanti **Informazioni** e **Disconnetti**. Fare clic su **Informazioni** per ottenere lo stato di sincronizzazione. 
  
Nella pagina Stato sincronizzazione fare clic su Sincronizza per ottenere i criteri di gestione più recenti per i dispositivi mobili nel PC.
  
Per iniziare a usare l'account Premium di Microsoft 365 business, passare al pulsante **Start** di Windows, fare clic con il tasto destro del mouse sull'immagine corrente dell'account e quindi **cambiare account**. Accedere usando l'indirizzo di posta elettronica e la password della propria organizzazione.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>Verificare che sia stato eseguito l'aggiornamento a Windows 10 Business nel dispositivo

Verificare che i dispositivi di Azure AD join Windows 10 siano stati aggiornati a Windows 10 business come parte dell'abbonamento a Microsoft 365 Business Premium.
  
1. Selezionare **Impostazioni** \> **Sistema** \> **Informazioni su**.
    
2. Verificare che in **Edizione** sia indicato **Windows 10 Business**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Passaggi successivi

Per configurare i dispositivi mobili, vedere [configurare i dispositivi mobili per gli utenti di Microsoft 365 Business Premium](set-up-mobile-devices.md), per impostare i criteri di protezione dei dispositivi o di protezione delle app, vedere [gestire Microsoft 365 for business](manage.md).
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Per ulteriori informazioni sulla configurazione e l'utilizzo di Microsoft 365 Business Premium

[Video sulla formazione di Microsoft 365 per le aziende](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
