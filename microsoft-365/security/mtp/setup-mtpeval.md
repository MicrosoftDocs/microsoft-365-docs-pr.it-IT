---
title: Configurare l'ambiente di test lab di Microsoft Threat Protection
description: Accedere a Microsoft 365 Security Center e quindi configurare l'ambiente di test lab di Microsoft Threat Protection
keywords: Installazione di valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab Setup
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049616"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="22269-104">Configurare l'ambiente di test lab di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="22269-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="22269-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="22269-105">**Applies to:**</span></span>
- <span data-ttu-id="22269-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="22269-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="22269-107">La creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la distribuzione di questo è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="22269-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparare il laboratorio di valutazione di Microsoft Threat Protection" />
      <br/><span data-ttu-id="22269-109">Fase 1: preparazione</a></span><span class="sxs-lookup"><span data-stu-id="22269-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurare il laboratorio di valutazione di Microsoft Threat Protection" />
      <br/><span data-ttu-id="22269-111">Fase 2: installazione</a></span><span class="sxs-lookup"><span data-stu-id="22269-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configurare ogni pilastro Microsoft Threat Protection per l'ambiente di test lab di Microsoft Threat Protection e onboard your Endpoints" />
      <br/><span data-ttu-id="22269-113">Fase 3: configurare & onboard</a></span><span class="sxs-lookup"><span data-stu-id="22269-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="22269-114">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="22269-114">You are currently in the set up phase.</span></span> <span data-ttu-id="22269-115">Eseguire la procedura iniziale per accedere a Microsoft 365 Security Center e quindi configurare l'ambiente di prova.</span><span class="sxs-lookup"><span data-stu-id="22269-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="22269-116">Iscriversi a una sottoscrizione di Office 365 o Azure Active Directory per generare un tenant con *estensione onmicrosoft.com* che è possibile utilizzare per iscriversi alla propria licenza Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="22269-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="22269-117">Se si dispone già di una sottoscrizione di Office 365 o di Azure Active Directory, è possibile ignorare la procedura di creazione del tenant di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="22269-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="22269-118">In questa fase, verranno guidati i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="22269-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="22269-119">Creare un tenant di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="22269-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="22269-120">Abilitare la sottoscrizione di valutazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22269-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="22269-121">Creare un tenant di valutazione di Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="22269-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="22269-122">Se si dispone già di una sottoscrizione di Office 365 o di Azure Active Directory, è possibile ignorare la procedura di creazione del tenant di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="22269-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="22269-123">Andare al [portale del prodotto Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selezionare **versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="22269-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="22269-124">![Of_page immagine](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="22269-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="22269-125">Completare la registrazione di prova inserendo l'indirizzo di posta elettronica (personale o aziendale).</span><span class="sxs-lookup"><span data-stu-id="22269-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="22269-126">Fare clic su **Configura account**.</span><span class="sxs-lookup"><span data-stu-id="22269-126">Click **Set up account**.</span></span>
<span data-ttu-id="22269-127">![Of_page immagine](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="22269-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="22269-128">Inserire il nome, il cognome, il numero di telefono aziendale, il nome della società, la dimensione dell'azienda e il paese o l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="22269-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Of_page immagine](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="22269-130">Il paese o l'area geografica impostata in questa sezione determina l'area del Data Center in cui verrà ospitata la sede di Office 365.</span><span class="sxs-lookup"><span data-stu-id="22269-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="22269-131">Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="22269-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="22269-132">Fare clic su **Invia codice di verifica**.</span><span class="sxs-lookup"><span data-stu-id="22269-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="22269-133">![Of_page immagine](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="22269-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="22269-134">Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="22269-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="22269-135">![Of_page immagine](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="22269-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="22269-136">Configurare la prima identità che sarà un amministratore globale per il tenant.</span><span class="sxs-lookup"><span data-stu-id="22269-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="22269-137">Immettere il **nome** e la **password**.</span><span class="sxs-lookup"><span data-stu-id="22269-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="22269-138">Fare clic su **Iscriviti**.</span><span class="sxs-lookup"><span data-stu-id="22269-138">Click **Sign up**.</span></span>
<span data-ttu-id="22269-139">![Of_page immagine](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="22269-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="22269-140">c</span><span class="sxs-lookup"><span data-stu-id="22269-140">c</span></span>
7. <span data-ttu-id="22269-141">Fare clic su **Vai al programma di installazione** per completare il provisioning del tenant di valutazione di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="22269-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="22269-142">![Of_page immagine](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="22269-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="22269-143">Connettere il dominio aziendale al tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="22269-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="22269-144">Optional Scegliere **Connect a Domain your già own** e digitare il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="22269-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="22269-145">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="22269-145">Click **Next**.</span></span>
<br><span data-ttu-id="22269-146">![Of_page immagine](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="22269-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="22269-147">Sarà necessario aggiungere un record TXT o MX per convalidare la proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="22269-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="22269-148">Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="22269-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="22269-149">![Of_page immagine](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="22269-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="22269-150">Optional Creare più account utente per il tenant.</span><span class="sxs-lookup"><span data-stu-id="22269-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="22269-151">È possibile ignorare questo passaggio facendo clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="22269-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="22269-152">![Of_page immagine](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="22269-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="22269-153">Optional Scaricare le app di Office.</span><span class="sxs-lookup"><span data-stu-id="22269-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="22269-154">Fare clic su **Avanti** per ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="22269-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="22269-155">![Of_page immagine](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="22269-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="22269-156">Optional Eseguire la migrazione dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="22269-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="22269-157">Anche in questo caso, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="22269-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="22269-158">![Of_page immagine](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="22269-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="22269-159">Scegliere servizi online.</span><span class="sxs-lookup"><span data-stu-id="22269-159">Choose online services.</span></span> <span data-ttu-id="22269-160">Selezionare **Exchange** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="22269-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="22269-161">![Of_page immagine](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="22269-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="22269-162">Aggiungere i record MX, CNAME e TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="22269-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="22269-163">Al termine, selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="22269-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="22269-164">![Of_page immagine](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="22269-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="22269-165">Congratulazioni, è stato completato il provisioning del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="22269-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="22269-166">![Of_page immagine](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="22269-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="22269-167">Abilitare la sottoscrizione di valutazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22269-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="22269-168">La registrazione per una versione di valutazione fornisce 25 licenze utente da utilizzare per un mese.</span><span class="sxs-lookup"><span data-stu-id="22269-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="22269-169">Per ulteriori informazioni, vedere [provare o acquistare un abbonamento a M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="22269-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="22269-170">Dall'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/), fare clic su **fatturazione** , quindi passare a **acquisto servizi**.</span><span class="sxs-lookup"><span data-stu-id="22269-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="22269-171">Selezionare **Microsoft 365 E5** e fare clic su **Avvia versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="22269-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="22269-172">![Of_page immagine](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="22269-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="22269-173">Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata.</span><span class="sxs-lookup"><span data-stu-id="22269-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="22269-174">Dopo aver deciso, immettere il numero di telefono, selezionare **Text me** or **Call me** a seconda della selezione.</span><span class="sxs-lookup"><span data-stu-id="22269-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="22269-175">![Of_page immagine](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="22269-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="22269-176">Immettere il codice di verifica e fare clic su **Avvia la versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="22269-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="22269-177">![Of_page immagine](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="22269-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="22269-178">Fare clic su **prova ora** per confermare la versione di valutazione di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="22269-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="22269-179">![Of_page immagine](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="22269-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="22269-180">Accedere agli utenti**attivi**degli > **utenti** > dell'interfaccia di **amministrazione di Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="22269-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="22269-181">Selezionare l'account utente, selezionare **Gestisci licenze di prodotto**, quindi scambiare la licenza da Office 365 E5 a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="22269-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="22269-182">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="22269-182">Click **Save**.</span></span>
<span data-ttu-id="22269-183">![Of_page immagine](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="22269-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="22269-184">Selezionare di nuovo l'account di amministratore globale e quindi fare clic su **Gestisci nome utente**.</span><span class="sxs-lookup"><span data-stu-id="22269-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="22269-185">![Of_page immagine](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="22269-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="22269-186">Optional Modificare il dominio da *onmicrosoft.com* al proprio dominio, a seconda di cosa si è scelto nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="22269-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="22269-187">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="22269-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="22269-188">![Of_page immagine](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="22269-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="22269-189">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="22269-189">Next step</span></span>
<span data-ttu-id="22269-190">||| |:-------|:-----| config-onboard. png)</span><span class="sxs-lookup"><span data-stu-id="22269-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="22269-191">[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro Microsoft Threat Protection per l'ambiente di test lab di Microsoft Threat Protection e onboard your Endpoints.</span><span class="sxs-lookup"><span data-stu-id="22269-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>
