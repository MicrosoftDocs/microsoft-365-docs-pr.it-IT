---
title: Sottoscrizioni, licenze, account e tenant per offerte cloud di Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/25/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Comprendere le relazioni delle organizzazioni, le sottoscrizioni, le licenze, gli account utente e i tenant tra le offerte cloud di Microsoft.
ms.openlocfilehash: 7b19c2d6a870f53642d37ee98276f7b6a9e1febf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691071"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a><span data-ttu-id="cb235-103">Sottoscrizioni, licenze, account e tenant per offerte cloud di Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb235-103">Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings</span></span>

<span data-ttu-id="cb235-104">Microsoft fornisce una gerarchia di organizzazioni, sottoscrizioni, licenze e account utente per garantire un utilizzo uniforme di identità e fatturazione tra le varie offerte cloud:</span><span class="sxs-lookup"><span data-stu-id="cb235-104">Microsoft provides a hierarchy of organizations, subscriptions, licenses, and user accounts for consistent use of identities and billing across its cloud offerings:</span></span>
  
- <span data-ttu-id="cb235-105">Microsoft 365 e Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="cb235-105">Microsoft 365 and Microsoft Office 365</span></span>
- <span data-ttu-id="cb235-106">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="cb235-106">Microsoft Azure</span></span>
- <span data-ttu-id="cb235-107">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="cb235-107">Microsoft Dynamics 365</span></span>

## <a name="elements-of-the-hierarchy"></a><span data-ttu-id="cb235-108">Elementi della gerarchia</span><span class="sxs-lookup"><span data-stu-id="cb235-108">Elements of the hierarchy</span></span>

<span data-ttu-id="cb235-109">Di seguito sono riportati gli elementi della gerarchia:</span><span class="sxs-lookup"><span data-stu-id="cb235-109">Here are the elements of the hierarchy:</span></span>
  
### <a name="organization"></a><span data-ttu-id="cb235-110">Organizzazione</span><span class="sxs-lookup"><span data-stu-id="cb235-110">Organization</span></span>

<span data-ttu-id="cb235-p101">Un'organizzazione rappresenta un'entità aziendale che utilizza le offerte cloud di Microsoft, in genere identificate da uno o più nomi di dominio Domain Name System (DNS), ad esempio contoso.com. L'organizzazione è un contenitore per le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="cb235-p101">An organization represents a business entity that is using Microsoft cloud offerings, typically identified by one or more public Domain Name System (DNS) domain names, such as contoso.com. The organization is a container for subscriptions.</span></span>
  
### <a name="subscriptions"></a><span data-ttu-id="cb235-113">Sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="cb235-113">Subscriptions</span></span>

<span data-ttu-id="cb235-114">Una sottoscrizione è un contratto stipulato con Microsoft per utilizzare uno o più piattaforme cloud oppure servizi di Microsoft pagando un costo stabilito su licenza utente o su consumo delle risorse cloud.</span><span class="sxs-lookup"><span data-stu-id="cb235-114">A subscription is an agreement with Microsoft to use one or more Microsoft cloud platforms or services, for which charges accrue based on either a per-user license fee or on cloud-based resource consumption.</span></span> 

- <span data-ttu-id="cb235-115">Le offerte cloud SaaS di Microsoft (Microsoft 365 e Dynamics 365) vengono fatturate in base alla licenza per utente.</span><span class="sxs-lookup"><span data-stu-id="cb235-115">Microsoft's Software as a Service (SaaS)-based cloud offerings (Microsoft 365 and Dynamics 365) charge per-user license fees.</span></span> 
- <span data-ttu-id="cb235-116">Le offerte cloud PaaS e IaaS di Microsoft vengono fatturate in base al consumo di risorse.</span><span class="sxs-lookup"><span data-stu-id="cb235-116">Microsoft's Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) cloud offerings (Azure) charge based on cloud resource consumption.</span></span>
 
<span data-ttu-id="cb235-p102">È anche possibile utilizzare una sottoscrizione di prova, che scade dopo un determinato periodo di tempo o dopo una soglia di consumo. È possibile convertire una sottoscrizione di prova in sottoscrizione a pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb235-p102">You can also use a trial subscription, but the subscription expires after a specific amount of time or consumption charges. You can convert a trial subscription to a paid subscription.</span></span>
  
