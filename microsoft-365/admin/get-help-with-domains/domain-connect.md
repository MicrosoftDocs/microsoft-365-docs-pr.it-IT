---
title: Utilizzo di Domain Connessione
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Informazioni su come usare i registrar abilitati Connessione dominio e aggiungere il dominio a Microsoft 365.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228014"
---
# <a name="using-domain-connect"></a>Utilizzo di Domain Connessione

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.

[I Connessione](https://www.domainconnect.org/) abilitati al dominio consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti.

Nella procedura guidata verrà semplicemente confermata la proprietà del dominio e quindi verranno impostati automaticamente i record del dominio, in modo che la posta elettronica venga inviata a Microsoft 365 e ad altri servizi Microsoft 365, ad esempio Teams, che funzionino con il dominio.

> [!NOTE]
> Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registrar Connessione di dominio che si integrano con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (rivenditori GoDaddy che usano l'hosting DNS SecureServer)
  - [MadDog Web Hosting](https://maddogwebhosting.com/domains/)
  - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Cosa succede alla posta elettronica e al sito Web?

Al termine dell'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica per il dominio inizieranno a essere Microsoft 365. Assicurarsi di aver aggiunto utenti e di configurare le cassette postali in Microsoft 365 per tutti coloro che riceve la posta elettronica nel dominio.

Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova. La procedura di Connessione dominio non influisce sul sito Web.
