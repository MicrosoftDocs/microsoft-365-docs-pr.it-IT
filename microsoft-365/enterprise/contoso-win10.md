---
title: Distribuzione di Windows 10 Enterprise per Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo Contoso ha usato Microsoft Endpoint Configuration Manager per la distribuzione degli aggiornamenti sul posto per Windows 10 Enterprise.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754248"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="4d88e-103">Distribuzione di Windows 10 Enterprise per Contoso</span><span class="sxs-lookup"><span data-stu-id="4d88e-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="4d88e-p101">Prima dell'ampia implementazione di Microsoft 365 per Enterprise, contoso disponeva di PC e dispositivi compatibili con Windows che eseguivano una combinazione di Windows 7 (10%), Windows 8,1 (65%) e Windows 10 (25%). Contoso voleva aggiornare i propri PC per Windows 10 Enterprise approfittare della sicurezza avanzata e abbassare il sovraccarico dalle distribuzioni automatizzate di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="4d88e-p101">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="4d88e-106">Dopo aver valutato la propria infrastruttura e le proprie esigenze aziendali, Contoso ha identificato i seguenti requisiti chiave per la distribuzione:</span><span class="sxs-lookup"><span data-stu-id="4d88e-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="4d88e-107">Esecuzione di Windows 10 Enterprise sul maggior numero possibile di computer e dispositivi</span><span class="sxs-lookup"><span data-stu-id="4d88e-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="4d88e-108">Sfruttamento dell'infrastruttura di Configuration Manager esistente per l'implementazione degli aggiornamenti sul posto</span><span class="sxs-lookup"><span data-stu-id="4d88e-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="4d88e-109">Controllo sulle versioni di Windows 10 Enterprise da distribuire e sugli aggiornamenti che vengono eseguiti tramite gli anelli</span><span class="sxs-lookup"><span data-stu-id="4d88e-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="4d88e-110">PC e dispositivi devono rimanere sempre aggiornati con costi di amministrazione dell'IT minimi e un impatto minimo sugli utenti finali</span><span class="sxs-lookup"><span data-stu-id="4d88e-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="4d88e-111">Con il termine "aggiornato" si intende la versione di Windows 10 Enterprise più adatta alle esigenze aziendali di Contoso, che può essere diverso dall'avere tutti i computer compatibili con Windows che utilizzano la versione più aggiornata di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4d88e-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="4d88e-112">Strumenti di distribuzione</span><span class="sxs-lookup"><span data-stu-id="4d88e-112">Deployment tools</span></span>

<span data-ttu-id="4d88e-113">Prima e durante gli aggiornamenti sul posto di Windows 10 Enterprise, Contoso utilizzava le soluzioni di seguenti di Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="4d88e-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="4d88e-114">Preparazione aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="4d88e-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="4d88e-115">Raccoglie dati di sistema, applicazione e driver per l'analisi e quindi identifica i problemi di compatibilità che possono bloccare un aggiornamento e suggerisce le correzioni ai problemi noti a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d88e-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="4d88e-116">Conformità aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="4d88e-116">Update Compliance</span></span>  

  <span data-ttu-id="4d88e-117">Mostra lo stato dei dispositivi rispetto agli aggiornamenti di Windows, in modo che sia possibile verificare che dispongano degli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="4d88e-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="4d88e-118">Integrità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4d88e-118">Device Health</span></span>  

  <span data-ttu-id="4d88e-119">Identifica i dispositivi che si arrestano spesso in modo anomalo e quindi potrebbe essere necessario ricreare o sostituire e i driver di dispositivo che causano arresti anomali, con suggerimenti sulle versioni alternative di tali driver che potrebbero ridurre il numero di errori.</span><span class="sxs-lookup"><span data-stu-id="4d88e-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="4d88e-120">Notifica la presenza di configurazioni errate di Windows Information Protection con invio di messaggi agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="4d88e-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="4d88e-p103">Contoso dispone di un'infrastruttura di Configuration Manager (Current Branch) esistente. Configuration Manager si adatta ad ambienti di grandi dimensioni e fornisce un controllo completo sull'installazione, gli aggiornamenti e le impostazioni. Inoltre, dispone di funzionalità integrate per semplificare e rendere più efficiente la distribuzione e la gestione di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4d88e-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="4d88e-124">Processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="4d88e-124">Planning process</span></span>

