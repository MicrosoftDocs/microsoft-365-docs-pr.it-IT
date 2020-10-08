---
title: Introduzione a Esplora attività
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Esplora attività estende la funzionalità di classificazione dei dati consentendo di visualizzare e filtrare le azioni intraprese dagli utenti sul contenuto etichettato.
ms.openlocfilehash: 0175f41ca3fbcfc685acf933cc0cd97af6aa61ad
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379200"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="ed40e-103">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="ed40e-103">Get started with activity explorer</span></span>

<span data-ttu-id="ed40e-104">Le schede Panoramica ed Esplora contenuto della classificazione dei dati consentono di ottenere informazioni sul contenuto individuato ed etichettato nonché di sapere dove si trova tale contenuto.</span><span class="sxs-lookup"><span data-stu-id="ed40e-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="ed40e-105">Esplora attività estende questa famiglia di funzionalità, consentendo di monitorare le operazioni eseguite sul contenuto etichettato.</span><span class="sxs-lookup"><span data-stu-id="ed40e-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="ed40e-106">Le informazioni di Esplora attività sono visualizzate in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="ed40e-106">Activity explorer provides a historical view.</span></span>

![Segnaposto per screenshot della panoramica di Esplora attività](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="ed40e-108">Sono disponibili per l'uso oltre 30 filtri diversi, alcuni dei quali sono:</span><span class="sxs-lookup"><span data-stu-id="ed40e-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="ed40e-109">intervallo di date</span><span class="sxs-lookup"><span data-stu-id="ed40e-109">date range</span></span>
- <span data-ttu-id="ed40e-110">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="ed40e-110">activity type</span></span>
- <span data-ttu-id="ed40e-111">posizione</span><span class="sxs-lookup"><span data-stu-id="ed40e-111">location</span></span>
- <span data-ttu-id="ed40e-112">utente</span><span class="sxs-lookup"><span data-stu-id="ed40e-112">user</span></span>
- <span data-ttu-id="ed40e-113">etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="ed40e-113">sensitivity label</span></span>
- <span data-ttu-id="ed40e-114">etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="ed40e-114">retention label</span></span>
- <span data-ttu-id="ed40e-115">percorso file</span><span class="sxs-lookup"><span data-stu-id="ed40e-115">file path</span></span>
- <span data-ttu-id="ed40e-116">Criteri DLP</span><span class="sxs-lookup"><span data-stu-id="ed40e-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="ed40e-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ed40e-117">Prerequisites</span></span>

<span data-ttu-id="ed40e-118">A ogni account che accede e usa la classificazione dei dati deve essere assegnata una licenza da uno di questi abbonamenti:</span><span class="sxs-lookup"><span data-stu-id="ed40e-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="ed40e-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="ed40e-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="ed40e-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="ed40e-120">Office 365 (E5)</span></span>
- <span data-ttu-id="ed40e-121">Componente aggiuntivo Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="ed40e-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="ed40e-122">Componente aggiuntivo Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="ed40e-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="ed40e-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ed40e-123">Permissions</span></span>

 <span data-ttu-id="ed40e-124">Per accedere alla scheda Esplora attività, è necessario che a un account sia assegnata l'appartenenza a uno di questi ruoli o gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="ed40e-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="ed40e-125">**Gruppi di ruoli di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="ed40e-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="ed40e-126">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ed40e-126">Global administrator</span></span>
- <span data-ttu-id="ed40e-127">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="ed40e-127">Compliance administrator</span></span>
- <span data-ttu-id="ed40e-128">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ed40e-128">Security administrator</span></span>
- <span data-ttu-id="ed40e-129">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="ed40e-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="ed40e-130">Tipo di attività</span><span class="sxs-lookup"><span data-stu-id="ed40e-130">Activity type</span></span>

<span data-ttu-id="ed40e-131">Microsoft 365 monitora e crea report sui tipi di attività in SharePoint Online e OneDrive, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ed40e-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="ed40e-132">Etichetta applicata</span><span class="sxs-lookup"><span data-stu-id="ed40e-132">label applied</span></span>
- <span data-ttu-id="ed40e-133">Etichetta modificata (sottoposta a upgrade o downgrade oppure rimossa)</span><span class="sxs-lookup"><span data-stu-id="ed40e-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="ed40e-134">Simulazione di etichettatura automatica</span><span class="sxs-lookup"><span data-stu-id="ed40e-134">auto-labeling simulation</span></span>

<span data-ttu-id="ed40e-135">Conoscere le azioni intraprese sul contenuto etichettato sensibile consente di verificare l'efficacia dei controlli già implementati, ad esempio i [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ed40e-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="ed40e-136">Se non sono efficaci o se si individua un comportamento imprevisto, ad esempio un numero elevato di elementi etichettati come `highly confidential` declassato a `general`, è possibile gestire i vari criteri e intraprendere nuove azioni per limitare il comportamento indesiderato.</span><span class="sxs-lookup"><span data-stu-id="ed40e-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="ed40e-137">Esplora risorse non esegue il monitoraggio delle attività di conservazione per Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ed40e-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed40e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed40e-138">See also</span></span>
- [<span data-ttu-id="ed40e-139">Informazioni sulle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="ed40e-139">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="ed40e-140">Informazioni sui criteri e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="ed40e-140">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="ed40e-141">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="ed40e-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

