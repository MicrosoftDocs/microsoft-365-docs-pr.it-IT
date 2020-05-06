---
title: Configurare i pilastri Microsoft Threat Protection per l'ambiente lab di valutazione
description: Configurare i pilastri Microsoft Threat Protection, Office 365 ATP, Azure ATP, Microsoft cloud app Security e Microsoft Defender ATP per l'ambiente di prova Lab
keywords: configurazione di Microsoft Threat Protection Trial, Microsoft Threat Protection Trial Configuration, Configure Microsoft Threat Protection Pillars, Microsoft Threat Protection Pillars
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
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049510"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="a0a49-104">Configurare i pilastri Microsoft Threat Protection per l'ambiente lab di valutazione</span><span class="sxs-lookup"><span data-stu-id="a0a49-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="a0a49-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a0a49-105">**Applies to:**</span></span>
- <span data-ttu-id="a0a49-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0a49-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="a0a49-107">La creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la distribuzione di questo è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="a0a49-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparare l'ambiente di laboratorio di valutazione di Microsoft Threat Protection" />
      <br/><span data-ttu-id="a0a49-109">Fase 1: preparazione</a></span><span class="sxs-lookup"><span data-stu-id="a0a49-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurare l'ambiente di test lab di Microsoft Threat Protection" />
      <br/><span data-ttu-id="a0a49-111">Fase 2: installazione</a></span><span class="sxs-lookup"><span data-stu-id="a0a49-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurare ogni pilastro Microsoft Threat Protection per l'ambiente di test lab di Microsoft Threat Protection e gli endpoint di bordo" />
      <br/><span data-ttu-id="a0a49-113">Fase 3: configurare & onboard</a></span><span class="sxs-lookup"><span data-stu-id="a0a49-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="a0a49-114">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a0a49-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="a0a49-115">La preparazione è la chiave per una distribuzione corretta.</span><span class="sxs-lookup"><span data-stu-id="a0a49-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="a0a49-116">In questo articolo verranno illustrati i punti che è necessario prendere in considerazione durante la preparazione per la distribuzione di Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a0a49-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="a0a49-117">Pilastri di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0a49-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="a0a49-118">Microsoft Threat Protection è costituito da quattro pilastri.</span><span class="sxs-lookup"><span data-stu-id="a0a49-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="a0a49-119">Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione della rete, l'abilitazione dei quattro pilastri Microsoft Threat Protection darà alla propria organizzazione il massimo valore.</span><span class="sxs-lookup"><span data-stu-id="a0a49-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![Of_page immagine](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="a0a49-121">In questa sezione viene illustrata la configurazione:</span><span class="sxs-lookup"><span data-stu-id="a0a49-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="a0a49-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0a49-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="a0a49-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0a49-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="a0a49-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a0a49-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="a0a49-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0a49-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="a0a49-126">Configurare Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0a49-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="a0a49-127">Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0a49-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="a0a49-128">È presente un modulo di PowerShell denominato l' *analizzatore di configurazione consigliato di Office 365 Advanced Threat Protection (Orca)* che consente di determinare alcune di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a0a49-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="a0a49-129">Quando si esegue il ruolo di amministratore nel tenant, Get-ORCAReport contribuirà a generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre informazioni di igiene dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a0a49-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="a0a49-130">È possibile scaricare il modulo da https://www.powershellgallery.com/packages/ORCA/.</span><span class="sxs-lookup"><span data-stu-id="a0a49-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="a0a49-131">Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat Management** > **policy**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="a0a49-132">![Of_page immagine](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="a0a49-133">Fare clic su **ATP anti-phishing**, selezionare **Crea** e compila il nome e la descrizione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="a0a49-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="a0a49-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-134">Click **Next**.</span></span>
<span data-ttu-id="a0a49-135">![Of_page immagine](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="a0a49-136">Modificare i criteri avanzati di anti-phishing ATP.</span><span class="sxs-lookup"><span data-stu-id="a0a49-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="a0a49-137">Modificare la **soglia di phishing avanzata** su **2-aggressiva**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="a0a49-138">Fare clic sul menu a discesa **Aggiungi condizione** e selezionare il dominio o i domini come dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a0a49-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="a0a49-139">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-139">Click **Next**.</span></span>
<span data-ttu-id="a0a49-140">![Of_page immagine](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="a0a49-141">Esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a0a49-141">Review your settings.</span></span> <span data-ttu-id="a0a49-142">Fare clic su **crea questo criterio** per confermare.</span><span class="sxs-lookup"><span data-stu-id="a0a49-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="a0a49-143">![Of_page immagine](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="a0a49-144">Selezionare **allegati sicuri di ATP** e selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .</span><span class="sxs-lookup"><span data-stu-id="a0a49-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="a0a49-145">![Of_page immagine](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="a0a49-146">Fare clic sull'icona + per creare un nuovo criterio allegato sicuro, applicarlo come dominio destinatario ai domini.</span><span class="sxs-lookup"><span data-stu-id="a0a49-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="a0a49-147">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-147">Click **Save**.</span></span>
<span data-ttu-id="a0a49-148">![Of_page immagine](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="a0a49-149">Successivamente, selezionare il criterio **collegamenti sicuri ATP** , quindi fare clic sull'icona a forma di matita per modificare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="a0a49-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="a0a49-150">Verificare che l'opzione non **rintracci quando gli utenti fanno clic su collegamenti sicuri** non è selezionata, mentre le altre opzioni sono selezionate.</span><span class="sxs-lookup"><span data-stu-id="a0a49-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="a0a49-151">Per informazioni dettagliate, vedere [Safe Links Settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="a0a49-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="a0a49-152">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-152">Click **Save**.</span></span> 
<span data-ttu-id="a0a49-153">![Of_page immagine](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="a0a49-154">Selezionare quindi il criterio **antimalware** , selezionare l'impostazione predefinita e scegliere l'icona a forma di matita.</span><span class="sxs-lookup"><span data-stu-id="a0a49-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="a0a49-155">Fare clic su **Impostazioni** e selezionare **Sì e utilizzare il testo di notifica predefinito** per abilitare la **risposta di rilevamento malware**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="a0a49-156">Attiva il **filtro dei tipi di allegati comuni** .</span><span class="sxs-lookup"><span data-stu-id="a0a49-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="a0a49-157">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-157">Click **Save**.</span></span>
<br><span data-ttu-id="a0a49-158">![Of_page immagine](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="a0a49-159">Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **log di controllo** di ricerca e attivazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="a0a49-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="a0a49-160">![Of_page immagine](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="a0a49-161">Integrazione di Office 365 ATP con Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a0a49-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="a0a49-162">Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat Management** > **Explorer** e selezionare le **impostazioni di WDATP** nell'angolo superiore destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="a0a49-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="a0a49-163">Nella finestra di dialogo Microsoft Defender ATP Connection, abilitare **Connect to Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="a0a49-164">![Of_page immagine](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="a0a49-165">Configurare la protezione avanzata dalle minacce di Azure</span><span class="sxs-lookup"><span data-stu-id="a0a49-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="a0a49-166">Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Azure</span><span class="sxs-lookup"><span data-stu-id="a0a49-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="a0a49-167">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info) > selezionare **altre risorse** > **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="a0a49-168">![Of_page immagine](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="a0a49-169">Fare clic su **Crea** per avviare la procedura guidata di Azure Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="a0a49-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="a0a49-170">![Of_page immagine](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="a0a49-171">Scegliere **Fornisci un nome utente e una password per connettersi alla foresta di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="a0a49-172">![Of_page immagine](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="a0a49-173">Immettere le credenziali di Active Directory in locale.</span><span class="sxs-lookup"><span data-stu-id="a0a49-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="a0a49-174">Può trattarsi di qualsiasi account utente che disponga dell'accesso in lettura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a0a49-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="a0a49-175">![Of_page immagine](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="a0a49-176">Successivamente, scegliere **download Sensor Setup** and transfer file to your domain controller.</span><span class="sxs-lookup"><span data-stu-id="a0a49-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="a0a49-177">![Of_page immagine](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="a0a49-178">Eseguire il programma di installazione del sensore ATP di Azure e iniziare a seguire la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0a49-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="a0a49-179">![Of_page immagine](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="a0a49-180">Fare clic su **Avanti** nel tipo di distribuzione del sensore.</span><span class="sxs-lookup"><span data-stu-id="a0a49-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="a0a49-181">![Of_page immagine](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="a0a49-182">Copiare il tasto di accesso poiché sarà necessario immetterlo successivamente nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0a49-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="a0a49-183">![Of_page immagine](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="a0a49-184">Copiare la chiave di accesso nella procedura guidata e fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="a0a49-185">![Of_page immagine](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="a0a49-186">Congratulazioni, è stata configurata correttamente la protezione avanzata dalle minacce di Azure nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="a0a49-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="a0a49-187">![Of_page immagine](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="a0a49-188">Nella sezione impostazioni [ATP di Azure Azure](https://go.microsoft.com/fwlink/?linkid=2040449) selezionare **Windows Defender ATP**e quindi attivare l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="a0a49-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="a0a49-189">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-189">Click **Save**.</span></span> 
<span data-ttu-id="a0a49-190">![Of_page immagine](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="a0a49-191">Windows Defender ATP è stato rebranded As Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a0a49-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="a0a49-192">Le modifiche di rebranding in tutti i portali vengono distribuite per garantire la coerenza.</span><span class="sxs-lookup"><span data-stu-id="a0a49-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="a0a49-193">Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="a0a49-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="a0a49-194">Ignorare questo passaggio se è già stata abilitata la sicurezza delle app cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0a49-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="a0a49-195">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info) > **altre risorse** > **Microsoft cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="a0a49-196">![Of_page immagine](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="a0a49-197">Alla richiesta di informazioni per l'integrazione di Azure ATP, selezionare **Enable Azure ATP Data Integration**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="a0a49-198">![Of_page immagine](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="a0a49-199">Se questo messaggio non viene visualizzato, potrebbe significare che l'integrazione dei dati ATP di Azure è già stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="a0a49-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="a0a49-200">Tuttavia, se non si è certi, contattare l'amministratore IT per confermare.</span><span class="sxs-lookup"><span data-stu-id="a0a49-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="a0a49-201">Andare a **Impostazioni**, attivare l'interruttore di **integrazione ATP di Azure** , quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="a0a49-202">![Of_page immagine](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="a0a49-203">Per le nuove istanze di Azure ATP, questo interruttore di integrazione viene attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a0a49-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="a0a49-204">Verificare che l'integrazione di Azure ATP sia stata abilitata prima di procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a0a49-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="a0a49-205">In impostazioni di individuazione cloud selezionare **Microsoft Defender ATP Integration**e quindi abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="a0a49-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="a0a49-206">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-206">Click **Save**.</span></span>
<span data-ttu-id="a0a49-207">![Of_page immagine](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="a0a49-208">In impostazioni di individuazione cloud selezionare **arricchimento degli utenti**e quindi abilitare l'integrazione con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a0a49-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="a0a49-209">![Of_page immagine](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="a0a49-210">Configurare Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0a49-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="a0a49-211">Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a0a49-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="a0a49-212">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info) > **altre risorse** > **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="a0a49-213">Fare clic su **Apri**. </span><span class="sxs-lookup"><span data-stu-id="a0a49-213">Click **Open**.</span></span>
<br><span data-ttu-id="a0a49-214">![Of_page immagine](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="a0a49-215">Seguire la procedura guidata Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="a0a49-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="a0a49-216">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-216">Click **Next**.</span></span> 
<br><span data-ttu-id="a0a49-217">![Of_page immagine](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="a0a49-218">Scegliere in base alla posizione di archiviazione dei dati preferita, al criterio di conservazione dei dati, alle dimensioni dell'organizzazione e all'opt-in per le funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="a0a49-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="a0a49-219">![Of_page immagine](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="a0a49-220">Non è possibile modificare alcune impostazioni, ad esempio il percorso di archiviazione dei dati, in seguito.</span><span class="sxs-lookup"><span data-stu-id="a0a49-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="a0a49-221">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-221">Click **Next**.</span></span> 

4. <span data-ttu-id="a0a49-222">Fare clic su **continua** e verrà eseguito il provisioning del tenant Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a0a49-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="a0a49-223">![Of_page immagine](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="a0a49-224">Onboard your Endpoints tramite criteri di gruppo, Microsoft Endpoint Manager o esecuzione di uno script locale in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a0a49-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="a0a49-225">Per semplicità, in questa guida viene utilizzato lo script locale.</span><span class="sxs-lookup"><span data-stu-id="a0a49-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="a0a49-226">Fare clic su **Scarica pacchetto** e copiare lo script di onboarding negli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a0a49-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="a0a49-227">![Of_page immagine](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="a0a49-228">Nell'endpoint, eseguire lo script onboarding come amministratore e scegliere Y.</span><span class="sxs-lookup"><span data-stu-id="a0a49-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="a0a49-229">![Of_page immagine](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="a0a49-230">Congratulazioni, è stato installato il primo endpoint.</span><span class="sxs-lookup"><span data-stu-id="a0a49-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Of_page immagine](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="a0a49-232">Copia e incolla il test di rilevamento dalla procedura guidata ATP di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a0a49-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="a0a49-233">![Of_page immagine](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="a0a49-234">Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="a0a49-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="a0a49-235">![Of_page immagine](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="a0a49-236">Fare clic su **avvia tramite Microsoft Defender ATP** dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a0a49-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="a0a49-237">![Of_page immagine](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="a0a49-238">Visitare il [Centro sicurezza di Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="a0a49-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="a0a49-239">Andare a **Impostazioni** , quindi selezionare **funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="a0a49-240">![Of_page immagine](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="a0a49-241">Attiva l'integrazione con **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="a0a49-242">![Of_page immagine](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="a0a49-243">Attiva l'integrazione con **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="a0a49-244">![Of_page immagine](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="a0a49-245">Attiva l'integrazione con **Microsoft cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="a0a49-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="a0a49-246">![Of_page immagine](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="a0a49-247">Scorrere verso il basso e fare clic su **Salva preferenze** per confermare le nuove integrazioni.</span><span class="sxs-lookup"><span data-stu-id="a0a49-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="a0a49-248">![Of_page immagine](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="a0a49-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="a0a49-249">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a0a49-249">Next steps</span></span>
<span data-ttu-id="a0a49-250">[Attiva Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) e quindi [genera un avviso di test](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="a0a49-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
