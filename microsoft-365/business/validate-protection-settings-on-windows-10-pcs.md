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
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="45c26-103">Verificare le impostazioni di protezione delle app nei PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="45c26-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="45c26-104">Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi aziendali</span><span class="sxs-lookup"><span data-stu-id="45c26-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="45c26-105">Dopo aver [configurato i criteri di protezione delle app](protection-settings-for-windows-10-devices.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="45c26-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="45c26-106">Se è  stata attivata l'impostazione Impedisci agli utenti di copiare i dati aziendali nei file personali e di forzarli a salvare i file di lavoro in **OneDrive for Business** per i dispositivi di proprietà dell'azienda, è possibile controllare questa opzione nel dispositivo dell'utente dopo essersi connessi ad Azure AD e aver eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="45c26-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="45c26-107">**Verificare le impostazioni di connessione**</span><span class="sxs-lookup"><span data-stu-id="45c26-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="45c26-108">Dopo l'accesso con le credenziali di Microsoft 365 Business Premium e la connessione ad Azure AD come descritto in Configurare i dispositivi Windows per gli utenti di [Microsoft 365 Business Premium,](set-up-windows-devices.md)passare a Impostazioni di **Windows** Account Accesso all'azienda o all'istituto di \>  \> **istruzione.**</span><span class="sxs-lookup"><span data-stu-id="45c26-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="45c26-109">Scegliere **Connesso ad Azure \<tenant name\> AD** e quindi **Info.**</span><span class="sxs-lookup"><span data-stu-id="45c26-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="45c26-111">Nella pagina **Gestito da** puoi visualizzare le informazioni di connessione che includono un indirizzo del server di gestione come quello mostrato \<tenant name\> nella figura seguente.  </span><span class="sxs-lookup"><span data-stu-id="45c26-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="45c26-113">**Verificare che non sia possibile incollare i dati aziendali in un'app non gestita**</span><span class="sxs-lookup"><span data-stu-id="45c26-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="45c26-114">Aprire Outlook 2016 installato da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="45c26-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="45c26-115">Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="45c26-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="45c26-116">Aprire Blocco note e provare a incollare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="45c26-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="45c26-117">Riceverai un errore che indica che l'app non può accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="45c26-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="45c26-119">Lo stesso contenuto può però essere incollato in Word 2016.</span><span class="sxs-lookup"><span data-stu-id="45c26-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="45c26-120">Verificare che gli utenti non possano copiare i dati aziendali in file personali sui dispositivi personali</span><span class="sxs-lookup"><span data-stu-id="45c26-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="45c26-121">**Verificare le impostazioni di connessione**</span><span class="sxs-lookup"><span data-stu-id="45c26-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="45c26-122">Nel dispositivo personale di Windows 10 in cui hai effettuato l'accesso come utente locale, vai a Impostazioni di **Windows** e tocca o fai clic **su** Account Accedi all'ambiente di lavoro o \> **all'istituto di istruzione.**</span><span class="sxs-lookup"><span data-stu-id="45c26-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="45c26-123">Scegliere **Connetti** in **Accedi all'azienda o all'istituto di istruzione**.</span><span class="sxs-lookup"><span data-stu-id="45c26-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="45c26-124">Immetti le credenziali di Microsoft 365 Business Premium nella finestra di dialogo Configura un account aziendale o **dell'istituto di istruzione** \> **Accedi.**</span><span class="sxs-lookup"><span data-stu-id="45c26-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="45c26-125">Nella pagina **Accedi all'azienda o all'istituto di istruzione** scegliere **Account aziendale o dell'istituto di istruzione**, quindi scegliere **Informazioni**.</span><span class="sxs-lookup"><span data-stu-id="45c26-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Toccare o fare clic su Informazioni nella finestra di dialogo Account aziendale o dell'istituto di istruzione.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="45c26-127">Nella pagina **Accedi** all'istituto di  istruzione o all'istituto di istruzione puoi visualizzare le informazioni di connessione che includono un indirizzo del **server** di gestione come quello mostrato nella figura seguente e che include le parole *wip* e *mam* all'interno.</span><span class="sxs-lookup"><span data-stu-id="45c26-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="45c26-129">**Verificare che non sia possibile incollare i dati aziendali in un'app non gestita**</span><span class="sxs-lookup"><span data-stu-id="45c26-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="45c26-130">Aprire Outlook 2016 e aggiungere l'account Microsoft 365 Business Premium, se necessario, e accedere con le credenziali di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="45c26-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="45c26-131">Aprire un messaggio di posta elettronica e copiare parte del contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="45c26-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="45c26-132">Aprire Blocco note e provare a incollare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="45c26-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="45c26-133">Riceverai un errore che indica che l'app non può accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="45c26-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="45c26-135">Lo stesso contenuto può però essere incollato in Word 2016.</span><span class="sxs-lookup"><span data-stu-id="45c26-135">You can, however, paste the same content into Word 2016.</span></span>
    

