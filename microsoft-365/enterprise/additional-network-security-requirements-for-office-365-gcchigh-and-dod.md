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
description: 'Riepilogo: Office 365 GCC High e DoD hanno requisiti di sicurezza di rete aggiuntivi'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691243"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Altri requisiti di sicurezza della rete per Office 365 GCC High e DoD

*Questo articolo si applica a Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*

Office 365 GCC High e DOD sono ambienti cloud sicuri per soddisfare le esigenze del governo degli Stati Uniti e dei suoi fornitori e terzisti.  Questi ambienti cloud hanno restrizioni di rete aggiuntive a cui gli endpoint esterni a cui i servizi sono autorizzati ad accedere.

I clienti GCC High e DOD che pianificano di utilizzare le identità federate o la coesistenza ibrida potrebbero richiedere a Microsoft di consentire l'accesso in ingresso e/o in uscita alle distribuzioni locali esistenti.  Di seguito sono riportati alcuni esempi di queste attività:

* Utilizzo di identità federate (con Active Directory Federation Services o un servizio token di sicurezza supportato simile)
* Coesistenza ibrida con una distribuzione Exchange Server locale o Skype for Business
* Migrazione di contenuto utente esistente da un sistema locale

Per consentire al servizio di comunicare con gli  endpoint locali, è necessario inviare un messaggio di posta elettronica a Office 365 engineering per le modifiche di rete.

> [!WARNING]
> Tutte le richieste **hanno** un contratto di servizio di tre settimane e non possono essere accelerate a causa dei controlli di sicurezza e conformità necessari e delle pipeline di distribuzione.  Sono incluse le richieste di rete di onboarding iniziali e le eventuali modifiche dopo la migrazione al servizio.  Assicurarsi che i team di rete siano a conoscenza di questa sequenza temporale e di includerla nei cicli di pianificazione.

Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:

* **A**: Whitelist della rete di [Office 365 Government](mailto:o365gwlt@microsoft.com)
* **Da**: un amministratore tenant: il messaggio di posta elettronica di **invio deve corrispondere** a un contatto amministratore globale nel tenant
* **Oggetto della** posta elettronica : Richiesta di rete elevata di Office 365 GCC - contoso.onmicrosoft.us (sostituire questo con il nome del tenant)

Il corpo del messaggio deve includere i dati seguenti:

* Nome Microsoft Online Services tenant (ad esempio, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Una lista di distribuzione di posta elettronica con cui Microsoft comunicherà per le comunicazioni in corso relative a modifiche di rete e/o follow-up per subnet non valide
* Indicare se si prevede di usare la coesistenza ibrida di Microsoft Teams con le distribuzioni locali
* URL accessibile esternamente dal sistema di identità federata (ad esempio sts.contoso.com) e intervallo di indirizzi IP nella notazione CIDR (ad esempio 10.1.1.0/28)
* URL e intervallo di indirizzi IP dell'elenco di revoche di certificati PKI locali nella notazione CIDR
* URL e intervallo di indirizzi IP accessibili esternamente Exchange Server distribuzione locale nella notazione CIDR
* URL e intervallo di indirizzi IP accessibili esternamente per la distribuzione locale di Skype for Business nella notazione CIDR

Per motivi di sicurezza e conformità, tenere presenti le restrizioni seguenti per la richiesta:

* Esiste una limitazione di quattro subnet per tenant
* Le subnet devono essere in notazione CIDR (ad esempio 10.1.1.0/28)
* Gli intervalli di subnet non possono essere superiori /24
* Non **è possibile** soddisfare le richieste per consentire l'accesso a servizi cloud commerciali (Office 365 commerciale, Google G-Suite, Amazon Web Services e così via)

Dopo che la richiesta è stata ricevuta e approvata da Microsoft, è previsto un contratto di servizio di tre settimane per l'implementazione e non può essere accelerato.  Riceverai un riconoscimento iniziale quando abbiamo ricevuto la richiesta e una conferma finale una volta completata.
