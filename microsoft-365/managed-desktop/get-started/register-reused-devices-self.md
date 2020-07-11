---
title: Registrare manualmente i dispositivi già presenti
description: Registrare i dispositivi riutilizzati che potrebbero essere già disponibili in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101486"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="84708-103">Registrare manualmente i dispositivi già presenti</span><span class="sxs-lookup"><span data-stu-id="84708-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="84708-104">In questo argomento vengono illustrati i passaggi da eseguire per riutilizzare i dispositivi già presenti e registrarli in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="84708-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="84708-105">Se si utilizzano dispositivi nuovi di zecca, eseguire i passaggi descritti in [registrare i nuovi dispositivi in Microsoft Managed Desktop](register-devices-self.md) .</span><span class="sxs-lookup"><span data-stu-id="84708-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="84708-106">Il processo per i partner è documentato nei [passaggi per i partner per la registrazione dei dispositivi](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="84708-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="84708-107">Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi che potrebbero essere già presenti (il che richiede che vengano ristampati).</span><span class="sxs-lookup"><span data-stu-id="84708-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="84708-108">È possibile registrare i dispositivi tramite il portale di amministrazione di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="84708-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="84708-109">Preparare la registrazione di dispositivi esistenti</span><span class="sxs-lookup"><span data-stu-id="84708-109">Prepare to register existing devices</span></span>


<span data-ttu-id="84708-110">Per registrare i dispositivi esistenti, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="84708-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="84708-111">Ottenere l'hash hardware per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84708-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="84708-112">Unire i dati hash</span><span class="sxs-lookup"><span data-stu-id="84708-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="84708-113">[Registrare i dispositivi in Microsoft Managed Desktop](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="84708-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="84708-114">Verificare che l'immagine sia corretta.</span><span class="sxs-lookup"><span data-stu-id="84708-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="84708-115">Recapito del dispositivo</span><span class="sxs-lookup"><span data-stu-id="84708-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="84708-116">Ottenere l'hash hardware</span><span class="sxs-lookup"><span data-stu-id="84708-116">Obtain the hardware hash</span></span>

<span data-ttu-id="84708-117">Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware.</span><span class="sxs-lookup"><span data-stu-id="84708-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="84708-118">Sono disponibili quattro opzioni per ottenere queste informazioni dai dispositivi che si stanno già usando:</span><span class="sxs-lookup"><span data-stu-id="84708-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="84708-119">Rivolgersi al fornitore OEM per il file di registrazione Autopilot, che includerà gli hash hardware.</span><span class="sxs-lookup"><span data-stu-id="84708-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="84708-120">Creare un report personalizzato in [Configuration Manager](#configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="84708-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="84708-121">Eseguire uno script di Windows PowerShell, utilizzando [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) su ogni dispositivo, e raccogliere i risultati in un file.</span><span class="sxs-lookup"><span data-stu-id="84708-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="84708-122">Avviare ogni dispositivo--ma non completare l'esperienza di installazione di Windows--e [raccogliere gli hash su un'unità flash rimovibile](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="84708-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="84708-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="84708-123">Configuration Manager</span></span>

<span data-ttu-id="84708-124">È possibile utilizzare Gestione configurazione endpoint Microsoft per raccogliere gli hash hardware dai dispositivi esistenti che si desidera registrare con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="84708-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84708-125">Tutti i dispositivi per i quali si desidera ottenere queste informazioni devono essere in esecuzione Windows 10, versione 1703 o successiva.</span><span class="sxs-lookup"><span data-stu-id="84708-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="84708-126">È inoltre necessario un dispositivo che sia un client di Configuration Manager connesso al sito Gestione configurazione (succursale corrente).</span><span class="sxs-lookup"><span data-stu-id="84708-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="84708-127">È inoltre necessario impostare il ruolo di sistema dei siti di Reporting Point configurato nell'ambiente in cui è abilitato SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="84708-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="84708-128">Se sono stati soddisfatti tutti questi prerequisiti, è possibile raccogliere le informazioni attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="84708-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="84708-129">Nella console di Configuration Manager, selezionare **monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="84708-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="84708-130">Nell'area di lavoro Monitoraggio espandere **report**e quindi selezionare **report**.</span><span class="sxs-lookup"><span data-stu-id="84708-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="84708-131">Nella sezione **Crea** della scheda **Home** selezionare **Crea rapporto** per aprire la creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="84708-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="84708-132">Nella pagina delle **informazioni** , impostare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="84708-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="84708-133">**Nome:** Specificare un nome per il report.</span><span class="sxs-lookup"><span data-stu-id="84708-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="84708-134">**Descrizione:** Specificare una descrizione per il report.</span><span class="sxs-lookup"><span data-stu-id="84708-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="84708-135">**Server:** Visualizza il nome del server di report in cui si sta creando il report.</span><span class="sxs-lookup"><span data-stu-id="84708-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="84708-136">**Percorso:** Selezionare **Sfoglia** per specificare una cartella nella quale si desidera archiviare il report.</span><span class="sxs-lookup"><span data-stu-id="84708-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="84708-137">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="84708-137">Select **Next**.</span></span> 
6. <span data-ttu-id="84708-138">Nella pagina **Riepilogo** , esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="84708-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="84708-139">Selezionare **Previous** per modificare le impostazioni oppure fare clic su **Avanti** per creare il report in Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="84708-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="84708-140">Nella pagina **completamento** , selezionare **Chiudi** per uscire dalla procedura guidata e aprire **Generatore report** per immettere le impostazioni del report.</span><span class="sxs-lookup"><span data-stu-id="84708-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="84708-141">Immettere l'account utente e la password, se richiesto, quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="84708-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="84708-142">Se il generatore di report non è installato nel dispositivo, viene richiesto di installarlo.</span><span class="sxs-lookup"><span data-stu-id="84708-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="84708-143">Selezionare **Esegui per installare Generatore di report**, necessario per modificare e creare report.</span><span class="sxs-lookup"><span data-stu-id="84708-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="84708-144">**In Microsoft Report Builder**fornire l'istruzione SQL per il report e attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="84708-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="84708-145">Nel riquadro a sinistra, selezionare **set**di dati, quindi fare clic con il pulsante destro del mouse per **aggiungere un oggetto DataSet**.</span><span class="sxs-lookup"><span data-stu-id="84708-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="84708-146">Passare alla scheda **query** e quindi immettere il nome come *DataSet0*.</span><span class="sxs-lookup"><span data-stu-id="84708-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="84708-147">Selezionare **utilizza un set di dati incorporato nel report**. Verrà aperto generatore di report.</span><span class="sxs-lookup"><span data-stu-id="84708-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="84708-148">In **Generatore report**selezionare **origine dati:**.</span><span class="sxs-lookup"><span data-stu-id="84708-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="84708-149">Selezionare l'origine dati predefinita, che dovrebbe iniziare con "AutoGen".</span><span class="sxs-lookup"><span data-stu-id="84708-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="84708-150">Scegliere **tipo di query come testo**e quindi immettere la query seguente:</span><span class="sxs-lookup"><span data-stu-id="84708-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="84708-151">Passare alla scheda **campo** , i valori wehre per il **nome del campo** e l' **origine campo** devono essere già inseriti.</span><span class="sxs-lookup"><span data-stu-id="84708-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="84708-152">Se non lo sono, fare clic su **Aggiungi**, quindi selezionare **campo query**.</span><span class="sxs-lookup"><span data-stu-id="84708-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="84708-153">Immettere il **nome del campo** e l' **origine del campo**.</span><span class="sxs-lookup"><span data-stu-id="84708-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="84708-154">Ripetere questa procedura per ognuno di questi valori:</span><span class="sxs-lookup"><span data-stu-id="84708-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="84708-155">Produttore</span><span class="sxs-lookup"><span data-stu-id="84708-155">Manufacturer</span></span> 
    - <span data-ttu-id="84708-156">Modello</span><span class="sxs-lookup"><span data-stu-id="84708-156">Model</span></span> 
    - <span data-ttu-id="84708-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="84708-157">Serial_Number</span></span> 
    - <span data-ttu-id="84708-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="84708-158">HardwareHash</span></span>
7. <span data-ttu-id="84708-159">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="84708-159">Select **OK**.</span></span>

<span data-ttu-id="84708-160">**Successivamente, definire la visualizzazione del report e creare il report** attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="84708-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="84708-161">Selezionare **tabella o matrice**; verrà aperta una nuova procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="84708-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="84708-162">In **Scegli un set di dati**, selezionare **Scegli un set di dati esistente nel rapporto o un set**di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="84708-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="84708-163">Selezionare **DataSet0** (impostazione predefinita) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="84708-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="84708-164">Trascinare il **produttore**, il **modello**e il **numero di serie** nella casella gruppi di **righe** .</span><span class="sxs-lookup"><span data-stu-id="84708-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="84708-165">Trascinare **HardwareHash** nella casella **valori** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="84708-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="84708-166">Cancellare le caselle di controllo per **Mostra i subtotali e i totali** complessivi e i **gruppi Espandi/Comprimi**.</span><span class="sxs-lookup"><span data-stu-id="84708-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="84708-167">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="84708-167">Select **Next**.</span></span>
6. <span data-ttu-id="84708-168">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="84708-168">Select **Finish**.</span></span>
7. <span data-ttu-id="84708-169">Selezionare **Esegui** per eseguire il report.</span><span class="sxs-lookup"><span data-stu-id="84708-169">Select **Run** to run your report.</span></span> <span data-ttu-id="84708-170">Verificare che nel report siano disponibili le informazioni prevedibili.</span><span class="sxs-lookup"><span data-stu-id="84708-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="84708-171">Se necessario, selezionare **progetta** per tornare alla visualizzazione struttura per modificare il report.</span><span class="sxs-lookup"><span data-stu-id="84708-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="84708-172">Fare clic su **Salva** per salvare il report nel server di report.</span><span class="sxs-lookup"><span data-stu-id="84708-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="84708-173">È possibile eseguire il nuovo rapporto nel nodo rapporti nell'area di lavoro di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="84708-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="84708-174">**Infine, esportare il report e utilizzarlo per registrare i dispositivi** attenendosi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="84708-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="84708-175">(È necessario seguire i passaggi 1 e 2 di questa sezione se si è passati dopo i passaggi precedenti):</span><span class="sxs-lookup"><span data-stu-id="84708-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="84708-176">Nella console di Configuration Manager, selezionare **monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="84708-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="84708-177">In **monitoraggio**, espandere **report**e quindi fare clic su **report**.</span><span class="sxs-lookup"><span data-stu-id="84708-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="84708-178">Trovare il report utilizzando il nome creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="84708-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="84708-179">Fare clic con il pulsante destro del mouse su questo report e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="84708-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="84708-180">Nella finestra di dialogo visualizzata, selezionare **Esporta** e quindi fare clic su **Salva come CSV**.</span><span class="sxs-lookup"><span data-stu-id="84708-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="84708-181">Questa versione del report estrae gli hash da tutti i dispositivi Windows 10 a cui comunica Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="84708-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="84708-182">Sarà necessario filtrare i risultati in base ai soli dispositivi che si intende registrare con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="84708-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="84708-183">La query in Configuration Manager non consente l'esecuzione di spazi nei nomi di colonna esportati. Questo è il motivo per cui i passaggi sono stati immessi "Serial_Number" e "HardwareHash".</span><span class="sxs-lookup"><span data-stu-id="84708-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="84708-184">Dopo aver esportato il file CSV, è necessario modificare le intestazioni dei rapporti per leggere il *numero di serie* e l' *hash hardware* come illustrato di seguito prima di procedere con la registrazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="84708-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="84708-185">A questo punto è possibile procedere alla [registrazione dei dispositivi tramite il portale di amministrazione](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="84708-185">Now you can proceed to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="84708-186">Metodo script di PowerShell di Active Directory</span><span class="sxs-lookup"><span data-stu-id="84708-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="84708-187">In un ambiente Active Directory, è possibile utilizzare il `Get-MMDRegistrationInfo` cmdlet di PowerShell per raccogliere in remoto le informazioni dai dispositivi nei gruppi di Active Directory tramite WinRM.</span><span class="sxs-lookup"><span data-stu-id="84708-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="84708-188">È inoltre possibile utilizzare il `Get-AD Computer` cmdlet e ottenere i risultati filtrati per uno specifico nome di modello hardware incluso nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="84708-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="84708-189">A tale scopo, prima di tutto confermare questi prerequisiti e quindi procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="84708-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="84708-190">Gestione remota Windows è abilitata.</span><span class="sxs-lookup"><span data-stu-id="84708-190">WinRM is enabled.</span></span>
- <span data-ttu-id="84708-191">I dispositivi che si desidera registrare sono attivi sulla rete (ovvero non sono disconnessi o disattivati).</span><span class="sxs-lookup"><span data-stu-id="84708-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="84708-192">Verificare di disporre di un parametro di credenziali di dominio che disponga dell'autorizzazione per l'esecuzione remota sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="84708-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="84708-193">Verificare che Windows Firewall consenta l'accesso a WMI.</span><span class="sxs-lookup"><span data-stu-id="84708-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="84708-194">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="84708-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="84708-195">Aprire il pannello di controllo di **Windows Defender Firewall** e selezionare **Consenti un'app o una funzionalità tramite il firewall di Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="84708-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="84708-196">Individuare **Windows Management Instrumentation (WMI)** nell'elenco, abilitare sia per il **privato che**per il pubblico, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="84708-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="84708-197">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="84708-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="84708-198">Eseguire *uno* di questi script:</span><span class="sxs-lookup"><span data-stu-id="84708-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="84708-199">Accedere a tutte le directory in cui possono essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="84708-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="84708-200">Rimuovere le voci per ogni dispositivo da *tutte le* directory, inclusi i servizi di dominio di Windows Server Active Directory e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="84708-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="84708-201">Tenere presente che questa rimozione potrebbe richiedere alcune ore per elaborarla completamente.</span><span class="sxs-lookup"><span data-stu-id="84708-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="84708-202">Servizi di gestione accessi in cui possono essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="84708-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="84708-203">Rimuovere le voci per ogni dispositivo da *tutti i* servizi di gestione, tra cui Microsoft endpoint Configuration Manager, Microsoft Intune e Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="84708-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="84708-204">Tenere presente che questa rimozione potrebbe richiedere alcune ore per elaborarla completamente.</span><span class="sxs-lookup"><span data-stu-id="84708-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="84708-205">A questo punto è possibile procedere alla [registrazione di dispositivi](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="84708-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="84708-206">Metodo script di PowerShell manuale</span><span class="sxs-lookup"><span data-stu-id="84708-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="84708-207">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="84708-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="84708-208">Correre`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="84708-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="84708-209">Correre`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="84708-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="84708-210">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="84708-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="84708-211">Metodo dell'unità flash</span><span class="sxs-lookup"><span data-stu-id="84708-211">Flash drive method</span></span>

1. <span data-ttu-id="84708-212">In un dispositivo diverso da quello che si sta registrando, inserire un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="84708-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="84708-213">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="84708-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="84708-214">Correre`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="84708-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="84708-215">Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione*.</span><span class="sxs-lookup"><span data-stu-id="84708-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="84708-216">Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84708-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="84708-217">Inserire l'unità USB e quindi premere MAIUSC + F10.</span><span class="sxs-lookup"><span data-stu-id="84708-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="84708-218">Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguirlo `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="84708-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="84708-219">Correre`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="84708-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="84708-220">Correre`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="84708-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="84708-221">Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="84708-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="84708-222">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="84708-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="84708-223">Non accendere il dispositivo che si sta registrando di nuovo fino a quando non si è completata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="84708-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="84708-224">Unire i dati hash</span><span class="sxs-lookup"><span data-stu-id="84708-224">Merge hash data</span></span>

<span data-ttu-id="84708-225">Se i dati dell'hash hardware sono stati raccolti tramite i metodi di PowerShell manuale o di unità flash, è necessario che i dati dei file CSV siano combinati in un unico file per completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="84708-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="84708-226">Di seguito è indicato uno script di PowerShell di esempio per semplificare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84708-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="84708-227">Con i dati hash Uniti in un unico file CSV, è ora possibile procedere alla [registrazione dei dispositivi](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="84708-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="84708-228">Registrare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="84708-228">Register devices</span></span>

<span data-ttu-id="84708-229">Il file CSV deve trovarsi in un formato specifico per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="84708-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="84708-230">Se i dati sono stati raccolti nei passaggi precedenti, il file deve essere già nel formato corretto. Se si ottiene il file da un fornitore, potrebbe essere necessario modificare il formato.</span><span class="sxs-lookup"><span data-stu-id="84708-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="84708-231">Per comodità, è possibile scaricare un [modello](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) per questo file CSV.</span><span class="sxs-lookup"><span data-stu-id="84708-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="84708-232">Il file deve includere le **intestazioni di colonna** identiche a quelle del campione (produttore, modello e così via), ma i propri dati per le altre righe.</span><span class="sxs-lookup"><span data-stu-id="84708-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="84708-233">Se si utilizza il modello, aprirlo in uno strumento di modifica del testo, ad esempio Blocco note, e considerare di lasciare tutti i dati solo nella riga 1, immettendo solo i dati nelle righe 2 e seguenti.</span><span class="sxs-lookup"><span data-stu-id="84708-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="84708-234">Se si dimentica di modificare i dati di esempio, la registrazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="84708-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="84708-235">Registrare i dispositivi tramite il portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="84708-235">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="84708-236">Dal [portale di amministrazione](https://aka.ms/mmdportal)di Microsoft Managed Desktop, selezionare **dispositivi** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="84708-236">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="84708-237">Selezionare **+ registra dispositivi**; verrà aperto il volo:</span><span class="sxs-lookup"><span data-stu-id="84708-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="84708-238">[![Fly-in dopo aver selezionato i dispositivi di registrazione, elencare i dispositivi con colonne per gli utenti assegnati, il numero di serie, lo stato, la data dell'ultima visualizzazione e l'età](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="84708-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Purtroppo questo non è vero. È possibile rimuovere questa nota, lasciandola adesso fino a quando non avremo la possibilità di chattare.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="84708-240">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="84708-240">Follow these steps:</span></span>

1. <span data-ttu-id="84708-241">In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="84708-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="84708-242">Facoltativamente, è possibile aggiungere un **ID ordine** o un **ID acquisto** per i propri scopi di verifica.</span><span class="sxs-lookup"><span data-stu-id="84708-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="84708-243">Non sono presenti requisiti di formato per questi valori.</span><span class="sxs-lookup"><span data-stu-id="84708-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="84708-244">Selezionare **registra dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="84708-244">Select **Register devices**.</span></span> <span data-ttu-id="84708-245">Il sistema aggiungerà i dispositivi all'elenco di dispositivi sul Blade dei **dispositivi**, contrassegnati come **registrazione in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="84708-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="84708-246">La registrazione richiede in genere meno di 10 minuti e, quando il dispositivo verrà visualizzato come **pronto per il significato dell'utente** , è pronto e in attesa che l'utente finale inizi a utilizzare.</span><span class="sxs-lookup"><span data-stu-id="84708-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="84708-247">È possibile monitorare lo stato di registrazione dei dispositivi nella pagina principale di **Microsoft Managed Desktop-Devices** .</span><span class="sxs-lookup"><span data-stu-id="84708-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="84708-248">Gli stati possibili segnalati includono:</span><span class="sxs-lookup"><span data-stu-id="84708-248">Possible states reported there include:</span></span>

| <span data-ttu-id="84708-249">Stato</span><span class="sxs-lookup"><span data-stu-id="84708-249">State</span></span> | <span data-ttu-id="84708-250">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84708-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="84708-251">Registrazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="84708-251">Registration pending</span></span> | <span data-ttu-id="84708-252">La registrazione non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="84708-252">Registration is not done yet.</span></span> <span data-ttu-id="84708-253">Controllare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="84708-253">Check back later.</span></span> |
| <span data-ttu-id="84708-254">Registrazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="84708-254">Registration failed</span></span> | <span data-ttu-id="84708-255">La registrazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="84708-255">Registration could not be completed.</span></span> <span data-ttu-id="84708-256">Per ulteriori informazioni, vedere [risoluzione dei problemi relativi alla registrazione del dispositivo](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="84708-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="84708-257">Pronto per l'utente</span><span class="sxs-lookup"><span data-stu-id="84708-257">Ready for user</span></span> | <span data-ttu-id="84708-258">La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="84708-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="84708-259">Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi.</span><span class="sxs-lookup"><span data-stu-id="84708-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="84708-260">Attivazione</span><span class="sxs-lookup"><span data-stu-id="84708-260">Active</span></span> | <span data-ttu-id="84708-261">Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant.</span><span class="sxs-lookup"><span data-stu-id="84708-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="84708-262">Questo indica anche che stanno usando regolarmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84708-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="84708-263">Inattivo</span><span class="sxs-lookup"><span data-stu-id="84708-263">Inactive</span></span> | <span data-ttu-id="84708-264">Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant.</span><span class="sxs-lookup"><span data-stu-id="84708-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="84708-265">Tuttavia, non hanno utilizzato il dispositivo di recente (negli ultimi 7 giorni).</span><span class="sxs-lookup"><span data-stu-id="84708-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="84708-266">Risoluzione dei problemi relativi alla registrazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="84708-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="84708-267">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="84708-267">Error message</span></span> | <span data-ttu-id="84708-268">Dettagli</span><span class="sxs-lookup"><span data-stu-id="84708-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="84708-269">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="84708-269">Device not found</span></span> | <span data-ttu-id="84708-270">Non è stato possibile registrare il dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato.</span><span class="sxs-lookup"><span data-stu-id="84708-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="84708-271">Confermare questi valori con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84708-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="84708-272">Hash hardware non valido</span><span class="sxs-lookup"><span data-stu-id="84708-272">Hardware hash not valid</span></span> | <span data-ttu-id="84708-273">L'hash hardware fornito per il dispositivo non è stato formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="84708-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="84708-274">Fare doppio check sull'hash hardware e quindi inviare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="84708-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="84708-275">Dispositivo già registrato</span><span class="sxs-lookup"><span data-stu-id="84708-275">Device already registered</span></span> | <span data-ttu-id="84708-276">Questo dispositivo è già registrato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84708-276">This device is already registered to your organization.</span></span> <span data-ttu-id="84708-277">Non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="84708-277">No further action required.</span></span> |
| <span data-ttu-id="84708-278">Dispositivo rivendicato da un'altra organizzazione</span><span class="sxs-lookup"><span data-stu-id="84708-278">Device claimed by another organization</span></span> | <span data-ttu-id="84708-279">Questo dispositivo è già stato rivendicato da un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84708-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="84708-280">Controllare con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84708-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="84708-281">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="84708-281">Unexpected error</span></span> | <span data-ttu-id="84708-282">La richiesta non è stata elaborata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="84708-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="84708-283">Contattare il supporto tecnico e fornire l'ID richiesta:<requestId></span><span class="sxs-lookup"><span data-stu-id="84708-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="84708-284">Controllare l'immagine</span><span class="sxs-lookup"><span data-stu-id="84708-284">Check the image</span></span>

<span data-ttu-id="84708-285">Se il dispositivo proviene da un fornitore di partner di Microsoft Managed Desktop, è necessario che l'immagine sia corretta.</span><span class="sxs-lookup"><span data-stu-id="84708-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="84708-286">Se si preferisce, è anche possibile applicare l'immagine da soli.</span><span class="sxs-lookup"><span data-stu-id="84708-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="84708-287">Per iniziare, contattare il rappresentante Microsoft che si sta utilizzando e fornirà la posizione e i passaggi per l'applicazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="84708-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="84708-288">Recapito del dispositivo</span><span class="sxs-lookup"><span data-stu-id="84708-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84708-289">Prima di distribuire il dispositivo all'utente, verificare di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per l'utente.</span><span class="sxs-lookup"><span data-stu-id="84708-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="84708-290">Se vengono applicate tutte le licenze, è possibile [ottenere gli utenti pronti per l'utilizzo dei dispositivi](get-started-devices.md)e quindi l'utente può avviare il dispositivo e procedere con l'esperienza di installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="84708-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









