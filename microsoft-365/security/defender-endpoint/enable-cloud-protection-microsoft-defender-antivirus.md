---
title: Attivare la protezione fornita dal cloud in Antivirus Microsoft Defender
description: Attiva la protezione fornita dal cloud per beneficiare di funzionalità di protezione veloci e avanzate.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, cloud, blocco a prima vista
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
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="28b24-104">Attivare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28b24-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="28b24-105">**Applies to:**</span></span>

- [<span data-ttu-id="28b24-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="28b24-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="28b24-107">Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint.</span><span class="sxs-lookup"><span data-stu-id="28b24-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="28b24-108">Sebbene sia chiamato servizio cloud, non è semplicemente protezione per i file archiviati nel cloud; piuttosto, utilizza risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto ai tradizionali aggiornamenti di intelligence sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="28b24-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="28b24-109">Antivirus Microsoft Defender utilizza più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente.</span><span class="sxs-lookup"><span data-stu-id="28b24-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="28b24-110">[Conoscere le tecnologie avanzate al centro della protezione di nuova generazione di Microsoft Defender for Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="28b24-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="28b24-111">È possibile attivare o disattivare Antivirus Microsoft Defender protezione fornita dal cloud in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="28b24-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="28b24-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="28b24-112">Microsoft Intune</span></span>
- <span data-ttu-id="28b24-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="28b24-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="28b24-114">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="28b24-114">Group Policy</span></span>
- <span data-ttu-id="28b24-115">Cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28b24-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="28b24-116">Puoi anche attivarlo o disattivarlo nei singoli client con l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="28b24-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="28b24-117">Per una panoramica della protezione fornita dal cloud Microsoft, vedere Antivirus Microsoft Defender Use [Microsoft cloud-delivered](cloud-protection-microsoft-defender-antivirus.md) protection.</span><span class="sxs-lookup"><span data-stu-id="28b24-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="28b24-118">Per ulteriori informazioni sui requisiti specifici di connettività di rete per garantire che gli endpoint possano connettersi al servizio di protezione fornito dal cloud, vedere [Configurare e convalidare le connessioni di rete](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="28b24-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="28b24-119">In Windows 10 non vi è alcuna differenza tra le opzioni **di** reporting **di base** e avanzate descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="28b24-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="28b24-120">Si tratta di una distinzione legacy e la scelta di entrambe le impostazioni comporterà lo stesso livello di protezione fornita dal cloud.</span><span class="sxs-lookup"><span data-stu-id="28b24-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="28b24-121">Non vi è alcuna differenza nel tipo o nella quantità di informazioni condivise.</span><span class="sxs-lookup"><span data-stu-id="28b24-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="28b24-122">Per ulteriori informazioni su ciò che raccogliamo, vedere l'Informativa [sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).</span><span class="sxs-lookup"><span data-stu-id="28b24-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="28b24-123">Utilizzare Intune per attivare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="28b24-124">Passare all'interfaccia Microsoft Endpoint Manager'interfaccia di [https://endpoint.microsoft.com](https://endpoint.microsoft.com) amministrazione di Amministrazione ( ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="28b24-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="28b24-125">Nel riquadro **Home** selezionare Configurazione **dispositivo > profili**.</span><span class="sxs-lookup"><span data-stu-id="28b24-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="28b24-126">Selezionare il **tipo di profilo** Restrizioni dispositivo da configurare.</span><span class="sxs-lookup"><span data-stu-id="28b24-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="28b24-127">Se è necessario creare un nuovo tipo di profilo **restrizioni dispositivo,** vedere [Configurare le impostazioni di restrizione del dispositivo in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="28b24-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="28b24-128">Selezionare **Impostazioni**  >  **di configurazione proprietà: Modifica**  >  **Antivirus Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="28b24-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="28b24-129">**Nell'opzione di protezione recapitata dal** cloud selezionare **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="28b24-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="28b24-130">**Nell'elenco a discesa Richiedi utenti prima dell'invio** di esempio selezionare Invia **automaticamente tutti i dati**.</span><span class="sxs-lookup"><span data-stu-id="28b24-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="28b24-131">Per ulteriori informazioni sui profili dei dispositivi Intune, incluso come creare e configurare le impostazioni, [vedere Cosa sono i Microsoft Intune dei dispositivi?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="28b24-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="28b24-132">Utilizzare Microsoft Endpoint Manager per attivare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="28b24-133">Passare all'interfaccia Microsoft Endpoint Manager'interfaccia di [https://endpoint.microsoft.com](https://endpoint.microsoft.com) amministrazione di Amministrazione ( ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="28b24-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="28b24-134">Scegliere **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="28b24-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="28b24-135">Selezionare un profilo antivirus.</span><span class="sxs-lookup"><span data-stu-id="28b24-135">Select an antivirus profile.</span></span> <span data-ttu-id="28b24-136">Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le [impostazioni di restrizione del dispositivo in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="28b24-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="28b24-137">Selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="28b24-137">Select **Properties**.</span></span> <span data-ttu-id="28b24-138">Accanto alle impostazioni **di configurazione scegliere** **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="28b24-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="28b24-139">Espandere **Protezione cloud** e quindi nell'elenco Livello di protezione **recapitato nel** cloud selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28b24-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="28b24-140">**Alto:** applica un forte livello di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="28b24-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="28b24-141">**Alto plus:** utilizza il **livello Alto e** applica ulteriori misure di protezione (può influire sulle prestazioni del client).</span><span class="sxs-lookup"><span data-stu-id="28b24-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="28b24-142">**Tolleranza zero:** blocca tutti gli eseguibili sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="28b24-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="28b24-143">Selezionare **Revisione + salva**, quindi Scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="28b24-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="28b24-144">Per ulteriori informazioni sulla configurazione Microsoft Endpoint Configuration Manager, vedere [Come creare e distribuire criteri antimalware: Servizio di protezione cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="28b24-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="28b24-145">Usare Criteri di gruppo per attivare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="28b24-146">Nel dispositivo di gestione Criteri di gruppo aprire Console Gestione Criteri di gruppo , [fare clic con](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="28b24-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="28b24-147">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="28b24-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="28b24-148">Selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="28b24-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="28b24-149">Espandere l'albero **per Windows componenti > Antivirus Microsoft Defender > MAPS**</span><span class="sxs-lookup"><span data-stu-id="28b24-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="28b24-150">Fare doppio clic **su Partecipa a Microsoft MAPS**.</span><span class="sxs-lookup"><span data-stu-id="28b24-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="28b24-151">Assicurarsi che l'opzione sia attivata e impostata **su Basic MAPS** o Advanced **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="28b24-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="28b24-152">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="28b24-152">Select **OK**.</span></span>

6. <span data-ttu-id="28b24-153">Fare doppio clic su **Invia esempi di file quando è necessaria un'ulteriore analisi**.</span><span class="sxs-lookup"><span data-stu-id="28b24-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="28b24-154">Verificare che la prima opzione sia impostata **su Abilitato** e che le altre opzioni siano impostate su:</span><span class="sxs-lookup"><span data-stu-id="28b24-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="28b24-155">**Invia campioni sicuri** (1)</span><span class="sxs-lookup"><span data-stu-id="28b24-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="28b24-156">**Invia tutti i campioni** (3)</span><span class="sxs-lookup"><span data-stu-id="28b24-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="28b24-157">**L'opzione Invia campioni sicuri** (1) significa che la maggior parte dei campioni verrà inviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="28b24-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="28b24-158">I file che potrebbero contenere informazioni personali richiederanno comunque una conferma aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="28b24-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="28b24-159">L'impostazione **dell'opzione su Richiedi** sempre (0) riducerà lo stato di protezione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28b24-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="28b24-160">Impostarlo su **Mai inviare** (2) significa che [la funzionalità Blocca a prima](configure-block-at-first-sight-microsoft-defender-antivirus.md) vista di Microsoft Defender per endpoint non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="28b24-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="28b24-161">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="28b24-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="28b24-162">Utilizzare i cmdlet di PowerShell per attivare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="28b24-163">I cmdlet seguenti possono attivare la protezione fornita dal cloud:</span><span class="sxs-lookup"><span data-stu-id="28b24-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="28b24-164">Per ulteriori informazioni sull'utilizzo di PowerShell con Antivirus Microsoft Defender, vedere [Utilizzare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) cmdlet di [Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="28b24-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="28b24-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) dispone inoltre di ulteriori informazioni specifiche su [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="28b24-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="28b24-166">È inoltre possibile impostare **-SubmitSamplesConsent** `SendSafeSamples` su (impostazione predefinita), `NeverSend` o `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="28b24-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="28b24-167">`SendSafeSamples`L'impostazione significa che la maggior parte dei campioni verrà inviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="28b24-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="28b24-168">I file che potrebbero contenere informazioni personali richiederanno comunque una conferma aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="28b24-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="28b24-169">Impostazione **di -SubmitSamplesConsent** `NeverSend` su o si riduce il livello di protezione del `AlwaysPrompt` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28b24-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="28b24-170">Inoltre, impostarlo su `NeverSend` significa che la funzionalità Blocca a [prima](configure-block-at-first-sight-microsoft-defender-antivirus.md) vista di Microsoft Defender per endpoint non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="28b24-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="28b24-171">Utilizzare Windows di gestione dei dati (WMI) per attivare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="28b24-172">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="28b24-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="28b24-173">Per ulteriori informazioni sui parametri consentiti, [vedere Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="28b24-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="28b24-174">Attivare la protezione fornita dal cloud sui singoli client con l'app Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="28b24-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="28b24-175">Se **l'impostazione Configura override delle impostazioni locali per la segnalazione** di Criteri di gruppo di Microsoft MAPS è **disabilitata**, **l'impostazione di** protezione basata su cloud in Windows Impostazioni verrà disattivata e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="28b24-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="28b24-176">Le modifiche apportate tramite un oggetto Criteri di gruppo devono essere distribuite nei singoli endpoint prima che l'impostazione venga aggiornata nelle impostazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="28b24-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="28b24-177">Aprire l Sicurezza di Windows applicazione selezionando l'icona scudo nella barra delle applicazioni o cercando Defender nel menu di **avvio**.</span><span class="sxs-lookup"><span data-stu-id="28b24-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="28b24-178">Selezionare il **riquadro & protezione da virus** (o l'icona scudo sulla barra dei menu sinistra) e quindi **l'etichetta & protezione dalle minacce** di Virus:</span><span class="sxs-lookup"><span data-stu-id="28b24-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot dell'etichetta Impostazioni di Protezione da virus e minacce nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="28b24-180">Verificare che **la protezione basata sul cloud e l'invio** **automatico dell'esempio** siano accesi . </span><span class="sxs-lookup"><span data-stu-id="28b24-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="28b24-181">Se l'invio automatico dell'esempio è stato configurato con Criteri di gruppo, l'impostazione verrà disattivata e non disponibile.</span><span class="sxs-lookup"><span data-stu-id="28b24-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="28b24-182">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="28b24-182">Related articles</span></span>

- [<span data-ttu-id="28b24-183">Configurare il periodo di timeout del blocco cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="28b24-184">Configurare il blocco a prima vista</span><span class="sxs-lookup"><span data-stu-id="28b24-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="28b24-185">Usare PowerShell cmdlets per gestire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="28b24-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="28b24-186">[Proteggere i Windows pc con Endpoint Protection per Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="28b24-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="28b24-187">Cmdlet di Defender</span><span class="sxs-lookup"><span data-stu-id="28b24-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="28b24-188">Utilizzare la protezione fornita dal cloud Microsoft in Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="28b24-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="28b24-189">Come creare e distribuire criteri antimalware: servizio di protezione del cloud</span><span class="sxs-lookup"><span data-stu-id="28b24-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="28b24-190">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="28b24-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
