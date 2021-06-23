---
title: Ricerca delle minacce in Threat Explorer per Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Usa Threat Explorer o i rilevamenti in tempo reale nel portale Microsoft 365 Defender per analizzare e rispondere alle minacce in modo efficiente.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b0c0c36cb481aac64b55467da4aaf9e3cf7a493
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083561"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="2e0b6-103">Ricerca delle minacce in Threat Explorer per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2e0b6-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2e0b6-104">Contenuto dell'articolo:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-104">In this article:</span></span>

- [<span data-ttu-id="2e0b6-105">Analisi di Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="2e0b6-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="2e0b6-106">Analisi della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2e0b6-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="2e0b6-107">Correzione della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2e0b6-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="2e0b6-108">Miglioramenti all'esperienza di ricerca delle minacce</span><span class="sxs-lookup"><span data-stu-id="2e0b6-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="2e0b6-109">Questo articolo fa parte di una serie di **3** articoli su **Threat Explorer (Explorer),** sicurezza della posta elettronica e informazioni di base su **Explorer** e sui rilevamenti in tempo reale (ad esempio le differenze tra gli strumenti e le autorizzazioni necessarie per operare). </span><span class="sxs-lookup"><span data-stu-id="2e0b6-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="2e0b6-110">Gli altri due articoli di questa serie sono sicurezza della posta elettronica [con Threat Explorer](email-security-in-microsoft-defender.md) e Threat Explorer e nozioni di base sui [rilevamenti in tempo reale.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="2e0b6-111">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="2e0b6-111">**Applies to**</span></span>
- [<span data-ttu-id="2e0b6-112">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="2e0b6-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2e0b6-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e0b6-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2e0b6-114">Se l'organizzazione dispone di [Microsoft Defender per Office 365](defender-for-office-365.md)e si dispone  delle autorizzazioni [,](#required-licenses-and-permissions)è possibile utilizzare **Esplora** risorse o rilevamenti in tempo reale per rilevare e correggere le minacce.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="2e0b6-115">Nel portale **Microsoft 365 Defender ,** passare a Posta elettronica **& collaborazione** e quindi scegliere **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-115">In the **Microsoft 365 Defender portal**, go to **Email & collaboration**, and then choose **Explorer**.</span></span>

<br>

****

|<span data-ttu-id="2e0b6-116">Con Microsoft Defender per Office 365 Piano 2, viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="2e0b6-117">Con Microsoft Defender per Office 365 piano 1, viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Esplora minacce](../../media/path-to-explorer.png)|![Rilevamenti in tempo reale](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="2e0b6-120">Con questi strumenti è possibile:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-120">With these tools, you can:</span></span>

- <span data-ttu-id="2e0b6-121">Vedere malware rilevato dalle Microsoft 365 di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e0b6-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="2e0b6-122">Visualizzare l'URL di phishing e fare clic su Dati verdetto</span><span class="sxs-lookup"><span data-stu-id="2e0b6-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="2e0b6-123">Avviare un processo di indagine e risposta automatizzato da una visualizzazione in Esplora risorse</span><span class="sxs-lookup"><span data-stu-id="2e0b6-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="2e0b6-124">Analizzare la posta elettronica dannosa e altro ancora</span><span class="sxs-lookup"><span data-stu-id="2e0b6-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="2e0b6-125">Per altre informazioni, vedi [Sicurezza della posta elettronica con Threat Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="2e0b6-126">Analisi di Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="2e0b6-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="2e0b6-127">In Microsoft Defender per Office 365, sono disponibili due piani di sottoscrizione: Piano 1 e Piano 2.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="2e0b6-128">Gli strumenti di ricerca delle minacce gestiti manualmente esistono in entrambi i piani, con nomi diversi e con funzionalità diverse.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="2e0b6-129">Defender per Office 365 Piano 1 usa i rilevamenti in tempo *reale,* che è un sottoinsieme dello strumento di ricerca *Threat Explorer* (denominato anche *Explorer)* nel Piano 2.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="2e0b6-130">In questa serie di articoli, la maggior parte degli esempi è stata creata usando l'intero Threat Explorer.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="2e0b6-131">Gli amministratori devono testare i passaggi nei rilevamenti in tempo reale per vedere dove si applicano.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="2e0b6-132">Per aprire lo strumento Esplora risorse, vai a **Microsoft 365 Defender portale** Email  >  **& collaboration**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-132">To open the Explorer tool, go to **Microsoft 365 Defender portal** > **Email & collaboration** > **Explorer**.</span></span> <span data-ttu-id="2e0b6-133">Per impostazione predefinita, arriverai nella pagina **Malware,** ma usa l'elenco a discesa **Visualizza** per acquisire familiarità con le opzioni.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="2e0b6-134">Se stai cercando Phish o stai scavando in una campagna di minacce, scegli queste visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-135">![Elenco a discesa Visualizza in Esplora minacce](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-135">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="2e0b6-136">Una volta che un utente delle operazioni di sicurezza (Sec Ops) seleziona i dati che desidera visualizzare, se l'ambito  è ristretto come invii utente o una visualizzazione più ampia, come Tutti i messaggi di posta **elettronica,** può utilizzare il pulsante Mittente per filtrare ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="2e0b6-137">Ricordarsi di selezionare Aggiorna per completare le azioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-138">![Pulsante Mittente in Esplora minacce](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-138">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="2e0b6-139">La perfezione dello stato attivo in Esplora risorse o il rilevamento in tempo reale può essere pensata nei livelli.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="2e0b6-140">Il primo è **View.**</span><span class="sxs-lookup"><span data-stu-id="2e0b6-140">The first is **View**.</span></span> <span data-ttu-id="2e0b6-141">Il secondo può essere pensato come uno *stato attivo filtrato.*</span><span class="sxs-lookup"><span data-stu-id="2e0b6-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="2e0b6-142">Ad esempio, puoi ripercorrere i passaggi che hai fatto per trovare una minaccia registrando le tue decisioni come questa: Per trovare il problema in Esplora risorse, ho scelto la visualizzazione **Malware** con un filtro destinatario attivo.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="2e0b6-143">In questo modo è più semplice eseguire nuovamente i passaggi.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="2e0b6-144">Se Sec Ops usa **Tag** per contrassegnare gli account che considerano obiettivi di valore elevato, possono effettuare selezioni come Visualizzazione phish con lo stato attivo del filtro Tag (includere un intervallo di date se *usato).*</span><span class="sxs-lookup"><span data-stu-id="2e0b6-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="2e0b6-145">Questo mostrerà loro eventuali tentativi di phishing indirizzati ai loro obiettivi utente di alto valore durante un intervallo di tempo (ad esempio date in cui determinati attacchi di phishing stanno avvenendo molto per il loro settore).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="2e0b6-146">I criteri di affinamento possono essere evasi in intervalli di date utilizzando i controlli dell'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="2e0b6-147">Qui puoi vedere Esplora risorse nella visualizzazione **Malware,** con lo stato attivo del filtro **Tecnologia** di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="2e0b6-148">Ma è il pulsante **Filtro avanzato** che consente ai team sec ops di scavare in profondità.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-149">![Filtro avanzato in Esplora minacce](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-149">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="2e0b6-150">Se si **fa clic sul** filtro Avanzato, viene visualizzato un pannello che consente ai cacciatori sec ops di creare query in modo che includano o escludono le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="2e0b6-151">Sia il grafico che la tabella nella pagina Esplora risorse rifletteranno i risultati.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-152">![Risultati di una query](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="2e0b6-153">Utilizzare il **pulsante Opzioni** colonna per ottenere il tipo di informazioni sulla tabella più utili:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-154">![Pulsante Opzioni colonna evidenziato](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-155">![Opzioni disponibili in Colonne](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-155">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="2e0b6-156">Nello stesso ambiente, assicurati di testare le opzioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="2e0b6-157">Gruppi di destinatari diversi reagiscono bene alle diverse presentazioni degli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="2e0b6-158">Per alcuni visualizzatori, la mappa **Email Origins** può mostrare che  una minaccia è diffusa o discreta più rapidamente rispetto all'opzione Visualizzazione campagna accanto ad essa.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="2e0b6-159">Sec Ops può usare questi display per fare al meglio punti che sottolineano la necessità di sicurezza e protezione o per un confronto successivo, per dimostrare l'efficacia delle loro azioni.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-160">![Mappa Origini posta elettronica](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-161">![Opzioni di visualizzazione della campagna](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="2e0b6-162">Analisi della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2e0b6-162">Email investigation</span></span>

<span data-ttu-id="2e0b6-163">Quando viene visualizzato un messaggio di posta elettronica sospetto, fare clic sul nome per espandere il riquadro a comparsa a destra.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="2e0b6-164">In questo caso, è disponibile il banner che consente a Sec Ops di visualizzare la [pagina dell'entità di posta](mdo-email-entity-page.md) elettronica.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="2e0b6-165">La pagina dell'entità di posta elettronica riunisce il contenuto disponibile **in** **Dettagli,** **Allegati,** Dispositivi, ma include dati più organizzati.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="2e0b6-166">Sono inclusi elementi come i risultati DMARC, la visualizzazione in testo normale dell'intestazione del messaggio di posta elettronica con un'opzione di copia, le informazioni di verdetto sugli allegati detonati in modo sicuro e i file eliminati da tali detonazioni (possono includere indirizzi IP contattati e screenshot di pagine o file).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="2e0b6-167">Anche gli URL e i loro verdetti sono elencati con dettagli simili segnalati.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="2e0b6-168">Quando si raggiunge questa fase, la pagina dell'entità di posta elettronica sarà fondamentale per il passaggio finale,*ovvero la correzione.*</span><span class="sxs-lookup"><span data-stu-id="2e0b6-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-169">![Pagina entità di posta elettronica](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="2e0b6-170">Per ulteriori informazioni sulla pagina dell'entità di posta elettronica completa (visualizzata di seguito nella scheda **Analisi),** inclusi i risultati degli allegati detonati, i risultati degli URL inclusi e l'anteprima sicura della posta elettronica, fare clic [qui](mdo-email-entity-page.md).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-171">![Scheda Analisi della pagina dell'entità di posta elettronica](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="2e0b6-172">Correzione della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2e0b6-172">Email remediation</span></span>

<span data-ttu-id="2e0b6-173">Una volta che una persona di Sec Ops determina che un messaggio di posta elettronica è una minaccia, il passaggio successivo di Explorer o rilevamento in tempo reale si occupa della minaccia e la correla.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="2e0b6-174">A tale scopo, tornare a Esplora minacce, selezionare la casella di controllo per l'e-mail del problema e usare il **pulsante** Azioni.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-175">![Pulsante Azioni in Esplora minacce](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="2e0b6-176">In questo caso, l'analista può eseguire azioni come segnalare la posta elettronica come Posta indesiderata, Phishing o Malware, contattare i destinatari o ulteriori indagini che possono includere l'attivazione di playbook di indagine e risposta automatizzata (o AIR) (se si dispone del Piano 2).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="2e0b6-177">Oppure, la posta può anche essere segnalata come pulita.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-178">![Elenco a discesa Azioni](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="2e0b6-179">Miglioramenti all'esperienza di ricerca delle minacce</span><span class="sxs-lookup"><span data-stu-id="2e0b6-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="2e0b6-180">ID avviso</span><span class="sxs-lookup"><span data-stu-id="2e0b6-180">Alert ID</span></span>

<span data-ttu-id="2e0b6-181">Quando ci si sposta da un avviso in Esplora minacce, **la visualizzazione** verrà filtrata in base **all'ID avviso.**</span><span class="sxs-lookup"><span data-stu-id="2e0b6-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="2e0b6-182">Questo vale anche per il rilevamento in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="2e0b6-183">Vengono visualizzati i messaggi rilevanti per l'avviso specifico e un totale di posta elettronica (un conteggio).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="2e0b6-184">Sarà possibile vedere se un messaggio fa parte di un avviso e passare da tale messaggio all'avviso correlato.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="2e0b6-185">Infine, l'ID avviso è incluso nell'URL, ad esempio: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="2e0b6-185">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-186">![Filtro per l'ID avviso](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-187">![ID avviso nel riquadro a comparsa dettagli](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="2e0b6-188">Estensione del limite di conservazione e ricerca dei dati di Explorer (e rilevamento in tempo reale) per i tenant di prova</span><span class="sxs-lookup"><span data-stu-id="2e0b6-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="2e0b6-189">Come parte di questa modifica, gli analisti saranno in grado di cercare e filtrare i dati di posta elettronica in 30 giorni (da sette giorni) in Threat Explorer e rilevamenti in tempo reale per i tenant di prova di Office P1 e P2.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="2e0b6-190">Questo non influisce sui tenant di produzione per i clienti P1 e P2 E5, dove il valore predefinito di conservazione è già 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="2e0b6-191">Limite di esportazione aggiornato</span><span class="sxs-lookup"><span data-stu-id="2e0b6-191">Updated Export limit</span></span> 

<span data-ttu-id="2e0b6-192">Il numero di record email che possono essere esportati da Threat Explorer è ora 200.000 (era 9990).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="2e0b6-193">Il set di colonne che è possibile esportare rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="2e0b6-194">Tag in Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="2e0b6-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="2e0b6-195">La funzionalità tag utente è disponibile in Anteprima e potrebbe non essere disponibile per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="2e0b6-196">Inoltre, le anteprime sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="2e0b6-197">Per informazioni sulla pianificazione dei rilasci, vedere la guida di orientamento Microsoft 365 rilascio.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="2e0b6-198">I tag utente identificano gruppi specifici di utenti in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="2e0b6-199">Per ulteriori informazioni sui tag, incluse le licenze e la configurazione, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="2e0b6-200">In Esplora minacce puoi visualizzare le informazioni sui tag utente nelle esperienze seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="2e0b6-201">Visualizzazione griglia posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2e0b6-201">Email grid view</span></span>

<span data-ttu-id="2e0b6-202">Quando gli analisti osservano la colonna **Tag** nella griglia della posta elettronica, vengono visualizzati tutti i tag applicati alle cassette postali del mittente o del destinatario.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="2e0b6-203">Per impostazione predefinita, i tag di sistema come *gli account di* priorità vengono visualizzati per primi.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-204">![Filtrare i tag nella visualizzazione griglia della posta elettronica](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="2e0b6-205">Filtro</span><span class="sxs-lookup"><span data-stu-id="2e0b6-205">Filtering</span></span>

<span data-ttu-id="2e0b6-206">I tag possono essere utilizzati come filtri.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-206">Tags can be used as filters.</span></span> <span data-ttu-id="2e0b6-207">Eseguire la ricerca solo tra account con priorità o utilizzare scenari specifici di tag utente in questo modo.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="2e0b6-208">È inoltre possibile escludere i risultati con determinati tag.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="2e0b6-209">Combina i tag con altri filtri e intervalli di date per restringere l'ambito di indagine.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="2e0b6-210">[![Tag di filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-211">![Tag non filtrati](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="2e0b6-212">Riquadro a comparsa Dettagli posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2e0b6-212">Email detail flyout</span></span>

<span data-ttu-id="2e0b6-213">Per visualizzare i singoli tag per mittente e destinatario, selezionare un messaggio di posta elettronica per aprire il riquadro a comparsa dei dettagli del messaggio.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="2e0b6-214">Nella scheda **Riepilogo,** i tag mittente e destinatario vengono visualizzati separatamente.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="2e0b6-215">Le informazioni sui singoli tag per mittente e destinatario possono essere esportate come dati CSV.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-216">![Tag Dettagli posta elettronica](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="2e0b6-217">Le informazioni sui tag vengono visualizzate anche nel riquadro a comparsa dei clic sull'URL.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="2e0b6-218">Per visualizzarlo, passare alla visualizzazione Phish o All Email > **URL** o alla scheda **Url Clicks.** Seleziona un singolo riquadro a comparsa URL per visualizzare ulteriori dettagli sui clic per tale URL, inclusi gli eventuali tag associati a tale clic.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="2e0b6-219">Visualizzazione sequenza temporale aggiornata</span><span class="sxs-lookup"><span data-stu-id="2e0b6-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-220">![Tag URL](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="2e0b6-221">Scopri di più guardando [questo video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span><span class="sxs-lookup"><span data-stu-id="2e0b6-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="2e0b6-222">Funzionalità estese</span><span class="sxs-lookup"><span data-stu-id="2e0b6-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="2e0b6-223">Utenti di destinazione principali</span><span class="sxs-lookup"><span data-stu-id="2e0b6-223">Top targeted users</span></span>

<span data-ttu-id="2e0b6-224">Principali famiglie di malware mostra **gli utenti di destinazione principali** nella sezione Malware.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="2e0b6-225">Gli utenti di destinazione principali verranno estesi anche tramite le visualizzazioni Phish e All Email.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="2e0b6-226">Gli analisti saranno in grado di visualizzare i cinque utenti più mirati, insieme al numero di tentativi per ogni utente in ogni visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="2e0b6-227">Operazioni di sicurezza Gli utenti possono esportare l'elenco degli utenti di destinazione, fino a un limite di 3.000, insieme al numero di tentativi effettuati, per l'analisi offline per ogni visualizzazione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="2e0b6-228">Inoltre, selezionando il numero di tentativi (ad esempio, 13 tentativi nell'immagine seguente) verrà aperta una visualizzazione filtrata in Esplora minacce, in modo da poter visualizzare ulteriori dettagli tra i messaggi di posta elettronica e le minacce per tale utente.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-229">![Utenti di destinazione principali](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="2e0b6-230">Exchange di trasporto</span><span class="sxs-lookup"><span data-stu-id="2e0b6-230">Exchange transport rules</span></span>

<span data-ttu-id="2e0b6-231">Il team delle operazioni di sicurezza sarà in grado di visualizzare tutte le regole di trasporto Exchange (o regole del flusso di posta) applicate a un messaggio nella visualizzazione Griglia posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="2e0b6-232">Selezionare **Opzioni colonna** nella griglia e quindi Exchange regola di **trasporto** dalle opzioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="2e0b6-233">L Exchange delle regole di trasporto è visibile anche nel riquadro **a** comparsa Dettagli nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="2e0b6-234">Vengono visualizzati i nomi e i GUID delle regole di trasporto applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="2e0b6-235">Gli analisti potranno cercare i messaggi utilizzando il nome della regola di trasporto.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="2e0b6-236">Si tratta di una ricerca CONTAINS, che significa che è possibile eseguire anche ricerche parziali.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2e0b6-237">Exchange ricerca delle regole di trasporto e la disponibilità dei nomi dipendono dal ruolo specifico assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="2e0b6-238">Per visualizzare i nomi delle regole di trasporto e la ricerca, è necessario disporre di uno dei ruoli o delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="2e0b6-239">Tuttavia, anche senza i ruoli o le autorizzazioni seguenti, un analista può visualizzare l'etichetta della regola di trasporto e le informazioni sul GUID nei dettagli della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="2e0b6-240">Altre esperienze di visualizzazione dei record nelle griglie di posta elettronica, nei riquadri a comparsa di posta elettronica, nei filtri e nell'esportazione non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="2e0b6-241">Exchange Online Solo - Prevenzione della perdita di dati: Tutti</span><span class="sxs-lookup"><span data-stu-id="2e0b6-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="2e0b6-242">Exchange Online Solo - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="2e0b6-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="2e0b6-243">Microsoft Azure Active Directory o Exchange Online - Amministratore sicurezza: Tutti</span><span class="sxs-lookup"><span data-stu-id="2e0b6-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="2e0b6-244">Azure Active Directory o Exchange Online - Security Reader: All</span><span class="sxs-lookup"><span data-stu-id="2e0b6-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="2e0b6-245">Exchange Online Solo - Regole di trasporto: Tutte</span><span class="sxs-lookup"><span data-stu-id="2e0b6-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="2e0b6-246">Exchange Online Solo - View-Only configurazione: Tutti</span><span class="sxs-lookup"><span data-stu-id="2e0b6-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="2e0b6-247">All'interno della griglia di posta elettronica, del riquadro a comparsa Dettagli e del file CSV esportato, gli ETF vengono presentati con un nome/GUID, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="2e0b6-248">![Exchange Regole di trasporto](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="2e0b6-249">Connettori in ingresso</span><span class="sxs-lookup"><span data-stu-id="2e0b6-249">Inbound connectors</span></span>

<span data-ttu-id="2e0b6-250">I connettori sono una raccolta di istruzioni che personalizzano il flusso della posta elettronica da e verso l'Microsoft 365 o Office 365'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="2e0b6-251">Consentono di applicare eventuali restrizioni o controlli di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="2e0b6-252">In Esplora minacce, è possibile visualizzare i connettori correlati a un messaggio di posta elettronica e cercare i messaggi di posta elettronica utilizzando i nomi dei connettori.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="2e0b6-253">La ricerca di connettori è una query CONTAINS, il che significa che le ricerche con parole chiave parziali possono funzionare:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e0b6-254">![Dettagli connettore](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="2e0b6-255">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="2e0b6-255">Required licenses and permissions</span></span>

<span data-ttu-id="2e0b6-256">Devi disporre di [Microsoft Defender per Office 365](defender-for-office-365.md) usare Explorer o rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="2e0b6-257">Explorer è incluso in Defender per Office 365 Piano 2.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="2e0b6-258">Il report rilevamenti in tempo reale è incluso in Defender per Office 365 piano 1.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="2e0b6-259">Pianificare l'assegnazione delle licenze per tutti gli utenti che devono essere protetti da Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="2e0b6-260">Explorer e i rilevamenti in tempo reale mostrano i dati di rilevamento per gli utenti con licenza.</span><span class="sxs-lookup"><span data-stu-id="2e0b6-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="2e0b6-261">Per visualizzare e usare Esplora risorse o rilevamenti in tempo reale, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="2e0b6-262">Per il portale Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-262">For the Microsoft 365 Defender portal:</span></span>

  - <span data-ttu-id="2e0b6-263">Gestione dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2e0b6-263">Organization Management</span></span>
  - <span data-ttu-id="2e0b6-264">Amministratore della sicurezza (può essere assegnato nell'Azure Active Directory di amministrazione ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="2e0b6-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="2e0b6-265">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="2e0b6-265">Security Reader</span></span>

- <span data-ttu-id="2e0b6-266">Per Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-266">For Exchange Online:</span></span>

  - <span data-ttu-id="2e0b6-267">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="2e0b6-267">Organization Management</span></span>
  - <span data-ttu-id="2e0b6-268">Gestione organizzazione sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="2e0b6-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="2e0b6-269">Destinatari solo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="2e0b6-269">View-Only Recipients</span></span>
  - <span data-ttu-id="2e0b6-270">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="2e0b6-270">Compliance Management</span></span>

<span data-ttu-id="2e0b6-271">Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e0b6-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="2e0b6-272">Autorizzazioni nel portale di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e0b6-272">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="2e0b6-273">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2e0b6-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="2e0b6-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e0b6-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="2e0b6-275">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="2e0b6-275">More information</span></span>

- [<span data-ttu-id="2e0b6-276">Identificare e analizzare i messaggi di posta elettronica dannosi recapitati</span><span class="sxs-lookup"><span data-stu-id="2e0b6-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="2e0b6-277">Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e0b6-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="2e0b6-278">Ottenere una panoramica delle visualizzazioni in Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="2e0b6-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="2e0b6-279">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="2e0b6-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="2e0b6-280">Indagine e reazione automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2e0b6-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="2e0b6-281">Analizzare i messaggi di posta elettronica con la pagina Entità di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2e0b6-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)