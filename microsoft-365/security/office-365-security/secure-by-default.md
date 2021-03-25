---
title: Proteggere per impostazione predefinita in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Ulteriori informazioni sull'impostazione di protezione per impostazione predefinita in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1b495a9c985077dfc88d1da7a221bb60ca10df9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205652"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="13c4b-103">Proteggere per impostazione predefinita in Office 365</span><span class="sxs-lookup"><span data-stu-id="13c4b-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="13c4b-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="13c4b-104">**Applies to**</span></span>
- [<span data-ttu-id="13c4b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="13c4b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="13c4b-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="13c4b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="13c4b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13c4b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="13c4b-108">"Sicuro per impostazione predefinita" è un termine utilizzato per definire le impostazioni predefinite più sicure possibile.</span><span class="sxs-lookup"><span data-stu-id="13c4b-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="13c4b-109">Tuttavia, la sicurezza deve essere bilanciata con la produttività.</span><span class="sxs-lookup"><span data-stu-id="13c4b-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="13c4b-110">Ciò può includere il bilanciamento tra:</span><span class="sxs-lookup"><span data-stu-id="13c4b-110">This can include balancing across:</span></span>

- <span data-ttu-id="13c4b-111">**Usabilità:** le impostazioni non devono essere un mezzo per la produttività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="13c4b-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="13c4b-112">**Rischio:** la sicurezza potrebbe bloccare le attività importanti.</span><span class="sxs-lookup"><span data-stu-id="13c4b-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="13c4b-113">**Impostazioni legacy:** alcune configurazioni per prodotti e funzionalità meno recenti potrebbero dover essere mantenute per motivi aziendali, anche se vengono migliorate nuove impostazioni moderne.</span><span class="sxs-lookup"><span data-stu-id="13c4b-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="13c4b-114">Le organizzazioni di Microsoft 365 con cassette postali in Exchange Online sono protette da Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="13c4b-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="13c4b-115">Questa protezione include:</span><span class="sxs-lookup"><span data-stu-id="13c4b-115">This protection includes:</span></span>

- <span data-ttu-id="13c4b-116">I messaggi di posta elettronica con malware sospetto verranno automaticamente messi in quarantena e i destinatari riceveranno una notifica.</span><span class="sxs-lookup"><span data-stu-id="13c4b-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="13c4b-117">Vedere [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="13c4b-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="13c4b-118">I messaggi di posta elettronica identificati come phishing ad alta probabilità verranno gestiti in base all'azione dei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="13c4b-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="13c4b-119">Vedere [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="13c4b-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="13c4b-120">Per ulteriori informazioni su EOP, vedere [Panoramica di Exchange Online Protection.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="13c4b-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="13c4b-121">Poiché Microsoft vuole proteggere i clienti per impostazione predefinita, alcune sostituzioni dei tenant non vengono applicate per malware o phishing ad alta sicurezza.</span><span class="sxs-lookup"><span data-stu-id="13c4b-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="13c4b-122">Queste sostituzioni includono:</span><span class="sxs-lookup"><span data-stu-id="13c4b-122">These overrides include:</span></span>

- <span data-ttu-id="13c4b-123">Elenchi di mittenti consentiti o elenchi di domini consentiti (criteri di protezione da posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="13c4b-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="13c4b-124">Mittenti attendibili di Outlook</span><span class="sxs-lookup"><span data-stu-id="13c4b-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="13c4b-125">Elenco indirizzi IP consentiti (filtro connessioni)</span><span class="sxs-lookup"><span data-stu-id="13c4b-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="13c4b-126">Per ulteriori informazioni su queste sostituzioni, vedere [Create safe sender lists.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="13c4b-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="13c4b-127">È in corso il processo  di deprecazione dell'azione Sposta il messaggio nella cartella Posta indesiderata per un verdetto di posta elettronica di **phishing** ad alta probabilità nei criteri di protezione da posta indesiderata di EOP.</span><span class="sxs-lookup"><span data-stu-id="13c4b-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="13c4b-128">I criteri di protezione da posta indesiderata che utilizzano questa azione per i messaggi di phishing ad alta probabilità verranno convertiti in **messaggio di quarantena.**</span><span class="sxs-lookup"><span data-stu-id="13c4b-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="13c4b-129">**L'azione Reindirizza messaggio all'indirizzo di** posta elettronica per i messaggi di phishing ad alta probabilità non è influenzata.</span><span class="sxs-lookup"><span data-stu-id="13c4b-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="13c4b-130">La protezione per impostazione predefinita non è un'impostazione che può essere attivata o disattivata, ma è il modo in cui il filtro funziona per mantenere i messaggi potenzialmente pericolosi o indesiderati fuori dalle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="13c4b-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="13c4b-131">Il malware e i messaggi di phishing ad alta probabilità devono essere messi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="13c4b-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="13c4b-132">Solo gli amministratori possono gestire i messaggi messi in quarantena come malware o phishing ad alta probabilità e possono anche segnalare falsi positivi a Microsoft da lì.</span><span class="sxs-lookup"><span data-stu-id="13c4b-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="13c4b-133">Per ulteriori informazioni, vedere [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="13c4b-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="13c4b-134">Ulteriori informazioni sul motivo per cui si sta eseguendo questa operazione</span><span class="sxs-lookup"><span data-stu-id="13c4b-134">More on why we're doing this</span></span>

<span data-ttu-id="13c4b-135">Lo spirito di protezione per impostazione predefinita è: stiamo prendendo la stessa azione sul messaggio che si farebbe se si conoscesse il messaggio dannoso, anche quando un'eccezione configurata consentirebbe altrimenti il recapito del messaggio.</span><span class="sxs-lookup"><span data-stu-id="13c4b-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="13c4b-136">Questo è lo stesso approccio che abbiamo sempre usato per il malware e ora stiamo estendendo questo stesso comportamento ai messaggi di phishing ad alta confidenza.</span><span class="sxs-lookup"><span data-stu-id="13c4b-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="13c4b-137">I nostri dati indicano che un utente ha 30 volte più probabilità di fare clic su un collegamento dannoso nei messaggi nella cartella Posta indesiderata rispetto alla quarantena.</span><span class="sxs-lookup"><span data-stu-id="13c4b-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="13c4b-138">I nostri dati indicano anche che il tasso di falsi positivi (messaggi positivi contrassegnati come non validi) per i messaggi di phishing ad alta probabilità è molto basso e gli amministratori possono risolvere eventuali falsi positivi con invii di amministratori.</span><span class="sxs-lookup"><span data-stu-id="13c4b-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="13c4b-139">È stato inoltre determinato che il mittente consentito e gli elenchi di domini consentiti nei criteri di protezione da posta indesiderata e Mittenti attendibili in Outlook erano troppo ampi e causavano più danni che buoni.</span><span class="sxs-lookup"><span data-stu-id="13c4b-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="13c4b-140">Per dirla in un altro modo: come servizio di sicurezza, microsoft agisce per conto dell'utente per evitare che gli utenti vengano compromessi.</span><span class="sxs-lookup"><span data-stu-id="13c4b-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="13c4b-141">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="13c4b-141">Exceptions</span></span>

<span data-ttu-id="13c4b-142">L'unico override che consente ai messaggi di phishing ad alta probabilità di ignorare il filtro sono le regole del flusso di posta di Exchange (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="13c4b-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="13c4b-143">Per utilizzare le regole del flusso di posta per ignorare il filtro, vedere [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="13c4b-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="13c4b-144">È consigliabile utilizzare le sostituzioni solo negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="13c4b-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="13c4b-145">Simulazioni di phishing: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influisca sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13c4b-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="13c4b-146">Cassette postali Di sicurezza/SecOps: cassette postali dedicate utilizzate dai team di sicurezza per ottenere messaggi non filtrati (sia buoni che non filtrati).</span><span class="sxs-lookup"><span data-stu-id="13c4b-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="13c4b-147">Teams può quindi esaminare per verificare se contengono contenuti dannosi.</span><span class="sxs-lookup"><span data-stu-id="13c4b-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="13c4b-148">Filtri di terze parti: la protezione per impostazione predefinita non si applica quando il record MX del dominio non punta a Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c4b-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="13c4b-149">Falsi positivi: è possibile consentire temporaneamente determinati messaggi ancora in fase di analisi da Microsoft [tramite invii di amministratori.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="13c4b-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="13c4b-150">Come per tutte le sostituzioni, è consigliabile che siano temporanee.</span><span class="sxs-lookup"><span data-stu-id="13c4b-150">As with all overrides, it is recommended that they are temporary.</span></span>
