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
description: Usa Office 365 Advanced Message Encryption per estendere la sicurezza della posta elettronica impostando una data di scadenza per i messaggi di posta elettronica tramite un modello personalizzato personalizzato.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927786"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Impostare una data di scadenza per un'e-mail crittografata da Office 365 Advanced Message Encryption

Office 365 Advanced Message Encryption è incluso in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Noprofit Staff Pricing), Office 365 Enterprise E5 (Noprofit Staff Pricing) e Office 365 Education A5. Se l'organizzazione dispone di una sottoscrizione che non include Office 365 Advanced Message Encryption, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3, Microsoft 365 E3 (Prezzi del personale nonprofit) o con il componente aggiuntivo SKU Office 365 Advanced Compliance per Microsoft 365 E3, Microsoft 365 E3 (Prezzi del personale nonprofit) o SKU Office 365.

È possibile utilizzare la scadenza dei messaggi nei messaggi di posta elettronica inviati dagli utenti a destinatari esterni che utilizzano il portale OME per accedere ai messaggi di posta elettronica crittografati. È possibile forzare i destinatari a utilizzare il portale OME per visualizzare e rispondere ai messaggi di posta elettronica crittografati inviati dall'organizzazione utilizzando un modello personalizzato personalizzato che specifica una data di scadenza in Windows PowerShell.

Come amministratore Office 365 globale, quando si applica il marchio aziendale per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione, è anche possibile specificare una scadenza per questi messaggi di posta elettronica. Con Office 365 Advanced Message Encryption, è possibile creare più modelli per i messaggi di posta elettronica crittografati che hanno origine dall'organizzazione. Utilizzando un modello, è possibile controllare per quanto tempo i destinatari hanno accesso alla posta inviata dagli utenti.

Quando un utente finale riceve la posta con una data di scadenza impostata, l'utente visualizza la data di scadenza nel messaggio di posta elettronica wrapper. Se un utente tenta di aprire un messaggio di posta scaduto, viene visualizzato un errore nel portale OME.

È possibile impostare solo date di scadenza per i messaggi di posta elettronica a destinatari esterni.

Con Office 365 Advanced Message Encryption, ogni volta che si applica la personalizzazione, il Office 365 applica il wrapper alla posta elettronica che si adatta alla regola del flusso di posta a cui si applica il modello. Inoltre, puoi usare la scadenza solo se usi la personalizzazione.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Creare un modello di personalizzazione personalizzato per forzare la scadenza della posta tramite PowerShell

1. [Connessione per Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) con un account con autorizzazioni di amministratore globale nell'organizzazione.

2. Eseguire il cmdlet New-OMEConfiguration.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Dove:

- `Identity` è il nome del modello personalizzato.

- `ExternalMailExpiryInDays` identifica il numero di giorni in cui i destinatari possono conservare la posta prima della scadenza. È possibile utilizzare qualsiasi valore compreso tra 1 e 730 giorni.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Ulteriori informazioni su Office 365 Advanced Message Encryption

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md)

- [Criteri dei messaggi e descrizione del servizio di conformità](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)