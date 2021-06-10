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
description: Crittografia avanzata dei messaggi consente alle organizzazioni di soddisfare i propri obblighi di conformità consentendo agli amministratori di fare ancora di più con i messaggi protetti.
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923956"
---
# <a name="advanced-message-encryption"></a>Crittografia avanzata dei messaggi

Office 365 Advanced Message Encryption è incluso in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Noprofit Staff Pricing), Office 365 Enterprise E5 (Noprofit Staff Pricing) e Office 365 Education A5. Se l'organizzazione dispone di una sottoscrizione che non include Office 365 Advanced Message Encryption, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3, Microsoft 365 E3 (Prezzi del personale nonprofit) o con il componente aggiuntivo SKU Office 365 Advanced Compliance per Microsoft 365 E3, Microsoft 365 E3 (prezzi del personale nonprofit), SKU Office 365 o il componente aggiuntivo SKU Microsoft 365 E5/A5 Information Protection and Governance per Microsoft 365 A3/E3.

La crittografia avanzata dei messaggi consente ai clienti di soddisfare gli obblighi di conformità che richiedono controlli più flessibili sui destinatari esterni e sul loro accesso ai messaggi di posta elettronica crittografati. Con crittografia avanzata dei messaggi in Office 365, è possibile controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici. È possibile configurare questi criteri per identificare i tipi di informazioni riservate, ad esempio INFORMAZIONI personali, dati finanziari o ID integrità, oppure è possibile utilizzare parole chiave per migliorare la protezione. Dopo aver configurato i criteri, associare i criteri ai modelli di posta elettronica personalizzati personalizzati e quindi aggiungere una data di scadenza per un controllo aggiuntivo dei messaggi di posta elettronica che si adattano al criterio. Inoltre, gli amministratori possono controllare ulteriormente i messaggi di posta elettronica crittografati a cui si accede esternamente tramite un portale Web sicuro revocando l'accesso alla posta in qualsiasi momento.

È possibile solo revocare e impostare una data di scadenza per i messaggi di posta elettronica inviati a destinatari esterni.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Introduzione a Office 365 Advanced Message Encryption

Gli articoli seguenti descrivono come configurare e utilizzare la crittografia avanzata dei messaggi.

L'organizzazione deve disporre di una sottoscrizione che includa Office 365 Advanced Message Encryption. Per informazioni dettagliate sulle sottoscrizioni supportate, vedere la descrizione dei criteri dei messaggi [e del servizio di conformità.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

Se non è già stata Office 365 Message Encryption, vedere Configurare nuove Office 365 Message Encryption [funzionalità.](set-up-new-message-encryption-capabilities.md)

Con La crittografia avanzata dei messaggi non sei limitato a un singolo modello di personalizzazione. Puoi invece creare e usare più modelli di personalizzazione. Per informazioni, vedere [Aggiungere il marchio dell'organizzazione ai messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)

[Impostare una data di scadenza per la posta elettronica crittografata da Office 365 Advanced Message Encryption](ome-advanced-expiration.md). Controlla i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che migliorano la protezione con la scadenza dell'accesso tramite un portale Web sicuro ai messaggi di posta elettronica crittografati.

[Revocare la posta elettronica crittografata da Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md). Controlla i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione e migliora la protezione revocando l'accesso tramite un portale Web sicuro ai messaggi di posta elettronica crittografati.  

Con Office 365 Advanced Message Encryption, ogni volta che si applica un modello di personalizzazione personalizzato, Microsoft applica un wrapper alla posta elettronica che si adatta alla regola del flusso di posta a cui si applica il modello. È possibile revocare i messaggi e applicare date di scadenza solo ai messaggi ricevuti dagli utenti tramite il portale. In altre parole, i messaggi di posta elettronica a cui è applicato un modello di personalizzazione. Per ulteriori informazioni e un esempio, vedere le linee guida in [Ensure all external recipients use the OME Portal to read encrypted mail](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).