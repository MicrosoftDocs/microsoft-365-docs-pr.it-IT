---
title: Siti di SharePoint per dati altamente regolamentati
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un sito del team di SharePoint sicuro in cui archiviare i file più importanti e sensibili.
ms.openlocfilehash: ece6547ba596fe53c4f3b3f6bfbaa6570a724c6a
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437826"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="1885d-103">Siti di SharePoint per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="1885d-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="1885d-104">*Questo scenario si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1885d-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="1885d-p101">Microsoft 365 Enterprise include una gamma completa di servizi basati sul cloud, che permettono di creare, archiviare, proteggere e gestire i dati altamente regolamentati archiviati nei file, tra cui quelli:</span><span class="sxs-lookup"><span data-stu-id="1885d-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="1885d-107">Soggetti alle normative internazionali.</span><span class="sxs-lookup"><span data-stu-id="1885d-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="1885d-108">I dati più importanti per l'organizzazione, ad esempio segreti finanziari o informazioni sulle risorse umane e strategia dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1885d-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="1885d-109">Uno scenario simile che usa Microsoft Teams è in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="1885d-109">A similar scenario using Microsoft Teams is in development.</span></span>
>

<span data-ttu-id="1885d-110">Affinché una scenario Microsoft 365 Enterprise basata sul cloud soddisfi le esigenze aziendali, è necessario:</span><span class="sxs-lookup"><span data-stu-id="1885d-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="1885d-111">Archiviare i file (documenti, presentazioni, fogli di calcolo e così via) in un sito del team di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1885d-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="1885d-112">Bloccare il sito per impedire:</span><span class="sxs-lookup"><span data-stu-id="1885d-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="1885d-113">L'accesso a utenti che non siano membri del gruppo di Office 365 per il sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="1885d-114">I membri del sito dalla concessione dell'accesso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="1885d-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="1885d-115">I non-membri del sito dalla richiesta di accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="1885d-116">Configurare un'etichetta di conservazione di Office 365 per i siti di SharePoint come modo predefinito per impedire agli utenti di inviare file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1885d-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="1885d-117">Crittografare i file più sensibili del sito con crittografia che segue il file.</span><span class="sxs-lookup"><span data-stu-id="1885d-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="1885d-118">Aggiungere autorizzazioni per i file più sensibili, in modo che, anche in caso di condivisione all'esterno del sito, all'apertura vengano richieste le credenziali valide di un account utente autorizzato.</span><span class="sxs-lookup"><span data-stu-id="1885d-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="1885d-119">La tabella seguente associa i requisiti di questo scenario a una funzionalità di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1885d-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="1885d-120">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="1885d-120">**Requirement**</span></span> | <span data-ttu-id="1885d-121">**Funzionalità di Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="1885d-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="1885d-122">Archiviare file</span><span class="sxs-lookup"><span data-stu-id="1885d-122">Store files</span></span> | <span data-ttu-id="1885d-123">Siti del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="1885d-123">SharePoint team sites</span></span> |
| <span data-ttu-id="1885d-124">Bloccare il sito</span><span class="sxs-lookup"><span data-stu-id="1885d-124">Lock down the site</span></span> | <span data-ttu-id="1885d-125">Autorizzazioni per gruppi di Azure Active Directory (Azure AD) e sito del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="1885d-125">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="1885d-126">Etichettare i file del sito</span><span class="sxs-lookup"><span data-stu-id="1885d-126">Label the files of the site</span></span> | <span data-ttu-id="1885d-127">Etichette di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="1885d-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="1885d-128">Bloccare gli utenti quando inviano file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1885d-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="1885d-129">Criteri di prevenzione della perdita di dati (DLP) in Office 365</span><span class="sxs-lookup"><span data-stu-id="1885d-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="1885d-130">Crittografare tutti i file del sito</span><span class="sxs-lookup"><span data-stu-id="1885d-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="1885d-131">Sottoetichette di riservatezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="1885d-131">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="1885d-132">Aggiungere autorizzazioni ai file del sito</span><span class="sxs-lookup"><span data-stu-id="1885d-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="1885d-133">Sottoetichette di riservatezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="1885d-133">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="1885d-134">Ecco la configurazione per un sito di SharePoint sicuro.</span><span class="sxs-lookup"><span data-stu-id="1885d-134">Here is the configuration for a secure SharePoint site.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="1885d-136">Questo scenario richiede di aver già implementato:</span><span class="sxs-lookup"><span data-stu-id="1885d-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="1885d-137">La fase [Identità](identity-infrastructure.md) e i passaggi 1 e 2 della fase [Protezione delle informazioni](infoprotect-infrastructure.md) dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="1885d-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="1885d-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="1885d-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="1885d-139">Le fasi seguenti illustrano come progettare, configurare e facilitare l'adozione dei siti di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="1885d-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<span data-ttu-id="1885d-140">Per vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha progettato un sito di SharePoint per i propri team di ricerca, vedere questo [esempio di configurazione](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="1885d-140">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="1885d-141">Prerequisiti di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="1885d-141">Identity and device access prerequisites</span></span>

