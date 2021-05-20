---
title: Consentire agli utenti di reimpostare le loro password
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Informazioni su come impostare un criterio per consentire agli utenti di reimpostare le proprie password utilizzando lo strumento di reimpostazione delle password self-service.
ms.openlocfilehash: 2c79d5611ab2db00f4de5f227b0ec2f411955558
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571854"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="1368a-103">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="1368a-103">Let users reset their own passwords</span></span>

<span data-ttu-id="1368a-104">In qualità Microsoft 365 amministratore, puoi lasciare che le persone [usino lo strumento di reimpostazione delle password self-service](https://go.microsoft.com/fwlink/p/?LinkId=522677) in modo da non doverle reimpostare le password.</span><span class="sxs-lookup"><span data-stu-id="1368a-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="1368a-105">Un gran risparmio di tempo!</span><span class="sxs-lookup"><span data-stu-id="1368a-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="1368a-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1368a-106">Before you begin</span></span>
  
- <span data-ttu-id="1368a-107">Ottieni la reimpostazione della password self-service per gli utenti cloud **gratuitamente** con qualsiasi Microsoft 365 aziendale, educativo o a pagamento senza scopo di lucro.</span><span class="sxs-lookup"><span data-stu-id="1368a-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="1368a-108">Non funziona con il Microsoft 365 prova.</span><span class="sxs-lookup"><span data-stu-id="1368a-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="1368a-p103">Si basa su Azure. Questa funzionalità verrà scaricata automaticamente e **gratuitamente** in Azure quando si esegue questa procedura. L'attivazione della reimpostazione della password in modalità self-service non costa nulla se non si usano altre funzionalità di Azure.</span><span class="sxs-lookup"><span data-stu-id="1368a-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="1368a-112">**Se si utilizza un Active Directory locale , i** due punti precedenti non si applicano.</span><span class="sxs-lookup"><span data-stu-id="1368a-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="1368a-113">È invece possibile configurarlo, ma è **necessaria una sottoscrizione a pagamento ad Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="1368a-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="1368a-114">Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit.</span><span class="sxs-lookup"><span data-stu-id="1368a-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="1368a-115">Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1368a-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="1368a-116">Che cos'è un account amministratore?</span><span class="sxs-lookup"><span data-stu-id="1368a-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="1368a-117">Per eseguire questa [procedura, è necessario essere un amministratore globale](about-admin-roles.md) o un amministratore di password.</span><span class="sxs-lookup"><span data-stu-id="1368a-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="1368a-118">Guarda: consentire agli utenti di reimpostare le proprie password</span><span class="sxs-lookup"><span data-stu-id="1368a-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="1368a-119">Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="1368a-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="1368a-120">Passaggi: lasciare che le persone ripristinino le proprie password</span><span class="sxs-lookup"><span data-stu-id="1368a-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="1368a-121">Con questi passaggi si attiva la reimpostazione della password in modalità self-service per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="1368a-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="1368a-122"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Nell'interfaccia di amministrazione</a>passare alla **pagina Impostazioni**  >  **impostazioni dell'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="1368a-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="1368a-123">Nella parte superiore della pagina **Impostazioni organizzazione** selezionare la scheda **& privacy.**</span><span class="sxs-lookup"><span data-stu-id="1368a-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="1368a-124">Selezionare **Reimpostazione password self-service**.</span><span class="sxs-lookup"><span data-stu-id="1368a-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="1368a-125">In **Reimpostazione password in servizio** personale selezionare Vai al portale di Azure per attivare la **reimpostazione della password self-service**.</span><span class="sxs-lookup"><span data-stu-id="1368a-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="1368a-126">Nel riquadro di spostamento sinistro selezionare **Utenti** e quindi nel **riquadro Utenti | Pagina Tutti gli** utenti selezionare **Reimposta password**.</span><span class="sxs-lookup"><span data-stu-id="1368a-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="1368a-127">Nella pagina **Proprietà** selezionare Tutto **per** abilitarlo per tutti gli utenti dell'azienda e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1368a-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="1368a-128">Quando gli utenti esedranno, verrà richiesto loro di immettere ulteriori informazioni di contatto che li aiuteranno a reimpostare la password in futuro.</span><span class="sxs-lookup"><span data-stu-id="1368a-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="1368a-129">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="1368a-129">Related content</span></span>

<span data-ttu-id="1368a-130">[Impostare i criteri di scadenza della password per l'organizzazione](../manage/set-password-expiration-policy.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="1368a-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>

<span data-ttu-id="1368a-131">[Impostare la password di un singolo utente in modo che non scada mai](set-password-to-never-expire.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="1368a-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>

<span data-ttu-id="1368a-132">[Microsoft 365 Business video di formazione (pagina](../../business-video/index.yml) dei link)</span><span class="sxs-lookup"><span data-stu-id="1368a-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
