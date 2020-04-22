---
title: Utilizzare lo strumento di esportazione di eDiscovery in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: È necessario abilitare il supporto ClickOnce per utilizzare la versione più recente di Microsoft Edge per scaricare i risultati della ricerca dalla ricerca di contenuto e eDiscovery nel centro sicurezza e conformità.
ms.openlocfilehash: c48e3fb04747306693364a2cdbc6f18047a0fd9e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632381"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="ad0e2-103">Utilizzare lo strumento di esportazione di eDiscovery in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ad0e2-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="ad0e2-104">A seguito delle recenti modifiche apportate alla versione più recente di Microsoft Edge, il supporto ClickOnce non è più abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="ad0e2-105">Per continuare a utilizzare lo strumento di esportazione di eDiscovery per scaricare i risultati della ricerca di contenuto o di eDiscovery, è necessario utilizzare [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o abilitare il supporto di ClickOnce nella versione più recente di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="ad0e2-106">Abilitare il supporto ClickOnce in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ad0e2-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="ad0e2-107">In Microsoft Edge, passare a **edge://flags/#edge-fare clic su-una volta**.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="ad0e2-108">Se il valore esistente è impostato su **predefinito** o **disabilitato** nell'elenco a discesa, impostarlo su **abilitato**.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="ad0e2-109">Scorrere verso il basso fino alla parte inferiore della finestra del browser e fare clic su **Riavvia** per riavviare Edge.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="ad0e2-110">**Nota:** Le organizzazioni possono utilizzare criteri di gruppo per disabilitare il supporto ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="ad0e2-111">Per verificare se è presente un criterio di organizzazione per il supporto di ClickOnce, accedere a **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-111">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="ad0e2-112">Nella schermata seguente viene mostrato che ClickOnce è abilitata all'interno dell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="ad0e2-113">Se il valore di questo criterio è impostato su **false**, sarà necessario contattare un amministratore dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="ad0e2-114">Installare ed eseguire lo strumento di esportazione di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ad0e2-114">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="ad0e2-115">Fare clic su **Scarica risultati** nella pagina a comparsa di un'esportazione in ricerca contenuto o in un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Fare clic su Scarica risultati nella pagina a comparsa per scaricare i risultati della ricerca](../media/ClickOnceExport1.png)

2. <span data-ttu-id="ad0e2-117">Verrà visualizzata la richiesta di conferma per l'avvio dello strumento, fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Fare clic su Apri per avviare lo strumento di esportazione di eDiscovery](../media/ClickOnceimage4.png)

   <span data-ttu-id="ad0e2-119">Se lo strumento di esportazione di eDiscovery non è installato, verrà visualizzato un avviso di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="ad0e2-119">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Fare clic su Installa per installare lo strumento di esportazione di eDiscovery](../media/ClickOnceimage5.png)

3. <span data-ttu-id="ad0e2-121">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-121">Click **Install**.</span></span> <span data-ttu-id="ad0e2-122">Dopo l'installazione, lo strumento di esportazione verrà avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ad0e2-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="ad0e2-123">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="ad0e2-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="ad0e2-124">Esportare i risultati della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="ad0e2-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="ad0e2-125">Come abilitare i flag degli esperimenti in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ad0e2-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
