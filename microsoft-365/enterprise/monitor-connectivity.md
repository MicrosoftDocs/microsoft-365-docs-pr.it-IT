---
title: Monitorare la connettività di Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: In questo articolo vengono illustrate le tecniche e gli strumenti che è possibile utilizzare per monitorare e mantenere la Microsoft 365 connettività.
ms.openlocfilehash: 8fa0820cf9b7778001be5184041e5c96930a29dd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924200"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="49075-103">Monitorare la connettività di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49075-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="49075-104">Dopo aver distribuito la Microsoft 365, è possibile mantenere la Microsoft 365 connettività utilizzando alcuni degli strumenti e delle tecniche seguenti.</span><span class="sxs-lookup"><span data-stu-id="49075-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="49075-105">È necessario comprendere le [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) linee guida ufficiali sull'integrità e la continuità dei servizi e le procedure consigliate per l'Microsoft 365 [in una rete lenta.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="49075-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="49075-106">Dovrai anche acquisire [l'app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) di Microsoft 365 e aggiungere un segnalibro al Microsoft 365 per le [aziende - Guida per gli amministratori.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="49075-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="49075-107">Monitoraggio della Microsoft 365 connettività</span><span class="sxs-lookup"><span data-stu-id="49075-107">Monitoring Microsoft 365 Connectivity</span></span>

|<span data-ttu-id="49075-108">Tipo di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="49075-108">Type of monitoring</span></span> |<span data-ttu-id="49075-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49075-109">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="49075-110">**Ricevere una notifica dei nuovi endpoint Microsoft 365 di destinazione**</span><span class="sxs-lookup"><span data-stu-id="49075-110">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="49075-111">Se si sta gestendo [Microsoft 365 endpoint](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), è possibile ricevere notifiche quando vengono pubblicati nuovi endpoint, è possibile sottoscrivere il feed RSS utilizzando il lettore RSS preferito.</span><span class="sxs-lookup"><span data-stu-id="49075-111">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="49075-112">Ecco come [sottoscrivere tramite Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) oppure è possibile ricevere tramite posta elettronica gli [aggiornamenti dei feed RSS.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="49075-112">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="49075-113">**Usare System Center per monitorare Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="49075-113">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="49075-114">Se si utilizza Microsoft System Center, è possibile scaricare il [Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) di System Center per Office 365 per iniziare a monitorare Microsoft 365 oggi.</span><span class="sxs-lookup"><span data-stu-id="49075-114">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="49075-115">Per istruzioni più dettagliate, vedere la Guida operativa del Management Pack.</span><span class="sxs-lookup"><span data-stu-id="49075-115">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="49075-116">**Monitorare l'integrità di Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="49075-116">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="49075-117">Se ci si connette a Microsoft 365 usando Azure ExpressRoute per Microsoft 365, è necessario assicurarsi di usare sia il dashboard di integrità del servizio di Microsoft 365 sia il dashboard di Azure Riducendo i tempi di risoluzione dei problemi con Integrità risorse di [Azure](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="49075-117">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="49075-118">**Usare Azure AD Connect Health con AD FS**</span><span class="sxs-lookup"><span data-stu-id="49075-118">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="49075-119">Se si usa AD FS per single Sign-On con Microsoft 365, è necessario iniziare a usare Azure AD Connessione Health per monitorare l'infrastruttura [AD FS.](/azure/active-directory/hybrid/how-to-connect-health-adfs)</span><span class="sxs-lookup"><span data-stu-id="49075-119">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="49075-120">**Monitorare i dati a livello di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="49075-120">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="49075-121">Fai riferimento alle nostre indicazioni [sull'API Microsoft 365 Management.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="49075-121">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="49075-122">Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="49075-122">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="49075-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="49075-123">Related topics</span></span>

[<span data-ttu-id="49075-124">Configurare Microsoft 365 Enterprise e applicazioni</span><span class="sxs-lookup"><span data-stu-id="49075-124">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="49075-125">Prepara l'organizzazione per la Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49075-125">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="49075-126">Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49075-126">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="49075-127">Microsoft 365'integrazione con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="49075-127">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="49075-128">Gestione Microsoft 365 endpoint</span><span class="sxs-lookup"><span data-stu-id="49075-128">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
