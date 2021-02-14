---
title: Threading della posta elettronica in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Quando si esegue un'analisi advanced eDiscovery, il threading della posta elettronica analizza una conversazione di posta elettronica e separa ogni messaggio in categorie diverse.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285562"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="477fb-103">Threading della posta elettronica in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="477fb-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="477fb-104">Considera una conversazione di posta elettronica che è in corso da un po' di tempo.</span><span class="sxs-lookup"><span data-stu-id="477fb-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="477fb-105">Nella maggior parte dei casi, l'ultimo messaggio di posta elettronica nel thread includerà il contenuto di tutti i messaggi di posta elettronica precedenti; Esaminando l'ultimo messaggio di posta elettronica, verrà visualizzato un contesto completo della conversazione che si è verificata nel thread.</span><span class="sxs-lookup"><span data-stu-id="477fb-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="477fb-106">Il threading della posta elettronica identifica tali messaggi di posta elettronica in modo che i revisori possano esaminare una frazione di documenti raccolti senza perdere alcun contesto.</span><span class="sxs-lookup"><span data-stu-id="477fb-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="477fb-107">Cosa fa il threading della posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="477fb-107">What does email threading do?</span></span>

<span data-ttu-id="477fb-108">Il threading della posta elettronica analizza ogni messaggio di posta elettronica e lo decostruisce in singoli messaggi; ogni messaggio di posta elettronica è una catena di singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="477fb-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="477fb-109">Quindi, analizza tutti i messaggi di posta elettronica nel set di revisione per determinare se un messaggio di posta elettronica include contenuto univoco o se la catena è interamente contenuta in un messaggio di posta elettronica diverso.</span><span class="sxs-lookup"><span data-stu-id="477fb-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="477fb-110">Alla fine i messaggi di posta elettronica sono suddivisi in quattro categorie:</span><span class="sxs-lookup"><span data-stu-id="477fb-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="477fb-111">**Inclusivo:** l'ultimo messaggio nel messaggio di posta elettronica ha contenuto univoco e il messaggio contiene tutti gli allegati inclusi in altri messaggi di posta elettronica di cui il contenuto è interamente contenuto in questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="477fb-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="477fb-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span><span class="sxs-lookup"><span data-stu-id="477fb-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="477fb-113">**Copia inclusiva**: una copia esatta di un messaggio di posta elettronica inclusivo/inclusivo</span><span class="sxs-lookup"><span data-stu-id="477fb-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="477fb-114">**Nessuno:** il contenuto di questo messaggio di posta elettronica è interamente contenuto in almeno un messaggio di posta elettronica contrassegnato come inclusivo/inclusivo meno.</span><span class="sxs-lookup"><span data-stu-id="477fb-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="477fb-115">In che modo è diverso dalle conversazioni in Outlook?</span><span class="sxs-lookup"><span data-stu-id="477fb-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="477fb-116">A colpo d'occhio, questo sembra simile ai raggruppamenti di conversazioni in Outlook.</span><span class="sxs-lookup"><span data-stu-id="477fb-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="477fb-117">Tuttavia, esistono alcune importanti distinzioni.</span><span class="sxs-lookup"><span data-stu-id="477fb-117">However, there are some important distinctions.</span></span> <span data-ttu-id="477fb-118">Considerare una conversazione di posta elettronica che è stata suddivisa in due conversazioni; ad esempio, qualcuno ha risposto a un messaggio di posta elettronica non più recente della conversazione, quindi gli ultimi due messaggi di posta elettronica nella conversazione hanno entrambi contenuto univoco.</span><span class="sxs-lookup"><span data-stu-id="477fb-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="477fb-119">Outlook ancora raggruppa i messaggi di posta elettronica in una singola conversazione; leggere solo l'ultimo messaggio di posta elettronica significa mancare il contesto del secondo a ultimo messaggio di posta elettronica, che contiene anche contenuto univoco.</span><span class="sxs-lookup"><span data-stu-id="477fb-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="477fb-120">Poiché il threading della posta elettronica analizza ogni messaggio di posta elettronica in singoli componenti e li confronta, il threading della posta elettronica contrassegna entrambi gli ultimi due messaggi di posta elettronica come inclusivi, assicurandosi di non perdere alcun contesto, purché tutti i messaggi di posta elettronica contrassegnati come inclusivi non mancheranno.</span><span class="sxs-lookup"><span data-stu-id="477fb-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
