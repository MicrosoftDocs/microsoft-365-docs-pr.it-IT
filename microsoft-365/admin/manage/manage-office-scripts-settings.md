---
title: Gestire le impostazioni di Office Scripts
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Informazioni su come gestire le impostazioni degli script di Office per gli utenti dell'organizzazione.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058424"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="11516-103">Gestire le impostazioni di Office Scripts</span><span class="sxs-lookup"><span data-stu-id="11516-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="11516-104">Gli script di Office consentono agli utenti di automatizzare le attività registrando, modificando ed eseguendo script in Excel sul Web.</span><span class="sxs-lookup"><span data-stu-id="11516-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="11516-105">Gli script di Office funzionano con Power Automate e gli utenti eseguono script nelle cartelle di lavoro utilizzando il connettore Di Excel Online (Business).</span><span class="sxs-lookup"><span data-stu-id="11516-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="11516-106">Gli amministratori di Microsoft 365 possono gestire le impostazioni degli script di Office dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="11516-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="11516-107">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="11516-107">Before you begin</span></span>

- <span data-ttu-id="11516-108">Per gestire le impostazioni degli script di Office, è necessario essere un amministratore globale. Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="11516-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="11516-109">Assicurarsi che gli utenti dell'organizzazione hanno una licenza valida per un piano commerciale o EDU di Microsoft 365 o Office 365 che include l'accesso alle app desktop di Office, ad esempio uno dei piani seguenti:</span><span class="sxs-lookup"><span data-stu-id="11516-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="11516-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="11516-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="11516-111">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="11516-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="11516-112">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="11516-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="11516-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="11516-113">Office 365 E3</span></span>
    - <span data-ttu-id="11516-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="11516-114">Office 365 E5</span></span>
    - <span data-ttu-id="11516-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="11516-115">Office 365 A3</span></span>
    - <span data-ttu-id="11516-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="11516-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="11516-117">Gestire la disponibilità degli script di Office e la condivisione degli script</span><span class="sxs-lookup"><span data-stu-id="11516-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="11516-118">Nell'interfaccia di amministrazione di Microsoft 365 passare alla scheda **Impostazioni** \> **organizzazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Servizi.</a></span><span class="sxs-lookup"><span data-stu-id="11516-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="11516-119">Selezionare **Script di Office.**</span><span class="sxs-lookup"><span data-stu-id="11516-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="11516-120">Gli script di Office sono attivati per impostazione predefinita e tutti gli utenti dell'organizzazione possono accedere e utilizzare la funzionalità e condividere gli script.</span><span class="sxs-lookup"><span data-stu-id="11516-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="11516-121">Per disattivare gli script di Office per l'organizzazione, deselezionare la casella di controllo Consenti agli utenti di automatizzare le attività **in Excel sul Web.**</span><span class="sxs-lookup"><span data-stu-id="11516-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="11516-122">Se in precedenza sono stati disattivati gli script di Office per l'organizzazione e si desidera riattivarlo, selezionare Consenti agli utenti di **automatizzare** le attività in Excel sul Web e quindi specificare chi può accedere e utilizzare la funzionalità:</span><span class="sxs-lookup"><span data-stu-id="11516-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="11516-123">Per consentire a tutti gli utenti dell'organizzazione di accedere e utilizzare gli script di Office, lasciare selezionato **Tutti** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="11516-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="11516-124">Per consentire solo ai membri di un gruppo specifico di accedere e utilizzare gli script di Office, selezionare Gruppo specifico **e** quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti.</span><span class="sxs-lookup"><span data-stu-id="11516-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="11516-125">È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="11516-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="11516-126">Gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11516-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="11516-127">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="11516-127">Distribution group</span></span>
        - <span data-ttu-id="11516-128">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="11516-128">Security group</span></span>
        - <span data-ttu-id="11516-129">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="11516-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="11516-130">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confrontare i gruppi.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="11516-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="11516-131">Per consentire agli utenti con accesso agli script di Office di condividere i propri script con altri utenti dell'organizzazione, selezionare Consenti agli utenti con accesso agli script di Office di condividere i propri script con altri utenti **dell'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="11516-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="11516-132">La condivisione di script all'esterno di un'organizzazione non è consentita.</span><span class="sxs-lookup"><span data-stu-id="11516-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="11516-133">Se successivamente si disattiva la condivisione degli script per l'organizzazione, gli utenti potranno comunque eseguire script condivisi in precedenza.</span><span class="sxs-lookup"><span data-stu-id="11516-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="11516-134">Specificare quali utenti con accesso agli script di Office possono condividere i propri script:</span><span class="sxs-lookup"><span data-stu-id="11516-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="11516-135">Per consentire a tutti gli utenti con accesso agli script di Office di condividere i propri script, lasciare selezionato **Tutti** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="11516-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="11516-136">Per consentire solo ai membri di un gruppo specifico con accesso agli script di Office di condividere i propri script, selezionare Gruppo specifico **e** quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti.</span><span class="sxs-lookup"><span data-stu-id="11516-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="11516-137">È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="11516-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="11516-138">Gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11516-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="11516-139">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="11516-139">Distribution group</span></span>
        - <span data-ttu-id="11516-140">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="11516-140">Security group</span></span>
        - <span data-ttu-id="11516-141">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="11516-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="11516-142">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confrontare i gruppi.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="11516-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="11516-143">Per consentire agli utenti di eseguire i propri script di Office all'interno dei flussi di Power Automate, selezionare Consenti agli utenti con accesso agli script di Office di eseguire i **propri script con Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="11516-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="11516-144">Ciò consente agli utenti di aggiungere passaggi del flusso con l'opzione di script Esegui del connettore [di Excel Online (Business).](/connectors/excelonlinebusiness) </span><span class="sxs-lookup"><span data-stu-id="11516-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="11516-145">Per consentire a tutti gli utenti con accesso agli script di Office di utilizzare i propri script nei flussi, lasciare selezionato **Tutti** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="11516-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="11516-146">Per consentire solo ai membri di un gruppo specifico con accesso agli script di Office di utilizzare i propri script nei flussi, selezionare **Gruppo** specifico e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti.</span><span class="sxs-lookup"><span data-stu-id="11516-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="11516-147">È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="11516-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="11516-148">Gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11516-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="11516-149">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="11516-149">Distribution group</span></span>
        - <span data-ttu-id="11516-150">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="11516-150">Security group</span></span>
        - <span data-ttu-id="11516-151">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="11516-151">Mail-enabled security group</span></span>

        <span data-ttu-id="11516-152">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confrontare i gruppi.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="11516-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="11516-153">Per ulteriori informazioni sull'utilizzo degli script di Office con Power Automate, incluso l'impatto dei criteri di prevenzione della perdita dei dati, vedere Eseguire script di [Office con Power Automate.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="11516-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="11516-154">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11516-154">Select **Save**.</span></span>

    <span data-ttu-id="11516-155">L'applicazione delle modifiche alle impostazioni degli script di Office può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="11516-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11516-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="11516-156">Next steps</span></span>

<span data-ttu-id="11516-157">Poiché gli script di Office funzionano con Power Automate, è consigliabile esaminare i criteri di prevenzione della perdita dei dati esistenti per garantire che i dati dell'organizzazione rimangano protetti mentre gli utenti utilizzano gli script di Office.</span><span class="sxs-lookup"><span data-stu-id="11516-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="11516-158">Per ulteriori informazioni, vedere Criteri di prevenzione della perdita [dei dati (DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="11516-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="11516-159">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="11516-159">Related content</span></span>

<span data-ttu-id="11516-160">[Documentazione tecnica degli script di Office](/office/dev/scripts/) (pagina di collegamento)</span><span class="sxs-lookup"><span data-stu-id="11516-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="11516-161">[Introduzione agli script di Office in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (articolo)</span><span class="sxs-lookup"><span data-stu-id="11516-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="11516-162">[Condivisione di script di Office in Excel per il Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (articolo)</span><span class="sxs-lookup"><span data-stu-id="11516-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="11516-163">[Registrare, modificare e creare script di Office in Excel sul Web](/office/dev/scripts/tutorials/excel-tutorial) (articolo)</span><span class="sxs-lookup"><span data-stu-id="11516-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
