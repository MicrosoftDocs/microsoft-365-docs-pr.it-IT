---
title: Configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender
description: Accedere al Centro sicurezza Microsoft 365 e quindi configurare l'ambiente lab di valutazione di Microsoft 365 Defender
keywords: Configurazione della versione di valutazione di Microsoft Threat Protection, configurazione pilota di Microsoft Threat Protection, provare Microsoft Threat Protection, configurazione del lab di valutazione di Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932983"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="425e6-104">Configurare l'ambiente lab di valutazione di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="425e6-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="425e6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="425e6-105">**Applies to:**</span></span>
- <span data-ttu-id="425e6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="425e6-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="425e6-107">La creazione di un ambiente pilota o un lab di valutazione di Microsoft 365 Defender e la sua distribuzione è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="425e6-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="425e6-108">[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="425e6-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="425e6-109">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="425e6-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![Fase 2: configurazione](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="425e6-111">Fase 2: configurazione</span><span class="sxs-lookup"><span data-stu-id="425e6-111">Phase 2: Set up</span></span> |<span data-ttu-id="425e6-112">[![Fase 3: onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="425e6-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="425e6-113">Fase 3: onboard</span><span class="sxs-lookup"><span data-stu-id="425e6-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="425e6-114">[![Tornare al progetto pilota](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="425e6-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="425e6-115">Tornare al playbook pilota</span><span class="sxs-lookup"><span data-stu-id="425e6-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="425e6-116">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="425e6-116">*You are here!*</span></span>  | | |


<span data-ttu-id="425e6-117">Al momento è in corso la fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="425e6-117">You're currently in the set up phase.</span></span> <span data-ttu-id="425e6-118">Eseguire i passaggi iniziali per accedere al Centro sicurezza Microsoft 365 e quindi configurare il laboratorio di valutazione o l'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="425e6-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="425e6-119">Iscriversi a un abbonamento a Office 365 o Azure Active Directory per generare un tenant con estensione *onmicrosoft.com* che è possibile usare per iscriversi alla licenza di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="425e6-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="425e6-120">Se si dispone già di un abbonamento a Office 365 o Azure Active Directory, è possibile ignorare i passaggi di creazione del tenant pilota o di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="425e6-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="425e6-121">In questa fase, si verrà guidati a:</span><span class="sxs-lookup"><span data-stu-id="425e6-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="425e6-122">Creare un tenant di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="425e6-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="425e6-123">Abilitare la sottoscrizione di valutazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="425e6-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="425e6-124">Creare un tenant di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="425e6-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="425e6-125">Se si dispone già di un abbonamento a Office 365 o Azure Active Directory, è possibile ignorare i passaggi di creazione del tenant di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="425e6-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="425e6-126">Accedere al portale [del prodotto Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selezionare **Versione di valutazione gratuita.**</span><span class="sxs-lookup"><span data-stu-id="425e6-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Immagine of_Office pagina di valutazione gratuita di 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="425e6-128">Completare la registrazione della versione di valutazione immettendo il proprio indirizzo di posta elettronica (personale o aziendale).</span><span class="sxs-lookup"><span data-stu-id="425e6-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="425e6-129">Fare **clic su Configura account.**</span><span class="sxs-lookup"><span data-stu-id="425e6-129">Click **Set up account**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)

3. <span data-ttu-id="425e6-131">Compila nome, cognome, numero di telefono dell'azienda, nome della società, dimensione della società e paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="425e6-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Immagine of_Office pagina di configurazione della registrazione della versione di valutazione di 365 E5 che richiede nome, telefono e dettagli aziendali](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="425e6-133">Il paese o l'area geografica impostata qui determina l'area del data center in cui verrà ospitato Office 365.</span><span class="sxs-lookup"><span data-stu-id="425e6-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="425e6-134">Scegli la preferenza di verifica: tramite un SMS o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="425e6-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="425e6-135">Fare clic **su Invia codice di verifica.**</span><span class="sxs-lookup"><span data-stu-id="425e6-135">Click **Send Verification Code**.</span></span> 

   ![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)

