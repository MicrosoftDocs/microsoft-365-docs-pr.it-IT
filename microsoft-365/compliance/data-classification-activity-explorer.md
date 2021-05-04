---
title: Introduzione a Esplora attività
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Esplora attività estende la funzionalità di classificazione dei dati consentendo di visualizzare e filtrare le azioni intraprese dagli utenti sul contenuto etichettato.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114008"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="19802-103">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="19802-103">Get started with activity explorer</span></span>

<span data-ttu-id="19802-104">La [panoramica della classificazione dei](data-classification-overview.md) dati e le schede [di](data-classification-content-explorer.md) Esplora contenuto offrono visibilità sul contenuto individuato ed etichettato e sulla posizione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="19802-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="19802-105">Esplora attività estende questa famiglia di funzionalità, consentendo di monitorare le operazioni eseguite sul contenuto etichettato.</span><span class="sxs-lookup"><span data-stu-id="19802-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="19802-106">Esplora attività offre una visualizzazione cronologica delle attività nel contenuto etichettato.</span><span class="sxs-lookup"><span data-stu-id="19802-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="19802-107">Le informazioni sull'attività vengono raccolte dai Microsoft 365 di controllo unificati, trasformate e rese disponibili nell'interfaccia utente di Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="19802-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![Segnaposto per screenshot della panoramica di Esplora attività](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="19802-109">Sono disponibili per l'uso oltre 30 filtri diversi, alcuni dei quali sono:</span><span class="sxs-lookup"><span data-stu-id="19802-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="19802-110">intervallo di date</span><span class="sxs-lookup"><span data-stu-id="19802-110">date range</span></span>
- <span data-ttu-id="19802-111">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="19802-111">activity type</span></span>
- <span data-ttu-id="19802-112">posizione</span><span class="sxs-lookup"><span data-stu-id="19802-112">location</span></span>
- <span data-ttu-id="19802-113">utente</span><span class="sxs-lookup"><span data-stu-id="19802-113">user</span></span>
- <span data-ttu-id="19802-114">etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="19802-114">sensitivity label</span></span>
- <span data-ttu-id="19802-115">etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="19802-115">retention label</span></span>
- <span data-ttu-id="19802-116">percorso file</span><span class="sxs-lookup"><span data-stu-id="19802-116">file path</span></span>
- <span data-ttu-id="19802-117">Criteri DLP</span><span class="sxs-lookup"><span data-stu-id="19802-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="19802-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="19802-118">Prerequisites</span></span>

<span data-ttu-id="19802-119">A ogni account che accede e usa la classificazione dei dati deve essere assegnata una licenza da uno di questi abbonamenti:</span><span class="sxs-lookup"><span data-stu-id="19802-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="19802-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="19802-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="19802-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="19802-121">Office 365 (E5)</span></span>
- <span data-ttu-id="19802-122">Componente aggiuntivo Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="19802-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="19802-123">Componente aggiuntivo Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="19802-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="19802-124">Protezione delle informazioni e governance di Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="19802-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="19802-125">Conformità di Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="19802-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="19802-126">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="19802-126">Permissions</span></span>

 <span data-ttu-id="19802-127">Per ottenere l'accesso alla scheda Esplora attività, è necessario assegnare esplicitamente a un account l'appartenenza a uno di questi gruppi di ruoli o concedere esplicitamente il ruolo.</span><span class="sxs-lookup"><span data-stu-id="19802-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="19802-128">**Gruppi di ruoli di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="19802-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="19802-129">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="19802-129">Global administrator</span></span>
- <span data-ttu-id="19802-130">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="19802-130">Compliance administrator</span></span>
- <span data-ttu-id="19802-131">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="19802-131">Security administrator</span></span>
- <span data-ttu-id="19802-132">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="19802-132">Compliance data administrator</span></span>

<span data-ttu-id="19802-133">**Microsoft 365 ruoli**</span><span class="sxs-lookup"><span data-stu-id="19802-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="19802-134">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="19802-134">Compliance administrator</span></span>
- <span data-ttu-id="19802-135">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="19802-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="19802-136">Tipi di attività</span><span class="sxs-lookup"><span data-stu-id="19802-136">Activity types</span></span>

<span data-ttu-id="19802-137">Esplora attività raccoglie informazioni sulle attività dai log di controllo su più origini di attività.</span><span class="sxs-lookup"><span data-stu-id="19802-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="19802-138">Per informazioni più dettagliate sull'attività di applicazione di etichette a Esplora attività, vedi Eventi di etichettatura [disponibili in Esplora attività.](data-classification-activity-explorer-available-events.md)</span><span class="sxs-lookup"><span data-stu-id="19802-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="19802-139">**Attività delle etichette** di riservatezza e **attività** di etichettatura di conservazione da applicazioni native di Office, componente aggiuntivo di Azure Information Protection, SharePoint Online, Exchange Online (solo etichette di riservatezza) e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="19802-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="19802-140">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="19802-140">Some examples are:</span></span>

- <span data-ttu-id="19802-141">Etichetta applicata</span><span class="sxs-lookup"><span data-stu-id="19802-141">label applied</span></span>
- <span data-ttu-id="19802-142">Etichetta modificata (sottoposta a upgrade o downgrade oppure rimossa)</span><span class="sxs-lookup"><span data-stu-id="19802-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="19802-143">Simulazione di etichettatura automatica</span><span class="sxs-lookup"><span data-stu-id="19802-143">auto-labeling simulation</span></span>
- <span data-ttu-id="19802-144">file letto</span><span class="sxs-lookup"><span data-stu-id="19802-144">file read</span></span> 

<span data-ttu-id="19802-145">**Scanner Azure Information Protection (AIP) e client AIP**</span><span class="sxs-lookup"><span data-stu-id="19802-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="19802-146">protezione applicata</span><span class="sxs-lookup"><span data-stu-id="19802-146">protection applied</span></span>
- <span data-ttu-id="19802-147">protezione modificata</span><span class="sxs-lookup"><span data-stu-id="19802-147">protection changed</span></span>
- <span data-ttu-id="19802-148">protezione rimossa</span><span class="sxs-lookup"><span data-stu-id="19802-148">protection removed</span></span>
- <span data-ttu-id="19802-149">file individuati</span><span class="sxs-lookup"><span data-stu-id="19802-149">files discovered</span></span> 

<span data-ttu-id="19802-150">Esplora attività raccoglie anche gli eventi corrispondenti ai criteri **DLP** di Exchange Online, SharePoint Online, OneDrive, Teams Chat e canale (anteprima), cartelle e raccolte di SharePoint locali e condivisioni file locali e dispositivi Windows 10 tramite prevenzione della perdita dei dati degli endpoint **(DLP).**</span><span class="sxs-lookup"><span data-stu-id="19802-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="19802-151">Alcuni esempi di eventi Windows 10 dispositivi sono file:</span><span class="sxs-lookup"><span data-stu-id="19802-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="19802-152">eliminazioni</span><span class="sxs-lookup"><span data-stu-id="19802-152">deletions</span></span>
- <span data-ttu-id="19802-153">creazioni</span><span class="sxs-lookup"><span data-stu-id="19802-153">creations</span></span>
- <span data-ttu-id="19802-154">copiato negli Appunti</span><span class="sxs-lookup"><span data-stu-id="19802-154">copied to clipboard</span></span>
- <span data-ttu-id="19802-155">modificati</span><span class="sxs-lookup"><span data-stu-id="19802-155">modified</span></span>
- <span data-ttu-id="19802-156">lettura</span><span class="sxs-lookup"><span data-stu-id="19802-156">read</span></span>
- <span data-ttu-id="19802-157">stampa</span><span class="sxs-lookup"><span data-stu-id="19802-157">printed</span></span>
- <span data-ttu-id="19802-158">ridenominazione</span><span class="sxs-lookup"><span data-stu-id="19802-158">renamed</span></span>
- <span data-ttu-id="19802-159">copiato nella condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="19802-159">copied to network share</span></span>
- <span data-ttu-id="19802-160">accessibile da un'app non consentita</span><span class="sxs-lookup"><span data-stu-id="19802-160">accessed by unallowed app</span></span> 

<span data-ttu-id="19802-161">Il valore di comprendere quali azioni vengono intraprese con il contenuto con etichetta sensibile è che [](dlp-learn-about-dlp.md) è possibile vedere se i controlli già messi in atto, ad esempio la prevenzione della perdita di dati, sono efficaci o meno.</span><span class="sxs-lookup"><span data-stu-id="19802-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="19802-162">Se non sono efficaci o se si individua un comportamento imprevisto, ad esempio un numero elevato di elementi etichettati come `highly confidential` declassato a `general`, è possibile gestire i vari criteri e intraprendere nuove azioni per limitare il comportamento indesiderato.</span><span class="sxs-lookup"><span data-stu-id="19802-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="19802-163">Esplora risorse non esegue il monitoraggio delle attività di conservazione per Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="19802-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="19802-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19802-164">See also</span></span>

- [<span data-ttu-id="19802-165">Informazioni sulle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="19802-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="19802-166">Informazioni sui criteri e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="19802-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="19802-167">Ulteriori informazioni sui tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="19802-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="19802-168">Informazioni sulla classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="19802-168">Learn about data classification</span></span>](data-classification-overview.md)
