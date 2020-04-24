---
title: Siti di SharePoint per dati altamente regolamentati
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Creare un sito del team di SharePoint sicuro in cui archiviare i file più importanti e sensibili.
ms.openlocfilehash: 97a01275d1d45cb02e66e88f82c95311bcb6fe70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636712"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="3414b-103">Siti di SharePoint per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="3414b-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="3414b-104">*Questo scenario si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3414b-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3414b-p101">Microsoft 365 Enterprise include una gamma completa di servizi basati sul cloud, che permettono di creare, archiviare, proteggere e gestire i dati altamente regolamentati archiviati nei file, tra cui quelli:</span><span class="sxs-lookup"><span data-stu-id="3414b-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="3414b-107">Soggetti alle normative internazionali.</span><span class="sxs-lookup"><span data-stu-id="3414b-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="3414b-108">I dati più importanti per l'organizzazione, ad esempio segreti finanziari o informazioni sulle risorse umane e strategia dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3414b-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="3414b-109">Uno scenario simile che usa Microsoft Teams è disponibile [qui](secure-teams-highly-regulated-data-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="3414b-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="3414b-110">Affinché una scenario Microsoft 365 Enterprise basata sul cloud soddisfi le esigenze aziendali, è necessario:</span><span class="sxs-lookup"><span data-stu-id="3414b-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="3414b-111">Archiviare i file (documenti, presentazioni, fogli di calcolo e così via) in un sito del team di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3414b-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="3414b-112">Bloccare il sito per impedire:</span><span class="sxs-lookup"><span data-stu-id="3414b-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="3414b-113">Accesso per gli utenti che non sono membri del gruppo di Microsoft 365 per il sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-113">Access to users who are not members of the Microsoft 365 group for the site.</span></span>
  - <span data-ttu-id="3414b-114">I membri del sito dalla concessione dell'accesso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3414b-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="3414b-115">I non-membri del sito dalla richiesta di accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="3414b-116">Configurare un'etichetta di conservazione per i siti di SharePoint come metodo predefinito per impedire agli utenti di inviare file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3414b-116">Configure a retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="3414b-117">Crittografare i file più sensibili del sito con crittografia che segue il file.</span><span class="sxs-lookup"><span data-stu-id="3414b-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="3414b-118">Aggiungere autorizzazioni per i file più sensibili, in modo che, anche in caso di condivisione all'esterno del sito, all'apertura vengano richieste le credenziali valide di un account utente autorizzato.</span><span class="sxs-lookup"><span data-stu-id="3414b-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="3414b-119">La tabella seguente associa i requisiti di questo scenario a una funzionalità di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3414b-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="3414b-120">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="3414b-120">**Requirement**</span></span> | <span data-ttu-id="3414b-121">**Funzionalità di Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="3414b-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="3414b-122">Archiviare file</span><span class="sxs-lookup"><span data-stu-id="3414b-122">Store files</span></span> | <span data-ttu-id="3414b-123">Siti del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3414b-123">SharePoint team sites</span></span> |
