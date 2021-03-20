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
description: Informazioni sul consenso dell'utente alle app e su come attivarle per consentire alle app di terze parti di accedere alle informazioni di Microsoft 365 degli utenti.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914559"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="b3328-103">Gestione del consenso degli utenti alle app in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3328-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="b3328-104">Questa impostazione controlla se gli utenti possono concedere il consenso alle app che usano OpenID Connect e OAuth 2.0 per l'accesso e le richieste di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="b3328-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="b3328-105">Un'app può essere creata dall'organizzazione oppure da un'altra organizzazione di Office 365 o da terze parti.</span><span class="sxs-lookup"><span data-stu-id="b3328-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="b3328-106">Se attivi questa impostazione, queste app chiederanno agli utenti l'autorizzazione per accedere ai dati dell'organizzazione e gli utenti possono scegliere se consentirla.</span><span class="sxs-lookup"><span data-stu-id="b3328-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="b3328-107">Se distoglie questa impostazione, gli amministratori devono acconsentire a tali app prima che gli utenti possano usarle.</span><span class="sxs-lookup"><span data-stu-id="b3328-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="b3328-108">In questo caso, è consigliabile configurare un flusso di lavoro di consenso dell'amministratore nel portale di Azure in modo che gli utenti possano inviare una richiesta di approvazione dell'amministratore per usare qualsiasi app bloccata.</span><span class="sxs-lookup"><span data-stu-id="b3328-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="b3328-109">Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3328-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="b3328-110">Non può invece concedere l'accesso alle informazioni degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="b3328-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="b3328-111">Attivazione o disattivazione del consenso dell'utente</span><span class="sxs-lookup"><span data-stu-id="b3328-111">Turning user consent on or off</span></span>
<span data-ttu-id="b3328-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="b3328-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="b3328-113">Ecco come attivare o disattivare il consenso dell'utente per le app.</span><span class="sxs-lookup"><span data-stu-id="b3328-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="b3328-114">Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** \> **impostazioni organizzazione**  >  [Servizi](https://go.microsoft.com/fwlink/p/?linkid=2053743) e quindi selezionare Consenso **utente per le app**.</span><span class="sxs-lookup"><span data-stu-id="b3328-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="b3328-115">Nella pagina **Consenso utente alle app** seleziona l'opzione per attivare o disattivare il consenso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b3328-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="b3328-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b3328-116">More info</span></span>
<span data-ttu-id="b3328-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="b3328-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="b3328-118">Per informazioni su come configurare le impostazioni di consenso in Azure Active Directory, vedere [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="b3328-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="b3328-119">Per informazioni sulla gestione del consenso degli utenti alle app, vedere Gestione del consenso alle [applicazioni e valutazione delle richieste di consenso.](/azure/active-directory/manage-apps/manage-consent-requests)</span><span class="sxs-lookup"><span data-stu-id="b3328-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span></span>