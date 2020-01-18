---
title: Elenchi di mittenti attendibili e bloccati in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: In qualità di amministratore di Exchange Online o Exchange Online Protection (EOP), è possibile fare in modo che i messaggi di posta elettronica inviati tramite il servizio non vengano classificati come posta indesiderata. Un modo per farlo consiste nel creare elenchi di mittenti attendibili e di mittenti bloccati per gli utenti dell'organizzazione.
ms.openlocfilehash: 9c281460aeff64226343af5e5608ccf42fc83799
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238393"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="7d096-104">Elenchi di mittenti attendibili e bloccati in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7d096-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="7d096-p102">In qualità di amministratore di Exchange Online o Exchange Online Protection (EOP), è possibile fare in modo che i messaggi di posta elettronica inviati tramite il servizio non vengano classificati come posta indesiderata. Un modo per farlo consiste nel creare elenchi di mittenti attendibili e di mittenti bloccati per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d096-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="7d096-107">*Vedere la versione aggiornata dei suggerimenti e delle procedure per la modalità di utilizzo di questi elenchi come amministratore in* [come impedire che la posta elettronica venga contrassegnata come posta indesiderata in Office 365](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="7d096-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="7d096-108">Se non si è un amministratore e si desidera solo gestire la posta indesiderata in Outlook utilizzando un elenco di mittenti attendibili, vedere la procedura illustrata nella[Panoramica del filtro della posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="7d096-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="7d096-109">Quali sono i limiti dei mittenti attendibili e bloccati in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="7d096-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="7d096-p103">I limiti dei mittenti attendibili e bloccati in Exchange Online sono diversi da quelli di Active Directory e di Outlook. Tali limiti sono elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="7d096-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>

- <span data-ttu-id="7d096-112">Limite dei mittenti attendibili: 1.024</span><span class="sxs-lookup"><span data-stu-id="7d096-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="7d096-113">Limite dei mittenti bloccati: 500</span><span class="sxs-lookup"><span data-stu-id="7d096-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="7d096-114">Nota:</span><span class="sxs-lookup"><span data-stu-id="7d096-114">Note:</span></span>

<span data-ttu-id="7d096-115">È possibile che si verifichi l'errore descritto in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="7d096-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="7d096-116">Per risolvere il problema, deselezionare la casella di controllo "Considera attendibili i messaggi di posta elettronica provenienti dai contatti personali".</span><span class="sxs-lookup"><span data-stu-id="7d096-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="7d096-117">In alternativa, ridurre la quantità di indirizzi di posta elettronica presenti nella cartella Contatti predefinita per riportarla entro il limite massimo consentito di 1024 in Exchange Online impostato per l'attributo "parametri MaxSafeSenders".</span><span class="sxs-lookup"><span data-stu-id="7d096-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="7d096-118">Per ulteriori informazioni sull'attributo e sul cmdlet Set-Mailbox, vedere l'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="7d096-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="7d096-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="7d096-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="7d096-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d096-120">See also</span></span>

[<span data-ttu-id="7d096-121">Filtro mittente in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7d096-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
