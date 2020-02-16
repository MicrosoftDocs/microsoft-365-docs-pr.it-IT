---
title: Modificare l'accesso condizionale
description: Come escludere determinati account Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1bc5d937616cba60c5af43fe22a7c4dccf89a55e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085806"
---
# <a name="adjust-conditional-access"></a>Modificare l'accesso condizionale

Se si utilizzano i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) nell'organizzazione, sarà necessario impostarli in modo da escludere determinati account affinché Microsoft Managed Desktop possa funzionare correttamente.

A tale scopo, attieniti alla seguente procedura:

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
