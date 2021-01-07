---
title: Usare l'editor delle comunicazioni
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
description: Utilizzare l'editor comunicazioni per modificare il testo e unire le variabili di campo durante la formattazione del contenuto.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769161"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="86370-103">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="86370-103">Use the communications editor</span></span>

<span data-ttu-id="86370-104">Quando si definisce il contenuto del contenuto del portale, le notifiche di blocco legale e i promemoria e le escalation correlati, è possibile utilizzare l'editor comunicazioni per formattare e personalizzare dinamicamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="86370-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="86370-105">Editor di testo RTF</span><span class="sxs-lookup"><span data-stu-id="86370-105">Rich text editor</span></span>

<span data-ttu-id="86370-106">L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor.</span><span class="sxs-lookup"><span data-stu-id="86370-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="86370-107">Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare il contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="86370-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="86370-108">Unire le variabili di campo</span><span class="sxs-lookup"><span data-stu-id="86370-108">Merge field variables</span></span>

<span data-ttu-id="86370-109">È possibile utilizzare le variabili di Unione dei messaggi di posta elettronica dall'editor comunicazioni per incorporare gli attributi di custode personalizzato nel testo del corpo di una comunicazione.</span><span class="sxs-lookup"><span data-stu-id="86370-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="86370-110">Quando viene inviato al custode, il campo unione verrà popolato con il campo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="86370-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="86370-111">Quando, ad esempio, viene inviato al custode John Smith, il campo merge [nome custode] verrebbe convertito con il nome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="86370-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="86370-112">È possibile utilizzare i campi unione di posta elettronica selezionando le icone del **campo unione** nella parte superiore del controllo editor RTF.</span><span class="sxs-lookup"><span data-stu-id="86370-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="86370-113">Il segnaposto verrà aggiunto in base alla posizione del cursore degli utenti.</span><span class="sxs-lookup"><span data-stu-id="86370-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="86370-114">Elenco delle variabili di campo unione</span><span class="sxs-lookup"><span data-stu-id="86370-114">List of merge field variables</span></span>

| <span data-ttu-id="86370-115">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="86370-115">Field name</span></span>                  | <span data-ttu-id="86370-116">Dettagli sul campo</span><span class="sxs-lookup"><span data-stu-id="86370-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="86370-117">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="86370-117">Display Name</span></span>  | <span data-ttu-id="86370-118">Nome e cognome del custode.</span><span class="sxs-lookup"><span data-stu-id="86370-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="86370-119">Collegamento di riconoscimento</span><span class="sxs-lookup"><span data-stu-id="86370-119">Acknowledgment Link</span></span> | <span data-ttu-id="86370-120">Un collegamento personalizzato per registrare il riconoscimento di ogni custode.</span><span class="sxs-lookup"><span data-stu-id="86370-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="86370-121">Collegamento portale</span><span class="sxs-lookup"><span data-stu-id="86370-121">Portal Link</span></span>     | <span data-ttu-id="86370-122">Un collegamento personalizzato per il portale di conformità del custode.</span><span class="sxs-lookup"><span data-stu-id="86370-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="86370-123">Responsabile del rilascio</span><span class="sxs-lookup"><span data-stu-id="86370-123">Issuing Officer</span></span>                   | <span data-ttu-id="86370-124">L'indirizzo di posta elettronica del responsabile del rilascio specificato.</span><span class="sxs-lookup"><span data-stu-id="86370-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="86370-125">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="86370-125">Issuing Date</span></span>                   | <span data-ttu-id="86370-126">La data in cui è stato emesso l'avviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="86370-126">The date that the notice was issued (UTC).</span></span>              |
|||
