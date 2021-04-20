---
title: Applicazioni connesse in Microsoft Defender for Endpoint
ms.reviewer: ''
description: Visualizza le applicazioni partner connesse che usano il protocollo OAuth 2.0 standard per autenticare e fornire token da usare con Le API di Microsoft Defender for Endpoint.
keywords: partner, applicazioni, terze parti, connessioni, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, meglio mobile
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
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893498"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="e8792-104">Applicazioni connesse in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e8792-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e8792-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e8792-105">**Applies to:**</span></span>
- [<span data-ttu-id="e8792-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e8792-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e8792-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8792-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e8792-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e8792-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e8792-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e8792-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e8792-110">Le applicazioni connesse si integrano con la piattaforma Defender for Endpoint usando le API.</span><span class="sxs-lookup"><span data-stu-id="e8792-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="e8792-111">Le applicazioni usano il protocollo OAuth 2.0 standard per autenticare e fornire token da usare con le API di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e8792-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="e8792-112">Inoltre, le applicazioni di Azure Active Directory (Azure AD) consentono agli amministratori tenant di impostare un controllo esplicito sulle API a cui è possibile accedere usando l'app corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e8792-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="e8792-113">Dovrai seguire questi [passaggi](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) per usare le API con l'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="e8792-113">You'll need to follow [these steps](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="e8792-114">Accedere alla pagina dell'applicazione connessa</span><span class="sxs-lookup"><span data-stu-id="e8792-114">Access the connected application page</span></span>
<span data-ttu-id="e8792-115">Nel menu di spostamento a sinistra seleziona **Partner & API Applicazioni**  >  **AAD connesse.**</span><span class="sxs-lookup"><span data-stu-id="e8792-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="e8792-116">Visualizzare i dettagli dell'applicazione connessa</span><span class="sxs-lookup"><span data-stu-id="e8792-116">View connected application details</span></span>
<span data-ttu-id="e8792-117">La pagina Applicazioni connesse fornisce informazioni sulle applicazioni di Azure AD connesse a Microsoft Defender for Endpoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8792-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="e8792-118">È possibile esaminare l'utilizzo delle applicazioni connesse: ultimo visto, numero di richieste nelle ultime 24 ore e tendenze delle richieste negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="e8792-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Immagine delle app connesse](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="e8792-120">Modificare, riconfigurare o eliminare un'applicazione connessa</span><span class="sxs-lookup"><span data-stu-id="e8792-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="e8792-121">Il **collegamento Apri impostazioni applicazione** apre la pagina di gestione delle applicazioni di Azure AD corrispondente nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e8792-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="e8792-122">Dal portale di Azure, è possibile gestire le autorizzazioni, riconfigurare o eliminare le applicazioni connesse.</span><span class="sxs-lookup"><span data-stu-id="e8792-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
