---
title: Configurare il lab di Microsoft 365 o l'ambiente pilota di Defender
description: Accedere Microsoft 365 Security Center e quindi configurare l'ambiente di testing di Microsoft 365 Defender
keywords: Microsoft 365 Configurazione della versione di valutazione di Defender, Microsoft 365 configurazione pilota di Defender, prova Microsoft 365 Defender, Microsoft 365 configurazione del lab di valutazione di Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935426"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="f134c-104">Configurare l'ambiente di Microsoft 365 lab di valutazione di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f134c-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f134c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f134c-105">**Applies to:**</span></span>
- <span data-ttu-id="f134c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f134c-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="f134c-107">La creazione Microsoft 365 lab di valutazione o un ambiente pilota di Defender e la distribuzione è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="f134c-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="f134c-108">[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="f134c-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="f134c-109">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="f134c-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![Fase 2: configurazione](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="f134c-111">Fase 2: configurazione</span><span class="sxs-lookup"><span data-stu-id="f134c-111">Phase 2: Set up</span></span> |<span data-ttu-id="f134c-112">[![Fase 3: onboarding](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="f134c-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="f134c-113">Fase 3: onboarding</span><span class="sxs-lookup"><span data-stu-id="f134c-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="f134c-114">[![Torna al progetto pilota](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="f134c-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="f134c-115">Torna al playbook pilota</span><span class="sxs-lookup"><span data-stu-id="f134c-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="f134c-116">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="f134c-116">*You are here!*</span></span>  | | |


<span data-ttu-id="f134c-117">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f134c-117">You're currently in the set up phase.</span></span> <span data-ttu-id="f134c-118">Eseguire i passaggi iniziali per accedere Microsoft 365 Security Center e quindi configurare il laboratorio di valutazione o l'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="f134c-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="f134c-119">Iscriversi a una sottoscrizione Office 365 o Azure Active Directory per generare un tenant *.onmicrosoft.com* che è possibile usare per iscriversi alla licenza Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f134c-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="f134c-120">Se si dispone già di una sottoscrizione Office 365 o Azure Active Directory, è possibile ignorare i passaggi di creazione del tenant Office 365 E5 o pilota.</span><span class="sxs-lookup"><span data-stu-id="f134c-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="f134c-121">In questa fase, si verrà guidati a:</span><span class="sxs-lookup"><span data-stu-id="f134c-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="f134c-122">Creare un tenant Office 365 di valutazione di E5</span><span class="sxs-lookup"><span data-stu-id="f134c-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="f134c-123">Abilitare Microsoft 365 di valutazione</span><span class="sxs-lookup"><span data-stu-id="f134c-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="f134c-124">Creare un tenant Office 365 di valutazione di E5</span><span class="sxs-lookup"><span data-stu-id="f134c-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="f134c-125">Se si dispone già di una sottoscrizione Office 365 o Azure Active Directory, è possibile ignorare i passaggi di creazione del tenant di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f134c-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="f134c-126">Accedere al portale [del Office 365 E5 e](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) selezionare Versione di valutazione **gratuita.**</span><span class="sxs-lookup"><span data-stu-id="f134c-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Pagina di valutazione of_Office 365 E5 gratuita di Image of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="f134c-128">Completare la registrazione della versione di valutazione immettendo l'indirizzo di posta elettronica (personale o aziendale).</span><span class="sxs-lookup"><span data-stu-id="f134c-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="f134c-129">Fare **clic su Configura account**.</span><span class="sxs-lookup"><span data-stu-id="f134c-129">Click **Set up account**.</span></span>

   ![Immagine of_Office pagina di configurazione della registrazione della versione di valutazione di 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="f134c-131">Compilare nome, cognome, numero di telefono dell'azienda, nome della società, dimensioni della società e paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="f134c-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Image of_Office 365 E5 trial registration setup page asking for name, phone, and company details](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="f134c-133">Il paese o l'area geografica impostata qui determina l'area del data center Office 365 sarà ospitata.</span><span class="sxs-lookup"><span data-stu-id="f134c-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="f134c-134">Scegli la preferenza di verifica: tramite un SMS o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="f134c-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f134c-135">Fare **clic su Invia codice di verifica**.</span><span class="sxs-lookup"><span data-stu-id="f134c-135">Click **Send Verification Code**.</span></span> 

   ![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)

5. <span data-ttu-id="f134c-137">Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f134c-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="f134c-139">Configurare la prima identità, che sarà un amministratore globale per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f134c-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="f134c-140">Compilare **Nome** e **Password**.</span><span class="sxs-lookup"><span data-stu-id="f134c-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="f134c-141">Fare **clic su Iscriviti.**</span><span class="sxs-lookup"><span data-stu-id="f134c-141">Click **Sign up**.</span></span>

   ![Immagine of_Office configurazione della registrazione della versione di valutazione di 365 E5 in cui è possibile impostare l'identità aziendale](../../media/mtp-eval-14.png)

7. <span data-ttu-id="f134c-143">Fare **clic su Vai al programma di** installazione per completare il provisioning Office 365 tenant di valutazione E5.</span><span class="sxs-lookup"><span data-stu-id="f134c-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Immagine della pagina Office 365 di configurazione della registrazione della versione di valutazione di E5 che richiede di fare clic sul pulsante Vai all'installazione](../../media/mtp-eval-15.png)

8. <span data-ttu-id="f134c-145">Connessione dominio aziendale al tenant Office 365 aziendale.</span><span class="sxs-lookup"><span data-stu-id="f134c-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="f134c-146">[Facoltativo] Scegliere **Connessione un dominio di cui si è già proprietari** e digitare il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="f134c-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="f134c-147">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f134c-147">Click **Next**.</span></span>

   ![Immagine of_Office configurazione di 365 E5 in cui personalizzare l'accesso e la posta elettronica](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="f134c-149">Aggiungere un record TXT o MX per convalidare la proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="f134c-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="f134c-150">Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="f134c-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Immagine of_Office configurazione di 365 E5 in cui aggiungere un record TXT di MX per verificare il dominio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="f134c-152">[Facoltativo] Creare altri account utente per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f134c-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="f134c-153">È possibile ignorare questo passaggio facendo clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f134c-153">You can skip this step by clicking **Next**.</span></span>

    ![Pagina of_Office configurazione di 365 E5 in cui è possibile aggiungere altri utenti](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="f134c-155">[Facoltativo] Scarica Office app.</span><span class="sxs-lookup"><span data-stu-id="f134c-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="f134c-156">Fare **clic su** Avanti per ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f134c-156">Click **Next** to skip this step.</span></span> 

    ![Pagina of_Office 365 E5 in cui puoi installare le tue Office app](../../media/mtp-eval-19.png)

12. <span data-ttu-id="f134c-158">[Facoltativo] Eseguire la migrazione dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f134c-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="f134c-159">Anche in questo caso, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f134c-159">Again, you can skip this step.</span></span>

    ![Immagine of_Office 365 E5 in cui è possibile impostare se eseguire o meno la migrazione dei messaggi di posta elettronica](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="f134c-161">Scegliere i servizi online.</span><span class="sxs-lookup"><span data-stu-id="f134c-161">Choose online services.</span></span> <span data-ttu-id="f134c-162">Selezionare **Exchange** e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f134c-162">Select **Exchange** and click **Next**.</span></span> 

    ![Immagine of_Office 365 E5 in cui è possibile scegliere i servizi online](../../media/mtp-eval-21.png)

14. <span data-ttu-id="f134c-164">Aggiungere record MX, CNAME e TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="f134c-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="f134c-165">Al termine, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="f134c-165">When completed, select **Verify**.</span></span>

    ![Immagine of_Office 365 E5 qui è possibile aggiungere i record DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="f134c-167">Congratulazioni, hai completato il provisioning del tenant Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="f134c-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Pagina di conferma del completamento dell'installazione di Of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="f134c-169">Abilitare Microsoft 365 di valutazione</span><span class="sxs-lookup"><span data-stu-id="f134c-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="f134c-170">La registrazione a una versione di valutazione offre 25 licenze utente da usare per un mese.</span><span class="sxs-lookup"><span data-stu-id="f134c-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="f134c-171">Per [informazioni dettagliate, vedere Try or Buy an M365 subscription.](../../commerce/try-or-buy-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="f134c-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="f134c-172">Da [Microsoft 365 Admin Center,](https://admin.microsoft.com/)fare clic su **Fatturazione** e quindi passare a **Acquista servizi.**</span><span class="sxs-lookup"><span data-stu-id="f134c-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="f134c-173">Seleziona **Microsoft 365 E5** e fai clic su **Avvia versione di valutazione gratuita.**</span><span class="sxs-lookup"><span data-stu-id="f134c-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)

3. <span data-ttu-id="f134c-175">Scegli la preferenza di verifica: tramite un SMS o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="f134c-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f134c-176">Una volta deciso, immettere il numero di telefono, selezionare **Chiamami** o **Chiamami** a seconda della selezione.</span><span class="sxs-lookup"><span data-stu-id="f134c-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="f134c-178">Immetti il codice di verifica e fai clic **su Avvia la versione di valutazione gratuita.**</span><span class="sxs-lookup"><span data-stu-id="f134c-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="f134c-180">Fai **clic su Prova ora** per confermare la Microsoft 365 E5 versione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="f134c-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="f134c-182">Passare **all'Microsoft 365 Admin Center**  >  **Utenti**  >  **attivi**.</span><span class="sxs-lookup"><span data-stu-id="f134c-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="f134c-183">Seleziona l'account utente, seleziona **Gestisci licenze prodotto,** quindi scambia la licenza da Office 365 E5 a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="f134c-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="f134c-184">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f134c-184">Click **Save**.</span></span>

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile selezionare Microsoft 365 E5 licenza](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="f134c-186">Selezionare di nuovo l'account amministratore globale, quindi fare clic **su Gestisci nome utente.**</span><span class="sxs-lookup"><span data-stu-id="f134c-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Immagine of_Microsoft interfaccia di amministrazione di 365 in cui è possibile selezionare Account e quindi Gestire il nome utente](../../media/mtp-eval-29.png)

8. <span data-ttu-id="f134c-188">[Facoltativo] Modificare il dominio *da onmicrosoft.com* al proprio dominio, a seconda di ciò che è stato scelto nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="f134c-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="f134c-189">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="f134c-189">Click **Save changes**.</span></span>

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile modificare la preferenza del dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="f134c-191">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f134c-191">Next step</span></span>
|[<span data-ttu-id="f134c-192">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="f134c-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="f134c-193">Configurare ogni pilastro Microsoft 365 Defender per il lab di Microsoft 365 di valutazione o l'ambiente pilota di Defender e l'onboardboard degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="f134c-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
