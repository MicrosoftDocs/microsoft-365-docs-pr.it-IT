---
title: Usare le etichette di riservatezza con Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint (anteprima pubblica)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Usare le etichette di riservatezza per proteggere il contenuto in siti di SharePoint e Microsoft Teams e in gruppi di Microsoft 365.
ms.openlocfilehash: 4bf640598b072064dcdec657b80182a58d430235
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327274"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="884ba-103">Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint (anteprima pubblica)</span><span class="sxs-lookup"><span data-stu-id="884ba-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites (public preview)</span></span>

><span data-ttu-id="884ba-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="884ba-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="884ba-105">Quando si creano etichette di riservatezza nel [Centro conformità Microsoft 365](https://protection.office.com/), ora è possibile applicarle ai seguenti contenitori: siti di Microsoft Teams, gruppi di Microsoft 365 ([precedentemente, gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="884ba-105">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="884ba-106">Usare le impostazioni di etichetta seguenti per proteggere il contenuto in tali contenitori:</span><span class="sxs-lookup"><span data-stu-id="884ba-106">Use the following label settings to help protect the content in those containers:</span></span>

- <span data-ttu-id="884ba-107">Privacy (pubblico o privato) dei siti dei team collegati ai gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="884ba-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="884ba-108">Accesso di utenti esterni</span><span class="sxs-lookup"><span data-stu-id="884ba-108">External users access</span></span>
- <span data-ttu-id="884ba-109">Accesso da dispositivi non gestiti</span><span class="sxs-lookup"><span data-stu-id="884ba-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="884ba-110">Quando si applica questa etichetta a uno dei contenitori supportati, questa applica automaticamente le opzioni configurate al sito o al gruppo connesso.</span><span class="sxs-lookup"><span data-stu-id="884ba-110">When you apply this label to a supported container, the label automatically applies the configured options to the connected site or group.</span></span> 

<span data-ttu-id="884ba-111">Il contenuto di tali contenitori, tuttavia, non eredita le etichette per impostazioni come il nome dell'etichetta, contrassegni visivi o la crittografia.</span><span class="sxs-lookup"><span data-stu-id="884ba-111">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="884ba-112">Per fare in modo che gli utenti possano etichettare i propri documenti nei siti di SharePoint o del team, [abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="884ba-112">So that users can label their documents in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="884ba-113">Informazioni sull'anteprima pubblica per Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="884ba-113">About the public preview for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="884ba-114">Le etichette di riservatezza per Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint sono in anteprima e potrebbero essere modificate prima del rilascio finale.</span><span class="sxs-lookup"><span data-stu-id="884ba-114">Sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites is in preview and might change before final release.</span></span> <span data-ttu-id="884ba-115">Questa anteprima pubblica non funziona con le reti per la distribuzione di contenuti (CDN) di Office 365.</span><span class="sxs-lookup"><span data-stu-id="884ba-115">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="884ba-116">Prima di abilitare questa anteprima e configurare le etichette di riservatezza per le nuove impostazioni, gli utenti possono vedere e applicare tali etichette nelle loro app.</span><span class="sxs-lookup"><span data-stu-id="884ba-116">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="884ba-117">Un esempio da Word:</span><span class="sxs-lookup"><span data-stu-id="884ba-117">For example, from Word:</span></span>

![Etichetta di riservatezza visualizzata nell'app Word per desktop](../media/sensitivity-label-word.png)

<span data-ttu-id="884ba-119">Dopo l'abilitazione e la configurazione di questa anteprima, gli utenti possono anche vedere e applicare etichette di riservatezza a Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="884ba-119">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="884ba-120">Un esempio quando si crea un nuovo sito del team di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="884ba-120">For example, when you create a new team site from SharePoint:</span></span>

![Etichetta di riservatezza durante la creazione di un sito del team da SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="884ba-122">Abilitare questa anteprima e sincronizzare le etichette</span><span class="sxs-lookup"><span data-stu-id="884ba-122">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="884ba-123">Dato che questa funzione usa le funzionalità di Azure AD, seguire le istruzioni riportate nella relativa documentazione per abilitare l'anteprima: [Assegnare etichette di riservatezza a gruppi di Microsoft 365 in Azure Active Directory (anteprima)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="884ba-123">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="884ba-124">Ora [connettersi a PowerShell per Centro sicurezza e conformità di Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="884ba-124">Now [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="884ba-125">Ad esempio, in una sessione di PowerShell eseguita come amministratore, accedere con un account di amministratore globale:</span><span class="sxs-lookup"><span data-stu-id="884ba-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="884ba-126">Eseguire il comando seguente per sincronizzare le etichette di riservatezza con Azure AD, in modo da poterle usare con i gruppi di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="884ba-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Microsoft 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="884ba-127">Come configurare le impostazioni a livello di sito e gruppo quando si creano o si modificano le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="884ba-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="884ba-128">Ora è possibile creare o modificare le etichette di riservatezza che si desidera rendere disponibili per siti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="884ba-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="884ba-129">L'abilitazione dell'anteprima rende visibile una nuova pagina nelle procedure guidate per l'etichetta di riservatezza: **Impostazioni sito e gruppo**</span><span class="sxs-lookup"><span data-stu-id="884ba-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="884ba-130">Se serve aiuto per creare o modificare un'etichetta di riservatezza, seguire le istruzioni [Creare e configurare etichette di riservatezza](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="884ba-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="884ba-131">In questa nuova pagina **Impostazioni sito e gruppo**, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="884ba-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="884ba-132">**Privacy dei siti dei team connessi a gruppi di Office 365**: mantenere l'impostazione predefinita **Pubblico - qualsiasi utente dell'organizzazione può accedere al sito** se si vuole che chiunque nell'organizzazione possa accedere al sito del team o al gruppo in cui è applicata l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="884ba-132">**Privacy of Office 365 group-connected teams sites**: Keep the default of **Public - anyone in the organization can access the site** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
    
    <span data-ttu-id="884ba-133">Selezionare **Privato** se si vuole limitare l'accesso solo ai membri approvati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="884ba-133">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
    
    <span data-ttu-id="884ba-134">Selezionare **Nessuno: consente agli utenti di scegliere chi può accedere al sito** quando si vuole proteggere il contenuto del contenitore usando l'etichetta di riservatezza, ma consentendo comunque agli utenti di configurare in autonomia le impostazioni di privacy.</span><span class="sxs-lookup"><span data-stu-id="884ba-134">Select **None - let user chose who can access the site** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="884ba-135">Le impostazioni di **Pubblico** o **Privato** impostano e bloccano l'impostazione della privacy quando si applica l'etichetta al contenitore.</span><span class="sxs-lookup"><span data-stu-id="884ba-135">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="884ba-136">L'impostazione scelta sostituisce ogni precedente impostazione della privacy configurata per il team o il gruppo, bloccando il livello di privacy in modo che possa essere modificato solo rimuovendo prima l'etichetta di riservatezza dal contenitore.</span><span class="sxs-lookup"><span data-stu-id="884ba-136">Your chosen seting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="884ba-137">Dopo aver rimosso l'etichetta di riservatezza, viene mantenuto il livello di privacy impostato dall'etichetta, che ora potrà essere modificato, se necessario.</span><span class="sxs-lookup"><span data-stu-id="884ba-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="884ba-138">**Accesso di utenti esterni**: controllare se il proprietario del gruppo può [aggiungere utenti guest al gruppo](/office365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="884ba-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="884ba-139">**Dispositivi non gestiti**: per i [dispositivi non gestiti](/sharepoint/control-access-from-unmanaged-devices), è possibile consentire l'accesso completo, il solo accesso Web o il blocco totale.</span><span class="sxs-lookup"><span data-stu-id="884ba-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![Scheda Impostazioni sito e gruppo](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> <span data-ttu-id="884ba-141">Quando si applica un'etichetta a un team, a un gruppo o a un sito, vengono applicate solo queste impostazioni a livello di sito e gruppo.</span><span class="sxs-lookup"><span data-stu-id="884ba-141">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="884ba-142">Le altre impostazioni dell'etichetta, come la crittografia e il contrassegno di contenuti, non vengono applicate ai contenuto all'interno del team, del gruppo o del sito.</span><span class="sxs-lookup"><span data-stu-id="884ba-142">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="884ba-143">In fase di implementazione graduale nei tenant: quando gli utenti creano team, gruppi e siti, saranno disponibili per la selezione solo le etichette con impostazioni a livello di sito e gruppo.</span><span class="sxs-lookup"><span data-stu-id="884ba-143">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="884ba-144">Se attualmente è possibile applicare un'etichetta a un contenitore quando l'etichetta non ha le impostazioni di sito e gruppo abilitate, al contenitore viene applicato solo il nome dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="884ba-144">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="884ba-145">Se l'etichetta di riservatezza non è già pubblicata, ora è possibile farlo [aggiungendola a un criterio di etichetta di riservatezza](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="884ba-145">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="884ba-146">Gli utenti a cui è stato assegnato un criterio di etichetta di riservatezza che include tale etichetta potranno selezionarla per siti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="884ba-146">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="884ba-147">Dal criterio di etichetta, solo l'impostazione dei criteri **Applica questa etichetta per impostazione predefinita a documenti e messaggi di posta elettronica** è applicabile quando si applica questa etichetta ai contenitori.</span><span class="sxs-lookup"><span data-stu-id="884ba-147">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="884ba-148">Le altre impostazioni dei criteri non vengono applicate, inclusi etichettatura obbligatoria, richiesta della motivazione da parte dell'utente e un collegamento alla pagina della Guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="884ba-148">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="884ba-149">Gestione delle etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="884ba-149">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="884ba-150">La creazione, la modifica e l'eliminazione delle etichette di riservatezza che si usano per Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint richiedono un attento coordinamento con la pubblicazione di criteri delle etichette per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="884ba-150">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Microsoft 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="884ba-151">Evitare errori nella creazione per siti e gruppi che possono incidere su tutti gli utenti, usando le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="884ba-151">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="884ba-152">**Creazione e pubblicazione di etichette**</span><span class="sxs-lookup"><span data-stu-id="884ba-152">**Creating and publishing labels:**</span></span>

<span data-ttu-id="884ba-153">Dopo la creazione e la pubblicazione di un'etichetta di riservatezza, possono essere necessarie fino a 24 ore prima che l'etichetta diventi visibile agli utenti di team, gruppi e siti.</span><span class="sxs-lookup"><span data-stu-id="884ba-153">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="884ba-154">Seguire questa procedura per pubblicare un'etichetta per tutti gli utenti nel tenant:</span><span class="sxs-lookup"><span data-stu-id="884ba-154">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="884ba-155">Creare l'etichetta di riservatezza e pubblicarla solo per pochi account utente nel tenant.</span><span class="sxs-lookup"><span data-stu-id="884ba-155">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="884ba-156">Attendere 24 ore.</span><span class="sxs-lookup"><span data-stu-id="884ba-156">Wait for 24 hours.</span></span>

3. <span data-ttu-id="884ba-157">Dopo questa attesa di 24 ore, usare uno degli account utente specificati nel passaggio 1 per creare un team, un gruppo di Microsoft 365 o un sito di SharePoint con l'etichetta creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="884ba-157">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="884ba-158">Se non si verificano errori durante l'operazione di creazione del passaggio 3, pubblicare l'etichetta per tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="884ba-158">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="884ba-159">In caso di errori, contattare il [Supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="884ba-159">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="884ba-160">**Modifica ed eliminazione di etichette pubblicate**</span><span class="sxs-lookup"><span data-stu-id="884ba-160">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="884ba-161">Se si modifica o si elimina un'etichetta di riservatezza con impostazioni a livello di sito e gruppo abilitate e questa etichetta è inclusa in uno o più criteri di etichetta, queste azioni possono causare errori di creazione per tutti i team, i gruppi e i siti.</span><span class="sxs-lookup"><span data-stu-id="884ba-161">If you modify or delete a sensitivity label with the site and group settings enabled, and that label is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="884ba-162">Per evitare questa situazione, seguire queste indicazioni:</span><span class="sxs-lookup"><span data-stu-id="884ba-162">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="884ba-163">Rimuovere l'etichetta di riservatezza da tutti i criteri che includono l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="884ba-163">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="884ba-164">Attendere 48 ore.</span><span class="sxs-lookup"><span data-stu-id="884ba-164">Wait for 48 hours.</span></span>

3. <span data-ttu-id="884ba-165">Dopo l'attesa di 48 ore, provare a creare un team, un gruppo o un sito e verificare che l'etichetta non sia più visibile.</span><span class="sxs-lookup"><span data-stu-id="884ba-165">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="884ba-166">Se l'etichetta di riservatezza non è visibile, è possibile modificare o eliminare l'etichetta in sicurezza.</span><span class="sxs-lookup"><span data-stu-id="884ba-166">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="884ba-167">Se l'etichetta è ancora visibile, contattare il [Supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="884ba-167">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="884ba-168">Assegnare etichette di riservatezza ai gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="884ba-168">Assign sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="884ba-169">Ora si è pronti per applicare una o più etichette di riservatezza ai gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="884ba-169">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="884ba-170">Per istruzioni, tornare alla documentazione di Azure AD:</span><span class="sxs-lookup"><span data-stu-id="884ba-170">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="884ba-171">Assegnare un'etichetta a un nuovo gruppo nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="884ba-171">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="884ba-172">Assegnare un'etichetta a un gruppo già esistente nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="884ba-172">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="884ba-173">[Assegnare un'etichetta da un gruppo già esistente nel portale di Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="884ba-173">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="884ba-174">Applicare un'etichetta di riservatezza a un nuovo team</span><span class="sxs-lookup"><span data-stu-id="884ba-174">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="884ba-175">Gli utenti possono selezionare le etichette di riservatezza quando creano nuovi team in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="884ba-175">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="884ba-176">Quando selezionano l'etichetta dall'elenco a discesa **Riservatezza**, l'impostazione della privacy può cambiare in modo da riflettere la configurazione dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="884ba-176">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="884ba-177">In base alle impostazioni di accesso degli utenti esterni selezionate per l'etichetta, gli utenti possono o non possano aggiungere al team persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="884ba-177">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="884ba-178">Altre informazioni sulle etichette di riservatezza per Teams</span><span class="sxs-lookup"><span data-stu-id="884ba-178">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Impostazioni di privacy durante la creazione di un nuovo team](../media/privacy-setting-new-team.png)

<span data-ttu-id="884ba-180">Dopo la creazione del team, l'etichetta di riservatezza compare nell'angolo in alto a destra di tutti i canali.</span><span class="sxs-lookup"><span data-stu-id="884ba-180">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![L'etichetta di riservatezza compare nel team](../media/privacy-setting-teams.png)

<span data-ttu-id="884ba-182">Il servizio applica automaticamente la stessa etichetta di riservatezza al gruppo di Microsoft 365 e al sito del team di SharePoint connesso.</span><span class="sxs-lookup"><span data-stu-id="884ba-182">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="884ba-183">Applicare un'etichetta di riservatezza a un nuovo gruppo in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="884ba-183">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="884ba-184">In Outlook sul Web, quando si crea un nuovo gruppo è possibile selezionare o modificare l'opzione **Riservatezza** per le etichette pubblicate:</span><span class="sxs-lookup"><span data-stu-id="884ba-184">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Creazione di un gruppo e selezione di un'opzione in Riservatezza](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="884ba-186">Applicare un'etichetta di riservatezza a un nuovo sito</span><span class="sxs-lookup"><span data-stu-id="884ba-186">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="884ba-187">Gli amministratori e gli utenti finali possono selezionare le etichette di riservatezza quando [creano siti di comunicazione e siti del team moderni](/sharepoint/create-site-collection) ed espandere le **Impostazioni avanzate**:</span><span class="sxs-lookup"><span data-stu-id="884ba-187">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![Creazione di un sito e selezione di un'opzione in Riservatezza](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="884ba-189">La casella a discesa mostra i nomi di etichetta disponibili per la selezione e l'icona della Guida mostra tutti i nomi delle etichette con la relativa descrizione comando, aiutando gli utenti a determinare l'etichetta corretta da applicare.</span><span class="sxs-lookup"><span data-stu-id="884ba-189">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="884ba-190">Quando l'etichetta viene applicata e gli utenti visitano il sito, vedono il nome dell'etichetta e i criteri applicati.</span><span class="sxs-lookup"><span data-stu-id="884ba-190">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="884ba-191">Ad esempio, questo sito è stato etichettato come **Riservato** e l'impostazione della privacy è **Privato**:</span><span class="sxs-lookup"><span data-stu-id="884ba-191">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![Sito a cui è applicata un'etichetta di riservatezza](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="884ba-193">Visualizzare le etichette di riservatezza nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="884ba-193">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="884ba-194">Per visualizzare le etichette di riservatezza applicate, usare la pagina **Siti attivi** nella nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="884ba-194">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="884ba-195">Potrebbe essere necessario aggiungere prima la colonna **Riservatezza**:</span><span class="sxs-lookup"><span data-stu-id="884ba-195">You might need to first add the **Sensitivity** column:</span></span>

![Colonna Riservatezza nella pagina Siti attivi](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="884ba-197">[Altre informazioni sulla gestione dei siti nella nuova interfaccia di amministrazione di SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="884ba-197">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="884ba-198">Modificare le impostazioni a livello di sito e gruppo</span><span class="sxs-lookup"><span data-stu-id="884ba-198">Change site and group settings for a label</span></span>

<span data-ttu-id="884ba-199">Ogni volta che si apporta una modifica alle impostazioni di sito e gruppo per un'etichetta, è necessario eseguire i comandi di PowerShell seguenti in modo che i team, i siti e i gruppi possano usare le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="884ba-199">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="884ba-200">Come procedura consigliata, non modificare le impostazioni di sito e gruppo per un'etichetta dopo aver applicato l'etichetta di riservatezza a più team, gruppi o siti.</span><span class="sxs-lookup"><span data-stu-id="884ba-200">As a best practice, don't the change site and group settings for a label after you've applied the sensitivity label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="884ba-201">Prima di tutto, [connettersi a PowerShell in Centro sicurezza e conformità di Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="884ba-201">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="884ba-202">Ad esempio, in una sessione di PowerShell eseguita come amministratore, accedere con un account di amministratore globale:</span><span class="sxs-lookup"><span data-stu-id="884ba-202">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="884ba-203">Ottenere l'elenco delle etichette di riservatezza e dei GUID corrispondenti usando il cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="884ba-203">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="884ba-204">Prendere nota del GUID dell'etichetta o delle etichette modificate.</span><span class="sxs-lookup"><span data-stu-id="884ba-204">Make a note of the GUID for the label or labels you have changed.</span></span>

4. <span data-ttu-id="884ba-205">Ora [connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="884ba-205">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="884ba-206">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="884ba-206">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```
    
5. <span data-ttu-id="884ba-207">Eseguire il cmdlet [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps), specificando il GUID dell'etichetta al posto del GUID di esempio "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="884ba-207">Run the [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

6. <span data-ttu-id="884ba-208">Per ogni gruppo, riapplicare l'etichetta di riservatezza specificando il GUID dell'etichetta al posto del GUID di esempio "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="884ba-208">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="884ba-209">Supporto per le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="884ba-209">Support for the sensitivity labels</span></span>

<span data-ttu-id="884ba-210">È possibile usare le etichette di riservatezza configurate per le impostazioni del sito e del gruppo con le app e i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="884ba-210">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="884ba-211">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="884ba-211">SharePoint Online</span></span>
- <span data-ttu-id="884ba-212">Teams</span><span class="sxs-lookup"><span data-stu-id="884ba-212">Teams</span></span>
- <span data-ttu-id="884ba-213">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="884ba-213">Outlook on the web</span></span>
- <span data-ttu-id="884ba-214">Interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="884ba-214">SharePoint admin center</span></span>
- <span data-ttu-id="884ba-215">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="884ba-215">Azure AD admin center</span></span>

<span data-ttu-id="884ba-216">Non risulta invece possibile utilizzare le etichette di riservatezza configurate per le impostazioni del sito e del gruppo con le app e i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="884ba-216">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="884ba-217">Outlook per Mac</span><span class="sxs-lookup"><span data-stu-id="884ba-217">Outlook for the Mac</span></span>
- <span data-ttu-id="884ba-218">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="884ba-218">Outlook mobile</span></span>
- <span data-ttu-id="884ba-219">Outlook desktop per Windows</span><span class="sxs-lookup"><span data-stu-id="884ba-219">Outlook desktop for Windows</span></span>
- <span data-ttu-id="884ba-220">Forms</span><span class="sxs-lookup"><span data-stu-id="884ba-220">Forms</span></span>
- <span data-ttu-id="884ba-221">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="884ba-221">Dynamics 365</span></span>
- <span data-ttu-id="884ba-222">Yammer</span><span class="sxs-lookup"><span data-stu-id="884ba-222">Yammer</span></span>
- <span data-ttu-id="884ba-223">Stream</span><span class="sxs-lookup"><span data-stu-id="884ba-223">Stream</span></span>
- <span data-ttu-id="884ba-224">Planner</span><span class="sxs-lookup"><span data-stu-id="884ba-224">Planner</span></span>
- <span data-ttu-id="884ba-225">Project</span><span class="sxs-lookup"><span data-stu-id="884ba-225">Project</span></span>
- <span data-ttu-id="884ba-226">PowerBI</span><span class="sxs-lookup"><span data-stu-id="884ba-226">PowerBI</span></span>
- <span data-ttu-id="884ba-227">Interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="884ba-227">Teams admin center</span></span>
- <span data-ttu-id="884ba-228">Interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="884ba-228">Microsoft 365 admin center</span></span>
- <span data-ttu-id="884ba-229">Interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="884ba-229">Exchange admin center</span></span>


## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="884ba-230">Classificazione dei gruppi di Azure AD classica</span><span class="sxs-lookup"><span data-stu-id="884ba-230">Classic Azure AD group classification</span></span>

<span data-ttu-id="884ba-231">Quando si abilita questa anteprima, Microsoft 365 non supporta più le vecchie classificazioni per i nuovi gruppi di Microsoft 365 e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="884ba-231">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="884ba-232">Tuttavia, i gruppi e i siti esistenti continuano a visualizzare i vecchi valori di classificazione, a meno che non vengano convertiti in modo da usa le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="884ba-232">However, existing groups and sites still display the old classification values unless you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="884ba-233">Come esempio della classificazione dei gruppi precedente per SharePoint, vedere [Classificazione dei siti "moderni" di SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="884ba-233">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="884ba-234">Queste classificazioni venivano configurate tramite Azure AD PowerShell o la raccolta PnP Core e definendo i valori per l'impostazione `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="884ba-234">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="884ba-235">Se il tenant include valori di classificazione definiti, vengono visualizzati eseguendo il comando seguente dal [modulo PowerShell AzureADPreview](https://www.powershellgallery.com/packages/AzureADPreview):</span><span class="sxs-lookup"><span data-stu-id="884ba-235">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="884ba-236">Per passare dalle vecchie classificazioni alle etichette di riservatezza, eseguire una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="884ba-236">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="884ba-237">Usare etichette esistenti: specificare le impostazioni di etichetta desiderate per i siti e i gruppi modificando etichette di riservatezza esistenti e già pubblicate.</span><span class="sxs-lookup"><span data-stu-id="884ba-237">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="884ba-238">Creare nuove etichette: specificare le impostazioni di etichetta desiderate per i siti e i gruppi creando e pubblicando nuove etichette di riservatezza che abbiano nomi identici alle classificazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="884ba-238">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="884ba-239">In seguito:</span><span class="sxs-lookup"><span data-stu-id="884ba-239">Then:</span></span> 

1. <span data-ttu-id="884ba-240">Usare PowerShell per applicare le etichette di riservatezza ai gruppi di Microsoft 365 e ai siti di SharePoint esistenti utilizzando il mapping del nome.</span><span class="sxs-lookup"><span data-stu-id="884ba-240">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="884ba-241">Per istruzioni, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="884ba-241">See the next section for instructions.</span></span>

2. <span data-ttu-id="884ba-242">Rimuovere le vecchie classificazioni dai gruppi e siti esistenti.</span><span class="sxs-lookup"><span data-stu-id="884ba-242">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="884ba-243">Nonostante non si possa impedire agli utenti di creare nuovi gruppi in app e servizi che non supportano ancora le etichette di riservatezza, è tuttavia possibile eseguire uno script di PowerShell ricorrente per cercare nuovi gruppi che gli utenti abbiano creato con le vecchie classificazioni, per poi convertirli all'uso delle etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="884ba-243">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="884ba-244">Usare PowerShell per convertire le classificazioni per i gruppi di Microsoft 365 in etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="884ba-244">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="884ba-245">Prima di tutto, [connettersi a PowerShell in Centro sicurezza e conformità di Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="884ba-245">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="884ba-246">Ad esempio, in una sessione di PowerShell eseguita come amministratore, accedere con un account di amministratore globale:</span><span class="sxs-lookup"><span data-stu-id="884ba-246">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="884ba-247">Ottenere l'elenco delle etichette di riservatezza e dei GUID corrispondenti usando il cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="884ba-247">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="884ba-248">Prendere nota dei GUID per le etichette di riservatezza che si desidera applicare ai gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="884ba-248">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="884ba-249">Ora [connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="884ba-249">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="884ba-250">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="884ba-250">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. <span data-ttu-id="884ba-251">Usare il comando seguente come un esempio per visualizzare l'elenco dei gruppi al momento classificati come "Generale":</span><span class="sxs-lookup"><span data-stu-id="884ba-251">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="884ba-252">Per ogni gruppo, aggiungere il GUID della nuova etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="884ba-252">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="884ba-253">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="884ba-253">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="884ba-254">Ripetere i passaggi 5 e 6 per le classificazioni dei gruppi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="884ba-254">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="884ba-255">Controllo delle attività sulle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="884ba-255">Auditing sensitivity label activities</span></span>

<span data-ttu-id="884ba-256">Se qualcuno carica un documento in un sito protetto con un'etichetta di riservatezza e il documento ha un'etichetta di riservatezza con [priorità più elevata](sensitivity-labels.md#label-priority-order-matters) rispetto all'etichetta di riservatezza applicata al sito, l'azione non verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="884ba-256">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="884ba-257">Ad esempio, si supponga sia stata applicata l'etichetta **Generale** a un sito di SharePoint e che qualcuno carichi su tale sito un documento con etichetta **Riservato**.</span><span class="sxs-lookup"><span data-stu-id="884ba-257">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="884ba-258">Dato che un'etichetta di riservatezza con una priorità più elevata identifica un contenuto maggiormente riservato di quello contrassegnato con un ordine di priorità inferiore, la situazione potrebbe porre un problema di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="884ba-258">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="884ba-259">Anche se l'azione non è bloccata, viene controllata e genera automaticamente un messaggio di posta elettronica per la persona che ha caricato il documento e l'amministratore del sito.</span><span class="sxs-lookup"><span data-stu-id="884ba-259">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="884ba-260">Di conseguenza, sia l'utente che l'amministratore possono identificare quali documenti abbiano questo disallineamento di priorità dell'etichetta e, se necessario, intervenire.</span><span class="sxs-lookup"><span data-stu-id="884ba-260">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="884ba-261">Ad esempio, è possibile spostare o eliminare dal sito il documento caricato.</span><span class="sxs-lookup"><span data-stu-id="884ba-261">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="884ba-262">Non costituirebbe alcun problema di sicurezza se il documento recasse un'etichetta di riservatezza con priorità inferiore rispetto a quella applicata al sito.</span><span class="sxs-lookup"><span data-stu-id="884ba-262">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="884ba-263">Ad esempio, un documento con etichetta **Generale** viene caricato in un sito con etichetta **Riservato**.</span><span class="sxs-lookup"><span data-stu-id="884ba-263">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="884ba-264">In questo scenario non viene generato alcun evento di controllo o messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="884ba-264">In this scenario, an auditing event and email isn't generated.</span></span>

<span data-ttu-id="884ba-265">Per eseguire una ricerca di tale evento nel log di controllo, cercare **È stata rilevata una mancata corrispondenza della riservatezza del documento** nella categoria **Attività su file e pagine**.</span><span class="sxs-lookup"><span data-stu-id="884ba-265">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="884ba-266">Il messaggio di posta elettronica generato automaticamente ha l'oggetto **Rilevata etichetta di riservatezza incompatibile** e il messaggio di posta elettronica spiega la mancata corrispondenza dell'etichetta, con un collegamento al documento caricato e al sito.</span><span class="sxs-lookup"><span data-stu-id="884ba-266">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="884ba-267">Include anche un collegamento alla documentazione che spiega in che modo gli utenti possono modificare l'etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="884ba-267">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="884ba-268">Attualmente, non è possibile disabilitare o personalizzare questi messaggi di posta elettronica automatici.</span><span class="sxs-lookup"><span data-stu-id="884ba-268">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="884ba-269">Vengono controllate anche le attività di aggiunta o rimozione di un'etichetta di riservatezza da un sito o gruppo, senza però che venga generato un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="884ba-269">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span> 

<span data-ttu-id="884ba-270">Tutti questi eventi di controllo sono disponibili nella categoria [Attività etichetta di riservatezza](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities).</span><span class="sxs-lookup"><span data-stu-id="884ba-270">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="884ba-271">Per istruzioni sulla ricerca nel log di controllo, vedere [Eseguire ricerche nel log di controllo nel Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="884ba-271">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="884ba-272">Risolvere i problemi di distribuzione delle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="884ba-272">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="884ba-273">Problemi con le etichette di riservatezza per Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint?</span><span class="sxs-lookup"><span data-stu-id="884ba-273">Having problems with sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="884ba-274">Verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="884ba-274">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="884ba-275">Etichette non visibili dopo la pubblicazione</span><span class="sxs-lookup"><span data-stu-id="884ba-275">Labels not visible after publishing</span></span>
<span data-ttu-id="884ba-276">Se si verificano problemi durante la creazione di un sito o un gruppo di Microsoft 365 dopo aver abilitato queste impostazioni o aver modificato il nome o la descrizione comando di un'etichetta di riservatezza, attendere alcune ore e quindi provare di nuovo a creare il team o il gruppo.</span><span class="sxs-lookup"><span data-stu-id="884ba-276">If you experience issues when you create a site or Microsoft 365 group after you enable these settings or modify a sensitivity label's name or tooltip, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="884ba-277">Per informazioni, vedere [Pianificare l'implementazione dopo aver creato o modificato un'etichetta di riservatezza](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="884ba-277">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="884ba-278">Se non è ancora possibile vedere la nuova etichetta di riservatezza da SharePoint Online, contattare il [Supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="884ba-278">If you still can't see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="884ba-279">Errori nella creazione di team, gruppi o siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="884ba-279">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="884ba-280">Se si verificano errori di creazione durante l'anteprima pubblica, è possibile disattivare le etichette di riservatezza per Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint seguendo le stesse istruzioni per [Abilitare il supporto per le etichette di riservatezza](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="884ba-280">If you experience creation errors during the public preview, you can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="884ba-281">Tuttavia, per disabilitare l'anteprima, disabilitare la funzionalità usando `$setting["EnableMIPLabels"] = "False"` al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="884ba-281">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="884ba-282">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="884ba-282">Additional resources</span></span>

<span data-ttu-id="884ba-283">Per informazioni su come [usare le etichette di riservatezza con Microsoft Teams, Gruppi di Office 365 e i siti di SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380), consultare la registrazione del webinar e le risposte alle domande.</span><span class="sxs-lookup"><span data-stu-id="884ba-283">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

