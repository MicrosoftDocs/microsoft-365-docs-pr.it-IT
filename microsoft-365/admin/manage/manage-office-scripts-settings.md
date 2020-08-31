---
title: Gestire le impostazioni degli script di Office
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
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300835"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="9de20-103">Gestire le impostazioni degli script di Office</span><span class="sxs-lookup"><span data-stu-id="9de20-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="9de20-104">Gli script di Office consentono agli utenti di automatizzare le attività tramite la registrazione, la modifica e l'esecuzione di script in Excel sul Web.</span><span class="sxs-lookup"><span data-stu-id="9de20-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="9de20-105">Office Scripts è compatibile con Power automatizzate e gli utenti eseguono script nelle cartelle di lavoro utilizzando il connettore Excel online (business).</span><span class="sxs-lookup"><span data-stu-id="9de20-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="9de20-106">Microsoft 365 admins è in grado di gestire le impostazioni degli script di Office dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9de20-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9de20-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9de20-107">Before you begin</span></span>

- <span data-ttu-id="9de20-108">Per gestire le impostazioni degli script di Office, è necessario essere un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9de20-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="9de20-109">Verificare che gli utenti dell'organizzazione dispongano di una licenza valida per un piano commerciale o EDU di Microsoft 365 o Office 365 che includa l'accesso alle app desktop di Office, ad esempio uno dei seguenti piani:</span><span class="sxs-lookup"><span data-stu-id="9de20-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="9de20-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="9de20-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="9de20-111">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="9de20-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="9de20-112">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="9de20-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="9de20-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="9de20-113">Office 365 E3</span></span>
    - <span data-ttu-id="9de20-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="9de20-114">Office 365 E5</span></span>
    - <span data-ttu-id="9de20-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="9de20-115">Office 365 A3</span></span>
    - <span data-ttu-id="9de20-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="9de20-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="9de20-117">Gestire la disponibilità degli script di Office e la condivisione degli script</span><span class="sxs-lookup"><span data-stu-id="9de20-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="9de20-118">Nell'interfaccia di amministrazione di Microsoft 365 passare alla scheda **Impostazioni** \> **org** Settings \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .</span><span class="sxs-lookup"><span data-stu-id="9de20-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="9de20-119">Selezionare **script di Office**.</span><span class="sxs-lookup"><span data-stu-id="9de20-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="9de20-120">Gli script di Office sono attivati per impostazione predefinita e tutti gli utenti dell'organizzazione possono accedere e usare la funzionalità e condividere gli script.</span><span class="sxs-lookup"><span data-stu-id="9de20-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="9de20-121">Per disattivare gli script di Office per l'organizzazione, deselezionare la casella di controllo **Consenti agli utenti di automatizzare le attività in Excel sul Web** .</span><span class="sxs-lookup"><span data-stu-id="9de20-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="9de20-122">Se in precedenza sono stati disattivati gli script di Office per l'organizzazione e si desidera riattivarla, selezionare **Consenti agli utenti di automatizzare le attività in Excel sul Web**e quindi specificare chi può accedere e usare la caratteristica:</span><span class="sxs-lookup"><span data-stu-id="9de20-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="9de20-123">Per consentire a tutti gli utenti dell'organizzazione di accedere e utilizzare gli script di Office, lasciare **tutti** (impostazione predefinita) selezionati.</span><span class="sxs-lookup"><span data-stu-id="9de20-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="9de20-124">Per consentire l'accesso e l'utilizzo di script di Office solo ai membri di un gruppo specifico, selezionare **gruppo specifico**e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti.</span><span class="sxs-lookup"><span data-stu-id="9de20-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="9de20-125">È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9de20-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="9de20-126">Gruppo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de20-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="9de20-127">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="9de20-127">Distribution group</span></span>
        - <span data-ttu-id="9de20-128">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9de20-128">Security group</span></span>
        - <span data-ttu-id="9de20-129">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9de20-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="9de20-130">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [confronto di gruppi](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9de20-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="9de20-131">Per consentire agli utenti con accesso agli script di Office di condividere i propri script con altri membri dell'organizzazione, selezionare **Consenti agli utenti di accedere agli script di Office di condividere i propri script con altri membri dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="9de20-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="9de20-132">La condivisione di script all'esterno di un'organizzazione non è consentita.</span><span class="sxs-lookup"><span data-stu-id="9de20-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="9de20-133">Se in seguito si disattiva la condivisione degli script per l'organizzazione, gli utenti potranno comunque eseguire script condivisi in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9de20-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="9de20-134">Specificare gli utenti con accesso agli script di Office che possono condividere gli script seguenti:</span><span class="sxs-lookup"><span data-stu-id="9de20-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="9de20-135">Per consentire a tutti gli utenti con accesso agli script di Office di condividere gli script, lasciare **tutti** (impostazione predefinita) selezionati.</span><span class="sxs-lookup"><span data-stu-id="9de20-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="9de20-136">Per consentire solo ai membri di un gruppo specifico di accedere agli script di Office di condividere gli script, selezionare **gruppo specifico**e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti.</span><span class="sxs-lookup"><span data-stu-id="9de20-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="9de20-137">È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9de20-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="9de20-138">Gruppo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de20-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="9de20-139">Gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="9de20-139">Distribution group</span></span>
        - <span data-ttu-id="9de20-140">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9de20-140">Security group</span></span>
        - <span data-ttu-id="9de20-141">Gruppo di sicurezza abilitato alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9de20-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="9de20-142">Per ulteriori informazioni sui diversi tipi di gruppi, vedere [confronto di gruppi](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9de20-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="9de20-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9de20-143">Select **Save**.</span></span>

    <span data-ttu-id="9de20-144">Per rendere effettive le modifiche apportate alle impostazioni di Office script, possono essere necessarie fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="9de20-144">It can take up to 48 hours for changes to Office Script settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9de20-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9de20-145">Next steps</span></span>

<span data-ttu-id="9de20-146">Poiché Office scripts funziona con Power automatizzate, è consigliabile esaminare i criteri di prevenzione della perdita di dati (DLP, Data Loss Prevention) esistenti per garantire la protezione dei dati dell'organizzazione mentre gli utenti utilizzano gli script di Office.</span><span class="sxs-lookup"><span data-stu-id="9de20-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="9de20-147">Per ulteriori informazioni, vedere [criteri di prevenzione della perdita di dati (DLP)](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="9de20-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="9de20-148">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="9de20-148">Related content</span></span>

<span data-ttu-id="9de20-149">[Documentazione tecnica di Office scripts](/office/dev/scripts/) (pagina collegamento) </span><span class="sxs-lookup"><span data-stu-id="9de20-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="9de20-150">[Introduzione agli script di Office in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (articolo) </span><span class="sxs-lookup"><span data-stu-id="9de20-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="9de20-151">[Condivisione degli script di Office in Excel per il Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (articolo) </span><span class="sxs-lookup"><span data-stu-id="9de20-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="9de20-152">[Registrare, modificare e creare script di Office in Excel sul Web](/office/dev/scripts/tutorials/excel-tutorial) (articolo)</span><span class="sxs-lookup"><span data-stu-id="9de20-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>