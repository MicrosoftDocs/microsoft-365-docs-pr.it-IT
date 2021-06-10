---
title: Microsoft Threat Experts
ms.reviewer: ''
description: Microsoft Threat Experts fornisce un ulteriore livello di competenza a Microsoft Defender for Endpoint.
keywords: servizio di ricerca delle minacce gestite, ricerca di minacce gestite, servizio MDR (Managed Detection and Response), MTE, Microsoft Threat Experts, MTE-TAN, notifica di attacco mirato, notifica di attacco mirato
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ebde023db5196117a02a2372784a3110839c51fa
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843531"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="b142b-104">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="b142b-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b142b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b142b-105">**Applies to:**</span></span>
- [<span data-ttu-id="b142b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b142b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b142b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b142b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b142b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b142b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b142b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b142b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="b142b-110">Microsoft Threat Experts è un servizio di ricerca delle minacce gestito che fornisce ai Centri operativi per la sicurezza (SOC) un monitoraggio e un'analisi a livello di esperti per garantire che le minacce critiche negli ambienti specifici non si perdino.</span><span class="sxs-lookup"><span data-stu-id="b142b-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="b142b-111">Questo servizio di ricerca delle minacce gestite fornisce informazioni e dati guidati da esperti attraverso queste due funzionalità: notifica di attacchi mirati e accesso a esperti su richiesta.</span><span class="sxs-lookup"><span data-stu-id="b142b-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b142b-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b142b-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="b142b-113">Discutere i requisiti di idoneità con il provider di servizi tecnici Microsoft e il team dell'account prima di applicare il servizio di ricerca delle minacce gestite.</span><span class="sxs-lookup"><span data-stu-id="b142b-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="b142b-114">Se sei un cliente di Microsoft Defender for Endpoint, devi richiedere Microsoft Threat Experts **- Notifiche** di attacco mirato per ottenere informazioni e analisi speciali che consentono di identificare le minacce più critiche nell'ambiente in modo da poterle rispondere rapidamente</span><span class="sxs-lookup"><span data-stu-id="b142b-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="b142b-115">Per iscriverti a Microsoft Threat Experts - Vantaggi delle notifiche di **attacco** mirate, vai a Impostazioni Funzionalità avanzate Microsoft Threat Experts - Notifiche di attacco  >    >    >   mirate da applicare.</span><span class="sxs-lookup"><span data-stu-id="b142b-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="b142b-116">Una volta accettato, si otterrà i vantaggi delle notifiche di attacco mirato.</span><span class="sxs-lookup"><span data-stu-id="b142b-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="b142b-117">Contattare il team dell'account o il rappresentante Microsoft per sottoscrivere **Microsoft Threat Experts - Esperti** su richiesta per consultare i nostri esperti di minacce sui rilevamenti e gli avversari rilevanti che l'organizzazione sta affrontando.</span><span class="sxs-lookup"><span data-stu-id="b142b-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="b142b-118">Per [informazioni dettagliate, vedere Configure Microsoft Threat Experts capabilities.](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="b142b-118">See [Configure Microsoft Threat Experts capabilities](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="b142b-119">Microsoft Threat Experts - Notifica di attacco mirato</span><span class="sxs-lookup"><span data-stu-id="b142b-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="b142b-120">Microsoft Threat Experts - La notifica di attacco mirato offre una ricerca proattiva delle minacce più importanti per la rete, tra cui intrusioni umane, attacchi tramite tastiera o attacchi avanzati come lo spionaggio informatico.</span><span class="sxs-lookup"><span data-stu-id="b142b-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="b142b-121">Queste notifiche vengono visualizzate come nuovo avviso.</span><span class="sxs-lookup"><span data-stu-id="b142b-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="b142b-122">Il servizio di ricerca gestito include:</span><span class="sxs-lookup"><span data-stu-id="b142b-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="b142b-123">Monitoraggio e analisi delle minacce, riducendo tempi di attività e rischi per l'azienda</span><span class="sxs-lookup"><span data-stu-id="b142b-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="b142b-124">Intelligenza artificiale addestrata da Hunter per individuare e assegnare priorità agli attacchi noti e sconosciuti</span><span class="sxs-lookup"><span data-stu-id="b142b-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="b142b-125">Identificare i rischi più importanti, aiutando i SOC a ottimizzare tempo ed energia</span><span class="sxs-lookup"><span data-stu-id="b142b-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="b142b-126">Ambito di compromissione e contesto che possono essere rapidamente recapitati per consentire una risposta SOC veloce.</span><span class="sxs-lookup"><span data-stu-id="b142b-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="b142b-127">Microsoft Threat Experts - Esperti su richiesta</span><span class="sxs-lookup"><span data-stu-id="b142b-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="b142b-128">I clienti possono coinvolgere i nostri esperti di sicurezza direttamente dall'Microsoft Defender Security Center per una risposta accurata e immediata.</span><span class="sxs-lookup"><span data-stu-id="b142b-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="b142b-129">Gli esperti forniscono informazioni dettagliate necessarie per comprendere meglio le minacce complesse che interessano l'organizzazione, dalle richieste di informazioni sugli avvisi, ai dispositivi potenzialmente compromessi, alla causa principale di una connessione di rete sospetta, a un'ulteriore intelligence sulle minacce per quanto riguarda le campagne di minacce persistenti avanzate in corso.</span><span class="sxs-lookup"><span data-stu-id="b142b-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="b142b-130">Con questa funzionalità, è possibile:</span><span class="sxs-lookup"><span data-stu-id="b142b-130">With this capability, you can:</span></span>
- <span data-ttu-id="b142b-131">Ottenere ulteriori chiarimenti sugli avvisi, inclusa la causa radice o l'ambito dell'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="b142b-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="b142b-132">Acquisire chiarezza nel comportamento sospetto dei dispositivi e nei passaggi successivi se si trova di fronte a un utente malintenzionato avanzato</span><span class="sxs-lookup"><span data-stu-id="b142b-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="b142b-133">Determinare i rischi e la protezione relativi a minacce, campagne o tecniche di attacco emergenti</span><span class="sxs-lookup"><span data-stu-id="b142b-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="b142b-134">L'opzione **Consulta un esperto** di minacce è disponibile in diversi punti del portale in modo da poter interagire con esperti nel contesto dell'indagine:</span><span class="sxs-lookup"><span data-stu-id="b142b-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="b142b-135"><i>**Menu Guida e supporto tecnico**</i></span><span class="sxs-lookup"><span data-stu-id="b142b-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="b142b-136">![Screenshot dell'opzione di menu MTE-EOD](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="b142b-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="b142b-137"><i>**Menu Azioni pagina dispositivo**</i></span><span class="sxs-lookup"><span data-stu-id="b142b-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="b142b-138">![Screenshot dell'opzione di menu azione pagina dispositivo MTE-EOD](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="b142b-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="b142b-139"><i>**Menu Azioni pagina avvisi**</i></span><span class="sxs-lookup"><span data-stu-id="b142b-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="b142b-140">![Screenshot dell'opzione di menu azione della pagina di avviso MTE-EOD](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="b142b-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="b142b-141"><i>**Menu Azioni pagina file**</i></span><span class="sxs-lookup"><span data-stu-id="b142b-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="b142b-142">![Screenshot dell'opzione di menu Azione pagina file MTE-EOD](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="b142b-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b142b-143">Se si desidera tenere traccia dello stato dei casi esperti su richiesta tramite Hub dei servizi Microsoft, contattare il technical account manager.</span><span class="sxs-lookup"><span data-stu-id="b142b-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="b142b-144">Guarda questo video per una breve panoramica dell'hub dei servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b142b-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="b142b-145">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="b142b-145">Related topic</span></span>
- [<span data-ttu-id="b142b-146">Configurare Microsoft Threat Experts funzionalità</span><span class="sxs-lookup"><span data-stu-id="b142b-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
