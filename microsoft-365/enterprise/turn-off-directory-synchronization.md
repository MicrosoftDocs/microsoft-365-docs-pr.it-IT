---
title: Disattivare la sincronizzazione della directory per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: In questo articolo, trovare informazioni sull'uso di PowerShell per disattivare la sincronizzazione della directory per Microsoft 365.
ms.openlocfilehash: 036130b70382e28ad9d8cb10786ad5e266375c20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909311"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="c3c26-103">Disattivare la sincronizzazione della directory per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3c26-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="c3c26-104">È possibile utilizzare PowerShell per disattivare la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="c3c26-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="c3c26-105">Tuttavia, non è consigliabile disattivare la sincronizzazione della directory come passaggio di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="c3c26-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="c3c26-106">Per assistenza nella risoluzione dei problemi di sincronizzazione della directory, vedere l'articolo Risolvere i problemi di [sincronizzazione della directory per Microsoft 365.](fix-problems-with-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="c3c26-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="c3c26-107">[Se necessario,](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) contattare il supporto per i prodotti aziendali.</span><span class="sxs-lookup"><span data-stu-id="c3c26-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="c3c26-108">Disattivare la sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="c3c26-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="c3c26-109">Per disattivare la sincronizzazione della directory:</span><span class="sxs-lookup"><span data-stu-id="c3c26-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="c3c26-110">Innanzitutto, installare il software necessario e connettersi all'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3c26-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="c3c26-111">Per istruzioni, vedere [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3c26-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="c3c26-112">Utilizzare [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) per disabilitare la sincronizzazione della directory:</span><span class="sxs-lookup"><span data-stu-id="c3c26-112">Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="c3c26-113">Se si utilizza questo comando, è necessario attendere 72 ore prima di poter riattivare la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="c3c26-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