| <span data-ttu-id="3414b-124">Bloccare il sito</span><span class="sxs-lookup"><span data-stu-id="3414b-124">Lock down the site</span></span> | <span data-ttu-id="3414b-125">Autorizzazioni per i gruppi di Microsoft 365 e il sito del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3414b-125">Microsoft 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="3414b-126">Etichettare i file del sito</span><span class="sxs-lookup"><span data-stu-id="3414b-126">Label the files of the site</span></span> | <span data-ttu-id="3414b-127">Etichette di conservazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3414b-127">Microsoft 365 retention labels</span></span> |
| <span data-ttu-id="3414b-128">Bloccare gli utenti quando inviano file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3414b-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="3414b-129">Criteri di prevenzione perdita dati (DLP)</span><span class="sxs-lookup"><span data-stu-id="3414b-129">Data Loss Prevention (DLP) policies</span></span> |
| <span data-ttu-id="3414b-130">Crittografare tutti i file del sito</span><span class="sxs-lookup"><span data-stu-id="3414b-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="3414b-131">Etichette o etichette secondarie di riservatezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3414b-131">Microsoft 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="3414b-132">Aggiungere autorizzazioni ai file del sito</span><span class="sxs-lookup"><span data-stu-id="3414b-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="3414b-133">Etichette o etichette secondarie di riservatezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3414b-133">Microsoft 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="3414b-134">Ecco una configurazione di esempio per un sito di SharePoint sicuro.</span><span class="sxs-lookup"><span data-stu-id="3414b-134">Here is an example configuration for a secure SharePoint site.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="3414b-136">Questo scenario richiede di aver già implementato:</span><span class="sxs-lookup"><span data-stu-id="3414b-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="3414b-137">La fase [Identità](identity-infrastructure.md) e i passaggi 1 e 2 della fase [Protezione delle informazioni](infoprotect-infrastructure.md) dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="3414b-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="3414b-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="3414b-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="3414b-139">Le fasi seguenti illustrano come progettare, configurare e facilitare l'adozione dei siti di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="3414b-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a> <span data-ttu-id="3414b-140">Per un riepilogo di una pagina per questo scenario, vedere il [poster Siti di SharePoint per dati altamente regolamentati](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="3414b-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="3414b-141">[![Poster Siti di SharePoint per dati altamente regolamentati](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="3414b-141">[![SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="3414b-142">È anche possibile scaricare il poster in formato [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) o [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).</span><span class="sxs-lookup"><span data-stu-id="3414b-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="3414b-143">Prerequisiti di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="3414b-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="3414b-144">Per proteggere l'accesso ai siti di SharePoint, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint consigliati](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3414b-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="3414b-145">Fase 1: progettazione</span><span class="sxs-lookup"><span data-stu-id="3414b-145">Phase 1: Design</span></span>

<span data-ttu-id="3414b-146">Per creare un sito di SharePoint per i dati altamente regolamentati, è necessario prima di tutto identificarne lo scopo.</span><span class="sxs-lookup"><span data-stu-id="3414b-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="3414b-147">Ad esempio, il reparto ricerca e sviluppo di un'azienda del settore manifatturiero ha bisogno di un sito di SharePoint per archiviare le specifiche di progettazione attuali per i prodotti esistenti e come luogo in cui collaborare su nuovi prodotti.</span><span class="sxs-lookup"><span data-stu-id="3414b-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="3414b-148">Solo i membri del reparto di ricerca e sviluppo e i dirigenti selezionati saranno autorizzati ad accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="3414b-149">Questo scopo, ad esempio determinerà l'identificazione di elementi essenziali quali:</span><span class="sxs-lookup"><span data-stu-id="3414b-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="3414b-150">L'etichetta di conservazione da assegnare alla sezione Documenti del sito e i criteri DLP per l'etichetta</span><span class="sxs-lookup"><span data-stu-id="3414b-150">The retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="3414b-151">Le impostazioni di una etichetta secondaria di riservatezza che gli utenti applicano ai file altamente sensibili archiviati nel sito</span><span class="sxs-lookup"><span data-stu-id="3414b-151">The settings of a sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="3414b-152">Una volta determinate queste impostazioni, usarle per configurare il sito nella Fase 2.</span><span class="sxs-lookup"><span data-stu-id="3414b-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-microsoft-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="3414b-153">Passaggio 1: criteri DLP ed etichette di conservazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3414b-153">Step 1 Microsoft 365 retention labels and DLP policies</span></span>

<span data-ttu-id="3414b-154">Quando vengono applicate alla sezione Documenti di un sito del team di SharePoint, le etichette di conservazione forniscono un metodo predefinito per classificare tutti i file archiviati nel sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-154">When applied to the Documents portion of a SharePoint team site, retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="3414b-155">Per i siti di SharePoint per dati altamente regolamentati, è necessario determinare quale etichetta di conservazione usare.</span><span class="sxs-lookup"><span data-stu-id="3414b-155">For SharePoint sites for highly regulated data, you need to determine which retention label to use.</span></span>

<span data-ttu-id="3414b-156">Per considerazioni sulla progettazione delle etichette, vedere [Classificazione ed etichette di Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="3414b-156">For the design considerations of labels, see [Microsoft 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="3414b-p103">Per proteggere le informazioni sensibili e prevenirne la divulgazione accidentale o intenzionale, si utilizzano criteri DLP. Per ulteriori informazioni, vedere [Panoramica](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="3414b-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="3414b-159">Per i siti di SharePoint, è necessario configurare un criterio DLP per l'etichetta di conservazione assegnata al sito in modo da bloccare gli utenti quando provano a condividere file con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="3414b-159">For SharePoint sites, you must configure a DLP policy for the retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-microsoft-365-sensitivity-sublabel"></a><span data-ttu-id="3414b-160">Passaggio 2: l'etichetta secondaria di riservatezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3414b-160">Step 2: Your Microsoft 365 sensitivity sublabel</span></span>

<span data-ttu-id="3414b-161">Per fornire la crittografia e un set di autorizzazioni per i file più sensibili, gli utenti devono applicare un'etichetta o un'etichetta secondaria di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="3414b-161">To provide encryption and a set of permissions to your most sensitive files, users must apply a sensitivity label or sublabel.</span></span> <span data-ttu-id="3414b-162">Una sottoetichetta si trova sotto un'etichetta esistente.</span><span class="sxs-lookup"><span data-stu-id="3414b-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="3414b-163">Usare un'etichetta di riservatezza quando è necessario un numero limitato di etichette sia per l'uso globale che per i singoli team privati.</span><span class="sxs-lookup"><span data-stu-id="3414b-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="3414b-164">Usare una sottoetichetta di riservatezza se si ha un numero elevato di etichette o se si vogliono organizzare le etichette per siti sicuri sotto l'etichetta per i dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="3414b-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="3414b-165">Le impostazioni dell'etichetta o della sottoetichetta applicata seguono il file.</span><span class="sxs-lookup"><span data-stu-id="3414b-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="3414b-166">Anche se dovesse uscire dal sito, solo gli account utente autenticati con autorizzazioni adeguate potrebbero aprirlo.</span><span class="sxs-lookup"><span data-stu-id="3414b-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="3414b-167">Risultati della progettazione</span><span class="sxs-lookup"><span data-stu-id="3414b-167">Design results</span></span>

<span data-ttu-id="3414b-168">È stato determinato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3414b-168">You have determined the following:</span></span>

- <span data-ttu-id="3414b-169">L'etichetta di conservazione appropriata e il criterio DLP associato</span><span class="sxs-lookup"><span data-stu-id="3414b-169">The appropriate retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="3414b-170">Le impostazioni delle etichette secondarie di riservatezza che includono crittografia e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3414b-170">The settings of the sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="3414b-171">Fase 2: Configurazione</span><span class="sxs-lookup"><span data-stu-id="3414b-171">Phase 2: Configure</span></span>

<span data-ttu-id="3414b-172">In questa fase, le impostazioni determinate nella Fase 1 vengono implementate per creare un sito di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="3414b-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-microsoft-365-group"></a><span data-ttu-id="3414b-173">Passaggio 1: creare un sito del team di SharePoint privato con proprietari e membri del gruppo di Microsoft 365 corrispondente</span><span class="sxs-lookup"><span data-stu-id="3414b-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Microsoft 365 group</span></span>

<span data-ttu-id="3414b-174">Seguire [queste istruzioni]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) per creare un sito del team di SharePoint privato.</span><span class="sxs-lookup"><span data-stu-id="3414b-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="3414b-175">Passaggio 2: Configurare altre impostazioni delle autorizzazioni per il sito del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3414b-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="3414b-176">Nel sito di SharePoint configurare queste impostazioni per le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3414b-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="3414b-177">Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="3414b-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="3414b-178">Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.</span><span class="sxs-lookup"><span data-stu-id="3414b-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="3414b-179">In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**.</span><span class="sxs-lookup"><span data-stu-id="3414b-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="3414b-180">Disattivare **Consenti richieste di accesso** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3414b-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="3414b-181">Con queste impostazioni, la possibilità per i membri del gruppo di siti di condividere il sito con altri membri o per i non membri di richiedere l'accesso al sito è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3414b-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-a-retention-label"></a><span data-ttu-id="3414b-182">Passaggio 3: configurare il sito per un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="3414b-182">Step 3: Configure the site for a retention label</span></span>

<span data-ttu-id="3414b-183">Attenersi alle istruzioni riportate in [Proteggere i file di SharePoint con le etichette e la prevenzione della perdita dei dati](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) per:</span><span class="sxs-lookup"><span data-stu-id="3414b-183">Use the instructions in [Protect SharePoint files with labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="3414b-184">Creare e pubblicare un'etichetta di conservazione per i dati altamente regolamentati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3414b-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="3414b-185">Configurare il sito per l'etichetta di conservazione creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3414b-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="3414b-186">Creare un criterio DLP per i dati altamente regolamentati che usi l'etichetta di conservazione creata nel passaggio 2 e impedisca agli utenti di inviare file all'esterno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3414b-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-a-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="3414b-187">Passaggio 4: creare un'etichetta secondaria di riservatezza per il sito</span><span class="sxs-lookup"><span data-stu-id="3414b-187">Step 4: Create a sensitivity sublabel for the site</span></span>

<span data-ttu-id="3414b-188">Diversamente da un'etichetta di riservatezza per dati altamente regolamentati, che chiunque può applicare a qualsiasi file, un sito sicuro deve avere una propria sottoetichetta, in modo che i file a cui è assegnata la sottoetichetta:</span><span class="sxs-lookup"><span data-stu-id="3414b-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="3414b-189">Siano crittografati e la crittografia segua il file.</span><span class="sxs-lookup"><span data-stu-id="3414b-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="3414b-190">Contengano autorizzazioni personalizzate in modo che solo i membri del gruppo del sito possano aprirli.</span><span class="sxs-lookup"><span data-stu-id="3414b-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="3414b-191">Per implementare questo ulteriore livello di sicurezza per i file archiviati nel sito, è necessario configurare una nuova etichetta di riservatezza oppure una sottoetichetta dell'etichetta generale per i file altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="3414b-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="3414b-192">La vedranno solo i membri del gruppo per il sito, nell'elenco di sottoetichette relative all'etichetta per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="3414b-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="3414b-193">Usare le istruzioni disponibili [qui](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) per configurare un'etichetta o una sottoetichetta dell'etichetta che si usa per i file altamente regolamentati, con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3414b-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="3414b-194">Il nome dell'etichetta o della sottoetichetta contiene il nome del sito, per semplificare l'associazione quando si assegna l'etichetta o la sottoetichetta a un file.</span><span class="sxs-lookup"><span data-stu-id="3414b-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="3414b-195">La crittografia è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3414b-195">Encryption is enabled.</span></span>
- <span data-ttu-id="3414b-196">Il gruppo di siti ha autorizzazioni di creazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="3414b-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="3414b-197">Risultati della configurazione</span><span class="sxs-lookup"><span data-stu-id="3414b-197">Configuration results</span></span>

<span data-ttu-id="3414b-198">È stato configurato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3414b-198">You have configured the following:</span></span>

- <span data-ttu-id="3414b-199">Impostazioni di autorizzazione più restrittive nel sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3414b-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="3414b-200">Un'etichetta di conservazione assegnata alla sezione Documenti del sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3414b-200">A retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="3414b-201">Un criterio DLP per l'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="3414b-201">A DLP policy for the retention label</span></span>
- <span data-ttu-id="3414b-202">Un'etichetta o un'etichetta secondaria di riservatezza che gli utenti possono applicare ai file più sensibili archiviati nel sito, che crittografa il file e consente solo l'accesso in modalità di creazione condivisa ai membri del gruppo del sito del team</span><span class="sxs-lookup"><span data-stu-id="3414b-202">A sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="3414b-203">Ecco la configurazione risultante che usa una sottoetichetta dell'etichetta per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="3414b-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![Siti di SharePoint per lo scenario dei dati altamente regolamentati](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="3414b-205">Ecco un esempio di un utente che ha applicato la sottoetichetta a un file archiviato nel sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="3414b-207">Fase 3: Incoraggiare l'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="3414b-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="3414b-208">Un sito di SharePoint per dati altamente regolamentati può proteggere tali dati solo se viene usato regolarmente per l'archiviazione e l'accesso ai file sensibili.</span><span class="sxs-lookup"><span data-stu-id="3414b-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="3414b-209">Questa è la fase più difficile, perché dipende dal cambiamento di abitudini degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3414b-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="3414b-210">Ad esempio, i dipendenti che sono abituati ad archiviare file sensibili in unità USB o soluzioni di archiviazione basate sul cloud personale dovranno ora archiviarli esclusivamente in un sito di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="3414b-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="3414b-211">Passaggio 1: formare gli utenti</span><span class="sxs-lookup"><span data-stu-id="3414b-211">Step 1: Train your users</span></span>

<span data-ttu-id="3414b-212">Dopo aver completato la configurazione, formare gli utenti membri del sito:</span><span class="sxs-lookup"><span data-stu-id="3414b-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="3414b-213">Sull'importanza di usare il nuovo sito per proteggere file preziosi e le conseguenze di una perdita di dati altamente regolamentati, come implicazioni legali, sanzioni per inadempimento alle normative, ransomware o perdita di vantaggi competitivi.</span><span class="sxs-lookup"><span data-stu-id="3414b-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="3414b-214">Come accedere al sito e ai suoi file.</span><span class="sxs-lookup"><span data-stu-id="3414b-214">How to access the site and its files.</span></span>
- <span data-ttu-id="3414b-215">Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.</span><span class="sxs-lookup"><span data-stu-id="3414b-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="3414b-216">In che modo i criteri DLP impediscono di condividere i file esternamente.</span><span class="sxs-lookup"><span data-stu-id="3414b-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="3414b-217">Come contrassegnare i file più sensibili con l'etichetta o la sottoetichetta del sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="3414b-218">In che modo l'etichetta o la sottoetichetta protegge un file anche se viene diffuso all'esterno del sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="3414b-219">Questa formazione dovrebbe includere esercizi pratici in modo che gli utenti possano sperimentare queste operazioni e i loro risultati.</span><span class="sxs-lookup"><span data-stu-id="3414b-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="3414b-220">Passaggio 2: Effettuare revisioni periodiche sull'utilizzo e sui file</span><span class="sxs-lookup"><span data-stu-id="3414b-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="3414b-221">Nelle settimane successive alla formazione, l'amministratore di SharePoint per il sito di SharePoint può:</span><span class="sxs-lookup"><span data-stu-id="3414b-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="3414b-222">Analizzare l'utilizzo del sito e confrontarlo con le aspettative di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="3414b-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="3414b-223">Verificare che i file altamente sensibili siano stati etichettati correttamente con l'etichetta o la sottoetichetta di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="3414b-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="3414b-224">È possibile vedere i file a cui è assegnata un'etichetta visualizzando una cartella in SharePoint e aggiungendo la colonna **Riservatezza** con l'opzione **Aggiungi colonna** in **Mostra/Nascondi colonne**.</span><span class="sxs-lookup"><span data-stu-id="3414b-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="3414b-225">Ripetere la formazione degli utenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="3414b-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="3414b-226">Risultati dell'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="3414b-226">User adoption results</span></span>

<span data-ttu-id="3414b-227">I file altamente regolamentati vengono archiviati esclusivamente nei siti di SharePoint per dati altamente regolamentati e ai file più sensibili è applicata l'etichetta o la sottoetichetta di riservatezza per il sito.</span><span class="sxs-lookup"><span data-stu-id="3414b-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="3414b-228">Utilizzo di un sito di SharePoint per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="3414b-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="3414b-229">Contoso Corporation è un conglomerato industriale fittizio ma rappresentativo a livello internazionale.</span><span class="sxs-lookup"><span data-stu-id="3414b-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="3414b-230">Vedere il modo in cui Contoso ha sviluppato, configurato e quindi ha guidato l'adozione di un [sito di SharePoint protetto](contoso-sharepoint-online-site-for-highly-confidential-assets.md) per i team di ricerca a Parigi, Mosca, New York, Pechino e Bengaluru.</span><span class="sxs-lookup"><span data-stu-id="3414b-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="3414b-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3414b-231">See also</span></span>

[<span data-ttu-id="3414b-232">Teams per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="3414b-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="3414b-233">Carichi di lavoro e scenari di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3414b-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="3414b-234">[Raccolta di produttività di Microsoft 365](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="3414b-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="3414b-235">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="3414b-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
