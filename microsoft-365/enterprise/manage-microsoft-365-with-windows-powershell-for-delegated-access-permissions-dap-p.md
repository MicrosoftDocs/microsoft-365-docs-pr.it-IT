---
title: Gestire Microsoft 365 con Windows PowerShell per i partner di DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Il modo in cui i partner di syndication e Cloud Solution Provider (CSP) possono utilizzare Windows PowerShell per gestire i tenant dei clienti Microsoft 365.
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429879"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a>Come gestire Microsoft 365 con Windows PowerShell per i partner di autorizzazioni di accesso delegati

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

I partner di autorizzazione accesso delegato (DAP, Delegated Access Permission) sono partner di Syndication e Cloud Solution Provider (CSP). Molti sono provider di servizi di rete o di telecomunicazioni. Essi bundle Microsoft 365 abbonamenti nelle loro offerte di servizi. Quando vendono un abbonamento a Microsoft 365, vengono concesse automaticamente amministrare per conto di (AOBO) le autorizzazioni per l'locazione del cliente in modo che possano amministrare e riferire su tali locazione. Queste attività sono difficili da fare nell'interfaccia di amministrazione di Microsoft 365. L'utilizzo di PowerShell per Microsoft 365 è molto più semplice per eseguire attività amministrative quali:
- Elencare tutti i clienti **TenantIds** e i relativi domini 
- Identificare tutti gli utenti in un contratto di locazione dei clienti e le relative licenze assegnate
> [!NOTE]
> Alcune attività amministrative possono essere eseguite solo in PowerShell.

Negli articoli seguenti viene illustrato come la diffusione e i partner CSP utilizzano PowerShell per amministrare i propri clienti locazione:
  
- [Gestire i tenant Microsoft 365 con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegate Access Permissions)](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [Aggiungere un dominio a un tenancy client con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [Connettersi a PowerShell per Exchange Online](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [Recuperare i dati di report dei tenant dei clienti con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   