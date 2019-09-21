---
title: Informazioni legacy per Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
description: Se non è stata ancora spostata l'organizzazione di Office 365 nelle nuove funzionalità OME, ma è già stata distribuita OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia di effettuare un piano per passare alle nuove funzionalità OME non appena è ragionevole per la propria organizzazione. Per istruzioni, vedere Configurare le nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection. Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere crittografia dei messaggi di Office 365. Il resto di questo articolo si riferisce al comportamento OME prima del rilascio delle nuove funzionalità OME.
ms.openlocfilehash: 70529e9aa5c444ab8fc57d4a9698295e50198725
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083724"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Informazioni legacy per Office 365 Message Encryption

Se non è stata ancora spostata l'organizzazione di Office 365 nelle nuove funzionalità OME, ma è già stata distribuita OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia di effettuare un piano per passare alle nuove funzionalità OME non appena è ragionevole per la propria organizzazione. Per istruzioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection](set-up-new-message-encryption-capabilities.md). Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere [crittografia dei messaggi di Office 365](ome.md). Il resto di questo articolo si riferisce al comportamento OME prima del rilascio delle nuove funzionalità OME.
  
Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti all'interno e all'esterno dell'organizzazione. La crittografia dei messaggi di Office 365 è compatibile con Outlook.com, Yahoo, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica consente di verificare che solo i destinatari previsti possano visualizzare il contenuto del messaggio.
  
Ecco alcuni esempi:
  
- Un dipendente di banca invia istruzioni sulla carta di credito ai clienti

- Un rappresentante della compagnia assicurativa fornisce informazioni sui criteri ai clienti

- Un broker di mutui richiede informazioni finanziarie da un cliente per una domanda di prestito

- Un provider di servizi sanitari invia informazioni sull'assistenza sanitaria ai pazienti

- Un avvocato invia informazioni riservate a un cliente o a un altro avvocato

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Funzionamento della crittografia dei messaggi di Office 365 senza le nuove funzionalità

La crittografia dei messaggi di Office 365 è un servizio online basato su Microsoft Azure Rights Management (Azure RMS). Con Azure RMS, gli amministratori possono definire le regole del flusso di posta per determinare le condizioni per la crittografia. Ad esempio, una regola può richiedere la crittografia di tutti i messaggi indirizzati a un destinatario specifico.
  
Guardare questo breve video per vedere come funziona la crittografia dei messaggi di Office 365 senza le nuove funzionalità.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
Quando un utente invia un messaggio di posta elettronica in Exchange Online che corrisponde a una regola di crittografia, il messaggio viene inviato con un allegato HTML. Il destinatario apre l'allegato HTML e segue le istruzioni per visualizzare il messaggio crittografato sul portale di crittografia dei messaggi di Office 365. Il destinatario può scegliere di visualizzare il messaggio accedendo con un account Microsoft o un lavoro o una scuola associati a Office 365 oppure utilizzando un codice Pass una tantum. Tali opzioni garantiscono che solo il destinatario specificato sia in grado di visualizzare il messaggio crittografato. Questo processo è molto diverso per le nuove funzionalità OME.
  
Nel seguente diagramma viene riepilogata la procedura di crittografia e decrittografia di un messaggio di posta elettronica.
  
![Diagramma del percorso di un messaggio di posta elettronica crittografato](media/O365-Office365MessageEncryption-Concept.png)
  
