---
title: Configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Informazioni su come configurare Microsoft Viva Learning (Anteprima) nell'Teams di amministrazione.
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625299"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="d4669-103">Configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione</span><span class="sxs-lookup"><span data-stu-id="d4669-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="d4669-104">Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="d4669-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="d4669-105">L Teams admin installa Viva Learning (Preview) e applica i criteri di autorizzazione tramite l'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d4669-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="d4669-106">Per l'anteprima pubblica, devi prima impostare i criteri di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d4669-106">For Public Preview, you must first set the Update policy.</span></span> <span data-ttu-id="d4669-107">Per ulteriori dettagli, vedere il sito Teams e [Microsoft Teams Public Preview.](/MicrosoftTeams/public-preview-doc-updates)</span><span class="sxs-lookup"><span data-stu-id="d4669-107">For more details, see the Teams site [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="d4669-108">Accedere all'interfaccia Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d4669-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="d4669-109">Selezionare **Teams**  >  **Criteri di aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="d4669-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="d4669-110">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d4669-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="d4669-111">Assegnare un nome al criterio di aggiornamento, aggiungere un criterio e attivare **Mostra funzionalità di anteprima.**</span><span class="sxs-lookup"><span data-stu-id="d4669-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="d4669-112">L'amministratore deve informare gli utenti dell'aggiornamento dei criteri in modo che spostino la build in Anteprima pubblica per Teams.</span><span class="sxs-lookup"><span data-stu-id="d4669-112">The admin must notify users of the policy update so that they move their build into Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="d4669-113">L'utente deve selezionare l'immagine del profilo --> Informazioni su --> Anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="d4669-113">User must select their profile image --> About --> Public Preview.</span></span>
   
        ![Spostamento superiore nell'Teams che mostra il profilo dell'utente](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="d4669-115">L'utente deve accettare i termini dell'anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="d4669-115">User must accept terms of Public Preview.</span></span>

        ![Passare alla build di anteprima pubblica](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="d4669-117">Per le organizzazioni che dispongono di criteri restrittivi e che devono abilitare Viva Learning, seguire il processo nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="d4669-117">For organizations that have restrictive policies and need to enable Viva Learning, follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="d4669-118">Gestire le impostazioni per Viva Learning (anteprima)</span><span class="sxs-lookup"><span data-stu-id="d4669-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="d4669-119">Per eseguire queste attività, è Teams amministratore dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d4669-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="d4669-120">Per rendere Viva Learning (Anteprima) disponibile per gli utenti dell'organizzazione, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="d4669-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="d4669-121">Nel riquadro di spostamento sinistro dell'Teams di amministrazione passare a Teams  >  **app Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="d4669-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Spostamento a sinistra nell'Teams di amministrazione che mostra le Teams app e la sezione Gestisci app.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="d4669-123">Nella casella **di ricerca della** pagina Gestisci app digitare Viva *learning* e quindi selezionare Viva **Learning (anteprima).**</span><span class="sxs-lookup"><span data-stu-id="d4669-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Pagina Gestisci app nell'interfaccia Teams di amministrazione che mostra la casella di ricerca.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="d4669-125">Nella pagina **Viva Learning (Anteprima):**</span><span class="sxs-lookup"><span data-stu-id="d4669-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="d4669-126">In **Stato** seleziona **Consentito per** attivare Viva Learning (Anteprima).</span><span class="sxs-lookup"><span data-stu-id="d4669-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="d4669-127">Nella scheda **Impostazioni,** in **Impostazioni app,** passare all'interfaccia di amministrazione Microsoft 365 per [configurare le origini di contenuto didattiche.](content-sources-365-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="d4669-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Pagina Di apprendimento nell'Teams di amministrazione che mostra la sezione Impostazioni stato e app.](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="d4669-129">Dopo Gestire le impostazioni   **dell'app,** vai a Criteri di autorizzazione e Criteri di installazione per concedere l'autorizzazione ai dipendenti che devono avere accesso a Viva Learning (Preview) come parte della partecipazione dell'organizzazione all'anteprima.</span><span class="sxs-lookup"><span data-stu-id="d4669-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="d4669-130">Se l'organizzazione si trova nel Circuito 4.0 come parte del programma TAP100 di Teams, potrebbe essere necessario abilitare gli utenti approvati nel Circuito 3.0 per accedere a Viva Learning (Anteprima).</span><span class="sxs-lookup"><span data-stu-id="d4669-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="d4669-131">Come parte dell'anteprima, Viva Learning (Preview) viene rilasciato nel Circuito 3.0.</span><span class="sxs-lookup"><span data-stu-id="d4669-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="d4669-132">Se l'organizzazione si trova nel Circuito 4.0, viva learning (anteprima) non verrà visualizzato nella **pagina Gestisci** app.</span><span class="sxs-lookup"><span data-stu-id="d4669-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="d4669-133">Per testare l'app, devi creare un criterio di autorizzazione per le app personalizzate, impostarlo su Consenti tutte le app e assegnarlo agli utenti approvati di Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="d4669-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="d4669-134">![Tap-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="d4669-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="d4669-135">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d4669-135">Next step</span></span>

[<span data-ttu-id="d4669-136">Configurare le origini di contenuto di apprendimento per Viva Learning (anteprima) nell'Microsoft 365 di amministrazione</span><span class="sxs-lookup"><span data-stu-id="d4669-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
