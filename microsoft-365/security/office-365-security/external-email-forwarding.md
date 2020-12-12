---
title: Configurazione e controllo dell'inoltro della posta elettronica esterno, inoltro automatico, accesso negato per 5.7.520, disabilitazione dell'inoltro esterno, l'amministratore ha disabilitato l'inoltro esterno, i criteri di protezione dalla posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 76cd560c3b97bb67d25d2e4ff2c219669c3d4f0d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658882"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="0ea16-103">Controllare l'inoltro automatico di messaggi di posta elettronica esterni in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ea16-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ea16-104">Come amministratore, è possibile che i requisiti della società possano limitare o controllare i messaggi inoltrati automaticamente a destinatari esterni (destinatari all'esterno dell'organizzazione).</span><span class="sxs-lookup"><span data-stu-id="0ea16-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="0ea16-105">L'inoltro della posta elettronica può essere utile, ma può anche rappresentare un rischio per la sicurezza a causa della possibile divulgazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="0ea16-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="0ea16-106">Gli utenti malintenzionati possono utilizzare queste informazioni per attaccare l'organizzazione o i partner.</span><span class="sxs-lookup"><span data-stu-id="0ea16-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="0ea16-107">In Microsoft 365 sono disponibili i seguenti tipi di inoltro automatico:</span><span class="sxs-lookup"><span data-stu-id="0ea16-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="0ea16-108">Gli utenti possono configurare [le regole di posta in arrivo](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) per inoltrare automaticamente i messaggi ai mittenti esterni (deliberatamente o come risultato di un account compromesso).</span><span class="sxs-lookup"><span data-stu-id="0ea16-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="0ea16-109">Gli amministratori possono configurare l' [inoltro delle cassette postali](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (noto anche come _inoltro SMTP_) per inoltrare automaticamente i messaggi ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="0ea16-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="0ea16-110">L'amministratore può scegliere se inoltrare semplicemente i messaggi oppure conservare le copie dei messaggi inoltrati nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0ea16-110">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="0ea16-111">È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="0ea16-111">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="0ea16-112">Sono disponibili tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="0ea16-112">Three settings are available:</span></span>

- <span data-ttu-id="0ea16-113">**Automatico**: l'inoltro automatico esterno è bloccato.</span><span class="sxs-lookup"><span data-stu-id="0ea16-113">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="0ea16-114">L'inoltro automatico interno dei messaggi continuerà a funzionare.</span><span class="sxs-lookup"><span data-stu-id="0ea16-114">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="0ea16-115">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0ea16-115">This is the default setting.</span></span>
- <span data-ttu-id="0ea16-116">**On**: l'inoltro automatico esterno è consentito e non è limitato.</span><span class="sxs-lookup"><span data-stu-id="0ea16-116">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="0ea16-117">**Disattivata**: l'inoltro automatico esterno è disabilitato e si verificherà un rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo) al mittente.</span><span class="sxs-lookup"><span data-stu-id="0ea16-117">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="0ea16-118">Per istruzioni su come configurare queste impostazioni, vedere [configurare il filtro della posta indesiderata in uscita in EOP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="0ea16-118">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0ea16-119">La disattivazione dell'inoltro automatico disattiva le regole di posta in arrivo (utenti) o l'inoltro delle cassette postali (amministratori) che reindirizzano i messaggi agli indirizzi esterni.</span><span class="sxs-lookup"><span data-stu-id="0ea16-119">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="0ea16-120">L'inoltro automatico dei messaggi tra gli utenti interni non è influenzato dalle impostazioni nei criteri di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="0ea16-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="0ea16-121">È possibile visualizzare informazioni sugli utenti che inoltrano automaticamente i messaggi a destinatari esterni nel [rapporto messaggi auto-inoltrati](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="0ea16-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="0ea16-122">Funzionamento delle impostazioni dei criteri di filtro della posta indesiderata in uscita con altri controlli di inoltro della posta elettronica automatici</span><span class="sxs-lookup"><span data-stu-id="0ea16-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="0ea16-123">Come amministratore, è possibile che siano già stati configurati altri controlli per consentire o bloccare l'inoltro automatico della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0ea16-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="0ea16-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0ea16-124">For example:</span></span>

- <span data-ttu-id="0ea16-125">[Domini remoti](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) per consentire o bloccare l'inoltro automatico dei messaggi di posta elettronica ad alcuni o a tutti i domini esterni.</span><span class="sxs-lookup"><span data-stu-id="0ea16-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="0ea16-126">Condizioni e azioni nelle [regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) per rilevare e bloccare automaticamente i messaggi inoltrati ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="0ea16-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="0ea16-127">Le impostazioni del dominio remoto e le regole del flusso di posta sono indipendenti dalle impostazioni nei criteri di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="0ea16-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="0ea16-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0ea16-128">For example:</span></span>

- <span data-ttu-id="0ea16-129">È possibile consentire l'inoltro automatico per un dominio remoto, ma si blocca l'inoltro automatico nei criteri di filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="0ea16-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="0ea16-130">In questo esempio, i messaggi inoltrati automaticamente vengono bloccati.</span><span class="sxs-lookup"><span data-stu-id="0ea16-130">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="0ea16-131">È possibile consentire l'inoltro automatico nei criteri di filtro della posta indesiderata in uscita, ma si utilizzano le regole del flusso di posta o le impostazioni del dominio remoto per bloccare la posta elettronica inoltrata automaticamente</span><span class="sxs-lookup"><span data-stu-id="0ea16-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="0ea16-132">In questo esempio, le regole del flusso di posta o le impostazioni del dominio remoto bloccano automaticamente i messaggi inoltrati.</span><span class="sxs-lookup"><span data-stu-id="0ea16-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="0ea16-133">Questa funzionalità di indipendenza consente di (ad esempio) consentire l'inoltro automatico nei criteri di filtro per la posta indesiderata in uscita, ma usare domini remoti per controllare i domini esterni a cui gli utenti possono inoltrare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="0ea16-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="0ea16-134">Il messaggio di inoltro della posta elettronica bloccato</span><span class="sxs-lookup"><span data-stu-id="0ea16-134">The blocked email forwarding message</span></span>

<span data-ttu-id="0ea16-135">Quando un messaggio viene rilevato come inoltrato automaticamente e il criterio dell'organizzazione *blocca* tale attività, il messaggio viene restituito al mittente in un rapporto di mancato recapito che contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ea16-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
