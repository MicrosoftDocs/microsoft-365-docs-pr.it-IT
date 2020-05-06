---
title: Threading della posta elettronica-eDiscovery
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
ms.assetid: ''
description: Durante l'esecuzione di un'analisi avanzata di eDiscovery, il threading della posta elettronica analizza una conversazione di posta elettronica e separa ogni messaggio in categorie diverse.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d3c014973996b312e0b51c1d5fae9da808000cf1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035880"
---
# <a name="email-threading"></a><span data-ttu-id="b59fa-103">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b59fa-103">Email threading</span></span>

<span data-ttu-id="b59fa-104">Si consideri una conversazione di posta elettronica che si sta protrattando da un po' di tempo.</span><span class="sxs-lookup"><span data-stu-id="b59fa-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="b59fa-105">Nella maggior parte dei casi, l'ultimo messaggio di posta elettronica sul thread includerà il contenuto di tutti i messaggi di posta elettronica precedenti. la revisione dell'ultimo messaggio di posta elettronica fornirà un contesto completo della conversazione che è stata eseguita nel thread.</span><span class="sxs-lookup"><span data-stu-id="b59fa-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="b59fa-106">Il threading e-mail identifica tali messaggi di posta elettronica in modo che i revisori possano rivedere una frazione dei documenti raccolti senza perdere alcun contesto.</span><span class="sxs-lookup"><span data-stu-id="b59fa-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="b59fa-107">Cosa fa il threading della posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="b59fa-107">What does email threading do?</span></span>

<span data-ttu-id="b59fa-108">Il threading della posta elettronica analizza ogni messaggio di posta elettronica e lo desconstructs ai singoli messaggi; ogni messaggio di posta elettronica è una catena di singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="b59fa-108">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="b59fa-109">Quindi, analizza tutti i messaggi di posta elettronica nel set di revisione per determinare se un messaggio di posta elettronica ha contenuto univoco o se la catena è totalmente contenuta in un altro messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b59fa-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="b59fa-110">Alla fine i messaggi di posta elettronica sono divisi in quattro categorie:</span><span class="sxs-lookup"><span data-stu-id="b59fa-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="b59fa-111">**Inclusive**: l'ultimo messaggio nella posta elettronica ha contenuto univoco e l'indirizzo di posta elettronica include tutti gli allegati inclusi in altri messaggi di posta elettronica di cui il contenuto è totalmente contenuto in questa e-mail.</span><span class="sxs-lookup"><span data-stu-id="b59fa-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="b59fa-112">**Inclusive minus**: l'ultimo messaggio nella posta elettronica ha contenuto univoco, ma la posta elettronica non contiene alcuni degli allegati che sono stati inclusi in altri messaggi di posta elettronica di cui il contenuto è totalmente contenuto in questo indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b59fa-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="b59fa-113">**Copia inclusiva**: una copia esatta di un messaggio di posta elettronica incluso/incluso</span><span class="sxs-lookup"><span data-stu-id="b59fa-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="b59fa-114">**None**: il contenuto di questo messaggio di posta elettronica è totalmente contenuto in almeno un messaggio di posta elettronica contrassegnato come incluso/inclusivo meno.</span><span class="sxs-lookup"><span data-stu-id="b59fa-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="b59fa-115">In che modo è diversa dalle conversazioni in Outlook?</span><span class="sxs-lookup"><span data-stu-id="b59fa-115">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="b59fa-116">A colpo d'occhio, questo sembra molto simile ai gruppi di conversazione in Outlook.</span><span class="sxs-lookup"><span data-stu-id="b59fa-116">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="b59fa-117">Tuttavia, esistono alcune distinzioni importanti.</span><span class="sxs-lookup"><span data-stu-id="b59fa-117">However, there are some important distinctions.</span></span> <span data-ttu-id="b59fa-118">Si consideri una conversazione di posta elettronica che è stata biforcuta in due conversazioni; ad esempio, qualcuno ha risposto a un messaggio di posta elettronica che non è l'ultimo della conversazione in modo che gli ultimi due messaggi di posta elettronica nella conversazione abbiano entrambi contenuto univoco.</span><span class="sxs-lookup"><span data-stu-id="b59fa-118">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="b59fa-119">Outlook potrebbe comunque raggruppare i messaggi di posta elettronica in una singola conversazione; leggere solo l'ultimo messaggio di posta elettronica significherebbe mancare il contesto del penultimo messaggio di posta elettronica, che contiene anche contenuti univoci.</span><span class="sxs-lookup"><span data-stu-id="b59fa-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="b59fa-120">Poiché il threading della posta elettronica analizza tutti i messaggi di posta elettronica in singoli componenti e li confronta, il threading della posta elettronica contrassegna entrambi gli ultimi due messaggi di posta elettronica come inclusivi, assicurando che non mancherà alcun contesto purché vengano lette tutte le e-mail contrassegnate come inclusive.</span><span class="sxs-lookup"><span data-stu-id="b59fa-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
