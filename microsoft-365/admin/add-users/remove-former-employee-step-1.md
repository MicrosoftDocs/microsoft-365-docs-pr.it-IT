---
title: 'Passaggio 1: impedire a un dipendente di accedere a Microsoft 365'
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
description: Impedire a un ex dipendente di accedere e bloccare l'accesso Microsoft 365 servizi.
ms.openlocfilehash: cdba6dcaf239e94cf33f3bf88e7f217b4793bfd6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840851"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="3b5ba-103">Passaggio 1 - Impedire a un ex dipendente di accedere e bloccare l'accesso Microsoft 365 servizi</span><span class="sxs-lookup"><span data-stu-id="3b5ba-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="3b5ba-104">Se è necessario impedire immediatamente l'accesso di un utente, è consigliabile reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="3b5ba-105">In questo passaggio forzare la disconnessione dell'utente da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="3b5ba-106">È necessario essere un amministratore globale per avviare la disconnessione per altri amministratori.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="3b5ba-107">Per gli utenti non amministratori, è possibile utilizzare un amministratore utente o un utente amministratore dell'helpdesk per eseguire questa azione.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="3b5ba-108">Altre informazioni sui ruoli di amministratore</span><span class="sxs-lookup"><span data-stu-id="3b5ba-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="3b5ba-109">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b5ba-110">Selezionare la casella accanto al nome dell'utente e quindi selezionare **Reimposta password.**</span><span class="sxs-lookup"><span data-stu-id="3b5ba-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="3b5ba-111">Immettere una nuova password e quindi selezionare **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="3b5ba-112">Non inviarlo a loro.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="3b5ba-113">Selezionare il nome dell'utente per passare al riquadro delle proprietà e nella **scheda Account** selezionare **Avvia disconnessione.**</span><span class="sxs-lookup"><span data-stu-id="3b5ba-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="3b5ba-114">Entro un'ora o dopo aver lasciato la pagina Microsoft 365 corrente in cui si trova, viene richiesto di accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="3b5ba-115">Un token di accesso è valido per un'ora, quindi la sequenza temporale dipende dal tempo che rimane su quel token e dal fatto che si snavigare fuori dalla pagina Web corrente.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b5ba-116">Se l'utente è Outlook sul Web, basta fare clic nella propria cassetta postale, potrebbe non essere espulso immediatamente.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="3b5ba-117">Non appena selezionano un riquadro diverso, ad esempio OneDrive o aggiornano il browser, viene avviata la disconnessione.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="3b5ba-118">Per usare PowerShell per disconnettere immediatamente un utente, vedere il cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="3b5ba-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="3b5ba-119">Per altre informazioni sul tempo necessario per rimuovere un dipendente dalla posta elettronica, vedere [Cosa occorre sapere sulla chiusura delle sessione di posta elettronica di un dipendente](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="3b5ba-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="3b5ba-120">Bloccare l'accesso di un ex dipendente Microsoft 365 servizi</span><span class="sxs-lookup"><span data-stu-id="3b5ba-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="3b5ba-121">L'applicazione del blocco di un account può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="3b5ba-122">Se devi impedire immediatamente l'accesso di un utente, segui i passaggi precedenti e reimposta la password.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="3b5ba-123">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3b5ba-124">Selezionare il nome del dipendente che si desidera bloccare e, sotto il nome dell'utente, selezionare il simbolo **per Blocca questo utente.**</span><span class="sxs-lookup"><span data-stu-id="3b5ba-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="3b5ba-125">Seleziona **Blocca l'accesso dell'utente** e quindi seleziona **Salva.**</span><span class="sxs-lookup"><span data-stu-id="3b5ba-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="3b5ba-126">Bloccare l'accesso alla posta elettronica (Exchange Online) di un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="3b5ba-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="3b5ba-127">Se hai posta elettronica come parte dell'abbonamento Microsoft 365, accedi all'interfaccia di amministrazione di Exchange e segui questa procedura per impedire all'ex dipendente di accedere alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="3b5ba-128">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="3b5ba-129">Nell'Interfaccia di amministrazione di Exchange passare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="3b5ba-130">Fare doppio clic sull'utente e passare alla **pagina Funzionalità cassetta** postale.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-130">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="3b5ba-131">In **Dispositivi mobili** seleziona **Disabilita** Exchange ActiveSync e Disabilita OWA per i dispositivi **e** rispondi **Sì** a entrambi quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-131">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="3b5ba-132">In **Connettività posta** elettronica selezionare **Disabilita** e rispondi **Sì** quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="3b5ba-132">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
