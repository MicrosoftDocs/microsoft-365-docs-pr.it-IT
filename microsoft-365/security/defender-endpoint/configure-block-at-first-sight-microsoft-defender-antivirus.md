---
title: Abilitare il blocco al primo rilevamento per rilevare il malware in pochi secondi
description: Attivare la funzionalità blocco al primo rilevamento per rilevare e bloccare il malware in pochi secondi.
keywords: analisi, blocco al primo rilevamento, malware, primo rilevamento, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079204"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="324d7-104">Abilitare il blocco al primo rilevamento</span><span class="sxs-lookup"><span data-stu-id="324d7-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="324d7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="324d7-105">**Applies to:**</span></span>

- [<span data-ttu-id="324d7-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="324d7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="324d7-107">In questo articolo viene descritta una funzionalità antivirus/antimalware nota come "blocco al primo sguardo" e viene descritto come abilitare il blocco al primo sguardo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="324d7-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="324d7-108">Questo articolo è destinato agli amministratori aziendali e ai professionisti IT che gestiscono le impostazioni di sicurezza per le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="324d7-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="324d7-109">Se non sei un amministratore enteprise o un professionista IT, ma hai domande sul blocco a prima vista, vedi Non è un amministratore aziendale o [un professionista IT?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="324d7-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="324d7-110">Che cos'è "blocco al primo sguardo"?</span><span class="sxs-lookup"><span data-stu-id="324d7-110">What is "block at first sight"?</span></span>

<span data-ttu-id="324d7-111">Block at first sight è una funzionalità di protezione dalle minacce di nuova generazione che rileva nuovo malware e lo blocca in pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="324d7-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="324d7-112">Il blocco al primo sguardo è abilitato quando sono abilitate determinate impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="324d7-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="324d7-113">Queste impostazioni includono:</span><span class="sxs-lookup"><span data-stu-id="324d7-113">These settings include:</span></span>

- <span data-ttu-id="324d7-114">Protezione basata sul cloud;</span><span class="sxs-lookup"><span data-stu-id="324d7-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="324d7-115">Un timeout di invio di esempio specificato (ad esempio 50 secondi); e</span><span class="sxs-lookup"><span data-stu-id="324d7-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="324d7-116">Livello di blocco dei file elevato.</span><span class="sxs-lookup"><span data-stu-id="324d7-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="324d7-117">Nella maggior parte delle organizzazioni aziendali, le impostazioni necessarie per abilitare il blocco al primo sguardo sono configurate con le distribuzioni di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="324d7-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="324d7-118">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="324d7-118">How it works</span></span>

<span data-ttu-id="324d7-119">Quando Microsoft Defender Antivirus rileva un file sospetto ma non rilevato, interroga il back-end di protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="324d7-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="324d7-120">Il back-end cloud applica l'euristica, l'apprendimento automatico e l'analisi automatica del file per determinare se i file sono dannosi o meno una minaccia.</span><span class="sxs-lookup"><span data-stu-id="324d7-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="324d7-121">Microsoft Defender Antivirus usa più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, intelligente e in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="324d7-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Elenco dei motori Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="324d7-123">Per altre informazioni, vedi questo blog: Informazioni sulle tecnologie avanzate alla base di [Microsoft Defender for Endpoint next-generation protection.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="324d7-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="324d7-124">Alcune informazioni sul blocco a prima vista</span><span class="sxs-lookup"><span data-stu-id="324d7-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="324d7-125">In Windows 10, versione 1803 o successiva, il blocco al primo sguardo può bloccare i file eseguibili non portabili (ad esempio JS, VBS o macro) e i file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="324d7-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="324d7-126">Block at first sight usa solo il back-end di protezione cloud per i file eseguibili e i file eseguibili non portatili scaricati da Internet o originati dall'area Internet.</span><span class="sxs-lookup"><span data-stu-id="324d7-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="324d7-127">Un valore hash del file exe viene controllato tramite il back-end cloud per determinare se il file è un file non rilevato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="324d7-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="324d7-128">Se il back-end cloud non è in grado di effettuare una determinazione, Microsoft Defender Antivirus blocca il file e carica una copia nel cloud.</span><span class="sxs-lookup"><span data-stu-id="324d7-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="324d7-129">Il cloud esegue un'analisi più approfondita per raggiungere una determinazione prima di consentire l'esecuzione del file o bloccarlo in tutti gli incontri futuri, a seconda che il file sia dannoso o meno una minaccia.</span><span class="sxs-lookup"><span data-stu-id="324d7-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="324d7-130">In molti casi, questo processo può ridurre il tempo di risposta per il nuovo malware da ore a secondi.</span><span class="sxs-lookup"><span data-stu-id="324d7-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="324d7-131">È possibile [specificare per quanto tempo deve essere impedito l'esecuzione](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) di un file durante l'analisi del file da parte del servizio di protezione basato su cloud.</span><span class="sxs-lookup"><span data-stu-id="324d7-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="324d7-132">Inoltre, è [possibile personalizzare il messaggio visualizzato sui desktop](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) degli utenti quando un file viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="324d7-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="324d7-133">È possibile modificare il nome della società, le informazioni di contatto e l'URL del messaggio.</span><span class="sxs-lookup"><span data-stu-id="324d7-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="324d7-134">Attivare il blocco al primo sguardo con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="324d7-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="324d7-135">Microsoft Intune fa ora parte di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="324d7-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="324d7-136">Nell'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), accedere a Profili **di** configurazione  >  **dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="324d7-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="324d7-137">Seleziona o crea un profilo usando il **tipo di profilo** Restrizioni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="324d7-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="324d7-138">In Impostazioni **di configurazione per** il profilo Restrizioni dispositivo imposta o conferma le impostazioni seguenti in Microsoft Defender **Antivirus:**</span><span class="sxs-lookup"><span data-stu-id="324d7-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="324d7-139">**Protezione recapitata nel cloud**: abilitata</span><span class="sxs-lookup"><span data-stu-id="324d7-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="324d7-140">**Livello di blocco dei file**: Alto</span><span class="sxs-lookup"><span data-stu-id="324d7-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="324d7-141">**Estensione temporale per l'analisi dei file dal cloud**: 50</span><span class="sxs-lookup"><span data-stu-id="324d7-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="324d7-142">**Chiedi conferma agli utenti prima dell'invio** dell'esempio: invia tutti i dati senza chiedere conferma</span><span class="sxs-lookup"><span data-stu-id="324d7-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Configurazione di Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="324d7-144">Salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="324d7-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="324d7-145">Se si imposta il livello di blocco dei file **su Alto,** viene applicato un livello elevato di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="324d7-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="324d7-146">Nell'improbabile caso in cui il blocco dei file causa un rilevamento falso positivo dei file legittimi, il team delle operazioni di sicurezza può [ripristinare i file in quarantena.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="324d7-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="324d7-147">Per altre informazioni sulla configurazione delle restrizioni per i dispositivi Microsoft Defender Antivirus in Intune, vedi [Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="324d7-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="324d7-148">Per un elenco delle restrizioni per i dispositivi Microsoft Defender Antivirus in Intune, vedi Restrizioni dei dispositivi per le impostazioni di [Windows 10 (e più nuove) in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="324d7-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="324d7-149">Attivare il blocco al primo sguardo con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="324d7-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="324d7-150">Se stai cercando Microsoft Endpoint Configuration Manager, ora fa parte di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="324d7-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="324d7-151">In Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), passare a Endpoint **security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="324d7-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="324d7-152">Seleziona un criterio esistente o crea un nuovo criterio usando il tipo di profilo **Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="324d7-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="324d7-153">Impostare o confermare le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="324d7-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="324d7-154">**Attivare la protezione basata sul cloud**: Sì</span><span class="sxs-lookup"><span data-stu-id="324d7-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="324d7-155">**Livello di protezione fornito dal cloud**: Alto</span><span class="sxs-lookup"><span data-stu-id="324d7-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="324d7-156">**Timeout esteso defender cloud in secondi**: 50</span><span class="sxs-lookup"><span data-stu-id="324d7-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloccare le impostazioni al primo avvistamento in Endpoint Manager":::

4. <span data-ttu-id="324d7-158">Applicare il profilo Microsoft Defender Antivirus a un gruppo, ad esempio Tutti gli **utenti** **,** Tutti i dispositivi o Tutti gli utenti e **i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="324d7-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="324d7-159">Attivare il blocco al primo sguardo con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="324d7-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="324d7-160">Ti consigliamo di usare Intune o Microsoft Endpoint Manager per attivare il blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="324d7-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="324d7-161">Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="324d7-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="324d7-162">Usando **l'Editor Gestione Criteri di gruppo** vai a Configurazione **computer**  >  **Modelli amministrativi** Componenti di  >  **Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="324d7-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="324d7-163">Nella sezione MAPPE fare doppio clic su Configura la funzionalità **"Blocca** al primo avvistamento" e impostarla su **Abilitato** e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="324d7-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="324d7-164">**L'impostazione su Chiedi sempre conferma (0)** riduce lo stato di protezione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="324d7-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="324d7-165">Se si **imposta su Non inviare mai (2),** il blocco al primo sguardo non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="324d7-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="324d7-166">Nella sezione MAPPE fare doppio clic su **Invia esempi di file** quando è necessaria un'ulteriore analisi e impostarlo su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="324d7-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="324d7-167">In **Invia esempi di file quando è necessaria un'ulteriore analisi** selezionare Invia tutti **i** campioni e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="324d7-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="324d7-168">Ridistribuire l'oggetto Criteri di gruppo nella rete come in genere.</span><span class="sxs-lookup"><span data-stu-id="324d7-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="324d7-169">Verificare che il blocco al primo avvistamento sia abilitato nei singoli dispositivi client</span><span class="sxs-lookup"><span data-stu-id="324d7-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="324d7-170">Puoi verificare che il blocco al primo sguardo sia abilitato nei singoli dispositivi client usando l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="324d7-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="324d7-171">Il blocco al primo rilevamento viene abilitato automaticamente, purché la protezione consegnata dal **cloud** e l'invio automatico **di** campioni siano entrambi attivati.</span><span class="sxs-lookup"><span data-stu-id="324d7-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="324d7-172">Apri l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="324d7-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="324d7-173">Selezionare **Protezione da &** virus e quindi, in **Impostazioni** protezione da & virus, selezionare Gestisci **impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="324d7-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="324d7-175">Verificare che **la protezione con distribuzione cloud e** **l'invio automatico** di esempi siano entrambi attivati.</span><span class="sxs-lookup"><span data-stu-id="324d7-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="324d7-176">Se le impostazioni dei prerequisiti vengono configurate e distribuite tramite Criteri di gruppo, le impostazioni descritte in questa sezione saranno disattivate e non saranno disponibili per l'utilizzo nei singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="324d7-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="324d7-177">Le modifiche apportate tramite un oggetto Criteri di gruppo devono prima essere distribuite a singoli endpoint prima che l'impostazione venga aggiornata in Impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="324d7-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="324d7-178">Convalidare il blocco al primo avvistamento funziona</span><span class="sxs-lookup"><span data-stu-id="324d7-178">Validate block at first sight is working</span></span>

<span data-ttu-id="324d7-179">Per verificare che la funzionalità funzioni, seguire le indicazioni in Convalidare le connessioni [tra la rete e il cloud.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="324d7-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="324d7-180">Disattivare il blocco al primo sguardo</span><span class="sxs-lookup"><span data-stu-id="324d7-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="324d7-181">Disattivando il blocco al primo sguardo, si riduce lo stato di protezione dei dispositivi e della rete.</span><span class="sxs-lookup"><span data-stu-id="324d7-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="324d7-182">È possibile scegliere di disabilitare il blocco al primo sguardo se si desidera mantenere le impostazioni dei prerequisiti senza usare effettivamente la protezione blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="324d7-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="324d7-183">Potresti disattivare temporaneamente il blocco al primo sguardo per vedere in che modo questa funzionalità influisce sulla rete.</span><span class="sxs-lookup"><span data-stu-id="324d7-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="324d7-184">Tuttavia, non è consigliabile disabilitare definitivamente la protezione del blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="324d7-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="324d7-185">Disattivare il blocco al primo sguardo con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="324d7-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="324d7-186">Vai all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e accedi.</span><span class="sxs-lookup"><span data-stu-id="324d7-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="324d7-187">Vai a **Endpoint security**  >  **Antivirus** e quindi seleziona i criteri di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="324d7-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="324d7-188">In **Gestisci** scegliere **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="324d7-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="324d7-189">Accanto a **Impostazioni di configurazione** scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="324d7-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="324d7-190">Modificare una o più delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="324d7-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="324d7-191">Impostare **Attiva protezione recapitata nel cloud** su **No** o Non **configurato**.</span><span class="sxs-lookup"><span data-stu-id="324d7-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="324d7-192">Impostare **il livello di protezione fornito dal cloud** su Non **configurato**.</span><span class="sxs-lookup"><span data-stu-id="324d7-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="324d7-193">Deselezionare la casella di controllo **Defender Cloud Extended Timeout in secondi.**</span><span class="sxs-lookup"><span data-stu-id="324d7-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="324d7-194">Rivedere e salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="324d7-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="324d7-195">Disattivare il blocco al primo sguardo con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="324d7-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="324d7-196">Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="324d7-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="324d7-197">Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="324d7-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="324d7-198">Espandere l'albero tramite **i componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="324d7-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="324d7-199">Fai doppio clic **su Configura la funzionalità "Blocca** al primo avvistamento" e imposta l'opzione su **Disabilitato.**</span><span class="sxs-lookup"><span data-stu-id="324d7-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="324d7-200">La disabilitazione del blocco al primo avvistamento non disabilita o modifica i criteri di gruppo dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="324d7-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="324d7-201">Non sei un amministratore aziendale o un professionista IT?</span><span class="sxs-lookup"><span data-stu-id="324d7-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="324d7-202">Se non sei un amministratore aziendale o un professionista IT, ma hai domande sul blocco a prima vista, questa sezione fa per te.</span><span class="sxs-lookup"><span data-stu-id="324d7-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="324d7-203">Blocca al primo rilevamento è una funzionalità di protezione dalle minacce che rileva e blocca il malware in pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="324d7-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="324d7-204">Anche se non esiste un'impostazione specifica denominata "Blocca al primo sguardo", la funzionalità viene abilitata quando determinate impostazioni sono configurate nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="324d7-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="324d7-205">Come gestire il blocco al primo sguardo sul tuo dispositivo</span><span class="sxs-lookup"><span data-stu-id="324d7-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="324d7-206">Se hai un dispositivo personale non gestito da un'organizzazione, potresti chiederti come attivare o disattivare il blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="324d7-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="324d7-207">Puoi usare l'app Sicurezza di Windows per gestire il blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="324d7-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="324d7-208">Nel computer Windows 10 apri l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="324d7-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="324d7-209">Selezionare **Protezione da & virus**.</span><span class="sxs-lookup"><span data-stu-id="324d7-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="324d7-210">In **Impostazioni protezione da & virus** selezionare Gestisci **impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="324d7-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="324d7-211">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="324d7-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="324d7-212">Per abilitare il blocco al primo rilevamento, assicurati che sia la protezione consegnata dal **cloud** che l'invio automatico **di** campioni siano entrambi attivati.</span><span class="sxs-lookup"><span data-stu-id="324d7-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="324d7-213">Per disabilitare il blocco al primo rilevamento, disattiva **Protezione recapitata dal cloud** o Invio automatico di **campioni.**</span><span class="sxs-lookup"><span data-stu-id="324d7-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="324d7-214">La disattivazione del blocco al primo sguardo riduce il livello di protezione per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="324d7-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="324d7-215">Non è consigliabile disabilitare definitivamente il blocco al primo sguardo.</span><span class="sxs-lookup"><span data-stu-id="324d7-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="324d7-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="324d7-216">See also</span></span>

- [<span data-ttu-id="324d7-217">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="324d7-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="324d7-218">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="324d7-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="324d7-219">Protezione di Windows</span><span class="sxs-lookup"><span data-stu-id="324d7-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)