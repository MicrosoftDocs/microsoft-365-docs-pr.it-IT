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
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403185"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="4f91c-103">Siti di SharePoint per dati altamente regolamentati</span><span class="sxs-lookup"><span data-stu-id="4f91c-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="4f91c-104">*Questo scenario si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4f91c-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4f91c-p101">Microsoft 365 Enterprise include una gamma completa di servizi basati sul cloud, che permettono di creare, archiviare e proteggere i dati altamente regolamentati archiviati nei file, tra cui quelli:</span><span class="sxs-lookup"><span data-stu-id="4f91c-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="4f91c-107">Soggetti alle normative internazionali.</span><span class="sxs-lookup"><span data-stu-id="4f91c-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="4f91c-108">I dati più importanti per l'organizzazione, ad esempio segreti finanziari o informazioni sulle risorse umane e strategia dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f91c-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="4f91c-109">Affinché una scenario Microsoft 365 Enterprise basata sul cloud soddisfi le esigenze aziendali, è necessario:</span><span class="sxs-lookup"><span data-stu-id="4f91c-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="4f91c-110">Archiviare i file (documenti, presentazioni, fogli di calcolo e così via) in un sito del team di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4f91c-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="4f91c-111">Bloccare il sito per impedire:</span><span class="sxs-lookup"><span data-stu-id="4f91c-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="4f91c-112">L'accesso a utenti che non siano membri del gruppo di Office 365 per il sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="4f91c-113">I membri del sito dalla concessione dell'accesso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="4f91c-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="4f91c-114">I non-membri del sito dalla richiesta di accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="4f91c-115">Configurare un'etichetta di conservazione di Office 365 per i siti di SharePoint come modo predefinito per impedire agli utenti di inviare file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f91c-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="4f91c-116">Crittografare i file più sensibili del sito con crittografia che segue il file.</span><span class="sxs-lookup"><span data-stu-id="4f91c-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="4f91c-117">Aggiungere autorizzazioni per i file più sensibili, in modo che, anche in caso di condivisione all'esterno del sito, all'apertura vengano richieste le credenziali valide di un account utente autorizzato.</span><span class="sxs-lookup"><span data-stu-id="4f91c-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="4f91c-118">La tabella seguente associa i requisiti di questo scenario a una funzionalità di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4f91c-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="4f91c-119">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="4f91c-119">**Requirement**</span></span> | <span data-ttu-id="4f91c-120">**Funzionalità di Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="4f91c-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="4f91c-121">Archiviare file</span><span class="sxs-lookup"><span data-stu-id="4f91c-121">Store files online</span></span> | <span data-ttu-id="4f91c-122">Siti del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4f91c-122">Sensitive SharePoint Online team sites</span></span> |
| <span data-ttu-id="4f91c-123">Bloccare il sito</span><span class="sxs-lookup"><span data-stu-id="4f91c-123">Lock down the site</span></span> | <span data-ttu-id="4f91c-124">Autorizzazioni per gruppi di Azure Active Directory (Azure AD) e sito del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4f91c-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="4f91c-125">Etichettare i file del sito</span><span class="sxs-lookup"><span data-stu-id="4f91c-125">Label the digital assets of the site</span></span> | <span data-ttu-id="4f91c-126">Etichette di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f91c-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="4f91c-127">Bloccare gli utenti quando inviano file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f91c-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="4f91c-128">Criteri di prevenzione della perdita di dati (DLP) in Office 365</span><span class="sxs-lookup"><span data-stu-id="4f91c-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="4f91c-129">Crittografare tutti i file del sito</span><span class="sxs-lookup"><span data-stu-id="4f91c-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="4f91c-130">Sottoetichette di riservatezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f91c-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="4f91c-131">Aggiungere autorizzazioni ai file del sito</span><span class="sxs-lookup"><span data-stu-id="4f91c-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="4f91c-132">Sottoetichette di riservatezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f91c-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="4f91c-133">Ecco la configurazione per un sito di SharePoint sicuro.</span><span class="sxs-lookup"><span data-stu-id="4f91c-133">Here is the configuration for a SharePoint Online site.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="4f91c-135">Questo scenario richiede di aver già implementato:</span><span class="sxs-lookup"><span data-stu-id="4f91c-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="4f91c-136">La fase [Identità](identity-infrastructure.md) e i passaggi 1 e 2 della fase [Protezione delle informazioni](infoprotect-infrastructure.md) dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="4f91c-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="4f91c-137">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="4f91c-137">SharePoint</span></span>

