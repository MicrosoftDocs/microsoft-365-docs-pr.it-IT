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
description: In questo articolo vengono illustrate le tecniche e gli strumenti che è possibile utilizzare per monitorare e gestire la connettività di Microsoft 365.
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920777"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="b272b-103">Monitorare la connettività di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b272b-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="b272b-104">Dopo aver distribuito Microsoft 365, è possibile mantenere la connettività di Microsoft 365 utilizzando alcuni degli strumenti e delle tecniche seguenti.</span><span class="sxs-lookup"><span data-stu-id="b272b-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="b272b-105">È necessario comprendere le [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) linee guida ufficiali per l'integrità e la continuità dei servizi e le procedure consigliate per l'utilizzo di [Microsoft 365 in una rete lenta.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="b272b-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="b272b-106">È anche necessario acquisire l'app di amministrazione di [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) e aggiungere un segnalibro a [Microsoft 365 per le aziende - Guida per gli amministratori.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="b272b-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="b272b-107">Monitoraggio della connettività di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b272b-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b272b-108">**Ricevere una notifica dei nuovi endpoint di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="b272b-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="b272b-109">Se si gestiscono gli endpoint di [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)è necessario ricevere notifiche quando vengono pubblicati nuovi endpoint, è possibile sottoscrivere il feed RSS utilizzando il lettore RSS preferito.</span><span class="sxs-lookup"><span data-stu-id="b272b-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="b272b-110">Ecco come [sottoscrivere tramite Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) oppure è possibile ricevere tramite posta elettronica gli aggiornamenti [dei feed RSS.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="b272b-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="b272b-111">**Usare System Center per monitorare Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="b272b-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="b272b-112">Se si usa Microsoft System Center, è possibile scaricare [System Center Management Pack per Office 365](https://www.microsoft.com/download/details.aspx?id=43708) per iniziare a monitorare Microsoft 365 oggi stesso.</span><span class="sxs-lookup"><span data-stu-id="b272b-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="b272b-113">Per istruzioni più dettagliate, vedere la guida operativa del Management Pack o questo blog post [Office365 Monitoring using System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="b272b-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="b272b-114">**Monitorare l'integrità di Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="b272b-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="b272b-115">Se ci si connette a Microsoft 365 usando Azure ExpressRoute per Microsoft 365, è necessario assicurarsi di usare sia il dashboard di integrità dei servizi di Microsoft 365 sia il dashboard per la risoluzione dei problemi di Azure Riducendo i tempi di risoluzione dei problemi con [l'integrità](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) delle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="b272b-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="b272b-116">**Usare Azure AD Connect Health con AD FS**</span><span class="sxs-lookup"><span data-stu-id="b272b-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="b272b-117">Se si usa AD FS per Single Sign-On con Microsoft 365, è necessario iniziare a usare Azure AD Connect Health per monitorare [l'infrastruttura AD FS.](/azure/active-directory/hybrid/how-to-connect-health-adfs)</span><span class="sxs-lookup"><span data-stu-id="b272b-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="b272b-118">**Monitorare a livello di programmazione Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="b272b-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="b272b-119">Fai riferimento alle nostre indicazioni sull'API di [gestione di Microsoft 365.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="b272b-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="b272b-120">Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="b272b-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b272b-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b272b-121">Related topics</span></span>

[<span data-ttu-id="b272b-122">Configurare i servizi e le applicazioni di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b272b-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="b272b-123">Prepara l'organizzazione per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b272b-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="b272b-124">Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b272b-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="b272b-125">Integrazione di Microsoft 365 con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="b272b-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="b272b-126">Gestione degli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b272b-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)