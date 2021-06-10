---
title: Minori e acquisizione di componenti aggiuntivi dallo Store
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Informazioni sulle normative del Regolamento generale sulla protezione dei dati (GDPR) che regolano i dati personali dei minori.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580919"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="aba0e-103">Minori e acquisizione di componenti aggiuntivi dallo Store</span><span class="sxs-lookup"><span data-stu-id="aba0e-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="aba0e-104">Il Regolamento generale sulla protezione dei dati (GDPR) è un regolamento dell'Unione Europea che diventa effettivo il 25 maggio 2018.</span><span class="sxs-lookup"><span data-stu-id="aba0e-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="aba0e-105">Concede agli utenti i diritti e la protezione dei propri dati.</span><span class="sxs-lookup"><span data-stu-id="aba0e-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="aba0e-106">Uno degli aspetti del GDPR è che i minori non possono avere i propri dati personali inviati a parti che il genitore o il tutore non hanno approvato.</span><span class="sxs-lookup"><span data-stu-id="aba0e-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="aba0e-107">L'età specifica definita come minore dipende dall'area geografica in cui si trova l'individuo.</span><span class="sxs-lookup"><span data-stu-id="aba0e-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="aba0e-108">Le regioni che dispongono di normative legali sul consenso dei genitori includono Stati Uniti, Corea del Sud, Regno Unito e Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="aba0e-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="aba0e-109">Per tali aree geografiche, un componente aggiuntivo secondario verrà impedito (tramite Azure Active Directory) di ottenere eventuali nuovi componenti aggiuntivi Office dallo Store ed eseguire i componenti aggiuntivi acquisiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="aba0e-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="aba0e-110">Per i paesi senza normative di legge, non ci saranno restrizioni per il download.</span><span class="sxs-lookup"><span data-stu-id="aba0e-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="aba0e-111">Un utente viene determinato come secondario in base ai dati specificati in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aba0e-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="aba0e-112">L'amministratore dell'organizzazione è responsabile della dichiarazione del gruppo di età legale e del consenso dei genitori per tale utente.</span><span class="sxs-lookup"><span data-stu-id="aba0e-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="aba0e-113">Se il genitore/tutore acconsente a un minore usando un componente aggiuntivo specifico, l'amministratore dell'organizzazione può usare la distribuzione centralizzata per distribuire il componente aggiuntivo a tutti i minori che hanno il consenso.</span><span class="sxs-lookup"><span data-stu-id="aba0e-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="aba0e-114">Per essere conformi al GDPR per i minori, devi assicurarti che una delle build seguenti di Office sia distribuita nella tua scuola/organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aba0e-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="aba0e-115">**Per Word, Excel, PowerPoint e Project**:</span><span class="sxs-lookup"><span data-stu-id="aba0e-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="aba0e-116">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="aba0e-116">**Platform**</span></span> <br/> |<span data-ttu-id="aba0e-117">**Numero di build**</span><span class="sxs-lookup"><span data-stu-id="aba0e-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="aba0e-118">Microsoft 365 Apps for enterprise (Canale corrente)</span><span class="sxs-lookup"><span data-stu-id="aba0e-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="aba0e-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="aba0e-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="aba0e-120">Microsoft 365 Apps for enterprise (Canale semestra Enterprise)</span><span class="sxs-lookup"><span data-stu-id="aba0e-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="aba0e-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="aba0e-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="aba0e-122">Office 2016 per Windows</span><span class="sxs-lookup"><span data-stu-id="aba0e-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="aba0e-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="aba0e-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="aba0e-124">Office 2013 per Windows</span><span class="sxs-lookup"><span data-stu-id="aba0e-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="aba0e-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="aba0e-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="aba0e-126">Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="aba0e-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="aba0e-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="aba0e-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="aba0e-128">Office per il web</span><span class="sxs-lookup"><span data-stu-id="aba0e-128">Office for the web</span></span>  <br/> |<span data-ttu-id="aba0e-129">N/D</span><span class="sxs-lookup"><span data-stu-id="aba0e-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="aba0e-130">**Per Outlook**:</span><span class="sxs-lookup"><span data-stu-id="aba0e-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="aba0e-131">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="aba0e-131">**Platform**</span></span> <br/> |<span data-ttu-id="aba0e-132">**Numero di build**</span><span class="sxs-lookup"><span data-stu-id="aba0e-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="aba0e-133">Outlook 2016 per Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="aba0e-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="aba0e-134">Build No TBD</span><span class="sxs-lookup"><span data-stu-id="aba0e-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="aba0e-135">Outlook 2016 per Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="aba0e-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="aba0e-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="aba0e-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="aba0e-137">Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="aba0e-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="aba0e-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="aba0e-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="aba0e-139">Outlook mobile per iOS</span><span class="sxs-lookup"><span data-stu-id="aba0e-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="aba0e-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="aba0e-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="aba0e-141">Outlook mobile per Android</span><span class="sxs-lookup"><span data-stu-id="aba0e-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="aba0e-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="aba0e-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="aba0e-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="aba0e-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="aba0e-144">N/D</span><span class="sxs-lookup"><span data-stu-id="aba0e-144">N/A</span></span>  <br/> |

 <span data-ttu-id="aba0e-145">**Office 2013**</span><span class="sxs-lookup"><span data-stu-id="aba0e-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="aba0e-146">Word, Excel e PowerPoint 2013 per Windows supporteranno gli stessi controlli minori se è abilitata la libreria di autenticazione di Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="aba0e-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="aba0e-147">Esistono due opzioni per la conformità, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="aba0e-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="aba0e-148">**Abilita ADAL**.</span><span class="sxs-lookup"><span data-stu-id="aba0e-148">**Enable ADAL**.</span></span> <span data-ttu-id="aba0e-149">In questo articolo viene illustrato come abilitare ADAL per Office 2013: [Utilizzo Microsoft 365'autenticazione](../../enterprise/modern-auth-for-office-2013-and-2016.md)moderna con Office client .</span><span class="sxs-lookup"><span data-stu-id="aba0e-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="aba0e-150">È inoltre necessario impostare le chiavi del Registro di sistema per abilitare ADAL, come illustrato in [Enable Modern Authentication for Office 2013 in Windows devices](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="aba0e-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="aba0e-151">Inoltre, è necessario installare i seguenti aggiornamenti di aprile per Office 2013:</span><span class="sxs-lookup"><span data-stu-id="aba0e-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="aba0e-152">Descrizione dell'aggiornamento della sicurezza Office 2013: 10 aprile 2018</span><span class="sxs-lookup"><span data-stu-id="aba0e-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="aba0e-153">Aggiornamento del 3 aprile 2018 per Office 2013 (KB40183333)</span><span class="sxs-lookup"><span data-stu-id="aba0e-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="aba0e-154">**Non abilitare ADAL**.</span><span class="sxs-lookup"><span data-stu-id="aba0e-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="aba0e-155">Se non è possibile abilitare ADAL in Office 2013, è consigliabile usare Criteri di gruppo per disattivare lo Store per i Office client.</span><span class="sxs-lookup"><span data-stu-id="aba0e-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="aba0e-156">Le informazioni su come disattivare l'app per Office impostazioni sono disponibili [qui.](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="aba0e-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="aba0e-157">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="aba0e-157">Related articles</span></span>

[<span data-ttu-id="aba0e-158">Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="aba0e-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="aba0e-159">Gestire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="aba0e-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
