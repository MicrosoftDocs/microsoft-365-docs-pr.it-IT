---
title: Analisi di regressione della memoria
description: Come dedurre la regressione della memoria
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323105"
---
# <a name="memory-regression-analysis"></a><span data-ttu-id="67c98-103">Analisi di regressione della memoria</span><span class="sxs-lookup"><span data-stu-id="67c98-103">Memory Regression Analysis</span></span>

<span data-ttu-id="67c98-104">Test Base consente di notare con maggiore chiarezza un aumento significativo dell'utilizzo della memoria nelle macchine virtuali di test che eseguono le app.</span><span class="sxs-lookup"><span data-stu-id="67c98-104">Test Base helps you more clearly notice significant memory usage increases in the test VMs running your apps.</span></span> <span data-ttu-id="67c98-105">Le metriche delle prestazioni, ad esempio l'utilizzo della memoria, possono essere indicative dell'integrità complessiva dell'applicazione e riteniamo che questa aggiunta aiuterà notevolmente a mantenere le prestazioni ottimali delle tue app.</span><span class="sxs-lookup"><span data-stu-id="67c98-105">Performance metrics, such as memory usage, can be indicative of overall application health and we believe this addition will greatly help keep your apps performing optimally.</span></span>

<span data-ttu-id="67c98-106">Continua a leggere per altri dettagli o guarda questo video per una breve panoramica dei miglioramenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="67c98-106">Read on for more details or watch this video for a quick walk through of the latest improvements.</span></span> 

<span data-ttu-id="67c98-107">Per ulteriori informazioni sulla base di test per la capacità di M365 di facilitare l'analisi di regressione, vedere Risultati di regressione basati sull'affidabilità del processo.</span><span class="sxs-lookup"><span data-stu-id="67c98-107">For more information on Test Base for M365's ability to help with regression analysis, see Regression results based on process reliability.</span></span>

<span data-ttu-id="67c98-108"><b>Analisi più ravvicinata delle regressioni della memoria</b></span><span class="sxs-lookup"><span data-stu-id="67c98-108"><b>Looking closer at memory regressions</b></span></span>

<span data-ttu-id="67c98-109">La base di test per il dashboard di M365 mostra la memoria utilizzata dall'applicazione in un nuovo aggiornamento Windows pre-rilasciato e la confronta con la memoria utilizzata dall'ultimo aggiornamento Windows rilasciato.</span><span class="sxs-lookup"><span data-stu-id="67c98-109">The Test Base for M365 dashboard shows the memory consumed by your application on a new pre-released Windows update and compares it with the memory used by the last released Windows update.</span></span> 

<span data-ttu-id="67c98-110">Con i miglioramenti di questo mese, l'analisi di regressione della memoria è ora disponibile nei processi preferiti.</span><span class="sxs-lookup"><span data-stu-id="67c98-110">With this month’s enhancements, memory regression analysis is now featured in your favorited processes.</span></span> <span data-ttu-id="67c98-111">Le applicazioni possono contenere più processi ed è possibile selezionare manualmente i processi preferiti tramite la scheda Affidabilità. Il servizio identificherà quindi le regressioni di memoria in questi processi preferiti confrontando le esecuzioni dei test tra Windows versioni di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="67c98-111">Applications can contain multiple processes and you can manually select your favorite processes through the Reliability tab. Our service will then identify memory regressions in these favorited processes while comparing test runs across different Windows update releases.</span></span> <span data-ttu-id="67c98-112">Se viene rilevata una regressione, i dettagli sulla regressione sono facilmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="67c98-112">If a regression is detected, details about the regression are easily available.</span></span>

<span data-ttu-id="67c98-113">Esamini ora questa funzionalità in dettaglio e discutono come risolvere i problemi relativi alle regressioni della memoria usando Windows Performance Analyzer.</span><span class="sxs-lookup"><span data-stu-id="67c98-113">Now let's look at this feature in detail and discuss how you can troubleshoot memory regressions using Windows Performance Analyzer.</span></span>

