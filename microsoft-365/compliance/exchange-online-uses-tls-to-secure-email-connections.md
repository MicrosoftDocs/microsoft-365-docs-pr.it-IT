---
title: Come viene utilizzato TLS in Exchange Online per proteggere il traffico della posta elettronica in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
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
description: Informazioni su come Exchange Online e Office 365 utilizzano TLS (Transport Layer Security) e la segretezza di inoltro (FS) per proteggere le comunicazioni tramite posta elettronica. Ottenere anche informazioni sul certificato emesso da Microsoft per Exchange Online.
ms.openlocfilehash: 34667714840e23be5d19aed8f47a539ea1474ab4
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38686402"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica in Office 365

Informazioni su come Exchange Online e Office 365 utilizzano TLS (Transport Layer Security) e la segretezza di inoltro (FS) per proteggere le comunicazioni tramite posta elettronica. Vengono inoltre fornite informazioni sul certificato emesso da Microsoft per Exchange Online.
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Introduzione a TLS per Office 365 ed Exchange Online

Transport Layer Security (TLS) e il precedente Secure Sockets Layer (SSL) sono protocolli crittografici che proteggono la comunicazione in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. TLS sostituisce Secure Sockets Layer (SSL) e spesso viene indicato come SSL 3.1. Per Exchange Online, è possibile utilizzare TLS per crittografare le connessioni tra i server Exchange e le connessioni tra i server Exchange e altri server, ad esempio i server di Exchange locali o i server di posta dei destinatari. Una volta crittografata la connessione, tutti i dati inviati mediante tale connessione utilizzano il canale crittografato. Tuttavia, se si inoltra un messaggio che è stato inviato tramite una connessione TLS crittografata, tale messaggio non viene necessariamente crittografato. Ciò è dovuto al fatto che, in termini semplici, TLS non crittografa il messaggio, solo la connessione.
  
Se si desidera crittografare il messaggio, è necessario utilizzare una tecnologia di crittografia che consenta di crittografare i contenuti dei messaggi come, ad esempio, Crittografia messaggi di Office. Per informazioni sulle opzioni di crittografia dei messaggi in Office 365, vedere [Email encryption in Office 365](email-encryption.md) e [Office 365 Message Encryption (OME)](ome.md). 
  
È consigliabile utilizzare TLS in situazioni in cui si desidera impostare un canale di corrispondenza sicuro tra Office 365 e l'organizzazione locale o un'altra organizzazione, ad esempio un partner. Exchange Online tenta di utilizzare innanzitutto TLS per proteggere la posta elettronica, ma questa operazione non è sempre possibile se l'altra parte non offre la protezione TLS. Continuare a leggere per scoprire come è possibile proteggere tutti i messaggi di posta elettronica nei server locali o partner importanti tramite i *connettori*. 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Come viene utilizzato TLS in Exchange Online tra clienti di Exchange Online

I server di Exchange Online consentono di crittografare sempre le connessioni ad altri server di Exchange Online nei nostri datacenter con TLS 1.2. Quando si invia la posta a un destinatario all'interno dell'organizzazione di Office 365, la posta elettronica viene inviata automaticamente tramite una connessione crittografata utilizzando TLS. Inoltre, tutta la posta elettronica inviata agli altri clienti di Office 365 viene inviata tramite connessioni che vengono crittografate con TLS e protette utilizzando Forward Secrecy.
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Come Office 365 utilizza TLS tra Office 365 ed esterni, partner attendibili

