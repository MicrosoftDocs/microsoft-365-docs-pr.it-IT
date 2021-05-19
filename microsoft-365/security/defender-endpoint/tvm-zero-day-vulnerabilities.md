---
title: Ridurre le vulnerabilità zero-day - gestione di minacce e vulnerabilità
description: Informazioni su come individuare e ridurre le vulnerabilità zero-day nell'ambiente tramite gestione di minacce e vulnerabilità.
keywords: Microsoft Defender for Endpoint tvm zero day vulnerabilities, tvm, threat & gestione delle vulnerabilità, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538772"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="6578a-104">Ridurre le vulnerabilità zero-day - gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="6578a-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6578a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6578a-105">**Applies to:**</span></span>

- [<span data-ttu-id="6578a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6578a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6578a-107">Minaccia e gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="6578a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6578a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6578a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6578a-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6578a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6578a-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6578a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="6578a-111">Una vulnerabilità zero-day è una vulnerabilità divulgata pubblicamente per la quale non sono state rilasciate patch ufficiali o aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6578a-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="6578a-112">Le vulnerabilità zero-day spesso hanno livelli di gravità elevati e vengono attivamente sfruttate.</span><span class="sxs-lookup"><span data-stu-id="6578a-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="6578a-113">Minacce e gestione delle vulnerabilità verranno visualizzate solo vulnerabilità zero-day su cui sono disponibili informazioni.</span><span class="sxs-lookup"><span data-stu-id="6578a-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="6578a-114">Informazioni sulle vulnerabilità zero-day</span><span class="sxs-lookup"><span data-stu-id="6578a-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="6578a-115">Una volta trovata una vulnerabilità zero-day, le informazioni su di essa verranno trasmesse tramite le esperienze seguenti nel Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="6578a-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

>[!NOTE]
> <span data-ttu-id="6578a-116">La funzionalità di 0 giorni non è attualmente disponibile per i prodotti non Windows (Mac, Linux); verrà tuttavia aggiunto in futuro.</span><span class="sxs-lookup"><span data-stu-id="6578a-116">0-day capability is not currently available for non-Windows products (Mac, Linux); it will, however, be added in the future.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="6578a-117">Dashboard delle minacce gestione delle vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="6578a-117">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="6578a-118">Cerca i suggerimenti con un tag zero-day nella scheda "Suggerimenti per la sicurezza principali".</span><span class="sxs-lookup"><span data-stu-id="6578a-118">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Suggerimenti principali con tag zero-day.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="6578a-120">Trova il software principale con il tag zero-day nella scheda "Software più vulnerabile".</span><span class="sxs-lookup"><span data-stu-id="6578a-120">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Software più vulnerabile con tag zero-day.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="6578a-122">Pagina Punti deboli</span><span class="sxs-lookup"><span data-stu-id="6578a-122">Weaknesses page</span></span>

<span data-ttu-id="6578a-123">Cercare la vulnerabilità denominata zero-day insieme a una descrizione e dettagli.</span><span class="sxs-lookup"><span data-stu-id="6578a-123">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="6578a-124">Se a questa vulnerabilità è assegnato un ID CVE, verrà visualizzata l'etichetta zero-day accanto al nome CVE.</span><span class="sxs-lookup"><span data-stu-id="6578a-124">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="6578a-125">Se a questa vulnerabilità non è assegnato un CVE-ID, si troverà sotto un nome temporaneo interno simile a "TVM-XXXX-XXXX".</span><span class="sxs-lookup"><span data-stu-id="6578a-125">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="6578a-126">Il nome verrà aggiornato dopo l'assegnazione di un CVE-ID ufficiale, ma il nome interno precedente sarà comunque disponibile per la ricerca e verrà trovato nel pannello laterale.</span><span class="sxs-lookup"><span data-stu-id="6578a-126">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Esempio di zero giorni per CVE-2020-17087 nella pagina dei punti deboli.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="6578a-128">Pagina Inventario software</span><span class="sxs-lookup"><span data-stu-id="6578a-128">Software inventory page</span></span>

<span data-ttu-id="6578a-129">Cercare software con il tag zero-day.</span><span class="sxs-lookup"><span data-stu-id="6578a-129">Look for software with the zero-day tag.</span></span> <span data-ttu-id="6578a-130">Filtrare in base al tag "zero day" per visualizzare solo il software con vulnerabilità zero-day.</span><span class="sxs-lookup"><span data-stu-id="6578a-130">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Esempio zero giorno di Windows Server 2016 nella pagina dell'inventario software.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="6578a-132">Pagina Software</span><span class="sxs-lookup"><span data-stu-id="6578a-132">Software page</span></span>

<span data-ttu-id="6578a-133">Cercare un tag zero-day per ogni software interessato dalla vulnerabilità zero-day.</span><span class="sxs-lookup"><span data-stu-id="6578a-133">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Esempio di zero giorni per Windows Server 2016 software.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="6578a-135">Pagina Suggerimenti per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="6578a-135">Security recommendations page</span></span>

<span data-ttu-id="6578a-136">Visualizzare suggerimenti chiari sulle opzioni di correzione e mitigazione, incluse le soluzioni alternative, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="6578a-136">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="6578a-137">Filtrare in base al tag "zero day" per visualizzare solo i suggerimenti per la sicurezza che affrontano le vulnerabilità zero-day.</span><span class="sxs-lookup"><span data-stu-id="6578a-137">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="6578a-138">Se è presente un software con una vulnerabilità zero-day e vulnerabilità aggiuntive da risolvere, si otterrà un consiglio su tutte le vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="6578a-138">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Zero day example of Windows Server 2016 nella pagina degli elementi consigliati per la sicurezza.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="6578a-140">Affrontare le vulnerabilità zero-day</span><span class="sxs-lookup"><span data-stu-id="6578a-140">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="6578a-141">Vai alla pagina dei suggerimenti per la sicurezza e seleziona un suggerimento con zero-day.</span><span class="sxs-lookup"><span data-stu-id="6578a-141">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="6578a-142">Verrà aperto un riquadro a comparsa con informazioni sulla zero-day e altre vulnerabilità per tale software.</span><span class="sxs-lookup"><span data-stu-id="6578a-142">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="6578a-143">Se disponibili, sarà disponibile un collegamento alle opzioni di mitigazione e alle soluzioni alternative.</span><span class="sxs-lookup"><span data-stu-id="6578a-143">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="6578a-144">Le soluzioni alternative possono contribuire a ridurre il rischio rappresentato da questa vulnerabilità zero-day fino a quando non è possibile distribuire una patch o un aggiornamento della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6578a-144">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="6578a-145">Apri le opzioni di correzione e scegli il tipo di attenzione.</span><span class="sxs-lookup"><span data-stu-id="6578a-145">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="6578a-146">È consigliabile un'opzione di correzione "attenzione necessaria" per le vulnerabilità zero-day, poiché un aggiornamento non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="6578a-146">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="6578a-147">Non sarà possibile selezionare una data di scadenza, poiché non è disponibile alcuna azione specifica da eseguire.</span><span class="sxs-lookup"><span data-stu-id="6578a-147">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="6578a-148">Se sono presenti vulnerabilità meno recenti per questo software che si desidera correggere, è possibile ignorare l'opzione di correzione "attenzione necessaria" e scegliere "aggiorna".</span><span class="sxs-lookup"><span data-stu-id="6578a-148">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Esempio di riquadro a comparsa zero Windows Server 2016 nella pagina dei suggerimenti per la sicurezza.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="6578a-150">Tenere traccia delle attività di correzione zero-day</span><span class="sxs-lookup"><span data-stu-id="6578a-150">Track zero-day remediation activities</span></span>

<span data-ttu-id="6578a-151">Passare alla pagina gestione di minacce e vulnerabilità [correzione per](tvm-remediation.md) visualizzare l'elemento attività di correzione.</span><span class="sxs-lookup"><span data-stu-id="6578a-151">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="6578a-152">Se hai scelto l'opzione di correzione "attenzione necessaria", non ci saranno barre di avanzamento, stato del ticket o data di scadenza poiché non è possibile monitorare alcuna azione effettiva.</span><span class="sxs-lookup"><span data-stu-id="6578a-152">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="6578a-153">È possibile filtrare in base al tipo di correzione, ad esempio "aggiornamento software" o "attenzione necessaria", per visualizzare tutti gli elementi attività nella stessa categoria.</span><span class="sxs-lookup"><span data-stu-id="6578a-153">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="6578a-154">Applicazione di patch alle vulnerabilità zero-day</span><span class="sxs-lookup"><span data-stu-id="6578a-154">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="6578a-155">Quando viene rilasciata una patch per il giorno zero, il suggerimento verrà modificato in "Aggiornamento" e accanto a essa verrà visualizzato un'etichetta blu che indica "Nuovo aggiornamento della sicurezza per zero giorno".</span><span class="sxs-lookup"><span data-stu-id="6578a-155">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="6578a-156">Non verrà più utilizzato come zero-day, il tag zero-day verrà rimosso da tutte le pagine.</span><span class="sxs-lookup"><span data-stu-id="6578a-156">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Suggerimento per "Aggiornare Microsoft Windows 10" con la nuova etichetta di patch.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="6578a-158">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="6578a-158">Related articles</span></span>

- [<span data-ttu-id="6578a-159">Panoramica delle minacce gestione delle vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="6578a-159">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6578a-160">Dashboard</span><span class="sxs-lookup"><span data-stu-id="6578a-160">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="6578a-161">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="6578a-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="6578a-162">Inventario software</span><span class="sxs-lookup"><span data-stu-id="6578a-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="6578a-163">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6578a-163">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
