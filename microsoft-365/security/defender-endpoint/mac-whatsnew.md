---
title: Novità di Microsoft Defender per Endpoint su Mac
description: Informazioni sulle modifiche principali per le versioni precedenti di Microsoft Defender per Endpoint su Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, macos, novità
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 6348d688103c51176fbed36c923a660c77a2258d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842783"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="a0443-104">Novità di Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="a0443-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0443-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a0443-105">**Applies to:**</span></span>
- [<span data-ttu-id="a0443-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a0443-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a0443-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0443-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a0443-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a0443-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a0443-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a0443-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="a0443-110">In macOS 11 (Big Sur), Microsoft Defender for Endpoint richiede profili di configurazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="a0443-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="a0443-111">Se sei un cliente esistente che esegue l'aggiornamento da versioni precedenti di macOS, assicurati di distribuire i profili di configurazione aggiuntivi elencati [in questa pagina.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a0443-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="a0443-112">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-112">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="a0443-113">A partire da questa versione, le minacce rilevate durante le analisi antivirus su richiesta attivate tramite il client della riga di comando vengono corretti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a0443-113">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="a0443-114">Le minacce rilevate durante le analisi attivate tramite l'interfaccia utente richiedono comunque un'azione manuale.</span><span class="sxs-lookup"><span data-stu-id="a0443-114">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="a0443-115">`mdatp diagnostic real-time-protection-statistics` ora supporta due opzioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="a0443-115">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="a0443-116">`--sort`: ordina l'output in ordine decrescente in base al numero totale di file analizzati</span><span class="sxs-lookup"><span data-stu-id="a0443-116">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="a0443-117">`--top N`: visualizza i primi N risultati (funziona solo se `--sort` viene specificato anche)</span><span class="sxs-lookup"><span data-stu-id="a0443-117">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="a0443-118">Miglioramenti delle prestazioni (in particolare per l'utilizzo di YARN) & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-118">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="a0443-119">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-119">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="a0443-120">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span><span class="sxs-lookup"><span data-stu-id="a0443-120">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="a0443-121">Questa correzione ripristina la funzionalità di gestione delle & (TVM, Threat & Vulnerability Management).</span><span class="sxs-lookup"><span data-stu-id="a0443-121">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="a0443-122">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-122">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="a0443-123">Microsoft Defender per Endpoint su macOS è ora disponibile in anteprima per i clienti del governo degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="a0443-123">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="a0443-124">Per altre informazioni, vedi [Microsoft Defender for Endpoint per i clienti del governo statunitense.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="a0443-124">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="a0443-125">Miglioramenti delle prestazioni (in particolare per la situazione in cui viene usata l'app XCode Simulator) & correzioni di bug.</span><span class="sxs-lookup"><span data-stu-id="a0443-125">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="a0443-126">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-126">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="a0443-127">È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="a0443-127">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="a0443-128">Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="a0443-128">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="a0443-129">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-129">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="a0443-130">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-130">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="a0443-131">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-131">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="a0443-132">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-132">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="a0443-133">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-133">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="a0443-134">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-134">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="a0443-135">La sintassi dello strumento da riga di comando precedente è stata deprecata con questa versione.</span><span class="sxs-lookup"><span data-stu-id="a0443-135">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="a0443-136">Per informazioni sulla nuova sintassi, vedere [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="a0443-136">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="a0443-137">È stata aggiunta una nuova opzione della riga di comando per disabilitare l'estensione di rete: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="a0443-137">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="a0443-138">Questo comando può essere utile per risolvere i problemi di rete che potrebbero essere correlati a Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="a0443-138">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="a0443-139">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-139">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="a0443-140">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-140">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="a0443-141">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-141">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="a0443-142">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-142">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="a0443-143">Miglioramento dell'affidabilità dell'agente durante l'esecuzione in macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="a0443-143">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="a0443-144">È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="a0443-144">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="a0443-145">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-145">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="a0443-146">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="a0443-146">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="a0443-147">Condizioni rimosse quando Microsoft Defender for Endpoint attivava un bug macOS 11 (Big Sur) che si manifesta in un kernel in stato di panico</span><span class="sxs-lookup"><span data-stu-id="a0443-147">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="a0443-148">È stata corretta una perdita di memoria nell'estensione di sistema di Endpoint Security durante l'esecuzione su mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="a0443-148">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="a0443-149">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-149">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="a0443-150">101.10.72</span><span class="sxs-lookup"><span data-stu-id="a0443-150">101.10.72</span></span>

- <span data-ttu-id="a0443-151">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-151">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="a0443-152">101.09.61</span><span class="sxs-lookup"><span data-stu-id="a0443-152">101.09.61</span></span>

- <span data-ttu-id="a0443-153">È stata aggiunta una nuova preferenza gestita per [disabilitare l'opzione per inviare feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="a0443-153">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="a0443-154">L'icona del menu Stato ora mostra uno stato integro quando vengono gestite le impostazioni del prodotto.</span><span class="sxs-lookup"><span data-stu-id="a0443-154">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="a0443-155">In precedenza, l'icona del menu di stato visualizzava uno stato di avviso o di errore, anche se le impostazioni del prodotto erano gestite dall'amministratore</span><span class="sxs-lookup"><span data-stu-id="a0443-155">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="a0443-156">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-156">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="a0443-157">101.09.50</span><span class="sxs-lookup"><span data-stu-id="a0443-157">101.09.50</span></span>

- <span data-ttu-id="a0443-158">Questa versione del prodotto è stata convalidata in macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="a0443-158">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="a0443-159">La nuova sintassi per `mdatp` lo strumento da riga di comando è ora quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="a0443-159">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="a0443-160">Per altre informazioni sulla nuova sintassi, vedi [Risorse per Microsoft Defender per Endpoint su macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="a0443-160">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="a0443-161">La sintassi dello strumento da riga di comando precedente verrà rimossa dal prodotto il **1° gennaio 2021.**</span><span class="sxs-lookup"><span data-stu-id="a0443-161">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="a0443-162">Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa</span><span class="sxs-lookup"><span data-stu-id="a0443-162">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="a0443-163">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-163">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="a0443-164">101.09.49</span><span class="sxs-lookup"><span data-stu-id="a0443-164">101.09.49</span></span>

- <span data-ttu-id="a0443-165">Miglioramenti dell'interfaccia utente per distinguere le esclusioni gestite dall'amministratore IT rispetto alle esclusioni definite dall'utente locale</span><span class="sxs-lookup"><span data-stu-id="a0443-165">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="a0443-166">Miglioramento dell'utilizzo della CPU durante le analisi su richiesta</span><span class="sxs-lookup"><span data-stu-id="a0443-166">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="a0443-167">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-167">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="a0443-168">101.07.23</span><span class="sxs-lookup"><span data-stu-id="a0443-168">101.07.23</span></span>

- <span data-ttu-id="a0443-169">Sono stati aggiunti nuovi campi all'output di per controllare lo stato della modalità passiva e `mdatp --health` l'ID EDR gruppo di lavoro</span><span class="sxs-lookup"><span data-stu-id="a0443-169">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="a0443-170">`mdatp --health` verrà sostituito con `mdatp health` in un aggiornamento futuro del prodotto.</span><span class="sxs-lookup"><span data-stu-id="a0443-170">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="a0443-171">È stato risolto un bug in cui l'invio automatico di esempio non era contrassegnato come gestito nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a0443-171">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="a0443-172">Sono state aggiunte nuove impostazioni per il controllo della conservazione degli elementi nella cronologia dell'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="a0443-172">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="a0443-173">È ora possibile specificare il numero di giorni per [conservare](mac-preferences.md#antivirus-scan-history-retention-in-days) gli elementi nella cronologia analisi e specificare il numero massimo di elementi [nella cronologia analisi](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="a0443-173">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="a0443-174">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-174">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="a0443-175">101.06.63</span><span class="sxs-lookup"><span data-stu-id="a0443-175">101.06.63</span></span>

- <span data-ttu-id="a0443-176">È stata affrontata una regressione delle prestazioni introdotta nella versione `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="a0443-176">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="a0443-177">La regressione è stata introdotta con la correzione per eliminare i problemi del kernel osservati da alcuni clienti durante l'accesso alle condivisioni SMB.</span><span class="sxs-lookup"><span data-stu-id="a0443-177">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="a0443-178">Abbiamo ripristinato questa modifica del codice e stiamo esaminando modi alternativi per eliminare il panico del kernel.</span><span class="sxs-lookup"><span data-stu-id="a0443-178">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="a0443-179">101.05.17</span><span class="sxs-lookup"><span data-stu-id="a0443-179">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0443-180">Stiamo lavorando a una sintassi nuova e migliorata per lo `mdatp` strumento da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a0443-180">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="a0443-181">La nuova sintassi è attualmente l'impostazione predefinita nei canali di aggiornamento Insider Fast e Insider Slow.</span><span class="sxs-lookup"><span data-stu-id="a0443-181">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="a0443-182">Ti invitiamo a utilizzare questa nuova sintassi.</span><span class="sxs-lookup"><span data-stu-id="a0443-182">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="a0443-183">Continueremo a supportare la vecchia sintassi in parallelo con la nuova sintassi e forniremo maggiori comunicazioni sul piano di deprecazione per la sintassi precedente nei prossimi mesi.</span><span class="sxs-lookup"><span data-stu-id="a0443-183">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="a0443-184">È stato provocato un problema di kernel che si verificava a volte durante l'accesso alle condivisioni file SMB</span><span class="sxs-lookup"><span data-stu-id="a0443-184">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="a0443-185">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-185">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="a0443-186">101.05.16</span><span class="sxs-lookup"><span data-stu-id="a0443-186">101.05.16</span></span>

- <span data-ttu-id="a0443-187">Miglioramenti alla logica di analisi rapida per ridurre in modo significativo il numero di file analizzati</span><span class="sxs-lookup"><span data-stu-id="a0443-187">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="a0443-188">È [stato aggiunto il supporto per il completamento automatico](mac-resources.md#how-to-enable-autocompletion) per lo strumento da riga di comando</span><span class="sxs-lookup"><span data-stu-id="a0443-188">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="a0443-189">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-189">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="a0443-190">101.03.12</span><span class="sxs-lookup"><span data-stu-id="a0443-190">101.03.12</span></span>

- <span data-ttu-id="a0443-191">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-191">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="a0443-192">101.01.54</span><span class="sxs-lookup"><span data-stu-id="a0443-192">101.01.54</span></span>

- <span data-ttu-id="a0443-193">Miglioramenti relativi alla compatibilità con Time Machine</span><span class="sxs-lookup"><span data-stu-id="a0443-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="a0443-194">Miglioramenti dell'accessibilità</span><span class="sxs-lookup"><span data-stu-id="a0443-194">Accessibility improvements</span></span>
- <span data-ttu-id="a0443-195">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-195">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="a0443-196">101.00.31</span><span class="sxs-lookup"><span data-stu-id="a0443-196">101.00.31</span></span>

- <span data-ttu-id="a0443-197">Esperienza [di onboarding dei prodotti migliorata per gli utenti di Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="a0443-197">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="a0443-198">Le [esclusioni antivirus ora supportano i caratteri jolly](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="a0443-198">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="a0443-199">È stata aggiunta la possibilità di attivare le analisi antivirus dal menu contestuale di macOS.</span><span class="sxs-lookup"><span data-stu-id="a0443-199">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="a0443-200">Ora puoi fare clic con il pulsante destro del mouse su un file o una cartella nel Finder e selezionare **Analizza con Microsoft Defender for Endpoint**</span><span class="sxs-lookup"><span data-stu-id="a0443-200">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="a0443-201">I downgrade sul posto dei prodotti sono ora esplicitamente non consentiti dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="a0443-201">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="a0443-202">Se devi eseguire il downgrade, disinstalla prima la versione esistente e riconfigura il dispositivo</span><span class="sxs-lookup"><span data-stu-id="a0443-202">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="a0443-203">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-203">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="a0443-204">100.90.27</span><span class="sxs-lookup"><span data-stu-id="a0443-204">100.90.27</span></span>

- <span data-ttu-id="a0443-205">Ora puoi impostare [un canale di](mac-updates.md#set-the-channel-name) aggiornamento per Microsoft Defender per Endpoint in macOS diverso dal canale di aggiornamento a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="a0443-205">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="a0443-206">Icona Nuovo prodotto</span><span class="sxs-lookup"><span data-stu-id="a0443-206">New product icon</span></span>
- <span data-ttu-id="a0443-207">Altri miglioramenti dell'esperienza utente</span><span class="sxs-lookup"><span data-stu-id="a0443-207">Other user experience improvements</span></span>
- <span data-ttu-id="a0443-208">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-208">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="a0443-209">100.86.92</span><span class="sxs-lookup"><span data-stu-id="a0443-209">100.86.92</span></span>

- <span data-ttu-id="a0443-210">Miglioramenti relativi alla compatibilità con Time Machine</span><span class="sxs-lookup"><span data-stu-id="a0443-210">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="a0443-211">È stato risolto un problema per cui il prodotto a volte non puliva tutti i file durante `/Library/Application Support/Microsoft/Defender` la disinstallazione</span><span class="sxs-lookup"><span data-stu-id="a0443-211">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="a0443-212">Riduzione dell'utilizzo della CPU del prodotto quando i prodotti Microsoft vengono aggiornati tramite Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="a0443-212">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="a0443-213">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-213">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="a0443-214">100.86.91</span><span class="sxs-lookup"><span data-stu-id="a0443-214">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="a0443-215">Per garantire la protezione più completa per i dispositivi macOS e in linea con l'interruzione della distribuzione di aggiornamenti della sicurezza nativa di Apple a versioni del sistema operativo precedenti a [corrente – 2], la distribuzione e gli aggiornamenti di MDATP per Mac non saranno più supportati in macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="a0443-215">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="a0443-216">MDATP aggiornamenti e miglioramenti per Mac verranno recapitati ai dispositivi che eseguono versioni Catalina [10.15], Mojave [10.14] e High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="a0443-216">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="a0443-217">Se hai già distribuito MDATP per Mac nei dispositivi Sierra [10.12], eseguire l'aggiornamento alla versione più recente di macOS per eliminare i rischi di perdita di protezione.</span><span class="sxs-lookup"><span data-stu-id="a0443-217">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="a0443-218">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-218">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="a0443-219">100.83.73</span><span class="sxs-lookup"><span data-stu-id="a0443-219">100.83.73</span></span>

- <span data-ttu-id="a0443-220">Sono stati aggiunti altri controlli per gli amministratori IT sulla gestione [delle](mac-preferences.md#exclusion-merge-policy)esclusioni, sulla [gestione delle](mac-preferences.md#threat-type-settings-merge-policy)impostazioni del tipo di minaccia e sulle azioni di minaccia [non consentite](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="a0443-220">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="a0443-221">Quando l'accesso completo al disco non è abilitato nel dispositivo, nel menu di stato viene visualizzato un avviso</span><span class="sxs-lookup"><span data-stu-id="a0443-221">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="a0443-222">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-222">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="a0443-223">100.82.60</span><span class="sxs-lookup"><span data-stu-id="a0443-223">100.82.60</span></span>

- <span data-ttu-id="a0443-224">È stato risolto un problema a causa del quale il prodotto non riesce a iniziare dopo un aggiornamento delle definizioni.</span><span class="sxs-lookup"><span data-stu-id="a0443-224">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="a0443-225">100.80.42</span><span class="sxs-lookup"><span data-stu-id="a0443-225">100.80.42</span></span>

- <span data-ttu-id="a0443-226">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-226">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="a0443-227">100.79.42</span><span class="sxs-lookup"><span data-stu-id="a0443-227">100.79.42</span></span>

- <span data-ttu-id="a0443-228">È stato risolto un problema a causa del quale Microsoft Defender per Endpoint sul Mac interferiva con Time Machine</span><span class="sxs-lookup"><span data-stu-id="a0443-228">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="a0443-229">È stata aggiunta una nuova opzione all'utilità della riga di comando per testare la connettività con il servizio back-end</span><span class="sxs-lookup"><span data-stu-id="a0443-229">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="a0443-230">Aggiunta della possibilità di visualizzare la cronologia completa delle minacce nell'interfaccia utente (è possibile accedervi dalla **visualizzazione Cronologia protezione)**</span><span class="sxs-lookup"><span data-stu-id="a0443-230">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="a0443-231">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-231">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="a0443-232">100.72.15</span><span class="sxs-lookup"><span data-stu-id="a0443-232">100.72.15</span></span>

- <span data-ttu-id="a0443-233">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-233">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="a0443-234">100.70.99</span><span class="sxs-lookup"><span data-stu-id="a0443-234">100.70.99</span></span>

- <span data-ttu-id="a0443-235">È stato risolto un problema che influisce sulla possibilità di alcuni utenti di eseguire l'aggiornamento a macOS Catalina quando è abilitata la protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="a0443-235">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="a0443-236">Questo problema sporadico è stato causato da Microsoft Defender per i file di blocco degli endpoint all'interno del pacchetto di aggiornamento Catalina durante l'analisi delle minacce, causando errori nella sequenza di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a0443-236">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="a0443-237">100.68.99</span><span class="sxs-lookup"><span data-stu-id="a0443-237">100.68.99</span></span>

- <span data-ttu-id="a0443-238">È stata aggiunta la possibilità di configurare la funzionalità antivirus per l'esecuzione in [modalità passiva](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="a0443-238">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="a0443-239">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-239">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="a0443-240">100.65.28</span><span class="sxs-lookup"><span data-stu-id="a0443-240">100.65.28</span></span>

- <span data-ttu-id="a0443-241">Aggiunta del supporto per macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="a0443-241">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="a0443-242">macOS 10.15 (Catalina) contiene nuovi miglioramenti alla sicurezza e alla privacy.</span><span class="sxs-lookup"><span data-stu-id="a0443-242">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="a0443-243">A partire da questa versione, per impostazione predefinita, le applicazioni non sono in grado di accedere a determinate posizioni sul disco (ad esempio Documenti, Download, Desktop e così via) senza il consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="a0443-243">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="a0443-244">In assenza di questo consenso, Microsoft Defender for Endpoint non è in grado di proteggere completamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0443-244">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="a0443-245">Il meccanismo per concedere questo consenso dipende dalla modalità di distribuzione di Microsoft Defender per Endpoint:</span><span class="sxs-lookup"><span data-stu-id="a0443-245">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="a0443-246">Per le distribuzioni manuali, vedere le istruzioni aggiornate [nell'argomento Distribuzione](mac-install-manually.md#how-to-allow-full-disk-access) manuale.</span><span class="sxs-lookup"><span data-stu-id="a0443-246">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="a0443-247">Per le distribuzioni gestite, vedere le istruzioni aggiornate negli argomenti sulla distribuzione basata su [JAMF](mac-install-with-jamf.md) [Microsoft Intune e sulla distribuzione basata su](mac-install-with-intune.md#create-system-configuration-profiles) Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="a0443-247">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="a0443-248">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="a0443-248">Performance improvements & bug fixes</span></span>
