---
title: Governance delle informazioni Microsoft in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: Implementare le funzionalità di Governance delle informazioni Microsoft per gestire i dati in base ai requisiti di conformità o normativi.
ms.openlocfilehash: 304b4e57702c55242e49fae7fdf4a36e9b2f7cdb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244565"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a><span data-ttu-id="b5781-103">Governance delle informazioni Microsoft in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5781-103">Microsoft Information Governance in Microsoft 365</span></span>

><span data-ttu-id="b5781-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="b5781-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="b5781-105">Usare le funzionalità di Governance delle informazioni Microsoft, a volte abbreviato in MIG, per gestire i dati in base ai requisiti di conformità o normativi.</span><span class="sxs-lookup"><span data-stu-id="b5781-105">Use Microsoft Information Governance (sometimes abbreviated to MIG) capabilities to govern your data for compliance or regulatory requirements.</span></span>

![Gestire i dati: governance delle informazioni e gestione dei record](../media/information-governance-records-management.png)

<span data-ttu-id="b5781-107">Si vuole proteggere i propri dati?</span><span class="sxs-lookup"><span data-stu-id="b5781-107">Looking to protect your data?</span></span> <span data-ttu-id="b5781-108">Vedere [Microsoft Information Protection in Microsoft 365](information-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b5781-108">See [Microsoft Information Protection in Microsoft 365](information-protection.md).</span></span>

<span data-ttu-id="b5781-109">Per consentire il rispetto delle normative sulla privacy dei dati, è stato progettato un flusso di lavoro che fornisce una guida attraverso il processo end-to end di pianificazione e implementazione delle funzionalità in Microsoft 365, tra cui accesso sicuro, protezione dalla minacce, protezione delle informazioni e governance dei dati.</span><span class="sxs-lookup"><span data-stu-id="b5781-109">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including secure access, threat protection, information protection, and data governance.</span></span> <span data-ttu-id="b5781-110">Per altre informazioni, vedere [Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="b5781-110">For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 

## <a name="information-governance"></a><span data-ttu-id="b5781-111">Governance delle informazioni</span><span class="sxs-lookup"><span data-stu-id="b5781-111">Information governance</span></span>

<span data-ttu-id="b5781-112">Per conservare ciò di cui si ha bisogno ed eliminare ciò che non serve:</span><span class="sxs-lookup"><span data-stu-id="b5781-112">To keep what you need and delete what you don't:</span></span>
 
|<span data-ttu-id="b5781-113">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="b5781-113">Capability</span></span>|<span data-ttu-id="b5781-114">Che problemi risolve?</span><span class="sxs-lookup"><span data-stu-id="b5781-114">What problems does it solve?</span></span>|<span data-ttu-id="b5781-115">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="b5781-115">Get started</span></span>|
|:------|:------------|:--------------------|:-----------------------------|
|[<span data-ttu-id="b5781-116">Criteri di conservazione ed etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b5781-116">Retention policies and retention labels</span></span>](retention.md)| <span data-ttu-id="b5781-117">Conservare o eliminare i contenuti con la gestione dei criteri e un flusso di lavoro di eliminazione per messaggi di posta elettronica, documenti, messaggi istantanei e altro ancora</span><span class="sxs-lookup"><span data-stu-id="b5781-117">Retain or delete content with policy management and a deletion workflow for email, documents, instant messages, and more</span></span> <br /><br /><span data-ttu-id="b5781-118">Scenario di esempio: [Applicare automaticamente un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="b5781-118">Example scenario: [Apply a retention label to content automatically](apply-retention-labels-automatically.md)</span></span> | [<span data-ttu-id="b5781-119">Informazioni sui criteri e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b5781-119">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)|
|[<span data-ttu-id="b5781-120">Servizio di importazione</span><span class="sxs-lookup"><span data-stu-id="b5781-120">Import service</span></span>](importing-pst-files-to-office-365.md)| <span data-ttu-id="b5781-121">Importare file PST in blocco nelle cassette postali di Exchange Online per conservare e cercare i messaggi di posta elettronica per i requisiti di conformità o normativi</span><span class="sxs-lookup"><span data-stu-id="b5781-121">Bulk-import PST files to Exchange Online mailboxes to retain and search email messages for compliance or regulatory requirements</span></span> | [<span data-ttu-id="b5781-122">Usare il caricamento in rete per importare file PST dell'organizzazione in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5781-122">Use network upload to import your organization's PST files to Microsoft 365</span></span>](use-network-upload-to-import-pst-files.md)|
|[<span data-ttu-id="b5781-123">Archiviare i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="b5781-123">Archive third-party data</span></span>](archiving-third-party-data.md)| <span data-ttu-id="b5781-124">Importare, archiviare e applicare soluzioni di conformità a dati di terze parti da piattaforme di social media, di messaggistica istantanea e di collaborazione per documenti</span><span class="sxs-lookup"><span data-stu-id="b5781-124">Import, archive, and apply compliance solutions to third-party data from social media platforms, instant messaging platforms, and document collaboration platforms</span></span>| [<span data-ttu-id="b5781-125">Connettori di terze parti</span><span class="sxs-lookup"><span data-stu-id="b5781-125">Third-party connectors</span></span>](archiving-third-party-data.md#third-party-data-connectors)|
|[<span data-ttu-id="b5781-126">Cassette postali inattive</span><span class="sxs-lookup"><span data-stu-id="b5781-126">Inactive mailboxes</span></span>](inactive-mailboxes-in-office-365.md)| <span data-ttu-id="b5781-127">Conservare il contenuto delle cassette postali dopo che i dipendenti lasciano l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b5781-127">Retain mailbox content after employees leave the organization</span></span> | [<span data-ttu-id="b5781-128">Creare e gestire le cassette postali inattive</span><span class="sxs-lookup"><span data-stu-id="b5781-128">Create and manage inactive mailboxes</span></span>](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a><span data-ttu-id="b5781-129">Gestione dei record</span><span class="sxs-lookup"><span data-stu-id="b5781-129">Records management</span></span>

<span data-ttu-id="b5781-130">Per gestire contenuti di valore elevato per obblighi legali, aziendali o normativi:</span><span class="sxs-lookup"><span data-stu-id="b5781-130">To manage high-value content for legal, business, or regulatory obligations:</span></span>

|<span data-ttu-id="b5781-131">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="b5781-131">Capability</span></span>|<span data-ttu-id="b5781-132">Che problemi risolve?</span><span class="sxs-lookup"><span data-stu-id="b5781-132">What problems does it solve?</span></span>|<span data-ttu-id="b5781-133">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="b5781-133">Get started</span></span>|
|:------|:------------|---------------------|:----------------------------|
|[<span data-ttu-id="b5781-134">Gestione record</span><span class="sxs-lookup"><span data-stu-id="b5781-134">Records management</span></span>](records-management.md)| <span data-ttu-id="b5781-135">Un'unica soluzione per la posta elettronica e i documenti che incorpora pianificazione e requisiti di conservazione in un piano di archiviazione che supporta l'intero ciclo di vita del contenuto con dichiarazioni, conservazione ed eliminazione dei record</span><span class="sxs-lookup"><span data-stu-id="b5781-135">A single solution for email and documents that incorporates retention schedules and requirements into a file plan that supports the full lifecycle of your content with records declaration, retention, and disposition</span></span> <br /><br /><span data-ttu-id="b5781-136">Scenario di esempio: [Eliminazione dei record](disposition.md#disposition-of-records)</span><span class="sxs-lookup"><span data-stu-id="b5781-136">Example scenario: [Disposition of records](disposition.md#disposition-of-records)</span></span>|[<span data-ttu-id="b5781-137">Introduzione alla gestione dei record</span><span class="sxs-lookup"><span data-stu-id="b5781-137">Get started with records management</span></span>](get-started-with-records-management.md) |