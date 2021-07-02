---
title: Usare l'interoperabilità degli strumenti di OneDrive Learning di distribuzione
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Crea e classifica le assegnazioni, crea e cura il contenuto del corso e collabora ai file in tempo reale con la nuova app OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256985"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="4a345-103">Usare Microsoft OneDrive LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="4a345-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a345-104">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="4a345-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4a345-105">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="4a345-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="4a345-106">Integrazione con Canvas</span><span class="sxs-lookup"><span data-stu-id="4a345-106">Integrate with Canvas</span></span>

<span data-ttu-id="4a345-107">La persona che esegue questa integrazione deve essere un amministratore di Canvas e un amministratore del tenant Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="4a345-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="4a345-108">Accedi al portale di Microsoft Azure con l'account di amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="4a345-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="4a345-109">Anche l'amministratore tenant di Azure deve avere il ruolo di amministratore del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4a345-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![amministratore di gruppo evidenziato](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="4a345-111">Accedere al portale di Microsoft [OneDrive LTI](https://odltiappnl.azurewebsites.net/admin).</span><span class="sxs-lookup"><span data-stu-id="4a345-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="4a345-112">Accettare le autorizzazioni per completare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4a345-112">Accept the permissions to complete the sign-in.</span></span>

    ![accettare autorizzazioni](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="4a345-114">Selezionare **Aggiungi tenant LTI**.</span><span class="sxs-lookup"><span data-stu-id="4a345-114">Select **Add LTI Tenant**.</span></span>

     ![aggiungere tenant LTI](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="4a345-116">Seleziona **Piattaforma consumer LTI** come **canvas nell'elenco** a discesa.</span><span class="sxs-lookup"><span data-stu-id="4a345-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="4a345-117">Seleziona **URL di base** canvas e quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="4a345-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![selezionare Canvas e aggiungere l'URL di base](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="4a345-119">Nella schermata successiva vengono mostrati i campi riservati all'utente.</span><span class="sxs-lookup"><span data-stu-id="4a345-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="4a345-120">Selezionare **Avanti** da ??</span><span class="sxs-lookup"><span data-stu-id="4a345-120">Select **Next** from ??</span></span> <span data-ttu-id="4a345-121">pagina.</span><span class="sxs-lookup"><span data-stu-id="4a345-121">page.</span></span> <span data-ttu-id="4a345-122">I REVISORI POSSONO COMPILARE LO SPAZIO VUOTO QUI?</span><span class="sxs-lookup"><span data-stu-id="4a345-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="4a345-123">Seleziona **Avanti** nella schermata che mostra informazioni riservate all'utente.</span><span class="sxs-lookup"><span data-stu-id="4a345-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="4a345-124">La schermata finale del portale di Azure mostra i passaggi successivi per aggiungere l'istanza canvas.</span><span class="sxs-lookup"><span data-stu-id="4a345-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="4a345-125">Copia le chiavi per sviluppatori da questa schermata.</span><span class="sxs-lookup"><span data-stu-id="4a345-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="4a345-126">Userai quando crei l'istanza Canvas.</span><span class="sxs-lookup"><span data-stu-id="4a345-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="4a345-127">Aggiungere l'istanza canvas</span><span class="sxs-lookup"><span data-stu-id="4a345-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="4a345-128">Nell'istanza canvas deseleziona **Admin**  >  **Developer Keys.**</span><span class="sxs-lookup"><span data-stu-id="4a345-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="4a345-129">Scegli **LTI Key** nell'elenco a discesa in **Developer Key.**</span><span class="sxs-lookup"><span data-stu-id="4a345-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![Ottenere le chiavi per sviluppatori LTI](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="4a345-131">Incolla qui le chiavi per sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="4a345-131">Paste the developer keys here.</span></span>

     ![Incollare le chiavi dello sviluppatore](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="4a345-133">Il tasto viene creato in **modalità OFF**</span><span class="sxs-lookup"><span data-stu-id="4a345-133">The key gets created in **OFF** mode</span></span>

   ![Chiavi per sviluppatori create in modalità disattivata](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="4a345-135">Copiare il testo evidenziato.</span><span class="sxs-lookup"><span data-stu-id="4a345-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="4a345-136">Questo viene utilizzato come ID client Microsoft OneDrive portale LTI.</span><span class="sxs-lookup"><span data-stu-id="4a345-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="4a345-137">Incollare il testo nel **campo ID client** Microsoft OneDrive portale LTI e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="4a345-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="4a345-138">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4a345-138">Select **Save**.</span></span>

7. <span data-ttu-id="4a345-139">Visualizzare le impostazioni selezionando **Visualizza tenant LTI**.</span><span class="sxs-lookup"><span data-stu-id="4a345-139">View the settings by selecting **View LTI Tenants**.</span></span>
