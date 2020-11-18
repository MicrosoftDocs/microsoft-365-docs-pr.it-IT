---
title: Protezione per impostazione predefinita in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Per ulteriori informazioni sull'impostazione sicura per impostazione predefinita in Exchange Online Protection (EOP)
ms.openlocfilehash: d4345134e98ae204f73dfb51a0abf5136590a24c
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126662"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="78455-103">Protezione per impostazione predefinita in Office 365</span><span class="sxs-lookup"><span data-stu-id="78455-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="78455-104">"Sicuro per impostazione predefinita" è un termine utilizzato per definire le impostazioni predefinite più sicure possibile.</span><span class="sxs-lookup"><span data-stu-id="78455-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="78455-105">Tuttavia, la sicurezza deve essere bilanciata con la produttività.</span><span class="sxs-lookup"><span data-stu-id="78455-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="78455-106">Ciò può includere il bilanciamento tra:</span><span class="sxs-lookup"><span data-stu-id="78455-106">This can include balancing across:</span></span>

- <span data-ttu-id="78455-107">Usabilità: le impostazioni non devono essere inutilizzate per la produttività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="78455-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="78455-108">Rischio: la sicurezza potrebbe bloccare attività importanti.</span><span class="sxs-lookup"><span data-stu-id="78455-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="78455-109">Impostazioni legacy: potrebbe essere necessario mantenere le configurazioni per i prodotti e le funzionalità meno recenti, anche se sono state migliorate nuove impostazioni moderne.</span><span class="sxs-lookup"><span data-stu-id="78455-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="78455-110">Microsoft 365 le organizzazioni con cassette postali in Exchange Online sono protette da Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="78455-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="78455-111">Questa protezione include:</span><span class="sxs-lookup"><span data-stu-id="78455-111">This protection includes:</span></span>

1. <span data-ttu-id="78455-112">La posta elettronica con sospetto di malware verrà automaticamente messa in quarantena e i destinatari verranno informati.</span><span class="sxs-lookup"><span data-stu-id="78455-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="78455-113">Vedere [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="78455-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="78455-114">La posta elettronica di phishing identificata come "elevata sicurezza" verrà gestita in base all'azione relativa ai criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="78455-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="78455-115">Vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="78455-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="78455-116">Poiché Microsoft desidera mantenere i clienti sicuri per impostazione predefinita, alcune sostituzioni dei tenant non vengono applicate per phishing di malware o high confidence.</span><span class="sxs-lookup"><span data-stu-id="78455-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="78455-117">Tali sostituzioni includono:</span><span class="sxs-lookup"><span data-stu-id="78455-117">These overrides include:</span></span>

- <span data-ttu-id="78455-118">Elenchi mittenti consentiti o elenchi di domini consentiti (criteri di protezione dalla posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="78455-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="78455-119">Mittenti attendibili di Outlook</span><span class="sxs-lookup"><span data-stu-id="78455-119">Outlook Safe senders</span></span>
- <span data-ttu-id="78455-120">Elenco indirizzi IP consentiti (filtro connessioni)</span><span class="sxs-lookup"><span data-stu-id="78455-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="78455-121">Per ulteriori informazioni su tali sostituzioni, vedere [creare elenchi di mittenti attendibili](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="78455-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="78455-122">Sicuro per impostazione predefinita qui non è un'impostazione che potrebbe essere attivata o disattivata, ma il modo in cui il filtro funziona fuori dalla casella per mantenere i messaggi potenzialmente pericolosi o indesiderati fuori dalle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="78455-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="78455-123">Per la quarantena, è necessario inviare malware e phishing con elevata sicurezza.</span><span class="sxs-lookup"><span data-stu-id="78455-123">Malware and high confidence phishing should be sent to quarantine.</span></span> <span data-ttu-id="78455-124">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware o phishing con elevato livello di sicurezza e possono anche segnalare falsi positivi a Microsoft da qui.</span><span class="sxs-lookup"><span data-stu-id="78455-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="78455-125">Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="78455-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="78455-126">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="78455-126">Exceptions</span></span>

<span data-ttu-id="78455-127">L'unica sostituzione che consente ai messaggi di phishing con elevata sicurezza di ignorare il filtro è la regola del flusso di posta di Exchange (nota anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="78455-127">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="78455-128">Per utilizzare le regole del flusso di posta per ignorare il filtro, vedere [Use Mail Flow Rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="78455-128">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="78455-129">Le sostituzioni devono essere utilizzate solo per:</span><span class="sxs-lookup"><span data-stu-id="78455-129">Overrides should only be used for:</span></span>

- <span data-ttu-id="78455-130">Simulazioni di phishing: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influenzi l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78455-130">Phishing simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="78455-131">Cassette postali di sicurezza/secops: cassette postali dedicate utilizzate dai team di sicurezza per ottenere messaggi non filtrati (sia buoni che cattivi).</span><span class="sxs-lookup"><span data-stu-id="78455-131">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="78455-132">I team possono quindi verificare se contengono contenuto dannoso.</span><span class="sxs-lookup"><span data-stu-id="78455-132">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="78455-133">Filtri di terze parti: alcuni fornitori di terze parti consigliano di disattivare EOP (SCL =-1) come filtro di terze parti per gestire il filtro della posta.</span><span class="sxs-lookup"><span data-stu-id="78455-133">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="78455-134">Microsoft non consiglia di disattivare EOP poiché EOP è obbligatorio per Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="78455-134">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="78455-135">Falsi positivi: è possibile che si desideri consentire a alcuni messaggi che vengono ancora analizzati da Microsoft [tramite invii di amministratore](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="78455-135">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="78455-136">Come per tutte le sostituzioni, è consigliabile che siano temporanei.</span><span class="sxs-lookup"><span data-stu-id="78455-136">As with all overrides, it is recommended that they are temporary.</span></span>
