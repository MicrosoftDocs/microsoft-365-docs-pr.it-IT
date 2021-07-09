---
title: Configurare il supporto dei provider di servizi di sicurezza gestiti
description: Eseguire le operazioni necessarie per configurare l'integrazione di MSSP con Microsoft Defender for Endpoint
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
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339359"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="c2e8f-104">Configurazione integrazione con il provider di servizi di sicurezza gestita</span><span class="sxs-lookup"><span data-stu-id="c2e8f-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c2e8f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c2e8f-105">**Applies to:**</span></span>
- [<span data-ttu-id="c2e8f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c2e8f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c2e8f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2e8f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c2e8f-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c2e8f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c2e8f-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="c2e8f-110">Per abilitare l'integrazione mssp (Managed Security Service Provider) è necessario eseguire la procedura di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="c2e8f-111">In questo articolo vengono utilizzati i termini seguenti per distinguere tra il provider di servizi e l'utente del servizio:</span><span class="sxs-lookup"><span data-stu-id="c2e8f-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="c2e8f-112">MSSP: organizzazioni di sicurezza che offrono di monitorare e gestire i dispositivi di sicurezza per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="c2e8f-113">Clienti MSSP: organizzazioni che si impegnano nei servizi di MSSP.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="c2e8f-114">L'integrazione consentirà agli MSSP di eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2e8f-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="c2e8f-115">Ottenere l'accesso al portale Microsoft 365 Defender clienti MSSP</span><span class="sxs-lookup"><span data-stu-id="c2e8f-115">Get access to MSSP customer's Microsoft 365 Defender portal</span></span>
- <span data-ttu-id="c2e8f-116">Ricevere notifiche tramite posta elettronica e</span><span class="sxs-lookup"><span data-stu-id="c2e8f-116">Get email notifications, and</span></span> 
- <span data-ttu-id="c2e8f-117">Recuperare gli avvisi tramite gli strumenti di gestione degli eventi e delle informazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c2e8f-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="c2e8f-118">Prima che gli MSSP possano eseguire queste azioni, il cliente di MSSP dovrà concedere l'accesso al tenant Defender for Endpoint in modo che possa accedere al portale.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="c2e8f-119">In genere, i clienti MSSP esereranno la procedura di configurazione iniziale per concedere agli MSSP l'accesso al tenant Windows Defender Security Central.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="c2e8f-120">Dopo aver concesso l'accesso, il cliente MSSP o il provider mssp può eseguire altri passaggi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="c2e8f-121">In generale, è necessario eseguire i passaggi di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2e8f-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="c2e8f-122">**Concedere al provider mssp l'accesso Microsoft 365 Defender**</span><span class="sxs-lookup"><span data-stu-id="c2e8f-122">**Grant the MSSP access to Microsoft 365 Defender**</span></span> <br>
<span data-ttu-id="c2e8f-123">Questa azione deve essere eseguita dal cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="c2e8f-124">Concede al provider mssp l'accesso al tenant Defender for Endpoint del cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="c2e8f-125">**Configurare le notifiche di avviso inviate a MSSP**</span><span class="sxs-lookup"><span data-stu-id="c2e8f-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="c2e8f-126">Questa azione può essere eseguita dal cliente MSSP o da MSSP.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="c2e8f-127">In questo modo gli MSSP possono sapere quali avvisi devono essere indirizzati al cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="c2e8f-128">**Recuperare gli avvisi dal tenant del cliente MSSP nel sistema SIEM**</span><span class="sxs-lookup"><span data-stu-id="c2e8f-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="c2e8f-129">Questa azione viene eseguita dal provider di servizi condivisi.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="c2e8f-130">Consente agli MSSP di recuperare gli avvisi negli strumenti SIEM.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="c2e8f-131">**Recuperare gli avvisi dal tenant del cliente MSSP usando le API**</span><span class="sxs-lookup"><span data-stu-id="c2e8f-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="c2e8f-132">Questa azione viene eseguita dal provider di servizi condivisi.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="c2e8f-133">Consente agli MSSP di recuperare gli avvisi usando le API.</span><span class="sxs-lookup"><span data-stu-id="c2e8f-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="c2e8f-134">Accesso multi-tenant per mssp</span><span class="sxs-lookup"><span data-stu-id="c2e8f-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="c2e8f-135">Per informazioni su come implementare un accesso delegato multi-tenant, vedere [Accesso multi-tenant per i provider di servizi di sicurezza gestiti.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)</span><span class="sxs-lookup"><span data-stu-id="c2e8f-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="c2e8f-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c2e8f-136">Related topics</span></span>
- [<span data-ttu-id="c2e8f-137">Concedere a MSSP l'accesso al portale</span><span class="sxs-lookup"><span data-stu-id="c2e8f-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="c2e8f-138">Accedere al portale clienti MSSP</span><span class="sxs-lookup"><span data-stu-id="c2e8f-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="c2e8f-139">Configurare le notifiche di avviso</span><span class="sxs-lookup"><span data-stu-id="c2e8f-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="c2e8f-140">Recuperare gli avvisi dal tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="c2e8f-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

