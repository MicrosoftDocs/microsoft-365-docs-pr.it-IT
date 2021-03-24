---
title: Configurazione e controllo dell'inoltro esterno della posta elettronica, inoltro automatico, accesso negato 5.7.520, disabilitazione dell'inoltro esterno, L'amministratore ha disabilitato l'inoltro esterno, i criteri di protezione da posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063405"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="6eb97-103">Controllare l'inoltro automatico della posta elettronica esterna in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6eb97-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6eb97-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="6eb97-104">**Applies to**</span></span>
- [<span data-ttu-id="6eb97-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6eb97-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6eb97-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="6eb97-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6eb97-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6eb97-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6eb97-108">Gli amministratori potrebbero avere requisiti aziendali per limitare o controllare i messaggi inoltrati automaticamente a destinatari esterni (destinatari esterni all'organizzazione).</span><span class="sxs-lookup"><span data-stu-id="6eb97-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="6eb97-109">L'inoltro della posta elettronica può essere utile, ma può anche rappresentare un rischio per la sicurezza a causa della potenziale divulgazione di informazioni.</span><span class="sxs-lookup"><span data-stu-id="6eb97-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="6eb97-110">Gli utenti malintenzionati potrebbero usare queste informazioni per attaccare l'organizzazione o i partner.</span><span class="sxs-lookup"><span data-stu-id="6eb97-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="6eb97-111">In Microsoft 365 sono disponibili i seguenti tipi di inoltro automatico:</span><span class="sxs-lookup"><span data-stu-id="6eb97-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="6eb97-112">Gli utenti possono configurare [le regole di Posta](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) in arrivo per inoltrare automaticamente i messaggi ai mittenti esterni (deliberatamente o a seguito di un account compromesso).</span><span class="sxs-lookup"><span data-stu-id="6eb97-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="6eb97-113">Gli amministratori possono configurare [l'inoltro delle cassette](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) postali (noto anche come inoltro _SMTP)_ per inoltrare automaticamente i messaggi ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="6eb97-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="6eb97-114">L'amministratore può scegliere se inoltrare semplicemente i messaggi o conservare copie dei messaggi inoltrati nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="6eb97-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="6eb97-115">È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="6eb97-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="6eb97-116">Sono disponibili tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="6eb97-116">Three settings are available:</span></span>

- <span data-ttu-id="6eb97-117">**Automatico:** l'inoltro esterno automatico è bloccato.</span><span class="sxs-lookup"><span data-stu-id="6eb97-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="6eb97-118">L'inoltro automatico interno dei messaggi continuerà a funzionare.</span><span class="sxs-lookup"><span data-stu-id="6eb97-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="6eb97-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6eb97-119">This is the default setting.</span></span>
- <span data-ttu-id="6eb97-120">**On**: l'inoltro esterno automatico è consentito e non limitato.</span><span class="sxs-lookup"><span data-stu-id="6eb97-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="6eb97-121">**Disattivato:** l'inoltro esterno automatico è disabilitato e verrà visualizzato un rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito) al mittente.</span><span class="sxs-lookup"><span data-stu-id="6eb97-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="6eb97-122">Per istruzioni su come configurare queste impostazioni, vedere [Configure outbound spam filtering in EOP.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="6eb97-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6eb97-123">La disabilitazione dell'inoltro automatico disabilita le regole di Posta in arrivo (utenti) o l'inoltro delle cassette postali (amministratori) che reindirizzano i messaggi a indirizzi esterni.</span><span class="sxs-lookup"><span data-stu-id="6eb97-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="6eb97-124">L'inoltro automatico dei messaggi tra utenti interni non è influenzato dalle impostazioni dei criteri di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="6eb97-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="6eb97-125">È possibile visualizzare le informazioni sugli utenti che inoltrano automaticamente i messaggi ai destinatari esterni nel [rapporto Messaggi inoltrati automaticamente.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="6eb97-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="6eb97-126">Funzionamento delle impostazioni dei criteri di filtro della posta indesiderata in uscita con altri controlli di inoltro automatico della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6eb97-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="6eb97-127">Come amministratore, potresti aver già configurato altri controlli per consentire o bloccare l'inoltro automatico della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6eb97-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="6eb97-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6eb97-128">For example:</span></span>

- <span data-ttu-id="6eb97-129">[Domini remoti per](/exchange/mail-flow-best-practices/remote-domains/remote-domains) consentire o bloccare l'inoltro automatico della posta elettronica ad alcuni o a tutti i domini esterni.</span><span class="sxs-lookup"><span data-stu-id="6eb97-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="6eb97-130">Condizioni e azioni nelle regole del flusso di [posta](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) per rilevare e bloccare i messaggi inoltrati automaticamente ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="6eb97-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="6eb97-131">Le impostazioni del dominio remoto e le regole del flusso di posta sono indipendenti dalle impostazioni dei criteri di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="6eb97-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="6eb97-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6eb97-132">For example:</span></span>

- <span data-ttu-id="6eb97-133">Si consente l'inoltro automatico per un dominio remoto, ma si blocca l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="6eb97-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="6eb97-134">In questo esempio, i messaggi inoltrati automaticamente vengono bloccati.</span><span class="sxs-lookup"><span data-stu-id="6eb97-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="6eb97-135">Si consente l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita, ma si utilizzano le regole del flusso di posta o le impostazioni del dominio remoto per bloccare la posta elettronica inoltrata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6eb97-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="6eb97-136">In questo esempio, le regole del flusso di posta o le impostazioni del dominio remoto bloccano i messaggi inoltrati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6eb97-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="6eb97-137">Questa funzionalità consente, ad esempio, di consentire l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita, ma di utilizzare i domini remoti per controllare i domini esterni a cui gli utenti possono inoltrare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6eb97-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="6eb97-138">Messaggi di inoltro della posta elettronica bloccati</span><span class="sxs-lookup"><span data-stu-id="6eb97-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="6eb97-139">Quando un messaggio viene rilevato come [](configure-the-outbound-spam-policy.md) inoltrato automaticamente e il criterio di filtro della posta indesiderata in uscita blocca tale attività, il messaggio viene restituito al mittente in un rapporto di mancato recapito contenente le informazioni seguenti: </span><span class="sxs-lookup"><span data-stu-id="6eb97-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`