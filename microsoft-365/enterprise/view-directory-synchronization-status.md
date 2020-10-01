---
title: Visualizzare lo stato di sincronizzazione della directory in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: In questo articolo, informazioni su come è possibile controllare lo stato della sincronizzazione della directory in Office 365.
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326950"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="fa744-103">Visualizzare lo stato di sincronizzazione della directory in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa744-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="fa744-104">Se sono stati integrati i servizi di dominio Active Directory (AD DS) locali con Azure Active Directory (Azure AD) sincronizzando l'ambiente locale con Microsoft 365, è anche possibile controllare lo stato della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa744-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="fa744-105">Visualizzare lo stato della sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="fa744-105">View directory synchronization status</span></span>

- <span data-ttu-id="fa744-106">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) e scegliere **stato dirsync** nella Home page.</span><span class="sxs-lookup"><span data-stu-id="fa744-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="fa744-107">In alternativa, è possibile accedere agli utenti attivi **degli utenti** \> **Active users**, quindi nella pagina **utenti attivi** scegliere **altre** \> **sincronizzazione della directory**.</span><span class="sxs-lookup"><span data-stu-id="fa744-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="fa744-108">Nel riquadro di **sincronizzazione della directory** scegliere **Vai a gestione dirsync**.</span><span class="sxs-lookup"><span data-stu-id="fa744-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="fa744-109">Informazioni sulla pagina Gestisci sincronizzazione directory</span><span class="sxs-lookup"><span data-stu-id="fa744-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="fa744-110">Nella tabella seguente sono elencate le funzionalità che consentono di ottenere informazioni sulla pagina.</span><span class="sxs-lookup"><span data-stu-id="fa744-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="fa744-111">Se si verifica un problema con la sincronizzazione della directory, anche gli errori sono elencati in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="fa744-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="fa744-112">Per ulteriori informazioni sui diversi errori che potrebbero verificarsi, vedere [identificare gli errori di sincronizzazione della directory in Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="fa744-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="fa744-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa744-113">Item</span></span>|<span data-ttu-id="fa744-114">Scopo</span><span class="sxs-lookup"><span data-stu-id="fa744-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa744-115">**Domini verificati**</span><span class="sxs-lookup"><span data-stu-id="fa744-115">**Domains verified**</span></span> | <span data-ttu-id="fa744-116">Il numero di domini nel tenant Microsoft 365 verificato che si è proprietari.</span><span class="sxs-lookup"><span data-stu-id="fa744-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="fa744-117">**Domini non verificati**</span><span class="sxs-lookup"><span data-stu-id="fa744-117">**Domains not verified**</span></span> | <span data-ttu-id="fa744-118">Domini che sono stati aggiunti, ma non sono stati verificati.</span><span class="sxs-lookup"><span data-stu-id="fa744-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="fa744-119">**Sincronizzazione della directory attivata**</span><span class="sxs-lookup"><span data-stu-id="fa744-119">**Directory sync enabled**</span></span> |<span data-ttu-id="fa744-120">True o false.</span><span class="sxs-lookup"><span data-stu-id="fa744-120">True or False.</span></span> <span data-ttu-id="fa744-121">Specifica se è stata abilitata la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="fa744-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="fa744-122">**Sincronizzazione della directory più recente**</span><span class="sxs-lookup"><span data-stu-id="fa744-122">**Latest directory sync**</span></span> | <span data-ttu-id="fa744-123">Ultima esecuzione della sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="fa744-123">Last time directory sync ran.</span></span> <span data-ttu-id="fa744-124">Verrà visualizzato un messaggio di avviso e un collegamento a uno strumento per la risoluzione dei problemi se l'ultima sincronizzazione è stata più di tre giorni fa.</span><span class="sxs-lookup"><span data-stu-id="fa744-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="fa744-125">**Sincronizzazione password attivata**</span><span class="sxs-lookup"><span data-stu-id="fa744-125">**Password sync enabled**</span></span> | <span data-ttu-id="fa744-126">True o false.</span><span class="sxs-lookup"><span data-stu-id="fa744-126">True or False.</span></span> <span data-ttu-id="fa744-127">Specifica se si dispone della sincronizzazione hash delle password tra il tenant locale e quello Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa744-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="fa744-128">**Sincronizzazione ultima password**</span><span class="sxs-lookup"><span data-stu-id="fa744-128">**Last Password Sync**</span></span> | <span data-ttu-id="fa744-129">L'ultima volta che è stata eseguita la sincronizzazione hash password.</span><span class="sxs-lookup"><span data-stu-id="fa744-129">Last time password hash sync ran.</span></span> <span data-ttu-id="fa744-130">Verrà visualizzato un messaggio di avviso e un collegamento a uno strumento per la risoluzione dei problemi se l'ultima sincronizzazione è stata più di tre giorni fa.</span><span class="sxs-lookup"><span data-stu-id="fa744-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="fa744-131">**Versione client di sincronizzazione della directory**</span><span class="sxs-lookup"><span data-stu-id="fa744-131">**Directory sync client version**</span></span> | <span data-ttu-id="fa744-132">Contiene un collegamento di download se è stata rilasciata una nuova versione di Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="fa744-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="fa744-133">**Account del servizio di sincronizzazione della directory**</span><span class="sxs-lookup"><span data-stu-id="fa744-133">**Directory sync service account**</span></span> | <span data-ttu-id="fa744-134">Visualizza il nome dell'account del servizio di sincronizzazione della directory Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa744-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="fa744-135">Monitorare l'integrità della sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="fa744-135">Monitor synchronization health</span></span>

<span data-ttu-id="fa744-136">In questa sezione verrà installato un agente di Azure AD Connect Health in ogni controller di dominio AD DS locale per monitorare l'infrastruttura di gestione delle identità e i servizi di sincronizzazione forniti da Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="fa744-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="fa744-137">Le informazioni sul monitoraggio vengono rese disponibili nel portale di Azure AD Connect Health, dove è possibile visualizzare avvisi, il monitoraggio delle prestazioni, analisi sull'utilizzo e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="fa744-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="fa744-138">La decisione di progettazione chiave su come usare Azure AD Connect Health si basa sul modo in cui si utilizza Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="fa744-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="fa744-139">Se si usa l'opzione **autenticazione gestita** iniziare con [Uso di Azure AD Connect Health con la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) per comprendere e configurare Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="fa744-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="fa744-140">Se si stanno sincronizzando soli i nomi di account e gruppi tramite l'**autenticazione federata** con Active Directory Federation Services (AD FS), iniziare con [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) per comprendere e configurare Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="fa744-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="fa744-141">Al termine, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa744-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="fa744-142">L'agente di Azure AD Connect Health è installato su ciascuno dei server del provider di identità locale.</span><span class="sxs-lookup"><span data-stu-id="fa744-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="fa744-143">Il portale di Azure AD Connect Health mostra lo stato corrente dell'infrastruttura locale e delle attività di sincronizzazione con il tenant di Azure AD per l’abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa744-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

