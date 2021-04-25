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
ms.openlocfilehash: a1e07ac2e2e544605f04e9090177004db64d2f04
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994998"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="5ae2a-104">Novità di Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="5ae2a-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ae2a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5ae2a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ae2a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5ae2a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ae2a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ae2a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5ae2a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5ae2a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ae2a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="5ae2a-110">In macOS 11 (Big Sur), Microsoft Defender for Endpoint richiede profili di configurazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="5ae2a-111">Se sei un cliente esistente che esegue l'aggiornamento da versioni precedenti di macOS, assicurati di distribuire i profili di configurazione aggiuntivi elencati [in questa pagina.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="5ae2a-112">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-112">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="5ae2a-113">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-113">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="5ae2a-114">Questa correzione ripristina la funzionalità di gestione delle & (TVM, Threat & Vulnerability Management).</span><span class="sxs-lookup"><span data-stu-id="5ae2a-114">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="5ae2a-115">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-115">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="5ae2a-116">Microsoft Defender per Endpoint su macOS è ora disponibile in anteprima per i clienti del governo degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-116">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="5ae2a-117">Per altre informazioni, vedi [Microsoft Defender for Endpoint per i clienti del governo statunitense.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-117">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="5ae2a-118">Miglioramenti delle prestazioni (in particolare per la situazione in cui viene usata l'app XCode Simulator) & correzioni di bug.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-118">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="5ae2a-119">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-119">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="5ae2a-120">È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-120">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="5ae2a-121">Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="5ae2a-121">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="5ae2a-122">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-122">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="5ae2a-123">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-123">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="5ae2a-124">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-124">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="5ae2a-125">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-125">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="5ae2a-126">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-126">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="5ae2a-127">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-127">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="5ae2a-128">La sintassi dello strumento da riga di comando precedente è stata deprecata con questa versione.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-128">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="5ae2a-129">Per informazioni sulla nuova sintassi, vedere [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="5ae2a-129">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="5ae2a-130">È stata aggiunta una nuova opzione della riga di comando per disabilitare l'estensione di rete: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="5ae2a-130">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="5ae2a-131">Questo comando può essere utile per risolvere i problemi di rete che potrebbero essere correlati a Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="5ae2a-131">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="5ae2a-132">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-132">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="5ae2a-133">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-133">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="5ae2a-134">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-134">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="5ae2a-135">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-135">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="5ae2a-136">Miglioramento dell'affidabilità dell'agente durante l'esecuzione in macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="5ae2a-136">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="5ae2a-137">È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="5ae2a-137">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="5ae2a-138">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-138">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="5ae2a-139">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-139">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="5ae2a-140">Condizioni rimosse quando Microsoft Defender for Endpoint attivava un bug macOS 11 (Big Sur) che si manifesta in un kernel in stato di panico</span><span class="sxs-lookup"><span data-stu-id="5ae2a-140">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="5ae2a-141">È stata corretta una perdita di memoria nell'estensione di sistema di Endpoint Security durante l'esecuzione su mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-141">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="5ae2a-142">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-142">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="5ae2a-143">101.10.72</span><span class="sxs-lookup"><span data-stu-id="5ae2a-143">101.10.72</span></span>

- <span data-ttu-id="5ae2a-144">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-144">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="5ae2a-145">101.09.61</span><span class="sxs-lookup"><span data-stu-id="5ae2a-145">101.09.61</span></span>

- <span data-ttu-id="5ae2a-146">È stata aggiunta una nuova preferenza gestita per [disabilitare l'opzione per inviare feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-146">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="5ae2a-147">L'icona del menu Stato ora mostra uno stato integro quando vengono gestite le impostazioni del prodotto.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-147">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="5ae2a-148">In precedenza, l'icona del menu di stato visualizzava uno stato di avviso o di errore, anche se le impostazioni del prodotto erano gestite dall'amministratore</span><span class="sxs-lookup"><span data-stu-id="5ae2a-148">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="5ae2a-149">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-149">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="5ae2a-150">101.09.50</span><span class="sxs-lookup"><span data-stu-id="5ae2a-150">101.09.50</span></span>

- <span data-ttu-id="5ae2a-151">Questa versione del prodotto è stata convalidata in macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="5ae2a-151">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="5ae2a-152">La nuova sintassi per `mdatp` lo strumento da riga di comando è ora quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-152">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="5ae2a-153">Per altre informazioni sulla nuova sintassi, vedi [Risorse per Microsoft Defender per Endpoint su macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-153">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="5ae2a-154">La sintassi dello strumento da riga di comando precedente verrà rimossa dal prodotto il **1° gennaio 2021.**</span><span class="sxs-lookup"><span data-stu-id="5ae2a-154">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="5ae2a-155">Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa</span><span class="sxs-lookup"><span data-stu-id="5ae2a-155">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="5ae2a-156">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-156">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="5ae2a-157">101.09.49</span><span class="sxs-lookup"><span data-stu-id="5ae2a-157">101.09.49</span></span>

- <span data-ttu-id="5ae2a-158">Miglioramenti dell'interfaccia utente per distinguere le esclusioni gestite dall'amministratore IT rispetto alle esclusioni definite dall'utente locale</span><span class="sxs-lookup"><span data-stu-id="5ae2a-158">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="5ae2a-159">Miglioramento dell'utilizzo della CPU durante le analisi su richiesta</span><span class="sxs-lookup"><span data-stu-id="5ae2a-159">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="5ae2a-160">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-160">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="5ae2a-161">101.07.23</span><span class="sxs-lookup"><span data-stu-id="5ae2a-161">101.07.23</span></span>

- <span data-ttu-id="5ae2a-162">Sono stati aggiunti nuovi campi all'output di `mdatp --health` per controllare lo stato della modalità passiva e l'ID gruppo EDR</span><span class="sxs-lookup"><span data-stu-id="5ae2a-162">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="5ae2a-163">`mdatp --health` verrà sostituito con `mdatp health` in un aggiornamento futuro del prodotto.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-163">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="5ae2a-164">È stato risolto un bug in cui l'invio automatico di esempio non era contrassegnato come gestito nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="5ae2a-164">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="5ae2a-165">Sono state aggiunte nuove impostazioni per il controllo della conservazione degli elementi nella cronologia dell'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-165">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="5ae2a-166">È ora possibile specificare il numero di giorni per [conservare](mac-preferences.md#antivirus-scan-history-retention-in-days) gli elementi nella cronologia analisi e specificare il numero massimo di elementi [nella cronologia analisi](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-166">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="5ae2a-167">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-167">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="5ae2a-168">101.06.63</span><span class="sxs-lookup"><span data-stu-id="5ae2a-168">101.06.63</span></span>

- <span data-ttu-id="5ae2a-169">È stata affrontata una regressione delle prestazioni introdotta nella versione `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="5ae2a-169">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="5ae2a-170">La regressione è stata introdotta con la correzione per eliminare i problemi del kernel osservati da alcuni clienti durante l'accesso alle condivisioni SMB.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-170">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="5ae2a-171">Abbiamo ripristinato questa modifica del codice e stiamo esaminando modi alternativi per eliminare il panico del kernel.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-171">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="5ae2a-172">101.05.17</span><span class="sxs-lookup"><span data-stu-id="5ae2a-172">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ae2a-173">Stiamo lavorando a una sintassi nuova e migliorata per lo `mdatp` strumento da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-173">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="5ae2a-174">La nuova sintassi è attualmente l'impostazione predefinita nei canali di aggiornamento Insider Fast e Insider Slow.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-174">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="5ae2a-175">Ti invitiamo a utilizzare questa nuova sintassi.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-175">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="5ae2a-176">Continueremo a supportare la vecchia sintassi in parallelo con la nuova sintassi e forniremo maggiori comunicazioni sul piano di deprecazione per la sintassi precedente nei prossimi mesi.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-176">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="5ae2a-177">È stato provocato un problema di kernel che si verificava a volte durante l'accesso alle condivisioni file SMB</span><span class="sxs-lookup"><span data-stu-id="5ae2a-177">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="5ae2a-178">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-178">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="5ae2a-179">101.05.16</span><span class="sxs-lookup"><span data-stu-id="5ae2a-179">101.05.16</span></span>

- <span data-ttu-id="5ae2a-180">Miglioramenti alla logica di analisi rapida per ridurre in modo significativo il numero di file analizzati</span><span class="sxs-lookup"><span data-stu-id="5ae2a-180">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="5ae2a-181">È [stato aggiunto il supporto per il completamento automatico](mac-resources.md#how-to-enable-autocompletion) per lo strumento da riga di comando</span><span class="sxs-lookup"><span data-stu-id="5ae2a-181">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="5ae2a-182">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-182">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="5ae2a-183">101.03.12</span><span class="sxs-lookup"><span data-stu-id="5ae2a-183">101.03.12</span></span>

- <span data-ttu-id="5ae2a-184">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-184">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="5ae2a-185">101.01.54</span><span class="sxs-lookup"><span data-stu-id="5ae2a-185">101.01.54</span></span>

- <span data-ttu-id="5ae2a-186">Miglioramenti relativi alla compatibilità con Time Machine</span><span class="sxs-lookup"><span data-stu-id="5ae2a-186">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="5ae2a-187">Miglioramenti dell'accessibilità</span><span class="sxs-lookup"><span data-stu-id="5ae2a-187">Accessibility improvements</span></span>
- <span data-ttu-id="5ae2a-188">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-188">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="5ae2a-189">101.00.31</span><span class="sxs-lookup"><span data-stu-id="5ae2a-189">101.00.31</span></span>

- <span data-ttu-id="5ae2a-190">Esperienza [di onboarding dei prodotti migliorata per gli utenti di Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-190">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="5ae2a-191">Le [esclusioni antivirus ora supportano i caratteri jolly](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-191">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="5ae2a-192">È stata aggiunta la possibilità di attivare le analisi antivirus dal menu contestuale di macOS.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-192">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="5ae2a-193">Ora puoi fare clic con il pulsante destro del mouse su un file o una cartella nel Finder e selezionare **Analizza con Microsoft Defender for Endpoint**</span><span class="sxs-lookup"><span data-stu-id="5ae2a-193">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="5ae2a-194">I downgrade sul posto dei prodotti sono ora esplicitamente non consentiti dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-194">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="5ae2a-195">Se devi eseguire il downgrade, disinstalla prima la versione esistente e riconfigura il dispositivo</span><span class="sxs-lookup"><span data-stu-id="5ae2a-195">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="5ae2a-196">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-196">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="5ae2a-197">100.90.27</span><span class="sxs-lookup"><span data-stu-id="5ae2a-197">100.90.27</span></span>

- <span data-ttu-id="5ae2a-198">Ora puoi impostare [un canale di](mac-updates.md#set-the-channel-name) aggiornamento per Microsoft Defender per Endpoint in macOS diverso dal canale di aggiornamento a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="5ae2a-198">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="5ae2a-199">Icona Nuovo prodotto</span><span class="sxs-lookup"><span data-stu-id="5ae2a-199">New product icon</span></span>
- <span data-ttu-id="5ae2a-200">Altri miglioramenti dell'esperienza utente</span><span class="sxs-lookup"><span data-stu-id="5ae2a-200">Other user experience improvements</span></span>
- <span data-ttu-id="5ae2a-201">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-201">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="5ae2a-202">100.86.92</span><span class="sxs-lookup"><span data-stu-id="5ae2a-202">100.86.92</span></span>

- <span data-ttu-id="5ae2a-203">Miglioramenti relativi alla compatibilità con Time Machine</span><span class="sxs-lookup"><span data-stu-id="5ae2a-203">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="5ae2a-204">È stato risolto un problema per cui il prodotto a volte non puliva tutti i file durante `/Library/Application Support/Microsoft/Defender` la disinstallazione</span><span class="sxs-lookup"><span data-stu-id="5ae2a-204">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="5ae2a-205">Riduzione dell'utilizzo della CPU del prodotto quando i prodotti Microsoft vengono aggiornati tramite Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="5ae2a-205">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="5ae2a-206">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-206">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="5ae2a-207">100.86.91</span><span class="sxs-lookup"><span data-stu-id="5ae2a-207">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="5ae2a-208">Per garantire la protezione più completa per i dispositivi macOS e in linea con l'interruzione della distribuzione di aggiornamenti della sicurezza nativa di Apple a versioni del sistema operativo precedenti a [current – 2], la distribuzione e gli aggiornamenti di MDATP per Mac non saranno più supportati in macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="5ae2a-208">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="5ae2a-209">Gli aggiornamenti e i miglioramenti di MDATP per Mac verranno recapitati ai dispositivi che eseguono versioni Catalina [10.15], Mojave [10.14] e High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="5ae2a-209">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="5ae2a-210">Se nei dispositivi Sierra [10.12] è già stato distribuito MDATP per Mac, eseguire l'aggiornamento alla versione più recente di macOS per eliminare i rischi di perdita della protezione.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-210">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="5ae2a-211">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-211">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="5ae2a-212">100.83.73</span><span class="sxs-lookup"><span data-stu-id="5ae2a-212">100.83.73</span></span>

- <span data-ttu-id="5ae2a-213">Sono stati aggiunti altri controlli per gli amministratori IT sulla gestione [delle](mac-preferences.md#exclusion-merge-policy)esclusioni, sulla [gestione delle](mac-preferences.md#threat-type-settings-merge-policy)impostazioni del tipo di minaccia e sulle azioni di minaccia [non consentite](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-213">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="5ae2a-214">Quando l'accesso completo al disco non è abilitato nel dispositivo, nel menu di stato viene visualizzato un avviso</span><span class="sxs-lookup"><span data-stu-id="5ae2a-214">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="5ae2a-215">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-215">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="5ae2a-216">100.82.60</span><span class="sxs-lookup"><span data-stu-id="5ae2a-216">100.82.60</span></span>

- <span data-ttu-id="5ae2a-217">È stato risolto un problema a causa del quale il prodotto non riesce a iniziare dopo un aggiornamento delle definizioni.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-217">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="5ae2a-218">100.80.42</span><span class="sxs-lookup"><span data-stu-id="5ae2a-218">100.80.42</span></span>

- <span data-ttu-id="5ae2a-219">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-219">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="5ae2a-220">100.79.42</span><span class="sxs-lookup"><span data-stu-id="5ae2a-220">100.79.42</span></span>

- <span data-ttu-id="5ae2a-221">È stato risolto un problema a causa del quale Microsoft Defender per Endpoint sul Mac interferiva con Time Machine</span><span class="sxs-lookup"><span data-stu-id="5ae2a-221">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="5ae2a-222">È stata aggiunta una nuova opzione all'utilità della riga di comando per testare la connettività con il servizio back-end</span><span class="sxs-lookup"><span data-stu-id="5ae2a-222">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="5ae2a-223">Aggiunta della possibilità di visualizzare la cronologia completa delle minacce nell'interfaccia utente (è possibile accedervi dalla **visualizzazione Cronologia protezione)**</span><span class="sxs-lookup"><span data-stu-id="5ae2a-223">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="5ae2a-224">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-224">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="5ae2a-225">100.72.15</span><span class="sxs-lookup"><span data-stu-id="5ae2a-225">100.72.15</span></span>

- <span data-ttu-id="5ae2a-226">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-226">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="5ae2a-227">100.70.99</span><span class="sxs-lookup"><span data-stu-id="5ae2a-227">100.70.99</span></span>

- <span data-ttu-id="5ae2a-228">È stato risolto un problema che influisce sulla possibilità di alcuni utenti di eseguire l'aggiornamento a macOS Catalina quando è abilitata la protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-228">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="5ae2a-229">Questo problema sporadico è stato causato da Microsoft Defender per i file di blocco degli endpoint all'interno del pacchetto di aggiornamento Catalina durante l'analisi delle minacce, causando errori nella sequenza di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-229">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="5ae2a-230">100.68.99</span><span class="sxs-lookup"><span data-stu-id="5ae2a-230">100.68.99</span></span>

- <span data-ttu-id="5ae2a-231">È stata aggiunta la possibilità di configurare la funzionalità antivirus per l'esecuzione in [modalità passiva](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-231">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="5ae2a-232">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-232">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="5ae2a-233">100.65.28</span><span class="sxs-lookup"><span data-stu-id="5ae2a-233">100.65.28</span></span>

- <span data-ttu-id="5ae2a-234">Aggiunta del supporto per macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="5ae2a-234">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="5ae2a-235">macOS 10.15 (Catalina) contiene nuovi miglioramenti alla sicurezza e alla privacy.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-235">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="5ae2a-236">A partire da questa versione, per impostazione predefinita, le applicazioni non sono in grado di accedere a determinate posizioni sul disco (ad esempio Documenti, Download, Desktop e così via) senza il consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-236">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="5ae2a-237">In assenza di questo consenso, Microsoft Defender for Endpoint non è in grado di proteggere completamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-237">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="5ae2a-238">Il meccanismo per concedere questo consenso dipende dalla modalità di distribuzione di Microsoft Defender per Endpoint:</span><span class="sxs-lookup"><span data-stu-id="5ae2a-238">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="5ae2a-239">Per le distribuzioni manuali, vedere le istruzioni aggiornate [nell'argomento Distribuzione](mac-install-manually.md#how-to-allow-full-disk-access) manuale.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-239">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="5ae2a-240">Per le distribuzioni gestite, vedere le istruzioni aggiornate negli argomenti sulla distribuzione basata su [JAMF](mac-install-with-jamf.md) e sulla distribuzione basata [su Microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="5ae2a-240">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="5ae2a-241">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="5ae2a-241">Performance improvements & bug fixes</span></span>
