---
title: Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Scopri come Exchange Online e Microsoft 365 transport layer security (TLS) e Forward Secrecy (FS) per proteggere le comunicazioni di posta elettronica. Ottieni anche informazioni sul certificato emesso da Microsoft per Exchange Online.
ms.openlocfilehash: cc7ca631f9322fdc8a85cfaba197e63d06d08aee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906952"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica

Scopri come Exchange Online e Microsoft 365 transport layer security (TLS) e Forward Secrecy (FS) per proteggere le comunicazioni di posta elettronica. Fornisce inoltre informazioni sul certificato emesso da Microsoft per Exchange Online.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Nozioni di base su TLS Microsoft 365 e Exchange Online

Transport Layer Security (TLS) e il precedente Secure Sockets Layer (SSL) sono protocolli crittografici che proteggono la comunicazione in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. TLS sostituisce Secure Sockets Layer (SSL) e spesso viene indicato come SSL 3.1. Per Exchange Online, viene utilizzato TLS per crittografare le connessioni tra i server Exchange e le connessioni tra i server Exchange e altri server, ad esempio i server Exchange locali o i server di posta dei destinatari. Una volta crittografata la connessione, tutti i dati inviati mediante tale connessione utilizzano il canale crittografato. Tuttavia, se si inoltra un messaggio che è stato inviato tramite una connessione TLS crittografata, tale messaggio non viene necessariamente crittografato. Questo perché, in termini semplici, TLS non crittografa il messaggio, ma solo la connessione.
  
Se si desidera crittografare il messaggio, è necessario utilizzare una tecnologia di crittografia che consenta di crittografare i contenuti dei messaggi come, ad esempio, Crittografia messaggi di Office. Per informazioni sulle opzioni di crittografia dei messaggi in Office 365, vedere [Email encryption in Office 365](email-encryption.md) e [Office 365 Message Encryption (OME)](ome.md). 
  
È consigliabile usare TLS in situazioni in cui si desidera configurare un canale sicuro di corrispondenza tra Microsoft e l'organizzazione locale o un'altra organizzazione, ad esempio un partner. Exchange Online tenta di utilizzare innanzitutto TLS per proteggere la posta elettronica, ma questa operazione non è sempre possibile se l'altra parte non offre la protezione TLS. Continua a leggere per scoprire come proteggere tutta la posta ai server locali o ai partner importanti utilizzando  *i connettori*. 

Per fornire la crittografia più avanzata ai clienti, Microsoft ha deprecato Transport Layer Security (TLS) versioni 1.0 e 1.1 in [Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) e [Office 365 GCC](tls-1-2-in-office-365-gcc.md). È tuttavia possibile continuare a utilizzare una connessione SMTP non crittografata senza TLS. Si sconsiglia la trasmissione della posta elettronica senza alcuna crittografia.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Come viene utilizzato TLS in Exchange Online tra clienti di Exchange Online

I server di Exchange Online consentono di crittografare sempre le connessioni ad altri server di Exchange Online nei nostri datacenter con TLS 1.2. Quando si invia posta a un destinatario all'interno dell'organizzazione, tale messaggio viene inviato automaticamente tramite una connessione crittografata tramite TLS. Inoltre, tutti i messaggi di posta elettronica inviati ad altri clienti vengono inviati tramite connessioni crittografate tramite TLS e protette tramite forward secrecy.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Come Microsoft 365 TLS tra Microsoft 365 partner attendibili ed esterni

