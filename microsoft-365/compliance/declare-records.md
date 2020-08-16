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
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695258"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="96432-103">Usare le etichette di conservazione per dichiarare i record</span><span class="sxs-lookup"><span data-stu-id="96432-103">Declare records by using retention labels</span></span>

><span data-ttu-id="96432-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="96432-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="96432-105">Usare [etichette di conservazione ](retention.md#retention-labels) per contrassegnare un contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="96432-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="96432-106">È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.</span><span class="sxs-lookup"><span data-stu-id="96432-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="96432-107">Configurare le etichette di conservazione per dichiarare i record</span><span class="sxs-lookup"><span data-stu-id="96432-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="96432-108">Quando si crea un'[etichetta di conservazione](retention.md#retention-labels), si può scegliere di usarla per contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="96432-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="96432-109">L'opzione per contrassegnare il contenuto come record non è disponibile quando si creano o si configurano le etichette dalla **Governance delle informazioni** nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96432-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="96432-110">È invece necessario usare **Gestione record**.</span><span class="sxs-lookup"><span data-stu-id="96432-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="96432-111">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com) passare a **Gestione record** \> **Piano di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="96432-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="96432-112">Nella pagina **Piano di archiviazione**, selezionare **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="96432-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="96432-113">Nella pagina **Impostazioni etichetta** della procedura guidata scegliere l'opzione di impostazione dell'etichetta di conservazione per contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="96432-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Fare clic sulla casella di controllo Utilizza l'etichetta per contrassegnare il contenuto come Record](../media/recordversioning6.png)

3. <span data-ttu-id="96432-115">Applicare l'etichetta di conservazione ai documenti di SharePoint o OneDrive e ai messaggi di posta elettronica di Exchange, se necessario.</span><span class="sxs-lookup"><span data-stu-id="96432-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="96432-116">Per istruzioni:</span><span class="sxs-lookup"><span data-stu-id="96432-116">For instructions:</span></span>
    
    - [<span data-ttu-id="96432-117">Creare etichette di conservazione e applicarle nelle app</span><span class="sxs-lookup"><span data-stu-id="96432-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="96432-118">Applicare automaticamente un'etichetta di conservazione al contenuto</span><span class="sxs-lookup"><span data-stu-id="96432-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="96432-119">Applicare l'etichetta di conservazione configurata al contenuto</span><span class="sxs-lookup"><span data-stu-id="96432-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="96432-120">Quando le etichette di conservazione che classificano il contenuto come record vengono rese disponibili agli utenti per applicarle nelle app:</span><span class="sxs-lookup"><span data-stu-id="96432-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="96432-121">Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="96432-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="96432-122">Per SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="96432-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="96432-123">Esempio di documento contrassegnato come record da un'etichetta di conservazione:</span><span class="sxs-lookup"><span data-stu-id="96432-123">Example of a document marked as record by using a retention label:</span></span>

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="96432-125">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="96432-125">Next steps</span></span>

<span data-ttu-id="96432-126">Se è necessario aggiornare i record, vedere [Usare il controllo delle versioni dei record per aggiornare i record archiviati in SharePoint o OneDrive](record-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="96432-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="96432-127">Per ulteriori informazioni sull'eliminazione dei record, vedere [Eliminazione dei record](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="96432-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
