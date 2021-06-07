---
title: Microsoft 365 Integrazione di Defender con Azure Sentinel
description: Usa Azure Sentinel come SIEM per Microsoft 365 eventi ed eventi di Defender.
keywords: incidenti, avvisi, analizzare, analizzare, risposta, correlazione, attacco, computer, dispositivi, utenti, identità, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7d9cff584f35c39544034501c607b7156a0f1bf2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782922"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="24621-104">Microsoft 365 Integrazione di Defender con Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="24621-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="24621-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="24621-105">**Applies to:**</span></span>
- <span data-ttu-id="24621-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24621-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="24621-107">Il connettore Microsoft 365 Defender per Azure Sentinel (anteprima) invia tutti gli eventi imprevisti e gli avvisi di Microsoft 365 Defender ad Azure Sentinel e mantiene sincronizzati gli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="24621-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="24621-108">Dopo aver aggiunto il connettore, gli eventi imprevisti di Microsoft 365 Defender che includono tutti gli avvisi, le entità e le informazioni pertinenti associati ricevuti da Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender per Office 365 e Microsoft Cloud App Security vengono trasmessi ad Azure Sentinel come dati &mdash; siem (Security Information and Event Management), fornendo il contesto per eseguire la triage e la risposta agli incidenti con &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="24621-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="24621-109">Una volta in Azure Sentinel, gli incidenti rimangono sincronizzati bidirezionalemente con Microsoft 365 Defender, consentendoti di sfruttare i vantaggi del Centro sicurezza Microsoft 365 e di Azure Sentinel nel portale di Azure per l'indagine e la risposta agli incidenti.</span><span class="sxs-lookup"><span data-stu-id="24621-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="24621-110">Ecco come funziona.</span><span class="sxs-lookup"><span data-stu-id="24621-110">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flusso e condivisione dei dati degli eventi imprevisti tra Microsoft 365 Defender e Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="24621-112">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="24621-112">Next steps</span></span>

1. <span data-ttu-id="24621-113">Informazioni più approfondite [sull'integrazione Microsoft 365 Defender con Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)</span><span class="sxs-lookup"><span data-stu-id="24621-113">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="24621-114">[Connessione dati da Microsoft 365 Defender ad Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="24621-114">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="24621-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24621-115">See also</span></span>

- [<span data-ttu-id="24621-116">Panoramica degli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24621-116">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="24621-117">Analizzare gli eventi imprevisti con Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="24621-117">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
