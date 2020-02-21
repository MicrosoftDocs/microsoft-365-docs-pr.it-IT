---
title: Azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection
description: Panoramica delle funzionalità di indagine e reazione automatizzate in Microsoft Threat Protection
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175935"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="322a1-104">Azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="322a1-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="322a1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="322a1-105">**Applies to:**</span></span>
- <span data-ttu-id="322a1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="322a1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="322a1-107">Le funzionalità di ricerca e risposta automatizzate in Microsoft Threat Protection includono determinate azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="322a1-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="322a1-108">Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint.</span><span class="sxs-lookup"><span data-stu-id="322a1-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="322a1-109">Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="322a1-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="322a1-110">Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="322a1-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="322a1-111">Azioni correttive degli endpoint</span><span class="sxs-lookup"><span data-stu-id="322a1-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="322a1-112">Azioni correttive della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="322a1-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="322a1-113">Quarantena del file</span><span class="sxs-lookup"><span data-stu-id="322a1-113">Quarantine file</span></span><br/><span data-ttu-id="322a1-114">Rimozione della chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="322a1-114">Remove registry key</span></span><br/><span data-ttu-id="322a1-115">Termine del processo</span><span class="sxs-lookup"><span data-stu-id="322a1-115">Kill process</span></span> <br/><span data-ttu-id="322a1-116">Interruzione del servizio</span><span class="sxs-lookup"><span data-stu-id="322a1-116">Stop service</span></span> <br/><span data-ttu-id="322a1-117">Rimozione della chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="322a1-117">Remove registry key</span></span> <br/><span data-ttu-id="322a1-118">Disabilitazione del driver</span><span class="sxs-lookup"><span data-stu-id="322a1-118">Disable driver</span></span> <br/><span data-ttu-id="322a1-119">Rimozione di attività pianificate</span><span class="sxs-lookup"><span data-stu-id="322a1-119">Remove scheduled task</span></span>      |<span data-ttu-id="322a1-120">Eliminazione temporanea di messaggi di posta elettronica o cluster</span><span class="sxs-lookup"><span data-stu-id="322a1-120">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="322a1-121">Blocco di URL (al momento del clic)</span><span class="sxs-lookup"><span data-stu-id="322a1-121">Block URL (time-of-click)</span></span><br/><span data-ttu-id="322a1-122">Disattivazione dell'inoltro della posta elettronica esterna</span><span class="sxs-lookup"><span data-stu-id="322a1-122">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="322a1-123">Le azioni di correzione, sia che siano in attesa di approvazione o che sono già complete, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="322a1-123">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="322a1-124">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="322a1-124">Next steps</span></span>

- [<span data-ttu-id="322a1-125">Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate</span><span class="sxs-lookup"><span data-stu-id="322a1-125">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="322a1-126">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="322a1-126">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
