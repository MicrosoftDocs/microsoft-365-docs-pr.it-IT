---
title: Informazioni sui criteri delle applicazioni
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Informazioni sui criteri delle applicazioni.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420361"
---
# <a name="learn-about-app-policies"></a><span data-ttu-id="d6df0-103">Informazioni sui criteri delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="d6df0-103">Learn about app policies</span></span>

><span data-ttu-id="d6df0-104">*[Indicazioni sulle licenze di Microsoft 365 per la sicurezza e la conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="d6df0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d6df0-105">La governance delle app Microsoft rileva il comportamento anomalo delle app nel tenant di Microsoft 365 e genera avvisi che è possibile visualizzare, analizzare e risolvere.</span><span class="sxs-lookup"><span data-stu-id="d6df0-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="d6df0-106">Oltre a questa funzionalità di rilevamento predefinita, è possibile usare un insieme di modelli predefiniti per creare criteri di app personalizzati che generano altri avvisi.</span><span class="sxs-lookup"><span data-stu-id="d6df0-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="d6df0-107">Questi criteri per i modelli e i comportamenti delle app e utenti possono proteggere gli utenti dall'uso di app non conformi o dannose e limitare l'accesso delle app rischiose ai dati del tenant.</span><span class="sxs-lookup"><span data-stu-id="d6df0-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="d6df0-108">Ecco una rapida revisione dei ruoli di amministratore necessari per la gestione dei criteri delle app.</span><span class="sxs-lookup"><span data-stu-id="d6df0-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="d6df0-109">Ruolo</span><span class="sxs-lookup"><span data-stu-id="d6df0-109">Role</span></span> | <span data-ttu-id="d6df0-110">Lettura dei criteri</span><span class="sxs-lookup"><span data-stu-id="d6df0-110">Read policies</span></span> | <span data-ttu-id="d6df0-111">Creare, aggiornare o eliminare criteri</span><span class="sxs-lookup"><span data-stu-id="d6df0-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="d6df0-112">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="d6df0-112">Compliance Administrator</span></span> | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| <span data-ttu-id="d6df0-115">Lettore di conformità</span><span class="sxs-lookup"><span data-stu-id="d6df0-115">Compliance Reader</span></span> | ![Segno di spunta](..\media\checkmark.png) |  |
| <span data-ttu-id="d6df0-117">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="d6df0-117">Global Administrator</span></span> | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| <span data-ttu-id="d6df0-120">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="d6df0-120">Global Reader</span></span>  | ![Segno di spunta](..\media\checkmark.png) |  |
| <span data-ttu-id="d6df0-122">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6df0-122">Security Administrator</span></span> | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| <span data-ttu-id="d6df0-125">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6df0-125">Security Reader</span></span>  | ![Segno di spunta](..\media\checkmark.png) |  |
| <span data-ttu-id="d6df0-127">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6df0-127">Security Operator</span></span> | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a><span data-ttu-id="d6df0-130">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d6df0-130">Next step</span></span>

[<span data-ttu-id="d6df0-131">Introduzione ai criteri delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d6df0-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
