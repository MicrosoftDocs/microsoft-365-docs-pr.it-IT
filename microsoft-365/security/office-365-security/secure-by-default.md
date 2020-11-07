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
description: Informazioni su come trovare e utilizzare i report sulla sicurezza della posta elettronica per l'organizzazione. I report sulla sicurezza della posta elettronica sono disponibili nel centro sicurezza & conformità.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944480"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="780a8-104">Protezione per impostazione predefinita in Office 365</span><span class="sxs-lookup"><span data-stu-id="780a8-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="780a8-105">"Sicuro per impostazione predefinita" è un termine utilizzato per definire le impostazioni predefinite più sicure possibile.</span><span class="sxs-lookup"><span data-stu-id="780a8-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="780a8-106">Tuttavia, la sicurezza deve essere bilanciata con la produttività.</span><span class="sxs-lookup"><span data-stu-id="780a8-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="780a8-107">Ciò può includere il bilanciamento tra:</span><span class="sxs-lookup"><span data-stu-id="780a8-107">This can include balancing across:</span></span>
- <span data-ttu-id="780a8-108">Usabilità: le impostazioni non devono essere inutilizzate per la produttività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="780a8-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="780a8-109">Rischio: la sicurezza potrebbe bloccare attività importanti.</span><span class="sxs-lookup"><span data-stu-id="780a8-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="780a8-110">Impostazioni legacy: potrebbe essere necessario mantenere le configurazioni per i prodotti e le funzionalità meno recenti, anche se sono state migliorate nuove impostazioni moderne.</span><span class="sxs-lookup"><span data-stu-id="780a8-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="780a8-111">Microsoft 365 le organizzazioni con cassette postali in Exchange Online sono protette da Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="780a8-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="780a8-112">Questa protezione include:</span><span class="sxs-lookup"><span data-stu-id="780a8-112">This  protection includes:</span></span>
1. <span data-ttu-id="780a8-113">La posta elettronica con sospetto di malware verrà automaticamente messa in quarantena e i destinatari verranno informati.</span><span class="sxs-lookup"><span data-stu-id="780a8-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="780a8-114">Vedere [Configure anti-malware Policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="780a8-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="780a8-115">La posta elettronica di phishing identificata come "elevata sicurezza" verrà gestita in base all'azione relativa ai criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="780a8-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="780a8-116">Vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="780a8-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="780a8-117">Poiché Microsoft desidera mantenere i clienti sicuri per impostazione predefinita, alcune sostituzioni dei tenant non vengono applicate per phishing di malware o high confidence.</span><span class="sxs-lookup"><span data-stu-id="780a8-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="780a8-118">Tali sostituzioni includono:</span><span class="sxs-lookup"><span data-stu-id="780a8-118">These overrides include:</span></span>
- <span data-ttu-id="780a8-119">Elenchi mittenti consentiti o elenchi di domini consentiti (criteri di protezione dalla posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="780a8-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="780a8-120">Mittenti attendibili di Outlook</span><span class="sxs-lookup"><span data-stu-id="780a8-120">Outlook Safe senders</span></span>
- <span data-ttu-id="780a8-121">Elenco indirizzi IP consentiti (filtro connessioni)</span><span class="sxs-lookup"><span data-stu-id="780a8-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="780a8-122">Per ulteriori informazioni su tali sostituzioni, vedere [creare elenchi di mittenti attendibili](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="780a8-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="780a8-123">Sicuro per impostazione predefinita qui non è un'impostazione che potrebbe essere attivata o disattivata, ma il modo in cui il filtro funziona fuori dalla casella per mantenere i messaggi potenzialmente pericolosi o indesiderati fuori dalle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="780a8-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="780a8-124">I malware e phishing ad alta sicurezza devono essere inviati alla quarantena.</span><span class="sxs-lookup"><span data-stu-id="780a8-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="780a8-125">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware o phishing con elevato livello di sicurezza e possono anche segnalare falsi positivi a Microsoft da qui.</span><span class="sxs-lookup"><span data-stu-id="780a8-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="780a8-126">Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="780a8-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="780a8-127">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="780a8-127">Exceptions</span></span>
<span data-ttu-id="780a8-128">Le uniche sostituzioni che ignoreranno tutti i filtri sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="780a8-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="780a8-129">Regole di trasporto di Exchange (ETR)/mail.</span><span class="sxs-lookup"><span data-stu-id="780a8-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="780a8-130">Utilizzare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi in EOP.</span><span class="sxs-lookup"><span data-stu-id="780a8-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="780a8-131">Elenco Consenti/blocca tenant: gestire gli URL e i file nell'elenco Consenti/blocca tenant.</span><span class="sxs-lookup"><span data-stu-id="780a8-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="780a8-132">Questi tipi di sostituzioni sono utili per:</span><span class="sxs-lookup"><span data-stu-id="780a8-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="780a8-133">Simulazioni di phishing: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale impatti la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="780a8-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="780a8-134">Cassette postali di sicurezza/secops: cassette postali dedicate utilizzate dai team di sicurezza per ottenere messaggi non filtrati (sia buoni che cattivi).</span><span class="sxs-lookup"><span data-stu-id="780a8-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="780a8-135">I team possono quindi verificare se contengono contenuto dannoso.</span><span class="sxs-lookup"><span data-stu-id="780a8-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="780a8-136">Filtri di terze parti: alcuni fornitori di terze parti consigliano di disattivare EOP (SCL =-1) come filtro di terze parti per gestire il filtro della posta.</span><span class="sxs-lookup"><span data-stu-id="780a8-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="780a8-137">Microsoft non consiglia di disattivare EOP poiché EOP è obbligatorio per Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="780a8-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="780a8-138">Falsi positivi: è possibile che si desideri consentire a alcuni messaggi che vengono ancora analizzati da Microsoft [tramite invii di amministratore](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="780a8-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="780a8-139">Come per tutte le sostituzioni, è consigliabile che siano temporanei.</span><span class="sxs-lookup"><span data-stu-id="780a8-139">As with all overrides, it is recommended that they are temporary.</span></span>
