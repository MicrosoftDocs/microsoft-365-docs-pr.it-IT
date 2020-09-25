---
title: Configurare i pilastri Microsoft Threat Protection per il laboratorio di valutazione o l'ambiente pilota
description: Configurare i pilastri Microsoft Threat Protection, ad esempio Office 365 ATP, Azure ATP, Microsoft cloud app Security e Microsoft Defender ATP, per il laboratorio di valutazione o l'ambiente pilota.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 43facffde9c31dc33445de87997d2b91cba6a9f1
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277561"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="42350-104">Configurare i pilastri Microsoft Threat Protection per il laboratorio di valutazione o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="42350-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="42350-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="42350-105">**Applies to:**</span></span>
- <span data-ttu-id="42350-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="42350-107">La creazione di un ambiente pilota o di un laboratorio di valutazione di Microsoft Threat Protection è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="42350-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota" />
      <br/><span data-ttu-id="42350-109">Fase 1: preparazione </a></span><span class="sxs-lookup"><span data-stu-id="42350-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Configurare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota" />
      <br/><span data-ttu-id="42350-111">Fase 2: installazione </a></span><span class="sxs-lookup"><span data-stu-id="42350-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurare ogni pilastro Microsoft Threat Protection per il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota e gli endpoint di bordo" />
      <br/><span data-ttu-id="42350-113">Fase 3: configurare & onboard </a></span><span class="sxs-lookup"><span data-stu-id="42350-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="42350-114">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="42350-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="42350-115">La preparazione è la chiave per una distribuzione corretta.</span><span class="sxs-lookup"><span data-stu-id="42350-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="42350-116">In questo articolo verranno illustrati i punti che è necessario prendere in considerazione durante la preparazione per la distribuzione di Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="42350-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="42350-117">Pilastri di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="42350-118">Microsoft Threat Protection è costituito da quattro pilastri.</span><span class="sxs-lookup"><span data-stu-id="42350-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="42350-119">Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione della rete, l'abilitazione dei quattro pilastri Microsoft Threat Protection darà alla propria organizzazione il massimo valore.</span><span class="sxs-lookup"><span data-stu-id="42350-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="42350-120">Image of_Microsoft soluzione di protezione dalle minacce per gli utenti, la protezione avanzata dalle minacce di Azure, per gli endpoint Microsoft Defender Advanced Threat Protection, per le app Cloud, Microsoft cloud app Security e per i dati, Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png)

