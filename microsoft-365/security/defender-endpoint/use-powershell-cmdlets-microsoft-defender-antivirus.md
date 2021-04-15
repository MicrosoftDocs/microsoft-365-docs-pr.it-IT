---
title: Utilizzare i cmdlet di PowerShell per configurare ed eseguire Microsoft Defender AV
description: In Windows 10, è possibile utilizzare i cmdlet di PowerShell per eseguire analisi, aggiornare Security intelligence e modificare le impostazioni in Microsoft Defender Antivirus.
keywords: analisi, riga di comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 0fd1e6b2eec1be722af58e0753e158c050b56c6b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749879"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="97c22-104">Utilizzare i cmdlet di PowerShell per configurare e gestire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="97c22-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="97c22-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="97c22-105">**Applies to:**</span></span>

- [<span data-ttu-id="97c22-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="97c22-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="97c22-107">È possibile utilizzare PowerShell per eseguire varie funzioni in Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="97c22-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="97c22-108">Analogamente al prompt dei comandi o alla riga di comando, PowerShell è una shell da riga di comando basata su attività e un linguaggio di script progettato appositamente per l'amministrazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="97c22-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="97c22-109">Per altre informazioni, vedere [l'hub di PowerShell su MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="97c22-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="97c22-110">Per un elenco dei cmdlet, delle relative funzioni e dei parametri disponibili, vedere [l'argomento Cmdlet defender.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="97c22-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="97c22-111">I cmdlet di PowerShell sono particolarmente utili in ambienti Windows Server che non si basano su un'interfaccia utente grafica (GUI) per configurare il software.</span><span class="sxs-lookup"><span data-stu-id="97c22-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="97c22-112">I cmdlet di PowerShell non devono essere utilizzati in sostituzione di un'infrastruttura di gestione dei criteri di rete completa, ad esempio [Microsoft Endpoint Configuration Manager,](/configmgr) [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo o modelli ADMX di Criteri di gruppo di Microsoft [Defender Antivirus.](https://www.microsoft.com/download/101445)</span><span class="sxs-lookup"><span data-stu-id="97c22-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="97c22-113">Le modifiche apportate con PowerShell influiranno sulle impostazioni locali nell'endpoint in cui le modifiche vengono distribuite o apportate.</span><span class="sxs-lookup"><span data-stu-id="97c22-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="97c22-114">Ciò significa che le distribuzioni dei criteri con Criteri di gruppo, Microsoft Endpoint Configuration Manager o Microsoft Intune possono sovrascrivere le modifiche apportate con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97c22-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="97c22-115">È possibile [configurare le impostazioni che possono essere ignorate localmente con le sostituzioni dei criteri locali.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="97c22-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="97c22-116">PowerShell viene in genere installato nella cartella `%SystemRoot%\system32\WindowsPowerShell` .</span><span class="sxs-lookup"><span data-stu-id="97c22-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="97c22-117">Utilizzare i cmdlet di PowerShell di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="97c22-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="97c22-118">Nella barra di ricerca di Windows digitare **powershell.**</span><span class="sxs-lookup"><span data-stu-id="97c22-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="97c22-119">Selezionare **Windows PowerShell** dai risultati per aprire l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="97c22-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="97c22-120">Immettere il comando PowerShell e gli eventuali parametri.</span><span class="sxs-lookup"><span data-stu-id="97c22-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="97c22-121">Potrebbe essere necessario aprire PowerShell in modalità amministratore.</span><span class="sxs-lookup"><span data-stu-id="97c22-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="97c22-122">Fare clic con il pulsante destro del mouse sull'elemento nel menu Start, scegliere Esegui come **amministratore** e fare clic su **Sì** al prompt delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="97c22-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="97c22-123">Per aprire la Guida in linea per uno dei cmdlet, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97c22-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="97c22-124">Omettere il `-online` parametro per ottenere la Guida memorizzata localmente nella cache.</span><span class="sxs-lookup"><span data-stu-id="97c22-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="97c22-125">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="97c22-125">Related topics</span></span>

- [<span data-ttu-id="97c22-126">Argomenti di riferimento per gli strumenti di gestione e configurazione</span><span class="sxs-lookup"><span data-stu-id="97c22-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="97c22-127">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="97c22-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="97c22-128">Cmdlet di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="97c22-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)