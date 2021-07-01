---
title: Avvisi di sicurezza di Microsoft Defender for Identity in Microsoft 365 Defender
description: Informazioni su come gestire ed esaminare gli avvisi di sicurezza emessi da Microsoft Defender per l'identità in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228964"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="dad5d-103">Avvisi di sicurezza di Defender for Identity in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dad5d-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="dad5d-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dad5d-104">**Applies to:**</span></span>

- <span data-ttu-id="dad5d-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dad5d-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="dad5d-106">Defender per identità</span><span class="sxs-lookup"><span data-stu-id="dad5d-106">Defender for Identity</span></span>

<span data-ttu-id="dad5d-107">In questo articolo vengono illustrate le nozioni di base su come utilizzare gli avvisi di sicurezza di [Microsoft Defender for Identity](/defender-for-identity) nel Centro sicurezza Microsoft 365 [sicurezza](/microsoft-365/security/defender/overview-security-center).</span><span class="sxs-lookup"><span data-stu-id="dad5d-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="dad5d-108">Gli avvisi di Defender for Identity sono integrati in modo nativo nel centro sicurezza [Microsoft 365](https://security.microsoft.com) con un formato di pagina di avviso identità dedicato.</span><span class="sxs-lookup"><span data-stu-id="dad5d-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="dad5d-109">Questo rappresenta il primo passaggio del percorso per introdurre l'esperienza completa di [Microsoft Defender for Identity in Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="dad5d-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="dad5d-110">La nuova pagina di avviso identità offre ai clienti di Microsoft Defender for Identity un miglioramento del segnale tra domini e nuove funzionalità di risposta automatica alle identità.</span><span class="sxs-lookup"><span data-stu-id="dad5d-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="dad5d-111">Garantisce la sicurezza e consente di migliorare l'efficienza delle operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dad5d-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="dad5d-112">Uno dei vantaggi dell'analisi degli avvisi tramite [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) è che gli avvisi di Microsoft Defender for Identity sono ulteriormente correlati alle informazioni ottenute da ognuno degli altri prodotti della famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="dad5d-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="dad5d-113">Questi avvisi migliorati sono coerenti con gli altri Microsoft 365 Defender di avviso provenienti da [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security) e Microsoft Defender for [Endpoint.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="dad5d-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="dad5d-114">La nuova pagina elimina in modo efficace la necessità di passare a un altro portale del prodotto per analizzare gli avvisi associati all'identità.</span><span class="sxs-lookup"><span data-stu-id="dad5d-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="dad5d-115">Gli avvisi provenienti da Defender for Identity possono ora attivare le funzionalità di analisi e risposta automatizzate [(AIR)](/microsoft-365/security/defender/m365d-autoir) di Microsoft 365 Defender, tra cui la correzione automatica degli avvisi e la mitigazione di strumenti e processi che possono contribuire all'attività sospetta.</span><span class="sxs-lookup"><span data-stu-id="dad5d-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dad5d-116">Come parte della convergenza con Microsoft 365 Defender, alcune opzioni e dettagli sono cambiati dalla loro posizione nel portale defender per l'identità.</span><span class="sxs-lookup"><span data-stu-id="dad5d-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="dad5d-117">Leggi i dettagli seguenti per scoprire dove trovare sia le funzionalità familiari che le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="dad5d-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="dad5d-118">Esaminare gli avvisi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="dad5d-118">Review security alerts</span></span>

<span data-ttu-id="dad5d-119">È possibile accedere agli avvisi da più  posizioni, tra cui la pagina Avvisi, la pagina Eventi imprevisti, le pagine dei singoli dispositivi e dalla **pagina Ricerca** avanzata. </span><span class="sxs-lookup"><span data-stu-id="dad5d-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="dad5d-120">In questo esempio verrà esaminata la **pagina Avvisi**.</span><span class="sxs-lookup"><span data-stu-id="dad5d-120">In this example, we'll review the **Alerts page**.</span></span>

