---
title: Filtro contenuto Web
description: Usare il filtro contenuto Web in Microsoft Defender ATP per tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto.
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, monitoraggio, report, schede, elenco di domini, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dd1b21b306d40ab03fa518f48c8a0bc985191f69
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063722"
---
# <a name="web-content-filtering"></a><span data-ttu-id="5dc9b-104">Filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5dc9b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5dc9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="5dc9b-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5dc9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="5dc9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5dc9b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="5dc9b-108">**Il filtro contenuto Web è attualmente in anteprima pubblica**</span><span class="sxs-lookup"><span data-stu-id="5dc9b-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="5dc9b-109">Questa versione di anteprima viene fornita senza un contratto di servizio e non è consigliata per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="5dc9b-110">Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="5dc9b-111">Per altre informazioni, vedi [Funzionalità di anteprima di Microsoft Defender per Endpoint.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="5dc9b-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="5dc9b-112">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5dc9b-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5dc9b-113">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="5dc9b-114">Il filtro contenuto Web fa parte [delle funzionalità di protezione Web](web-protection-overview.md) in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5dc9b-115">Consente all'organizzazione di tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="5dc9b-116">Molti di questi siti Web, sebbene non dannosi, potrebbero essere problematici a causa delle normative di conformità, dell'utilizzo della larghezza di banda o di altri problemi.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="5dc9b-117">Configura i criteri tra i gruppi di dispositivi per bloccare determinate categorie.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="5dc9b-118">Il blocco di una categoria impedisce agli utenti all'interno di gruppi di dispositivi specificati di accedere agli URL associati alla categoria.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="5dc9b-119">Per qualsiasi categoria non bloccata, gli URL vengono controllati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="5dc9b-120">Gli utenti possono accedere agli URL senza interruzioni e verranno raccolte statistiche di accesso per creare una decisione di criteri più personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="5dc9b-121">Gli utenti visualizzeranno una notifica di blocco se un elemento nella pagina che sta visualizzando sta effettuando chiamate a una risorsa bloccata.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="5dc9b-122">Il filtro contenuto Web è disponibile nei principali Web browser, con blocchi eseguiti da Windows Defender SmartScreen (Microsoft Edge) e Network Protection (Chrome, Firefox, Brave e Opera).</span><span class="sxs-lookup"><span data-stu-id="5dc9b-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="5dc9b-123">Per ulteriori informazioni sul supporto dei browser, vedere la sezione prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="5dc9b-124">Riepilogo dei vantaggi:</span><span class="sxs-lookup"><span data-stu-id="5dc9b-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="5dc9b-125">Agli utenti viene impedito l'accesso a siti Web in categorie bloccate, indipendentemente dal fatto che si esezionino in locale o fuori sede</span><span class="sxs-lookup"><span data-stu-id="5dc9b-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="5dc9b-126">Distribuire comodamente i criteri a gruppi di utenti usando i gruppi di dispositivi definiti in [Microsoft Defender per le impostazioni di](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac) controllo di accesso basato sui ruoli di Endpoint</span><span class="sxs-lookup"><span data-stu-id="5dc9b-126">Conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="5dc9b-127">Accedere ai report Web nella stessa posizione centrale, con visibilità sui blocchi effettivi e sull'utilizzo web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-127">Access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="5dc9b-128">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="5dc9b-128">User experience</span></span>

<span data-ttu-id="5dc9b-129">L'esperienza di blocco per i browser supportati da terze parti è fornita da Protezione di rete, che fornisce un avviso popup a livello di sistema che informa l'utente di una connessione bloccata.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> 

<span data-ttu-id="5dc9b-130">Per un'esperienza più facile da usare nel browser, prendi in considerazione l'uso di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-130">For a more user-friendly in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5dc9b-131">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5dc9b-131">Prerequisites</span></span>

<span data-ttu-id="5dc9b-132">Prima di provare questa funzionalità, verificare di disporre dei requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5dc9b-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="5dc9b-133">Licenza di Windows 10 Enterprise E5 O componente aggiuntivo Microsoft 365 E3 + Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-133">Windows 10 Enterprise E5 license OR Microsoft 365 E3 + Microsoft 365 E5 Security add-on.</span></span>
- <span data-ttu-id="5dc9b-134">Accesso al portale di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="5dc9b-134">Access to Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="5dc9b-135">Dispositivi che eseguono l'aggiornamento dell'anniversario di Windows 10 (versione 1607) o successiva con l'aggiornamento MoCAMP più recente.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

