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
description: Utilizzare l'Editor comunicazioni per modificare il testo e le variabili dei campi unione durante la formattazione del contenuto.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769161"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="ad517-103">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="ad517-103">Use the communications editor</span></span>

<span data-ttu-id="ad517-104">Quando si definiscono il contenuto del portale, le notifiche di blocco a livello legale e i promemoria/escalation correlati, è possibile utilizzare Communications Editor per formattare e personalizzare dinamicamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="ad517-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="ad517-105">Editor di testo RTF</span><span class="sxs-lookup"><span data-stu-id="ad517-105">Rich text editor</span></span>

<span data-ttu-id="ad517-106">L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor.</span><span class="sxs-lookup"><span data-stu-id="ad517-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="ad517-107">Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare il contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="ad517-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="ad517-108">Variabili di campo unione</span><span class="sxs-lookup"><span data-stu-id="ad517-108">Merge field variables</span></span>

<span data-ttu-id="ad517-109">È possibile utilizzare le variabili di stampa unione dall'editor di comunicazioni per incorporare attributi di responsabile personalizzati nel corpo del testo di una comunicazione.</span><span class="sxs-lookup"><span data-stu-id="ad517-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="ad517-110">Quando viene inviato al responsabile, il campo unione verrà popolato con il campo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ad517-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="ad517-111">Ad esempio, quando viene inviato al responsabile John Smith, il campo unione [Nome del responsabile] viene convertito con il nome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ad517-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="ad517-112">È possibile utilizzare i campi di stampa unione selezionando le icone **dei** campi unione nella parte superiore del controllo editor rtf.</span><span class="sxs-lookup"><span data-stu-id="ad517-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="ad517-113">Il segnaposto verrà aggiunto in base alla posizione del cursore dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ad517-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="ad517-114">Elenco di variabili di campo unione</span><span class="sxs-lookup"><span data-stu-id="ad517-114">List of merge field variables</span></span>

| <span data-ttu-id="ad517-115">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="ad517-115">Field name</span></span>                  | <span data-ttu-id="ad517-116">Dettagli campo</span><span class="sxs-lookup"><span data-stu-id="ad517-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="ad517-117">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="ad517-117">Display Name</span></span>  | <span data-ttu-id="ad517-118">Nome e cognome del responsabile.</span><span class="sxs-lookup"><span data-stu-id="ad517-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="ad517-119">Collegamento riconoscimento</span><span class="sxs-lookup"><span data-stu-id="ad517-119">Acknowledgment Link</span></span> | <span data-ttu-id="ad517-120">Un collegamento personalizzato per registrare il riconoscimento di ogni responsabile.</span><span class="sxs-lookup"><span data-stu-id="ad517-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="ad517-121">Collegamento al portale</span><span class="sxs-lookup"><span data-stu-id="ad517-121">Portal Link</span></span>     | <span data-ttu-id="ad517-122">Collegamento personalizzato per il portale di conformità del responsabile.</span><span class="sxs-lookup"><span data-stu-id="ad517-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="ad517-123">Responsabile del rilascio</span><span class="sxs-lookup"><span data-stu-id="ad517-123">Issuing Officer</span></span>                   | <span data-ttu-id="ad517-124">L'indirizzo di posta elettronica del responsabile emittente specificato.</span><span class="sxs-lookup"><span data-stu-id="ad517-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="ad517-125">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="ad517-125">Issuing Date</span></span>                   | <span data-ttu-id="ad517-126">Data di emissione dell'avviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="ad517-126">The date that the notice was issued (UTC).</span></span>              |
|||
