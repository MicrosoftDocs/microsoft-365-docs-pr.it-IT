---
title: Crittografia della posta elettronica in Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Confronto delle opzioni di crittografia di Microsoft 365, tra cui la crittografia dei messaggi di Office (OME), S/MIME, Information Rights Management (IRM) e presentazione di Transport Layer Security (TLS).
ms.openlocfilehash: 81ce8ca567c2b696060a1dd41b9af06bfc7b94a7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769054"
---
# <a name="email-encryption"></a>Crittografia della posta elettronica

Questo articolo confronta le opzioni di crittografia in Microsoft 365, tra cui la crittografia dei messaggi di Office (OME), S/MIME, Information Rights Management (IRM) e introduce Transport Layer Security (TLS).
  
Microsoft 365 delivers multiple encryption options to help you meet your business needs for email security. This article presents three ways to encrypt email in Office 365. If you want to learn more about all security features in Office 365, visit the [Office 365 Trust Center](https://go.microsoft.com/fwlink/p/?LinkID=282470). This article introduces the three types of encryption available for Microsoft 365 administrators to help secure email in Office 365:
  
- Crittografia messaggi di Office (OME).

- S/MIME (Secure/Multipurpose Internet Mail Extensions).

- Information Rights Management (IRM).

## <a name="email-encryption-and-how-microsoft-365-uses-it"></a>Che cos'è la crittografia della posta elettronica e come viene usata in Microsoft 365

Encryption is the process by which information is encoded so that only an authorized recipient can decode and consume the information. Microsoft 365 uses encryption in two ways: in the service, and as a customer control. In the service, encryption is used in Microsoft 365 by default; you don't have to configure anything. For example, Microsoft 365 uses Transport Layer Security (TLS) to encrypt the connection, or session, between two servers. 
  
Ecco come funziona in genere la crittografia della posta elettronica:
  
- Un messaggio viene crittografato o trasformato da testo normale a testo crittografato illeggibile, sul computer del mittente o da un server centrale, mentre il messaggio è in transito.

- Mentre è in transito, per impedire la lettura nel caso in cui venga intercettato, il messaggio rimane in testo crittografato.

- Dopo la ricezione da parte del destinatario, il messaggio viene trasformato nuovamente in testo normale leggibile in uno dei due modi indicati di seguito:

  - il computer del destinatario utilizza una chiave per decrittografare il messaggio, o

  - un server centrale decrittografa il messaggio per conto del destinatario, dopo averne convalidato l'identità.

Per altre informazioni su come Microsoft 365 protegge la comunicazione tra server, ad esempio tra le organizzazioni in Microsoft 365 o tra Microsoft 365 e un partner commerciale attendibile all'esterno di Microsoft 365, vedere l'articolo su [come Exchange Online usa TLS per proteggere le connessioni di posta elettronica in Office 365](exchange-online-uses-tls-to-secure-email-connections.md).
  
Questo video offre un'introduzione alla [crittografia in Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Confronto tra le opzioni di crittografia dei messaggi di posta elettronica disponibili in Office 365

||![Immagine concettuale che descrive OME](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![Immagine concettuale che descrive IRM](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![Immagine concettuale che descrive SMIME](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|Di cosa si tratta?|Crittografia messaggi di Office 365 (OME) è un servizio basato su Azure Rights Management (Azure RMS) che consente di inviare posta elettronica crittografata a destinatari interni o esterni all'organizzazione, indipendentemente dall'indirizzo di posta elettronica di destinazione (Gmail, Yahoo! Mail, Outlook.com e così via). <br/> Come amministratore, è possibile impostare le regole di trasporto che definiscono le condizioni per la crittografia. Quando un utente invia un messaggio che corrisponde a una regola, la crittografia viene applicata automaticamente. <br/> To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Office 365. Recipients can also send encrypted replies. They don't need a Microsoft 365 subscription to view encrypted messages or send encrypted replies.|IRM è una soluzione di crittografia che applica anche limitazioni di utilizzo ai messaggi di posta elettronica. Consente di impedire che informazioni riservate vengano stampate, inoltrate o copiate da persone non autorizzate. <br/> Le funzionalità IRM in Microsoft 365 usano Azure Rights Management (Azure RMS).|S/MIME is a certificate-based encryption solution that allows you to both encrypt and digitally sign a message. The message encryption helps ensure that only the intended recipient can open and read the message. A digital signature helps the recipient validate the identity of the sender. <br/> Le firme digitali e la crittografia dei messaggi vengono entrambe rese possibili tramite l'uso di certificati digitali univoci che contengono le chiavi per la verifica delle firme digitali e per la crittografia o la decrittografia dei messaggi. <br/> To use S/MIME, you must have public keys on file for each recipient. Recipients have to maintain their own private keys, which must remain secure. If a recipient's private keys are compromised, the recipient needs to get a new private key and redistribute public keys to all potential senders.|
|Quali operazioni consente di eseguire la soluzione?|OME: <br/> Consente di crittografare i messaggi inviati a destinatari interni o esterni. <br/>  Consente agli utenti di inviare messaggi crittografati a qualsiasi indirizzo di posta elettronica, tra cui Outlook.com, Yahoo! Mail e Gmail. <br/>  Consente all'amministratore di personalizzare il portale di visualizzazione della posta elettronica per riflettere il marchio dell'organizzazione. <br/> Microsoft gestisce e archivia in modo sicuro le chiavi per conto dell'utente. <br/> Se il messaggio crittografato (inviato come allegato HTML) può essere aperto in un browser, non è necessario alcun software specifico dal lato client.|IRM: <br/> Usa la crittografia e le restrizioni di utilizzo per fornire protezione online e offline per i messaggi e gli allegati di posta elettronica. <br/> Fornisce all'amministratore la possibilità di configurare le regole di trasporto o le regole di protezione di Outlook per applicare automaticamente la protezione IRM per selezionare i messaggi. <br/> Consente agli utenti di applicare manualmente i modelli di Outlook o Outlook sul web (in precedenza noto come Outlook Web App).|Autenticazione del mittente di indirizzi S/MIME con le firme digitali e riservatezza dei messaggi con la crittografia.|
|Quali sono le operazioni che la soluzione non consente?|OME doesn't let you apply usage restrictions to messages. For example, you can't use it to stop a recipient from forwarding or printing an encrypted message.|Some applications may not support IRM emails on all devices. For more information about these and other products that support IRM email, see [Client device capabilities](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).|S/MIME non consente l'analisi dei messaggi crittografati per verificare la presenza di malware, posta indesiderata o dei criteri.|
|Consigli e scenari di esempio|We recommend using OME when you want to send sensitive business information to people outside your organization, whether they're consumers or other businesses. For example:  <br/>  Un dipendente di banca invia comunicazioni sulla carta di credito ai clienti  <br/>  Un medico che invia cartelle cliniche a un paziente  <br/>  Un avvocato invia informazioni legali riservate a un altro avvocato|Si consiglia di utilizzare IRM per applicare limitazioni di utilizzo e la crittografia. Esempio:  <br/>  Un responsabile che invia informazioni riservate al team su un nuovo prodotto applicando l'opzione "Non inoltrare".  <br/>  Un dirigente che deve condividere una proposta di offerta con un'altra società, che include un allegato inviato da un partner che utilizza Office 365 e richiede che la posta elettronica e l'allegato siano entrambi protetti.|Si consiglia di utilizzare S/MIME quando la propria organizzazione o quella del destinatario richiede una reale crittografia peer-to-peer.  <br/>  S/MIME viene utilizzato più comunemente nei seguenti scenari:  <br/>  Comunicazione tra enti pubblici e altri enti governativi  <br/>  Comunicazioni tra un'azienda e un ente governativo|
||

Se si usano sia [Azure Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information) che la crittografia della posta elettronica per proteggere i dati, considerare quanto segue:
- È possibile usare le etichette di riservatezza con la crittografia IRM e OME. Per maggiori dettagli, vedere [Limitare l'accesso al contenuto utilizzando la crittografia nelle etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#what-happens-to-existing-encryption-when-a-labels-applied).
- È possibile applicare etichette di riservatezza ai messaggi di posta elettronica con firma digitale usando S/MIME.
- Non è possibile applicare etichette di riservatezza ai messaggi di posta elettronica crittografati con S/MIME, perché i messaggi protetti dalla crittografia end-to-end non vengono elaborati dai criteri.

## <a name="encryption-options-available-for-my-microsoft-365-subscription"></a>Opzioni di crittografia disponibili per il proprio abbonamento a Microsoft 365

Per informazioni sulle opzioni di crittografia disponibili per l'abbonamento a Microsoft 365, vedere la [descrizione del servizio Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx). Qui è possibile trovare informazioni sulle seguenti funzionalità di crittografia:

- Azure RMS, incluse le funzionalità IRM e le nuove funzionalità OME

- S/MIME

- TLS

- Crittografia dei dati statici (tramite BitLocker)

Con Microsoft 365 è anche possibile usare strumenti di crittografia di terze parti, ad esempio PGP (Pretty Good Privacy). Microsoft 365 non supporta PGP/MIME ed è possibile usare solo PGP/Inline per inviare e ricevere messaggi di posta elettronica crittografati con PGP.

## <a name="what-about-encryption-for-data-at-rest"></a>Informazioni sulla crittografia dei dati inattivi

L'espressione "dati statici" fa riferimento ai dati non attivamente in transito. In Microsoft 365, i dati di posta elettronica inattivi vengono crittografati usando Crittografia unità BitLocker. BitLocker crittografa i dischi rigidi nei data center Microsoft per offrire protezione avanzata dall'accesso non autorizzato. Per altre informazioni, vedere [Panoramica di BitLocker](https://go.microsoft.com/fwlink/p/?LinkId=394737).
  
## <a name="more-information-about-email-encryption-options"></a>Altre informazioni sulle opzioni di crittografia dei messaggi di posta elettronica

Per altre informazioni sulle opzioni di crittografia della posta elettronica descritte in questo articolo e su TLS, vedere questi articoli:
  
**OME**
  
[Office 365 Message Encryption (OME)](ome.md)
  
**IRM**
  
[Information Rights Management in Exchange Online](https://technet.microsoft.com/library/jj983436%28v=exchg.150%29.aspx)
  
[Informazioni su Azure Rights Management](https://technet.microsoft.com/library/jj585026)
  
**S/MIME**
  
[S/MIME per la crittografia e firma dei messaggi](https://technet.microsoft.com/library/dn626158)
  
[Informazioni su S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[Informazioni sulla crittografia a chiave pubblica](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
**TLS**
  
[Configurare il flusso di posta tramite connettori](https://technet.microsoft.com/library/jj723138%28v=exchg.150%29.aspx)
