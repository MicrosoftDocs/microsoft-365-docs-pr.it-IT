---
title: Utilizzare popout snelli per ridurre la memoria utilizzata durante la lettura dei messaggi di posta elettronica
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: In questo articolo sono contenute informazioni sull'utilizzo di popup snelli per migliorare le prestazioni di download dei messaggi in Outlook sul Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691442"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="21edc-103">Utilizzare popout snelli per ridurre la memoria utilizzata durante la lettura dei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="21edc-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="21edc-104">In questo articolo sono contenute informazioni per migliorare le prestazioni di download dei messaggi in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="21edc-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="21edc-105">Questo articolo fa parte del progetto Pianificazione della rete e ottimizzazione delle prestazioni [per office 365.](https://aka.ms/tune)</span><span class="sxs-lookup"><span data-stu-id="21edc-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="21edc-106">In quanto amministratore globale di Office 365, è possibile configurare Outlook sul Web per recapitare _popout_ snelli, una versione più piccola e meno intensiva di memoria di alcuni messaggi di posta elettronica in Microsoft Edge o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="21edc-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="21edc-107">Quando i popup snelli sono configurati per Outlook sul Web, vengono caricati i componenti sottoposti a rendering sul lato server che ottimizzano le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="21edc-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21edc-108">A partire da marzo 2018, i popup snelli non sono disponibili per i messaggi che specificano restrizioni relative ai diritti di utilizzo, ad esempio Information Rights Management (IRM).</span><span class="sxs-lookup"><span data-stu-id="21edc-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="21edc-109">Queste funzionalità continueranno a funzionare nella finestra principale, ma non sono disponibili nei popup snelli:</span><span class="sxs-lookup"><span data-stu-id="21edc-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="21edc-110">Componenti aggiuntivi di Outlook</span><span class="sxs-lookup"><span data-stu-id="21edc-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="21edc-111">Presenza in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="21edc-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="21edc-112">Per configurare i popup snelli per tutti gli utenti all'interno dell'organizzazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="21edc-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="21edc-113">[Connettersi a Exchange Online utilizzando Remote PowerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx )</span><span class="sxs-lookup"><span data-stu-id="21edc-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="21edc-114">Eseguire il cmdlet [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) con il parametro LeanPopoutEnabled nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="21edc-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="21edc-115">Ad esempio, per abilitare i popup snelli per tutti gli utenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="21edc-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="21edc-116">Per disabilitare i popup snelli per tutti gli utenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="21edc-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
