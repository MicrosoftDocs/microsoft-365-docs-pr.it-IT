---
title: Crittografia dei messaggi di Office 365
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
description: Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti all'interno e all'esterno dell'organizzazione. La crittografia dei messaggi di posta elettronica consente di verificare che solo i destinatari previsti possano visualizzare il contenuto del messaggio.
ms.openlocfilehash: a80086e64c7e7033141fcc84e0cd9145d64a22f6
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862026"
---
# <a name="office-365-message-encryption"></a>Crittografia dei messaggi di Office 365

Spesso si utilizza la posta elettronica per scambiare informazioni riservate, come ad esempio dati finanziari, contratti legali, informazioni riservate di prodotto, rapporti e proiezioni sulle vendite, informazioni sulla salute dei pazienti o informazioni relative ai clienti e agli impiegati. Di conseguenza, le cassette postali possono diventare archivi di grandi quantità di informazioni potenzialmente riservate e la fuga di informazioni può diventare una seria minaccia per l'organizzazione.

Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti all'interno e all'esterno dell'organizzazione. La crittografia dei messaggi di Office 365 è compatibile con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica consente di verificare che solo i destinatari previsti possano visualizzare il contenuto del messaggio.

## <a name="how-office-365-message-encryption-works"></a>Funzionamento della crittografia dei messaggi di Office 365

Il resto di questo articolo si applica alle nuove funzionalità OME.

> [!NOTE]
> I delegati che dispongono di autorizzazioni di accesso completo per una cassetta postale possono leggere i messaggi crittografati inviati alla cassetta postale.

