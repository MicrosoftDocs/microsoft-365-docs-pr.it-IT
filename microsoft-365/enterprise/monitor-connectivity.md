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
# <a name="monitor-microsoft-365-connectivity"></a>Monitorare la connettività di Microsoft 365

Dopo aver distribuito Microsoft 365, è possibile mantenere la connettività di Microsoft 365 utilizzando alcuni degli strumenti e delle tecniche seguenti. È necessario comprendere le [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) linee guida ufficiali per l'integrità e la continuità dei servizi e le procedure consigliate per l'utilizzo di [Microsoft 365 in una rete lenta.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) È anche necessario acquisire l'app di amministrazione di [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) e aggiungere un segnalibro a [Microsoft 365 per le aziende - Guida per gli amministratori.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Monitoraggio della connettività di Microsoft 365

|||
|:-----|:-----|
|**Ricevere una notifica dei nuovi endpoint di Microsoft 365** <br/> |Se si gestiscono gli endpoint di [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)è necessario ricevere notifiche quando vengono pubblicati nuovi endpoint, è possibile sottoscrivere il feed RSS utilizzando il lettore RSS preferito. Ecco come [sottoscrivere tramite Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) oppure è possibile ricevere tramite posta elettronica gli aggiornamenti [dei feed RSS.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Usare System Center per monitorare Microsoft 365** <br/> |Se si usa Microsoft System Center, è possibile scaricare [System Center Management Pack per Office 365](https://www.microsoft.com/download/details.aspx?id=43708) per iniziare a monitorare Microsoft 365 oggi stesso. Per istruzioni più dettagliate, vedere la guida operativa del Management Pack o questo blog post [Office365 Monitoring using System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Monitorare l'integrità di Azure ExpressRoute** <br/> |Se ci si connette a Microsoft 365 usando Azure ExpressRoute per Microsoft 365, è necessario assicurarsi di usare sia il dashboard di integrità dei servizi di Microsoft 365 sia il dashboard per la risoluzione dei problemi di Azure Riducendo i tempi di risoluzione dei problemi con [l'integrità](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) delle risorse di Azure <br/> |
|**Usare Azure AD Connect Health con AD FS** <br/> |Se si usa AD FS per Single Sign-On con Microsoft 365, è necessario iniziare a usare Azure AD Connect Health per monitorare [l'infrastruttura AD FS.](/azure/active-directory/hybrid/how-to-connect-health-adfs)  <br/> |
|**Monitorare a livello di programmazione Microsoft 365** <br/> |Fai riferimento alle nostre indicazioni sull'API di [gestione di Microsoft 365.](/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare i servizi e le applicazioni di Microsoft 365 Enterprise](configure-services-and-applications.md)
  
[Prepara l'organizzazione per Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](network-planning-and-performance.md)
  
[Integrazione di Microsoft 365 con ambienti locali](microsoft-365-integration.md)
  
[Gestione degli endpoint di Microsoft 365](managing-office-365-endpoints.md)