<span data-ttu-id="4f91c-138">Le fasi seguenti illustrano come progettare, configurare e facilitare l'adozione dei siti di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="4f91c-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="4f91c-139">Per vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha progettato un sito di SharePoint per i propri team di ricerca, vedere questo [esempio di configurazione](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="4f91c-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="4f91c-140">Prerequisiti di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="4f91c-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="4f91c-141">Per proteggere l'accesso ai siti di SharePoint, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint consigliati](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4f91c-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="4f91c-142">Fase 1: progettazione</span><span class="sxs-lookup"><span data-stu-id="4f91c-142">Phase 1: Design</span></span>

<span data-ttu-id="4f91c-143">Per creare un sito di SharePoint per i dati altamente regolamentati, è necessario prima di tutto identificarne lo scopo.</span><span class="sxs-lookup"><span data-stu-id="4f91c-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="4f91c-144">Ad esempio, il reparto ricerca e sviluppo di un'azienda del settore manifatturiero ha bisogno di un sito di SharePoint per archiviare le specifiche di progettazione attuali per i prodotti esistenti e come luogo in cui collaborare su nuovi prodotti.</span><span class="sxs-lookup"><span data-stu-id="4f91c-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="4f91c-145">Solo i membri del reparto di ricerca e sviluppo e i dirigenti selezionati saranno autorizzati ad accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="4f91c-146">Questo scopo, ad esempio determinerà l'identificazione di elementi essenziali quali:</span><span class="sxs-lookup"><span data-stu-id="4f91c-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="4f91c-147">L'etichetta di conservazione di Office 365 da assegnare alla sezione Documenti del sito e i criteri DLP per l'etichetta</span><span class="sxs-lookup"><span data-stu-id="4f91c-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="4f91c-148">Le impostazioni di una sottoetichetta di riservatezza di Office 365 che gli utenti applicano ai file altamente sensibili archiviati nel sito</span><span class="sxs-lookup"><span data-stu-id="4f91c-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="4f91c-149">Una volta determinate queste impostazioni, usarle per configurare il sito nella Fase 2.</span><span class="sxs-lookup"><span data-stu-id="4f91c-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="4f91c-150">Passaggio 1: Etichette di conservazione di Office 365 e criteri DLP</span><span class="sxs-lookup"><span data-stu-id="4f91c-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="4f91c-151">Quando vengono applicate alla sezione Documenti di un sito del team di SharePoint, le etichette di conservazione di Office 365 forniscono un metodo predefinito per classificare tutti i file archiviati nel sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="4f91c-152">Per i siti di SharePoint per dati altamente regolamentati, è necessario determinare quale etichetta di conservazione di Office 365 usare.</span><span class="sxs-lookup"><span data-stu-id="4f91c-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="4f91c-153">Per considerazioni sulla progettazione delle etichette di Office 365, vedere [Classificazione ed etichette di Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="4f91c-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="4f91c-p103">Per proteggere le informazioni sensibili e prevenirne la divulgazione accidentale o intenzionale, si utilizzano criteri DLP. Per ulteriori informazioni, vedere [Panoramica](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="4f91c-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="4f91c-156">Per i siti di SharePoint, è necessario configurare un criterio DLP per l'etichetta di conservazione di Office 365 assegnata al sito per bloccare gli utenti quando provano a condividere file con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="4f91c-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="4f91c-157">Passaggio 2: Sottoetichetta di riservatezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f91c-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="4f91c-158">Per fornire la crittografia e un set di autorizzazioni per i file più sensibili, gli utenti devono applicare una sottoetichetta di riservatezza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f91c-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="4f91c-159">Una sottoetichetta esiste sotto un'etichetta esistente.</span><span class="sxs-lookup"><span data-stu-id="4f91c-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="4f91c-160">Ad esempio, è possibile creare una sottoetichetta Ricerca e sviluppo sotto l'etichetta Altamente regolamentato.</span><span class="sxs-lookup"><span data-stu-id="4f91c-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="4f91c-161">Per i siti di SharePoint per i dati altamente regolamentati, è necessario configurare le autorizzazioni in modo che solo i membri del sito possano aprire e modificare il file a cui è allegata la sottoetichetta.</span><span class="sxs-lookup"><span data-stu-id="4f91c-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="4f91c-162">Le impostazioni della sottoetichetta applicata seguono il file.</span><span class="sxs-lookup"><span data-stu-id="4f91c-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="4f91c-163">Anche se dovesse uscire dal sito, solo gli account utente autenticati con autorizzazioni adeguate potrebbero aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4f91c-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="4f91c-164">Risultati della progettazione</span><span class="sxs-lookup"><span data-stu-id="4f91c-164">Design results</span></span>

<span data-ttu-id="4f91c-165">È stato determinato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4f91c-165">You have determined the following:</span></span>

- <span data-ttu-id="4f91c-166">L'etichetta di conservazione appropriata di Office 365 e il criterio DLP ad essa associato</span><span class="sxs-lookup"><span data-stu-id="4f91c-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="4f91c-167">Le impostazioni della sottoetichetta di riservatezza di Office 365 che includono crittografia e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4f91c-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="4f91c-168">Fase 2: Configurazione</span><span class="sxs-lookup"><span data-stu-id="4f91c-168">Phase 2: Configure</span></span>

<span data-ttu-id="4f91c-169">In questa fase, le impostazioni determinate nella Fase 1 vengono implementate per creare un sito di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="4f91c-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="4f91c-170">Passaggio 1: Creare un sito del team di SharePoint privato con proprietari e membri del gruppo di Office 365 corrispondente</span><span class="sxs-lookup"><span data-stu-id="4f91c-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="4f91c-171">Seguire [queste istruzioni]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) per creare un sito del team di SharePoint privato.</span><span class="sxs-lookup"><span data-stu-id="4f91c-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="4f91c-172">Passaggio 2: Configurare altre impostazioni delle autorizzazioni per il sito del team di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4f91c-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="4f91c-173">Nel sito di SharePoint configurare queste impostazioni per le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4f91c-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="4f91c-174">Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="4f91c-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="4f91c-175">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="4f91c-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="4f91c-176">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="4f91c-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="4f91c-177">Nella finestra di dialogo **Impostazioni richieste di accesso** deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti richieste di accesso** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f91c-177">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and \*\*Allow access requests \*\*(so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="4f91c-178">Con queste impostazioni, la possibilità per i membri del gruppo di siti di condividere il sito con altri membri o per i non membri di richiedere l'accesso al sito è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4f91c-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="4f91c-179">Passaggio 3: Configurare il sito per un'etichetta di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f91c-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="4f91c-180">Attenersi alle istruzioni riportate in [Proteggere i file di SharePoint con le etichette di Office 365 e la prevenzione della perdita dei dati](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) per:</span><span class="sxs-lookup"><span data-stu-id="4f91c-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="4f91c-181">Creare e pubblicare un'etichetta di conservazione per i dati altamente regolamentati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="4f91c-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="4f91c-182">Configurare il sito per l'etichetta di conservazione creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="4f91c-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="4f91c-183">Creare un criterio DLP per i dati altamente regolamentati che usi l'etichetta di conservazione creata nel passaggio 2 e impedisca agli utenti di inviare file all'esterno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4f91c-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="4f91c-184">Passaggio 4: Creare una sottoetichetta di riservatezza di Office 365 per il sito</span><span class="sxs-lookup"><span data-stu-id="4f91c-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="4f91c-185">Diversamente da un'etichetta di riservatezza per dati altamente regolamentati, che chiunque può applicare a qualsiasi file, un sito sicuro deve avere una propria sottoetichetta, in modo che i file a cui è assegnata la sottoetichetta:</span><span class="sxs-lookup"><span data-stu-id="4f91c-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="4f91c-186">Siano crittografati e la crittografia segua il file.</span><span class="sxs-lookup"><span data-stu-id="4f91c-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="4f91c-187">Contengano autorizzazioni personalizzate in modo che solo i membri del gruppo del sito possano aprirli.</span><span class="sxs-lookup"><span data-stu-id="4f91c-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="4f91c-188">Per implementare questo ulteriore livello di sicurezza per i file archiviati nel sito, è necessario configurare una nuova etichetta di riservatezza, ossia una sottoetichetta dell'etichetta generale per i file altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="4f91c-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="4f91c-189">La vedranno solo i membri del gruppo per il sito, nell'elenco di sottoetichette per l'etichetta altamente regolamentata.</span><span class="sxs-lookup"><span data-stu-id="4f91c-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="4f91c-190">Usare le istruzioni disponibili [qui](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) per configurare una sottoetichetta dell'etichetta che si usa per i file altamente regolamentati, con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f91c-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="4f91c-191">Il nome della sottoetichetta contiene il nome del sito, per semplificare l'associazione quando si assegna la sottoetichetta a un file.</span><span class="sxs-lookup"><span data-stu-id="4f91c-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="4f91c-192">La crittografia è abilitata.</span><span class="sxs-lookup"><span data-stu-id="4f91c-192">Encryption is enabled.</span></span>
- <span data-ttu-id="4f91c-193">Il gruppo di siti ha autorizzazioni di creazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="4f91c-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="4f91c-194">Risultati della configurazione</span><span class="sxs-lookup"><span data-stu-id="4f91c-194">Configuration results</span></span>

