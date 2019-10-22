---
title: Team per dati altamente regolamentati
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un team sicuro in cui archiviare i file più importanti e sensibili.
ms.openlocfilehash: 5117d310ccd877a7377e6e538e7fba13daaad4ef
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617264"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="5554b-103">Team per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="5554b-103">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="5554b-104">Questo articolo contiene suggerimenti e procedure per la configurazione di un team privato in Microsoft Teams che limiti l'accesso alle funzionalità di Teams, ad esempio chat, riunioni e file, ai soli membri e ai proprietari del gruppo di Office 365 per il team.</span><span class="sxs-lookup"><span data-stu-id="5554b-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="5554b-105">Oltre all'accesso privato basato sul gruppo Office 365, questo articolo descrive come configurare il sito del team di SharePoint privato sottostante, a cui è possibile accedere dalla sezione **File** di un canale del team, per implementare la sicurezza aggiuntiva necessaria per archiviare dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="5554b-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="5554b-106">In questo sito del team di SharePoint è possibile archiviare e collaborare su file, pagine, un calendario condiviso, attività, un blocco appunti ed elenchi.</span><span class="sxs-lookup"><span data-stu-id="5554b-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="5554b-107">Gli elementi della configurazione di un team per dati altamente regolamentati sono:</span><span class="sxs-lookup"><span data-stu-id="5554b-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="5554b-108">Un team privato con un gruppo di Office 365 corrispondente che include gli account utente di proprietari e membri.</span><span class="sxs-lookup"><span data-stu-id="5554b-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="5554b-109">Sicurezza aggiuntiva nel sito di SharePoint sottostante per il team che:</span><span class="sxs-lookup"><span data-stu-id="5554b-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="5554b-110">Impedisce ai membri del sito di concedere accesso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="5554b-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="5554b-111">Impedisce ai non-membri del sito di richiedere accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="5554b-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="5554b-112">Un'etichetta di conservazione di Office 365 per il sito di SharePoint sottostante che viene applicata automaticamente ai nuovi file nel sito come strumento predefinito per definire i criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="5554b-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="5554b-113">Criteri di prevenzione della perdita dei dati che usano l'etichetta di conservazione e impediscono agli utenti di condividere o inviare file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5554b-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="5554b-114">Un'etichetta di riservatezza di Office 365 o una sottoetichetta di un'etichetta per dati altamente regolamentati con crittografia abilitata e autorizzazioni di creazione condivisa per il gruppo di Office 365 del team.</span><span class="sxs-lookup"><span data-stu-id="5554b-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="5554b-115">Gli utenti applicano l'etichetta o la sottoetichetta ai file archiviati nella sezione **File** del team dall'opzione della barra dei menu Riservatezza in Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="5554b-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="5554b-116">Ecco la configurazione risultante con un'etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="5554b-116">Here is the resulting configuration with a sensitivity label.</span></span>