La crittografia dei messaggi di Office 365 è un servizio online basato su Microsoft Azure Rights Management (Azure RMS) che fa parte di Azure Information Protection. Sono inclusi i criteri di crittografia, identità e autorizzazione che consentono di proteggere il messaggio di posta elettronica. È possibile crittografare i messaggi utilizzando i modelli Rights Management, l' [opzione non inoltrare](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)e l' [opzione solo crittografia](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

Gli utenti possono quindi crittografare i messaggi di posta elettronica e una vasta gamma di allegati di Office 365 utilizzando queste opzioni. Per un elenco completo dei tipi di allegati supportati, vedere ["tipi di file coperti da criteri IRM quando sono allegati ai messaggi" in Introduzione a IRM per i messaggi di posta elettronica](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM).

In qualità di amministratore, è anche possibile definire le regole del flusso di posta per applicare la protezione. Ad esempio, è possibile creare una regola che richiede la crittografia di tutti i messaggi indirizzati a un destinatario specifico o che contiene parole specifiche nella riga dell'oggetto e specificare anche che i destinatari non possono copiare o stampare il contenuto del messaggio.

A differenza della versione precedente di OME, le nuove funzionalità forniscono un'esperienza di mittente unificata se si sta inviando posta all'interno dell'organizzazione o ai destinatari esterni a Office 365. Inoltre, i destinatari che ricevono un messaggio di posta elettronica protetto inviato a un account di Office 365 in Outlook 2016 o Outlook sul Web, non è necessario eseguire ulteriori operazioni per visualizzare il messaggio. Funziona perfettamente. Anche i destinatari che utilizzano client di posta elettronica e provider di servizi di posta elettronica dispongono di un'esperienza migliorata. Per informazioni, vedere [Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) e [come aprire un messaggio protetto](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Per un elenco dettagliato delle differenze tra la versione precedente di OME e le nuove funzionalità OME, vedere [compare versions of ome](ome-version-comparison.md).

Quando un utente invia un messaggio di posta elettronica che corrisponde a una regola del flusso di posta di crittografia, il messaggio viene crittografato prima dell'invio. Tutti gli utenti finali di Office 365 che utilizzano i client Outlook per leggere la posta ricevono le esperienze di lettura native, di prima classe per i messaggi crittografati e protetti da diritti, anche se non sono presenti nella stessa organizzazione del mittente. I client Outlook supportati includono Outlook desktop, Outlook Mac, Outlook Mobile su iOS e Android e Outlook sul Web (in precedenza noto come Outlook Web App).

I destinatari dei messaggi crittografati che ricevono la posta crittografata o protetta da diritti inviati ai propri account di Outlook.com, Gmail e Yahoo ricevono un messaggio di posta elettronica wrapper che li indirizza al portale OME, in cui è possibile eseguire facilmente l'autenticazione utilizzando un account Microsoft, Gmail o Credenziali Yahoo.

Gli utenti finali che leggono i messaggi crittografati o protetti da diritti nei client diversi da Outlook utilizzano anche il portale OME per visualizzare le informazioni crittografate e protette con i diritti ricevuti.

Se il mittente della posta protetta è in GCC High e il destinatario è esterno a GCC High, compresi gli utenti di Office 365 commerciali, gli utenti di Outlook.com e gli utenti di altri provider di posta elettronica, ad esempio Gmail, il destinatario riceve un messaggio di posta elettronica wrapper. La posta del wrapper indirizza il destinatario al portale OME in cui il destinatario è in grado di leggere e rispondere al messaggio. In caso contrario, se il mittente e il destinatario sono entrambi nell'ambiente GCC High, anche se non sono presenti nella stessa organizzazione, i destinatari che utilizzano i client di Outlook per leggere la posta elettronica ricevano le esperienze di lettura di prima classe per i messaggi crittografati e protetti da diritti . Per ulteriori informazioni sulle diverse esperienze in GCC High, vedere [compare versions of ome](ome-version-comparison.md).

Per ulteriori informazioni sui limiti di dimensione per i messaggi e gli allegati che è possibile crittografare tramite OME, vedere [Exchange Online limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Come funziona la crittografia avanzata dei messaggi di Office 365 in primo piano

La crittografia avanzata dei messaggi di Office 365 consente di creare modelli di branding multipli, in modo da poter ottimizzare il controllo della posta dei destinatari e creare esperienze personalizzate di branding per supportare una struttura organizzativa diversificata.

La crittografia avanzata dei messaggi in Office 365 consente di soddisfare gli obblighi di conformità che richiedono un controllo più flessibile sull'accesso dei destinatari esterni ai messaggi di posta elettronica crittografati. Con la crittografia avanzata dei messaggi in Office 365, in qualità di amministratore, è possibile controllare i messaggi di posta elettronica riservati condivisi all'esterno dell'organizzazione con criteri automatici che consentono di rilevare tipi di informazioni riservate (ad esempio, ID di integrità, finanziario o sanitario) o parole chiave per migliorare protezione tramite la scadenza dell'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati. Inoltre, come amministratore è possibile controllare ulteriormente i messaggi di posta elettronica crittografati accessibili esternamente tramite un portale Web di Office 365 revocando l'accesso a un messaggio di posta elettronica in qualsiasi momento.

La revoca dei messaggi e la scadenza funzionano solo per i messaggi di posta elettronica inviati dagli utenti ai destinatari all'esterno dell'organizzazione di Office 365. Inoltre, i destinatari devono accedere al messaggio di posta elettronica tramite il portale Web. Per assicurarsi che il destinatario utilizzi il portale per la ricezione della posta elettronica, è necessario configurare un modello di personalizzazione personalizzato che applica il wrapper. Viene quindi applicato il modello di personalizzazione in una regola del flusso di posta. Per ulteriori informazioni sulla crittografia avanzata dei messaggi, vedere [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-office-365-message-encryption"></a>Regole di definizione per la crittografia dei messaggi di Office 365

Un modo per abilitare le nuove funzionalità per la crittografia dei messaggi di Office 365 è per gli amministratori di Exchange Online e Exchange Online Protection per definire le regole del flusso di posta. Queste regole determinano in quali condizioni devono essere crittografati i messaggi di posta elettronica. Quando viene impostata un'azione di crittografia per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati prima di essere inviati.

Le regole del flusso di posta sono flessibili, consentendo di combinare condizioni in modo da poter soddisfare requisiti di sicurezza specifici in una singola regola. Ad esempio, è possibile creare una regola per crittografare tutti i messaggi che contengono parole chiave specificate e che sono indirizzati a destinatari esterni. Le nuove funzionalità per la crittografia dei messaggi di Office 365 crittografano anche le risposte dai destinatari della posta elettronica crittografata.

Per ulteriori informazioni su come creare regole del flusso di posta per sfruttare le nuove funzionalità OME, vedere [definire le regole per la crittografia dei messaggi di Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-the-new-ome-capabilities"></a>Iniziare a utilizzare le nuove funzionalità OME

Se si è pronti per iniziare a utilizzare le nuove funzionalità OME all'interno dell'organizzazione, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md).

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Invio, risposta e visualizzazione di messaggi di posta elettronica crittografati

Con la crittografia dei messaggi di Office 365, gli utenti possono inviare messaggi di posta elettronica crittografati da Outlook e Outlook sul Web. Gli amministratori possono inoltre configurare le regole del flusso di posta in Office 365 per crittografare automaticamente le e-mail in base alle parole chiave corrispondenti o ad altre condizioni.

I destinatari dei messaggi crittografati che si trovano nelle organizzazioni di Office 365 saranno in grado di leggere tali messaggi senza problemi in qualsiasi versione di Outlook, tra cui Outlook per PC, Outlook per Mac, Outlook sul Web, Outlook per iOS e Outlook per Android. Gli utenti che ricevono messaggi crittografati in altri client di posta elettronica possono visualizzare i messaggi nel portale OME.

Per istruzioni dettagliate su come inviare e visualizzare i messaggi crittografati, vedere gli articoli seguenti:

|||
|:-----|:-----|
|Leggere questo articolo...|Se si è...|
|[Informazioni sui messaggi protetti in Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Un utente finale che desidera ottenere ulteriori informazioni sul funzionamento dei messaggi crittografati e sulle opzioni disponibili.|
|[Come aprire un messaggio protetto](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Un utente finale che vuole leggere un messaggio protetto che è stato inviato. In questo articolo sono incluse informazioni sulla lettura di messaggi in diverse versioni di Outlook e su account di posta elettronica diversi, compresi quelli esterni a Office 365, ad esempio Gmail e Yahoo! account.|
|[Inviare, visualizzare e rispondere a messaggi crittografati in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)|Un utente finale che desidera inviare, visualizzare o rispondere a un messaggio crittografato da Outlook. Anche se non si è membri di un'organizzazione di Office 365, viene comunque ricevuta la notifica dei messaggi crittografati inviati all'utente in Outlook. Utilizzare questo articolo per istruzioni su come visualizzare e rispondere a messaggi crittografati inviati da Office 365.|
|[Inviare un messaggio con firma digitale o crittografato](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Un utente finale che desidera inviare, visualizzare o rispondere a messaggi crittografati utilizzando Outlook per Mac. Questo articolo riguarda anche l'utilizzo di metodi di crittografia diversi da OME, ad esempio S/MIME.|
|[Visualizzazione dei messaggi crittografati sul dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Un utente finale che ha ricevuto un messaggio crittografato con la crittografia dei messaggi di Office 365 sul dispositivo Android, è possibile utilizzare l'app gratuito OME Viewer per visualizzare il messaggio e inviare una risposta crittografata. In questo articolo viene illustrato come.|
|[Visualizzare i messaggi crittografati sul tuo iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)|Un utente finale che ha ricevuto un messaggio crittografato con la crittografia dei messaggi di Office 365 sul vostro iPhone o iPad, è possibile utilizzare l'app visualizzatore gratuito OME per visualizzare il messaggio e inviare una risposta crittografata. In questo articolo viene illustrato come.|
||