---
title: Analizzatore configurazione conformità Microsoft per Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come usare Microsoft Compliance Configuration Analyzer per iniziare rapidamente a usare Microsoft Compliance Manager.
ms.openlocfilehash: 36f11597eac1837e3e18885f3c0a5d8dbc89a774
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148963"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="086b9-103">Analizzatore configurazione conformità Microsoft per Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="086b9-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="086b9-104">**In questo articolo:** Informazioni su come installare ed eseguire lo strumento Microsoft Compliance Configure Analyzer per iniziare rapidamente a usare Microsoft Compliance Manger.</span><span class="sxs-lookup"><span data-stu-id="086b9-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="086b9-105">Panoramica di Microsoft Compliance Configuration Analyzer (MCCA) (anteprima)</span><span class="sxs-lookup"><span data-stu-id="086b9-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="086b9-106">Microsoft Compliance Configuration Analyzer (MCCA) è uno strumento di anteprima che consente di iniziare a usare [Microsoft Compliance Manager.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="086b9-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="086b9-107">MCCA è un'utilità basata su PowerShell che recupera le configurazioni correnti dell'organizzazione e le convalida Microsoft 365 consigliate.</span><span class="sxs-lookup"><span data-stu-id="086b9-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="086b9-108">Queste procedure consigliate si basano su un set di controlli che includono normative e standard chiave per la protezione dei dati e la governance dei dati.</span><span class="sxs-lookup"><span data-stu-id="086b9-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="086b9-109">MCCA consente di vedere rapidamente quali azioni di miglioramento in Compliance Manager si applicano all'ambiente Microsoft 365 corrente.</span><span class="sxs-lookup"><span data-stu-id="086b9-109">MCCA can help you quickly see which improvement actions in Compliance Manager apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="086b9-110">Ogni azione identificata da MCCA offrirà consigli per l'implementazione, con collegamenti diretti a Compliance Manager e alla soluzione applicabile per iniziare a prendere misure correttive.</span><span class="sxs-lookup"><span data-stu-id="086b9-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="086b9-111">Una risorsa aggiuntiva per comprendere MCCA è visitare le istruzioni [README su GitHub](https://github.com/OfficeDev/MCCA#overview).</span><span class="sxs-lookup"><span data-stu-id="086b9-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="086b9-112">In questa pagina vengono fornite informazioni dettagliate sui prerequisiti e vengono fornite istruzioni complete per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="086b9-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="086b9-113">Non è necessario un account GitHub per accedere a questa pagina.</span><span class="sxs-lookup"><span data-stu-id="086b9-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="086b9-114">**Disponibilità**: MCCA è disponibile per tutte le organizzazioni con licenze di Office 365 e Microsoft 365 e per i clienti di US Government Community (GCC) Moderate, GCC High e Department of Defense (DoD).</span><span class="sxs-lookup"><span data-stu-id="086b9-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="086b9-115">Installare MCCA ed eseguire un report</span><span class="sxs-lookup"><span data-stu-id="086b9-115">Install MCCA and run a report</span></span>

<span data-ttu-id="086b9-116">Puoi installare lo strumento MCCA usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="086b9-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="086b9-117">Dopo aver scaricato e installato lo strumento, non è necessario ripetere questi passaggi per eseguire i report.</span><span class="sxs-lookup"><span data-stu-id="086b9-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="086b9-118">Ogni volta che apri MCCA, ti chiederà le credenziali di accesso e genererà un nuovo report aggiornato.</span><span class="sxs-lookup"><span data-stu-id="086b9-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="086b9-119">Passaggio 1: installare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="086b9-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="086b9-120">Per iniziare, è necessario il modulo Exchange Online PowerShell (v2.0.3 o versione successiva) disponibile nella raccolta PowerShell.</span><span class="sxs-lookup"><span data-stu-id="086b9-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="086b9-121">[Ottenere le istruzioni di installazione](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span><span class="sxs-lookup"><span data-stu-id="086b9-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="086b9-122">Passaggio 2: installare MCCA</span><span class="sxs-lookup"><span data-stu-id="086b9-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="086b9-123">Per installare MCCA, iniziare usando PowerShell in modalità amministratore.</span><span class="sxs-lookup"><span data-stu-id="086b9-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="086b9-124">Seguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="086b9-124">Follow the steps below:</span></span>

1. <span data-ttu-id="086b9-125">Seleziona il Windows **Start.**</span><span class="sxs-lookup"><span data-stu-id="086b9-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="086b9-126">Digitare **PowerShell,** fare clic con il pulsante destro **del mouse Windows PowerShell** e quindi scegliere Esegui come **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="086b9-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="086b9-127">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="086b9-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="086b9-128">Passaggio 3: Eseguire un report</span><span class="sxs-lookup"><span data-stu-id="086b9-128">Step 3: Run a report</span></span>

<span data-ttu-id="086b9-129">Dopo aver installato MCCA, è possibile eseguire MCCA e generare un report.</span><span class="sxs-lookup"><span data-stu-id="086b9-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="086b9-130">Per eseguire un report:</span><span class="sxs-lookup"><span data-stu-id="086b9-130">To run a report:</span></span>

1. <span data-ttu-id="086b9-131">Aprire PowerShell</span><span class="sxs-lookup"><span data-stu-id="086b9-131">Open PowerShell</span></span>
2. <span data-ttu-id="086b9-132">Eseguire il cmdlet:</span><span class="sxs-lookup"><span data-stu-id="086b9-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="086b9-133">Se sei un cliente GCC High, dovrai fornire un parametro di input aggiuntivo per eseguire il report:</span><span class="sxs-lookup"><span data-stu-id="086b9-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="086b9-134">Dopo l'esecuzione di MCCA, esegue un controllo della versione iniziale e richiede le credenziali.</span><span class="sxs-lookup"><span data-stu-id="086b9-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="086b9-135">Al prompt Immettere il nome utente, accedere con l'indirizzo di posta elettronica dell Microsoft 365 account ( visualizzare i ruoli idonei per[la creazione di report).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="086b9-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="086b9-136">Immettere quindi la password al prompt della password.</span><span class="sxs-lookup"><span data-stu-id="086b9-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="086b9-137">La generazione del report richiederà circa 2-5 minuti.</span><span class="sxs-lookup"><span data-stu-id="086b9-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="086b9-138">Al termine, viene aperta una finestra del browser che visualizza il report HTML.</span><span class="sxs-lookup"><span data-stu-id="086b9-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="086b9-139">Ogni volta che esegui lo strumento, ti chiederà le credenziali e genererà un nuovo report.</span><span class="sxs-lookup"><span data-stu-id="086b9-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="086b9-140">Questo report viene archiviato localmente nella directory seguente:</span><span class="sxs-lookup"><span data-stu-id="086b9-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="086b9-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="086b9-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="086b9-142">È possibile accedere ai report generati in precedenza da questa directory.</span><span class="sxs-lookup"><span data-stu-id="086b9-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="086b9-143">Informazioni sul report</span><span class="sxs-lookup"><span data-stu-id="086b9-143">Understanding your report</span></span>

<span data-ttu-id="086b9-144">Il report riflette i dati in base alla data e all'ora in cui è stato generato.</span><span class="sxs-lookup"><span data-stu-id="086b9-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="086b9-145">Nella sezione superiore sono disponibili informazioni dettagliate su quando è stata generata, sul nome dell'organizzazione e sull'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="086b9-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="086b9-146">Report basati sulla georilevazione</span><span class="sxs-lookup"><span data-stu-id="086b9-146">Geolocation-based reporting</span></span>

<span data-ttu-id="086b9-147">La **sezione Nota** mostra che il report è personalizzato in base alla posizione geografica del tenant.</span><span class="sxs-lookup"><span data-stu-id="086b9-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="086b9-148">Consigli elencato nello strumento sarà specifico del proprio paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="086b9-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="086b9-149">La selezione di georilevazione viene utilizzata per valutare i tipi di informazioni riservate (SIT) rilevanti per tale georilevazione e generare un report allineato al proprio paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="086b9-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="086b9-150">Scegliere le georilevazioni in base ai dati presenti nel tenant.</span><span class="sxs-lookup"><span data-stu-id="086b9-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="086b9-151">Per modificare le informazioni sulla posizione del report, è necessario fornire un parametro di input di georilevazione (-Geo).</span><span class="sxs-lookup"><span data-stu-id="086b9-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="086b9-152">È possibile scegliere una o più georilevazioni applicabili al tenant.</span><span class="sxs-lookup"><span data-stu-id="086b9-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="086b9-153">Seguire queste istruzioni per eseguire un report in base a un percorso specifico:</span><span class="sxs-lookup"><span data-stu-id="086b9-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="086b9-154">Aprire PowerShell</span><span class="sxs-lookup"><span data-stu-id="086b9-154">Open PowerShell</span></span>
2. <span data-ttu-id="086b9-155">Per specificare una determinata area geografica, verrà eseguito un cmdlet utilizzando i numeri della tabella seguente che corrispondono al paese o all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="086b9-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="086b9-156">Immettere più numeri separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="086b9-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="086b9-157">Ad esempio, il cmdlet seguente eseguirà un report personalizzato per Asia-Pacific Giappone:</span><span class="sxs-lookup"><span data-stu-id="086b9-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="086b9-158">Input</span><span class="sxs-lookup"><span data-stu-id="086b9-158">Input</span></span> |  <span data-ttu-id="086b9-159">Paese</span><span class="sxs-lookup"><span data-stu-id="086b9-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="086b9-160">1 </span><span class="sxs-lookup"><span data-stu-id="086b9-160">1</span></span> | <span data-ttu-id="086b9-161">Asia-Pacifico</span><span class="sxs-lookup"><span data-stu-id="086b9-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="086b9-162">2 </span><span class="sxs-lookup"><span data-stu-id="086b9-162">2</span></span> | <span data-ttu-id="086b9-163">Australia</span><span class="sxs-lookup"><span data-stu-id="086b9-163">Australia</span></span> |
  | <span data-ttu-id="086b9-164">3 </span><span class="sxs-lookup"><span data-stu-id="086b9-164">3</span></span> | <span data-ttu-id="086b9-165">Canada</span><span class="sxs-lookup"><span data-stu-id="086b9-165">Canada</span></span> |
  | <span data-ttu-id="086b9-166">4 </span><span class="sxs-lookup"><span data-stu-id="086b9-166">4</span></span> | <span data-ttu-id="086b9-167">Europa (Francia esclusa) / Medio Oriente / Africa</span><span class="sxs-lookup"><span data-stu-id="086b9-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="086b9-168">5 </span><span class="sxs-lookup"><span data-stu-id="086b9-168">5</span></span> | <span data-ttu-id="086b9-169">Francia</span><span class="sxs-lookup"><span data-stu-id="086b9-169">France</span></span> |
  | <span data-ttu-id="086b9-170">6 </span><span class="sxs-lookup"><span data-stu-id="086b9-170">6</span></span> | <span data-ttu-id="086b9-171">India</span><span class="sxs-lookup"><span data-stu-id="086b9-171">India</span></span> |
  | <span data-ttu-id="086b9-172">7 </span><span class="sxs-lookup"><span data-stu-id="086b9-172">7</span></span> | <span data-ttu-id="086b9-173">Giappone</span><span class="sxs-lookup"><span data-stu-id="086b9-173">Japan</span></span> |
  | <span data-ttu-id="086b9-174">8 </span><span class="sxs-lookup"><span data-stu-id="086b9-174">8</span></span> | <span data-ttu-id="086b9-175">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="086b9-175">Korea</span></span> |
  | <span data-ttu-id="086b9-176">9 </span><span class="sxs-lookup"><span data-stu-id="086b9-176">9</span></span> | <span data-ttu-id="086b9-177">Nord America (canada escluso)</span><span class="sxs-lookup"><span data-stu-id="086b9-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="086b9-178">10 </span><span class="sxs-lookup"><span data-stu-id="086b9-178">10</span></span> | <span data-ttu-id="086b9-179">Sud America</span><span class="sxs-lookup"><span data-stu-id="086b9-179">South America</span></span> |
  | <span data-ttu-id="086b9-180">11 </span><span class="sxs-lookup"><span data-stu-id="086b9-180">11</span></span> | <span data-ttu-id="086b9-181">Sudafrica</span><span class="sxs-lookup"><span data-stu-id="086b9-181">South Africa</span></span> |
  | <span data-ttu-id="086b9-182">12 </span><span class="sxs-lookup"><span data-stu-id="086b9-182">12</span></span> | <span data-ttu-id="086b9-183">Svizzera</span><span class="sxs-lookup"><span data-stu-id="086b9-183">Switzerland</span></span> |
  | <span data-ttu-id="086b9-184">13 </span><span class="sxs-lookup"><span data-stu-id="086b9-184">13</span></span> | <span data-ttu-id="086b9-185">Emirati Arabi Uniti</span><span class="sxs-lookup"><span data-stu-id="086b9-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="086b9-186">14 </span><span class="sxs-lookup"><span data-stu-id="086b9-186">14</span></span> | <span data-ttu-id="086b9-187">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="086b9-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="086b9-188">Il report includerà sempre i tipi di informazioni sensibili internazionali supportati da MCCA, ad esempio codice SWIFT, numero di carta di credito e così via.</span><span class="sxs-lookup"><span data-stu-id="086b9-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="086b9-189">Report basati sui ruoli</span><span class="sxs-lookup"><span data-stu-id="086b9-189">Role-based reporting</span></span>

<span data-ttu-id="086b9-190">Il report verrà inoltre personalizzato in base al ruolo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="086b9-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="086b9-191">La tabella seguente mostra quali ruoli hanno accesso alle sezioni del report.</span><span class="sxs-lookup"><span data-stu-id="086b9-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="086b9-192">Altri ruoli all'interno dell'organizzazione (non elencati nella tabella seguente) potrebbero non essere in grado di eseguire lo strumento oppure potrebbero eseguire lo strumento e avere accesso limitato alle informazioni nel report finale.</span><span class="sxs-lookup"><span data-stu-id="086b9-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="086b9-193">![MCCA - ruoli](../media/compliance-manager-mcca-roles.png "Ruoli MCCA")</span><span class="sxs-lookup"><span data-stu-id="086b9-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="086b9-194">Eccezioni:</span><span class="sxs-lookup"><span data-stu-id="086b9-194">Exceptions:</span></span>
1. <span data-ttu-id="086b9-195">Gli utenti non saranno in grado di generare report per IP a parte la sezione "Usare IRM per Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="086b9-195">Users won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="086b9-196">Gli utenti potranno generare report per IP oltre alla sezione "Usare IRM per Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="086b9-196">Users will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="086b9-197">Gli utenti saranno in grado di generare report per IP oltre alla sezione "Abilitare la conformità delle comunicazioni in O365".</span><span class="sxs-lookup"><span data-stu-id="086b9-197">Users will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="086b9-198">Gli utenti non saranno in grado di generare report per IP oltre alla sezione "Abilita controllo in Office 365".</span><span class="sxs-lookup"><span data-stu-id="086b9-198">Users won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="086b9-199">Gli utenti saranno in grado di generare report per IP a parte la sezione "Abilita controllo in Office 365".</span><span class="sxs-lookup"><span data-stu-id="086b9-199">Users will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="086b9-200">Sezione Riepilogo soluzioni</span><span class="sxs-lookup"><span data-stu-id="086b9-200">Solutions Summary section</span></span>

<span data-ttu-id="086b9-201">Nella **sezione Riepilogo soluzioni** del report viene fornita una panoramica delle azioni di miglioramento che l'organizzazione può eseguire in Compliance Manager per migliorare la conformità.</span><span class="sxs-lookup"><span data-stu-id="086b9-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="086b9-202">![MCCA - Riepilogo delle soluzioni](../media/compliance-manager-mcca-solutions.png "Schermata di riepilogo delle soluzioni MCCA")</span><span class="sxs-lookup"><span data-stu-id="086b9-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="086b9-203">MCCA valuta le configurazioni correnti in base alle azioni di miglioramento consigliate in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="086b9-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="086b9-204">Tutte le azioni di miglioramento identificate dallo strumento MCCA come necessarie saranno elencate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="086b9-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="086b9-205">Accanto a ogni soluzione Microsoft sono presenti caselle con codice a colori che indicano il numero di elementi che corrispondono alle azioni di miglioramento in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="086b9-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="086b9-206">Le azioni sono suddivise in tre stati di stato:</span><span class="sxs-lookup"><span data-stu-id="086b9-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="086b9-207">**OK**: le azioni che soddisfano le condizioni consigliate e non necessitano di attenzione in questo momento</span><span class="sxs-lookup"><span data-stu-id="086b9-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="086b9-208">**Miglioramento**: azioni che necessitano di attenzione</span><span class="sxs-lookup"><span data-stu-id="086b9-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="086b9-209">**Suggerimento**: azioni che non necessitano di attenzione, ma per le quali è consigliabile utilizzare le procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="086b9-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="086b9-210">Selezionare una casella per visualizzare i miglioramenti e i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="086b9-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="086b9-211">**Elementi con stato Miglioramento**</span><span class="sxs-lookup"><span data-stu-id="086b9-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="086b9-212">Seleziona l'elenco a discesa **accanto** all'etichetta Miglioramento a destra dell'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="086b9-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="086b9-213">Vedrai un breve riepilogo e dettagli sulle impostazioni correnti e sulle azioni di miglioramento consigliate.</span><span class="sxs-lookup"><span data-stu-id="086b9-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="086b9-214">Il riepilogo include collegamenti diretti a Compliance Manager, alla soluzione applicabile nella Centro conformità Microsoft 365 e alla documentazione pertinente.</span><span class="sxs-lookup"><span data-stu-id="086b9-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="086b9-215">Facendo clic sul collegamento Compliance Manager viene visualizzata una visualizzazione filtrata di tutte le azioni di miglioramento all'interno della soluzione non ancora implementate.</span><span class="sxs-lookup"><span data-stu-id="086b9-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="086b9-216">Da qui è possibile visualizzare il numero di punti che è possibile raggiungere per aumentare il punteggio di conformità [e](compliance-score-calculation.md)le valutazioni a cui si applicano e le normative e le certificazioni applicabili.</span><span class="sxs-lookup"><span data-stu-id="086b9-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="086b9-217">Per DLP, è presente un pulsante **Script** di correzione che fornisce uno script di PowerShell pre-generato in base a quanto consigliato.</span><span class="sxs-lookup"><span data-stu-id="086b9-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="086b9-218">È possibile copiarlo e incollarlo direttamente nella console di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="086b9-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="086b9-219">Verrà creato un criterio DLP in modalità test</span><span class="sxs-lookup"><span data-stu-id="086b9-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="086b9-220">**Elementi con stato Consiglio**</span><span class="sxs-lookup"><span data-stu-id="086b9-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="086b9-221">Seleziona l'elenco a discesa accanto **all'etichetta** Raccomandazione a destra dell'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="086b9-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="086b9-222">Verrà visualizzato un riepilogo dell'ambiente di Microsoft 365 dell'organizzazione correlato all'azione di miglioramento, insieme alle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="086b9-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="086b9-223">Risorse</span><span class="sxs-lookup"><span data-stu-id="086b9-223">Resources</span></span>

<span data-ttu-id="086b9-224">Per informazioni più dettagliate sull'installazione, la configurazione e l'utilizzo di MCCA, vedere le istruzioni [README](https://github.com/OfficeDev/MCCA#overview) su GitHub (nessun account GitHub necessario).</span><span class="sxs-lookup"><span data-stu-id="086b9-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="086b9-225">Per ulteriori informazioni su Windows PowerShell, iniziare da [Come usare la documentazione di PowerShell.](/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="086b9-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="086b9-226">Vedere anche [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="086b9-226">See also [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
