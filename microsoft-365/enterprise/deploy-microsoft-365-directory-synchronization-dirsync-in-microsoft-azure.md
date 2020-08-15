---
title: Distribuire la sincronizzazione della directory Microsoft 365 in Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Informazioni su come distribuire Azure AD Connect in una macchina virtuale in Azure per sincronizzare gli account tra la directory locale e il tenant di Azure AD.
ms.openlocfilehash: 8db78d20ee4c2186918a0b3b433f8f0ae056816e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691315"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a><span data-ttu-id="19fc0-103">Distribuire la sincronizzazione della directory Microsoft 365 in Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-103">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>

<span data-ttu-id="19fc0-104">Azure Active Directory (Azure AD) Connect (noto in precedenza come strumento di sincronizzazione della directory, strumento di sincronizzazione della directory o strumento di DirSync.exe) è un'applicazione installata in un server appartenente a un dominio per sincronizzare gli utenti di servizi di dominio Active Directory (AD DS) locali con il tenant di Azure AD della sottoscrizione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-104">Azure Active Directory (Azure AD) Connect (formerly known as the Directory Synchronization tool, Directory Sync tool, or the DirSync.exe tool) is an application that you install on a domain-joined server to synchronize your on-premises Active Directory Domain Services (AD DS) users to the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="19fc0-105">Microsoft 365 utilizza Azure AD per il servizio directory.</span><span class="sxs-lookup"><span data-stu-id="19fc0-105">Microsoft 365 uses Azure AD for its directory service.</span></span> <span data-ttu-id="19fc0-106">La sottoscrizione Microsoft 365 include un tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19fc0-106">Your Microsoft 365 subscription includes an Azure AD tenant.</span></span> <span data-ttu-id="19fc0-107">Questo tenant può essere utilizzato anche per la gestione delle identità dell'organizzazione con altri carichi di lavoro cloud, incluse altre applicazioni SaaS e app in Azure.</span><span class="sxs-lookup"><span data-stu-id="19fc0-107">This tenant can also be used for management of your organization's identities with other cloud workloads, including other SaaS applications and apps in Azure.</span></span>

<span data-ttu-id="19fc0-108">È possibile installare Azure AD Connect in un server locale, ma è anche possibile installarlo in una macchina virtuale di Azure per questi motivi:</span><span class="sxs-lookup"><span data-stu-id="19fc0-108">You can install Azure AD Connect on a on-premises server, but you can also install it on a virtual machine in Azure for these reasons:</span></span>
  
- <span data-ttu-id="19fc0-109">È possibile effettuare il provisioning e configurare i server basati su cloud più rapidamente, in modo da rendere disponibili i servizi in minor tempo.</span><span class="sxs-lookup"><span data-stu-id="19fc0-109">You can provision and configure cloud-based servers faster, making the services available to your users sooner.</span></span>
- <span data-ttu-id="19fc0-110">Azure offre una migliore disponibilità del sito con un numero minore di operazioni.</span><span class="sxs-lookup"><span data-stu-id="19fc0-110">Azure offers better site availability with less effort.</span></span>
- <span data-ttu-id="19fc0-111">È possibile ridurre il numero di server locali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="19fc0-111">You can reduce the number of on-premises servers in your organization.</span></span>

