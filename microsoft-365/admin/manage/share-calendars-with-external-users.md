---
title: Condividere calendari con utenti esterni
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Informazioni su come consentire agli utenti di condividere i propri calendari con utenti esterni per riunioni e appuntamenti.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760055"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="bdca9-103">Condividere calendari con utenti esterni</span><span class="sxs-lookup"><span data-stu-id="bdca9-103">Share calendars with external users</span></span>

<span data-ttu-id="bdca9-104">A volte gli utenti devono pianificare riunioni con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bdca9-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="bdca9-105">Per semplificare il processo di individuazione degli orari delle riunioni comuni, Microsoft 365 consente di rendere i calendari disponibili per queste persone.</span><span class="sxs-lookup"><span data-stu-id="bdca9-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="bdca9-106">Si tratta di persone che devono visualizzare gli orari di disponibilità per gli utenti dell'organizzazione, ma non hanno account utente per l'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdca9-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="bdca9-107">È possibile abilitare la condivisione del calendario per tutti gli utenti dell'organizzazione nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdca9-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bdca9-108">Una volta abilitata la condivisione, gli utenti possono utilizzare Outlook Web App per condividere i propri calendari con chiunque all'interno o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bdca9-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="bdca9-109">Gli utenti all'interno dell'organizzazione possono visualizzare il calendario condiviso insieme al proprio calendario.</span><span class="sxs-lookup"><span data-stu-id="bdca9-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="bdca9-110">Agli utenti esterni all'organizzazione verrà inviato un URL che può essere utilizzato per visualizzare il calendario.</span><span class="sxs-lookup"><span data-stu-id="bdca9-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="bdca9-111">Gli utenti dell'organizzazione decidono quando condividere e quanto condividere.</span><span class="sxs-lookup"><span data-stu-id="bdca9-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="bdca9-112">Se si desidera condividere i calendari con un'organizzazione che utilizza Exchange Server 2013 (una soluzione locale), l'amministratore di Exchange dovrà impostare una relazione di autenticazione con il cloud.</span><span class="sxs-lookup"><span data-stu-id="bdca9-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="bdca9-113">Questa operazione è nota come federazione e deve soddisfare i requisiti software minimi.</span><span class="sxs-lookup"><span data-stu-id="bdca9-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="bdca9-114">Per [ulteriori informazioni,](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) vedere Condivisione.</span><span class="sxs-lookup"><span data-stu-id="bdca9-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="bdca9-115">Abilitare la condivisione del calendario tramite l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bdca9-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="bdca9-116">Nell'interfaccia di amministrazione passare a **Impostazioni** \> **organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="bdca9-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="bdca9-117">Nella scheda **Servizi** selezionare **Calendario.**</span><span class="sxs-lookup"><span data-stu-id="bdca9-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="bdca9-118">Nella pagina **Calendario** scegliere se consentire agli utenti di condividere i propri calendari con persone esterne all'organizzazione che dispongono di Microsoft 365 o Exchange.</span><span class="sxs-lookup"><span data-stu-id="bdca9-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="bdca9-119">Scegliere se consentire agli utenti anonimi (utenti senza credenziali) di accedere ai calendari tramite un invito tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bdca9-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="bdca9-120">Scegliere il tipo di informazioni del calendario da rendere disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="bdca9-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="bdca9-121">È possibile consentire tutte le informazioni o limitarlo solo all'ora o solo all'ora, all'oggetto e alla posizione.</span><span class="sxs-lookup"><span data-stu-id="bdca9-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="bdca9-122">Invitare utenti ad accedere ai calendari</span><span class="sxs-lookup"><span data-stu-id="bdca9-122">Invite people to access calendars</span></span>

<span data-ttu-id="bdca9-123">Una volta abilitata la condivisione, i proprietari del calendario possono estendere gli inviti a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="bdca9-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="bdca9-124">Per istruzioni, vedere [Condivisione del calendario in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span><span class="sxs-lookup"><span data-stu-id="bdca9-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>