<span data-ttu-id="4d88e-125">Contoso ha utilizzato la preparazione per l'aggiornamento in Windows Analytics per determinare il set di app installate e la compatibilità con Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4d88e-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="4d88e-126">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="4d88e-126">Deployment process</span></span>

<span data-ttu-id="4d88e-127">Per completare la distribuzione degli aggiornamenti sul posto di Windows 10 Enterprise, Contoso ha implementato la procedura seguente, che include le procedure consigliate da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="4d88e-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="4d88e-128">Abilitazione della cache peer per Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="4d88e-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="4d88e-129">Creazione di pacchetti di Windows personalizzati basati sulle immagini del Volume Licensing Service Center.</span><span class="sxs-lookup"><span data-stu-id="4d88e-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="4d88e-130">Gestione configurazione utilizzata per distribuire i pacchetti di Windows ai punti di distribuzione nella propria rete e distribuisce le compilazioni ai tre gruppi di gestione temporanea di convalida e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d88e-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="4d88e-131">Esecuzione della valutazione della riuscita per i computer e i dispositivi negli anelli di gestione temporanea della convalida e della distribuzione mediante soluzioni Integrità del dispositivo e Conformità aggiornamenti di Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="4d88e-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="4d88e-132">In base alle informazioni di Windows Analytics, Contoso ha determinato la versione di Windows 10 Enterprise da distribuire al gruppo di distribuzione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4d88e-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="4d88e-133">Esecuzione delle sequenze di attività di distribuzione di Configuration Manager per distribuire il pacchetto di Windows selezionato in un gruppo di distribuzione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4d88e-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="4d88e-134">Computer e dispositivi monitorati nel gruppo di distribuzione di grandi dimensioni utilizzando le soluzioni di conformità per l'integrità e l'aggiornamento dei dispositivi per risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="4d88e-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="4d88e-135">Ecco l'architettura di distribuzione degli aggiornamenti sul posto e degli aggiornamenti continui di Contoso.</span><span class="sxs-lookup"><span data-stu-id="4d88e-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Infrastruttura di distribuzione di Windows 10 Enterprise di Contoso](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="4d88e-137">Questa infrastruttura è costituita da:</span><span class="sxs-lookup"><span data-stu-id="4d88e-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="4d88e-138">Configuration Manager, che:</span><span class="sxs-lookup"><span data-stu-id="4d88e-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="4d88e-139">Ottiene le immagini per i pacchetti di Windows 10 Enterprise da Microsoft Volume Licensing Center in Microsoft Network.</span><span class="sxs-lookup"><span data-stu-id="4d88e-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="4d88e-140">Si tratta del punto di amministrazione centrale per i pacchetti di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d88e-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="4d88e-141">Punti di distribuzione regionali che in genere si trovano negli hub regionali di Contoso.</span><span class="sxs-lookup"><span data-stu-id="4d88e-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="4d88e-142">PC e dispositivi Windows in vari percorsi che ricevono e installano i pacchetti di distribuzione per l'aggiornamento sul posto o per gli aggiornamenti in corso basati sull'appartenenza a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="4d88e-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="4d88e-143">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4d88e-143">Next step</span></span>

<span data-ttu-id="4d88e-144">Informazioni su come Contoso sta facendo leva sull'infrastruttura di gestione configurazione per [distribuire e mantenere le app Microsoft 365 per Enterprise](contoso-o365pp.md) nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d88e-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="4d88e-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d88e-145">See also</span></span>

[<span data-ttu-id="4d88e-146">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4d88e-146">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="4d88e-147">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="4d88e-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4d88e-148">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="4d88e-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
