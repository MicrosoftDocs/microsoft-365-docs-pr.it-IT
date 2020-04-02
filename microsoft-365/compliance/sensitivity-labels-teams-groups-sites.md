---
title: Usare le etichette di riservatezza con Microsoft Teams, gruppi di Office 365 e siti di SharePoint (anteprima pubblica)
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
description: Usare le etichette di riservatezza per proteggere il contenuto in siti di SharePoint e Microsoft Teams e in gruppi di Office 365.
ms.openlocfilehash: 0ac1d9f605c32664115086057b7c17355d495c00
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106134"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="c8837-103">Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Office 365 e siti di SharePoint (anteprima pubblica)</span><span class="sxs-lookup"><span data-stu-id="c8837-103">Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

><span data-ttu-id="c8837-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c8837-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c8837-105">Quando si creano etichette di riservatezza nel [Centro conformità Microsoft 365](https://protection.office.com/), ora è possibile applicarle ai seguenti contenitori: siti di Microsoft Teams, gruppi di Office 365 e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8837-105">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams sites, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="c8837-106">Usare le impostazioni di etichetta seguenti per proteggere il contenuto in tali contenitori:</span><span class="sxs-lookup"><span data-stu-id="c8837-106">Use the following label settings to help protect the content in those containers:</span></span>

- <span data-ttu-id="c8837-107">Privacy (pubblico o privato) dei siti dei team collegati ai gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="c8837-107">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="c8837-108">Accesso di utenti esterni</span><span class="sxs-lookup"><span data-stu-id="c8837-108">External users access</span></span>
- <span data-ttu-id="c8837-109">Accesso da dispositivi non gestiti</span><span class="sxs-lookup"><span data-stu-id="c8837-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="c8837-110">Quando si applica questa etichetta a uno dei contenitori supportati, questa applica automaticamente le opzioni configurate al sito o al gruppo connesso.</span><span class="sxs-lookup"><span data-stu-id="c8837-110">When you apply this label to a supported container, the label automatically applies the configured options to the connected site or group.</span></span> 

<span data-ttu-id="c8837-111">Il contenuto di tali contenitori, tuttavia, non eredita le etichette per impostazioni come il nome dell'etichetta, contrassegni visivi o la crittografia.</span><span class="sxs-lookup"><span data-stu-id="c8837-111">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="c8837-112">Per fare in modo che gli utenti possano etichettare i propri documenti nei siti di SharePoint o del team, [abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="c8837-112">So that users can label their documents in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="c8837-113">Informazioni sull'anteprima pubblica per Microsoft Teams, gruppi di Office 365 e siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8837-113">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="c8837-114">Le etichette di riservatezza per Microsoft Teams, gruppi di Office 365 e siti di SharePoint sono in fase di implementazione graduale nei tenant e potrebbero essere modificate prima del rilascio finale.</span><span class="sxs-lookup"><span data-stu-id="c8837-114">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are in gradual rollout to tenants and might change before final release.</span></span> <span data-ttu-id="c8837-115">Questa anteprima pubblica non funziona con le reti per la distribuzione di contenuti (CDN) di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c8837-115">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="c8837-116">Prima di abilitare questa anteprima e configurare le etichette di riservatezza per le nuove impostazioni, gli utenti possono vedere e applicare tali etichette nelle loro app.</span><span class="sxs-lookup"><span data-stu-id="c8837-116">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="c8837-117">Un esempio da Word:</span><span class="sxs-lookup"><span data-stu-id="c8837-117">For example, from Word:</span></span>

![Etichetta di riservatezza visualizzata nell'app Word per desktop](../media/sensitivity-label-word.png)

<span data-ttu-id="c8837-119">Dopo l'abilitazione e la configurazione di questa anteprima, gli utenti possono anche vedere e applicare etichette di riservatezza a Microsoft Teams, gruppi di Office 365 e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8837-119">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="c8837-120">Un esempio quando si crea un nuovo sito del team di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c8837-120">For example, when you create a new team site from SharePoint:</span></span>

![Etichetta di riservatezza durante la creazione di un sito del team da SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="c8837-122">Abilitare questa anteprima e sincronizzare le etichette</span><span class="sxs-lookup"><span data-stu-id="c8837-122">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="c8837-123">Dato che questa funzione usa le funzionalità di Azure AD, seguire le istruzioni riportate nella relativa documentazione per abilitare l'anteprima: [Assegnare etichette di riservatezza a gruppi di Office 365 in Azure Active Directory (anteprima)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c8837-123">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="c8837-124">Aprire una sessione di PowerShell con l'opzione **Esegui come amministratore** e connettersi al Centro sicurezza e conformità usando un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c8837-124">Open a PowerShell session with the **Run as Administrator** option, and connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="c8837-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c8837-125">For example:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```
    
    <span data-ttu-id="c8837-126">Per istruzioni complete, vedere [Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8837-126">For full instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="c8837-127">Eseguire il comando seguente per sincronizzare le etichette di riservatezza con Azure AD, in modo da poterle usare con i gruppi di Office 365:</span><span class="sxs-lookup"><span data-stu-id="c8837-127">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="c8837-128">Come configurare le impostazioni a livello di sito e gruppo quando si creano o si modificano le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8837-128">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="c8837-129">Ora è possibile creare o modificare le etichette di riservatezza che si desidera rendere disponibili per siti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8837-129">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="c8837-130">L'abilitazione dell'anteprima rende visibile una nuova pagina nelle procedure guidate per l'etichetta di riservatezza: **Impostazioni sito e gruppo**</span><span class="sxs-lookup"><span data-stu-id="c8837-130">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="c8837-131">Se serve aiuto per creare o modificare un'etichetta di riservatezza, seguire le istruzioni [Creare e configurare etichette di riservatezza](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c8837-131">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="c8837-132">In questa nuova pagina **Impostazioni sito e gruppo**, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8837-132">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="c8837-133">**Privacy dei siti dei team connessi a gruppi di Office 365**: l'impostazione predefinita **Nessuno: consente agli utenti di scegliere chi può accedere al sito** è in fase di distribuzione ai tenant.</span><span class="sxs-lookup"><span data-stu-id="c8837-133">**Privacy of Office 365 group-connected teams sites**: The default setting of **None - let user chose who can access the site** is currently rolling out to tenants.</span></span> <span data-ttu-id="c8837-134">Mantenere questa impostazione predefinita quando si vuole proteggere il contenuto del contenitore usando l'etichetta di riservatezza, ma consentendo comunque agli utenti di configurare in autonomia le impostazioni di privacy.</span><span class="sxs-lookup"><span data-stu-id="c8837-134">Keep this default setting when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="c8837-135">Selezionare **Pubblico** o **Privato** per impostare e bloccare l'impostazione della privacy quando si applica l'etichetta al contenitore.</span><span class="sxs-lookup"><span data-stu-id="c8837-135">Select **Public** or**Private** to set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="c8837-136">Scegliere **Pubblico** se si vuole che tutti gli utenti dell'organizzazione possano accedere al sito del team o al gruppo a cui è applicata l'etichetta oppure **Privato** se si vuole limitare l'accesso solo ai membri approvati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8837-136">Choose **Public** if you want anyone in your organization to access the team site or group where this label is applied, or **Private** if you want access to be restricted to only approved members in your organization.</span></span> 
    
    <span data-ttu-id="c8837-137">L'impostazione **Pubblico** o **Privato** sostituisce ogni precedente impostazione della privacy configurata per il team o il gruppo, bloccando il livello di privacy in modo che possa essere modificato solo rimuovendo prima l'etichetta di riservatezza dal contenitore.</span><span class="sxs-lookup"><span data-stu-id="c8837-137">The **Public** or **Private** setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="c8837-138">Dopo aver rimosso l'etichetta di riservatezza, viene mantenuto il livello di privacy impostato dall'etichetta, che ora potrà essere modificato, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c8837-138">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="c8837-139">**Accesso di utenti esterni**: controllare se il proprietario del gruppo può [aggiungere utenti guest al gruppo](/office365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="c8837-139">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="c8837-140">**Dispositivi non gestiti**: per i [dispositivi non gestiti](/sharepoint/control-access-from-unmanaged-devices), è possibile consentire l'accesso completo, il solo accesso Web o il blocco totale.</span><span class="sxs-lookup"><span data-stu-id="c8837-140">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![Scheda Impostazioni sito e gruppo](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="c8837-142">Quando si applica un'etichetta a un team, a un gruppo o a un sito, vengono applicate solo queste impostazioni a livello di sito e gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8837-142">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="c8837-143">Le altre impostazioni dell'etichetta, come la crittografia e il contrassegno di contenuti, non vengono applicate ai contenuto all'interno del team, del gruppo o del sito.</span><span class="sxs-lookup"><span data-stu-id="c8837-143">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="c8837-144">In fase di implementazione graduale nei tenant: quando gli utenti creano team, gruppi e siti, saranno disponibili per la selezione solo le etichette con impostazioni a livello di sito e gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8837-144">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="c8837-145">Se attualmente è possibile applicare un'etichetta a un contenitore quando l'etichetta non ha le impostazioni di sito e gruppo abilitate, al contenitore viene applicato solo il nome dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="c8837-145">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="c8837-146">Se l'etichetta di riservatezza non è già pubblicata, ora è possibile farlo [aggiungendola a un criterio di etichetta di riservatezza](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="c8837-146">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="c8837-147">Gli utenti a cui è stato assegnato un criterio di etichetta di riservatezza che include tale etichetta potranno selezionarla per siti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8837-147">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="c8837-148">Dal criterio di etichetta, solo l'impostazione dei criteri **Applica questa etichetta per impostazione predefinita a documenti e messaggi di posta elettronica** è applicabile quando si applica questa etichetta ai contenitori.</span><span class="sxs-lookup"><span data-stu-id="c8837-148">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="c8837-149">Le altre impostazioni dei criteri non vengono applicate, inclusi etichettatura obbligatoria, richiesta della motivazione da parte dell'utente e un collegamento alla pagina della Guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c8837-149">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="c8837-150">Gestione delle etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8837-150">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="c8837-151">La creazione, la modifica e l'eliminazione delle etichette di riservatezza che si usano per Microsoft Teams, gruppi di Office 365 e siti di SharePoint richiedono un attento coordinamento con la pubblicazione di criteri delle etichette per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c8837-151">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="c8837-152">Evitare errori nella creazione per siti e gruppi che possono incidere su tutti gli utenti, usando le indicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c8837-152">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="c8837-153">**Creazione e pubblicazione di etichette**</span><span class="sxs-lookup"><span data-stu-id="c8837-153">**Creating and publishing labels:**</span></span>

<span data-ttu-id="c8837-154">Dopo la creazione e la pubblicazione di un'etichetta di riservatezza, possono essere necessarie fino a 24 ore prima che l'etichetta diventi visibile agli utenti di team, gruppi e siti.</span><span class="sxs-lookup"><span data-stu-id="c8837-154">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="c8837-155">Seguire questa procedura per pubblicare un'etichetta per tutti gli utenti nel tenant:</span><span class="sxs-lookup"><span data-stu-id="c8837-155">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="c8837-156">Creare l'etichetta di riservatezza e pubblicarla solo per pochi account utente nel tenant.</span><span class="sxs-lookup"><span data-stu-id="c8837-156">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="c8837-157">Attendere 24 ore.</span><span class="sxs-lookup"><span data-stu-id="c8837-157">Wait for 24 hours.</span></span>

3. <span data-ttu-id="c8837-158">Dopo questa attesa di 24 ore, usare uno degli account utente specificati nel passaggio 1 per creare un team, un gruppo di Office 365 o un sito di SharePoint con l'etichetta creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c8837-158">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="c8837-159">Se non si verificano errori durante l'operazione di creazione del passaggio 3, pubblicare l'etichetta per tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="c8837-159">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="c8837-160">In caso di errori, contattare il [Supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="c8837-160">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="c8837-161">**Modifica ed eliminazione di etichette pubblicate**</span><span class="sxs-lookup"><span data-stu-id="c8837-161">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="c8837-162">Se si modifica o si elimina un'etichetta di riservatezza con impostazioni a livello di sito e gruppo abilitate e questa etichetta è inclusa in uno o più criteri di etichetta, queste azioni possono causare errori di creazione per tutti i team, i gruppi e i siti.</span><span class="sxs-lookup"><span data-stu-id="c8837-162">If you modify or delete a sensitivity label with the site and group settings enabled, and that label is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="c8837-163">Per evitare questa situazione, seguire queste indicazioni:</span><span class="sxs-lookup"><span data-stu-id="c8837-163">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="c8837-164">Rimuovere l'etichetta di riservatezza da tutti i criteri che includono l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="c8837-164">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="c8837-165">Attendere 48 ore.</span><span class="sxs-lookup"><span data-stu-id="c8837-165">Wait for 48 hours.</span></span>

3. <span data-ttu-id="c8837-166">Dopo l'attesa di 48 ore, provare a creare un team, un gruppo o un sito e verificare che l'etichetta non sia più visibile.</span><span class="sxs-lookup"><span data-stu-id="c8837-166">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="c8837-167">Se l'etichetta di riservatezza non è visibile, è possibile modificare o eliminare l'etichetta in sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c8837-167">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="c8837-168">Se l'etichetta è ancora visibile, contattare il [Supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="c8837-168">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="c8837-169">Assegnare etichette di riservatezza ai gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="c8837-169">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="c8837-170">Ora si è pronti per applicare una o più etichette di riservatezza ai gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c8837-170">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="c8837-171">Per istruzioni, tornare alla documentazione di Azure AD:</span><span class="sxs-lookup"><span data-stu-id="c8837-171">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="c8837-172">Assegnare un'etichetta a un nuovo gruppo nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="c8837-172">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="c8837-173">Assegnare un'etichetta a un gruppo già esistente nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="c8837-173">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="c8837-174">[Assegnare un'etichetta da un gruppo già esistente nel portale di Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c8837-174">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="c8837-175">Applicare un'etichetta di riservatezza a un nuovo team</span><span class="sxs-lookup"><span data-stu-id="c8837-175">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="c8837-176">Gli utenti possono selezionare le etichette di riservatezza quando creano nuovi team in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c8837-176">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="c8837-177">Quando selezionano l'etichetta dall'elenco a discesa **Riservatezza**, l'impostazione della privacy può cambiare in modo da riflettere la configurazione dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="c8837-177">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="c8837-178">In base alle impostazioni di accesso degli utenti esterni selezionate per l'etichetta, gli utenti possono o non possano aggiungere al team persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8837-178">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="c8837-179">Altre informazioni sulle etichette di riservatezza per Teams</span><span class="sxs-lookup"><span data-stu-id="c8837-179">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Impostazioni di privacy durante la creazione di un nuovo team](../media/privacy-setting-new-team.png)

<span data-ttu-id="c8837-181">Dopo la creazione del team, l'etichetta di riservatezza compare nell'angolo in alto a destra di tutti i canali.</span><span class="sxs-lookup"><span data-stu-id="c8837-181">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![L'etichetta di riservatezza compare nel team](../media/privacy-setting-teams.png)

<span data-ttu-id="c8837-183">Il servizio applica automaticamente la stessa etichetta di riservatezza al gruppo di Office 365 e al sito del team di SharePoint connesso.</span><span class="sxs-lookup"><span data-stu-id="c8837-183">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="c8837-184">Applicare un'etichetta di riservatezza a un nuovo gruppo in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="c8837-184">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="c8837-185">In Outlook sul Web, quando si crea un nuovo gruppo è possibile selezionare o modificare l'opzione **Riservatezza** per le etichette pubblicate:</span><span class="sxs-lookup"><span data-stu-id="c8837-185">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Creazione di un gruppo e selezione di un'opzione in Riservatezza](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="c8837-187">Applicare un'etichetta di riservatezza a un nuovo sito</span><span class="sxs-lookup"><span data-stu-id="c8837-187">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="c8837-188">Gli amministratori e gli utenti finali possono selezionare le etichette di riservatezza quando [creano siti di comunicazione e siti del team moderni](/sharepoint/create-site-collection) ed espandere le **Impostazioni avanzate**:</span><span class="sxs-lookup"><span data-stu-id="c8837-188">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![Creazione di un sito e selezione di un'opzione in Riservatezza](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="c8837-190">La casella a discesa mostra i nomi di etichetta disponibili per la selezione e l'icona della Guida mostra tutti i nomi delle etichette con la relativa descrizione comando, aiutando gli utenti a determinare l'etichetta corretta da applicare.</span><span class="sxs-lookup"><span data-stu-id="c8837-190">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="c8837-191">Quando l'etichetta viene applicata e gli utenti visitano il sito, vedono il nome dell'etichetta e i criteri applicati.</span><span class="sxs-lookup"><span data-stu-id="c8837-191">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="c8837-192">Ad esempio, questo sito è stato etichettato come **Riservato** e l'impostazione della privacy è **Privato**:</span><span class="sxs-lookup"><span data-stu-id="c8837-192">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![Sito a cui è applicata un'etichetta di riservatezza](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="c8837-194">Visualizzare le etichette di riservatezza nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8837-194">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="c8837-195">Per visualizzare le etichette di riservatezza applicate, usare la pagina **Siti attivi** nella nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8837-195">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="c8837-196">Potrebbe essere necessario aggiungere prima la colonna **Riservatezza**:</span><span class="sxs-lookup"><span data-stu-id="c8837-196">You might need to first add the **Sensitivity** column:</span></span>

![Colonna Riservatezza nella pagina Siti attivi](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="c8837-198">[Altre informazioni sulla gestione dei siti nella nuova interfaccia di amministrazione di SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c8837-198">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="c8837-199">Modificare le impostazioni a livello di sito e gruppo</span><span class="sxs-lookup"><span data-stu-id="c8837-199">Change site and group settings for a label</span></span>

<span data-ttu-id="c8837-200">Ogni volta che si apporta una modifica alle impostazioni di sito e gruppo per un'etichetta, è necessario eseguire i comandi di PowerShell seguenti in modo che i team, i siti e i gruppi possano usare le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c8837-200">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="c8837-201">Come procedura consigliata, non modificare le impostazioni di sito e gruppo per un'etichetta dopo aver applicato l'etichetta a più team, gruppi o siti.</span><span class="sxs-lookup"><span data-stu-id="c8837-201">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="c8837-202">In una sessione di PowerShell aperta con l'opzione **Esegui come amministratore** eseguire i comandi seguenti per connettersi a PowerShell per Centro sicurezza e conformità di Office 365 e ottenere l'elenco delle etichette di riservatezza e i relativi GUID.</span><span class="sxs-lookup"><span data-stu-id="c8837-202">In a PowerShell session that you open with the **Run as Administrator** option, run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="c8837-203">Prendere nota del GUID dell'etichetta o delle etichette modificate.</span><span class="sxs-lookup"><span data-stu-id="c8837-203">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="c8837-204">Ora connettersi a PowerShell per Exchange Online ed eseguire il cmdlet Get-UnifiedGroup, specificando il GUID dell'etichetta al posto del GUID di esempio "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="c8837-204">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="c8837-205">Per ogni gruppo, riapplicare l'etichetta di riservatezza specificando il GUID dell'etichetta al posto del GUID di esempio "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="c8837-205">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="c8837-206">Supporto per le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8837-206">Support for the sensitivity labels</span></span>

<span data-ttu-id="c8837-207">È possibile usare le etichette di riservatezza configurate per le impostazioni del sito e del gruppo con le app e i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8837-207">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="c8837-208">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c8837-208">SharePoint Online</span></span>
- <span data-ttu-id="c8837-209">Teams</span><span class="sxs-lookup"><span data-stu-id="c8837-209">Teams</span></span>
- <span data-ttu-id="c8837-210">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="c8837-210">Outlook on the web</span></span>
- <span data-ttu-id="c8837-211">Interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8837-211">SharePoint admin center</span></span>
- <span data-ttu-id="c8837-212">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="c8837-212">Azure AD admin center</span></span>

<span data-ttu-id="c8837-213">Non risulta invece possibile utilizzare le etichette di riservatezza configurate per le impostazioni del sito e del gruppo con le app e i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8837-213">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="c8837-214">Outlook per Mac</span><span class="sxs-lookup"><span data-stu-id="c8837-214">Outlook for the Mac</span></span>
- <span data-ttu-id="c8837-215">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="c8837-215">Outlook mobile</span></span>
- <span data-ttu-id="c8837-216">Outlook desktop per Windows</span><span class="sxs-lookup"><span data-stu-id="c8837-216">Outlook desktop for Windows</span></span>
- <span data-ttu-id="c8837-217">Forms</span><span class="sxs-lookup"><span data-stu-id="c8837-217">Forms</span></span>
- <span data-ttu-id="c8837-218">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c8837-218">Dynamics 365</span></span>
- <span data-ttu-id="c8837-219">Yammer</span><span class="sxs-lookup"><span data-stu-id="c8837-219">Yammer</span></span>
- <span data-ttu-id="c8837-220">Stream</span><span class="sxs-lookup"><span data-stu-id="c8837-220">Stream</span></span>
- <span data-ttu-id="c8837-221">Planner</span><span class="sxs-lookup"><span data-stu-id="c8837-221">Planner</span></span>
- <span data-ttu-id="c8837-222">Project</span><span class="sxs-lookup"><span data-stu-id="c8837-222">Project</span></span>
- <span data-ttu-id="c8837-223">PowerBI</span><span class="sxs-lookup"><span data-stu-id="c8837-223">PowerBI</span></span>
- <span data-ttu-id="c8837-224">Interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="c8837-224">Teams admin center</span></span>
- <span data-ttu-id="c8837-225">Interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8837-225">Microsoft 365 admin center</span></span>
- <span data-ttu-id="c8837-226">Interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="c8837-226">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="c8837-227">Classificazione dei siti di Azure AD classica</span><span class="sxs-lookup"><span data-stu-id="c8837-227">Classic Azure AD site classification</span></span>

<span data-ttu-id="c8837-228">Quando si abilita questa anteprima, Office 365 non supporta più le vecchie classificazioni per i nuovi gruppi e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8837-228">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="c8837-229">Tuttavia, i gruppi e i siti esistenti continuano a visualizzare le vecchie classificazioni, a meno che non vengano convertite all'uso delle etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c8837-229">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="c8837-230">Le vecchie classificazioni includono la classificazione dei siti "moderni" configurata, probabilmente tramite Azure AD PowerShell o la libreria principale di PnP, che definiscono i valori per l'impostazione `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="c8837-230">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="c8837-231">Ad esempio, in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c8837-231">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="c8837-232">Per altre informazioni sul metodo di classificazione precedente, vedere [Classificazione dei siti "moderni" di SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="c8837-232">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="c8837-233">Per passare dalle vecchie classificazioni alle etichette di riservatezza, eseguire una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="c8837-233">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="c8837-234">Usare etichette esistenti: specificare le impostazioni di etichetta desiderate per i siti e i gruppi modificando etichette di riservatezza esistenti e già pubblicate.</span><span class="sxs-lookup"><span data-stu-id="c8837-234">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="c8837-235">Creare nuove etichette: specificare le impostazioni di etichetta desiderate per i siti e i gruppi creando e pubblicando nuove etichette di riservatezza che abbiano nomi identici alle classificazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="c8837-235">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="c8837-236">In seguito:</span><span class="sxs-lookup"><span data-stu-id="c8837-236">Then:</span></span> 

1. <span data-ttu-id="c8837-237">Usare PowerShell per applicare le etichette di riservatezza ai gruppi di Office 365 e ai siti di SharePoint esistenti utilizzando il mapping del nome.</span><span class="sxs-lookup"><span data-stu-id="c8837-237">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="c8837-238">Per istruzioni, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="c8837-238">See the next section for instructions.</span></span>

2. <span data-ttu-id="c8837-239">Rimuovere le vecchie classificazioni dai gruppi e siti esistenti.</span><span class="sxs-lookup"><span data-stu-id="c8837-239">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="c8837-240">Nonostante non si possa impedire agli utenti di creare nuovi gruppi in app e servizi che non supportano ancora le etichette di riservatezza, è tuttavia possibile eseguire uno script di PowerShell ricorrente per cercare nuovi gruppi che gli utenti abbiano creato con le vecchie classificazioni, per poi convertirli all'uso delle etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c8837-240">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="c8837-241">Usare PowerShell per convertire le classificazioni per i gruppi di Office 365 in etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8837-241">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="c8837-242">Verificare che sia in uso la versione di SharePoint Online Management Shell 16.0.19418.12000 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c8837-242">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="c8837-243">Se la versione più recente è già installata, andare direttamente al passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="c8837-243">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="c8837-244">Se è stata installata una versione precedente di SharePoint Online Management Shell da PowerShell Gallery, è possibile aggiornare il modulo eseguendo il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="c8837-244">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="c8837-245">Se è stata installata una versione precedente di SharePoint Online Management Shell dall'Area download Microsoft, passare a **Installazione applicazioni** e disinstallare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8837-245">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="c8837-246">In seguito, installare la versione più recente di SharePoint Online Management Shell dall'[Area download Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="c8837-246">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="c8837-247">Usando un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale o amministratore di SharePoint in Office 365, connettersi a SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8837-247">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="c8837-248">Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="c8837-248">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="c8837-249">Eseguire i comandi seguenti per ottenere l'elenco delle etichette di riservatezza e dei GUID corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c8837-249">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="c8837-250">Prendere nota dei GUID per le etichette di riservatezza che si desidera applicare ai gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c8837-250">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="c8837-251">Usare il comando seguente come un esempio per visualizzare l'elenco dei gruppi al momento classificati come "Generale":</span><span class="sxs-lookup"><span data-stu-id="c8837-251">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="c8837-252">Per ogni gruppo, aggiungere il GUID della nuova etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c8837-252">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="c8837-253">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c8837-253">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="c8837-254">Controllo delle attività sulle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8837-254">Auditing sensitivity label activities</span></span>

<span data-ttu-id="c8837-255">Se qualcuno carica un documento in un sito protetto con un'etichetta di riservatezza e il documento ha un'etichetta di riservatezza con [priorità più elevata](sensitivity-labels.md#label-priority-order-matters) rispetto all'etichetta di riservatezza applicata al sito, l'azione non verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="c8837-255">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="c8837-256">Ad esempio, si supponga sia stata applicata l'etichetta **Generale** a un sito di SharePoint e che qualcuno carichi su tale sito un documento con etichetta **Riservato**.</span><span class="sxs-lookup"><span data-stu-id="c8837-256">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="c8837-257">Dato che un'etichetta di riservatezza con una priorità più elevata identifica un contenuto maggiormente riservato di quello contrassegnato con un ordine di priorità inferiore, la situazione potrebbe porre un problema di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c8837-257">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="c8837-258">L'azione non viene bloccata, ma soggetta a controllo, in modo da identificare quali documenti abbiano questo disallineamento di priorità dell'etichetta e, se necessario, intervenire.</span><span class="sxs-lookup"><span data-stu-id="c8837-258">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="c8837-259">Ad esempio, è possibile spostare o eliminare dal sito il documento caricato.</span><span class="sxs-lookup"><span data-stu-id="c8837-259">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="c8837-260">Non costituirebbe alcun problema di sicurezza se il documento recasse un'etichetta di riservatezza con priorità inferiore rispetto a quella applicata al sito.</span><span class="sxs-lookup"><span data-stu-id="c8837-260">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="c8837-261">Ad esempio, un documento con etichetta **Generale** viene caricato in un sito con etichetta **Riservato**.</span><span class="sxs-lookup"><span data-stu-id="c8837-261">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="c8837-262">In questo scenario, non viene generato alcun evento di controllo.</span><span class="sxs-lookup"><span data-stu-id="c8837-262">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="c8837-263">Per eseguire una ricerca di tale evento nel log di controllo, cercare **Mancata corrispondenza della riservatezza del documento** nella categoria **Attività su file e pagine**.</span><span class="sxs-lookup"><span data-stu-id="c8837-263">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="c8837-264">Vengono controllate anche le attività di aggiunta o rimozione di un'etichetta di riservatezza da un sito o gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8837-264">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="c8837-265">Questi eventi sono disponibili nella categoria [Attività sulle etichetta di riservatezza](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities).</span><span class="sxs-lookup"><span data-stu-id="c8837-265">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="c8837-266">Per istruzioni sulla ricerca nel log di controllo, vedere [Eseguire ricerche nel log di controllo nel Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="c8837-266">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="c8837-267">Risolvere i problemi di distribuzione delle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8837-267">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="c8837-268">Problemi con le etichette di riservatezza per Microsoft Teams, gruppi di Office 365 e siti di SharePoint?</span><span class="sxs-lookup"><span data-stu-id="c8837-268">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="c8837-269">Verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c8837-269">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="c8837-270">Etichette non visibili dopo la pubblicazione</span><span class="sxs-lookup"><span data-stu-id="c8837-270">Labels not visible after publishing</span></span>
<span data-ttu-id="c8837-271">Se si verificano problemi durante la creazione di un sito o un gruppo di Office 365 dopo aver abilitato queste impostazioni o aver modificato il nome o la descrizione comando di un'etichetta di riservatezza, attendere alcune ore e quindi provare di nuovo a creare il team o il gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8837-271">If you experience issues when you create a site or Office 365 group after you enable these settings or modify a sensitivity label's name or tooltip, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="c8837-272">Per informazioni, vedere [Pianificare l'implementazione dopo aver creato o modificato un'etichetta di riservatezza](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="c8837-272">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="c8837-273">Se non è ancora possibile vedere la nuova etichetta di riservatezza da SharePoint Online, contattare il [Supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="c8837-273">If you still can't see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="c8837-274">Errori nella creazione di team, gruppi o siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8837-274">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="c8837-275">Se si verificano errori di creazione durante l'anteprima pubblica, è possibile disattivare le etichette di riservatezza per Microsoft Teams, gruppi di Office 365 e siti di SharePoint seguendo le stesse istruzioni per [Abilitare il supporto per le etichette di riservatezza](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8837-275">If you experience creation errors during the public preview, you can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="c8837-276">Tuttavia, per disabilitare l'anteprima, disabilitare la funzionalità usando `$setting["EnableMIPLabels"] = "False"` al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="c8837-276">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8837-277">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c8837-277">Additional resources</span></span>

<span data-ttu-id="c8837-278">Per informazioni su come [usare le etichette di riservatezza con Microsoft Teams, Gruppi di Office 365 e i siti di SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380), consultare la registrazione del webinar e le risposte alle domande.</span><span class="sxs-lookup"><span data-stu-id="c8837-278">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