<span data-ttu-id="42350-121">In questa sezione viene illustrata la configurazione:</span><span class="sxs-lookup"><span data-stu-id="42350-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="42350-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="42350-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="42350-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="42350-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="42350-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="42350-126">Configurare Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-126">Configure Office 365 Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="42350-127">Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Office 365.</span><span class="sxs-lookup"><span data-stu-id="42350-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="42350-128">È presente un modulo di PowerShell denominato l' *analizzatore di configurazione consigliato di Office 365 Advanced Threat Protection (Orca)* che consente di determinare alcune di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="42350-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="42350-129">Quando si esegue il ruolo di amministratore nel tenant, Get-ORCAReport contribuirà a generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre informazioni di igiene dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="42350-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="42350-130">È possibile scaricare il modulo da https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="42350-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="42350-131">Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **policy**.</span><span class="sxs-lookup"><span data-stu-id="42350-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Pagina Image of_Office 365 Security & Compliance Center Threat Management Policy](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="42350-133">Fare clic su **ATP anti-phishing**, selezionare **Crea** e compila il nome e la descrizione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="42350-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="42350-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="42350-134">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile assegnare un nome ai criteri](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="42350-136">Modificare i criteri avanzati di anti-phishing ATP.</span><span class="sxs-lookup"><span data-stu-id="42350-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="42350-137">Modificare la **soglia di phishing avanzata** su **2-aggressiva**.</span><span class="sxs-lookup"><span data-stu-id="42350-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="42350-138">Fare clic sul menu a discesa **Aggiungi condizione** e selezionare il dominio o i domini come dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="42350-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="42350-139">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="42350-139">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile aggiungere una condizione per la relativa applicazione](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="42350-141">Esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="42350-141">Review your settings.</span></span> <span data-ttu-id="42350-142">Fare clic su **crea questo criterio** per confermare.</span><span class="sxs-lookup"><span data-stu-id="42350-142">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page dove è possibile rivedere le impostazioni e fare clic sul pulsante Crea questo criterio](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="42350-144">Selezionare **allegati sicuri di ATP** e selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .</span><span class="sxs-lookup"><span data-stu-id="42350-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="42350-146">Fare clic sull'icona + per creare un nuovo criterio allegato sicuro, applicarlo come dominio destinatario ai domini.</span><span class="sxs-lookup"><span data-stu-id="42350-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="42350-147">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42350-147">Click **Save**.</span></span>

   ![Image of_Office 365 Security & Compliance Center page in cui è possibile creare un nuovo criterio degli allegati sicuri](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="42350-149">Successivamente, selezionare il criterio **collegamenti sicuri ATP** , quindi fare clic sull'icona a forma di matita per modificare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="42350-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="42350-150">Verificare che l'opzione non **rintracci quando gli utenti fanno clic su collegamenti sicuri** non è selezionata, mentre le altre opzioni sono selezionate.</span><span class="sxs-lookup"><span data-stu-id="42350-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="42350-151">Per informazioni dettagliate, vedere [Safe Links Settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="42350-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="42350-152">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42350-152">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & Compliance Center page che indica che l'opzione non tiene conto del fatto che gli utenti fanno clic su sicuro non è selezionata](../../media/mtp-eval-38.png)

9. <span data-ttu-id="42350-154">Selezionare quindi il criterio **antimalware** , selezionare l'impostazione predefinita e scegliere l'icona a forma di matita.</span><span class="sxs-lookup"><span data-stu-id="42350-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="42350-155">Fare clic su **Impostazioni** e selezionare **Sì e utilizzare il testo di notifica predefinito** per abilitare la **risposta di rilevamento malware**.</span><span class="sxs-lookup"><span data-stu-id="42350-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="42350-156">Attiva il **filtro dei tipi di allegati comuni** .</span><span class="sxs-lookup"><span data-stu-id="42350-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="42350-157">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42350-157">Click **Save**.</span></span>

    ![Image of_Office 365 Security & Compliance Center page che indica che la risposta di rilevamento malware è attivata con la notifica predefinita e che il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="42350-159">Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Search**  >  **log di controllo** di ricerca e attivazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="42350-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare la ricerca del registro di controllo](../../media/mtp-eval-40.png)

12. <span data-ttu-id="42350-161">Integrazione di Office 365 ATP con Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="42350-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="42350-162">Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Explorer** e selezionare le **impostazioni di WDATP** nell'angolo superiore destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="42350-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="42350-163">Nella finestra di dialogo Microsoft Defender ATP Connection, abilitare **Connect to Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="42350-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>

    ![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare la connessione a Windows Defender ATP](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="42350-165">Configurare la protezione avanzata dalle minacce di Azure</span><span class="sxs-lookup"><span data-stu-id="42350-165">Configure Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="42350-166">Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Azure</span><span class="sxs-lookup"><span data-stu-id="42350-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>

1. <span data-ttu-id="42350-167">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info) > selezionare **altre risorse**  >  **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="42350-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>

   ![Image of_Microsoft 365 pagina Centro sicurezza in cui è disponibile un'opzione per aprire Azure Advanced Threat Protection](../../media/mtp-eval-42.png)

2. <span data-ttu-id="42350-169">Fare clic su **Crea** per avviare la procedura guidata di Azure Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="42350-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 

   ![Immagine of_Azure pagina avanzata della procedura guidata di protezione dalle minacce in cui è necessario fare clic su Crea pulsante](../../media/mtp-eval-43.png)

3. <span data-ttu-id="42350-171">Scegliere **Fornisci un nome utente e una password per connettersi alla foresta di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="42350-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Pagina di benvenuto per l'immagine of_Azure Advanced Threat Protection](../../media/mtp-eval-44.png)

4. <span data-ttu-id="42350-173">Immettere le credenziali di Active Directory in locale.</span><span class="sxs-lookup"><span data-stu-id="42350-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="42350-174">Può trattarsi di qualsiasi account utente che disponga dell'accesso in lettura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42350-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Immagine of_Azure pagina servizi directory Advanced Threat Protection in cui inserire le credenziali](../../media/mtp-eval-45.png)

5. <span data-ttu-id="42350-176">Successivamente, scegliere **download Sensor Setup** and transfer file to your domain controller.</span><span class="sxs-lookup"><span data-stu-id="42350-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Immagine of_Azure pagina avanzata di protezione dalle minacce in cui è possibile selezionare Download Sensor Setup](../../media/mtp-eval-46.png)

6. <span data-ttu-id="42350-178">Eseguire il programma di installazione del sensore ATP di Azure e iniziare a seguire la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="42350-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>

   ![Immagine of_Azure pagina avanzata di protezione dalle minacce in cui è necessario fare clic su Avanti per seguire la procedura guidata del sensore ATP di Azure](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="42350-180">Fare clic su **Avanti** nel tipo di distribuzione del sensore.</span><span class="sxs-lookup"><span data-stu-id="42350-180">Click **Next** at the sensor deployment type.</span></span>

   ![Immagine of_Azure pagina avanzata di protezione dalle minacce in cui è necessario fare clic su Avanti per passare alla pagina successiva](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="42350-182">Copiare il tasto di accesso perché è necessario immetterlo successivamente nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="42350-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Pagina of_the sensori immagine in cui è necessario copiare la chiave di accesso che è necessario immettere nella pagina successiva installazione guidata sensore di Azure ATP](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="42350-184">Copiare la chiave di accesso nella procedura guidata e fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="42350-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Immagine of_Azure pagina Advanced Threat Protection Azure ATP Sensor Wizard in cui è necessario fornire il tasto di accesso e quindi fare clic sul pulsante Installa.](../../media/mtp-eval-50.png)

10. <span data-ttu-id="42350-186">Congratulazioni, è stata configurata correttamente la protezione avanzata dalle minacce di Azure nel controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="42350-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>

    ![Immagine of_Azure Advanced Threat Protection Azure ATP Sensor Wizard completamento dell'installazione in cui è necessario fare clic sul pulsante fine](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="42350-188">Nella sezione impostazioni [ATP di Azure Azure](https://go.microsoft.com/fwlink/?linkid=2040449) selezionare **Windows Defender ATP**e quindi attivare l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="42350-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="42350-189">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42350-189">Click **Save**.</span></span> 

    ![Immagine of_the pagina Impostazioni ATP di Azure Azure in cui è necessario attivare l'interruttore ATP di Windows Defender](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="42350-191">Windows Defender ATP è stato rebranded As Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="42350-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="42350-192">Le modifiche di rebranding in tutti i portali vengono distribuite per garantire la coerenza.</span><span class="sxs-lookup"><span data-stu-id="42350-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="42350-193">Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="42350-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="42350-194">Ignorare questo passaggio se è già stata abilitata la sicurezza delle app cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="42350-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="42350-195">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="42350-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Immagine of_Microsoft 365 pagina Centro sicurezza in cui è possibile visualizzare la scheda app cloud Microsoft e fare clic sul pulsante Apri.](../../media/mtp-eval-53.png)

2. <span data-ttu-id="42350-197">Alla richiesta di informazioni per l'integrazione di Azure ATP, selezionare **Enable Azure ATP Data Integration**.</span><span class="sxs-lookup"><span data-stu-id="42350-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span>
  
   ![Of_the di informazioni per l'integrazione dell'ATP di Azure in cui è necessario selezionare il collegamento attiva l'integrazione dei dati di Azure ATP](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="42350-199">Se questo messaggio non viene visualizzato, potrebbe significare che l'integrazione dei dati ATP di Azure è già stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="42350-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="42350-200">Tuttavia, se non si è certi, contattare l'amministratore IT per confermare.</span><span class="sxs-lookup"><span data-stu-id="42350-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="42350-201">Andare a **Impostazioni**, attivare l'interruttore di **integrazione ATP di Azure** , quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42350-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 

   ![Pagina Impostazioni of_the immagine in cui è necessario attivare l'interruttore di integrazione ATP di Azure e quindi fare clic su Salva](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="42350-203">Per le nuove istanze di Azure ATP, questo interruttore di integrazione viene attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="42350-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="42350-204">Verificare che l'integrazione di Azure ATP sia stata abilitata prima di procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="42350-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="42350-205">In impostazioni di individuazione cloud selezionare **Microsoft Defender ATP Integration**e quindi abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="42350-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="42350-206">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42350-206">Click **Save**.</span></span>

   ![Immagine of_the Microsoft Defender ATP pagina in cui è selezionata la casella di controllo Blocca app non autorizzate in Microsoft Defender ATP Integration.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="42350-209">In impostazioni di individuazione cloud selezionare **arricchimento degli utenti**e quindi abilitare l'integrazione con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42350-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Immagine della sezione di arricchimento degli utenti in cui è selezionata la casella di controllo arricchisci gli identificatori utente individuati con Azure Active Directory nomeutente.](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="42350-211">Configurare Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-211">Configure Microsoft Defender Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="42350-212">Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="42350-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="42350-213">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="42350-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="42350-214">Fare clic su **Apri**. </span><span class="sxs-lookup"><span data-stu-id="42350-214">Click **Open**.</span></span>

   ![Opzione Image of_Microsoft Defender Security Center nella pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="42350-216">Seguire la procedura guidata Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="42350-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="42350-217">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="42350-217">Click **Next**.</span></span> 

   ![Pagina of_the di Microsoft Defender Security Center Wizard di benvenuto](../../media/mtp-eval-59.png)

3. <span data-ttu-id="42350-219">Scegliere in base alla posizione di archiviazione dei dati preferita, al criterio di conservazione dei dati, alle dimensioni dell'organizzazione e all'opt-in per le funzionalità di anteprima.</span><span class="sxs-lookup"><span data-stu-id="42350-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Pagina of_the immagine per selezionare il paese di archiviazione dei dati, i criteri di conservazione e le dimensioni dell'organizzazione.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="42350-222">Non è possibile modificare alcune impostazioni, ad esempio il percorso di archiviazione dei dati, in seguito.</span><span class="sxs-lookup"><span data-stu-id="42350-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="42350-223">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="42350-223">Click **Next**.</span></span> 

4. <span data-ttu-id="42350-224">Fare clic su **continua** e verrà eseguito il provisioning del tenant Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="42350-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>

   ![Pagina of_the immagini che richiede di fare clic sul pulsante continua per creare l'istanza del cloud](../../media/mtp-eval-61.png)

5. <span data-ttu-id="42350-226">Onboard your Endpoints tramite criteri di gruppo, Microsoft Endpoint Manager o esecuzione di uno script locale in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="42350-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="42350-227">Per semplicità, in questa guida viene utilizzato lo script locale.</span><span class="sxs-lookup"><span data-stu-id="42350-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="42350-228">Fare clic su **Scarica pacchetto** e copiare lo script di onboarding negli endpoint.</span><span class="sxs-lookup"><span data-stu-id="42350-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Of_page immagine che richiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o negli endpoint](../../media/mtp-eval-62.png)

7. <span data-ttu-id="42350-230">Nell'endpoint, eseguire lo script onboarding come amministratore e scegliere Y.</span><span class="sxs-lookup"><span data-stu-id="42350-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Immagine of_the riga di comando in cui si esegue lo script di onboarding e scegliere Y per continuare](../../media/mtp-eval-63.png)

8. <span data-ttu-id="42350-232">Congratulazioni, è stato imbarcato il primo endpoint.</span><span class="sxs-lookup"><span data-stu-id="42350-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the CommandLine, in cui viene confermata l'onboarding del primo endpoint.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="42350-235">Copia e incolla il test di rilevamento dalla procedura guidata ATP di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="42350-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>

   ![Of_the immagine eseguire un passaggio del test di rilevamento in cui è necessario fare clic su copia per copiare lo script di test di rilevamento che è necessario incollare nel prompt dei comandi](../../media/mtp-eval-65.png)

10. <span data-ttu-id="42350-237">Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="42350-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Prompt of_command immagine in cui è necessario copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="42350-239">Fare clic su **avvia tramite Microsoft Defender ATP** dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="42350-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>

    ![Prompt di conferma dell'immagine of_the dalla procedura guidata in cui è necessario fare clic su avvia tramite Microsoft Defender ATP](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="42350-241">Visitare il [Centro sicurezza di Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="42350-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="42350-242">Andare a **Impostazioni** , quindi selezionare **funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="42350-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Image of_Microsoft Defender Security Center Settings menu in cui è necessario selezionare funzionalità avanzate](../../media/mtp-eval-68.png)

13. <span data-ttu-id="42350-244">Attiva l'integrazione con **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="42350-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced Features, l'opzione per la protezione avanzata dalle minacce di Azure è necessario attivare](../../media/mtp-eval-69.png)

14. <span data-ttu-id="42350-246">Attiva l'integrazione con **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="42350-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Office 365 Threat Intelligence Option Toggle che è necessario attivare](../../media/mtp-eval-70.png)

15. <span data-ttu-id="42350-248">Attiva l'integrazione con **Microsoft cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="42350-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Microsoft cloud app Security Option Toggle che è necessario attivare](../../media/mtp-eval-71.png)

16. <span data-ttu-id="42350-250">Scorrere verso il basso e fare clic su **Salva preferenze** per confermare le nuove integrazioni.</span><span class="sxs-lookup"><span data-stu-id="42350-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Pulsante Preferenze of_Save immagine che è necessario fare clic su](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="42350-252">Avviare il servizio Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42350-252">Start the Microsoft Threat Protection service</span></span>

>[!NOTE]
><span data-ttu-id="42350-253">A partire dal 1 ° giugno 2020, Microsoft attiva automaticamente le funzionalità di protezione dalle minacce di Microsoft per tutti i tenant idonei.</span><span class="sxs-lookup"><span data-stu-id="42350-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="42350-254">Per ulteriori informazioni, vedere l' [articolo relativo a Microsoft Tech Community sull'idoneità delle licenze](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="42350-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="42350-255">Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="42350-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="42350-256">Passare a **Impostazioni** , quindi selezionare **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="42350-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>

![<span data-ttu-id="42350-257">Immagine of_Microsoft opzione di protezione dalle minacce screenshot dalla pagina delle impostazioni di Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="42350-257">Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="42350-258">Per ulteriori informazioni, vedere [abilitare Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="42350-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="42350-259">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="42350-259">Congratulations!</span></span> <span data-ttu-id="42350-260">È stato appena creato il laboratorio di valutazione di Microsoft Threat Protection o un ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="42350-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="42350-261">A questo punto, è possibile acquisire familiarità con l'interfaccia utente di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="42350-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="42350-262">Vedere cosa si può imparare dalla seguente guida interattiva di Microsoft Threat Protection e sapere come utilizzare ogni dashboard per le attività quotidiane di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="42350-262">See what you can learn from the following Microsoft Threat Protection interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="42350-263">Successivamente, è possibile simulare un attacco e vedere in che modo le funzionalità del prodotto incrociato rilevano, creano avvisi e rispondono automaticamente a un attacco non file su un endpoint.</span><span class="sxs-lookup"><span data-stu-id="42350-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="42350-264">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="42350-264">Next step</span></span>
|<span data-ttu-id="42350-265">![Fase di simulazione d'attacco](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="42350-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="42350-266">Fase di simulazione d'attacco</span><span class="sxs-lookup"><span data-stu-id="42350-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="42350-267">Eseguire la simulazione di attacco per l'ambiente pilota di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="42350-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