<span data-ttu-id="67c98-114">Il segnale di errore causato da una regressione della memoria viene visualizzato nel dashboard Test Base per M365 nella pagina Risultati dei test in Utilizzo memoria:</span><span class="sxs-lookup"><span data-stu-id="67c98-114">The failure signal caused by a memory regression is shown in the Test Base for M365 dashboard on the Test results page under Memory Utilization:</span></span>

![Risultati dell'utilizzo della memoria](Media/01_memory-utilization-results.png)


<span data-ttu-id="67c98-116">L'errore dell'applicazione a causa di un consumo di memoria maggiore verrà visualizzato anche come ```Fail``` nella pagina Riepilogo test:</span><span class="sxs-lookup"><span data-stu-id="67c98-116">Failure for the application due to higher memory consumption, will also be displayed as ```Fail``` on the Test Summary page:</span></span>

![Risultati di riepilogo dei test](Media/02_test-summary.png)

<span data-ttu-id="67c98-118">Fornendo questi segnali di errore in anticipo, il nostro obiettivo è contrassegnare chiaramente i potenziali problemi che possono interrompere e influire sull'esperienza dell'utente finale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="67c98-118">By providing these failure signals upfront, our goal is to clearly flag potential issues that can disrupt and impact the end user experience for your application.</span></span> 

<span data-ttu-id="67c98-119">È quindi possibile scaricare i file di registro e usare l Windows Performance Analyzer o il toolkit preferito per analizzare ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="67c98-119">You can then download the log files and use the Windows Performance Analyzer, or your preferred toolkit, to investigate further.</span></span> <span data-ttu-id="67c98-120">È inoltre possibile collaborare con il team test di base per M365 per risolvere il problema e evitare problemi che influiscono sugli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="67c98-120">You can also work jointly with the Test Base for M365 team on remediating the issue and help prevent issues impacting end users.</span></span>

<span data-ttu-id="67c98-121">I segnali di memoria vengono acquisiti nella scheda Utilizzo memoria nella base di test per il servizio M365 per tutte le esecuzioni dei test.</span><span class="sxs-lookup"><span data-stu-id="67c98-121">Memory signals are captured in the Memory Utilization tab in the Test Base for M365 service for all test runs.</span></span> <span data-ttu-id="67c98-122">L'esempio seguente mostra una recente esecuzione dei test con l'applicazione onboarded "Smoke Test Memory Stress" rispetto all'aggiornamento della sicurezza di agosto 2020 non definitiva.</span><span class="sxs-lookup"><span data-stu-id="67c98-122">The example below shows a recent test run with the onboarded application “Smoke Test Memory Stress” against the pre-release August 2020 security update.</span></span> <span data-ttu-id="67c98-123">Questa applicazione è stata scritta dal team per illustrare le regressioni della memoria.</span><span class="sxs-lookup"><span data-stu-id="67c98-123">(This application was written by our team to illustrate memory regressions.)</span></span>

![Risultati di regressione della memoria](Media/03_memory-regression%20comparison.png)

<span data-ttu-id="67c98-125">In questo esempio, il processo preferito "USLTestMemoryStress.exe" ha utilizzato una media di circa 100 MB nell'aggiornamento di agosto non definitiva rispetto all'aggiornamento di luglio rilasciato, quindi la base di test per M365 ha identificato una regressione.</span><span class="sxs-lookup"><span data-stu-id="67c98-125">In this example, the favorite process “USLTestMemoryStress.exe” process consumed an average of approximately 100 MB on the pre-release August update compared to the released July update, hence the Test Base for M365 identified a regression.</span></span> 

<span data-ttu-id="67c98-126">Anche gli altri processi, indicati come "USLTestMemoryStress_Aux1.exe" e "USLTestMemoryStress_Aux2.exe", appartengono alla stessa applicazione, ma hanno consumato circa la stessa quantità di memoria per le due versioni in modo che "superano" e siano considerati integri.</span><span class="sxs-lookup"><span data-stu-id="67c98-126">The other processes—shown here as “USLTestMemoryStress_Aux1.exe” and “USLTestMemoryStress_Aux2.exe”—also belong to the same application, but consumed approximately the same amount of memory for the two releases so they "passed" and were considered healthy.</span></span>

<span data-ttu-id="67c98-127">La regressione nel processo principale è stata determinata come "statisticamente significativa" in modo che il servizio comunicava ed evidenziava questa differenza per l'utente.</span><span class="sxs-lookup"><span data-stu-id="67c98-127">The regression on the main process was determined to be “statistically significant” so the service communicated and highlighted this difference to the user.</span></span> <span data-ttu-id="67c98-128">Se il confronto non fosse statisticamente significativo, non verrà evidenziato.</span><span class="sxs-lookup"><span data-stu-id="67c98-128">If the comparison was not statistically significant, it would not be highlighted.</span></span> <span data-ttu-id="67c98-129">L'utilizzo della memoria può essere rumoroso, quindi usiamo modelli statistici per distinguere, tra build e rilasci, differenze significative dalle differenze inconsequenziali.</span><span class="sxs-lookup"><span data-stu-id="67c98-129">Memory utilization can be noisy, so we use statistical models to distinguish, across builds and releases, meaningful differences from inconsequential differences.</span></span> 

<span data-ttu-id="67c98-130">Un confronto può essere raramente contrassegnato quando non esiste alcuna differenza reale (un falso positivo), ma si tratta di un compromesso necessario per migliorare la probabilità di identificare correttamente le regressioni (o i veri positivi).</span><span class="sxs-lookup"><span data-stu-id="67c98-130">A comparison may rarely be flagged when there is no true difference (a false positive), but this is a necessary tradeoff to improve the likelihood of correctly identifying regressions (or true positives.)</span></span>

<span data-ttu-id="67c98-131">Il passaggio successivo consiste nel comprendere cosa ha causato la regressione della memoria.</span><span class="sxs-lookup"><span data-stu-id="67c98-131">The next step is to understand what caused the memory regression.</span></span> <span data-ttu-id="67c98-132">È possibile scaricare i file ZIP per entrambe le esecuzioni dall'opzione Scarica file di registro, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="67c98-132">You can download the zip files for both executions from the Download log files option, as shown below.</span></span> 

<span data-ttu-id="67c98-133">Questi file ZIP contengono i risultati dell'esecuzione dei test, inclusi i risultati dello script e i dati sulle prestazioni di memoria e CPU inclusi nel file ETL.</span><span class="sxs-lookup"><span data-stu-id="67c98-133">These zip files contain the results of your test run, including script results and memory and CPU performance data which is included in the ETL file.</span></span>

![File di test di regressione della memoria](Media/04_memory-regression-test-files.png)

<span data-ttu-id="67c98-135">È possibile scaricare e decomprimere i log per le due esecuzioni dei test, quindi individuare il file ETL all'interno di ogni cartella e rinominarli come target.etl (per l'esecuzione dei test nell'aggiornamento non definitiva) e baseline.etl (per l'esecuzione dei test nell'ultimo aggiornamento rilasciato) per semplificare l'esplorazione e l'esplorazione.</span><span class="sxs-lookup"><span data-stu-id="67c98-135">You can download and unzip the logs for the two test runs, then locate the ETL file within each folder and rename them as target.etl (for the test run on the pre-release update) and baseline.etl (for the test run on last released update) to simplify exploration and navigation.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="67c98-136">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="67c98-136">Next steps</span></span>

<span data-ttu-id="67c98-137">Passare all'articolo successivo per iniziare a comprendere l'analisi intelligente della regressione della CPU.</span><span class="sxs-lookup"><span data-stu-id="67c98-137">Advance to the next article to get started with understanding intelligent CPU regression analysis.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="67c98-138">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="67c98-138">Next step</span></span>](cpu.md)

<!---
Add button for next page
-->
