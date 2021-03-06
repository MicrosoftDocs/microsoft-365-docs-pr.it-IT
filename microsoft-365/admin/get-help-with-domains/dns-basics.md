---
title: Informazioni di base sul DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Il Domain Name System mappa i nomi host del computer agli indirizzi IP e la comprensione dei concetti fondamentali relativi al DNS e ai registrar faciliterà la gestione dei domini.
ms.openlocfilehash: 68b9b82d52e9bb2c4105237f0a29e8137623138e
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393908"
---
# <a name="dns-basics"></a>Informazioni di base sul DNS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

I nomi di dominio, ad esempio contoso.com, vengono gestiti mediante un sistema internazionale di registrar e database. Il Domain Name System (DNS) fornisce un mapping tra i nomi host dei computer leggibili e gli indirizzi IP usati dalle apparecchiature di rete. La comprensione dei concetti fondamentali relativi al DNS e ai registrar faciliterà la gestione dei domini.

## <a name="watch-domains--dns-an-overview"></a>Guarda: Domini e DNS: una panoramica
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

I nomi di dominio, ad esempio contoso.com, vengono gestiti mediante un sistema internazionale di registrar e database. Il Domain Name System (DNS) fornisce un mapping tra i nomi host dei computer leggibili e gli indirizzi IP usati dalle apparecchiature di rete. La comprensione dei concetti fondamentali relativi al DNS e ai registrar faciliterà la gestione dei domini.

## <a name="watch-domains--dns-an-overview"></a>Guarda: Domini e DNS: una panoramica
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

I nomi di dominio, ad esempio contoso.com, vengono gestiti mediante un sistema internazionale di registrar e database. Il Domain Name System (DNS) fornisce un mapping tra i nomi host dei computer leggibili e gli indirizzi IP usati dalle apparecchiature di rete. La comprensione dei concetti fondamentali relativi al DNS e ai registrar faciliterà la gestione dei domini.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Che cosa sono i nomi di dominio?

I nomi di dominio vengono usati negli URL e negli indirizzi di posta elettronica e hanno livelli diversi. Ad esempio, mail.contoso.com è un nome di dominio con i tre livelli seguenti:
  
- **.com** è il dominio di primo livello 
    
- **contoso** è il dominio di secondo livello 
    
- **mail** è il dominio di terzo livello 
    
Perché usare un dominio di terzo livello? Ad esempio, si potrebbero volere nomi di dominio diversi per questioni di marketing o per un blog, come blog.contoso.com. In genere ci si limita ad aggiungere un dominio di secondo livello, come contoso.com, da usare con Microsoft, ma è possibile usare anche domini di terzo livello.
  
Per altre informazioni su cosa è possibile fare con i domini per ogni tipo di offerta, vedere la [descrizione dei servizi delle piattaforme Microsoft 365 e Office 365](/office365/servicedescriptions/office-365-platform-service-description/domains).
  
## <a name="understand-dns-record-types"></a>Comprendere i tipi di record DNS

I record DNS archiviati presso un host DNS per il proprio dominio vengono usati per indirizzare il traffico del dominio. La tabella seguente descrive i record DNS usati con maggiore frequenza e ne illustra l’uso.
  
