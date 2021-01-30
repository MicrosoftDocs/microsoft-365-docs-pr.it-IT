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
description: Informazioni su come Exchange Online e Microsoft 365 utilizzano Transport Layer Security (TLS) e Forward Secrecy (FS) per proteggere le comunicazioni di posta elettronica. Ottenere inoltre informazioni sul certificato emesso da Microsoft per Exchange Online.
ms.openlocfilehash: 507a152130113868293d8d08441f298e5f5ae512
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058459"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica

Informazioni su come Exchange Online e Microsoft 365 utilizzano Transport Layer Security (TLS) e Forward Secrecy (FS) per proteggere le comunicazioni di posta elettronica. Fornisce inoltre informazioni sul certificato emesso da Microsoft per Exchange Online.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Nozioni di base su TLS per Microsoft 365 ed Exchange Online

Transport Layer Security (TLS) e il precedente Secure Sockets Layer (SSL) sono protocolli crittografici che proteggono la comunicazione in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. TLS sostituisce Secure Sockets Layer (SSL) e spesso viene indicato come SSL 3.1. Per Exchange Online, viene utilizzato TLS per crittografare le connessioni tra i server Exchange e le connessioni tra i server Exchange e altri server, ad esempio i server Exchange locali o i server di posta dei destinatari. Una volta crittografata la connessione, tutti i dati inviati mediante tale connessione utilizzano il canale crittografato. Tuttavia, se si inoltra un messaggio che è stato inviato tramite una connessione TLS crittografata, tale messaggio non viene necessariamente crittografato. Questo perché, in parole semplici, TLS non crittografa il messaggio, ma solo la connessione.
  
Se si desidera crittografare il messaggio, è necessario utilizzare una tecnologia di crittografia che consenta di crittografare i contenuti dei messaggi come, ad esempio, Crittografia messaggi di Office. Per informazioni sulle opzioni di crittografia dei messaggi in Office 365, vedere [Email encryption in Office 365](email-encryption.md) e [Office 365 Message Encryption (OME)](ome.md). 
  
È consigliabile utilizzare TLS nelle situazioni in cui si desidera configurare un canale sicuro di corrispondenza tra Microsoft e l'organizzazione locale o un'altra organizzazione, ad esempio un partner. Exchange Online tenta di utilizzare innanzitutto TLS per proteggere la posta elettronica, ma questa operazione non è sempre possibile se l'altra parte non offre la protezione TLS. Continuare a leggere per scoprire come proteggere tutta la posta ai server locali o ai partner importanti utilizzando *i connettori.* 

Per fornire la crittografia migliore ai clienti, Microsoft ha deprecato Transport Layer Security (TLS) versioni 1.0 e 1.1 in [Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) e [Office 365 GCC.](tls-1-2-in-office-365-gcc.md) Tuttavia, è possibile continuare a utilizzare una connessione SMPT non crittografata senza TLS. Si sconsiglia la trasmissione della posta elettronica senza alcuna crittografia.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Come viene utilizzato TLS in Exchange Online tra clienti di Exchange Online

I server di Exchange Online consentono di crittografare sempre le connessioni ad altri server di Exchange Online nei nostri datacenter con TLS 1.2. Quando si invia posta a un destinatario interno all'organizzazione, tale messaggio viene inviato automaticamente tramite una connessione crittografata tramite TLS. Inoltre, tutta la posta elettronica inviata ad altri clienti viene inviata tramite connessioni crittografate tramite TLS e protette tramite Forward Secrecy.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Come Microsoft 365 usa TLS tra Microsoft 365 e partner attendibili esterni

