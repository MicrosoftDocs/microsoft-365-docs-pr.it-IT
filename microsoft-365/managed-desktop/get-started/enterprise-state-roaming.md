---
title: Abilitare Enterprise State Roaming
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409117"
---
# <a name="enable-enterprise-state-roaming"></a>Abilitare Enterprise State Roaming

[Enterprise stato roaming consente](/azure/active-directory/devices/enterprise-state-roaming-overview) agli utenti di sincronizzare in modo sicuro i dati delle impostazioni utente e dell'applicazione nel cloud. Ciò significa che hanno la stessa esperienza, indipendentemente Windows dispositivo a cui a loro accede. Ad esempio, se si sostituisce uno dei dispositivi Microsoft Managed Desktop con uno nuovo, l'aspetto e il comportamento saranno esattamente gli stessi dell'ultimo. Enterprise State Roaming è una funzionalità facoltativa per il servizio di Microsoft Managed Desktop che è possibile configurare per gli utenti e non è inclusa o gestita come parte di Microsoft Managed Desktop.

Per abilitare Enterprise roaming dello stato, seguire i passaggi descritti in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

>[!NOTE]
>Se abiliti Enterprise stato roaming, l'elenco delle lingue preferite sovrascriverà la lingua selezionata durante la configurazione del dispositivo. Anche se gli utenti possono risolvere facilmente questo problema, inizialmente potrebbe verificarsi un'esperienza di localizzazione incoerente. Determinare se Enterprise stato roaming è giusto per gli utenti prima di configurare i dispositivi.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a usare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. [Distribuire il Portale aziendale Intune](company-portal.md)
5. Abilitare Enterprise roaming dello stato (questo argomento)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)
