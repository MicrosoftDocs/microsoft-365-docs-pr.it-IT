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
description: 'Riepilogo: Office 365 GCC high e DoD hanno requisiti di sicurezza di rete aggiuntivi'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926560"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Altri requisiti di sicurezza della rete per Office 365 GCC High e DoD

*Questo articolo si applica Office 365 GCC high, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*

Office 365 GCC High e DOD sono ambienti cloud sicuri per soddisfare le esigenze del governo degli Stati Uniti e dei suoi fornitori e appaltatori.  Questi ambienti cloud hanno restrizioni di rete aggiuntive a cui gli endpoint esterni a cui i servizi possono accedere.

GCC I clienti high e DOD che pianificano di utilizzare le identità federate o la coesistenza ibrida potrebbero richiedere a Microsoft di consentire l'accesso in ingresso e/o in uscita alle distribuzioni locali esistenti.  Esempi di queste attività sono:

* Utilizzo di identità federate (con Active Directory Federation Services o un servizio token di sicurezza supportato simile)
* Coesistenza ibrida con una distribuzione locale Exchange Server o Skype for Business locale
* Migrazione del contenuto utente esistente da un sistema locale

Per consentire al servizio di comunicare con gli  endpoint locali, è necessario inviare un messaggio di posta elettronica Office 365 progettazione per le modifiche di rete.

> [!WARNING]
> Tutte le richieste hanno **un** contratto di servizio di tre settimane e non possono essere accelerate a causa dei controlli di sicurezza e conformità necessari e delle pipeline di distribuzione.  Sono incluse le richieste di rete di onboarding iniziali e le eventuali modifiche dopo la migrazione al servizio.  Assicurati che i team di rete siano a conoscenza di questa sequenza temporale e la includano nei cicli di pianificazione.

Invia un messaggio di posta [elettronica Office 365 Government Allow-List richieste](mailto:o365gwlt@microsoft.com) con le informazioni seguenti:

* **A**: [Office 365 Government Allow-List richieste](mailto:o365gwlt@microsoft.com)
* **Da**: un amministratore tenant: il messaggio di posta **elettronica di invio deve** corrispondere a un contatto amministratore globale nel tenant
* **Oggetto di** posta elettronica : Office 365 GCC high network request - contoso.onmicrosoft.us (sostituire con il nome del tenant)

Il corpo del messaggio deve includere i dati seguenti:

* Nome Microsoft Online Services tenant (ad esempio, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Una lista di distribuzione di posta elettronica con cui Microsoft comunicherà per le comunicazioni in corso relative alle modifiche di rete e/o al follow-up per subnet non valide
* Indicare se si prevede di usare Microsoft Teams coesistenza ibrida con le distribuzioni locali
* URL accessibile esternamente dal sistema di identità federata (ad esempio, sts.contoso.com) e intervallo di indirizzi IP nella notazione CIDR (ad esempio, . 10.1.1.0/28)
* URL e intervallo di indirizzi IP dell'elenco di revoche di certificati PKI locali nella notazione CIDR
* URL e intervallo di indirizzi IP accessibili esternamente Exchange Server distribuzione locale nella notazione CIDR
* URL e intervallo di indirizzi IP accessibili esternamente Skype for Business distribuzione locale nella notazione CIDR

Per motivi di sicurezza e conformità, tenere presenti le restrizioni seguenti per la richiesta:

* Esiste una limitazione di quattro subnet per tenant
* Le subnet devono essere in notazione CIDR (ad esempio, 10.1.1.0/28)
* Gli intervalli di subnet non possono essere superiori a /24
* Non **è possibile** soddisfare le richieste per consentire l'accesso ai servizi cloud commerciali (Office 365, Google G-Suite, Amazon Web Services e così via)

Dopo che la richiesta è stata ricevuta e approvata da Microsoft, è previsto un contratto di servizio di tre settimane per l'implementazione e non può essere accelerato.  Riceverai un riconoscimento iniziale quando abbiamo ricevuto la richiesta e un riconoscimento finale una volta completata.
