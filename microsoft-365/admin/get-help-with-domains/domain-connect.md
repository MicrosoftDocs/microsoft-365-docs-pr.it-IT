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
description: Informazioni su come utilizzare i registrar abilitati per la connessione al dominio e aggiungere il proprio dominio a Microsoft 365.
ms.openlocfilehash: e907317ec5b606c2fe73232a73c9abdfce26feea
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645348"
---
# <a name="using-domain-connect"></a>Utilizzo di Domain Connect

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.
  
I registrar abilitati alla [connessione di dominio](https://www.domainconnect.org/) consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti. 
  
Nella procedura guidata, è sufficiente confermare che si è proprietari del dominio e quindi configurare automaticamente i record del dominio, in modo che la posta elettronica venga a Microsoft 365 e ad altri servizi Microsoft 365, come i team, che collaborino con il proprio dominio.
  
> [!NOTE]
> Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect registrar che si integrano con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (rivenditori GoDaddy con hosting DNS di SecureServer)
    - [Domini di MadDog](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Cosa succede alla posta elettronica e al sito Web?

Dopo aver completato l'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica per il dominio inizieranno a essere inviati a Microsoft 365. Assicurarsi di aver aggiunto utenti e configurare le cassette postali in Microsoft 365 per tutti coloro che ricevono la posta elettronica nel dominio.
  
Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova. I passaggi di installazione di Domain Connect non influiscono sul sito Web.
