---
title: Preparare la distribuzione dei client di Office da Microsoft 365 for business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Informazioni su come installare automaticamente le app di Office a 32 bit nei computer Windows 10 e mantenerle aggiornate.
ms.openlocfilehash: 6f3a80be9729a3818607c0f42e2cc7ece66a07ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401323"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="23693-103">Preparare la distribuzione dei client di Office da Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="23693-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="23693-104">Preparare l'installazione automatica delle app di Office nei computer client</span><span class="sxs-lookup"><span data-stu-id="23693-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="23693-105">È possibile utilizzare Microsoft 365 for business per installare automaticamente le app di Office a 32 bit nei computer Windows 10 e mantenerle aggiornate con gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="23693-105">You can use Microsoft 365 for business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="23693-106">L'installazione automatica funziona meglio se il computer dell'utente finale è in Windows 10 business e:</span><span class="sxs-lookup"><span data-stu-id="23693-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="23693-107">Non sono installate app desktop di Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).</span><span class="sxs-lookup"><span data-stu-id="23693-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="23693-108">oppure</span><span class="sxs-lookup"><span data-stu-id="23693-108">or</span></span>
    
- <span data-ttu-id="23693-109">È installata una versione A portata di clic di Office.</span><span class="sxs-lookup"><span data-stu-id="23693-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="23693-110">Per determinare se si ha la versione A portata di clic di Office, in un'app di Office qualsiasi scegliere **File** \> **Account** ( **Account di Office** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="23693-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="23693-111">Se si visualizzano **gli aggiornamenti di Office** , come illustrato nella figura seguente, l'installazione è stata eseguita tramite la funzione a portata di clic.</span><span class="sxs-lookup"><span data-stu-id="23693-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="23693-113">**Vantaggi dell'utilizzo di questa funzionalità**</span><span class="sxs-lookup"><span data-stu-id="23693-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="23693-114">L'utente finale il cui PC:</span><span class="sxs-lookup"><span data-stu-id="23693-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="23693-115">**Ha** una licenza per gli utenti di Windows 10 business, una licenza attiva di Microsoft 365 per le aziende, un aggiornamento di Windows 10 Creator ed è aggiunto ad Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="23693-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="23693-116">**Non dispone** di app di Office a 64 bit (ad esempio: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="23693-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="23693-117">Se sono necessarie le app di Office a 64 bit, questa funzionalità non è adatta perché non è disponibile alcun supporto per l'attivazione di una versione di Office a portata di clic a 64 bit a 2016 dalla console di amministrazione di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="23693-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="23693-118">**Non ha** app autonome della versione 2016 installate tramite Windows Installer (MSI), ad esempio Visio o Project.</span><span class="sxs-lookup"><span data-stu-id="23693-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="23693-119">Microsoft 365 for business aggiorna Office alla versione a portata di clic di Office 2016 e non funziona con le app autonome MSI di Office 2016.</span><span class="sxs-lookup"><span data-stu-id="23693-119">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="23693-120">Nella tabella seguente vengono illustrate le azioni che potrebbero essere necessarie per gli utenti finali e gli amministratori, a seconda dello stato iniziale, per avere una versione a portata di clic di 32 bit di distribuzione di Office dalla console di amministrazione di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="23693-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="23693-121">**Stato di installazione iniziale di Office**</span><span class="sxs-lookup"><span data-stu-id="23693-121">**Starting Office install status**</span></span>|<span data-ttu-id="23693-122">**Azione da eseguire prima dell'installazione di Microsoft 365 per le aziende**</span><span class="sxs-lookup"><span data-stu-id="23693-122">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="23693-123">**Stato finale**</span><span class="sxs-lookup"><span data-stu-id="23693-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23693-124">Nessuna famiglia di applicazioni Office installata</span><span class="sxs-lookup"><span data-stu-id="23693-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="23693-125">Nessuna</span><span class="sxs-lookup"><span data-stu-id="23693-125">None</span></span>  <br/> |<span data-ttu-id="23693-126">Office 2016 32 bit è installato tramite la funzione a portata di clic</span><span class="sxs-lookup"><span data-stu-id="23693-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="23693-127">Versione A portata di clic a 32 bit di Office esistente (2016 o precedente) e nessuna app autonoma</span><span class="sxs-lookup"><span data-stu-id="23693-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="23693-128">Nessuna</span><span class="sxs-lookup"><span data-stu-id="23693-128">None</span></span>  <br/> |<span data-ttu-id="23693-129">Aggiornamento all'ultima versione A portata di clic a 32 bit di Office 2016, in base alle necessità **\***</span><span class="sxs-lookup"><span data-stu-id="23693-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="23693-130">Versione a portata di clic a 32 bit di Office e a portata di clic su app di Office autonoma a 32 bit o a 64 bit (ad esempio, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="23693-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="23693-131">Nessuna</span><span class="sxs-lookup"><span data-stu-id="23693-131">None</span></span>  <br/> |<span data-ttu-id="23693-132">Le app autonome non sono intaccate.</span><span class="sxs-lookup"><span data-stu-id="23693-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="23693-133">La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="23693-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="23693-134">Versione A portata di clic a 32 bit di Office esistente e qualsiasi app di Office autonoma a 32 o 64 bit (tranne la versione 2016) installata tramite MSI</span><span class="sxs-lookup"><span data-stu-id="23693-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="23693-135">Nessuna</span><span class="sxs-lookup"><span data-stu-id="23693-135">None</span></span>  <br/> |<span data-ttu-id="23693-136">Le app autonome non sono intaccate.</span><span class="sxs-lookup"><span data-stu-id="23693-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="23693-137">La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="23693-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="23693-138">Qualsiasi versione A portata di clic a 64 bit di Office esistente</span><span class="sxs-lookup"><span data-stu-id="23693-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="23693-139">Disinstallare le app di Office a 64 bit, se è possibile sostituirle con le app di Office a 32 bit</span><span class="sxs-lookup"><span data-stu-id="23693-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="23693-140">Se le app di Office a 64 bit vengono rimosse, viene installata la versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="23693-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="23693-141">Un'installazione MSI esistente di Office 2016 con o senza app autonome</span><span class="sxs-lookup"><span data-stu-id="23693-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="23693-142">Disinstallare Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="23693-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="23693-p106">Viene installata la versione A portata di clic a 32 bit di Office 2016. Nessuna modifica alle app autonome</span><span class="sxs-lookup"><span data-stu-id="23693-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="23693-145">Installazione MSI esistente di Office 2013 (o versione precedente) e/o app autonome di Office</span><span class="sxs-lookup"><span data-stu-id="23693-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="23693-146">Nessuno</span><span class="sxs-lookup"><span data-stu-id="23693-146">None</span></span>  <br/> |<span data-ttu-id="23693-147">La versione A portata di clic a 32 bit di Office 2016 e l'installazione MSI di Office preesistente (e le app autonome) coesistono affiancate</span><span class="sxs-lookup"><span data-stu-id="23693-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="23693-148">**(\*) Nota:** l'aggiornamento alla versione A portata di clic a 32 bit di Office 2016 non viene eseguito a causa di un bug noto.</span><span class="sxs-lookup"><span data-stu-id="23693-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="23693-149">È in corso una correzione.</span><span class="sxs-lookup"><span data-stu-id="23693-149">A fix is in progress.</span></span> 
  
