---
title: Creare e gestire gruppi di dispositivi in Microsoft Defender ATP
description: Creare gruppi di dispositivi e impostare livelli di correzione automatizzati su di essi confiando le regole applicabili al gruppo
keywords: gruppi di dispositivi, gruppi, correzione, livello, regole, gruppo aad, ruolo, assegnare, classificare
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
ms.openlocfilehash: dfc7c04bbde2b7061c92f5a25115b75a2f5b47b5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066301"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="f2bbe-104">Creare e gestire gruppi di dispositivi</span><span class="sxs-lookup"><span data-stu-id="f2bbe-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f2bbe-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f2bbe-105">**Applies to:**</span></span>
- <span data-ttu-id="f2bbe-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f2bbe-106">Azure Active Directory</span></span>
- <span data-ttu-id="f2bbe-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="f2bbe-107">Office 365</span></span>

> <span data-ttu-id="f2bbe-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f2bbe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f2bbe-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f2bbe-110">In uno scenario aziendale, ai team delle operazioni di sicurezza viene in genere assegnato un set di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="f2bbe-111">Questi dispositivi sono raggruppati in base a un set di attributi, ad esempio domini, nomi di computer o tag designati.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="f2bbe-112">In Microsoft Defender for Endpoint puoi creare gruppi di dispositivi e usarli per:</span><span class="sxs-lookup"><span data-stu-id="f2bbe-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="f2bbe-113">Limitare l'accesso agli avvisi e ai dati correlati a gruppi di utenti di Azure AD specifici con [ruoli RBAC assegnati](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="f2bbe-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="f2bbe-114">Configurare impostazioni di correzione automatica diverse per diversi set di dispositivi</span><span class="sxs-lookup"><span data-stu-id="f2bbe-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="f2bbe-115">Assegnare livelli di correzione specifici da applicare durante indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="f2bbe-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="f2bbe-116">In un'indagine filtra **l'elenco Dispositivi** in base a gruppi di dispositivi specifici usando il **filtro** Gruppo.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="f2bbe-117">Puoi creare gruppi di dispositivi nel contesto dell'accesso basato sui ruoli (RBAC) per controllare chi può eseguire azioni specifiche o visualizzare informazioni assegnando i gruppi di dispositivi a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="f2bbe-118">Per ulteriori informazioni, vedere [Manage portal access using role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="f2bbe-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="f2bbe-119">Per un'analisi completa dell'applicazione RBAC, vedere: Il SOC è in esecuzione [flat con RBAC.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="f2bbe-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="f2bbe-120">Come parte del processo di creazione di un gruppo di dispositivi, dovrai:</span><span class="sxs-lookup"><span data-stu-id="f2bbe-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="f2bbe-121">Imposta il livello di correzione automatico per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="f2bbe-122">Per ulteriori informazioni sui livelli di correzione, vedere [Use Automated investigation to investigate and remediate threats.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="f2bbe-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="f2bbe-123">Specifica la regola di corrispondenza che determina quale gruppo di dispositivi appartiene al gruppo in base al nome del dispositivo, al dominio, ai tag e alla piattaforma del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="f2bbe-124">Se un dispositivo è abbinato anche ad altri gruppi, viene aggiunto solo al gruppo di dispositivi con il livello più alto.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="f2bbe-125">Selezionare il gruppo di utenti di Azure AD che deve avere accesso al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="f2bbe-126">Classificare il gruppo di dispositivi rispetto ad altri gruppi dopo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="f2bbe-127">Un gruppo di dispositivi è accessibile a tutti gli utenti se non gli assegni alcun gruppo di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="f2bbe-128">Creare un gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="f2bbe-128">Create a device group</span></span>

1. <span data-ttu-id="f2bbe-129">Nel riquadro di spostamento seleziona **Impostazioni Gruppi**  >  **di dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="f2bbe-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="f2bbe-130">Fai **clic su Aggiungi gruppo di dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="f2bbe-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="f2bbe-131">Immetti il nome del gruppo e le impostazioni di automazione e specifica la regola di corrispondenza che determina quali dispositivi appartengono al gruppo.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="f2bbe-132">Vedi [Come inizia l'indagine automatizzata.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="f2bbe-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="f2bbe-133">Se si desidera raggruppare i dispositivi in base all'unità organizzativa, è possibile configurare la chiave del Registro di sistema per l'affiliazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="f2bbe-134">Per altre informazioni sul tagging dei dispositivi, vedi [Creare e gestire tag dispositivo.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="f2bbe-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="f2bbe-135">Visualizzare in anteprima diversi dispositivi che saranno corrispondenti a questa regola.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="f2bbe-136">Se si è soddisfatti della regola, fare clic sulla **scheda Accesso** utente.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="f2bbe-137">Assegnare i gruppi di utenti che possono accedere al gruppo di dispositivi creato.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f2bbe-138">È possibile concedere l'accesso solo ai gruppi di utenti di Azure AD assegnati ai ruoli RBAC.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="f2bbe-139">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-139">Click **Close**.</span></span> <span data-ttu-id="f2bbe-140">Le modifiche alla configurazione vengono applicate.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="f2bbe-141">Gestire i gruppi di dispositivi</span><span class="sxs-lookup"><span data-stu-id="f2bbe-141">Manage device groups</span></span>

<span data-ttu-id="f2bbe-142">Puoi alzare di livello o abbassare di livello il rango di un gruppo di dispositivi in modo che gli sia stata data una priorità maggiore o inferiore durante la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="f2bbe-143">Quando un dispositivo viene abbinato a più di un gruppo, viene aggiunto solo al gruppo con il livello più alto.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="f2bbe-144">È inoltre possibile modificare ed eliminare gruppi.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="f2bbe-145">L'eliminazione di un gruppo di dispositivi può influire sulle regole di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="f2bbe-146">Se un gruppo di dispositivi è configurato in base a una regola di notifica tramite posta elettronica, verrà rimosso da tale regola.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="f2bbe-147">Se il gruppo di dispositivi è l'unico gruppo configurato per una notifica tramite posta elettronica, la regola di notifica tramite posta elettronica verrà eliminata insieme al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="f2bbe-148">Per impostazione predefinita, i gruppi di dispositivi sono accessibili a tutti gli utenti con accesso al portale.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="f2bbe-149">Puoi modificare il comportamento predefinito assegnando gruppi di utenti di Azure AD al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="f2bbe-150">I dispositivi non corrispondenti ad alcun gruppo vengono aggiunti al gruppo Dispositivi non raggruppati (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="f2bbe-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="f2bbe-151">Non è possibile modificare la classificazione di questo gruppo o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="f2bbe-152">Tuttavia, è possibile modificare il livello di correzione di questo gruppo e definire i gruppi di utenti di Azure AD che possono accedere a questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="f2bbe-153">L'applicazione delle modifiche alla configurazione del gruppo di dispositivi può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="f2bbe-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2bbe-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f2bbe-154">Related topics</span></span>

- [<span data-ttu-id="f2bbe-155">Gestire l'accesso al portale tramite il controllo dell'accesso basato sui ruoli</span><span class="sxs-lookup"><span data-stu-id="f2bbe-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="f2bbe-156">Creare e gestire tag dispositivo</span><span class="sxs-lookup"><span data-stu-id="f2bbe-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="f2bbe-157">Ottenere l'elenco dei gruppi di dispositivi tenant con l'API Graph</span><span class="sxs-lookup"><span data-stu-id="f2bbe-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
