---
title: Configurare Microsoft 365 Defender pilastri per il laboratorio di valutazione o l'ambiente pilota
description: Configurare Microsoft 365 Defender pilastri, ad esempio Microsoft Defender per Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security e Microsoft Defender for Endpoint, per il laboratorio di valutazione o l'ambiente pilota.
keywords: configurare Microsoft 365 Defender di valutazione, Microsoft 365 Defender di valutazione, configurare Microsoft 365 Defender progetto pilota, configurare Microsoft 365 Defender pilastri, Microsoft 365 Defender pilastri
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
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229780"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="6a294-104">Configurare Microsoft 365 Defender pilastri per il laboratorio di valutazione o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="6a294-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6a294-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6a294-105">**Applies to:**</span></span>
- <span data-ttu-id="6a294-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a294-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="6a294-107">La creazione Microsoft 365 Defender laboratorio di valutazione o un ambiente pilota e la distribuzione è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="6a294-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="6a294-108">[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="6a294-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="6a294-109">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="6a294-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="6a294-110">[![Fase 2: configurazione](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="6a294-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="6a294-111">Fase 2: configurazione</span><span class="sxs-lookup"><span data-stu-id="6a294-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Phase 3: onboarding](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="6a294-113">Fase 3: onboarding</span><span class="sxs-lookup"><span data-stu-id="6a294-113">Phase 3: Onboard</span></span> | <span data-ttu-id="6a294-114">[![Torna al progetto pilota](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="6a294-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="6a294-115">Torna al playbook pilota</span><span class="sxs-lookup"><span data-stu-id="6a294-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="6a294-116">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="6a294-116">*You are here!*</span></span> | |

<span data-ttu-id="6a294-117">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6a294-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="6a294-118">La preparazione è fondamentale per una distribuzione corretta.</span><span class="sxs-lookup"><span data-stu-id="6a294-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="6a294-119">In questo articolo, sarai guidato sui punti da considerare durante la preparazione della distribuzione di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>

## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="6a294-120">Microsoft 365 Defender pilastri</span><span class="sxs-lookup"><span data-stu-id="6a294-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="6a294-121">Microsoft 365 Defender è costituito da quattro pilastri.</span><span class="sxs-lookup"><span data-stu-id="6a294-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="6a294-122">Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione di rete, l'abilitazione dei quattro pilastri Microsoft 365 Defender offrirà all'organizzazione il massimo valore.</span><span class="sxs-lookup"><span data-stu-id="6a294-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Immagine of_Microsoft 365 Defender per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender for Endpoint, per le app cloud, Microsoft Cloud App Security e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="6a294-124">Questa sezione ti guiderà a configurare:</span><span class="sxs-lookup"><span data-stu-id="6a294-124">This section will guide you to configure:</span></span>

- <span data-ttu-id="6a294-125">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6a294-125">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="6a294-126">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="6a294-126">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="6a294-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6a294-127">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6a294-128">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6a294-128">Microsoft Defender for Endpoint</span></span>

## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="6a294-129">Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6a294-129">Configure Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="6a294-130">Ignora questo passaggio se hai già abilitato Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a294-130">Skip this step if you've already enabled Defender for Office 365.</span></span>

<span data-ttu-id="6a294-131">Esiste un modulo di PowerShell denominato Office 365 *Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* che consente di determinare alcune di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6a294-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="6a294-132">Quando viene eseguito come amministratore nel tenant, get-ORCAReport consente di generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phish e altre impostazioni di igiene dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a294-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="6a294-133">È possibile scaricare questo modulo da https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="6a294-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span>

1. <span data-ttu-id="6a294-134">Passare a Office 365 [sicurezza & criteri di](https://protection.office.com/homepage)gestione delle minacce del Centro  >  **conformità**  >  .</span><span class="sxs-lookup"><span data-stu-id="6a294-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)

2. <span data-ttu-id="6a294-136">Fare **clic su Anti-phishing,** selezionare **Crea** e compilare il nome e la descrizione del criterio.</span><span class="sxs-lookup"><span data-stu-id="6a294-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="6a294-137">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6a294-137">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="6a294-139">Modificare i criteri anti-phishing avanzati in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a294-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6a294-140">Modificare **la soglia di phishing avanzato** su **2 - Aggressivo.**</span><span class="sxs-lookup"><span data-stu-id="6a294-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="6a294-141">Fai clic sul menu **a** discesa Aggiungi una condizione e seleziona i domini come dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6a294-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="6a294-142">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6a294-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)

4. <span data-ttu-id="6a294-144">Rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6a294-144">Review your settings.</span></span> <span data-ttu-id="6a294-145">Fare **clic su Crea questo criterio** per confermare.</span><span class="sxs-lookup"><span data-stu-id="6a294-145">Click **Create this policy** to confirm.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)

5. <span data-ttu-id="6a294-147">Selezionare **Cassaforte allegati** e selezionare l'opzione Attiva **ATP per SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="6a294-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & Compliance Center, in cui è possibile attivare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="6a294-149">Fare clic sull'icona + per creare un nuovo criterio degli allegati sicuri, applicarlo come dominio destinatario ai domini.</span><span class="sxs-lookup"><span data-stu-id="6a294-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="6a294-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a294-150">Click **Save**.</span></span>

   ![Immagine of_Office 365 Security & Compliance Center in cui è possibile creare un nuovo criterio di creazione di un nuovo allegato sicuro](../../media/mtp-eval-37.png)

7. <span data-ttu-id="6a294-152">Successivamente, selezionare il criterio **Cassaforte collegamenti,** quindi fare clic sull'icona a forma di matita per modificare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="6a294-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="6a294-153">Assicurarsi che **l'opzione Non tenere traccia** quando gli utenti fanno clic su collegamenti sicuri non sia selezionata, mentre le altre opzioni sono selezionate.</span><span class="sxs-lookup"><span data-stu-id="6a294-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="6a294-154">Per [informazioni dettagliate, Cassaforte impostazioni dei collegamenti.](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365)</span><span class="sxs-lookup"><span data-stu-id="6a294-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="6a294-155">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a294-155">Click **Save**.</span></span>

   ![Image of_Office 365 Security & Compliance Center che mostra che l'opzione Non tenere traccia quando gli utenti fanno clic su Sicuro non è selezionata](../../media/mtp-eval-38.png)

9. <span data-ttu-id="6a294-157">Seleziona quindi il **criterio Antimalware,** seleziona il valore predefinito e scegli l'icona a forma di matita.</span><span class="sxs-lookup"><span data-stu-id="6a294-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="6a294-158">Fai **clic Impostazioni** e seleziona Sì e usa il testo di notifica **predefinito** per abilitare La risposta di **rilevamento malware.**</span><span class="sxs-lookup"><span data-stu-id="6a294-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="6a294-159">Attivare il **filtro Tipi di allegati** comuni.</span><span class="sxs-lookup"><span data-stu-id="6a294-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="6a294-160">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a294-160">Click **Save**.</span></span>

    ![Immagine of_Office 365 Security & Compliance Center che mostra che la risposta di rilevamento malware è attivata con la notifica predefinita e il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png)

11. <span data-ttu-id="6a294-162">Passare a Office 365 [sicurezza &](https://protection.office.com/homepage)ricerca nel log di controllo di ricerca del Centro conformità e  >    >   attivare il controllo.</span><span class="sxs-lookup"><span data-stu-id="6a294-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Immagine of_Office 365 Security & Compliance Center in cui è possibile attivare la ricerca nei log di controllo](../../media/mtp-eval-40.png)

12. <span data-ttu-id="6a294-164">Integrare Microsoft Defender per Office 365 con Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6a294-165">Passa a [Office 365 Sicurezza & Centro](https://protection.office.com/homepage)conformità Gestione minacce e seleziona Microsoft Defender per Endpoint  >    >   **Impostazioni** nell'angolo in alto a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="6a294-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="6a294-166">Nella finestra di dialogo Defender for Endpoint connection attiva **Connessione a Microsoft Defender for Endpoint.**</span><span class="sxs-lookup"><span data-stu-id="6a294-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Immagine of_Office 365 Security & Compliance Center in cui è possibile attivare la connessione a Microsoft Defender for Endpoint](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="6a294-168">Configurare Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="6a294-168">Configure Microsoft Defender for Identity</span></span>

> [!NOTE]
> <span data-ttu-id="6a294-169">Ignora questo passaggio se hai già abilitato Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="6a294-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="6a294-170">Passare a [Microsoft 365 Centro sicurezza](https://security.microsoft.com/info) > selezionare Altre **risorse** Microsoft Defender  >  **per l'identità**.</span><span class="sxs-lookup"><span data-stu-id="6a294-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Image of_Microsoft 365 Security Center in cui è disponibile un'opzione per aprire Microsoft Defender for Identity](../../media/mtp-eval-42.png)

2. <span data-ttu-id="6a294-172">Fai **clic su** Crea per avviare la procedura guidata di Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="6a294-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span>

   ![Immagine of_Microsoft pagina della procedura guidata defender per l'identità in cui fare clic sul pulsante Crea](../../media/mtp-eval-43.png)

3. <span data-ttu-id="6a294-174">Scegliere **Fornire un nome utente e una password per connettersi alla foresta di Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="6a294-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>

   ![Pagina di benvenuto of_Microsoft Image of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. <span data-ttu-id="6a294-176">Immettere le credenziali di Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="6a294-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="6a294-177">Può trattarsi di qualsiasi account utente con accesso in lettura ad Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a294-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft Defender for Identity Directory services page where you should put your credentials](../../media/mtp-eval-45.png)

5. <span data-ttu-id="6a294-179">Successivamente, scegliere **Download Sensor Setup** and transfer file to your domain controller.</span><span class="sxs-lookup"><span data-stu-id="6a294-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Pagina of_Microsoft Defender for Identity in cui puoi selezionare Scarica configurazione sensore](../../media/mtp-eval-46.png)

6. <span data-ttu-id="6a294-181">Eseguire l'installazione del sensore di identità di Microsoft Defender per e iniziare a seguire la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="6a294-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Immagine of_Microsoft defender per l'identità in cui fare clic su avanti per seguire la procedura guidata sensore di Microsoft Defender for Identity](../../media/mtp-eval-47.png)

7. <span data-ttu-id="6a294-183">Fare **clic su Avanti** nel tipo di distribuzione del sensore.</span><span class="sxs-lookup"><span data-stu-id="6a294-183">Click **Next** at the sensor deployment type.</span></span>

   ![Image of_Microsoft Defender for Identity page where you should click next to go to next page](../../media/mtp-eval-48.png)

8. <span data-ttu-id="6a294-185">Copiare il tasto di scelta perché è necessario immetterlo successivamente nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="6a294-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Pagina of_the sensori di immagine in cui copiare il tasto di scelta che è necessario immettere nella pagina successiva della configurazione guidata del sensore di identità di Microsoft Defender for Identity](../../media/mtp-eval-49.png)

9. <span data-ttu-id="6a294-187">Copiare il tasto di scelta nella procedura guidata e fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="6a294-187">Copy the access key into the Wizard and click **Install**.</span></span>

   ![Image of_Microsoft Defender for Identity sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)

10. <span data-ttu-id="6a294-189">Congratulazioni, Microsoft Defender è stato configurato correttamente per l'identità nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="6a294-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)

11. <span data-ttu-id="6a294-191">Nella sezione [Impostazioni di Microsoft Defender per l'identità](https://go.microsoft.com/fwlink/?linkid=2040449) seleziona \*\*Microsoft Defender per Endpoint \*\*, quindi attiva l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="6a294-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="6a294-192">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a294-192">Click **Save**.</span></span>

    ![Immagine of_the pagina delle impostazioni di Microsoft Defender per l'identità in cui attivare l'interruttore Microsoft Defender for Endpoint](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="6a294-194">Configurare Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6a294-194">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="6a294-195">Ignorare questo passaggio se è già stato abilitato Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="6a294-195">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span>

1. <span data-ttu-id="6a294-196">Passare a [Microsoft 365 Centro sicurezza](https://security.microsoft.com/info)e sicurezza  >  **altre** risorse  >  **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="6a294-196">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Immagine of_Microsoft pagina del Centro sicurezza 365 in cui è possibile visualizzare la scheda Microsoft Cloud App e fare clic sul pulsante Apri](../../media/mtp-eval-53.png)

2. <span data-ttu-id="6a294-198">Al prompt delle informazioni per integrare Microsoft Defender for Identity, seleziona **Abilita Microsoft Defender per l'integrazione dei dati di identità.**</span><span class="sxs-lookup"><span data-stu-id="6a294-198">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>

   ![Richiesta di of_the immagine per integrare Microsoft Defender for Identity in cui selezionare il collegamento Abilita l'integrazione dei dati di Microsoft Defender per l'identità](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="6a294-200">Se non viene visualizzato questo prompt, potrebbe significare che l'integrazione dei dati di Microsoft Defender for Identity è già stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="6a294-200">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="6a294-201">Tuttavia, se non si è sicuri, contattare l'amministratore IT per confermare.</span><span class="sxs-lookup"><span data-stu-id="6a294-201">However, if you are not sure, contact your IT Administrator to confirm.</span></span>

3. <span data-ttu-id="6a294-202">Vai **a** Impostazioni , attiva l'interruttore **integrazione di Microsoft Defender per** l'identità, quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a294-202">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span>

   ![Pagina delle of_the delle immagini in cui devi attivare l'interruttore integrazione di Microsoft Defender per l'identità, quindi fai clic su Salva](../../media/mtp-eval-55.png)

   > [!NOTE]
   > <span data-ttu-id="6a294-204">Per le nuove istanze di Microsoft Defender for Identity, questo interruttore di integrazione viene attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6a294-204">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="6a294-205">Verificare che l'integrazione di Microsoft Defender for Identity sia stata abilitata prima di procedere al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="6a294-205">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>

4. <span data-ttu-id="6a294-206">Nelle impostazioni di individuazione cloud seleziona **Microsoft Defender per l'integrazione degli endpoint** e quindi abilita l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6a294-206">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="6a294-207">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a294-207">Click **Save**.</span></span>

   ![Immagine of_the pagina Microsoft Defender for Endpoint in cui è selezionata la casella di controllo Blocca app non bloccate in Microsoft Defender per l'integrazione degli endpoint.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="6a294-210">In Impostazioni individuazione cloud seleziona **Arricchimento utente** e quindi abilita l'integrazione con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a294-210">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Immagine della sezione Arricchimento utente in cui è selezionata la casella di controllo Arricchire gli identificatori utente individuati con Azure Active Directory nomi utente.](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="6a294-212">Configurare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a294-212">Configure Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="6a294-213">Ignora questo passaggio se hai già abilitato Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-213">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="6a294-214">Passare a [Microsoft 365 Centro sicurezza](https://security.microsoft.com/info)  >  **e** sicurezza Altre risorse  >  **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="6a294-214">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="6a294-215">Fare clic su **Apri**. </span><span class="sxs-lookup"><span data-stu-id="6a294-215">Click **Open**.</span></span>

   ![Immagine of_Microsoft'opzione Defender Security Center nella pagina Microsoft 365 Centro sicurezza PC](../../media/mtp-eval-58.png)

2. <span data-ttu-id="6a294-217">Segui la procedura guidata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-217">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="6a294-218">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6a294-218">Click **Next**.</span></span>

   ![Pagina of_the Microsoft Defender Security Center della procedura guidata di benvenuto](../../media/mtp-eval-59.png)

3. <span data-ttu-id="6a294-220">Scegli in base alla posizione di archiviazione dei dati preferita, ai criteri di conservazione dei dati, alle dimensioni dell'organizzazione e al consenso esplicito per le funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="6a294-220">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Pagina of_the immagine per selezionare il paese di archiviazione dei dati, i criteri di conservazione e le dimensioni dell'organizzazione.](../../media/mtp-eval-60.png)

   > [!NOTE]
   > <span data-ttu-id="6a294-223">Non è possibile modificare alcune impostazioni, ad esempio la posizione di archiviazione dei dati, in seguito.</span><span class="sxs-lookup"><span data-stu-id="6a294-223">You cannot change some of the settings, like data storage location, afterwards.</span></span>

   <span data-ttu-id="6a294-224">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6a294-224">Click **Next**.</span></span>

4. <span data-ttu-id="6a294-225">Fai **clic su Continua** e eseguirà il provisioning del tenant di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-225">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Pagina of_the che richiede di fare clic sul pulsante Continua per creare l'istanza cloud](../../media/mtp-eval-61.png)

5. <span data-ttu-id="6a294-227">Onboard degli endpoint tramite Criteri di gruppo, Microsoft Endpoint Manager o eseguendo uno script locale in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6a294-228">Per semplicità, in questa guida viene utilizzato lo script locale.</span><span class="sxs-lookup"><span data-stu-id="6a294-228">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="6a294-229">Fai **clic su Scarica** pacchetto e copia lo script di onboarding nei tuoi endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-229">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Immagine of_page che ti chiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o nell'endpoint](../../media/mtp-eval-62.png)

7. <span data-ttu-id="6a294-231">Nell'endpoint esegui lo script di onboarding come amministratore e scegli Y.</span><span class="sxs-lookup"><span data-stu-id="6a294-231">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>

   ![Immagine of_the riga di comando in cui esegui lo script di onboarding e scegli Y per procedere](../../media/mtp-eval-63.png)

8. <span data-ttu-id="6a294-233">Congratulazioni, hai onboarded il primo endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-233">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Immagine of_the riga di comando in cui si ottiene la conferma di aver eseguito l'onboarded del primo endpoint.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="6a294-236">Copia e incolla il test di rilevamento dalla procedura guidata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-236">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the eseguire un passaggio del test di rilevamento in cui fare clic su Copia per copiare lo script di test di rilevamento da incollare nel prompt dei comandi](../../media/mtp-eval-65.png)

10. <span data-ttu-id="6a294-238">Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="6a294-238">Copy the PowerShell script to an elevated command prompt and run it.</span></span>

    ![Image of_command prompt in cui copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="6a294-240">Seleziona **Inizia a usare Microsoft Defender per Endpoint** dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="6a294-240">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Immagine of_the richiesta di conferma dalla procedura guidata in cui fare clic su Inizia a usare Microsoft Defender per Endpoint](../../media/mtp-eval-67.png)

12. <span data-ttu-id="6a294-242">Visitare il [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="6a294-242">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="6a294-243">Vai a **Impostazioni** e quindi seleziona **Funzionalità avanzate.**</span><span class="sxs-lookup"><span data-stu-id="6a294-243">Go to **Settings** and then select **Advanced features**.</span></span>

    ![Image of_Microsoft Defender Security Center Impostazioni menu in cui selezionare Funzionalità avanzate](../../media/mtp-eval-68.png)

13. <span data-ttu-id="6a294-245">Attivare l'integrazione con **Microsoft Defender per l'identità**.</span><span class="sxs-lookup"><span data-stu-id="6a294-245">Turn on the integration with **Microsoft Defender for Identity**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Opzione di Microsoft Defender for Identity che devi attivare](../../media/mtp-eval-69.png)

14. <span data-ttu-id="6a294-247">Attivare l'integrazione con **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="6a294-247">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Office 365'opzione Threat Intelligence che devi attivare](../../media/mtp-eval-70.png)

15. <span data-ttu-id="6a294-249">Attivare l'integrazione **con Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="6a294-249">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Microsoft Cloud App Security'opzione che devi attivare](../../media/mtp-eval-71.png)

16. <span data-ttu-id="6a294-251">Scorri verso il basso e fai **clic su Salva preferenze** per confermare le nuove integrazioni.</span><span class="sxs-lookup"><span data-stu-id="6a294-251">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Pulsante of_Save preferenze di immagine su cui devi fare clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="6a294-253">Avviare il servizio Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a294-253">Start the Microsoft 365 Defender service</span></span>

> [!NOTE]
> <span data-ttu-id="6a294-254">A partire dal 1 giugno 2020, Microsoft abilita automaticamente le Microsoft 365 Defender per tutti i tenant idonei.</span><span class="sxs-lookup"><span data-stu-id="6a294-254">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="6a294-255">Per informazioni [dettagliate, vedere questo articolo di Microsoft Tech Community sull'idoneità delle](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) licenze.</span><span class="sxs-lookup"><span data-stu-id="6a294-255">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span>

<span data-ttu-id="6a294-256">Passare a [Microsoft 365 Sicurezza](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="6a294-256">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="6a294-257">Passare a **Impostazioni** e quindi selezionare **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="6a294-257">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![Screenshot of_Microsoft'opzione di Of_Microsoft Defender 365 dalla pagina Microsoft 365 Sicurezza Impostazioni sicurezza](../../media/mtp-eval-72b.png)

<span data-ttu-id="6a294-259">Per una guida più completa, vedere [Attivare Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="6a294-259">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="6a294-260">Congratulazioni.</span><span class="sxs-lookup"><span data-stu-id="6a294-260">Congratulations!</span></span> <span data-ttu-id="6a294-261">Hai appena creato il laboratorio di Microsoft 365 Defender o l'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="6a294-261">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="6a294-262">Ora è possibile acquisire familiarità con l'Microsoft 365 Defender utente.</span><span class="sxs-lookup"><span data-stu-id="6a294-262">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="6a294-263">Scopri cosa puoi imparare dalla seguente guida Microsoft 365 Defender interattiva e informazioni su come usare ogni dashboard per le attività quotidiane relative alle operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6a294-263">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="6a294-264">Consulta la guida interattiva</span><span class="sxs-lookup"><span data-stu-id="6a294-264">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="6a294-265">Successivamente, è possibile simulare un attacco e vedere come le funzionalità tra prodotti rilevano, creano avvisi e rispondono automaticamente a un attacco senza file su un endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a294-265">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="6a294-266">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6a294-266">Next step</span></span>

- <span data-ttu-id="6a294-267">[Generare un avviso di test:](generate-test-alert.md) eseguire una simulazione di attacco nel Microsoft 365 Defender di valutazione.</span><span class="sxs-lookup"><span data-stu-id="6a294-267">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>
