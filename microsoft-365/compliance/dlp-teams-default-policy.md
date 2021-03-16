---
title: Informazioni sui criteri di prevenzione della perdita dei dati predefiniti in Microsoft Teams (anteprima)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Informazioni sui criteri di prevenzione della perdita di dati predefiniti in Microsoft Teams
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826247"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="10f50-103">Informazioni sui criteri di prevenzione della perdita dei dati predefiniti in Microsoft Teams (anteprima)</span><span class="sxs-lookup"><span data-stu-id="10f50-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="10f50-104">[Le funzionalità di prevenzione della](data-loss-prevention-policies.md) perdita dei dati (DLP) sono state estese per includere i messaggi di chat e canali di Microsoft Teams, inclusi i messaggi del canale privato.</span><span class="sxs-lookup"><span data-stu-id="10f50-104">[Data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="10f50-105">Come parte di questa versione, è stato creato un criterio DLP predefinito per i clienti per la prima volta al Centro conformità.</span><span class="sxs-lookup"><span data-stu-id="10f50-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="10f50-106">Si applica a</span><span class="sxs-lookup"><span data-stu-id="10f50-106">Applies to</span></span>

<span data-ttu-id="10f50-107">Qualsiasi tenant concesso in licenza con una o più delle licenze seguenti e con utenti di Teams attivi</span><span class="sxs-lookup"><span data-stu-id="10f50-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="10f50-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="10f50-108">ME5,</span></span> 
- <span data-ttu-id="10f50-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="10f50-109">MA5,</span></span> 
- <span data-ttu-id="10f50-110">Conformità E5/A5,</span><span class="sxs-lookup"><span data-stu-id="10f50-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="10f50-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="10f50-111">IP+G,</span></span> 
- <span data-ttu-id="10f50-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="10f50-112">OE5,</span></span> 
- <span data-ttu-id="10f50-113">Conformità avanzata di O365</span><span class="sxs-lookup"><span data-stu-id="10f50-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="10f50-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="10f50-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="10f50-115">Cosa fa il criterio predefinito?</span><span class="sxs-lookup"><span data-stu-id="10f50-115">What does the default policy do?</span></span>

<span data-ttu-id="10f50-116">Il criterio DLP predefinito tiene traccia di tutti i numeri di carta di credito condivisi internamente ed esternamente all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="10f50-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="10f50-117">Questo criterio è in base all'impostazione predefinita per tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="10f50-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="10f50-118">Non genera suggerimenti per i criteri per gli utenti finali, ma genera un evento Alert e inoltre attiva un messaggio di posta elettronica di bassa gravità per l'amministratore (aggiunto nel criterio).</span><span class="sxs-lookup"><span data-stu-id="10f50-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="10f50-119">L'amministratore può visualizzare le attività e modificare i dettagli dei criteri accedendo al Centro conformità.</span><span class="sxs-lookup"><span data-stu-id="10f50-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="10f50-120">Gli amministratori possono visualizzare questo criterio nel [Centro](https://compliance.microsoft.com/compliancesettings) conformità > criteri di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="10f50-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="10f50-121">![criterio DLP predefinito di Teams](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="10f50-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="10f50-122">Modificare o eliminare il criterio predefinito</span><span class="sxs-lookup"><span data-stu-id="10f50-122">Edit or delete the default policy</span></span>

<span data-ttu-id="10f50-123">Per [modificare il criterio predefinito per migliorare le prestazioni](create-test-tune-dlp-policy.md#tune-a-dlp-policy)o eliminarlo, è sufficiente utilizzare un account con autorizzazioni di gestione della conformità **DLP.**</span><span class="sxs-lookup"><span data-stu-id="10f50-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="10f50-124">Per ulteriori informazioni, vedere [Autorizzazioni](create-test-tune-dlp-policy.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="10f50-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

