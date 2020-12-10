---
title: Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: "Riepilogo: configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo e di testing di Microsoft 365."
ms.openlocfilehash: 6e056cd1d930d13e1ae20f8f8d0cdc9aa886f17e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616489"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="4c686-103">Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="4c686-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="4c686-104">**Riepilogo:** Configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo e di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c686-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="4c686-105">I siti del team di SharePoint online in Microsoft 365 sono percorsi per la collaborazione utilizzando una raccolta documenti comune, un blocco appunti di OneNote e altri servizi.</span><span class="sxs-lookup"><span data-stu-id="4c686-105">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="4c686-106">In molti casi, è necessario un accesso esteso e una collaborazione tra dipartimenti o organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4c686-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="4c686-107">Tuttavia, in alcuni casi, si desidera controllare in modo rigoroso l'accesso e le autorizzazioni per la collaborazione tra un piccolo gruppo di persone.</span><span class="sxs-lookup"><span data-stu-id="4c686-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="4c686-108">L'accesso ai siti del team di SharePoint Online e gli elementi che gli utenti possono eseguire sono controllati da gruppi e livelli di autorizzazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4c686-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="4c686-109">Per impostazione predefinita, i siti di SharePoint Online hanno tre livelli di accesso:</span><span class="sxs-lookup"><span data-stu-id="4c686-109">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="4c686-110">**Membri**, che possono visualizzare, creare e modificare le risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="4c686-110">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="4c686-111">**Proprietari**, che dispongono del controllo completo del sito, inclusa la possibilità di modificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4c686-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="4c686-112">**Visitatori**, che possono solo visualizzare le risorse sul sito.</span><span class="sxs-lookup"><span data-stu-id="4c686-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="4c686-113">In questo articolo viene illustrata la configurazione di un sito del team di SharePoint Online isolato per un progetto di ricerca segreto denominato ProjectX.</span><span class="sxs-lookup"><span data-stu-id="4c686-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="4c686-114">I requisiti di accesso sono:</span><span class="sxs-lookup"><span data-stu-id="4c686-114">The access requirements are:</span></span>

