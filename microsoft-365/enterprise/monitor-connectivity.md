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
description: In questo articolo vengono fornite informazioni sugli strumenti e sulle tecniche che è possibile utilizzare per monitorare e gestire la connettività Microsoft 365.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690970"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="16de4-103">Monitorare la connettività di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16de4-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="16de4-104">Dopo aver distribuito Microsoft 365, è possibile mantenere la connettività Microsoft 365 utilizzando alcuni degli strumenti e delle tecniche seguenti.</span><span class="sxs-lookup"><span data-stu-id="16de4-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="16de4-105">È consigliabile comprendere le linee guida per l' [integrità e la continuità dei servizi](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) ufficiali, nonché le [procedure consigliate per l'utilizzo di Microsoft 365 su una rete lenta](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span><span class="sxs-lookup"><span data-stu-id="16de4-105">You'll want to understand the official [Service Health and Continuity](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="16de4-106">Si vorrà anche prendere l' [app microsoft 365 admin](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) e aggiungere un segnalibro a [Microsoft 365 for Business-Guida per gli amministratori](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span><span class="sxs-lookup"><span data-stu-id="16de4-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="16de4-107">Monitoraggio della connettività di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16de4-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="16de4-108">**Ottenere la notifica dei nuovi endpoint di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="16de4-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="16de4-109">Se si [gestiscono gli endpoint di Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), è necessario ricevere notifiche quando si pubblicano nuovi endpoint, è possibile sottoscrivere un feed RSS usando il lettore RSS preferito.</span><span class="sxs-lookup"><span data-stu-id="16de4-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="16de4-110">Ecco come effettuare la [sottoscrizione tramite Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) oppure è possibile che [gli aggiornamenti del feed RSS vengano inviati tramite posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span><span class="sxs-lookup"><span data-stu-id="16de4-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="16de4-111">**Utilizzare System Center per monitorare Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="16de4-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="16de4-112">Se si utilizza Microsoft System Center, è possibile scaricare [System Center Management Pack per Office 365](https://www.microsoft.com/download/details.aspx?id=43708) per avviare il monitoraggio di Microsoft 365 oggi.</span><span class="sxs-lookup"><span data-stu-id="16de4-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="16de4-113">Per informazioni più dettagliate, vedere la Guida alle operazioni del Management Pack o questo post di Blog sul [monitoraggio di Office365 tramite System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="16de4-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="16de4-114">**Monitorare l'integrità di Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="16de4-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="16de4-115">Se si sta effettuando la connessione a Microsoft 365 utilizzando Azure ExpressRoute per Microsoft 365, è necessario assicurarsi di utilizzare sia il dashboard di integrità del servizio Microsoft 365 che la riduzione del [tempo di risoluzione dei problemi con Azure Resource Health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="16de4-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="16de4-116">**Usare Azure AD Connect Health con AD FS**</span><span class="sxs-lookup"><span data-stu-id="16de4-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="16de4-117">Se si usa AD FS per Single Sign-on con Microsoft 365, si vorrà iniziare a [usare Azure ad Connect Health per monitorare l'infrastruttura ad FS](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span><span class="sxs-lookup"><span data-stu-id="16de4-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span></span>  <br/> |
|<span data-ttu-id="16de4-118">**Monitorare a livello di programmazione Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="16de4-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="16de4-119">Fare riferimento alle indicazioni sull' [API di gestione Microsoft 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="16de4-119">Refer to our guidance on the [Microsoft 365 Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="16de4-120">Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span><span class="sxs-lookup"><span data-stu-id="16de4-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="16de4-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="16de4-121">Related topics</span></span>

[<span data-ttu-id="16de4-122">Configurare le applicazioni e i servizi Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="16de4-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="16de4-123">Preparare la propria organizzazione per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="16de4-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="16de4-124">Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16de4-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="16de4-125">Integrazione di Microsoft 365 con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="16de4-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="16de4-126">Gestione degli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16de4-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
