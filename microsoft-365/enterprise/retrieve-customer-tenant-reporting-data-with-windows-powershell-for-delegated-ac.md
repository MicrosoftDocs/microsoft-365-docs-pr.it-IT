---
title: Recuperare i dati di report del tenant dei clienti con Windows PowerShell per i partner DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Riepilogo: Usare Windows PowerShell remoto di Microsoft Exchange Online per recuperare i report dei tenant di un singolo cliente.'
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927217"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="b8023-103">Recuperare i dati di report dei tenant dei clienti con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)</span><span class="sxs-lookup"><span data-stu-id="b8023-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="b8023-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b8023-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b8023-105">Usare le Windows PowerShell remote per Microsoft Exchange Online per recuperare i report dai tenant dei singoli clienti.</span><span class="sxs-lookup"><span data-stu-id="b8023-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>
  
<span data-ttu-id="b8023-106">I partner syndication e Cloud Solution Provider (CSP) possono accedere ai dati che costituisce i report dei tenant dei clienti direttamente tramite Windows PowerShell per PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b8023-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="b8023-107">Ciò consente ai partner di raccogliere e salvare i dati di report, per poi eseguire operazioni su di essi.</span><span class="sxs-lookup"><span data-stu-id="b8023-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="b8023-108">Dopo avere aperto una connessione remota, il recupero dei dati di report relativi al tenancy di un cliente è identico all'esecuzione di qualsiasi cmdlet per il tenancy di un cliente.</span><span class="sxs-lookup"><span data-stu-id="b8023-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>
  
<span data-ttu-id="b8023-109">In questo articolo viene utilizzato il servizio Windows PowerShell per Exchange Online per connettersi a una tenancy di un singolo cliente e recuperare un report.</span><span class="sxs-lookup"><span data-stu-id="b8023-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="b8023-110">Per impostazione predefinita, Windows PowerShell non supporta l'aggregazione dei dati di report dai tenancy di più clienti.</span><span class="sxs-lookup"><span data-stu-id="b8023-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="b8023-111">I report recuperati con questa procedura sono solo per il  _DelegatedOrg_ al quale ci si connette.</span><span class="sxs-lookup"><span data-stu-id="b8023-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>
  
 
## <a name="before-you-begin"></a><span data-ttu-id="b8023-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b8023-112">Before you begin</span></span>

- <span data-ttu-id="b8023-p103">È necessario connettersi al tenant Exchange Online tramite Windows PowerShell remoto. Per istruzioni, vedere [Connettersi ai tenant Exchange Online con Windows PowerShell remoto per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b8023-p103">You need to connect to your Exchange Online tenant by using remote Windows PowerShell. For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>
    
## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="b8023-115">Eseguire il cmdlet di esempio Get-StaleMailboxReport</span><span class="sxs-lookup"><span data-stu-id="b8023-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="b8023-116">Dopo avere aperto una sessione remota in Exchange Online, eseguire questo comando per recuperare il cmdlet **Get-StaleMailboxReport** per l'intervallo di date compreso tra il 25/03/2015 e il 31/03/2015.</span><span class="sxs-lookup"><span data-stu-id="b8023-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="b8023-p104">Sono disponibili molti altri cmdlet di report per Exchange Online, Lync Online e SharePoint Online, e altri per il controllo dei messaggi. Per ulteriori informazioni sui cmdlet di report disponibili e sul servizio Web per la creazione di report di Office 365, vedere gli argomenti riportati nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="b8023-p104">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use. To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b8023-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8023-119">See also</span></span>

#### 

<span data-ttu-id="b8023-120">[Servizio Web per la creazione di report di Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="b8023-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>
  
[<span data-ttu-id="b8023-121">Cmdlet per la creazione di report in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b8023-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[<span data-ttu-id="b8023-122">Guida per partner</span><span class="sxs-lookup"><span data-stu-id="b8023-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)