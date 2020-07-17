---
title: Qual &apos; è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle differenze tra la posta indesiderata (posta indesiderata) e la posta elettronica in blocco (Gray mail) in Exchange Online Protection (EOP).
ms.openlocfilehash: c1f5ca724f7a41d9fc11ed0c93f52a79a6ecc8e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819437"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="6cb79-103">Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco in EOP?</span><span class="sxs-lookup"><span data-stu-id="6cb79-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="6cb79-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, i clienti a volte chiedono: "Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?"</span><span class="sxs-lookup"><span data-stu-id="6cb79-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="6cb79-105">In questo argomento viene illustrata la differenza e vengono descritti i controlli disponibili in EOP.</span><span class="sxs-lookup"><span data-stu-id="6cb79-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="6cb79-106">La **posta** indesiderata è posta indesiderata, ovvero messaggi non richiesti e universalmente non necessari (se identificati correttamente).</span><span class="sxs-lookup"><span data-stu-id="6cb79-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="6cb79-107">Per impostazione predefinita, il EOP respinge la posta indesiderata in base alla reputazione del server di posta elettronica di origine.</span><span class="sxs-lookup"><span data-stu-id="6cb79-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="6cb79-108">Se un messaggio passa il controllo IP di origine, viene inviato al filtro per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6cb79-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="6cb79-109">Se il messaggio viene classificato come posta indesiderata dal filtro posta indesiderata, il messaggio viene (per impostazione predefinita) recapitato ai destinatari previsti e spostato nella cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6cb79-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="6cb79-110">È possibile configurare le azioni da intraprendere sui verdetti del filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6cb79-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="6cb79-111">Per istruzioni, vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6cb79-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="6cb79-112">Se non si è d'accordo con il verdetto del filtro della posta indesiderata, è possibile segnalare i messaggi che si considerano come posta indesiderata o non indesiderata a Microsoft in diversi modi, come descritto in [messaggi e file di report a Microsoft](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6cb79-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="6cb79-113">La posta **elettronica in blocco** (nota anche come _posta grigia_) è più difficile da classificare.</span><span class="sxs-lookup"><span data-stu-id="6cb79-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="6cb79-114">Se la posta indesiderata è una minaccia costante, la posta elettronica in blocco è spesso una pubblicità o un messaggio di marketing.</span><span class="sxs-lookup"><span data-stu-id="6cb79-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="6cb79-115">Alcuni utenti desiderano messaggi di posta elettronica in blocco (e, in effetti, hanno deliberatamente iscritto per riceverli), mentre altri utenti considerano la posta elettronica in blocco come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6cb79-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="6cb79-116">Ad esempio, alcuni utenti desiderano ricevere messaggi pubblicitari dalla Contoso Corporation o inviti a una conferenza imminente sulla sicurezza cibernetica, mentre altri utenti considerano gli stessi messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6cb79-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="6cb79-117">Per ulteriori informazioni sul modo in cui è stato identificato il messaggio di posta elettronica in blocco, vedere [bulk lamentel Level (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="6cb79-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="6cb79-118">Come gestire la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="6cb79-118">How to manage bulk email</span></span>

<span data-ttu-id="6cb79-119">A causa della reazione mista al messaggio di posta elettronica in blocco, non vi sono indicazioni universali valide per ogni organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cb79-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="6cb79-120">I criteri di protezione dalla posta indesiderata hanno una soglia BCL predefinita utilizzata per identificare la posta elettronica in blocco come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6cb79-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="6cb79-121">Gli amministratori possono aumentare o diminuire la soglia.</span><span class="sxs-lookup"><span data-stu-id="6cb79-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="6cb79-122">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6cb79-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="6cb79-123">[Configurazione dei criteri di protezione da posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6cb79-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="6cb79-124">Impostazioni dei criteri di protezione da posta indesiderata di EOP</span><span class="sxs-lookup"><span data-stu-id="6cb79-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="6cb79-125">Un'altra opzione facilmente trascurabile: se un utente si lamenta della ricezione di posta elettronica in blocco, ma i messaggi vengono inviati da mittenti affidabili che passano il filtro per la posta indesiderata in EOP, fare in modo che l'utente verifichi un'opzione di annullamento della sottoscrizione nel messaggio di posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="6cb79-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
