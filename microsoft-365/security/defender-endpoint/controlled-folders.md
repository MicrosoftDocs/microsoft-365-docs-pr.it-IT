---
title: Proteggere le cartelle importanti dal ransomware dalla crittografia dei file con accesso controllato alle cartelle
description: I file nelle cartelle predefinite possono essere protetti da modifiche da app dannose. Impedire a ransomware di crittografare i file.
keywords: accesso controllato alle cartelle, windows 10, windows defender, ransomware, proteggere, file, cartelle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ae50d53fbc9bf01d4cd16b939461eecc9ec1a568
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165178"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="8204b-105">Proteggere le cartelle importanti con l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="8204b-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8204b-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8204b-106">**Applies to:**</span></span>
- [<span data-ttu-id="8204b-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8204b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8204b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8204b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8204b-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8204b-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8204b-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8204b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="8204b-111">Che cos'è l'accesso controllato alle cartelle?</span><span class="sxs-lookup"><span data-stu-id="8204b-111">What is controlled folder access?</span></span>

<span data-ttu-id="8204b-112">L'accesso controllato alle cartelle consente di proteggere i dati importanti da app e minacce dannose, ad esempio ransomware.</span><span class="sxs-lookup"><span data-stu-id="8204b-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="8204b-113">L'accesso controllato alle cartelle protegge i dati controllando le app da un elenco di app note e attendibili.</span><span class="sxs-lookup"><span data-stu-id="8204b-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="8204b-114">Supportato nei client Windows Server 2019 e Windows 10, l'accesso controllato alle cartelle può essere attivato tramite App di sicurezza di Windows, Microsoft Endpoint Configuration Manager o Intune (per i dispositivi gestiti).</span><span class="sxs-lookup"><span data-stu-id="8204b-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="8204b-115">I motori di script non sono attendibili e non è possibile consentire loro l'accesso alle cartelle protette controllate.</span><span class="sxs-lookup"><span data-stu-id="8204b-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="8204b-116">Ad esempio, PowerShell non è considerato attendibile dall'accesso controllato alle cartelle, anche se si consente con [indicatori di file e certificati.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="8204b-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="8204b-117">L'accesso controllato alle cartelle funziona meglio con [Microsoft Defender for Endpoint,](microsoft-defender-advanced-threat-protection.md)che fornisce report dettagliati sugli eventi di accesso controllato alle cartelle e sui blocchi nell'ambito dei soliti scenari di analisi [degli avvisi.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8204b-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="8204b-118">I blocchi di accesso controllato alle cartelle non generano avvisi nella [coda avvisi.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="8204b-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="8204b-119">Tuttavia, puoi visualizzare le informazioni sui blocchi di accesso controllato alle cartelle nella visualizzazione sequenza temporale del [dispositivo,](investigate-machines.md)usando la ricerca avanzata [o](advanced-hunting-overview.md)con regole di [rilevamento personalizzate.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="8204b-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="8204b-120">Come funziona l'accesso controllato alle cartelle?</span><span class="sxs-lookup"><span data-stu-id="8204b-120">How does controlled folder access work?</span></span>

<span data-ttu-id="8204b-121">L'accesso controllato alle cartelle funziona consentendo solo alle app attendibili di accedere alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="8204b-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="8204b-122">Le cartelle protette vengono specificate quando viene configurato l'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="8204b-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="8204b-123">In genere, le cartelle di uso comune, ad esempio quelle utilizzate per documenti, immagini, download e così via, sono incluse nell'elenco delle cartelle controllate.</span><span class="sxs-lookup"><span data-stu-id="8204b-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="8204b-124">L'accesso controllato alle cartelle funziona con un elenco di app attendibili.</span><span class="sxs-lookup"><span data-stu-id="8204b-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="8204b-125">Le app incluse nell'elenco del software attendibile funzionano come previsto.</span><span class="sxs-lookup"><span data-stu-id="8204b-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="8204b-126">Alle app non incluse nell'elenco non viene impedito di apportare modifiche ai file all'interno delle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="8204b-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="8204b-127">Le app vengono aggiunte all'elenco in base alla loro diffusione e reputazione.</span><span class="sxs-lookup"><span data-stu-id="8204b-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="8204b-128">Le app altamente diffuse in tutta l'organizzazione e che non hanno mai visualizzato alcun comportamento ritenuto dannoso sono considerate attendibili.</span><span class="sxs-lookup"><span data-stu-id="8204b-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="8204b-129">Tali app vengono aggiunte automaticamente all'elenco.</span><span class="sxs-lookup"><span data-stu-id="8204b-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="8204b-130">Le app possono anche essere aggiunte manualmente all'elenco attendibile tramite Configuration Manager o Intune.</span><span class="sxs-lookup"><span data-stu-id="8204b-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="8204b-131">Altre azioni, ad esempio [l'aggiunta di un indicatore di file](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) per un'app, possono essere eseguite dalla console del Centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8204b-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="8204b-132">Perché l'accesso controllato alle cartelle è importante</span><span class="sxs-lookup"><span data-stu-id="8204b-132">Why controlled folder access is important</span></span>

<span data-ttu-id="8204b-133">L'accesso controllato alle cartelle è particolarmente utile per proteggere i documenti e le informazioni da [ransomware.](https://www.microsoft.com/wdsi/threats/ransomware)</span><span class="sxs-lookup"><span data-stu-id="8204b-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="8204b-134">In un attacco ransomware, i file possono essere crittografati e tenuti in ostaggio.</span><span class="sxs-lookup"><span data-stu-id="8204b-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="8204b-135">Con l'accesso controllato alle cartelle, viene visualizzata una notifica nel computer in cui un'app ha tentato di apportare modifiche a un file in una cartella protetta.</span><span class="sxs-lookup"><span data-stu-id="8204b-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="8204b-136">Puoi personalizzare [la notifica con i](customize-attack-surface-reduction.md#customize-the-notification) dettagli dell'azienda e le informazioni di contatto.</span><span class="sxs-lookup"><span data-stu-id="8204b-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="8204b-137">È inoltre possibile abilitare le regole singolarmente per personalizzare le tecniche monitorate dalla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8204b-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="8204b-138">Le [cartelle protette](#review-controlled-folder-access-events-in-windows-event-viewer) includono cartelle di sistema comuni (inclusi i settori di avvio) ed è possibile [aggiungere altre cartelle.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="8204b-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="8204b-139">Puoi anche consentire [alle app](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) di concedere loro l'accesso alle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="8204b-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="8204b-140">È possibile utilizzare [la modalità di controllo](audit-windows-defender.md) per valutare l'impatto dell'accesso controllato alle cartelle nell'organizzazione se fosse abilitato.</span><span class="sxs-lookup"><span data-stu-id="8204b-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="8204b-141">È inoltre possibile visitare il sito Web Windows Defender test di base [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.</span><span class="sxs-lookup"><span data-stu-id="8204b-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="8204b-142">L'accesso controllato alle cartelle è supportato nelle seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="8204b-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="8204b-143">[Windows 10, versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) e successive</span><span class="sxs-lookup"><span data-stu-id="8204b-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="8204b-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8204b-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="8204b-145">Le cartelle di sistema di Windows sono protette per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="8204b-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="8204b-146">Le cartelle di sistema di Windows sono protette per impostazione predefinita, insieme a diverse altre cartelle:</span><span class="sxs-lookup"><span data-stu-id="8204b-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="8204b-147">È possibile configurare cartelle aggiuntive come protette, ma non è possibile rimuovere le cartelle di sistema di Windows protette per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8204b-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="8204b-148">Requisiti per l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="8204b-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="8204b-149">L'accesso controllato alle cartelle richiede [l'abilitazione](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)della protezione in tempo reale di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8204b-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="8204b-150">Esaminare gli eventi di accesso controllato alle cartelle in Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="8204b-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="8204b-151">Defender for Endpoint fornisce report dettagliati su eventi e blocchi nell'ambito degli scenari di [analisi degli avvisi.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8204b-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="8204b-152">Puoi eseguire una query su Microsoft Defender per i dati dell'endpoint usando [Ricerca avanzata.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="8204b-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="8204b-153">Se usi la modalità [di](audit-windows-defender.md)controllo, puoi usare la ricerca avanzata per vedere in che modo le impostazioni di accesso controllato alle cartelle influirebbero sull'ambiente se fossero abilitate. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8204b-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="8204b-154">Query di esempio:</span><span class="sxs-lookup"><span data-stu-id="8204b-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="8204b-155">Esaminare gli eventi di accesso controllato alle cartelle nel Visualizzatore eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="8204b-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="8204b-156">Puoi esaminare il registro eventi di Windows per visualizzare gli eventi che vengono creati quando un'app controlla o blocca l'accesso controllato alle cartelle:</span><span class="sxs-lookup"><span data-stu-id="8204b-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="8204b-157">Scarica il [pacchetto di valutazione](https://aka.ms/mp7z2w) ed estrai il file *cfa-events.xml* in un percorso facilmente accessibile nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8204b-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="8204b-158">Digita **Visualizzatore** eventi nel menu Start per aprire il Visualizzatore eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="8204b-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="8204b-159">Nel riquadro sinistro, in **Azioni,** selezionare **Importa visualizzazione personalizzata...**.</span><span class="sxs-lookup"><span data-stu-id="8204b-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="8204b-160">Passare al punto in cui è stato *cfa-events.xml* e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="8204b-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="8204b-161">In alternativa, [copiare il codice XML direttamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="8204b-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="8204b-162">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8204b-162">Select **OK**.</span></span>

<span data-ttu-id="8204b-163">La tabella seguente mostra gli eventi correlati all'accesso controllato alle cartelle:</span><span class="sxs-lookup"><span data-stu-id="8204b-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="8204b-164">ID evento</span><span class="sxs-lookup"><span data-stu-id="8204b-164">Event ID</span></span> | <span data-ttu-id="8204b-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8204b-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="8204b-166">5007</span><span class="sxs-lookup"><span data-stu-id="8204b-166">5007</span></span> | <span data-ttu-id="8204b-167">Evento quando vengono modificate le impostazioni</span><span class="sxs-lookup"><span data-stu-id="8204b-167">Event when settings are changed</span></span> |
|<span data-ttu-id="8204b-168">1124</span><span class="sxs-lookup"><span data-stu-id="8204b-168">1124</span></span> | <span data-ttu-id="8204b-169">Evento di accesso controllato alle cartelle controllato</span><span class="sxs-lookup"><span data-stu-id="8204b-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="8204b-170">1123</span><span class="sxs-lookup"><span data-stu-id="8204b-170">1123</span></span> | <span data-ttu-id="8204b-171">Evento di accesso controllato alla cartella bloccato</span><span class="sxs-lookup"><span data-stu-id="8204b-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="8204b-172">Visualizzare o modificare l'elenco delle cartelle protette</span><span class="sxs-lookup"><span data-stu-id="8204b-172">View or change the list of protected folders</span></span>

<span data-ttu-id="8204b-173">Puoi usare l'app Sicurezza di Windows per visualizzare l'elenco delle cartelle protette dall'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="8204b-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="8204b-174">Nel dispositivo Windows 10 apri l'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="8204b-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="8204b-175">Selezionare **Protezione da & virus**.</span><span class="sxs-lookup"><span data-stu-id="8204b-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="8204b-176">In **Protezione ransomware** seleziona Gestisci protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="8204b-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="8204b-177">Se l'accesso controllato alle cartelle è disattivato, è necessario attivarlo.</span><span class="sxs-lookup"><span data-stu-id="8204b-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="8204b-178">Selezionare **cartelle protette**.</span><span class="sxs-lookup"><span data-stu-id="8204b-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="8204b-179">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8204b-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="8204b-180">Per aggiungere una cartella, selezionare **+ Aggiungi una cartella protetta.**</span><span class="sxs-lookup"><span data-stu-id="8204b-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="8204b-181">Per rimuovere una cartella, selezionarla e quindi **selezionare Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="8204b-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="8204b-182">[Le cartelle di sistema](#windows-system-folders-are-protected-by-default) di Windows sono protette per impostazione predefinita e non è possibile rimuoverle dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="8204b-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="8204b-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8204b-183">See also</span></span>

- [<span data-ttu-id="8204b-184">Valutare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="8204b-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="8204b-185">Personalizzare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="8204b-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="8204b-186">Proteggere più cartelle</span><span class="sxs-lookup"><span data-stu-id="8204b-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