<span data-ttu-id="5dc9b-136">Se Windows Defender SmartScreen non è attivato, Protezione di rete prenderà il controllo del blocco.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-136">If Windows Defender SmartScreen isn't turned on, Network Protection will take over the blocking.</span></span> <span data-ttu-id="5dc9b-137">Richiede [l'abilitazione di Protezione](enable-network-protection.md) di rete nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-137">It requires [enabling Network Protection](enable-network-protection.md) on the device.</span></span> <span data-ttu-id="5dc9b-138">Chrome, Firefox, Brave e Opera sono attualmente browser di terze parti in cui questa funzionalità è abilitata.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-138">Chrome, Firefox, Brave, and Opera are currently 3rd party browsers in which this feature is enabled.</span></span>

## <a name="data-handling"></a><span data-ttu-id="5dc9b-139">Gestione dei dati</span><span class="sxs-lookup"><span data-stu-id="5dc9b-139">Data handling</span></span>

<span data-ttu-id="5dc9b-140">Seguiremo qualsiasi area geografica hai scelto di usare come parte delle impostazioni di gestione dei dati di [Microsoft Defender for Endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="5dc9b-140">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy).</span></span> <span data-ttu-id="5dc9b-141">I dati non lasceranno il data center in tale area.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-141">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="5dc9b-142">Inoltre, i dati non verranno condivisi con terze parti, inclusi i provider di dati.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-142">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="5dc9b-143">Attivare il filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-143">Turn on web content filtering</span></span>

<span data-ttu-id="5dc9b-144">Dal menu di spostamento a sinistra, selezionare **Impostazioni > generale > funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-144">From the left-hand navigation menu, select **Settings > General > Advanced Features**.</span></span> <span data-ttu-id="5dc9b-145">Scorrere verso il basso fino a visualizzare la voce relativa al filtro **contenuto Web.**</span><span class="sxs-lookup"><span data-stu-id="5dc9b-145">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="5dc9b-146">Imposta l'interruttore **su Attivato** **e Salva preferenze.**</span><span class="sxs-lookup"><span data-stu-id="5dc9b-146">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="5dc9b-147">Configurare i criteri di filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-147">Configure web content filtering policies</span></span>

<span data-ttu-id="5dc9b-148">I criteri di filtro del contenuto Web specificano quali categorie di siti sono bloccate in quali gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-148">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="5dc9b-149">Per gestire i criteri, passare a **Impostazioni > Regole > filtro contenuto Web**.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-149">To manage the policies, go to **Settings > Rules > Web content filtering**.</span></span>

<span data-ttu-id="5dc9b-150">Usa il filtro per individuare i criteri che contengono determinate categorie bloccate o che vengono applicati a gruppi di dispositivi specifici.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-150">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="5dc9b-151">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="5dc9b-151">Create a policy</span></span>

<span data-ttu-id="5dc9b-152">Per aggiungere un nuovo criterio:</span><span class="sxs-lookup"><span data-stu-id="5dc9b-152">To add a new policy:</span></span>

1. <span data-ttu-id="5dc9b-153">Selezionare **Aggiungi criterio** nella pagina Filtro contenuto **Web** in **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-153">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>
2. <span data-ttu-id="5dc9b-154">Specificare un nome.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-154">Specify a name.</span></span>
3. <span data-ttu-id="5dc9b-155">Selezionare le categorie da bloccare.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-155">Select the categories to block.</span></span> <span data-ttu-id="5dc9b-156">Utilizzare l'icona espandi per espandere completamente ogni categoria padre e selezionare categorie di contenuto Web specifiche.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-156">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>
4. <span data-ttu-id="5dc9b-157">Specificare l'ambito dei criteri.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-157">Specify the policy scope.</span></span> <span data-ttu-id="5dc9b-158">Seleziona i gruppi di dispositivi per specificare dove applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-158">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="5dc9b-159">Solo i dispositivi nei gruppi di dispositivi selezionati non potranno accedere ai siti Web nelle categorie selezionate.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-159">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>
5. <span data-ttu-id="5dc9b-160">Esaminare il riepilogo e salvare il criterio.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-160">Review the summary and save the policy.</span></span> <span data-ttu-id="5dc9b-161">L'aggiornamento dei criteri può richiedere fino a 2 ore per l'applicazione ai dispositivi selezionati.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-161">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

