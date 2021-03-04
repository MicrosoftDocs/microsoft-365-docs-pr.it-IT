---
title: Aggiungere un dominio
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come aggiungere un altro dominio all'abbonamento.
ms.openlocfilehash: fef3dc06f270b79cc7f9e729b39727c9116b923d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423084"
---
# <a name="add-another-domain"></a>Aggiungere un altro dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

L'azienda potrebbe avere bisogno di più nomi di dominio per scopi diversi. Ad esempio, potrebbe essere necessario aggiungere un'ortografia diversa del nome della società perché i clienti lo stanno già usando e le loro comunicazioni non sono riuscite a raggiungere l'utente.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Configurazione.**
1. In **Configurare il dominio personalizzato selezionare** **Visualizza.**
1. Scegliere **Gestisci** e quindi **Aggiungi dominio.**
1. Immettere il nuovo nome di dominio che si desidera aggiungere e quindi selezionare **Avanti.**
1. Accedere al registrar, in questo caso GoDaddy, quindi selezionare **Avanti.**
1. Se richiesto, accedere al registrar e quindi scegliere **Autorizza.**
1. Choose **Add the DNS records for me**, and then select **Next**.
1. Scegliere i servizi per il nuovo dominio e deselezionare le caselle di controllo per tutti i servizi che verranno gestiti da un dominio diverso. Ad esempio, se si vuole solo usare il nuovo dominio per la posta elettronica, scegliere **Exchange** e deselezionare le caselle di controllo per **Skype for Business** e Gestione dispositivi mobili per Office **365.**
1. Selezionare **Avanti,** **Autorizza,** **Avanti** e quindi **Fine.** Il nuovo dominio è stato aggiunto.

Per ricevere la posta elettronica nel nuovo dominio, è necessario aggiungere un nuovo alias di posta elettronica per ogni utente:

1. Selezionare **Utenti**, **Utenti attivi** e quindi selezionare l'utente a cui verrà assegnato il nuovo alias.
1. Choose **Manage email aliases**, and then **Add an alias**.
1. Immetti il nome utente e quindi scegli il nuovo dominio nell'elenco a discesa.
1. Selezionare **Salva modifiche** e quindi chiudere la finestra.
1. Ripetere questi passaggi per ogni utente che deve ricevere posta elettronica nel nuovo dominio.