Per impostazione predefinita, Exchange Online utilizza sempre TLS opportunistico. Ciò significa che Exchange Online tenta sempre di crittografare prima le connessioni con la versione più sicura di TLS, quindi scende nell'elenco delle crittografie TLS finché non ne trova una su cui entrambe le parti sono d'accordo. A meno che Exchange Online non sia stato configurato per garantire che i messaggi a tale destinatario vengano inviati solo tramite connessioni sicure, per impostazione predefinita il messaggio verrà inviato non crittografato se l'organizzazione del destinatario non supporta la crittografia TLS. TLS opportunistico è sufficiente per la maggior parte delle aziende. Tuttavia, per le aziende che hanno requisiti di conformità come organizzazioni mediche, bancarie o governative, è possibile configurare Exchange Online per richiedere o forzare TLS. Per istruzioni, vedere [Configurare il flusso di posta con i connettori in Office 365.](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
Se si decide di configurare TLS tra la propria organizzazione e un'organizzazione partner attendibile, in Exchange Online è possibile utilizzare TLS forzato per creare canali di comunicazione attendibili. TLS forzato richiede che l'organizzazione partner esegua l'autenticazione a Exchange Online con un certificato di sicurezza per inviare la posta all'utente. A tale scopo, il partner dovrà gestire i propri certificati. In Exchange Online, i connettori vengono utilizzati per proteggere i messaggi inviati dall'accesso non autorizzato prima che arrivino al provider di posta elettronica del destinatario. Per informazioni sull'utilizzo dei connettori per configurare il flusso di posta, vedere Configurare il flusso di posta tramite [i connettori in Office 365.](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e distribuzioni ibride di Exchange Server

Se si gestisce una distribuzione ibrida di Exchange, il server Exchange locale deve eseguire l'autenticazione in Microsoft 365 utilizzando un certificato di sicurezza per inviare posta ai destinatari le cui cassette postali sono solo in Office 365. Di conseguenza, è necessario gestire i propri certificati di sicurezza per i server Exchange locali. Inoltre, è necessario archiviare e conservare questi certificati per i server in modo sicuro. Per ulteriori informazioni sulla gestione dei certificati nelle distribuzioni ibride, vedere [Requisiti dei certificati per le distribuzioni ibride.](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Come configurare TLS forzato per Exchange Online in Office 365

Per i clienti di Exchange Online, affinché TLS forzato sia utilizzato per proteggere tutta la posta elettronica inviata e ricevuta, è necessario configurare più di un connettore che richiede TLS. Sarà necessario un connettore per la posta elettronica inviata alle cassette postali degli utenti e un altro connettore per la posta elettronica inviata dalle cassette postali degli utenti. Creare tali connettori nell'interfaccia di amministrazione di Exchange in Office 365. Per istruzioni, vedere [Configurare il flusso di posta con i connettori in Office 365.](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
## <a name="tls-certificate-information-for-exchange-online"></a>Informazioni sul certificato TLS per Exchange Online

Le informazioni sul certificato utilizzate da Exchange Online sono descritte nella tabella seguente. Se il partner commerciale configura TLS forzato sul proprio server di posta elettronica, sarà necessario fornire tali informazioni al partner. Tenere presente che, per motivi di sicurezza, i nostri certificati possono subire delle modifiche di tanto in tanto. È stato installato un aggiornamento del certificato all'interno dei datacenter. Il nuovo certificato è valido dal 3 settembre 2018.
  
 **Informazioni aggiornate sui certificati valide dal 3 settembre 2018**
  
|**Attributo**|**Valore**|
|:-----|:-----|
|Autorità di certificazione principale  <br/> |GlobalSign Root CA – R1 <br/> |
|Nome certificato  <br/> |mail.protection.outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
 **Informazioni sui certificati deprecate valide fino al 3 settembre 2018**
  
Per garantire una transizione senza problemi, continueremo a fornire le informazioni del certificato precedente per riferimento per un certo periodo di tempo, tuttavia, è consigliabile usare le informazioni sul certificato corrente d'ora in poi.
  
****

|**Attributo**|**Valore**|
|:-----|:-----|
|Autorità di certificazione principale  <br/> |Baltimore CyberTrust Root  <br/> |
|Nome certificato  <br/> |mail.protection.outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |Microsoft Corporation  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Preparare il nuovo certificato di Exchange Online

Il nuovo certificato viene emesso da un'autorità di certificazione (CA) diversa dal certificato precedente utilizzato da Exchange Online. Di conseguenza, potrebbe essere necessario eseguire alcune azioni per utilizzare il nuovo certificato.

Il nuovo certificato richiede la connessione agli endpoint della nuova CA come parte della convalida del certificato. In caso negativo, il flusso di posta potrebbe essere influenzato negativamente. Se si proteggono i server di posta con firewall che consentono solo ai server di posta di connettersi a determinate destinazioni, è necessario verificare se il server è in grado di convalidare il nuovo certificato. Per verificare che il server possa utilizzare il nuovo certificato, eseguire la procedura seguente:

1. Connettersi al Exchange Server locale utilizzando Windows PowerShell quindi eseguire il comando seguente:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. Nella finestra visualizzata scegliere **Recupera.**
3. Quando l'utilità completa il controllo, restituisce uno stato. Se lo stato è **OK,** il server di posta può convalidare correttamente il nuovo certificato. In caso contrario, è necessario determinare la causa dell'errore delle connessioni. Molto probabilmente, è necessario aggiornare le impostazioni di un firewall. L'elenco completo degli endpoint a cui è necessario accedere include:
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

In genere, gli aggiornamenti dei certificati radice vengono ricevuti automaticamente tramite Windows Update. Tuttavia, alcune distribuzioni hanno una sicurezza aggiuntiva che impedisce che questi aggiornamenti si verifichino automaticamente. In queste distribuzioni bloccate in cui Windows Update non è in grado di aggiornare automaticamente i certificati radice, è necessario verificare che sia installato il certificato DELLA CA radice corretto completando la procedura seguente:
1.  Connettersi al Exchange Server locale utilizzando Windows PowerShell quindi eseguire il comando seguente:  
  `certmgr.msc`
2. In **Autorità di certificazione radice attendibile/Certificati** verificare che il nuovo certificato sia elencato.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Altre informazioni su TLS e Microsoft 365

Per un elenco delle suite di crittografia supportate, vedi informazioni di riferimento tecniche [sulla crittografia.](technical-reference-details-about-encryption.md)
  
[Impostare i connettori per il flusso di posta sicura con un'organizzazione partner](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Connettori con sicurezza avanzata della posta elettronica](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Crittografia in Microsoft 365](encryption.md)
  

