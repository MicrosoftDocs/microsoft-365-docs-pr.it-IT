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
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417565"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="85b4c-104">Funzionamento delle etichette di riservatezza nelle app di Office</span><span class="sxs-lookup"><span data-stu-id="85b4c-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="85b4c-105">Quali sono i prerequisiti per usare le etichette di riservatezza nelle applicazioni di Office?</span><span class="sxs-lookup"><span data-stu-id="85b4c-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="85b4c-106">Requisiti comuni</span><span class="sxs-lookup"><span data-stu-id="85b4c-106">Common requirements</span></span> 

- <span data-ttu-id="85b4c-107">Occorre [configurare e pubblicare nel Centro sicurezza e conformità](https://aka.ms/managemip) etichette di riservatezza unificate</span><span class="sxs-lookup"><span data-stu-id="85b4c-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="85b4c-108">Gli utenti devono avere effettuato l'accesso a Office con il proprio account aziendale.</span><span class="sxs-lookup"><span data-stu-id="85b4c-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="85b4c-109">Gli utenti devono avere una licenza di Office 365 E3 o superiore.</span><span class="sxs-lookup"><span data-stu-id="85b4c-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="85b4c-110">Requisiti aggiuntivi per Office per Windows</span><span class="sxs-lookup"><span data-stu-id="85b4c-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="85b4c-111">Il client di Azure Information Protection non deve essere in esecuzione in Office.</span><span class="sxs-lookup"><span data-stu-id="85b4c-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="85b4c-112">Vedere anche: [È possibile usare le etichette di riservatezza insieme al client di Azure Information Protection in Office per Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span><span class="sxs-lookup"><span data-stu-id="85b4c-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="85b4c-113">Altri requisiti per Outlook in tutte le piattaforme</span><span class="sxs-lookup"><span data-stu-id="85b4c-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="85b4c-114">Nella configurazione dell'etichetta, se si attiva il contrassegno del contenuto, è necessario usare Exchange Online per inserire il contrassegno del contenuto in transito.</span><span class="sxs-lookup"><span data-stu-id="85b4c-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="85b4c-115">Quali funzionalità delle etichette di riservatezza sono attualmente supportate in Office?</span><span class="sxs-lookup"><span data-stu-id="85b4c-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="85b4c-116"><font size="-1">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="85b4c-116"><font size="-1">Capability</span></span><th><span data-ttu-id="85b4c-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="85b4c-117"><font size="-1">Windows</span></span><th><span data-ttu-id="85b4c-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="85b4c-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="85b4c-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="85b4c-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="85b4c-120">Excel</span><span class="sxs-lookup"><span data-stu-id="85b4c-120">Excel</span></span><br>
<span data-ttu-id="85b4c-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="85b4c-121">PowerPoint</span></span><br>
<span data-ttu-id="85b4c-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="85b4c-122">Outlook</span></span>


<td><span data-ttu-id="85b4c-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="85b4c-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="85b4c-124">Excel</span><span class="sxs-lookup"><span data-stu-id="85b4c-124">Excel</span></span><br>
<span data-ttu-id="85b4c-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="85b4c-125">PowerPoint</span></span><br>
<span data-ttu-id="85b4c-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="85b4c-126">Outlook</span></span>

<td><span data-ttu-id="85b4c-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="85b4c-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="85b4c-128">Excel</span><span class="sxs-lookup"><span data-stu-id="85b4c-128">Excel</span></span><br>
<span data-ttu-id="85b4c-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="85b4c-129">PowerPoint</span></span>
<td><span data-ttu-id="85b4c-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="85b4c-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="85b4c-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="85b4c-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="85b4c-132">Excel</span><span class="sxs-lookup"><span data-stu-id="85b4c-132">Excel</span></span><br>
<span data-ttu-id="85b4c-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="85b4c-133">PowerPoint</span></span>
<td><span data-ttu-id="85b4c-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="85b4c-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="85b4c-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="85b4c-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="85b4c-136">Excel</span><span class="sxs-lookup"><span data-stu-id="85b4c-136">Excel</span></span><br>
<span data-ttu-id="85b4c-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="85b4c-137">PowerPoint</span></span>
<td><span data-ttu-id="85b4c-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="85b4c-139"><font size="-1">Applicare, cambiare o rimuovere manualmente l'etichetta</span><span class="sxs-lookup"><span data-stu-id="85b4c-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="85b4c-140"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="85b4c-142"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="85b4c-144"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="85b4c-146"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-147"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="85b4c-149"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-150"><font size="-1">Presto disponibile<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="85b4c-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="85b4c-151"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="85b4c-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Applicare un'etichetta predefinita</a>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="85b4c-153"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="85b4c-155"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="85b4c-157"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="85b4c-159"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-160"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="85b4c-162"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-163"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-164"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="85b4c-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Richiedere una giustificazione per la modifica di un'etichetta</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="85b4c-166"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="85b4c-168"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="85b4c-170"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="85b4c-172"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-173"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="85b4c-175"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-176"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-177"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="85b4c-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Fornire un collegamento a una pagina della Guida personalizzata</a>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="85b4c-179"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="85b4c-181"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="85b4c-183"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="85b4c-185"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-186"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="85b4c-188"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-189"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-190"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="85b4c-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Contrassegnare il contenuto</a>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="85b4c-192"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="85b4c-194"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="85b4c-196"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="85b4c-198"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-199"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="85b4c-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="85b4c-201"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-202"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-203"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="85b4c-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Assegnare autorizzazioni predefinite</a>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="85b4c-205"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="85b4c-207"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="85b4c-209"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="85b4c-211"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-212"><font size="-1"><b>Sì</b></span><span class="sxs-lookup"><span data-stu-id="85b4c-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="85b4c-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="85b4c-214"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-215"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-216"><font size="-1">Presto disponibile<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="85b4c-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Consentire agli utenti di assegnare autorizzazioni</a>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="85b4c-218"><font size="-1"><b>Sì</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="85b4c-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="85b4c-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="85b4c-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="85b4c-220"><font size="-1"><b>Sì</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="85b4c-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="85b4c-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="85b4c-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="85b4c-222"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-223"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-224"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="85b4c-225"><font size="-1">Presto disponibile<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="85b4c-226"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-227"><font size="-1">Presto disponibile<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="85b4c-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="85b4c-228"><font size="-1">Inviare dati di <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">analisi delle etichette</a> per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="85b4c-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="85b4c-229"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="85b4c-230"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="85b4c-231"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-232"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-233"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-234"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-235"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-236"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="85b4c-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti</a>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="85b4c-238"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="85b4c-239"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="85b4c-240"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-241"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-242"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-243"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-244"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-245"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="85b4c-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Applicare automaticamente un'etichetta di riservatezza al contenuto</a>
</span><span class="sxs-lookup"><span data-stu-id="85b4c-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="85b4c-247"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="85b4c-248"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="85b4c-249"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-250"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-251"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-252"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-253"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="85b4c-254"><font size="-1">Da definire</span><span class="sxs-lookup"><span data-stu-id="85b4c-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="85b4c-255"><sup>1</sup>Se configurato, agli utenti viene chiesto di giustificare il downgrade delle etichette.</span><span class="sxs-lookup"><span data-stu-id="85b4c-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="85b4c-256">Tuttavia, i dati relativi alla giustificazione non sono ancora resi disponibili agli amministratori.</span><span class="sxs-lookup"><span data-stu-id="85b4c-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="85b4c-257">Diventeranno disponibili quando sarà supportata la funzionalità di invio dati di analisi delle etichette per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="85b4c-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="85b4c-258"><sup>2</sup>La funzionalità per consentire agli utenti di assegnare le autorizzazioni è attualmente disponibile solo in Outlook per Windows e per Mac.</span><span class="sxs-lookup"><span data-stu-id="85b4c-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="85b4c-259">La disponibilità per Word, Excel e PowerPoint è da definire.</span><span class="sxs-lookup"><span data-stu-id="85b4c-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="85b4c-260"><sup>3</sup>Previsto per il quarto trimestre 2019.</span><span class="sxs-lookup"><span data-stu-id="85b4c-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="85b4c-261">Quando vengono applicati i contrassegni o la crittografia dopo l'assegnazione di un'etichetta di riservatezza al contenuto?</span><span class="sxs-lookup"><span data-stu-id="85b4c-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="85b4c-262">Applicazione</span><span class="sxs-lookup"><span data-stu-id="85b4c-262">Application</span></span> | <span data-ttu-id="85b4c-263">Contrassegno contenuto</span><span class="sxs-lookup"><span data-stu-id="85b4c-263">Content marking</span></span> | <span data-ttu-id="85b4c-264">Crittografia</span><span class="sxs-lookup"><span data-stu-id="85b4c-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="85b4c-265">Word, Excel, PowerPoint in tutte le piattaforme</span><span class="sxs-lookup"><span data-stu-id="85b4c-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="85b4c-266">Immediatamente.</span><span class="sxs-lookup"><span data-stu-id="85b4c-266">Immediately</span></span> | <span data-ttu-id="85b4c-267">Immediatamente.</span><span class="sxs-lookup"><span data-stu-id="85b4c-267">Immediately</span></span> |
| <span data-ttu-id="85b4c-268">Outlook per PC e Mac</span><span class="sxs-lookup"><span data-stu-id="85b4c-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="85b4c-269">Dopo l'invio del messaggio di posta elettronica da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="85b4c-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="85b4c-270">Immediatamente.</span><span class="sxs-lookup"><span data-stu-id="85b4c-270">Immediately</span></span> |
| <span data-ttu-id="85b4c-271">Outlook sul web, iOS e Android</span><span class="sxs-lookup"><span data-stu-id="85b4c-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="85b4c-272">Dopo l'invio del messaggio di posta elettronica da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="85b4c-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="85b4c-273">Dopo l'invio del messaggio di posta elettronica da Exchange Online</span><span class="sxs-lookup"><span data-stu-id="85b4c-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="85b4c-274">È possibile usare le etichette di riservatezza insieme al client di Azure Information Protection in Office per Windows?</span><span class="sxs-lookup"><span data-stu-id="85b4c-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="85b4c-275">No.</span><span class="sxs-lookup"><span data-stu-id="85b4c-275">No.</span></span> <span data-ttu-id="85b4c-276">Le etichette di riservatezza vengono disattivate se il client di Azure Information Protection viene caricato in Office per Windows.</span><span class="sxs-lookup"><span data-stu-id="85b4c-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="85b4c-277">Se è installato il client di Azure Information Protection, ma si vogliono usare invece le etichette di riservatezza, è possibile:</span><span class="sxs-lookup"><span data-stu-id="85b4c-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="85b4c-278">Configurare l'impostazione di Criteri di gruppo  **Utilizzo della funzionalità Riservatezza di Office per applicare e visualizzare le etichette di riservatezza**, disponibile in **Configurazione utente\Modelli amministrativi/Microsoft Office 2016/Impostazioni di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="85b4c-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="85b4c-279">Nota: questa impostazione può essere distribuita tramite i meccanismi tradizionali di distribuzione di Criteri di gruppo oppure dal [servizio criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span><span class="sxs-lookup"><span data-stu-id="85b4c-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="85b4c-280">In alternativa, è possibile disinstallare o  [disabilitare](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) il client di Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="85b4c-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="85b4c-281">Riavviare tutte le applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="85b4c-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="85b4c-282">Le etichette di riservatezza verranno supportate nelle versioni di Office non in abbonamento, come Office 2016 o Office 2019?</span><span class="sxs-lookup"><span data-stu-id="85b4c-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="85b4c-283">No.</span><span class="sxs-lookup"><span data-stu-id="85b4c-283">No.</span></span> <span data-ttu-id="85b4c-284">Le etichette di riservatezza verranno supportate solo nell'abbonamento a Office 365 e non saranno supportate in alcuna versione non in abbonamento.</span><span class="sxs-lookup"><span data-stu-id="85b4c-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="85b4c-285">Tuttavia, nelle versioni di Office non in abbonamento è possibile usare il  client di etichettatura unificata di Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="85b4c-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="85b4c-286">In precedenza, prima di configurare le etichette di riservatezza. sono stati distribuiti modelli di protezione.</span><span class="sxs-lookup"><span data-stu-id="85b4c-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="85b4c-287">Dove sono finiti?</span><span class="sxs-lookup"><span data-stu-id="85b4c-287">Where did they go?</span></span>

<span data-ttu-id="85b4c-288">Quando sono abilitate le etichette di riservatezza, i [modelli di protezione](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definiti dall'amministratore sono nascosti dall'esperienza utente di Office in quanto ridondanti, visto che le etichette di riservatezza hanno la crittografia abilitata.</span><span class="sxs-lookup"><span data-stu-id="85b4c-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="85b4c-289">Un file o un indirizzo di posta elettronica può avere più di una classificazione?</span><span class="sxs-lookup"><span data-stu-id="85b4c-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="85b4c-290">No.</span><span class="sxs-lookup"><span data-stu-id="85b4c-290">No.</span></span> <span data-ttu-id="85b4c-291">Gli utenti possono selezionare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="85b4c-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="85b4c-292">Quando si etichetta un messaggio di posta elettronica, gli allegati ottengono automaticamente la stessa etichetta?</span><span class="sxs-lookup"><span data-stu-id="85b4c-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="85b4c-293">No.</span><span class="sxs-lookup"><span data-stu-id="85b4c-293">No.</span></span> <span data-ttu-id="85b4c-294">Quando si etichetta un messaggio di posta elettronica con allegati, gli allegati non ereditano la stessa etichetta.</span><span class="sxs-lookup"><span data-stu-id="85b4c-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="85b4c-295">Gli allegati restano senza etichetta o conservano un'eventuale etichetta applicata separatamente.</span><span class="sxs-lookup"><span data-stu-id="85b4c-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="85b4c-296">Tuttavia, se l'etichetta del messaggio di posta elettronica applica la protezione, la protezione viene applicata agli allegati di Office.</span><span class="sxs-lookup"><span data-stu-id="85b4c-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="85b4c-297">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="85b4c-297">Additional resources</span></span>

[<span data-ttu-id="85b4c-298">Domande frequenti sulla classificazione e l'etichettatura in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="85b4c-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="85b4c-299">Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office</span><span class="sxs-lookup"><span data-stu-id="85b4c-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