<span data-ttu-id="5dc9b-162">Suggerimento: puoi distribuire un criterio senza selezionare alcuna categoria in un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-162">Tip: You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="5dc9b-163">Questa azione creerà un criterio solo di controllo, per aiutarti a comprendere il comportamento dell'utente prima di creare un criterio di blocco.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-163">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="5dc9b-164">Se stai rimuovendo un criterio o modificando i gruppi di dispositivi contemporaneamente, questo potrebbe causare un ritardo nella distribuzione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-164">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="5dc9b-165">Il blocco della categoria "Non classificato" può causare risultati imprevisti e indesiderati.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-165">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="5dc9b-166">Consentire siti Web specifici</span><span class="sxs-lookup"><span data-stu-id="5dc9b-166">Allow specific websites</span></span>

<span data-ttu-id="5dc9b-167">È possibile ignorare la categoria bloccata nel filtro contenuto Web per consentire un singolo sito creando un criterio indicatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-167">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="5dc9b-168">Il criterio indicatore personalizzato sostituisce il criterio di filtro contenuto Web quando viene applicato al gruppo di dispositivi in questione.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-168">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="5dc9b-169">Creare un indicatore personalizzato in Microsoft Defender Security Center andando a **Impostazioni**  >    >  **Indicatori URL/Elemento aggiunta**  >  **dominio**</span><span class="sxs-lookup"><span data-stu-id="5dc9b-169">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**</span></span>
2. <span data-ttu-id="5dc9b-170">Immettere il dominio del sito</span><span class="sxs-lookup"><span data-stu-id="5dc9b-170">Enter the domain of the site</span></span>
3. <span data-ttu-id="5dc9b-171">Impostare l'azione del criterio su **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-171">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="5dc9b-172">Segnalazione di imprecisioni</span><span class="sxs-lookup"><span data-stu-id="5dc9b-172">Reporting inaccuracies</span></span>

<span data-ttu-id="5dc9b-173">Se si verifica un dominio categorizzato in modo errato, è possibile segnalare imprecisioni direttamente dalla pagina dei report filtro contenuto Web.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-173">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="5dc9b-174">Questa funzionalità è disponibile solo nel nuovo Centro sicurezza Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5dc9b-174">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="5dc9b-175">Per segnalare un'imprecisione, passare a Report **> Protezione Web > Web Content Filtering Details > Domains**.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-175">To report an inaccuracy, navigate to **Reports > Web protection > Web Content Filtering Details > Domains**.</span></span> <span data-ttu-id="5dc9b-176">Nella scheda domini dei report Filtro contenuto Web verrà visualizzato un pulsante con i puntini di sospensione accanto a ognuno dei domini.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-176">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="5dc9b-177">Posizionare il puntatore del mouse sui puntini di sospensione e selezionare **Segnala imprecisione.**</span><span class="sxs-lookup"><span data-stu-id="5dc9b-177">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="5dc9b-178">Verrà aperto un pannello in cui è possibile selezionare la priorità e aggiungere ulteriori dettagli, ad esempio la categoria suggerita per la ri categorizzazione.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-178">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="5dc9b-179">Dopo aver completato il modulo, selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-179">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="5dc9b-180">Il team esamina la richiesta entro un giorno lavorativo.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-180">Our team will review the request within one business day.</span></span> <span data-ttu-id="5dc9b-181">Per sbloccare immediatamente, crea un [indicatore consenti personalizzato.](indicator-ip-domain.md)</span><span class="sxs-lookup"><span data-stu-id="5dc9b-181">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="5dc9b-182">Schede e dettagli del filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-182">Web content filtering cards and details</span></span>

<span data-ttu-id="5dc9b-183">Selezionare **Report > protezione Web** per visualizzare schede con informazioni sul filtro contenuto Web e sulla protezione dalle minacce Web.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-183">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="5dc9b-184">Nelle schede seguenti vengono fornite informazioni di riepilogo sul filtro contenuto Web.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-184">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="5dc9b-185">Attività Web per categoria</span><span class="sxs-lookup"><span data-stu-id="5dc9b-185">Web activity by category</span></span>

<span data-ttu-id="5dc9b-186">In questa scheda sono elencate le categorie di contenuto Web padre con l'aumento o la riduzione maggiori del numero di tentativi di accesso.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-186">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="5dc9b-187">Comprendere i cambiamenti drastici dei modelli di attività Web nell'organizzazione degli ultimi 30 giorni, 3 mesi o 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-187">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="5dc9b-188">Selezionare un nome di categoria per visualizzare ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-188">Select a category name to view more information.</span></span>

