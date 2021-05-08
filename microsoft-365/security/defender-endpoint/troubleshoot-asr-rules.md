---
title: Segnalare e risolvere i problemi relativi alle regole di Risoluzione dei problemi di Microsoft Defender per Endpoint ASR
description: In questo argomento viene descritto come segnalare e risolvere i problemi di Microsoft Defender per le regole asR endpoint
keywords: Regole di riduzione della superficie di attacco, asr, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, microsoft defender per endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246145"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="ebb0e-104">Segnalare e risolvere i problemi relativi alle regole asR di Microsoft Defender for ATP</span><span class="sxs-lookup"><span data-stu-id="ebb0e-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ebb0e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ebb0e-105">**Applies to:**</span></span>

- [<span data-ttu-id="ebb0e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ebb0e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ebb0e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebb0e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ebb0e-108">Il Microsoft 365 sicurezza è la nuova interfaccia per il monitoraggio e la gestione della sicurezza tra identità, dati, dispositivi, app e infrastruttura Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="ebb0e-109">Qui è possibile visualizzare facilmente l'integrità della sicurezza dell'organizzazione, configurare dispositivi, utenti e app e ricevere avvisi per attività sospette.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="ebb0e-110">Il Centro sicurezza Microsoft 365 è progettato per gli amministratori e i team delle operazioni di sicurezza per gestire e proteggere in modo migliore le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="ebb0e-111">Visitare il centro Microsoft 365 sicurezza all'indirizzo https://security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="ebb0e-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="ebb0e-112">Nel Microsoft 365 sicurezza, ti offriamo un'occhiata completa alla configurazione e agli eventi correnti delle regole di ripristino automatico nel tuo immobile.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="ebb0e-113">Tieni presente che i dispositivi devono essere inseriti nel servizio Microsoft Defender for Endpoint per poter essere popolati.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="ebb0e-114">Ecco uno screenshot dal Centro sicurezza Microsoft 365 sicurezza **(in** Segnala  >  **dispositivi** Riduzione superficie  >  **di attacco**).</span><span class="sxs-lookup"><span data-stu-id="ebb0e-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="ebb0e-115">A livello di dispositivo, seleziona **Configurazione nel** riquadro Regole di riduzione della **superficie di** attacco.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="ebb0e-116">Viene visualizzata la schermata seguente, in cui è possibile selezionare un dispositivo specifico e controllare la configurazione delle singole regole asr.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="Schermata regole di risoluzione dei dati":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="ebb0e-118">Microsoft Defender for Endpoint - Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="ebb0e-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="ebb0e-119">Una delle funzionalità più potenti di Microsoft Defender for Endpoint è la ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="ebb0e-120">Se non hai familiarità con la ricerca avanzata, fai riferimento alla ricerca proattiva per le [minacce con la ricerca avanzata.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ebb0e-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="ebb0e-121">Ricerca avanzata è uno strumento di ricerca delle minacce basato su query (Kusto Query Language) che consente di esplorare fino a 30 giorni dei dati acquisiti (non elaborati EDR), raccolti da tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="ebb0e-122">Tramite la ricerca avanzata, è possibile esaminare in modo proattivo gli eventi per individuare indicatori ed entità interessanti.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="ebb0e-123">L'accesso flessibile ai dati consente di cercare senza vincoli minacce note e potenziali.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="ebb0e-124">Attraverso la ricerca avanzata, è possibile estrarre informazioni sulle regole asr, creare report e ottenere informazioni approfondite sul contesto di un determinato evento di controllo o blocco delle regole ASR.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="ebb0e-125">Gli eventi delle regole di registrazione asr sono disponibili per essere interrogati dalla tabella DeviceEvents nella sezione ricerca avanzata del Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="ebb0e-126">Ad esempio, una query semplice come quella riportata di seguito può segnalare tutti gli eventi che dispongono di regole asr come origine dati per gli ultimi 30 giorni e li riepiloga in base al conteggio ActionType, che in questo caso sarà il nome in codice effettivo della regola asr.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Query di ricerca avanzata":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="schermata di ricerca avanzata":::

<span data-ttu-id="ebb0e-129">Con la ricerca avanzata è possibile modellare le query a proprio piacimento, in modo da poter vedere cosa accade, indipendentemente dal fatto che si desideri individuare un elemento in un singolo computer o estrarre informazioni dettagliate dall'intero ambiente.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="ebb0e-130">Sequenza temporale del computer Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ebb0e-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="ebb0e-131">Un'alternativa alla ricerca avanzata, ma con un ambito più ristretto, è la sequenza temporale del computer microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="ebb0e-132">Puoi visualizzare tutti gli eventi raccolti di un dispositivo, negli ultimi sei mesi, nel Microsoft Defender Security Center, andando all'elenco Machines, selezionare un determinato computer e quindi fare clic sulla scheda Timeline.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="ebb0e-133">Nella figura seguente è riportata una schermata della visualizzazione Sequenza temporale di questi eventi in un determinato endpoint.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="ebb0e-134">Da questa visualizzazione è possibile filtrare l'elenco degli eventi in base a uno qualsiasi dei gruppi di eventi nel riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="ebb0e-135">Puoi anche abilitare o disabilitare gli eventi contrassegnati e dettagliati durante la visualizzazione degli avvisi e lo scorrimento nella sequenza temporale cronologica.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Sequenza temporale del Centro sicurezza Microsoft Defender":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="ebb0e-137">Come risolvere i problemi relativi alle regole asr?</span><span class="sxs-lookup"><span data-stu-id="ebb0e-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="ebb0e-138">Il primo e più immediato modo è controllare localmente, in un dispositivo Windows, quali regole di registrazione automatico sono abilitate (e la relativa configurazione) utilizzando i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="ebb0e-139">Ecco alcune altre fonti di informazioni che Windows, per risolvere i problemi relativi all'impatto e al funzionamento delle regole asr.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="ebb0e-140">Esecuzione di query sulle regole attive</span><span class="sxs-lookup"><span data-stu-id="ebb0e-140">Querying which rules are active</span></span>
<span data-ttu-id="ebb0e-141">Uno dei modi più semplici per determinare se le regole asr sono già abilitate e, tramite un cmdlet di PowerShell, Get-MpPreference.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="ebb0e-142">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="ebb0e-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="get mppreference script":::

<span data-ttu-id="ebb0e-144">Sono attive più regole asr, con diverse azioni configurate.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="ebb0e-145">Per espandere le informazioni sopra riportate sulle regole asr, è possibile utilizzare le proprietà **AttackSurfaceReductionRules_Ids** e/o **AttackSurfaceReductionRules_Actions**.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="ebb0e-146">Esempio:</span><span class="sxs-lookup"><span data-stu-id="ebb0e-146">Example:</span></span>

<span data-ttu-id="ebb0e-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="ebb0e-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="esempio di ottenere mpreference":::

<span data-ttu-id="ebb0e-149">Quanto sopra mostra tutti gli ID per le regole asr con un'impostazione diversa da 0 (Non configurato).</span><span class="sxs-lookup"><span data-stu-id="ebb0e-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="ebb0e-150">Il passaggio successivo consiste nell'elencare le azioni effettive (Blocca o Controlla) con cui è configurata ogni regola.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="ebb0e-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="ebb0e-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="ebb0e-153">Esecuzione di query su eventi di blocco e controllo</span><span class="sxs-lookup"><span data-stu-id="ebb0e-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="ebb0e-154">Gli eventi delle regole asr possono essere visualizzati all'interno del Windows Defender registrazione.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="ebb0e-155">Per accedervi, aprire Windows Visualizzatore eventi e passare **a** Registri applicazioni e servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="visualizzatore eventi scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="ebb0e-157">Registri di Microsoft Defender Malware Protection</span><span class="sxs-lookup"><span data-stu-id="ebb0e-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="ebb0e-158">È inoltre possibile visualizzare gli eventi delle regole Antivirus Microsoft Defender tramite lo strumento da riga di comando dedicato, denominato , che può essere utilizzato per gestire e configurare e automatizzare le attività, `*mpcmdrun.exe*` se necessario.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="ebb0e-159">Questa utilità è presente in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="ebb0e-160">È necessario eseguirlo da un prompt dei comandi con privilegi elevati, ovvero esegui come amministratore.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="ebb0e-161">Per generare le informazioni di supporto, *digitareMpCmdRun.exe -getfiles*.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="ebb0e-162">Dopo un po', diversi log verranno archiviati in un archivio (MpSupportFiles.cab) e resi disponibili in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="registri di protezione antimalware":::

<span data-ttu-id="ebb0e-164">Estrai l'archivio e avrai molti file disponibili per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="ebb0e-165">I file più rilevanti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebb0e-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="ebb0e-166">**MPOperationalEvents.txt-** Questo file contiene lo stesso livello di informazioni disponibili nel Visualizzatore eventi per Windows Defender del registro operativo di Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="ebb0e-167">**MPRegistry.txt:** in questo file è possibile analizzare tutte le configurazioni Windows Defender corrente, dal momento in cui i registri di supporto sono stati acquisiti.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="ebb0e-168">**MPLog.txt:** questo registro contiene informazioni più dettagliate su tutte le azioni/operazioni dell'Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="ebb0e-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
