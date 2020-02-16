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
description: ''
ms.openlocfilehash: 2f445e4449fb20f0d13d857bb83d3dc85d7b7387
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069203"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="6ee97-102">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="6ee97-102">Use the communications editor</span></span>

<span data-ttu-id="6ee97-103">Quando si definisce il contenuto del contenuto del portale, le notifiche di blocco legale e i promemoria e le escalation correlati, è possibile utilizzare l'editor comunicazioni per formattare e personalizzare dinamicamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="6ee97-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="6ee97-104">Editor di testo RTF</span><span class="sxs-lookup"><span data-stu-id="6ee97-104">Rich text editor</span></span> 

<span data-ttu-id="6ee97-105">L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor.</span><span class="sxs-lookup"><span data-stu-id="6ee97-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="6ee97-106">Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare il contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="6ee97-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="6ee97-107">Unire le variabili di campo</span><span class="sxs-lookup"><span data-stu-id="6ee97-107">Merge field variables</span></span>

<span data-ttu-id="6ee97-108">È possibile sfruttare le variabili di stampa unione dall'editor comunicazioni per incorporare gli attributi di un custode personalizzato nel testo del corpo di una comunicazione.</span><span class="sxs-lookup"><span data-stu-id="6ee97-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="6ee97-109">Quando viene inviato al custode, il campo unione verrà popolato con il campo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6ee97-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="6ee97-110">Quando, ad esempio, viene inviato al custode John Smith, il campo merge [nome custode] verrebbe convertito con il nome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6ee97-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="6ee97-111">È possibile utilizzare i campi unione di posta elettronica selezionando le icone del **campo unione** nella parte superiore del controllo editor RTF.</span><span class="sxs-lookup"><span data-stu-id="6ee97-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="6ee97-112">Il segnaposto verrà aggiunto in base alla posizione del cursore degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6ee97-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="6ee97-113">Elenco delle variabili di campo unione</span><span class="sxs-lookup"><span data-stu-id="6ee97-113">List of merge field variables</span></span>

| <span data-ttu-id="6ee97-114">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="6ee97-114">Field name</span></span>                  | <span data-ttu-id="6ee97-115">Dettagli sul campo</span><span class="sxs-lookup"><span data-stu-id="6ee97-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="6ee97-116">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="6ee97-116">Display Name</span></span>  | <span data-ttu-id="6ee97-117">Nome e cognome del custode.</span><span class="sxs-lookup"><span data-stu-id="6ee97-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="6ee97-118">Collegamento di conferma</span><span class="sxs-lookup"><span data-stu-id="6ee97-118">Acknowledgement Link</span></span> | <span data-ttu-id="6ee97-119">Un collegamento personalizzato per registrare il riconoscimento di ogni custode.</span><span class="sxs-lookup"><span data-stu-id="6ee97-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="6ee97-120">Collegamento portale</span><span class="sxs-lookup"><span data-stu-id="6ee97-120">Portal Link</span></span>     | <span data-ttu-id="6ee97-121">Un collegamento personalizzato per il portale di conformità del custode.</span><span class="sxs-lookup"><span data-stu-id="6ee97-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="6ee97-122">Responsabile del rilascio</span><span class="sxs-lookup"><span data-stu-id="6ee97-122">Issuing Officer</span></span>                   | <span data-ttu-id="6ee97-123">L'indirizzo di posta elettronica del responsabile del rilascio specificato.</span><span class="sxs-lookup"><span data-stu-id="6ee97-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="6ee97-124">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="6ee97-124">Issuing Date</span></span>                   | <span data-ttu-id="6ee97-125">La data in cui è stato emesso l'avviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="6ee97-125">The date that the notice was issued (UTC).</span></span>              |
