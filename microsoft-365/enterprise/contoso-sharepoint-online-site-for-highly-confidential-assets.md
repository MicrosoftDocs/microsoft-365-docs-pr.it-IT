---
title: Sito di SharePoint Online per le risorse digitali estremamente riservate di Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: informazioni su come Contoso ha implementato un sito di SharePoint Online per dati altamente regolamentati per semplificare la collaborazione tra i team di ricerca.'
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369527"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="eff74-103">Sito di SharePoint Online per le risorse digitali estremamente riservate di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="eff74-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="eff74-104">**Riepilogo:** Come Contoso ha implementato un sito di SharePoint Online per dati altamente regolamentati per semplificare la collaborazione tra i propri team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="eff74-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="eff74-105">Le risorse più importanti di Contoso sono la proprietà intellettuale in forma di segreti commerciali, come le tecniche di produzione proprietarie e le specifiche di progettazione per i prodotti in sviluppo.</span><span class="sxs-lookup"><span data-stu-id="eff74-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="eff74-106">Tali risorse sono in formato digitale, archiviate originariamente come file in un sito di SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="eff74-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="eff74-107">Quando Contoso ha distribuito Microsoft 365 Enterprise, volevano passare al cloud le risorse digitali locali per semplificare l'accesso e una collaborazione più aperta tra i team di ricerca di Parigi, Mosca, New York, Pechino e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="eff74-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="eff74-108">Tuttavia, a causa della loro natura sensibile, l'accesso a questi file deve essere:</span><span class="sxs-lookup"><span data-stu-id="eff74-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="eff74-109">Limitato all'insieme di utenti autorizzati a visualizzarli o modificarli, con autorizzazioni in uscita per il sito amministrate solo da amministratori di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="eff74-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="eff74-110">Protetto con la prevenzione della perdita di dati (DLP) per impedire agli utenti di distribuirli all'esterno del sito.</span><span class="sxs-lookup"><span data-stu-id="eff74-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="eff74-111">Crittografati e protetti con gli elenchi di controllo di accesso per impedire agli utenti non autorizzati di accedere ai propri contenuti, anche se sono distribuiti all'esterno del sito.</span><span class="sxs-lookup"><span data-stu-id="eff74-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="eff74-112">Gli amministratori di sicurezza e di SharePoint nel reparto IT di Contoso hanno deciso di utilizzare un [sito di SharePoint Online per dati altamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="eff74-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="eff74-113">Contoso ha utilizzato questi passaggi per creare e proteggere i siti del team di SharePoint Online per i propri team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="eff74-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="eff74-114">Passaggio 1: Revisione e verifica dei membri dei gruppi del team di ricerca</span><span class="sxs-lookup"><span data-stu-id="eff74-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="eff74-115">Contoso IT Admins ha eseguito una revisione del set di gruppi di sicurezza per i propri team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="eff74-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="eff74-116">Sono stati rimossi tutti coloro che non erano un ricercatore o che non avevano bisogno di accedere alle risorse di ricerca.</span><span class="sxs-lookup"><span data-stu-id="eff74-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="eff74-117">Sono stati creati anche questi nuovi gruppi di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="eff74-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="eff74-118">**Ricerca-amministratori**  Set di amministratori di SharePoint che dispongono del controllo completo sul sito, inclusa la possibilità di modificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="eff74-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="eff74-119">**Membri della ricerca**  Set di gruppi di sicurezza per i team di ricerca di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="eff74-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="eff74-120">**Ricerca-visualizzatori**  Il set di utenti di gestione, ad esempio i dirigenti dell'organizzazione di ricerca, che può solo visualizzare le risorse nel sito.</span><span class="sxs-lookup"><span data-stu-id="eff74-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="eff74-121">Passaggio 2: creazione di un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="eff74-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="eff74-122">Contoso SharePoint Admins ha creato per la prima volta un nuovo sito del team denominato **Research**.</span><span class="sxs-lookup"><span data-stu-id="eff74-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="eff74-123">Sono quindi configurati:</span><span class="sxs-lookup"><span data-stu-id="eff74-123">They then configured:</span></span>

