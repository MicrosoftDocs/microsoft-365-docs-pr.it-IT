---
title: Infrastruttura di base di Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere le fasi principali della distribuzione dell'infrastruttura di base per Microsoft 365 Enterprise all'interno dell'organizzazione.
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868278"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="bebea-103">Infrastruttura di base di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bebea-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="bebea-104">Per trarre vantaggi da Microsoft 365 Enterprise, iniziare la distribuzione con la sua infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="bebea-104">To fully realize the benefits of Microsoft 365 Enterprise, you’ll begin your deployment with its foundation infrastructure.</span></span> 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a><span data-ttu-id="bebea-105">Infrastruttura di base per la distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bebea-105">Foundation infrastructure for deploying Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bebea-p101">L'infrastruttura di base è la base da cui è possibile distribuire i carichi di lavoro per la produttività (come Exchange Online e Microsoft Teams in Office 365) e scenari (come una migrazione a Microsoft 365 e aggiornamenti client automatizzati). Fornisce sicurezza e integrazione intelligenti che semplificano la gestione continuativa, garantendo che il software client sia aggiornato con i miglioramenti più recenti relativi a produttività e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bebea-p101">The foundation infrastructure is the groundwork upon which you can deploy productivity workloads (such as Microsoft Teams and Exchange Online in Office 365) and scenarios (such as migrating to Microsoft 365 and automating client updates). It provides intelligent security and integration that simplifies ongoing management, which ensures that your client software is updated with the latest productivity and security enhancements.</span></span>

<span data-ttu-id="bebea-108">Per pianificare e distribuire l'infrastruttura di base di Microsoft 365 Enterprise all'interno dell'organizzazione si usano le seguenti fasi:</span><span class="sxs-lookup"><span data-stu-id="bebea-108">You'll use the following phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise in your organization:</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="bebea-109">Fase 1: rete</span><span class="sxs-lookup"><span data-stu-id="bebea-109">Phase 1: Networking</span></span>](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="bebea-110">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="bebea-110">Phase 2: Identity</span></span>](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="bebea-111">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bebea-111">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="bebea-112">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="bebea-112">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="bebea-113">Fase 5: gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="bebea-113">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="bebea-114">Fase 6: protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="bebea-114">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)|


<span data-ttu-id="bebea-p102">Prima di uscire da ogni fase, è necessario esaminare i relativi criteri uscita, ovvero un insieme di condizioni necessarie che è necessario soddisfare e di condizioni facoltative da prendere in considerazione. I criteri uscita di ogni fase garantiscono che l'infrastruttura cloud e locale e la risultante configurazione end-to-end soddisfino i requisiti di una distribuzione Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bebea-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="bebea-117">Guardare questo breve video sul funzionamento del contenuto dell'infrastruttura di base.</span><span class="sxs-lookup"><span data-stu-id="bebea-117">Watch this short video on how the foundation infrastructure content works.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="bebea-118">La figura seguente mostra l'infrastruttura di base nel contenuto della distribuzione generale di Microsoft 365 Enterprise e il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="bebea-118">The following figure shows the foundation infrastructure in the overall Microsoft 365 Enterprise deployment content and your path through it.</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a><span data-ttu-id="bebea-119">FastTrack</span><span class="sxs-lookup"><span data-stu-id="bebea-119">FastTrack</span></span>

<span data-ttu-id="bebea-p103">FastTrack è un vantaggio continuo e ripetibile, disponibile come parte dell'abbonamento, fornito dai tecnici Microsoft per consentire di passare al cloud secondo le proprie tempistiche. FastTrack inoltre offre l'accesso a partner qualificati per servizi aggiuntivi, in base alle proprie esigenze. Con al momento oltre 40.000 utenti abilitati, FastTrack consente di massimizzare il ROI, di accelerare la distribuzione e di aumentare l'adozione all'interno dell'organizzazione. Vedere [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span><span class="sxs-lookup"><span data-stu-id="bebea-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span> 

<span data-ttu-id="bebea-p104">Se si desidera sfruttare FastTrack per la distribuzione di Microsoft 365 Enterprise, è possibile usare l'[assistente distribuzione di Microsoft 365](https://aka.ms/microsoft365setupguide) di FastTrack per indicazioni su come distribuire e configurare l'infrastruttura di base. Per accedere a questa pagina è necessario essere connesso come amministratore globale in un tenant di Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bebea-p104">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="next-step"></a><span data-ttu-id="bebea-126">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bebea-126">Next step</span></span>

<span data-ttu-id="bebea-p105">Se si dispone dell'infrastruttura per Office 365, Enterprise Mobility + Security o Windows 10 Enterprise, vedere [Distribuzione di Microsoft 365 Enterprise con l'infrastruttura esistente](deploy-with-existing-infrastructure.md). In questo articolo vengono descritti i passaggi dei criteri uscita di ogni fase. Con queste informazioni, è possibile determinare più rapidamente cosa è necessario cambiare per rendere l'infrastruttura IT conforme a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bebea-p105">If you have existing infrastructure for Office 365, Enterprise Mobility + Security, or Windows 10 Enterprise, see [Deployment of Microsoft 365 Enterprise with existing infrastructure](deploy-with-existing-infrastructure.md). This article steps you through the exit criteria for each phase. With this information, you can more quickly determine what you need to change to make your IT infrastructure Microsoft 365 Enterprise-compliant.</span></span>

<span data-ttu-id="bebea-130">In caso contrario, è possibile iniziare la distribuzione end-to-end di Microsoft 365 Enterprise da [Fase 1: rete](networking-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="bebea-130">Otherwise, you can begin your Microsoft 365 Enterprise end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>