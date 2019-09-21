---
title: Domande frequenti sull'amministrazione delegata
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: In questo argomento vengono riportate le domande frequenti per i partner e rivenditori Microsoft che vogliono eseguire attività di amministrazione delegata in Office 365, quali la possibilità di gestire Exchange Online Protection (EOP) per altri tenant (aziende).
ms.openlocfilehash: 8fcc409c9a5705ad824f7f74b3370afa07e650e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084540"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="58c4c-103">Domande frequenti sull'amministrazione delegata</span><span class="sxs-lookup"><span data-stu-id="58c4c-103">Delegated administration FAQ</span></span>

<span data-ttu-id="58c4c-104">In questo argomento vengono riportate le domande frequenti per i partner e rivenditori Microsoft che vogliono eseguire attività di amministrazione delegata in Office 365, quali la possibilità di gestire Exchange Online Protection (EOP) per altri tenant (aziende).</span><span class="sxs-lookup"><span data-stu-id="58c4c-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated Office 365 administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>
  
 <span data-ttu-id="58c4c-105">**D. Sono un rivenditore e devo gestire i tenant del mio cliente. Come posso eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="58c4c-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>
  
<span data-ttu-id="58c4c-106">R.</span><span class="sxs-lookup"><span data-stu-id="58c4c-106">A.</span></span> <span data-ttu-id="58c4c-107">Se si è un partner o rivenditore Microsoft e si è iscritti a Microsoft Advisor, è possibile richiedere l'autorizzazione per l'amministrazione del tenant all'interno dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="58c4c-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="58c4c-108">Questa operazione è nota come amministrazione delegata e consente di gestire il tenant di Office 365 (incluse le impostazioni di EOP) come se si trattasse di un amministratore all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58c4c-108">This is known as delegated administration, and it allows you to manage their Office 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="58c4c-109">Di seguito sono riportati i passaggi per l'esecuzione di un'amministrazione delegata:</span><span class="sxs-lookup"><span data-stu-id="58c4c-109">The steps for performing delegated administration are as follows:</span></span>
  
1. <span data-ttu-id="58c4c-110">Iscriviti e diventa un [consulente di Microsoft Office 365](https://aka.ms/cloudbenefits).</span><span class="sxs-lookup"><span data-stu-id="58c4c-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="58c4c-p102">Registrati per eseguire l'amministrazione delegata di Office 365. Prima di iniziare ad amministrare l'account di un cliente, il cliente stesso deve concedere al partner l'autorizzazione di amministratore delegato. Per ricevere la sua approvazione, devi innanzitutto [inviargli un'offerta per l'amministrazione delegata](https://go.microsoft.com/fwlink/?LinkId=396829). (Puoi anche offrire l'amministrazione delegata al cliente in un momento successivo.)</span><span class="sxs-lookup"><span data-stu-id="58c4c-p102">Sign up for Office 365 delegated administration. Before you can start administering a customer's account, they must authorize you as a delegated administrator. To obtain their approval, you first [send them an offer for delegated administration](https://go.microsoft.com/fwlink/?LinkId=396829). (You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="58c4c-115">Creare l'account amministratore delegato utilizzando la procedura descritta in [aggiungere o eliminare un amministratore delegato](https://go.microsoft.com/fwlink/?LinkId=396831).</span><span class="sxs-lookup"><span data-stu-id="58c4c-115">Create the delegated admin account using the steps in [Add or delete a delegated admin](https://go.microsoft.com/fwlink/?LinkId=396831).</span></span>

<span data-ttu-id="58c4c-116">Visita [Partner: Sviluppo dell'attività e amministrazione dell'account Office 365](https://go.microsoft.com/fwlink/?LinkId=301485) per ulteriori informazioni su come configurare l'amministrazione delegata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="58c4c-116">Visit [Partners: Build your business and administer your Office 365 partner account](https://go.microsoft.com/fwlink/?LinkId=301485) for more information about how to set up Office 365 delegated administration.</span></span>
  
 <span data-ttu-id="58c4c-117">**D. Sono un cliente, non un rivenditore, come posso configurare l'amministratore delegato del mio tenant secondario?**</span><span class="sxs-lookup"><span data-stu-id="58c4c-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>
  
<span data-ttu-id="58c4c-p103">R. Attualmente, l'amministrazione delegata è disponibile soltanto per rivenditori e partner. Tuttavia, forniamo un script di Windows PowerShell di esempio che ti consente di applicare criteri ai tenant secondari (aziende). Per ulteriori informazioni, vedi [Script di esempio per l'applicazione delle impostazioni EOP a più tenant](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="58c4c-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>
  
 <span data-ttu-id="58c4c-122">**D. Posso impedire all'amministratore del tenant secondario di modificare i miei criteri?**</span><span class="sxs-lookup"><span data-stu-id="58c4c-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>
  
<span data-ttu-id="58c4c-p104">R. Attualmente, questa funzionalità non è compresa in Office 365.</span><span class="sxs-lookup"><span data-stu-id="58c4c-p104">A. Office 365 does not currently have this capability.</span></span>
  
 <span data-ttu-id="58c4c-125">**D. Posso visualizzare report consolidati in tutti i miei tenant secondari?**</span><span class="sxs-lookup"><span data-stu-id="58c4c-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>
  
<span data-ttu-id="58c4c-126">R.</span><span class="sxs-lookup"><span data-stu-id="58c4c-126">A.</span></span> <span data-ttu-id="58c4c-127">La creazione di rapporti consolidati tra le società gestite non è disponibile per i report dell'interfaccia di amministrazione di Microsoft 365 in questo momento.</span><span class="sxs-lookup"><span data-stu-id="58c4c-127">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="58c4c-128">Tuttavia, è possibile eseguire questa operazione utilizzando Windows PowerShell remoto o il [servizio Web di Reporting di Office 365](https://go.microsoft.com/fwlink/?LinkId=279926).</span><span class="sxs-lookup"><span data-stu-id="58c4c-128">However, you can do this by using remote Windows PowerShell or the [Office 365 Reporting web service](https://go.microsoft.com/fwlink/?LinkId=279926).</span></span>

