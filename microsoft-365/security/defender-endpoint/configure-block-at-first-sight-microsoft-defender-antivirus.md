---
title: Abilitare il blocco al primo rilevamento per rilevare il malware in pochi secondi
description: Attivare la funzionalità blocco al primo rilevamento per rilevare e bloccare il malware in pochi secondi.
keywords: scan, BAFS, malware, first seen, first sight, cloud, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 837b7899368e69b274323125c97169bbe4f823b7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691569"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="0d99f-104">Attivare il blocco al primo sguardo</span><span class="sxs-lookup"><span data-stu-id="0d99f-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0d99f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0d99f-105">**Applies to:**</span></span>

- [<span data-ttu-id="0d99f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0d99f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0d99f-107">Blocca al primo rilevamento consente di rilevare e bloccare nuovi malware in pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="0d99f-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="0d99f-108">Questa protezione è abilitata per impostazione predefinita quando sono abilitate determinate impostazioni dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="0d99f-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="0d99f-109">Queste impostazioni includono la protezione recapitata nel cloud, un timeout di invio di esempio specificato (ad esempio 50 secondi) e un livello di blocco dei file elevato.</span><span class="sxs-lookup"><span data-stu-id="0d99f-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="0d99f-110">Nella maggior parte delle organizzazioni aziendali, queste impostazioni sono abilitate per impostazione predefinita con le distribuzioni di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0d99f-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="0d99f-111">È possibile [specificare per quanto tempo deve essere impedito l'esecuzione](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) di un file durante l'analisi del file da parte del servizio di protezione basato su cloud.</span><span class="sxs-lookup"><span data-stu-id="0d99f-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="0d99f-112">Inoltre, è [possibile personalizzare il messaggio visualizzato sui desktop](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) degli utenti quando un file viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="0d99f-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="0d99f-113">È possibile modificare il nome della società, le informazioni di contatto e l'URL del messaggio.</span><span class="sxs-lookup"><span data-stu-id="0d99f-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="0d99f-114">Visita il sito Web demo di Microsoft Defender for Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che le funzionalità funzionino e vedere come funzionano.</span><span class="sxs-lookup"><span data-stu-id="0d99f-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="0d99f-115">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="0d99f-115">How it works</span></span>

<span data-ttu-id="0d99f-116">Quando Microsoft Defender Antivirus rileva un file sospetto ma non rilevato, interroga il back-end di protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="0d99f-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="0d99f-117">Il back-end cloud applica l'euristica, l'apprendimento automatico e l'analisi automatica del file per determinare se i file sono dannosi o meno una minaccia.</span><span class="sxs-lookup"><span data-stu-id="0d99f-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="0d99f-118">Microsoft Defender Antivirus usa più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, intelligente e in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="0d99f-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="0d99f-119">Per altre informazioni, vedi questo blog: Informazioni sulle tecnologie avanzate alla base di [Microsoft Defender for Endpoint next-generation protection.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="0d99f-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="0d99f-120">![Elenco dei motori Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="0d99f-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="0d99f-121">In Windows 10, versione 1803 o successiva, il blocco al primo sguardo può bloccare i file eseguibili non portabili (ad esempio JS, VBS o macro) e i file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="0d99f-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="0d99f-122">Block at first sight usa solo il back-end di protezione cloud per i file eseguibili e i file eseguibili non portatili scaricati da Internet o originati dall'area Internet.</span><span class="sxs-lookup"><span data-stu-id="0d99f-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="0d99f-123">Un valore hash del file exe viene controllato tramite il back-end cloud per determinare se il file è un file non rilevato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0d99f-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="0d99f-124">Se il back-end cloud non è in grado di effettuare una determinazione, Microsoft Defender Antivirus blocca il file e carica una copia nel cloud.</span><span class="sxs-lookup"><span data-stu-id="0d99f-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="0d99f-125">Il cloud esegue un'analisi aggiuntiva per raggiungere una determinazione prima di consentire l'esecuzione del file o bloccarlo in tutti gli incontri futuri, a seconda che il file sia dannoso o sicuro.</span><span class="sxs-lookup"><span data-stu-id="0d99f-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="0d99f-126">In molti casi, questo processo può ridurre il tempo di risposta per il nuovo malware da ore a secondi.</span><span class="sxs-lookup"><span data-stu-id="0d99f-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="0d99f-127">Attivare il blocco al primo sguardo con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0d99f-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="0d99f-128">Microsoft Intune fa ora parte di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="0d99f-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="0d99f-129">Nell'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), accedere a Profili **di** configurazione  >  **dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="0d99f-130">Seleziona o crea un profilo usando il **tipo di profilo** Restrizioni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d99f-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="0d99f-131">In Impostazioni **di configurazione per** il profilo Restrizioni dispositivo imposta o conferma le impostazioni seguenti in Microsoft Defender **Antivirus:**</span><span class="sxs-lookup"><span data-stu-id="0d99f-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="0d99f-132">**Protezione recapitata nel cloud**: abilitata</span><span class="sxs-lookup"><span data-stu-id="0d99f-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="0d99f-133">**Livello di blocco dei file**: Alto</span><span class="sxs-lookup"><span data-stu-id="0d99f-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="0d99f-134">**Estensione temporale per l'analisi dei file dal cloud**: 50</span><span class="sxs-lookup"><span data-stu-id="0d99f-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="0d99f-135">**Chiedi conferma agli utenti prima dell'invio** dell'esempio: invia tutti i dati senza chiedere conferma</span><span class="sxs-lookup"><span data-stu-id="0d99f-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Configurazione di Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="0d99f-137">Salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0d99f-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="0d99f-138">Se si imposta il livello di blocco dei file **su Alto,** viene applicato un livello elevato di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="0d99f-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="0d99f-139">Nell'improbabile caso in cui il blocco dei file causa un rilevamento falso positivo dei file legittimi, è possibile [ripristinare i file in quarantena.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0d99f-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="0d99f-140">Per altre informazioni sulla configurazione delle restrizioni per i dispositivi Microsoft Defender Antivirus in Intune, vedi [Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="0d99f-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="0d99f-141">Per un elenco delle restrizioni per i dispositivi Microsoft Defender Antivirus in Intune, vedi Restrizioni dei dispositivi per le impostazioni di [Windows 10 (e più nuove) in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="0d99f-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="0d99f-142">Attivare il blocco al primo sguardo con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0d99f-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="0d99f-143">Se stai cercando Microsoft Endpoint Configuration Manager, ora fa parte di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="0d99f-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="0d99f-144">In Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), passare a Endpoint **security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="0d99f-145">Seleziona un criterio esistente o crea un nuovo criterio usando il tipo di profilo **Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="0d99f-146">Impostare o confermare le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d99f-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="0d99f-147">**Attivare la protezione basata sul cloud**: Sì</span><span class="sxs-lookup"><span data-stu-id="0d99f-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="0d99f-148">**Livello di protezione fornito dal cloud**: Alto</span><span class="sxs-lookup"><span data-stu-id="0d99f-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="0d99f-149">**Timeout esteso defender cloud in secondi**: 50</span><span class="sxs-lookup"><span data-stu-id="0d99f-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloccare le impostazioni al primo avvistamento in Endpoint Manager":::

4. <span data-ttu-id="0d99f-151">Applicare il profilo Microsoft Defender Antivirus a un gruppo, ad esempio Tutti gli **utenti** **,** Tutti i dispositivi o Tutti gli utenti e **i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="0d99f-152">Attivare il blocco al primo sguardo con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d99f-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="0d99f-153">Ti consigliamo di usare Intune o Microsoft Endpoint Manager per attivare il blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="0d99f-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="0d99f-154">Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="0d99f-155">Usando **l'Editor Gestione Criteri di gruppo** vai a Configurazione **computer**  >  **Modelli amministrativi** Componenti di  >  **Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="0d99f-156">Nella sezione MAPPE fare doppio clic su Configura la funzionalità **"Blocca** al primo avvistamento" e impostarla su **Abilitato** e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0d99f-157">**L'impostazione su Chiedi sempre conferma (0)** riduce lo stato di protezione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d99f-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="0d99f-158">Se si **imposta su Non inviare mai (2),** il blocco al primo sguardo non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="0d99f-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="0d99f-159">Nella sezione MAPPE fare doppio clic su **Invia esempi di file** quando è necessaria un'ulteriore analisi e impostarlo su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="0d99f-160">In **Invia esempi di file quando sono necessarie ulteriori analisi** selezionare Invia tutti **gli** esempi e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="0d99f-161">Se sono state modificate impostazioni, ridistribuire l'oggetto Criteri di gruppo nella rete per garantire che tutti gli endpoint siano coperti.</span><span class="sxs-lookup"><span data-stu-id="0d99f-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="0d99f-162">Verificare che il blocco al primo avvistamento sia abilitato nei singoli client</span><span class="sxs-lookup"><span data-stu-id="0d99f-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="0d99f-163">Puoi verificare che il blocco al primo sguardo sia abilitato nei singoli client usando le impostazioni di sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="0d99f-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="0d99f-164">Il blocco al primo rilevamento viene abilitato automaticamente, purché la protezione consegnata dal **cloud** e l'invio automatico **di** campioni siano entrambi attivati.</span><span class="sxs-lookup"><span data-stu-id="0d99f-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="0d99f-165">Apri l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="0d99f-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="0d99f-166">Selezionare **Protezione da &** virus e quindi, in **Impostazioni** protezione da & virus, selezionare Gestisci **impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="0d99f-168">Verificare che **la protezione con distribuzione cloud e** **l'invio automatico** di esempi siano entrambi attivati.</span><span class="sxs-lookup"><span data-stu-id="0d99f-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="0d99f-169">Se le impostazioni dei prerequisiti vengono configurate e distribuite tramite Criteri di gruppo, le impostazioni descritte in questa sezione saranno disattivate e non saranno disponibili per l'utilizzo nei singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="0d99f-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="0d99f-170">Le modifiche apportate tramite un oggetto Criteri di gruppo devono prima essere distribuite a singoli endpoint prima che l'impostazione venga aggiornata in Impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="0d99f-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="0d99f-171">Convalidare il blocco al primo avvistamento funziona</span><span class="sxs-lookup"><span data-stu-id="0d99f-171">Validate block at first sight is working</span></span>

<span data-ttu-id="0d99f-172">Per verificare che la funzionalità funzioni, seguire le indicazioni in Convalidare le connessioni [tra la rete e il cloud.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="0d99f-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="0d99f-173">Disattivare il blocco al primo sguardo</span><span class="sxs-lookup"><span data-stu-id="0d99f-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="0d99f-174">Disattivando il blocco al primo sguardo, si riduce lo stato di protezione dei dispositivi e della rete.</span><span class="sxs-lookup"><span data-stu-id="0d99f-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="0d99f-175">È possibile scegliere di disabilitare il blocco al primo sguardo se si desidera mantenere le impostazioni dei prerequisiti senza usare effettivamente la protezione blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="0d99f-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="0d99f-176">È possibile disattivare temporaneamente il blocco al primo sguardo se si verificano problemi di latenza o si desidera testare l'impatto della funzionalità sulla rete.</span><span class="sxs-lookup"><span data-stu-id="0d99f-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="0d99f-177">Tuttavia, non è consigliabile disabilitare definitivamente la protezione del blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="0d99f-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="0d99f-178">Disattivare il blocco al primo sguardo con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0d99f-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="0d99f-179">Vai all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e accedi.</span><span class="sxs-lookup"><span data-stu-id="0d99f-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="0d99f-180">Vai a **Endpoint security**  >  **Antivirus** e quindi seleziona i criteri di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0d99f-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="0d99f-181">In **Gestisci** scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="0d99f-182">Accanto a **Impostazioni di configurazione** scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="0d99f-183">Modificare una o più delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d99f-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="0d99f-184">Impostare **Attiva protezione recapitata nel cloud** su **No** o Non **configurato**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="0d99f-185">Impostare **il livello di protezione fornito dal cloud** su Non **configurato**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="0d99f-186">Deselezionare **la casella Timeout esteso defender cloud in** secondi.</span><span class="sxs-lookup"><span data-stu-id="0d99f-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="0d99f-187">Rivedere e salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0d99f-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="0d99f-188">Disattivare il blocco al primo sguardo con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d99f-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="0d99f-189">Nel computer di gestione di Criteri di gruppo aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="0d99f-190">Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="0d99f-191">Espandere l'albero tramite **i componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="0d99f-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="0d99f-192">Fai doppio clic **su Configura la funzionalità "Blocca** al primo avvistamento" e imposta l'opzione su **Disabilitato.**</span><span class="sxs-lookup"><span data-stu-id="0d99f-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d99f-193">La disabilitazione del blocco al primo avvistamento non disabilita o modifica i criteri di gruppo dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="0d99f-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d99f-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d99f-194">See also</span></span>

- [<span data-ttu-id="0d99f-195">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="0d99f-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="0d99f-196">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="0d99f-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)