---
title: Evitare caratteri non validi nelle regole di filtro della posta indesiderata e nel criterio del filtro della posta indesiderata
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Viene fornita assistenza per gli amministratori che dispongono di caratteri non validi nella configurazione di protezione da posta indesiderata e vengono eseguiti in &amp; problemi quando si tenta di utilizzare il Centro sicurezza e conformità.
ms.openlocfilehash: f1841eb86583a48acecde0770f030b626323fa8e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599113"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="fa9af-103">Evitare caratteri non validi nelle regole del filtro posta indesiderata e nei criteri di filtro della posta</span><span class="sxs-lookup"><span data-stu-id="fa9af-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="fa9af-104">In precedenza, gli amministratori di Office 365 impostare e configurare le regole di filtro della posta indesiderata e i criteri di filtro della posta indesiderata tramite l'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="fa9af-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="fa9af-105">A questo punto, è possibile &amp; utilizzare il Centro sicurezza e conformità per gestire la configurazione della protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="fa9af-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="fa9af-106">I caratteri seguenti sono supportati nell'interfaccia di amministrazione di Exchange, ma non sono supportati per &amp; l'utilizzo nel centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="fa9af-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="fa9af-107">**Caratteri non validi:**</span><span class="sxs-lookup"><span data-stu-id="fa9af-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="fa9af-108">Se le regole del filtro di posta indesiderata o il criterio di filtro della posta indesiderata contiene uno dei caratteri non validi, è possibile che si verifichi uno o tutti questi problemi:</span><span class="sxs-lookup"><span data-stu-id="fa9af-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="fa9af-109">Potrebbe essere Impossibile trovare il criterio o le regole nel centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="fa9af-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="fa9af-110">È possibile che si verifichino errori durante il tentativo di ottenere le regole o il criterio utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa9af-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="fa9af-111">Potrebbe risultare che il criterio o le impostazioni non vengano eseguite o eseguite come previsto.</span><span class="sxs-lookup"><span data-stu-id="fa9af-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="fa9af-112">Rimuovere i caratteri non validi dai criteri e dalle regole del filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="fa9af-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="fa9af-113">Dopo aver identificato i criteri e le regole che contengono caratteri non validi, è possibile modificare i nomi utilizzando i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa9af-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="fa9af-114">[Connettersi a Exchange Online tramite Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fa9af-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="fa9af-115">Per modificare il nome del criterio di filtro della posta indesiderata, eseguire il cmdlet Set-HostedContentFilterPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fa9af-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="fa9af-116">Per modificare il nome di una regola di filtro per la posta indesiderata, eseguire il cmdlet Set-HostedContentFilterRule come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fa9af-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="fa9af-117">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="fa9af-117">For more information</span></span>

[<span data-ttu-id="fa9af-118">Gestione delle minacce nel centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="fa9af-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="fa9af-119">Set-HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="fa9af-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[<span data-ttu-id="fa9af-120">Set-HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="fa9af-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
