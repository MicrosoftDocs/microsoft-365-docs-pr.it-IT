---
title: Usare le etichette di conservazione per dichiarare i record
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Usare le etichette di conservazione per dichiarare i record.
ms.openlocfilehash: d637817e8d1bcc8c72bfe011dfd288ac4e2d0298
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778516"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="76e5b-103">Usare le etichette di conservazione per dichiarare i record</span><span class="sxs-lookup"><span data-stu-id="76e5b-103">Declare records by using retention labels</span></span>

><span data-ttu-id="76e5b-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="76e5b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="76e5b-105">Per dichiarare gli elementi come record, usare [etichette di conservazione](retention.md#retention-labels) per contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="76e5b-105">To declare items as a record, you use [retention labels](retention.md#retention-labels) that mark the content as a record.</span></span> <span data-ttu-id="76e5b-106">È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.</span><span class="sxs-lookup"><span data-stu-id="76e5b-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="76e5b-107">Configurare le etichette di conservazione per dichiarare i record</span><span class="sxs-lookup"><span data-stu-id="76e5b-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="76e5b-108">Quando si crea un'etichetta di conservazione, si può scegliere di usarla per contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="76e5b-108">When you create or configure a retention label, select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="76e5b-109">L'opzione per contrassegnare il contenuto come record non è disponibile quando si creano o si configurano le etichette dalla **Governance delle informazioni** nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76e5b-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="76e5b-110">È invece necessario usare **Gestione record**.</span><span class="sxs-lookup"><span data-stu-id="76e5b-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="76e5b-111">Per creare una nuova etichetta di conservazione che contrassegni il contenuto come record:</span><span class="sxs-lookup"><span data-stu-id="76e5b-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="76e5b-112">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com) passare a **Gestione record** \> **Piano di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="76e5b-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="76e5b-113">Nella pagina **Piano di archiviazione**, selezionare **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="76e5b-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="76e5b-114">Nella pagina **Impostazioni etichetta** della procedura guidata scegliere l'opzione di impostazione dell'etichetta di conservazione per contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="76e5b-114">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Fare clic sulla casella di controllo Utilizza l'etichetta per contrassegnare il contenuto come Record](../media/recordversioning6.png)

3. <span data-ttu-id="76e5b-116">Applicare l'etichetta di conservazione ai documenti di SharePoint o OneDrive e ai messaggi di posta elettronica di Exchange, se necessario.</span><span class="sxs-lookup"><span data-stu-id="76e5b-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="76e5b-117">Per istruzioni:</span><span class="sxs-lookup"><span data-stu-id="76e5b-117">For instructions:</span></span>
    
    - [<span data-ttu-id="76e5b-118">Creare etichette di conservazione e applicarle nelle app</span><span class="sxs-lookup"><span data-stu-id="76e5b-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="76e5b-119">Applicare automaticamente un'etichetta di conservazione al contenuto</span><span class="sxs-lookup"><span data-stu-id="76e5b-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="76e5b-120">Applicare l'etichetta di conservazione configurata al contenuto</span><span class="sxs-lookup"><span data-stu-id="76e5b-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="76e5b-121">Quando le etichette di conservazione che classificano il contenuto come record vengono rese disponibili agli utenti per applicarle nelle app:</span><span class="sxs-lookup"><span data-stu-id="76e5b-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="76e5b-122">Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="76e5b-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="76e5b-123">Per SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="76e5b-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="76e5b-124">Esempio di documento contrassegnato come record da un'etichetta di conservazione:</span><span class="sxs-lookup"><span data-stu-id="76e5b-124">Example of a document marked as record by using a retention label:</span></span>

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="76e5b-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="76e5b-126">Next steps</span></span>

<span data-ttu-id="76e5b-127">Per la lista degli scenari supportati dalla gestione dei record, vedere [Scenari comuni per la gestione dei record](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="76e5b-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
