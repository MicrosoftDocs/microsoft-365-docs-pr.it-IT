---
title: Nomi dei dispositivi
description: Modalità di gestione dei nomi dei dispositivi da parte di Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893891"
---
# <a name="device-names"></a><span data-ttu-id="13095-103">Nomi dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="13095-103">Device names</span></span>

<span data-ttu-id="13095-104">Microsoft Managed Desktop usa Windows Autopilot, Azure Active Directory e Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="13095-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="13095-105">Perché questi servizi funzionino senza problemi, i dispositivi necessitano di nomi coerenti e standardizzati.</span><span class="sxs-lookup"><span data-stu-id="13095-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="13095-106">Microsoft Managed Desktop applica un formato di nome standardizzato (nel formato *MMD-%RAND11)* quando i dispositivi vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="13095-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="13095-107">Windows Autopilot assegna questi nomi.</span><span class="sxs-lookup"><span data-stu-id="13095-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="13095-108">Per ulteriori informazioni su Autopilot, vedere [First-run experience with Autopilot and the Enrollment Status Page.](../get-started/esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="13095-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="13095-109">Modifiche automatiche al nome</span><span class="sxs-lookup"><span data-stu-id="13095-109">Automated name changes</span></span>

<span data-ttu-id="13095-110">Se un dispositivo viene rinominato in un secondo momento, Microsoft Managed Desktop lo rinomina automaticamente con un nuovo nome nel formato standardizzato.</span><span class="sxs-lookup"><span data-stu-id="13095-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="13095-111">Questo processo viene eseguito ogni quattro ore.</span><span class="sxs-lookup"><span data-stu-id="13095-111">This process occurs every four hours.</span></span> <span data-ttu-id="13095-112">La modifica del nome viene apportata al successivo riavvio del dispositivo da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="13095-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13095-113">Se l'ambiente dipende da nomi di dispositivi specifici ,ad esempio per supportare una particolare configurazione di rete, è consigliabile analizzare le opzioni per rimuovere tale dipendenza prima di eseguire la registrazione in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="13095-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="13095-114">Se devi mantenere la dipendenza del nome, puoi [](../working-with-managed-desktop/admin-support.md) inviare una richiesta tramite il portale di amministrazione per disabilitare la funzione di ridenominazione e usare il formato del nome desiderato.</span><span class="sxs-lookup"><span data-stu-id="13095-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>