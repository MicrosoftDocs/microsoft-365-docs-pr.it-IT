---
title: Quarantena in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo viene illustrata la quarantena in Microsoft 365. La quarantena contiene messaggi potenzialmente pericolosi o indesiderati.
ms.openlocfilehash: 396be17e07a347ab4d28a3e0b67dd137bda999db
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033867"
---
# <a name="quarantine-email-messages"></a><span data-ttu-id="41c15-104">Messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="41c15-104">Quarantine email messages</span></span>

<span data-ttu-id="41c15-105">Se si è un cliente Microsoft 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena è disponibile per contenere messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="41c15-105">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="41c15-106">*I* criteri anti-malware consentono di mettere in quarantena automaticamente un messaggio se viene trovato un allegato contenente malware.</span><span class="sxs-lookup"><span data-stu-id="41c15-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="41c15-107">Per ulteriori informazioni, vedere [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41c15-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="41c15-108">Per impostazione predefinita, la protezione da posta indesiderata consente di mettere in quarantena i messaggi di phishing e inviare messaggi di posta indesiderata alla cartella posta indesiderata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="41c15-108">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="41c15-109">Tuttavia, è anche possibile creare e personalizzare i criteri di protezione da posta indesiderata per la quarantena della posta indesiderata e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="41c15-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="41c15-110">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41c15-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="41c15-111">Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena:</span><span class="sxs-lookup"><span data-stu-id="41c15-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="41c15-112">Gli amministratori possono utilizzare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="41c15-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="41c15-113">Solo gli amministratori possono utilizzare i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="41c15-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="41c15-114">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="41c15-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="41c15-115">Gli utenti possono lavorare con i messaggi in quarantena dove sono un destinatario se il messaggio è stato messo in quarantena come posta indesiderata, posta elettronica in blocco o (da aprile 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="41c15-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="41c15-116">Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="41c15-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="41c15-117">Per impedire agli utenti di gestire i propri messaggi di phishing in quarantena, gli amministratori possono configurare un'azione diversa per il verdetto del filtro della **posta elettronica di phishing** nei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="41c15-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="41c15-118">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41c15-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="41c15-119">Gli amministratori e gli utenti possono segnalare falsi positivi a Microsoft in quarantena.</span><span class="sxs-lookup"><span data-stu-id="41c15-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="41c15-120">Per ulteriori informazioni sulla quarantena, vedere [domande frequenti sulla quarantena](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="41c15-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
