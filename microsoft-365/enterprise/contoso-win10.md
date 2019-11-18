---
title: Distribuzione di Windows 10 Enterprise per Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo Contoso ha usato Microsoft Endpoint Configuration Manager per la distribuzione degli aggiornamenti sul posto per Windows 10 Enterprise.
ms.openlocfilehash: a36e933d31ac6d629b649f07d6b8c9a4fe950ec8
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627332"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="e850d-103">Distribuzione di Windows 10 Enterprise per Contoso</span><span class="sxs-lookup"><span data-stu-id="e850d-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="e850d-104">**Riepilogo:** Comprendere in che modo Contoso ha usato Microsoft Endpoint Configuration Manager per la distribuzione degli aggiornamenti sul posto per Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e850d-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="e850d-p101">Prima dell'implementazione estesa di Microsoft 365 Enterprise, Contoso disponeva di PC compatibili con Windows e dispositivi con una combinazione di Windows 7 (10%), Windows 8.1 (65%) e Windows 10 (25%). Contoso voleva aggiornare i PC a Windows 10 Enterprise per usufruire della maggiore sicurezza e della riduzione dei costi IT generati dalle distribuzioni automatiche degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e850d-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="e850d-107">Dopo aver valutato la propria infrastruttura e le proprie esigenze aziendali, Contoso ha identificato i seguenti requisiti chiave per la distribuzione:</span><span class="sxs-lookup"><span data-stu-id="e850d-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="e850d-108">Esecuzione di Windows 10 Enterprise sul maggior numero possibile di computer e dispositivi</span><span class="sxs-lookup"><span data-stu-id="e850d-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="e850d-109">Sfruttamento dell'infrastruttura di Configuration Manager esistente per l'implementazione degli aggiornamenti sul posto</span><span class="sxs-lookup"><span data-stu-id="e850d-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="e850d-110">Controllo sulle versioni di Windows 10 Enterprise da distribuire e sugli aggiornamenti che vengono eseguiti tramite gli anelli</span><span class="sxs-lookup"><span data-stu-id="e850d-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="e850d-111">PC e dispositivi devono rimanere sempre aggiornati con costi di amministrazione dell'IT minimi e un impatto minimo sugli utenti finali</span><span class="sxs-lookup"><span data-stu-id="e850d-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="e850d-112">Con il termine "aggiornato" si intende la versione di Windows 10 Enterprise più adatta alle esigenze aziendali di Contoso, che può essere diverso dall'avere tutti i computer compatibili con Windows che utilizzano la versione più aggiornata di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e850d-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="e850d-113">Strumenti di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e850d-113">Deployment tools</span></span>

<span data-ttu-id="e850d-114">Prima e durante gli aggiornamenti sul posto di Windows 10 Enterprise, Contoso utilizzava le soluzioni di seguenti di Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="e850d-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="e850d-115">Preparazione aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="e850d-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="e850d-116">Raccoglie dati di sistema, applicazione e driver per l'analisi e quindi identifica i problemi di compatibilità che possono bloccare un aggiornamento e suggerisce le correzioni ai problemi noti a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e850d-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="e850d-117">Conformità aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="e850d-117">Update Compliance</span></span>  

  <span data-ttu-id="e850d-118">Mostra lo stato dei dispositivi rispetto agli aggiornamenti di Windows, in modo che sia possibile verificare che dispongano degli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="e850d-118">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="e850d-119">Integrità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e850d-119">Device Health</span></span>  

  <span data-ttu-id="e850d-120">Identifica i dispositivi che si arrestano spesso in modo anomalo e quindi potrebbe essere necessario ricreare o sostituire e i driver di dispositivo che causano arresti anomali, con suggerimenti sulle versioni alternative di tali driver che potrebbero ridurre il numero di errori.</span><span class="sxs-lookup"><span data-stu-id="e850d-120">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="e850d-121">Notifica la presenza di configurazioni errate di Windows Information Protection con invio di messaggi agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="e850d-121">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="e850d-p103">Contoso dispone di un'infrastruttura di Configuration Manager (Current Branch) esistente. Configuration Manager si adatta ad ambienti di grandi dimensioni e fornisce un controllo completo sull'installazione, gli aggiornamenti e le impostazioni. Inoltre, dispone di funzionalità integrate per semplificare e rendere più efficiente la distribuzione e la gestione di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e850d-p103">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="e850d-125">Processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="e850d-125">Planning process</span></span>