|**Record del server dei nomi (NS)**|**Identifica i server dei nomi autorevoli per un dominio. Se si cambiano i server dei nomi per il dominio, cambia anche la posizione in cui vengono gestiti i record DNS e in cui il sistema DNS cerca le informazioni sui server della posta e altro. Microsoft ha i propri server dei nomi, ma si può decidere di continuare a usare quelli già configurati con il proprio dominio.**|
|:-----|:-----|
|Un record (record dell'indirizzo)  <br/> |Associa un nome di dominio a un indirizzo IP.  <br/> |
|Record CNAME (alias o canonico)  <br/> |Reindirizza un dominio a un altro nel sistema DNS. Quando un server dei nomi esegue la ricerca di un dominio e trova un record CNAME, sostituisce il nome del primo dominio con il CNAME e quindi esegue una ricerca del nuovo nome.  <br/> |
|Record MX (Mail Exchanger)  <br/> |Punta alla destinazione del messaggio di posta elettronica. Contiene anche un campo della priorità per consentire l'invio di posta a server diversi in un ordine di priorità.  <br/> |
|Record SPF (sender policy framework)  <br/> |Un record TXT che consente di prevenire spoofing e phishing di posta elettronica.  <br/> |
|Record SRV (service)  <br/> |Usato da Skype for Business online e Exchange Online per coordinare il flusso di informazioni tra i servizi Microsoft. Ad esempio, i record SRV sono necessari per visualizzare la presenza in Outlook Web App e per usare Skype for Business online, Skype o altri strumenti di messaggistica istantanea con utenti di altre aziende.  <br/> |
|TTL (Time-To-Live)  <br/> |Il periodo di tempo in cui un server dei nomi mantiene un record DNS prima di cercarne una versione aggiornata.  <br/> |
   
## <a name="how-does-dns-work"></a>Come funziona il sistema DNS?

La procedura di configurazione del dominio con un servizio cloud come Microsoft 365 include la modifica o l'aggiunta di [record DNS](dns-basics.md) per il dominio. Queste modifiche sono necessarie a causa del modo in cui Internet usa il DNS (Domain Name System) e i nomi di dominio per indirizzare correttamente la posta elettronica e individuare i siti Web. 
  
La rete Internet è configurata per l'uso del DNS, o Domain Name System, che consente di usare nomi comuni, come contoso.com, per individuare percorsi Internet specifici che sono in realtà serie di numeri difficili da ricordare, chiamati indirizzi IP (Internet Protocol). Gli indirizzi IP hanno un aspetto simile a 70.42.241.42, quindi è evidente che è molto più facile usare un nome di dominio per identificare i percorsi di siti Web e host di posta elettronica.
  
In breve: i record DNS indicano a Internet dove inviare la posta elettronica (ad esempio luca@contoso.com) o trovare siti Web (ad esempio www.contoso.com) che usano un determinato nome di dominio. Se si inseriscono le informazioni giuste nei record DNS appropriati per il proprio dominio, il sistema DNS instrada tutto correttamente, in modo che la posta elettronica, ad esempio, venga recapitata in Microsoft 365 e non altrove.
  
I record DNS di un dominio possono essere utili anche in altre situazioni. Ad esempio, Exchange usa un record DNS che consente ad Outlook di configurare automaticamente una connessione al server di Exchange corretto.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>I record DNS consentono a Internet di indirizzare correttamente la posta elettronica

Come si è già accennato, il DNS essenzialmente indirizza il traffico in Internet, mappando nomi di dominio intuitivi agli indirizzi IP difficili da ricordare. Un record DNS in particolare, denominato record MX, svolge la funzione specifica di invio della posta elettronica all'host corretto. 
  
I record DNS sono come un database di informazioni su un dominio. I record e i relativi valori vengono archiviati in un file di zona, che include un elenco di tutti i record del dominio e il valore corrispondente. Sui siti Web dei registrar e di altri provider di hosting DNS è disponibile un'interfaccia utente che consente di modificare i record nel file di zona del dominio. È lì che si aggiorna il record MX del proprio dominio in modo da recapitare i messaggi di posta elettronica in Microsoft 365.
  
 *Quando si configura il proprio indirizzo di posta elettronica per Microsoft 365, aggiornando il record MX del dominio nel prossimo passaggio, TUTTI i messaggi inviati a quel dominio inizieranno a essere recapitati in Microsoft 365.*  Se altri utenti usano il dominio per la posta elettronica, è necessario configurare le cassette postali di Microsoft 365 per ognuno di essi. 
  
Può sembrare complicato, ma per facilitare la configurazione del dominio di Microsoft 365, ogni singolo passaggio viene illustrato in dettaglio.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>Il DNS indica a Internet dove cercare i siti Web

Quando si digita l'indirizzo di un sito Web, ad esempio www.contoso.com, Internet cerca prima di tutto in uno dei server DNS il record server dei nomi (NS) per contoso.com (in questo caso). Il record NS indica a Internet dove cercare il file di zona che contiene i valori di tutti gli altri record DNS del dominio. I server DNS sono moltissimi e sono tutti connessi tra loro. Questi server interagiscono per tenere traccia di tutti i nomi di dominio registrati, che devono essere univoci, e della posizione dei file di zona di ogni dominio.
  
::: moniker range="o365-worldwide"

Si supponga che il record NS di contoso.com sia "godaddy.com". Internet riconosce che deve cercare in GoDaddy.com il file di zona che elenca tutti gli altri record DNS per contoso.com. I record DNS includono il record MX che indica dove inviare i messaggi di posta elettronica per contoso.com e altri record. Se il valore del record MX è "invia la posta elettronica a Microsoft 365" (anche se lo indica in termini tecnici), è qui che verranno recapitati tutti i messaggi inviati a un indirizzo di posta elettronica di contoso.com, ad esempio luca@contoso.com. Quindi, purché in questa posizione ci sia una cassetta postale con questo nome, il messaggio verrà recapitato.

::: moniker-end

::: moniker range="o365-germany"

Si supponga che il record NS di contoso.com sia "godaddy.com". Internet riconosce che deve cercare in GoDaddy.com il file di zona che elenca tutti gli altri record DNS per contoso.com. I record DNS includono il record MX che indica dove inviare i messaggi di posta elettronica per contoso.com e altri record. Se il valore del record MX è "invia la posta elettronica a Microsoft 365" (anche se lo indica in termini tecnici), è qui che verranno recapitati tutti i messaggi inviati a un indirizzo di posta elettronica di contoso.com, ad esempio luca@contoso.com. Quindi, purché in questa posizione ci sia una cassetta postale con questo nome, il messaggio verrà recapitato.

::: moniker-end

::: moniker range="o365-21vianet"

Si supponga che il record NS di contoso.com sia "hichina.com". Internet riconosce che deve cercare in hichina.com il file di zona che elenca tutti gli altri record DNS per contoso.com. I record DNS includono il record MX che indica dove inviare i messaggi di posta elettronica per contoso.com e altri record. Se il valore del record MX è "invia la posta elettronica a Microsoft 365" (anche se lo indica in termini tecnici), è qui che verranno recapitati tutti i messaggi inviati a un indirizzo di posta elettronica di contoso.com, ad esempio luca@contoso.com. Quindi, purché in questa posizione ci sia una cassetta postale con questo nome, il messaggio verrà recapitato.

::: moniker-end

I valori effettivi che occorre immettere perché questo processo funzioni in Microsoft 365 appaiono già elencati nei diversi passaggi di configurazione del dominio. Se la configurazione viene eseguita manualmente, occorre copiare e incollare i valori nei record DNS corretti (record MX, record CNAME e così via) presso l'host DNS, che potrebbe essere, ma non necessariamente, il registrar.
  
::: moniker range="o365-worldwide"

Il file di zona del dominio può infatti essere archiviato in una posizione diversa dal registrar. Ad esempio, si può registrare il proprio dominio presso un registrar come GoDaddy e affidare la gestione dei record DNS a un altro provider di hosting DNS o di hosting Web. Queste informazioni sono archiviate nei record NS del dominio in modo da indirizzare tutti i server DNS ai percorsi corretti.

::: moniker-end

::: moniker range="o365-germany"

Il file di zona del dominio può infatti essere archiviato in una posizione diversa dal registrar. Ad esempio, si può registrare il proprio dominio presso un registrar come GoDaddy e affidare la gestione dei record DNS a un altro provider di hosting DNS o di hosting Web. Queste informazioni sono archiviate nei record NS del dominio in modo da indirizzare tutti i server DNS ai percorsi corretti.

::: moniker-end

::: moniker range="o365-21vianet"

Il file di zona del dominio può infatti essere archiviato in una posizione diversa dal registrar. Ad esempio, si può registrare il proprio dominio presso un registrar come HiChina e affidare la gestione dei record DNS a un altro provider di hosting DNS o di hosting Web. Queste informazioni sono archiviate nei record NS del dominio in modo da indirizzare tutti i server DNS ai percorsi corretti.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Perché aggiungere un dominio in Microsoft 365?


L'aggiunta di un dominio personalizzato, come fourthcoffee.com, a Microsoft 365 consente di usare indirizzi di posta elettronica e ID utente più corti e familiari con il servizio. Quando si effettua la registrazione per un account Microsoft 365, [si riceve un dominio pronto per l'uso](../setup/domains-faq.yml), che però include "onmicrosoft.com". Molti utenti preferiscono aggiungere il dominio della propria organizzazione o azienda se prevedono di usare Microsoft 365 per la posta elettronica. 
  
