---
title: Azioni di correzione nell'analisi e nella risposta automatizzate di Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Informazioni sulle azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955534"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="462a5-104">Azioni di correzione dopo un'analisi automatizzata in Office 365</span><span class="sxs-lookup"><span data-stu-id="462a5-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="462a5-105">Azioni correttive</span><span class="sxs-lookup"><span data-stu-id="462a5-105">Remediation actions</span></span>

<span data-ttu-id="462a5-106">[Le funzionalità di ricerca e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) piano 2 includono determinate azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="462a5-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="462a5-107">Ogni volta che un'indagine automatizzata è in esecuzione o è stata completata, in genere vengono visualizzate una o più operazioni di correzione che richiedono l'approvazione da parte del team di operazioni di sicurezza per procedere.</span><span class="sxs-lookup"><span data-stu-id="462a5-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="462a5-108">Nella tabella seguente sono riepilogate le azioni di correzione attualmente disponibili in Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="462a5-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="462a5-109">Azione</span><span class="sxs-lookup"><span data-stu-id="462a5-109">Action</span></span> | <span data-ttu-id="462a5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="462a5-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="462a5-111">Blocco di URL (al momento del clic)</span><span class="sxs-lookup"><span data-stu-id="462a5-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="462a5-112">Protegge da messaggi di posta elettronica e documenti che contengono URL dannosi.</span><span class="sxs-lookup"><span data-stu-id="462a5-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="462a5-113">In questo modo è possibile bloccare i collegamenti dannosi e tutte le pagine Web correlate tramite [collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando l'utente fa clic su un collegamento in un file di Office esistente o in un messaggio di posta elettronica precedente.</span><span class="sxs-lookup"><span data-stu-id="462a5-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="462a5-114">Elimina messaggio di posta elettronica soft</span><span class="sxs-lookup"><span data-stu-id="462a5-114">Soft delete email</span></span>  |<span data-ttu-id="462a5-115">Elimina temporaneamente i messaggi di posta elettronica specifici dalla cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="462a5-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="462a5-116">Un messaggio eliminato temporaneamente viene spostato nella cartella elementi ripristinabili di un utente e viene mantenuto fino alla scadenza del periodo di conservazione dell'elemento eliminato.</span><span class="sxs-lookup"><span data-stu-id="462a5-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="462a5-117">Cluster di posta elettronica con eliminazione morbida</span><span class="sxs-lookup"><span data-stu-id="462a5-117">Soft delete email clusters</span></span>  |<span data-ttu-id="462a5-118">Eliminare i messaggi di posta elettronica dannosi che corrispondono a una query da tutte le cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="462a5-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="462a5-119">I messaggi eliminati temporaneamente vengono spostati nella cartella elementi ripristinabili degli utenti e vengono mantenuti fino alla scadenza del periodo di conservazione dell'elemento eliminato.</span><span class="sxs-lookup"><span data-stu-id="462a5-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="462a5-120">Disattivazione dell'inoltro della posta elettronica esterna</span><span class="sxs-lookup"><span data-stu-id="462a5-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="462a5-121">Rimuove una regola di inoltro dalla cassetta postale di un utente finale specifico.</span><span class="sxs-lookup"><span data-stu-id="462a5-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="462a5-122">In Office 365 ATP, non viene eseguita automaticamente alcuna azione di correzione.</span><span class="sxs-lookup"><span data-stu-id="462a5-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="462a5-123">Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="462a5-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="462a5-124">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="462a5-124">Next steps</span></span>

- [<span data-ttu-id="462a5-125">Visualizzare le azioni di correzione in sospeso o completate dopo un'analisi automatizzata in Office 365</span><span class="sxs-lookup"><span data-stu-id="462a5-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="462a5-126">Informazioni dettagliate e risultati di un'indagine automatizzata in Office 365</span><span class="sxs-lookup"><span data-stu-id="462a5-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="462a5-127">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="462a5-127">Related articles</span></span>

- [<span data-ttu-id="462a5-128">Analisi automatizzata in Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="462a5-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="462a5-129">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="462a5-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)