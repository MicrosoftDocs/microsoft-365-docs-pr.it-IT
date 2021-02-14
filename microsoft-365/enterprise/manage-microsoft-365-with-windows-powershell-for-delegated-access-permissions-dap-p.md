---
title: Gestire Microsoft 365 con Windows PowerShell partner DAP
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
description: In che modo i partner Syndication e Cloud Solution Provider (CSP) possono usare Windows PowerShell per gestire i tenant dei clienti di Microsoft 365.
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429879"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="9f045-103">Come gestire Microsoft 365 con Windows PowerShell per i partner con autorizzazioni di accesso delegato</span><span class="sxs-lookup"><span data-stu-id="9f045-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="9f045-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="9f045-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9f045-105">I partner di autorizzazione accesso delegato (DAP, Delegated Access Permission) sono partner di Syndication e Cloud Solution Provider (CSP).</span><span class="sxs-lookup"><span data-stu-id="9f045-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="9f045-106">Molti sono provider di rete o telecomunicazioni.</span><span class="sxs-lookup"><span data-stu-id="9f045-106">Many are network or telecom providers.</span></span> <span data-ttu-id="9f045-107">Aggregano le sottoscrizioni di Microsoft 365 nelle offerte di servizi.</span><span class="sxs-lookup"><span data-stu-id="9f045-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="9f045-108">Quando vendono una sottoscrizione a Microsoft 365, gli vengono automaticamente concesse le autorizzazioni Amministra per conto di (AOBO) per i tenaci del cliente in modo che possano amministrare e creare report su tali tenaci.</span><span class="sxs-lookup"><span data-stu-id="9f045-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="9f045-109">Queste attività sono difficili da eseguire nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f045-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9f045-110">È molto più facile usare PowerShell per Microsoft 365 per eseguire attività amministrative, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9f045-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="9f045-111">Elencare tutti i **TenantId dei clienti** e i relativi domini</span><span class="sxs-lookup"><span data-stu-id="9f045-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="9f045-112">Identificare tutti gli utenti in un tenancy del cliente e le relative licenze assegnate</span><span class="sxs-lookup"><span data-stu-id="9f045-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="9f045-113">Alcune attività amministrative possono essere eseguite solo in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f045-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="9f045-114">Gli articoli seguenti mostrano in che modo i partner syndication e CSP usano PowerShell per amministrare i tenaci dei clienti:</span><span class="sxs-lookup"><span data-stu-id="9f045-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="9f045-115">Gestire i tenant di Microsoft 365 con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permissions)</span><span class="sxs-lookup"><span data-stu-id="9f045-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="9f045-116">Aggiungere un dominio a un tenancy client con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)</span><span class="sxs-lookup"><span data-stu-id="9f045-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="9f045-117">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9f045-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="9f045-118">Recuperare i dati di report dei tenant dei clienti con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)</span><span class="sxs-lookup"><span data-stu-id="9f045-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   