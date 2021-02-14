---
title: Crittografia avanzata dei messaggi
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: La crittografia avanzata dei messaggi consente alle organizzazioni di soddisfare i propri obblighi di conformità consentendo agli amministratori di fare ancora di più con i messaggi protetti.
ms.openlocfilehash: 0e28bd283b6a7d1666d5db9b71040d2f377adffe
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626894"
---
# <a name="advanced-message-encryption"></a>Crittografia avanzata dei messaggi

Office 365 Advanced Message Encryption è incluso in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Noprofit Staff Pricing), Office 365 Enterprise E5 (Noprofit Staff Pricing) e Office 365 Education A5. Se l'organizzazione ha un abbonamento che non include Office 365 Advanced Message Encryption, è possibile acquistarlo con il componente aggiuntivo SKU conformità Microsoft 365 E5 per Microsoft 365 E3, Microsoft 365 E3 (Prezzi per il personale no profit) o il componente aggiuntivo Office 365 Advanced Compliance SKU per Microsoft 365 E3, Microsoft 365 E3 (Prezzi del personale no profit), SKU di Office 365 o il componente aggiuntivo Microsoft 365 E5/A5 Information Protection and Governance SKU per Microsoft 365 A3/E3.

Crittografia avanzata dei messaggi consente ai clienti di rispettare gli obblighi di conformità che richiedono controlli più flessibili sui destinatari esterni e il loro accesso ai messaggi di posta elettronica crittografati. Con La crittografia avanzata dei messaggi in Office 365, è possibile controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici. È possibile configurare questi criteri per identificare i tipi di informazioni riservate, ad esempio INFORMAZIONI PERSONALI, DATI FINANZIARI o ID integrità oppure è possibile utilizzare parole chiave per migliorare la protezione. Dopo aver configurato i criteri, è necessario associare i criteri ai modelli di posta elettronica personalizzati personalizzati e quindi aggiungere una data di scadenza per un maggiore controllo dei messaggi di posta elettronica che rientrano nel criterio. Inoltre, gli amministratori possono controllare ulteriormente i messaggi di posta elettronica crittografati a cui si accede esternamente tramite un portale Web sicuro revocando l'accesso alla posta in qualsiasi momento.

È possibile solo revocare e impostare una data di scadenza per i messaggi di posta elettronica inviati a destinatari esterni.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Introduzione alla crittografia avanzata dei messaggi di Office 365

Nei seguenti articoli viene descritto come configurare e utilizzare la crittografia avanzata dei messaggi.

L'organizzazione deve disporre di un abbonamento che includa La crittografia avanzata dei messaggi di Office 365. Per informazioni dettagliate sulle sottoscrizioni supportate, vedere il criterio messaggio e la descrizione [del servizio di conformità.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

Se la crittografia dei messaggi di Office 365 non è già impostata, vedere Configurare le nuove funzionalità di crittografia dei messaggi [di Office 365.](set-up-new-message-encryption-capabilities.md)

Con La crittografia avanzata dei messaggi non si è limitati a un singolo modello di personalizzazione. Puoi invece creare e usare più modelli di personalizzazione. Per informazioni, vedere [Aggiungere il marchio dell'organizzazione ai messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)

[Impostare una data di scadenza per la posta elettronica crittografata da Office 365 Advanced Message Encryption.](ome-advanced-expiration.md) Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che migliorano la protezione tramite un portale Web sicuro per i messaggi di posta elettronica crittografati.

[Revocare la posta elettronica crittografata da Office 365 Advanced Message Encryption.](revoke-ome-encrypted-mail.md) Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione e migliorare la protezione revocando l'accesso tramite un portale Web sicuro ai messaggi di posta elettronica crittografati.  

Con Office 365 Advanced Message Encryption, ogni volta che si applica un modello di personalizzazione, Microsoft applica un wrapper alla posta elettronica che si adatta alla regola del flusso di posta a cui si applica il modello. È possibile revocare i messaggi e applicare le date di scadenza solo ai messaggi ricevuti dagli utenti tramite il portale. In altre parole, i messaggi di posta elettronica a cui è applicato un modello di personalizzazione personalizzato. Per ulteriori informazioni e un esempio, vedere le indicazioni in Verificare che tutti i destinatari esterni utilizzino il [portale OME per leggere la posta crittografata.](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)
