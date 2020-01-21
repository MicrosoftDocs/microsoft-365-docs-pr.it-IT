---
title: Utilizzo di Esplora attività di classificazione dei dati
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
search.appverid:
- MOE150
- MET150
description: Esplora attività estende la funzionalità di classificazione dei dati consentendo di visualizzare e filtrare le azioni intraprese dagli utenti sul contenuto etichettato.
ms.openlocfilehash: ab80de0e1be3a164da8414ef3791fb9717bcc190
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233697"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="dd424-103">Visualizzare le attività sul contenuto etichettato (anteprima)</span><span class="sxs-lookup"><span data-stu-id="dd424-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="dd424-104">Le schede Panoramica ed Esplora contenuto della classificazione dei dati consentono di ottenere informazioni sul contenuto individuato ed etichettato nonché di sapere dove si trova tale contenuto.</span><span class="sxs-lookup"><span data-stu-id="dd424-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="dd424-105">Esplora attività estende questa famiglia di funzionalità, consentendo di monitorare le operazioni eseguite sul contenuto etichettato.</span><span class="sxs-lookup"><span data-stu-id="dd424-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="dd424-106">Le informazioni di Esplora attività sono visualizzate in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="dd424-106">Activity explorer provides a historical view.</span></span>

![Segnaposto per screenshot della panoramica di Esplora attività](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="dd424-108">È possibile filtrare i dati in base a:</span><span class="sxs-lookup"><span data-stu-id="dd424-108">You can filter the data by:</span></span>

- <span data-ttu-id="dd424-109">intervallo di date</span><span class="sxs-lookup"><span data-stu-id="dd424-109">date range</span></span>
- <span data-ttu-id="dd424-110">tipo di attività</span><span class="sxs-lookup"><span data-stu-id="dd424-110">activity type</span></span>
- <span data-ttu-id="dd424-111">posizione</span><span class="sxs-lookup"><span data-stu-id="dd424-111">location</span></span>
- <span data-ttu-id="dd424-112">utente</span><span class="sxs-lookup"><span data-stu-id="dd424-112">user</span></span>
- <span data-ttu-id="dd424-113">etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="dd424-113">sensitivity label</span></span>
- <span data-ttu-id="dd424-114">etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="dd424-114">retention label</span></span>


<span data-ttu-id="dd424-115">È possibile visualizzare i dati sotto forma di elenco o grafico a barre.</span><span class="sxs-lookup"><span data-stu-id="dd424-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dd424-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dd424-116">Prerequisites</span></span>

<span data-ttu-id="dd424-117">A ogni account che accede e usa Esplora attività deve essere assegnata una licenza da uno di questi abbonamenti:</span><span class="sxs-lookup"><span data-stu-id="dd424-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="dd424-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="dd424-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="dd424-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="dd424-119">Office 365 E5</span></span>
- <span data-ttu-id="dd424-120">Componente aggiuntivo Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="dd424-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="dd424-121">Componente aggiuntivo Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="dd424-121">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="dd424-122">Componente aggiuntivo Advanced Threat Protection (E5)</span><span class="sxs-lookup"><span data-stu-id="dd424-122">Advanced Threat Protection (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="dd424-123">Tipo di attività</span><span class="sxs-lookup"><span data-stu-id="dd424-123">Activity type</span></span>

<span data-ttu-id="dd424-124">Microsoft 365 monitora e crea report relativi a 12 tipi di attività in SharePoint Online, OneDrive ed endpoint.</span><span class="sxs-lookup"><span data-stu-id="dd424-124">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="dd424-125">Gli endpoint sono dispositivi utente che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dd424-125">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="dd424-126">File creato</span><span class="sxs-lookup"><span data-stu-id="dd424-126">File created</span></span>
- <span data-ttu-id="dd424-127">File modificato</span><span class="sxs-lookup"><span data-stu-id="dd424-127">File modified</span></span>
- <span data-ttu-id="dd424-128">File rinominato</span><span class="sxs-lookup"><span data-stu-id="dd424-128">File renamed</span></span>
- <span data-ttu-id="dd424-129">File copiato nel cloud</span><span class="sxs-lookup"><span data-stu-id="dd424-129">File copied to cloud</span></span>
- <span data-ttu-id="dd424-130">File utilizzato da un'app non consentita</span><span class="sxs-lookup"><span data-stu-id="dd424-130">File accessed by unallowed app</span></span>
- <span data-ttu-id="dd424-131">File stampato</span><span class="sxs-lookup"><span data-stu-id="dd424-131">File printed</span></span>
- <span data-ttu-id="dd424-132">File copiato su supporto rimovibile</span><span class="sxs-lookup"><span data-stu-id="dd424-132">File copied to removable media</span></span>
- <span data-ttu-id="dd424-133">File copiato in una condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="dd424-133">File copied to network share</span></span>
- <span data-ttu-id="dd424-134">File letto</span><span class="sxs-lookup"><span data-stu-id="dd424-134">File read</span></span>
- <span data-ttu-id="dd424-135">File copiato negli Appunti</span><span class="sxs-lookup"><span data-stu-id="dd424-135">file copied to clipboard</span></span>
- <span data-ttu-id="dd424-136">Etichetta applicata</span><span class="sxs-lookup"><span data-stu-id="dd424-136">Label applied</span></span>
- <span data-ttu-id="dd424-137">Etichetta modificata (sottoposta a upgrade o downgrade oppure rimossa)</span><span class="sxs-lookup"><span data-stu-id="dd424-137">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="dd424-138">Conoscere le azioni intraprese sul contenuto etichettato sensibile consente di verificare l'efficacia dei controlli già implementati, ad esempio i [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dd424-138">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="dd424-139">Se non sono efficaci o se si individua un comportamento imprevisto, ad esempio un numero elevato di elementi etichettati come `highly confidential` declassato a `general`, è possibile gestire i vari criteri e intraprendere nuove azioni per limitare il comportamento indesiderato.</span><span class="sxs-lookup"><span data-stu-id="dd424-139">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="dd424-140">Dopo aver impostato i filtri, è possibile:</span><span class="sxs-lookup"><span data-stu-id="dd424-140">Once your filters are set, you can:</span></span>

- <span data-ttu-id="dd424-141">passare con il mouse su un segmento del grafico a barre per visualizzare il numero di elementi che rientrano in tale categoria ![Esplora attività al passaggio del mouse](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="dd424-141">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="dd424-142">esportare i dati</span><span class="sxs-lookup"><span data-stu-id="dd424-142">export the data</span></span>
- <span data-ttu-id="dd424-143">selezionare un determinato elemento nell'elenco e visualizzare i dettagli dell'azione nel riquadro a comparsa</span><span class="sxs-lookup"><span data-stu-id="dd424-143">select any given item from the list and view the details of the action in the fly-out</span></span>

![Riquadro a comparsa dei dettagli di Esplora attività](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="dd424-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd424-145">See also</span></span>
- [<span data-ttu-id="dd424-146">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="dd424-146">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="dd424-147">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="dd424-147">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="dd424-148">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="dd424-148">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="dd424-149">Panoramica dei criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="dd424-149">Overview of retention policies</span></span>](retention-policies.md)