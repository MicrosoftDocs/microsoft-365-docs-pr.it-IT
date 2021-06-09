---
title: Configurare Antivirus Microsoft Defender con WMI
description: Informazioni su come configurare e gestire Antivirus Microsoft Defender utilizzando script WMI per recuperare, modificare e aggiornare le impostazioni in Microsoft Defender for Endpoint.
keywords: wmi, script, strumentazione gestione Windows, configurazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764064"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="412a3-104">Utilizzare Windows Management Instrumentation (WMI) per configurare e gestire Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="412a3-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="412a3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="412a3-105">**Applies to:**</span></span>

- [<span data-ttu-id="412a3-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="412a3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="412a3-107">Windows Strumentazione gestione (WMI) è un'interfaccia di scripting che consente di recuperare, modificare e aggiornare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="412a3-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="412a3-108">Per ulteriori informazioni su WMI, vedere la libreria [Microsoft Developer Network System Administration.](/windows/win32/wmisdk/wmi-start-page)</span><span class="sxs-lookup"><span data-stu-id="412a3-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="412a3-109">Antivirus Microsoft Defender dispone di una serie di classi WMI specifiche che possono essere utilizzate per eseguire la maggior parte delle stesse funzioni di Criteri di gruppo e di altri strumenti di gestione.</span><span class="sxs-lookup"><span data-stu-id="412a3-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="412a3-110">Molte delle classi sono analoghe ai [cmdlet di Defender PowerShell.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="412a3-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="412a3-111">La [libreria di riferimento Windows Defender provider WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) di MSDN elenca le classi WMI disponibili per Antivirus Microsoft Defender e include script di esempio.</span><span class="sxs-lookup"><span data-stu-id="412a3-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="412a3-112">Le modifiche apportate con WMI influiranno sulle impostazioni locali nell'endpoint in cui le modifiche vengono distribuite o apportate.</span><span class="sxs-lookup"><span data-stu-id="412a3-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="412a3-113">Ciò significa che le distribuzioni di criteri con Criteri di gruppo, Microsoft Endpoint Configuration Manager o Microsoft Intune possono sovrascrivere le modifiche apportate con WMI.</span><span class="sxs-lookup"><span data-stu-id="412a3-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="412a3-114">È possibile [configurare le impostazioni che possono essere ignorate localmente con le sostituzioni dei criteri locali.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="412a3-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="412a3-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="412a3-115">Related topics</span></span>

- [<span data-ttu-id="412a3-116">Argomenti di riferimento per gli strumenti di gestione e configurazione</span><span class="sxs-lookup"><span data-stu-id="412a3-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="412a3-117">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="412a3-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)