---
title: Isolamento basato su hardware (Windows 10)
ms.reviewer: ''
description: Scopri come l'isolamento basato su hardware in Windows 10 aiuta a contrastare il malware.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060953"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="f991b-103">Isolamento basato su hardware in Windows 10</span><span class="sxs-lookup"><span data-stu-id="f991b-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f991b-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f991b-104">**Applies to:**</span></span>
- [<span data-ttu-id="f991b-105">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f991b-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f991b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f991b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f991b-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f991b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f991b-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f991b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f991b-109">L'isolamento basato su hardware consente di proteggere l'integrità del sistema in Windows 10 ed è integrato con Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f991b-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="f991b-110">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="f991b-110">Feature</span></span> | <span data-ttu-id="f991b-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f991b-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="f991b-112">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="f991b-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="f991b-113">Application Guard protegge il dispositivo da attacchi avanzati, mantenendoti produttivo.</span><span class="sxs-lookup"><span data-stu-id="f991b-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="f991b-114">Utilizzando un approccio di isolamento basato su hardware univoco, l'obiettivo è isolare i siti Web e i documenti PDF non attendibili all'interno di un contenitore leggero separato dal sistema operativo tramite l'hypervisor windows nativo.</span><span class="sxs-lookup"><span data-stu-id="f991b-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="f991b-115">Se un sito o un documento PDF non attendibile risulta dannoso, rimane comunque contenuto nel contenitore sicuro di Application Guard, mantenendo il PC desktop protetto e l'autore dell'attacco lontano dai dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="f991b-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="f991b-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="f991b-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="f991b-117">System Guard protegge e mantiene l'integrità del sistema all'avvio e dopo l'esecuzione e convalida l'integrità del sistema utilizzando l'attestazione.</span><span class="sxs-lookup"><span data-stu-id="f991b-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

