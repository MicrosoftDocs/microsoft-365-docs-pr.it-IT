---
title: Aggiungere un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
description: L'organizzazione potrebbe avere bisogno di più domini in modo che i clienti possano trovarti. Informazioni su come aggiungere un altro dominio all'abbonamento.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706431"
---
# <a name="add-another-domain"></a>Aggiungere un altro dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

L'azienda potrebbe avere bisogno di più nomi di dominio per scopi diversi. Ad esempio, potresti voler aggiungere un'ortografia diversa del nome della società perché i clienti lo stanno già usando e le loro comunicazioni non sono riuscite a raggiungere l'utente.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'Microsoft 365 di amministrazione scegliere **Installazione**.
1. In **Configurare il dominio personalizzato** selezionare **Visualizza.**
1. Scegliere **Gestisci** e quindi **Aggiungi dominio**.
1. Immettere il nuovo nome di dominio che si desidera aggiungere e quindi selezionare **Avanti.**
1. Accedi al registrar, in questo caso GoDaddy, quindi seleziona **Avanti**.
1. Se richiesto, accedere al registrar e quindi scegliere **Autorizza**.
1. Scegliere **Add the DNS records for me** e quindi selezionare **Next**.
1. Scegliere i servizi per il nuovo dominio e deselezionare le caselle di controllo per tutti i servizi che verranno gestiti da un dominio diverso. Ad esempio, se si desidera solo utilizzare il nuovo dominio per la posta elettronica, scegliere **Exchange** e deselezionare le caselle di controllo per Skype for Business **e** **Gestione dispositivi mobili per Office 365**.
1. Selezionare **Avanti**, **Autorizza**, **Avanti** e quindi **Fine**. Il nuovo dominio è stato aggiunto.

Per ricevere posta elettronica nel nuovo dominio, è necessario aggiungere un nuovo alias di posta elettronica per ogni utente:

1. Selezionare **Utenti**, **Utenti attivi** e quindi selezionare l'utente a cui verrà assegnato il nuovo alias.
1. Scegliere **Gestisci alias di posta** elettronica e quindi Aggiungi un **alias.**
1. Immetti il nome utente e quindi scegli il nuovo dominio nell'elenco a discesa.
1. Selezionare **Salva modifiche** e quindi chiudere la finestra.
1. Ripetere questi passaggi per ogni utente che deve ricevere posta elettronica nel nuovo dominio.

## <a name="related-content"></a>Contenuto correlato

[Aggiungere un dominio a Microsoft 365](../admin/setup/add-domain.md) (articolo)\
[Aggiungere record DNS per connettere il dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (articolo)\
[Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar del dominio](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (articolo)\
[Domande frequenti sui domini](../admin/setup/domains-faq.yml) (articolo)