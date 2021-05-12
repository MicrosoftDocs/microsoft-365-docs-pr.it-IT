---
title: Usare le classi di Microsoft Teams nel sistema di gestione dell'apprendimento
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
description: Integrare le classi di Microsoft Teams nel sistema di gestione dell'apprendimento
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327786"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="c2492-103">Usare le classi di Microsoft Teams nel sistema di gestione dell'apprendimento</span><span class="sxs-lookup"><span data-stu-id="c2492-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2492-104">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="c2492-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c2492-105">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="c2492-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c2492-106">I team di classe di Microsoft Teams sono un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il sistema di gestione dell'apprendimento (LMS) e Teams.</span><span class="sxs-lookup"><span data-stu-id="c2492-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="c2492-107">Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="c2492-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="c2492-108">Approvare l'app nel tenant di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="c2492-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="c2492-109">Le attività seguenti vengono completate dall'amministratore Microsoft Office 365 e dall'amministratore di Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="c2492-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="c2492-110">Prima di gestire l'integrazione all'interno di Blackboard Learn Ultra, l'amministratore di Microsoft Office 365 deve approvare l'app Blackboard **MSFT Teams for Learn Ultra Azure** per il tenant di Microsoft Azure dell'istituto.</span><span class="sxs-lookup"><span data-stu-id="c2492-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="c2492-111">Trovare l'ID tenant Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2492-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="c2492-112">Vedere [come trovare il tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span><span class="sxs-lookup"><span data-stu-id="c2492-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="c2492-113">Reindirizzare l'endpoint di consenso dell'amministratore di Microsoft Identity Platform in base all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c2492-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="c2492-114">Sostituire {tenant} con l'ID tenant Microsoft dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2492-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="c2492-115">Registrare le app di integrazione</span><span class="sxs-lookup"><span data-stu-id="c2492-115">Register the integration apps</span></span>

<span data-ttu-id="c2492-116">Come amministratore di Blackboard Learn Ultra, dovrai registrare 2 app di integrazione LTI 1.3 nell'ambiente di testing:</span><span class="sxs-lookup"><span data-stu-id="c2492-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="c2492-117">Integrazione di Blackboard Learn Class Teams per supportare la sincronizzazione dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c2492-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="c2492-118">App LTI del team di classe di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c2492-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="c2492-119">Prendere nota degli ID client LTI seguenti per entrambe le app:</span><span class="sxs-lookup"><span data-stu-id="c2492-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="c2492-120">Lavagna - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="c2492-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="c2492-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="c2492-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="c2492-122">Accedere al Pannello di amministrazione e in **Integrazioni** individuare i provider di strumenti LTI.</span><span class="sxs-lookup"><span data-stu-id="c2492-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![questa è la finestra di dialogo provider di strumenti LTI che mostra un elenco di provider](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="c2492-124">Selezionare **Register LTI1.3/Advantage Tool**.</span><span class="sxs-lookup"><span data-stu-id="c2492-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="c2492-125">Immetti il primo degli ID client forniti (Blackboard o Microsoft) e seleziona **Invia.**</span><span class="sxs-lookup"><span data-stu-id="c2492-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![lo strumento di registrazione LTI con un campo per immettere l'ID client](../media/lti-media/register-tool.png)

5. <span data-ttu-id="c2492-127">Esaminare le impostazioni precompilato e verificare che lo stato dello strumento sia contrassegnato come approvato.</span><span class="sxs-lookup"><span data-stu-id="c2492-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="c2492-128">Scorrere verso il basso e quindi selezionare **Invia.**</span><span class="sxs-lookup"><span data-stu-id="c2492-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="c2492-129">Ripeti i passaggi precedenti per registrare la seconda delle app LTI nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c2492-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="c2492-130">Configurare l'applicazione REST e la condivisione delle risorse tra origini</span><span class="sxs-lookup"><span data-stu-id="c2492-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="c2492-131">L'amministratore di Blackboard Learn Ultra dovrà anche configurare l'applicazione REST e la configurazione di Condivisione risorse tra origini.</span><span class="sxs-lookup"><span data-stu-id="c2492-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="c2492-132">Completare le operazioni seguenti per configurare l'applicazione REST</span><span class="sxs-lookup"><span data-stu-id="c2492-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="c2492-133">Accedi agli strumenti di amministrazione di Learn e quindi seleziona **Integrazioni API REST** nella **sezione Integrazioni.**</span><span class="sxs-lookup"><span data-stu-id="c2492-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c2492-134">Seleziona **Crea integrazioni** e immetti lo stesso ID applicazione/client immesso per lo strumento Blackboard Learn Class Teams Integration LTI.</span><span class="sxs-lookup"><span data-stu-id="c2492-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="c2492-135">Immetti Learn User (potrebbe essere il tuo nome utente amministratore learn) o seleziona **Sfoglia** per individuarlo.</span><span class="sxs-lookup"><span data-stu-id="c2492-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="c2492-136">Selezionare **Sì** per **Accesso utente finale.**</span><span class="sxs-lookup"><span data-stu-id="c2492-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="c2492-137">Selezionare **Sì** per **Autorizzato ad agire come utente**</span><span class="sxs-lookup"><span data-stu-id="c2492-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="c2492-138">Selezionare **Invia** al termine.</span><span class="sxs-lookup"><span data-stu-id="c2492-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="c2492-139">Configurare condivisione risorse tra origini</span><span class="sxs-lookup"><span data-stu-id="c2492-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="c2492-140">Accedere a Strumenti di amministrazione di Learn e selezionare **Condivisione risorse tra** origini nella sezione **Integrazioni.**</span><span class="sxs-lookup"><span data-stu-id="c2492-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c2492-141">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="c2492-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="c2492-142">Immettere `https://bb-ms-teams-ultra-ext.api.blackboard.com` l'origine.</span><span class="sxs-lookup"><span data-stu-id="c2492-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="c2492-143">Aggiungere la parola **Autorizzazione** nelle **intestazioni consentite.**</span><span class="sxs-lookup"><span data-stu-id="c2492-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="c2492-144">Impostare **Disponibile** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c2492-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="c2492-145">Selezionare **Invia** al termine.</span><span class="sxs-lookup"><span data-stu-id="c2492-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="c2492-146">Abilitare Class Teams in Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="c2492-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="c2492-147">Dopo aver abilitato gli strumenti LTI, il passaggio successivo consisterà nel configurare l'integrazione di Microsoft Class Teams dal proprio tenant Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="c2492-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="c2492-148">Puoi farlo seguendo questi passaggi come amministratore di Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="c2492-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="c2492-149">In **Learn Admin** Tools and  >  **Utilities** selezionare Microsoft Teams Integration **Admin.**</span><span class="sxs-lookup"><span data-stu-id="c2492-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![finestra di dialogo strumenti e utilità con un elenco degli strumenti disponibili](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="c2492-151">Selezionare la casella di controllo **Abilita Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="c2492-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="c2492-152">Immetti l'ID tenant come riferimento nella sezione in Amministratore di Microsoft O365</span><span class="sxs-lookup"><span data-stu-id="c2492-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="c2492-153">Non potrai salvare le impostazioni finché l'app non viene approvata dall'amministratore di O365. Vedi [Approvare l'app nel tenant di Microsoft Azure.](#approve-the-app-in-the-microsoft-azure-tenant)</span><span class="sxs-lookup"><span data-stu-id="c2492-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="c2492-154">Quando l'amministratore globale di O365 ha approvato l'applicazione Blackboard Teams nel tenant Microsoft, selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c2492-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
