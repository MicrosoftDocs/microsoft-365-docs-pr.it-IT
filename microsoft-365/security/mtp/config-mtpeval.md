---
title: Configurare i pilastri Microsoft 365 Defender per il laboratorio di valutazione o l'ambiente pilota
description: Configurare i pilastri Microsoft 365 Defender, ad esempio Microsoft Defender per Office 365, Microsoft Defender per Identity, Microsoft cloud app Security e Microsoft Defender per endpoint, per il laboratorio di valutazione o l'ambiente pilota.
keywords: configurazione di Microsoft Threat Protection Trial, Microsoft Threat Protection Trial Configuration, Configure Microsoft Threat Protection Pilot Project, Configure Microsoft Threat Protection Pillars, Microsoft Threat Protection Pillars
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131298"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="b205b-104">Configurare i pilastri Microsoft 365 Defender per il laboratorio di valutazione o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="b205b-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b205b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b205b-105">**Applies to:**</span></span>
- <span data-ttu-id="b205b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b205b-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="b205b-107">La creazione di un ambiente pilota o di un laboratorio di valutazione di Microsoft 365 Defender è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="b205b-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="b205b-108">[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="b205b-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="b205b-109">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="b205b-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="b205b-110">[![Fase 2: configurare](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="b205b-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="b205b-111">Fase 2: configurare</span><span class="sxs-lookup"><span data-stu-id="b205b-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="b205b-113">Fase 3: Onboard</span><span class="sxs-lookup"><span data-stu-id="b205b-113">Phase 3: Onboard</span></span> | <span data-ttu-id="b205b-114">[![Torna a Pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="b205b-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="b205b-115">Torna a Pilot PlayBook</span><span class="sxs-lookup"><span data-stu-id="b205b-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="b205b-116">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="b205b-116">*You are here!*</span></span> | |

<span data-ttu-id="b205b-117">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b205b-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="b205b-118">La preparazione è la chiave per una distribuzione corretta.</span><span class="sxs-lookup"><span data-stu-id="b205b-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="b205b-119">In questo articolo verranno illustrati i punti che è necessario prendere in considerazione durante la preparazione per la distribuzione di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="b205b-120">Pilastri Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b205b-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="b205b-121">Microsoft 365 Defender è costituito da quattro pilastri.</span><span class="sxs-lookup"><span data-stu-id="b205b-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="b205b-122">Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione della rete, l'abilitazione dei quattro pilastri Microsoft 365 Defender consentirà alla propria organizzazione di ottenere il massimo valore.</span><span class="sxs-lookup"><span data-stu-id="b205b-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft soluzione Defender di 365 per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender per endpoint, per le app Cloud, per la sicurezza di Microsoft cloud app e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="b205b-124">In questa sezione viene illustrata la configurazione:</span><span class="sxs-lookup"><span data-stu-id="b205b-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="b205b-125">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="b205b-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="b205b-126">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="b205b-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="b205b-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b205b-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="b205b-128">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b205b-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="b205b-129">Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="b205b-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="b205b-130">Ignorare questo passaggio se è già stata abilitata la protezione per Office 365.</span><span class="sxs-lookup"><span data-stu-id="b205b-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="b205b-131">È presente un modulo di PowerShell denominato l' *analizzatore di configurazione consigliato di Office 365 Advanced Threat Protection (Orca)* che consente di determinare alcune di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b205b-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="b205b-132">Quando si esegue il ruolo di amministratore nel tenant, Get-ORCAReport contribuirà a generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre informazioni di igiene dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b205b-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="b205b-133">È possibile scaricare il modulo da https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="b205b-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="b205b-134">Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **policy**.</span><span class="sxs-lookup"><span data-stu-id="b205b-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Pagina Image of_Office 365 Security & Compliance Center Threat Management Policy](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="b205b-136">Fare clic su **anti-phishing**, selezionare **Crea** e compila il nome e la descrizione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="b205b-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="b205b-137">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b205b-137">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile assegnare un nome ai criteri](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="b205b-139">Modificare il criterio anti-phishing avanzato in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="b205b-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b205b-140">Modificare la **soglia di phishing avanzata** su **2-aggressiva**.</span><span class="sxs-lookup"><span data-stu-id="b205b-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="b205b-141">Fare clic sul menu a discesa **Aggiungi condizione** e selezionare il dominio o i domini come dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b205b-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="b205b-142">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b205b-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile aggiungere una condizione per la relativa applicazione](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="b205b-144">Esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b205b-144">Review your settings.</span></span> <span data-ttu-id="b205b-145">Fare clic su **crea questo criterio** per confermare.</span><span class="sxs-lookup"><span data-stu-id="b205b-145">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page dove è possibile rivedere le impostazioni e fare clic sul pulsante Crea questo criterio](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="b205b-147">Selezionare **allegati sicuri** e selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .</span><span class="sxs-lookup"><span data-stu-id="b205b-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="b205b-149">Fare clic sull'icona + per creare un nuovo criterio allegato sicuro, applicarlo come dominio destinatario ai domini.</span><span class="sxs-lookup"><span data-stu-id="b205b-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="b205b-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b205b-150">Click **Save**.</span></span>

   ![Image of_Office 365 Security & Compliance Center page in cui è possibile creare un nuovo criterio degli allegati sicuri](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="b205b-152">Successivamente, selezionare il criterio **collegamenti sicuri** , quindi fare clic sull'icona matita per modificare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b205b-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="b205b-153">Verificare che l'opzione non **rintracci quando gli utenti fanno clic su collegamenti sicuri** non è selezionata, mentre le altre opzioni sono selezionate.</span><span class="sxs-lookup"><span data-stu-id="b205b-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="b205b-154">Per informazioni dettagliate, vedere [Safe Links Settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="b205b-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="b205b-155">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b205b-155">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & Compliance Center page che indica che l'opzione non tiene conto del fatto che gli utenti fanno clic su sicuro non è selezionata](../../media/mtp-eval-38.png)

9. <span data-ttu-id="b205b-157">Selezionare quindi il criterio **antimalware** , selezionare l'impostazione predefinita e scegliere l'icona a forma di matita.</span><span class="sxs-lookup"><span data-stu-id="b205b-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="b205b-158">Fare clic su **Impostazioni** e selezionare **Sì e utilizzare il testo di notifica predefinito** per abilitare la **risposta di rilevamento malware**.</span><span class="sxs-lookup"><span data-stu-id="b205b-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="b205b-159">Attiva il **filtro dei tipi di allegati comuni** .</span><span class="sxs-lookup"><span data-stu-id="b205b-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="b205b-160">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b205b-160">Click **Save**.</span></span>

    ![Image of_Office 365 Security & Compliance Center page che indica che la risposta di rilevamento malware è attivata con la notifica predefinita e che il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="b205b-162">Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Search**  >  **log di controllo** di ricerca e attivazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="b205b-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare la ricerca del registro di controllo](../../media/mtp-eval-40.png)

12. <span data-ttu-id="b205b-164">Integrazione di Microsoft Defender per Office 365 con Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b205b-165">Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Explorer** e selezionare **Microsoft Defender per le impostazioni dell'endpoint** nell'angolo in alto a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="b205b-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="b205b-166">Nella finestra di dialogo protezione per la connessione endpoint, abilitare la **connessione a Microsoft Defender per endpoint**.</span><span class="sxs-lookup"><span data-stu-id="b205b-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Image of_Office 365 sicurezza & centro conformità pagina in cui è possibile trasformare Microsoft Defender per la connessione endpoint su](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="b205b-168">Configurare Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="b205b-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="b205b-169">Ignorare questo passaggio se è già stato abilitato Microsoft Defender per Identity</span><span class="sxs-lookup"><span data-stu-id="b205b-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="b205b-170">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info) > selezionare **altre risorse**  >  **Microsoft Defender per Identity**.</span><span class="sxs-lookup"><span data-stu-id="b205b-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Image of_Microsoft 365 pagina Centro sicurezza in cui è disponibile un'opzione per aprire Microsoft Defender per Identity](../../media/mtp-eval-42.png)

2. <span data-ttu-id="b205b-172">Fare clic su **Crea** per avviare la procedura guidata Microsoft Defender per identità.</span><span class="sxs-lookup"><span data-stu-id="b205b-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Pagina immagine of_Microsoft protezione per la creazione guidata identità in cui è necessario fare clic su Crea pulsante](../../media/mtp-eval-43.png)

3. <span data-ttu-id="b205b-174">Scegliere **Fornisci un nome utente e una password per connettersi alla foresta di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b205b-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Immagine of_Microsoft difensore per la pagina di benvenuto dell'identità](../../media/mtp-eval-44.png)

4. <span data-ttu-id="b205b-176">Immettere le credenziali di Active Directory in locale.</span><span class="sxs-lookup"><span data-stu-id="b205b-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="b205b-177">Può trattarsi di qualsiasi account utente che disponga dell'accesso in lettura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b205b-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft Defender per la pagina dei servizi directory di identità in cui è necessario inserire le credenziali](../../media/mtp-eval-45.png)

5. <span data-ttu-id="b205b-179">Successivamente, scegliere **download Sensor Setup** and transfer file to your domain controller.</span><span class="sxs-lookup"><span data-stu-id="b205b-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Immagine of_Microsoft difensore della pagina identità in cui è possibile selezionare Download Sensor Setup](../../media/mtp-eval-46.png)

6. <span data-ttu-id="b205b-181">Eseguire il programma di installazione di Microsoft Defender per il sensore di identità e iniziare a seguire la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b205b-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Immagine of_Microsoft difensore della pagina identità in cui è necessario fare clic su Avanti per seguire la procedura guidata Microsoft Defender for Identity Sensor](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="b205b-183">Fare clic su **Avanti** nel tipo di distribuzione del sensore.</span><span class="sxs-lookup"><span data-stu-id="b205b-183">Click **Next** at the sensor deployment type.</span></span>

   ![Immagine of_Microsoft difensore della pagina identità in cui è necessario fare clic su Avanti per passare alla pagina successiva](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="b205b-185">Copiare il tasto di accesso perché è necessario immetterlo successivamente nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b205b-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Pagina of_the sensori immagine in cui è necessario copiare la chiave di accesso che è necessario immettere nella pagina successiva installazione guidata del Microsoft Defender per il sensore di identità](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="b205b-187">Copiare la chiave di accesso nella procedura guidata e fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="b205b-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Immagine of_Microsoft Defender per la pagina della procedura guidata sensore di identità in cui è necessario fornire il tasto di accesso e quindi fare clic sul pulsante Installa.](../../media/mtp-eval-50.png)

10. <span data-ttu-id="b205b-189">Congratulazioni, è stata configurata correttamente Microsoft Defender per Identity nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="b205b-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Immagine of_Microsoft Defender per il completamento dell'installazione guidata del sensore di identità in cui è necessario fare clic sul pulsante fine](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="b205b-191">Nella sezione [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) Settings selezionare \* \* Microsoft Defender per endpoint \* \*, quindi attivare l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="b205b-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="b205b-192">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b205b-192">Click **Save**.</span></span> 

    ![Immagine of_the Microsoft Defender per le impostazioni di identità pagina in cui è necessario attivare l'interruttore Microsoft Defender for endpoint su](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="b205b-194">Windows Defender ATP è stato riassegnato come Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b205b-195">Le modifiche di rebranding in tutti i portali vengono distribuite per garantire la coerenza.</span><span class="sxs-lookup"><span data-stu-id="b205b-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="b205b-196">Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="b205b-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="b205b-197">Ignorare questo passaggio se è già stata abilitata la sicurezza delle app cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b205b-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="b205b-198">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="b205b-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Immagine of_Microsoft 365 pagina Centro sicurezza in cui è possibile visualizzare la scheda app cloud Microsoft e fare clic sul pulsante Apri.](../../media/mtp-eval-53.png)

2. <span data-ttu-id="b205b-200">Alla richiesta di informazioni per l'integrazione di Microsoft Defender per Identity, selezionare **Abilita Microsoft Defender per Identity Data Integration**.</span><span class="sxs-lookup"><span data-stu-id="b205b-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Richiesta di informazioni of_the per l'integrazione di Microsoft Defender per l'identità in cui è necessario selezionare il collegamento attiva Microsoft Defender per l'integrazione dei dati di identità](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="b205b-202">Se non viene visualizzato questo messaggio, potrebbe significare che l'integrazione dei dati di Microsoft Defender per Identity è già stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="b205b-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="b205b-203">Tuttavia, se non si è certi, contattare l'amministratore IT per confermare.</span><span class="sxs-lookup"><span data-stu-id="b205b-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="b205b-204">Andare a **Impostazioni**, attivare l'interruttore **Microsoft Defender per l'integrazione delle identità** , quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b205b-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Pagina Impostazioni of_the immagine in cui è necessario attivare l'interruttore Microsoft Defender per l'integrazione delle identità e quindi fare clic su Salva](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="b205b-206">Per le istanze di Microsoft Defender nuove per le identità, questo interruttore di integrazione viene attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b205b-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="b205b-207">Verificare che l'integrazione di Microsoft Defender per l'identità sia stata abilitata prima di procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="b205b-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="b205b-208">In impostazioni di individuazione cloud selezionare **Microsoft Defender per l'integrazione di endpoint** e quindi abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="b205b-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="b205b-209">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b205b-209">Click **Save**.</span></span>

   ![Immagine of_the Microsoft Defender for Endpoint pagina in cui è selezionata la casella di controllo Blocca app non autorizzate in Microsoft Defender for endpoint Integration.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="b205b-212">In impostazioni di individuazione cloud selezionare **arricchimento degli utenti** e quindi abilitare l'integrazione con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b205b-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Immagine della sezione di arricchimento degli utenti in cui è selezionata la casella di controllo arricchisci gli identificatori utente individuati con Azure Active Directory nomeutente.](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="b205b-214">Configurare Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b205b-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="b205b-215">Ignorare questo passaggio se è già stato abilitato Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="b205b-216">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="b205b-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="b205b-217">Fare clic su **Apri**. </span><span class="sxs-lookup"><span data-stu-id="b205b-217">Click **Open**.</span></span>

   ![Opzione Image of_Microsoft Defender Security Center nella pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="b205b-219">Seguire la procedura guidata Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="b205b-220">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b205b-220">Click **Next**.</span></span> 

   ![Pagina of_the di Microsoft Defender Security Center Wizard di benvenuto](../../media/mtp-eval-59.png)

3. <span data-ttu-id="b205b-222">Scegliere in base alla posizione di archiviazione dei dati preferita, al criterio di conservazione dei dati, alle dimensioni dell'organizzazione e all'opt-in per le funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="b205b-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Pagina of_the immagine per selezionare il paese di archiviazione dei dati, i criteri di conservazione e le dimensioni dell'organizzazione.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="b205b-225">Non è possibile modificare alcune impostazioni, ad esempio il percorso di archiviazione dei dati, in seguito.</span><span class="sxs-lookup"><span data-stu-id="b205b-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="b205b-226">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b205b-226">Click **Next**.</span></span> 

4. <span data-ttu-id="b205b-227">Fare clic su **continua** e verrà eseguito il provisioning di Microsoft Defender per endpoint tenant.</span><span class="sxs-lookup"><span data-stu-id="b205b-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Pagina of_the immagini che richiede di fare clic sul pulsante continua per creare l'istanza del cloud](../../media/mtp-eval-61.png)

5. <span data-ttu-id="b205b-229">Onboard your Endpoints tramite criteri di gruppo, Microsoft Endpoint Manager o esecuzione di uno script locale in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b205b-230">Per semplicità, in questa guida viene utilizzato lo script locale.</span><span class="sxs-lookup"><span data-stu-id="b205b-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="b205b-231">Fare clic su **Scarica pacchetto** e copiare lo script di onboarding negli endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Of_page immagine che richiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o negli endpoint](../../media/mtp-eval-62.png)

7. <span data-ttu-id="b205b-233">Nell'endpoint, eseguire lo script onboarding come amministratore e scegliere Y.</span><span class="sxs-lookup"><span data-stu-id="b205b-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Immagine of_the riga di comando in cui si esegue lo script di onboarding e scegliere Y per continuare](../../media/mtp-eval-63.png)

8. <span data-ttu-id="b205b-235">Congratulazioni, è stato imbarcato il primo endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the CommandLine, in cui viene confermata l'onboarding del primo endpoint.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="b205b-238">Copia e incolla il test di rilevamento dalla procedura guidata Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Of_the immagine eseguire un passaggio del test di rilevamento in cui è necessario fare clic su copia per copiare lo script di test di rilevamento che è necessario incollare nel prompt dei comandi](../../media/mtp-eval-65.png)

10. <span data-ttu-id="b205b-240">Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="b205b-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Prompt of_command immagine in cui è necessario copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="b205b-242">Selezionare **avvia tramite Microsoft Defender per endpoint** dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b205b-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Prompt di conferma dell'immagine of_the dalla procedura guidata in cui è necessario fare clic su avvia tramite Microsoft Defender per endpoint](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="b205b-244">Visitare il [Centro sicurezza di Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="b205b-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="b205b-245">Andare a **Impostazioni** , quindi selezionare **funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b205b-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Image of_Microsoft Defender Security Center Settings menu in cui è necessario selezionare funzionalità avanzate](../../media/mtp-eval-68.png)

13. <span data-ttu-id="b205b-247">Attiva l'integrazione con **Microsoft Defender per Identity**.</span><span class="sxs-lookup"><span data-stu-id="b205b-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced Features, Microsoft Defender for Identity Option Toggle che è necessario attivare](../../media/mtp-eval-69.png)

14. <span data-ttu-id="b205b-249">Attiva l'integrazione con **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="b205b-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Office 365 Threat Intelligence Option Toggle che è necessario attivare](../../media/mtp-eval-70.png)

15. <span data-ttu-id="b205b-251">Attiva l'integrazione con **Microsoft cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="b205b-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Microsoft cloud app Security Option Toggle che è necessario attivare](../../media/mtp-eval-71.png)

16. <span data-ttu-id="b205b-253">Scorrere verso il basso e fare clic su **Salva preferenze** per confermare le nuove integrazioni.</span><span class="sxs-lookup"><span data-stu-id="b205b-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Pulsante Preferenze of_Save immagine che è necessario fare clic su](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="b205b-255">Avviare il servizio Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b205b-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="b205b-256">A partire dal 1 ° giugno 2020, Microsoft attiva automaticamente le funzionalità di Microsoft 365 Defender per tutti i tenant idonei.</span><span class="sxs-lookup"><span data-stu-id="b205b-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="b205b-257">Per ulteriori informazioni, vedere l' [articolo relativo a Microsoft Tech Community sull'idoneità delle licenze](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="b205b-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="b205b-258">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="b205b-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="b205b-259">Passare a **Impostazioni** , quindi selezionare **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="b205b-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="b205b-260">Image of_Microsoft 365 Defender Option screenshot dalla pagina delle impostazioni di Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="b205b-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="b205b-261">Per ulteriori informazioni, vedere [accendere Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="b205b-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="b205b-262">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="b205b-262">Congratulations!</span></span> <span data-ttu-id="b205b-263">Si è appena creato il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="b205b-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="b205b-264">A questo punto, è possibile acquisire familiarità con l'interfaccia utente Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b205b-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="b205b-265">Vedere cosa si può imparare dalla seguente guida interattiva di Microsoft 365 Defender e sapere come utilizzare ogni dashboard per le attività quotidiane di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b205b-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="b205b-266">Successivamente, è possibile simulare un attacco e vedere in che modo le funzionalità del prodotto incrociato rilevano, creano avvisi e rispondono automaticamente a un attacco non file su un endpoint.</span><span class="sxs-lookup"><span data-stu-id="b205b-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="b205b-267">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b205b-267">Next step</span></span>
|[<span data-ttu-id="b205b-268">Fase di simulazione d'attacco</span><span class="sxs-lookup"><span data-stu-id="b205b-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="b205b-269">Eseguire la simulazione di attacco per l'ambiente pilota Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b205b-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
