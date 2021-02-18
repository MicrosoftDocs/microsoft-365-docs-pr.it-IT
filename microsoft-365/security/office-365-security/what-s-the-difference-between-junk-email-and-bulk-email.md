---
title: Qual &apos; è la differenza tra posta indesiderata e posta elettronica inviata in blocco?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono conoscere le differenze tra la posta indesiderata (posta indesiderata) e la posta elettronica in blocco (posta grigia) in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290646"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="ff0de-103">Qual è la differenza tra posta indesiderata e posta elettronica in blocco in EOP?</span><span class="sxs-lookup"><span data-stu-id="ff0de-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff0de-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="ff0de-104">**Applies to**</span></span>
- [<span data-ttu-id="ff0de-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ff0de-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ff0de-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="ff0de-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ff0de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff0de-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ff0de-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i clienti a volte si chiedono: "Qual è la differenza tra posta indesiderata e posta elettronica in blocco?"</span><span class="sxs-lookup"><span data-stu-id="ff0de-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="ff0de-109">In questo argomento viene illustrata la differenza e vengono descritti i controlli disponibili in EOP.</span><span class="sxs-lookup"><span data-stu-id="ff0de-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="ff0de-110">**La posta indesiderata** è posta indesiderata, ovvero messaggi indesiderati e universalmente indesiderati (se identificati correttamente).</span><span class="sxs-lookup"><span data-stu-id="ff0de-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="ff0de-111">Per impostazione predefinita, EOP rifiuta la posta indesiderata in base alla reputazione del server di posta elettronica di origine.</span><span class="sxs-lookup"><span data-stu-id="ff0de-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="ff0de-112">Se un messaggio supera il controllo IP di origine, viene inviato al filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ff0de-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="ff0de-113">Se il messaggio viene classificato come posta indesiderata dal filtro posta indesiderata, il messaggio viene (per impostazione predefinita) recapitato ai destinatari previsti e spostato nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ff0de-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="ff0de-114">È possibile configurare le azioni da eseguire sui verdetti del filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ff0de-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="ff0de-115">Per istruzioni, vedere Configurare i criteri di protezione [dalla posta indesiderata in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ff0de-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="ff0de-116">Se non si è d'accordo con il verdetto del filtro della posta indesiderata, è possibile segnalare i messaggi che si considerano posta indesiderata o non indesiderata a Microsoft in diversi modi, come descritto in Segnalare messaggi e file [a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ff0de-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="ff0de-117">**La classificazione della** posta elettronica in blocco (nota anche come posta _grigia)_ è più difficile da classificare.</span><span class="sxs-lookup"><span data-stu-id="ff0de-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="ff0de-118">Mentre la posta indesiderata è una minaccia costante, la posta elettronica in blocco spesso è un messaggio pubblicitario o di marketing una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ff0de-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="ff0de-119">Alcuni utenti desiderano che i messaggi di posta elettronica in blocco (e di fatto, si siano deliberatamente registrati per riceverli), mentre altri utenti considerano la posta elettronica inviata in blocco come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ff0de-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="ff0de-120">Ad esempio, alcuni utenti desiderano ricevere messaggi pubblicitari da Contoso Corporation o inviti a una conferenza imminente sulla cyber security, mentre altri utenti considerano questi stessi messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ff0de-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="ff0de-121">Per ulteriori informazioni sull'identificazione della posta elettronica in blocco, vedere [Bulk complaint level (BCL) in EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="ff0de-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="ff0de-122">Come gestire la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="ff0de-122">How to manage bulk email</span></span>

<span data-ttu-id="ff0de-123">A causa della reazione mista alla posta elettronica in blocco, non sono disponibili indicazioni universali che si applicano a tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ff0de-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="ff0de-124">I criteri di protezione dalla posta indesiderata hanno una soglia BCL predefinita che viene utilizzata per identificare la posta elettronica in blocco come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ff0de-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="ff0de-125">Gli amministratori possono aumentare o ridurre la soglia.</span><span class="sxs-lookup"><span data-stu-id="ff0de-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="ff0de-126">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="ff0de-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="ff0de-127">[Configurare i criteri di protezione dalla posta indesiderata in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ff0de-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="ff0de-128">Impostazioni dei criteri di protezione da posta indesiderata di EOP</span><span class="sxs-lookup"><span data-stu-id="ff0de-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="ff0de-129">Un'altra opzione facile da ignorare: se un utente si lamenta di ricevere posta elettronica in blocco, ma i messaggi sono provenienti da mittenti affidabili che superano il filtro di protezione da posta indesiderata in EOP, fare in modo che l'utente controlli la presenza di un'opzione di annullamento della sottoscrizione nel messaggio di posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="ff0de-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
