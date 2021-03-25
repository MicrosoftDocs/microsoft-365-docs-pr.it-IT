---
title: Creare indicatori per i file
ms.reviewer: ''
description: Creare indicatori per un hash di file che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: file, hash, gestire, consentito, bloccato, bloccare, pulito, dannoso, hash file, indirizzo IP, URL, dominio
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067714"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="65933-104">Creare indicatori per i file</span><span class="sxs-lookup"><span data-stu-id="65933-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="65933-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="65933-105">**Applies to:**</span></span>
- [<span data-ttu-id="65933-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="65933-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="65933-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65933-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="65933-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="65933-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="65933-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="65933-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="65933-110">È possibile impedire un'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.</span><span class="sxs-lookup"><span data-stu-id="65933-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="65933-111">Se si conosce un file pe (Portable Executable) potenzialmente dannoso, è possibile bloccarlo.</span><span class="sxs-lookup"><span data-stu-id="65933-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="65933-112">Questa operazione ne impedirà la lettura, la scrittura o l'esecuzione nei computer dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65933-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="65933-113">Esistono due modi per creare indicatori per i file:</span><span class="sxs-lookup"><span data-stu-id="65933-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="65933-114">Creando un indicatore tramite la pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="65933-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="65933-115">Creando un indicatore contestuale usando il pulsante Aggiungi indicatore dalla pagina dei dettagli del file</span><span class="sxs-lookup"><span data-stu-id="65933-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="65933-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="65933-116">Before you begin</span></span>
<span data-ttu-id="65933-117">Prima di creare indicatori per i file, è importante comprendere i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="65933-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="65933-118">Questa funzionalità è disponibile se l'organizzazione usa Windows Defender antivirus e la protezione basata su cloud è abilitata.</span><span class="sxs-lookup"><span data-stu-id="65933-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="65933-119">Per altre informazioni, vedi Usare tecnologie di nuova generazione in Microsoft Defender Antivirus tramite la [protezione basata sul cloud.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="65933-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="65933-120">La versione del client Antimalware deve essere 4.18.1901.x o successiva.</span><span class="sxs-lookup"><span data-stu-id="65933-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="65933-121">Supportato nei computer con Windows 10, versione 1703 o successiva, Windows Server 2016 e 2019.</span><span class="sxs-lookup"><span data-stu-id="65933-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="65933-122">Per iniziare a bloccare i file, devi prima attivare [la **funzionalità Blocca**](advanced-features.md) o consenti in Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="65933-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="65933-123">Questa funzionalità è progettata per impedire il download di malware sospetti (o file potenzialmente dannosi) dal Web.</span><span class="sxs-lookup"><span data-stu-id="65933-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="65933-124">Attualmente supporta file eseguibili portabili (PE), inclusi i file _EXE_ _e DLL._</span><span class="sxs-lookup"><span data-stu-id="65933-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="65933-125">La copertura verrà estesa nel tempo.</span><span class="sxs-lookup"><span data-stu-id="65933-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="65933-126">La funzione consenti o blocca non può essere eseguita sui file se la classificazione del file esiste nella cache del dispositivo prima dell'azione consenti o blocca</span><span class="sxs-lookup"><span data-stu-id="65933-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="65933-127">I file firmati attendibili verranno trattati in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="65933-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="65933-128">Defender for Endpoint è ottimizzato per gestire i file dannosi.</span><span class="sxs-lookup"><span data-stu-id="65933-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="65933-129">Il tentativo di bloccare i file firmati attendibili, in alcuni casi, può avere implicazioni sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="65933-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="65933-130">In genere, i blocchi di file vengono applicati entro un paio di minuti, ma possono richiedere fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="65933-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="65933-131">Creare un indicatore per i file dalla pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="65933-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="65933-132">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.</span><span class="sxs-lookup"><span data-stu-id="65933-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="65933-133">Selezionare la **scheda Hash file.**</span><span class="sxs-lookup"><span data-stu-id="65933-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="65933-134">Selezionare **Aggiungi indicatore**.</span><span class="sxs-lookup"><span data-stu-id="65933-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="65933-135">Specificare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="65933-135">Specify the following details:</span></span>
   - <span data-ttu-id="65933-136">Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="65933-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="65933-137">Azione: specificare l'azione da eseguire e fornire una descrizione.</span><span class="sxs-lookup"><span data-stu-id="65933-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="65933-138">Ambito: definire l'ambito del gruppo di computer.</span><span class="sxs-lookup"><span data-stu-id="65933-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="65933-139">Esaminare i dettagli nella scheda Riepilogo, quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="65933-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="65933-140">Creare un indicatore contestuale dalla pagina dei dettagli del file</span><span class="sxs-lookup"><span data-stu-id="65933-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="65933-141">Una delle opzioni disponibili per eseguire [azioni di risposta su un file](respond-file-alerts.md) è l'aggiunta di un indicatore per il file.</span><span class="sxs-lookup"><span data-stu-id="65933-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="65933-142">Quando si aggiunge un hash indicatore per un file, è possibile scegliere di generare un avviso e bloccare il file ogni volta che un computer dell'organizzazione tenta di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="65933-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="65933-143">I file bloccati automaticamente da un indicatore non verranno visualizzati nel centro notifiche del file, ma gli avvisi saranno comunque visibili nella coda avvisi.</span><span class="sxs-lookup"><span data-stu-id="65933-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="65933-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="65933-144">Related topics</span></span>
- [<span data-ttu-id="65933-145">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="65933-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="65933-146">Creare indicatori per IP e URL/domini</span><span class="sxs-lookup"><span data-stu-id="65933-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="65933-147">Creare indicatori in base ai certificati</span><span class="sxs-lookup"><span data-stu-id="65933-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="65933-148">Gestire gli indicatori</span><span class="sxs-lookup"><span data-stu-id="65933-148">Manage indicators</span></span>](indicator-manage.md)
