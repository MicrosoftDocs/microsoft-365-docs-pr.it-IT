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
description: Utilizzare l'Editor comunicazioni per modificare le variabili di campo di testo e unione durante la formattazione del contenuto.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 26076ff82ba226c2993c7c40e36bca2e08cbf683
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288120"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="23bdf-103">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="23bdf-103">Use the communications editor</span></span>

<span data-ttu-id="23bdf-104">Quando si definisce il contenuto del portale, le notifiche di blocco legale e i promemoria/escalation correlati, è possibile utilizzare l'Editor comunicazioni per formattare e personalizzare dinamicamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="23bdf-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="23bdf-105">Editor di testo RTF</span><span class="sxs-lookup"><span data-stu-id="23bdf-105">Rich text editor</span></span>

<span data-ttu-id="23bdf-106">L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor.</span><span class="sxs-lookup"><span data-stu-id="23bdf-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="23bdf-107">Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="23bdf-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="23bdf-108">Variabili di campo unione</span><span class="sxs-lookup"><span data-stu-id="23bdf-108">Merge field variables</span></span>

<span data-ttu-id="23bdf-109">È possibile utilizzare le variabili di stampa unione dall'Editor comunicazioni per incorporare attributi di custodia personalizzati nel corpo del testo di una comunicazione.</span><span class="sxs-lookup"><span data-stu-id="23bdf-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="23bdf-110">Quando viene inviato al responsabile, il campo unione verrà popolato con il campo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="23bdf-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="23bdf-111">Ad esempio, quando viene inviato al responsabile John Smith, il campo unione [Nome depositario] viene convertito con il nome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="23bdf-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="23bdf-112">È possibile utilizzare i campi di stampa unione selezionando le **icone dei** campi unione nella parte superiore del controllo editor di testo RTF.</span><span class="sxs-lookup"><span data-stu-id="23bdf-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="23bdf-113">Il segnaposto verrà aggiunto in base alla posizione del cursore degli utenti.</span><span class="sxs-lookup"><span data-stu-id="23bdf-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="23bdf-114">Elenco di variabili di campo unione</span><span class="sxs-lookup"><span data-stu-id="23bdf-114">List of merge field variables</span></span>

<br>

****

|<span data-ttu-id="23bdf-115">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="23bdf-115">Field name</span></span>|<span data-ttu-id="23bdf-116">Dettagli campo</span><span class="sxs-lookup"><span data-stu-id="23bdf-116">Field details</span></span>|
|---|---|
|<span data-ttu-id="23bdf-117">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="23bdf-117">Display Name</span></span>|<span data-ttu-id="23bdf-118">Nome e cognome del responsabile.</span><span class="sxs-lookup"><span data-stu-id="23bdf-118">The custodian's first and last name.</span></span>|
|<span data-ttu-id="23bdf-119">Collegamento di riconoscimento</span><span class="sxs-lookup"><span data-stu-id="23bdf-119">Acknowledgment Link</span></span>|<span data-ttu-id="23bdf-120">Un collegamento personalizzato per registrare il riconoscimento di ogni responsabile.</span><span class="sxs-lookup"><span data-stu-id="23bdf-120">A customized link to record each custodian's acknowledgment.</span></span>|
|<span data-ttu-id="23bdf-121">Collegamento portale</span><span class="sxs-lookup"><span data-stu-id="23bdf-121">Portal Link</span></span>|<span data-ttu-id="23bdf-122">Collegamento personalizzato per il portale di conformità del responsabile.</span><span class="sxs-lookup"><span data-stu-id="23bdf-122">A customized link for the custodian's Compliance Portal.</span></span>|
|<span data-ttu-id="23bdf-123">Responsabile dell'emissione</span><span class="sxs-lookup"><span data-stu-id="23bdf-123">Issuing Officer</span></span>|<span data-ttu-id="23bdf-124">L'indirizzo di posta elettronica del responsabile del rilascio specificato.</span><span class="sxs-lookup"><span data-stu-id="23bdf-124">The email address of the specified issuing officer.</span></span>|
|<span data-ttu-id="23bdf-125">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="23bdf-125">Issuing Date</span></span>|<span data-ttu-id="23bdf-126">Data di emissione dell'avviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="23bdf-126">The date that the notice was issued (UTC).</span></span>|
|
