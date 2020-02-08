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
ms.openlocfilehash: dcc3e5666bcd438a046d535cf9fce88910b85ad7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597653"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="36995-103">Gestione dei record in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36995-103">Records management in Microsoft 365</span></span>

<span data-ttu-id="36995-104">Le organizzazioni di tutti i tipi richiedono una soluzione di gestione dei record per gestire i record normativi, legali e di rilevanza per l'azienda tra i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="36995-104">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="36995-105">La gestione dei record in Microsoft 365 consente alle organizzazioni di gestire gli obblighi legali, offre la possibilità di dimostrare la conformità alle normative e aumenta l'efficienza con una disponibilità regolare di elementi che non devono essere più conservati, non sono più di valore o non più obbligatori ai fini aziendali.</span><span class="sxs-lookup"><span data-stu-id="36995-105">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="36995-106">La soluzione di gestione dei record supporta i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="36995-106">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="36995-107">**Etichettare il contenuto come record**.</span><span class="sxs-lookup"><span data-stu-id="36995-107">**Label content as a record**.</span></span> <span data-ttu-id="36995-108">Pubblicare le [etichette di record](records.md) applicabili dagli utenti finali o le [etichette di record applicabili automaticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) agli elementi che contengono informazioni sensibili, parole chiave o tipi di contenuto specifici.</span><span class="sxs-lookup"><span data-stu-id="36995-108">Publish [record labels](records.md) to be applied by end users or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) record labels to items containing specific sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="36995-109">**Eseguire la migrazione e gestire il piano di conservazione con il piano file** e usare [gestione del piano di archiviazione](file-plan-manager.md) da inserire nel piano di conservazione esistente oppure crearne di nuovi con descrittori di file e gerarchie in espansione.</span><span class="sxs-lookup"><span data-stu-id="36995-109">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="36995-110">**Stabilire criteri di conservazione e di eliminazione nell'etichetta di record**.</span><span class="sxs-lookup"><span data-stu-id="36995-110">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="36995-111">Definire i periodi di [conservazione](retention-policies.md#retaining-content-for-a-specific-period-of-time) ed [eliminazione](retention-policies.md#deleting-content-thats-older-than-a-specific-age) in base a vari fattori, tra cui la data dell'ultima modifica o di creazione.</span><span class="sxs-lookup"><span data-stu-id="36995-111">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors including the date last modified or created.</span></span>

- <span data-ttu-id="36995-112">**Attivare la conservazione basata su eventi** con la [conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="36995-112">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="36995-113">\*\*Rivedere e convalidare l'eliminazione \*\* con la [revisione per l'eliminazione](disposition-reviews.md).</span><span class="sxs-lookup"><span data-stu-id="36995-113">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

- <span data-ttu-id="36995-114">**Esaminare gli elementi eliminati con la revisione per l'eliminazione** ed [esportare un report di eliminazione](disposition-reviews.md#export-the-disposition-items) per ulteriori convalide e report.</span><span class="sxs-lookup"><span data-stu-id="36995-114">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

- <span data-ttu-id="36995-115">**Impostare autorizzazioni specifiche** per le funzioni di gestione dei record nell'organizzazione per [avere l’accesso corretto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="36995-115">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="36995-116">Con la soluzione di gestione dei record in Microsoft 365, è possibile incorporare le pianificazioni di conservazione dell'organizzazione nel piano di archiviazione per gestire la conservazione, la dichiarazione dei record e l'eliminazione a supporto dell'intero ciclo di vita del contenuto.</span><span class="sxs-lookup"><span data-stu-id="36995-116">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span>
