---
title: Impostare una data di scadenza per un'e-mail crittografata da Office 365 Advanced Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Usare la crittografia avanzata dei messaggi di Office 365 per estendere la sicurezza della posta elettronica impostando una data di scadenza per i messaggi di posta elettronica tramite un modello personalizzato.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e929ce1d948a83a98cca6fa35a65b80a2fc9ef15
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818689"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Impostare una data di scadenza per un'e-mail crittografata da Office 365 Advanced Message Encryption

La crittografia avanzata dei messaggi di Office 365 è inclusa in [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (nonprofit staff pricing), Office 365 Enterprise E5 (nonprofit staff pricing) e Office 365 Education a5. Se l'organizzazione dispone di un abbonamento che non include la crittografia dei messaggi avanzata di Office 365, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o il componente aggiuntivo Office 365 Advanced Compliance SKU per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o Office 365 SKU.

È possibile utilizzare la scadenza dei messaggi nei messaggi di posta elettronica inviati dagli utenti ai destinatari esterni che utilizzano il portale OME per accedere ai messaggi di posta elettronica crittografati. È possibile forzare i destinatari a utilizzare il portale OME per visualizzare e rispondere ai messaggi di posta elettronica crittografati inviati dall'organizzazione utilizzando un modello personalizzato che specifichi una data di scadenza in Windows PowerShell.

In qualità di amministratore globale di O365, quando si applica il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione, è anche possibile specificare una scadenza per i messaggi di posta elettronica. Grazie alla crittografia avanzata dei messaggi di Office 365, è possibile creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione. Se si utilizza un modello, è possibile controllare la durata di accesso dei destinatari alla posta inviata dagli utenti.

Quando un utente finale riceve la posta con un set di date di scadenza, l'utente Visualizza la data di scadenza nel messaggio di posta elettronica del wrapper. Se un utente tenta di aprire un messaggio di posta elettronica scaduto, viene visualizzato un messaggio di errore nel portale OME.

È possibile impostare le date di scadenza solo per i messaggi di posta elettronica a destinatari esterni.

Con la crittografia avanzata dei messaggi di Office 365, ogni volta che si applica il marchio personalizzato, Office 365 applica il wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello. Inoltre, è possibile utilizzare la scadenza solo se si utilizza il marchio personalizzato.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Creare un modello di personalizzazione personalizzato per forzare la scadenza della posta tramite PowerShell

1. [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) con un account che disponga delle autorizzazioni di amministratore globale nell'organizzazione.

2. Eseguire il cmdlet New-OMEConfiguration.

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

Dove:

- `Identity`è il nome del modello personalizzato.

- `ExternalMailExpiryInDays`identifica il numero di giorni in cui i destinatari possono mantenere la posta prima della scadenza. È possibile utilizzare qualsiasi valore compreso tra 1 e 730 giorni.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md)

- [Descrizione del servizio criteri di conformità e del messaggio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
