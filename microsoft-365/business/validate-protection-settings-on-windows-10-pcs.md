---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informazioni su come convalidare le impostazioni di protezione delle app di Microsoft 365 in dispositivi Windows 10.
ms.openlocfilehash: 7710accf9a3cd1db788dd5215ab6d7bbb97e48a6
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074381"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="4c24d-103">Verificare le impostazioni di protezione delle app nei PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="4c24d-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="4c24d-104">Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi aziendali</span><span class="sxs-lookup"><span data-stu-id="4c24d-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="4c24d-p101">Dopo aver [configurato i criteri di protezione delle app](protection-settings-for-windows-10-devices.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti. Se è stata **attivata** l'impostazione **Impedisci agli utenti di copiare dati aziendali in file personali e forzali a salvare i file di lavoro in OneDrive for Business** per i dispositivi di proprietà dell'azienda, è possibile eseguire questo controllo nel dispositivo dell'utente dopo che si è connesso ad Azure Active Directory e ha eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4c24d-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="4c24d-107">**Verificare le impostazioni di connessione**</span><span class="sxs-lookup"><span data-stu-id="4c24d-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="4c24d-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="4c24d-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="4c24d-111">Nella pagina **Gestito da** \<nome tenant\> è possibile visualizzare le **Informazioni di connessione** che includono un **Indirizzo server di gestione** come quello visualizzato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="4c24d-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="4c24d-113">**Verificare che non sia possibile incollare dati aziendali in un'app non gestita**</span><span class="sxs-lookup"><span data-stu-id="4c24d-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="4c24d-114">Aprire Outlook 2016 installato da Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="4c24d-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="4c24d-115">Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4c24d-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="4c24d-116">Aprire Blocco note e provare a incollare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4c24d-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="4c24d-117">Si riceverà un messaggio di errore che indica che l'app non può accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="4c24d-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="4c24d-119">Lo stesso contenuto può però essere incollato in Word 2016.</span><span class="sxs-lookup"><span data-stu-id="4c24d-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="4c24d-120">Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi personali</span><span class="sxs-lookup"><span data-stu-id="4c24d-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="4c24d-121">**Verificare le impostazioni di connessione**</span><span class="sxs-lookup"><span data-stu-id="4c24d-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="4c24d-122">Nel dispositivo personale Windows 10 in cui si è connessi come utente locale, passare a **Impostazioni di Windows** e fare clic o toccare **Account** \> **Accedi all'azienda o all'istituto di istruzione**.</span><span class="sxs-lookup"><span data-stu-id="4c24d-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="4c24d-123">Scegliere **Connetti** in **Accedi all'azienda o all'istituto di istruzione**.</span><span class="sxs-lookup"><span data-stu-id="4c24d-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="4c24d-124">Immettere le credenziali di Microsoft 365 Business nella finestra di dialogo **Imposta un account aziendale o dell'istituto di istruzione** \> **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="4c24d-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="4c24d-125">Nella pagina **Accedi all'azienda o all'istituto di istruzione** scegliere **Account aziendale o dell'istituto di istruzione**, quindi scegliere **Informazioni**.</span><span class="sxs-lookup"><span data-stu-id="4c24d-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="4c24d-127">Nella pagina **Accedi all'azienda o all'istituto di istruzione** è possibile visualizzare le **Informazioni di connessione** che includono un **Indirizzo server di gestione** come quello visualizzato nella figura seguente e le parole  *wip*  e  *mam*  .</span><span class="sxs-lookup"><span data-stu-id="4c24d-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="4c24d-129">**Verificare che non sia possibile incollare dati aziendali in un'app non gestita**</span><span class="sxs-lookup"><span data-stu-id="4c24d-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="4c24d-130">Aprire Outlook 2016 e aggiungere l'account di Microsoft 365 Business, se necessario, quindi accedere con le credenziali di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="4c24d-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="4c24d-131">Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4c24d-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="4c24d-132">Aprire Blocco note e provare a incollare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4c24d-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="4c24d-133">Si riceverà un messaggio di errore che indica che l'app non può accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="4c24d-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="4c24d-135">Lo stesso contenuto può però essere incollato in Word 2016.</span><span class="sxs-lookup"><span data-stu-id="4c24d-135">You can, however, paste the same content into Word 2016.</span></span>
    

