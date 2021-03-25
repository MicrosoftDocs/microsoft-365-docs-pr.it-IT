---
title: Assegnare l'accesso utente a Microsoft Defender Security Center
description: Assegnare l'accesso in lettura e scrittura o di sola lettura al portale di Microsoft Defender per endpoint.
keywords: assegnare ruoli utente, assegnare l'accesso in lettura e scrittura, assegnare l'accesso di sola lettura, utente, ruoli utente, ruoli
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164767"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Assegnare l'accesso utente a Microsoft Defender Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- Azure Active Directory
- Office 365
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint supporta due modi per gestire le autorizzazioni:

- **Gestione delle autorizzazioni di base:** impostare le autorizzazioni per l'accesso completo o di sola lettura.
- **Controllo degli accessi** in base al ruolo : consente di impostare autorizzazioni granulari definendo i ruoli, assegnando gruppi di utenti di Azure AD ai ruoli e concedendo ai gruppi di utenti l'accesso ai gruppi di dispositivi. Per ulteriori informazioni sul controllo degli accessi in base al ruolo, vedere [Manage portal access using role-based access control](rbac.md).

> [!NOTE]
> Se sono già state assegnate autorizzazioni di base, è possibile passare a RBAC in qualsiasi momento. Prima di eseguire il passaggio, considerare quanto segue:
> 
> - Agli utenti con accesso completo (gli utenti a cui è assegnato il ruolo di amministratore globale o amministratore della sicurezza in Azure AD), viene automaticamente assegnato il ruolo di amministratore predefinito defender per endpoint, che dispone anche dell'accesso completo. È possibile assegnare ulteriori gruppi di utenti di Azure AD al ruolo di amministratore di Defender for Endpoint dopo il passaggio a RBAC.  Solo gli utenti assegnati al ruolo di amministratore di Defender for Endpoint possono gestire le autorizzazioni tramite RBAC. 
> - Gli utenti con accesso di sola lettura (Lettori di sicurezza) perderanno l'accesso al portale finché non viene loro assegnato un ruolo. Si noti che solo i gruppi di utenti di Azure AD possono essere assegnati a un ruolo in RBAC.
> - Dopo il passaggio al controllo degli accessi in base al ruolo, non sarà possibile tornare a utilizzare la gestione delle autorizzazioni di base.

## <a name="related-topics"></a>Argomenti correlati

- [Usare le autorizzazioni di base per accedere al portale](basic-permissions.md)
- [Gestire l'accesso al portale tramite RBAC](rbac.md)
