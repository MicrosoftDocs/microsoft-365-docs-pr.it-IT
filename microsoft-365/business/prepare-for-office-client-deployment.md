---
title: Preparare la distribuzione client di Office per Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Informazioni su come installare le applicazioni di Office a 32 bit nei computer Windows 10 e mantenerle aggiornate automaticamente.
ms.openlocfilehash: 16a8230d60157f1c6731ac639d89533b05aa3afe
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868276"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="5d37c-103">Preparare la distribuzione client di Office per Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="5d37c-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="5d37c-104">Preparare l'installazione automatica delle app di Office nei computer client</span><span class="sxs-lookup"><span data-stu-id="5d37c-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="5d37c-105">È possibile usare Microsoft 365 Business per installare automaticamente le app di Office a 32 bit in computer Windows 10 e mantenerle aggiornate.</span><span class="sxs-lookup"><span data-stu-id="5d37c-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="5d37c-106">Questa procedura funziona al meglio se nel computer dell'utente finale è installato Windows 10 Business e:</span><span class="sxs-lookup"><span data-stu-id="5d37c-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="5d37c-107">Non sono installate app desktop di Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).</span><span class="sxs-lookup"><span data-stu-id="5d37c-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="5d37c-108">oppure</span><span class="sxs-lookup"><span data-stu-id="5d37c-108">or</span></span>
    
- <span data-ttu-id="5d37c-109">È installata una versione A portata di clic di Office.</span><span class="sxs-lookup"><span data-stu-id="5d37c-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="5d37c-p101">Per determinare se si ha la versione A portata di clic di Office, in un'app di Office qualsiasi scegliere **File** \> **Account** ( **Account di Office** in Outlook). Se la sezione Aggiornamenti di Office ha lo stesso aspetto della figura seguente, significa che l'installazione è stata eseguita tramite A portata di clic.</span><span class="sxs-lookup"><span data-stu-id="5d37c-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="5d37c-113">**Chi trarrà vantaggio da questa caratteristica**</span><span class="sxs-lookup"><span data-stu-id="5d37c-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="5d37c-114">L'utente finale il cui PC:</span><span class="sxs-lookup"><span data-stu-id="5d37c-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="5d37c-115">**Ha** una licenza utente di Windows 10 Business, una licenza attiva di Microsoft 365 Business, Windows 10 Creators Update e fa parte di un dominio Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d37c-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="5d37c-p102">**Non ha** le app di Office a 64 bit (ad esempio Word, Excel, Powerpoint). Se le app di Office a 64 bit sono necessarie, questa caratteristica non è ideale perché non è offerto alcun supporto per l'attivazione di una versione A portata di clic di Office 2016 a 64 bit dalla console di amministrazione di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="5d37c-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="5d37c-p103">**Non ha** app autonome della versione 2016 installate tramite Windows Installer (MSI), ad esempio Visio o Project. Microsoft 365 Business aggiorna Office alla versione A portata di clic di Office 2016, che non funziona con queste app autonome.</span><span class="sxs-lookup"><span data-stu-id="5d37c-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="5d37c-120">La tabella seguente descrive nel dettaglio le azione che gli utenti finali/amministratori potrebbero dover eseguire, a seconda dello stato iniziale, per distribuire correttamente la versione A portata di clic di Office a 32 bit dalla console di amministrazione di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="5d37c-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="5d37c-121">**Stato di installazione iniziale di Office**</span><span class="sxs-lookup"><span data-stu-id="5d37c-121">**Starting Office install status**</span></span>|<span data-ttu-id="5d37c-122">**Azione da eseguire prima di installare Office di Microsoft 365 Business**</span><span class="sxs-lookup"><span data-stu-id="5d37c-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="5d37c-123">**Stato finale**</span><span class="sxs-lookup"><span data-stu-id="5d37c-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d37c-124">Nessuna famiglia di applicazioni Office installata</span><span class="sxs-lookup"><span data-stu-id="5d37c-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="5d37c-125">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5d37c-125">None</span></span>  <br/> |<span data-ttu-id="5d37c-126">Office 2016 a 32 bit è installato con A portata di clic</span><span class="sxs-lookup"><span data-stu-id="5d37c-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="5d37c-127">Versione A portata di clic a 32 bit di Office esistente (2016 o precedente) e nessuna app autonoma</span><span class="sxs-lookup"><span data-stu-id="5d37c-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="5d37c-128">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5d37c-128">None</span></span>  <br/> |<span data-ttu-id="5d37c-129">Aggiornamento all'ultima versione A portata di clic a 32 bit di Office 2016, in base alle necessità **\***</span><span class="sxs-lookup"><span data-stu-id="5d37c-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="5d37c-130">Versione A portata di clic a 32 bit di Office esistente e app di Office autonome A portata di clic a 32 o 64 bit (ad esempio Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="5d37c-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="5d37c-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5d37c-131">None</span></span>  <br/> |<span data-ttu-id="5d37c-p104">Le app autonome non vengono interessate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="5d37c-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="5d37c-134">Versione A portata di clic a 32 bit di Office esistente e qualsiasi app di Office autonoma a 32 o 64 bit (tranne la versione 2016) installata tramite MSI</span><span class="sxs-lookup"><span data-stu-id="5d37c-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="5d37c-135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5d37c-135">None</span></span>  <br/> |<span data-ttu-id="5d37c-p105">Le app autonome non vengono interessate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="5d37c-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="5d37c-138">Qualsiasi versione A portata di clic a 64 bit di Office esistente</span><span class="sxs-lookup"><span data-stu-id="5d37c-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="5d37c-139">Disinstallare le app di Office a 64 bit, se è possibile sostituirle con le app di Office a 32 bit</span><span class="sxs-lookup"><span data-stu-id="5d37c-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="5d37c-140">Se le app di Office a 64 bit vengono rimosse, viene installata la versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="5d37c-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="5d37c-141">Un'installazione MSI esistente di Office 2016 con o senza app autonome</span><span class="sxs-lookup"><span data-stu-id="5d37c-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="5d37c-142">Disinstallare Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="5d37c-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="5d37c-p106">Viene installata la versione A portata di clic a 32 bit di Office 2016. Nessuna modifica alle app autonome</span><span class="sxs-lookup"><span data-stu-id="5d37c-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="5d37c-145">Installazione MSI esistente di Office 2013 (o versione precedente) e/o app autonome di Office</span><span class="sxs-lookup"><span data-stu-id="5d37c-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="5d37c-146">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5d37c-146">None</span></span>  <br/> |<span data-ttu-id="5d37c-147">La versione A portata di clic a 32 bit di Office 2016 e l'installazione MSI di Office preesistente (e le app autonome) coesistono affiancate</span><span class="sxs-lookup"><span data-stu-id="5d37c-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="5d37c-p107">**(\*) Nota:** l'aggiornamento alla versione A portata di clic a 32 bit di Office 2016 non viene eseguito a causa di un bug noto. Una correzione è in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="5d37c-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


