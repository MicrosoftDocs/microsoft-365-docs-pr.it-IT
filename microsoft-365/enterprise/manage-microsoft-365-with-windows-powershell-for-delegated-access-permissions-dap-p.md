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
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="e637c-103">Come gestire Microsoft 365 con Windows PowerShell per i partner di autorizzazioni di accesso delegati</span><span class="sxs-lookup"><span data-stu-id="e637c-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="e637c-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e637c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e637c-105">I partner di autorizzazione accesso delegato (DAP, Delegated Access Permission) sono partner di Syndication e Cloud Solution Provider (CSP).</span><span class="sxs-lookup"><span data-stu-id="e637c-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="e637c-106">Molti sono provider di servizi di rete o di telecomunicazioni.</span><span class="sxs-lookup"><span data-stu-id="e637c-106">Many are network or telecom providers.</span></span> <span data-ttu-id="e637c-107">Essi bundle Microsoft 365 abbonamenti nelle loro offerte di servizi.</span><span class="sxs-lookup"><span data-stu-id="e637c-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="e637c-108">Quando vendono un abbonamento a Microsoft 365, vengono concesse automaticamente amministrare per conto di (AOBO) le autorizzazioni per l'locazione del cliente in modo che possano amministrare e riferire su tali locazione.</span><span class="sxs-lookup"><span data-stu-id="e637c-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="e637c-109">Queste attività sono difficili da fare nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e637c-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e637c-110">L'utilizzo di PowerShell per Microsoft 365 è molto più semplice per eseguire attività amministrative quali:</span><span class="sxs-lookup"><span data-stu-id="e637c-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="e637c-111">Elencare tutti i clienti **TenantIds** e i relativi domini</span><span class="sxs-lookup"><span data-stu-id="e637c-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="e637c-112">Identificare tutti gli utenti in un contratto di locazione dei clienti e le relative licenze assegnate</span><span class="sxs-lookup"><span data-stu-id="e637c-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="e637c-113">Alcune attività amministrative possono essere eseguite solo in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e637c-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="e637c-114">Negli articoli seguenti viene illustrato come la diffusione e i partner CSP utilizzano PowerShell per amministrare i propri clienti locazione:</span><span class="sxs-lookup"><span data-stu-id="e637c-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="e637c-115">Gestire i tenant Microsoft 365 con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegate Access Permissions)</span><span class="sxs-lookup"><span data-stu-id="e637c-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="e637c-116">Aggiungere un dominio a un tenancy client con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)</span><span class="sxs-lookup"><span data-stu-id="e637c-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="e637c-117">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e637c-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="e637c-118">Recuperare i dati di report dei tenant dei clienti con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)</span><span class="sxs-lookup"><span data-stu-id="e637c-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   