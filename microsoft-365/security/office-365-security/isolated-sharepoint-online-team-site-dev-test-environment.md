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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: "Riepilogo: configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Microsoft 365."
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286610"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="8fbe9-103">Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="8fbe9-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8fbe9-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-104">**Applies to**</span></span>
- [<span data-ttu-id="8fbe9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8fbe9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8fbe9-106">Microsoft Defender per Office 365 piano 1</span><span class="sxs-lookup"><span data-stu-id="8fbe9-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="8fbe9-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8fbe9-107">SharePoint Online</span></span> 


 <span data-ttu-id="8fbe9-108">**Riepilogo:** Configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-108">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="8fbe9-109">I siti del team di SharePoint Online in Microsoft 365 sono posizioni per la collaborazione tramite una raccolta documenti comune, un blocco appunti di OneNote e altri servizi.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-109">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="8fbe9-110">In molti casi, si desidera un ampio accesso e collaborazione tra reparti o organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-110">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="8fbe9-111">Tuttavia, in alcuni casi, si desidera controllare strettamente l'accesso e le autorizzazioni per la collaborazione tra un piccolo gruppo di persone.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-111">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="8fbe9-112">L'accesso ai siti del team di SharePoint Online e le azioni che gli utenti possono eseguire sono controllati dai gruppi e dai livelli di autorizzazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-112">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="8fbe9-113">Per impostazione predefinita, i siti di SharePoint Online dispongono di tre livelli di accesso:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-113">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="8fbe9-114">**Membri**, che possono visualizzare, creare e modificare le risorse nel sito.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-114">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="8fbe9-115">**Proprietari**, che hanno il controllo completo del sito, inclusa la possibilità di modificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-115">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="8fbe9-116">**Visitatori,** che possono visualizzare solo le risorse nel sito.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-116">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="8fbe9-117">In questo articolo viene illustrata la configurazione di un sito del team di SharePoint Online isolato per un progetto di ricerca segreto denominato ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-117">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="8fbe9-118">I requisiti di accesso sono:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-118">The access requirements are:</span></span>

- <span data-ttu-id="8fbe9-119">Solo i membri del progetto possono accedere al sito e al relativo contenuto (documenti, blocco appunti di OneNote, pagine), con i livelli di autorizzazione di modifica e visualizzazione di SharePoint controllati tramite l'appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-119">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="8fbe9-120">Solo il creatore del sito e i membri di un gruppo Admins del sito possono eseguire l'amministrazione del sito, inclusa la modifica delle autorizzazioni a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-120">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="8fbe9-121">Esistono tre fasi per configurare un sito del team di SharePoint Online isolato nell'ambiente di sviluppo/test di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-121">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="8fbe9-122">Creare l'ambiente di sviluppo/test di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-122">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="8fbe9-123">Creare gli utenti e i gruppi per ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-123">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="8fbe9-124">Creare un nuovo sito del team di ProjectX SharePoint Online e isolarlo.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-124">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="8fbe9-125">Fare clic [qui](https://aka.ms/catlgstack) per consultare una mappa di tutti gli articoli relativi alla guida del laboratorio di testing cloud di One Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-125">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="8fbe9-126">Fase 1: creare l'ambiente di sviluppo/test di Microsoft 365 aziendale leggero o simulato</span><span class="sxs-lookup"><span data-stu-id="8fbe9-126">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="8fbe9-127">Se si desidera creare un sito del team di SharePoint Online isolato in modo leggero con i requisiti minimi, seguire le istruzioni nelle fasi 2 e 3 della configurazione [di base leggera.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="8fbe9-127">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="8fbe9-128">Se si desidera creare un sito del team di SharePoint Online isolato in una configurazione aziendale simulata, seguire le istruzioni in Sincronizzazione hash delle password per l'ambiente di testing di [Microsoft 365.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="8fbe9-128">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](../../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8fbe9-129">La creazione di un sito di SharePoint Online isolato non richiede l'ambiente di sviluppo/test aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-129">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8fbe9-130">Qui viene fornito come opzione in modo da poter testare un sito di SharePoint Online isolato e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-130">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="8fbe9-131">Fase 2: creare account utente e gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="8fbe9-131">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="8fbe9-132">Seguire le istruzioni in [Connettersi a PowerShell di Office 365](../../enterprise/connect-to-microsoft-365-powershell.md) per connettersi all'abbonamento di valutazione con l'account amministratore globale da:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-132">Use the instructions in [Connect to Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="8fbe9-133">Computer (per l'ambiente di sviluppo/test di Microsoft 365 leggero).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-133">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="8fbe9-134">La macchina virtuale CLIENT1 (per l'ambiente di sviluppo/test di Microsoft 365 aziendale simulato).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-134">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="8fbe9-135">Per creare i nuovi gruppi di accesso per il sito del team di SharePoint Online di ProjectX, eseguire questi comandi dal modulo di Active Directory di Windows Azure per Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-135">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="8fbe9-136">Immettere il nome dell'organizzazione (ad esempio: contosotoycompany), il prefisso internazionale a due caratteri e quindi eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-136">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8fbe9-137">Dalla visualizzazione del comando **New-MsolUser,** prendere nota della password generata per l'account lead designer e registrarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-137">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="8fbe9-138">Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-138">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8fbe9-139">Dalla visualizzazione del comando **New-MsolUser,** prendere nota della password generata per l'account del ricercatore principale e registrarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-139">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="8fbe9-140">Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-140">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8fbe9-141">Dalla visualizzazione del comando **New-MsolUser,** prendere nota della password generata per l'account VP development e registrarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-141">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="8fbe9-142">Successivamente, per aggiungere i nuovi account ai nuovi gruppi di accesso, eseguire questi comandi di PowerShell dal modulo di Active Directory Windows Azure per Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-142">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="8fbe9-143">Risultati:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-143">Results:</span></span>

- <span data-ttu-id="8fbe9-144">Il ProjectX-Members di accesso contiene gli account utente Lead Designer e Lead Researcher</span><span class="sxs-lookup"><span data-stu-id="8fbe9-144">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="8fbe9-145">Il ProjectX-Admins di accesso include l'account amministratore globale per la sottoscrizione di valutazione</span><span class="sxs-lookup"><span data-stu-id="8fbe9-145">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="8fbe9-146">Il ProjectX-Viewers di accesso include l'account utente VP di sviluppo</span><span class="sxs-lookup"><span data-stu-id="8fbe9-146">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="8fbe9-147">La figura 1 mostra i gruppi di accesso e la relativa appartenenza.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-147">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="8fbe9-148">**Figura 1:**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-148">**Figure 1**:</span></span>

![I gruppi di Microsoft 365 e la relativa appartenenza per un sito del gruppo di SharePoint Online isolato](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="8fbe9-150">Fase 3: creare un nuovo sito del team di ProjectX SharePoint Online e isolarlo</span><span class="sxs-lookup"><span data-stu-id="8fbe9-150">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="8fbe9-151">Per creare un sito del team di SharePoint Online per ProjectX, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-151">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="8fbe9-152">Usando un browser nel computer locale (configurazione leggera) o in CLIENT1 (configurazione aziendale simulata), accedere all'interfaccia di amministrazione di Microsoft 365 ( ) con <https://admin.microsoft.com> l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-152">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="8fbe9-153">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-153">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8fbe9-154">Nella nuova scheda SharePoint del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-154">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="8fbe9-155">In **Nome sito del team** digitare **ProjectX.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-155">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="8fbe9-156">In **Impostazioni privacy** selezionare **Privato: solo i membri possono accedere al sito.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-156">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="8fbe9-157">In **Descrizione sito del team** digitare Sito di **SharePoint per ProjectX** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-157">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="8fbe9-158">Nella pagina **Chi si desidera aggiungere?** , fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-158">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="8fbe9-159">Nella nuova **scheda ProjectX-Home** del browser fare clic sull'icona delle impostazioni nella barra degli strumenti e quindi su **Autorizzazioni sito.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-159">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="8fbe9-160">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-160">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="8fbe9-161">Nella nuova scheda **Autorizzazioni: Progetto X** del browser fare clic su **Impostazioni richieste di accesso.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-161">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="8fbe9-162">Nella finestra **di** dialogo Impostazioni  richieste di accesso deselezionare Consenti ai membri di condividere il sito e singoli file e cartelle e Consenti richieste di accesso **(in** modo che tutte e tre le caselle di controllo siano deselezionate) e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-162">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="8fbe9-163">Fare **clic su Membri ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-163">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="8fbe9-164">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-164">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="8fbe9-165">Nella finestra **di** dialogo Condividi digitare **ProjectX-Members,** selezionarlo e quindi fare clic su **Condividi.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-165">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="8fbe9-166">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-166">Click the back button on your browser.</span></span>

15. <span data-ttu-id="8fbe9-167">Fare **clic su Proprietari ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-167">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="8fbe9-168">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-168">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="8fbe9-169">Nella finestra **di** dialogo Condividi digitare **ProjectX-Admins,** selezionarlo e quindi fare clic su **Condividi.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-169">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="8fbe9-170">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-170">Click the back button on your browser.</span></span>

19. <span data-ttu-id="8fbe9-171">Fare **clic su Visitatori di ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-171">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="8fbe9-172">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-172">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="8fbe9-173">Nella finestra **di** dialogo Condividi digitare **Visualizzatori ProjectX,** selezionarlo e quindi fare clic su **Condividi.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-173">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="8fbe9-174">Chiudere la **scheda Utenti e** gruppi nel browser, fare clic sulla scheda **ProjectX-Home** nel browser e quindi chiudere il **riquadro Autorizzazioni** sito.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-174">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="8fbe9-175">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-175">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="8fbe9-176">Il gruppo di SharePoint Membri di ProjectX contiene solo il gruppo di accesso ProjectX-Members (che contiene solo gli account utente Lead Designer e Lead Researcher) e il gruppo ProjectX (che contiene solo l'account utente amministratore globale).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-176">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="8fbe9-177">Il gruppo di SharePoint Proprietari di ProjectX contiene solo il ProjectX-Admins di accesso completo (che contiene solo l'account utente amministratore globale).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-177">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="8fbe9-178">Il gruppo di SharePoint Visitatori di ProjectX contiene solo il gruppo di ProjectX-Viewers di accesso (che contiene solo l'account utente VP di sviluppo).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-178">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="8fbe9-179">I membri non possono modificare le autorizzazioni a livello di sito ( questa operazione può essere eseguita solo dai membri del ProjectX-Admins gruppo).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-179">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="8fbe9-180">Gli altri account utente non possono accedere al sito o alle relative risorse né richiedere l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-180">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="8fbe9-181">La figura 2 mostra i gruppi di SharePoint e la relativa appartenenza.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-181">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="8fbe9-182">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-182">**Figure 2**</span></span>

![I gruppi di SharePoint Online e la relativa appartenenza a un sito del gruppo di SharePoint Online isolato](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="8fbe9-184">Ora dimostreremo l'accesso con l'account utente Lead Designer:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-184">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="8fbe9-185">Chiudere la **scheda ProjectX-Home** nel browser e quindi fare clic sulla Microsoft Office **Home** nel browser.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-185">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="8fbe9-186">Fare clic sul nome dell'amministratore globale e quindi **su Disconnennei.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-186">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="8fbe9-187">Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) usando il nome dell'account lead designer e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-187">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="8fbe9-188">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-188">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="8fbe9-189">Nella nuova scheda **di SharePoint** nel browser digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team **di ProjectX.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-189">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="8fbe9-190">Nel browser dovrebbe essere visualizzata una nuova scheda per il sito del team di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-190">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="8fbe9-191">Fare clic sull'icona delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-191">Click the settings icon.</span></span> <span data-ttu-id="8fbe9-192">Si noti che non è disponibile alcuna opzione per **autorizzazioni sito.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-192">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="8fbe9-193">Ciò è corretto perché solo i membri del gruppo ProjectX-Admins possono modificare le autorizzazioni per il sito</span><span class="sxs-lookup"><span data-stu-id="8fbe9-193">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="8fbe9-194">Aprire blocco note o un editor di testo di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-194">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="8fbe9-195">Copiare l'URL del sito del team di ProjectX e incollarlo in una nuova riga del Blocco note o nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-195">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="8fbe9-196">Nella nuova **scheda ProjectX-Home del** browser fare clic su **Documenti.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-196">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="8fbe9-197">Copiare l'URL della cartella dei documenti di ProjectX e incollarlo in una nuova riga del Blocco note o dell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-197">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="8fbe9-198">Nella nuova **scheda ProjectX-Documents del** browser fare clic su > documento di **Word.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-198">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="8fbe9-199">Digitare del testo nella pagina, attendere che lo stato indichi **Salvato,** fare clic sul pulsante Indietro nel browser e quindi aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-199">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="8fbe9-200">Verrà visualizzato un nuovo **Document.docx** nella **cartella** Documenti.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-200">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="8fbe9-201">Fare clic sui puntini di sospensione **perDocument.docx** documento e quindi fare clic su Ottieni **un collegamento.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-201">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="8fbe9-202">Copiare l'URL nella finestra di dialogo **Condividi 'Document.docx'** e incollarlo in una nuova riga del Blocco note o nell'editor di testo, quindi chiudere la finestra di dialogo **Condividi 'Document.docx'.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-202">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="8fbe9-203">Chiudere le **schede ProjectX-Documents** e **SharePoint** nel browser e quindi fare clic sulla **Microsoft Office Home.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-203">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="8fbe9-204">Fare clic **sul nome lead designer** e quindi su **Disconner.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-204">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8fbe9-205">Ora dimostreremo l'accesso con l'account utente VP di sviluppo:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-205">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="8fbe9-206">Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) usando il nome dell'account VP development e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-206">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="8fbe9-207">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-207">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8fbe9-208">Nella nuova scheda **di SharePoint** nel browser digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team **di ProjectX.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-208">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="8fbe9-209">Nel browser dovrebbe essere visualizzata una nuova scheda per il sito del team di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-209">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="8fbe9-210">Fare **clic su** Documenti e quindi sulDocument.docxfile. </span><span class="sxs-lookup"><span data-stu-id="8fbe9-210">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="8fbe9-211">Nella scheda **Document.docx** del browser provare a modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-211">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="8fbe9-212">Verrà visualizzato un messaggio che indica **che il documento è di sola lettura.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-212">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="8fbe9-213">Ciò è previsto perché l'account utente VP di sviluppo dispone solo delle autorizzazioni di visualizzazione per il sito.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-213">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="8fbe9-214">Chiudere le **Document.docx,** **ProjectX-Documents** e **SharePoint** nel browser.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-214">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="8fbe9-215">Fare clic **Microsoft Office home** page, fare clic sul nome **del VP di sviluppo** e quindi su **Disconnetta.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-215">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8fbe9-216">Ora dimostreremo l'accesso con un account utente che non dispone di autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="8fbe9-216">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="8fbe9-217">Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) usando il nome dell'account User 3 e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-217">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="8fbe9-218">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-218">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8fbe9-219">Nella nuova scheda **di SharePoint** nel browser digitare **ProjectX** nella casella di ricerca e quindi attivare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-219">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="8fbe9-220">Verrà visualizzato il messaggio Nothing **qui corrispondente alla ricerca.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-220">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="8fbe9-221">Dall'istanza aperta del Blocco note o dall'editor di testo, copiare l'URL del sito ProjectX nella barra degli indirizzi del browser e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-221">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8fbe9-222">Dovrebbe essere visualizzata una **pagina Accesso** negato.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-222">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="8fbe9-223">Dal Blocco note o dall'editor di testo, copiare l'URL della cartella Documenti ProjectX nella barra degli indirizzi del browser e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-223">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8fbe9-224">Dovrebbe essere visualizzata una **pagina Accesso** negato.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-224">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="8fbe9-225">Dal Blocco note o dall'editor di testo, copiare l'URL del file Documents.docx nella barra degli indirizzi del browser e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-225">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8fbe9-226">Dovrebbe essere visualizzata una **pagina Accesso** negato.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-226">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="8fbe9-227">Chiudere la **scheda SharePoint** nel browser, fare clic sulla **Microsoft Office Home,** fare clic sul nome **User 3** e quindi su **Disconnetta.**</span><span class="sxs-lookup"><span data-stu-id="8fbe9-227">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8fbe9-228">Il sito di SharePoint Online isolato è ora pronto per la sperimentazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="8fbe9-228">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="8fbe9-229">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8fbe9-229">Next Step</span></span>

<span data-ttu-id="8fbe9-230">Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="8fbe9-230">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8fbe9-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fbe9-231">See Also</span></span>

[<span data-ttu-id="8fbe9-232">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="8fbe9-232">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="8fbe9-233">Guida al lab test (TLG) per adozione del cloud</span><span class="sxs-lookup"><span data-stu-id="8fbe9-233">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="8fbe9-234">La configurazione di base per l'organizzazione simulata</span><span class="sxs-lookup"><span data-stu-id="8fbe9-234">The simulated enterprise base configuration</span></span>](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="8fbe9-235">La configurazione di base</span><span class="sxs-lookup"><span data-stu-id="8fbe9-235">The lightweight base configuration</span></span>](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="8fbe9-236">Microsoft 365 Solution and Architecture Center</span><span class="sxs-lookup"><span data-stu-id="8fbe9-236">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)