---
title: Preparare la distribuzione client di Office da Microsoft 365 per le aziende
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Scopri come installare automaticamente le app di Office a 32 bit nei computer Windows 10 e mantenerle aggiornate.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580055"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="3d1d9-103">Preparare la distribuzione client di Office da Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3d1d9-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="3d1d9-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="3d1d9-105">Preparare l'installazione automatica delle app di Office nei computer client</span><span class="sxs-lookup"><span data-stu-id="3d1d9-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="3d1d9-106">Puoi usare Microsoft 365 Business Premium per installare automaticamente le app di Office a 32 bit nei computer Windows 10 e mantenerle aggiornati con gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="3d1d9-107">L'installazione automatica funziona meglio se il computer dell'utente finale si trova in Windows 10 Business e:</span><span class="sxs-lookup"><span data-stu-id="3d1d9-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="3d1d9-108">Non sono installate app desktop di Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).</span><span class="sxs-lookup"><span data-stu-id="3d1d9-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="3d1d9-109">oppure</span><span class="sxs-lookup"><span data-stu-id="3d1d9-109">or</span></span>
    
- <span data-ttu-id="3d1d9-110">È installata una versione A portata di clic di Office.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="3d1d9-111">Per determinare se si ha la versione A portata di clic di Office, in un'app di Office qualsiasi scegliere **File** \> **Account** ( **Account di Office** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="3d1d9-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="3d1d9-112">Se gli aggiornamenti **di Office vengono** visualizzati come illustrato nella figura seguente, l'installazione è stata eseguita tramite A click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="3d1d9-114">**Chi trae vantaggio dall'avere questa funzionalità**</span><span class="sxs-lookup"><span data-stu-id="3d1d9-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="3d1d9-115">L'utente finale il cui PC:</span><span class="sxs-lookup"><span data-stu-id="3d1d9-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="3d1d9-116">**Ha**  una licenza utente di Windows 10 Business, una licenza attiva di Microsoft 365 per le aziende, Windows 10 Creators Update e fa parte di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="3d1d9-117">**Non dispone di app** di Office a 64 bit ,ad esempio Word, Excel, PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="3d1d9-118">Se sono necessarie app di Office a 64 bit, questa funzionalità non è adatta perché non è disponibile alcun supporto per l'attivazione di una versione a scelta a 64 bit di Office 2016 dalla console di amministrazione di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="3d1d9-119">**Non ha** app autonome della versione 2016 installate tramite Windows Installer (MSI), ad esempio Visio o Project.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="3d1d9-120">Microsoft 365 per le aziende aggiorna Office alla versione A click-to-Run di Office 2016 e non funziona con le app autonome MSI di Office 2016.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="3d1d9-121">Nella tabella seguente viene illustrata l'azione che gli utenti finali/amministratori potrebbero dover eseguire, a seconda dello stato iniziale, per avere una versione a 32 bit a 32 bit della distribuzione di Office dalla console di amministrazione di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="3d1d9-122">**Stato di installazione iniziale di Office**</span><span class="sxs-lookup"><span data-stu-id="3d1d9-122">**Starting Office install status**</span></span>|<span data-ttu-id="3d1d9-123">**Azione da eseguire prima dell'installazione di Microsoft 365 per le aziende di Office**</span><span class="sxs-lookup"><span data-stu-id="3d1d9-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="3d1d9-124">**Stato finale**</span><span class="sxs-lookup"><span data-stu-id="3d1d9-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d1d9-125">Nessuna famiglia di applicazioni Office installata</span><span class="sxs-lookup"><span data-stu-id="3d1d9-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="3d1d9-126">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d1d9-126">None</span></span>  <br/> |<span data-ttu-id="3d1d9-127">Office 2016 a 32 bit viene installato tramite A click-to-Run</span><span class="sxs-lookup"><span data-stu-id="3d1d9-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="3d1d9-128">Versione A portata di clic a 32 bit di Office esistente (2016 o precedente) e nessuna app autonoma</span><span class="sxs-lookup"><span data-stu-id="3d1d9-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="3d1d9-129">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d1d9-129">None</span></span>  <br/> |<span data-ttu-id="3d1d9-130">Aggiornamento all'ultima versione A portata di clic a 32 bit di Office 2016, in base alle necessità **\***</span><span class="sxs-lookup"><span data-stu-id="3d1d9-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="3d1d9-131">Versione a 32 bit a 32 bit esistente di Office e app di Office autonome a 32 bit o a 64 bit a a click-to-run (ad esempio, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="3d1d9-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="3d1d9-132">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d1d9-132">None</span></span>  <br/> |<span data-ttu-id="3d1d9-133">Le app autonome non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="3d1d9-134">La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="3d1d9-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="3d1d9-135">Versione A portata di clic a 32 bit di Office esistente e qualsiasi app di Office autonoma a 32 o 64 bit (tranne la versione 2016) installata tramite MSI</span><span class="sxs-lookup"><span data-stu-id="3d1d9-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="3d1d9-136">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d1d9-136">None</span></span>  <br/> |<span data-ttu-id="3d1d9-137">Le app autonome non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="3d1d9-138">La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="3d1d9-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="3d1d9-139">Qualsiasi versione A portata di clic a 64 bit di Office esistente</span><span class="sxs-lookup"><span data-stu-id="3d1d9-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="3d1d9-140">Disinstallare le app di Office a 64 bit, se è possibile sostituirle con le app di Office a 32 bit</span><span class="sxs-lookup"><span data-stu-id="3d1d9-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="3d1d9-141">Se le app di Office a 64 bit vengono rimosse, viene installata la versione A portata di clic a 32 bit di Office 2016</span><span class="sxs-lookup"><span data-stu-id="3d1d9-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="3d1d9-142">Un'installazione MSI esistente di Office 2016 con o senza app autonome</span><span class="sxs-lookup"><span data-stu-id="3d1d9-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="3d1d9-143">Disinstallare Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="3d1d9-p106">Viene installata la versione A portata di clic a 32 bit di Office 2016. Nessuna modifica alle app autonome</span><span class="sxs-lookup"><span data-stu-id="3d1d9-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="3d1d9-146">Installazione MSI esistente di Office 2013 (o versione precedente) e/o app autonome di Office</span><span class="sxs-lookup"><span data-stu-id="3d1d9-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="3d1d9-147">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d1d9-147">None</span></span>  <br/> |<span data-ttu-id="3d1d9-148">La versione A portata di clic a 32 bit di Office 2016 e l'installazione MSI di Office preesistente (e le app autonome) coesistono affiancate</span><span class="sxs-lookup"><span data-stu-id="3d1d9-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="3d1d9-149">**(\*) Nota:** l'aggiornamento alla versione A portata di clic a 32 bit di Office 2016 non viene eseguito a causa di un bug noto.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="3d1d9-150">È in corso una correzione.</span><span class="sxs-lookup"><span data-stu-id="3d1d9-150">A fix is in progress.</span></span> 
  