<span data-ttu-id="cb235-119">Le organizzazioni possono disporre di più sottoscrizioni per le offerte cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb235-119">Organizations can have multiple subscriptions for Microsoft's cloud offerings.</span></span> <span data-ttu-id="cb235-120">Nella figura 1 viene mostrata una singola organizzazione che dispone di più sottoscrizioni di Microsoft 365, una di Dynamics 365 e più sottoscrizioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="cb235-120">Figure 1 shows a single organization that has multiple Microsoft 365 subscriptions, a Dynamics 365 subscription, and multiple Azure subscriptions.</span></span>

<span data-ttu-id="cb235-121">**Figura 1: esempio di più sottoscrizioni per un'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="cb235-121">**Figure 1: Example of multiple subscriptions for an organization**</span></span>

![Esempio di organizzazione con più sottoscrizioni per le offerte cloud di Microsoft.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a><span data-ttu-id="cb235-123">Licenze</span><span class="sxs-lookup"><span data-stu-id="cb235-123">Licenses</span></span>

<span data-ttu-id="cb235-124">Per le offerte cloud SaaS di Microsoft, una licenza consente a un account utente specifico di utilizzare l'offerta cloud.</span><span class="sxs-lookup"><span data-stu-id="cb235-124">For Microsoft's SaaS cloud offerings, a license allows a specific user account to use the services of the cloud offering.</span></span> <span data-ttu-id="cb235-125">Vengono effettuati addebiti mensili fissi come parte della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="cb235-125">You are charged a fixed monthly fee as part of your subscription.</span></span> <span data-ttu-id="cb235-126">Gli amministratori assegnano licenza a singoli account utente nella sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="cb235-126">Administrators assign licenses to individual user accounts in the subscription.</span></span> <span data-ttu-id="cb235-127">Ad esempio, nella figura 2, la Contoso Corporation dispone di una sottoscrizione a Microsoft 365 E5 con 100 licenze, che consente a oltre 100 account utente singoli di usare le funzionalità e i servizi di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="cb235-127">For the example in Figure 2, the Contoso Corporation has a Microsoft 365 E5 subscription with 100 licenses, which allows to up to 100 individual user accounts to use Microsoft 365 E5 features and services.</span></span>
  
<span data-ttu-id="cb235-128">**Figura 2: licenze comprese nelle sottoscrizioni basate su SaaS di un'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="cb235-128">**Figure 2: Licenses within the SaaS-based subscriptions for an organization**</span></span>

![Un esempio di più licenze all'interno delle sottoscrizioni per le offerte cloud di Microsoft basate su SaaS.](../media/Subscriptions/Subscriptions-Fig2.png)
  
<span data-ttu-id="cb235-130">Per i servizi cloud basati su PaaS di Azure, le licenze software sono integrate nel prezzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="cb235-130">For Azure PaaS-based cloud services, software licenses are built into the service pricing.</span></span>
  
<span data-ttu-id="cb235-p105">Per le macchine virtuali basate su IaaS di Azure, potrebbero essere necessarie altre licenze per usare il software o l'applicazione installata sull'immagine di una macchina virtuale. Alcune immagini della macchina virtuale dispongono di versioni concesse in licenza o software installato; i costi sono inclusi nella tariffa al minuto del server. Alcuni esempi sono le immagini della macchina virtuale per SQL Server 2014 e SQL Server 2016. </span><span class="sxs-lookup"><span data-stu-id="cb235-p105">For Azure IaaS-based virtual machines, additional licenses to use the software or application installed on a virtual machine image might be required. Some virtual machine images have licensed versions of software installed and the cost is included in the per-minute rate for the server. Examples are the virtual machine images for SQL Server 2014 and SQL Server 2016.</span></span> 
  
<span data-ttu-id="cb235-p106">Alcune immagini della macchina virtuale dispongono di versioni di prova delle applicazioni installate e necessitano di ulteriori licenze software per l’uso dopo il periodo di prova. Ad esempio, l'immagine della macchina virtuale di prova di SharePoint Server 2016 include una versione di prova di SharePoint Server 2016 preinstallata. Per continuare a usare SharePoint Server 2016 dopo il periodo di prova, è necessario acquistare una licenza di SharePoint Server 2016 e le licenze client da Microsoft. Tali costi sono separati rispetto alla sottoscrizione di Azure e si applica ancora la tariffa al minuto di esecuzione della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="cb235-p106">Some virtual machine images have trial versions of applications installed and need additional software application licenses for use beyond the trial period. For example, the SharePoint Server 2016 Trial virtual machine image includes a trial version of SharePoint Server 2016 pre-installed. To continue using SharePoint Server 2016 after the trial expiration date, you must purchase a SharePoint Server 2016 license and client licenses from Microsoft. These charges are separate from the Azure subscription and the per-minute rate to run the virtual machine still applies.</span></span>
  
### <a name="user-accounts"></a><span data-ttu-id="cb235-138">Account utente</span><span class="sxs-lookup"><span data-stu-id="cb235-138">User accounts</span></span>

<span data-ttu-id="cb235-139">Gli account utente per tutte le offerte cloud di Microsoft sono archiviati in un tenant di Azure Active Directory (Azure AD) che include gli account utente e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="cb235-139">User accounts for all of Microsoft's cloud offerings are stored in an Azure Active Directory (Azure AD) tenant, which contains user accounts and groups.</span></span> <span data-ttu-id="cb235-140">Un tenant di Azure AD può essere sincronizzato con gli account Active Directory Domain Services (AD DS) esistenti tramite Azure AD Connect, un servizio basato su server di Windows.</span><span class="sxs-lookup"><span data-stu-id="cb235-140">An Azure AD tenant can be synchronized with your existing Active Directory Domain Services (AD DS) accounts using Azure AD Connect, a Windows server-based service.</span></span> <span data-ttu-id="cb235-141">Si tratta della cosiddetta sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="cb235-141">This is known as directory synchronization.</span></span>
  
<span data-ttu-id="cb235-142">Nella figura 3 viene mostrato un esempio di più sottoscrizioni di un'organizzazione che usa un tenant Azure AD comune, il quale include gli account dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb235-142">Figure 3 shows an example of multiple subscriptions of an organization using a common Azure AD tenant that contains the organization's accounts.</span></span>
  
<span data-ttu-id="cb235-143">**Figura 3: più sottoscrizioni di un'organizzazione che utilizza lo stesso tenant di Azure AD**</span><span class="sxs-lookup"><span data-stu-id="cb235-143">**Figure 3: Multiple subscriptions of an organization that use the same Azure AD tenant**</span></span>

![Esempio di organizzazione con più sottoscrizioni che utilizzano lo stesso tenant Azure AD.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a><span data-ttu-id="cb235-145">Tenant</span><span class="sxs-lookup"><span data-stu-id="cb235-145">Tenants</span></span>

<span data-ttu-id="cb235-146">Per le offerte cloud SaaS, il tenant rappresenta il percorso locale che ospita i server che forniscono i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="cb235-146">For SaaS cloud offerings, the tenant is the regional location that houses the servers providing cloud services.</span></span> <span data-ttu-id="cb235-147">Ad esempio, la Contoso Corporation ha scelto l'Europa per ospitare Microsoft 365, EMS e i tenant di Dynamics 365 per i 15.000 dipendenti della sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="cb235-147">For example, the Contoso Corporation chose the European region to host its Microsoft 365, EMS, and Dynamics 365 tenants for the 15,000 workers in their Paris headquarters.</span></span>
  
<span data-ttu-id="cb235-p109">I servizi PaaS di Azure e i carichi di lavoro basati su macchina virtuale e ospitati in IaaS di Azure possono avere tenancy in qualsiasi datacenter di Azure in tutto il mondo. Quando si crea un'app o un servizio PaaS di Azure oppure elementi di un carico di lavoro IaaS, si specifica il datacenter di Azure, noto anche come percorso.</span><span class="sxs-lookup"><span data-stu-id="cb235-p109">Azure PaaS services and virtual machine-based workloads hosted in Azure IaaS can have tenancy in any Azure datacenter across the world. You specify the Azure datacenter, known as the location, when you create the Azure PaaS app or service or element of an IaaS workload.</span></span>
  
<span data-ttu-id="cb235-150">Un tenant Azure AD è un'istanza specifica di Azure AD che include account e gruppi.</span><span class="sxs-lookup"><span data-stu-id="cb235-150">An Azure AD tenant is a specific instance of Azure AD containing accounts and groups.</span></span> <span data-ttu-id="cb235-151">Le sottoscrizioni di prova o a pagamento di Microsoft 365 o Dynamics 365 includono un tenant Azure AD gratuito.</span><span class="sxs-lookup"><span data-stu-id="cb235-151">Paid or trial subscriptions of Microsoft 365 or Dynamics 365 include a free Azure AD tenant.</span></span> <span data-ttu-id="cb235-152">Il tenant Azure AD non include altri servizi di Azure e non è lo stesso per la sottoscrizione di prova o a pagamento di Azure.</span><span class="sxs-lookup"><span data-stu-id="cb235-152">This Azure AD tenant does not include other Azure services and is not the same as an Azure trial or paid subscription.</span></span>
  
### <a name="summary-of-the-hierarchy"></a><span data-ttu-id="cb235-153">Riepilogo della gerarchia</span><span class="sxs-lookup"><span data-stu-id="cb235-153">Summary of the hierarchy</span></span>

<span data-ttu-id="cb235-154">Ecco un rapido riepilogo:</span><span class="sxs-lookup"><span data-stu-id="cb235-154">Here is a quick recap:</span></span>
  
- <span data-ttu-id="cb235-155">Un'organizzazione può avere più sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="cb235-155">An organization can have multiple subscriptions</span></span>
    
  - <span data-ttu-id="cb235-156">Una sottoscrizione può avere più licenze</span><span class="sxs-lookup"><span data-stu-id="cb235-156">A subscription can have multiple licenses</span></span>
    
  - <span data-ttu-id="cb235-157">Le licenze possono essere assegnate a singoli account utente</span><span class="sxs-lookup"><span data-stu-id="cb235-157">Licenses can be assigned to individual user accounts</span></span>
    
  - <span data-ttu-id="cb235-158">Gli account utente sono memorizzati in un tenant di Azure AD</span><span class="sxs-lookup"><span data-stu-id="cb235-158">User accounts are stored in an Azure AD tenant</span></span>
    
<span data-ttu-id="cb235-159">Ecco un esempio di relazione di organizzazioni, sottoscrizioni, licenze e account utente:</span><span class="sxs-lookup"><span data-stu-id="cb235-159">Here is an example of the relationship of organizations, subscriptions, licenses, and user accounts:</span></span>
  
- <span data-ttu-id="cb235-160">Un'organizzazione identificata dal nome di dominio pubblico.</span><span class="sxs-lookup"><span data-stu-id="cb235-160">An organization identified by its public domain name.</span></span>
    
  - <span data-ttu-id="cb235-161">Una sottoscrizione a Microsoft 365 E3 con licenze utente.</span><span class="sxs-lookup"><span data-stu-id="cb235-161">A Microsoft 365 E3 subscription with user licenses.</span></span>
    
    <span data-ttu-id="cb235-162">Una sottoscrizione a Microsoft 365 E5 con licenze utente.</span><span class="sxs-lookup"><span data-stu-id="cb235-162">A Microsoft 365 E5 subscription with user licenses.</span></span>
    
    <span data-ttu-id="cb235-163">Una sottoscrizione a  Dynamics 365 con licenze utente.</span><span class="sxs-lookup"><span data-stu-id="cb235-163">A Dynamics 365 subscription with user licenses.</span></span>
    
    <span data-ttu-id="cb235-164">Più sottoscrizioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="cb235-164">Multiple Azure subscriptions.</span></span>
    
  - <span data-ttu-id="cb235-165">Gli account utente dell'organizzazione in un tenant Azure AD comune.</span><span class="sxs-lookup"><span data-stu-id="cb235-165">The organization's user accounts in a common Azure AD tenant.</span></span>
    
<span data-ttu-id="cb235-166">Più sottoscrizioni alle offerte cloud di Microsoft sono in grado di usare lo stesso tenant Azure AD che si comporta come un provider di identità comune.</span><span class="sxs-lookup"><span data-stu-id="cb235-166">Multiple Microsoft cloud offering subscriptions can use the same Azure AD tenant that acts as a common identity provider.</span></span> <span data-ttu-id="cb235-167">Un tenant Azure AD centrale che contiene gli account sincronizzati di Active Directory Domain Services locale offre IDaaS basata su cloud per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb235-167">A central Azure AD tenant that contains the synchronized accounts of your on-premises AD DS provides cloud-based Identity as a Service (IDaaS) for your organization.</span></span> 
  
<span data-ttu-id="cb235-168">**Figura 4: account sincronizzati in locale e IDaaS per un'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="cb235-168">**Figure 4: Synchronized on-premises accounts and IDaaS for an organization**</span></span>

![IDaaS IaaS per l'organizzazione.](../media/Subscriptions/Subscriptions-Fig4.png)
  
<span data-ttu-id="cb235-p112">La figura 4 mostra in che modo il tenant di Azure AD comune viene usato dalle offerte cloud SaaS di Microsoft, dalle app PaaS di Azure e dalle macchine virtuali IaaS di Azure che usano Azure AD Domain Services. Azure AD Connect sincronizza la foresta di Active Directory Domain Services locale con il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cb235-p112">Figure 4 shows how a common Azure AD tenant is used by Microsoft's SaaS cloud offerings, Azure PaaS apps, and virtual machines in Azure IaaS that use Azure AD Domain Services. Azure AD Connect synchronizes the on-premises AD DS forest with the Azure AD tenant.</span></span>
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a><span data-ttu-id="cb235-172">Combinazione di sottoscrizioni per offerte cloud di Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb235-172">Combining subscriptions for multiple Microsoft cloud offerings</span></span>

<span data-ttu-id="cb235-173">La tabella descrive il modo in cui è possibile combinare più offerte cloud di Microsoft sulla base della sottoscrizione già in possesso per un tipo di offerte cloud (le etichette dall'alto verso il basso della prima colonna) e aggiungendo una sottoscrizione per un'offerta cloud differente (tra le colonne).</span><span class="sxs-lookup"><span data-stu-id="cb235-173">The following table describes how you can combine multiple Microsoft cloud offerings based on already having a subscription for one type of cloud offering (the labels going down the first column) and adding a subscription for a different cloud offering (going across the columns).</span></span>
  
||<span data-ttu-id="cb235-174">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="cb235-174">**Microsoft 365**</span></span>|<span data-ttu-id="cb235-175">**Azure**</span><span class="sxs-lookup"><span data-stu-id="cb235-175">**Azure**</span></span>|<span data-ttu-id="cb235-176">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="cb235-176">**Dynamics 365**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb235-177">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="cb235-177">**Microsoft 365**</span></span> <br/> |<span data-ttu-id="cb235-178">ND</span><span class="sxs-lookup"><span data-stu-id="cb235-178">NA</span></span>  <br/> |<span data-ttu-id="cb235-179">È necessario aggiungere una sottoscrizione di Azure all'organizzazione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="cb235-179">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="cb235-180">È necessario aggiungere una sottoscrizione di Dynamics 365 all'organizzazione dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb235-180">You add a Dynamics 365 subscription to your organization from the Microsoft 365 admin center.</span></span>  <br/> |
|<span data-ttu-id="cb235-181">**Azure**</span><span class="sxs-lookup"><span data-stu-id="cb235-181">**Azure**</span></span> <br/> |<span data-ttu-id="cb235-182">È necessario aggiungere una sottoscrizione di Microsoft 365 all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb235-182">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="cb235-183">ND</span><span class="sxs-lookup"><span data-stu-id="cb235-183">NA</span></span>  <br/> |<span data-ttu-id="cb235-184">È necessario aggiungere una sottoscrizione di Dynamics 365 all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb235-184">You add a Dynamics 365 subscription to your organization.</span></span>  <br/> |
|<span data-ttu-id="cb235-185">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="cb235-185">**Dynamics 365**</span></span> <br/> |<span data-ttu-id="cb235-186">È necessario aggiungere una sottoscrizione di Microsoft 365 all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb235-186">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="cb235-187">È necessario aggiungere una sottoscrizione di Azure all'organizzazione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="cb235-187">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="cb235-188">ND</span><span class="sxs-lookup"><span data-stu-id="cb235-188">NA</span></span>  <br/> |
   
<span data-ttu-id="cb235-189">Un metodo rapido per aggiungere sottoscrizioni all'organizzazione per i servizi basati su SaaS di Microsoft è quello di utilizzare l'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="cb235-189">An easy way to add subscriptions to your organization for Microsoft SaaS-based services is through the admin center:</span></span>
  
1. <span data-ttu-id="cb235-190">Accedere all'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="cb235-190">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with your global administrator account.</span></span>
    
2. <span data-ttu-id="cb235-191">Dal riquadro di navigazione a sinistra della home page dell'**interfaccia di amministrazione**, fare clic su **Fatturazione**, quindi su **Acquista servizi**.</span><span class="sxs-lookup"><span data-stu-id="cb235-191">From the left navigation of the **Admin center** home page, click **Billing**, and then **Purchase services**.</span></span>
    
3. <span data-ttu-id="cb235-192">Nella pagina **Acquista servizi**, procedere all'acquisto delle nuove sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="cb235-192">On the **Purchase services** page, purchase your new subscriptions.</span></span>
    
<span data-ttu-id="cb235-193">L'interfaccia di amministrazione assegna l'organizzazione e il tenant Azure AD della sottoscrizione di Microsoft 365 alle nuove sottoscrizioni per le offerte cloud basate su SaaS.</span><span class="sxs-lookup"><span data-stu-id="cb235-193">The admin center assigns the organization and Azure AD tenant of your Microsoft 365 subscription to the new subscriptions for SaaS-based cloud offerings.</span></span>
  
<span data-ttu-id="cb235-194">Per aggiungere una sottoscrizione di Azure con la stessa organizzazione e il tenant di Azure AD della sottoscrizione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="cb235-194">To add an Azure subscription with the same organization and Azure AD tenant as your Microsoft 365 subscription:</span></span>
  
1. <span data-ttu-id="cb235-195">Accedere al portale di Azure ([https://portal.azure.com](https://portal.azure.com)) con l'account di amministratore globale di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb235-195">Sign in to the Azure portal ([https://portal.azure.com](https://portal.azure.com)) with your Microsoft 365 global administrator account.</span></span>
    
2. <span data-ttu-id="cb235-196">Nella barra di spostamento a sinistra, fare clic su **Sottoscrizioni**, quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cb235-196">In the left navigation, click **Subscriptions**, and then click **Add**.</span></span>
    
3. <span data-ttu-id="cb235-197">Nella pagina **Aggiungi sottoscrizione**, selezionare un'offerta e completare le informazioni di pagamento e il contratto.</span><span class="sxs-lookup"><span data-stu-id="cb235-197">On the **Add subscription** page, select an offer and complete the payment information and agreement.</span></span>
    
<span data-ttu-id="cb235-198">Se sono state acquistate sottoscrizioni di Azure e Microsoft 365 separate e si desidera accedere al tenant di Microsoft 365 Azure AD dalla sottoscrizione di Azure, vedere le istruzioni riportate nell'articolo [Aggiungere un abbonamento Azure esistente al tenant di Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span><span class="sxs-lookup"><span data-stu-id="cb235-198">If you purchased Azure and Microsoft 365 subscriptions separately and want to access the Microsoft 365 Azure AD tenant from your Azure subscription, see the instructions in [Add an existing Azure subscription to your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="cb235-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb235-199">See also</span></span>

[<span data-ttu-id="cb235-200">Microsoft cloud per le illustrazioni di Enterprise Architecture</span><span class="sxs-lookup"><span data-stu-id="cb235-200">Microsoft cloud for enterprise architects illustrations</span></span>](../solutions/cloud-architecture-models.md)
  
[<span data-ttu-id="cb235-201">Modelli architetturali per SharePoint, Exchange, Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="cb235-201">Architectural models for SharePoint, Exchange, Skype for Business, and Lync</span></span>](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[<span data-ttu-id="cb235-202">Soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="cb235-202">Hybrid solutions</span></span>](hybrid-solutions.md)

## <a name="next-step"></a><span data-ttu-id="cb235-203">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="cb235-203">Next step</span></span>

[<span data-ttu-id="cb235-204">Valutazione della connettività di rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb235-204">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
