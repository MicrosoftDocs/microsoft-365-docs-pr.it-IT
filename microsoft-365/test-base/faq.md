---
title: Domande frequenti sulla base di test
description: Esaminare le domande frequenti
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323381"
---
# <a name="test-base-faq"></a><span data-ttu-id="2d1a4-103">Domande frequenti sulla base di test</span><span class="sxs-lookup"><span data-stu-id="2d1a4-103">Test Base FAQ</span></span>

<span data-ttu-id="2d1a4-104">**D: Come si inviano i pacchetti al team di test di base?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="2d1a4-105">**A:** Invia i pacchetti direttamente all'ambiente di base di test usando il portale self-service.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="2d1a4-106">Per inviare il pacchetto dell'applicazione, passare al portale di [Azure](https://www.aka.ms/testbaseportal "Home page di base dei test") e caricare una cartella compressa contenente i file binari, le dipendenze e gli script di test dell'applicazione tramite il dashboard del portale della base di test self-service.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="2d1a4-107">Per ulteriori informazioni, vedere il manuale dell'utente per l'onboarding o contattare il team all'indirizzo per <testbasepreview@microsoft.com> assistenza e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="2d1a4-108">**D: Cosa sono i test out-of-box (OOB) ?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="2d1a4-109">**A:** I test out-of-box (OOB) sono standardizzati, le esecuzioni di test predefinite in cui i pacchetti dell'applicazione vengono installati, avviati e chiusi trenta (30) volte e quindi disinstallati.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="2d1a4-110">I pacchetti creati per Test Base avranno gli script di test seguenti: install, launch, close e facoltativamente lo script di disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="2d1a4-111">I test out-of-box (OOB) forniscono telemetria standardizzata nell'applicazione da confrontare tra Windows build.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="2d1a4-112">**D: È possibile inviare test al di fuori dei test out-of-box (installare, avviare, chiudere, disinstallare script di test)?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="2d1a4-113">**A:** Sì, i clienti possono anche caricare pacchetti di applicazioni per test **funzionali** tramite il dashboard del portale self-service.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="2d1a4-114">**I test funzionali** sono test che consentono ai clienti di eseguire i propri script per eseguire funzionalità personalizzate nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="2d1a4-115">Test</span><span class="sxs-lookup"><span data-stu-id="2d1a4-115">Testing</span></span>

<span data-ttu-id="2d1a4-116">**D: Sono supportati i test funzionali?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="2d1a4-117">**A:** Sì, Test Base supporta i test funzionali.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="2d1a4-118">I test funzionali sono test che consentono ai clienti di eseguire i propri script per eseguire funzionalità personalizzate nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="2d1a4-119">Per inviare il pacchetto dell'applicazione per i test funzionali, è sufficiente caricare la cartella compressa contenente i file binari, le dipendenze e gli script di test dell'applicazione tramite il dashboard del portale self-service.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="2d1a4-120">Per ulteriori informazioni, vedere il manuale dell'utente per l'onboarding o contattare il team all'indirizzo per <testbasepreview@microsoft.com> assistenza e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="2d1a4-121">**D: In che modo Test Base gestisce i dati di test?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="2d1a4-122">**A:** Test Base raccoglie e gestisce in modo sicuro i dati di test nell'ambiente Azure.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="2d1a4-123">**D: Test Base può supportare i test automatizzati?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="2d1a4-124">Sì, test base supporta test automatizzati, tuttavia, non sono supportati test manuali in questo momento a causa delle funzionalità del servizio.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="2d1a4-125">**D: Quali linguaggi e framework di test automatizzati sono supportati?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="2d1a4-126">**A:** Supportiamo tutti i linguaggi e i framework.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="2d1a4-127">Tutti gli script vengono richiamati tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="2d1a4-128">Dovrai anche fornire (caricare) i file binari dipendenti del framework richiesto.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="2d1a4-129">**D: Quanto tempo base di test fornisce i risultati dei test?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="2d1a4-130">**A:** Per ogni test eseguito con le build non definitiva, forniremo risultati entro 48 ore nel dashboard del portale [di Azure.](https://www.aka.ms/testbaseportal "Home page di base dei test")</span><span class="sxs-lookup"><span data-stu-id="2d1a4-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="2d1a4-131">**D: È possibile riavviare dopo l'installazione?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="2d1a4-132">**A:** Sì, il processo supporta il riavvio dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="2d1a4-133">Assicurarsi di selezionare questa opzione nell'elenco a discesa "Impostazioni facoltative" quando si **impostano** le attività nel portale di onboarding.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="2d1a4-134">Per i test out-of-box (OOB), è possibile specificare se è necessario un riavvio per lo _script di installazione._</span><span class="sxs-lookup"><span data-stu-id="2d1a4-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![Immagine di riavvio](Media/reboot.png)

<span data-ttu-id="2d1a4-136">Durante i test funzionali, è possibile specificare se è necessario un riavvio per ogni script aggiunto.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![Come selezionare i test funzionali](Media/functionalreboot.png)

<span data-ttu-id="2d1a4-138">**D: Quali Windows supportate?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="2d1a4-139">**A:** Attualmente sono supportati Windows 10 client, Windows Server 2016, Windows Server 2016 Core, Windows Server 2019 e Windows Server 2019 Core.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="2d1a4-140">**D: Qual è la differenza tra i test di aggiornamento della sicurezza e i test di aggiornamento delle funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="2d1a4-141">**A:** Per i test di aggiornamento della sicurezza, vengono testati gli aggiornamenti della sicurezza **<ins>non</ins>** definitiva mensili su Windows che sono incentrati sulla protezione e la protezione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="2d1a4-142">Per i test di aggiornamento delle funzionalità, vengono testati gli aggiornamenti delle funzionalità **<ins>pre-rilascio bi</ins>** annuali che introducono nuove funzionalità e funzionalità in Windows.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="2d1a4-143">Opzioni di debug</span><span class="sxs-lookup"><span data-stu-id="2d1a4-143">Debugging options</span></span>

<span data-ttu-id="2d1a4-144">**D: Si ottiene l'accesso alle macchine virtuali (VM) in caso di errori? Cosa condivide Test Base?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="2d1a4-145">**A:** Perché il servizio sia conforme e gli aggiornamenti non definitiva siano sicuri, solo Microsoft ha accesso alle macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="2d1a4-146">Tuttavia, i clienti possono visualizzare i risultati dei test e altre metriche di test nel dashboard del portale, tra cui segnali di arresto anomalo e blocco, metriche di affidabilità, utilizzo della memoria e CPU e così via. Vengono inoltre generati e forniti log delle esecuzioni dei test nel dashboard per il download e ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="2d1a4-147">Possiamo anche fornire dump di memoria per il debug di arresto anomalo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="2d1a4-148">**D: Se durante il test vengono rilevati problemi, quali sono i passaggi successivi per risolverli?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="2d1a4-149">**A:** Il team test base eseguirà un processo di analisi iniziale per determinare la causa principale dell'errore e quindi, a seconda dei risultati, verrà eseguito il routing al cliente o ai team interni di Microsoft per il debug.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="2d1a4-150">Lavoriamo sempre a stretto contatto con i clienti per risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="2d1a4-151">**D: Microsoft ha il rilascio della patch di sicurezza fino a quando il problema non viene risolto? Quali risoluzioni alternative sono disponibili?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="2d1a4-152">**A:** L'obiettivo di Test Base è quello di garantire che i nostri clienti finali congiunti non facciano fronte ad alcun problema.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="2d1a4-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="2d1a4-154">Varie</span><span class="sxs-lookup"><span data-stu-id="2d1a4-154">Miscellaneous</span></span>

<span data-ttu-id="2d1a4-155">**D: Come funziona il servizio con un server locale?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="2d1a4-156">**A:** Attualmente non è disponibile il supporto per i server locali.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="2d1a4-157">Tuttavia, se il server espone l'endpoint HTTP, è possibile connettersi ad esso tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="2d1a4-158">**D: Who ospita le macchine virtuali?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="2d1a4-159">**A:** Microsoft esegue il provisioning della macchina virtuale per questo servizio, prendendo il carico di farlo dal cliente.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="2d1a4-160">**D: Questo servizio supporta applicazioni Web, mobili o desktop?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="2d1a4-161">**A:** Attualmente, l'attenzione è concentrata sulle applicazioni desktop, tuttavia, abbiamo in programma di eseguire l'onboardboard delle applicazioni Web in futuro, ma al momento non supportiamo le applicazioni per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="2d1a4-162">**D: Qual è la differenza tra Test Base e SUVP?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="2d1a4-163">**A:** La differenza principale tra Test Base e SUVP consiste nel fatto che i nostri partner eserciteranno le loro applicazioni nell'ambiente di Azure di base di test per la convalida eseguiti in base agli aggiornamenti non definitiva invece di eseguire i test stessi.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="2d1a4-164">Oltre al test degli aggiornamenti della sicurezza non definitiva, supportiamo i test degli aggiornamenti delle funzionalità non definitiva sulla nostra piattaforma.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="2d1a4-165">Nella nostra roadmap sono disponibili molti altri tipi di aggiornamenti e test del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="2d1a4-166">**D: Il servizio è associato a un costo?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="2d1a4-167">**A:** Il servizio Di base di test sarà gratuito per gli utenti fino a disponibilità generale (GA).</span><span class="sxs-lookup"><span data-stu-id="2d1a4-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="2d1a4-168">In quel momento, annunceremo una struttura dei costi che sarà in vigore per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="2d1a4-169">**D: Come posso fornire feedback sulla base di test?**</span><span class="sxs-lookup"><span data-stu-id="2d1a4-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="2d1a4-170">**A:** Per condividere il feedback sulla base di test, selezionare **l'icona Feedback** nella parte inferiore sinistra del portale.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="2d1a4-171">Includi uno screenshot con il tuo invio per aiutare Microsoft a comprendere meglio il tuo feedback.</span><span class="sxs-lookup"><span data-stu-id="2d1a4-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="2d1a4-172">Puoi anche inviare suggerimenti sul prodotto e inviare altre idee all'indirizzo <testbasepreview@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="2d1a4-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
