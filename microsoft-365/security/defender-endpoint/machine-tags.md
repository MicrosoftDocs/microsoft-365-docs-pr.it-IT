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
ms.openlocfilehash: 83dd2483b93b2f4fe520973ce05346f59baf2f28
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453584"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="64e45-104">Creare e gestire tag di dispositivi</span><span class="sxs-lookup"><span data-stu-id="64e45-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64e45-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="64e45-105">**Applies to:**</span></span>
- [<span data-ttu-id="64e45-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="64e45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64e45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64e45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64e45-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="64e45-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="64e45-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="64e45-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="64e45-110">Aggiungere tag nei dispositivi per creare un'affiliazione a un gruppo logico.</span><span class="sxs-lookup"><span data-stu-id="64e45-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="64e45-111">I tag del dispositivo supportano la mappatura corretta della rete, consentendo di collegare tag diversi per acquisire il contesto e consentire la creazione di elenchi dinamici come parte di un incidente.</span><span class="sxs-lookup"><span data-stu-id="64e45-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="64e45-112">I tag possono essere usati come filtro nella **visualizzazione elenco** Dispositivi o per raggruppare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="64e45-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="64e45-113">Per altre informazioni sul raggruppamento dei dispositivi, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="64e45-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="64e45-114">Puoi aggiungere tag nei dispositivi usando i modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="64e45-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="64e45-115">Usando il portale</span><span class="sxs-lookup"><span data-stu-id="64e45-115">Using the portal</span></span>
- <span data-ttu-id="64e45-116">Impostando un valore della chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="64e45-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="64e45-117">Potrebbe verificarsi una latenza tra il momento in cui un tag viene aggiunto a un dispositivo e la relativa disponibilità nell'elenco dei dispositivi e nella pagina del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64e45-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="64e45-118">Per aggiungere tag del dispositivo usando l'API, vedere [Aggiungere o rimuovere l'API dei tag del dispositivo](add-or-remove-machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="64e45-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="64e45-119">Aggiungere e gestire i tag per i dispositivi tramite il portale</span><span class="sxs-lookup"><span data-stu-id="64e45-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="64e45-120">Selezionare il dispositivo in cui gestire i tag.</span><span class="sxs-lookup"><span data-stu-id="64e45-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="64e45-121">È possibile selezionare o cercare un dispositivo in una delle seguenti visualizzazioni:</span><span class="sxs-lookup"><span data-stu-id="64e45-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="64e45-122">**Dashboard delle operazioni di** sicurezza: selezionare il nome del dispositivo nella sezione Dispositivi principali con avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="64e45-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="64e45-123">**Coda degli avvisi**: selezionare il nome del dispositivo accanto all'icona del dispositivo dalla coda degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="64e45-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="64e45-124">**Elenco dispositivi**: selezionare il nome del dispositivo nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="64e45-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="64e45-125">**Casella di ricerca**: selezionare Dispositivo dal menu a discesa e inserire il nome del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64e45-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="64e45-126">È anche possibile accedere alla pagina di avviso tramite le visualizzazioni file e IP.</span><span class="sxs-lookup"><span data-stu-id="64e45-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="64e45-127">Selezionare **Gestisci tag** dalla riga Azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="64e45-127">Select **Manage Tags** from the row of Response actions.</span></span>

    :::image type="content" alt-text="Immagine del pulsante Gestisci tag." source="images/manage-tags-option.png":::

3. <span data-ttu-id="64e45-129">Digitare per trovare o creare tag</span><span class="sxs-lookup"><span data-stu-id="64e45-129">Type to find or create tags</span></span>

    :::image type="content" alt-text="Immagine dell'aggiunta di tag in un dispositivo1." source="images/create-new-tag.png":::

<span data-ttu-id="64e45-131">I tag vengono aggiunti alla visualizzazione del dispositivo e verranno visualizzati anche nella **visualizzazione elenco** Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="64e45-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="64e45-132">Puoi quindi usare il filtro **Tag** per visualizzare l'elenco pertinente dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="64e45-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="64e45-133">Il filtro potrebbe non funzionare sui nomi di tag che contengono parentesi.</span><span class="sxs-lookup"><span data-stu-id="64e45-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="64e45-134">Quando si crea un nuovo tag, viene visualizzato un elenco di tag esistenti.</span><span class="sxs-lookup"><span data-stu-id="64e45-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="64e45-135">L'elenco mostra solo i tag creati tramite il portale.</span><span class="sxs-lookup"><span data-stu-id="64e45-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="64e45-136">I tag esistenti creati dai dispositivi client non verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="64e45-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="64e45-137">È inoltre possibile eliminare i tag da questa visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="64e45-137">You can also delete tags from this view.</span></span>

:::image type="content" alt-text="Immagine dell'aggiunta di tag in un dispositivo2." source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="64e45-139">Aggiungere tag dispositivo impostando un valore di chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="64e45-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="64e45-140">Applicabile solo nei dispositivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="64e45-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="64e45-141">Windows 10 versione 1709 o successiva</span><span class="sxs-lookup"><span data-stu-id="64e45-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="64e45-142">Windows Server, versione 1803 o successiva</span><span class="sxs-lookup"><span data-stu-id="64e45-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="64e45-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="64e45-143">Windows Server 2016</span></span>
>- <span data-ttu-id="64e45-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="64e45-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="64e45-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="64e45-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="64e45-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="64e45-146">Windows 8.1</span></span>
>- <span data-ttu-id="64e45-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="64e45-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="64e45-148">Il numero massimo di caratteri che è possibile impostare in un tag è 200.</span><span class="sxs-lookup"><span data-stu-id="64e45-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="64e45-149">I dispositivi con tag simili possono essere utili quando devi applicare un'azione contestuale a un elenco specifico di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="64e45-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="64e45-150">Usa la seguente voce della chiave del Registro di sistema per aggiungere un tag in un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="64e45-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="64e45-151">Chiave del Registro di sistema: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="64e45-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="64e45-152">Valore della chiave del Registro di sistema (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="64e45-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="64e45-153">Dati chiave del Registro di sistema: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="64e45-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="64e45-154">Il tag del dispositivo fa parte del report delle informazioni sul dispositivo generato una volta al giorno.</span><span class="sxs-lookup"><span data-stu-id="64e45-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="64e45-155">In alternativa, puoi scegliere di riavviare l'endpoint che trasferirebbe un nuovo report di informazioni sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64e45-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="64e45-156">Se devi rimuovere un tag aggiunto usando la chiave del Registro di sistema precedente, cancella il contenuto dei dati della chiave del Registro di sistema invece di rimuovere la chiave "Group".</span><span class="sxs-lookup"><span data-stu-id="64e45-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
