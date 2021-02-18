---
title: Messaggi di posta elettronica in quarantena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulla quarantena in Exchange Online Protection (EOP) che contiene messaggi potenzialmente pericolosi o indesiderati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47742008af9c1cd0a0a17df9e43ebc0228a825b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288766"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="0f7a4-103">Messaggi di posta elettronica in quarantena in EOP</span><span class="sxs-lookup"><span data-stu-id="0f7a4-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0f7a4-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="0f7a4-104">**Applies to**</span></span>
- [<span data-ttu-id="0f7a4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0f7a4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0f7a4-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="0f7a4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0f7a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f7a4-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="0f7a4-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, la quarantena è disponibile per contenere messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="0f7a4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="0f7a4-109">I criteri antimalware mettere automaticamente in quarantena un messaggio se *viene rilevato* che un allegato contiene malware.</span><span class="sxs-lookup"><span data-stu-id="0f7a4-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="0f7a4-110">Per ulteriori informazioni, vedere [Configurare i criteri antimalware in EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0f7a4-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="0f7a4-111">Per impostazione predefinita, i criteri di protezione dalla posta indesiderata messi in quarantena i messaggi di phishing e recapitare messaggi di posta indesiderata e in blocco nella cartella Posta indesiderata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0f7a4-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="0f7a4-112">Tuttavia, è anche possibile creare e personalizzare i criteri di protezione dalla posta indesiderata per mettere in quarantena la posta indesiderata e i messaggi di posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="0f7a4-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="0f7a4-113">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0f7a4-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="0f7a4-114">Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena:</span><span class="sxs-lookup"><span data-stu-id="0f7a4-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="0f7a4-115">Gli amministratori possono utilizzare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0f7a4-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="0f7a4-116">Solo gli amministratori possono utilizzare i messaggi messi in quarantena come malware, phishing ad alta probabilità o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="0f7a4-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="0f7a4-117">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="0f7a4-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="0f7a4-118">Gli utenti possono lavorare con i messaggi in quarantena dove sono destinatari se il messaggio è stato messo in quarantena come posta indesiderata, posta elettronica in blocco o phishing (a partire da aprile 2020).</span><span class="sxs-lookup"><span data-stu-id="0f7a4-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="0f7a4-119">Per ulteriori informazioni, vedere [Trovare e rilasciare i messaggi in quarantena come utente in EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="0f7a4-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="0f7a4-120">Per impedire agli utenti di gestire i propri messaggi di phishing in quarantena, gli amministratori possono configurare un'azione diversa per il verdetto del filtro della posta elettronica di **phishing** nei criteri di protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="0f7a4-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="0f7a4-121">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0f7a4-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="0f7a4-122">Gli amministratori e gli utenti possono segnalare falsi positivi a Microsoft in quarantena.</span><span class="sxs-lookup"><span data-stu-id="0f7a4-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="0f7a4-123">Per ulteriori informazioni sulla quarantena, vedere [Domande frequenti sulla quarantena.](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="0f7a4-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
