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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Informazioni su come è possibile reimpostare le password utilizzando lo strumento di reimpostazione della password self-service.
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780590"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="d6c73-103">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="d6c73-103">Let users reset their own passwords</span></span>

<span data-ttu-id="d6c73-104">Cosa fare per non ricevere più richieste di modifica delle password degli utenti?</span><span class="sxs-lookup"><span data-stu-id="d6c73-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="d6c73-105">Come amministratore di Microsoft 365, è possibile consentire agli utenti di utilizzare lo [strumento di reimpostazione della password in modalità self-service](https://go.microsoft.com/fwlink/p/?LinkId=522677) in modo che non sia necessario reimpostare le password.</span><span class="sxs-lookup"><span data-stu-id="d6c73-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="d6c73-106">Un gran risparmio di tempo!</span><span class="sxs-lookup"><span data-stu-id="d6c73-106">Less work for you!</span></span> 
  
<span data-ttu-id="d6c73-107">Ecco alcune informazioni utili:</span><span class="sxs-lookup"><span data-stu-id="d6c73-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="d6c73-108">Si ottiene la reimpostazione della password in modalità self-service per gli utenti Cloud **gratis** con qualsiasi piano di Microsoft 365 business, Education o no profit paid.</span><span class="sxs-lookup"><span data-stu-id="d6c73-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="d6c73-109">Non funziona con Microsoft 365 Trial.</span><span class="sxs-lookup"><span data-stu-id="d6c73-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="d6c73-110">It uses Azure.</span><span class="sxs-lookup"><span data-stu-id="d6c73-110">It uses Azure.</span></span> <span data-ttu-id="d6c73-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span><span class="sxs-lookup"><span data-stu-id="d6c73-111">You'll automatically get this feature in Azure for **free** when you do these steps.</span></span> <span data-ttu-id="d6c73-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span><span class="sxs-lookup"><span data-stu-id="d6c73-112">It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="d6c73-113">**Se si utilizza Active Directory locale**, non si applicano i due punti sopra riportati.</span><span class="sxs-lookup"><span data-stu-id="d6c73-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="d6c73-114">Piuttosto, è possibile configurare questa impostazione, ma **richiede un abbonamento a pagamento ad Azure ad Premium**.</span><span class="sxs-lookup"><span data-stu-id="d6c73-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="d6c73-115">Guardare un breve video su come consentire agli utenti di reimpostare le proprie password.</span><span class="sxs-lookup"><span data-stu-id="d6c73-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="d6c73-116">Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="d6c73-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="d6c73-117">Consentire alle persone di reimpostare le proprie password</span><span class="sxs-lookup"><span data-stu-id="d6c73-117">Let people reset their own passwords</span></span>

<span data-ttu-id="d6c73-118">Con questi passaggi si attiva la reimpostazione della password in modalità self-service per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="d6c73-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="d6c73-119">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a>, passare alla pagina **Impostazioni** > **org** Settings.</span><span class="sxs-lookup"><span data-stu-id="d6c73-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d6c73-120">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>passare alla pagina **Impostazioni** \> \*\* &amp; privacy sicurezza\*\* .</span><span class="sxs-lookup"><span data-stu-id="d6c73-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d6c73-121">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>passare alla pagina impostazioni di sicurezza **per la** \> **Settings** \> \*\* &amp; privacy\*\* delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d6c73-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="d6c73-122">Nella parte superiore della pagina **Impostazioni organizzazione** selezionare la scheda **protezione & privacy** .</span><span class="sxs-lookup"><span data-stu-id="d6c73-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="d6c73-123">Selezionare **reimpostazione della password in modalità self-service**.</span><span class="sxs-lookup"><span data-stu-id="d6c73-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="d6c73-124">In **reimpostazione della password self-service**selezionare **Vai al portale di Azure per abilitare la reimpostazione della password in modalità self-service**.</span><span class="sxs-lookup"><span data-stu-id="d6c73-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="d6c73-125">Nel riquadro di spostamento a sinistra, selezionare **utenti**e quindi fare clic su **utenti | Pagina tutti gli utenti** , selezionare **Reimposta password**.</span><span class="sxs-lookup"><span data-stu-id="d6c73-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="d6c73-126">Nella pagina delle **Proprietà** , selezionare **tutto** per attivarlo per tutti gli utenti dell'azienda, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d6c73-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="d6c73-127">Quando gli utenti accedono, verrà richiesto di immettere ulteriori informazioni di contatto che consentiranno di reimpostare la password in futuro.</span><span class="sxs-lookup"><span data-stu-id="d6c73-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d6c73-128">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="d6c73-128">Related articles</span></span>

[<span data-ttu-id="d6c73-129">Impostare i criteri di scadenza delle password per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d6c73-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="d6c73-130">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="d6c73-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="d6c73-131">Video per la formazione di Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="d6c73-131">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
