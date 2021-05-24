---
title: Configurare dispositivi Windows per Microsoft 365 Business Premium utenti
f1.keywords:
- CSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Configurare i Windows che eseguono Windows 10 Pro per Microsoft 365 Business Premium utenti, consentendo la gestione centralizzata e i controlli di sicurezza.
ms.openlocfilehash: 7a9c75f6ec14605225d40c103c18e62937e773bf
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635875"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Configurare dispositivi Windows per Microsoft 365 Business Premium utenti

## <a name="before-you-begin"></a>Prima di iniziare

Prima di poter configurare Windows per gli utenti di Microsoft 365 Business Premium, assicurati che tutti i dispositivi Windows esercitino Windows 10 Pro versione 1703 (Creators Update). Windows 10 Pro è un prerequisito per la distribuzione di Windows 10 Business, ovvero un set di servizi cloud e funzionalità di gestione dei dispositivi che integrano Windows 10 Pro e consentono la gestione centralizzata e i controlli di sicurezza di Microsoft 365 Business Premium.
  
Se si dispone di Windows che eseguono Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, l'abbonamento Microsoft 365 Business Premium consente di eseguire un Windows 10 aggiornamento.
  
Per altre informazioni su come eseguire l'aggiornamento di dispositivi Windows Pro a Windows 10 Pro Creators Update, seguire i passaggi descritti in questo argomento: [Eseguire l'aggiornamento di dispositivi Windows a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
  
Vedi [Verificare che il dispositivo sia connesso ad Azure AD](#verify-the-device-is-connected-to-azure-ad) per verificare di avere l'aggiornamento o per verificare che l'aggiornamento sia stato eseguito correttamente.

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a>Guarda: Connessione il PC per Microsoft 365 Business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../business-video/index.yml).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Unire i dispositivi Windows 10 a Azure AD dell'organizzazione.

Quando tutti i dispositivi Windows dell'organizzazione sono stati aggiornati a Windows 10 Pro Creators Update o sono già in esecuzione Windows 10 Pro Creators Update, è possibile aggiungere questi dispositivi al Azure Active Directory dell'organizzazione. Una volta aggiunti, i dispositivi verranno aggiornati automaticamente a Windows 10 Business, che fa parte dell'Microsoft 365 Business Premium abbonamento.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Per un dispositivo Windows 10 Pro nuovo o appena aggiornato

Per un nuovo dispositivo che esegue Windows 10 Pro Creators Update oppure appena aggiornato a Windows 10 Pro Creators Update ma che non è ancora stato configurato con Windows 10, seguire questa procedura.
  
1. Seguire la procedura di installazione di Windows 10 finché non viene visualizzata la pagina **Che configurazione vuoi eseguire?**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Qui scegli **Configura per un'organizzazione e** quindi immetti il nome utente e la password per Microsoft 365 Business Premium. 
    
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
  
6. Nella pagina **Verificare che l'organizzazione** sia corretta, verificare che le informazioni siano corrette e scegliere **Partecipa.**
  
   Nella pagina **You're all set!** , chosse **Done**.
  
   ![Nella schermata Verificare che questa sia la schermata dell'organizzazione, scegliere Partecipa](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Se sono stati caricati file in OneDrive for Business, sincronizzarli nuovamente. Se hai usato uno strumento di terze parti per eseguire la migrazione di profili e file, sincronizza anche quelli con il nuovo profilo.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Verificare che il dispositivo sia connesso a Azure AD

Per verificare lo stato  della sincronizzazione, nella pagina Accedi all'istituto di istruzione o all'istituto di istruzione di **Impostazioni** selezionare l'area Connesso a _ per esporre i pulsanti  \<organization name\> **Info** e **Disconnetti**. Scegliere **Info per** ottenere lo stato di sincronizzazione. 
  
Nella pagina **Stato sincronizzazione** scegliere **Sincronizza** per ottenere i criteri di gestione dei dispositivi mobili più recenti nel PC.
  
Per iniziare a usare l'account Microsoft 365 Business Premium, passare al pulsante **Start** Windows, fare clic con il pulsante destro del mouse sull'immagine dell'account corrente e quindi **scegliere Cambia account.** Accedere usando l'indirizzo di posta elettronica e la password della propria organizzazione.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Verificare che il PC sia aggiornato a Windows 10 Business

Verificare che i dispositivi Windows 10 aggiunti ad Azure AD siano aggiornati a Windows 10 Business come parte dell'Microsoft 365 Business Premium abbonamento.
  
1. Selezionare **Impostazioni** \> **Sistema** \> **Informazioni su**.
    
2. Verificare che in **Edizione** sia indicato **Windows 10 Business**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Passaggi successivi

Per configurare i dispositivi mobili, vedi Configurare i dispositivi mobili per gli utenti di [Microsoft 365 Business Premium](set-up-mobile-devices.md), Per impostare i criteri di protezione dei dispositivi o delle app, vedere Manage Microsoft 365 [for business](manage.md).
  
## <a name="related-content"></a>Contenuto correlato

[video Microsoft 365 formazione su Microsoft 365](../business-video/index.yml) per le aziende (pagina dei collegamenti)