<span data-ttu-id="1885d-142">Per proteggere l'accesso ai siti di SharePoint, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint consigliati](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1885d-142">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="1885d-143">Fase 1: progettazione</span><span class="sxs-lookup"><span data-stu-id="1885d-143">Phase 1: Design</span></span>

<span data-ttu-id="1885d-144">Per creare un sito di SharePoint per i dati altamente regolamentati, è necessario prima di tutto identificarne lo scopo.</span><span class="sxs-lookup"><span data-stu-id="1885d-144">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="1885d-145">Ad esempio, il reparto ricerca e sviluppo di un'azienda del settore manifatturiero ha bisogno di un sito di SharePoint per archiviare le specifiche di progettazione attuali per i prodotti esistenti e come luogo in cui collaborare su nuovi prodotti.</span><span class="sxs-lookup"><span data-stu-id="1885d-145">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="1885d-146">Solo i membri del reparto di ricerca e sviluppo e i dirigenti selezionati saranno autorizzati ad accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-146">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="1885d-147">Questo scopo, ad esempio determinerà l'identificazione di elementi essenziali quali:</span><span class="sxs-lookup"><span data-stu-id="1885d-147">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="1885d-148">L'etichetta di conservazione di Office 365 da assegnare alla sezione Documenti del sito e i criteri DLP per l'etichetta</span><span class="sxs-lookup"><span data-stu-id="1885d-148">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="1885d-149">Le impostazioni di una sottoetichetta di riservatezza di Office 365 che gli utenti applicano ai file altamente sensibili archiviati nel sito</span><span class="sxs-lookup"><span data-stu-id="1885d-149">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="1885d-150">Una volta determinate queste impostazioni, usarle per configurare il sito nella Fase 2.</span><span class="sxs-lookup"><span data-stu-id="1885d-150">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="1885d-151">Passaggio 1: Etichette di conservazione di Office 365 e criteri DLP</span><span class="sxs-lookup"><span data-stu-id="1885d-151">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="1885d-152">Quando vengono applicate alla sezione Documenti di un sito del team di SharePoint, le etichette di conservazione di Office 365 forniscono un metodo predefinito per classificare tutti i file archiviati nel sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-152">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="1885d-153">Per i siti di SharePoint per dati altamente regolamentati, è necessario determinare quale etichetta di conservazione di Office 365 usare.</span><span class="sxs-lookup"><span data-stu-id="1885d-153">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="1885d-154">Per considerazioni sulla progettazione delle etichette di Office 365, vedere [Classificazione ed etichette di Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="1885d-154">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="1885d-p103">Per proteggere le informazioni sensibili e prevenirne la divulgazione accidentale o intenzionale, si utilizzano criteri DLP. Per ulteriori informazioni, vedere [Panoramica](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="1885d-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="1885d-157">Per i siti di SharePoint, è necessario configurare un criterio DLP per l'etichetta di conservazione di Office 365 assegnata al sito per bloccare gli utenti quando provano a condividere file con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="1885d-157">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="1885d-158">Passaggio 2: Sottoetichetta di riservatezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="1885d-158">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="1885d-159">Per fornire la crittografia e un set di autorizzazioni per i file più sensibili, gli utenti devono applicare una sottoetichetta di riservatezza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="1885d-159">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="1885d-160">Una sottoetichetta esiste sotto un'etichetta esistente.</span><span class="sxs-lookup"><span data-stu-id="1885d-160">A sublabel exists under an existing label.</span></span> <span data-ttu-id="1885d-161">Ad esempio, è possibile creare una sottoetichetta Ricerca e sviluppo sotto l'etichetta Altamente regolamentato.</span><span class="sxs-lookup"><span data-stu-id="1885d-161">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="1885d-162">Per i siti di SharePoint per i dati altamente regolamentati, è necessario configurare le autorizzazioni in modo che solo i membri del sito possano aprire e modificare il file a cui è allegata la sottoetichetta.</span><span class="sxs-lookup"><span data-stu-id="1885d-162">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="1885d-163">Le impostazioni della sottoetichetta applicata seguono il file.</span><span class="sxs-lookup"><span data-stu-id="1885d-163">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="1885d-164">Anche se dovesse uscire dal sito, solo gli account utente autenticati con autorizzazioni adeguate potrebbero aprirlo.</span><span class="sxs-lookup"><span data-stu-id="1885d-164">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="1885d-165">Risultati della progettazione</span><span class="sxs-lookup"><span data-stu-id="1885d-165">Design results</span></span>

