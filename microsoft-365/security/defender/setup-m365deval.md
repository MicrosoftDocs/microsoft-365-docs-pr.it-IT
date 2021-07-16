---
title: Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota
description: Accedere Microsoft 365 Security Center e quindi configurare l'Microsoft 365 Defender lab di valutazione
keywords: Microsoft 365 Defender di prova, Microsoft 365 Defender installazione pilota, provare a Microsoft 365 Defender, Microsoft 365 Defender di valutazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454734"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="4f23d-104">Configurare la versione Microsoft 365 Defender in un ambiente lab</span><span class="sxs-lookup"><span data-stu-id="4f23d-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4f23d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4f23d-105">**Applies to:**</span></span>
- <span data-ttu-id="4f23d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f23d-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="4f23d-107">In questo argomento viene illustrato come configurare un ambiente lab dedicato.</span><span class="sxs-lookup"><span data-stu-id="4f23d-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="4f23d-108">Per informazioni sulla configurazione di una versione di valutazione in produzione, vedere la nuova guida di valutazione [e Microsoft 365 Defender](eval-overview.md) pilota.</span><span class="sxs-lookup"><span data-stu-id="4f23d-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="4f23d-109">Creare un tenant Office 365 E5 di valutazione</span><span class="sxs-lookup"><span data-stu-id="4f23d-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="4f23d-110">Se si dispone già di una sottoscrizione Office 365 o Azure Active Directory, è possibile ignorare i passaggi Office 365 E5 creazione del tenant di valutazione.</span><span class="sxs-lookup"><span data-stu-id="4f23d-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="4f23d-111">Vai al portale [Office 365 E5 prodotto e](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) seleziona Versione di valutazione **gratuita.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Pagina di valutazione of_Office 365 E5 gratuita di Image of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="4f23d-113">Completare la registrazione della versione di valutazione immettendo l'indirizzo di posta elettronica (personale o aziendale).</span><span class="sxs-lookup"><span data-stu-id="4f23d-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="4f23d-114">Fare **clic su Configura account**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-114">Click **Set up account**.</span></span>

   ![Immagine of_Office pagina di configurazione della registrazione della versione di valutazione di 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="4f23d-116">Compilare nome, cognome, numero di telefono dell'azienda, nome della società, dimensioni della società e paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="4f23d-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Image of_Office 365 E5 trial registration setup page asking for name, phone, and company details](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="4f23d-118">Il paese o l'area geografica impostata qui determina l'area del data center Office 365 sarà ospitata.</span><span class="sxs-lookup"><span data-stu-id="4f23d-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="4f23d-119">Scegli la preferenza di verifica: tramite un SMS o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="4f23d-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="4f23d-120">Fare **clic su Invia codice di verifica**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-120">Click **Send Verification Code**.</span></span> 

   ![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)

5. <span data-ttu-id="4f23d-122">Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="4f23d-124">Configurare la prima identità, che sarà un amministratore globale per il tenant.</span><span class="sxs-lookup"><span data-stu-id="4f23d-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="4f23d-125">Compilare **Nome** e **Password**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="4f23d-126">Fare **clic su Iscriviti.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-126">Click **Sign up**.</span></span>

   ![Immagine of_Office configurazione della registrazione della versione di valutazione di 365 E5 in cui è possibile impostare l'identità aziendale](../../media/mtp-eval-14.png)

7. <span data-ttu-id="4f23d-128">Fare **clic su Vai a Installazione** per completare il provisioning Office 365 E5 tenant di valutazione.</span><span class="sxs-lookup"><span data-stu-id="4f23d-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Immagine della pagina Office 365 E5 di installazione della registrazione della versione di valutazione che richiede di fare clic sul pulsante Vai all'installazione](../../media/mtp-eval-15.png)

8. <span data-ttu-id="4f23d-130">Connessione dominio aziendale al tenant Office 365 aziendale.</span><span class="sxs-lookup"><span data-stu-id="4f23d-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="4f23d-131">[Facoltativo] Scegliere **Connessione un dominio di cui si è già proprietari** e digitare il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="4f23d-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="4f23d-132">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-132">Click **Next**.</span></span>

   ![Immagine of_Office configurazione di 365 E5 in cui personalizzare l'accesso e la posta elettronica](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="4f23d-134">Aggiungere un record TXT o MX per convalidare la proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="4f23d-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="4f23d-135">Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Immagine of_Office configurazione di 365 E5 in cui aggiungere un record TXT di MX per verificare il dominio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="4f23d-137">[Facoltativo] Creare altri account utente per il tenant.</span><span class="sxs-lookup"><span data-stu-id="4f23d-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="4f23d-138">È possibile ignorare questo passaggio facendo clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-138">You can skip this step by clicking **Next**.</span></span>

    ![Pagina of_Office configurazione di 365 E5 in cui è possibile aggiungere altri utenti](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="4f23d-140">[Facoltativo] Scarica Office app.</span><span class="sxs-lookup"><span data-stu-id="4f23d-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="4f23d-141">Fare **clic su** Avanti per ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4f23d-141">Click **Next** to skip this step.</span></span> 

    ![Pagina of_Office 365 E5 in cui puoi installare le tue Office app](../../media/mtp-eval-19.png)

12. <span data-ttu-id="4f23d-143">[Facoltativo] Eseguire la migrazione dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4f23d-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="4f23d-144">Anche in questo caso, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4f23d-144">Again, you can skip this step.</span></span>

    ![Immagine of_Office 365 E5 in cui è possibile impostare se eseguire o meno la migrazione dei messaggi di posta elettronica](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="4f23d-146">Scegliere i servizi online.</span><span class="sxs-lookup"><span data-stu-id="4f23d-146">Choose online services.</span></span> <span data-ttu-id="4f23d-147">Selezionare **Exchange** e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-147">Select **Exchange** and click **Next**.</span></span> 

    ![Immagine of_Office 365 E5 in cui è possibile scegliere i servizi online](../../media/mtp-eval-21.png)

14. <span data-ttu-id="4f23d-149">Aggiungere record MX, CNAME e TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="4f23d-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="4f23d-150">Al termine, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-150">When completed, select **Verify**.</span></span>

    ![Immagine of_Office 365 E5 qui è possibile aggiungere i record DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="4f23d-152">Congratulazioni, hai completato il provisioning del tenant Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="4f23d-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Pagina di conferma del completamento dell'installazione di Of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="4f23d-154">Abilitare Microsoft 365 di valutazione</span><span class="sxs-lookup"><span data-stu-id="4f23d-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="4f23d-155">La registrazione a una versione di valutazione offre 25 licenze utente da usare per un mese.</span><span class="sxs-lookup"><span data-stu-id="4f23d-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="4f23d-156">Per [informazioni dettagliate, vedere Try or Buy an M365 subscription.](../../commerce/try-or-buy-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="4f23d-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="4f23d-157">Da [Amministrazione Microsoft 365,](https://admin.microsoft.com/)fare clic su **Fatturazione** e quindi passare a **Acquista servizi.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="4f23d-158">Seleziona **Microsoft 365 E5** e fai clic su **Avvia versione di valutazione gratuita.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)

3. <span data-ttu-id="4f23d-160">Scegli la preferenza di verifica: tramite un SMS o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="4f23d-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="4f23d-161">Una volta deciso, immettere il numero di telefono, selezionare **Chiamami** o **Chiamami** a seconda della selezione.</span><span class="sxs-lookup"><span data-stu-id="4f23d-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="4f23d-163">Immetti il codice di verifica e fai clic **su Avvia la versione di valutazione gratuita.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="4f23d-165">Fai **clic su Prova ora** per confermare la Microsoft 365 E5 versione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="4f23d-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="4f23d-167">Passare al Centro **Amministrazione Microsoft 365**  >  **utenti Utenti**  >  **attivi**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="4f23d-168">Seleziona l'account utente, seleziona **Gestisci licenze prodotto,** quindi scambia la licenza da Office 365 E5 a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="4f23d-169">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-169">Click **Save**.</span></span>

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile selezionare Microsoft 365 E5 licenza](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="4f23d-171">Selezionare di nuovo l'account amministratore globale, quindi fare clic **su Gestisci nome utente.**</span><span class="sxs-lookup"><span data-stu-id="4f23d-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![Immagine of_Microsoft interfaccia di amministrazione di 365 in cui è possibile selezionare Account e quindi Gestire il nome utente](../../media/mtp-eval-29.png)

8. <span data-ttu-id="4f23d-173">[Facoltativo] Modificare il dominio *da onmicrosoft.com* al proprio dominio, a seconda di ciò che è stato scelto nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="4f23d-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="4f23d-174">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="4f23d-174">Click **Save changes**.</span></span>

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile modificare la preferenza del dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="4f23d-176">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4f23d-176">Next step</span></span>
|[<span data-ttu-id="4f23d-177">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="4f23d-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="4f23d-178">Configurare ogni Microsoft 365 Defender pilastro per il Microsoft 365 Defender di prova o l'ambiente pilota e l'onboardboard degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="4f23d-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
