---
title: Filtro contenuti Web
description: Usare il filtro contenuto Web in Microsoft Defender for Endpoint per tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto.
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, monitoraggio, report, schede, elenco di domini, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c7b39b600af2fed130a0b78a590740a8bc063f50
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861696"
---
# <a name="web-content-filtering"></a><span data-ttu-id="d974f-104">Filtro contenuti Web</span><span class="sxs-lookup"><span data-stu-id="d974f-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d974f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d974f-105">**Applies to:**</span></span>
- [<span data-ttu-id="d974f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d974f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d974f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d974f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="d974f-108">**Il filtro contenuto Web è attualmente in anteprima pubblica**</span><span class="sxs-lookup"><span data-stu-id="d974f-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="d974f-109">Questa versione di anteprima viene fornita senza un contratto di servizio e non è consigliata per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="d974f-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="d974f-110">Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.</span><span class="sxs-lookup"><span data-stu-id="d974f-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="d974f-111">Per altre informazioni, vedi [Funzionalità di anteprima di Microsoft Defender per Endpoint.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="d974f-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

> [!TIP]
> <span data-ttu-id="d974f-112">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d974f-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d974f-113">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d974f-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="d974f-114">Il filtro contenuto Web fa parte [delle funzionalità di protezione Web](web-protection-overview.md) in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d974f-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d974f-115">Consente all'organizzazione di tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto.</span><span class="sxs-lookup"><span data-stu-id="d974f-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="d974f-116">Molti di questi siti Web, sebbene non dannosi, potrebbero essere problematici a causa delle normative di conformità, dell'utilizzo della larghezza di banda o di altri problemi.</span><span class="sxs-lookup"><span data-stu-id="d974f-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="d974f-117">Configura i criteri tra i gruppi di dispositivi per bloccare determinate categorie.</span><span class="sxs-lookup"><span data-stu-id="d974f-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="d974f-118">Il blocco di una categoria impedisce agli utenti all'interno di gruppi di dispositivi specificati di accedere agli URL associati alla categoria.</span><span class="sxs-lookup"><span data-stu-id="d974f-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="d974f-119">Per qualsiasi categoria non bloccata, gli URL vengono controllati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d974f-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="d974f-120">Gli utenti possono accedere agli URL senza interruzioni e verranno raccolte statistiche di accesso per creare una decisione di criteri più personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d974f-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="d974f-121">Gli utenti visualizzeranno una notifica di blocco se un elemento nella pagina che sta visualizzando sta effettuando chiamate a una risorsa bloccata.</span><span class="sxs-lookup"><span data-stu-id="d974f-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="d974f-122">Il filtro contenuto Web è disponibile nei principali Web browser, con blocchi eseguiti da Windows Defender SmartScreen (Microsoft Edge) e Network Protection (Chrome, Firefox, Brave e Opera).</span><span class="sxs-lookup"><span data-stu-id="d974f-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="d974f-123">Per ulteriori informazioni sul supporto dei browser, vedere la sezione prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="d974f-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="d974f-124">Riepilogo dei vantaggi:</span><span class="sxs-lookup"><span data-stu-id="d974f-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="d974f-125">Agli utenti viene impedito l'accesso a siti Web in categorie bloccate, indipendentemente dal fatto che si esezionino in locale o fuori sede</span><span class="sxs-lookup"><span data-stu-id="d974f-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="d974f-126">Il team di sicurezza può distribuire comodamente i criteri a gruppi di utenti usando i gruppi di dispositivi definiti in [Microsoft Defender per le impostazioni di](/microsoft-365/security/defender-endpoint/rbac) controllo di accesso basato sui ruoli di Endpoint</span><span class="sxs-lookup"><span data-stu-id="d974f-126">Your security team can conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="d974f-127">Il team di sicurezza può accedere ai report Web nella stessa posizione centrale, con visibilità sui blocchi effettivi e sull'utilizzo web</span><span class="sxs-lookup"><span data-stu-id="d974f-127">Your security team can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="d974f-128">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="d974f-128">User experience</span></span>

<span data-ttu-id="d974f-129">L'esperienza di blocco per i browser supportati da terze parti è fornita da Protezione di rete, che fornisce un avviso popup a livello di sistema che informa l'utente di una connessione bloccata.</span><span class="sxs-lookup"><span data-stu-id="d974f-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> <span data-ttu-id="d974f-130">Per un'esperienza più facile da usare nel browser, prendi in considerazione l'uso di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="d974f-130">For a more user-friendly, in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d974f-131">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d974f-131">Prerequisites</span></span>

<span data-ttu-id="d974f-132">Prima di provare questa funzionalità, assicurarsi di soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d974f-132">Before trying out this feature, make sure you meet the following requirements:</span></span>

- <span data-ttu-id="d974f-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security componente aggiuntivo o la licenza autonoma di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d974f-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security add-on or the Microsoft Defender for Endpoint standalone license.</span></span> 
- <span data-ttu-id="d974f-134">Accesso a Microsoft Defender Security Center portale ( https://securitycenter.windows.com) .</span><span class="sxs-lookup"><span data-stu-id="d974f-134">Access to Microsoft Defender Security Center portal (https://securitycenter.windows.com).</span></span>
- <span data-ttu-id="d974f-135">Dispositivi che Windows 10'aggiornamento dell'anniversario (versione 1607) o successiva con l'aggiornamento MoCAMP più recente.</span><span class="sxs-lookup"><span data-stu-id="d974f-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>
- <span data-ttu-id="d974f-136">Windows Defender SmartScreen e Protezione di rete abilitati.</span><span class="sxs-lookup"><span data-stu-id="d974f-136">Windows Defender SmartScreen and Network protection enabled.</span></span>


## <a name="data-handling"></a><span data-ttu-id="d974f-137">Gestione dati</span><span class="sxs-lookup"><span data-stu-id="d974f-137">Data handling</span></span>

<span data-ttu-id="d974f-138">I dati vengono archiviati nell'area selezionata come parte delle impostazioni di gestione dei dati di [Microsoft Defender for Endpoint.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="d974f-138">Data is stored in the region that was selected as part of your [Microsoft Defender for Endpoint data handling settings](data-storage-privacy.md).</span></span> <span data-ttu-id="d974f-139">I dati non lasceranno il data center in tale area.</span><span class="sxs-lookup"><span data-stu-id="d974f-139">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="d974f-140">Inoltre, i dati non verranno condivisi con terze parti, inclusi i provider di dati.</span><span class="sxs-lookup"><span data-stu-id="d974f-140">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="d974f-141">Attivare il filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="d974f-141">Turn on web content filtering</span></span>

<span data-ttu-id="d974f-142">Dal menu di spostamento a sinistra, **selezionare** Impostazioni  >  **Funzionalità**  >  **avanzate generali.**</span><span class="sxs-lookup"><span data-stu-id="d974f-142">From the left-hand navigation menu, select **Settings** > **General** > **Advanced Features**.</span></span> <span data-ttu-id="d974f-143">Scorrere verso il basso fino a visualizzare la voce relativa al filtro **contenuto Web.**</span><span class="sxs-lookup"><span data-stu-id="d974f-143">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="d974f-144">Imposta l'interruttore **su Attivato** **e Salva preferenze.**</span><span class="sxs-lookup"><span data-stu-id="d974f-144">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="d974f-145">Configurare i criteri di filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="d974f-145">Configure web content filtering policies</span></span>

<span data-ttu-id="d974f-146">I criteri di filtro del contenuto Web specificano quali categorie di siti sono bloccate in quali gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d974f-146">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="d974f-147">Per gestire i criteri, passare **a** Regole Impostazioni  >  **filtro**  >  **contenuto Web**.</span><span class="sxs-lookup"><span data-stu-id="d974f-147">To manage the policies, go to **Settings** > **Rules** > **Web content filtering**.</span></span>

<span data-ttu-id="d974f-148">Usa il filtro per individuare i criteri che contengono determinate categorie bloccate o che vengono applicati a gruppi di dispositivi specifici.</span><span class="sxs-lookup"><span data-stu-id="d974f-148">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="d974f-149">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="d974f-149">Create a policy</span></span>

<span data-ttu-id="d974f-150">Per aggiungere un nuovo criterio:</span><span class="sxs-lookup"><span data-stu-id="d974f-150">To add a new policy:</span></span>

1. <span data-ttu-id="d974f-151">Selezionare **Aggiungi criterio** nella pagina Filtro contenuto **Web** in **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="d974f-151">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>

2. <span data-ttu-id="d974f-152">Specificare un nome.</span><span class="sxs-lookup"><span data-stu-id="d974f-152">Specify a name.</span></span>

3. <span data-ttu-id="d974f-153">Selezionare le categorie da bloccare.</span><span class="sxs-lookup"><span data-stu-id="d974f-153">Select the categories to block.</span></span> <span data-ttu-id="d974f-154">Utilizzare l'icona espandi per espandere completamente ogni categoria padre e selezionare categorie di contenuto Web specifiche.</span><span class="sxs-lookup"><span data-stu-id="d974f-154">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>

4. <span data-ttu-id="d974f-155">Specificare l'ambito dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d974f-155">Specify the policy scope.</span></span> <span data-ttu-id="d974f-156">Seleziona i gruppi di dispositivi per specificare dove applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="d974f-156">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="d974f-157">Solo i dispositivi nei gruppi di dispositivi selezionati non potranno accedere ai siti Web nelle categorie selezionate.</span><span class="sxs-lookup"><span data-stu-id="d974f-157">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>

5. <span data-ttu-id="d974f-158">Esaminare il riepilogo e salvare il criterio.</span><span class="sxs-lookup"><span data-stu-id="d974f-158">Review the summary and save the policy.</span></span> <span data-ttu-id="d974f-159">L'aggiornamento dei criteri può richiedere fino a 2 ore per l'applicazione ai dispositivi selezionati.</span><span class="sxs-lookup"><span data-stu-id="d974f-159">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

> [!NOTE]
> - <span data-ttu-id="d974f-160">Puoi distribuire un criterio senza selezionare alcuna categoria in un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d974f-160">You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="d974f-161">Questa azione creerà un criterio solo di controllo, per aiutarti a comprendere il comportamento dell'utente prima di creare un criterio di blocco.</span><span class="sxs-lookup"><span data-stu-id="d974f-161">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>
> - <span data-ttu-id="d974f-162">Se stai rimuovendo un criterio o modificando i gruppi di dispositivi contemporaneamente, questo potrebbe causare un ritardo nella distribuzione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d974f-162">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>
> - <span data-ttu-id="d974f-163">Il blocco della categoria "Non classificato" può causare risultati imprevisti e indesiderati.</span><span class="sxs-lookup"><span data-stu-id="d974f-163">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="d974f-164">Consentire siti Web specifici</span><span class="sxs-lookup"><span data-stu-id="d974f-164">Allow specific websites</span></span>

<span data-ttu-id="d974f-165">È possibile ignorare la categoria bloccata nel filtro contenuto Web per consentire un singolo sito creando un criterio indicatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d974f-165">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="d974f-166">Il criterio indicatore personalizzato sostituisce il criterio di filtro contenuto Web quando viene applicato al gruppo di dispositivi in questione.</span><span class="sxs-lookup"><span data-stu-id="d974f-166">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="d974f-167">Creare un indicatore personalizzato nel Microsoft Defender Security Center andando a Impostazioni  >    >  **URL indicatori/Elemento aggiunta**  >  **dominio**.</span><span class="sxs-lookup"><span data-stu-id="d974f-167">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**.</span></span>

2. <span data-ttu-id="d974f-168">Immettere il dominio del sito.</span><span class="sxs-lookup"><span data-stu-id="d974f-168">Enter the domain of the site.</span></span>

3. <span data-ttu-id="d974f-169">Impostare l'azione del criterio su **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="d974f-169">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="d974f-170">Segnalazione di imprecisioni</span><span class="sxs-lookup"><span data-stu-id="d974f-170">Reporting inaccuracies</span></span>

<span data-ttu-id="d974f-171">Se si verifica un dominio categorizzato in modo errato, è possibile segnalare imprecisioni direttamente dalla pagina dei report filtro contenuto Web.</span><span class="sxs-lookup"><span data-stu-id="d974f-171">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="d974f-172">Questa funzionalità è disponibile solo nel nuovo centro sicurezza Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d974f-172">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="d974f-173">Per segnalare un'imprecisione, passare **a** Report Protezione Web Protezione  >    >  **Web Dettagli filtro contenuto**  >  **Domini.**</span><span class="sxs-lookup"><span data-stu-id="d974f-173">To report an inaccuracy, navigate to **Reports** > **Web protection** > **Web Content Filtering Details** > **Domains**.</span></span> <span data-ttu-id="d974f-174">Nella scheda domini dei report Filtro contenuto Web verrà visualizzato un pulsante con i puntini di sospensione accanto a ognuno dei domini.</span><span class="sxs-lookup"><span data-stu-id="d974f-174">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="d974f-175">Posizionare il puntatore del mouse sui puntini di sospensione e selezionare **Segnala imprecisione.**</span><span class="sxs-lookup"><span data-stu-id="d974f-175">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="d974f-176">Verrà aperto un pannello in cui è possibile selezionare la priorità e aggiungere ulteriori dettagli, ad esempio la categoria suggerita per la ri categorizzazione.</span><span class="sxs-lookup"><span data-stu-id="d974f-176">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="d974f-177">Dopo aver completato il modulo, selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="d974f-177">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="d974f-178">Il team esamina la richiesta entro un giorno lavorativo.</span><span class="sxs-lookup"><span data-stu-id="d974f-178">Our team will review the request within one business day.</span></span> <span data-ttu-id="d974f-179">Per sbloccare immediatamente, crea un [indicatore consenti personalizzato.](indicator-ip-domain.md)</span><span class="sxs-lookup"><span data-stu-id="d974f-179">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="d974f-180">Schede e dettagli del filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="d974f-180">Web content filtering cards and details</span></span>

<span data-ttu-id="d974f-181">Selezionare **Report**  >  **Protezione Web per** visualizzare le schede con informazioni sul filtro contenuto Web e sulla protezione dalle minacce Web.</span><span class="sxs-lookup"><span data-stu-id="d974f-181">Select **Reports** > **Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="d974f-182">Nelle schede seguenti vengono fornite informazioni di riepilogo sul filtro contenuto Web.</span><span class="sxs-lookup"><span data-stu-id="d974f-182">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="d974f-183">Attività Web per categoria</span><span class="sxs-lookup"><span data-stu-id="d974f-183">Web activity by category</span></span>

<span data-ttu-id="d974f-184">In questa scheda sono elencate le categorie di contenuto Web padre con l'aumento o la riduzione maggiori del numero di tentativi di accesso.</span><span class="sxs-lookup"><span data-stu-id="d974f-184">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="d974f-185">Comprendere i cambiamenti drastici dei modelli di attività Web nell'organizzazione degli ultimi 30 giorni, 3 mesi o 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="d974f-185">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="d974f-186">Selezionare un nome di categoria per visualizzare ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="d974f-186">Select a category name to view more information.</span></span>

<span data-ttu-id="d974f-187">Nei primi 30 giorni di utilizzo di questa funzionalità, l'organizzazione potrebbe non disporre di dati sufficienti per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="d974f-187">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![Immagine dell'attività Web per scheda categoria](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="d974f-189">Scheda di riepilogo filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="d974f-189">Web content filtering  summary card</span></span>

<span data-ttu-id="d974f-190">Questa scheda visualizza la distribuzione dei tentativi di accesso bloccati tra le diverse categorie di contenuto Web padre.</span><span class="sxs-lookup"><span data-stu-id="d974f-190">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="d974f-191">Selezionare una delle barre colorate per visualizzare ulteriori informazioni su una categoria Web padre specifica.</span><span class="sxs-lookup"><span data-stu-id="d974f-191">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Immagine della scheda di riepilogo del filtro contenuto Web](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="d974f-193">Scheda riepilogativo attività Web</span><span class="sxs-lookup"><span data-stu-id="d974f-193">Web activity summary card</span></span>

<span data-ttu-id="d974f-194">Questa scheda visualizza il numero totale di richieste di contenuto Web in tutti gli URL.</span><span class="sxs-lookup"><span data-stu-id="d974f-194">This card displays the total number of requests for web content in all URLs.</span></span>

![Immagine della scheda di riepilogo dell'attività Web](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="d974f-196">Visualizzare i dettagli della scheda</span><span class="sxs-lookup"><span data-stu-id="d974f-196">View card details</span></span>

<span data-ttu-id="d974f-197">È possibile accedere ai **dettagli del report** per ogni scheda selezionando una riga di tabella o una barra colorata dal grafico nella scheda.</span><span class="sxs-lookup"><span data-stu-id="d974f-197">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="d974f-198">La pagina dei dettagli del report per ogni scheda contiene dati statistici dettagliati sulle categorie di contenuto Web, sui domini di siti Web e sui gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d974f-198">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Immagine dei dettagli del report di protezione Web](images/web-protection-report-details.png)

- <span data-ttu-id="d974f-200">**Categorie Web**: elenca le categorie di contenuto Web che hanno avuto tentativi di accesso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d974f-200">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="d974f-201">Selezionare una categoria specifica per aprire un riquadro a comparsa di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="d974f-201">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="d974f-202">**Domini**: elenca i domini Web a cui è stato eseguito l'accesso o che sono stati bloccati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d974f-202">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="d974f-203">Selezionare un dominio specifico per visualizzare informazioni dettagliate su tale dominio.</span><span class="sxs-lookup"><span data-stu-id="d974f-203">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="d974f-204">**Gruppi di dispositivi**: elenca tutti i gruppi di dispositivi che hanno generato attività Web nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d974f-204">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="d974f-205">Usa il filtro dell'intervallo di tempo nella parte superiore sinistra della pagina per selezionare un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d974f-205">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="d974f-206">È inoltre possibile filtrare le informazioni o personalizzare le colonne.</span><span class="sxs-lookup"><span data-stu-id="d974f-206">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="d974f-207">Selezionare una riga per aprire un riquadro a comparsa con ulteriori informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="d974f-207">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="d974f-208">Errori e problemi</span><span class="sxs-lookup"><span data-stu-id="d974f-208">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="d974f-209">Limitazioni e problemi noti in questa anteprima</span><span class="sxs-lookup"><span data-stu-id="d974f-209">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="d974f-210">Solo Microsoft Edge è supportata se la configurazione del sistema operativo del dispositivo è Server (**cmd**  >  **Systeminfo**  >  **OS Configuration**).</span><span class="sxs-lookup"><span data-stu-id="d974f-210">Only Microsoft Edge is supported if your device's OS configuration is Server (**cmd** > **Systeminfo** > **OS Configuration**).</span></span> <span data-ttu-id="d974f-211">Protezione di rete è supportata solo in modalità Inspect nei dispositivi server, responsabile della protezione del traffico tra i browser di terze parti supportati.</span><span class="sxs-lookup"><span data-stu-id="d974f-211">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="d974f-212">I dispositivi non assegnati avranno dati non corretti visualizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="d974f-212">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="d974f-213">Nel **pivot Dettagli rapporto**  >  **Gruppi di dispositivi** potrebbe essere visualizzata una riga con un campo Gruppo di dispositivi vuoto.</span><span class="sxs-lookup"><span data-stu-id="d974f-213">In the **Report details** > **Device groups** pivot, you might see a row with a blank Device Group field.</span></span> <span data-ttu-id="d974f-214">Questo gruppo contiene i dispositivi non assegnati prima di essere inseriti nel gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="d974f-214">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="d974f-215">Il report per questa riga potrebbe non contenere un conteggio accurato dei dispositivi o dei conteggi di accesso.</span><span class="sxs-lookup"><span data-stu-id="d974f-215">The report for this row might not contain an accurate count of devices or access counts.</span></span>

- <span data-ttu-id="d974f-216">I report filtro contenuto Web sono attualmente limitati alla visualizzazione dei primi 5.000 record.</span><span class="sxs-lookup"><span data-stu-id="d974f-216">Web Content Filtering reports are currently limited to showing the top 5000 records.</span></span> <span data-ttu-id="d974f-217">Ad esempio, il report Domini mostrerà solo un massimo di 5000 domini principali per una determinata query di filtro, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="d974f-217">For example, the Domains report will only show a maximum of the top 5000 domains for a given filter query, if applicable.</span></span> 



- [<span data-ttu-id="d974f-218">Panoramica protezione Web</span><span class="sxs-lookup"><span data-stu-id="d974f-218">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="d974f-219">Protezione dalle minacce sul Web</span><span class="sxs-lookup"><span data-stu-id="d974f-219">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="d974f-220">Monitorare la sicurezza sul Web</span><span class="sxs-lookup"><span data-stu-id="d974f-220">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="d974f-221">Rispondere alle minacce sul Web</span><span class="sxs-lookup"><span data-stu-id="d974f-221">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="d974f-222">Requisiti per Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="d974f-222">Requirements for Network Protection</span></span>](web-content-filtering.md)

