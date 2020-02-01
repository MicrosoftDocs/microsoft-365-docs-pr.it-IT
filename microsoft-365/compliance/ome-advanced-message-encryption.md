---
title: Office 365 Advanced Message Encryption
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
description: La crittografia avanzata dei messaggi in Office 365 consente alle organizzazioni di soddisfare i propri obblighi di conformità consentendo agli amministratori di fare ancora di più con i messaggi protetti.
ms.openlocfilehash: 580803d7b15608ebb0852896cdbd9a43ee5a2ff4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601803"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption

La crittografia avanzata dei messaggi di Office 365 è inclusa in [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (nonprofit staff pricing), Office 365 Enterprise E5 (nonprofit staff pricing) e Office 365 Education a5. Se l'organizzazione dispone di un abbonamento che non include la crittografia dei messaggi avanzata di Office 365, è possibile acquistarla con il componente aggiuntivo Microsoft 365 E5 Compliance SKU per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o Office 365 Advanced Componente aggiuntivo SKU di conformità per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o SKU di Office 365.

La crittografia avanzata dei messaggi in Office 365 consente ai clienti di soddisfare gli obblighi di conformità che richiedono controlli più flessibili su destinatari esterni e l'accesso ai messaggi di posta elettronica crittografati. Con la crittografia avanzata dei messaggi in Office 365, è possibile controllare i messaggi di posta elettronica riservati condivisi all'esterno dell'organizzazione con criteri automatici. Questi criteri possono essere configurati per identificare tipi di informazioni riservate, ad esempio i dati personali, finanziari o di integrità, oppure è possibile utilizzare parole chiave per migliorare la protezione. Dopo aver configurato i criteri, è necessario associare i criteri ai modelli di posta elettronica personalizzati e quindi aggiungere una data di scadenza per il controllo supplementare dei messaggi di posta elettronica che soddisfano i criteri. Gli amministratori possono inoltre controllare ulteriori messaggi di posta elettronica crittografati accessibili esternamente tramite un portale web sicuro, revocando l'accesso alla posta in qualsiasi momento.

È possibile revocare e impostare solo una data di scadenza per i messaggi di posta elettronica inviati a destinatari esterni.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Iniziare a usare la crittografia avanzata dei messaggi di Office 365

Negli articoli seguenti viene descritto come configurare e utilizzare la crittografia avanzata dei messaggi.

L'organizzazione deve disporre di un abbonamento che include la crittografia avanzata dei messaggi di Office 365. Per informazioni dettagliate sulle sottoscrizioni supportate, vedere [Message Policy and Compliance Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Se non è già stata configurata la crittografia dei messaggi di Office 365, vedere [configurare le nuove funzionalità di crittografia dei messaggi di office 365](set-up-new-message-encryption-capabilities.md).

Con la crittografia avanzata dei messaggi non si è limitati a un singolo modello di branding. In alternativa, è possibile creare e utilizzare modelli di branding multipli. Per informazioni, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).

[Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](ome-advanced-expiration.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che migliorano la protezione, in scadenza l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati

[Revocare la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](revoke-ome-encrypted-mail.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione e migliorare la protezione revocando l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati.  

Con la crittografia avanzata dei messaggi di Office 365, ogni volta che si applica un modello di personalizzazione personalizzato, Office 365 applica un wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello. È possibile revocare solo i messaggi e applicare le date di scadenza ai messaggi che gli utenti ricevono tramite il portale. In altre parole, il messaggio di posta elettronica con un modello di personalizzazione personalizzato è stato applicato. Per ulteriori informazioni e un esempio, vedere le linee guida per [garantire che tutti i destinatari esterni utilizzino il portale ome per leggere la posta crittografata, solo la crittografia avanzata dei messaggi di Office 365](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only).
