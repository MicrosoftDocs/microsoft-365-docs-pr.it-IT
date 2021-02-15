---
title: Gestire le sottoscrizioni di iscrizione self-service
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Informazioni su come gestire le sottoscrizioni di iscrizione self-service gratuite per l'organizzazione.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376306"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="f1d34-103">Gestire le sottoscrizioni di iscrizione self-service</span><span class="sxs-lookup"><span data-stu-id="f1d34-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="f1d34-104">Che cosa sono le sottoscrizioni di iscrizione self-service?</span><span class="sxs-lookup"><span data-stu-id="f1d34-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="f1d34-105">Per gli utenti dell'organizzazione è disponibile un numero limitato di sottoscrizioni di iscrizione self-service gratuite.</span><span class="sxs-lookup"><span data-stu-id="f1d34-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="f1d34-106">Un utente può iscriversi e usare una sottoscrizione di iscrizione self-service solo per se stesso.</span><span class="sxs-lookup"><span data-stu-id="f1d34-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="f1d34-107">Puoi gestire le sottoscrizioni di iscrizione self-service bloccando la registrazione degli utenti ed eliminando le sottoscrizioni gratuite a cui gli utenti hanno effettuato l'iscrizione.</span><span class="sxs-lookup"><span data-stu-id="f1d34-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="f1d34-108">Per ulteriori informazioni sull'iscrizione self-service e sulle sottoscrizioni disponibili, vedere [Using self-service sign up in your organization.](../../admin/misc/self-service-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="f1d34-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="f1d34-109">Visualizzare un elenco di sottoscrizioni di iscrizione self-service</span><span class="sxs-lookup"><span data-stu-id="f1d34-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="f1d34-110">Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="f1d34-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f1d34-111">Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Libero.**</span><span class="sxs-lookup"><span data-stu-id="f1d34-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="f1d34-112">Viene visualizzato un elenco di tutte le sottoscrizioni di iscrizione self-service.</span><span class="sxs-lookup"><span data-stu-id="f1d34-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="f1d34-113">In che modo queste sottoscrizioni sono diverse da quelle per gli acquisti in modalità self-service?</span><span class="sxs-lookup"><span data-stu-id="f1d34-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="f1d34-114">Le sottoscrizioni di iscrizione self-service sono gratuite e sono disponibili per un elenco di prodotti più ampio rispetto alle sottoscrizioni di acquisto self-service.</span><span class="sxs-lookup"><span data-stu-id="f1d34-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="f1d34-115">Quando un utente si i iscrizione a una sottoscrizione di acquisto self-service, è responsabile del pagamento.</span><span class="sxs-lookup"><span data-stu-id="f1d34-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="f1d34-116">Le sottoscrizioni per gli acquisti self-service sono disponibili solo per i prodotti Power Platform (Power BI, Power Apps e Power Automate), Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="f1d34-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="f1d34-117">Per ulteriori informazioni, vedere [Domande frequenti sugli acquisti self-service.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="f1d34-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="f1d34-118">Impedire agli utenti di registrarsi</span><span class="sxs-lookup"><span data-stu-id="f1d34-118">Block users from signing up</span></span>

<span data-ttu-id="f1d34-119">Utilizzare il cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) con il parametro **AllowAdHocSubscriptions** per controllare se gli utenti possono iscriversi per le sottoscrizioni di iscrizione self-service.</span><span class="sxs-lookup"><span data-stu-id="f1d34-119">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="f1d34-120">Per ulteriori informazioni, vedere [Come si controllano le impostazioni self-service?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="f1d34-120">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="f1d34-121">Eliminare una sottoscrizione di iscrizione self-service</span><span class="sxs-lookup"><span data-stu-id="f1d34-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1d34-122">Quando si elimina una sottoscrizione di iscrizione self-service, tutti gli utenti non possono accedere ai propri dati e messaggi di posta elettronica ed eliminare tutti i dati e i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f1d34-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="f1d34-123">Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="f1d34-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f1d34-124">Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Libero.**</span><span class="sxs-lookup"><span data-stu-id="f1d34-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="f1d34-125">Selezionare la sottoscrizione di iscrizione self-service che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="f1d34-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="f1d34-126">Nella sezione Sottoscrizioni e impostazioni di pagamento della pagina dei dettagli **dell'abbonamento** selezionare **Elimina sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="f1d34-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="f1d34-127">Nel riquadro **Elimina sottoscrizione** selezionare la casella di controllo, quindi selezionare **Elimina sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="f1d34-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="f1d34-128">Ho una sottoscrizione di iscrizione self-service che blocca l'eliminazione della directory</span><span class="sxs-lookup"><span data-stu-id="f1d34-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="f1d34-129">I prodotti di iscrizione self-service a cui i singoli utenti possono iscriversi possono anche creare un utente guest per l'autenticazione nella directory di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f1d34-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="f1d34-130">Per evitare la perdita di dati, questi prodotti self-service bloccano le eliminazioni della directory fino a quando non vengono eliminati completamente dalla directory.</span><span class="sxs-lookup"><span data-stu-id="f1d34-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="f1d34-131">Possono essere eliminati solo dall'amministratore di Azure AD. Per ulteriori informazioni, vedere [Eliminare una directory in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="f1d34-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>