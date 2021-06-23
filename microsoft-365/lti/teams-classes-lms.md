---
title: Usare Microsoft Teams classi con Blackboard
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
description: Integrare Microsoft Teams classi nel sistema Learning management
ms.openlocfilehash: 940c5c695d602ddce6ea49b1f914f2345fbeb7e5
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083244"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="c9ad3-103">Usare Microsoft Teams classi con Blackboard</span><span class="sxs-lookup"><span data-stu-id="c9ad3-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9ad3-104">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c9ad3-105">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c9ad3-106">Microsoft Teams classi è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il Learning Management System (LMS) e il Teams.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="c9ad3-107">Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="c9ad3-108">Approvare l'app nel tenant Microsoft Azure app</span><span class="sxs-lookup"><span data-stu-id="c9ad3-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="c9ad3-109">Le attività seguenti vengono completate dall'amministratore Microsoft Office 365 e dall'amministratore di Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="c9ad3-110">Prima di gestire l'integrazione all'interno di Blackboard Learn Ultra, l'amministratore di Microsoft Office 365 deve approvare la blackboard **MSFT Teams for Learn Ultra Azure** app for the institution's Microsoft Azure tenant.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="c9ad3-111">Trovare l'ID tenant Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="c9ad3-112">Vedere [come trovare il tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span><span class="sxs-lookup"><span data-stu-id="c9ad3-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="c9ad3-113">Reindirizzare l'endpoint di consenso dell'amministratore di Microsoft Identity Platform in base all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c9ad3-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="c9ad3-114">Sostituire {tenant} con l'ID tenant Microsoft dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="c9ad3-115">Registrare le app di integrazione</span><span class="sxs-lookup"><span data-stu-id="c9ad3-115">Register the integration apps</span></span>

<span data-ttu-id="c9ad3-116">Come amministratore di Blackboard Learn Ultra, dovrai registrare 2 app di integrazione LTI 1.3 nell'ambiente di testing:</span><span class="sxs-lookup"><span data-stu-id="c9ad3-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="c9ad3-117">La blackboard Learn Class Teams integrazione per supportare la sincronizzazione dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9ad3-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="c9ad3-118">App LTI Microsoft Teams team di classe</span><span class="sxs-lookup"><span data-stu-id="c9ad3-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="c9ad3-119">Prendere nota degli ID client LTI seguenti per entrambe le app:</span><span class="sxs-lookup"><span data-stu-id="c9ad3-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="c9ad3-120">Lavagna - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="c9ad3-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="c9ad3-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="c9ad3-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="c9ad3-122">Accedere al Pannello di amministrazione e in **Integrazioni** individuare i provider di strumenti LTI.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![questa è la finestra di dialogo provider di strumenti LTI che mostra un elenco di provider](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="c9ad3-124">Selezionare **Register LTI1.3/Advantage Tool**.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="c9ad3-125">Immetti il primo degli ID client forniti (Blackboard o Microsoft) e seleziona **Invia.**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

5. <span data-ttu-id="c9ad3-126">Esaminare le impostazioni precompilato e verificare che lo stato dello strumento sia contrassegnato come approvato.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-126">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="c9ad3-127">Scorrere verso il basso e quindi selezionare **Invia.**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-127">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="c9ad3-128">Ripeti i passaggi precedenti per registrare la seconda delle app LTI nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-128">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="c9ad3-129">Configurare l'applicazione REST e la condivisione delle risorse tra origini</span><span class="sxs-lookup"><span data-stu-id="c9ad3-129">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="c9ad3-130">L'amministratore di Blackboard Learn Ultra dovrà anche configurare l'applicazione REST e la configurazione di Condivisione risorse tra origini.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-130">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="c9ad3-131">Completare le operazioni seguenti per configurare l'applicazione REST</span><span class="sxs-lookup"><span data-stu-id="c9ad3-131">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="c9ad3-132">Accedi agli strumenti di amministrazione di Learn e quindi seleziona **Integrazioni API REST** nella **sezione Integrazioni.**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-132">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c9ad3-133">Seleziona **Crea integrazioni** e immetti lo stesso ID applicazione/client immesso per lo strumento Blackboard Learn Class Teams Integration LTI.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-133">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="c9ad3-134">Immetti Learn User (potrebbe essere il tuo nome utente amministratore learn) o seleziona **Sfoglia** per individuarlo.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-134">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="c9ad3-135">Selezionare **Sì** per **Accesso utente finale.**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-135">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="c9ad3-136">Selezionare **Sì** per **Autorizzato ad agire come utente**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-136">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="c9ad3-137">Selezionare **Invia** al termine.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-137">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="c9ad3-138">Configurare condivisione risorse tra origini</span><span class="sxs-lookup"><span data-stu-id="c9ad3-138">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="c9ad3-139">Accedere a Strumenti di amministrazione di Learn e selezionare **Condivisione risorse tra** origini nella sezione **Integrazioni.**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-139">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c9ad3-140">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-140">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="c9ad3-141">Immettere `https://bb-ms-teams-ultra-ext.api.blackboard.com` l'origine.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-141">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="c9ad3-142">Aggiungere la parola **Autorizzazione** nelle **intestazioni consentite.**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-142">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="c9ad3-143">Impostare **Disponibile** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-143">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="c9ad3-144">Selezionare **Invia** al termine.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-144">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="c9ad3-145">Enable Class Teams in Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="c9ad3-145">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="c9ad3-146">Dopo aver abilitato gli strumenti LTI, il passaggio successivo consisterà nel configurare l'integrazione di Microsoft Class Teams dal tenant Microsoft Office 365 proprio.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-146">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="c9ad3-147">Puoi farlo seguendo questi passaggi come amministratore di Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-147">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="c9ad3-148">In **Learn Admin** Tools and  >  **Utilities** selezionare Microsoft Teams Integration **Admin.**</span><span class="sxs-lookup"><span data-stu-id="c9ad3-148">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![finestra di dialogo strumenti e utilità con un elenco degli strumenti disponibili](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="c9ad3-150">Selezionare la casella di controllo **Abilita Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-150">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="c9ad3-151">Immetti l'ID tenant come riferimento nella sezione in Amministratore di Microsoft O365</span><span class="sxs-lookup"><span data-stu-id="c9ad3-151">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="c9ad3-152">Non potrai salvare le impostazioni finché l'app non viene approvata dall'amministratore di O365. Vedi [Approvare l'app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span><span class="sxs-lookup"><span data-stu-id="c9ad3-152">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="c9ad3-153">Quando l'amministratore globale di O365 ha approvato l'applicazione blackboard Teams nel tenant Microsoft, selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c9ad3-153">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
