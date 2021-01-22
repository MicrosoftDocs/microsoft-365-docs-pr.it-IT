---
title: Configurare i pilastri di Microsoft 365 Defender per il laboratorio di valutazione o l'ambiente pilota
description: Configurare i pilastri di Microsoft 365 Defender, ad esempio Microsoft Defender per Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security e Microsoft Defender for Endpoint, per il lab di valutazione o l'ambiente pilota.
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932239"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="bd8e3-104">Configurare i pilastri di Microsoft 365 Defender per il lab di valutazione o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="bd8e3-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bd8e3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-105">**Applies to:**</span></span>
- <span data-ttu-id="bd8e3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd8e3-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="bd8e3-107">La creazione di un ambiente pilota o un lab di valutazione di Microsoft 365 Defender e la sua distribuzione è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="bd8e3-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="bd8e3-108">[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="bd8e3-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="bd8e3-109">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="bd8e3-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="bd8e3-110">[![Fase 2: configurazione](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="bd8e3-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="bd8e3-111">Fase 2: configurazione</span><span class="sxs-lookup"><span data-stu-id="bd8e3-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fase 3: onboard](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="bd8e3-113">Fase 3: onboard</span><span class="sxs-lookup"><span data-stu-id="bd8e3-113">Phase 3: Onboard</span></span> | <span data-ttu-id="bd8e3-114">[![Tornare al progetto pilota](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="bd8e3-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="bd8e3-115">Tornare al playbook pilota</span><span class="sxs-lookup"><span data-stu-id="bd8e3-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="bd8e3-116">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="bd8e3-116">*You are here!*</span></span> | |

<span data-ttu-id="bd8e3-117">Al momento è in corso la fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="bd8e3-118">La preparazione è fondamentale per una distribuzione corretta.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="bd8e3-119">In questo articolo, sarai guidato sui punti che dovrai considerare durante la preparazione della distribuzione di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="bd8e3-120">Pilastri di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd8e3-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="bd8e3-121">Microsoft 365 Defender è costituito da quattro pilastri.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="bd8e3-122">Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione di rete, l'abilitazione dei quattro pilastri di Microsoft 365 Defender offrirà all'organizzazione il valore più importante.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="bd8e3-124">Questa sezione ti guiderà a configurare:</span><span class="sxs-lookup"><span data-stu-id="bd8e3-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="bd8e3-125">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="bd8e3-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="bd8e3-126">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="bd8e3-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="bd8e3-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bd8e3-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="bd8e3-128">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="bd8e3-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="bd8e3-129">Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="bd8e3-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="bd8e3-130">Ignorare questo passaggio se Defender è già stato abilitato per Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="bd8e3-131">È presente un modulo di PowerShell denominato *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* che consente di determinare alcune di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="bd8e3-132">Quando viene eseguito come amministratore nel tenant, get-ORCAReport consente di generare una valutazione della protezione da posta indesiderata, anti-phish e altre impostazioni di igiene dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="bd8e3-133">È possibile scaricare questo modulo da https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="bd8e3-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="bd8e3-134">Passare a Criteri di gestione delle minacce del Centro sicurezza & conformità di [Office 365.](https://protection.office.com/homepage)  >    >  </span><span class="sxs-lookup"><span data-stu-id="bd8e3-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="bd8e3-136">Fare **clic su Anti-phishing,** selezionare **Crea** e compilare il nome e la descrizione del criterio.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="bd8e3-137">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-137">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="bd8e3-139">Modificare i criteri di anti-phishing avanzati in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="bd8e3-140">Modificare **la soglia di phishing avanzato** su **2 - Aggressivo.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="bd8e3-141">Fare clic sul menu **a discesa** Aggiungi una condizione e selezionare i domini come dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="bd8e3-142">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="bd8e3-144">Rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-144">Review your settings.</span></span> <span data-ttu-id="bd8e3-145">Fare **clic su Crea questo criterio** per confermare.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-145">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="bd8e3-147">Selezionare **Allegati sicuri** e selezionare l'opzione Attiva **ATP per SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Immagine of_Office pagina Centro sicurezza & conformità di 365 in cui è possibile attivare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="bd8e3-149">Fare clic sull'icona + per creare un nuovo criterio allegati sicuri, applicarlo come dominio del destinatario ai domini.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="bd8e3-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-150">Click **Save**.</span></span>

   ![Immagine of_Office pagina Centro sicurezza & conformità di 365 in cui è possibile creare un nuovo criterio per gli allegati sicuri](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="bd8e3-152">Selezionare quindi il criterio **Collegamenti sicuri,** quindi fare clic sull'icona della matita per modificare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="bd8e3-153">Assicurarsi che **l'opzione Non tenere** traccia quando gli utenti fanno clic su collegamenti sicuri non sia selezionata, mentre le altre opzioni sono selezionate.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="bd8e3-154">Per [informazioni dettagliate, vedere Safe Links settings.](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)</span><span class="sxs-lookup"><span data-stu-id="bd8e3-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="bd8e3-155">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-155">Click **Save**.</span></span> 

   ![Immagine of_Office pagina Centro sicurezza & conformità di 365 che mostra che l'opzione Non tenere traccia di quando gli utenti fanno clic su Sicuro non è selezionata](../../media/mtp-eval-38.png)

9. <span data-ttu-id="bd8e3-157">Selezionare quindi il **criterio antimalware,** selezionare il valore predefinito e scegliere l'icona della matita.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="bd8e3-158">Fare **clic su** Impostazioni e selezionare Sì e utilizzare il testo di notifica **predefinito** per abilitare Risposta **rilevamento malware.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="bd8e3-159">Attivare il **filtro Tipi di allegati** comuni.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="bd8e3-160">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-160">Click **Save**.</span></span>

    ![Immagine of_Office pagina Centro sicurezza & conformità di 365 che mostra che la risposta di rilevamento malware è attivata con la notifica predefinita e il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="bd8e3-162">Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Search  >  **Audit** log search  >  **and** turn Auditing on.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Immagine of_Office pagina Centro sicurezza & conformità di 365 in cui è possibile attivare la ricerca nel log di controllo](../../media/mtp-eval-40.png)

12. <span data-ttu-id="bd8e3-164">Integrare Microsoft Defender per Office 365 con Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bd8e3-165">Passare a [Office 365 Security & Compliance Center Threat](https://protection.office.com/homepage)Management Explorer e selezionare Microsoft Defender for Endpoint Settings nell'angolo in alto a  >    >   destra dello schermo. </span><span class="sxs-lookup"><span data-stu-id="bd8e3-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="bd8e3-166">Nella finestra di dialogo Defender per la connessione endpoint attiva **Connetti a Microsoft Defender per Endpoint.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Immagine of_Office 365 Security & Compliance Center in cui è possibile attivare la connessione di Microsoft Defender for Endpoint](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="bd8e3-168">Configurare Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="bd8e3-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="bd8e3-169">Ignorare questo passaggio se è già stato abilitato Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="bd8e3-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="bd8e3-170">Passare al [Centro sicurezza Microsoft 365](https://security.microsoft.com/info) > **selezionare Altre** risorse di Microsoft Defender  >  **per l'identità.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Immagine of_Microsoft pagina Del Centro sicurezza 365 in cui è disponibile un'opzione per aprire Microsoft Defender for Identity](../../media/mtp-eval-42.png)

2. <span data-ttu-id="bd8e3-172">Fai **clic su** Crea per avviare la procedura guidata di Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Immagine of_Microsoft pagina della procedura guidata di Defender for Identity in cui fare clic sul pulsante Crea](../../media/mtp-eval-43.png)

3. <span data-ttu-id="bd8e3-174">Scegliere **Fornire un nome utente e una password per connettersi alla foresta di Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Immagine of_Microsoft pagina di benvenuto di Defender for Identity](../../media/mtp-eval-44.png)

4. <span data-ttu-id="bd8e3-176">Immettere le credenziali locali di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="bd8e3-177">Può trattarsi di qualsiasi account utente con accesso in lettura ad Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft Defender for Identity Directory services page where you should put your credentials](../../media/mtp-eval-45.png)

5. <span data-ttu-id="bd8e3-179">Successivamente, scegliere **Download Sensor Setup** e trasferire il file nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Image of_Microsoft Defender for Identity page where you can select Download Sensor Setup](../../media/mtp-eval-46.png)

6. <span data-ttu-id="bd8e3-181">Eseguire l'installazione del sensore di identità di Microsoft Defender per l'identità e iniziare a seguire la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Immagine of_Microsoft pagina Defender per l'identità in cui fare clic accanto per seguire la procedura guidata del sensore di identità di Microsoft Defender](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="bd8e3-183">Fai **clic su Avanti** nel tipo di distribuzione del sensore.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-183">Click **Next** at the sensor deployment type.</span></span>

   ![Immagine of_Microsoft pagina Defender for Identity in cui fare clic accanto per passare alla pagina successiva](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="bd8e3-185">Copiare il tasto di scelta perché è necessario immetterlo successivamente nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Image of_the sensors page where you should copy the access key that you need to enter in the next Microsoft Defender for Identity sensor setup wizard page](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="bd8e3-187">Copiare il tasto di scelta nella procedura guidata e fare clic su **Installa.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Immagine of_Microsoft della procedura guidata del sensore di identità di Defender for Identity in cui devi fornire il tasto di scelta e quindi fai clic sul pulsante installa](../../media/mtp-eval-50.png)

10. <span data-ttu-id="bd8e3-189">Congratulazioni, microsoft defender è stato configurato correttamente per l'identità nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="bd8e3-191">Nella sezione [Impostazioni di Microsoft Defender per l'identità](https://go.microsoft.com/fwlink/?linkid=2040449) seleziona \*\*Microsoft Defender per Endpoint \*\*, quindi attiva l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="bd8e3-192">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-192">Click **Save**.</span></span> 

    ![Immagine of_the pagina delle impostazioni di Microsoft Defender per l'identità in cui attivare l'interruttore Microsoft Defender per endpoint](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="bd8e3-194">Windows Defender ATP è stato ridenobrato come Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bd8e3-195">Per garantire la coerenza, è in corso l'implementazione delle modifiche in tutti i portali.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="bd8e3-196">Configurare Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bd8e3-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="bd8e3-197">Ignorare questo passaggio se è già stato abilitato Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="bd8e3-198">Passare a [Centro sicurezza Microsoft 365](https://security.microsoft.com/info)  >  **Altre risorse di** Microsoft Cloud App  >  **Security.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 Security Center page where you can see Microsoft Cloud App card and should click the open button](../../media/mtp-eval-53.png)

2. <span data-ttu-id="bd8e3-200">Al prompt delle informazioni per integrare Microsoft Defender for Identity, selezionare **Abilita l'integrazione dei dati di Microsoft Defender per l'identità.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Image of_the information prompt to integrate Microsoft Defender for Identity where you should select the Enable Microsoft Defender for Identity data integration link](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="bd8e3-202">Se questa richiesta non viene visualizzata, potrebbe significare che l'integrazione dei dati di Microsoft Defender for Identity è già stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="bd8e3-203">Tuttavia, se non si è sicuri, contattare l'amministratore IT per confermare.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="bd8e3-204">Vai a **Impostazioni,** attiva l'interruttore **di integrazione di Microsoft Defender for Identity** e quindi fai clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Image of_the settings page where you should turn on the Microsoft Defender for Identity integration toggle then click save](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="bd8e3-206">Per le nuove istanze di Microsoft Defender for Identity, questo interruttore di integrazione viene attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="bd8e3-207">Verificare che l'integrazione di Microsoft Defender for Identity sia stata abilitata prima di procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="bd8e3-208">Nelle impostazioni di individuazione cloud seleziona **Microsoft Defender per l'integrazione degli endpoint** e quindi abilita l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="bd8e3-209">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-209">Click **Save**.</span></span>

   ![Immagine of_the pagina Microsoft Defender per endpoint in cui è selezionata la casella di controllo Blocca app non bloccate in Microsoft Defender per l'integrazione degli endpoint.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="bd8e3-212">In Impostazioni individuazione cloud selezionare **Arricchimento utenti,** quindi abilitare l'integrazione con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Immagine della sezione Di arricchimento degli utenti in cui è selezionata la casella di controllo arricchire gli identificatori utente individuati con i nomi utente di Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="bd8e3-214">Configurare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd8e3-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="bd8e3-215">Ignora questo passaggio se hai già abilitato Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="bd8e3-216">Passare a [Centro sicurezza Microsoft 365](https://security.microsoft.com/info)  >  **Altre risorse** di Microsoft Defender Security  >  **Center.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="bd8e3-217">Fare clic su **Apri**. </span><span class="sxs-lookup"><span data-stu-id="bd8e3-217">Click **Open**.</span></span>

   ![Immagine of_Microsoft'opzione Defender Security Center nella pagina Centro sicurezza Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="bd8e3-219">Segui la procedura guidata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="bd8e3-220">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-220">Click **Next**.</span></span> 

   ![Immagine of_the pagina della procedura guidata di benvenuto di Microsoft Defender Security Center](../../media/mtp-eval-59.png)

3. <span data-ttu-id="bd8e3-222">Scegliere in base alla posizione di archiviazione dei dati preferita, ai criteri di conservazione dei dati, alle dimensioni dell'organizzazione e al consenso esplicito per le funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Image of_the page to select your data storage country, retention policy, and organization size.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="bd8e3-225">Non è possibile modificare alcune delle impostazioni, ad esempio la posizione di archiviazione dei dati, in seguito.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="bd8e3-226">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-226">Click **Next**.</span></span> 

4. <span data-ttu-id="bd8e3-227">Fai **clic su Continua** e eseguirà il provisioning del tenant di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Image of_the page prompting you click the continue button to create your cloud instance](../../media/mtp-eval-61.png)

5. <span data-ttu-id="bd8e3-229">Onboard degli endpoint tramite Criteri di gruppo, Microsoft Endpoint Manager o eseguendo uno script locale in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bd8e3-230">Per semplicità, in questa guida viene utilizzato lo script locale.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="bd8e3-231">Fai **clic su Scarica** pacchetto e copia lo script di onboarding nei tuoi endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Immagine of_page che ti chiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o endpoint](../../media/mtp-eval-62.png)

7. <span data-ttu-id="bd8e3-233">Nell'endpoint esegui lo script di onboarding come amministratore e scegli Y.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the commandline where you run the onboarding script and choose Y to proceed](../../media/mtp-eval-63.png)

8. <span data-ttu-id="bd8e3-235">Congratulazioni, hai onboarded il primo endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Immagine of_the riga di comando in cui si ottiene la conferma di aver eseguito l'onboarded del primo endpoint.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="bd8e3-238">Copiare e incollare il test di rilevamento dalla procedura guidata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Immagine of_the eseguire un passaggio del test di rilevamento in cui è necessario fare clic su Copia per copiare lo script di test di rilevamento da incollare nel prompt dei comandi](../../media/mtp-eval-65.png)

10. <span data-ttu-id="bd8e3-240">Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Image of_command prompt dei comandi in cui copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="bd8e3-242">Seleziona **Inizia a usare Microsoft Defender per Endpoint** dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Immagine of_the richiesta di conferma dalla procedura guidata in cui fare clic su Inizia a usare Microsoft Defender per Endpoint](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="bd8e3-244">Visitare [Microsoft Defender Security Center.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="bd8e3-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="bd8e3-245">Vai a **Impostazioni** e quindi seleziona **Funzionalità avanzate.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Immagine of_Microsoft menu Impostazioni di Defender Security Center in cui selezionare Funzionalità avanzate](../../media/mtp-eval-68.png)

13. <span data-ttu-id="bd8e3-247">Attivare l'integrazione con **Microsoft Defender for Identity.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Immagine of_Microsoft funzionalità avanzate di Defender Security Center, opzione di Microsoft Defender per l'identità che è necessario attivare](../../media/mtp-eval-69.png)

14. <span data-ttu-id="bd8e3-249">Attivare l'integrazione con **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)

15. <span data-ttu-id="bd8e3-251">Attivare l'integrazione **con Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Immagine of_Microsoft funzionalità avanzate di Defender Security Center, interruttore dell'opzione Microsoft Cloud App Security che è necessario attivare](../../media/mtp-eval-71.png)

16. <span data-ttu-id="bd8e3-253">Scorrere verso il basso e fare **clic su Salva preferenze** per confermare le nuove integrazioni.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Pulsante of_Save preferenze di immagine su cui è necessario fare clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="bd8e3-255">Avviare il servizio Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd8e3-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="bd8e3-256">A partire dal 1° giugno 2020, Microsoft abilita automaticamente le funzionalità di Microsoft 365 Defender per tutti i tenant idonei.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="bd8e3-257">Per informazioni dettagliate, vedere questo articolo della [Microsoft Tech Community sull'idoneità](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) alla licenza.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="bd8e3-258">Passare al [Centro sicurezza Microsoft 365.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="bd8e3-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="bd8e3-259">Passare a **Impostazioni** e quindi selezionare **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="bd8e3-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="bd8e3-260">Immagine of_Microsoft'opzione di Defender 365 dalla pagina Impostazioni Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd8e3-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="bd8e3-261">Per una guida più completa, vedere [Attivare Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="bd8e3-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="bd8e3-262">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="bd8e3-262">Congratulations!</span></span> <span data-ttu-id="bd8e3-263">Hai appena creato il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="bd8e3-264">Ora è possibile acquisire familiarità con l'interfaccia utente di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="bd8e3-265">Vedere cosa si può imparare dalla seguente guida interattiva di Microsoft 365 Defender e sapere come usare ogni dashboard per le attività quotidiane relative alle operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="bd8e3-266">Successivamente, è possibile simulare un attacco e vedere come le funzionalità tra prodotti rilevano, creano avvisi e rispondono automaticamente a un attacco senza file su un endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="bd8e3-267">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bd8e3-267">Next step</span></span>
|[<span data-ttu-id="bd8e3-268">Fase di simulazione degli attacchi</span><span class="sxs-lookup"><span data-stu-id="bd8e3-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="bd8e3-269">Eseguire la simulazione di attacco per l'ambiente pilota di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bd8e3-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
