---
title: L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365
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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente di Microsoft 365 per testare l’identità e l’accesso dei dispositivi.
ms.openlocfilehash: e90c27edbf4ad5a78c337bf2488956ce82a1ec3e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051319"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365

*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

[Le configurazioni di identità e](../security/defender-365-security/microsoft-365-policies-configurations.md) accesso ai dispositivi sono un set di configurazioni consigliate e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD).

Per creare un ambiente di test con le configurazioni comuni di identità e accesso ai dispositivi:

1. Configurare l'ambiente di testing con le funzionalità essenziali di identità e sicurezza in base alle scelte dell’utente del modello di identità e metodo di autenticazione:

  - [Solo cloud](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronizzazione dell'hash delle password (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticazione pass-through](pta-prereqs-m365-test-environment.md)

2. Usa [Criteri comuni di identità](../security/defender-365-security/identity-access-policies.md) e accesso ai dispositivi per configurare i criteri che si basano sui prerequisiti configurati per l'ambiente di testing ed esplorare e verificare la protezione per identità e dispositivi.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test per identità aggiuntive](m365-enterprise-test-lab-guides.md#identity)

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)
