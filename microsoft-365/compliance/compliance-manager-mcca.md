---
title: Analizzatore configurazione di conformità Microsoft per Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
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
ms.openlocfilehash: 41315dd072e089bd61767181b17dffd5fba88281
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423427"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="41e48-103">Analizzatore configurazione di conformità Microsoft per Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41e48-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="41e48-104">**In questo articolo:** Informazioni su come installare ed eseguire lo strumento Microsoft Compliance Configure Analyzer per iniziare rapidamente a usare Microsoft Compliance Manger.</span><span class="sxs-lookup"><span data-stu-id="41e48-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="41e48-105">Panoramica di Microsoft Compliance Configuration Analyzer (MCCA) (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41e48-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="41e48-106">Microsoft Compliance Configuration Analyzer (MCCA) è uno strumento di anteprima che consente di iniziare a usare [Microsoft Compliance Manager.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="41e48-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="41e48-107">MCCA è un'utilità basata su PowerShell che recupera le configurazioni correnti dell'organizzazione e le convalida in base alle procedure consigliate di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41e48-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="41e48-108">Queste procedure consigliate si basano su un insieme di controlli che includono normative e standard chiave per la protezione dei dati e la governance dei dati.</span><span class="sxs-lookup"><span data-stu-id="41e48-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="41e48-109">MCCA consente di vedere rapidamente quali azioni di miglioramento in Compliance Manger si applicano all'ambiente Microsoft 365 corrente.</span><span class="sxs-lookup"><span data-stu-id="41e48-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="41e48-110">Ogni azione identificata da MCCA ti offrirà consigli per l'implementazione, con collegamenti diretti a Compliance Manager e alla soluzione applicabile per avviare l'azione correttiva.</span><span class="sxs-lookup"><span data-stu-id="41e48-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="41e48-111">Una risorsa aggiuntiva per comprendere MCCA è visitare le istruzioni [README su GitHub.](https://github.com/OfficeDev/MCCA#overview)</span><span class="sxs-lookup"><span data-stu-id="41e48-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="41e48-112">In questa pagina vengono fornite informazioni dettagliate sui prerequisiti e vengono fornite istruzioni di installazione complete.</span><span class="sxs-lookup"><span data-stu-id="41e48-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="41e48-113">Non è necessario un account GitHub per accedere a questa pagina.</span><span class="sxs-lookup"><span data-stu-id="41e48-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="41e48-114">**Disponibilità:** MCCA è disponibile per tutte le organizzazioni con licenze di Office 365 e Microsoft 365 e clienti della US Government Community (GCC) Moderate e GCC High, con piani in corso per espandere il servizio ai clienti DOD.</span><span class="sxs-lookup"><span data-stu-id="41e48-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate and GCC High customers, with plans underway to expand service to DOD customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="41e48-115">Installare MCCA ed eseguire un report</span><span class="sxs-lookup"><span data-stu-id="41e48-115">Install MCCA and run a report</span></span>

<span data-ttu-id="41e48-116">Puoi installare lo strumento MCCA usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41e48-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="41e48-117">Dopo aver scaricato e installato lo strumento, non è necessario ripetere questi passaggi per eseguire i report.</span><span class="sxs-lookup"><span data-stu-id="41e48-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="41e48-118">Ogni volta che apri MCCA, ti chiederà le credenziali di accesso e genererà un nuovo report aggiornato.</span><span class="sxs-lookup"><span data-stu-id="41e48-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="41e48-119">Passaggio 1: installare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41e48-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="41e48-120">Per iniziare, è necessario il modulo PowerShell di Exchange Online (v2.0.3 o versione successiva) disponibile nella raccolta PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41e48-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="41e48-121">[Ottenere le istruzioni di installazione.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)</span><span class="sxs-lookup"><span data-stu-id="41e48-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="41e48-122">Passaggio 2: installare MCCA</span><span class="sxs-lookup"><span data-stu-id="41e48-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="41e48-123">Per installare MCCA, iniziare con PowerShell in modalità amministratore.</span><span class="sxs-lookup"><span data-stu-id="41e48-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="41e48-124">Seguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="41e48-124">Follow the steps below:</span></span>

1. <span data-ttu-id="41e48-125">Seleziona il pulsante **Start di** Windows.</span><span class="sxs-lookup"><span data-stu-id="41e48-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="41e48-126">Digitare **PowerShell,** fare clic con il pulsante destro **del Windows PowerShell** e quindi scegliere Esegui come **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="41e48-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="41e48-127">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="41e48-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="41e48-128">Passaggio 3: Eseguire un report</span><span class="sxs-lookup"><span data-stu-id="41e48-128">Step 3: Run a report</span></span>

<span data-ttu-id="41e48-129">Dopo aver installato MCCA, è possibile eseguire MCCA e generare un report.</span><span class="sxs-lookup"><span data-stu-id="41e48-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="41e48-130">Per eseguire un report:</span><span class="sxs-lookup"><span data-stu-id="41e48-130">To run a report:</span></span>

1. <span data-ttu-id="41e48-131">Aprire PowerShell</span><span class="sxs-lookup"><span data-stu-id="41e48-131">Open PowerShell</span></span>
2. <span data-ttu-id="41e48-132">Eseguire il cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41e48-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
   <span data-ttu-id="41e48-133">Se sei un cliente GCC High, dovrai fornire un parametro di input aggiuntivo per eseguire il report:</span><span class="sxs-lookup"><span data-stu-id="41e48-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="41e48-134">Dopo l'esecuzione di MCCA, esegue un controllo della versione iniziale e richiede le credenziali.</span><span class="sxs-lookup"><span data-stu-id="41e48-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="41e48-135">Al prompt Input the user name, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span><span class="sxs-lookup"><span data-stu-id="41e48-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="41e48-136">Immettere quindi la password al prompt della password.</span><span class="sxs-lookup"><span data-stu-id="41e48-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="41e48-137">La generazione del report richiederà circa 2-5 minuti.</span><span class="sxs-lookup"><span data-stu-id="41e48-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="41e48-138">Al termine, viene visualizzata una finestra del browser in cui viene visualizzato il report HTML.</span><span class="sxs-lookup"><span data-stu-id="41e48-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="41e48-139">Ogni volta che esegui lo strumento, ti chiederà le credenziali e genererà un nuovo report.</span><span class="sxs-lookup"><span data-stu-id="41e48-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="41e48-140">Questo report viene archiviato localmente nella directory seguente:</span><span class="sxs-lookup"><span data-stu-id="41e48-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="41e48-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="41e48-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="41e48-142">Da questa directory è possibile accedere ai report generati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41e48-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="41e48-143">Informazioni sul report</span><span class="sxs-lookup"><span data-stu-id="41e48-143">Understanding your report</span></span>

<span data-ttu-id="41e48-144">Il report riflette i dati in base alla data e all'ora in cui è stato generato.</span><span class="sxs-lookup"><span data-stu-id="41e48-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="41e48-145">Nella sezione superiore sono disponibili informazioni dettagliate su quando è stata generata, sul nome dell'organizzazione e sull'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="41e48-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="41e48-146">Report basati sulla georilevazione</span><span class="sxs-lookup"><span data-stu-id="41e48-146">Geolocation-based reporting</span></span>

<span data-ttu-id="41e48-147">La **sezione** Nota mostra che il report è personalizzato in base alla posizione geografica del tenant.</span><span class="sxs-lookup"><span data-stu-id="41e48-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="41e48-148">Gli elementi consigliati elencati nello strumento saranno specifici del proprio paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="41e48-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="41e48-149">La selezione della georilevazione viene usata per valutare i tipi di informazioni sensibili (SIT) rilevanti per tale georilevazione e generare un report allineato al proprio paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="41e48-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="41e48-150">Scegliere le georilevazioni in base ai dati presenti nel tenant.</span><span class="sxs-lookup"><span data-stu-id="41e48-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="41e48-151">Per modificare le informazioni sulla posizione del report, è necessario fornire un parametro di input di georilevazione (-Geo).</span><span class="sxs-lookup"><span data-stu-id="41e48-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="41e48-152">È possibile scegliere una o più georilevazioni applicabili per il tenant.</span><span class="sxs-lookup"><span data-stu-id="41e48-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="41e48-153">Seguire queste istruzioni per eseguire un report in base a un percorso specifico:</span><span class="sxs-lookup"><span data-stu-id="41e48-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="41e48-154">Aprire PowerShell</span><span class="sxs-lookup"><span data-stu-id="41e48-154">Open PowerShell</span></span>
2. <span data-ttu-id="41e48-155">Per specificare una determinata area geografica, eseguire un cmdlet utilizzando i numeri della tabella seguente corrispondenti al paese o all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="41e48-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="41e48-156">Immettere più numeri separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="41e48-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="41e48-157">Ad esempio, il cmdlet seguente eseguirà un report personalizzato per Asia-Pacific Giappone:</span><span class="sxs-lookup"><span data-stu-id="41e48-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="41e48-158">Input</span><span class="sxs-lookup"><span data-stu-id="41e48-158">Input</span></span> |  <span data-ttu-id="41e48-159">Paese</span><span class="sxs-lookup"><span data-stu-id="41e48-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="41e48-160">1 </span><span class="sxs-lookup"><span data-stu-id="41e48-160">1</span></span> | <span data-ttu-id="41e48-161">Asia-Pacifico</span><span class="sxs-lookup"><span data-stu-id="41e48-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="41e48-162">2 </span><span class="sxs-lookup"><span data-stu-id="41e48-162">2</span></span> | <span data-ttu-id="41e48-163">Australia</span><span class="sxs-lookup"><span data-stu-id="41e48-163">Australia</span></span> |
  | <span data-ttu-id="41e48-164">3 </span><span class="sxs-lookup"><span data-stu-id="41e48-164">3</span></span> | <span data-ttu-id="41e48-165">Canada</span><span class="sxs-lookup"><span data-stu-id="41e48-165">Canada</span></span> |
  | <span data-ttu-id="41e48-166">4 </span><span class="sxs-lookup"><span data-stu-id="41e48-166">4</span></span> | <span data-ttu-id="41e48-167">Europa (francia esclusa) / Medio Oriente / Africa</span><span class="sxs-lookup"><span data-stu-id="41e48-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="41e48-168">5 </span><span class="sxs-lookup"><span data-stu-id="41e48-168">5</span></span> | <span data-ttu-id="41e48-169">Francia</span><span class="sxs-lookup"><span data-stu-id="41e48-169">France</span></span> |
  | <span data-ttu-id="41e48-170">6 </span><span class="sxs-lookup"><span data-stu-id="41e48-170">6</span></span> | <span data-ttu-id="41e48-171">India</span><span class="sxs-lookup"><span data-stu-id="41e48-171">India</span></span> |
  | <span data-ttu-id="41e48-172">7 </span><span class="sxs-lookup"><span data-stu-id="41e48-172">7</span></span> | <span data-ttu-id="41e48-173">Giappone</span><span class="sxs-lookup"><span data-stu-id="41e48-173">Japan</span></span> |
  | <span data-ttu-id="41e48-174">8 </span><span class="sxs-lookup"><span data-stu-id="41e48-174">8</span></span> | <span data-ttu-id="41e48-175">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="41e48-175">Korea</span></span> |
  | <span data-ttu-id="41e48-176">9 </span><span class="sxs-lookup"><span data-stu-id="41e48-176">9</span></span> | <span data-ttu-id="41e48-177">Nord America (canada escluso)</span><span class="sxs-lookup"><span data-stu-id="41e48-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="41e48-178">10  </span><span class="sxs-lookup"><span data-stu-id="41e48-178">10</span></span> | <span data-ttu-id="41e48-179">Sud America</span><span class="sxs-lookup"><span data-stu-id="41e48-179">South America</span></span> |
  | <span data-ttu-id="41e48-180">11 </span><span class="sxs-lookup"><span data-stu-id="41e48-180">11</span></span> | <span data-ttu-id="41e48-181">Sudafrica</span><span class="sxs-lookup"><span data-stu-id="41e48-181">South Africa</span></span> |
  | <span data-ttu-id="41e48-182">12 </span><span class="sxs-lookup"><span data-stu-id="41e48-182">12</span></span> | <span data-ttu-id="41e48-183">Svizzera</span><span class="sxs-lookup"><span data-stu-id="41e48-183">Switzerland</span></span> |
  | <span data-ttu-id="41e48-184">13 </span><span class="sxs-lookup"><span data-stu-id="41e48-184">13</span></span> | <span data-ttu-id="41e48-185">Emirati Arabi Uniti</span><span class="sxs-lookup"><span data-stu-id="41e48-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="41e48-186">14 </span><span class="sxs-lookup"><span data-stu-id="41e48-186">14</span></span> | <span data-ttu-id="41e48-187">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="41e48-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="41e48-188">Il report includerà sempre i tipi di informazioni sensibili internazionali supportati da MCCA, ad esempio codice SWIFT, numero di carta di credito e così via.</span><span class="sxs-lookup"><span data-stu-id="41e48-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="41e48-189">Creazione di report basati sui ruoli</span><span class="sxs-lookup"><span data-stu-id="41e48-189">Role-based reporting</span></span>

<span data-ttu-id="41e48-190">Il report verrà inoltre personalizzato in base al ruolo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="41e48-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="41e48-191">La tabella seguente mostra quali ruoli hanno accesso a quali sezioni del report.</span><span class="sxs-lookup"><span data-stu-id="41e48-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="41e48-192">Altri ruoli all'interno dell'organizzazione (non elencati nella tabella seguente) potrebbero non essere in grado di eseguire lo strumento oppure potrebbero eseguire lo strumento e avere accesso limitato alle informazioni nel report finale.</span><span class="sxs-lookup"><span data-stu-id="41e48-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="41e48-193">![MCCA - ruoli](../media/compliance-manager-mcca-roles.png "Ruoli MCCA")</span><span class="sxs-lookup"><span data-stu-id="41e48-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="41e48-194">Eccezioni:</span><span class="sxs-lookup"><span data-stu-id="41e48-194">Exceptions:</span></span>
1. <span data-ttu-id="41e48-195">L'utente non sarà in grado di generare un rapporto per IP a parte la sezione "Utilizzare IRM per Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="41e48-195">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="41e48-196">L'utente sarà in grado di generare un rapporto per IP a parte la sezione "Utilizzare IRM per Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="41e48-196">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="41e48-197">L'utente sarà in grado di generare un report per IP a parte la sezione "Abilitare la conformità delle comunicazioni in O365".</span><span class="sxs-lookup"><span data-stu-id="41e48-197">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="41e48-198">L'utente non sarà in grado di generare report per IP a parte la sezione "Abilitare il controllo in Office 365".</span><span class="sxs-lookup"><span data-stu-id="41e48-198">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="41e48-199">L'utente sarà in grado di generare report per IP a parte la sezione "Abilitare il controllo in Office 365".</span><span class="sxs-lookup"><span data-stu-id="41e48-199">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="41e48-200">Sezione Riepilogo soluzioni</span><span class="sxs-lookup"><span data-stu-id="41e48-200">Solutions Summary section</span></span>

<span data-ttu-id="41e48-201">Nella **sezione Riepilogo soluzioni** del report viene fornita una panoramica delle azioni di miglioramento che l'organizzazione può eseguire in Compliance Manager per migliorare la conformità.</span><span class="sxs-lookup"><span data-stu-id="41e48-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="41e48-202">![MCCA - Riepilogo delle soluzioni](../media/compliance-manager-mcca-solutions.png "Schermata di riepilogo delle soluzioni MCCA")</span><span class="sxs-lookup"><span data-stu-id="41e48-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="41e48-203">MCCA valuta le configurazioni correnti in base alle azioni di miglioramento consigliate in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="41e48-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="41e48-204">Tutte le azioni di miglioramento identificate dallo strumento MCCA che necessitano attenzione verranno elencate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="41e48-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="41e48-205">Accanto a ogni soluzione Microsoft sono presenti caselle con codice a colori che indicano il numero di elementi che corrispondono alle azioni di miglioramento in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="41e48-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="41e48-206">Le azioni sono suddivise in tre stati di stato:</span><span class="sxs-lookup"><span data-stu-id="41e48-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="41e48-207">**OK:** le azioni che soddisfano le condizioni consigliate e non necessitano attenzione in questo momento</span><span class="sxs-lookup"><span data-stu-id="41e48-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="41e48-208">**Miglioramento:** azioni che necessitano attenzione</span><span class="sxs-lookup"><span data-stu-id="41e48-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="41e48-209">**Raccomandazione:** azioni che non necessitano di attenzione, ma per le quali si consigliano le procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="41e48-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="41e48-210">Selezionare una casella per visualizzare miglioramenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="41e48-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="41e48-211">**Elementi con stato Miglioramento**</span><span class="sxs-lookup"><span data-stu-id="41e48-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="41e48-212">Selezionare l'elenco a discesa accanto **all'etichetta Miglioramento** a destra dell'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="41e48-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="41e48-213">Vedrai un breve riepilogo e dettagli sulle impostazioni correnti e sulle azioni di miglioramento consigliate.</span><span class="sxs-lookup"><span data-stu-id="41e48-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="41e48-214">Il riepilogo include collegamenti diretti a Compliance Manager, la soluzione applicabile nel Centro conformità Microsoft 365 e la documentazione pertinente.</span><span class="sxs-lookup"><span data-stu-id="41e48-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="41e48-215">Facendo clic sul collegamento di Compliance Manager si visualizza una visualizzazione filtrata di tutte le azioni di miglioramento all'interno della soluzione non ancora implementate.</span><span class="sxs-lookup"><span data-stu-id="41e48-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="41e48-216">Da qui è possibile vedere il numero di punti che è possibile raggiungere per aumentare il punteggio di conformità [e](compliance-score-calculation.md)le valutazioni a cui si applicano e le normative e le certificazioni applicabili.</span><span class="sxs-lookup"><span data-stu-id="41e48-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="41e48-217">Per DLP, è  presente un pulsante Script di correzione che fornisce uno script di PowerShell pre-generato in base a quanto consigliato.</span><span class="sxs-lookup"><span data-stu-id="41e48-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="41e48-218">È possibile copiarlo e incollarlo direttamente nella console di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41e48-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="41e48-219">Verrà creato un criterio DLP in modalità test</span><span class="sxs-lookup"><span data-stu-id="41e48-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="41e48-220">**Elementi con stato Elementi consigliati**</span><span class="sxs-lookup"><span data-stu-id="41e48-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="41e48-221">Selezionare l'elenco a discesa accanto **all'etichetta** Elementi consigliati a destra dell'azione di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="41e48-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="41e48-222">Verrà visualizzato un riepilogo dell'ambiente Microsoft 365 corrente dell'organizzazione relativo all'azione di miglioramento, insieme alle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="41e48-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="41e48-223">Risorse</span><span class="sxs-lookup"><span data-stu-id="41e48-223">Resources</span></span>

<span data-ttu-id="41e48-224">Per informazioni più dettagliate sull'installazione, la configurazione e l'uso di MCCA, vedi le istruzioni README su [GitHub](https://github.com/OfficeDev/MCCA#overview) (non è necessario alcun account GitHub).</span><span class="sxs-lookup"><span data-stu-id="41e48-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="41e48-225">Per altre informazioni su Windows PowerShell, inizia dalla documentazione [di PowerShell.](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="41e48-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="41e48-226">Vedere anche [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="41e48-226">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