<span data-ttu-id="1885d-166">È stato determinato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1885d-166">You have determined the following:</span></span>

- <span data-ttu-id="1885d-167">L'etichetta di conservazione appropriata di Office 365 e il criterio DLP ad essa associato</span><span class="sxs-lookup"><span data-stu-id="1885d-167">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="1885d-168">Le impostazioni della sottoetichetta di riservatezza di Office 365 che includono crittografia e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1885d-168">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="1885d-169">Fase 2: Configurazione</span><span class="sxs-lookup"><span data-stu-id="1885d-169">Phase 2: Configure</span></span>

<span data-ttu-id="1885d-170">In questa fase, le impostazioni determinate nella Fase 1 vengono implementate per creare un sito di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="1885d-170">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="1885d-171">Passaggio 1: Creare un sito del team di SharePoint privato con proprietari e membri del gruppo di Office 365 corrispondente</span><span class="sxs-lookup"><span data-stu-id="1885d-171">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="1885d-172">Seguire [queste istruzioni]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) per creare un sito del team di SharePoint privato.</span><span class="sxs-lookup"><span data-stu-id="1885d-172">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="1885d-173">Passaggio 2: Configurare altre impostazioni delle autorizzazioni per il sito del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="1885d-173">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="1885d-174">Nel sito di SharePoint configurare queste impostazioni per le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1885d-174">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="1885d-175">Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="1885d-175">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="1885d-176">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="1885d-176">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="1885d-177">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="1885d-177">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="1885d-178">Nella finestra di dialogo **Impostazioni richieste di accesso** deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti richieste di accesso** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1885d-178">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="1885d-179">Con queste impostazioni, la possibilità per i membri del gruppo di siti di condividere il sito con altri membri o per i non membri di richiedere l'accesso al sito è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="1885d-179">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="1885d-180">Passaggio 3: Configurare il sito per un'etichetta di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="1885d-180">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="1885d-181">Attenersi alle istruzioni riportate in [Proteggere i file di SharePoint con le etichette di Office 365 e la prevenzione della perdita dei dati](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) per:</span><span class="sxs-lookup"><span data-stu-id="1885d-181">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="1885d-182">Creare e pubblicare un'etichetta di conservazione per i dati altamente regolamentati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="1885d-182">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="1885d-183">Configurare il sito per l'etichetta di conservazione creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="1885d-183">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="1885d-184">Creare un criterio DLP per i dati altamente regolamentati che usi l'etichetta di conservazione creata nel passaggio 2 e impedisca agli utenti di inviare file all'esterno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1885d-184">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="1885d-185">Passaggio 4: Creare una sottoetichetta di riservatezza di Office 365 per il sito</span><span class="sxs-lookup"><span data-stu-id="1885d-185">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="1885d-186">Diversamente da un'etichetta di riservatezza per dati altamente regolamentati, che chiunque può applicare a qualsiasi file, un sito sicuro deve avere una propria sottoetichetta, in modo che i file a cui è assegnata la sottoetichetta:</span><span class="sxs-lookup"><span data-stu-id="1885d-186">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="1885d-187">Siano crittografati e la crittografia segua il file.</span><span class="sxs-lookup"><span data-stu-id="1885d-187">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="1885d-188">Contengano autorizzazioni personalizzate in modo che solo i membri del gruppo del sito possano aprirli.</span><span class="sxs-lookup"><span data-stu-id="1885d-188">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="1885d-189">Per implementare questo ulteriore livello di sicurezza per i file archiviati nel sito, è necessario configurare una nuova etichetta di riservatezza, ossia una sottoetichetta dell'etichetta generale per i file altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="1885d-189">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="1885d-190">La vedranno solo i membri del gruppo per il sito, nell'elenco di sottoetichette per l'etichetta altamente regolamentata.</span><span class="sxs-lookup"><span data-stu-id="1885d-190">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="1885d-191">Usare le istruzioni disponibili [qui](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) per configurare una sottoetichetta dell'etichetta che si usa per i file altamente regolamentati, con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1885d-191">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="1885d-192">Il nome della sottoetichetta contiene il nome del sito, per semplificare l'associazione quando si assegna la sottoetichetta a un file.</span><span class="sxs-lookup"><span data-stu-id="1885d-192">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="1885d-193">La crittografia è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1885d-193">Encryption is enabled.</span></span>
- <span data-ttu-id="1885d-194">Il gruppo di siti ha autorizzazioni di creazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="1885d-194">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="1885d-195">Risultati della configurazione</span><span class="sxs-lookup"><span data-stu-id="1885d-195">Configuration results</span></span>

