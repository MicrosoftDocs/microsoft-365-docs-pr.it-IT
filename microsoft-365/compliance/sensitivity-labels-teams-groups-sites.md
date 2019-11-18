---
title: Utilizzare le etichette di riservatezza con Microsoft teams, i gruppi di Office 365 e i siti di SharePoint (anteprima pubblica)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: È possibile applicare etichette a Microsoft teams, gruppi di Office 365 e siti di SharePoint.
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686529"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="349bf-103">Utilizzare le etichette di riservatezza con Microsoft teams, i gruppi di Office 365 e i siti di SharePoint (anteprima pubblica)</span><span class="sxs-lookup"><span data-stu-id="349bf-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="349bf-104">Quando si creano etichette di riservatezza nel [centro conformità di microsoft 365](https://protection.office.com/), è possibile applicarle a Microsoft teams, gruppi di Office 365 e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="349bf-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="349bf-105">È possibile associare i criteri alle etichette da controllare:</span><span class="sxs-lookup"><span data-stu-id="349bf-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="349bf-106">Impostazioni pubbliche/private</span><span class="sxs-lookup"><span data-stu-id="349bf-106">Public/private settings</span></span>
- <span data-ttu-id="349bf-107">Accesso guest</span><span class="sxs-lookup"><span data-stu-id="349bf-107">Guest access</span></span>
- <span data-ttu-id="349bf-108">Accesso da dispositivi non gestiti</span><span class="sxs-lookup"><span data-stu-id="349bf-108">Access from unmanaged devices</span></span>

<span data-ttu-id="349bf-109">Quando si applica un'etichetta a un team o a un gruppo, l'etichetta viene applicata automaticamente al sito del team di SharePoint connesso e all'altro.</span><span class="sxs-lookup"><span data-stu-id="349bf-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="349bf-110">A questo punto, è anche possibile abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="349bf-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="349bf-111">[Altre informazioni](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="349bf-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="349bf-112">Informazioni sull'anteprima pubblica per Microsoft teams, i gruppi di Office 365 e i siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="349bf-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="349bf-113">Le etichette di riservatezza per Microsoft teams, i gruppi di Office 365 e i siti di SharePoint vengono gradualmente distribuite ai tenant e potrebbero cambiare prima del rilascio finale.</span><span class="sxs-lookup"><span data-stu-id="349bf-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

## <a name="overview"></a><span data-ttu-id="349bf-114">Panoramica</span><span class="sxs-lookup"><span data-stu-id="349bf-114">Overview</span></span>

<span data-ttu-id="349bf-115">Quando si pubblicano le etichette di riservatezza, gli utenti di Office 365 hanno accesso allo stesso elenco di etichette.</span><span class="sxs-lookup"><span data-stu-id="349bf-115">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="349bf-116">Queste immagini mostrano:</span><span class="sxs-lookup"><span data-stu-id="349bf-116">These images show:</span></span>

- <span data-ttu-id="349bf-117">Come viene visualizzato l'elenco quando si crea un nuovo sito del team da SharePoint</span><span class="sxs-lookup"><span data-stu-id="349bf-117">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="349bf-118">Quando si visualizza l'elenco in Word</span><span class="sxs-lookup"><span data-stu-id="349bf-118">When you view the list in Word</span></span>

![Un'etichetta di riservatezza quando si crea un sito del team da SharePoint](media/sensitivity-label-new-team-site.png)

![Un'etichetta di riservatezza visualizzata nell'app desktop Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="349bf-121">Abilitazione di questa anteprima mediante Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="349bf-121">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="349bf-122">Accedere a Azure come amministratore globale utilizzando Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="349bf-122">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="349bf-123">Per istruzioni, vedere [accedere con Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="349bf-123">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="349bf-124">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="349bf-124">Run the following command:</span></span>

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

<span data-ttu-id="349bf-125">Quando si Abilita l'anteprima, Office 365 non utilizza più le vecchie classificazioni per i nuovi gruppi e i siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="349bf-125">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="349bf-126">Se è stata utilizzata la [classificazione del sito di Azure ad](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["classificazione"]), i gruppi e i siti esistenti continuano a visualizzare le vecchie classificazioni.</span><span class="sxs-lookup"><span data-stu-id="349bf-126">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="349bf-127">Per visualizzare le nuove classificazioni, convertirle.</span><span class="sxs-lookup"><span data-stu-id="349bf-127">To display the new classifications, convert them.</span></span> <span data-ttu-id="349bf-128">Per informazioni su come convertirli, vedere [se è stata utilizzata la classificazione del sito di Azure ad classico](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="349bf-128">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span>

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a><span data-ttu-id="349bf-129">Impostare le impostazioni del sito e del gruppo quando si creano etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="349bf-129">Set site and group settings when you create sensitivity labels</span></span>

<span data-ttu-id="349bf-130">Dopo aver abilitato l'anteprima, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="349bf-130">After you enable the preview, follow these steps:</span></span>

1. <span data-ttu-id="349bf-131">Nel centro conformità di Microsoft 365, selezionare **classificazione** > **etichette di riservatezza**.</span><span class="sxs-lookup"><span data-stu-id="349bf-131">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="349bf-132">Selezionare **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="349bf-132">Select **Create a label**.</span></span>

3. <span data-ttu-id="349bf-133">Selezionare le opzioni desiderate e quindi nella scheda **Impostazioni sito e gruppo** scegliere:</span><span class="sxs-lookup"><span data-stu-id="349bf-133">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="349bf-134">Privacy (pubblico/privato): privato significa che solo i membri approvati nell'organizzazione possono vedere cosa c'è all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="349bf-134">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="349bf-135">Chiunque altro nell'organizzazione non può vedere cosa c'è nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="349bf-135">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="349bf-136">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="349bf-136">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="349bf-137">Accesso Guest: è possibile controllare se gli utenti possono essere aggiunti a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="349bf-137">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="349bf-138">Informazioni sulla gestione dell'accesso guest nei gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="349bf-138">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="349bf-139">Dispositivi non gestiti: questa impostazione consente di bloccare o limitare l'accesso al contenuto di SharePoint da dispositivi che non sono ibridi AD Uniti o conformi a Intune.</span><span class="sxs-lookup"><span data-stu-id="349bf-139">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="349bf-140">Se si selezionano dispositivi non gestiti, è necessario passare a Azure AD per completare la configurazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="349bf-140">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="349bf-141">Per informazioni, vedere [controllare l'accesso da dispositivi non gestiti](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="349bf-141">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![Scheda Impostazioni sito e gruppo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="349bf-143">Solo le impostazioni del sito e del gruppo hanno effetto quando si applica un'etichetta a un team, a un gruppo o a un sito.</span><span class="sxs-lookup"><span data-stu-id="349bf-143">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="349bf-144">Altre impostazioni, ad esempio la crittografia e la marcatura del contenuto, non vengono applicate a tutto il contenuto all'interno del team, del gruppo o del sito.</span><span class="sxs-lookup"><span data-stu-id="349bf-144">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="349bf-145">Analogamente, se si crea un'etichetta e non si attivano le impostazioni del sito e del gruppo, l'etichetta sarà ancora disponibile quando gli utenti creano team, gruppi e siti, ma non eseguiranno alcuna operazione quando gli utenti lo applicano.</span><span class="sxs-lookup"><span data-stu-id="349bf-145">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="349bf-146">Informazioni su come pubblicare un'etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="349bf-146">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="349bf-147">Applicazione di un'etichetta di riservatezza a un nuovo team</span><span class="sxs-lookup"><span data-stu-id="349bf-147">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="349bf-148">Gli utenti possono selezionare le etichette di riservatezza quando creano nuovi team in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="349bf-148">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="349bf-149">Quando si seleziona il livello di riservatezza, l'impostazione della privacy cambia in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="349bf-149">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="349bf-150">A seconda dell'impostazione di accesso Guest selezionata per l'etichetta, gli utenti possono o non possono aggiungere persone all'esterno dell'organizzazione al team.</span><span class="sxs-lookup"><span data-stu-id="349bf-150">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![Impostazione della privacy quando si crea un nuovo team](media/privacy-setting-new-team.png)

<span data-ttu-id="349bf-152">Dopo aver creato il team, l'etichetta di riservatezza viene visualizzata nell'angolo in alto a destra di tutti i canali.</span><span class="sxs-lookup"><span data-stu-id="349bf-152">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![L'etichetta di riservatezza viene visualizzata nel team](media/privacy-setting-teams.png)

<span data-ttu-id="349bf-154">Il servizio applica automaticamente la stessa etichetta di riservatezza al gruppo di Office 365 e al sito del team di SharePoint connesso.</span><span class="sxs-lookup"><span data-stu-id="349bf-154">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="349bf-155">Applicazione di un'etichetta di riservatezza a un nuovo gruppo</span><span class="sxs-lookup"><span data-stu-id="349bf-155">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="349bf-156">In Outlook sul Web, la nuova casella di **sensibilità** contiene le etichette pubblicate.</span><span class="sxs-lookup"><span data-stu-id="349bf-156">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="349bf-157">Se gli utenti desiderano altre informazioni, possono fare clic sull'icona della Guida per leggere i dettagli sulle etichette disponibili e sui criteri associati.</span><span class="sxs-lookup"><span data-stu-id="349bf-157">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Creazione di un gruppo e selezione di un'opzione in Sensitivity](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="349bf-159">Applicazione di un'etichetta di riservatezza a un nuovo sito</span><span class="sxs-lookup"><span data-stu-id="349bf-159">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="349bf-160">Gli amministratori e gli utenti finali possono selezionare le etichette di riservatezza quando creano siti del team e siti di comunicazione moderni.</span><span class="sxs-lookup"><span data-stu-id="349bf-160">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="349bf-161">Informazioni su come creare un sito nella nuova interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="349bf-161">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="349bf-162">Quando gli utenti creano siti di comunicazione e team moderni, per impostazione predefinita è già selezionata un'etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="349bf-162">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="349bf-163">Gli utenti possono selezionare l'icona della Guida per ottenere ulteriori informazioni sulle etichette.</span><span class="sxs-lookup"><span data-stu-id="349bf-163">Users can select the help icon to learn more about the labels.</span></span>

![Creazione di un sito e selezione di un'opzione in Sensitivity](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="349bf-165">Quando gli utenti accedono al sito, possono visualizzare il nome dell'etichetta e i criteri applicati.</span><span class="sxs-lookup"><span data-stu-id="349bf-165">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Un sito a cui è applicata un'etichetta di riservatezza](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="349bf-167">Gestire le etichette di riservatezza nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="349bf-167">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="349bf-168">Per visualizzare e modificare le etichette, utilizzare la pagina siti attivi nella nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="349bf-168">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Colonna Sensitivity nella pagina siti attivi](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="349bf-170">[Per ulteriori informazioni, vedere Managing sites in the New SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="349bf-170">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="349bf-171">Modificare le impostazioni del gruppo e del sito per un'etichetta</span><span class="sxs-lookup"><span data-stu-id="349bf-171">Change site and group settings for a label</span></span>

<span data-ttu-id="349bf-172">Come procedura consigliata, non modificare le impostazioni dopo aver applicato un'etichetta a più team, gruppi o siti.</span><span class="sxs-lookup"><span data-stu-id="349bf-172">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="349bf-173">Se è necessario apportare una modifica, è necessario utilizzare uno script di Azure AD PowerShell per applicare manualmente gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="349bf-173">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="349bf-174">Questo metodo garantisce che tutti i team, i siti e i gruppi esistenti applichino la nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="349bf-174">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="349bf-175">Supporto per le nuove etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="349bf-175">Support for the new sensitivity labels</span></span>

<span data-ttu-id="349bf-176">Le app e i servizi seguenti supportano le etichette di riservatezza in questa anteprima:</span><span class="sxs-lookup"><span data-stu-id="349bf-176">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="349bf-177">Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="349bf-177">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="349bf-178">SharePoint</span><span class="sxs-lookup"><span data-stu-id="349bf-178">SharePoint</span></span>
- <span data-ttu-id="349bf-179">Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="349bf-179">Outlook on the web</span></span>
- <span data-ttu-id="349bf-180">Teams</span><span class="sxs-lookup"><span data-stu-id="349bf-180">Teams</span></span>
- <span data-ttu-id="349bf-181">Interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="349bf-181">SharePoint admin center</span></span>
- <span data-ttu-id="349bf-182">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="349bf-182">Azure AD admin center</span></span>

<span data-ttu-id="349bf-183">Non è possibile utilizzare le app e i servizi seguenti per creare gruppi di Office 365 con le nuove etichette di riservatezza:</span><span class="sxs-lookup"><span data-stu-id="349bf-183">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="349bf-184">Outlook per Mac</span><span class="sxs-lookup"><span data-stu-id="349bf-184">Outlook for the Mac</span></span>
- <span data-ttu-id="349bf-185">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="349bf-185">Outlook mobile</span></span>  
- <span data-ttu-id="349bf-186">Desktop di Outlook per Windows</span><span class="sxs-lookup"><span data-stu-id="349bf-186">Outlook desktop for Windows</span></span>
- <span data-ttu-id="349bf-187">Forms</span><span class="sxs-lookup"><span data-stu-id="349bf-187">Forms</span></span>  
- <span data-ttu-id="349bf-188">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="349bf-188">Dynamics 365</span></span>  
- <span data-ttu-id="349bf-189">Yammer</span><span class="sxs-lookup"><span data-stu-id="349bf-189">Yammer</span></span>  
- <span data-ttu-id="349bf-190">Stream</span><span class="sxs-lookup"><span data-stu-id="349bf-190">Stream</span></span>  
- <span data-ttu-id="349bf-191">Planner</span><span class="sxs-lookup"><span data-stu-id="349bf-191">Planner</span></span>  
- <span data-ttu-id="349bf-192">Project</span><span class="sxs-lookup"><span data-stu-id="349bf-192">Project</span></span>  
- <span data-ttu-id="349bf-193">PowerBI</span><span class="sxs-lookup"><span data-stu-id="349bf-193">PowerBI</span></span>  
- <span data-ttu-id="349bf-194">Interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="349bf-194">Teams admin center</span></span>  
- <span data-ttu-id="349bf-195">Interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="349bf-195">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="349bf-196">Interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="349bf-196">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="349bf-197">Se è stata utilizzata la classificazione del sito di Azure AD classico</span><span class="sxs-lookup"><span data-stu-id="349bf-197">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="349bf-198">Quando si Abilita l'anteprima, Office 365 non supporta più la classificazione obsoleta per i nuovi gruppi e i siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="349bf-198">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="349bf-199">Tuttavia, i gruppi e i siti esistenti continuano a visualizzare le vecchie classificazioni, a meno che non vengano convertite.</span><span class="sxs-lookup"><span data-stu-id="349bf-199">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="349bf-200">Le classi precedenti includono la classificazione dei siti "moderna" configurata, possibilmente tramite Azure AD PowerShell o la libreria di base PnP, che definisce `ClassificationList` i valori per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="349bf-200">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="349bf-201">Ad esempio, in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="349bf-201">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="349bf-202">Per ulteriori informazioni sul vecchio metodo di classificazione, vedere [classificazione dei siti di SharePoint "moderna"](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="349bf-202">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="349bf-203">In base alla distribuzione corrente, sono disponibili due opzioni per convertire le classificazioni obsolete nelle nuove classificazioni.</span><span class="sxs-lookup"><span data-stu-id="349bf-203">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="349bf-204">Se non sono mai state utilizzate etichette di riservatezza (etichette di Microsoft Information Protection unificate) per file e messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="349bf-204">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="349bf-205">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="349bf-205">We recommend that you:</span></span>

1. <span data-ttu-id="349bf-206">Creare nuove etichette di riservatezza nel centro conformità di Microsoft 365 con gli stessi nomi delle classificazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="349bf-206">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="349bf-207">Utilizzare PowerShell per applicare le nuove etichette ai gruppi di Office 365 e ai siti di SharePoint esistenti utilizzando il mapping dei nomi.</span><span class="sxs-lookup"><span data-stu-id="349bf-207">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="349bf-208">Eliminare le classificazioni obsolete.</span><span class="sxs-lookup"><span data-stu-id="349bf-208">Delete the old classifications.</span></span>

<span data-ttu-id="349bf-209">Le app e i servizi che supportano le nuove etichette di riservatezza verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="349bf-209">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="349bf-210">È possibile creare nuovi team, gruppi e siti con le nuove etichette.</span><span class="sxs-lookup"><span data-stu-id="349bf-210">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="349bf-211">Gli utenti possono comunque creare gruppi da app e servizi che non supportano le nuove etichette.</span><span class="sxs-lookup"><span data-stu-id="349bf-211">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="349bf-212">Tuttavia, gli utenti non possono applicare un'etichetta a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="349bf-212">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="349bf-213">Utilizzare PowerShell per applicare le nuove etichette di riservatezza a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="349bf-213">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="349bf-214">È possibile mantenere le classificazioni obsolete; Tuttavia, è consigliabile utilizzare PowerShell per applicare le nuove etichette di riservatezza a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="349bf-214">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="349bf-215">Le app e i servizi che supportano le nuove etichette di riservatezza vengono creati con le nuove etichette.</span><span class="sxs-lookup"><span data-stu-id="349bf-215">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="349bf-216">Quando gli utenti creano gruppi da app e servizi che non supportano le nuove etichette, possono selezionare una classificazione.</span><span class="sxs-lookup"><span data-stu-id="349bf-216">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="349bf-217">Se si utilizzano le etichette di riservatezza (etichette Microsoft per la protezione delle informazioni unificate) per file e messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="349bf-217">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="349bf-218">Non appena si abilita questa anteprima, passare a ciascuna etichetta nel centro conformità di Microsoft 365 e applicare i criteri desiderati per i siti e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="349bf-218">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="349bf-219">Gli utenti inizieranno a visualizzare le etichette esistenti per i siti e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="349bf-219">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="349bf-220">Preparare la shell di gestione di SharePoint Online prima di rietichettare i gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="349bf-220">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="349bf-221">Prima di applicare nuove etichette, verificare che sia in esecuzione la versione più recente di SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="349bf-221">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="349bf-222">Se si ha già la versione più recente, è possibile procedere e [rietichettare i gruppi di Office 365 con nuove etichette di riservatezza](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="349bf-222">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="349bf-223">Per preparare SharePoint Online Management Shell per l'anteprima:</span><span class="sxs-lookup"><span data-stu-id="349bf-223">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="349bf-224">Se è stata installata una versione precedente di SharePoint Online Management Shell, andare a installazione **applicazioni** e disinstallare "SharePoint Online Management Shell".</span><span class="sxs-lookup"><span data-stu-id="349bf-224">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="349bf-225">In un Web browser passare alla pagina Centro download e [scaricare la versione più recente di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="349bf-225">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="349bf-226">Selezionare la lingua e quindi fare clic su **download**.</span><span class="sxs-lookup"><span data-stu-id="349bf-226">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="349bf-227">Scegliere tra il file x64 e x86. msi.</span><span class="sxs-lookup"><span data-stu-id="349bf-227">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="349bf-228">Scaricare il file x64 se si esegue la versione di Windows a 64 bit o il file x86 se si esegue la versione a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="349bf-228">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="349bf-229">Se non si conosce, vedere [la versione del sistema operativo Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="349bf-229">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="349bf-230">Dopo aver scaricato il file, eseguire il file e seguire i passaggi illustrati nell'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="349bf-230">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="349bf-231">Relabel Office 365 gruppi con nuove etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="349bf-231">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="349bf-232">Assicurarsi di utilizzare la versione più recente di SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="349bf-232">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="349bf-233">Per istruzioni, vedere [preparare la shell di gestione di SharePoint Online prima di rietichettare i gruppi di Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="349bf-233">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="349bf-234">Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Office 365, connettersi a SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="349bf-234">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="349bf-235">Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="349bf-235">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="349bf-236">Eseguire il seguente comando per ottenere l'elenco delle etichette di riservatezza e dei relativi GUID.</span><span class="sxs-lookup"><span data-stu-id="349bf-236">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="349bf-237">Prendere nota del GUID per l'etichetta che si desidera sovrascrivere.</span><span class="sxs-lookup"><span data-stu-id="349bf-237">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="349bf-238">Ad esempio, l'etichetta "generale".</span><span class="sxs-lookup"><span data-stu-id="349bf-238">For example, the "General" label.</span></span>

5. <span data-ttu-id="349bf-239">Utilizzare il seguente comando per ottenere l'elenco dei gruppi che hanno la classificazione "generale".</span><span class="sxs-lookup"><span data-stu-id="349bf-239">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="349bf-240">Quando si esegue questo comando, è possibile connettersi a PowerShell di Exchange Online ed eseguire il cmdlet Get-UnifiedGroup.</span><span class="sxs-lookup"><span data-stu-id="349bf-240">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="349bf-241">Per ogni gruppo, aggiungere il nuovo GUID dell'etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="349bf-241">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
