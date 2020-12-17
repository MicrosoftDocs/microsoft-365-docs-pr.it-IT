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
ROBOTS: NOINDEX, NOFOLLOW
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
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702166"
---
# <a name="add-another-domain"></a>Aggiungere un altro dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

La propria azienda potrebbe richiedere più nomi di dominio per scopi diversi. Ad esempio, è possibile aggiungere un altro controllo ortografico del nome della società perché i clienti lo utilizzano già e le comunicazioni non sono state in grado di raggiungere l'utente.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Setup**.
1. In **Get your custom domain set up**, selezionare **View**.
1. Scegliere **Gestisci** e quindi **Aggiungi dominio**.
1. Immettere il nuovo nome di dominio che si desidera aggiungere e quindi fare clic su **Avanti**.
1. Accedere al registrar, in questo caso GoDaddy, quindi selezionare **Avanti**.
1. Se richiesto, accedere al servizio di registrazione e quindi scegliere **autorizza**.
1. Scegliere **Add the DNS Records for me**, quindi fare clic su **Avanti**.
1. Scegliere i servizi per il nuovo dominio e deselezionare le caselle di controllo per tutti i servizi che verranno gestiti da un dominio diverso. Ad esempio, se si desidera utilizzare il nuovo dominio per la posta elettronica, scegliere **Exchange** e deselezionare le caselle di controllo per **Skype for business** e **per la gestione dei dispositivi mobili per Office 365**.
1. Fare clic su **Avanti**, su **autorizzare**, su **Avanti** e quindi su **fine**. È stato aggiunto il nuovo dominio.

Per ricevere la posta elettronica nel nuovo dominio, è necessario aggiungere un nuovo alias di posta elettronica per ogni utente:

1. Selezionare **gli utenti**, **gli utenti attivi** e quindi selezionare l'utente a cui verrà assegnato il nuovo alias.
1. Scegliere **Gestisci alias di posta elettronica** e quindi **aggiungere un alias**.
1. Immettere il nome utente e quindi scegliere il nuovo dominio dall'elenco a discesa.
1. Selezionare **Salva modifiche**, quindi chiudere la finestra.
1. Ripetere questi passaggi per ogni utente che deve ricevere la posta elettronica nel nuovo dominio.