---
title: Gestione del consenso degli utenti alle app in Microsoft 365
f1.keywords:
- CSH
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
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Informazioni sul consenso degli utenti per le app e su come attivarle per consentire alle app di terze parti di accedere all'informazione Microsoft 365.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999572"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="c5287-103">Gestione del consenso degli utenti alle app in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5287-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="c5287-104">Questa impostazione consente di controllare se gli utenti possono concedere il consenso alle app che utilizzano OpenID Connect e OAuth 2,0 per l'accesso e le richieste di accedere ai dati.</span><span class="sxs-lookup"><span data-stu-id="c5287-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="c5287-105">Un'app può essere creata dall'interno dell'organizzazione oppure può provenire da un'altra organizzazione di Office 365 o da terze parti.</span><span class="sxs-lookup"><span data-stu-id="c5287-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="c5287-106">Se si attiva questa impostazione, tali app richiederanno agli utenti l'autorizzazione per accedere ai dati dell'organizzazione e gli utenti possono scegliere se consentirli.</span><span class="sxs-lookup"><span data-stu-id="c5287-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="c5287-107">Se questa impostazione viene disattivata, gli amministratori devono acconsentire a tali app prima che gli utenti possano usarli.</span><span class="sxs-lookup"><span data-stu-id="c5287-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="c5287-108">In questo caso, prendere in considerazione la configurazione di un flusso di lavoro di consenso dell'amministratore nel portale di Azure in modo che gli utenti possano inviare una richiesta di approvazione dell'amministratore per l'utilizzo di qualsiasi applicazione bloccata.</span><span class="sxs-lookup"><span data-stu-id="c5287-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="c5287-109">Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5287-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="c5287-110">Non può invece concedere l'accesso alle informazioni degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="c5287-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="c5287-111">Attivazione o disattivazione del consenso dell'utente</span><span class="sxs-lookup"><span data-stu-id="c5287-111">Turning user consent on or off</span></span>
<span data-ttu-id="c5287-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="c5287-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="c5287-113">Ecco come abilitare o disabilitare l'autorizzazione utente per le app.</span><span class="sxs-lookup"><span data-stu-id="c5287-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="c5287-114">Nell'interfaccia di amministrazione, passare alla pagina **Impostazioni** \> **org Settings**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) , quindi selezionare **consenso utente per le app**.</span><span class="sxs-lookup"><span data-stu-id="c5287-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="c5287-115">Nella pagina **autorizzazioni utente per le app** selezionare l'opzione per abilitare o disabilitare il consenso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c5287-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="c5287-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c5287-116">More info</span></span>
<span data-ttu-id="c5287-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="c5287-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="c5287-118">Per informazioni su come configurare le impostazioni di consenso in Azure Active Directory, leggere [configurare il flusso di lavoro di approvazione dell'amministratore](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="c5287-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="c5287-119">Per ulteriori informazioni sulla gestione del consenso degli utenti alle app, vedere [Managing consenso to Applications and valutare le richieste di consenso](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="c5287-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>