Per ulteriori informazioni, vedere [informazioni sul servizio per la crittografia dei messaggi di Office 365 legacy prima del rilascio delle nuove funzionalità ome](legacy-information-for-message-encryption.md#LegacyServiceInfo).
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definizione delle regole del flusso di posta per la crittografia dei messaggi di Office 365 che non utilizzano le nuove funzionalità OME

Per abilitare la crittografia dei messaggi di Office 365 senza le nuove funzionalità, gli amministratori di Exchange Online e Exchange Online Protection definiscono le regole del flusso di posta di Exchange. Queste regole determinano in quali condizioni devono essere crittografati i messaggi di posta elettronica, nonché le condizioni per la rimozione della crittografia dei messaggi. Quando viene impostata un'azione di crittografia per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati prima di essere inviati.
  
Le regole del flusso di posta sono flessibili, consentendo di combinare condizioni in modo da poter soddisfare requisiti di sicurezza specifici in una singola regola. Ad esempio, è possibile creare una regola per crittografare tutti i messaggi che contengono parole chiave specificate e che sono indirizzati a destinatari esterni. La crittografia dei messaggi di Office 365 crittografa anche le risposte provenienti da destinatari di messaggi di posta elettronica crittografati ed è possibile creare una regola che decripta tali risposte come vantaggio per gli utenti di posta elettronica. In questo modo, gli utenti dell'organizzazione non dovranno accedere al portale di crittografia per visualizzare le risposte.
  
Per ulteriori informazioni su come creare regole del flusso di posta di Exchange, vedere [definire le regole per la crittografia dei messaggi di Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Invio, risposta e visualizzazione di messaggi di posta elettronica crittografati

Con la crittografia dei messaggi di Office 365, i messaggi di posta elettronica vengono crittografati automaticamente, in base alle regole definite dall'amministratore. Un messaggio di posta elettronica in cui viene inserito un messaggi crittografato arriva nella posta in arrivo del destinatario con un file HTML allegato.
  
I destinatari seguono le istruzioni del messaggio per aprire l'allegato e eseguire l'autenticazione utilizzando un account Microsoft o un lavoro o una scuola associati a Office 365. Se i destinatari non dispongono di un account, è possibile creare un account Microsoft che consentirà di accedere per visualizzare il messaggio crittografato. In alternativa, i destinatari possono scegliere di ottenere un codice Pass una tantum per visualizzare il messaggio. Dopo aver eseguito l'accesso o l'utilizzo di un codice Pass una tantum, i destinatari possono visualizzare il messaggio decrittografato e inviare una risposta crittografata.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalizzare i messaggi crittografati con la crittografia dei messaggi di Office 365

In qualità di amministratore di Exchange Online e Exchange Online Protection, è possibile personalizzare i messaggi crittografati. Ad esempio, è possibile aggiungere il marchio e il logo della società, specificare un'introduzione e aggiungere testo di dichiarazione di non responsabilità nei messaggi crittografati e nel portale in cui i destinatari visualizzano i messaggi crittografati. Utilizzando i cmdlet Windows PowerShell, è possibile personalizzare i seguenti aspetti dell'esperienza di visualizzazione per i destinatari dei messaggi di posta elettronica crittografati:
  
- Testo introduttivo del messaggio di posta elettronica contenente il messaggio crittografato

- Testo della dichiarazione di non responsabilità del messaggio di posta elettronica contenente il messaggio crittografato

- Testo portale che apparirà nel messaggio di visualizzazione del portale

- Logo che verrà visualizzato nel messaggio di posta elettronica e nel portale di visualizzazione

È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.
  
Nel seguente esempio viene illustrato un logo personalizzato per ContosoPharma nell'allegato di posta elettronica:
  
![Esempio di visualizzazione della pagina del messaggio crittografato](media/TA-OME-3attachment2.jpg)
  
 **Per personalizzare i messaggi di posta elettronica di crittografia e il portale di crittografia con il marchio dell'organizzazione**
  
1. Connettersi a Exchange Online tramite Remote PowerShell, come descritto in [Connect to Exchange Online using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated).

2. Utilizzare il cmdlet Set-OMEConfiguration come descritto di seguito: [set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) oppure utilizzare la seguente tabella per istruzioni.

   **Opzioni di personalizzazione della crittografia**

|**Per personalizzare questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi di Windows PowerShell**|
|:-----|:-----|
|Testo predefinito che accompagna i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Esempio:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Esempio:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Esempio:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|Logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Esempio:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formati di file supportati: png, jpg, bmp o tiff  <br/> Dimensione ottimale relativa al file del logo: inferiore a 40 KB  <br/> Dimensioni ottimali relative all'immagine del logo: 170x70 pixel  <br/> |

 **Per rimuovere le personalizzazioni di marca dai messaggi di posta elettronica di crittografia e il portale di crittografia**
  
1. Connettersi a Exchange Online tramite Remote PowerShell, come descritto in [Connect to Exchange Online using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).

2. Utilizzare il cmdlet Set-OMEConfiguration come descritto di seguito: [set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). Per rimuovere le personalizzazioni personalizzate dell'organizzazione dai valori DisclaimerText, EmailText e PortalText, impostare il valore su una stringa vuota `""`. Per tutti i valori di immagine, ad esempio logo, impostare il `"$null"`valore su.

   **Opzioni di personalizzazione della crittografia**

|**Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi di Windows PowerShell**|
|:-----|:-----|
|Testo predefinito che accompagna i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Esempio:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Esempio:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Esempio ripristinando il valore predefinito:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|Logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Esempio ripristinando il valore predefinito:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Informazioni sul servizio per la crittografia dei messaggi di Office 365 legacy prima del rilascio delle nuove funzionalità OME
<a name="LegacyServiceInfo"> </a>

La tabella seguente fornisce informazioni tecniche per il servizio di crittografia dei messaggi di Office 365 prima del rilascio delle nuove funzionalità OME.
  
|**Dettagli servizio**|**Descrizione**|
|:-----|:-----|
|Requisiti dei dispositivi client  <br/> |I messaggi crittografati possono essere visualizzati su tutti i dispositivi client, purché l'allegato HTML possa essere aperto in un browser moderno che supporta Post per i moduli.  <br/> |
|Algoritmo di crittografia e conformità FIPS (Federal Information Processing Standards)  <br/> |La crittografia dei messaggi di Office 365 utilizza le stesse chiavi di crittografia di Windows Azure Information Rights Management (IRM) e supporta Modalità crittografia 2 (chiave a 2 K per RSA e chiave a 256 bit per sistemi SHA-1). Per ulteriori informazioni sulle modalità di crittografia IRM sottostanti, vedere [modalità di crittografia ad RMS](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).  <br/> |
|Tipi di messaggi supportati  <br/> |La crittografia messaggi di Office 365 è supportata soltanto per gli elementi con ID classe messaggio pari a **IPM.Note**. Per ulteriori informazioni, vedere [tipi di elementi e classi di messaggi](https://msdn.microsoft.com/library/office/ff861573.aspx).  <br/> |
|Limiti di dimensione dei messaggi  <br/> |Crittografia dei messaggi di Office 365 è in grado di crittografare messaggi con dimensioni fino a 25 megabyte. Per ulteriori informazioni sui limiti relativi alle dimensioni dei messaggi, vedere [limiti di Exchange Online](http://technet.microsoft.com/library/exchange-online-limits.aspx).  <br/> |
|Criteri di conservazione della posta elettronica di Exchange Online  <br/> |Exchange Online non archivia i messaggi crittografati.  <br/> |
|Supporto linguistico per la crittografia dei messaggi di Office 365  <br/> | Crittografia dei messaggi di Office 365 supporta le ingue di Office 365, come segue:  <br/>  I messaggi di posta elettronica in arrivo e i file HTML allegati vengono localizzati in base alle impostazioni della lingua del mittente.  <br/>  Il portale di visualizzazione viene localizzato in base alle impostazioni del browser del destinatario.  <br/>  Il corpo (contenuto) del messaggio crittografato non è localizzato.  <br/> |
|Informazioni sulla privacy per il Portale OME e l'app visualizzatore OME  <br/> |[Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/en-US/privacystatement) fornisce informazioni dettagliate sulle azioni effettuate da Microsoft con le informazioni private fornite dagli utenti.  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>Domande frequenti su OME legacy
<a name="LegacyServiceInfo"> </a>

Hai domande sulla crittografia dei messaggi di Office 365? Di seguito sono riportate alcune risposte. Se non si riesce a trovare le informazioni necessarie, consultare i forum della community di Office 365 nella [community di office 365](http://community.office365.com/en-us/forums/default.aspx).
  
 **D. gli utenti che inviano messaggi di posta elettronica crittografati ai destinatari esterni all'organizzazione. Per leggere e rispondere ai messaggi di posta elettronica crittografati con la crittografia dei messaggi di Office 365, è necessario eseguire altre attività ai destinatari esterni.**
  
I destinatari esterni all'organizzazione che ricevono messaggi crittografati di Office 365 possono visualizzarli seguendo uno dei due metodi riportati:
  
- Tramite l'accesso con un account Microsoft o un account aziendale o dell'Istituto di istruzione associato a Office 365.

- Utilizzando un codice pass monouso.

 **D. I messaggi criptati di Office 365 vengono memorizzati sul cloud o sui server Microsoft?**
  
No, i messaggi crittografati vengono mantenuti nel sistema di posta elettronica del destinatario e, quando il destinatario apre il messaggio, viene temporaneamente inviato per la visualizzazione nei server di Office 365. I messaggi non vengono archiviati.
  
 **D. È possibile personalizzare i messaggi di posta elettronica crittografati con il proprio marchio?**
  
Sì. È possibile utilizzare i cmdlet di Windows PowerShell per personalizzare il testo personalizzato che viene visualizzato nella parte superiore dei messaggi di posta elettronica crittografati, il testo della Dichiarazione di non responsabilità e il logo che si desidera utilizzare per il messaggio di posta elettronica e il portale di crittografia. Per i dettagli, vedere [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **D. Il servizio richiede una licenza per ogni utente dell'organizzazione?**
  
È necessario disporre di una licenza per ogni utente dell'organizzazione che invia messaggi di posta elettronica crittografati.
  
 **D. I destinatari esterni hanno bisogno di sottoscrizioni?**
  
No, i destinatari esterni non necessitano di una sottoscrizione per leggere o rispondere ai messaggi crittografati.
  
 **D. in che modo la crittografia dei messaggi di Office 365 è diversa da Rights Management Services (RMS)?**
  
RMS fornisce le funzionalità di protezione dei diritti di informazioni per i messaggi di posta elettronica interni di un'organizzazione fornendo modelli incorporati, ad esempio: non inoltrare e riservare la società. La crittografia dei messaggi di Office 365 supporta la crittografia dei messaggi di posta elettronica che vengono inviati ai destinatari esterni e interni.
  
 **D. in che modo la crittografia dei messaggi di Office 365 è diversa da S/MIME?**
  
S/MIME rappresenta una tecnologia di crittografia sul lato client e necessita di una complessa gestione del certificato e di pubblicazione dell'infrastruttura. La crittografia dei messaggi di Office 365 utilizza le regole del flusso di posta (note anche come regole di trasporto) e non dipende dalla pubblicazione dei certificati.
  
 **D. È possibile leggere i messaggi crittografati su dispositivi mobili?**
  
Sì, è possibile visualizzare i messaggi su Android e iOS scaricando le app del Visualizzatore OME da [Google Play Store](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409) e dall' [Apple App Store](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409). Aprire l'allegato in formato HTML nell'app Visualizzatore Crittografia messaggi di Office 365 e attenersi alle istruzioni per aprire il messaggio crittografato. Per quanto riguarda altri dispositivi mobili, è possibile aprire l'allegato in formato HTML fin tanto che il client di posta elettronica supporta Post per i form.
  
 **D. I messaggi di risposta e i messaggi inoltrati vengono crittografati?**
  
Sì. I messaggi di risposta vengono crittografati per tutta la durata del thread.
  
 **D. la crittografia dei messaggi di Office 365 fornisce la localizzazione?**
  
Il contenuto della posta elettronica in arrivo viene localizzata in base alle impostazioni di posta elettronica del mittente. Il portale di visualizzazione viene localizzato in base alle impostazioni del browser del destinatario. Tuttavia, il corpo (contenuto) del messaggio crittografato non viene localizzato.
  
 **D. quale metodo di crittografia viene utilizzato per la crittografia dei messaggi di Office 365?**
  
La crittografia dei messaggi di Office 365 utilizza Rights Management Services (RMS) come infrastruttura di crittografia. Il metodo di crittografia utilizzato dipende da dove ottieni le chiavi RMS utilizzate per crittografare e decrittografare messaggi.
  
- Se si utilizza Microsoft Azure RMS per ottenere le chiavi, viene utilizzata la modalità di crittografia 2. La Modalità di crittografia 2 è un'implementazione di crittografia AD RMS aggiornata e migliorata. Questa supporta RSA 2048 per la crittografia e firma e SHA-256 per firma.

- Se si utilizza Active Directory (AD) RMS per ottenere le chiavi, viene utilizzata la Modalità di crittografia 1 o la Modalità di crittografia 2. Il metodo utilizzato dipende dalla distribuzione Active directory (AD) RMS. La Modalità di crittografia 1 è l'implementazione di crittografia AD RMS originale. Questa supporta RSA 1024 per la crittografia e firma e SHA-1 per firma. Questa modalità continua ad essere supportata da tutte le versioni correnti di RMS.

Per ulteriori informazioni, vedere [modalità di crittografia ad RMS](http://go.microsoft.com/fwlink/p/?LinkId=398616).
  
 **D: perché alcuni messaggi crittografati dicono di essere provenienti da** Office365@messaging.microsoft.com?
  
Quando una risposta crittografata viene inviata dal portale di crittografia oppure tramite l'app Visualizzatore Crittografia messaggi di Office 365, l'indirizzo del messaggio di posta elettronica da inviare è impostato su Office365@messaging.microsoft.com perché il messaggio crittografato viene inviato tramite un endpoint di Microsoft. In questo modo si evita che i messaggi crittografati vengano contrassegnati come posta indesiderata. Il nome visualizzato nel messaggio di posta elettronica e l'indirizzo all'interno del portale di crittografia non vengono modificati a causa di questa etichetta. Inoltre, tale etichetta si applica solo ai messaggi inviati tramite il portale, non tramite altri client di posta elettronica.
  
 **D. sono un Sottoscrittore di Exchange Hosted Encryption (EHE). Dove è possibile ottenere ulteriori informazioni sull'aggiornamento alla crittografia dei messaggi di Office 365?**
  
Si è provveduto all'aggiornamento al servizio di crittografia dei messaggi di Office 365 per tutti gli utenti di EHE. Per ulteriori informazioni, visitare il [Centro aggiornamenti di Exchange Hosted Encryption](http://go.microsoft.com/fwlink/p/?LinkID=511077).
  
 **D. è necessario aprire tutti gli URL, gli indirizzi IP o le porte del firewall dell'organizzazione per supportare la crittografia dei messaggi di Office 365?**
  
Sì. È necessario aggiungere URL per Exchange Online all'elenco Consenti per l'organizzazione per abilitare l'autenticazione per i messaggi crittografati tramite la crittografia dei messaggi di Office 365. Per un elenco di URL di Exchange Online, vedi [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx).
  
 **D. A quanti destinatari posso inviare un messaggio crittografato tramite Office 365?**
  
Il limite del destinatario è 500 destinatari per messaggio oppure, se combinato dopo l'espansione della lista di distribuzione, 11.980 caratteri del messaggio in campo **a** , a seconda di quale verrà prima.
  
 **D. È possibile revocare un messaggio inviato a un particolare destinatario?**
  
No. Non è possibile revocare un messaggio a una persona specifica dopo che è stata inviata.
  
 **D. Posso visualizzare un report dei messaggi crittografati che sono stati ricevuti e letti?**
  
Non è presente un rapporto che indica se è stato visualizzato un messaggio crittografato, ma sono disponibili rapporti di Office 365 che è possibile utilizzare per determinare il numero di messaggi che corrispondono a una regola del flusso di posta specifica (nota anche come regola di trasporto), ad esempio.
  
 **D. Come vengono utilizzate da Microsoft le informazioni fornite tramite il Portale OME e l'app visualizzatore OME?**
  
L'informativa [sulla privacy di Office 365 Messaging Encryption Portal](https://privacy.microsoft.com/en-US/privacystatement) fornisce informazioni dettagliate su ciò che Microsoft fa e non fa con le informazioni private.
 
