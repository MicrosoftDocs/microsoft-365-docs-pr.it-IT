---
title: 'Fase 1: infrastruttura di rete di Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di rete di Microsoft 365 Enterprise.
ms.openlocfilehash: 9fe7f16aef8b9c82ded2c17ce562dffb2194eaa2
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033671"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="697a1-103">Fase 1: infrastruttura di rete di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="697a1-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![Fase 1: collegamento in rete](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="697a1-105">Microsoft 365 Enterprise include Office 365, Microsoft Intune e molti servizi di identità e sicurezza di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="697a1-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="697a1-106">Tutti questi servizi basati su cloud si basano su sicurezza, prestazioni e affidabilità delle connessioni dei dispositivi client su Internet o circuiti dedicati.</span><span class="sxs-lookup"><span data-stu-id="697a1-106">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="697a1-107">Per ospitare questi servizi e renderli disponibili per i clienti in tutto il mondo, Microsoft ha progettato un'infrastruttura di rete che mette in evidenza le prestazioni e l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="697a1-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="697a1-p102">In questa fase, si esaminano le considerazioni chiave sulla creazione di una connessione ad alte prestazioni ai servizi cloud di Microsoft 365 Enterprise. Per una panoramica, vedere [Principi di rete di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="697a1-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="697a1-110">Se è stata già implementata un'infrastruttura di rete, vedere i [criteri uscita](networking-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni facoltative e obbligatorie di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="697a1-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="697a1-111">Pianificare e distribuire l'infrastruttura di rete di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="697a1-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="697a1-112">Usare la procedura seguente per creare l'infrastruttura di rete per i requisiti e le funzionalità di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="697a1-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Passaggio 1](./media/stepnumbers/Step1.png)|[<span data-ttu-id="697a1-114">Preparare la rete per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="697a1-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![Passaggio 2](./media/stepnumbers/Step2.png)|[<span data-ttu-id="697a1-116">Configurare le connessioni Internet locali per ogni sede</span><span class="sxs-lookup"><span data-stu-id="697a1-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![Passaggio 3](./media/stepnumbers/Step3.png)|[<span data-ttu-id="697a1-118">Evitare fenomeni di "hairpinning" di rete</span><span class="sxs-lookup"><span data-stu-id="697a1-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![Passaggio 4](./media/stepnumbers/Step4.png)|[<span data-ttu-id="697a1-120">Configurare il bypass di traffico</span><span class="sxs-lookup"><span data-stu-id="697a1-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![Passaggio 5](./media/stepnumbers/Step5.png)|[<span data-ttu-id="697a1-122">Ottimizzare prestazioni di client e del servizio di Office 365</span><span class="sxs-lookup"><span data-stu-id="697a1-122">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="697a1-123">Dopo aver completato questi passaggi, passare ai [criteri uscita](networking-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="697a1-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="697a1-124">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="697a1-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="697a1-125">Ulteriori informazioni su come la società [ha ottimizzato la rete Microsoft per i servizi cloud](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="697a1-125">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="697a1-126">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="697a1-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="697a1-127">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha ottimizzato i propri dispositivi di rete e le connessioni Internet](contoso-networking.md) per i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="697a1-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="697a1-129">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="697a1-129">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 1](./media/stepnumbers/Step1.png)|[<span data-ttu-id="697a1-131">Preparare la rete per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="697a1-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

