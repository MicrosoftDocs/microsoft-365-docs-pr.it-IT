---
title: Gestione dei record
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Con la gestione dei record in Microsoft 365, è possibile applicare le pianificazioni di conservazione specifiche dell'organizzazione in un piano di archiviazione per gestire la conservazione, la dichiarazione dei record e l'eliminazione a supporto dell'intero ciclo di vita del contenuto.
ms.openlocfilehash: 261ae3286792dde540d9bf648c15e529863091ed
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44231869"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="0b442-103">Gestione dei record in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b442-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="0b442-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="0b442-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0b442-105">Le organizzazioni di tutti i tipi richiedono una soluzione di gestione dei record per gestire i record normativi, legali e di rilevanza per l'azienda tra i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="0b442-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="0b442-106">La gestione dei record in Microsoft 365 consente alle organizzazioni di gestire gli obblighi legali, offre la possibilità di dimostrare la conformità alle normative e aumenta l'efficienza con una disponibilità regolare di elementi che non devono essere più conservati, non sono più di valore o non più obbligatori ai fini aziendali.</span><span class="sxs-lookup"><span data-stu-id="0b442-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="0b442-107">La soluzione di gestione dei record supporta i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="0b442-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="0b442-108">**Etichettare il contenuto come record**.</span><span class="sxs-lookup"><span data-stu-id="0b442-108">**Label content as a record**.</span></span> <span data-ttu-id="0b442-109">Creare e pubblicare etichette di conservazione che dichiarano il contenuto come [record](records.md) che può essere applicato dagli utent finali o [applicato automaticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) identificando informazioni sensibili, parole chiave o tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="0b442-109">Create and publish retention labels that declare content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="0b442-110">**Eseguire la migrazione e gestire il piano di conservazione con il piano file** e usare [gestione del piano di archiviazione](file-plan-manager.md) da inserire nel piano di conservazione esistente oppure crearne di nuovi con descrittori di file e gerarchie in espansione.</span><span class="sxs-lookup"><span data-stu-id="0b442-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="0b442-111">**Stabilire criteri di conservazione e di eliminazione nell'etichetta di record**.</span><span class="sxs-lookup"><span data-stu-id="0b442-111">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="0b442-112">Definire i periodi di [conservazione](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) ed [eliminazione](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) in base a vari fattori, tra cui la data dell'ultima modifica o di creazione.</span><span class="sxs-lookup"><span data-stu-id="0b442-112">Define [retention](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors including the date last modified or created.</span></span>

- <span data-ttu-id="0b442-113">**Attivare la conservazione basata su eventi** con la [conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="0b442-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="0b442-114">\*\*Rivedere e convalidare l'eliminazione \*\* con la [revisione per l'eliminazione](disposition.md#disposition-reviews) e la prova dell'[eliminazione dei record](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="0b442-114">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="0b442-115">**Esportare le informazioni riguardanti tutti gli elementi eliminati** con l'[opzione di esportazione](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="0b442-115">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="0b442-116">**Impostare autorizzazioni specifiche** per le funzioni di gestione dei record nell'organizzazione per [avere l’accesso corretto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0b442-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="0b442-117">Con la soluzione di gestione dei record in Microsoft 365, è possibile incorporare le pianificazioni di conservazione dell'organizzazione nel piano di archiviazione per gestire la conservazione, la dichiarazione dei record e l'eliminazione a supporto dell'intero ciclo di vita del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0b442-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>
