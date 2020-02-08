---
title: Distribuire siti di SharePoint Online per tre livelli di protezione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Sintesi: creare e configurare siti del team di SharePoint Online per diversi livelli di protezione delle informazioni.'
ms.openlocfilehash: 8aee0018db9035ca29037448e3d1200471589a7c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595291"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="571f2-103">Distribuire siti di SharePoint Online per tre livelli di protezione</span><span class="sxs-lookup"><span data-stu-id="571f2-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="571f2-p101">Usare i passaggi descritti in questo articolo per progettare e distribuire siti del team di SharePoint Online di base, sensibili e con riservatezza elevata. Per altre informazioni su questi tre livelli di protezione, vedere [Proteggere siti e file di SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="571f2-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="571f2-106">Siti del team di SharePoint Online di base</span><span class="sxs-lookup"><span data-stu-id="571f2-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="571f2-p102">La protezione di siti di base include siti del team pubblici e privati. I siti del team pubblici possono essere individuati e usati da qualsiasi persona dell'organizzazione. I siti privati possono essere individuati e usati solo dai membri del gruppo di Office 365 associato al sito del team. Entrambi questi tipi di siti del team consentono ai membri di condividere il sito con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="571f2-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="571f2-111">Pubblico</span><span class="sxs-lookup"><span data-stu-id="571f2-111">Public</span></span>

<span data-ttu-id="571f2-112">Per creare un sito del team di SharePoint Online di base con accesso pubblico e autorizzazioni, seguire [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="571f2-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="571f2-113">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="571f2-113">Here is your resulting configuration.</span></span>
  
![Protezione di livello di base per un sito del team di SharePoint Online pubblico.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="571f2-115">Privato</span><span class="sxs-lookup"><span data-stu-id="571f2-115">Private</span></span>

<span data-ttu-id="571f2-116">Per creare un sito del team di SharePoint Online di base con accesso privato e autorizzazioni, seguire [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="571f2-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="571f2-117">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="571f2-117">Here is your resulting configuration.</span></span>
  
![Protezione di livello di base per un sito del team di SharePoint Online privato.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="571f2-119">Siti del team di SharePoint Online sensibili</span><span class="sxs-lookup"><span data-stu-id="571f2-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="571f2-120">Un sito del team di SharePoint Online riservato viene avviato come sito del team privato.</span><span class="sxs-lookup"><span data-stu-id="571f2-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="571f2-121">Creare innanzitutto il sito del team di SharePoint Online privato seguendo [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="571f2-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="571f2-122">Successivamente, dal nuovo sito del team di SharePoint Online configurare le altre impostazioni delle autorizzazioni seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="571f2-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="571f2-123">Nella barra degli strumenti del sito del team di SharePoint fare clic sull'icona delle impostazioni, poi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="571f2-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="571f2-124">Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.</span><span class="sxs-lookup"><span data-stu-id="571f2-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="571f2-125">In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="571f2-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="571f2-126">I risultati di queste impostazioni delle autorizzazioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="571f2-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="571f2-127">La possibilità per i membri di condividere con altri membri è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="571f2-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="571f2-128">La possibilità per gli utenti non membri di richiedere l'accesso è abilitata.</span><span class="sxs-lookup"><span data-stu-id="571f2-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="571f2-129">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="571f2-129">Here is your resulting configuration.</span></span>
  
![Protezione di livello riservato per un sito del team di SharePoint Online isolato.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="571f2-131">I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="571f2-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="571f2-132">Siti del team di SharePoint Online con riservatezza elevata</span><span class="sxs-lookup"><span data-stu-id="571f2-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="571f2-133">Un sito del team di SharePoint Online estremamente riservato è un sito del team privato con altre impostazioni delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="571f2-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="571f2-134">Creare innanzitutto il sito del team di SharePoint Online privato seguendo [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="571f2-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="571f2-135">Successivamente, dal nuovo sito del team di SharePoint Online configurare le altre impostazioni delle autorizzazioni seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="571f2-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="571f2-136">Nella barra degli strumenti del sito del team di SharePoint fare clic sull'icona delle impostazioni, poi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="571f2-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="571f2-137">Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.</span><span class="sxs-lookup"><span data-stu-id="571f2-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="571f2-138">In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**.</span><span class="sxs-lookup"><span data-stu-id="571f2-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="571f2-139">Disattivare **Consenti richieste di accesso** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="571f2-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="571f2-140">I risultati di queste impostazioni delle autorizzazioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="571f2-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="571f2-141">La possibilità per i membri di condividere con altri membri è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="571f2-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="571f2-142">La possibilità per gli utenti non membri di richiedere l'accesso è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="571f2-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="571f2-143">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="571f2-143">Here is your resulting configuration.</span></span>
  
![Protezione di livello estremamente riservato per un team di SharePoint Online isolato.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="571f2-145">I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="571f2-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="571f2-146">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="571f2-146">Next step</span></span>

[<span data-ttu-id="571f2-147">Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="571f2-147">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="571f2-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="571f2-148">See also</span></span>

[<span data-ttu-id="571f2-149">Protezione di file e siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="571f2-149">Secure SharePoint Online sites and files</span></span>](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="571f2-150">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile</span><span class="sxs-lookup"><span data-stu-id="571f2-150">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="571f2-151">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="571f2-151">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
