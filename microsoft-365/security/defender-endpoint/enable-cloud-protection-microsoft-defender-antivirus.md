---
title: Attivare la protezione basata sul cloud in Microsoft Defender Antivirus
description: Attivare la protezione basata sul cloud per usufruire di funzionalità di protezione avanzate e veloci.
keywords: Microsoft Defender Antivirus, antimalware, sicurezza, cloud, blocco al primo sguardo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: cfaf4563e96568ae26bd990678462836b9202656
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691474"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="1026e-104">Attivare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1026e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1026e-105">**Applies to:**</span></span>

- [<span data-ttu-id="1026e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1026e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="1026e-107">Il servizio cloud Microsoft Defender Antivirus è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint.</span><span class="sxs-lookup"><span data-stu-id="1026e-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="1026e-108">Sebbene sia denominato servizio cloud, non è semplicemente protezione per i file archiviati nel cloud. usa invece risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="1026e-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="1026e-109">Microsoft Defender Antivirus usa più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente.</span><span class="sxs-lookup"><span data-stu-id="1026e-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="1026e-110">[Informazioni sulle tecnologie avanzate alla base di Microsoft Defender for Endpoint di nuova generazione.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="1026e-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="1026e-111">![Elenco dei motori Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="1026e-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="1026e-112">Puoi attivare o disattivare la protezione con distribuzione cloud di Microsoft Defender Antivirus in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="1026e-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="1026e-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1026e-113">Microsoft Intune</span></span>
- <span data-ttu-id="1026e-114">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1026e-114">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="1026e-115">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="1026e-115">Group Policy</span></span>
- <span data-ttu-id="1026e-116">Cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1026e-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="1026e-117">Puoi anche attivarlo o disattivarlo nei singoli client con l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="1026e-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="1026e-118">Vedi [Usare la protezione fornita dal cloud Microsoft](cloud-protection-microsoft-defender-antivirus.md) per una panoramica della protezione fornita dal cloud di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="1026e-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="1026e-119">Per ulteriori informazioni sui requisiti di connettività di rete specifici per garantire che gli endpoint possano connettersi al servizio di protezione fornito dal cloud, vedere [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1026e-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1026e-120">In Windows 10, non esiste alcuna differenza tra le **opzioni** di creazione di report di base **e** avanzate descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1026e-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="1026e-121">Si tratta di una distinzione legacy e la scelta di entrambe le impostazioni determina lo stesso livello di protezione fornito dal cloud.</span><span class="sxs-lookup"><span data-stu-id="1026e-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="1026e-122">Non esiste alcuna differenza nel tipo o nella quantità di informazioni condivise.</span><span class="sxs-lookup"><span data-stu-id="1026e-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="1026e-123">Per altre informazioni sui dati raccolti, vedi l'Informativa [sulla privacy di Microsoft.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="1026e-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="1026e-124">Usare Intune per attivare la protezione con distribuzione cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="1026e-125">Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1026e-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="1026e-126">Nel riquadro **Home** selezionare **Configurazione dispositivo > Profili**.</span><span class="sxs-lookup"><span data-stu-id="1026e-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>
3. <span data-ttu-id="1026e-127">Selezionare il **tipo di profilo** Restrizioni dispositivo che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="1026e-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="1026e-128">Se devi creare un nuovo tipo di profilo Restrizioni **dispositivo,** vedi [Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="1026e-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="1026e-129">Selezionare **Proprietà**  >  **Impostazioni di configurazione: Modifica** Microsoft Defender  >  **Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="1026e-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>
5. <span data-ttu-id="1026e-130">**Nell'opzione Protezione con recapito cloud** selezionare **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="1026e-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>
6. <span data-ttu-id="1026e-131">**Nell'elenco a discesa Richiedi conferma agli utenti prima dell'invio** di esempio seleziona **Invia automaticamente tutti i dati.**</span><span class="sxs-lookup"><span data-stu-id="1026e-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="1026e-132">Per altre informazioni sui profili dei dispositivi Intune, incluso come creare e configurare le impostazioni, vedere Che cosa sono i profili di [dispositivo di Microsoft Intune?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="1026e-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="1026e-133">Usare Microsoft Endpoint Manager per attivare la protezione con distribuzione cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="1026e-134">Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1026e-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="1026e-135">Scegliere **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="1026e-135">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="1026e-136">Selezionare un profilo antivirus.</span><span class="sxs-lookup"><span data-stu-id="1026e-136">Select an antivirus profile.</span></span> <span data-ttu-id="1026e-137">Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="1026e-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="1026e-138">Selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1026e-138">Select **Properties**.</span></span> <span data-ttu-id="1026e-139">Quindi, accanto a **Impostazioni di configurazione** scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="1026e-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>
5. <span data-ttu-id="1026e-140">Espandere **Protezione cloud** e  quindi selezionare una delle opzioni seguenti nell'elenco Livello di protezione fornito dal cloud:</span><span class="sxs-lookup"><span data-stu-id="1026e-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
    1. <span data-ttu-id="1026e-141">**High**: applica un livello elevato di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1026e-141">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="1026e-142">**High plus**: usa **il livello High** e applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client).</span><span class="sxs-lookup"><span data-stu-id="1026e-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="1026e-143">**Tolleranza zero:** blocca tutti i file eseguibili sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="1026e-143">**Zero tolerance**: Blocks all unknown executables.</span></span>
6. <span data-ttu-id="1026e-144">Seleziona **Rivedi e salva,** quindi scegli **Salva.**</span><span class="sxs-lookup"><span data-stu-id="1026e-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="1026e-145">Per ulteriori informazioni sulla configurazione di Microsoft Endpoint Configuration Manager, vedere [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="1026e-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="1026e-146">Usare Criteri di gruppo per attivare la protezione con distribuzione cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="1026e-147">Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1026e-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="1026e-148">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="1026e-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="1026e-149">Selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="1026e-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="1026e-150">Espandere l'albero fino **ai componenti di Windows > Microsoft Defender Antivirus > MAPS**</span><span class="sxs-lookup"><span data-stu-id="1026e-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="1026e-151">Fare doppio clic su **Partecipa a Microsoft MAPS.**</span><span class="sxs-lookup"><span data-stu-id="1026e-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="1026e-152">Assicurati che l'opzione sia attivata e impostata su **MAPPE di base** o MAPPE **avanzate.**</span><span class="sxs-lookup"><span data-stu-id="1026e-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="1026e-153">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1026e-153">Select **OK**.</span></span>

6. <span data-ttu-id="1026e-154">Fare doppio clic su **Invia esempi di file quando è necessaria un'ulteriore analisi.**</span><span class="sxs-lookup"><span data-stu-id="1026e-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="1026e-155">Verificare che la prima opzione sia impostata su **Abilitato** e che le altre opzioni siano impostate su:</span><span class="sxs-lookup"><span data-stu-id="1026e-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="1026e-156">**Inviare campioni sicuri** (1)</span><span class="sxs-lookup"><span data-stu-id="1026e-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="1026e-157">**Inviare tutti gli esempi** (3)</span><span class="sxs-lookup"><span data-stu-id="1026e-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="1026e-158">**L'opzione Invia campioni sicuri** (1) indica che la maggior parte dei campioni verrà inviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1026e-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="1026e-159">I file che probabilmente contengono informazioni personali verranno comunque richiesti e richiederanno ulteriore conferma.</span><span class="sxs-lookup"><span data-stu-id="1026e-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

        > [!WARNING]
        > <span data-ttu-id="1026e-160">Se si imposta **l'opzione su Chiedi** sempre conferma (0), lo stato di protezione del dispositivo verrà abbassato.</span><span class="sxs-lookup"><span data-stu-id="1026e-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="1026e-161">L'impostazione su **Non inviare** mai (2) significa che la [funzionalità](configure-block-at-first-sight-microsoft-defender-antivirus.md) Blocca al primo sguardo di Microsoft Defender per Endpoint non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="1026e-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="1026e-162">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1026e-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="1026e-163">Usare i cmdlet di PowerShell per attivare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="1026e-164">I cmdlet seguenti possono attivare la protezione recapitata nel cloud:</span><span class="sxs-lookup"><span data-stu-id="1026e-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="1026e-165">Per ulteriori informazioni su come usare PowerShell con Microsoft Defender Antivirus, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="1026e-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="1026e-166">[CSP criteri - Defender](/windows/client-management/mdm/policy-csp-defender) include anche altre informazioni specifiche su [-SubmitSamplesConsent.](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)</span><span class="sxs-lookup"><span data-stu-id="1026e-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="1026e-167">Puoi anche impostare **-SubmitSamplesConsent** `SendSafeSamples` su (impostazione predefinita), `NeverSend` o `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="1026e-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="1026e-168">`SendSafeSamples`L'impostazione indica che la maggior parte dei campioni verrà inviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1026e-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="1026e-169">I file che probabilmente contengono informazioni personali verranno comunque richiesti e richiederanno ulteriore conferma.</span><span class="sxs-lookup"><span data-stu-id="1026e-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="1026e-170">Se **si imposta -SubmitSamplesConsent** su o si riduce il livello `NeverSend` di protezione del `AlwaysPrompt` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1026e-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="1026e-171">Inoltre, impostandola su significa che la funzionalità Blocca al primo sguardo `NeverSend` di Microsoft Defender per Endpoint non funzionerà. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1026e-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="1026e-172">Usare Windows Management Instruction (WMI) per attivare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="1026e-173">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="1026e-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="1026e-174">Per altre informazioni sui parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="1026e-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="1026e-175">Attivare la protezione basata sul cloud su singoli client con l'app Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="1026e-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="1026e-176">Se **l'impostazione** di Criteri di gruppo Configura impostazioni locali per la segnalazione di Microsoft MAPS è impostata su **Disabilitato,** l'impostazione di protezione basata su **cloud** in Impostazioni di Windows sarà disattivata e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="1026e-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="1026e-177">Le modifiche apportate tramite un oggetto Criteri di gruppo devono prima essere distribuite a singoli endpoint prima che l'impostazione venga aggiornata in Impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="1026e-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="1026e-178">Apri l'app Sicurezza di Windows selezionando l'icona scudo nella barra delle applicazioni o cercando Defender **nel** menu Start.</span><span class="sxs-lookup"><span data-stu-id="1026e-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="1026e-179">Seleziona il **riquadro Protezione** da & virus (o l'icona scudo sulla barra dei menu sinistra) e quindi l'etichetta **Impostazioni** protezione da & virus:</span><span class="sxs-lookup"><span data-stu-id="1026e-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="1026e-181">Verificare che **Protezione basata su cloud e** **Invio** automatico di esempio siano stati commutati su **On.**</span><span class="sxs-lookup"><span data-stu-id="1026e-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="1026e-182">Se l'invio automatico di esempio è stato configurato con Criteri di gruppo, l'impostazione sarà disattivata e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="1026e-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1026e-183">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="1026e-183">Related articles</span></span>

- [<span data-ttu-id="1026e-184">Configurare il periodo di timeout del blocco cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1026e-185">Configurare il blocco al primo avvistamento</span><span class="sxs-lookup"><span data-stu-id="1026e-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1026e-186">Utilizzare i cmdlet di PowerShell per gestire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1026e-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="1026e-187">[Proteggere i PC Windows con Endpoint Protection per Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="1026e-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="1026e-188">Cmdlet defender</span><span class="sxs-lookup"><span data-stu-id="1026e-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="1026e-189">Usare la protezione microsoft basata sul cloud in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1026e-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1026e-190">Come creare e distribuire criteri antimalware: servizio di protezione cloud</span><span class="sxs-lookup"><span data-stu-id="1026e-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="1026e-191">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="1026e-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)