Per impostazione predefinita, Exchange Online USA sempre TLS opportunistico. Questo significa che Exchange Online Cerca sempre di crittografare le connessioni con la versione più sicura di TLS prima, quindi si sposta verso il basso nell'elenco dei cifrari TLS fino a quando non ne trova uno in cui entrambe le parti possono concordare. A meno che non sia stato configurato Exchange Online per garantire che i messaggi a quel destinatario vengano inviati solo tramite connessioni sicure, per impostazione predefinita il messaggio verrà inviato in formato non crittografato se l'organizzazione del destinatario non supporta la crittografia TLS. TLS opportunistico è sufficiente per la maggior parte delle aziende. Tuttavia, per le aziende con requisiti di conformità, ad esempio le organizzazioni mediche, bancarie o governative, è possibile configurare Exchange online in modo da richiedere o forzare TLS. Per istruzioni, vedere [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
Se si decide di configurare TLS tra la propria organizzazione e un'organizzazione partner attendibile, in Exchange Online è possibile utilizzare TLS forzato per creare canali di comunicazione attendibili. TLS forzato richiede che l'organizzazione partner esegua l'autenticazione a Exchange Online con un certificato di sicurezza per inviare la posta all'utente. A tale scopo, il partner dovrà gestire i propri certificati. In Exchange Online, i connettori vengono utilizzati per proteggere i messaggi inviati da accessi non autorizzati prima che giungano al provider di posta elettronica del destinatario. Per informazioni sull'utilizzo dei connettori per configurare il flusso di posta, vedere [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e distribuzioni ibride di Exchange Server

Se si gestisce una distribuzione ibrida di Exchange, per il server di Exchange locale è necessario eseguire l'autenticazione a Office 365 tramite un certificato di sicurezza per inviare posta ai destinatari le cui cassette postali si trovano solo in Office 365. Di conseguenza, è necessario gestire i propri certificati di sicurezza per i server Exchange locali. Inoltre, è necessario archiviare e conservare questi certificati per i server in modo sicuro. Per ulteriori informazioni sulla gestione dei certificati nelle distribuzioni ibride, vedere [requisiti dei certificati per le distribuzioni ibride](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Come configurare TLS forzato per Exchange Online in Office 365

Per i clienti di Exchange Online, affinché TLS forzato sia utilizzato per proteggere tutta la posta elettronica inviata e ricevuta, è necessario configurare più di un connettore che richiede TLS. Sarà necessario un connettore per la posta elettronica inviata alle cassette postali degli utenti e un altro connettore per la posta elettronica inviata dalle cassette postali degli utenti. Creare tali connettori nell'interfaccia di amministrazione di Exchange in Office 365. Per istruzioni, vedere [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Informazioni sul certificato TLS per Exchange Online

Le informazioni sul certificato utilizzate da Exchange Online sono descritte nella tabella seguente. Se il partner commerciale configura TLS forzato sul proprio server di posta elettronica, sarà necessario fornire tali informazioni al partner. Tenere presente che, per motivi di sicurezza, i nostri certificati possono subire delle modifiche di tanto in tanto. È stato implementato un aggiornamento del certificato all'interno dei data center. Il nuovo certificato è valido dal 3 settembre 2018.
  
 **Informazioni aggiornate sul certificato valide dal 3 settembre 2018**
  
|**Attributo**|**Valore**|
|:-----|:-----|
|Autorità di certificazione principale  <br/> |CA radice di GlobalSign-R1 <br/> |
|Nome certificato  <br/> |mail.protection.outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
 **Informazioni sul certificato obsolete valide fino al 3 settembre 2018**
  
Per garantire una transizione graduale, continueremo a fornire le vecchie informazioni sui certificati per il riferimento per un certo tempo, tuttavia, è necessario utilizzare le informazioni del certificato corrente da ora in poi.
  
****

|**Attributo**|**Valore**|
|:-----|:-----|
|Autorità di certificazione principale  <br/> |Baltimore CyberTrust Root  <br/> |
|Nome certificato  <br/> |mail.protection.outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |Microsoft Corporation  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Preparare il nuovo certificato di Exchange Online

Il nuovo certificato viene emesso da un'autorità di certificazione (CA) diversa dal certificato precedente utilizzato da Exchange Online. Di conseguenza, potrebbe essere necessario eseguire alcune azioni per poter utilizzare il nuovo certificato.

Il nuovo certificato richiede la connessione agli endpoint della nuova CA come parte della convalida del certificato. La mancata esecuzione di questa operazione può comportare un impatto negativo sul flusso di posta. Se si proteggono i server di posta elettronica con firewall che consentono solo ai server di posta elettronica di connettersi con determinate destinazioni, è necessario controllare se il server è in grado di convalidare il nuovo certificato. Per confermare che il server può utilizzare il nuovo certificato, eseguire la procedura seguente:

1. Connettersi al server Exchange locale utilizzando Windows PowerShell e quindi eseguire il comando riportato di seguito:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. Nella finestra visualizzata fare clic su **Recupera**.
3. Quando l'utilità completa il controllo, restituisce uno stato. Se lo stato è visualizzato **OK**, il server di posta è in grado di convalidare correttamente il nuovo certificato. In caso contrario, è necessario determinare cosa sta causando la mancata esecuzione delle connessioni. È molto probabile che sia necessario aggiornare le impostazioni di un firewall. L'elenco completo degli endpoint che devono essere accessibili include:
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

In genere, si ricevono automaticamente gli aggiornamenti ai certificati radice tramite Windows Update. Tuttavia, alcune distribuzioni dispongono di una sicurezza aggiuntiva che impedisce l'esecuzione automatica di tali aggiornamenti. In queste distribuzioni bloccate, in cui Windows Update non è in grado di aggiornare automaticamente i certificati radice, è necessario assicurarsi che il certificato della CA radice corretta sia installato eseguendo la procedura seguente:
1.  Connettersi al server Exchange locale utilizzando Windows PowerShell e quindi eseguire il comando riportato di seguito:  
  `certmgr.msc`
2. In **autorità di certificazione/certificati radice attendibili**, verificare che il nuovo certificato sia elencato.

## <a name="get-more-information-about-tls-and-office-365"></a>Ulteriori informazioni su TLS e Office 365

Per un elenco dei gruppi di crittografia supportati, vedere [Technical Reference details about Encryption in Office 365](technical-reference-details-about-encryption.md).
  
[Impostare i connettori per il flusso di posta sicura con un'organizzazione partner](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Connettori con sicurezza della posta elettronica avanzata](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Crittografia in Office 365](encryption.md)
  

