---
title: Vulnerabilità nell'organizzazione - gestione delle minacce e delle vulnerabilità
description: Elenca l'ID CVE (Common Vulnerabilities and Exposures) dei punti deboli rilevati nel software in esecuzione nell'organizzazione. Individuata dalla funzionalità di gestione delle minacce e delle vulnerabilità di Microsoft Defender for Endpoint.
keywords: Microsoft Defender for Endpoint threat & vulnerability management, threat and vulnerability management, Microsoft Defender for Endpoint tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8039a06dc58c31158f90d39857ffbeba92138d5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933074"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="43aea-105">Vulnerabilità nell'organizzazione - gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43aea-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="43aea-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="43aea-106">**Applies to:**</span></span>
- [<span data-ttu-id="43aea-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="43aea-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="43aea-108">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43aea-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="43aea-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43aea-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="43aea-110">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="43aea-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="43aea-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="43aea-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="43aea-112">La gestione delle minacce e delle vulnerabilità usa gli stessi segnali in Defender per la protezione degli endpoint per analizzare e rilevare le vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="43aea-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="43aea-113">Nella **pagina Punti** deboli sono elencate le vulnerabilità software a cui sono esposti i dispositivi elencando l'ID CVE (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="43aea-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="43aea-114">È inoltre possibile visualizzare la gravità, il sistema di valutazione delle vulnerabilità comuni (CVSS, Common Vulnerability Scoring System), la diffusione nell'organizzazione, la violazione corrispondente, le informazioni dettagliate sulle minacce e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="43aea-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="43aea-115">Se non esiste un CVE-ID ufficiale assegnato a una vulnerabilità, il nome della vulnerabilità viene assegnato dalla gestione delle minacce e delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="43aea-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="43aea-116">Per ricevere messaggi di posta elettronica sui nuovi eventi di vulnerabilità, vedere Configurare le notifiche di posta elettronica relative alla vulnerabilità [in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="43aea-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="43aea-117">Passare alla pagina Punti deboli</span><span class="sxs-lookup"><span data-stu-id="43aea-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="43aea-118">Accedere alla pagina Punti deboli in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="43aea-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="43aea-119">Selezione **di punti** di debolezza dal menu di spostamento per la gestione delle minacce e delle vulnerabilità in Microsoft Defender Security [Center](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="43aea-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="43aea-120">Ricerca globale</span><span class="sxs-lookup"><span data-stu-id="43aea-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="43aea-121">Menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="43aea-121">Navigation menu</span></span>

<span data-ttu-id="43aea-122">Vai al menu di spostamento per la gestione delle minacce e delle vulnerabilità e seleziona **Debolezze** per aprire l'elenco di CVE.</span><span class="sxs-lookup"><span data-stu-id="43aea-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="43aea-123">Vulnerabilità nella ricerca globale</span><span class="sxs-lookup"><span data-stu-id="43aea-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="43aea-124">Vai al menu a discesa ricerca globale.</span><span class="sxs-lookup"><span data-stu-id="43aea-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="43aea-125">Seleziona **Vulnerabilità e** chiave nell'ID CVE (Common Vulnerabilities and Exposures) che stai cercando, quindi seleziona l'icona di ricerca.</span><span class="sxs-lookup"><span data-stu-id="43aea-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="43aea-126">Viene **visualizzata** la pagina Punti deboli con le informazioni CVE che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="43aea-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="43aea-127">![Casella di ricerca globale con l'opzione a discesa "vulnerabilità" selezionata e un esempio di CVE.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="43aea-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="43aea-128">Seleziona il CVE per aprire un riquadro a comparsa con altre informazioni, tra cui la descrizione della vulnerabilità, i dettagli, le informazioni dettagliate sulle minacce e i dispositivi esposti.</span><span class="sxs-lookup"><span data-stu-id="43aea-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="43aea-129">Per visualizzare il resto delle vulnerabilità nella pagina **Punti deboli,** digitare CVE, quindi selezionare cerca.</span><span class="sxs-lookup"><span data-stu-id="43aea-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="43aea-130">Panoramica dei punti deboli</span><span class="sxs-lookup"><span data-stu-id="43aea-130">Weaknesses overview</span></span>

<span data-ttu-id="43aea-131">Correggere le vulnerabilità nei dispositivi esposti per ridurre il rischio per le risorse e l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43aea-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="43aea-132">Se la **colonna Dispositivi esposti** mostra 0, significa che non sei a rischio.</span><span class="sxs-lookup"><span data-stu-id="43aea-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![Pagina di destinazione punti deboli.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="43aea-134">Informazioni dettagliate su violazioni e minacce</span><span class="sxs-lookup"><span data-stu-id="43aea-134">Breach and threat insights</span></span>

<span data-ttu-id="43aea-135">Visualizzare eventuali informazioni dettagliate sulle violazioni e sulle minacce correlate nella **colonna Minaccia** quando le icone sono di colore rosso.</span><span class="sxs-lookup"><span data-stu-id="43aea-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="43aea-136">Assegnare sempre la priorità ai suggerimenti associati alle minacce in corso.</span><span class="sxs-lookup"><span data-stu-id="43aea-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="43aea-137">Questi suggerimenti sono contrassegnati con l'icona di analisi delle minacce ![ Disegno semplice di un bug rosso.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="43aea-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="43aea-138">e icona informazioni di violazione ![ Disegno semplice di una freccia che colpisce un obiettivo. ](images/tvm_alert_icon.png)</span><span class="sxs-lookup"><span data-stu-id="43aea-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="43aea-139">L'icona informazioni dettagliate sulle violazioni è evidenziata se nell'organizzazione è presente una vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="43aea-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="43aea-140">![Esempio di testo di informazioni dettagliate sulle violazioni che potrebbe essere visualizzato quando si passa il mouse sull'icona.</span><span class="sxs-lookup"><span data-stu-id="43aea-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="43aea-141">Questo messaggio indica che "il possibile avviso attivo è associato a questo suggerimento.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="43aea-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="43aea-142">L'icona informazioni dettagliate sulle minacce è evidenziata se sono presenti exploit associati nella vulnerabilità rilevata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43aea-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="43aea-143">Il passaggio del mouse sull'icona indica se la minaccia fa parte di un exploit kit o è connessa a campagne o gruppi di attività persistenti avanzati specifici.</span><span class="sxs-lookup"><span data-stu-id="43aea-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="43aea-144">Se disponibile, è disponibile un collegamento a un report di Threat Analytics con notizie, divulgazioni o avvisi di sicurezza correlati allo sfruttamento zero-day.</span><span class="sxs-lookup"><span data-stu-id="43aea-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![Testo di informazioni dettagliate sulle minacce che potrebbe essere visualizzato al passaggio del mouse sull'icona.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="43aea-147">Acquisire informazioni dettagliate sulla vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43aea-147">Gain vulnerability insights</span></span>

<span data-ttu-id="43aea-148">Se si seleziona un CVE, verrà aperto un riquadro a comparsa con ulteriori informazioni, ad esempio la descrizione della vulnerabilità, i dettagli, le informazioni dettagliate sulle minacce e i dispositivi esposti.</span><span class="sxs-lookup"><span data-stu-id="43aea-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="43aea-149">La categoria "Funzionalità del sistema operativo" viene visualizzata negli scenari pertinenti</span><span class="sxs-lookup"><span data-stu-id="43aea-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="43aea-150">Puoi passare alla raccomandazione di sicurezza correlata per ogni CVE con dispositivo esposto</span><span class="sxs-lookup"><span data-stu-id="43aea-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![Esempio di riquadro a comparsa punto debole.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="43aea-152">Software non supportato</span><span class="sxs-lookup"><span data-stu-id="43aea-152">Software that isn't supported</span></span>

<span data-ttu-id="43aea-153">CvEs per software attualmente non supportato dalle minacce & la gestione delle vulnerabilità è ancora presente nella pagina Punti deboli.</span><span class="sxs-lookup"><span data-stu-id="43aea-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="43aea-154">Poiché il software non è supportato, saranno disponibili solo dati limitati.</span><span class="sxs-lookup"><span data-stu-id="43aea-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="43aea-155">Le informazioni sui dispositivi esposti non saranno disponibili per i CVE con software non supportato.</span><span class="sxs-lookup"><span data-stu-id="43aea-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="43aea-156">Filtra per software non supportato selezionando l'opzione "Non disponibile" nella sezione "Dispositivi esposti".</span><span class="sxs-lookup"><span data-stu-id="43aea-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![Filtro dei dispositivi esposti.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="43aea-158">Visualizzare le voci CVE (Common Vulnerabilities and Exposures) in altre posizioni</span><span class="sxs-lookup"><span data-stu-id="43aea-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="43aea-159">Software più vulnerabile nel dashboard</span><span class="sxs-lookup"><span data-stu-id="43aea-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="43aea-160">Vai al [dashboard di gestione delle minacce e delle](tvm-dashboard-insights.md) vulnerabilità e scorri verso il basso fino al widget Software più **vulnerabile.**</span><span class="sxs-lookup"><span data-stu-id="43aea-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="43aea-161">Verrà visualizzato il numero di vulnerabilità riscontrate in ogni software, insieme alle informazioni sulle minacce e a una visualizzazione di alto livello dell'esposizione dei dispositivi nel tempo.</span><span class="sxs-lookup"><span data-stu-id="43aea-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![Scheda software più vulnerabile con quattro colonne: software, punti deboli, minacce, dispositivi esposti.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="43aea-163">Selezionare il software che si desidera analizzare per passare a una pagina di drill-down.</span><span class="sxs-lookup"><span data-stu-id="43aea-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="43aea-164">Selezionare la **scheda Vulnerabilità individuate.**</span><span class="sxs-lookup"><span data-stu-id="43aea-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="43aea-165">Selezionare la vulnerabilità che si desidera analizzare per ulteriori informazioni sui dettagli della vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43aea-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Panoramica del drill-down di Windows Server 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="43aea-167">Individuare le vulnerabilità nella pagina del dispositivo</span><span class="sxs-lookup"><span data-stu-id="43aea-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="43aea-168">Visualizza le informazioni sui punti deboli correlati nella pagina del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43aea-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="43aea-169">Vai alla barra dei menu di spostamento di Microsoft Defender Security Center, quindi seleziona l'icona del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43aea-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="43aea-170">Verrà **visualizzata la pagina elenco** Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="43aea-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="43aea-171">Nella pagina **elenco Dispositivi** seleziona il nome del dispositivo che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="43aea-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![Elenco dei dispositivi con il dispositivo selezionato da analizzare.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="43aea-173">La pagina del dispositivo si aprirà con i dettagli e le opzioni di risposta per il dispositivo che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="43aea-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="43aea-174">Selezionare **Vulnerabilità individuate.**</span><span class="sxs-lookup"><span data-stu-id="43aea-174">Select **Discovered vulnerabilities**.</span></span>

    ![Pagina del dispositivo con dettagli e opzioni di risposta.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="43aea-176">Seleziona la vulnerabilità che vuoi analizzare per aprire un riquadro a comparsa con i dettagli CVE, ad esempio: descrizione della vulnerabilità, informazioni dettagliate sulle minacce e logica di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="43aea-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="43aea-177">Logica di rilevamento CVE</span><span class="sxs-lookup"><span data-stu-id="43aea-177">CVE Detection logic</span></span>

<span data-ttu-id="43aea-178">Analogamente alla prova software, ora mostriamo la logica di rilevamento applicata a un dispositivo per dimostrare che è vulnerabile.</span><span class="sxs-lookup"><span data-stu-id="43aea-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="43aea-179">La nuova sezione è denominata "Logica di rilevamento" (in qualsiasi vulnerabilità individuata nella pagina del dispositivo) e mostra la logica di rilevamento e l'origine.</span><span class="sxs-lookup"><span data-stu-id="43aea-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="43aea-180">La categoria "Funzionalità del sistema operativo" viene visualizzata anche negli scenari pertinenti.</span><span class="sxs-lookup"><span data-stu-id="43aea-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="43aea-181">Un CVE influisce sui dispositivi che eseguono un sistema operativo vulnerabile solo se è abilitato uno specifico componente del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="43aea-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="43aea-182">Supponiamo che Windows Server 2019 abbia una vulnerabilità nel suo componente DNS.</span><span class="sxs-lookup"><span data-stu-id="43aea-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="43aea-183">Con questa nuova funzionalità, questo CVE verrà collegato solo ai dispositivi Windows Server 2019 con la funzionalità DNS abilitata nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="43aea-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![Esempio di logica di rilevamento che elenca il software rilevato nel dispositivo e nei KB.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="43aea-185">Imprecisione dei report</span><span class="sxs-lookup"><span data-stu-id="43aea-185">Report inaccuracy</span></span>

<span data-ttu-id="43aea-186">Segnalare un falso positivo quando vengono visualizzate informazioni vaghe, imprecise o incomplete.</span><span class="sxs-lookup"><span data-stu-id="43aea-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="43aea-187">È inoltre possibile segnalare suggerimenti sulla sicurezza che sono già stati corretti.</span><span class="sxs-lookup"><span data-stu-id="43aea-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="43aea-188">Aprire CVE nella pagina Punti deboli.</span><span class="sxs-lookup"><span data-stu-id="43aea-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="43aea-189">Selezionare **Report inaccuracy e** verrà aperto un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="43aea-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="43aea-190">Seleziona la categoria di imprecisione dal menu a discesa e inserisci l'indirizzo di posta elettronica e i dettagli dell'imprecisione.</span><span class="sxs-lookup"><span data-stu-id="43aea-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="43aea-191">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="43aea-191">Select **Submit**.</span></span> <span data-ttu-id="43aea-192">Il feedback viene inviato immediatamente agli esperti di gestione delle minacce e delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="43aea-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="43aea-193">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="43aea-193">Related articles</span></span>

- [<span data-ttu-id="43aea-194">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43aea-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="43aea-195">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="43aea-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="43aea-196">Inventario software</span><span class="sxs-lookup"><span data-stu-id="43aea-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="43aea-197">Dashboard Dati analitici</span><span class="sxs-lookup"><span data-stu-id="43aea-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="43aea-198">Visualizzare e organizzare l'elenco di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="43aea-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
