---
title: Configurare i pilastri di Microsoft 365 Defender per il laboratorio di valutazione o l'ambiente pilota
description: Configurare i pilastri di Microsoft 365 Defender, ad esempio Microsoft Defender per Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security e Microsoft Defender for Endpoint, per il laboratorio di valutazione o l'ambiente pilota.
keywords: configurare la versione di valutazione di Microsoft Threat Protection, la configurazione di valutazione di Microsoft Threat Protection, configurare il progetto pilota di Microsoft Threat Protection, configurare i pilastri di Microsoft Threat Protection, i pilastri di Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 9b192a029704d1354867b169efdf0d489345030e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580967"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="27216-104">Configurare i pilastri di Microsoft 365 Defender per il laboratorio di valutazione o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="27216-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="27216-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="27216-105">**Applies to:**</span></span>
- <span data-ttu-id="27216-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27216-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="27216-107">La creazione di un laboratorio di valutazione o di un ambiente pilota di Microsoft 365 Defender e la distribuzione è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="27216-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="27216-108">[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="27216-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="27216-109">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="27216-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="27216-110">[![Fase 2: configurazione](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="27216-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="27216-111">Fase 2: configurazione</span><span class="sxs-lookup"><span data-stu-id="27216-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Phase 3: onboarding](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="27216-113">Fase 3: onboarding</span><span class="sxs-lookup"><span data-stu-id="27216-113">Phase 3: Onboard</span></span> | <span data-ttu-id="27216-114">[![Torna al progetto pilota](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="27216-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="27216-115">Torna al playbook pilota</span><span class="sxs-lookup"><span data-stu-id="27216-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="27216-116">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="27216-116">*You are here!*</span></span> | |

<span data-ttu-id="27216-117">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27216-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="27216-118">La preparazione è fondamentale per una distribuzione corretta.</span><span class="sxs-lookup"><span data-stu-id="27216-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="27216-119">In questo articolo, sarai guidato sui punti da considerare durante la preparazione della distribuzione di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="27216-120">Pilastri di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27216-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="27216-121">Microsoft 365 Defender è costituito da quattro pilastri.</span><span class="sxs-lookup"><span data-stu-id="27216-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="27216-122">Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione di rete, l'abilitazione dei quattro pilastri di Microsoft 365 Defender offrirà all'organizzazione il massimo valore.</span><span class="sxs-lookup"><span data-stu-id="27216-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Immagine of_Microsoft 365 Defender per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender for Endpoint, per le app cloud, Microsoft Cloud App Security e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="27216-124">Questa sezione ti guiderà a configurare:</span><span class="sxs-lookup"><span data-stu-id="27216-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="27216-125">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="27216-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="27216-126">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="27216-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="27216-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="27216-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="27216-128">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="27216-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="27216-129">Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="27216-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="27216-130">Ignorare questo passaggio se è già stato abilitato Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="27216-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="27216-131">È presente un modulo di PowerShell denominato *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* che consente di determinare alcune di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="27216-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="27216-132">Quando viene eseguito come amministratore nel tenant, get-ORCAReport consente di generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phish e altre impostazioni di igiene dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="27216-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="27216-133">È possibile scaricare questo modulo da https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="27216-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="27216-134">Passare a [Office 365 Security & Compliance Center Threat](https://protection.office.com/homepage)  >  **Management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="27216-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="27216-136">Fare **clic su Anti-phishing,** selezionare **Crea** e compilare il nome e la descrizione del criterio.</span><span class="sxs-lookup"><span data-stu-id="27216-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="27216-137">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27216-137">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="27216-139">Modificare i criteri anti-phishing avanzati in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="27216-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="27216-140">Modificare **la soglia di phishing avanzato** su **2 - Aggressivo.**</span><span class="sxs-lookup"><span data-stu-id="27216-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="27216-141">Fai clic sul menu **a** discesa Aggiungi una condizione e seleziona i domini come dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="27216-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="27216-142">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27216-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="27216-144">Rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="27216-144">Review your settings.</span></span> <span data-ttu-id="27216-145">Fare **clic su Crea questo criterio** per confermare.</span><span class="sxs-lookup"><span data-stu-id="27216-145">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="27216-147">Selezionare **Allegati sicuri** e selezionare **l'opzione Attiva ATP per SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="27216-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & Compliance Center in cui è possibile attivare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="27216-149">Fare clic sull'icona + per creare un nuovo criterio degli allegati sicuri, applicarlo come dominio destinatario ai domini.</span><span class="sxs-lookup"><span data-stu-id="27216-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="27216-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27216-150">Click **Save**.</span></span>

   ![Immagine of_Office 365 Security & Compliance Center in cui è possibile creare un nuovo criterio di creazione di un nuovo allegato sicuro](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="27216-152">Selezionare quindi il criterio **Collegamenti sicuri,** quindi fare clic sull'icona a forma di matita per modificare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="27216-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="27216-153">Assicurarsi che **l'opzione Non tenere traccia** quando gli utenti fanno clic su collegamenti sicuri non sia selezionata, mentre le altre opzioni sono selezionate.</span><span class="sxs-lookup"><span data-stu-id="27216-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="27216-154">Per [informazioni dettagliate, vedere Safe Links settings.](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365)</span><span class="sxs-lookup"><span data-stu-id="27216-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="27216-155">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27216-155">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & Compliance Center che mostra che l'opzione Non tenere traccia quando gli utenti fanno clic su Sicuro non è selezionata](../../media/mtp-eval-38.png)

9. <span data-ttu-id="27216-157">Seleziona quindi il **criterio Antimalware,** seleziona il valore predefinito e scegli l'icona a forma di matita.</span><span class="sxs-lookup"><span data-stu-id="27216-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="27216-158">Fai **clic su** Impostazioni e seleziona Sì e usa il testo di notifica **predefinito** per abilitare Risposta **rilevamento malware.**</span><span class="sxs-lookup"><span data-stu-id="27216-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="27216-159">Attivare il **filtro Tipi di allegati** comuni.</span><span class="sxs-lookup"><span data-stu-id="27216-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="27216-160">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27216-160">Click **Save**.</span></span>

    ![Immagine of_Office 365 Security & Compliance Center che mostra che la risposta di rilevamento malware è attivata con la notifica predefinita e il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="27216-162">Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Search  >  **Audit** log  >  **search** and turn Auditing on.</span><span class="sxs-lookup"><span data-stu-id="27216-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Immagine of_Office 365 Security & Compliance Center in cui è possibile attivare la ricerca nei log di controllo](../../media/mtp-eval-40.png)

12. <span data-ttu-id="27216-164">Integrare Microsoft Defender per Office 365 con Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="27216-165">Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat Management Explorer e selezionare Microsoft Defender for Endpoint Settings nell'angolo in alto  >    >   a destra dello schermo. </span><span class="sxs-lookup"><span data-stu-id="27216-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="27216-166">Nella finestra di dialogo Connessione defender per endpoint attiva Connetti **a Microsoft Defender per Endpoint**.</span><span class="sxs-lookup"><span data-stu-id="27216-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Immagine of_Office 365 Security & Compliance Center in cui è possibile attivare la connessione a Microsoft Defender for Endpoint](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="27216-168">Configurare Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="27216-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="27216-169">Ignora questo passaggio se hai già abilitato Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="27216-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="27216-170">Passare a [Centro sicurezza Microsoft 365](https://security.microsoft.com/info) > **selezionare Altre risorse** Microsoft Defender  >  **per l'identità**.</span><span class="sxs-lookup"><span data-stu-id="27216-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Image of_Microsoft 365 Security Center in cui è disponibile un'opzione per aprire Microsoft Defender for Identity](../../media/mtp-eval-42.png)

2. <span data-ttu-id="27216-172">Fai **clic su** Crea per avviare la procedura guidata di Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="27216-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Immagine of_Microsoft pagina della procedura guidata defender per l'identità in cui fare clic sul pulsante Crea](../../media/mtp-eval-43.png)

3. <span data-ttu-id="27216-174">Scegliere **Fornire un nome utente e una password per connettersi alla foresta di Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="27216-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Pagina di benvenuto of_Microsoft Image of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. <span data-ttu-id="27216-176">Immettere le credenziali di Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="27216-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="27216-177">Può trattarsi di qualsiasi account utente con accesso in lettura ad Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27216-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft Defender for Identity Directory services page where you should put your credentials](../../media/mtp-eval-45.png)

5. <span data-ttu-id="27216-179">Successivamente, scegliere **Download Sensor Setup** and transfer file to your domain controller.</span><span class="sxs-lookup"><span data-stu-id="27216-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Pagina of_Microsoft Defender for Identity in cui puoi selezionare Scarica configurazione sensore](../../media/mtp-eval-46.png)

6. <span data-ttu-id="27216-181">Eseguire l'installazione del sensore di identità di Microsoft Defender per e iniziare a seguire la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="27216-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Immagine of_Microsoft defender per l'identità in cui fare clic su avanti per seguire la procedura guidata sensore di Microsoft Defender for Identity](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="27216-183">Fare **clic su Avanti** nel tipo di distribuzione del sensore.</span><span class="sxs-lookup"><span data-stu-id="27216-183">Click **Next** at the sensor deployment type.</span></span>

   ![Image of_Microsoft Defender for Identity page where you should click next to go to next page](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="27216-185">Copiare il tasto di scelta perché è necessario immetterlo successivamente nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="27216-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Pagina of_the sensori di immagine in cui copiare il tasto di scelta che è necessario immettere nella pagina successiva della configurazione guidata del sensore di identità di Microsoft Defender for Identity](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="27216-187">Copiare il tasto di scelta nella procedura guidata e fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="27216-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Microsoft Defender for Identity sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)

10. <span data-ttu-id="27216-189">Congratulazioni, Microsoft Defender è stato configurato correttamente per l'identità nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="27216-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="27216-191">Nella sezione [Impostazioni di Microsoft Defender per l'identità](https://go.microsoft.com/fwlink/?linkid=2040449) seleziona \*\*Microsoft Defender per Endpoint \*\*, quindi attiva l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="27216-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="27216-192">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27216-192">Click **Save**.</span></span> 

    ![Immagine of_the pagina delle impostazioni di Microsoft Defender per l'identità in cui attivare l'interruttore Microsoft Defender for Endpoint](../../media/mtp-eval-52.png)

> [!NOTE]
> <span data-ttu-id="27216-194">Windows Defender ATP è stato rebranded come Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="27216-195">È in corso l'implementazione delle modifiche di rebranding in tutti i portali per garantire la coerenza.</span><span class="sxs-lookup"><span data-stu-id="27216-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="27216-196">Configurare Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="27216-196">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="27216-197">Ignora questo passaggio se hai già abilitato Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="27216-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="27216-198">Passare a [Centro sicurezza Microsoft 365 Altre](https://security.microsoft.com/info)  >  **risorse** Microsoft Cloud  >  **App Security**.</span><span class="sxs-lookup"><span data-stu-id="27216-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Immagine of_Microsoft pagina del Centro sicurezza 365 in cui è possibile visualizzare la scheda Microsoft Cloud App e fare clic sul pulsante Apri](../../media/mtp-eval-53.png)

2. <span data-ttu-id="27216-200">Al prompt delle informazioni per integrare Microsoft Defender for Identity, seleziona **Abilita Microsoft Defender per l'integrazione dei dati di identità.**</span><span class="sxs-lookup"><span data-stu-id="27216-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Richiesta di of_the immagine per integrare Microsoft Defender for Identity in cui selezionare il collegamento Abilita l'integrazione dei dati di Microsoft Defender per l'identità](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="27216-202">Se non viene visualizzato questo prompt, potrebbe significare che l'integrazione dei dati di Microsoft Defender for Identity è già stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="27216-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="27216-203">Tuttavia, se non si è sicuri, contattare l'amministratore IT per confermare.</span><span class="sxs-lookup"><span data-stu-id="27216-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="27216-204">Vai a **Impostazioni,** attiva l'interruttore **integrazione di Microsoft Defender per l'identità,** quindi fai clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="27216-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Pagina delle of_the delle immagini in cui devi attivare l'interruttore integrazione di Microsoft Defender per l'identità, quindi fai clic su Salva](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="27216-206">Per le nuove istanze di Microsoft Defender for Identity, questo interruttore di integrazione viene attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="27216-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="27216-207">Verificare che l'integrazione di Microsoft Defender for Identity sia stata abilitata prima di procedere al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="27216-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="27216-208">Nelle impostazioni di individuazione cloud seleziona **Microsoft Defender per l'integrazione degli endpoint** e quindi abilita l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="27216-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="27216-209">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27216-209">Click **Save**.</span></span>

   ![Immagine of_the pagina Microsoft Defender for Endpoint in cui è selezionata la casella di controllo Blocca app non bloccate in Microsoft Defender per l'integrazione degli endpoint.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="27216-212">In Impostazioni individuazione cloud seleziona **Arricchimento utente** e quindi abilita l'integrazione con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27216-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Immagine della sezione User enrichment in cui è selezionata la casella di controllo Enrich discovered user identifiers with Azure Active Directory usernames](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="27216-214">Configurare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="27216-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="27216-215">Ignora questo passaggio se hai già abilitato Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="27216-216">Passare a [Centro sicurezza Microsoft 365](https://security.microsoft.com/info)  >  **Altre risorse**  >  **Microsoft Defender Security Center.**</span><span class="sxs-lookup"><span data-stu-id="27216-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="27216-217">Fare clic su **Apri**. </span><span class="sxs-lookup"><span data-stu-id="27216-217">Click **Open**.</span></span>

   ![Immagine of_Microsoft'opzione Defender Security Center nella pagina Centro sicurezza Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="27216-219">Segui la procedura guidata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="27216-220">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27216-220">Click **Next**.</span></span> 

   ![Pagina of_the di benvenuto di Microsoft Defender Security Center](../../media/mtp-eval-59.png)

3. <span data-ttu-id="27216-222">Scegli in base alla posizione di archiviazione dei dati preferita, ai criteri di conservazione dei dati, alle dimensioni dell'organizzazione e al consenso esplicito per le funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="27216-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Pagina of_the immagine per selezionare il paese di archiviazione dei dati, i criteri di conservazione e le dimensioni dell'organizzazione.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="27216-225">Non è possibile modificare alcune impostazioni, ad esempio la posizione di archiviazione dei dati, in seguito.</span><span class="sxs-lookup"><span data-stu-id="27216-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="27216-226">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27216-226">Click **Next**.</span></span> 

4. <span data-ttu-id="27216-227">Fai **clic su Continua** e eseguirà il provisioning del tenant di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Pagina of_the che richiede di fare clic sul pulsante Continua per creare l'istanza cloud](../../media/mtp-eval-61.png)

5. <span data-ttu-id="27216-229">Onboard degli endpoint tramite Criteri di gruppo, Microsoft Endpoint Manager o eseguendo uno script locale in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="27216-230">Per semplicità, in questa guida viene utilizzato lo script locale.</span><span class="sxs-lookup"><span data-stu-id="27216-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="27216-231">Fai **clic su Scarica** pacchetto e copia lo script di onboarding nei tuoi endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Immagine of_page che ti chiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o nell'endpoint](../../media/mtp-eval-62.png)

7. <span data-ttu-id="27216-233">Nell'endpoint esegui lo script di onboarding come amministratore e scegli Y.</span><span class="sxs-lookup"><span data-stu-id="27216-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Immagine of_the riga di comando in cui esegui lo script di onboarding e scegli Y per procedere](../../media/mtp-eval-63.png)

8. <span data-ttu-id="27216-235">Congratulazioni, hai onboarded il primo endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Immagine of_the riga di comando in cui si ottiene la conferma di aver eseguito l'onboarded del primo endpoint.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="27216-238">Copia e incolla il test di rilevamento dalla procedura guidata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the eseguire un passaggio del test di rilevamento in cui fare clic su Copia per copiare lo script di test di rilevamento da incollare nel prompt dei comandi](../../media/mtp-eval-65.png)

10. <span data-ttu-id="27216-240">Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="27216-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Image of_command prompt in cui copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="27216-242">Seleziona **Inizia a usare Microsoft Defender per Endpoint** dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="27216-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Immagine of_the richiesta di conferma dalla procedura guidata in cui fare clic su Inizia a usare Microsoft Defender per Endpoint](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="27216-244">Visitare [Microsoft Defender Security Center.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="27216-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="27216-245">Vai a **Impostazioni** e quindi seleziona **Funzionalità avanzate.**</span><span class="sxs-lookup"><span data-stu-id="27216-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Image of_Microsoft Defender Security Center Settings menu where you should select Advanced features](../../media/mtp-eval-68.png)

13. <span data-ttu-id="27216-247">Attivare l'integrazione con **Microsoft Defender per l'identità**.</span><span class="sxs-lookup"><span data-stu-id="27216-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced features, Opzione di Microsoft Defender for Identity che devi attivare](../../media/mtp-eval-69.png)

14. <span data-ttu-id="27216-249">Attivare l'integrazione con **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="27216-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Opzione di Office 365 Threat Intelligence che devi attivare](../../media/mtp-eval-70.png)

15. <span data-ttu-id="27216-251">Attivare l'integrazione **con Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="27216-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Opzione Microsoft Cloud App Security che devi attivare](../../media/mtp-eval-71.png)

16. <span data-ttu-id="27216-253">Scorri verso il basso e fai **clic su Salva preferenze** per confermare le nuove integrazioni.</span><span class="sxs-lookup"><span data-stu-id="27216-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Pulsante of_Save preferenze di immagine su cui devi fare clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="27216-255">Avviare il servizio Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27216-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="27216-256">A partire dal 1 giugno 2020, Microsoft abilita automaticamente le funzionalità di Microsoft 365 Defender per tutti i tenant idonei.</span><span class="sxs-lookup"><span data-stu-id="27216-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="27216-257">Per informazioni [dettagliate, vedere](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) questo articolo della Microsoft Tech Community sull'idoneità delle licenze.</span><span class="sxs-lookup"><span data-stu-id="27216-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="27216-258">Passare al Centro sicurezza [Microsoft 365](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="27216-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="27216-259">Passare a **Impostazioni** e quindi selezionare **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="27216-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="27216-260">Immagine of_Microsoft schermata dell'opzione Defender 365 dalla pagina Impostazioni Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27216-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="27216-261">Per una guida più completa, vedere [Attivare Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="27216-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span> 

<span data-ttu-id="27216-262">Congratulazioni.</span><span class="sxs-lookup"><span data-stu-id="27216-262">Congratulations!</span></span> <span data-ttu-id="27216-263">Hai appena creato il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="27216-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="27216-264">Ora è possibile acquisire familiarità con l'interfaccia utente di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="27216-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="27216-265">Scopri cosa puoi imparare dalla seguente guida interattiva di Microsoft 365 Defender e scopri come usare ogni dashboard per le attività quotidiane relative alle operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="27216-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="27216-266">Consultare la guida interattiva</span><span class="sxs-lookup"><span data-stu-id="27216-266">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="27216-267">Successivamente, è possibile simulare un attacco e vedere come le funzionalità tra prodotti rilevano, creano avvisi e rispondono automaticamente a un attacco senza file su un endpoint.</span><span class="sxs-lookup"><span data-stu-id="27216-267">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="27216-268">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="27216-268">Next step</span></span>

- <span data-ttu-id="27216-269">[Generare un avviso di test:](generate-test-alert.md) eseguire una simulazione di attacco nel laboratorio di valutazione di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="27216-269">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>