<span data-ttu-id="dad5d-121">Nel centro [Microsoft 365](https://security.microsoft.com/)sicurezza, passare a Eventi **imprevisti & avvisi** e quindi a **Avvisi**.</span><span class="sxs-lookup"><span data-stu-id="dad5d-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Vai a Eventi imprevisti e avvisi, quindi Avvisi](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="dad5d-123">Per visualizzare gli avvisi di Defender for Identity, in alto a destra seleziona **Filtro** e quindi in Origini dei servizi **seleziona** Microsoft Defender per **l'identità** e seleziona **Applica:**</span><span class="sxs-lookup"><span data-stu-id="dad5d-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Filtro per gli eventi defender per l'identità](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="dad5d-125">Gli avvisi vengono visualizzati con informazioni nelle colonne seguenti: Nome avviso, Tag, Gravità, Stato indagine,  **Stato,**   **Categoria,** Origine **rilevamento,** Asset con **impatto,** Prima attività e **Ultima attività.**  </span><span class="sxs-lookup"><span data-stu-id="dad5d-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Eventi Defender for Identity](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="dad5d-127">Gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="dad5d-127">Manage alerts</span></span>

<span data-ttu-id="dad5d-128">Se si fa clic **sul nome** dell'avviso per uno degli avvisi, si andrà alla pagina con i dettagli sull'avviso.</span><span class="sxs-lookup"><span data-stu-id="dad5d-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="dad5d-129">Nel riquadro sinistro verrà visualizzato un riepilogo di **Cosa è successo:**</span><span class="sxs-lookup"><span data-stu-id="dad5d-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![Cosa è successo nell'avviso](../../media/defender-identity/what-happened.png)

<span data-ttu-id="dad5d-131">Sopra la **casella Cosa è** successo sono presenti i pulsanti **Account,** **Host di destinazione** e Host **di** origine dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="dad5d-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="dad5d-132">Per altri avvisi, potresti visualizzare pulsanti per informazioni dettagliate su host, account, indirizzi IP, domini e gruppi di sicurezza aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="dad5d-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="dad5d-133">Seleziona una di queste entità per ottenere ulteriori dettagli sulle entità coinvolte.</span><span class="sxs-lookup"><span data-stu-id="dad5d-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="dad5d-134">Nel riquadro destro, vedrai i dettagli **dell'avviso.**</span><span class="sxs-lookup"><span data-stu-id="dad5d-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="dad5d-135">Qui è possibile visualizzare ulteriori dettagli ed eseguire diverse attività:</span><span class="sxs-lookup"><span data-stu-id="dad5d-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="dad5d-136">**Classificare questo avviso-** Qui è possibile designare questo avviso come **avviso True o** **False**</span><span class="sxs-lookup"><span data-stu-id="dad5d-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Classificare l'avviso](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="dad5d-138">**Stato avviso:** in **Imposta classificazione** è possibile classificare l'avviso **come True** o **False.**</span><span class="sxs-lookup"><span data-stu-id="dad5d-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="dad5d-139">In **Assegnato a** è possibile assegnare l'avviso a se stessi o annullarne l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="dad5d-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Stato avviso](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="dad5d-141">Dettagli **avviso-** In Dettagli avviso **è** possibile trovare ulteriori informazioni sull'avviso specifico, seguire un collegamento alla documentazione relativa al tipo di avviso, vedere l'evento imprevisto a cui è associato l'avviso, esaminare eventuali indagini automatizzate collegate a questo tipo di avviso e vedere i dispositivi e gli utenti a cui è stato generato l'impatto.</span><span class="sxs-lookup"><span data-stu-id="dad5d-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Dettagli avviso](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="dad5d-143">**Commenti &** cronologia: qui è possibile aggiungere i commenti all'avviso e visualizzare la cronologia di tutte le azioni associate all'avviso.</span><span class="sxs-lookup"><span data-stu-id="dad5d-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Commenti e cronologia](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="dad5d-145">**Gestisci avviso-** Se si seleziona **Gestisci** avviso, si passa a un riquadro che consente di modificare:</span><span class="sxs-lookup"><span data-stu-id="dad5d-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="dad5d-146">**Stato:** è possibile scegliere **Nuovo,** **Risolto** **o In corso.**</span><span class="sxs-lookup"><span data-stu-id="dad5d-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="dad5d-147">**Classificazione:** è possibile scegliere **True alert o** False **alert.**</span><span class="sxs-lookup"><span data-stu-id="dad5d-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="dad5d-148">**Commento:** è possibile aggiungere un commento sull'avviso.</span><span class="sxs-lookup"><span data-stu-id="dad5d-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="dad5d-149">Se si selezionano i tre punti accanto a Gestisci **avviso,** è possibile consultare un esperto di **minacce,** Esportare l'avviso in un file di Excel o Collega **a** un altro **evento imprevisto.**</span><span class="sxs-lookup"><span data-stu-id="dad5d-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Gestire l'avviso](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > <span data-ttu-id="dad5d-151">Nel file Excel sono ora disponibili **due collegamenti:** Visualizza **in Microsoft Defender per** l'identità e Visualizza in Microsoft 365 Defender .</span><span class="sxs-lookup"><span data-stu-id="dad5d-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="dad5d-152">Ogni collegamento consente di accedere al portale pertinente e di fornire informazioni sull'avviso.</span><span class="sxs-lookup"><span data-stu-id="dad5d-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="dad5d-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dad5d-153">See also</span></span>

- [<span data-ttu-id="dad5d-154">Analizzare gli avvisi in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dad5d-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