<span data-ttu-id="4f91c-195">È stato configurato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4f91c-195">You have configured the following:</span></span>

- <span data-ttu-id="4f91c-196">Impostazioni di autorizzazione più restrittive nel sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4f91c-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="4f91c-197">Un'etichetta di conservazione di Office 365 assegnata alla sezione Documenti del sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4f91c-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="4f91c-198">Un criterio DLP per l'etichetta di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="4f91c-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="4f91c-199">Una sottoetichetta di riservatezza di Office 365 che gli utenti possono applicare ai file più sensibili archiviati nel sito, che crittografa il file e consente solo l'accesso in modalità di creazione condivisa ai membri del gruppo del sito del team</span><span class="sxs-lookup"><span data-stu-id="4f91c-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="4f91c-200">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="4f91c-200">Here is the resulting configuration.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="4f91c-202">Ecco un esempio di un utente che ha applicato la sottoetichetta di riservatezza a un file archiviato nel sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![I siti di SharePoint per lo scenario dei dati altamente regolamentati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="4f91c-204">Fase 3: Incoraggiare l'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="4f91c-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="4f91c-205">Un sito di SharePoint per dati altamente regolamentati può proteggere tali dati solo se viene usato regolarmente per l'archiviazione e l'accesso ai file sensibili.</span><span class="sxs-lookup"><span data-stu-id="4f91c-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="4f91c-206">Questa è la fase più difficile, perché dipende dal cambiamento di abitudini degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4f91c-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="4f91c-207">Ad esempio, i dipendenti che sono abituati ad archiviare file sensibili in unità USB o soluzioni di archiviazione basate sul cloud personale dovranno ora archiviarli esclusivamente in un sito di SharePoint per dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="4f91c-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="4f91c-208">Passaggio 1: Formazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="4f91c-208">Step 1: Train your users</span></span>

<span data-ttu-id="4f91c-209">Dopo aver completato la configurazione, formare gli utenti membri dei gruppi di accesso al sito:</span><span class="sxs-lookup"><span data-stu-id="4f91c-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="4f91c-210">Sull'importanza di usare il nuovo sito per proteggere file preziosi e le conseguenze di una perdita di dati altamente regolamentati, come implicazioni legali, sanzioni per inadempimento alle normative, ransomware o perdita di vantaggi competitivi.</span><span class="sxs-lookup"><span data-stu-id="4f91c-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="4f91c-211">Come accedere al sito e ai suoi file.</span><span class="sxs-lookup"><span data-stu-id="4f91c-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="4f91c-212">Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.</span><span class="sxs-lookup"><span data-stu-id="4f91c-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="4f91c-213">In che modo i criteri DLP impediscono di condividere i file esternamente.</span><span class="sxs-lookup"><span data-stu-id="4f91c-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="4f91c-214">Come contrassegnare i file più sensibili con la sottoetichetta del sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="4f91c-215">Come la sottoetichetta protegge un file anche se fuoriesce dal sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="4f91c-216">Questa formazione dovrebbe includere esercizi pratici in modo che gli utenti possano sperimentare queste operazioni e i loro risultati.</span><span class="sxs-lookup"><span data-stu-id="4f91c-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="4f91c-217">Passaggio 2: Effettuare revisioni periodiche sull'utilizzo e sui file</span><span class="sxs-lookup"><span data-stu-id="4f91c-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="4f91c-218">Nelle settimane successive alla formazione, l'amministratore di SharePoint per il sito di SharePoint può:</span><span class="sxs-lookup"><span data-stu-id="4f91c-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="4f91c-219">Analizzare l'utilizzo del sito e confrontarlo con le aspettative di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4f91c-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="4f91c-220">Verificare che i file riservati siano stati etichettati correttamente con l'etichetta di riservatezza secondaria.</span><span class="sxs-lookup"><span data-stu-id="4f91c-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="4f91c-221">Ripetere la formazione degli utenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="4f91c-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="4f91c-222">Risultati dell'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="4f91c-222">User adoption results</span></span>

<span data-ttu-id="4f91c-223">I file con elevato livello di regolamentazione vengono archiviati esclusivamente nei siti di SharePoint per dati altamente regolamentati e ai file più sensibili è applicata la sottoetichetta di riservatezza per il sito.</span><span class="sxs-lookup"><span data-stu-id="4f91c-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="4f91c-224">Informazioni sulle modalità di distribuzione di Microsoft 365 Enterprise da parte di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="4f91c-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4f91c-225">Contoso Corporation è un conglomerato industriale fittizio ma rappresentativo a livello internazionale con sede a Parigi, Francia.</span><span class="sxs-lookup"><span data-stu-id="4f91c-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="4f91c-226">Vedere il modo in cui Contoso ha sviluppato, configurato e quindi ha guidato l'adozione di un [sito di SharePoint protetto](contoso-sharepoint-online-site-for-highly-confidential-assets.md) per i team di ricerca a Parigi, Mosca, New York, Pechino e Bengaluru.</span><span class="sxs-lookup"><span data-stu-id="4f91c-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="4f91c-227">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f91c-227">See also</span></span>

[<span data-ttu-id="4f91c-228">Guida all'implementazione</span><span class="sxs-lookup"><span data-stu-id="4f91c-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4f91c-229">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="4f91c-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