<span data-ttu-id="19fc0-p102">Questa soluzione richiede che venga stabilita una connessione tra la rete locale e la rete virtuale di Azure. Per altre informazioni, vedere [Connettere una rete locale a una rete virtuale di Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="19fc0-p102">This solution requires connectivity between your on-premises network and your Azure virtual network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="19fc0-114">In questo articolo viene descritta la sincronizzazione di un singolo dominio in una foresta singola.</span><span class="sxs-lookup"><span data-stu-id="19fc0-114">This article describes synchronization of a single domain in a single forest.</span></span> <span data-ttu-id="19fc0-115">Azure AD Connect sincronizza tutti i domini di AD DS nella foresta di Active Directory con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-115">Azure AD Connect synchronizes all AD DS domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="19fc0-116">Se si dispone di più foreste di Active Directory per la sincronizzazione con Microsoft 365, vedere [multi-Forest Directory Sync with Single Sign-on scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span><span class="sxs-lookup"><span data-stu-id="19fc0-116">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a><span data-ttu-id="19fc0-117">Panoramica della distribuzione della sincronizzazione della directory Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-117">Overview of deploying Microsoft 365 directory synchronization in Azure</span></span>

<span data-ttu-id="19fc0-118">Nel diagramma seguente viene illustrato Azure AD Connect in esecuzione su una macchina virtuale in Azure (il server di sincronizzazione della directory) che sincronizza una foresta di AD DS locale in un abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-118">The following diagram shows Azure AD Connect running on a virtual machine in Azure (the directory sync server) that synchronizes an on-premises AD DS forest to a Microsoft 365 subscription.</span></span>
  
![Strumento di Azure AD Connect in una macchina virtuale in Azure sincronizzazione degli account locali al tenant di Azure AD di un abbonamento a Microsoft 365 con flusso di traffico](../media/CP-DirSyncOverview.png)
  
<span data-ttu-id="19fc0-p104">Nel diagramma, sono riportate due reti connesse tramite una VPN da sito a sito o una connessione ExpressRoute. Una è la rete locale in cui si trovano i controller di dominio di AD DS, mentre l'altra è una rete virtuale di Azure con un server di sincronizzazione della directory, una macchina virtuale che esegue [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). I flussi di traffico principali provenienti dal server di sincronizzazione della directory sono due:</span><span class="sxs-lookup"><span data-stu-id="19fc0-p104">In the diagram, there are two networks connected by a site-to-site VPN or ExpressRoute connection. There is an on-premises network where AD DS domain controllers are located, and there is an Azure virtual network with a directory sync server, which is a virtual machine running [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). There are two main traffic flows originating from the directory sync server:</span></span>
  
-  <span data-ttu-id="19fc0-123">Azure AD Connect esegue la query a un controller di dominio nella rete locale per apportare modifiche ad account e password.</span><span class="sxs-lookup"><span data-stu-id="19fc0-123">Azure AD Connect queries a domain controller on the on-premises network for changes to accounts and passwords.</span></span>
-  <span data-ttu-id="19fc0-124">Azure AD Connect invia le modifiche apportate agli account e alle password all'istanza di Azure AD dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-124">Azure AD Connect sends the changes to accounts and passwords to the Azure AD instance of your Microsoft 365 subscription.</span></span> <span data-ttu-id="19fc0-125">Poiché il server di sincronizzazione della directory si trova in una parte estesa della rete locale, queste modifiche vengono inviate tramite il server proxy della rete locale.</span><span class="sxs-lookup"><span data-stu-id="19fc0-125">Because the directory sync server is in an extended portion of your on-premises network, these changes are sent through the on-premises network's proxy server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="19fc0-126">Questa soluzione descrive la sincronizzazione di un singolo dominio di Active Directory, in una foresta Active Directory singola.</span><span class="sxs-lookup"><span data-stu-id="19fc0-126">This solution describes synchronization of a single Active Directory domain, in a single Active Directory forest.</span></span> <span data-ttu-id="19fc0-127">Azure AD Connect sincronizza tutti i domini di Active Directory nella foresta di Active Directory con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-127">Azure AD Connect synchronizes all Active Directory domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="19fc0-128">Se si dispone di più foreste di Active Directory per la sincronizzazione con Microsoft 365, vedere [multi-Forest Directory Sync with Single Sign-on scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span><span class="sxs-lookup"><span data-stu-id="19fc0-128">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
<span data-ttu-id="19fc0-129">La distribuzione di questa soluzione comprende due passaggi principali:</span><span class="sxs-lookup"><span data-stu-id="19fc0-129">There are two major steps when you deploy this solution:</span></span>
  
1. <span data-ttu-id="19fc0-p107">Creare una rete virtuale Azure e stabilire una connessione VPN da sito a sito verso la rete locale. Per ulteriori informazioni, vedere [Connettere una rete locale a una rete virtuale di Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="19fc0-p107">Create an Azure virtual network and establish a site-to-site VPN connection to your on-premises network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
    
2. <span data-ttu-id="19fc0-132">Installare [Azure ad Connect](https://www.microsoft.com/download/details.aspx?id=47594) in una macchina virtuale aggiunta a un dominio in Azure e quindi sincronizzare ad DS locale con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-132">Install [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) on a domain-joined virtual machine in Azure, and then synchronize the on-premises AD DS to Microsoft 365.</span></span> <span data-ttu-id="19fc0-133">Questa operazione implica:</span><span class="sxs-lookup"><span data-stu-id="19fc0-133">This involves:</span></span>
    
    <span data-ttu-id="19fc0-134">La creazione di una macchina virtuale di Azure per l'esecuzione di Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="19fc0-134">Creating an Azure Virtual Machine to run Azure AD Connect.</span></span>
    
    <span data-ttu-id="19fc0-135">L'installazione e la configurazione di [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span><span class="sxs-lookup"><span data-stu-id="19fc0-135">Installing and configuring [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span>
    
    <span data-ttu-id="19fc0-136">La configurazione di Azure AD Connect richiede le credenziali (nome utente e password) di un account di amministratore di Azure AD e di un account di amministratore dell'organizzazione di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="19fc0-136">Configuring Azure AD Connect requires the credentials (user name and password) of an Azure AD administrator account and a AD DS enterprise administrator account.</span></span> <span data-ttu-id="19fc0-137">Azure AD Connect viene eseguito immediatamente e su base continuativa per sincronizzare la foresta di servizi di dominio Active Directory locale con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-137">Azure AD Connect runs immediately and on an ongoing basis to synchronize the on-premises AD DS forest to Microsoft 365.</span></span>
    
<span data-ttu-id="19fc0-138">Prima di distribuire questa soluzione in produzione, è possibile utilizzare le istruzioni riportate nella [configurazione di base per l'organizzazione simulata](simulated-ent-base-configuration-microsoft-365-enterprise.md) per impostare la configurazione come prova del concetto, per le dimostrazioni o per la sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="19fc0-138">Before you deploy this solution in production, you can use the instructions in [The simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to set this configuration up as a proof of concept, for demonstrations, or for experimentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="19fc0-139">Al termine della configurazione di Azure AD Connect, le credenziali dell'account amministratore dell'organizzazione di AD DS non vengono memorizzate.</span><span class="sxs-lookup"><span data-stu-id="19fc0-139">When Azure AD Connect configuration completes, it does not save the AD DS enterprise administrator account credentials.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="19fc0-140">Questa soluzione descrive la sincronizzazione di una singola foresta di servizi di dominio Active Directory a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-140">This solution describes synchronizing a single AD DS forest to Microsoft 365.</span></span> <span data-ttu-id="19fc0-141">La topologia discussa in questo articolo rappresenta soltanto un modo per implementare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="19fc0-141">The topology discussed in this article represents only one way to implement this solution.</span></span> <span data-ttu-id="19fc0-142">La topologia dell'organizzazione potrebbe variare in base ai requisiti di rete e alle considerazioni di sicurezza univoci.</span><span class="sxs-lookup"><span data-stu-id="19fc0-142">Your organization's topology might differ based on your unique network requirements and security considerations.</span></span> 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a><span data-ttu-id="19fc0-143">Pianificare l'hosting di un server di sincronizzazione della directory per Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-143">Plan for hosting a directory sync server for Microsoft 365 in Azure</span></span>
<span data-ttu-id="19fc0-144"><a name="PlanningVirtual"> </a></span><span class="sxs-lookup"><span data-stu-id="19fc0-144"><a name="PlanningVirtual"> </a></span></span>

### <a name="prerequisites"></a><span data-ttu-id="19fc0-145">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="19fc0-145">Prerequisites</span></span>

<span data-ttu-id="19fc0-146">Prima di iniziare, rivedere i prerequisiti relativi alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="19fc0-146">Before you begin, review the following prerequisites for this solution:</span></span>
  
- <span data-ttu-id="19fc0-147">Rivedere i contenuti sulla pianificazione correlati in [Pianificare la rete virtuale di Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span><span class="sxs-lookup"><span data-stu-id="19fc0-147">Review the related planning content in [Plan your Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span></span>
    
- <span data-ttu-id="19fc0-148">Assicurarsi che siano soddisfatti tutti i [Prerequisiti](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) relativi alla configurazione della rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="19fc0-148">Ensure that you meet all [Prerequisites](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) for configuring the Azure virtual network.</span></span>
    
- <span data-ttu-id="19fc0-149">Avere un abbonamento a Microsoft 365 che includa la funzionalità di integrazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="19fc0-149">Have a Microsoft 365 subscription that includes the Active Directory integration feature.</span></span> <span data-ttu-id="19fc0-150">Per informazioni sulle sottoscrizioni di Microsoft 365, visitare la [pagina di sottoscrizione di microsoft 365](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span><span class="sxs-lookup"><span data-stu-id="19fc0-150">For information about Microsoft 365 subscriptions, go to the [Microsoft 365 subscription page](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span></span>
    
- <span data-ttu-id="19fc0-151">Eseguire il provisioning di una macchina virtuale di Azure che esegue Azure AD Connect per sincronizzare la foresta di servizi di dominio Active Directory locale con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-151">Provision one Azure Virtual Machine that runs Azure AD Connect to synchronize your on-premises AD DS forest with Microsoft 365.</span></span>
    
    <span data-ttu-id="19fc0-152">È necessario disporre delle credenziali (nomi e password) dell'account amministratore dell'organizzazione AD DS e dell'account amministratore di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19fc0-152">You must have the credentials (names and passwords) for a AD DS enterprise administrator account and an Azure AD Administrator account.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="19fc0-153">Presupposti per la progettazione dell’architettura della soluzione</span><span class="sxs-lookup"><span data-stu-id="19fc0-153">Solution architecture design assumptions</span></span>

<span data-ttu-id="19fc0-154">Di seguito sono riportate le scelte di progettazione effettuate per questa soluzione:</span><span class="sxs-lookup"><span data-stu-id="19fc0-154">The following list describes the design choices made for this solution.</span></span>
  
- <span data-ttu-id="19fc0-p112">In questa soluzione viene utilizzata una singola rete virtuale Azure con una connessione VPN da sito a sito. La rete virtuale Azure ospita una singola subnet che contiene il server di sincronizzazione della directory, sul quale è in esecuzione Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="19fc0-p112">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that has one server, the directory sync server that is running Azure AD Connect.</span></span> 
    
- <span data-ttu-id="19fc0-157">Nella rete locale sono disponibili un controller di dominio e alcuni server DNS.</span><span class="sxs-lookup"><span data-stu-id="19fc0-157">On the on-premises network, a domain controller and DNS servers exist.</span></span>
    
- <span data-ttu-id="19fc0-p113">Azure AD Connect esegue la sincronizzazione dell'hash delle password al posto del Single Sign-On. Non è necessario distribuire un'infrastruttura AD FS (Active Directory Federation Services). Per ulteriori informazioni sulla sincronizzazione della password e su Single Sign-On, vedere [Scelta del giusto metodo di autenticazione per la soluzione ibrida di gestione delle identità di Azure Active Directory](https://aka.ms/auth-options).</span><span class="sxs-lookup"><span data-stu-id="19fc0-p113">Azure AD Connect performs password hash synchronization instead of single sign-on. You do not have to deploy an Active Directory Federation Services (AD FS) infrastructure. To learn more about password hash synchronization and single sign-on options, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://aka.ms/auth-options).</span></span>
    
<span data-ttu-id="19fc0-p114">Quando si distribuisce la soluzione nel proprio ambiente, sono disponibili ulteriori opzioni di progettazione che è possibile considerare. Tale opzioni includono:</span><span class="sxs-lookup"><span data-stu-id="19fc0-p114">There are additional design choices that you might consider when you deploy this solution in your environment. These include the following:</span></span>
  
- <span data-ttu-id="19fc0-163">Se in una rete virtuale Azure esistente sono disponibili server DNS, determinare se si desidera che il server di sincronizzazione della directory li utilizzi per la risoluzione dei nomi al posto dei server DNS presenti nella rete locale.</span><span class="sxs-lookup"><span data-stu-id="19fc0-163">If there are existing DNS servers in an existing Azure virtual network, determine whether you want your directory sync server to use them for name resolution instead of DNS servers on the on-premises network.</span></span>
    
- <span data-ttu-id="19fc0-p115">Se in una rete virtuale Azure esistente sono disponibili controller di dominio, determinare se la configurazione di siti e servizi di Active Directory rappresenta una migliore opzione. Anziché utilizzare i controller di dominio nella rete locale, il server di sincronizzazione della directory può eseguire query con i controller di dominio nella rete virtuale Azure per cercare le modifiche apportate ad account e password.</span><span class="sxs-lookup"><span data-stu-id="19fc0-p115">If there are domain controllers in an existing Azure virtual network, determine whether configuring Active Directory Sites and Services may be a better option for you. The directory sync server can query the domain controllers in the Azure virtual network for changes in accounts and passwords instead of domain controllers on the on-premises network.</span></span>
    
## <a name="deployment-roadmap"></a><span data-ttu-id="19fc0-166">Guida di orientamento alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="19fc0-166">Deployment roadmap</span></span>

<span data-ttu-id="19fc0-167">La distribuzione di Azure AD Connect in una macchina virtuale in Azure è costituita da tre fasi:</span><span class="sxs-lookup"><span data-stu-id="19fc0-167">Deploying Azure AD Connect on a virtual machine in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="19fc0-168">Fase 1: Creare e configurare la rete virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-168">Phase 1: Create and configure the Azure virtual network</span></span>
    
- <span data-ttu-id="19fc0-169">Fase 2: Creare e configurare la macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-169">Phase 2: Create and configure the Azure virtual machine</span></span>
    
- <span data-ttu-id="19fc0-170">Fase 3: Installare e configurare Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="19fc0-170">Phase 3: Install and configure Azure AD Connect</span></span>
    
<span data-ttu-id="19fc0-171">Dopo la distribuzione, è necessario assegnare anche percorsi e licenze per i nuovi account utente in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19fc0-171">After deployment, you must also assign locations and licenses for the new user accounts in Microsoft 365.</span></span>


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a><span data-ttu-id="19fc0-172">Fase 1: Creare e configurare la rete virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-172">Phase 1: Create and configure the Azure virtual network</span></span>

<span data-ttu-id="19fc0-173">Per creare e configurare la rete virtuale di Azure, completare la [Fase 1: Preparare la rete locale](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) e la [Fase 2: Creare la rete virtuale cross-premise in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) nella guida di orientamento alla distribuzione di [Connect an on-premises network to a Microsoft Azure Virtual Network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="19fc0-173">To create and configure the Azure virtual network, complete [Phase 1: Prepare your on-premises network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) and [Phase 2: Create the cross-premises virtual network in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) in the deployment roadmap of [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
<span data-ttu-id="19fc0-174">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="19fc0-174">This is your resulting configuration.</span></span>
  
![Fase 1 del server di sincronizzazione della directory per Microsoft 365 ospitato in Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
<span data-ttu-id="19fc0-176">Nella figura viene illustrata una rete locale connessa a una rete virtuale di Azure tramite una connessione VPN da sito a sito o ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="19fc0-176">This figure shows an on-premises network connected to an Azure virtual network through a site-to-site VPN or ExpressRoute connection.</span></span>
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a><span data-ttu-id="19fc0-177">Fase 2: Creare e configurare la macchina virtuale Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-177">Phase 2: Create and configure the Azure virtual machine</span></span>

<span data-ttu-id="19fc0-p116">Creare la macchina virtuale in Azure seguendo le istruzioni disponibili nell’articolo [Creare una macchina virtuale Windows con il portale di Azure](https://go.microsoft.com/fwlink/p/?LinkId=393098). Utilizzare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="19fc0-p116">Create the virtual machine in Azure using the instructions [Create your first Windows virtual machine in the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Use the following settings:</span></span>
  
- <span data-ttu-id="19fc0-p117">Nel riquadro **Impostazioni di base**, selezionare la stessa sottoscrizione, lo stesso percorso e lo stesso gruppo di risorse della rete virtuale. Registrare nome utente e password in un percorso sicuro. Saranno necessari più avanti per connettersi alla macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="19fc0-p117">On the **Basics** pane, select the same subscription, location, and resource group as your virtual network. Record the user name and password in a secure location. You will need these later to connect to the virtual machine.</span></span>
    
- <span data-ttu-id="19fc0-183">Nel riquadro **Scegli una dimensione**, scegliere la dimensione **A2 Standard**.</span><span class="sxs-lookup"><span data-stu-id="19fc0-183">On the **Choose a size** pane, choose the **A2 Standard** size.</span></span>
    
- <span data-ttu-id="19fc0-p118">Nel riquadro **Impostazioni**, nella sezione **Archiviazione**, selezionare il tipo di disco **Standard**. Nella sezione **Rete**, selezionare il nome della rete virtuale e della subnet per ospitare il server di sincronizzazione della directory (non GatewaySubnet). Lasciare i valori predefiniti per tutte le altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="19fc0-p118">On the **Settings** pane, in the **Storage** section, select the **Standard** storage type. In the **Network** section, select the name of your virtual network and the subnet for hosting the directory sync server (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="19fc0-187">Verificare che il server di sincronizzazione della directory stia utilizzando correttamente il DNS controllando il DNS interno e accertandosi che sia stato aggiunto un record Address (A) per la macchina virtuale con l'indirizzo IP. </span><span class="sxs-lookup"><span data-stu-id="19fc0-187">Verify that your directory sync server is using DNS correctly by checking your internal DNS to make sure that an Address (A) record was added for the virtual machine with its IP address.</span></span> 
  
<span data-ttu-id="19fc0-p119">Seguire le istruzioni in [Connettersi e accedere alla macchina virtuale](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) per connettersi al server di sincronizzazione della directory con Connessione Desktop remoto. Dopo l'accesso, aggiungere la macchina virtuale al dominio di AD DS locale.</span><span class="sxs-lookup"><span data-stu-id="19fc0-p119">Use the instructions in [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to the directory sync server with a Remote Desktop Connection. After signing in, join the virtual machine to the on-premises AD DS domain.</span></span>
  
<span data-ttu-id="19fc0-p120">Affinché Azure AD Connect riesca ad accedere alle risorse di Internet, è necessario configurare il server di sincronizzazione della directory per utilizzare il server proxy della rete locale. È necessario contattare l'amministratore di rete per visualizzare eventuali ulteriori procedure di configurazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19fc0-p120">For Azure AD Connect to gain access to Internet resources, you must configure the directory sync server to use the on-premises network's proxy server. You should contact your network administrator for any additional configuration steps to perform.</span></span>
  
<span data-ttu-id="19fc0-192">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="19fc0-192">This is your resulting configuration.</span></span>
  
![Fase 2 del server di sincronizzazione della directory per Microsoft 365 ospitato in Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
<span data-ttu-id="19fc0-194">Nella figura viene illustrata la macchina virtuale del server di sincronizzazione della directory nella rete virtuale Azure cross-premise.</span><span class="sxs-lookup"><span data-stu-id="19fc0-194">This figure shows the directory sync server virtual machine in the cross-premises Azure virtual network.</span></span>
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a><span data-ttu-id="19fc0-195">Fase 3: Installare e configurare Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="19fc0-195">Phase 3: Install and configure Azure AD Connect</span></span>

<span data-ttu-id="19fc0-196">Completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="19fc0-196">Complete the following procedure:</span></span>
  
1. <span data-ttu-id="19fc0-p121">Eseguire la connessione al server di sincronizzazione della directory utilizzando Connessione Desktop remoto con un account di dominio AD DS dotato dei privilegi di amministratore locale. Vedere [Connettersi e accedere alla macchina virtuale](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="19fc0-p121">Connect to the directory sync server using a Remote Desktop Connection with an AD DS domain account that has local administrator privileges. See [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
    
2. <span data-ttu-id="19fc0-199">Dal server di sincronizzazione della directory, aprire l'articolo [configurare la sincronizzazione della directory per Microsoft 365](set-up-directory-synchronization.md) e seguire le istruzioni per la sincronizzazione della directory con la sincronizzazione degli hash delle password.</span><span class="sxs-lookup"><span data-stu-id="19fc0-199">From the directory sync server, open the [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) article and follow the directions for directory synchronization with password hash synchronization.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="19fc0-p122">Il programma di installazione crea l'account **AAD_xxxxxxxxxxxx** nell'unità organizzativa Utenti locali. Non spostare o eliminare l'account, altrimenti la sincronizzazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="19fc0-p122">Setup creates the **AAD_xxxxxxxxxxxx** account in the Local Users organizational unit (OU). Do not move or remove this account or synchronization will fail.</span></span>
  
<span data-ttu-id="19fc0-202">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="19fc0-202">This is your resulting configuration.</span></span>
  
![Fase 3 del server di sincronizzazione della directory per Microsoft 365 ospitato in Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
<span data-ttu-id="19fc0-204">Nella figura viene illustrato il server di sincronizzazione della directory con Azure AD Connect nella rete virtuale Azure cross-premise.</span><span class="sxs-lookup"><span data-stu-id="19fc0-204">This figure shows the directory sync server with Azure AD Connect in the cross-premises Azure virtual network.</span></span>
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a><span data-ttu-id="19fc0-205">Assegnare percorsi e licenze agli utenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19fc0-205">Assign locations and licenses to users in Microsoft 365</span></span>

<span data-ttu-id="19fc0-206">Azure AD Connect aggiunge account alla sottoscrizione Microsoft 365 dal servizio di dominio Active Directory locale, ma affinché gli utenti eseguano l'accesso a Microsoft 365 e utilizzino i propri servizi, gli account devono essere configurati con un percorso e licenze.</span><span class="sxs-lookup"><span data-stu-id="19fc0-206">Azure AD Connect adds accounts to your Microsoft 365 subscription from the on-premises AD DS, but in order for users to sign in to Microsoft 365 and use its services, the accounts must be configured with a location and licenses.</span></span> <span data-ttu-id="19fc0-207">Seguire questi passaggi per aggiungere il percorso e attivare le licenze per gli account utente appropriati:</span><span class="sxs-lookup"><span data-stu-id="19fc0-207">Use these steps to add the location and activate licenses for the appropriate user accounts:</span></span>
  
1. <span data-ttu-id="19fc0-208">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com)e quindi fare clic su **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="19fc0-208">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com), and then click **Admin**.</span></span>
    
2. <span data-ttu-id="19fc0-209">Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="19fc0-209">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="19fc0-210">Nell’elenco degli account utente, selezionare la casella di controllo accanto all'utente che si desidera attivare.</span><span class="sxs-lookup"><span data-stu-id="19fc0-210">In the list of user accounts, select the check box next to the user you want to activate.</span></span>
    
4. <span data-ttu-id="19fc0-211">Nella pagina dell'utente fare clic su **Modifica** per **Licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="19fc0-211">On the page for the user, click **Edit** for **Product licenses**.</span></span>
    
5. <span data-ttu-id="19fc0-212">Nella pagina **Licenze di prodotto** selezionare un percorso per l'utente per **Percorso**, quindi abilitare le licenze appropriate per l'utente.</span><span class="sxs-lookup"><span data-stu-id="19fc0-212">On the **Product licenses** page, select a location for the user for **Location**, and then enable the appropriate licenses for the user.</span></span>
    
6. <span data-ttu-id="19fc0-213">Al termine dell'operazione, fare clic su **Salva** e fare clic due volte su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="19fc0-213">When complete, click **Save**, and then click **Close** twice.</span></span>
    
7. <span data-ttu-id="19fc0-214">Tornare al passaggio 3 per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="19fc0-214">Go back to step 3 for additional users.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="19fc0-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19fc0-215">See also</span></span>

[<span data-ttu-id="19fc0-216">Microsoft 365 Solution and Architecture Center</span><span class="sxs-lookup"><span data-stu-id="19fc0-216">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)
  
[<span data-ttu-id="19fc0-217">Connettere una rete locale a una rete virtuale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="19fc0-217">Connect an on-premises network to a Microsoft Azure virtual network</span></span>](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[<span data-ttu-id="19fc0-218">Scaricare Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="19fc0-218">Download Azure AD Connect</span></span>](https://www.microsoft.com/download/details.aspx?id=47594)
  
[<span data-ttu-id="19fc0-219">Configurare la sincronizzazione della directory per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19fc0-219">Set up directory synchronization for Microsoft 365</span></span>](set-up-directory-synchronization.md)
  
