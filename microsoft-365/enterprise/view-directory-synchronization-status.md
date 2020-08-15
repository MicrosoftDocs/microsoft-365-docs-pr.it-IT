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
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691294"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="52a50-103">Visualizzare lo stato di sincronizzazione della directory in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52a50-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="52a50-104">Se è stata integrata Active Directory locale con Azure AD sincronizzando l'ambiente locale con Microsoft 365, è anche possibile controllare lo stato della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="52a50-104">If you have integrated your on-premises Active Directory with Azure AD by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="52a50-105">Visualizzare lo stato della sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="52a50-105">View directory synchronization status</span></span>

- <span data-ttu-id="52a50-106">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) e scegliere **stato dirsync** nella Home page.</span><span class="sxs-lookup"><span data-stu-id="52a50-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="52a50-107">In alternativa, è possibile accedere agli utenti attivi **degli utenti** \> **Active users**, quindi nella pagina **utenti attivi** scegliere **altre** \> **sincronizzazione della directory**.</span><span class="sxs-lookup"><span data-stu-id="52a50-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="52a50-108">Nel riquadro di **sincronizzazione della directory** scegliere **Vai a gestione dirsync**.</span><span class="sxs-lookup"><span data-stu-id="52a50-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="52a50-109">Informazioni sulla pagina Gestisci sincronizzazione directory</span><span class="sxs-lookup"><span data-stu-id="52a50-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="52a50-110">Nella tabella seguente sono elencate le funzionalità che consentono di ottenere informazioni sulla pagina.</span><span class="sxs-lookup"><span data-stu-id="52a50-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="52a50-111">Se si verifica un problema con la sincronizzazione della directory, anche gli errori sono elencati in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="52a50-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="52a50-112">Per ulteriori informazioni sui diversi errori che potrebbero verificarsi, vedere [identificare gli errori di sincronizzazione della directory in Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="52a50-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="52a50-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="52a50-113">**Item**</span></span>|<span data-ttu-id="52a50-114">**Scopo**</span><span class="sxs-lookup"><span data-stu-id="52a50-114">**What it's for**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52a50-115">**Domini verificati**</span><span class="sxs-lookup"><span data-stu-id="52a50-115">**Domains verified**</span></span> | <span data-ttu-id="52a50-116">Il numero di domini nel tenant Microsoft 365 verificato che si è proprietari.</span><span class="sxs-lookup"><span data-stu-id="52a50-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="52a50-117">**Domini non verificati**</span><span class="sxs-lookup"><span data-stu-id="52a50-117">**Domains not verified**</span></span> | <span data-ttu-id="52a50-118">Domini che sono stati aggiunti, ma non sono stati verificati.</span><span class="sxs-lookup"><span data-stu-id="52a50-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="52a50-119">**Sincronizzazione della directory attivata**</span><span class="sxs-lookup"><span data-stu-id="52a50-119">**Directory sync enabled**</span></span> |<span data-ttu-id="52a50-120">True o false.</span><span class="sxs-lookup"><span data-stu-id="52a50-120">True or False.</span></span> <span data-ttu-id="52a50-121">Specifica se è stata abilitata la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="52a50-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="52a50-122">**Sincronizzazione della directory più recente**</span><span class="sxs-lookup"><span data-stu-id="52a50-122">**Latest directory sync**</span></span> | <span data-ttu-id="52a50-123">Ultima esecuzione della sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="52a50-123">Last time directory sync ran.</span></span> <span data-ttu-id="52a50-124">Verrà visualizzato un messaggio di avviso e un collegamento a uno strumento per la risoluzione dei problemi se l'ultima sincronizzazione è stata più di tre giorni fa.</span><span class="sxs-lookup"><span data-stu-id="52a50-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="52a50-125">**Sincronizzazione password attivata**</span><span class="sxs-lookup"><span data-stu-id="52a50-125">**Password sync enabled**</span></span> | <span data-ttu-id="52a50-126">True o false.</span><span class="sxs-lookup"><span data-stu-id="52a50-126">True or False.</span></span> <span data-ttu-id="52a50-127">Specifica se si dispone della sincronizzazione hash delle password tra il tenant locale e quello Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52a50-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="52a50-128">**Sincronizzazione ultima password**</span><span class="sxs-lookup"><span data-stu-id="52a50-128">**Last Password Sync**</span></span> | <span data-ttu-id="52a50-129">L'ultima volta che è stata eseguita la sincronizzazione hash password.</span><span class="sxs-lookup"><span data-stu-id="52a50-129">Last time password hash sync ran.</span></span> <span data-ttu-id="52a50-130">Verrà visualizzato un messaggio di avviso e un collegamento a uno strumento per la risoluzione dei problemi se l'ultima sincronizzazione è stata più di tre giorni fa.</span><span class="sxs-lookup"><span data-stu-id="52a50-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="52a50-131">**Versione client di sincronizzazione della directory**</span><span class="sxs-lookup"><span data-stu-id="52a50-131">**Directory sync client version**</span></span> | <span data-ttu-id="52a50-132">Contiene un collegamento di download se è stata rilasciata una nuova versione di Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="52a50-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="52a50-133">**Account del servizio di sincronizzazione della directory**</span><span class="sxs-lookup"><span data-stu-id="52a50-133">**Directory sync service account**</span></span> | <span data-ttu-id="52a50-134">Visualizza il nome dell'account del servizio di sincronizzazione della directory Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52a50-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |