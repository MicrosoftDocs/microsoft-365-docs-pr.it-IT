---
title: Crittografia dei messaggi
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come inviare e ricevere messaggi di posta elettronica crittografati tra persone interne ed esterne all'organizzazione.
ms.openlocfilehash: f601618c3ad44361794720852b391949901122f2
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709622"
---
# <a name="message-encryption"></a>Crittografia dei messaggi

Spesso si utilizza la posta elettronica per scambiare informazioni riservate, come ad esempio dati finanziari, contratti legali, informazioni riservate di prodotto, rapporti e proiezioni sulle vendite, informazioni sulla salute dei pazienti o informazioni relative ai clienti e agli impiegati. Di conseguenza, le cassette postali possono diventare archivi di grandi quantità di informazioni potenzialmente riservate e la fuga di informazioni può diventare una seria minaccia per l'organizzazione.

Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra persone interne ed esterne all'organizzazione. La crittografia dei messaggi di Office 365 funziona con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica garantisce che solo i destinatari previsti possano visualizzare il contenuto del messaggio.

## <a name="how-office-365-message-encryption-works"></a>Funzionamento della crittografia dei messaggi di Office 365

Il resto di questo articolo si applica alle nuove funzionalità di OME.

Crittografia messaggi di Office 365 è un servizio online basato su Microsoft Azure Rights Management (Azure RMS) che fa parte di Azure Information Protection. Sono inclusi i criteri di crittografia, identità e autorizzazione per proteggere la posta elettronica. È possibile crittografare i messaggi utilizzando i modelli di rights management, [l'opzione Non](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)inoltrare e l'opzione [solo crittografia.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

Gli utenti possono quindi crittografare i messaggi di posta elettronica e diversi allegati utilizzando queste opzioni. Per un elenco completo dei tipi di allegati supportati, vedere "Tipi di file coperti dai criteri IRM quando sono allegati ai [messaggi" in Introduzione a IRM](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)per i messaggi di posta elettronica.

Gli amministratori possono inoltre definire le regole del flusso di posta per applicare questa protezione. Ad esempio, è possibile creare una regola che richiede la crittografia di tutti i messaggi indirizzati a un destinatario specifico o che contiene parole specifiche nella riga dell'oggetto e inoltre specificare che i destinatari non possono copiare o stampare il contenuto del messaggio.

A differenza della versione precedente di OME, le nuove funzionalità offrono un'esperienza di mittente unificato indipendentemente dal fatto che si invii posta all'interno dell'organizzazione o a destinatari esterni a Microsoft 365. Inoltre, i destinatari che ricevono un messaggio di posta elettronica protetto inviato a un account di Microsoft 365 in Outlook 2016 o Outlook sul Web, non devono eseguire ulteriori azioni per visualizzare il messaggio. Funziona senza problemi. Anche i destinatari che utilizzano altri client di posta elettronica e provider di servizi di posta elettronica hanno un'esperienza migliorata. Per informazioni, vedere [Informazioni sui messaggi protetti in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) e Come aprire un messaggio [protetto.](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)

Per un elenco dettagliato delle differenze tra la versione precedente di OME e le nuove funzionalità di [OME, vedere Confrontare le versioni di OME.](ome-version-comparison.md)

Quando un utente invia un messaggio di posta elettronica che corrisponde a una regola del flusso di posta elettronica di crittografia, il messaggio viene crittografato prima di essere inviato. Tutti gli utenti finali di Microsoft 365 che utilizzano i client Outlook per leggere la posta ricevono esperienze di lettura native di prima classe per la posta crittografata e protetta da diritti, anche se non fanno parte della stessa organizzazione del mittente. I client Outlook supportati includono Outlook desktop, Outlook Mac, Outlook mobile su iOS e Android e Outlook sul Web (in precedenza noto come Outlook Web App).

I destinatari dei messaggi crittografati che ricevono posta crittografata o protetta da diritti inviati ai propri account Outlook.com, Gmail e Yahoo ricevono un messaggio wrapper che li indirizza al portale OME, dove possono eseguire facilmente l'autenticazione con un account Microsoft, le credenziali Gmail o Yahoo.

Gli utenti finali che leggono la posta crittografata o protetta da diritti su client diversi da Outlook utilizzano anche il portale OME per visualizzare i messaggi crittografati e protetti da diritti ricevuti.

Se il mittente della posta protetta si trova in GCC High e il destinatario si trova all'esterno di GCC High, inclusi utenti commerciali, utenti di Outlook.com e utenti di altri provider di posta elettronica come Gmail, il destinatario riceve un messaggio wrapper. La posta wrapper indirizza il destinatario al portale OME, dove il destinatario è in grado di leggere e rispondere al messaggio. In caso contrario, se il mittente e il destinatario sono entrambi nell'ambiente GCC High, anche se non fanno parte della stessa organizzazione, i destinatari che utilizzano i client Outlook per leggere la posta ricevono esperienze di lettura native di prima classe per la posta crittografata e protetta da diritti. Per altre informazioni sulle diverse esperienze in GCC High, vedi [Confrontare le versioni di OME.](ome-version-comparison.md)

Per ulteriori informazioni sui limiti di dimensione per i messaggi e gli allegati che è possibile crittografare utilizzando OME, vedere [Limiti di Exchange Online.](https://technet.microsoft.com/library/exchange-online-limits.aspx)

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Funzionamento di Office 365 Advanced Message Encryption in OME

Crittografia avanzata dei messaggi di Office 365 consente di creare più modelli di personalizzazione in modo da ottimizzare il controllo sulla posta del destinatario e creare esperienze di personalizzazione personalizzate per supportare una struttura organizzativa diversificata.

Crittografia avanzata dei messaggi in Microsoft 365 consente di soddisfare gli obblighi di conformità che richiedono un controllo più flessibile sull'accesso dei destinatari esterni ai messaggi di posta elettronica crittografati. Con Advanced Message Encryption in Office 365, in quanto amministratore, è possibile controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che rilevano tipi di informazioni riservate (ad esempio, INFORMAZIONI PERSONALI, ID finanziari o sanitari) o parole chiave per migliorare la protezione tramite la scadenza dell'accesso tramite un portale Web sicuro ai messaggi di posta elettronica crittografati. Gli amministratori possono controllare ulteriormente i messaggi di posta elettronica crittografati a cui si accede tramite un portale Web di Microsoft 365 revocando l'accesso a un messaggio di posta elettronica in qualsiasi momento.

La revoca e la scadenza dei messaggi funzionano solo per i messaggi di posta elettronica inviati dagli utenti a destinatari esterni all'organizzazione. Inoltre, i destinatari devono accedere alla posta elettronica tramite il portale Web. Per assicurarsi che il destinatario utilizzi il portale per ricevere posta elettronica, configurare un modello di personalizzazione personalizzato che applica il wrapper. Quindi, applicare il modello di personalizzazione in una regola del flusso di posta. Per ulteriori informazioni sulla crittografia avanzata dei messaggi, vedere [Office 365 Advanced Message Encryption.](ome-advanced-message-encryption.md)

## <a name="defining-rules-for-office-365-message-encryption"></a>Regole di definizione per la crittografia dei messaggi di Office 365

Un modo per abilitare le nuove funzionalità per la crittografia dei messaggi di Office 365 è consentire agli amministratori di Exchange Online e Exchange Online Protection di definire le regole del flusso di posta. Queste regole determinano in quali condizioni i messaggi di posta elettronica devono essere crittografati. Quando viene impostata un'azione di crittografia per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati prima di essere inviati.

Le regole del flusso di posta sono flessibili, consentendo di combinare le condizioni in modo da soddisfare requisiti di sicurezza specifici in un'unica regola. Ad esempio, è possibile creare una regola per crittografare tutti i messaggi che contengono parole chiave specificate e indirizzati a destinatari esterni. Le nuove funzionalità per la crittografia dei messaggi di Office 365 crittografano anche le risposte dei destinatari di posta elettronica crittografata.

Per ulteriori informazioni su come creare regole del flusso di posta per sfruttare le nuove funzionalità di OME, vedere [Define Rules for Office 365 Message Encryption.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-the-new-ome-capabilities"></a>Introduzione alle nuove funzionalità di OME

Se si è pronti per iniziare a usare le nuove funzionalità di OME all'interno dell'organizzazione, vedere Configurare le nuove funzionalità di crittografia dei messaggi di [Office 365.](set-up-new-message-encryption-capabilities.md)

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Invio, risposta e visualizzazione di messaggi di posta elettronica crittografati

Con la crittografia dei messaggi di Office 365, gli utenti possono inviare messaggi di posta elettronica crittografati da Outlook e Outlook sul Web. Inoltre, gli amministratori possono configurare le regole del flusso di posta in Microsoft 365 per crittografare automaticamente i messaggi di posta elettronica in base alla corrispondenza delle parole chiave o ad altre condizioni.

I destinatari dei messaggi crittografati presenti nelle organizzazioni potranno leggere tali messaggi facilmente in qualsiasi versione di Outlook, tra cui Outlook per PC, Outlook per Mac, Outlook sul Web, Outlook per iOS e Outlook per Android. Gli utenti che ricevono messaggi crittografati su altri client di posta elettronica possono visualizzare i messaggi nel portale OME.

Per istruzioni dettagliate su come inviare e visualizzare i messaggi crittografati, vedere questi articoli.

|Leggi questo articolo...|In caso di...|
|:-----|:-----|
|[Informazioni sui messaggi protetti in Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Un utente finale che desidera ulteriori informazioni sul funzionamento dei messaggi crittografati e sulle opzioni disponibili.|
|[Come si apre un messaggio protetto?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Un utente finale che desidera leggere un messaggio protetto inviato all'utente. Questo articolo include informazioni sulla lettura dei messaggi in diverse versioni di Outlook e da diversi account di posta elettronica, inclusi gli account esterni a Microsoft 365, ad esempio gmail e Yahoo! account.|
|[Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Un utente finale che desidera inviare, visualizzare o rispondere a un messaggio crittografato da Outlook. Anche se non si è membri di un'organizzazione, si riceve comunque la notifica dei messaggi crittografati inviati in Outlook. Usare questo articolo per istruzioni su come visualizzare e rispondere ai messaggi crittografati inviati da Office 365.|
|[Inviare un messaggio con firma digitale o crittografato](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Un utente finale che desidera inviare, visualizzare o rispondere ai messaggi crittografati utilizzando Outlook per Mac. In questo articolo viene inoltre illustrato l'utilizzo di metodi di crittografia diversi da OME, ad esempio S/MIME.|
|[Visualizzare i messaggi crittografati nel dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Un utente finale che ha ricevuto un messaggio crittografato con crittografia dei messaggi di Office 365 nel dispositivo Android, è possibile utilizzare l'app OME Viewer gratuita per visualizzare il messaggio e inviare una risposta crittografata. Questo articolo spiega come.|
|[Visualizzare i messaggi crittografati su iPhone o iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Un utente finale che ha ricevuto un messaggio crittografato con Crittografia messaggi di Office 365 su iPhone o iPad, è possibile utilizzare l'app OME Viewer gratuita per visualizzare il messaggio e inviare una risposta crittografata. Questo articolo spiega come.|
||
