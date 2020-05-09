---
title: Consentire agli utenti di reimpostare le loro password
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Informazioni su come è possibile reimpostare le password utilizzando lo strumento di reimpostazione della password self-service.
ms.openlocfilehash: 01099f6f678bbaa3b163ac59e0417614352e0e97
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173531"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="bee45-103">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="bee45-103">Let users reset their own passwords</span></span>

<span data-ttu-id="bee45-104">Cosa fare per non ricevere più richieste di modifica delle password degli utenti?</span><span class="sxs-lookup"><span data-stu-id="bee45-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="bee45-105">Come amministratore di Microsoft 365, è possibile consentire agli utenti di utilizzare lo [strumento di reimpostazione della password in modalità self-service](https://go.microsoft.com/fwlink/p/?LinkId=522677) in modo che non sia necessario reimpostare le password.</span><span class="sxs-lookup"><span data-stu-id="bee45-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="bee45-106">Un gran risparmio di tempo!</span><span class="sxs-lookup"><span data-stu-id="bee45-106">Less work for you!</span></span> 
  
<span data-ttu-id="bee45-107">Ecco alcune informazioni utili:</span><span class="sxs-lookup"><span data-stu-id="bee45-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="bee45-108">Si ottiene la reimpostazione della password in modalità self-service per gli utenti Cloud **gratis** con qualsiasi piano di Microsoft 365 business, Education o no profit paid.</span><span class="sxs-lookup"><span data-stu-id="bee45-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="bee45-109">Non funziona con Microsoft 365 Trial.</span><span class="sxs-lookup"><span data-stu-id="bee45-109">It doesn't work with Microsoft 365 trial.</span></span> 
    
- <span data-ttu-id="bee45-p103">Si basa su Azure. Questa funzionalità verrà scaricata automaticamente e **gratuitamente** in Azure quando si esegue questa procedura. L'attivazione della reimpostazione della password in modalità self-service non costa nulla se non si usano altre funzionalità di Azure.</span><span class="sxs-lookup"><span data-stu-id="bee45-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="bee45-113">**Se si utilizza Active Directory locale**, non si applicano i due punti sopra riportati.</span><span class="sxs-lookup"><span data-stu-id="bee45-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="bee45-114">Piuttosto, è possibile configurare questa impostazione, ma **richiede un abbonamento a pagamento ad Azure ad Premium**.</span><span class="sxs-lookup"><span data-stu-id="bee45-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="bee45-115">Guardare un breve video su come consentire agli utenti di reimpostare le proprie password.</span><span class="sxs-lookup"><span data-stu-id="bee45-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="bee45-116">Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="bee45-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="bee45-117">Consentire alle persone di reimpostare le proprie password</span><span class="sxs-lookup"><span data-stu-id="bee45-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="bee45-118">Con questi passaggi si attiva la reimpostazione della password in modalità self-service per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="bee45-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1. <span data-ttu-id="bee45-119">Nell'interfaccia di amministrazione passare <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">alla pagina</a> impostazioni **Impostazioni** \> .</span><span class="sxs-lookup"><span data-stu-id="bee45-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bee45-120">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>passare alla pagina **Impostazioni** \> \*\*privacy sicurezza &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="bee45-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bee45-121">Nell'interfaccia <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">di amministrazione</a>passare alla **pagina impostazioni di** \> \*\*sicurezza &amp; \*\* **per la** \>privacy delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="bee45-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="bee45-122">Nella parte superiore della pagina Impostazioni selezionare **sicurezza & privacy**.</span><span class="sxs-lookup"><span data-stu-id="bee45-122">At the top of the Settings page select **Security & Privacy**.</span></span>
  
3. <span data-ttu-id="bee45-123">Selezionare la **reimpostazione della password self-service**.</span><span class="sxs-lookup"><span data-stu-id="bee45-123">Select **Self Service Password Reset**.</span></span>
  
4. <span data-ttu-id="bee45-124">Nella pagina delle proprietà, selezionare **tutto** per attivarlo per tutti gli utenti dell'azienda, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bee45-124">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="bee45-125">Quando gli utenti accedono, verrà richiesto di immettere ulteriori informazioni di contatto che consentiranno di reimpostare la password in futuro.</span><span class="sxs-lookup"><span data-stu-id="bee45-125">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bee45-126">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="bee45-126">Related articles</span></span>

[<span data-ttu-id="bee45-127">Impostare i criteri di scadenza delle password per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bee45-127">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="bee45-128">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="bee45-128">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="bee45-129">Video per la formazione di Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="bee45-129">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
