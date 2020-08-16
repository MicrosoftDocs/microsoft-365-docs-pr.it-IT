---
title: Note sulla versione del supporto Conformità Microsoft 365 per i set di caratteri a due byte (anteprima)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Note sulla versione del supporto per i set di caratteri a due byte.
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695257"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="50abe-103">Note sulla versione del supporto per i set di caratteri a due byte (anteprima)</span><span class="sxs-lookup"><span data-stu-id="50abe-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="50abe-104">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte nelle lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="50abe-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="50abe-105">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="50abe-105">Chinese (simplified)</span></span>
- <span data-ttu-id="50abe-106">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="50abe-106">Chinese (traditional)</span></span>
- <span data-ttu-id="50abe-107">Coreano</span><span class="sxs-lookup"><span data-stu-id="50abe-107">Korean</span></span>
- <span data-ttu-id="50abe-108">Giapponese</span><span class="sxs-lookup"><span data-stu-id="50abe-108">Japanese</span></span>

<span data-ttu-id="50abe-109">La versione di anteprima è disponibile solo nel cloud commerciale e l'implementazione è limitata ai paesi o aree geografiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="50abe-109">This preview is only in the commercial cloud and the rollout is limited to:</span></span>

- <span data-ttu-id="50abe-110">Giappone</span><span class="sxs-lookup"><span data-stu-id="50abe-110">Japan</span></span>
- <span data-ttu-id="50abe-111">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="50abe-111">Korea</span></span>
- <span data-ttu-id="50abe-112">Cina</span><span class="sxs-lookup"><span data-stu-id="50abe-112">China</span></span>
- <span data-ttu-id="50abe-113">RAS di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="50abe-113">Hong Kong</span></span>
- <span data-ttu-id="50abe-114">RAS di Macao</span><span class="sxs-lookup"><span data-stu-id="50abe-114">Macau</span></span>
- <span data-ttu-id="50abe-115">Taiwan</span><span class="sxs-lookup"><span data-stu-id="50abe-115">Taiwan</span></span>

<span data-ttu-id="50abe-116">Il supporto è disponibile per i tipi di informazioni sensibili e i dizionari di parole chiave e riguarda le soluzioni di prevenzione della perdita dei dati, conformità alle comunicazioni, Exchange Online, SharePoint Online, OneDrive for Business e Teams.</span><span class="sxs-lookup"><span data-stu-id="50abe-116">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="50abe-117">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="50abe-117">Known issues</span></span>

- <span data-ttu-id="50abe-118">Se un file di testo allegato a un messaggio di posta elettronica è in formato UTF-8 senza BOM (Byte Order Mark), il messaggio non viene rilevato dai criteri di conformità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="50abe-118">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="50abe-119">I criteri di conformità delle comunicazioni non rilevano valori se viene immessa una frase per la condizione del criterio: “Il messaggio contiene una di queste parole”.</span><span class="sxs-lookup"><span data-stu-id="50abe-119">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="50abe-120">Se il testo specificato nel criterio è una parola, è possibile individuarla, ma se si trova in mezzo a una frase, non verrà rilevata.</span><span class="sxs-lookup"><span data-stu-id="50abe-120">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="50abe-121">I criteri di conformità delle comunicazioni che descrivono i dizionari come informazioni tipo non rilevano le chat private e le chat di canale di Teams.</span><span class="sxs-lookup"><span data-stu-id="50abe-121">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="50abe-122">Le condizioni seguenti non sono supportate dalla conformità delle comunicazioni in questa fase (prevediamo di risolvere questi problemi in futuro):</span><span class="sxs-lookup"><span data-stu-id="50abe-122">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="50abe-123">“Il messaggio contiene alcune di queste parole”</span><span class="sxs-lookup"><span data-stu-id="50abe-123">“Message contains any of these words”</span></span>
  - <span data-ttu-id="50abe-124">“Il messaggio non contiene alcuna di queste parole”</span><span class="sxs-lookup"><span data-stu-id="50abe-124">“Message contains none of these words”</span></span>
  - <span data-ttu-id="50abe-125">“L'allegato contiene alcune di queste parole”</span><span class="sxs-lookup"><span data-stu-id="50abe-125">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="50abe-126">“L'allegato contiene alcune di queste parole”</span><span class="sxs-lookup"><span data-stu-id="50abe-126">“Attachment contains any of these words”</span></span>

<span data-ttu-id="50abe-127">In alternativa, è consigliabile creare un SIT (Sensitive Information Type) personalizzato con un dizionario di parole chiave che rileva i criteri nei messaggi e gli allegati e l’uso di tale tipo di contenuto personalizzato come condizione per la conformità alle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="50abe-127">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
