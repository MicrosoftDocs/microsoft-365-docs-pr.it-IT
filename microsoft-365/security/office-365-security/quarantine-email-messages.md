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
description: Gli amministratori possono ottenere informazioni sulla quarantena in Exchange Online Protection (EOP) che contiene messaggi potenzialmente pericolosi o indesiderati.
ms.openlocfilehash: 77eea3140fb96faec4fb5a749422c2bd9da85b45
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202472"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="5dacd-103">Messaggi di posta elettronica in quarantena in EOP</span><span class="sxs-lookup"><span data-stu-id="5dacd-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5dacd-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, la quarantena è disponibile per contenere messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="5dacd-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="5dacd-105">*I* criteri anti-malware consentono di mettere in quarantena automaticamente un messaggio se viene trovato un allegato contenente malware.</span><span class="sxs-lookup"><span data-stu-id="5dacd-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="5dacd-106">Per ulteriori informazioni, vedere [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5dacd-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="5dacd-107">Per impostazione predefinita, la protezione da posta indesiderata consente di mettere in quarantena i messaggi di phishing e inviare messaggi di posta indesiderata alla cartella posta indesiderata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5dacd-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="5dacd-108">Tuttavia, è anche possibile creare e personalizzare i criteri di protezione da posta indesiderata per la quarantena della posta indesiderata e messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5dacd-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="5dacd-109">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5dacd-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="5dacd-110">Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena:</span><span class="sxs-lookup"><span data-stu-id="5dacd-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="5dacd-111">Gli amministratori possono utilizzare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5dacd-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="5dacd-112">Solo gli amministratori possono utilizzare i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="5dacd-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="5dacd-113">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="5dacd-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="5dacd-114">Gli utenti possono lavorare con i messaggi in quarantena dove sono un destinatario se il messaggio è stato messo in quarantena come posta indesiderata, posta in blocco o (da aprile 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="5dacd-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="5dacd-115">Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="5dacd-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="5dacd-116">Per impedire agli utenti di gestire i propri messaggi di phishing in quarantena, gli amministratori possono configurare un'azione diversa per il verdetto del filtro della **posta elettronica di phishing** nei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5dacd-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="5dacd-117">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5dacd-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="5dacd-118">Gli amministratori e gli utenti possono segnalare falsi positivi a Microsoft in quarantena.</span><span class="sxs-lookup"><span data-stu-id="5dacd-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="5dacd-119">Per ulteriori informazioni sulla quarantena, vedere [domande frequenti sulla quarantena](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5dacd-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
