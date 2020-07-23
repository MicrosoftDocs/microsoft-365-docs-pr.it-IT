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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Con la gestione dei record di Microsoft 365, è possibile applicare le pianificazioni di conservazione in un piano di archiviazione che gestisce la conservazione, la dichiarazione dei record e l’eliminazione.
ms.openlocfilehash: 08b028bbd28c06684245321e09f8ef3252098956
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372489"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="3a47c-103">Gestione dei record in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3a47c-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="3a47c-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="3a47c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3a47c-105">Le organizzazioni di tutti i tipi richiedono una soluzione di gestione dei record per gestire i record normativi, legali e di rilevanza per l'azienda tra i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="3a47c-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="3a47c-106">La gestione dei record in Microsoft 365 consente alle organizzazioni di gestire gli obblighi legali, offre la possibilità di dimostrare la conformità alle normative e aumenta l'efficienza con una disponibilità regolare di elementi che non devono essere più conservati, non sono più di valore o non più obbligatori ai fini aziendali.</span><span class="sxs-lookup"><span data-stu-id="3a47c-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="3a47c-107">La gestione dei record in Microsoft 365 include le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a47c-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="3a47c-108">**Etichettare il contenuto come record**.</span><span class="sxs-lookup"><span data-stu-id="3a47c-108">**Label content as a record**.</span></span> <span data-ttu-id="3a47c-109">Creare e configurare etichette di conservazione per contrassegnare il contenuto come [record](records.md), che possono essere applicate dagli utenti o [applicate automaticamente](apply-retention-labels-automatically.md) identificando informazioni, parole chiave o tipi di contenuto sensibili.</span><span class="sxs-lookup"><span data-stu-id="3a47c-109">Create and configure retention labels to mark content as a [record](records.md) that can then be applied by users or [auto-applied](apply-retention-labels-automatically.md) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="3a47c-110">**Eseguire la migrazione e gestire i requisiti di conservazione con il piano di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="3a47c-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="3a47c-111">Con un [piano di archiviazione](file-plan-manager.md) è possibile inserire un piano di conservazione esistente in Microsoft 365 oppure crearne uno nuovo per funzionalità di gestione avanzate.</span><span class="sxs-lookup"><span data-stu-id="3a47c-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="3a47c-112">**Configurare le impostazioni di conservazione ed eliminazione con le etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="3a47c-112">**Configure retention and deletion settings with the retention label**.</span></span> <span data-ttu-id="3a47c-113">Definire i periodi e le azioni di conservazione in base a vari fattori, tra cui la data dell'ultima modifica o di creazione.</span><span class="sxs-lookup"><span data-stu-id="3a47c-113">Define retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="3a47c-114">**Avviare periodi di conservazione diversi quando si verifica un evento** con la[conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="3a47c-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="3a47c-115">\*\*Rivedere e convalidare l'eliminazione \*\* con la [revisione per l'eliminazione](disposition.md#disposition-reviews) e la prova dell'[eliminazione dei record](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="3a47c-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="3a47c-116">**Esportare le informazioni riguardanti tutti gli elementi eliminati** con l'[opzione di esportazione](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="3a47c-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="3a47c-117">**Impostare autorizzazioni specifiche** per le funzioni di gestione dei record nell'organizzazione per [avere l’accesso corretto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3a47c-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="3a47c-118">Con la soluzione di gestione dei record in Microsoft 365, è possibile incorporare le pianificazioni e i requisiti di conservazione dell'organizzazione in un piano di archiviazione che gestisce la conservazione, la dichiarazione dei record e l'eliminazione a supporto dell'intero ciclo di vita del contenuto.</span><span class="sxs-lookup"><span data-stu-id="3a47c-118">With the records-management solution in Microsoft 365, you can incorporate your organization's retention schedules and requirements into a file plan that manages retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3a47c-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3a47c-119">Additional resources</span></span>

<span data-ttu-id="3a47c-120">Per la gestione dei record, vedere la [registrazione del webinar](https://aka.ms/MIPC/Video-RecordsManagementWebinar) e la [presentazione con le domande frequenti](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span><span class="sxs-lookup"><span data-stu-id="3a47c-120">See the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) and [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) for records management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a47c-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3a47c-121">Next steps</span></span>

<span data-ttu-id="3a47c-122">Se si è pronti per iniziare a usare la gestione dei record in Microsoft 365, vedere [Informazioni sui record](records.md).</span><span class="sxs-lookup"><span data-stu-id="3a47c-122">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
