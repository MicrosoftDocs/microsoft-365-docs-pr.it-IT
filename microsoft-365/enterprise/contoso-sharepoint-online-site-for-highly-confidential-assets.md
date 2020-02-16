---
title: Sito di SharePoint per le risorse digitali estremamente riservate di Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: informazioni sul modo in cui Contoso ha implementato un sito di SharePoint per dati altamente regolamentati per semplificare la collaborazione tra i team di ricerca.'
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068274"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="7ed4c-103">Sito di SharePoint per le risorse digitali estremamente riservate di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="7ed4c-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="7ed4c-104">Le risorse più importanti di Contoso sono la proprietà intellettuale in forma di segreti commerciali, come le tecniche di produzione proprietarie e le specifiche di progettazione per i prodotti in sviluppo.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="7ed4c-105">Tali risorse erano in formato digitale, originariamente memorizzate come file in un sito di SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="7ed4c-106">Quando Contoso ha distribuito Microsoft 365 Enterprise, volevano passare al cloud le risorse digitali locali per semplificare l'accesso e una collaborazione più aperta tra i team di ricerca di Parigi, Mosca, New York, Pechino e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="7ed4c-107">Tuttavia, a causa della loro natura sensibile, l'accesso a questi file deve essere:</span><span class="sxs-lookup"><span data-stu-id="7ed4c-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="7ed4c-108">Limitato all'insieme di utenti autorizzati ad accedervi.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="7ed4c-109">Protetto con un criterio di prevenzione della perdita di dati (DLP) per impedire agli utenti di distribuirli all'esterno del sito.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="7ed4c-110">Crittografati e protetti con autorizzazioni per impedire agli utenti non autorizzati di accedere ai propri contenuti, anche se sono distribuiti all'esterno del sito.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="7ed4c-111">Gli amministratori di sicurezza e di SharePoint nel reparto IT di Contoso hanno deciso di utilizzare un [sito di SharePoint per dati altamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="7ed4c-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="7ed4c-112">Contoso ha utilizzato questi passaggi per creare e proteggere i siti del team di SharePoint per i propri team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="7ed4c-113">Passaggio 1: creazione di un sito del team di SharePoint privato</span><span class="sxs-lookup"><span data-stu-id="7ed4c-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="7ed4c-114">Per proteggere l'accesso al sito di SharePoint, Contoso ha configurato i [criteri di accesso di SharePoint consigliati](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7ed4c-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="7ed4c-115">Successivamente, contoso IT Admins ha compilato un elenco degli account utente per i ricercatori negli uffici Parigi, Mosca, New York, Pechino e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="7ed4c-116">Successivamente, un amministratore IT di Contoso ha creato un nuovo sito del team privato denominato **Research** e ha aggiunto tutti gli account utente per i suoi ricercatori.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="7ed4c-117">Successivamente, sono state configurate le impostazioni di autorizzazione aggiuntive per il sito per impedire ai ricercatori di condividere l'accesso al sito e impedire ai non ricercatori di richiedere l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="7ed4c-118">Passaggio 2: configurazione del sito per un criterio DLP restrittivo</span><span class="sxs-lookup"><span data-stu-id="7ed4c-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="7ed4c-119">Per prima cosa, gli amministratori di Contoso hanno applicato l'etichetta di conservazione di Office 365 **altamente riservata** esistente alla cartella documenti del sito di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="7ed4c-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="7ed4c-120">Successivamente, è stato creato un nuovo criterio DLP di Office 365 denominato **Research** :</span><span class="sxs-lookup"><span data-stu-id="7ed4c-120">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="7ed4c-121">Utilizza l'etichetta di conservazione di Office 365 **estremamente riservata** .</span><span class="sxs-lookup"><span data-stu-id="7ed4c-121">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="7ed4c-122">Blocca gli utenti quando tentano di condividere un asset digitale nel sito di **ricerca** esterno a contoso.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="7ed4c-123">Per informazioni dettagliate sulla configurazione, vedere [proteggere i file di SharePoint con etichette di conservazione e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="7ed4c-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="7ed4c-124">Passaggio 3: creazione di una sottoetichetta di riservatezza di Office 365 per il sito</span><span class="sxs-lookup"><span data-stu-id="7ed4c-124">Step 3: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="7ed4c-125">Gli amministratori di Contoso hanno creato una nuova sottoetichetta di sensitivity di Office 365 denominata **Research Teams** dell'etichetta **altamente riservata** che:</span><span class="sxs-lookup"><span data-stu-id="7ed4c-125">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="7ed4c-126">Richiede la crittografia.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-126">Requires encryption.</span></span>
- <span data-ttu-id="7ed4c-127">Consente le autorizzazioni di creazione condivisa per il gruppo **Research** Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed4c-127">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="7ed4c-128">Si applica al gruppo **Research** Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed4c-128">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="7ed4c-129">Ecco la configurazione risultante del sito del team di **ricerca** per le risorse estremamente riservate.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![La configurazione risultante del sito del team di ricerca per le risorse estremamente riservate](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="7ed4c-131">I file nelle cartelle del sito di **ricerca** sono protetti da:</span><span class="sxs-lookup"><span data-stu-id="7ed4c-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="7ed4c-132">Le autorizzazioni per il sito, che consentono l'accesso solo ai membri del gruppo **Research** Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-132">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="7ed4c-133">Il criterio DLP di **ricerca** , che utilizza l'etichetta di conservazione e le impostazioni **estremamente riservate** che impediscono la condivisione dei file con gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="7ed4c-134">La sottoetichetta di sensitivity dei **team di ricerca** , con la crittografia e le autorizzazioni che viaggiano con il file se sono state spostate o copiate dal sito di **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="7ed4c-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="7ed4c-135">Di seguito è riportato un esempio di un file archiviato nel sito di **ricerca** con la sottoetichetta di riservatezza dei **team di ricerca** assegnati.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![La configurazione risultante del sito del team di ricerca per le risorse estremamente riservate](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="7ed4c-137">Passaggio 4: migrazione dei dati di ricerca di SharePoint locali</span><span class="sxs-lookup"><span data-stu-id="7ed4c-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="7ed4c-138">Gli amministratori di Contoso hanno spostato tutti i file di ricerca locali nel sito di SharePoint Server 2016 locale in cartelle nel nuovo sito di SharePoint per la **ricerca** .</span><span class="sxs-lookup"><span data-stu-id="7ed4c-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="7ed4c-139">Passaggio 5: formazione dei ricercatori</span><span class="sxs-lookup"><span data-stu-id="7ed4c-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="7ed4c-140">Il personale di sicurezza di Contoso ha formato i membri del gruppo **Research** Office 365 in un corso obbligatorio che ha eseguito i seguenti controlli:</span><span class="sxs-lookup"><span data-stu-id="7ed4c-140">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="7ed4c-141">Informazioni su come accedere al nuovo sito di **ricerca** e ai file esistenti.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="7ed4c-142">Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="7ed4c-143">Dimostrazione del modo in cui il criterio DLP della **ricerca** blocca i file dalla condivisione esterna.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="7ed4c-144">Come assegnare etichette ai file con la sottoetichetta di sensitivity dei **team di ricerca** .</span><span class="sxs-lookup"><span data-stu-id="7ed4c-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="7ed4c-145">Dimostrazione del modo in cui l'etichetta secondaria dei **team di ricerca** protegge un file anche quando viene perso dal sito.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="7ed4c-146">Il risultato finale è un ambiente sicuro in cui i ricercatori possono collaborare tra Contoso in un ambiente sicuro su file contenenti informazioni sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="7ed4c-147">Se un documento di ricerca con la sottoetichetta del **team di ricerca** lascia il sito di **ricerca** , è crittografato e accessibile solo ai membri del gruppo **Research** Office 365 con credenziali dell'account utente valide.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="7ed4c-148">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7ed4c-148">Next step</span></span>

<span data-ttu-id="7ed4c-149">[Distribuzione](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ed4c-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ed4c-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ed4c-150">See also</span></span>

<span data-ttu-id="7ed4c-151">[Raccolta di produttività di Microsoft 365](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="7ed4c-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
