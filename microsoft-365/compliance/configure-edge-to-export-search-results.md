---
title: Utilizzare lo strumento di esportazione di eDiscovery di Office 365 in Microsoft Edge
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: È necessario abilitare il supporto ClickOnce per l'utilizzo di Microsoft Edge per esportare i risultati della ricerca dalla ricerca contenuto e eDiscovery nel centro sicurezza e conformità.
ms.openlocfilehash: f3e0442fe349aa3364594e07873b229f3205fb5e
ms.sourcegitcommit: d656fd58e5491cfb7fee16b55dc7a58904ed128d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "39891127"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="9104b-103">Utilizzare lo strumento di esportazione di eDiscovery di Office 365 in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9104b-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="9104b-104">A seguito delle recenti modifiche apportate a Microsoft Edge, il supporto ClickOnce non è più abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9104b-104">As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="9104b-105">Per continuare a utilizzare lo strumento di esportazione di Microsoft Office 365 eDiscovery per scaricare i risultati della ricerca di contenuto o eDiscovery, è necessario utilizzare [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o abilitare il supporto di ClickOnce in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9104b-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in Microsoft Edge.</span></span>

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="9104b-106">Come abilitare il supporto ClickOnce in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9104b-106">How to enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="9104b-107">In Microsoft Edge, passare a **edge://flags/#edge-fare clic-una volta**.</span><span class="sxs-lookup"><span data-stu-id="9104b-107">In Microsoft Edge, navigate to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="9104b-108">Se il valore esistente è impostato su **predefinito** o **disabilitato** nell'elenco a discesa, impostarlo su **abilitato**.</span><span class="sxs-lookup"><span data-stu-id="9104b-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>
    
   ![](media/ClickOnceimage1.png)

3. <span data-ttu-id="9104b-109">Scorrere verso il basso fino alla parte inferiore della finestra del browser e fare clic su **Riavvia** per riavviare Edge.</span><span class="sxs-lookup"><span data-stu-id="9104b-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](media/ClickOnceimage2.png)

<span data-ttu-id="9104b-110">**Nota:** Le organizzazioni possono utilizzare criteri di gruppo per disabilitare il supporto ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="9104b-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="9104b-111">Per verificare se è presente un criterio di organizzazione per il supporto di ClickOnce, passare a **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="9104b-111">To check if there is an organizational policy for ClickOnce support, navigate to **edge://policy**.</span></span> <span data-ttu-id="9104b-112">Nella schermata seguente viene mostrato che ClickOnce è abilitata all'interno dell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9104b-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="9104b-113">Se il valore di questo criterio è impostato su **false**, sarà necessario contattare un amministratore dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9104b-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a><span data-ttu-id="9104b-114">Installare ed eseguire lo strumento di esportazione di eDiscovery di Office 365</span><span class="sxs-lookup"><span data-stu-id="9104b-114">Install and run the Office 365 eDiscovery Export Tool</span></span>

1. <span data-ttu-id="9104b-115">Fare clic su **Scarica risultati** nella pagina a comparsa di un'esportazione in ricerca contenuto o in un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="9104b-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Fare clic su Scarica risultati nella pagina a comparsa per scaricare i risultati della ricerca](media/ClickOnceExport1.png)

2. <span data-ttu-id="9104b-117">Verrà visualizzata la richiesta di conferma per l'avvio dello strumento, fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="9104b-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Fare clic su Apri per avviare lo strumento di esportazione di eDiscovery](media/ClickOnceimage4.png)

   <span data-ttu-id="9104b-119">Se lo strumento di esportazione di Microsoft Office 365 eDiscovery non è installato, verrà visualizzato un avviso di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="9104b-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Fare clic su Installa per installare lo strumento di esportazione di eDiscovery](media/ClickOnceimage5.png)

3. <span data-ttu-id="9104b-121">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="9104b-121">Click **Install**.</span></span> <span data-ttu-id="9104b-122">Dopo l'installazione, lo strumento di esportazione verrà avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9104b-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="9104b-123">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9104b-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="9104b-124">Esportare i risultati della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="9104b-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="9104b-125">Come abilitare i flag degli esperimenti in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9104b-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
