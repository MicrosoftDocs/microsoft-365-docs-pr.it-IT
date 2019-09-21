---
title: Office 365 Advanced Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: La crittografia avanzata dei messaggi in Office 365 consente alle organizzazioni di soddisfare gli obblighi di conformità abilitando gli amministratori a scadere e revocare l'accesso tramite un portale Web di Office 365 ai messaggi di posta elettronica crittografati.
ms.openlocfilehash: dcef5f861711acffb8359063373cd90d4b122d88
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084448"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption

La crittografia avanzata dei messaggi di Office 365 è disponibile nella parte superiore della crittografia messaggi di Office 365 in alcuni abbonamenti. La crittografia avanzata dei messaggi è inclusa in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 e Office 365 Education a5. Se nell'organizzazione è presente un abbonamento a Office 365 che non include la crittografia avanzata dei messaggi di Office 365, è possibile acquistare la crittografia avanzata del messaggio come componente aggiuntivo con la conformità E5 della SKU per la conformità avanzata.

La crittografia avanzata dei messaggi in Office 365 consente ai clienti di soddisfare gli obblighi di conformità che richiedono controlli più flessibili su destinatari esterni e l'accesso ai messaggi di posta elettronica crittografati. Con la crittografia avanzata dei messaggi in Office 365, è possibile controllare i messaggi di posta elettronica riservati condivisi all'esterno dell'organizzazione con criteri automatici. Questi criteri possono essere configurati per identificare tipi di informazioni riservate, ad esempio i dati personali, finanziari o di integrità, oppure è possibile utilizzare parole chiave per migliorare la protezione. Dopo aver configurato i criteri, è necessario associare i criteri ai modelli di posta elettronica personalizzati e quindi aggiungere una data di scadenza per il controllo supplementare dei messaggi di posta elettronica che soddisfano i criteri. Gli amministratori possono inoltre controllare ulteriori messaggi di posta elettronica crittografati accessibili esternamente tramite un portale web sicuro, revocando l'accesso alla posta in qualsiasi momento.

È possibile revocare e impostare solo una data di scadenza per i messaggi di posta elettronica inviati a destinatari esterni.

Con la crittografia avanzata dei messaggi di Office 365, ogni volta che si applica un modello di personalizzazione personalizzato, Office 365 applica un wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello. È possibile revocare solo i messaggi e applicare le date di scadenza ai messaggi che gli utenti ricevono tramite il portale. In altre parole, il messaggio di posta elettronica con un modello di personalizzazione personalizzato è stato applicato.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Iniziare a usare la crittografia avanzata dei messaggi di Office 365

Negli argomenti seguenti viene descritto come configurare e utilizzare la crittografia avanzata dei messaggi.

L'organizzazione deve disporre di un abbonamento che include la crittografia avanzata dei messaggi di Office 365. Per informazioni dettagliate sulle sottoscrizioni supportate, vedere [Message Policy and Compliance Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Se non è già stata configurata la crittografia dei messaggi di Office 365, vedere [configurare le nuove funzionalità di crittografia dei messaggi di office 365](set-up-new-message-encryption-capabilities.md).

[Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](ome-advanced-expiration.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che migliorano la protezione, in scadenza l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati

[Revocare la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](revoke-ome-encrypted-mail.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione e migliorare la protezione revocando l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati.  