> [!NOTE]
> Se si vogliono solo scaricare e usare le app di Microsoft, come Outlook o Word, non è necessario aggiungere il dominio. Vedere [Installare Office nel PC o nel Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
È possibile usare il nome di dominio in Microsoft 365 con la posta elettronica, il sito Web pubblico e l'indirizzo di messaggistica istantanea.
  
- **Posta elettronica:** il nome di dominio consente di personalizzare l'indirizzo di posta elettronica, scegliendone uno più corto e più facile da ricordare rispetto all’ [indirizzo onmicrosoft.com iniziale](../setup/domains-faq.yml)che viene fornito con l'account. Quindi, invece di   luca@contoso.onmicrosoft.com, l'indirizzo di posta elettronica (che è anche l'account aziendale usato per accedere a Microsoft 365) potrebbe essere luca@contoso.com. 
    
- **Sito Web:** se il proprio abbonamento a Microsoft 365 include un sito Web pubblico di SharePoint Online (non più disponibile per l'acquisto), il sito Web pubblico è associato a un indirizzo iniziale simile a contoso-public.sharepoint.com. Se si configura il sito Web per la propria attività commerciale, è possibile usare un nome di dominio personalizzato per rinominare l'indirizzo del sito Web, ad esempio in www.contoso.com. 
    
- **Messaggistica istantanea:** anche l'indirizzo di Skype for Business online può essere personalizzato in modo da usare il nome di dominio, per consentire agli utenti dell'organizzazione di comunicare su Skype for Business online usando un indirizzo più breve e più facile da ricordare (come luca@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>Perché aggiungere un dominio in Microsoft 365?


L'aggiunta di un dominio personalizzato, come fourthcoffee.com, a Microsoft 365 consente di usare indirizzi di posta elettronica e ID utente più corti e familiari con il servizio. Quando si effettua la registrazione per un account Microsoft 365, [si riceve un dominio pronto per l'uso](../setup/domains-faq.yml), che però include "onmicrosoft.com". Molti utenti preferiscono aggiungere il dominio della propria organizzazione o azienda se prevedono di usare Microsoft 365 per la posta elettronica. 
  
> [!NOTE]
> Se si vogliono solo scaricare e usare le app di Microsoft 365, come Outlook o Word, non è necessario aggiungere il dominio. Vedere [Installare Office nel PC o nel Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
È possibile usare il nome di dominio in Microsoft 365 con la posta elettronica, il sito Web pubblico e l'indirizzo di messaggistica istantanea.
  
- **Posta elettronica:** il nome di dominio consente di personalizzare l'indirizzo di posta elettronica, scegliendone uno più corto e più facile da ricordare rispetto all’ [indirizzo onmicrosoft.com iniziale](../setup/domains-faq.yml)che viene fornito con l'account. Quindi, invece di   luca@contoso.onmicrosoft.com, l'indirizzo di posta elettronica (che è anche l'account aziendale usato per accedere a Microsoft 365) potrebbe essere luca@contoso.com. 
    
- **Sito Web:** se il proprio abbonamento include un sito Web pubblico di SharePoint Online (non più disponibile per l'acquisto), il sito Web pubblico è associato a un indirizzo iniziale simile a contoso-public.sharepoint.com. Se si configura il sito Web per la propria attività commerciale, è possibile usare un nome di dominio personalizzato per rinominare l'indirizzo del sito Web, ad esempio in www.contoso.com. 
    
- **Messaggistica istantanea:** anche l'indirizzo di Skype for Business online può essere personalizzato in modo da usare il nome di dominio, per consentire agli utenti dell'organizzazione di comunicare su Skype for Business online usando un indirizzo più breve e più facile da ricordare (come luca@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Record DNS necessari per Microsoft 365

I record DNS necessari per far funzionare Microsoft 365 con il proprio dominio sono numerosi. Oltre a configurare il record MX del dominio per l'invio della posta elettronica a Microsoft 365, occorre configurare record per assicurare la connessione automatica di Outlook al server di Exchange corretto, configurare la messaggistica istantanea e bloccare la posta indesiderata.
  
È possibile [trovare un elenco dei valori](information-for-dns-records.md) per configurare il dominio. Sono disponibili nell'interfaccia di amministrazione di Microsoft 365. 
  
In alternativa, se si prevede una distribuzione, è consigliabile rivedere un elenco di tutti i record DNS necessari per Microsoft 365, con la relativa funzione ed esempi di valori. Vedere [Record DNS esterno per Office 365](../../enterprise/external-domain-name-system-records.md).
  
## <a name="next-steps"></a>Passaggi successivi

Vedere una delle opzioni seguenti: 
  
- Per verificare dove è registrato il dominio, vedere [Trovare il registrar di dominio o il provider di hosting DNS](find-your-domain-registrar.md).
- Scoprire [perché occorre completare i passaggi della procedura guidata](../setup/add-domain.md) prima di usare il dominio con Microsoft 365.

## <a name="related-content"></a>Contenuto correlato

[Domande frequenti sui domini](../setup/domains-faq.yml) (articolo)\
[Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](find-and-fix-issues.md) (articolo)\
[Gestire i domini](index.yml) (pagina di collegamento)