<span data-ttu-id="5dc9b-189">Nei primi 30 giorni di utilizzo di questa funzionalità, l'organizzazione potrebbe non disporre di dati sufficienti per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-189">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![Immagine dell'attività Web per scheda categoria](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="5dc9b-191">Scheda di riepilogo filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-191">Web content filtering  summary card</span></span>

<span data-ttu-id="5dc9b-192">Questa scheda visualizza la distribuzione dei tentativi di accesso bloccati tra le diverse categorie di contenuto Web padre.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-192">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="5dc9b-193">Selezionare una delle barre colorate per visualizzare ulteriori informazioni su una categoria Web padre specifica.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-193">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Immagine della scheda di riepilogo del filtro contenuto Web](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="5dc9b-195">Scheda riepilogativo attività Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-195">Web activity summary card</span></span>

<span data-ttu-id="5dc9b-196">Questa scheda visualizza il numero totale di richieste di contenuto Web in tutti gli URL.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-196">This card displays the total number of requests for web content in all URLs.</span></span>

![Immagine della scheda di riepilogo dell'attività Web](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="5dc9b-198">Visualizzare i dettagli della scheda</span><span class="sxs-lookup"><span data-stu-id="5dc9b-198">View card details</span></span>

<span data-ttu-id="5dc9b-199">È possibile accedere ai **dettagli del report** per ogni scheda selezionando una riga di tabella o una barra colorata dal grafico nella scheda.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-199">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="5dc9b-200">La pagina dei dettagli del report per ogni scheda contiene dati statistici dettagliati sulle categorie di contenuto Web, sui domini di siti Web e sui gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-200">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Immagine dei dettagli del report di protezione Web](images/web-protection-report-details.png)

- <span data-ttu-id="5dc9b-202">**Categorie Web**: elenca le categorie di contenuto Web che hanno avuto tentativi di accesso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-202">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="5dc9b-203">Selezionare una categoria specifica per aprire un riquadro a comparsa di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-203">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="5dc9b-204">**Domini**: elenca i domini Web a cui è stato eseguito l'accesso o che sono stati bloccati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-204">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="5dc9b-205">Selezionare un dominio specifico per visualizzare informazioni dettagliate su tale dominio.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-205">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="5dc9b-206">**Gruppi di dispositivi**: elenca tutti i gruppi di dispositivi che hanno generato attività Web nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5dc9b-206">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="5dc9b-207">Usa il filtro dell'intervallo di tempo nella parte superiore sinistra della pagina per selezionare un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-207">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="5dc9b-208">È inoltre possibile filtrare le informazioni o personalizzare le colonne.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-208">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="5dc9b-209">Selezionare una riga per aprire un riquadro a comparsa con ulteriori informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-209">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="5dc9b-210">Errori e problemi</span><span class="sxs-lookup"><span data-stu-id="5dc9b-210">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="5dc9b-211">Limitazioni e problemi noti in questa anteprima</span><span class="sxs-lookup"><span data-stu-id="5dc9b-211">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="5dc9b-212">Solo Microsoft Edge è supportato se la configurazione del sistema operativo del dispositivo è Server (cmd > Systeminfo > OS Configuration).</span><span class="sxs-lookup"><span data-stu-id="5dc9b-212">Only Microsoft Edge is supported if your device's OS configuration is Server (cmd > Systeminfo > OS Configuration).</span></span> <span data-ttu-id="5dc9b-213">Protezione di rete è supportata solo in modalità Inspect nei dispositivi server, responsabile della protezione del traffico tra i browser di terze parti supportati.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-213">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="5dc9b-214">I dispositivi non assegnati avranno dati non corretti visualizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-214">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="5dc9b-215">Nel pivot Report details > Device groups, you may see a row with a blank Device Group field.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-215">In the Report details > Device groups pivot, you may see a row with a blank Device Group field.</span></span> <span data-ttu-id="5dc9b-216">Questo gruppo contiene i dispositivi non assegnati prima di essere inseriti nel gruppo specificato.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-216">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="5dc9b-217">Il report per questa riga potrebbe non contenere un conteggio accurato dei dispositivi o dei conteggi di accesso.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-217">The report for this row may not contain an accurate count of devices or access counts.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5dc9b-218">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5dc9b-218">Related topics</span></span>

- [<span data-ttu-id="5dc9b-219">Panoramica della protezione Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-219">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="5dc9b-220">Protezione dalle minacce Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-220">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="5dc9b-221">Monitorare la sicurezza Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-221">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="5dc9b-222">Rispondere alle minacce Web</span><span class="sxs-lookup"><span data-stu-id="5dc9b-222">Respond to web threats</span></span>](web-protection-response.md)