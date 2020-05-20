---
title: Inviare messaggi di posta elettronica crittografati
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come inviare messaggi di posta elettronica crittografati tramite Outlook.
ms.openlocfilehash: 5318fbe045c909e3b7f81d195a8e6b4d5eb96dc1
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322148"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Crittografare o contrassegnare il messaggio di posta elettronica sensibile

I dati e le informazioni sulla campagna sono importanti e spesso riservati. Proteggi queste informazioni riservate mediante la crittografia e le etichette di riservatezza affinché tu e i destinatari di posta elettronica trattiate le informazioni con la sensibilità necessaria.


## <a name="best-practices"></a>Procedure consigliate

Prima di inviare messaggi di posta elettronica con informazioni riservate o sensibili, prendere in considerazione l'attivazione:

- **Crittografia:** È possibile crittografare il messaggio di posta elettronica per proteggere la privacy delle informazioni contenute nel messaggio di posta elettronica. Quando si crittografa un messaggio di posta elettronica, viene convertito dal testo normale leggibile al testo cifrato criptato. Solo il destinatario che ha la chiave privata corrispondente alla chiave pubblica utilizzata per crittografare il messaggio può decifrare il messaggio per la lettura. Qualsiasi destinatario senza la chiave privata corrispondente, tuttavia, Visualizza testo indecifrabile. L'amministratore può definire regole per la crittografia automatica dei messaggi che soddisfano determinati criteri. Ad esempio, l'amministratore può creare una regola che consente di crittografare tutti i messaggi inviati all'esterno dell'organizzazione o tutti i messaggi che citano parole o frasi specifiche. Tutte le regole di crittografia verranno applicate automaticamente.
- **Etichette di riservatezza:** La campagna può anche configurare le etichette di riservatezza che è possibile applicare ai file e ai messaggi di posta elettronica per mantenerli conformi ai criteri di protezione delle informazioni della campagna. Quando si imposta un'etichetta, l'etichetta viene mantenuta con l'indirizzo di posta elettronica, anche quando viene inviata, ad esempio, come intestazione del messaggio.

![Diagramma di un messaggio di posta elettronica con callout per le etichette e la crittografia](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Configurazione

Se si desidera crittografare un messaggio che non soddisfa una regola predefinita o che l'amministratore non ha impostato regole, è possibile applicare una serie di regole di crittografia diverse prima di inviare il messaggio. Per inviare un messaggio crittografato da Outlook 2013 o 2016 o Outlook 2016 per Mac, selezionare **opzioni > autorizzazioni**, quindi selezionare l'opzione di protezione necessaria. È anche possibile inviare un messaggio crittografato selezionando il pulsante **Proteggi** in Outlook sul Web. Per ulteriori informazioni, vedere [inviare, visualizzare e rispondere a messaggi crittografati in Outlook per PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Impostazioni di amministratore

È possibile ottenere informazioni su come configurare la crittografia della posta elettronica alla [crittografia della posta elettronica in Office 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).

### <a name="automatically-encrypt-email-messages"></a>Crittografia automatica dei messaggi di posta elettronica

Gli amministratori possono creare regole del flusso di posta per proteggere automaticamente i messaggi di posta elettronica inviati e ricevuti dalla propria campagna. Configurare le regole per crittografare i messaggi di posta elettronica in uscita e rimuovere la crittografia dai messaggi crittografati provenienti dall'interno dell'organizzazione o dalle risposte ai messaggi crittografati inviati dall'organizzazione. 

È possibile creare regole del flusso di posta per crittografare i messaggi di posta elettronica con le nuove funzionalità di crittografia dei messaggi di Office 365. Definire le regole del flusso di posta per l'attivazione della crittografia dei messaggi con le nuove funzionalità OME utilizzando l'interfaccia di amministrazione di Exchange (EAC). 

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, accedere a Office 365. 
2. Scegliere il riquadro amministratore. 
3. Nell'interfaccia di amministrazione scegliere **admin centers > Exchange**. 

Per ulteriori informazioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

### <a name="brand-your-encryption-messages"></a>Personalizzare i messaggi di crittografia

È anche possibile applicare la personalizzazione della campagna per personalizzare l'aspetto e il testo nei messaggi di posta elettronica. Per ulteriori informazioni, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).

