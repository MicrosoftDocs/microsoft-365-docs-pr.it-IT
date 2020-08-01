---
title: Modificare l'accesso condizionale
description: Come escludere determinati account Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529684"
---
# <a name="adjust-conditional-access"></a>Modificare l'accesso condizionale

Se si utilizzano i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) nell'organizzazione, sarà necessario impostarli in modo da escludere determinati account affinché Microsoft Managed Desktop possa funzionare correttamente.

A tal fine, attenersi alla seguente procedura:

1. Fare riferimento alla sezione relativa ai passaggi di rollback [in procedura: pianificare la distribuzione di accesso condizionale in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).
2. Attenersi alla procedura seguente per escludere il gruppo di *account del servizio di lavoro moderno* per tutti i criteri.


In caso di problemi con l'accesso condizionale, contattare il [supporto](../working-with-managed-desktop/admin-support.md)dell'amministratore.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a utilizzare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. Modificare l'accesso condizionale (questo argomento)
3. [Assegnare licenze](assign-licenses.md)
4. [Distribuire il Portale aziendale Intune](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)
