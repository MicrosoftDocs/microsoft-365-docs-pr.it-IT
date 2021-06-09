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
description: Quando si esegue un'analisi Advanced eDiscovery, il threading della posta elettronica analizza una conversazione di posta elettronica e separa ogni messaggio in categorie diverse.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285562"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="fef5a-103">Threading della posta elettronica in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fef5a-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="fef5a-104">Considera una conversazione di posta elettronica che è in corso da un po' di tempo.</span><span class="sxs-lookup"><span data-stu-id="fef5a-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="fef5a-105">Nella maggior parte dei casi, l'ultimo messaggio di posta elettronica nel thread includerà il contenuto di tutti i messaggi di posta elettronica precedenti. Esaminando l'ultimo messaggio di posta elettronica verrà visualizzato un contesto completo della conversazione che si è verificata nel thread.</span><span class="sxs-lookup"><span data-stu-id="fef5a-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="fef5a-106">Il threading della posta elettronica identifica tali messaggi di posta elettronica in modo che i revisori possano esaminare una frazione di documenti raccolti senza perdere alcun contesto.</span><span class="sxs-lookup"><span data-stu-id="fef5a-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="fef5a-107">Cosa fa il threading della posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="fef5a-107">What does email threading do?</span></span>

<span data-ttu-id="fef5a-108">Il threading della posta elettronica analizza ogni messaggio di posta elettronica e lo decostruisce in singoli messaggi. ogni messaggio di posta elettronica è una catena di singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="fef5a-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="fef5a-109">Quindi, analizza tutti i messaggi di posta elettronica nel set di revisione per determinare se un messaggio di posta elettronica ha contenuto univoco o se la catena è interamente contenuta in un altro messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fef5a-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="fef5a-110">Alla fine i messaggi di posta elettronica sono suddivisi in quattro categorie:</span><span class="sxs-lookup"><span data-stu-id="fef5a-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="fef5a-111">**Conversazione completa**: l'ultimo messaggio dell'e-mail include contenuto univoco e l'e-mail contiene tutti gli allegati inclusi in altri messaggi di posta elettronica il cui contenuto è interamente incluso in questa e-mail.</span><span class="sxs-lookup"><span data-stu-id="fef5a-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="fef5a-112">**Conversazione completa senza allegati**: l'ultimo messaggio dell'e-mail include contenuto univoco e l'e-mail, ma non contiene tutti gli allegati inclusi in altri messaggi di posta elettronica il cui contenuto sia interamente incluso in questa e-mail.</span><span class="sxs-lookup"><span data-stu-id="fef5a-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="fef5a-113">**Copia della conversazione completa**: una copia esatta di una conversazione completa o di una conversazione completa senza allegati.</span><span class="sxs-lookup"><span data-stu-id="fef5a-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="fef5a-114">**Nessuno**: il contenuto di questa e-mail è interamente contenuto in una conversazione completa o una conversazione completa senza allegati.</span><span class="sxs-lookup"><span data-stu-id="fef5a-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="fef5a-115">In che modo è diverso dalle conversazioni in Outlook?</span><span class="sxs-lookup"><span data-stu-id="fef5a-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="fef5a-116">A colpo d'occhio, questo sembra simile ai raggruppamenti di conversazioni in Outlook.</span><span class="sxs-lookup"><span data-stu-id="fef5a-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="fef5a-117">Tuttavia, esistono alcune importanti distinzioni.</span><span class="sxs-lookup"><span data-stu-id="fef5a-117">However, there are some important distinctions.</span></span> <span data-ttu-id="fef5a-118">Considerare una conversazione di posta elettronica che è stata suddivisa in due conversazioni; ad esempio, qualcuno ha risposto a un messaggio di posta elettronica che non è l'ultimo della conversazione, quindi gli ultimi due messaggi di posta elettronica nella conversazione hanno contenuto univoco.</span><span class="sxs-lookup"><span data-stu-id="fef5a-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="fef5a-119">Outlook ancora raggruppare i messaggi di posta elettronica in una singola conversazione; leggere solo l'ultimo messaggio di posta elettronica significa mancare il contesto del secondo-ultimo messaggio di posta elettronica, che contiene anche contenuto univoco.</span><span class="sxs-lookup"><span data-stu-id="fef5a-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="fef5a-120">Poiché il threading della posta elettronica analizza ogni messaggio di posta elettronica in singoli componenti e li confronta, il threading della posta elettronica contrassegna entrambi gli ultimi due messaggi come inclusivi, assicurandosi di non perdere alcun contesto finché si leggono tutti i messaggi contrassegnati come inclusivi.</span><span class="sxs-lookup"><span data-stu-id="fef5a-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
