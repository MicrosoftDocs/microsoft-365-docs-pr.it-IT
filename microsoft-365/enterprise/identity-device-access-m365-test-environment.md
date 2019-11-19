---
title: L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente di Microsoft 365 per testare l’identità e l’accesso dei dispositivi.
ms.openlocfilehash: e86ff814f0b2b986de7eb26e7de362f17cd355e9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672592"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365

*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*

Le [configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md) sono un set di funzionalità e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD), tra cui Office 365 e Microsoft Intune in Microsoft 365 Enterprise.

Per creare un ambiente di testing che disponga dell’applicazione di questi criteri:

1. Configurare l'ambiente di testing con le funzionalità essenziali di identità e sicurezza in base alle scelte dell’utente del modello di identità e metodo di autenticazione:

  - [Solo cloud](cloud-only-prereqs-m365-test-environment.md)
  - [Sincronizzazione dell'hash delle password](phs-prereqs-m365-test-environment.md)
  - [Autenticazione pass-through](pta-prereqs-m365-test-environment.md)

2. Usare i [criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e testare la protezione di identità e dispositivi.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test per identità aggiuntive](m365-enterprise-test-lab-guides.md#identity)

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
