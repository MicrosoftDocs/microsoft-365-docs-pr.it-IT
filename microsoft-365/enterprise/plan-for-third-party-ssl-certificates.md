---
title: Pianificare i certificati SSL di terze parti per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 'Riepilogo: descrive i certificati SSL necessari per Exchange locale e ibrido, SSO tramite ADFS, servizi Exchange Online e servizi Web Exchange.'
ms.openlocfilehash: f2505a40e87ab36c96c0ed24514420b56d1479d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927489"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Pianificare i certificati SSL di terze parti per Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Per crittografare le comunicazioni tra i client e l'ambiente Microsoft 365, è necessario installare certificati SSL (Secure Socket Layer) di terze parti nei server dell'infrastruttura.

Questo articolo fa parte della pianificazione [della rete e dell'ottimizzazione delle prestazioni per Microsoft 365](./network-planning-and-performance.md).
   
I certificati sono necessari per i componenti Microsoft 365 seguenti:
  
- Exchange in locale
    
- Single #A0 (SSO) (sia per i server federativi Active Directory Federation Services (AD FS) che per i proxy del server federativo AD FS)
    
- Exchange Online servizi, ad esempio individuazione automatica, Outlook via Internet e Exchange Web Services
    
- Server ibrido Exchange
    
## <a name="certificates-for-exchange-on-premises"></a>Certificati per Exchange in locale

Per una panoramica sull'utilizzo dei certificati digitali per rendere sicura la comunicazione tra l'organizzazione di Exchange locale e Exchange Online, vedere l'articolo techNet [Understanding Certificate Requirements](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141)).
  
## <a name="certificates-for-single-sign-on"></a>Certificati per Single Sign-On

Per offrire agli utenti un'esperienza single sign-on semplificata che includa una protezione affidabile, i certificati riportati nella tabella seguente sono necessari nei server federativi o nei proxy server federativi. La tabella seguente è incentrata su Active Directory Federation Services (AD FS), sono inoltre disponibili ulteriori informazioni sull'utilizzo di provider [di identità di terze parti.](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| Tipo di certificato | Descrizione | Informazioni necessarie prima della distribuzione |
|:-----|:-----|:-----|
|**Certificato SSL (denominato anche certificato di autenticazione server)** <br/> |Si tratta di un certificato SSL standard utilizzato per proteggere le comunicazioni tra server federativi, client e computer proxy server federativi.  <br/> |ADFS richiede un certificato SSL. Per impostazione predefinita, ADFS usa il certificato SSL configurato per il sito Web predefinito in Internet Information Services (IIS).  <br/> Il nome soggetto di questo certificato SSL viene utilizzato per determinare il nome del servizio federativo (FS) per ogni istanza di ADFS distribuita. Prendere in considerazione la possibilità di scegliere un nome soggetto per qualsiasi nuovo certificato emesso da un'autorità di certificazione (CA) che rappresenti al meglio il nome della società o dell'organizzazione da Microsoft 365. Questo nome deve essere instradabile su Internet.  <br/>**Attenzione:** ADFS richiede che questo certificato SSL non abbia un nome soggetto senza punto (nome breve).          <br/> **Suggerimento:** Poiché questo certificato deve essere considerato attendibile dai client di ADFS, è consigliabile utilizzare un certificato SSL emesso da una CA pubblica (di terze parti) o da un'autorità di certificazione subordinata a una radice pubblicamente attendibile. ad esempio VeriSign o Thawte.  <br/> |
|**Certificato per la firma di token** <br/> |Si tratta di un certificato X.509 standard che viene utilizzato per firmare in modo sicuro tutti i token e problemi del server federativo e che Microsoft 365 accetta e convalida.  <br/> |Il certificato per la firma di token deve contenere una chiave privata concatenata a una radice attendibile in FS. Per impostazione predefinita, ADFS crea un certificato autofirmato. Tuttavia, a seconda delle esigenze dell'organizzazione, è possibile modificare questo certificato in un certificato emesso dall'autorità di certificazione utilizzando lo snap-in di gestione DI ADFS.  <br/>**Attenzione:** Il certificato per la firma di token è fondamentale per la stabilità di FS. Se il certificato viene modificato, Microsoft 365 notifica della modifica. Se non viene fornita la notifica, gli utenti non possono accedere alle offerte Microsoft 365 servizi.<br/>**Suggerimento:** È consigliabile usare il certificato autofirmato per la firma di token generato da ADFS. In questo modo, questo certificato viene utilizzato per impostazione predefinita. Ad esempio, quando questo certificato sta per scadere, ADFS genererà un nuovo certificato autofirmato.  <br/> |
   
I proxy server federativi richiedono il certificato descritto nella tabella seguente.
  
| Tipo di certificato | Descrizione | Informazioni necessarie prima della distribuzione |
|:-----|:-----|:-----|
|Certificato SSL  <br/> |Si tratta di un certificato SSL standard utilizzato per proteggere le comunicazioni tra un server federativo, un proxy server federativo e i computer client Internet.  <br/> |Questo certificato SSL deve essere associato al sito Web predefinito in IIS prima di poter eseguire correttamente la configurazione guidata proxy server federativo ADFS.  <br/> Questo certificato deve avere lo stesso nome soggetto del certificato SSL configurato nel server federativo nella rete aziendale.  <br/> **Suggerimento:** È consigliabile utilizzare lo stesso certificato di autenticazione server configurato nel server federativo a cui si connette questo proxy server federativo.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certificati per individuazione automatica, Outlook via Internet e sincronizzazione di Active Directory

I server Accesso client Exchange 2013, Exchange 2010, Exchange 2007 e Exchange 2003 richiedono un certificato SSL di terze parti per le connessioni protette per l'individuazione automatica, Outlook via Internet e i servizi di sincronizzazione di Active Directory. È possibile che tale certificato sia già installato nell'ambiente locale.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certificato per un Exchange ibrido

I server ibridi Exchange esterni richiedono un certificato SSL di terze parti per garantire la connettività con il Exchange Online servizio. È necessario ottenere questo certificato dal provider SSL di terze parti.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 Catene di certificati

In questo articolo vengono descritti i certificati che potrebbe essere necessario installare nell'infrastruttura. Per ulteriori informazioni sui certificati installati nei server Microsoft 365, vedere [Microsoft 365 Certificate Chains](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).
  
## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)