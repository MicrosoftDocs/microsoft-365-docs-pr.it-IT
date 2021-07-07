---
title: Analisi della regressione della CPU
description: Informazioni sui risultati di regressione e sulle metriche per l'utilizzo della CPU
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
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322721"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="822ac-103">Analisi intelligente della regressione della CPU</span><span class="sxs-lookup"><span data-stu-id="822ac-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="822ac-104">L'utilizzo della CPU può indicare se un'applicazione è interessata da un aggiornamento del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="822ac-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="822ac-105">Test Base for Microsoft 365 fornisce agli sviluppatori di software informazioni approfondite sulle regressioni delle prestazioni della CPU che si verificano quando l'applicazione è in esecuzione su versioni diverse di un aggiornamento del sistema operativo (OS) di Windows.</span><span class="sxs-lookup"><span data-stu-id="822ac-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="822ac-106">Queste regressioni della CPU consentono agli sviluppatori di rilevare e risolvere i problemi delle applicazioni (e i potenziali errori) prima della distribuzione generale dell'aggiornamento del sistema operativo, impedendo così un'esperienza negativa per l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="822ac-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="822ac-107">Funzionamento dell'analisi di regressione della CPU</span><span class="sxs-lookup"><span data-stu-id="822ac-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="822ac-108">In quanto utente della base di test, è possibile caricare i file binari dell'applicazione (in un singolo file .zip), insieme agli script di test associati e selezionare la versione del sistema operativo Windows in base alla quale si desidera testare l'applicazione nel portale test di base in Azure.</span><span class="sxs-lookup"><span data-stu-id="822ac-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="822ac-109">Il servizio Test Base esegue quindi gli script di test ed esegue l'analisi **di regressione della CPU.**</span><span class="sxs-lookup"><span data-stu-id="822ac-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="822ac-110">Il servizio verifica se l'utilizzo della CPU per l'applicazione nella versione non definitiva dell'aggiornamento per il sistema operativo di destinazione è in linea con l'utilizzo della CPU per la versione rilasciata del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="822ac-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="822ac-111">L'utilizzo della CPU non è un confronto simile al 100% perché i processi in esecuzione nelle due versioni del sistema operativo possono corrispondere o meno a una corrispondenza esatta a causa di versioni diverse del sistema operativo. Tuttavia, l'analisi eseguita da Test Base può indicare se l'utilizzo della CPU per l'applicazione è stato intasato da un aggiornamento del sistema operativo imminente e in particolare quali processi sono gressi dalle esecuzioni dei test precedenti.</span><span class="sxs-lookup"><span data-stu-id="822ac-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="822ac-112">Nello snapshot seguente sono disponibili due rilasci del sistema operativo rispetto ai quali vengono confrontati gli utilizzo della CPU per la stessa applicazione.</span><span class="sxs-lookup"><span data-stu-id="822ac-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="822ac-113">La scheda Utilizzo CPU mostra i limiti superiore e inferiore di utilizzo per entrambe le versioni rispettivamente al 90° e al 10° percentile.</span><span class="sxs-lookup"><span data-stu-id="822ac-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="822ac-114">I grafici mostrano la serie temporale di utilizzo della CPU insieme all'utilizzo medio.</span><span class="sxs-lookup"><span data-stu-id="822ac-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="822ac-115">I clienti possono ora usare la funzionalità per determinare se l'utilizzo della CPU dell'applicazione è stato intasato dagli aggiornamenti del sistema operativo e in particolare quali processi sono stati regressi dall'esecuzione precedente.</span><span class="sxs-lookup"><span data-stu-id="822ac-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![Analisi della regressione della CPU](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="822ac-117">Identificazione del processo pertinente</span><span class="sxs-lookup"><span data-stu-id="822ac-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="822ac-118">In questo argomento viene illustrato come identificare i processi regressi nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="822ac-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="822ac-119">L'analisi della regressione delle prestazioni richiede il rilevamento di diversi tipi di contatori delle prestazioni per ogni processo in esecuzione su una macchina virtuale durante l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="822ac-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="822ac-120">Tale analisi acquisisce molte variabili per molti processi per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="822ac-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="822ac-121">Non tutti i processi sono associati a un'esecuzione o a un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="822ac-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="822ac-122">Per risolvere questo problema, viene applicato un algoritmo di classificazione reciproca delle informazioni che usa la teoria della probabilità e delle informazioni per capire quali processi sono più rilevanti per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="822ac-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="822ac-123">Un'applicazione può essere considerata un tipo di variabile casuale discreta mentre un processo è considerato un altro tipo di variabile casuale discreta.</span><span class="sxs-lookup"><span data-stu-id="822ac-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="822ac-124">L'associazione delle due variabili casuali viene misurata utilizzando probabilità condizionali per la pertinenza.</span><span class="sxs-lookup"><span data-stu-id="822ac-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="822ac-125">I processi vengono quindi visualizzati nell'ordine di pertinenza per ogni applicazione.</span><span class="sxs-lookup"><span data-stu-id="822ac-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="822ac-126">È inoltre possibile scegliere tra i preferiti un sottoinsieme di processi che possono essere monitorati, per impostazione predefinita, insieme ai processi rilevanti per l'analisi della regressione della CPU.</span><span class="sxs-lookup"><span data-stu-id="822ac-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="822ac-127">Una volta rilevata una regressione, è possibile scaricare il toolkit analizzatore Windows prestazioni e analizzare i motivi delle regressioni delle prestazioni della CPU.</span><span class="sxs-lookup"><span data-stu-id="822ac-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="822ac-128">L Windows Performance Analyzer accetta il registro di traccia eventi (ETL) come input e questi file etl sono disponibili nei file di registro scaricabili per le esecuzioni di test nel portale.</span><span class="sxs-lookup"><span data-stu-id="822ac-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="822ac-129">Per ulteriori informazioni sul debug delle prestazioni della CPU, vedere la documentazione relativa Windows Performance Analyzer.</span><span class="sxs-lookup"><span data-stu-id="822ac-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

