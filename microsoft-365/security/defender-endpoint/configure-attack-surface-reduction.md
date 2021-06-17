---
title: Configurare le funzionalità per la riduzione della superficie di attacco
description: Utilizzare Microsoft Intune, Microsoft Endpoint Configuration Manager, i cmdlet di PowerShell e Criteri di gruppo per configurare la riduzione della superficie di attacco.
keywords: asr, riduzione della superficie di attacco, windows defender, microsoft defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984449"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="40329-104">Configurare le funzionalità per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="40329-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="40329-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="40329-105">**Applies to:**</span></span>

- [<span data-ttu-id="40329-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="40329-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="40329-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40329-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="40329-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="40329-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="40329-109">[Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="40329-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="40329-110">Defender for Endpoint include diverse funzionalità di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="40329-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="40329-111">Per altre informazioni, vedi [Panoramica delle funzionalità di riduzione della superficie di attacco.](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="40329-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="40329-112">Per configurare la riduzione della superficie di attacco nell'ambiente, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="40329-112">To configure attack surface reduction in your environment, follow these steps:</span></span>

1. <span data-ttu-id="40329-113">[Abilitare l'isolamento basato su hardware per Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span><span class="sxs-lookup"><span data-stu-id="40329-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="40329-114">Abilita il controllo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40329-114">Enable application control.</span></span>

   1. <span data-ttu-id="40329-115">Esaminare i criteri di base in Windows.</span><span class="sxs-lookup"><span data-stu-id="40329-115">Review base policies in Windows.</span></span> <span data-ttu-id="40329-116">Vedere [Criteri di base di esempio.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)</span><span class="sxs-lookup"><span data-stu-id="40329-116">See [Example Base Policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="40329-117">Vedi la [guida Windows Defender progettazione di Application Control](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span><span class="sxs-lookup"><span data-stu-id="40329-117">See the [Windows Defender Application Control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="40329-118">Fare riferimento [a Deploying Windows Defender Application Control (WDAC)](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="40329-118">Refer to [Deploying Windows Defender Application Control (WDAC) policies](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="40329-119">[Abilitare l'accesso controllato alle cartelle](enable-controlled-folders.md).</span><span class="sxs-lookup"><span data-stu-id="40329-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="40329-120">[Attivare Protezione di rete](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="40329-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="40329-121">[Abilita protezione da exploit](enable-exploit-protection.md).</span><span class="sxs-lookup"><span data-stu-id="40329-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="40329-122">[Configurare le regole di riduzione della superficie di attacco](enable-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="40329-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="40329-123">Configurare il firewall di rete.</span><span class="sxs-lookup"><span data-stu-id="40329-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="40329-124">Ottieni una panoramica di [Windows Defender Firewall con sicurezza avanzata.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="40329-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="40329-125">Usa la [Windows Defender progettazione del firewall per](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) decidere come progettare i criteri firewall.</span><span class="sxs-lookup"><span data-stu-id="40329-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="40329-126">Utilizzare la [Windows Defender di distribuzione di Firewall per](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) configurare il firewall dell'organizzazione con sicurezza avanzata.</span><span class="sxs-lookup"><span data-stu-id="40329-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span>

> [!TIP]
> <span data-ttu-id="40329-127">Nella maggior parte dei casi, quando si configurano le funzionalità di riduzione della superficie di attacco, è possibile scegliere tra diversi metodi:</span><span class="sxs-lookup"><span data-stu-id="40329-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>

> - <span data-ttu-id="40329-128">Microsoft Endpoint Manager (che ora include Microsoft Intune e Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="40329-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="40329-129">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="40329-129">Group Policy</span></span>
> - <span data-ttu-id="40329-130">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="40329-130">PowerShell cmdlets</span></span>
