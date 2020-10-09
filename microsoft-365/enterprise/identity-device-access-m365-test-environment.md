---
title: L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente di Microsoft 365 per testare l’identità e l’accesso dei dispositivi.
ms.openlocfilehash: b8e91a58bb6e1c00013b963c77151080a419b836
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398808"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

Le [configurazioni di accesso a identità e dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) sono un insieme di funzionalità e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure ad).

Per creare un ambiente di testing con le configurazioni di accesso ai dispositivi e le identità comuni sul posto:

1. Configurare l'ambiente di testing con le funzionalità essenziali di identità e sicurezza in base alle scelte dell’utente del modello di identità e metodo di autenticazione:

  - [Solo cloud](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronizzazione dell'hash delle password (PHS)](phs-prereqs-m365-test-environment.md)
  - [Autenticazione pass-through](pta-prereqs-m365-test-environment.md)

2. Utilizzare [criteri comuni di accesso a identità e](identity-access-policies.md) dispositivi per configurare i criteri che si basano sui prerequisiti configurati per l'ambiente di testing ed esplorare e verificare la protezione per identità e dispositivi.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test per identità aggiuntive](m365-enterprise-test-lab-guides.md#identity)

[Roadmap dell'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
