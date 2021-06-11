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
description: Informazioni su come gestire le Office script per gli utenti dell'organizzazione.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572310"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="ce2a6-103">Gestire le impostazioni di Office Scripts</span><span class="sxs-lookup"><span data-stu-id="ce2a6-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="ce2a6-104">[Office consente](/office/dev/scripts)agli utenti di automatizzare le attività registrando, modificando ed eseguendo script in Excel sul Web.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="ce2a6-105">Office Gli script funzionano con Power Automate e gli utenti eseguono script nelle cartelle di lavoro utilizzando il connettore Excel Online (Business).</span><span class="sxs-lookup"><span data-stu-id="ce2a6-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="ce2a6-106">Microsoft 365 amministratori possono gestire le impostazioni Office script dall'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce2a6-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ce2a6-107">Before you begin</span></span>

- <span data-ttu-id="ce2a6-108">Per gestire Office impostazioni degli script, devi essere un amministratore globale. Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="ce2a6-109">Verificare che gli utenti dell'organizzazione dispongono di una licenza valida per un piano commerciale o EDU di Microsoft 365 o Office 365 che includa l'accesso alle app desktop di Office, ad esempio uno dei piani seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce2a6-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="ce2a6-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="ce2a6-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="ce2a6-111">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="ce2a6-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="ce2a6-112">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="ce2a6-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="ce2a6-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="ce2a6-113">Office 365 E3</span></span>
    - <span data-ttu-id="ce2a6-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="ce2a6-114">Office 365 E5</span></span>
    - <span data-ttu-id="ce2a6-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="ce2a6-115">Office 365 A3</span></span>
    - <span data-ttu-id="ce2a6-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="ce2a6-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="ce2a6-117">Gestire la disponibilità Office script e la condivisione degli script</span><span class="sxs-lookup"><span data-stu-id="ce2a6-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="ce2a6-118">Nell'Microsoft 365 di amministrazione passare alla scheda **Impostazioni** \> **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">organizzazione.</a></span><span class="sxs-lookup"><span data-stu-id="ce2a6-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="ce2a6-119">Selezionare **Office script**.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="ce2a6-120">Office Gli script sono attivati per impostazione predefinita e tutti gli utenti dell'organizzazione possono accedere e usare la funzionalità e condividere gli script.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="ce2a6-121">Per disattivare Office script per l'organizzazione, deselezionare la casella di controllo Consenti agli utenti di automatizzare le attività **in Excel sul web.**</span><span class="sxs-lookup"><span data-stu-id="ce2a6-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="ce2a6-122">Se in precedenza è stato disattivato Office Scripts per l'organizzazione e si desidera riattivarlo, selezionare Consenti agli utenti di **automatizzare** le attività in Excel sul web e quindi specificare chi può accedere e usare la funzionalità:</span><span class="sxs-lookup"><span data-stu-id="ce2a6-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="ce2a6-123">Per consentire a tutti gli utenti dell'organizzazione di accedere Office script, lasciare selezionato **Tutti** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ce2a6-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="ce2a6-124">Per consentire solo ai membri di un gruppo specifico di accedere e utilizzare gli script di Office, selezionare Gruppo specifico **e** quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco consenti.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="ce2a6-125">È possibile aggiungere un solo gruppo all'elenco consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce2a6-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="ce2a6-126">Microsoft 365 gruppo</span><span class="sxs-lookup"><span data-stu-id="ce2a6-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="ce2a6-127">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="ce2a6-127">Distribution group</span></span>
        - <span data-ttu-id="ce2a6-128">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ce2a6-128">Security group</span></span>
        - <span data-ttu-id="ce2a6-129">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ce2a6-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="ce2a6-130">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confronto di gruppi.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="ce2a6-131">Per consentire agli utenti con accesso Office Scripts di condividere i propri script con altri utenti dell'organizzazione, selezionare Consenti agli utenti con accesso Office Scripts di condividere i propri script con altri utenti **dell'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="ce2a6-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="ce2a6-132">La condivisione di script all'esterno di un'organizzazione non è consentita.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="ce2a6-133">Se in seguito si disattiva la condivisione degli script per l'organizzazione, gli utenti potranno comunque eseguire script condivisi in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="ce2a6-134">Specificare quali utenti con accesso a Office script possono condividere i propri script:</span><span class="sxs-lookup"><span data-stu-id="ce2a6-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="ce2a6-135">Per consentire a tutti gli utenti con accesso Office script di condividere i propri script, lasciare **selezionato Tutti** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ce2a6-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="ce2a6-136">Per consentire solo ai membri di un gruppo specifico con accesso Office Scripts di condividere i propri script, selezionare **Gruppo** specifico e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco consenti.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="ce2a6-137">È possibile aggiungere un solo gruppo all'elenco consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce2a6-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="ce2a6-138">Microsoft 365 gruppo</span><span class="sxs-lookup"><span data-stu-id="ce2a6-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="ce2a6-139">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="ce2a6-139">Distribution group</span></span>
        - <span data-ttu-id="ce2a6-140">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ce2a6-140">Security group</span></span>
        - <span data-ttu-id="ce2a6-141">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ce2a6-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="ce2a6-142">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confronto di gruppi.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="ce2a6-143">Per consentire agli utenti di eseguire i propri script Office all'interno dei flussi di Power Automate, selezionare Consenti agli utenti con accesso Office Script di eseguire i propri script **con Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="ce2a6-144">In questo modo gli utenti possono aggiungere passaggi [del flusso con l'opzione di script Esegui Excel Online (Business) Connector.](/connectors/excelonlinebusiness) </span><span class="sxs-lookup"><span data-stu-id="ce2a6-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="ce2a6-145">Per consentire a tutti gli utenti con accesso Office Script di utilizzare i propri script nei flussi, lasciare selezionato **Tutti** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ce2a6-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="ce2a6-146">Per consentire solo ai membri di un gruppo specifico con accesso Office Scripts di utilizzare i propri script nei flussi, selezionare **Gruppo** specifico e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco consenti.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="ce2a6-147">È possibile aggiungere un solo gruppo all'elenco consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce2a6-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="ce2a6-148">Microsoft 365 gruppo</span><span class="sxs-lookup"><span data-stu-id="ce2a6-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="ce2a6-149">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="ce2a6-149">Distribution group</span></span>
        - <span data-ttu-id="ce2a6-150">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ce2a6-150">Security group</span></span>
        - <span data-ttu-id="ce2a6-151">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ce2a6-151">Mail-enabled security group</span></span>

        <span data-ttu-id="ce2a6-152">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confronto di gruppi.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="ce2a6-153">Per ulteriori informazioni sull'utilizzo Office script con Power Automate, vedere [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="ce2a6-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="ce2a6-154">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-154">Select **Save**.</span></span>

    <span data-ttu-id="ce2a6-155">L'applicazione delle modifiche alle impostazioni Office script può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce2a6-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ce2a6-156">Next steps</span></span>

<span data-ttu-id="ce2a6-157">Poiché Office Scripts funziona con Power Automate, è consigliabile esaminare i criteri di prevenzione della perdita dei dati (DLP) esistenti per garantire che i dati dell'organizzazione rimangano protetti mentre gli utenti usano Office Script.</span><span class="sxs-lookup"><span data-stu-id="ce2a6-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="ce2a6-158">Per ulteriori informazioni, vedere Criteri di [prevenzione della perdita dei dati (DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="ce2a6-159">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="ce2a6-159">Related content</span></span>

<span data-ttu-id="ce2a6-160">[Office documentazione tecnica script (pagina](/office/dev/scripts/) di collegamento)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="ce2a6-161">[Introduzione agli Office script in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (articolo)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="ce2a6-162">[Condivisione Office script in Excel per il Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (articolo)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="ce2a6-163">[Registrare, modificare e creare Office script in Excel sul web](/office/dev/scripts/tutorials/excel-tutorial) (articolo)</span><span class="sxs-lookup"><span data-stu-id="ce2a6-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
