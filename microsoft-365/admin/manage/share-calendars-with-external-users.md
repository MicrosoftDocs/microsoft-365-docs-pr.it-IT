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
description: 'Informazioni su come consentire agli utenti di condividere i propri calendari con utenti esterni per riunioni e appuntamenti. '
ms.openlocfilehash: 905280d3c23ffcb9fcf281c39b232a3d05ba1ec5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399567"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="6dccd-103">Condividere calendari con utenti esterni</span><span class="sxs-lookup"><span data-stu-id="6dccd-103">Share calendars with external users</span></span>

<span data-ttu-id="6dccd-104">Spesso capita di dover pianificare riunioni con utenti esterni alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dccd-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="6dccd-105">Per semplificare il processo di individuazione degli orari di riunione reciprocamente gradevoli, Microsoft 365 consente di rendere disponibili i calendari a "utenti esterni", a coloro che hanno necessità di visualizzare i tempi di disponibilità, ma non hanno account utente per l'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6dccd-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="6dccd-106">La condivisione del calendario è un'impostazione globale, ovvero l'amministratore può abilitarla per tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="6dccd-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="6dccd-107">Una volta abilitata la condivisione, gli utenti possono utilizzare Outlook Web App per condividere i propri calendari con chiunque sia all'interno che all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dccd-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="6dccd-108">Gli utenti all'interno dell'organizzazione possono visualizzare il calendario condiviso affiancato con il proprio.</span><span class="sxs-lookup"><span data-stu-id="6dccd-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="6dccd-109">Agli utenti esterni all'organizzazione verrà inviato un URL che può essere utilizzato per visualizzare il calendario.</span><span class="sxs-lookup"><span data-stu-id="6dccd-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="6dccd-110">Gli utenti decidono quando condividere, quanto condividere e quando mantenere privati i propri calendari.</span><span class="sxs-lookup"><span data-stu-id="6dccd-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6dccd-p103">Se si vogliono condividere i calendari con un'organizzazione che usa Exchange Server 2013 (una soluzione locale), l'amministratore di Exchange dovrà configurare una relazione di autenticazione con il cloud, ovvero una "federazione", che prevede una serie di requisiti minimi da soddisfare per il software. Per altre informazioni, vedere [Condivisione](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6dccd-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="6dccd-114">Abilitare la condivisione del calendario con l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6dccd-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6dccd-115">Nell' **interfaccia di amministrazione, andare a impostazioni** \> **organizzazione org**.</span><span class="sxs-lookup"><span data-stu-id="6dccd-115">In the admin center, go to **Settings** \> **Org Settings**.</span></span> 
    
2. <span data-ttu-id="6dccd-116">Nella scheda **Servizi** selezionare **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="6dccd-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="6dccd-117">Nella pagina **Calendario** che si apre, scegliere se si desidera consentire agli utenti di condividere i propri calendari con persone esterne all'organizzazione che dispongono di Microsoft 365 o Exchange.</span><span class="sxs-lookup"><span data-stu-id="6dccd-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="6dccd-118">Scegliere se si desidera consentire agli utenti anonimi (utenti senza credenziali di accesso) di accedere ai calendari tramite un invito di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6dccd-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="6dccd-119">Scegliere il tipo di informazioni del calendario da rendere disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dccd-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="6dccd-120">È possibile consentire l'accesso a tutte le informazioni oppure limitarlo solo al tempo, all'oggetto e alla posizione.</span><span class="sxs-lookup"><span data-stu-id="6dccd-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="6dccd-121">Invitare utenti ad accedere ai calendari</span><span class="sxs-lookup"><span data-stu-id="6dccd-121">Invite people to access calendars</span></span>

<span data-ttu-id="6dccd-p105">Dopo l'abilitazione della condivisione per il tenant, i proprietari dei calendari possono estendere gli inviti a utenti specifici. Per istruzioni, vedere [Condivisione del calendario in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx).</span><span class="sxs-lookup"><span data-stu-id="6dccd-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  