<span data-ttu-id="1885d-196">È stato configurato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1885d-196">You have configured the following:</span></span>

- <span data-ttu-id="1885d-197">Impostazioni di autorizzazione più restrittive nel sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="1885d-197">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="1885d-198">Un'etichetta di conservazione di Office 365 assegnata alla sezione Documenti del sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="1885d-198">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="1885d-199">Un criterio DLP per l'etichetta di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="1885d-199">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="1885d-200">Una sottoetichetta di riservatezza di Office 365 che gli utenti possono applicare ai file più sensibili archiviati nel sito, che crittografa il file e consente solo l'accesso in modalità di creazione condivisa ai membri del gruppo del sito del team</span><span class="sxs-lookup"><span data-stu-id="1885d-200">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="1885d-201">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="1885d-201">Here is the resulting configuration.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="1885d-203">Ecco un esempio di un utente che ha applicato la sottoetichetta di riservatezza a un file archiviato nel sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-203">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="1885d-205">Fase 3: Incoraggiare l'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="1885d-205">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="1885d-206">Un sito di SharePoint per dati altamente regolamentati può proteggere tali dati solo se viene usato regolarmente per l'archiviazione e l'accesso ai file sensibili.</span><span class="sxs-lookup"><span data-stu-id="1885d-206">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="1885d-207">Questa è la fase più difficile, perché dipende dal cambiamento di abitudini degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1885d-207">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="1885d-208">Ad esempio, i dipendenti che sono abituati ad archiviare file sensibili in unità USB o soluzioni di archiviazione basate sul cloud personale dovranno ora archiviarli esclusivamente in un sito di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="1885d-208">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="1885d-209">Passaggio 1: Formazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="1885d-209">Step 1: Train your users</span></span>

