---
title: Siti Microsoft Teams e SharePoint Online per dati altamente riservati
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un sito del team SharePoint Online sicuro o un team di Microsoft Teams per archiviare gli asset digitali più importanti e riservati.
ms.openlocfilehash: d9740a27cdb90f8d490a6c9a323e968725876deb
ms.sourcegitcommit: e87c9aa4d6f4756c0a761d3de7c70492b43bf0b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2019
ms.locfileid: "34681065"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="2a260-103">Siti Microsoft Teams e SharePoint Online per dati altamente riservati</span><span class="sxs-lookup"><span data-stu-id="2a260-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="2a260-104">*Questo scenario si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2a260-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2a260-p101">Poiché Microsoft 365 Enterprise include una gamma completa di servizi basati sul cloud, è possibile creare, archiviare e proteggere i dati altamente riservati, tra cui quelli:</span><span class="sxs-lookup"><span data-stu-id="2a260-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="2a260-107">Soggetti alle normative internazionali.</span><span class="sxs-lookup"><span data-stu-id="2a260-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="2a260-108">I dati più importanti per l'organizzazione, ad esempio segreti finanziari o informazioni sulle risorse umane e strategia dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a260-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="2a260-109">Affinché una scenario Microsoft 365 Enterprise basata sul cloud soddisfi le esigenze aziendali, è necessario:</span><span class="sxs-lookup"><span data-stu-id="2a260-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="2a260-110">Memorizzare asset digitali, quali documenti, presentazioni, fogli di calcolo e così via, in un sito di SharePoint Online o nella scheda **File** di un team di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a260-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="2a260-111">Bloccare i siti del team per evitare che:</span><span class="sxs-lookup"><span data-stu-id="2a260-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="2a260-112">Si acceda solo a un set specifico di account utente tramite l'appartenenza al gruppo, che include gli utenti che possono accedere al sito del team di SharePoint Online con relativo livello di autorizzazione e gli utenti che possono gestirlo.</span><span class="sxs-lookup"><span data-stu-id="2a260-112">Access to only a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="2a260-113">I membri del sito dalla concessione dell'accesso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="2a260-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="2a260-114">I non-membri del sito dalla richiesta di accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="2a260-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="2a260-115">Configurare un'etichetta di conservazione di Office 365 per i siti o i team di SharePoint Online come metodo predefinito per definire i criteri di conservazione dei documenti nel sito o nel team.</span><span class="sxs-lookup"><span data-stu-id="2a260-115">Configure an Office 365 retention label for your SharePoint Online sites or teams as a default way to define retention policies on the documents in the site or team.</span></span>
- <span data-ttu-id="2a260-116">Bloccare l'invio di file all'esterno dell'organizzazione da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a260-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="2a260-117">Crittografare gli asset digitali più riservati del sito o del team.</span><span class="sxs-lookup"><span data-stu-id="2a260-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="2a260-118">Aggiungere autorizzazioni per gli asset digitali più riservati, in modo che, anche in caso di condivisione all'esterno del sito, all'apertura vengano richieste le credenziali di un account utente che dispone dell'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a260-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="2a260-119">La tabella seguente associa i requisiti di questo scenario a una funzionalità di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2a260-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="2a260-120">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="2a260-120">**Requirement**</span></span> | <span data-ttu-id="2a260-121">**Funzionalità di Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="2a260-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="2a260-122">Memorizzare gli asset digitali</span><span class="sxs-lookup"><span data-stu-id="2a260-122">Store digital assets</span></span> | <span data-ttu-id="2a260-123">Siti del team di SharePoint Online e team di Office 365</span><span class="sxs-lookup"><span data-stu-id="2a260-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="2a260-124">Bloccare il sito</span><span class="sxs-lookup"><span data-stu-id="2a260-124">Lock down the site</span></span> | <span data-ttu-id="2a260-125">Autorizzazioni gruppi di Azure AD e sito del team di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2a260-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="2a260-126">Assegnare un'etichetta agli asset digitali del sito</span><span class="sxs-lookup"><span data-stu-id="2a260-126">Label the digital assets of the site</span></span> | <span data-ttu-id="2a260-127">Etichette di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="2a260-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="2a260-128">Bloccare gli utenti quando inviano file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a260-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="2a260-129">Criteri di prevenzione della perdita di dati (DLP) in Office 365</span><span class="sxs-lookup"><span data-stu-id="2a260-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="2a260-130">Crittografare tutti gli asset digitali del sito</span><span class="sxs-lookup"><span data-stu-id="2a260-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="2a260-131">Etichette secondarie di Azure Information Protection in Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="2a260-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="2a260-132">Aggiungere autorizzazioni a tutti gli asset digitali del sito</span><span class="sxs-lookup"><span data-stu-id="2a260-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="2a260-133">Etichette secondarie di Azure Information Protection in EMS</span><span class="sxs-lookup"><span data-stu-id="2a260-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="2a260-134">Ecco la configurazione per un sito di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2a260-134">Here is the configuration for a SharePoint Online site.</span></span>

