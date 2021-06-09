---
title: Nomi dei dispositivi
description: Come Microsoft Managed Desktop i nomi dei dispositivi
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
# <a name="device-names"></a>Nomi dei dispositivi

Microsoft Managed Desktop utilizza Windows Autopilot, Azure Active Directory e Microsoft Intune. Perché questi servizi funzionino senza problemi, i dispositivi necessitano di nomi coerenti e standardizzati. Microsoft Managed Desktop applica un formato di nome standardizzato (nel formato *MMD-%RAND11)* quando i dispositivi vengono registrati. Windows Autopilot assegna questi nomi. Per ulteriori informazioni su Autopilot, vedere [First-run experience with Autopilot and the Enrollment Status Page.](../get-started/esp-first-run.md)

## <a name="automated-name-changes"></a>Modifiche automatiche al nome

Se un dispositivo viene rinominato in un secondo momento, Microsoft Managed Desktop lo rinomina automaticamente con un nuovo nome nel formato standardizzato. Questo processo viene eseguito ogni quattro ore. La modifica del nome viene apportata al successivo riavvio del dispositivo da parte dell'utente.

> [!IMPORTANT]
> Se l'ambiente dipende da nomi di dispositivi specifici ,ad esempio per supportare una particolare configurazione di rete, è consigliabile analizzare le opzioni per rimuovere tale dipendenza prima di eseguire la registrazione in Microsoft Managed Desktop. Se devi mantenere la dipendenza del nome, puoi [](../working-with-managed-desktop/admin-support.md) inviare una richiesta tramite il portale di amministrazione per disabilitare la funzione di ridenominazione e usare il formato del nome desiderato.