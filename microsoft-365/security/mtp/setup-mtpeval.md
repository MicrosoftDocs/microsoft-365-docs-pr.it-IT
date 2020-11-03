---
title: Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota
description: Accedere a Microsoft 365 Security Center e quindi configurare l'ambiente di valutazione di Microsoft 365 Defender
keywords: Installazione di valutazione di Microsoft Threat Protection, installazione pilota di Microsoft Threat Protection, provare Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab Setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 47f4ceeebd50784b1880a028ebe2698012c406da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844825"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="f4566-104">Configurare l'ambiente di test lab di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4566-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f4566-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f4566-105">**Applies to:**</span></span>
- <span data-ttu-id="f4566-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4566-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="f4566-107">La creazione di un ambiente pilota o di un laboratorio di valutazione di Microsoft 365 Defender è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="f4566-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Preparare il laboratorio di valutazione di Microsoft 365 Defender o l'ambiente pilota" />
      <br/><span data-ttu-id="f4566-109">Fase 1: preparazione </a></span><span class="sxs-lookup"><span data-stu-id="f4566-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota" />
      <br/><span data-ttu-id="f4566-111">Fase 2: installazione </a></span><span class="sxs-lookup"><span data-stu-id="f4566-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints" title="
Configurare ogni pilastro Microsoft 365 Defender per il laboratorio di valutazione di Microsoft 365 Defender o l'ambiente pilota e onboard your Endpoints" />
      <br/><span data-ttu-id="f4566-113">Fase 3: configurare & onboard </a></span><span class="sxs-lookup"><span data-stu-id="f4566-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="f4566-114">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f4566-114">You're currently in the set up phase.</span></span> <span data-ttu-id="f4566-115">Eseguire i passaggi iniziali per accedere a Microsoft 365 Security Center e quindi configurare il laboratorio di valutazione o l'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="f4566-115">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="f4566-116">Iscriversi a una sottoscrizione di Office 365 o Azure Active Directory per generare un tenant con *estensione onmicrosoft.com* che è possibile utilizzare per iscriversi alla propria licenza Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4566-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="f4566-117">Se si dispone già di una sottoscrizione di Office 365 o Azure Active Directory, è possibile ignorare i passaggi di valutazione di Office 365 E5 o di creazione di tenant pilota.</span><span class="sxs-lookup"><span data-stu-id="f4566-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="f4566-118">In questa fase, verranno guidati i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="f4566-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="f4566-119">Creare un tenant di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f4566-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="f4566-120">Abilitare la sottoscrizione di valutazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4566-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="f4566-121">Creare un tenant di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f4566-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="f4566-122">Se si dispone già di una sottoscrizione di Office 365 o di Azure Active Directory, è possibile ignorare la procedura di creazione del tenant di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4566-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="f4566-123">Andare al [portale del prodotto Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selezionare **versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="f4566-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Image of_Office 365 E5 versione di valutazione gratuita](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="f4566-125">Completare la registrazione di prova inserendo l'indirizzo di posta elettronica (personale o aziendale).</span><span class="sxs-lookup"><span data-stu-id="f4566-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="f4566-126">Fare clic su **Configura account**.</span><span class="sxs-lookup"><span data-stu-id="f4566-126">Click **Set up account**.</span></span>

   ![Pagina immagine of_Office 365 E5 registrazione di prova](../../media/mtp-eval-10.png)

3. <span data-ttu-id="f4566-128">Inserire il nome, il cognome, il numero di telefono aziendale, il nome della società, la dimensione dell'azienda e il paese o l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="f4566-128">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Immagine of_Office 365 E5 pagina di installazione di registrazione di prova per i dettagli relativi a nome, telefono e società](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="f4566-130">Il paese o l'area geografica impostata in questa sezione determina l'area del Data Center in cui verrà ospitata la sede di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4566-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="f4566-131">Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="f4566-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f4566-132">Fare clic su **Invia codice di verifica**.</span><span class="sxs-lookup"><span data-stu-id="f4566-132">Click **Send Verification Code**.</span></span> 

   ![Immagine of_Office 365 E5 registrazione di prova pagina di installazione per richiedere la preferenza di verifica](../../media/mtp-eval-12.png)

5. <span data-ttu-id="f4566-134">Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4566-134">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Immagine of_Office pagina di installazione di registrazione di prova 365 E5 in cui è possibile configurare il nome di dominio personalizzato](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="f4566-136">Impostare la prima identità, che sarà un amministratore globale per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f4566-136">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="f4566-137">Immettere il **nome** e la **password**.</span><span class="sxs-lookup"><span data-stu-id="f4566-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="f4566-138">Fare clic su **Iscriviti**.</span><span class="sxs-lookup"><span data-stu-id="f4566-138">Click **Sign up**.</span></span>

   ![Immagine of_Office pagina di installazione di registrazione di prova 365 E5 in cui è possibile impostare l'identità aziendale](../../media/mtp-eval-14.png)

7. <span data-ttu-id="f4566-140">Fare clic su **Vai al programma di installazione** per completare il provisioning del tenant di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4566-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Immagine della pagina di installazione di registrazione di prova di Office 365 E5 che richiede di fare clic su Vai imposta pulsante](../../media/mtp-eval-15.png)

8. <span data-ttu-id="f4566-142">Connettere il dominio aziendale al tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4566-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="f4566-143">Optional Scegliere **Connect a Domain your già own** e digitare il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="f4566-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="f4566-144">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4566-144">Click **Next**.</span></span>

   ![Image of_Office pagina di installazione di 365 E5 dove è necessario personalizzare l'accesso e la posta elettronica](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="f4566-146">Aggiungere un record TXT o MX per convalidare la proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="f4566-146">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="f4566-147">Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="f4566-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Image of_Office pagina di installazione di 365 E5 dove è necessario aggiungere un record TXT di MX per verificare il dominio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="f4566-149">Optional Creare più account utente per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f4566-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="f4566-150">È possibile ignorare questo passaggio facendo clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4566-150">You can skip this step by clicking **Next**.</span></span>

    ![Pagina di installazione di Image of_Office 365 E5 dove è possibile aggiungere altri utenti](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="f4566-152">Optional Scaricare le app di Office.</span><span class="sxs-lookup"><span data-stu-id="f4566-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="f4566-153">Fare clic su **Avanti** per ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f4566-153">Click **Next** to skip this step.</span></span> 

    ![Image of_Office 365 E5 page dove è possibile installare le app di Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="f4566-155">Optional Eseguire la migrazione dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f4566-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="f4566-156">Anche in questo caso, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f4566-156">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5 dove è possibile impostare se eseguire la migrazione o meno dei messaggi di posta elettronica](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="f4566-158">Scegliere servizi online.</span><span class="sxs-lookup"><span data-stu-id="f4566-158">Choose online services.</span></span> <span data-ttu-id="f4566-159">Selezionare **Exchange** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f4566-159">Select **Exchange** and click **Next**.</span></span> 

    ![Image of_Office 365 E5 dove è possibile scegliere i servizi online](../../media/mtp-eval-21.png)

14. <span data-ttu-id="f4566-161">Aggiungere i record MX, CNAME e TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="f4566-161">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="f4566-162">Al termine, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="f4566-162">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 è possibile aggiungere i record DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="f4566-164">Congratulazioni, è stato completato il provisioning del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4566-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Pagina di conferma del completamento dell'installazione di Image of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="f4566-166">Abilitare la sottoscrizione di valutazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4566-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="f4566-167">La registrazione per una versione di valutazione fornisce 25 licenze utente da utilizzare per un mese.</span><span class="sxs-lookup"><span data-stu-id="f4566-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="f4566-168">Per ulteriori informazioni, vedere [provare o acquistare un abbonamento a M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="f4566-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="f4566-169">Dall'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/), fare clic su **fatturazione** , quindi passare a **acquisto servizi**.</span><span class="sxs-lookup"><span data-stu-id="f4566-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="f4566-170">Selezionare **Microsoft 365 E5** e fare clic su **Avvia versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="f4566-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Pagina immagine of_Microsoft 365 E5 inizio versione di valutazione gratuita](../../media/mtp-eval-24.png)

3. <span data-ttu-id="f4566-172">Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="f4566-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f4566-173">Dopo aver deciso, immettere il numero di telefono, selezionare **Text me** or **Call me** a seconda della selezione.</span><span class="sxs-lookup"><span data-stu-id="f4566-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Immagine of_Microsoft 365 E5 avvio della pagina di valutazione gratuita per richiedere informazioni di contatto per inviare codice per dimostrare che non sei un robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="f4566-175">Immettere il codice di verifica e fare clic su **Avvia la versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="f4566-175">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 avviare la pagina di valutazione gratuita dove è possibile compilare il codice di verifica del sistema inviato per dimostrare che non si è un robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="f4566-177">Fare clic su **prova ora** per confermare la versione di valutazione di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4566-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Immagine of_Microsoft 365 E5 avviare la pagina di prova gratuita in cui è necessario Clock il pulsante prova ora per iniziare](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="f4566-179">Accedere agli utenti attivi degli utenti dell'interfaccia di **amministrazione di Microsoft 365**  >  **Users**  >  **Active users**.</span><span class="sxs-lookup"><span data-stu-id="f4566-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="f4566-180">Selezionare l'account utente, selezionare **Gestisci licenze di prodotto** , quindi scambiare la licenza da Office 365 E5 a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="f4566-180">Select your user account, select **Manage product licenses** , then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="f4566-181">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f4566-181">Click **Save**.</span></span>

   ![Image of_Microsoft 365 pagina dell'interfaccia di amministrazione in cui è possibile selezionare la licenza Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="f4566-183">Selezionare di nuovo l'account di amministratore globale e quindi fare clic su **Gestisci nome utente**.</span><span class="sxs-lookup"><span data-stu-id="f4566-183">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 pagina dell'interfaccia di amministrazione in cui è possibile selezionare account e quindi Gestione nome utente](../../media/mtp-eval-29.png)

8. <span data-ttu-id="f4566-185">Optional Modificare il dominio da *onmicrosoft.com* al proprio dominio, a seconda di cosa si è scelto nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="f4566-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="f4566-186">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="f4566-186">Click **Save changes**.</span></span>

   ![Image of_Microsoft 365 pagina dell'interfaccia di amministrazione in cui è possibile modificare la preferenza del dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="f4566-188">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f4566-188">Next step</span></span>
|<span data-ttu-id="f4566-189">![Fase 3: configurare & onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="f4566-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="f4566-190">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="f4566-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="f4566-191">Configurare ogni pilastro Microsoft 365 Defender per il laboratorio di valutazione di Microsoft 365 Defender o l'ambiente pilota e onboard your Endpoints.</span><span class="sxs-lookup"><span data-stu-id="f4566-191">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
