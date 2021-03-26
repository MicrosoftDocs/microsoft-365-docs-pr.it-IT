---
title: Eseguire il pull dei rilevamenti agli strumenti SIEM da Microsoft Defender per Endpoint
description: Scopri come usare l'API REST e configurare gli strumenti di gestione degli eventi e delle informazioni di sicurezza supportati per ricevere e estrarre i rilevamenti.
keywords: configurare siem, strumenti di gestione delle informazioni di sicurezza ed eventi, splunk, arcsight, indicatori personalizzati, api rest, definizioni di avviso, indicatori di compromissione
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222336"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="58025-104">Eseguire il pull dei rilevamenti agli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="58025-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="58025-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="58025-105">**Applies to:**</span></span>
- [<span data-ttu-id="58025-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="58025-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="58025-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58025-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="58025-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="58025-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="58025-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="58025-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="58025-110">Rilevamento pull tramite strumenti di gestione di eventi e informazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="58025-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="58025-111">[Microsoft Defender for Endpoint Alert](alerts.md) è composto da uno o più rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="58025-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="58025-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) è composto dall'evento sospetto che si è verificato nel dispositivo e dai relativi dettagli di avviso.</span><span class="sxs-lookup"><span data-stu-id="58025-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="58025-113">-L'API di Microsoft Defender for Endpoint Alert è l'API più recente per il consumo di avvisi e contiene un elenco dettagliato di prove correlate per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="58025-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="58025-114">Per ulteriori informazioni, vedere [Metodi e proprietà degli](alerts.md) avvisi e Avvisi [elenco.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="58025-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="58025-115">Defender for Endpoint supporta gli strumenti siem (Security Information and Event Management) per il pull dei rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="58025-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="58025-116">Defender for Endpoint espone gli avvisi tramite un endpoint HTTPS ospitato in Azure.</span><span class="sxs-lookup"><span data-stu-id="58025-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="58025-117">L'endpoint può essere configurato per il pull dei rilevamenti dal tenant aziendale in Azure Active Directory (AAD) utilizzando il protocollo di autenticazione OAuth 2.0 per un'applicazione AAD che rappresenta lo specifico connettore SIEM installato nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="58025-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="58025-118">Defender for Endpoint attualmente supporta i seguenti strumenti di soluzione SIEM specifici tramite un modello di integrazione SIEM dedicato:</span><span class="sxs-lookup"><span data-stu-id="58025-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="58025-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="58025-119">IBM QRadar</span></span>
- <span data-ttu-id="58025-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="58025-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="58025-121">Altre soluzioni SIEM (come Splunk, RSA NetWitness) sono supportate tramite un modello di integrazione diverso basato sulla nuova API alert.</span><span class="sxs-lookup"><span data-stu-id="58025-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="58025-122">Per altre informazioni, visualizza la pagina [dell'applicazione partner](https://securitycenter.microsoft.com/interoperability/partners) e seleziona la sezione Analisi e informazioni di sicurezza per i dettagli completi.</span><span class="sxs-lookup"><span data-stu-id="58025-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="58025-123">Per utilizzare uno di questi strumenti SIEM supportati, è necessario:</span><span class="sxs-lookup"><span data-stu-id="58025-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="58025-124">Abilitare l'integrazione SIEM in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="58025-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="58025-125">Configurare lo strumento SIEM supportato:</span><span class="sxs-lookup"><span data-stu-id="58025-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="58025-126">Configurare Micro Focus ArcSight per eseguire il pull di Defender per i rilevamenti degli endpoint</span><span class="sxs-lookup"><span data-stu-id="58025-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="58025-127">Configurare IBM QRadar per il pull defender per i rilevamenti degli endpoint Per ulteriori informazioni, vedere [IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="58025-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="58025-128">Per altre informazioni sull'elenco dei campi esposti nell'API di rilevamento, vedi [Defender per i campi di rilevamento degli endpoint.](api-portal-mapping.md)</span><span class="sxs-lookup"><span data-stu-id="58025-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
