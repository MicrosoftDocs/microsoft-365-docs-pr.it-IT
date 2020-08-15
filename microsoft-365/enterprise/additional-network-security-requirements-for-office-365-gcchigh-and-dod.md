---
title: Requisiti di sicurezza di rete aggiuntivi per Office 365 GCC High e DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Riepilogo: Office 365 GCC High e DoD presentano requisiti di sicurezza della rete aggiuntivi'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691243"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Requisiti di sicurezza di rete aggiuntivi per Office 365 GCC High e DOD

*Questo articolo si applica a Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*

Office 365 GCC High e DOD sono ambienti cloud sicuri per soddisfare le esigenze del governo degli Stati Uniti e dei suoi fornitori e appaltatori.  Tali ambienti cloud dispongono di restrizioni di rete aggiuntive su cui gli endpoint esterni ai servizi sono autorizzati ad accedere.

I clienti GCC High e DOD che pianificano l'utilizzo di identità federate o di coesistenza ibrida possono richiedere a Microsoft di consentire l'accesso in ingresso e/o in uscita alle distribuzioni locali esistenti.  Di seguito sono riportati alcuni esempi di attività:

* Utilizzo di identità federate (con Active Directory Federation Services o STS supportate simili)
* Coesistenza ibrida con una distribuzione di Exchange Server locale o Skype for business
* Migrazione del contenuto utente esistente da un sistema locale

Per consentire al servizio di comunicare con gli endpoint locali, è **necessario** inviare un messaggio di posta elettronica a Office 365 Engineering per le modifiche apportate alla rete.

> [!WARNING]
> Tutte le richieste hanno un contratto di servizio di **tre settimane** e non possono essere velocizzate a causa dei controlli di sicurezza e conformità necessari e delle pipeline di distribuzione.  Sono incluse le richieste di rete onboarding iniziali e tutte le modifiche apportate dopo la migrazione al servizio.  Verificare che i team di rete siano a conoscenza di questa sequenza temporale e che lo includano nei cicli di pianificazione.

Inviare un messaggio di posta elettronica a [Office 365 Government Network whitelist](mailto:o365gwlt@microsoft.com) con le seguenti informazioni:

* **A**: [Office 365 Government Network whitelist](mailto:o365gwlt@microsoft.com)
* **From**: A tenant Administrator-l'invio di messaggi di posta elettronica **deve** corrispondere a un contatto di amministratore globale nel tenant
* **Oggetto di posta elettronica**: Office 365 GCC High Network Request-contoso.onmicrosoft.US (Replace this with your tenant Name)

Il corpo del messaggio deve includere i dati seguenti:

* Nome del tenant dei Microsoft Online Services (ad esempio, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Una lista di distribuzione di posta elettronica che Microsoft comunica con le comunicazioni in uscita relative alle modifiche alla rete e/o al follow-up per le subnet non valide
* Indicare se si prevede di utilizzare Microsoft teams Hybrid coesistenza con le distribuzioni locali
* URL con accesso esterno a un sistema di identità federata (ad esempio sts.contoso.com) e un intervallo di indirizzi IP nella notazione CIDR (ad esempio, 10.1.1.0/28)
* URL dell'elenco di revoche di certificati PKI locali e intervallo di indirizzi IP nella notazione CIDR
* Intervallo di indirizzi IP e URL accessibili esternamente per la distribuzione locale di Exchange Server in notazione CIDR
* Intervallo di indirizzi IP e URL accessibili esternamente per la distribuzione locale di Skype for business in notazione CIDR

Per motivi di sicurezza e conformità, tenere presente le restrizioni seguenti sulla richiesta:

* Vi è un limite di quattro subnet per tenant
* Le subnet devono trovarsi nella notazione CIDR (ad esempio, 10.1.1.0/28)
* Gli intervalli di subnet non possono essere superiori a/24
* **Non è possibile** soddisfare le richieste di autorizzazione per l'accesso ai servizi cloud commerciali (commercial Office 365, Google G-Suite, Amazon Web Services e così via).

Dopo che la richiesta è stata ricevuta e approvata da Microsoft, è presente un contratto di servizio per l'implementazione di tre settimane e non può essere velocizzata.  Si riceverà un riconoscimento iniziale quando è stata ricevuta la richiesta e una conferma finale dopo che è stata completata.
