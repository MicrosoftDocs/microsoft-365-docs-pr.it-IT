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
description: In questo articolo sono contenute informazioni sull'utilizzo di popout snelli per migliorare le prestazioni di download dei messaggi Outlook sul Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925257"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="69cbb-103">Utilizzare popout snelli per ridurre la memoria utilizzata durante la lettura dei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="69cbb-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="69cbb-104">Questo articolo contiene informazioni per migliorare le prestazioni di download dei messaggi Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="69cbb-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="69cbb-105">Questo articolo fa parte di Pianificazione della rete [e ottimizzazione delle](./network-planning-and-performance.md) prestazioni per Office 365 progetto.</span><span class="sxs-lookup"><span data-stu-id="69cbb-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="69cbb-106">In quanto amministratore globale Office 365, è possibile configurare Outlook sul Web per fornire _popout_ snelli, una versione più piccola e con un utilizzo minore della memoria di alcuni messaggi di posta elettronica in Microsoft Edge o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="69cbb-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="69cbb-107">Quando i popup snelli sono configurati per Outlook sul Web, vengono caricati i componenti di rendering sul lato server che ottimizzano le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="69cbb-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="69cbb-108">A partire da marzo 2018, i popup snelli non sono disponibili per i messaggi che specificano restrizioni per i diritti di utilizzo, ad esempio Information Rights Management (IRM).</span><span class="sxs-lookup"><span data-stu-id="69cbb-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="69cbb-109">Queste funzionalità continueranno a funzionare nella finestra principale, ma non sono disponibili nei popup snelli:</span><span class="sxs-lookup"><span data-stu-id="69cbb-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="69cbb-110">Outlook componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="69cbb-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="69cbb-111">Skype for Business presenza</span><span class="sxs-lookup"><span data-stu-id="69cbb-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="69cbb-112">Per configurare i popup snelli per tutti gli utenti all'interno dell'Office 365 organizzazione</span><span class="sxs-lookup"><span data-stu-id="69cbb-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="69cbb-113">[Connessione utilizzare Exchange Online PowerShell remoto.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="69cbb-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="69cbb-114">Eseguire il cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) con il parametro LeanPopoutEnabled come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="69cbb-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="69cbb-115">Ad esempio, per abilitare i popup snelli per tutti gli utenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="69cbb-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="69cbb-116">Per disabilitare i popup snelli per tutti gli utenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="69cbb-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```