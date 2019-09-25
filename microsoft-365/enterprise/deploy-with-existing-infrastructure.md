---
title: Distribuzione di Microsoft 365 Enterprise nell'infrastruttura esistente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Andare ai criteri uscita della distribuzione di Microsoft 365 Enterprise quando si dispone di un'infrastruttura esistente.
ms.openlocfilehash: 1b464398b981133e2851760d7bfe16869f1d1429
ms.sourcegitcommit: 328b31f69663669b3c656b2e4db529f70d1c753e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "37148510"
---
# <a name="deployment-of-microsoft-365-enterprise-with-existing-infrastructure"></a><span data-ttu-id="f18d0-103">Distribuzione di Microsoft 365 Enterprise nell'infrastruttura esistente</span><span class="sxs-lookup"><span data-stu-id="f18d0-103">Deployment of Microsoft 365 Enterprise with existing infrastructure</span></span>

<span data-ttu-id="f18d0-p101">Molte organizzazioni dispongono di rete, identità e componenti esistenti oppure di prodotti Microsoft locali e servizi basati sul cloud. In questo articolo viene illustrata ogni fase della distribuzione di Microsoft 365 Enterprise affinché sia possibile determinare rapidamente come adattare o modificare l'infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="f18d0-p101">Many organizations have exisiting networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 Enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="f18d0-p102">Prima di uscire da ogni fase, è necessario esaminare i relativi criteri uscita, ovvero un insieme di condizioni necessarie che è necessario soddisfare e di condizioni facoltative da prendere in considerazione. I criteri uscita di ogni fase garantiscono che l'infrastruttura cloud e locale e la risultante configurazione end-to-end soddisfino i requisiti di una distribuzione Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f18d0-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 Enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="f18d0-p103">FastTrack è un vantaggio continuo e ripetibile, disponibile gratuitamente come parte dell'abbonamento, fornito dai tecnici Microsoft per consentire di passare al cloud secondo le proprie tempistiche. FastTrack inoltre offre l'accesso a partner qualificati per servizi aggiuntivi, in base alle proprie esigenze. Con al momento oltre 40.000 utenti abilitati, FastTrack consente di massimizzare il ROI, di accelerare la distribuzione e di aumentare l'adozione all'interno dell'organizzazione. Vedere [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span><span class="sxs-lookup"><span data-stu-id="f18d0-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="f18d0-112">Criteri uscita per la rete (fase 1)</span><span class="sxs-lookup"><span data-stu-id="f18d0-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="f18d0-113">Esaminare le seguenti condizioni obbligatorie e facoltative per l'infrastruttura di rete.</span><span class="sxs-lookup"><span data-stu-id="f18d0-113">Step through the following required and optional conditions for the networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="f18d0-114">Criteri uscita per l'identità (fase 2)</span><span class="sxs-lookup"><span data-stu-id="f18d0-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="f18d0-115">Esaminare le seguenti condizioni obbligatorie e facoltative per l'infrastruttura di gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="f18d0-115">Step through the following required and optional conditions for the identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="f18d0-116">Criteri uscita per Windows 10 Enterprise (fase 3)</span><span class="sxs-lookup"><span data-stu-id="f18d0-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="f18d0-117">Esaminare le seguenti condizioni obbligatorie e facoltative per l'infrastruttura di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f18d0-117">Step through the following required and optional conditions for the Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-office-365-proplus-phase-4"></a><span data-ttu-id="f18d0-118">Criteri uscita per Office 365 ProPlus (fase 4)</span><span class="sxs-lookup"><span data-stu-id="f18d0-118">Exit criteria for Office 365 ProPlus (phase 4)</span></span>

<span data-ttu-id="f18d0-119">Soddisfare i requisiti per la valutazione, la pianificazione della distribuzione e la distribuzione dell'infrastruttura di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="f18d0-119">Meet the requirements for assessment, deployment planning, and deployment of the Office 365 ProPlus infrastructure for Microsoft 365 Enterprise.</span></span>

[!INCLUDE [Deployment exit criteria for Office 365 ProPlus](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="f18d0-120">Criteri uscita per la gestione di dispositivi mobili (fase 5)</span><span class="sxs-lookup"><span data-stu-id="f18d0-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="f18d0-121">Soddisfare i seguenti requisiti per l'infrastruttura di gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="f18d0-121">Meet the following requirements for the mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="f18d0-122">Criteri uscita della protezione delle informazioni (fase 6)</span><span class="sxs-lookup"><span data-stu-id="f18d0-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="f18d0-123">Esaminare le seguenti condizioni obbligatorie e facoltative per l'infrastruttura di protezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="f18d0-123">Step through the following required and optional conditions for the information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