Per impostazione predefinita, Exchange Online usa sempre TLS opportunistico. Questo significa che Exchange Online sempre tenta di crittografare le connessioni con la versione più sicura di TLS, quindi funziona lungo l'elenco delle crittografie TLS finché non ne trova una su cui entrambe le parti sono d'accordo. A meno che non sia stato configurato Exchange Online per garantire che i messaggi a tale destinatario vengano inviati solo tramite connessioni sicure, per impostazione predefinita il messaggio verrà inviato non crittografato se l'organizzazione destinatario non supporta la crittografia TLS. Tls opportunistico è sufficiente per la maggior parte delle aziende. Tuttavia, per le aziende con requisiti di conformità, ad esempio organizzazioni mediche, bancarie o governative, è possibile configurare Exchange Online per richiedere o forzare TLS. Per istruzioni, vedere [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
Se si decide di configurare TLS tra la propria organizzazione e un'organizzazione partner attendibile, in Exchange Online è possibile utilizzare TLS forzato per creare canali di comunicazione attendibili. TLS forzato richiede che l'organizzazione partner esegua l'autenticazione a Exchange Online con un certificato di sicurezza per inviare la posta all'utente. A tale scopo, il partner dovrà gestire i propri certificati. In Exchange Online i connettori vengono utilizzati per proteggere i messaggi inviati dall'accesso non autorizzato prima che arrivino al provider di posta elettronica del destinatario. Per informazioni sull'utilizzo dei connettori per configurare il flusso di posta, vedere [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e distribuzioni ibride di Exchange Server

Se si gestisce una distribuzione ibrida di Exchange, il server Exchange locale deve eseguire l'autenticazione a Microsoft 365 utilizzando un certificato di sicurezza per inviare posta ai destinatari le cui cassette postali sono solo in Office 365. Di conseguenza, è necessario gestire i propri certificati di sicurezza per i server Exchange locali. Inoltre, è necessario archiviare e conservare questi certificati per i server in modo sicuro. Per ulteriori informazioni sulla gestione dei certificati nelle distribuzioni ibride, vedere [Certificate requirements for hybrid deployments](/exchange/certificate-requirements).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Come configurare TLS forzato per Exchange Online in Office 365

Per i clienti di Exchange Online, affinché TLS forzato sia utilizzato per proteggere tutta la posta elettronica inviata e ricevuta, è necessario configurare più di un connettore che richiede TLS. Sarà necessario un connettore per la posta elettronica inviata alle cassette postali degli utenti e un altro connettore per la posta elettronica inviata dalle cassette postali degli utenti. Creare tali connettori nell'interfaccia di amministrazione di Exchange in Office 365. Per istruzioni, vedere [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Informazioni sul certificato TLS per Exchange Online

Le informazioni sul certificato utilizzate da Exchange Online sono descritte nella tabella seguente. Se il partner commerciale configura TLS forzato sul proprio server di posta elettronica, sarà necessario fornire tali informazioni al partner. Tenere presente che, per motivi di sicurezza, i nostri certificati possono subire delle modifiche di tanto in tanto. È stato installato un aggiornamento del certificato all'interno dei datacenter. Il nuovo certificato è valido dal 3 settembre 2018.
  
 **Informazioni correnti sul certificato valide dal 3 settembre 2018**
  
| Attributo | Valore |
|:-----|:-----|
|Autorità di certificazione principale  <br/> |GlobalSign Root CA – R1 <br/> |
|Nome certificato  <br/> |mail.protection.outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
 **Informazioni sui certificati deprecate valide fino al 3 settembre 2018**
  
Per garantire una transizione senza problemi, continueremo a fornire le informazioni del certificato precedente per il riferimento per un certo periodo di tempo, tuttavia, è consigliabile usare le informazioni del certificato corrente d'ora in poi.
  
****

| Attributo | Valore |
|:-----|:-----|
|Autorità di certificazione principale  <br/> |Baltimore CyberTrust Root  <br/> |
|Nome certificato  <br/> |mail.protection.outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |Microsoft Corporation  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Preparare il nuovo certificato Exchange Online certificato

Il nuovo certificato viene emesso da un'autorità di certificazione (CA) diversa dal certificato precedente utilizzato da Exchange Online. Di conseguenza, potrebbe essere necessario eseguire alcune azioni per utilizzare il nuovo certificato.

Il nuovo certificato richiede la connessione agli endpoint della nuova CA come parte della convalida del certificato. La mancata operazione può influire negativamente sul flusso di posta. Se si proteggono i server di posta con firewall che consentono solo ai server di posta di connettersi a determinate destinazioni, è necessario verificare se il server è in grado di convalidare il nuovo certificato. Per verificare che il server possa utilizzare il nuovo certificato, eseguire la procedura seguente:

1. Connessione'utente locale Exchange Server utilizzando Windows PowerShell quindi eseguire il comando seguente:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. Nella finestra visualizzata scegliere **Recupera**.

1. Quando l'utilità completa il controllo, restituisce uno stato. Se lo stato è **OK,** il server di posta può convalidare correttamente il nuovo certificato. In caso contrario, è necessario determinare la causa dell'errore delle connessioni. Molto probabilmente, è necessario aggiornare le impostazioni di un firewall. L'elenco completo degli endpoint a cui è necessario accedere includono:
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

In genere, si ricevono automaticamente gli aggiornamenti dei certificati radice tramite Windows Update. Tuttavia, alcune distribuzioni hanno una sicurezza aggiuntiva che impedisce l'esecuzione automatica di questi aggiornamenti. In queste distribuzioni bloccate in cui Windows Update non è in grado di aggiornare automaticamente i certificati radice, è necessario verificare che il certificato CA radice corretto sia installato completando la procedura seguente:
1.  Connessione'utente locale Exchange Server utilizzando Windows PowerShell quindi eseguire il comando seguente:  
  `certmgr.msc`

2. In **Autorità di certificazione radice attendibile/Certificati** verificare che il nuovo certificato sia elencato.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Altre informazioni su TLS e Microsoft 365

Per un elenco delle suite di crittografia supportate, vedi [Informazioni di riferimento tecniche sulla crittografia.](technical-reference-details-about-encryption.md)
  
[Impostare i connettori per il flusso di posta sicura con un'organizzazione partner](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[Connettori con sicurezza avanzata della posta elettronica](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Crittografia in Microsoft 365](encryption.md)
