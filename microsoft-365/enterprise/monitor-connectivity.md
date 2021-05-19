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
ms.openlocfilehash: dfba158085e6642856049d7894b4156f42353236
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538808"
---
# <a name="monitor-microsoft-365-connectivity"></a>Monitorare la connettività di Microsoft 365

Dopo aver distribuito la Microsoft 365, è possibile mantenere la Microsoft 365 connettività utilizzando alcuni degli strumenti e delle tecniche seguenti. È necessario comprendere le [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) linee guida ufficiali sull'integrità e la continuità dei servizi e le procedure consigliate per l'Microsoft 365 [in una rete lenta.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) Dovrai anche acquisire [l'app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) di Microsoft 365 e aggiungere un segnalibro al Microsoft 365 per le [aziende - Guida per gli amministratori.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Monitoraggio della Microsoft 365 connettività

|||
|:-----|:-----|
|**Ricevere una notifica dei nuovi endpoint Microsoft 365 di destinazione** <br/> |Se si sta gestendo [Microsoft 365 endpoint](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), è possibile ricevere notifiche quando vengono pubblicati nuovi endpoint, è possibile sottoscrivere il feed RSS utilizzando il lettore RSS preferito. Ecco come [sottoscrivere tramite Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) oppure è possibile ricevere tramite posta elettronica gli [aggiornamenti dei feed RSS.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Usare System Center per monitorare Microsoft 365** <br/> |Se si utilizza Microsoft System Center, è possibile scaricare il [Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) di System Center per Office 365 per iniziare a monitorare Microsoft 365 oggi. Per istruzioni più dettagliate, vedere la Guida operativa del Management Pack. <br/> |
|**Monitorare l'integrità di Azure ExpressRoute** <br/> |Se ci si connette a Microsoft 365 usando Azure ExpressRoute per Microsoft 365, è necessario assicurarsi di usare sia il dashboard di integrità del servizio di Microsoft 365 sia il dashboard di Azure Riducendo i tempi di risoluzione dei problemi con Integrità risorse di [Azure](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**Usare Azure AD Connect Health con AD FS** <br/> |Se si usa AD FS per single Sign-On con Microsoft 365, è necessario iniziare a usare Azure AD Connessione Health per monitorare l'infrastruttura [AD FS.](/azure/active-directory/hybrid/how-to-connect-health-adfs)  <br/> |
|**Monitorare i dati a livello di Microsoft 365** <br/> |Fai riferimento alle nostre indicazioni [sull'API Microsoft 365 Management.](/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare Microsoft 365 Enterprise e applicazioni](configure-services-and-applications.md)
  
[Prepara l'organizzazione per la Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](network-planning-and-performance.md)
  
[Microsoft 365'integrazione con ambienti locali](microsoft-365-integration.md)
  
[Gestione Microsoft 365 endpoint](managing-office-365-endpoints.md)