5. <span data-ttu-id="425e6-137">Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="425e6-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Immagine of_Office configurazione della registrazione della versione di valutazione di 365 E5 in cui è possibile configurare il nome di dominio personalizzato](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="425e6-139">Configurare la prima identità, che sarà un amministratore globale per il tenant.</span><span class="sxs-lookup"><span data-stu-id="425e6-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="425e6-140">Immettere **nome** e **password.**</span><span class="sxs-lookup"><span data-stu-id="425e6-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="425e6-141">Fare **clic su Registrazione.**</span><span class="sxs-lookup"><span data-stu-id="425e6-141">Click **Sign up**.</span></span>

   ![Immagine of_Office pagina di configurazione della registrazione della versione di valutazione di 365 E5 in cui è possibile impostare l'identità aziendale](../../media/mtp-eval-14.png)

7. <span data-ttu-id="425e6-143">Fare **clic su Go to Setup** per completare il provisioning del tenant di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="425e6-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Immagine della pagina di configurazione della registrazione della versione di valutazione di Office 365 E5 che richiede di fare clic sul pulsante Vai all'installazione](../../media/mtp-eval-15.png)

8. <span data-ttu-id="425e6-145">Connettere il dominio aziendale al tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="425e6-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="425e6-146">[Facoltativo] Choose **Connect a domain you already own** and type in your domain name.</span><span class="sxs-lookup"><span data-stu-id="425e6-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="425e6-147">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="425e6-147">Click **Next**.</span></span>

   ![Immagine of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="425e6-149">Aggiungere un record TXT o MX per convalidare la proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="425e6-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="425e6-150">Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="425e6-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="425e6-152">[Facoltativo] Creare altri account utente per il tenant.</span><span class="sxs-lookup"><span data-stu-id="425e6-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="425e6-153">È possibile ignorare questo passaggio facendo clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="425e6-153">You can skip this step by clicking **Next**.</span></span>

    ![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="425e6-155">[Facoltativo] Scaricare le app di Office.</span><span class="sxs-lookup"><span data-stu-id="425e6-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="425e6-156">Fare **clic su** Avanti per ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="425e6-156">Click **Next** to skip this step.</span></span> 

    ![Immagine of_Office 365 E5 in cui è possibile installare le app di Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="425e6-158">[Facoltativo] Eseguire la migrazione dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="425e6-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="425e6-159">Anche in questo caso, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="425e6-159">Again, you can skip this step.</span></span>

    ![Immagine of_Office 365 E5 in cui è possibile impostare se eseguire o meno la migrazione dei messaggi di posta elettronica](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="425e6-161">Scegliere i servizi online.</span><span class="sxs-lookup"><span data-stu-id="425e6-161">Choose online services.</span></span> <span data-ttu-id="425e6-162">Selezionare **Exchange** e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="425e6-162">Select **Exchange** and click **Next**.</span></span> 

    ![Immagine of_Office 365 E5 in cui è possibile scegliere i servizi online](../../media/mtp-eval-21.png)

14. <span data-ttu-id="425e6-164">Aggiungere record MX, CNAME e TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="425e6-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="425e6-165">Al termine, selezionare **Verifica.**</span><span class="sxs-lookup"><span data-stu-id="425e6-165">When completed, select **Verify**.</span></span>

    ![Immagine of_Office 365 E5 qui è possibile aggiungere i record DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="425e6-167">Congratulazioni, il provisioning del tenant di Office 365 è stato completato.</span><span class="sxs-lookup"><span data-stu-id="425e6-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="425e6-169">Abilitare la sottoscrizione di valutazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="425e6-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="425e6-170">La registrazione a una versione di valutazione offre 25 licenze utente da usare per un mese.</span><span class="sxs-lookup"><span data-stu-id="425e6-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="425e6-171">Per informazioni dettagliate, vedere Provare o acquistare [un abbonamento a M365.](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1)</span><span class="sxs-lookup"><span data-stu-id="425e6-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="425e6-172">[Dall'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/)fare clic su **Fatturazione** e quindi passare ad Acquisto **di servizi.**</span><span class="sxs-lookup"><span data-stu-id="425e6-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="425e6-173">Selezionare **Microsoft 365 E5** e fare clic su **Avvia versione di valutazione gratuita.**</span><span class="sxs-lookup"><span data-stu-id="425e6-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)

3. <span data-ttu-id="425e6-175">Scegli la preferenza di verifica: tramite un SMS o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="425e6-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="425e6-176">Dopo aver deciso, immettere il numero di telefono, selezionare **Sms o** **Chiamami a** seconda della selezione effettuata.</span><span class="sxs-lookup"><span data-stu-id="425e6-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="425e6-178">Immetti il codice di verifica e fai clic **su Avvia la versione di valutazione gratuita.**</span><span class="sxs-lookup"><span data-stu-id="425e6-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="425e6-180">Fare **clic su Prova per** confermare la versione di valutazione di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="425e6-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="425e6-182">Passare agli utenti **attivi dell'interfaccia di amministrazione di Microsoft 365.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="425e6-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="425e6-183">Selezionare l'account utente, selezionare Gestisci licenze di **prodotto,** quindi scambiare la licenza da Office 365 E5 a **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="425e6-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="425e6-184">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="425e6-184">Click **Save**.</span></span>

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile selezionare la licenza di Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="425e6-186">Selezionare di nuovo l'account amministratore globale, quindi fare clic **su Gestisci nome utente.**</span><span class="sxs-lookup"><span data-stu-id="425e6-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)

8. <span data-ttu-id="425e6-188">[Facoltativo] Modificare il dominio *da onmicrosoft.com* al proprio dominio, a seconda di ciò che è stato scelto nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="425e6-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="425e6-189">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="425e6-189">Click **Save changes**.</span></span>

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile modificare la preferenza del dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="425e6-191">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="425e6-191">Next step</span></span>
|[<span data-ttu-id="425e6-192">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="425e6-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="425e6-193">Configurare ogni pilastro di Microsoft 365 Defender per il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender ed eseguire l'onboardboard degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="425e6-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