<span data-ttu-id="e850d-126">Prima della distribuzione, Contoso ha definito i seguenti anelli:</span><span class="sxs-lookup"><span data-stu-id="e850d-126">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="e850d-127">Tre anelli per la gestione temporanea della convalida e la distribuzione</span><span class="sxs-lookup"><span data-stu-id="e850d-127">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="e850d-128">Uno per le build di anteprima</span><span class="sxs-lookup"><span data-stu-id="e850d-128">One for preview builds</span></span> 
  - <span data-ttu-id="e850d-129">Uno per le build delle nuove versioni</span><span class="sxs-lookup"><span data-stu-id="e850d-129">One for new release builds</span></span>
  - <span data-ttu-id="e850d-130">Uno per una build precedente</span><span class="sxs-lookup"><span data-stu-id="e850d-130">One for a previous build</span></span> 
- <span data-ttu-id="e850d-131">Un anello l'ampia distribuzione di Windows 10 Enterprise basata sui dati degli anelli di convalida</span><span class="sxs-lookup"><span data-stu-id="e850d-131">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="e850d-132">Contoso inoltre ha utilizzato la soluzione Preparazione aggiornamenti di Windows Analytics per identificare il gruppo di app installate e la loro compatibilità con Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e850d-132">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="e850d-133">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e850d-133">Deployment process</span></span>

<span data-ttu-id="e850d-134">Per completare la distribuzione degli aggiornamenti sul posto di Windows 10 Enterprise, Contoso ha implementato la procedura seguente, che include le procedure consigliate da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e850d-134">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="e850d-135">Abilitazione della cache peer per Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e850d-135">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="e850d-136">Creazione di pacchetti di Windows personalizzati basati sulle immagini del Volume Licensing Service Center.</span><span class="sxs-lookup"><span data-stu-id="e850d-136">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="e850d-137">Utilizzo di Configuration Manager per distribuire i pacchetti di Windows ai punti di distribuzione nella propria rete e distribuzione di build ai tre anelli per la gestione temporanea della convalida e della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e850d-137">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="e850d-138">Esecuzione della valutazione della riuscita per i computer e i dispositivi negli anelli di gestione temporanea della convalida e della distribuzione mediante soluzioni Integrità del dispositivo e Conformità aggiornamenti di Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="e850d-138">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="e850d-139">Sulla base delle informazioni di Windows Analytics, Contoso ha determinato la versione di Windows 10 Enterprise da distribuire all'anello per la distribuzione generale.</span><span class="sxs-lookup"><span data-stu-id="e850d-139">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="e850d-140">Esecuzione delle sequenze di attività di distribuzione di Configuration Manager per distribuire il pacchetto di Windows selezionato all'anello di distribuzione generale.</span><span class="sxs-lookup"><span data-stu-id="e850d-140">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="e850d-141">Monitoraggio di PC e dispositivi nell'anello di distribuzione generale mediante le soluzioni Integrità del dispositivo e Conformità aggiornamenti per risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="e850d-141">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="e850d-142">Ecco l'architettura di distribuzione degli aggiornamenti sul posto e degli aggiornamenti continui di Contoso.</span><span class="sxs-lookup"><span data-stu-id="e850d-142">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Infrastruttura di distribuzione di Windows 10 Enterprise di Contoso](./media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="e850d-144">Questa infrastruttura è costituita da:</span><span class="sxs-lookup"><span data-stu-id="e850d-144">This infrastructure consists of:</span></span>

- <span data-ttu-id="e850d-145">Configuration Manager, che:</span><span class="sxs-lookup"><span data-stu-id="e850d-145">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="e850d-146">Ottiene le immagini per i pacchetti di Windows 10 Enterprise da Microsoft Volume Licensing Center in Microsoft Network.</span><span class="sxs-lookup"><span data-stu-id="e850d-146">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="e850d-147">Si tratta del punto di amministrazione centrale per i pacchetti di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e850d-147">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="e850d-148">Punti di distribuzione regionali che in genere si trovano negli hub regionali di Contoso.</span><span class="sxs-lookup"><span data-stu-id="e850d-148">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="e850d-149">Computer e dispositivi Windows in diversi punti che ricevono e installano pacchetti di distribuzione per l'aggiornamento sul posto e gli aggiornamenti continui basati sull'appartenenza all'anello.</span><span class="sxs-lookup"><span data-stu-id="e850d-149">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="e850d-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e850d-150">Next step</span></span>

<span data-ttu-id="e850d-151">[Informazioni su](contoso-o365pp.md) come Contoso si avvale dell'infrastruttura di Configuration Manager per distribuire e mantenere aggiornato Office 365 ProPlus nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e850d-151">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e850d-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e850d-152">See also</span></span>

[<span data-ttu-id="e850d-153">Windows 10 Enterprise per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e850d-153">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="e850d-154">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="e850d-154">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e850d-155">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="e850d-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
