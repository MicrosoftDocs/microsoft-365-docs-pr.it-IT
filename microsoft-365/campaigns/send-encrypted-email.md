---
title: Inviare messaggi di posta elettronica crittografati
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come inviare messaggi di posta elettronica crittografati Outlook.
ms.openlocfilehash: 209734bd52d1d97278d5632f035723758fe2e016
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576974"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Crittografare o etichettare le comunicazioni di posta elettronica sensibili

I dati e le informazioni della campagna sono importanti e spesso riservati. Proteggere queste informazioni riservate utilizzando etichette di crittografia e riservatezza in modo che tu e i destinatari di posta elettronica trattino le informazioni con la riservatezza necessaria.

## <a name="best-practices"></a>Procedure consigliate

Prima di inviare messaggi di posta elettronica con informazioni riservate o riservate, è consigliabile attivare:

- **Crittografia:** È possibile crittografare la posta elettronica per proteggere la privacy delle informazioni contenute nel messaggio di posta elettronica. Quando si crittografa un messaggio di posta elettronica, questo viene convertito da testo normale leggibile in testo crittografato. Solo il destinatario che dispone della chiave privata corrispondente alla chiave pubblica utilizzata per crittografare il messaggio può decifrare il messaggio per la lettura. Qualsiasi destinatario senza la chiave privata corrispondente, tuttavia, visualizza testo indecifrabile. L'amministratore può definire regole per crittografare automaticamente i messaggi che soddisfano determinati criteri. Ad esempio, l'amministratore può creare una regola che crittografa tutti i messaggi inviati all'esterno dell'organizzazione o tutti i messaggi che menzionano parole o frasi specifiche. Tutte le regole di crittografia verranno applicate automaticamente.
- **Etichette di riservatezza:** La campagna può anche configurare etichette di riservatezza che è possibile applicare ai file e ai messaggi di posta elettronica per mantenerli conformi ai criteri di protezione delle informazioni della campagna. Quando si imposta un'etichetta, l'etichetta viene mantenuta con la posta elettronica, anche quando viene inviata, ad esempio come intestazione del messaggio.

![Diagramma di un messaggio di posta elettronica con callout per etichette e crittografia](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Configurazione

Se si desidera crittografare un messaggio che non soddisfa una regola predefinita o se l'amministratore non ha configurato alcuna regola, è possibile applicare diverse regole di crittografia prima di inviare il messaggio. Per inviare un messaggio crittografato da Outlook 2013 o 2016 o Outlook 2016 per Mac, selezionare Opzioni **> Autorizzazioni**, quindi selezionare l'opzione di protezione necessaria. È inoltre possibile inviare un messaggio crittografato selezionando il **pulsante** Proteggi Outlook sul Web. Per ulteriori informazioni, vedere [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Impostazioni amministratore

Per informazioni sulla configurazione della crittografia della posta elettronica, vedere [Crittografia della posta elettronica in Microsoft 365](../compliance/email-encryption.md).

### <a name="automatically-encrypt-email-messages"></a>Crittografare automaticamente i messaggi di posta elettronica

Gli amministratori possono creare regole del flusso di posta per proteggere automaticamente i messaggi di posta elettronica inviati e ricevuti dalla campagna. Configurare le regole per crittografare i messaggi di posta elettronica in uscita e rimuovere la crittografia dai messaggi crittografati provenienti dall'interno dell'organizzazione o dalle risposte ai messaggi crittografati inviati dall'organizzazione.

È possibile creare regole del flusso di posta per crittografare i messaggi di posta elettronica con le nuove funzionalità Office 365 Message Encryption (OME). Definire le regole del flusso di posta per attivare la crittografia dei messaggi con le nuove funzionalità OME tramite Exchange Admin Center (EAC). 

1. In un Web browser, utilizzando un account aziendale o dell'istituto di istruzione a cui sono state concesse autorizzazioni di amministratore globale, accedere.
2. Scegliere il riquadro Amministratore.
3. Nell'interfaccia di amministrazione scegliere **Interfaccia di amministrazione > Exchange**.

Per ulteriori informazioni, vedere Definire le [regole del flusso di posta per crittografare i messaggi di posta elettronica.](../compliance/define-mail-flow-rules-to-encrypt-email.md)

### <a name="brand-your-encryption-messages"></a>Personalizzazione dei messaggi di crittografia

Puoi anche applicare la personalizzazione della campagna per personalizzare l'aspetto e il testo nei messaggi di posta elettronica. Per ulteriori informazioni, vedere [Aggiungere il marchio dell'organizzazione ai messaggi crittografati.](../compliance/email-encryption.md)