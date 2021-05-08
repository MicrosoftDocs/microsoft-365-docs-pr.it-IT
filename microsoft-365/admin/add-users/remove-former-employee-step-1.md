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
ms.openlocfilehash: 60f4cf6b5c9a0b5dc2023b3ef7b6460685142d07
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244250"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="d85be-103">Passaggio 1 - Impedire a un ex dipendente di accedere e bloccare l'accesso Microsoft 365 servizi</span><span class="sxs-lookup"><span data-stu-id="d85be-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="d85be-104">Se è necessario impedire immediatamente l'accesso di un utente, è consigliabile reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="d85be-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="d85be-105">In questo passaggio forzare la disconnessione dell'utente da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d85be-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

1. <span data-ttu-id="d85be-106">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="d85be-106">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d85be-107">Selezionare la casella accanto al nome dell'utente e quindi selezionare **Reimposta password.**</span><span class="sxs-lookup"><span data-stu-id="d85be-107">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="d85be-108">Immettere una nuova password e quindi selezionare **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="d85be-108">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="d85be-109">Non inviarlo a loro.</span><span class="sxs-lookup"><span data-stu-id="d85be-109">(Don't send it to them.)</span></span>
4. <span data-ttu-id="d85be-110">Selezionare il nome dell'utente per passare al riquadro delle proprietà e nella **scheda Account** selezionare **Avvia disconnessione.**</span><span class="sxs-lookup"><span data-stu-id="d85be-110">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="d85be-111">Entro un'ora o dopo aver lasciato la pagina Microsoft 365 corrente in cui si trova, viene richiesto di accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="d85be-111">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="d85be-112">Un token di accesso è valido per un'ora, quindi la sequenza temporale dipende dal tempo che rimane su quel token e dal fatto che si snavigare fuori dalla pagina Web corrente.</span><span class="sxs-lookup"><span data-stu-id="d85be-112">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d85be-113">Se l'utente è Outlook sul Web, basta fare clic nella propria cassetta postale, potrebbe non essere espulso immediatamente.</span><span class="sxs-lookup"><span data-stu-id="d85be-113">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="d85be-114">Non appena selezionano un riquadro diverso, ad esempio OneDrive o aggiornano il browser, viene avviata la disconnessione.</span><span class="sxs-lookup"><span data-stu-id="d85be-114">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="d85be-115">Per usare PowerShell per disconnettere immediatamente un utente, vedere il cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="d85be-115">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="d85be-116">Per altre informazioni sul tempo necessario per rimuovere un dipendente dalla posta elettronica, vedere [Cosa occorre sapere sulla chiusura delle sessione di posta elettronica di un dipendente](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="d85be-116">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="d85be-117">Bloccare l'accesso di un ex dipendente Microsoft 365 servizi</span><span class="sxs-lookup"><span data-stu-id="d85be-117">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="d85be-118">L'applicazione del blocco di un account può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="d85be-118">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="d85be-119">Se devi impedire immediatamente l'accesso di un utente, segui i passaggi precedenti e reimposta la password.</span><span class="sxs-lookup"><span data-stu-id="d85be-119">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="d85be-120">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="d85be-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="d85be-121">Selezionare il nome del dipendente che si desidera bloccare e, sotto il nome dell'utente, selezionare il simbolo **per Blocca questo utente.**</span><span class="sxs-lookup"><span data-stu-id="d85be-121">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="d85be-122">Seleziona **Blocca l'accesso dell'utente** e quindi seleziona **Salva.**</span><span class="sxs-lookup"><span data-stu-id="d85be-122">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="d85be-123">Bloccare l'accesso alla posta elettronica (Exchange Online) di un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="d85be-123">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="d85be-124">Se hai posta elettronica come parte dell'abbonamento Microsoft 365, accedi all'interfaccia di amministrazione di Exchange e segui questa procedura per impedire all'ex dipendente di accedere alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d85be-124">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="d85be-125">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="d85be-125">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="d85be-126">Nell'Interfaccia di amministrazione di Exchange passare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="d85be-126">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="d85be-127">Fare doppio clic sull'utente e passare alla **pagina Funzionalità cassetta** postale.</span><span class="sxs-lookup"><span data-stu-id="d85be-127">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="d85be-128">In **Dispositivi mobili** seleziona **Disabilita** Exchange ActiveSync e Disabilita OWA per i dispositivi **e** rispondi **Sì** a entrambi quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="d85be-128">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="d85be-129">In **Connettività posta** elettronica selezionare **Disabilita** e rispondi **Sì** quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="d85be-129">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