- <span data-ttu-id="4c686-115">Solo i membri del progetto possono accedere al sito e al relativo contenuto (documenti, blocco appunti di OneNote, pagine), con i livelli di autorizzazione di modifica e visualizzazione di SharePoint controllati tramite l'appartenenza a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="4c686-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="4c686-116">Solo il creatore del sito e i membri di un gruppo Admins per il sito possono eseguire l'amministrazione del sito, che include la modifica delle autorizzazioni a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="4c686-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="4c686-117">Sono disponibili tre fasi per la configurazione di un sito del team di SharePoint Online isolato nell'ambiente di sviluppo/test di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="4c686-117">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="4c686-118">Creare l'ambiente di sviluppo e di testing di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c686-118">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="4c686-119">Creare gli utenti e i gruppi per ProjectX.</span><span class="sxs-lookup"><span data-stu-id="4c686-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="4c686-120">Creare un nuovo sito del team di SharePoint Online ProjectX e isolarlo.</span><span class="sxs-lookup"><span data-stu-id="4c686-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="4c686-121">Fare clic [qui](https://aka.ms/catlgstack) per consultare una mappa di tutti gli articoli relativi alla guida del laboratorio di testing cloud di One Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c686-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="4c686-122">Fase 1: creare l'ambiente di sviluppo/test di Microsoft 365 per l'organizzazione leggera o simulata</span><span class="sxs-lookup"><span data-stu-id="4c686-122">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="4c686-123">Se si desidera creare un sito del team di SharePoint Online isolato in modo semplice con i requisiti minimi, seguire le istruzioni riportate nelle fasi 2 e 3 della [configurazione di base Lightweight](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="4c686-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="4c686-124">Se si desidera creare un sito del team di SharePoint Online isolato in una configurazione aziendale simulata, seguire le istruzioni riportate in [sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="4c686-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="4c686-125">La creazione di un sito di SharePoint Online isolato non richiede l'ambiente di sviluppo e di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="4c686-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4c686-126">Viene fornito come opzione in modo che sia possibile testare un sito di SharePoint Online isolato e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="4c686-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="4c686-127">Fase 2: creare account utente e gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="4c686-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="4c686-128">Utilizzare le istruzioni riportate in [Connect to Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) per connettersi alla sottoscrizione di valutazione con l'account di amministratore globale da:</span><span class="sxs-lookup"><span data-stu-id="4c686-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="4c686-129">Il computer (per l'ambiente di sviluppo/test di Microsoft 365 Lightweight).</span><span class="sxs-lookup"><span data-stu-id="4c686-129">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="4c686-130">La macchina virtuale CLIENT1 (per l'ambiente di sviluppo/test di Microsoft 365 Enterprise simulato).</span><span class="sxs-lookup"><span data-stu-id="4c686-130">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="4c686-131">Per creare i nuovi gruppi di accesso per il sito del team di SharePoint Online di ProjectX, eseguire i comandi seguenti dal prompt del modulo di Windows Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4c686-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="4c686-132">Immettere il nome dell'organizzazione (ad esempio: contosotoycompany), il prefisso internazionale a due caratteri e quindi eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4c686-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="4c686-133">Dalla visualizzazione del comando **New-MsolUser** , prendere nota della password generata per l'account lead designer e registrarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="4c686-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="4c686-134">Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4c686-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="4c686-135">Dalla visualizzazione del comando **New-MsolUser** , prendere nota della password generata per l'account del ricercatore principale e registrarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="4c686-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="4c686-136">Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4c686-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="4c686-137">Dalla visualizzazione del comando **New-MsolUser** , prendere nota della password generata per l'account Development VP e registrarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="4c686-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="4c686-138">Successivamente, per aggiungere i nuovi account ai nuovi gruppi di accesso, eseguire i comandi di PowerShell dal modulo di Windows Azure Active Directory per il prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4c686-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="4c686-139">Risultati</span><span class="sxs-lookup"><span data-stu-id="4c686-139">Results:</span></span>

- <span data-ttu-id="4c686-140">Il gruppo di accesso ProjectX-Members contiene gli account utente lead designer e Lead Researcher</span><span class="sxs-lookup"><span data-stu-id="4c686-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="4c686-141">Il gruppo di accesso ProjectX-Admins contiene l'account di amministratore globale per la sottoscrizione di valutazione</span><span class="sxs-lookup"><span data-stu-id="4c686-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="4c686-142">Il gruppo di accesso ProjectX-Viewers contiene l'account utente Development VP</span><span class="sxs-lookup"><span data-stu-id="4c686-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="4c686-143">Nella figura 1 vengono visualizzati i gruppi di accesso e la relativa appartenenza.</span><span class="sxs-lookup"><span data-stu-id="4c686-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="4c686-144">**Figura 1**:</span><span class="sxs-lookup"><span data-stu-id="4c686-144">**Figure 1**:</span></span>

![Gruppi di Microsoft 365 e loro appartenenza a un sito di gruppo di SharePoint Online isolato](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="4c686-146">Fase 3: creare un nuovo sito del team di SharePoint Online ProjectX e isolarlo</span><span class="sxs-lookup"><span data-stu-id="4c686-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="4c686-147">Per creare un sito del team di SharePoint Online per ProjectX, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c686-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="4c686-148">Utilizzando un browser sul computer locale (configurazione lightweight) o su CLIENT1 (configurazione Enterprise simulata), accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) utilizzando l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4c686-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="4c686-149">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4c686-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="4c686-150">Nella nuova scheda SharePoint del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="4c686-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="4c686-151">In **nome sito del team** digitare **ProjectX**.</span><span class="sxs-lookup"><span data-stu-id="4c686-151">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="4c686-152">In **impostazioni di privacy**, selezionare **membri solo privati possono accedere a questo sito**.</span><span class="sxs-lookup"><span data-stu-id="4c686-152">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="4c686-153">In **Descrizione sito del team**, digitare **sito di SharePoint per ProjectX** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4c686-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="4c686-154">Per **chi si desidera aggiungere**? riquadro, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="4c686-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="4c686-155">Nella nuova scheda **ProjectX-Home** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona impostazioni e quindi su **autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="4c686-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="4c686-156">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="4c686-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="4c686-157">Nella scheda nuovo **autorizzazioni: progetto X** del browser, fare clic su **impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="4c686-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="4c686-158">Nella finestra di dialogo **impostazioni richieste di accesso** deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti le richieste di accesso** (in modo che tutte e tre le caselle di controllo siano deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c686-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="4c686-159">Fare clic su **membri di ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4c686-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="4c686-160">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4c686-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="4c686-161">Nella finestra di dialogo **Condividi** , digitare **ProjectX-members**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="4c686-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="4c686-162">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="4c686-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="4c686-163">Fare clic su **proprietari di ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4c686-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="4c686-164">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4c686-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="4c686-165">Nella finestra di dialogo **Condividi** , digitare **ProjectX-Admins**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="4c686-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="4c686-166">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="4c686-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="4c686-167">Fare clic su **ProjectX visitatori** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4c686-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="4c686-168">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4c686-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="4c686-169">Nella finestra di dialogo **Condividi** , digitare **ProjectX-Viewer**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="4c686-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="4c686-170">Chiudere la scheda **utenti e gruppi** del browser, fare clic sulla scheda **ProjectX-Home** nel browser e quindi chiudere il riquadro **autorizzazioni sito** .</span><span class="sxs-lookup"><span data-stu-id="4c686-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="4c686-171">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="4c686-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="4c686-172">Il gruppo di SharePoint membri di ProjectX contiene solo il gruppo di accesso ProjectX-Members (che contiene solo gli account utente lead designer e Lead Researcher) e il gruppo ProjectX (che contiene solo l'account utente di amministratore globale).</span><span class="sxs-lookup"><span data-stu-id="4c686-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="4c686-173">Il gruppo di SharePoint proprietari di ProjectX contiene solo il gruppo di accesso ProjectX-Admins (che contiene solo l'account utente di amministratore globale).</span><span class="sxs-lookup"><span data-stu-id="4c686-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="4c686-174">Il gruppo di SharePoint visitatori di ProjectX contiene solo il gruppo di accesso ProjectX-Viewers (che contiene solo l'account utente Development VP).</span><span class="sxs-lookup"><span data-stu-id="4c686-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="4c686-175">I membri non possono modificare le autorizzazioni a livello di sito (possono essere eseguite solo dai membri del gruppo ProjectX-Admins).</span><span class="sxs-lookup"><span data-stu-id="4c686-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="4c686-176">Gli altri account utente non possono accedere al sito o alle relative risorse né richiedere l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="4c686-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="4c686-177">Nella figura 2 sono riportati i gruppi di SharePoint e la relativa appartenenza.</span><span class="sxs-lookup"><span data-stu-id="4c686-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="4c686-178">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="4c686-178">**Figure 2**</span></span>

![I gruppi di SharePoint Online e la loro appartenenza a un sito di gruppo di SharePoint Online isolato](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="4c686-180">Ora dimostreremo l'accesso utilizzando l'account utente lead designer:</span><span class="sxs-lookup"><span data-stu-id="4c686-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="4c686-181">Chiudere la scheda **ProjectX-Home** nel browser, quindi fare clic sulla scheda **Microsoft Office Home** nel browser.</span><span class="sxs-lookup"><span data-stu-id="4c686-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="4c686-182">Fare clic sul nome dell'amministratore globale, quindi fare clic su **Esci.**</span><span class="sxs-lookup"><span data-stu-id="4c686-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="4c686-183">Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) utilizzando il nome dell'account del progettista principale e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="4c686-183">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="4c686-184">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4c686-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="4c686-185">Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team di **ProjectX** .</span><span class="sxs-lookup"><span data-stu-id="4c686-185">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="4c686-186">Verrà visualizzata una nuova scheda del browser per il sito del team di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="4c686-186">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="4c686-187">Fare clic sull'icona impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4c686-187">Click the settings icon.</span></span> <span data-ttu-id="4c686-188">Si noti che non è disponibile alcuna opzione per le autorizzazioni per il **sito**.</span><span class="sxs-lookup"><span data-stu-id="4c686-188">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="4c686-189">Questo è corretto perché solo i membri del gruppo di ProjectX-Admins possono modificare le autorizzazioni per il sito</span><span class="sxs-lookup"><span data-stu-id="4c686-189">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="4c686-190">Aprire il blocco note o un editor di testo desiderato.</span><span class="sxs-lookup"><span data-stu-id="4c686-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="4c686-191">Copiare l'URL del sito del team di ProjectX e incollarlo su una nuova riga nel blocco note o nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="4c686-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="4c686-192">Nella nuova scheda **ProjectX-Home** visualizzata nel browser, fare clic su **documenti**.</span><span class="sxs-lookup"><span data-stu-id="4c686-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="4c686-193">Copiare l'URL della cartella documenti di ProjectX e incollarlo su una nuova riga nel blocco note o nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="4c686-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="4c686-194">Nella nuova scheda **ProjectX-Documents** del browser fare clic su **nuovo > documento di Word**.</span><span class="sxs-lookup"><span data-stu-id="4c686-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="4c686-195">Digitare del testo nella pagina, attendere che lo stato indichi **salvato**, fare clic sul pulsante indietro nel browser e quindi aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="4c686-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="4c686-196">Nella cartella **documenti** dovrebbe essere visualizzato un nuovo **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="4c686-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="4c686-197">Fare clic sui puntini di sospensione per il documento **Document.docx** e quindi fare clic su **Ottieni un collegamento**.</span><span class="sxs-lookup"><span data-stu-id="4c686-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="4c686-198">Copiare l'URL nella finestra di dialogo **Condividi ' Document.docx'** e incollarlo su una nuova riga nel blocco note o nell'editor di testo, quindi chiudere la finestra di dialogo **Condividi ' Document.docx'** .</span><span class="sxs-lookup"><span data-stu-id="4c686-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="4c686-199">Chiudere le schede **ProjectX-Documents** e **SharePoint** nel browser, quindi fare clic sulla scheda **Microsoft Office Home** .</span><span class="sxs-lookup"><span data-stu-id="4c686-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="4c686-200">Fare clic sul nome del **progettista principale** e quindi fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="4c686-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="4c686-201">Ora dimostreremo l'accesso utilizzando l'account utente Development VP:</span><span class="sxs-lookup"><span data-stu-id="4c686-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="4c686-202">Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) utilizzando il nome dell'account Development VP e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="4c686-202">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="4c686-203">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4c686-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="4c686-204">Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team di **ProjectX** .</span><span class="sxs-lookup"><span data-stu-id="4c686-204">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="4c686-205">Verrà visualizzata una nuova scheda del browser per il sito del team di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="4c686-205">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="4c686-206">Fare clic su **documenti** e quindi fare clic sul file **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="4c686-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="4c686-207">Nella scheda **Document.docx** del browser, provare a modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="4c686-207">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="4c686-208">Verrà visualizzato un messaggio che indica che **il documento è di sola lettura.**</span><span class="sxs-lookup"><span data-stu-id="4c686-208">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="4c686-209">Questo è previsto perché l'account utente Development VP dispone solo delle autorizzazioni di visualizzazione per il sito.</span><span class="sxs-lookup"><span data-stu-id="4c686-209">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="4c686-210">Chiudere le schede **Document.docx**, **ProjectX-Documents** e **SharePoint** nel browser.</span><span class="sxs-lookup"><span data-stu-id="4c686-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="4c686-211">Fare clic sulla scheda **Microsoft Office Home** , **fare clic sul** nome **dello sviluppo VP** e quindi fare clic su Esci.</span><span class="sxs-lookup"><span data-stu-id="4c686-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="4c686-212">Ora dimostreremo l'accesso con un account utente che non dispone di autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="4c686-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="4c686-213">Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) utilizzando il nome dell'account utente 3 e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="4c686-213">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="4c686-214">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4c686-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="4c686-215">Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca e quindi attivare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4c686-215">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="4c686-216">Verrà visualizzato il messaggio **niente corrisponde alla ricerca.**</span><span class="sxs-lookup"><span data-stu-id="4c686-216">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="4c686-217">Nell'istanza aperta di blocco note o nell'editor di testo, copiare l'URL del sito di ProjectX nella barra degli indirizzi del browser e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="4c686-217">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="4c686-218">Verrà visualizzata una pagina di **accesso negato** .</span><span class="sxs-lookup"><span data-stu-id="4c686-218">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="4c686-219">Dal blocco note o dall'editor di testo, copiare l'URL della cartella documenti di ProjectX nella barra degli indirizzi del browser e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="4c686-219">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="4c686-220">Verrà visualizzata una pagina di **accesso negato** .</span><span class="sxs-lookup"><span data-stu-id="4c686-220">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="4c686-221">Dal blocco note o dall'editor di testo, copiare l'URL del file Documents.docx nella barra degli indirizzi del browser e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="4c686-221">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="4c686-222">Verrà visualizzata una pagina di **accesso negato** .</span><span class="sxs-lookup"><span data-stu-id="4c686-222">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="4c686-223">Chiudere la scheda **SharePoint** nel browser, fare clic sulla scheda **Microsoft Office Home** , fare clic sul nome dell' **utente 3** e quindi fare **clic su Esci.**</span><span class="sxs-lookup"><span data-stu-id="4c686-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="4c686-224">Il sito di SharePoint Online isolato è ora pronto per la sperimentazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="4c686-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="4c686-225">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4c686-225">Next Step</span></span>

<span data-ttu-id="4c686-226">Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="4c686-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c686-227">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c686-227">See Also</span></span>

[<span data-ttu-id="4c686-228">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="4c686-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="4c686-229">Guida al lab test (TLG) per adozione del cloud</span><span class="sxs-lookup"><span data-stu-id="4c686-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="4c686-230">La configurazione di base per l'organizzazione simulata</span><span class="sxs-lookup"><span data-stu-id="4c686-230">The simulated enterprise base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="4c686-231">La configurazione di base</span><span class="sxs-lookup"><span data-stu-id="4c686-231">The lightweight base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="4c686-232">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="4c686-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
