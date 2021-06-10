---
title: Creare e gestire tag di dispositivi
description: Usare i tag del dispositivo per raggruppare i dispositivi per acquisire il contesto e abilitare la creazione dinamica dell'elenco come parte di un evento imprevisto
keywords: tag, tag dispositivo, gruppi di dispositivi, gruppi, correzione, livello, regole, gruppo aad, ruolo, assegnare, classificare
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
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187590"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="f093b-104">Creare e gestire tag di dispositivi</span><span class="sxs-lookup"><span data-stu-id="f093b-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f093b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f093b-105">**Applies to:**</span></span>
- [<span data-ttu-id="f093b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f093b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f093b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f093b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f093b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f093b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f093b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f093b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f093b-110">Aggiungere tag nei dispositivi per creare un'affiliazione a un gruppo logico.</span><span class="sxs-lookup"><span data-stu-id="f093b-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="f093b-111">I tag del dispositivo supportano la mappatura corretta della rete, consentendo di collegare tag diversi per acquisire il contesto e consentire la creazione di elenchi dinamici come parte di un incidente.</span><span class="sxs-lookup"><span data-stu-id="f093b-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="f093b-112">I tag possono essere usati come filtro nella **visualizzazione elenco** Dispositivi o per raggruppare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f093b-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="f093b-113">Per altre informazioni sul raggruppamento dei dispositivi, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f093b-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="f093b-114">Puoi aggiungere tag nei dispositivi usando i modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f093b-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="f093b-115">Usando il portale</span><span class="sxs-lookup"><span data-stu-id="f093b-115">Using the portal</span></span>
- <span data-ttu-id="f093b-116">Impostando un valore della chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="f093b-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="f093b-117">Potrebbe verificarsi una latenza tra il momento in cui un tag viene aggiunto a un dispositivo e la relativa disponibilità nell'elenco dei dispositivi e nella pagina del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f093b-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="f093b-118">Per aggiungere tag del dispositivo usando l'API, vedere [Aggiungere o rimuovere l'API dei tag del dispositivo](add-or-remove-machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="f093b-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="f093b-119">Aggiungere e gestire i tag per i dispositivi tramite il portale</span><span class="sxs-lookup"><span data-stu-id="f093b-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="f093b-120">Selezionare il dispositivo in cui gestire i tag.</span><span class="sxs-lookup"><span data-stu-id="f093b-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="f093b-121">È possibile selezionare o cercare un dispositivo in una delle seguenti visualizzazioni:</span><span class="sxs-lookup"><span data-stu-id="f093b-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="f093b-122">**Dashboard delle operazioni di** sicurezza: selezionare il nome del dispositivo nella sezione Dispositivi principali con avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="f093b-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="f093b-123">**Coda degli avvisi**: selezionare il nome del dispositivo accanto all'icona del dispositivo dalla coda degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="f093b-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="f093b-124">**Elenco dispositivi**: selezionare il nome del dispositivo nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f093b-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="f093b-125">**Casella di ricerca**: selezionare Dispositivo dal menu a discesa e inserire il nome del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f093b-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="f093b-126">È anche possibile accedere alla pagina di avviso tramite le visualizzazioni file e IP.</span><span class="sxs-lookup"><span data-stu-id="f093b-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="f093b-127">Selezionare **Gestisci tag** dalla riga Azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="f093b-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![Immagine del pulsante Gestisci tag](images/manage-tags.png)

3. <span data-ttu-id="f093b-129">Digitare per trovare o creare tag</span><span class="sxs-lookup"><span data-stu-id="f093b-129">Type to find or create tags</span></span>

    ![Immagine dell'aggiunta di tag in un dispositivo1](images/new-tags.png)

<span data-ttu-id="f093b-131">I tag vengono aggiunti alla visualizzazione del dispositivo e verranno visualizzati anche nella **visualizzazione elenco** Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f093b-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="f093b-132">Puoi quindi usare il filtro **Tag** per visualizzare l'elenco pertinente dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f093b-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="f093b-133">Il filtro potrebbe non funzionare sui nomi di tag che contengono parentesi.</span><span class="sxs-lookup"><span data-stu-id="f093b-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="f093b-134">Quando si crea un nuovo tag, viene visualizzato un elenco di tag esistenti.</span><span class="sxs-lookup"><span data-stu-id="f093b-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="f093b-135">L'elenco mostra solo i tag creati tramite il portale.</span><span class="sxs-lookup"><span data-stu-id="f093b-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="f093b-136">I tag esistenti creati dai dispositivi client non verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="f093b-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="f093b-137">È inoltre possibile eliminare i tag da questa visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f093b-137">You can also delete tags from this view.</span></span>

![Immagine dell'aggiunta di tag in un dispositivo2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="f093b-139">Aggiungere tag dispositivo impostando un valore di chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="f093b-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="f093b-140">Applicabile solo nei dispositivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f093b-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="f093b-141">Windows 10 versione 1709 o successiva</span><span class="sxs-lookup"><span data-stu-id="f093b-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="f093b-142">Windows Server, versione 1803 o successiva</span><span class="sxs-lookup"><span data-stu-id="f093b-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="f093b-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f093b-143">Windows Server 2016</span></span>
>- <span data-ttu-id="f093b-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f093b-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="f093b-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f093b-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="f093b-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f093b-146">Windows 8.1</span></span>
>- <span data-ttu-id="f093b-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="f093b-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="f093b-148">Il numero massimo di caratteri che è possibile impostare in un tag è 200.</span><span class="sxs-lookup"><span data-stu-id="f093b-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="f093b-149">I dispositivi con tag simili possono essere utili quando devi applicare un'azione contestuale a un elenco specifico di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f093b-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="f093b-150">Usa la seguente voce della chiave del Registro di sistema per aggiungere un tag in un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f093b-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="f093b-151">Chiave del Registro di sistema: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="f093b-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="f093b-152">Valore della chiave del Registro di sistema (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="f093b-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="f093b-153">Dati chiave del Registro di sistema: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="f093b-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="f093b-154">Il tag del dispositivo fa parte del report delle informazioni sul dispositivo generato una volta al giorno.</span><span class="sxs-lookup"><span data-stu-id="f093b-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="f093b-155">In alternativa, puoi scegliere di riavviare l'endpoint che trasferirebbe un nuovo report di informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f093b-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="f093b-156">Se devi rimuovere un tag aggiunto usando la chiave del Registro di sistema precedente, cancella il contenuto dei dati della chiave del Registro di sistema invece di rimuovere la chiave "Group".</span><span class="sxs-lookup"><span data-stu-id="f093b-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