![Configurazione dello scenario del team sicuro](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="configuration"></a><span data-ttu-id="5554b-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="5554b-118">Configuration</span></span>

<span data-ttu-id="5554b-119">La configurazione end-to-end di un team sicuro prevede questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="5554b-119">The end-to-end configuration of a secure team consists of these steps:</span></span>

1. <span data-ttu-id="5554b-120">Configurare le identità e l'accesso ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5554b-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="5554b-121">Creare un team privato.</span><span class="sxs-lookup"><span data-stu-id="5554b-121">Create a private team.</span></span>
3. <span data-ttu-id="5554b-122">Configurare il sito di SharePoint sottostante per aumentare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5554b-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="5554b-123">Creare un'etichetta di conservazione e i criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="5554b-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="5554b-124">Creare l'etichetta o la sottoetichetta dell'etichetta per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="5554b-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="5554b-125">Passaggio1: Configurare le identità e l'accesso ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="5554b-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="5554b-126">Per proteggere l'accesso al team e al sito di SharePoint sottostante, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) e i [criteri di accesso a SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) consigliati.</span><span class="sxs-lookup"><span data-stu-id="5554b-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="5554b-127">Passaggio 2: Creare un team privato</span><span class="sxs-lookup"><span data-stu-id="5554b-127">Step 2: Create a private team</span></span>

<span data-ttu-id="5554b-128">Seguire [queste istruzioni](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) per creare un team privato.</span><span class="sxs-lookup"><span data-stu-id="5554b-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="5554b-129">Quando si crea un team privato, le autorizzazioni predefinite sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="5554b-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="5554b-130">Il gruppo di Office 365 per il team (gruppo del team) ha proprietari del gruppo e membri del gruppo</span><span class="sxs-lookup"><span data-stu-id="5554b-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="5554b-131">Per il sito di SharePoint sottostante per il team (sito del team):</span><span class="sxs-lookup"><span data-stu-id="5554b-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="5554b-132">Amministratori raccolta siti è configurato per Proprietari del gruppo del team</span><span class="sxs-lookup"><span data-stu-id="5554b-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="5554b-133">Per il sito del team:</span><span class="sxs-lookup"><span data-stu-id="5554b-133">For the Team Site:</span></span> 
    - <span data-ttu-id="5554b-134">Il gruppo di SharePoint Proprietari del sito del team, con il livello di autorizzazione Controllo completo, è impostato su Proprietari del gruppo del team</span><span class="sxs-lookup"><span data-stu-id="5554b-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="5554b-135">Il gruppo di SharePoint Membri del sito del team, con il livello di autorizzazione Modifica, è impostato su Membri del gruppo del team</span><span class="sxs-lookup"><span data-stu-id="5554b-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="5554b-136">Il gruppo di SharePoint Visitatori del sito del team, con il livello di autorizzazione Lettura, non ha gruppi o account utente</span><span class="sxs-lookup"><span data-stu-id="5554b-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="5554b-137">Ecco le autorizzazioni predefinite per il sito del team.</span><span class="sxs-lookup"><span data-stu-id="5554b-137">Here are the default permissions for the Team Site.</span></span>

![Autorizzazioni predefinite di un sito del team](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="5554b-139">Se si visualizza il \<gruppo di SharePoint nome team > Proprietari per il livello di autorizzazione Modifica, non compare \<nome team > Proprietari.</span><span class="sxs-lookup"><span data-stu-id="5554b-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="5554b-140">Le autorizzazioni risultanti consentono:</span><span class="sxs-lookup"><span data-stu-id="5554b-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="5554b-141">Ai proprietari del gruppo del team di amministrare il sito e avere il controllo completo sul contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="5554b-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="5554b-142">Ai membri del gruppo del team di creare e modificare i file nel sito.</span><span class="sxs-lookup"><span data-stu-id="5554b-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="5554b-143">La manutenzione delle autorizzazioni è uguale alla manutenzione di membri del team e proprietari.</span><span class="sxs-lookup"><span data-stu-id="5554b-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="5554b-144">Ecco la configurazione risultante finora.</span><span class="sxs-lookup"><span data-stu-id="5554b-144">Here’s the resulting configuration so far.</span></span>

![Passaggio 2 della configurazione dello scenario del team sicuro](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="5554b-146">Passaggio 3: Configurare il sito di SharePoint sottostante per aumentare la sicurezza</span><span class="sxs-lookup"><span data-stu-id="5554b-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="5554b-147">Nel sito del team configurare queste impostazioni per le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5554b-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="5554b-148">Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="5554b-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="5554b-149">Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.</span><span class="sxs-lookup"><span data-stu-id="5554b-149">In the **Site permissions** pane,, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="5554b-150">In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**.</span><span class="sxs-lookup"><span data-stu-id="5554b-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="5554b-151">Disattivare **Consenti richieste di accesso** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5554b-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="5554b-152">Con queste impostazioni, la possibilità per i membri del gruppo del team di condividere il sito con altri membri o per i non membri di richiedere l'accesso al sito del team è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5554b-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="5554b-153">Ecco la configurazione risultante finora.</span><span class="sxs-lookup"><span data-stu-id="5554b-153">Here’s the resulting configuration so far.</span></span>

![Passaggio 3 della configurazione dello scenario del team sicuro](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="5554b-155">Passaggio 4: Creare un'etichetta di conservazione e i criteri DLP</span><span class="sxs-lookup"><span data-stu-id="5554b-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="5554b-156">Seguire [queste istruzioni](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) per:</span><span class="sxs-lookup"><span data-stu-id="5554b-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="5554b-157">Creare e pubblicare un'etichetta di conservazione per i dati altamente regolamentati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5554b-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="5554b-158">Configurare il sito del team per l'etichetta di conservazione creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="5554b-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="5554b-159">Creare un criterio DLP per i dati altamente regolamentati che usi l'etichetta di conservazione creata nel passaggio 2 e impedisca agli utenti di inviare file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5554b-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="5554b-160">È anche possibile configurare il criterio per altri requisiti, ad esempio quelli delle normative per il settore sanitario o finanziario, in base ai [modelli di criteri DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="5554b-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="5554b-161">Ecco la configurazione risultante finora.</span><span class="sxs-lookup"><span data-stu-id="5554b-161">Here’s the resulting configuration so far.</span></span>

![Passaggio 4 della configurazione dello scenario del team sicuro](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="5554b-163">Passaggio 5: Creare l'etichetta o la sottoetichetta dell'etichetta per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="5554b-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="5554b-164">Diversamente da un'etichetta di riservatezza per dati altamente regolamentati, che chiunque può applicare a qualsiasi file, un team sicuro deve avere una propria etichetta o sottoetichetta, in modo che i file a cui è assegnata:</span><span class="sxs-lookup"><span data-stu-id="5554b-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="5554b-165">Siano crittografati e la crittografia segua il file.</span><span class="sxs-lookup"><span data-stu-id="5554b-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="5554b-166">Contengano autorizzazioni personalizzate in modo che solo i membri del gruppo del team possano aprirli.</span><span class="sxs-lookup"><span data-stu-id="5554b-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="5554b-167">Per implementare questo ulteriore livello di sicurezza per i file archiviati nel sito del team, è necessario configurare una nuova etichetta di riservatezza, autonoma o come sottoetichetta dell'etichetta generale per i file altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="5554b-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="5554b-168">Solo i membri del gruppo del team la vedranno nell'elenco di etichette.</span><span class="sxs-lookup"><span data-stu-id="5554b-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="5554b-169">Usare un'etichetta di riservatezza quando è necessario un numero limitato di etichette sia per l'uso globale che per i singoli team privati.</span><span class="sxs-lookup"><span data-stu-id="5554b-169">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="5554b-170">Usare una sottoetichetta di riservatezza se si ha un numero elevato di etichette o se si vogliono organizzare le etichette per i team privati sotto l'etichetta per i dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="5554b-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="5554b-171">[Seguire queste istruzioni ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) per configurare un'etichetta separata o una sottoetichetta con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5554b-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="5554b-172">Il nome dell'etichetta contiene il nome del team</span><span class="sxs-lookup"><span data-stu-id="5554b-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="5554b-173">La crittografia è abilitata</span><span class="sxs-lookup"><span data-stu-id="5554b-173">Encryption is enabled.</span></span>
- <span data-ttu-id="5554b-174">Il gruppo del team ha autorizzazioni di creazione condivisa</span><span class="sxs-lookup"><span data-stu-id="5554b-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="5554b-175">Ecco la configurazione risultante con la nuova etichetta.</span><span class="sxs-lookup"><span data-stu-id="5554b-175">Here’s the resulting configuration with the new label.</span></span>

![Passaggio 5 della configurazione dello scenario del team sicuro](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="5554b-177">Ecco la relazione tra l'etichetta di riservatezza e il gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="5554b-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Relazione tra il gruppo del team e le autorizzazioni dell'etichetta](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="5554b-179">Se si configura l'etichetta di riservatezza o la sottoetichetta per le autorizzazioni definite dall'utente o con una data di scadenza, non è possibile aprire il file da Teams o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5554b-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint Online.</span></span> <span data-ttu-id="5554b-180">È necessario usare un'app di Office.</span><span class="sxs-lookup"><span data-stu-id="5554b-180">You must use an Office app.</span></span>
>

## <a name="using-the-team-and-a-sensitivity-label"></a><span data-ttu-id="5554b-181">Uso del team e di un'etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="5554b-181">Using the team and a sensitivity label</span></span>

<span data-ttu-id="5554b-182">I membri del gruppo del team possono accedere al team e a tutte le relative risorse, tra cui chat, riunioni e altre app.</span><span class="sxs-lookup"><span data-stu-id="5554b-182">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="5554b-183">Quando usano file dalla sezione **File** di un canale, i membri del gruppo del team devono assegnare l'etichetta o la sottoetichetta di riservatezza ai file creati per il team sicuro.</span><span class="sxs-lookup"><span data-stu-id="5554b-183">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="5554b-184">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="5554b-184">Here’s an example.</span></span>

![Esempio di etichetta applicata a un file in un team sicuro](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="5554b-186">Quando l'etichetta viene applicata al file, viene protetto.</span><span class="sxs-lookup"><span data-stu-id="5554b-186">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="5554b-187">I membri del gruppo del team possono aprirlo in Teams e collaborare in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="5554b-187">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="5554b-188">È crittografato e include le autorizzazioni di creazione condivisa impostate sui membri del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="5554b-188">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="5554b-189">Se il file esce dal sito e viene inviato a un utente malintenzionato, quest'ultimo dovrà specificare le credenziali di un account utente membro del gruppo del team per aprire il file e visualizzarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5554b-189">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="5554b-190">È possibile vedere i file a cui è assegnata un'etichetta visualizzando una cartella in SharePoint Online e aggiungendo la colonna **Riservatezza** con l'opzione **Aggiungi colonna** in **Mostra/Nascondi colonne**.</span><span class="sxs-lookup"><span data-stu-id="5554b-190">You can see which files have a label assigned by viewing a folder in SharePoint Online and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

## <a name="custom-permissions"></a><span data-ttu-id="5554b-191">Autorizzazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5554b-191">Custom permissions</span></span>

<span data-ttu-id="5554b-192">È anche possibile configurare autorizzazioni del sito di SharePoint personalizzate per il sito del team e, se necessario, l'etichetta di riservatezza corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5554b-192">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="5554b-193">Ecco due esempi.</span><span class="sxs-lookup"><span data-stu-id="5554b-193">Here are two examples based on SQL:</span></span>

### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="5554b-194">Esempio 1: Delega dell'amministrazione del sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5554b-194">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="5554b-195">Se il proprietario del team non ha esperienza nell'amministrazione di SharePoint o vuole delegare l'amministrazione del sito del team, può aggiungere l'account utente di un amministratore di SharePoint all'elenco dei proprietari del team.</span><span class="sxs-lookup"><span data-stu-id="5554b-195">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="5554b-196">L'amministratore di SharePoint, tuttavia, avrà accesso completo al team e a tutte le risorse e potrà aprire un file a cui è applicata l'etichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="5554b-196">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="5554b-197">Per evitare questa assegnazione eccessiva di privilegi, aggiungere l'account utente dell'amministratore di SharePoint al gruppo di SharePoint Proprietari del sito del team nelle impostazioni avanzate di autorizzazione del sito.</span><span class="sxs-lookup"><span data-stu-id="5554b-197">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="5554b-198">L'amministratore di SharePoint potrà amministrare il sito, ma non potrà accedere al team o alle relative risorse, né aprire file con l'etichetta di riservatezza assegnata.</span><span class="sxs-lookup"><span data-stu-id="5554b-198">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="5554b-199">Esempio 2: Consentire l'accesso in sola visualizzazione ai file con etichetta</span><span class="sxs-lookup"><span data-stu-id="5554b-199">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="5554b-200">Se alcuni membri del personale devono esclusivamente visualizzare il contenuto dei file con etichetta nel sito del team, aggiungere i singoli account utente al:</span><span class="sxs-lookup"><span data-stu-id="5554b-200">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="5554b-201">\<gruppo di SharePoint nome team > Visitatori, che per impostazione predefinita ha il livello di autorizzazione Lettura.</span><span class="sxs-lookup"><span data-stu-id="5554b-201">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="5554b-202">Etichetta di riservatezza con le autorizzazioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="5554b-202">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="5554b-203">Ecco le autorizzazioni risultanti nell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="5554b-203">Here are the resulting permissions on the label.</span></span>

![Esempio di autorizzazioni personalizzate per la visualizzazione dei file con etichetta](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="5554b-205">I visitatori del sito potranno accedere direttamente al sito del team e visualizzare il contenuto dei file ai quali è applicata la sottoetichetta.</span><span class="sxs-lookup"><span data-stu-id="5554b-205">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="5554b-206">Tuttavia, dato che non sono membri del gruppo del team, non saranno in grado di accedere al team o alle relative risorse.</span><span class="sxs-lookup"><span data-stu-id="5554b-206">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="5554b-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5554b-207">See also</span></span>

[<span data-ttu-id="5554b-208">Siti di SharePoint per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="5554b-208">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="5554b-209">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="5554b-209">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
