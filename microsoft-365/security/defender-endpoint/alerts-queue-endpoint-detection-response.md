---
title: Coda avvisi in Microsoft Defender Security Center
ms.reviewer: ''
description: Visualizzare e gestire gli avvisi visualizzati in Microsoft Defender Security Center
keywords: ''
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
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067402"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="80a16-103">Coda avvisi in Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="80a16-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80a16-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="80a16-104">**Applies to:**</span></span>
- [<span data-ttu-id="80a16-105">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="80a16-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="80a16-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="80a16-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="80a16-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="80a16-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="80a16-108">Informazioni su come visualizzare e gestire la coda in modo da analizzare in modo efficace le minacce rilevate in entità quali dispositivi, file o account utente.</span><span class="sxs-lookup"><span data-stu-id="80a16-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="80a16-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="80a16-109">In this section</span></span>
<span data-ttu-id="80a16-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="80a16-110">Topic</span></span> | <span data-ttu-id="80a16-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80a16-111">Description</span></span> 
:---|:---
[<span data-ttu-id="80a16-112">Visualizzare e organizzare la coda di avvisi</span><span class="sxs-lookup"><span data-stu-id="80a16-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="80a16-113">Mostra un elenco di avvisi contrassegnati nella rete.</span><span class="sxs-lookup"><span data-stu-id="80a16-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="80a16-114">Gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="80a16-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="80a16-115">Informazioni su come gestire gli avvisi, ad esempio modificarne lo stato, assegnarlo a un membro delle operazioni di sicurezza e visualizzare la cronologia di un avviso.</span><span class="sxs-lookup"><span data-stu-id="80a16-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="80a16-116">Esaminare gli avvisi</span><span class="sxs-lookup"><span data-stu-id="80a16-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="80a16-117">Analizzare gli avvisi che interessano la rete, comprenderne il significato e come risolverli.</span><span class="sxs-lookup"><span data-stu-id="80a16-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="80a16-118">Esaminare i file</span><span class="sxs-lookup"><span data-stu-id="80a16-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="80a16-119">Analizzare i dettagli di un file associato a un avviso, un comportamento o un evento specifico.</span><span class="sxs-lookup"><span data-stu-id="80a16-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="80a16-120">Esaminare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="80a16-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="80a16-121">Analizzare i dettagli di un dispositivo associato a un avviso, un comportamento o un evento specifico.</span><span class="sxs-lookup"><span data-stu-id="80a16-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="80a16-122">Esaminare un indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="80a16-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="80a16-123">Esaminare le possibili comunicazioni tra i dispositivi della rete e gli indirizzi IP (Internet Protocol) esterni.</span><span class="sxs-lookup"><span data-stu-id="80a16-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="80a16-124">Esaminare un dominio</span><span class="sxs-lookup"><span data-stu-id="80a16-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="80a16-125">Analizzare un dominio per verificare se i dispositivi e i server della rete comunicano con un dominio dannoso noto.</span><span class="sxs-lookup"><span data-stu-id="80a16-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="80a16-126">Esaminare un account utente</span><span class="sxs-lookup"><span data-stu-id="80a16-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="80a16-127">Identificare gli account utente con gli avvisi più attivi e analizzare i casi di potenziali credenziali compromesse.</span><span class="sxs-lookup"><span data-stu-id="80a16-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


