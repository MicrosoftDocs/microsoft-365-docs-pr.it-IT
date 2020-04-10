---
title: Consentire agli utenti di reimpostare le loro password in Office 365
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
ms.openlocfilehash: 666d3843f7917cf9bd5718c0ce29f87f93d6effe
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211896"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="33a1e-103">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="33a1e-103">Let users reset their own passwords</span></span>

<span data-ttu-id="33a1e-104">Cosa fare per non ricevere più richieste di modifica delle password degli utenti?</span><span class="sxs-lookup"><span data-stu-id="33a1e-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="33a1e-105">Come amministratore di Microsoft 365, è possibile consentire agli utenti di utilizzare lo [strumento di reimpostazione della password in modalità self-service](https://go.microsoft.com/fwlink/p/?LinkId=522677) in modo che non sia necessario reimpostare le password.</span><span class="sxs-lookup"><span data-stu-id="33a1e-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="33a1e-106">Un gran risparmio di tempo!</span><span class="sxs-lookup"><span data-stu-id="33a1e-106">Less work for you!</span></span> 
  
<span data-ttu-id="33a1e-107">Ecco alcune informazioni utili:</span><span class="sxs-lookup"><span data-stu-id="33a1e-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="33a1e-p102">Con tutti i piani a pagamento di Office 365 Business, Education o Nonprofit, agli utenti viene fornita **gratuitamente** l'opzione di reimpostazione della password in modalità self-service. Questa opzione non funziona con la versione di valutazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="33a1e-p102">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan. It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="33a1e-p103">Si basa su Azure. Questa funzionalità verrà scaricata automaticamente e **gratuitamente** in Azure quando si esegue questa procedura. L'attivazione della reimpostazione della password in modalità self-service non costa nulla se non si usano altre funzionalità di Azure.</span><span class="sxs-lookup"><span data-stu-id="33a1e-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="33a1e-113">**Se si utilizza Active Directory locale**, non si applicano i due punti sopra riportati.</span><span class="sxs-lookup"><span data-stu-id="33a1e-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="33a1e-114">Piuttosto, è possibile configurare questa impostazione, ma **richiede un abbonamento a pagamento ad Azure ad Premium**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="33a1e-115">Guardare un breve video su come consentire agli utenti di reimpostare le proprie password.</span><span class="sxs-lookup"><span data-stu-id="33a1e-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="33a1e-116">Se il video è stato utile, vedere la [serie di corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="33a1e-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="33a1e-117">Consentire alle persone di reimpostare le proprie password</span><span class="sxs-lookup"><span data-stu-id="33a1e-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="33a1e-118">Con questi passaggi si attiva la reimpostazione della password in modalità self-service per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="33a1e-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="33a1e-119">Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">protezione & privacy</a> .</span><span class="sxs-lookup"><span data-stu-id="33a1e-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="33a1e-120">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>passare alla pagina **Impostazioni** \> \*\*privacy sicurezza &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="33a1e-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="33a1e-121">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>passare alla pagina **Impostazioni** \> \*\*privacy sicurezza &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="33a1e-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="33a1e-122">In **Consenti alle persone di reimpostare**le proprie password, selezionare il collegamento per l'interfaccia di **amministrazione di Azure ad**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="33a1e-123">Azure verrà scaricato gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="33a1e-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="33a1e-124">Selezionare **gli utenti** nella barra di spostamento sinistra, quindi selezionare **Reimposta password**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="33a1e-125">Nella pagina delle proprietà, selezionare **tutto** per attivarlo per tutti gli utenti dell'azienda, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="33a1e-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="33a1e-126">Quando gli utenti accedono a Office 365, verrà richiesto di immettere altre informazioni di contatto che gli consentiranno di reimpostare più facilmente la password in futuro.</span><span class="sxs-lookup"><span data-stu-id="33a1e-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="33a1e-127">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="33a1e-127">Related articles</span></span>

[<span data-ttu-id="33a1e-128">Impostare i criteri di scadenza delle password per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="33a1e-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="33a1e-129">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="33a1e-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="33a1e-130">Video per la formazione di Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="33a1e-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