<span data-ttu-id="1885d-210">Dopo aver completato la configurazione, formare gli utenti membri dei gruppi di accesso al sito:</span><span class="sxs-lookup"><span data-stu-id="1885d-210">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="1885d-211">Sull'importanza di usare il nuovo sito per proteggere file preziosi e le conseguenze di una perdita di dati altamente regolamentati, come implicazioni legali, sanzioni per inadempimento alle normative, ransomware o perdita di vantaggi competitivi.</span><span class="sxs-lookup"><span data-stu-id="1885d-211">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="1885d-212">Come accedere al sito e ai suoi file.</span><span class="sxs-lookup"><span data-stu-id="1885d-212">How to access the site and its files.</span></span>
- <span data-ttu-id="1885d-213">Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.</span><span class="sxs-lookup"><span data-stu-id="1885d-213">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="1885d-214">In che modo i criteri DLP impediscono di condividere i file esternamente.</span><span class="sxs-lookup"><span data-stu-id="1885d-214">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="1885d-215">Come contrassegnare i file più sensibili con la sottoetichetta del sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-215">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="1885d-216">Come la sottoetichetta protegge un file anche se fuoriesce dal sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-216">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="1885d-217">Questa formazione dovrebbe includere esercizi pratici in modo che gli utenti possano sperimentare queste operazioni e i loro risultati.</span><span class="sxs-lookup"><span data-stu-id="1885d-217">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="1885d-218">Passaggio 2: Effettuare revisioni periodiche sull'utilizzo e sui file</span><span class="sxs-lookup"><span data-stu-id="1885d-218">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="1885d-219">Nelle settimane successive alla formazione, l'amministratore di SharePoint per il sito di SharePoint può:</span><span class="sxs-lookup"><span data-stu-id="1885d-219">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="1885d-220">Analizzare l'utilizzo del sito e confrontarlo con le aspettative di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="1885d-220">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="1885d-221">Verificare che i file riservati siano stati etichettati correttamente con l'etichetta di riservatezza secondaria.</span><span class="sxs-lookup"><span data-stu-id="1885d-221">Verify that highly sensitive files have been properly labeled with the sensitivity sublabel.</span></span>

<span data-ttu-id="1885d-222">Ripetere la formazione degli utenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="1885d-222">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="1885d-223">Risultati dell'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="1885d-223">User adoption results</span></span>

<span data-ttu-id="1885d-224">I file con elevato livello di regolamentazione vengono archiviati esclusivamente nei siti di SharePoint per dati altamente regolamentati e ai file più sensibili è applicata la sottoetichetta di riservatezza per il sito.</span><span class="sxs-lookup"><span data-stu-id="1885d-224">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="1885d-225">Informazioni sulle modalità di distribuzione di Microsoft 365 Enterprise da parte di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="1885d-225">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1885d-226">Contoso Corporation è un conglomerato industriale fittizio ma rappresentativo a livello internazionale con sede a Parigi, Francia.</span><span class="sxs-lookup"><span data-stu-id="1885d-226">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="1885d-227">Vedere il modo in cui Contoso ha sviluppato, configurato e quindi ha guidato l'adozione di un [sito di SharePoint protetto](contoso-sharepoint-online-site-for-highly-confidential-assets.md) per i team di ricerca a Parigi, Mosca, New York, Pechino e Bengaluru.</span><span class="sxs-lookup"><span data-stu-id="1885d-227">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="1885d-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1885d-228">See also</span></span>

[<span data-ttu-id="1885d-229">Guida all'implementazione</span><span class="sxs-lookup"><span data-stu-id="1885d-229">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1885d-230">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="1885d-230">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

