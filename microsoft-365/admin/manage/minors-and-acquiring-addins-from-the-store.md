---
title: Minorenni e acquisizione di componenti aggiuntivi dallo Store
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni sui regolamenti generali sulla protezione dei dati (GDPR) che regolano i dati personali dei minorenni.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103103"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="e3bbb-103">Minorenni e acquisizione di componenti aggiuntivi dallo Store</span><span class="sxs-lookup"><span data-stu-id="e3bbb-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="e3bbb-104">Il regolamento generale sulla protezione dei dati (GDPR) è un regolamento dell'Unione europea che diventerà efficace il 25 maggio 2018.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="e3bbb-105">Attribuisce ai diritti degli utenti e alla protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="e3bbb-106">Uno degli aspetti della GDPR è che i minorenni non possono avere i dati personali inviati alle terze parti che il loro genitore o tutore non ha approvato.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="e3bbb-107">L'età specifica definita come minorenne dipende dall'area geografica in cui si trova l'individuo.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="e3bbb-108">Le regioni che dispongono di regole statutarie sul consenso dei genitori sono gli Stati Uniti, la Corea del sud, il Regno Unito e l'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="e3bbb-109">Per queste aree, un minorenne verrà bloccato (tramite Azure Active Directory) dall'acquisizione di nuovi componenti aggiuntivi di Office dall'archivio e dall'esecuzione di componenti aggiuntivi acquisiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="e3bbb-110">Per i paesi senza regole statutarie non sono previste restrizioni per il download.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="e3bbb-111">Un utente è determinato a essere un minorenne in base ai dati specificati in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="e3bbb-112">L'amministratore dell'organizzazione è responsabile della dichiarazione del gruppo di validità legale e del consenso dei genitori per tale utente.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="e3bbb-113">Se l'elemento padre/tutore acconsente a un minorenne utilizzando un componente aggiuntivo specifico, l'amministratore dell'organizzazione può utilizzare la distribuzione centralizzata per distribuire il componente aggiuntivo a tutti i minorenni che dispongono di un consenso.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="e3bbb-114">Per essere conformi a GDPR per i minorenni, è necessario assicurarsi che una delle seguenti build di Office venga distribuita nella propria scuola/organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="e3bbb-115">**Per Word, Excel, PowerPoint e Project**:</span><span class="sxs-lookup"><span data-stu-id="e3bbb-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="e3bbb-116">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="e3bbb-116">**Platform**</span></span> <br/> |<span data-ttu-id="e3bbb-117">**Numero di build**</span><span class="sxs-lookup"><span data-stu-id="e3bbb-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="e3bbb-118">Microsoft 365 Apps for Enterprise (canale corrente)</span><span class="sxs-lookup"><span data-stu-id="e3bbb-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="e3bbb-119">9001,2138</span><span class="sxs-lookup"><span data-stu-id="e3bbb-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="e3bbb-120">Microsoft 365 Apps for Enterprise (canale semestrale per l'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="e3bbb-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="e3bbb-121">8431,2159</span><span class="sxs-lookup"><span data-stu-id="e3bbb-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="e3bbb-122">Office 2016 per Windows</span><span class="sxs-lookup"><span data-stu-id="e3bbb-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="e3bbb-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="e3bbb-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="e3bbb-124">Office 2013 per Windows</span><span class="sxs-lookup"><span data-stu-id="e3bbb-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="e3bbb-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="e3bbb-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="e3bbb-126">Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="e3bbb-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="e3bbb-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="e3bbb-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="e3bbb-128">Office per il Web</span><span class="sxs-lookup"><span data-stu-id="e3bbb-128">Office for the web</span></span>  <br/> |<span data-ttu-id="e3bbb-129">N/D</span><span class="sxs-lookup"><span data-stu-id="e3bbb-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="e3bbb-130">**Per Outlook**:</span><span class="sxs-lookup"><span data-stu-id="e3bbb-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="e3bbb-131">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="e3bbb-131">**Platform**</span></span> <br/> |<span data-ttu-id="e3bbb-132">**Numero di build**</span><span class="sxs-lookup"><span data-stu-id="e3bbb-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="e3bbb-133">Outlook 2016 per Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="e3bbb-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="e3bbb-134">Build no TBD</span><span class="sxs-lookup"><span data-stu-id="e3bbb-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="e3bbb-135">Outlook 2016 per Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="e3bbb-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="e3bbb-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="e3bbb-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="e3bbb-137">Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="e3bbb-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="e3bbb-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="e3bbb-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="e3bbb-139">Outlook Mobile per iOS</span><span class="sxs-lookup"><span data-stu-id="e3bbb-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="e3bbb-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="e3bbb-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="e3bbb-141">Outlook Mobile per Android</span><span class="sxs-lookup"><span data-stu-id="e3bbb-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="e3bbb-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="e3bbb-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="e3bbb-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="e3bbb-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="e3bbb-144">N/D</span><span class="sxs-lookup"><span data-stu-id="e3bbb-144">N/A</span></span>  <br/> |

 <span data-ttu-id="e3bbb-145">**Requisiti di Office 2013**</span><span class="sxs-lookup"><span data-stu-id="e3bbb-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="e3bbb-146">Word, Excel e PowerPoint 2013 per Windows supportano gli stessi controlli secondari se è abilitata la libreria di autenticazione di Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="e3bbb-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="e3bbb-147">Sono disponibili due opzioni per la conformità, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="e3bbb-148">**Abilitare adal**.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-148">**Enable ADAL**.</span></span> <span data-ttu-id="e3bbb-149">In questo articolo viene illustrato come abilitare ADAL per Office 2013: [utilizzo dell'autenticazione moderna di Microsoft 365 con i client di Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span><span class="sxs-lookup"><span data-stu-id="e3bbb-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="e3bbb-150">È inoltre necessario impostare le chiavi del registro di sistema per abilitare ADAL come spiegato in [Enable Modern Authentication for Office 2013 on Windows Devices](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e3bbb-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="e3bbb-151">Inoltre, è necessario installare gli aggiornamenti di aprile seguenti per Office 2013:</span><span class="sxs-lookup"><span data-stu-id="e3bbb-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="e3bbb-152">Descrizione dell'aggiornamento della sicurezza per Office 2013:10 aprile 2018</span><span class="sxs-lookup"><span data-stu-id="e3bbb-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="e3bbb-153">2018 aprile 3, aggiornamento per Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="e3bbb-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="e3bbb-154">**Non abilitare adal**.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="e3bbb-155">Se non si è in grado di abilitare ADAL in Office 2013, è consigliabile utilizzare criteri di gruppo per disattivare l'archivio per i client di Office.</span><span class="sxs-lookup"><span data-stu-id="e3bbb-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="e3bbb-156">Informazioni su come disattivare l'app per le impostazioni di Office si trova [qui](https://technet.microsoft.com/library/cc178992.aspx).</span><span class="sxs-lookup"><span data-stu-id="e3bbb-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="e3bbb-157">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="e3bbb-157">Related articles</span></span>

[<span data-ttu-id="e3bbb-158">Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="e3bbb-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="e3bbb-159">Gestire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="e3bbb-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
