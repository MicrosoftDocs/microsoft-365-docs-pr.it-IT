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

La crittografia avanzata dei messaggi di Office 365 è inclusa in [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (nonprofit staff pricing), Office 365 Enterprise E5 (nonprofit staff pricing) e Office 365 Education a5. Se l'organizzazione dispone di un abbonamento che non include la crittografia dei messaggi avanzata di Office 365, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3. Microsoft 365 E3 (pricing staff no profit) o il componente aggiuntivo SKU di Office 365 Advanced Compliance per Microsoft 365 E3, Microsoft 365 E3 (pricing staff no profit), SKU di Office 365 o il componente aggiuntivo Microsoft 365 E5/A5 Information Protection and Governance SKU per Microsoft 365 A3/E3.

Crittografia avanzata dei messaggi consente ai clienti di soddisfare gli obblighi di conformità che richiedono controlli più flessibili su destinatari esterni e l'accesso ai messaggi di posta elettronica crittografati. Con la crittografia avanzata dei messaggi in Office 365, è possibile controllare i messaggi di posta elettronica riservati condivisi all'esterno dell'organizzazione con criteri automatici. Questi criteri possono essere configurati per identificare tipi di informazioni riservate, ad esempio i dati personali, finanziari o di integrità, oppure è possibile utilizzare parole chiave per migliorare la protezione. Dopo aver configurato i criteri, è necessario associare i criteri ai modelli di posta elettronica personalizzati e quindi aggiungere una data di scadenza per il controllo supplementare dei messaggi di posta elettronica che soddisfano i criteri. Gli amministratori possono inoltre controllare ulteriori messaggi di posta elettronica crittografati accessibili esternamente tramite un portale web sicuro, revocando l'accesso alla posta in qualsiasi momento.

È possibile revocare e impostare solo una data di scadenza per i messaggi di posta elettronica inviati a destinatari esterni.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Iniziare a usare la crittografia avanzata dei messaggi di Office 365

Negli articoli seguenti viene descritto come configurare e utilizzare la crittografia avanzata dei messaggi.

L'organizzazione deve disporre di un abbonamento che include la crittografia avanzata dei messaggi di Office 365. Per informazioni dettagliate sulle sottoscrizioni supportate, vedere [Message Policy and Compliance Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Se non è già stata configurata la crittografia dei messaggi di Office 365, vedere [configurare le nuove funzionalità di crittografia dei messaggi di office 365](set-up-new-message-encryption-capabilities.md).

Con la crittografia avanzata dei messaggi non si è limitati a un singolo modello di branding. In alternativa, è possibile creare e utilizzare modelli di branding multipli. Per informazioni, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).

[Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](ome-advanced-expiration.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che migliorano la protezione, in scadenza l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati

[Revocare la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](revoke-ome-encrypted-mail.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione e migliorare la protezione revocando l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati.  

Con la crittografia avanzata dei messaggi di Office 365, ogni volta che si applica un modello di personalizzazione personalizzato, Microsoft applica un wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello. È possibile revocare solo i messaggi e applicare le date di scadenza ai messaggi che gli utenti ricevono tramite il portale. In altre parole, il messaggio di posta elettronica con un modello di personalizzazione personalizzato è stato applicato. Per ulteriori informazioni e un esempio, vedere le linee guida per [assicurarsi che tutti i destinatari esterni utilizzino il portale ome per leggere la posta crittografata](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).
