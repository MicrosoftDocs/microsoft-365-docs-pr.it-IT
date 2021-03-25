---
title: Configurare la riduzione della superficie di attacco
description: Usa Microsoft Intune, Microsoft Endpoint Configuration Manager, cmdlet di PowerShell e Criteri di gruppo per configurare la riduzione della superficie di attacco.
keywords: asr, riduzione della superficie di attacco, windows defender, microsoft defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166164"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="6c413-104">Configurare la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="6c413-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6c413-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6c413-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c413-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6c413-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c413-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c413-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6c413-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6c413-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6c413-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c413-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="6c413-110">Puoi configurare la riduzione della superficie di attacco con molti strumenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="6c413-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="6c413-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6c413-111">Microsoft Intune</span></span>
* <span data-ttu-id="6c413-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6c413-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="6c413-113">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="6c413-113">Group Policy</span></span>
* <span data-ttu-id="6c413-114">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c413-114">PowerShell cmdlets</span></span>

<span data-ttu-id="6c413-115">Articolo</span><span class="sxs-lookup"><span data-stu-id="6c413-115">Article</span></span> | <span data-ttu-id="6c413-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c413-116">Description</span></span>
-|-
[<span data-ttu-id="6c413-117">Abilitare l'isolamento basato su hardware per Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6c413-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="6c413-118">Come preparare e installare Application Guard, inclusi i requisiti hardware e software</span><span class="sxs-lookup"><span data-stu-id="6c413-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="6c413-119">Abilitare il controllo dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6c413-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="6c413-120">Come controllare le applicazioni eseguite dagli utenti e proteggere i processi in modalità kernel</span><span class="sxs-lookup"><span data-stu-id="6c413-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="6c413-121">Protezione da exploit</span><span class="sxs-lookup"><span data-stu-id="6c413-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="6c413-122">Come applicare automaticamente tecniche di mitigazione degli exploit sia nei processi del sistema operativo che nelle singole app</span><span class="sxs-lookup"><span data-stu-id="6c413-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="6c413-123">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="6c413-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="6c413-124">Come impedire agli utenti di usare app per accedere a domini pericolosi</span><span class="sxs-lookup"><span data-stu-id="6c413-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="6c413-125">Accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="6c413-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="6c413-126">Come proteggere dati importanti da app dannose</span><span class="sxs-lookup"><span data-stu-id="6c413-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="6c413-127">Riduzione della superficie d'attacco</span><span class="sxs-lookup"><span data-stu-id="6c413-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="6c413-128">Come impedire azioni e app in genere usate da malware per la ricerca di exploit</span><span class="sxs-lookup"><span data-stu-id="6c413-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="6c413-129">Firewall di rete</span><span class="sxs-lookup"><span data-stu-id="6c413-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="6c413-130">Come proteggere i dispositivi e i dati in una rete</span><span class="sxs-lookup"><span data-stu-id="6c413-130">How to protect devices and data across a network</span></span>

