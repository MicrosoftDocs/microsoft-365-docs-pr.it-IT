---
title: Passaggio 7 - Eliminare l'account utente di un ex dipendente
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Seguire questa procedura per eliminare l'account utente di un ex dipendente.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244235"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="f408a-103">Passaggio 7 - Eliminare l'account utente di un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="f408a-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="f408a-104">Dopo il salvataggio e l'accesso ai dati utente dell'ex dipendente, è possibile eliminare l'account corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f408a-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f408a-p101">Non eliminare l'account se è stato configurato l'inoltro della posta elettronica o se l'account è stato convertito in una cassetta postale condivisa. In entrambi i casi è necessario l'account per ancorare l'inoltro o la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f408a-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="f408a-107">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="f408a-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f408a-108">Selezionare il nome del dipendente che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="f408a-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="f408a-109">Sotto il nome dell'utente, selezionare **Elimina utente.**</span><span class="sxs-lookup"><span data-stu-id="f408a-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="f408a-110">Scegliere le opzioni desiderate per l'utente e quindi selezionare **Elimina utente.**</span><span class="sxs-lookup"><span data-stu-id="f408a-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="f408a-111">Se hai già fornito a un altro utente l'accesso alla posta elettronica e OneDrive di questo utente, non è necessario farlo di nuovo qui.</span><span class="sxs-lookup"><span data-stu-id="f408a-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="f408a-p103">Quando si elimina un utente, il suo account diventa inattivo per circa 30 giorni. Si ha quindi a disposizione questo periodo di tempo per ripristinare l'account prima che venga eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="f408a-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="f408a-114">L'organizzazione usa Active Directory?</span><span class="sxs-lookup"><span data-stu-id="f408a-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="f408a-115">Se l'organizzazione sincronizza gli account utente Microsoft 365 da un ambiente Active Directory locale, è necessario eliminare e ripristinare tali account utente nel servizio Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="f408a-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="f408a-116">Non è possibile eliminarli o ripristinarli in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f408a-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="f408a-117">Per informazioni su come eliminare e ripristinare un account utente in Active Directory, vedere [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="f408a-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="f408a-118">Se si usa Azure Active Directory, vedere il cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f408a-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="f408a-119">Cosa occorre sapere sulla chiusura delle sessione di posta elettronica di un dipendente</span><span class="sxs-lookup"><span data-stu-id="f408a-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="f408a-120">Informazioni su come rimuovere un dipendente dalla posta elettronica (Exchange).</span><span class="sxs-lookup"><span data-stu-id="f408a-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f408a-121">**Cosa è possibile fare**</span><span class="sxs-lookup"><span data-stu-id="f408a-121">**What you can do**</span></span> <br/> |<span data-ttu-id="f408a-122">**Come farlo**</span><span class="sxs-lookup"><span data-stu-id="f408a-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="f408a-123">Terminare una sessione (ad esempio Outlook sul Web, Outlook, Exchange ActiveSync e così via) e forzare l'apertura di una nuova sessione</span><span class="sxs-lookup"><span data-stu-id="f408a-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="f408a-124">Reimpostare la password</span><span class="sxs-lookup"><span data-stu-id="f408a-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="f408a-125">Terminare una sessione e bloccare l'accesso a sessioni future (per tutti i protocolli)</span><span class="sxs-lookup"><span data-stu-id="f408a-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="f408a-126">Disabilitare l'account.</span><span class="sxs-lookup"><span data-stu-id="f408a-126">Disable the account.</span></span> <span data-ttu-id="f408a-127">Ad esempio, (nell'interfaccia di Exchange o usando PowerShell):</span><span class="sxs-lookup"><span data-stu-id="f408a-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="f408a-128">Terminare la sessione per un particolare protocollo, ad esempio ActiveSync</span><span class="sxs-lookup"><span data-stu-id="f408a-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="f408a-129">Disabilitare il protocollo.</span><span class="sxs-lookup"><span data-stu-id="f408a-129">Disable the protocol.</span></span> <span data-ttu-id="f408a-130">Ad esempio, (nell'interfaccia di Exchange o usando PowerShell):</span><span class="sxs-lookup"><span data-stu-id="f408a-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="f408a-131">Le operazioni precedenti possono essere eseguite in tre posizioni:</span><span class="sxs-lookup"><span data-stu-id="f408a-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f408a-132">**Se si termina la sessione qui**</span><span class="sxs-lookup"><span data-stu-id="f408a-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="f408a-133">**Quanto tempo occorre**</span><span class="sxs-lookup"><span data-stu-id="f408a-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="f408a-134">Nell'interfaccia di amministrazione di Exchange o con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f408a-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="f408a-135">Il ritardo massimo previsto è di 30 minuti</span><span class="sxs-lookup"><span data-stu-id="f408a-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="f408a-136">Nell'interfaccia di amministrazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f408a-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="f408a-137">Il ritardo previsto è di 60 minuti</span><span class="sxs-lookup"><span data-stu-id="f408a-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="f408a-138">In un ambiente locale</span><span class="sxs-lookup"><span data-stu-id="f408a-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="f408a-139">Il ritardo previsto è di 3 ore o più</span><span class="sxs-lookup"><span data-stu-id="f408a-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="f408a-140">Come ottenere la risposta più rapida per la chiusura di un account</span><span class="sxs-lookup"><span data-stu-id="f408a-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="f408a-p107">**Metodo più rapido**: usare l'interfaccia di amministrazione di Exchange (usare PowerShell) oppure l'interfaccia di amministrazione di Azure Active Directory. In un ambiente locale, la sincronizzazione delle modifiche con DirSync può richiedere diverse ore.</span><span class="sxs-lookup"><span data-stu-id="f408a-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="f408a-p108">**Metodo più rapido per utenti con presenza locale e nel data center di Exchange**: terminare la sessione con l'interfaccia di amministrazione di Exchange o di Azure Active Directory E apportare le modifiche anche nell'ambiente locale. In caso contrario, le modifiche nell'interfaccia di amministrazione di Exchange o di Azure Active Directory verranno sovrascritte da DirSync.</span><span class="sxs-lookup"><span data-stu-id="f408a-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f408a-145">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="f408a-145">Related articles</span></span>

[<span data-ttu-id="f408a-146">Ripristinare un utente</span><span class="sxs-lookup"><span data-stu-id="f408a-146">Restore a user</span></span>](restore-user.md)
