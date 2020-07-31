---
title: Configurare le impostazioni di ricerca e analisi-indagini sui dati
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
description: Informazioni su come configurare le impostazioni di ricerca e analisi, come quasi duplicati, Threading di posta elettronica e temi durante la gestione delle indagini sui dati.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3100c83fc027e793f7937a4d27e059ce7e3038a0
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527352"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="1a1a6-103">Configurare le impostazioni di ricerca e analisi</span><span class="sxs-lookup"><span data-stu-id="1a1a6-103">Configure search and analytics settings</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="1a1a6-104">Quasi duplicati e threading della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1a1a6-104">Near duplicates and email threading</span></span>

<span data-ttu-id="1a1a6-105">In questa sezione, è possibile impostare parametri per il rilevamento duplicati, vicino al rilevamento duplicati e al threading tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-105">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="1a1a6-106">Attiva/disattiva: Includi rilevamento duplicato, vicino al rilevamento duplicato e threading della posta elettronica come parte del flusso di analisi se abilitato.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-106">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="1a1a6-107">Poiché si basano sull'uno dall'altro, è necessario abilitarli o disabilitarli tutti.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-107">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="1a1a6-108">Soglia: se il livello di somiglianza di due documenti si trova al di sopra della soglia, verranno inseriti nello stesso set di duplicati vicino.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-108">Threshold: if the similarity level of two documents is above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="1a1a6-109">Nascondi i duplicati per impostazione predefinita: se questa impostazione è attivata, per impostazione predefinita verrà applicato un filtro per nascondere i documenti duplicati nel working set.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-109">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="1a1a6-110">Il filtro può essere rimosso manualmente nel working set, se necessario.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-110">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="1a1a6-111">Numero minimo/massimo di parole: quasi duplicati e il threading della posta elettronica verrà eseguito solo sui documenti che hanno almeno il numero minimo di parole e il numero massimo di parole.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-111">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>

<span data-ttu-id="1a1a6-112">Per ulteriori informazioni, vedere [near duplicate detection](near-duplicates.md) and [email Threading](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="1a1a6-112">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="1a1a6-113">Temi</span><span class="sxs-lookup"><span data-stu-id="1a1a6-113">Themes</span></span>

<span data-ttu-id="1a1a6-114">In questa sezione, è possibile impostare parametri per i temi.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-114">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="1a1a6-115">Abilita/Disabilita: Includi temi il clustering come parte del flusso di analisi se abilitato.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-115">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>

- <span data-ttu-id="1a1a6-116">Regola dinamicamente il numero massimo di temi: in alcuni casi, non sono disponibili documenti sufficienti per produrre il numero di temi desiderato.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-116">Adjust maximum number of themes dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="1a1a6-117">Se questa impostazione è attivata, anziché tentare di forzare il numero massimo di temi desiderato, il sistema regola in modo dinamico il numero massimo di temi.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-117">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>

- <span data-ttu-id="1a1a6-118">Numero massimo di temi: numero desiderato di temi.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-118">Maximum number of themes: desired number of themes.</span></span>

- <span data-ttu-id="1a1a6-119">Includere numeri nei temi: quando è abilitata, includerà i numeri durante la generazione di temi.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-119">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="1a1a6-120">Riconoscimento ottico caratteri (OCR)</span><span class="sxs-lookup"><span data-stu-id="1a1a6-120">Optical character recognition (OCR)</span></span>

<span data-ttu-id="1a1a6-121">Quando questa impostazione è attivata, l'OCR verrà eseguito su immagini che vengono ingerite in gruppi di lavoro in modo che possano essere ricercate.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-121">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="1a1a6-122">Ignora testo</span><span class="sxs-lookup"><span data-stu-id="1a1a6-122">Ignore text</span></span>

<span data-ttu-id="1a1a6-123">Esistono casi in cui alcuni testi diminuiscono la qualità dell'analisi, ad esempio le dichiarazioni di non responsabilità lunghe che vengono aggiunte a determinati messaggi di posta elettronica, indipendentemente dal contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-123">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="1a1a6-124">Se si è a conoscenza di tali casi, è possibile escludere questo testo da analisi specificando il testo (RegEx è supportato) e quali moduli devono essere esclusi per il testo.</span><span class="sxs-lookup"><span data-stu-id="1a1a6-124">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>
