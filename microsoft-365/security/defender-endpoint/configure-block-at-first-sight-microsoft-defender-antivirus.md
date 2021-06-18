---
title: Abilitare il blocco al primo rilevamento per rilevare il malware in pochi secondi
description: Attivare la funzionalità di blocco al primo rilevamento per rilevare e bloccare il malware entro pochi secondi.
keywords: analisi, blocco al primo rilevamento, malware, primo rilevamebto, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007400"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="b6920-104">Abilitare il blocco al primo rilevamento</span><span class="sxs-lookup"><span data-stu-id="b6920-104">Turn on block at first sight</span></span>

<span data-ttu-id="b6920-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b6920-105">**Applies to:**</span></span>

- [<span data-ttu-id="b6920-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b6920-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b6920-107">Questo articolo descrive una funzionalità antivirus/antimalware nota come blocco al primo rilevamento e descrive come abilitarla per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6920-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="b6920-108">Questo articolo è destinato agli amministratori aziendali e ai professionisti IT che gestiscono le impostazioni di sicurezza per le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="b6920-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="b6920-109">Se non si è un amministratore aziendale o un professionista IT, ma si hanno domande sul blocco al primo rilevamento, vedere la sezione [Non si è un amministratore aziendale o un professionista IT?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="b6920-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="b6920-110">Cos'è il blocco al primo rilevamento?</span><span class="sxs-lookup"><span data-stu-id="b6920-110">What is "block at first sight"?</span></span>

<span data-ttu-id="b6920-111">Il blocco al primo rilevamento è una funzionalità di protezione dalle minacce di nuova generazione, che rileva il nuovo malware e lo blocca entro pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="b6920-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="b6920-112">Il blocco al primo rilevamento è abilitato quando sono abilitate determinate impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6920-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="b6920-113">Queste impostazioni includono:</span><span class="sxs-lookup"><span data-stu-id="b6920-113">These settings include:</span></span>

- <span data-ttu-id="b6920-114">Protezione fornita dal cloud;</span><span class="sxs-lookup"><span data-stu-id="b6920-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="b6920-115">Un timeout di invio del campione specificato (ad esempio 50 secondi); e</span><span class="sxs-lookup"><span data-stu-id="b6920-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="b6920-116">Un livello di livello di blocco dei file alto.</span><span class="sxs-lookup"><span data-stu-id="b6920-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="b6920-117">Nella maggior parte delle organizzazioni aziendali, le impostazioni necessarie per abilitare il blocco al primo rilevamento sono configurate con le distribuzioni di Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b6920-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="b6920-118">Come funziona</span><span class="sxs-lookup"><span data-stu-id="b6920-118">How it works</span></span>

<span data-ttu-id="b6920-119">Quando Antivirus Microsoft Defender incontra un file sospetto, ma non rilevato, interroga il back-end per la protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="b6920-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="b6920-120">Il back-end cloud applica l'euristica, l'apprendimento automatico e l'analisi automatica del file per determinare se i file sono dannosi o se non si tratta di una minaccia.</span><span class="sxs-lookup"><span data-stu-id="b6920-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="b6920-121">Antivirus Microsoft Defender usa più tecnologie di rilevamento e prevenzione per offrire una protezione accurata, in tempo reale e intelligente.</span><span class="sxs-lookup"><span data-stu-id="b6920-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Elenco dei motori antivirus di Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="b6920-123">Per altre informazioni, vedere [ (Blog) Informazioni sulle tecnologie avanzate al centro della protezione di Microsoft Defender per endpoint di nuova generazione](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="b6920-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="b6920-124">Alcune informazioni da conoscere sul blocco al primo rilevamento</span><span class="sxs-lookup"><span data-stu-id="b6920-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="b6920-125">In Windows 10 versione 1803 e successive, il blocco al primo rilevamento può ora bloccare i file eseguibili non di tipo PE, ad esempio JS, VBS o macro, nonché i file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="b6920-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="b6920-126">Il blocco al primo rilevamento usa solo il back-end per la protezione cloud per i file eseguibili e i file eseguibili non di tipo PE scaricati da Internet o che provengono dall'area Internet.</span><span class="sxs-lookup"><span data-stu-id="b6920-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="b6920-127">Tramite il back-end cloud viene controllato un valore hash del file .exe, per determinare se si tratta di un file non rilevato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b6920-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="b6920-128">Se il back-end cloud non è in grado di eseguire questa operazione, Antivirus Microsoft Defender blocca il file e carica una copia nel cloud.</span><span class="sxs-lookup"><span data-stu-id="b6920-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="b6920-129">Il cloud effettua ulteriori analisi per raggiungere una decisione prima di consentire l'esecuzione o bloccare il file in tutti i futuri incontri, a seconda che sia ritenuto dannoso o sicuro.</span><span class="sxs-lookup"><span data-stu-id="b6920-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="b6920-130">In molti casi questo processo può ridurre il tempo di risposta per il nuovo malware da ore a secondi.</span><span class="sxs-lookup"><span data-stu-id="b6920-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="b6920-131">È possibile [specificare per quanto tempo deve essere impedita l'esecuzione del file](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) mentre il servizio di protezione basato sul cloud lo analizza.</span><span class="sxs-lookup"><span data-stu-id="b6920-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="b6920-132">Inoltre, si può [personalizzare il messaggio visualizzato sui desktop degli utenti](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) quando viene bloccato un file.</span><span class="sxs-lookup"><span data-stu-id="b6920-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="b6920-133">È possibile modificare il nome della società, le informazioni di contatto e l'URL del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6920-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="b6920-134">Attivare il blocco al primo rilevamento con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b6920-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="b6920-135">Microsoft Intune ora fa parte di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="b6920-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="b6920-136">Nell'interfaccia di amministrazione di Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) passare a **Dispositivi** > **Profili di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="b6920-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="b6920-137">Selezionare o creare un profilo usando il tipo di profilo **Limitazioni del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b6920-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="b6920-138">Nelle **Impostazioni di configurazione** del profilo Limitazioni del dispositivo impostare o confermare le impostazioni seguenti in **Antivirus Microsoft Defender**:</span><span class="sxs-lookup"><span data-stu-id="b6920-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="b6920-139">**Protezione fornita dal cloud**: abilitata</span><span class="sxs-lookup"><span data-stu-id="b6920-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="b6920-140">**Livello di blocco file**: alto</span><span class="sxs-lookup"><span data-stu-id="b6920-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="b6920-141">**Estensioni di tempo per l'analisi di file da parte del cloud**: 50</span><span class="sxs-lookup"><span data-stu-id="b6920-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="b6920-142">**Richiedi conferma all'utente prima dell'invio di campioni**: Invia tutti i dati senza chiedere conferma</span><span class="sxs-lookup"><span data-stu-id="b6920-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Blocco di configurazione di Intune al primo rilevamento":::

4. <span data-ttu-id="b6920-144">Salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b6920-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="b6920-145">Impostando il livello di blocco dei file su **Alto**, si applica un livello di rilevamento elevato.</span><span class="sxs-lookup"><span data-stu-id="b6920-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="b6920-146">Nel caso improbabile che il blocco dei file causi erroneamente il rilevamento di file legittimi, il team delle operazioni di sicurezza può [ripristinare i file in quarantena](./restore-quarantined-files-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="b6920-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="b6920-147">Per altre informazioni sulla configurazione delle limitazioni per i dispositivi di Antivirus Microsoft Defender in Intune, vedere [Configurare le impostazioni relative alle restrizioni dei dispositivi in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="b6920-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="b6920-148">Per un elenco delle limitazioni dei dispositivi di Antivirus Microsoft Defender in Intune, vedere [Impostazioni dei dispositivi Windows 10 (e versioni successive) per consentire o limitare l'uso delle funzionalità tramite Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="b6920-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="b6920-149">Abilitare il blocco al primo rilevamento con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b6920-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="b6920-150">Se si sta cercando Microsoft Endpoint Configuration Manager, ora fa parte di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="b6920-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="b6920-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) passare a **Sicurezza degli endpoint** > **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="b6920-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="b6920-152">Selezionare un criterio esistente o crearne uno nuovo usando il tipo di profilo **Antivirus Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="b6920-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="b6920-153">Impostare o confermare le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6920-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="b6920-154">**Attiva la protezione fornita dal cloud**: Sì</span><span class="sxs-lookup"><span data-stu-id="b6920-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="b6920-155">**Livello di protezione fornita dal cloud**: Alto</span><span class="sxs-lookup"><span data-stu-id="b6920-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="b6920-156">**Defender - Timeout esteso per il cloud in secondi**: 50</span><span class="sxs-lookup"><span data-stu-id="b6920-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Impostazioni di blocco al primo rilevamento in Endpoint Manager":::

4. <span data-ttu-id="b6920-158">Applicare il profilo Antivirus Microsoft Defender a un gruppo, ad esempio **Tutti gli utenti**, **Tutti i dispositivi** o **Tutti gli utenti e i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="b6920-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="b6920-159">Abilitare il blocco al primo rilevamento con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="b6920-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="b6920-160">È consigliabile usare Intune o Microsoft Endpoint Manager per abilitare il blocco al primo rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b6920-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="b6920-161">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo da configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b6920-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="b6920-162">Usando l'**Editor Gestione Criteri di gruppo** passare a **Configurazione computer** > **Modelli amministrativi** > **Componenti di Windows** > **Antivirus Microsoft Defender** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="b6920-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="b6920-163">Nella sezione MAPS fare doppio clic su **Configura la funzionalità 'Blocco al primo rilevamento'** e impostarla su **Abilitato**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6920-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b6920-164">Impostando **Richiedi sempre conferma (0)** verrà ridotto il livello di protezione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6920-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="b6920-165">Impostando **Non inviare mai (2)**, il blocco al primo rilevamento non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="b6920-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="b6920-166">Nella sezione MAPS fare doppio clic su **Invia campioni di file se sono necessarie ulteriori analisi** e impostarlo su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="b6920-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="b6920-167">In **Invia campioni di file se sono necessarie ulteriori analisi** selezionare **Invia tutti i campioni** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6920-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="b6920-168">Ridistribuire l'oggetto Criteri di gruppo nella rete nel modo consueto.</span><span class="sxs-lookup"><span data-stu-id="b6920-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="b6920-169">Confermare l'abilitazione della funzionalità di blocco al primo rilevamento in singoli dispositivi client</span><span class="sxs-lookup"><span data-stu-id="b6920-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="b6920-170">È possibile verificare che il blocco al primo rilevamento sia abilitato nei singoli dispositivi client usando l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6920-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="b6920-171">Il blocco al primo rilevamento viene abilitato automaticamente purché siano attivate le opzioni **Protezione fornita dal cloud** e **Invio automatico di file di esempio**.</span><span class="sxs-lookup"><span data-stu-id="b6920-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="b6920-172">Aprire l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6920-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="b6920-173">Selezionare **Protezione da virus e minacce**, quindi in **Impostazioni di Protezione da virus e minacce** selezionare **Gestisci impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b6920-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Screenshot dell'etichetta Impostazioni di Protezione da virus e minacce nell'app Sicurezza di Windows":::

3. <span data-ttu-id="b6920-175">Verificare che le opzioni **Protezione fornita dal cloud** e **Invio automatico di file di esempio** siano entrambe abilitate.</span><span class="sxs-lookup"><span data-stu-id="b6920-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="b6920-176">Se le impostazioni dei prerequisiti vengono configurate e distribuite tramite Criteri di gruppo, le impostazioni descritte in questa sezione non saranno disponibili per l'uso nei singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6920-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="b6920-177">Le modifiche apportate tramite un oggetto Criteri di gruppo devono essere distribuite nei singoli endpoint prima che l'impostazione venga aggiornata nelle impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6920-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="b6920-178">Verificare che il blocco al primo rilevamento funzioni</span><span class="sxs-lookup"><span data-stu-id="b6920-178">Validate block at first sight is working</span></span>

<span data-ttu-id="b6920-179">Per verificare che la funzionalità sia attivata correttamente, scaricare il file di esempio [Blocco al primo rilevamento](https://demo.wd.microsoft.com/Page/BAFS).</span><span class="sxs-lookup"><span data-stu-id="b6920-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="b6920-180">Per scaricare il file è necessario un account in Azure AD a cui sia assegnato il ruolo Amministratore della sicurezza o Amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b6920-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="b6920-181">Per verificare che la protezione abilitata per il cloud, seguire le istruzioni in [Convalidare le connessioni tra la rete e il cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="b6920-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="b6920-182">Disabilitare il blocco al primo rilevamento</span><span class="sxs-lookup"><span data-stu-id="b6920-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="b6920-183">Disabilitando il blocco al primo rilevamento si ridurrà lo stato di protezione dei dispositivi e della rete.</span><span class="sxs-lookup"><span data-stu-id="b6920-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="b6920-184">Si può scegliere di disabilitare il blocco al primo rilevamento se si vogliono mantenere le impostazioni dei prerequisiti senza usare la protezione del blocco al primo rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b6920-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="b6920-185">È possibile disabilitare temporaneamente il blocco al primo rilevamento per vedere in che modo questa funzionalità influisce sulla rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="b6920-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="b6920-186">Tuttavia, non è consigliabile disabilitare la protezione del blocco al primo rilevamento in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="b6920-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="b6920-187">Disabilitare il blocco al primo rilevamento con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b6920-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="b6920-188">Passare all'interfaccia di amministrazione di Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e accedere.</span><span class="sxs-lookup"><span data-stu-id="b6920-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="b6920-189">Passare a **Sicurezza endpoint** > **Antivirus** e quindi selezionare il criterio di Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b6920-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="b6920-190">In **Gestisci** scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b6920-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="b6920-191">Accanto a **Impostazioni di configurazione** scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b6920-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="b6920-192">Modificare una o più delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6920-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="b6920-193">Impostare **Attiva la protezione fornita dal cloud** su **No** o **Non configurato**.</span><span class="sxs-lookup"><span data-stu-id="b6920-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="b6920-194">Impostare **Livello di protezione fornita dal cloud** su **Non configurato**.</span><span class="sxs-lookup"><span data-stu-id="b6920-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="b6920-195">Deselezionare la casella di controllo **Defender - Timeout esteso per il cloud in secondi**.</span><span class="sxs-lookup"><span data-stu-id="b6920-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="b6920-196">Rivedere e salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b6920-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="b6920-197">Disabilitare il blocco al primo rilevamento con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="b6920-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="b6920-198">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo da configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b6920-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="b6920-199">Usando l **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="b6920-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="b6920-200">Espandere l'albero fino a visualizzare **Componenti di Windows** > **Antivirus Microsoft Defender** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="b6920-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="b6920-201">Fai doppio clic su **Configura la funzionalità 'Blocco al primo rilevamento'** e impostare l'opzione su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="b6920-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b6920-202">La disattivazione del blocco al primo rilevamento non disabilita né altera i Criteri di gruppo prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="b6920-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="b6920-203">Non si è un amministratore aziendale o un professionista IT?</span><span class="sxs-lookup"><span data-stu-id="b6920-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="b6920-204">Se non si è un amministratore aziendale o un professionista IT, ma si hanno domande sul blocco al primo rilevamento, questa è la sezione giusta.</span><span class="sxs-lookup"><span data-stu-id="b6920-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="b6920-205">Il blocco al primo rilevamento è una funzionalità di protezione dalle minacce che rileva e blocca il malware nel giro di pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="b6920-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="b6920-206">Anche se non esiste una specifica impostazione denominata "Blocco al primo rilevamento", la funzionalità viene abilitata quando nel dispositivo vengono configurate determinate impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b6920-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="b6920-207">Come gestire il blocco al primo rilevamento nel proprio dispositivo</span><span class="sxs-lookup"><span data-stu-id="b6920-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="b6920-208">Se si ha un dispositivo personale non gestito da un'organizzazione, può essere utile sapere come attivare o disattivare il blocco al primo rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b6920-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="b6920-209">A questo scopo si può usare l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6920-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="b6920-210">Nel computer Windows 10 aprire l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="b6920-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="b6920-211">Selezionare **Protezione da virus e minacce**.</span><span class="sxs-lookup"><span data-stu-id="b6920-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="b6920-212">In **Impostazioni di Protezione da virus e minacce** selezionare **Gestisci impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b6920-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="b6920-213">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6920-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="b6920-214">Per attivare il blocco al primo rilevamento, verificare che siano abilitate entrambe le opzioni **Protezione fornita dal cloud** e **Invio automatico di file di esempio**.</span><span class="sxs-lookup"><span data-stu-id="b6920-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="b6920-215">Per disattivare il blocco al primo rilevamento, disabilitare **Protezione fornita dal cloud** e **Invio automatico di file di esempio**.</span><span class="sxs-lookup"><span data-stu-id="b6920-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="b6920-216">Disattivando il blocco al primo rilevamento si riduce il livello di protezione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6920-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="b6920-217">Non è consigliabile disabilitare la protezione del blocco al primo rilevamento in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="b6920-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b6920-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6920-218">See also</span></span>

- [<span data-ttu-id="b6920-219">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="b6920-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b6920-220">Abilitare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="b6920-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6920-221">Restare protetti con Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="b6920-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
