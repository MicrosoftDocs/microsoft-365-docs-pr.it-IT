---
title: Utilizzo di Domain Connect
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
description: Informazioni su come usare i registrar abilitati per Domain Connect e aggiungere il dominio a Microsoft 365.
ms.openlocfilehash: 109255d82100e636e3472242866a519ff64a9e54
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655613"
---
# <a name="using-domain-connect"></a>Utilizzo di Domain Connect

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.
  
[I ](https://www.domainconnect.org/) registrar abilitati per Domain Connect consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti. 
  
Nella procedura guidata, verrà semplicemente confermata la proprietà del dominio e quindi verranno impostati automaticamente i record del dominio, in modo che la posta elettronica venga inviata a Microsoft 365 e ad altri servizi di Microsoft 365, come Teams, con il dominio.
  
> [!NOTE]
> Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Integrazione dei registrar di Domain Connect con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plissato](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (rivenditori GoDaddy che utilizzano l'hosting DNS SecureServer)
    - [Domini MadDog](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Cosa succede alla posta elettronica e al sito Web?

Al termine dell'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutta la posta elettronica per il dominio inizierà a essere inviata a Microsoft 365. Assicurarsi di aver aggiunto utenti e di configurare le cassette postali in Microsoft 365 per tutti gli utenti che riceve la posta elettronica nel dominio.
  
Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova. I passaggi di configurazione di Domain Connect non influiscono sul sito Web.
