---
title: Configurare le notifiche di avviso inviate a MSSP
description: Configurare le notifiche di avviso inviate a MSSP
keywords: provider di servizi di sicurezza gestiti, mssp, configurare, integrazione
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166054"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="5eee1-104">Configurare le notifiche di avviso inviate a MSSP</span><span class="sxs-lookup"><span data-stu-id="5eee1-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5eee1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5eee1-105">**Applies to:**</span></span>
- [<span data-ttu-id="5eee1-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5eee1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5eee1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5eee1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5eee1-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5eee1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5eee1-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5eee1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="5eee1-110">Questo passaggio può essere eseguito dal cliente MSSP o da MSSP.</span><span class="sxs-lookup"><span data-stu-id="5eee1-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="5eee1-111">Agli MSSP devono essere concesse le autorizzazioni appropriate per configurarlo per conto del cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="5eee1-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="5eee1-112">Dopo aver concesso l'accesso al portale, è possibile creare regole di notifica degli avvisi in modo che i messaggi di posta elettronica siano inviati agli MSSP quando vengono creati avvisi associati al tenant e vengono soddisfatte le condizioni impostate.</span><span class="sxs-lookup"><span data-stu-id="5eee1-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="5eee1-113">Per ulteriori informazioni, vedere [Creare regole per le notifiche di avviso.](configure-email-notifications.md#create-rules-for-alert-notifications)</span><span class="sxs-lookup"><span data-stu-id="5eee1-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="5eee1-114">Queste caselle di controllo devono essere selezionate:</span><span class="sxs-lookup"><span data-stu-id="5eee1-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="5eee1-115">**Includi nome organizzazione** - Il nome del cliente verrà aggiunto alle notifiche di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5eee1-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="5eee1-116">**Includi collegamento al portale specifico del tenant** - L'URL del collegamento avviso avrà un parametro specifico del tenant (tid=target_tenant_id) che consente l'accesso diretto al portale tenant di destinazione</span><span class="sxs-lookup"><span data-stu-id="5eee1-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="5eee1-117">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5eee1-117">Related topics</span></span>
- [<span data-ttu-id="5eee1-118">Concedere a MSSP l'accesso al portale</span><span class="sxs-lookup"><span data-stu-id="5eee1-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="5eee1-119">Accedere al portale clienti MSSP</span><span class="sxs-lookup"><span data-stu-id="5eee1-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="5eee1-120">Recuperare gli avvisi dal tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="5eee1-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
