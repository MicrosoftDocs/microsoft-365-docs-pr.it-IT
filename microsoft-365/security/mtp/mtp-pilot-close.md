---
title: Riepilogare i risultati del progetto pilota di Microsoft Threat Protection
description: Concludere il progetto pilota di Microsoft Threat Protection completando la scorecard, analizzando i risultati del report e decidendo come procedere.
keywords: Pilota di Microsoft Threat Protection, decidere cosa fare dopo il progetto pilota Microsoft Threat Protection, cosa fare dopo aver valutato Microsoft Threat Protection in produzione, transizione da Microsoft Threat Protection Pilot to Deployment, Cyber Security, Advanced Persistent Threat, Enterprise Security, Devices, Device, Identity, Users, data, Applications, Incidents, Automatic Investigation and remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 1a7b87432ce1eb16c29f462fb4865bfa5c5e2201
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418098"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="905b5-104">Chiusura e ricapitolazione del pilota di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="905b5-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="905b5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="905b5-105">**Applies to:**</span></span>
- <span data-ttu-id="905b5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="905b5-106">Microsoft Threat Protection</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Pianificare il progetto pilota di Microsoft Threat Protection" />
      <br/><span data-ttu-id="905b5-108">Pianificare </a></span><span class="sxs-lookup"><span data-stu-id="905b5-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota" />
      <br/><span data-ttu-id="905b5-110">Preparare </a></span><span class="sxs-lookup"><span data-stu-id="905b5-110">Prepare </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Eseguire le simulazioni di attacco di Microsoft Threat Protection" />
      <br/><span data-ttu-id="905b5-112">Simula attacco </a></span><span class="sxs-lookup"><span data-stu-id="905b5-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Chiudere e riepilogare il pilota di Microsoft Threat Protection" />
      <br/><span data-ttu-id="905b5-114">Chiudi e riassumi </a></span><span class="sxs-lookup"><span data-stu-id="905b5-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="905b5-115">Si è attualmente in fase di chiusura e di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="905b5-115">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="905b5-116">È stata appena eseguita una simulazione di attacco di solo memoria avanzata che ha eseguito il codice in remoto in un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="905b5-116">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="905b5-117">Si è visto come Microsoft Defender ATP e Azure ATP individuano e creano avvisi su attività malevole fraudolente.</span><span class="sxs-lookup"><span data-stu-id="905b5-117">You’ve seen how Microsoft Defender ATP and Azure ATP detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="905b5-118">Si è visto anche come gli avvisi provenienti da origini diverse vengono recapitati insieme ad altre informazioni contestuali in un singolo incidente nel portale del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="905b5-118">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="905b5-119">L'esperienza di tale integrazione consente agli analisti SOC di analizzare e intraprendere le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="905b5-119">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="905b5-120">Inoltre, è stata creata una query di ricerca avanzata che consente di identificare i messaggi di posta elettronica in ingresso in cui l'utente ha aperto o salvato l'allegato e ha creato il rilevamento in base a tale query.</span><span class="sxs-lookup"><span data-stu-id="905b5-120">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="905b5-121">Dopo aver concluso tutti i test, è stata raggiunta la fine del processo.</span><span class="sxs-lookup"><span data-stu-id="905b5-121">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="905b5-122">L'output finale deve essere:</span><span class="sxs-lookup"><span data-stu-id="905b5-122">The final output should be:</span></span>

- <span data-ttu-id="905b5-123">Una scorecard completata</span><span class="sxs-lookup"><span data-stu-id="905b5-123">A completed scorecard</span></span>
- <span data-ttu-id="905b5-124">Un rapporto dettagliato dei risultati del progetto pilota</span><span class="sxs-lookup"><span data-stu-id="905b5-124">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="905b5-125">Una decisione su come procedere</span><span class="sxs-lookup"><span data-stu-id="905b5-125">A decision on how to move forward</span></span>

<span data-ttu-id="905b5-126">Presentare i rapporti dall'output finale sia delle parti interessate interne (identificate durante la fase di [preparazione](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ) che dei contatti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="905b5-126">Present the reports from your final output both internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="905b5-127">Questo sforzo garantisce che eventuali commenti e suggerimenti possano essere utilizzati per migliorare i prodotti e la documentazione.</span><span class="sxs-lookup"><span data-stu-id="905b5-127">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="905b5-128">Si spera che questa simulazione sia stata molto apprezzata.</span><span class="sxs-lookup"><span data-stu-id="905b5-128">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="905b5-129">Per ottenere il massimo dalla soluzione di sicurezza integrata, iniziare a implementare le operazioni apprese in scala maggiore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="905b5-129">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="905b5-130">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="905b5-130">Next step</span></span>
<span data-ttu-id="905b5-131">Per ulteriori informazioni, vedere i pilastri di Microsoft Threat Protection tramite le seguenti guide interattive:</span><span class="sxs-lookup"><span data-stu-id="905b5-131">Learn more about the Microsoft Threat Protection pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="905b5-132">Salvaguardare l'organizzazione con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="905b5-132">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="905b5-133">Individuare attività sospette e potenziali attacchi con Microsoft Defender per Identity</span><span class="sxs-lookup"><span data-stu-id="905b5-133">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="905b5-134">Individuare le minacce e gestire gli avvisi con Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="905b5-134">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="905b5-135">Esaminare e correggere le minacce con Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="905b5-135">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
