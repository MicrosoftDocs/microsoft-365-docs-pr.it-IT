---
title: Sito di SharePoint Online per le risorse digitali altamente riservate di Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Riepilogo: Come Contoso ha implementato un sito di SharePoint Online per altamente regolamentati dati per una collaborazione più semplice tra le ricerche dei team.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868870"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="f41b7-103">Sito di SharePoint Online per le risorse digitali altamente riservate di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="f41b7-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="f41b7-104">**Riepilogo:** Modalità di implementazione di un sito di SharePoint Online per i dati per una collaborazione più semplice tra il team di ricerca altamente regolamentati Contoso.</span><span class="sxs-lookup"><span data-stu-id="f41b7-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="f41b7-p101">Risorse più importante di Contoso relativa proprietà intellettuale sotto forma di segreti commerciali, ad esempio le tecniche di produzione proprietari e progettare le specifiche per i prodotti di sviluppo. Queste attività sono nel formato digitale originariamente memorizzato come file in un sito di SharePoint Server 2016. Quando Contoso distribuito Microsoft 365 Enterprise, si desidera le risorse digitali in locale nel cloud per semplificare l'accesso e la collaborazione più vulnerabili la transizione tra i team di ricerca Parigi, Mosca, New York, Pechino e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="f41b7-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="f41b7-108">Tuttavia, a causa di informazioni sensibili, accedere a tali file deve essere:</span><span class="sxs-lookup"><span data-stu-id="f41b7-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="f41b7-109">Con limitazioni all'insieme di utenti autorizzati a visualizzare o modificare le loro, con le autorizzazioni in corso per il sito amministrati solo dagli amministratori di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f41b7-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="f41b7-110">Protetto con dati prevenzione della perdita (DLP) per impedire agli utenti di distribuirli all'esterno del sito.</span><span class="sxs-lookup"><span data-stu-id="f41b7-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="f41b7-111">Accesso crittografato e protetto con controllo elenchi per impedire agli utenti non autorizzati di accedere al relativo contenuto, anche se sono distribuiti all'esterno del sito.</span><span class="sxs-lookup"><span data-stu-id="f41b7-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="f41b7-112">Gli amministratori di SharePoint e sicurezza in Contoso del reparto IT ha deciso di utilizzare un [sito di SharePoint Online per regolamentato altamente dati](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="f41b7-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="f41b7-113">Contoso utilizzata la procedura seguente per creare e proteggere un siti del team di SharePoint Online per i team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f41b7-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="f41b7-114">Passaggio 1: Leggere e verificato i membri dei gruppi di team di ricerca</span><span class="sxs-lookup"><span data-stu-id="f41b7-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="f41b7-p102">Gli amministratori IT di Contoso eseguita una verifica dell'insieme di gruppi di sicurezza per i team di ricerca. Vengono rimossi tutti gli utenti che non è stato ricercatori o non sono necessarie di accedere alle risorse di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f41b7-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="f41b7-117">Vengono inoltre e creati i nuovi gruppi di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="f41b7-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="f41b7-118">**Amministratori della ricerca**  Gruppo di amministratori di SharePoint con il controllo completo del sito, inclusa la possibilità di modificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f41b7-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="f41b7-119">**Membri di ricerca**  Insieme di gruppi di sicurezza per i team di ricerca in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="f41b7-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="f41b7-120">**Visualizzatori di ricerca**  L'insieme di utenti di gestione, ad esempio dirigenti nell'organizzazione di ricerca, che possono visualizzare le risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="f41b7-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="f41b7-121">Passaggio 2: Creazione di un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="f41b7-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="f41b7-p103">Gli amministratori di Contoso SharePoint innanzitutto creati un nuovo sito del team denominata **ricerca**. Quindi configurate:</span><span class="sxs-lookup"><span data-stu-id="f41b7-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="f41b7-124">Il livello di autorizzazione controllo completo per l'utilizzo del gruppo dei proprietari di ricerca di SharePoint, che presenta il gruppo di sicurezza **Admins Research** come membro</span><span class="sxs-lookup"><span data-stu-id="f41b7-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="f41b7-125">Il livello di autorizzazione Modifica per l'utilizzo del gruppo di SharePoint membri Research, che presenta il gruppo di sicurezza **Membri Research** come membro</span><span class="sxs-lookup"><span data-stu-id="f41b7-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="f41b7-126">Il livello di autorizzazione di lettura per l'utilizzo del gruppo di SharePoint visitatori Research, che presenta il gruppo di sicurezza **Visualizzatori Research** come membro</span><span class="sxs-lookup"><span data-stu-id="f41b7-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="f41b7-127">Ecco i livelli di autorizzazione di SharePoint risultanti, i gruppi di SharePoint e i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="f41b7-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="f41b7-128">Successivamente, vengono configurate restrizioni aggiuntive per il sito.</span><span class="sxs-lookup"><span data-stu-id="f41b7-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="f41b7-129">Per informazioni dettagliate sulla configurazione, vedere [distribuzione di un sito del team di SharePoint Online isolato](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="f41b7-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="f41b7-130">Passaggio 3: Configurare il sito per un'etichetta di Office 365 restrittivo criterio DLP</span><span class="sxs-lookup"><span data-stu-id="f41b7-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="f41b7-131">Per prima cosa, gli amministratori di Contoso applicato l'etichetta di Office 365 **Altamente riservati** al sito di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="f41b7-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="f41b7-132">Successivamente, vengono creati un nuovo criterio DLP di Office 365 denominata **ricerca** :</span><span class="sxs-lookup"><span data-stu-id="f41b7-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="f41b7-133">Utilizza l'etichetta di Office 365 **Altamente riservati** .</span><span class="sxs-lookup"><span data-stu-id="f41b7-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="f41b7-134">Viene applicato al sito di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="f41b7-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="f41b7-135">Impedisce agli utenti di condivisione di documenti.</span><span class="sxs-lookup"><span data-stu-id="f41b7-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="f41b7-136">Per informazioni dettagliate sulla configurazione, vedere [file proteggere SharePoint Online con etichette di Office 365 e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="f41b7-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="f41b7-137">Passaggio 4: Creazione di un'etichetta secondaria Azure Information Protection per il sito</span><span class="sxs-lookup"><span data-stu-id="f41b7-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="f41b7-138">Gli amministratori di Contoso creati una nuova etichetta secondaria Azure Information Protection denominato **Research** dell'etichetta **Altamente riservati** predefinito in un criterio con ambito che:</span><span class="sxs-lookup"><span data-stu-id="f41b7-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="f41b7-139">Richiede la crittografia.</span><span class="sxs-lookup"><span data-stu-id="f41b7-139">Requires encryption.</span></span>
- <span data-ttu-id="f41b7-140">Consente l'accesso completo dai membri del gruppo di sicurezza **Membri Research** .</span><span class="sxs-lookup"><span data-stu-id="f41b7-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="f41b7-141">Consente l'accesso in lettura dai membri del gruppo di protezione **Visualizzatori Research** .</span><span class="sxs-lookup"><span data-stu-id="f41b7-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="f41b7-142">Successivamente, vengono distribuiti client Azure Information Protection per i dispositivi di membri del team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f41b7-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="f41b7-143">Per informazioni dettagliate sulla configurazione, vedere [file proteggere SharePoint Online con la protezione delle informazioni di Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="f41b7-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="f41b7-144">Di seguito è la configurazione del sito di **ricerca** per le risorse altamente riservati risultante.</span><span class="sxs-lookup"><span data-stu-id="f41b7-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="f41b7-145">Passaggio 5: Eseguire la migrazione di dati di ricerca di SharePoint locale</span><span class="sxs-lookup"><span data-stu-id="f41b7-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="f41b7-146">Gli amministratori di Contoso spostati che tutti locale ricerca file nel sito di SharePoint Server 2016 locale alle cartelle del nuovo sito di SharePoint Online di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="f41b7-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="f41b7-147">Passaggio 6: Addestrati agli utenti</span><span class="sxs-lookup"><span data-stu-id="f41b7-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="f41b7-148">Personale addetto alla protezione Contoso addestrati i team di ricerca in un corso obbligatorio che li tramite eseguito l'accesso:</span><span class="sxs-lookup"><span data-stu-id="f41b7-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="f41b7-149">Modalità di accesso del nuovo sito di SharePoint Online di **ricerca** e i relativi file esistente.</span><span class="sxs-lookup"><span data-stu-id="f41b7-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="f41b7-150">Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.</span><span class="sxs-lookup"><span data-stu-id="f41b7-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="f41b7-151">Una dimostrazione di come il criterio DLP consente di bloccare i file da condiviso esternamente.</span><span class="sxs-lookup"><span data-stu-id="f41b7-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="f41b7-152">Come utilizzare il client di Azure Information Protection per etichettare i file di ricerca con l'etichetta secondaria di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="f41b7-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="f41b7-153">Una dimostrazione di come etichetta secondaria **Research** protegge un file anche quando viene compromesso dal sito.</span><span class="sxs-lookup"><span data-stu-id="f41b7-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="f41b7-154">Il risultato finale è un ambiente protetto in cui i ricercatori possono collaborare in tutta l'organizzazione in un ambiente protetto.</span><span class="sxs-lookup"><span data-stu-id="f41b7-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="f41b7-155">Se un documento di ricerca con l'etichetta secondaria di **ricerca** sia compromesso dal sito di **ricerca** , è possibile accedere solo ai membri dei gruppi di sicurezza **Membri Research** e **Visualizzatori di ricerche** con le credenziali valide e crittografati.</span><span class="sxs-lookup"><span data-stu-id="f41b7-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="f41b7-156">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f41b7-156">Next step</span></span>

<span data-ttu-id="f41b7-157">[Distribuire](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f41b7-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

