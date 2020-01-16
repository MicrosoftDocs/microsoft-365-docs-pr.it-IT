---
title: Caccia alle minacce in Microsoft 365
description: Utilizzo delle funzionalità di ricerca di minacce nel centro sicurezza Microsoft 365 per individuare in modo proattivo le violazioni e altre minacce
keywords: sicurezza, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Centro sicurezza, Hunt, Threat Hunting, cyberthreat Hunting, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Advanced Hunting
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: lomayor
author: lomayor
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: e0f4c97a1c2963fc714420457208b40af688d86b
ms.sourcegitcommit: c9332016f61b26f63c9145c9169ea5330e91a243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "41173502"
---
# <a name="hunt-for-threats-in-microsoft-365"></a><span data-ttu-id="8fb06-104">Caccia alle minacce in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fb06-104">Hunt for threats in Microsoft 365</span></span>

<span data-ttu-id="8fb06-105">Con le funzionalità di ricerca di minacce nel centro sicurezza Microsoft 365, è possibile trovare in modo proattivo minacce nell'organizzazione che interessano la posta elettronica e i dati, i dispositivi e le identità.</span><span class="sxs-lookup"><span data-stu-id="8fb06-105">With threat hunting capabilities in the Microsoft 365 security center, you can proactively find threats in your organization affecting email and data, devices, and identities.</span></span> <span data-ttu-id="8fb06-106">Nella schermata di **caccia** è possibile accedere agli strumenti di ricerca di minacce resi disponibili da diverse soluzioni:</span><span class="sxs-lookup"><span data-stu-id="8fb06-106">From the **Hunting** screen, you can access threat hunting tools made available by various solutions:</span></span>
- <span data-ttu-id="8fb06-107">Office 365 ATP: [caccia alle minacce per la posta elettronica e i dati](../office-365-security/office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="8fb06-107">Office 365 ATP — [hunt for threats to email and data](../office-365-security/office-365-atp.md)</span></span>
- <span data-ttu-id="8fb06-108">Microsoft Defender ATP: [caccia alle minacce ai dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="8fb06-108">Microsoft Defender ATP — [hunt for threats to devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)</span></span>
- <span data-ttu-id="8fb06-109">Azure ATP: [ricerca di minacce per le identità](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user)</span><span class="sxs-lookup"><span data-stu-id="8fb06-109">Azure ATP — [hunt for threats to identities](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user)</span></span>

![Pagina di caccia](../images/hunt.png)


## <a name="hunt-with-microsoft-threat-protection"></a><span data-ttu-id="8fb06-111">Cercare con Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8fb06-111">Hunt with Microsoft Threat Protection</span></span>

<span data-ttu-id="8fb06-112">[Abilitare Microsoft Threat Protection](mtp-enable.md) per ottenere l'interfaccia di query di ricerca avanzata direttamente nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fb06-112">[Turn on Microsoft Threat Protection](mtp-enable.md) to get the advanced hunting query interface directly in the Microsoft 365 security center.</span></span> <span data-ttu-id="8fb06-113">Con la [ricerca avanzata](advanced-hunting-overview.md), è possibile creare singole query che esaminano i dati di Microsoft Defender ATP, coprendo i dati dai dispositivi onboarded e Office 365 ATP, fornendo dati da messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8fb06-113">With [advanced hunting](advanced-hunting-overview.md), you can create single queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8fb06-114">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8fb06-114">Related topics</span></span>
- [<span data-ttu-id="8fb06-115">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="8fb06-115">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8fb06-116">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8fb06-116">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="8fb06-117">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8fb06-117">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
