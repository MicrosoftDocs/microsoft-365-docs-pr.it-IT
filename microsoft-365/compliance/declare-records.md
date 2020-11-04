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
ms.openlocfilehash: 34b5272a8bed9be01c3965dae258c88facec0145
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830605"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="152a1-103">Usare le etichette di conservazione per dichiarare i record</span><span class="sxs-lookup"><span data-stu-id="152a1-103">Declare records by using retention labels</span></span>

><span data-ttu-id="152a1-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="152a1-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="152a1-105">Per dichiarare documenti e messaggi di posta elettronica come [record](records-management.md#records), usare [etichette di conservazione](retention.md#retention-labels) che contrassegnano i contenuti come **record** o **record normativi**.</span><span class="sxs-lookup"><span data-stu-id="152a1-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

<span data-ttu-id="152a1-106">Se si hanno dubbi sull'uso di un record oppure di un record normativo, vedere [Confrontare le restrizioni relative alle azioni consentite o bloccate](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="152a1-106">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="152a1-107">Se bisogna usare i record regolatori, per prima cosa si deve eseguire un comando di PowerShell, come descritto nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="152a1-107">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="152a1-108">In seguito è possibile pubblicare tali etichetta in un criterio per le etichette di conservazione, in modo che utenti e amministratori possano applicarle ai contenuti, oppure, per le etichette che contrassegnano elementi come record (ma non record normativi), applicare automaticamente le etichette ai contenuti che si vuole classificare come record.</span><span class="sxs-lookup"><span data-stu-id="152a1-108">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="152a1-109">Come visualizzare l'opzione per contrassegnare i contenuti come record normativi</span><span class="sxs-lookup"><span data-stu-id="152a1-109">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="152a1-110">Questa procedura è un'azione controllabile, che registra l' **Opzione dei record normativi abilitata per le etichette di conservazione** nella sezione [Criteri di conservazione e attività delle etichette di conservazione](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) del log di controllo.</span><span class="sxs-lookup"><span data-stu-id="152a1-110">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="152a1-111">Per impostazione predefinita, l'opzione dell'etichetta di conservazione per contrassegnare i contenuti come record normativi non è mostrata nella procedura guidata dell'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="152a1-111">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="152a1-112">Per visualizzare questa opzione, è prima necessario eseguire un comando di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="152a1-112">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="152a1-113">[Connettersi a PowerShell nel Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="152a1-113">[Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="152a1-114">Eseguire il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="152a1-114">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="152a1-115">Non viene richiesta la conferma, e l'impostazione ha effetto immediato.</span><span class="sxs-lookup"><span data-stu-id="152a1-115">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="152a1-116">Se si cambia idea in merito alla configurazione di questa opzione nella procedura di creazione dell'etichetta di conservazione, la si può nascondere eseguendo lo stesso cmdlet con il valore **false** : `Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="152a1-116">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="152a1-117">Configurare le etichette di conservazione per dichiarare i record</span><span class="sxs-lookup"><span data-stu-id="152a1-117">Configuring retention labels to declare records</span></span>

<span data-ttu-id="152a1-118">Quando si crea o modifica un'etichetta di conservazione tramite la soluzione **Records Management** nel Centro conformità di Microsoft 365, è possibile contrassegnare gli elementi come record.</span><span class="sxs-lookup"><span data-stu-id="152a1-118">When you create or edit a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="152a1-119">Se il comando di PowerShell è stato eseguito nella sezione precedente, in alternativa si può contrassegnare gli elementi come record normativi.</span><span class="sxs-lookup"><span data-stu-id="152a1-119">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="152a1-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="152a1-120">For example:</span></span>

![Configurare una etichetta di conservazione per contrassegnare i contenuti come record o record normativi](../media/recordversioning6.png)

<span data-ttu-id="152a1-122">Ora è possibile applicare questa etichetta di conservazione ai documenti di SharePoint o OneDrive e ai messaggi di posta elettronica di Exchange, se necessario.</span><span class="sxs-lookup"><span data-stu-id="152a1-122">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="152a1-123">Istruzioni complete:</span><span class="sxs-lookup"><span data-stu-id="152a1-123">For full instructions:</span></span>

- [<span data-ttu-id="152a1-124">Creare etichette di conservazione e applicarle nelle app</span><span class="sxs-lookup"><span data-stu-id="152a1-124">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="152a1-125">[Applicare automaticamente le etichette di conservazione ai contenuti](apply-retention-labels-automatically.md) (non supportato per i record normativi)</span><span class="sxs-lookup"><span data-stu-id="152a1-125">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="152a1-126">Applicare l'etichetta di conservazione configurata al contenuto</span><span class="sxs-lookup"><span data-stu-id="152a1-126">Applying the configured retention label to content</span></span>

<span data-ttu-id="152a1-127">Quando le etichette di conservazione che classificano gli elementi come record o record normativi vengono rese disponibili agli utenti per applicarle nelle app:</span><span class="sxs-lookup"><span data-stu-id="152a1-127">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="152a1-128">Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="152a1-128">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="152a1-129">Per SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="152a1-129">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="152a1-130">Esempio di documento contrassegnato come record da un'etichetta di conservazione:</span><span class="sxs-lookup"><span data-stu-id="152a1-130">Example of a document marked as record by using a retention label:</span></span>

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="152a1-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="152a1-132">Next steps</span></span>

<span data-ttu-id="152a1-133">Per la lista degli scenari supportati dalla gestione dei record, vedere [Scenari comuni per la gestione dei record](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="152a1-133">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