![Siti Microsoft Teams e SharePoint Online per scenario di dati altamente riservati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="2a260-136">Questo scenario richiede di aver già implementato:</span><span class="sxs-lookup"><span data-stu-id="2a260-136">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="2a260-137">La fase [Identità](identity-infrastructure.md) e i passaggi 1 e 2 della fase [Protezione delle informazioni](infoprotect-infrastructure.md) dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="2a260-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="2a260-138">[SharePoint Online](sharepoint-online-onedrive-workload.md) per i dati altamente riservati nei siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2a260-138">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="2a260-139">[Microsoft Teams](teams-workload.md), per i dati altamente riservati nei team di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a260-139">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="2a260-140">Le fasi seguenti illustrano la progettazione, la configurazione e l'adozione dei siti e dei team di SharePoint Online per dati altamente riservati.</span><span class="sxs-lookup"><span data-stu-id="2a260-140">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="2a260-141">Per vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha progettato un sito di SharePoint Online per i propri team di ricerca, vedere questo [esempio di configurazione](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="2a260-141">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>


<span data-ttu-id="2a260-p102">Un team con dati altamente riservati richiede che venga creato un sito del team di SharePoint Online per dati altamente riservati. Quindi si crea un nuovo team che utilizza il gruppo Office 365 del sito del team di SharePoint Online. Vedere Fase 2, Passaggio 4 per maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="2a260-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>

<span data-ttu-id="2a260-145">Ecco la configurazione per un team.</span><span class="sxs-lookup"><span data-stu-id="2a260-145">Here is the configuration for a team.</span></span>

![Siti Microsoft Teams e SharePoint Online per scenario di dati altamente riservati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-team.png)


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="2a260-147">Prerequisiti di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="2a260-147">Identity and device access prerequisites</span></span>

<span data-ttu-id="2a260-148">Per proteggere l'accesso al team o al sito di SharePoint Online, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint Online consigliati](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2a260-148">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="2a260-149">Fase 1: progettazione</span><span class="sxs-lookup"><span data-stu-id="2a260-149">Phase 1: Design</span></span>

<span data-ttu-id="2a260-p103">Per creare un sito o un team di SharePoint Online per dati altamente riservati, è necessario innanzitutto identificarne lo scopo. Ad esempio, il reparto di ricerca e sviluppo di un'organizzazione di produzione ha bisogno di un sito di SharePoint Online per archiviare le specifiche di progettazione attuali per i prodotti esistenti e un luogo in cui collaborare su nuovi prodotti. Solo i membri del reparto di ricerca e sviluppo e i dirigenti selezionati saranno autorizzati ad accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="2a260-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="2a260-153">Questo scopo, ad esempio determinerà l'identificazione di elementi essenziali quali:</span><span class="sxs-lookup"><span data-stu-id="2a260-153">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="2a260-154">L'insieme dei set di autorizzazione di SharePoint Online e i gruppi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="2a260-154">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="2a260-155">L'insieme dei gruppi di accesso, i gruppi di sicurezza di Azure AD e i membri da aggiungere ai gruppi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="2a260-155">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="2a260-156">L'etichetta di conservazione di Office 365 da assegnare al sito e il set di criteri DLP per l'etichetta</span><span class="sxs-lookup"><span data-stu-id="2a260-156">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="2a260-157">Le impostazioni di un'etichetta secondaria di Azure Information Protection che gli utenti applicano agli asset digitali altamente riservati archiviati nel sito</span><span class="sxs-lookup"><span data-stu-id="2a260-157">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="2a260-158">Una volta determinate queste impostazioni, utilizzarle per configurare il sito nella Fase 2.</span><span class="sxs-lookup"><span data-stu-id="2a260-158">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="2a260-159">Passaggio 1: Sito di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="2a260-159">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="2a260-p104">La versione bloccata di un sito del team di SharePoint Online è nota come sito isolato. A differenza delle impostazioni predefinite dei siti dei team privati, i siti isolati sono configurati per impedire:</span><span class="sxs-lookup"><span data-stu-id="2a260-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="2a260-162">L'accesso agli utenti che non sono membri di gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="2a260-162">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="2a260-163">La richiesta di accesso.</span><span class="sxs-lookup"><span data-stu-id="2a260-163">The requesting of access.</span></span>
- <span data-ttu-id="2a260-164">La concessione non autorizzata di accesso da parte di membri correnti di gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="2a260-164">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="2a260-165">L'amministrazione del sito da parte dei membri del gruppo di accesso.</span><span class="sxs-lookup"><span data-stu-id="2a260-165">Administration of the site by access group members.</span></span>

<span data-ttu-id="2a260-166">La sicurezza dei siti del team di SharePoint Online che contengono asset altamente riservati non cambia a meno che la modifica non venga apportata da un amministratore di SharePoint per il sito.</span><span class="sxs-lookup"><span data-stu-id="2a260-166">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="2a260-167">Vedere [Progettare un sito del team di SharePoint Online isolato](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) per avere dettagli su come determinare il set di livelli di autorizzazione, gruppi di SharePoint, gruppi di accesso e membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a260-167">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="2a260-168">Passaggio 2: Etichette di conservazione di Office 365 e criteri DLP</span><span class="sxs-lookup"><span data-stu-id="2a260-168">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="2a260-169">Quando vengono applicate a un sito del team di SharePoint Online, le etichette di conservazione di Office 365 forniscono un metodo predefinito per classificare tutti gli asset digitali archiviati nel sito.</span><span class="sxs-lookup"><span data-stu-id="2a260-169">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="2a260-170">Per i siti di SharePoint Online per dati altamente riservati, è necessario determinare quale etichetta di conservazione di Office 365 usare.</span><span class="sxs-lookup"><span data-stu-id="2a260-170">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="2a260-171">Per considerazioni sulla progettazione delle etichette di Office 365, vedere [Classificazione ed etichette di Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="2a260-171">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="2a260-p105">Per proteggere le informazioni sensibili e prevenirne la divulgazione accidentale o intenzionale, si utilizzano criteri DLP. Per ulteriori informazioni, vedere [Panoramica](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="2a260-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="2a260-174">Per i siti di SharePoint Online per dati altamente riservati, è necessario configurare un criterio DLP per l'etichetta di conservazione di Office 365 assegnata al sito per bloccare gli utenti quando tentano di condividere asset digitali con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="2a260-174">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="2a260-175">Passaggio 3: Etichette secondarie di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="2a260-175">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="2a260-p106">Per fornire la crittografia e un set di autorizzazioni per gli asset digitali più sensibili, gli utenti devono applicare un'etichetta di Azure Information Protection utilizzando il client di Azure Information Protection. Per utilizzare le etichette di Azure Information Protection per i siti di SharePoint Online per dati altamente riservati, è necessario configurare un'etichetta secondaria di Azure Information Protection in un criterio con ambito.</span><span class="sxs-lookup"><span data-stu-id="2a260-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="2a260-p107">L'etichetta secondaria è presente sotto l'etichetta esistente. Ad esempio, è possibile creare un'etichetta secondaria Ricerca e sviluppo sotto l'etichetta Altamente riservato. Un criterio con ambito è quello che si applica solo a un sottoinsieme di utenti. Per i siti di SharePoint Online per dati altamente riservati, l'ambito è l'insieme di utenti membri dei gruppi di accesso per il sito.</span><span class="sxs-lookup"><span data-stu-id="2a260-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="2a260-p108">Le impostazioni dell'etichetta secondaria applicata viaggiano con l'asset. Anche se viene scaricato e condiviso all'esterno del sito, solo gli account utente autenticati che dispongono delle autorizzazioni possono aprirlo.</span><span class="sxs-lookup"><span data-stu-id="2a260-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="2a260-184">Risultati della progettazione</span><span class="sxs-lookup"><span data-stu-id="2a260-184">Design results</span></span>

<span data-ttu-id="2a260-185">È stato determinato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a260-185">You have determined the following:</span></span>

- <span data-ttu-id="2a260-186">Il set di gruppi di SharePoint e i livelli di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2a260-186">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="2a260-187">Il set di gruppi di accesso e i relativi membri per ogni livello di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2a260-187">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="2a260-188">L'etichetta di conservazione appropriata di Office 365 e il criterio DLP ad essa associato</span><span class="sxs-lookup"><span data-stu-id="2a260-188">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="2a260-189">Le impostazioni dell'etichetta secondaria di Azure Information Protection che includono crittografia e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2a260-189">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="2a260-190">Fase 2: Configurazione</span><span class="sxs-lookup"><span data-stu-id="2a260-190">Phase 2: Configure</span></span>

<span data-ttu-id="2a260-191">In questa fase, le impostazioni determinate nella Fase 1 vengono implementate per creare un sito di SharePoint Online per dati altamente riservati.</span><span class="sxs-lookup"><span data-stu-id="2a260-191">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="2a260-192">Passaggio 1: Creare e configurare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="2a260-192">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="2a260-193">Attenersi alle istruzioni riportate in [Distribuire un sito del team di SharePoint Online isolato](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) per:</span><span class="sxs-lookup"><span data-stu-id="2a260-193">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="2a260-194">Creare e popolare i gruppi di accesso per ciascun livello di autorizzazione di SharePoint utilizzato nel sito.</span><span class="sxs-lookup"><span data-stu-id="2a260-194">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="2a260-195">Creare e configurare il sito del team isolato.</span><span class="sxs-lookup"><span data-stu-id="2a260-195">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a><span data-ttu-id="2a260-196">Passaggio 2: Configurare il sito per un criterio DLP dell'etichetta di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="2a260-196">Step 2: Configure the site for an Office 365 retention label DLP policy</span></span>

<span data-ttu-id="2a260-197">Attenersi alle istruzioni riportate in [Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) per:</span><span class="sxs-lookup"><span data-stu-id="2a260-197">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="2a260-198">Identificare o creare l'etichetta di conservazione di Office 365 e applicarla al sito di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="2a260-198">Identify or create the Office 365 retention label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="2a260-199">Creare e configurare il criterio DLP che blocca gli utenti quando tentano di condividere un asset digitale sul sito di SharePoint Online all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a260-199">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="2a260-200">Passaggio 3: Creare un'etichetta secondaria di Azure Information Protection per il sito</span><span class="sxs-lookup"><span data-stu-id="2a260-200">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="2a260-201">Attenersi alle istruzioni riportate in [Proteggere i file di SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) per:</span><span class="sxs-lookup"><span data-stu-id="2a260-201">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="2a260-202">Creare e configurare un'etichetta secondaria di Azure Information Protection in un criterio con ambito.</span><span class="sxs-lookup"><span data-stu-id="2a260-202">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="2a260-203">Implementazione del client di Azure Information Protection sul computer degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a260-203">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="2a260-204">Passaggio 4 (facoltativo): Creare un team per i dati altamente riservati</span><span class="sxs-lookup"><span data-stu-id="2a260-204">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="2a260-p109">Se si desidera un team per dati altamente riservati, è innanzitutto necessario creare un sito di SharePoint Online per dati altamente riservati. Quando si crea il l'iniziale sito privato del team di SharePoint Online, si specifica un nome per il gruppo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a260-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="2a260-207">Dopo che il sito di SharePoint Online per i dati altamente riservati è completamente configurato, utilizzare questi passaggi per convertirlo in un team per i dati altamente riservati:</span><span class="sxs-lookup"><span data-stu-id="2a260-207">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="2a260-208">Accedere a Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a260-208">Sign in to Office 365.</span></span>
2. <span data-ttu-id="2a260-209">Dalla scheda **Microsoft Office Home**, fare clic su **Team**.</span><span class="sxs-lookup"><span data-stu-id="2a260-209">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="2a260-210">Dalla scheda **Microsoft Teams**, nel riquadro per **partecipare o creare un team**, fare clic su **Crea team**.</span><span class="sxs-lookup"><span data-stu-id="2a260-210">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="2a260-211">Nel riquadro **Crea team**, fare clic su **Crea team da gruppo Office 365 esistente**.</span><span class="sxs-lookup"><span data-stu-id="2a260-211">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="2a260-212">Nell'elenco dei gruppi di Office 365, selezionare il nome del gruppo di Office 365 corrispondente al sito di SharePoint Online per i dati altamente riservati, quindi fare clic su **Scegli team**.</span><span class="sxs-lookup"><span data-stu-id="2a260-212">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="2a260-p110">La scheda **File** del nuovo team elenca i contenuti della cartella **Generale** dell'area **Documenti** del sito SharePoint Online corrispondente. Per visualizzare il resto delle risorse del sito SharePoint Online per il team, fare clic sui puntini di sospensione, quindi su **Apri in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="2a260-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="2a260-215">Risultati della configurazione</span><span class="sxs-lookup"><span data-stu-id="2a260-215">Configuration results</span></span>

<span data-ttu-id="2a260-216">È stato configurato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a260-216">You have configured the following:</span></span>

- <span data-ttu-id="2a260-217">Un sito SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="2a260-217">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="2a260-218">Un'etichetta di conservazione di Office 365 assegnata a un sito SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="2a260-218">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="2a260-219">Un criterio DLP per l'etichetta di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="2a260-219">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="2a260-220">Un'etichetta secondaria di Azure Information Protection di un criterio con ambito che gli utenti possono applicare agli asset digitali più sensibili memorizzate nel sito che crittografa l'asset e applica le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2a260-220">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="2a260-221">Se necessario, un team per i dati altamente riservati basati sul sito di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2a260-221">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="2a260-222">Fase 3: Favorire l'adozione degli utenti</span><span class="sxs-lookup"><span data-stu-id="2a260-222">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="2a260-p111">Un sito o un team di SharePoint Online per dati altamente riservati è in grado di proteggere tali dati solo se costantemente utilizzato per l'archiviazione e l'accesso ad asset digitali sensibili. Questa è la fase più difficile perché dipende dal cambiamento di abitudini degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a260-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="2a260-225">Ad esempio, i dirigenti che sono abituati a memorizzare file sensibili su unità USB o su soluzioni di archiviazione basate sul cloud personale dovranno ora archiviarli esclusivamente in un sito o un team di SharePoint Online per dati altamente riservati.</span><span class="sxs-lookup"><span data-stu-id="2a260-225">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="2a260-226">Passaggio 1: Formazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="2a260-226">Step 1: Train your users</span></span>

<span data-ttu-id="2a260-227">Dopo aver completato la configurazione, formare gli utenti membri dei gruppi di accesso al sito:</span><span class="sxs-lookup"><span data-stu-id="2a260-227">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="2a260-228">Sull'importanza di utilizzare il nuovo sito o team per proteggere risorse preziose e le conseguenze di una perdita di dati altamente riservati, come implicazioni legali, sanzioni per inadempimento alle normative, ransomware o perdita di vantaggi competitivi.</span><span class="sxs-lookup"><span data-stu-id="2a260-228">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="2a260-229">Come accedere al sito e ai suoi asset.</span><span class="sxs-lookup"><span data-stu-id="2a260-229">How to access the site and its assets.</span></span>
- <span data-ttu-id="2a260-230">Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.</span><span class="sxs-lookup"><span data-stu-id="2a260-230">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="2a260-231">In che modo i criteri DLP impediscono di condividere i file esternamente.</span><span class="sxs-lookup"><span data-stu-id="2a260-231">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="2a260-232">Come utilizzare il client Azure Information Protection per etichettare asset digitali più sensibili con l'etichetta secondaria configurata.</span><span class="sxs-lookup"><span data-stu-id="2a260-232">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="2a260-233">In che modo l'etichetta secondaria di Azure Information Protection protegge un asset anche quando non è più nel sito o team.</span><span class="sxs-lookup"><span data-stu-id="2a260-233">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="2a260-234">Questa formazione dovrebbe includere esercizi pratici in modo che gli utenti possano sperimentare queste operazioni e i loro risultati.</span><span class="sxs-lookup"><span data-stu-id="2a260-234">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="2a260-235">Passaggio 2: Effettuare revisioni periodiche sull'utilizzo e sui file</span><span class="sxs-lookup"><span data-stu-id="2a260-235">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="2a260-236">Nelle settimane successive alla formazione, l'amministratore di SharePoint per il sito o il team di SharePoint Online può:</span><span class="sxs-lookup"><span data-stu-id="2a260-236">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="2a260-237">Analizzare l'utilizzo del sito o del team e confrontarlo con le aspettative di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="2a260-237">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="2a260-238">Verificare che i file altamente sensibili siano stati etichettati correttamente con l'etichetta secondaria di Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="2a260-238">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="2a260-239">Ripetere la formazione degli utenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="2a260-239">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="2a260-240">Risultati dell'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="2a260-240">User adoption results</span></span>

<span data-ttu-id="2a260-241">Gli asset digitali sensibili vengono memorizzati esclusivamente nei siti o nei team di SharePoint Online per i dati altamente riservati e agli asset più sensibili viene applicata l'etichetta secondaria di Azure Information Protection configurata.</span><span class="sxs-lookup"><span data-stu-id="2a260-241">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="2a260-242">Informazioni sulle modalità di distribuzione di Microsoft 365 Enterprise da parte di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="2a260-242">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2a260-243">Contoso Corporation è un conglomerato industriale fittizio ma rappresentativo a livello internazionale con sede a Parigi, Francia.</span><span class="sxs-lookup"><span data-stu-id="2a260-243">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="2a260-244">Visualizzare il modo in cui Contoso ha sviluppato, configurato e quindi ha guidato l'adozione di un [sito di SharePoint Online protetto](contoso-sharepoint-online-site-for-highly-confidential-assets.md) per i team di ricerca a Parigi, Mosca, New York, Pechino e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="2a260-244">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2a260-245">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a260-245">See also</span></span>

[<span data-ttu-id="2a260-246">Guida all'implementazione</span><span class="sxs-lookup"><span data-stu-id="2a260-246">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2a260-247">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="2a260-247">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2a260-248">Proteggere i siti di SharePoint Online in un ambiente di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="2a260-248">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
