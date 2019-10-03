---
title: Funzionamento delle etichette di riservatezza nelle app di Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Con le etichette di riservatezza è possibile classificare e proteggere il contenuto riservato senza ostacolare la produttività e la capacità di collaborare degli utenti. È possibile usare le etichette di riservatezza per applicare al contenuto etichettato le impostazioni di protezione, ad esempio crittografia o filigrane.
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378653"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="2fbe8-104">Funzionamento delle etichette di riservatezza nelle app di Office</span><span class="sxs-lookup"><span data-stu-id="2fbe8-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="2fbe8-105">Quali sono i prerequisiti per usare le etichette di riservatezza nelle applicazioni di Office?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="2fbe8-106">Requisiti comuni</span><span class="sxs-lookup"><span data-stu-id="2fbe8-106">Common requirements</span></span> 

- <span data-ttu-id="2fbe8-107">Occorre [configurare e pubblicare nel Centro sicurezza e conformità](https://aka.ms/managemip) etichette di riservatezza unificate</span><span class="sxs-lookup"><span data-stu-id="2fbe8-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="2fbe8-108">Gli utenti devono avere effettuato l'accesso a Office con il proprio account aziendale.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="2fbe8-109">Gli utenti devono avere una licenza di Office 365 E3 o superiore.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="2fbe8-110">Requisiti aggiuntivi per Office per Windows</span><span class="sxs-lookup"><span data-stu-id="2fbe8-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="2fbe8-111">Il client di Azure Information Protection non deve essere in esecuzione in Office.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="2fbe8-112">Vedere anche: [È possibile usare le etichette di riservatezza insieme al client di Azure Information Protection in Office per Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span><span class="sxs-lookup"><span data-stu-id="2fbe8-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="2fbe8-113">Altri requisiti per Outlook in tutte le piattaforme</span><span class="sxs-lookup"><span data-stu-id="2fbe8-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="2fbe8-114">Nella configurazione dell'etichetta, se si attiva il contrassegno del contenuto, è necessario usare Exchange Online per inserire il contrassegno del contenuto in transito.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="2fbe8-115">Quali funzionalità delle etichette di riservatezza sono attualmente supportate in Office?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="2fbe8-116"><font size="-1">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="2fbe8-116"><font size="-1"></span></span><th><span data-ttu-id="2fbe8-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="2fbe8-117"><font size="-1">Windows</span></span><th><span data-ttu-id="2fbe8-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="2fbe8-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="2fbe8-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2fbe8-119"><font size="-1">Word</span></span><br>
<span data-ttu-id="2fbe8-120">Excel</span><span class="sxs-lookup"><span data-stu-id="2fbe8-120">Excel</span></span><br>
<span data-ttu-id="2fbe8-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2fbe8-121">PowerPoint</span></span><br>
<span data-ttu-id="2fbe8-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="2fbe8-122">Outlook</span></span>


<td><span data-ttu-id="2fbe8-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2fbe8-123"><font size="-1">Word</span></span><br>
<span data-ttu-id="2fbe8-124">Excel</span><span class="sxs-lookup"><span data-stu-id="2fbe8-124">Excel</span></span><br>
<span data-ttu-id="2fbe8-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2fbe8-125">PowerPoint</span></span><br>
<span data-ttu-id="2fbe8-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="2fbe8-126">Outlook</span></span>

<td><span data-ttu-id="2fbe8-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2fbe8-127"><font size="-1">Word</span></span><br>
<span data-ttu-id="2fbe8-128">Excel</span><span class="sxs-lookup"><span data-stu-id="2fbe8-128">Excel</span></span><br>
<span data-ttu-id="2fbe8-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2fbe8-129">PowerPoint</span></span>
<td><span data-ttu-id="2fbe8-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="2fbe8-130"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="2fbe8-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2fbe8-131"><font size="-1">Word</span></span><br>
<span data-ttu-id="2fbe8-132">Excel</span><span class="sxs-lookup"><span data-stu-id="2fbe8-132">Excel</span></span><br>
<span data-ttu-id="2fbe8-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2fbe8-133">PowerPoint</span></span>
<td><span data-ttu-id="2fbe8-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="2fbe8-134"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="2fbe8-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="2fbe8-135"><font size="-1">Word</span></span><br>
<span data-ttu-id="2fbe8-136">Excel</span><span class="sxs-lookup"><span data-stu-id="2fbe8-136">Excel</span></span><br>
<span data-ttu-id="2fbe8-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2fbe8-137">PowerPoint</span></span>
<td><span data-ttu-id="2fbe8-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-138">Outlook</span></span></tr>

<tr>
<td><span data-ttu-id="2fbe8-139"><font size="-1">Applicare, cambiare o rimuovere manualmente l'etichetta</span><span class="sxs-lookup"><span data-stu-id="2fbe8-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="2fbe8-140"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-140">Yes.</span></span><br><span data-ttu-id="2fbe8-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2fbe8-142"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-142">Yes.</span></span><br><span data-ttu-id="2fbe8-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2fbe8-144"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-144">Yes.</span></span><br><span data-ttu-id="2fbe8-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2fbe8-146"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-147"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-147">Yes.</span></span><br><span data-ttu-id="2fbe8-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2fbe8-149"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-150"><font size="-1">Presto disponibile<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2fbe8-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="2fbe8-151"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="2fbe8-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Applicare un'etichetta predefinita</a>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="2fbe8-153"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-153">Yes.</span></span><br><span data-ttu-id="2fbe8-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2fbe8-155"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-155">Yes.</span></span><br><span data-ttu-id="2fbe8-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2fbe8-157"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-157">Yes.</span></span><br><span data-ttu-id="2fbe8-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2fbe8-159"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-160"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-160">Yes.</span></span><br><span data-ttu-id="2fbe8-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2fbe8-162"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-163"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-164"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2fbe8-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Richiedere una giustificazione per la modifica di un'etichetta</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="2fbe8-166"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-166">Yes.</span></span><br><span data-ttu-id="2fbe8-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2fbe8-168"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-168">Yes.</span></span><br><span data-ttu-id="2fbe8-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2fbe8-170"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-170">Yes.</span></span><br><span data-ttu-id="2fbe8-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2fbe8-172"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-173"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-173">Yes.</span></span><br><span data-ttu-id="2fbe8-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2fbe8-175"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-176"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-177"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2fbe8-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Fornire un collegamento a una pagina della Guida personalizzata</a>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="2fbe8-179"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-179">Yes.</span></span><br><span data-ttu-id="2fbe8-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2fbe8-181"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-181">Yes.</span></span><br><span data-ttu-id="2fbe8-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2fbe8-183"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-183">Yes.</span></span><br><span data-ttu-id="2fbe8-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2fbe8-185"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-186"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-186">Yes.</span></span><br><span data-ttu-id="2fbe8-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2fbe8-188"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-189"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-190"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2fbe8-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Contrassegnare il contenuto</a>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="2fbe8-192"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-192">Yes.</span></span><br><span data-ttu-id="2fbe8-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2fbe8-194"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-194">Yes.</span></span><br><span data-ttu-id="2fbe8-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2fbe8-196"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-196">Yes.</span></span><br><span data-ttu-id="2fbe8-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2fbe8-198"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-199"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-199">Yes.</span></span><br><span data-ttu-id="2fbe8-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="2fbe8-201"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-202"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-203"><font size="-1">Presto disponibile<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2fbe8-203"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="2fbe8-204"><font size="-1">Assegnare autorizzazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="2fbe8-204"><font size="-1">Assign pre-defined permissions</span></span>
<td><span data-ttu-id="2fbe8-205"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-205">Yes.</span></span><br><span data-ttu-id="2fbe8-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2fbe8-207"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-207">Yes.</span></span><br><span data-ttu-id="2fbe8-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="2fbe8-209"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-209">Yes.</span></span><br><span data-ttu-id="2fbe8-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="2fbe8-211"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-212"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="2fbe8-212">Yes.</span></span><br><span data-ttu-id="2fbe8-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="2fbe8-214"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-215"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-216"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="2fbe8-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Consentire agli utenti di assegnare autorizzazioni</a>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-217">Let users assign permissions</span></span><td><span data-ttu-id="2fbe8-218"><font size="-1"><b>Sì</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2fbe8-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="2fbe8-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="2fbe8-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="2fbe8-220"><font size="-1"><b>Sì</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2fbe8-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="2fbe8-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="2fbe8-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="2fbe8-222"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-223"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-224"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="2fbe8-225"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="2fbe8-226"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-227"><font size="-1">Presto disponibile<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2fbe8-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="2fbe8-228"><font size="-1">Inviare dati di <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">analisi delle etichette</a> per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="2fbe8-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="2fbe8-229"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2fbe8-230"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2fbe8-231"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-232"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-233"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-234"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-235"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-236"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="2fbe8-237"><font size="-1">Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti</span><span class="sxs-lookup"><span data-stu-id="2fbe8-237"><font size="-1">Require users to apply a label to their email and documents</span></span>
<td><span data-ttu-id="2fbe8-238"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2fbe8-239"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2fbe8-240"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-241"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-242"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-243"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-244"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-245"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="2fbe8-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Applicare automaticamente un'etichetta di riservatezza al contenuto</a>
</span><span class="sxs-lookup"><span data-stu-id="2fbe8-246">Apply a sensitivity label to content automatically</span></span><td><span data-ttu-id="2fbe8-247"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2fbe8-248"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="2fbe8-249"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-250"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-251"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-252"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-253"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="2fbe8-254"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="2fbe8-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="2fbe8-255"><sup>1</sup>Se configurato, agli utenti viene chiesto di giustificare il downgrade delle etichette.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="2fbe8-256">Tuttavia, i dati relativi alla giustificazione non sono ancora resi disponibili agli amministratori.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="2fbe8-257">Diventeranno disponibili quando sarà supportata la funzionalità di invio dati di analisi delle etichette per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="2fbe8-258"><sup>2</sup>La funzionalità per consentire agli utenti di assegnare le autorizzazioni è attualmente disponibile solo in Outlook per Windows e per Mac.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="2fbe8-259">La disponibilità per Word, Excel e PowerPoint è da definire.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="2fbe8-260"><sup>3</sup>Previsto per il quarto trimestre 2019.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="2fbe8-261">Quando vengono applicati i contrassegni o la crittografia dopo l'assegnazione di un'etichetta di riservatezza al contenuto?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="2fbe8-262">Applicazione</span><span class="sxs-lookup"><span data-stu-id="2fbe8-262">Application</span></span> | <span data-ttu-id="2fbe8-263">Contrassegno contenuto</span><span class="sxs-lookup"><span data-stu-id="2fbe8-263">Content marking</span></span> | <span data-ttu-id="2fbe8-264">Crittografia</span><span class="sxs-lookup"><span data-stu-id="2fbe8-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="2fbe8-265">Word, Excel, PowerPoint in tutte le piattaforme</span><span class="sxs-lookup"><span data-stu-id="2fbe8-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="2fbe8-266">Immediatamente.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-266">Immediately</span></span> | <span data-ttu-id="2fbe8-267">Immediatamente.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-267">Immediately</span></span> |
| <span data-ttu-id="2fbe8-268">Outlook per PC e Mac</span><span class="sxs-lookup"><span data-stu-id="2fbe8-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="2fbe8-269">Dopo l'invio del messaggio di posta elettronica da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2fbe8-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="2fbe8-270">Immediatamente.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-270">Immediately</span></span> |
| <span data-ttu-id="2fbe8-271">Word, Excel, PowerPoint in tutte le piattaforme</span><span class="sxs-lookup"><span data-stu-id="2fbe8-271">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="2fbe8-272">Dopo l'invio del messaggio di posta elettronica da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2fbe8-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="2fbe8-273">Dopo l'invio del messaggio di posta elettronica da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2fbe8-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="2fbe8-274">È possibile usare le etichette di riservatezza insieme al client di Azure Information Protection in Office per Windows?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="2fbe8-275">No.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-275">No.</span></span> <span data-ttu-id="2fbe8-276">Le etichette di riservatezza vengono disattivate se il client di Azure Information Protection viene caricato in Office per Windows.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="2fbe8-277">Se è installato il client di Azure Information Protection, ma si vogliono usare invece le etichette di riservatezza, è possibile:</span><span class="sxs-lookup"><span data-stu-id="2fbe8-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="2fbe8-278">Configurare l'impostazione di Criteri di gruppo  **Utilizzo della funzionalità Riservatezza di Office per applicare e visualizzare le etichette di riservatezza**, disponibile in **Configurazione utente\Modelli amministrativi/Microsoft Office 2016/Impostazioni di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="2fbe8-279">Nota: questa impostazione può essere distribuita tramite i meccanismi tradizionali di distribuzione di Criteri di gruppo oppure dal [servizio criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span><span class="sxs-lookup"><span data-stu-id="2fbe8-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="2fbe8-280">In alternativa, è possibile disinstallare o  [disabilitare](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) il client di Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="2fbe8-281">Riavviare tutte le applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="2fbe8-282">Le etichette di riservatezza verranno supportate nelle versioni di Office non in abbonamento, come Office 2016 o Office 2019?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="2fbe8-283">No.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-283">No.</span></span> <span data-ttu-id="2fbe8-284">Le etichette di riservatezza verranno supportate solo nell'abbonamento a Office 365 e non saranno supportate in alcuna versione non in abbonamento.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="2fbe8-285">Tuttavia, nelle versioni di Office non in abbonamento è possibile usare il  client di etichettatura unificata di Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="2fbe8-286">In precedenza, prima di configurare le etichette di riservatezza. sono stati distribuiti modelli di protezione.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="2fbe8-287">Dove sono finiti?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-287">Where did they go?</span></span>

<span data-ttu-id="2fbe8-288">Quando sono abilitate le etichette di riservatezza, i [modelli di protezione](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definiti dall'amministratore sono nascosti dall'esperienza utente di Office in quanto ridondanti, visto che le etichette di riservatezza hanno la crittografia abilitata.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="2fbe8-289">Un file o un indirizzo di posta elettronica può avere più di una classificazione?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="2fbe8-290">Gli utenti possono selezionare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica, il che spesso si traduce in una sola classificazione.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-290">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span> <span data-ttu-id="2fbe8-291">Tuttavia, se un utente seleziona una sottoetichetta, in realtà applica due etichette contemporaneamente, un'etichetta primaria e un'etichetta secondaria.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-291">However, if users select a sublabel, this actually applies two labels at the same time; a primary label and a secondary label.</span></span> <span data-ttu-id="2fbe8-292">Usando le etichette secondarie, un file può avere due classificazioni che denotano una relazione padre/figlio per un ulteriore livello di controllo.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-292">By using sublabels, a file can have two classifications that denote a parent/child relationship for an additional level of control.</span></span> 

<span data-ttu-id="2fbe8-293">Ad esempio, l'etichetta  **Riservato**  potrebbe contenere etichette secondarie come  **Legale**  e  **Finanza**.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-293">For example, the label **Confidential** might contain sublabels such as **Legal** and **Finance**.</span></span> <span data-ttu-id="2fbe8-294">È possibile applicare alle etichette secondarie contrassegni visivi di classificazione diversi e modelli di Rights Management diversi.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-294">You can apply different classification visual markings and different Rights Management templates to these sublabels.</span></span> <span data-ttu-id="2fbe8-295">Un utente non può selezionare l'etichetta  **Riservato**  da sola, ma solo con una delle relative sottoetichette, ad esempio  **Legale**.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-295">A user cannot select the **Confidential** label by itself; only one of its sublabels, such as **Legal**.</span></span> <span data-ttu-id="2fbe8-296">Di conseguenza, l'etichetta visualizzata sarà  **Riservato** / **Legale**.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-296">As a result, the label that they see set is **Confidential** / **Legal**.</span></span> <span data-ttu-id="2fbe8-297">I metadati per quel file includono una proprietà di testo personalizzata per  **Riservato**, una proprietà di testo personalizzata per  **Legale** e un'altra che contiene entrambi i valori (**Riservato Legale**).</span><span class="sxs-lookup"><span data-stu-id="2fbe8-297">The metadata for that file includes one custom text property for **Confidential**, one custom text property for **Legal**, and another that contains both values (**Confidential Legal**).</span></span> 

<span data-ttu-id="2fbe8-298">Quando si usano etichette secondarie, non configurare contrassegni visivi, protezione e condizioni sull'etichetta principale.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-298">When you use sublabels, don't configure visual markings, protection, and conditions at the primary label.</span></span> <span data-ttu-id="2fbe8-299">Quando si usano sottolivelli, configurare queste impostazioni solo per l'etichetta secondaria.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-299">When you use sublevels, configure these setting on the sublabel only.</span></span> <span data-ttu-id="2fbe8-300">Se si configurano queste impostazioni sull'etichetta primaria e l'etichetta secondaria corrispondente, le impostazioni dell'etichetta secondaria hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-300">If you configure these settings on the primary label and its sublabel, the settings at the sublabel take precedence.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="2fbe8-301">Quando si etichetta un messaggio di posta elettronica, gli allegati ottengono automaticamente la stessa etichetta?</span><span class="sxs-lookup"><span data-stu-id="2fbe8-301">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="2fbe8-302">No.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-302">No.</span></span> <span data-ttu-id="2fbe8-303">Quando si etichetta un messaggio di posta elettronica con allegati, gli allegati non ereditano la stessa etichetta.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-303">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="2fbe8-304">Gli allegati restano senza etichetta o conservano un'eventuale etichetta applicata separatamente.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-304">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="2fbe8-305">Tuttavia, se l'etichetta del messaggio di posta elettronica applica la protezione, la protezione viene applicata agli allegati di Office.</span><span class="sxs-lookup"><span data-stu-id="2fbe8-305">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2fbe8-306">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="2fbe8-306">Additional resources</span></span>

[<span data-ttu-id="2fbe8-307">Domande frequenti sulla classificazione e l'etichettatura in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="2fbe8-307">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="2fbe8-308">Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office</span><span class="sxs-lookup"><span data-stu-id="2fbe8-308">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)