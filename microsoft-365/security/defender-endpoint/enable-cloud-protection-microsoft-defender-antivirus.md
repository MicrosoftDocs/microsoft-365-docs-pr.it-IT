---
title: Attivare la protezione basata sul cloud in Antivirus Microsoft Defender
description: Attivare la protezione basata sul cloud per usufruire di funzionalità di protezione avanzate e veloci.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, cloud, blocco al primo sguardo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572058"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="89d81-104">Attivare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89d81-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="89d81-105">**Applies to:**</span></span>

- [<span data-ttu-id="89d81-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="89d81-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="89d81-107">Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint.</span><span class="sxs-lookup"><span data-stu-id="89d81-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="89d81-108">Sebbene sia denominato servizio cloud, non è semplicemente protezione per i file archiviati nel cloud. usa invece risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="89d81-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="89d81-109">Antivirus Microsoft Defender più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente.</span><span class="sxs-lookup"><span data-stu-id="89d81-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="89d81-110">[Informazioni sulle tecnologie avanzate alla base di Microsoft Defender for Endpoint di nuova generazione.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="89d81-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="89d81-111">È possibile attivare o Antivirus Microsoft Defender la protezione basata sul cloud in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="89d81-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="89d81-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="89d81-112">Microsoft Intune</span></span>
- <span data-ttu-id="89d81-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="89d81-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="89d81-114">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="89d81-114">Group Policy</span></span>
- <span data-ttu-id="89d81-115">Cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89d81-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="89d81-116">Puoi anche attivarlo o disattivarlo nei singoli client con l Sicurezza di Windows app.</span><span class="sxs-lookup"><span data-stu-id="89d81-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="89d81-117">Vedi Usare la protezione fornita [dal cloud Microsoft](cloud-protection-microsoft-defender-antivirus.md) per una panoramica Antivirus Microsoft Defender protezione fornita dal cloud.</span><span class="sxs-lookup"><span data-stu-id="89d81-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="89d81-118">Per ulteriori informazioni sui requisiti di connettività di rete specifici per garantire che gli endpoint possano connettersi al servizio di protezione fornito dal cloud, vedere [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="89d81-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="89d81-119">In Windows 10, non esiste alcuna differenza tra le **opzioni** di creazione di **report** di base e avanzate descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="89d81-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="89d81-120">Si tratta di una distinzione legacy e la scelta di entrambe le impostazioni determina lo stesso livello di protezione fornito dal cloud.</span><span class="sxs-lookup"><span data-stu-id="89d81-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="89d81-121">Non esiste alcuna differenza nel tipo o nella quantità di informazioni condivise.</span><span class="sxs-lookup"><span data-stu-id="89d81-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="89d81-122">Per altre informazioni sui dati raccolti, vedi l'Informativa [sulla privacy di Microsoft.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="89d81-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="89d81-123">Usare Intune per attivare la protezione con distribuzione cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="89d81-124">Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="89d81-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="89d81-125">Nel riquadro **Home** selezionare **Configurazione dispositivo > Profili**.</span><span class="sxs-lookup"><span data-stu-id="89d81-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="89d81-126">Selezionare il **tipo di profilo** Restrizioni dispositivo che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="89d81-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="89d81-127">Se devi creare un  nuovo tipo di profilo Restrizioni dispositivo, vedi Configurare le impostazioni di [restrizione dei](/intune/device-restrictions-configure)dispositivi in Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="89d81-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="89d81-128">Selezionare **Proprietà**  >  **Impostazioni di configurazione: Modifica**  >  **Antivirus Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="89d81-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="89d81-129">**Nell'opzione Protezione con recapito cloud** selezionare **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="89d81-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="89d81-130">**Nell'elenco a discesa Richiedi conferma agli utenti prima dell'invio** di esempio seleziona **Invia automaticamente tutti i dati.**</span><span class="sxs-lookup"><span data-stu-id="89d81-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="89d81-131">Per altre informazioni sui profili dei dispositivi Intune, incluso come creare e configurare le impostazioni, vedere Che cosa sono i profili Microsoft Intune [dispositivo?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="89d81-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="89d81-132">Usare Microsoft Endpoint Manager per attivare la protezione con distribuzione cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="89d81-133">Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="89d81-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="89d81-134">Scegliere **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="89d81-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="89d81-135">Selezionare un profilo antivirus.</span><span class="sxs-lookup"><span data-stu-id="89d81-135">Select an antivirus profile.</span></span> <span data-ttu-id="89d81-136">Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="89d81-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="89d81-137">Selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="89d81-137">Select **Properties**.</span></span> <span data-ttu-id="89d81-138">Quindi, accanto a **Impostazioni di configurazione** scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="89d81-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="89d81-139">Espandere **Protezione cloud** e  quindi selezionare una delle opzioni seguenti nell'elenco Livello di protezione fornito dal cloud:</span><span class="sxs-lookup"><span data-stu-id="89d81-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="89d81-140">**High**: applica un livello elevato di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="89d81-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="89d81-141">**High plus**: usa **il livello High** e applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client).</span><span class="sxs-lookup"><span data-stu-id="89d81-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="89d81-142">**Tolleranza zero:** blocca tutti i file eseguibili sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="89d81-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="89d81-143">Seleziona **Rivedi e salva,** quindi scegli **Salva.**</span><span class="sxs-lookup"><span data-stu-id="89d81-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="89d81-144">Per ulteriori informazioni sulla configurazione Microsoft Endpoint Configuration Manager, vedere [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="89d81-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="89d81-145">Usare Criteri di gruppo per attivare la protezione con distribuzione cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="89d81-146">Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="89d81-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="89d81-147">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="89d81-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="89d81-148">Selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="89d81-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="89d81-149">Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > MAPS**</span><span class="sxs-lookup"><span data-stu-id="89d81-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="89d81-150">Fare doppio clic su **Partecipa a Microsoft MAPS.**</span><span class="sxs-lookup"><span data-stu-id="89d81-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="89d81-151">Assicurati che l'opzione sia attivata e impostata su **MAPPE di base** o MAPPE **avanzate.**</span><span class="sxs-lookup"><span data-stu-id="89d81-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="89d81-152">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="89d81-152">Select **OK**.</span></span>

6. <span data-ttu-id="89d81-153">Fare doppio clic su **Invia esempi di file quando è necessaria un'ulteriore analisi.**</span><span class="sxs-lookup"><span data-stu-id="89d81-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="89d81-154">Verificare che la prima opzione sia impostata su **Abilitato** e che le altre opzioni siano impostate su:</span><span class="sxs-lookup"><span data-stu-id="89d81-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="89d81-155">**Inviare campioni sicuri** (1)</span><span class="sxs-lookup"><span data-stu-id="89d81-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="89d81-156">**Inviare tutti gli esempi** (3)</span><span class="sxs-lookup"><span data-stu-id="89d81-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="89d81-157">**L'opzione Invia campioni sicuri** (1) indica che la maggior parte dei campioni verrà inviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="89d81-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="89d81-158">I file che probabilmente contengono informazioni personali verranno comunque richiesti e richiederanno ulteriore conferma.</span><span class="sxs-lookup"><span data-stu-id="89d81-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="89d81-159">Se si imposta **l'opzione su Chiedi** sempre conferma (0), lo stato di protezione del dispositivo verrà abbassato.</span><span class="sxs-lookup"><span data-stu-id="89d81-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="89d81-160">L'impostazione su **Non inviare** mai (2) significa che la [funzionalità](configure-block-at-first-sight-microsoft-defender-antivirus.md) Blocca al primo sguardo di Microsoft Defender per Endpoint non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="89d81-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="89d81-161">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="89d81-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="89d81-162">Usare i cmdlet di PowerShell per attivare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="89d81-163">I cmdlet seguenti possono attivare la protezione recapitata nel cloud:</span><span class="sxs-lookup"><span data-stu-id="89d81-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="89d81-164">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="89d81-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="89d81-165">[CSP criteri - Defender](/windows/client-management/mdm/policy-csp-defender) include anche altre informazioni specifiche su [-SubmitSamplesConsent.](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)</span><span class="sxs-lookup"><span data-stu-id="89d81-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="89d81-166">Puoi anche impostare **-SubmitSamplesConsent** `SendSafeSamples` su (impostazione predefinita), `NeverSend` o `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="89d81-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="89d81-167">`SendSafeSamples`L'impostazione indica che la maggior parte dei campioni verrà inviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="89d81-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="89d81-168">I file che probabilmente contengono informazioni personali verranno comunque richiesti e richiederanno ulteriore conferma.</span><span class="sxs-lookup"><span data-stu-id="89d81-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="89d81-169">Se **si imposta -SubmitSamplesConsent** su o si riduce il livello `NeverSend` di protezione del `AlwaysPrompt` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="89d81-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="89d81-170">Inoltre, impostandola su significa che la funzionalità Blocca al primo sguardo `NeverSend` di Microsoft Defender per Endpoint non funzionerà. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="89d81-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="89d81-171">Usare Windows Management Instruction (WMI) per attivare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="89d81-172">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="89d81-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="89d81-173">Per altre informazioni sui parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="89d81-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="89d81-174">Attivare la protezione basata sul cloud su singoli client con l'app Sicurezza di Windows cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="89d81-175">Se l'impostazione configura **l'override** dell'impostazione locale per la segnalazione di Criteri di gruppo di Microsoft MAPS è impostata su **Disabilitato,** l'impostazione di protezione basata su **cloud** in Windows Impostazioni sarà disattivata e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="89d81-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="89d81-176">Le modifiche apportate tramite un oggetto Criteri di gruppo devono essere distribuite nei singoli endpoint prima che l'impostazione venga aggiornata nelle impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="89d81-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="89d81-177">Apri l Sicurezza di Windows app selezionando l'icona scudo nella barra delle applicazioni o cercando Defender nel menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="89d81-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="89d81-178">Seleziona il **riquadro Protezione** da & virus (o l'icona scudo sulla barra dei menu sinistra) e quindi l'etichetta **Impostazioni** protezione da & virus:</span><span class="sxs-lookup"><span data-stu-id="89d81-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot dell'etichetta Impostazioni di Protezione da virus e minacce nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="89d81-180">Verificare che **Protezione basata su cloud e** **Invio** automatico di esempio siano stati commutati su **On.**</span><span class="sxs-lookup"><span data-stu-id="89d81-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="89d81-181">Se l'invio automatico di esempio è stato configurato con Criteri di gruppo, l'impostazione sarà disattivata e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="89d81-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="89d81-182">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="89d81-182">Related articles</span></span>

- [<span data-ttu-id="89d81-183">Configurare il periodo di timeout del blocco cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="89d81-184">Configurare il blocco al primo avvistamento</span><span class="sxs-lookup"><span data-stu-id="89d81-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="89d81-185">Usare PowerShell cmdlets per gestire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="89d81-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="89d81-186">[Proteggere i WINDOWS pc con Endpoint Protection per Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="89d81-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="89d81-187">Cmdlet defender</span><span class="sxs-lookup"><span data-stu-id="89d81-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="89d81-188">Usare la protezione microsoft basata su cloud in Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="89d81-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="89d81-189">Come creare e distribuire criteri antimalware: servizio di protezione cloud</span><span class="sxs-lookup"><span data-stu-id="89d81-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="89d81-190">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="89d81-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
