---
title: Usare le etichette di riservatezza con Microsoft Teams, gruppi di Office 365 e siti di SharePoint (anteprima pubblica)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
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
ms.openlocfilehash: a6c187227703395ed5fe3d926dabe30e6203fca5
ms.sourcegitcommit: 909f18d6c497086899fa239b5b5e0bb91f1e7804
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819132"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="c8a26-103">Usare le etichette di riservatezza con Microsoft Teams, gruppi di Office 365 e siti di SharePoint (anteprima pubblica)</span><span class="sxs-lookup"><span data-stu-id="c8a26-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="c8a26-104">Quando si creano etichette di riservatezza nel [centro conformità di microsoft 365](https://protection.office.com/), è possibile applicarle a Microsoft teams, gruppi di Office 365 e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8a26-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="c8a26-105">È possibile associare i criteri alle etichette da controllare:</span><span class="sxs-lookup"><span data-stu-id="c8a26-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="c8a26-106">Impostazioni pubbliche/private</span><span class="sxs-lookup"><span data-stu-id="c8a26-106">Public/private settings</span></span>
- <span data-ttu-id="c8a26-107">Accesso guest</span><span class="sxs-lookup"><span data-stu-id="c8a26-107">Guest access</span></span>
- <span data-ttu-id="c8a26-108">Accesso da dispositivi non gestiti</span><span class="sxs-lookup"><span data-stu-id="c8a26-108">Access from unmanaged devices</span></span>

<span data-ttu-id="c8a26-109">Quando si applica un'etichetta a un team o a un gruppo, l'etichetta viene applicata automaticamente al sito del team di SharePoint connesso e all'altro.</span><span class="sxs-lookup"><span data-stu-id="c8a26-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="c8a26-110">A questo punto, è anche possibile abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c8a26-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="c8a26-111">[Altre informazioni](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="c8a26-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="c8a26-112">Informazioni sull'anteprima pubblica per Microsoft teams, i gruppi di Office 365 e i siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8a26-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="c8a26-113">Le etichette di riservatezza per Microsoft teams, i gruppi di Office 365 e i siti di SharePoint vengono gradualmente distribuite ai tenant e potrebbero cambiare prima del rilascio finale.</span><span class="sxs-lookup"><span data-stu-id="c8a26-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="c8a26-114">L'anteprima pubblica non funziona con le reti di distribuzione del contenuto di Office 365 (reti CDN).</span><span class="sxs-lookup"><span data-stu-id="c8a26-114">The public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="c8a26-115">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c8a26-115">Overview</span></span>

<span data-ttu-id="c8a26-116">Quando si pubblicano le etichette di riservatezza, gli utenti di Office 365 hanno accesso allo stesso elenco di etichette.</span><span class="sxs-lookup"><span data-stu-id="c8a26-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="c8a26-117">Queste immagini mostrano:</span><span class="sxs-lookup"><span data-stu-id="c8a26-117">These images show:</span></span>

- <span data-ttu-id="c8a26-118">Come viene visualizzato l'elenco quando si crea un nuovo sito del team da SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8a26-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="c8a26-119">Quando si visualizza l'elenco in Word</span><span class="sxs-lookup"><span data-stu-id="c8a26-119">When you view the list in Word</span></span>

![Un'etichetta di riservatezza quando si crea un sito del team da SharePoint](media/sensitivity-label-new-team-site.png)

![Un'etichetta di riservatezza visualizzata nell'app desktop Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="c8a26-122">Abilitazione di questa anteprima mediante Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8a26-122">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="c8a26-123">Accedere a Azure come amministratore globale utilizzando Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8a26-123">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="c8a26-124">Per istruzioni, vedere [accedere con Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="c8a26-124">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="c8a26-125">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c8a26-125">Run the following command:</span></span>

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

<span data-ttu-id="c8a26-126">Quando si Abilita l'anteprima, Office 365 non utilizza più le vecchie classificazioni per i nuovi gruppi e i siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8a26-126">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="c8a26-127">Se è stata utilizzata la [classificazione del sito di Azure ad](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["classificazione"]), i gruppi e i siti esistenti continuano a visualizzare le vecchie classificazioni.</span><span class="sxs-lookup"><span data-stu-id="c8a26-127">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="c8a26-128">Per visualizzare le nuove classificazioni, convertirle.</span><span class="sxs-lookup"><span data-stu-id="c8a26-128">To display the new classifications, convert them.</span></span> <span data-ttu-id="c8a26-129">Per informazioni su come convertirli, vedere [se è stata utilizzata la classificazione del sito di Azure ad classico](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="c8a26-129">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="c8a26-130">Impostare le impostazioni del sito e del gruppo quando si creano o si modificano etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8a26-130">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="c8a26-131">Dopo aver abilitato l'anteprima, eseguire la procedura seguente per creare o modificare le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c8a26-131">After you enable the preview, follow these steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="c8a26-132">È necessario completare questa procedura per utilizzare le nuove etichette di riservatezza con i siti e i gruppi, anche se sono già state definite etichette.</span><span class="sxs-lookup"><span data-stu-id="c8a26-132">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="c8a26-133">Le modifiche apportate a queste impostazioni possono richiedere fino a 24 ore di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8a26-133">Changes to these settings may take up to 24 hours sync.</span></span>

1. <span data-ttu-id="c8a26-134">Nel centro conformità di Microsoft 365, selezionare **classificazione** > **etichette di riservatezza**.</span><span class="sxs-lookup"><span data-stu-id="c8a26-134">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="c8a26-135">Selezionare **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="c8a26-135">Select **Create a label**.</span></span> <span data-ttu-id="c8a26-136">Se si dispone già di un'etichetta, passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="c8a26-136">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="c8a26-137">Selezionare le opzioni desiderate e quindi nella scheda **Impostazioni sito e gruppo** scegliere:</span><span class="sxs-lookup"><span data-stu-id="c8a26-137">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="c8a26-138">Privacy (pubblico/privato): privato significa che solo i membri approvati nell'organizzazione possono vedere cosa c'è all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8a26-138">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="c8a26-139">Chiunque altro nell'organizzazione non può vedere cosa c'è nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8a26-139">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="c8a26-140">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c8a26-140">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="c8a26-141">Accesso Guest: è possibile controllare se gli utenti possono essere aggiunti a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8a26-141">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="c8a26-142">Informazioni sulla gestione dell'accesso guest nei gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="c8a26-142">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="c8a26-143">Dispositivi non gestiti: questa impostazione consente di bloccare o limitare l'accesso al contenuto di SharePoint da dispositivi che non sono ibridi AD Uniti o conformi a Intune.</span><span class="sxs-lookup"><span data-stu-id="c8a26-143">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="c8a26-144">Se si selezionano dispositivi non gestiti, è necessario passare a Azure AD per completare la configurazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="c8a26-144">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="c8a26-145">Per informazioni, vedere [controllare l'accesso da dispositivi non gestiti](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="c8a26-145">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![Scheda Impostazioni sito e gruppo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="c8a26-147">Solo le impostazioni del sito e del gruppo hanno effetto quando si applica un'etichetta a un team, a un gruppo o a un sito.</span><span class="sxs-lookup"><span data-stu-id="c8a26-147">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="c8a26-148">Altre impostazioni, ad esempio la crittografia e la marcatura del contenuto, non vengono applicate a tutto il contenuto all'interno del team, del gruppo o del sito.</span><span class="sxs-lookup"><span data-stu-id="c8a26-148">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="c8a26-149">Analogamente, se si crea un'etichetta e non si attivano le impostazioni del sito e del gruppo, l'etichetta sarà ancora disponibile quando gli utenti creano team, gruppi e siti, ma non eseguiranno alcuna operazione quando gli utenti lo applicano.</span><span class="sxs-lookup"><span data-stu-id="c8a26-149">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="c8a26-150">Informazioni su come pubblicare un'etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8a26-150">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="c8a26-151">Risoluzione dei problemi relativi alla distribuzione di etichette sensibili</span><span class="sxs-lookup"><span data-stu-id="c8a26-151">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="c8a26-152">Se si verificano problemi durante la creazione di un gruppo di team o di Office 365 dopo aver abilitato queste impostazioni o apportato una modifica alla descrizione di un'etichetta, salvare l'etichetta, attendere qualche ora e quindi provare a creare di nuovo il gruppo team o Office 365.</span><span class="sxs-lookup"><span data-stu-id="c8a26-152">IF you experience issues when you create a Teams or Office 365 group after you enable these settings or make a change to a Label's description, save the Label, wait a few hours, and then try to create the Team or Office 365 group again.</span></span>

<span data-ttu-id="c8a26-153">Se non si è ancora in grado di visualizzare la nuova etichetta di riservatezza da SharePoint Online, contattare immediatamente il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8a26-153">If you are still not able to see the new sensitivity label from SharePoint Online then contact Microsoft Support immediately.</span></span>

[<span data-ttu-id="c8a26-154">Informazioni su come pubblicare un'etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8a26-154">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="c8a26-155">Applicazione di un'etichetta di riservatezza a un nuovo team</span><span class="sxs-lookup"><span data-stu-id="c8a26-155">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="c8a26-156">Gli utenti possono selezionare le etichette di riservatezza quando creano nuovi team in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c8a26-156">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="c8a26-157">Quando si seleziona il livello di riservatezza, l'impostazione della privacy cambia in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c8a26-157">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="c8a26-158">A seconda dell'impostazione di accesso Guest selezionata per l'etichetta, gli utenti possono o non possono aggiungere persone all'esterno dell'organizzazione al team.</span><span class="sxs-lookup"><span data-stu-id="c8a26-158">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![Impostazione della privacy quando si crea un nuovo team](media/privacy-setting-new-team.png)

<span data-ttu-id="c8a26-160">Dopo aver creato il team, l'etichetta di riservatezza viene visualizzata nell'angolo in alto a destra di tutti i canali.</span><span class="sxs-lookup"><span data-stu-id="c8a26-160">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![L'etichetta di riservatezza viene visualizzata nel team](media/privacy-setting-teams.png)

<span data-ttu-id="c8a26-162">Il servizio applica automaticamente la stessa etichetta di riservatezza al gruppo di Office 365 e al sito del team di SharePoint connesso.</span><span class="sxs-lookup"><span data-stu-id="c8a26-162">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="c8a26-163">Applicazione di un'etichetta di riservatezza a un nuovo gruppo</span><span class="sxs-lookup"><span data-stu-id="c8a26-163">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="c8a26-164">In Outlook sul Web, la nuova casella di **sensibilità** contiene le etichette pubblicate.</span><span class="sxs-lookup"><span data-stu-id="c8a26-164">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="c8a26-165">Se gli utenti desiderano altre informazioni, possono fare clic sull'icona della Guida per leggere i dettagli sulle etichette disponibili e sui criteri associati.</span><span class="sxs-lookup"><span data-stu-id="c8a26-165">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Creazione di un gruppo e selezione di un'opzione in Sensitivity](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="c8a26-167">Applicazione di un'etichetta di riservatezza a un nuovo sito</span><span class="sxs-lookup"><span data-stu-id="c8a26-167">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="c8a26-168">Gli amministratori e gli utenti finali possono selezionare le etichette di riservatezza quando creano siti del team e siti di comunicazione moderni.</span><span class="sxs-lookup"><span data-stu-id="c8a26-168">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="c8a26-169">Informazioni su come creare un sito nella nuova interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8a26-169">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="c8a26-170">Quando gli utenti creano siti di comunicazione e team moderni, per impostazione predefinita è già selezionata un'etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c8a26-170">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="c8a26-171">Gli utenti possono selezionare l'icona della Guida per ottenere ulteriori informazioni sulle etichette.</span><span class="sxs-lookup"><span data-stu-id="c8a26-171">Users can select the help icon to learn more about the labels.</span></span>

![Creazione di un sito e selezione di un'opzione in Sensitivity](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="c8a26-173">Quando gli utenti accedono al sito, possono visualizzare il nome dell'etichetta e i criteri applicati.</span><span class="sxs-lookup"><span data-stu-id="c8a26-173">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Un sito a cui è applicata un'etichetta di riservatezza](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="c8a26-175">Gestire le etichette di riservatezza nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8a26-175">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="c8a26-176">Per visualizzare e modificare le etichette, utilizzare la pagina siti attivi nella nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8a26-176">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Colonna Sensitivity nella pagina siti attivi](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="c8a26-178">[Per ulteriori informazioni, vedere Managing sites in the New SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c8a26-178">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="c8a26-179">Modificare le impostazioni del gruppo e del sito per un'etichetta</span><span class="sxs-lookup"><span data-stu-id="c8a26-179">Change site and group settings for a label</span></span>

<span data-ttu-id="c8a26-180">Come procedura consigliata, non modificare le impostazioni dopo aver applicato un'etichetta a più team, gruppi o siti.</span><span class="sxs-lookup"><span data-stu-id="c8a26-180">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="c8a26-181">Se è necessario apportare una modifica, è necessario utilizzare uno script di Azure AD PowerShell per applicare manualmente gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c8a26-181">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="c8a26-182">Questo metodo garantisce che tutti i team, i siti e i gruppi esistenti applichino la nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="c8a26-182">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="c8a26-183">Supporto per le nuove etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8a26-183">Support for the new sensitivity labels</span></span>

<span data-ttu-id="c8a26-184">Le app e i servizi seguenti supportano le etichette di riservatezza in questa anteprima:</span><span class="sxs-lookup"><span data-stu-id="c8a26-184">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="c8a26-185">Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8a26-185">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="c8a26-186">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8a26-186">SharePoint</span></span>
- <span data-ttu-id="c8a26-187">Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="c8a26-187">Outlook on the web</span></span>
- <span data-ttu-id="c8a26-188">Teams</span><span class="sxs-lookup"><span data-stu-id="c8a26-188">Teams</span></span>
- <span data-ttu-id="c8a26-189">Interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8a26-189">SharePoint admin center</span></span>
- <span data-ttu-id="c8a26-190">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="c8a26-190">Azure AD admin center</span></span>

<span data-ttu-id="c8a26-191">Non è possibile utilizzare le app e i servizi seguenti per creare gruppi di Office 365 con le nuove etichette di riservatezza:</span><span class="sxs-lookup"><span data-stu-id="c8a26-191">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="c8a26-192">Outlook per Mac</span><span class="sxs-lookup"><span data-stu-id="c8a26-192">Outlook for the Mac</span></span>
- <span data-ttu-id="c8a26-193">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="c8a26-193">Outlook mobile</span></span>  
- <span data-ttu-id="c8a26-194">Desktop di Outlook per Windows</span><span class="sxs-lookup"><span data-stu-id="c8a26-194">Outlook desktop for Windows</span></span>
- <span data-ttu-id="c8a26-195">Forms</span><span class="sxs-lookup"><span data-stu-id="c8a26-195">Forms</span></span>  
- <span data-ttu-id="c8a26-196">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c8a26-196">Dynamics 365</span></span>  
- <span data-ttu-id="c8a26-197">Yammer</span><span class="sxs-lookup"><span data-stu-id="c8a26-197">Yammer</span></span>  
- <span data-ttu-id="c8a26-198">Stream</span><span class="sxs-lookup"><span data-stu-id="c8a26-198">Stream</span></span>  
- <span data-ttu-id="c8a26-199">Planner</span><span class="sxs-lookup"><span data-stu-id="c8a26-199">Planner</span></span>  
- <span data-ttu-id="c8a26-200">Project</span><span class="sxs-lookup"><span data-stu-id="c8a26-200">Project</span></span>  
- <span data-ttu-id="c8a26-201">PowerBI</span><span class="sxs-lookup"><span data-stu-id="c8a26-201">PowerBI</span></span>  
- <span data-ttu-id="c8a26-202">Interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="c8a26-202">Teams admin center</span></span>  
- <span data-ttu-id="c8a26-203">Interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8a26-203">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="c8a26-204">Interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="c8a26-204">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="c8a26-205">Se è stata utilizzata la classificazione del sito di Azure AD classico</span><span class="sxs-lookup"><span data-stu-id="c8a26-205">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="c8a26-206">Quando si Abilita l'anteprima, Office 365 non supporta più la classificazione obsoleta per i nuovi gruppi e i siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8a26-206">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="c8a26-207">Tuttavia, i gruppi e i siti esistenti continuano a visualizzare le vecchie classificazioni, a meno che non vengano convertite.</span><span class="sxs-lookup"><span data-stu-id="c8a26-207">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="c8a26-208">Le classi precedenti includono la classificazione dei siti "moderna" configurata, possibilmente tramite Azure AD PowerShell o la libreria di base PnP, che definisce `ClassificationList` i valori per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="c8a26-208">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="c8a26-209">Ad esempio, in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c8a26-209">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="c8a26-210">Per ulteriori informazioni sul vecchio metodo di classificazione, vedere [classificazione dei siti di SharePoint "moderna"](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="c8a26-210">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="c8a26-211">In base alla distribuzione corrente, sono disponibili due opzioni per convertire le classificazioni obsolete nelle nuove classificazioni.</span><span class="sxs-lookup"><span data-stu-id="c8a26-211">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="c8a26-212">Se non sono mai state utilizzate etichette di riservatezza (etichette di Microsoft Information Protection unificate) per file e messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c8a26-212">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="c8a26-213">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="c8a26-213">We recommend that you:</span></span>

1. <span data-ttu-id="c8a26-214">Creare nuove etichette di riservatezza nel centro conformità di Microsoft 365 con gli stessi nomi delle classificazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="c8a26-214">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="c8a26-215">Utilizzare PowerShell per applicare le nuove etichette ai gruppi di Office 365 e ai siti di SharePoint esistenti utilizzando il mapping dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c8a26-215">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="c8a26-216">Eliminare le classificazioni obsolete.</span><span class="sxs-lookup"><span data-stu-id="c8a26-216">Delete the old classifications.</span></span>

<span data-ttu-id="c8a26-217">Le app e i servizi che supportano le nuove etichette di riservatezza verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="c8a26-217">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="c8a26-218">È possibile creare nuovi team, gruppi e siti con le nuove etichette.</span><span class="sxs-lookup"><span data-stu-id="c8a26-218">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="c8a26-219">Gli utenti possono comunque creare gruppi da app e servizi che non supportano le nuove etichette.</span><span class="sxs-lookup"><span data-stu-id="c8a26-219">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="c8a26-220">Tuttavia, gli utenti non possono applicare un'etichetta a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8a26-220">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="c8a26-221">Utilizzare PowerShell per applicare le nuove etichette di riservatezza a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8a26-221">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="c8a26-222">È possibile mantenere le classificazioni obsolete; Tuttavia, è consigliabile utilizzare PowerShell per applicare le nuove etichette di riservatezza a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8a26-222">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="c8a26-223">Le app e i servizi che supportano le nuove etichette di riservatezza vengono creati con le nuove etichette.</span><span class="sxs-lookup"><span data-stu-id="c8a26-223">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="c8a26-224">Quando gli utenti creano gruppi da app e servizi che non supportano le nuove etichette, possono selezionare una classificazione.</span><span class="sxs-lookup"><span data-stu-id="c8a26-224">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="c8a26-225">Se si utilizzano le etichette di riservatezza (etichette Microsoft per la protezione delle informazioni unificate) per file e messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c8a26-225">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="c8a26-226">Non appena si abilita questa anteprima, passare a ciascuna etichetta nel centro conformità di Microsoft 365 e applicare i criteri desiderati per i siti e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8a26-226">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="c8a26-227">Gli utenti inizieranno a visualizzare le etichette esistenti per i siti e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8a26-227">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="c8a26-228">Preparare la shell di gestione di SharePoint Online prima di rietichettare i gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="c8a26-228">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="c8a26-229">Prima di applicare nuove etichette, verificare che sia in esecuzione la versione più recente di SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8a26-229">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="c8a26-230">Se si ha già la versione più recente, è possibile procedere e [rietichettare i gruppi di Office 365 con nuove etichette di riservatezza](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c8a26-230">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="c8a26-231">Per preparare SharePoint Online Management Shell per l'anteprima:</span><span class="sxs-lookup"><span data-stu-id="c8a26-231">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="c8a26-232">Se è stata installata una versione precedente di SharePoint Online Management Shell, andare a installazione **applicazioni** e disinstallare "SharePoint Online Management Shell".</span><span class="sxs-lookup"><span data-stu-id="c8a26-232">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="c8a26-233">In un Web browser passare alla pagina Centro download e [scaricare la versione più recente di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="c8a26-233">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="c8a26-234">Selezionare la lingua e quindi fare clic su **download**.</span><span class="sxs-lookup"><span data-stu-id="c8a26-234">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="c8a26-235">Scegliere tra il file x64 e x86. msi.</span><span class="sxs-lookup"><span data-stu-id="c8a26-235">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="c8a26-236">Scaricare il file x64 se si esegue la versione di Windows a 64 bit o il file x86 se si esegue la versione a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="c8a26-236">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="c8a26-237">Se non si conosce, vedere [la versione del sistema operativo Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="c8a26-237">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="c8a26-238">Dopo aver scaricato il file, eseguire il file e seguire i passaggi illustrati nell'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="c8a26-238">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="c8a26-239">Relabel Office 365 gruppi con nuove etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c8a26-239">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="c8a26-240">Assicurarsi di utilizzare la versione più recente di SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8a26-240">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="c8a26-241">Per istruzioni, vedere [preparare la shell di gestione di SharePoint Online prima di rietichettare i gruppi di Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="c8a26-241">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="c8a26-242">Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Office 365, connettersi a SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8a26-242">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="c8a26-243">Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="c8a26-243">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="c8a26-244">Eseguire il seguente comando per ottenere l'elenco delle etichette di riservatezza e dei relativi GUID.</span><span class="sxs-lookup"><span data-stu-id="c8a26-244">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="c8a26-245">Prendere nota del GUID per l'etichetta che si desidera sovrascrivere.</span><span class="sxs-lookup"><span data-stu-id="c8a26-245">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="c8a26-246">Ad esempio, l'etichetta "generale".</span><span class="sxs-lookup"><span data-stu-id="c8a26-246">For example, the "General" label.</span></span>

5. <span data-ttu-id="c8a26-247">Utilizzare il seguente comando per ottenere l'elenco dei gruppi che hanno la classificazione "generale".</span><span class="sxs-lookup"><span data-stu-id="c8a26-247">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="c8a26-248">Quando si esegue questo comando, è possibile connettersi a PowerShell di Exchange Online ed eseguire il cmdlet Get-UnifiedGroup.</span><span class="sxs-lookup"><span data-stu-id="c8a26-248">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="c8a26-249">Per ogni gruppo, aggiungere il nuovo GUID dell'etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c8a26-249">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
