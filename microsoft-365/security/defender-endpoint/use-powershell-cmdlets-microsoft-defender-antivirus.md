---
title: Utilizzare i cmdlet di PowerShell per configurare ed eseguire Microsoft Defender AV
description: In Windows 10, è possibile utilizzare i cmdlet di PowerShell per eseguire analisi, aggiornare Security intelligence e modificare le impostazioni in Antivirus Microsoft Defender.
keywords: analisi, riga di comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765300"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="e8ad7-104">Utilizzare i cmdlet di PowerShell per configurare e gestire Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8ad7-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e8ad7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e8ad7-105">**Applies to:**</span></span>

- [<span data-ttu-id="e8ad7-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e8ad7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e8ad7-107">È possibile utilizzare PowerShell per eseguire varie funzioni in Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="e8ad7-108">Analogamente al prompt dei comandi o alla riga di comando, PowerShell è una shell da riga di comando basata su attività e un linguaggio di script progettato appositamente per l'amministrazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="e8ad7-109">Per altre informazioni, vedere [l'hub di PowerShell su MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="e8ad7-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="e8ad7-110">Per un elenco dei cmdlet, delle relative funzioni e dei parametri disponibili, vedere [l'argomento Cmdlet defender.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="e8ad7-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="e8ad7-111">I cmdlet di PowerShell sono particolarmente utili negli ambienti Windows Server che non si basano su un'interfaccia utente grafica (GUI) per configurare il software.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ad7-112">I cmdlet di PowerShell non devono essere utilizzati in sostituzione di [un'infrastruttura](https://www.microsoft.com/download/101445)di gestione dei criteri di rete completa, ad esempio [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) [Microsoft Endpoint Configuration Manager,](/configmgr)Console Gestione Criteri di gruppo o Antivirus Microsoft Defender modelli ADMX di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="e8ad7-113">Le modifiche apportate con PowerShell influiranno sulle impostazioni locali nell'endpoint in cui le modifiche vengono distribuite o apportate.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="e8ad7-114">Ciò significa che le distribuzioni dei criteri con Criteri di gruppo, Microsoft Endpoint Configuration Manager o Microsoft Intune possono sovrascrivere le modifiche apportate con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="e8ad7-115">È possibile [configurare le impostazioni che possono essere ignorate localmente con le sostituzioni dei criteri locali.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e8ad7-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="e8ad7-116">PowerShell viene in genere installato nella cartella `%SystemRoot%\system32\WindowsPowerShell` .</span><span class="sxs-lookup"><span data-stu-id="e8ad7-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="e8ad7-117">Utilizzare Antivirus Microsoft Defender cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8ad7-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="e8ad7-118">Nella barra Windows ricerca digitare **powershell.**</span><span class="sxs-lookup"><span data-stu-id="e8ad7-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="e8ad7-119">Selezionare **Windows PowerShell** dai risultati per aprire l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="e8ad7-120">Immettere il comando PowerShell e gli eventuali parametri.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ad7-121">Potrebbe essere necessario aprire PowerShell in modalità amministratore.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="e8ad7-122">Fare clic con il pulsante destro del mouse sull'elemento nel menu Start, scegliere Esegui come **amministratore** e fare clic su **Sì** al prompt delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="e8ad7-123">Per aprire la Guida in linea per uno dei cmdlet, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e8ad7-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="e8ad7-124">Omettere il `-online` parametro per ottenere la Guida memorizzata localmente nella cache.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8ad7-125">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e8ad7-125">Related topics</span></span>

- [<span data-ttu-id="e8ad7-126">Argomenti di riferimento per gli strumenti di gestione e configurazione</span><span class="sxs-lookup"><span data-stu-id="e8ad7-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e8ad7-127">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e8ad7-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e8ad7-128">Antivirus Microsoft Defender Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e8ad7-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)