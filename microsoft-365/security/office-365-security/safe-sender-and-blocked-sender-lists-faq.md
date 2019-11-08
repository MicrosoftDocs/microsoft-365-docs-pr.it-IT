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
ms.openlocfilehash: 03d0bb35f174b1dcc76fa93f5a5411e8a437ea25
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031781"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="983e4-104">Elenchi di mittenti attendibili e bloccati in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="983e4-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="983e4-p102">In qualità di amministratore di Exchange Online o Exchange Online Protection (EOP), è possibile fare in modo che i messaggi di posta elettronica inviati tramite il servizio non vengano classificati come posta indesiderata. Un modo per farlo consiste nel creare elenchi di mittenti attendibili e di mittenti bloccati per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="983e4-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="983e4-107">*Vedere la versione aggiornata dei suggerimenti e delle procedure per la gestione di questi elenchi in qualità di amministratore in* [Impedire che i messaggi di posta elettronica legittimi vengano contrassegnati come posta indesiderata in Exchange Online Protection e Office 365](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span><span class="sxs-lookup"><span data-stu-id="983e4-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="983e4-108">Se non si è un amministratore e si desidera gestire la propria posta indesiderata in Outlook utilizzando un elenco di mittenti attendibili, vedere la procedura descritta nella panoramica di [Informazioni generali sul filtro per la posta indesiderata](https://go.microsoft.com/fwlink/?LinkId=817222).</span><span class="sxs-lookup"><span data-stu-id="983e4-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="983e4-109">Quali sono i limiti dei mittenti attendibili e bloccati in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="983e4-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="983e4-p103">I limiti dei mittenti attendibili e bloccati in Exchange Online sono diversi da quelli di Active Directory e di Outlook. Tali limiti sono elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="983e4-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>
  
- <span data-ttu-id="983e4-112">Limite dei mittenti attendibili: 1.024</span><span class="sxs-lookup"><span data-stu-id="983e4-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="983e4-113">Limite dei mittenti bloccati: 500</span><span class="sxs-lookup"><span data-stu-id="983e4-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="983e4-114">Nota:</span><span class="sxs-lookup"><span data-stu-id="983e4-114">Note:</span></span>
  
<span data-ttu-id="983e4-115">È possibile che si verifichi l'errore descritto in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="983e4-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="983e4-116">Per risolvere il problema, deselezionare la casella di controllo "Considera attendibili i messaggi di posta elettronica provenienti dai contatti personali".</span><span class="sxs-lookup"><span data-stu-id="983e4-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="983e4-117">In alternativa, ridurre la quantità di indirizzi di posta elettronica presenti nella cartella Contatti predefinita per riportarla entro il limite massimo consentito di 1024 in Exchange Online impostato per l'attributo "parametri MaxSafeSenders".</span><span class="sxs-lookup"><span data-stu-id="983e4-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="983e4-118">Per ulteriori informazioni sull'attributo e sul cmdlet Set-Mailbox, vedere l'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="983e4-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="983e4-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="983e4-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a><span data-ttu-id="983e4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="983e4-120">See also</span></span>

[<span data-ttu-id="983e4-121">Sender filtering in Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="983e4-121">Sender filtering in Exchange 2016</span></span>](https://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