- <span data-ttu-id="eff74-124">Il livello di autorizzazione controllo completo per l'utilizzo del gruppo di SharePoint proprietari di ricerca, che dispone del gruppo di sicurezza **Research-Admins** come membro</span><span class="sxs-lookup"><span data-stu-id="eff74-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="eff74-125">Il livello di autorizzazione modifica per l'utilizzo del gruppo di SharePoint membri della ricerca, che ha come membro il gruppo di sicurezza **membri della ricerca** .</span><span class="sxs-lookup"><span data-stu-id="eff74-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="eff74-126">Il livello di autorizzazione di lettura per l'utilizzo del gruppo di SharePoint visitors Research, che dispone del gruppo di sicurezza dei **visualizzatori di ricerca** come membro</span><span class="sxs-lookup"><span data-stu-id="eff74-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="eff74-127">Di seguito sono riportati i livelli di autorizzazione di SharePoint, i gruppi di SharePoint e i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="eff74-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![Livelli di autorizzazione di SharePoint, gruppi di SharePoint e relativi membri](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="eff74-129">Successivamente, sono state configurate restrizioni aggiuntive per il sito.</span><span class="sxs-lookup"><span data-stu-id="eff74-129">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="eff74-130">Per informazioni dettagliate sulla configurazione, vedere [deploy an isolated SharePoint Online Team Site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="eff74-130">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="eff74-131">Passaggio 3: configurazione del sito per un criterio DLP restrittivo</span><span class="sxs-lookup"><span data-stu-id="eff74-131">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="eff74-132">Per prima cosa, gli amministratori di Contoso hanno applicato l'etichetta di conservazione di Office 365 **estremamente riservata** al sito di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="eff74-132">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="eff74-133">Successivamente, è stato creato un nuovo criterio DLP di Office 365 denominato **Research** :</span><span class="sxs-lookup"><span data-stu-id="eff74-133">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="eff74-134">Utilizza l'etichetta di conservazione di Office 365 **estremamente riservata** .</span><span class="sxs-lookup"><span data-stu-id="eff74-134">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="eff74-135">Viene applicato al sito di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="eff74-135">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="eff74-136">Blocca gli utenti quando tentano di condividere un asset digitale nel sito di **ricerca** esterno a contoso.</span><span class="sxs-lookup"><span data-stu-id="eff74-136">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="eff74-137">Per informazioni dettagliate sulla configurazione, vedere [proteggere i file di SharePoint Online con etichette di conservazione e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="eff74-137">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="eff74-138">Passaggio 4: creazione di un'etichetta secondaria di Azure Information Protection per il sito</span><span class="sxs-lookup"><span data-stu-id="eff74-138">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="eff74-139">Gli amministratori di Contoso hanno creato una nuova etichetta secondaria di Azure Information Protection denominata **Research** dell'etichetta **altamente riservata** predefinita in un criterio con ambito che:</span><span class="sxs-lookup"><span data-stu-id="eff74-139">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="eff74-140">Richiede la crittografia.</span><span class="sxs-lookup"><span data-stu-id="eff74-140">Requires encryption.</span></span>
- <span data-ttu-id="eff74-141">Consente l'accesso completo da parte dei membri del gruppo di sicurezza **membri della ricerca** .</span><span class="sxs-lookup"><span data-stu-id="eff74-141">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="eff74-142">Consente l'accesso in lettura ai membri del gruppo di sicurezza **ricerca-visualizzatori** .</span><span class="sxs-lookup"><span data-stu-id="eff74-142">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="eff74-143">Successivamente, hanno distribuito il client Azure Information Protection ai dispositivi dei membri del team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="eff74-143">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="eff74-144">Per informazioni dettagliate sulla configurazione, vedere [proteggere i file di SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="eff74-144">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="eff74-145">Ecco la configurazione risultante del sito di **ricerca** per le risorse estremamente riservate.</span><span class="sxs-lookup"><span data-stu-id="eff74-145">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![La configurazione risultante del sito \* \* Research \* \* per le risorse estremamente riservate](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="eff74-147">I file nelle cartelle del sito di **ricerca** sono protetti da:</span><span class="sxs-lookup"><span data-stu-id="eff74-147">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="eff74-148">La sottoetichetta **Research** Azure Information Protection, che applica la crittografia e permssions a ogni file che viaggia con il file quando viene spostato o copiato dal sito di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="eff74-148">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="eff74-149">Il criterio DLP di **ricerca** , che utilizza l'etichetta di conservazione **estremamente riservata** e le impostazioni che impediscono la condivisione dei file con gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="eff74-149">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="eff74-150">Il set di autorizzazioni per i siti, che consentono l'accesso solo ai membri dei gruppi di sicurezza e dell'amministrazione di ricerca-spettatori **e dei** **visualizzatori** dai membri del gruppo di sicurezza **Research-Admins** .</span><span class="sxs-lookup"><span data-stu-id="eff74-150">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="eff74-151">Passaggio 5: migrazione dei dati di ricerca di SharePoint locali</span><span class="sxs-lookup"><span data-stu-id="eff74-151">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="eff74-152">Gli amministratori di Contoso hanno spostato tutti i file di ricerca locali nel sito di SharePoint Server 2016 locale in cartelle nel nuovo sito di **ricerca** di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="eff74-152">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="eff74-153">Passaggio 6: formazione dei propri utenti</span><span class="sxs-lookup"><span data-stu-id="eff74-153">Step 6: Trained their users</span></span> 

<span data-ttu-id="eff74-154">Il personale di sicurezza di Contoso ha formato i team di ricerca in un corso obbligatorio che ha superato:</span><span class="sxs-lookup"><span data-stu-id="eff74-154">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="eff74-155">Informazioni su come accedere al nuovo sito di **ricerca** di SharePoint Online e ai file esistenti.</span><span class="sxs-lookup"><span data-stu-id="eff74-155">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="eff74-156">Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.</span><span class="sxs-lookup"><span data-stu-id="eff74-156">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="eff74-157">Dimostrazione del modo in cui il criterio DLP blocca la condivisione esterna dei file.</span><span class="sxs-lookup"><span data-stu-id="eff74-157">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="eff74-158">Informazioni su come utilizzare il client Azure Information Protection per etichettare i file di ricerca con l'etichetta secondaria **Research** .</span><span class="sxs-lookup"><span data-stu-id="eff74-158">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="eff74-159">Dimostrazione del modo in cui l'etichetta secondaria di **ricerca** protegge un file anche quando viene perso dal sito.</span><span class="sxs-lookup"><span data-stu-id="eff74-159">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="eff74-160">Il risultato finale è un ambiente sicuro in cui i ricercatori possono collaborare all'interno dell'organizzazione in un ambiente sicuro.</span><span class="sxs-lookup"><span data-stu-id="eff74-160">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="eff74-161">Se un documento di ricerca con l' **etichetta secondaria di ricerca è** fuoriuscito dal sito di **ricerca** , è crittografato e accessibile solo ai membri dei gruppi di sicurezza **membri** della ricerca e ai **visualizzatori** di ricerca con credenziali valide.</span><span class="sxs-lookup"><span data-stu-id="eff74-161">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="eff74-162">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="eff74-162">Next step</span></span>

<span data-ttu-id="eff74-163">[Distribuzione](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eff74-163">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

