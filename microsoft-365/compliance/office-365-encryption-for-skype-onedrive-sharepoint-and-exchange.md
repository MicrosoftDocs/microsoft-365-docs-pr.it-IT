---
title: Crittografia per Skype, OneDrive, SharePoint ed Exchange
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
description: 'Riepilogo: Descrizione della crittografia per Skype, OneDrive, SharePoint e Exchange Online.'
ms.openlocfilehash: 13c46df74861120b6f5c2fbe7132f912ef29dde3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637286"
---
# <a name="encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Crittografia per Skype for Business, OneDrive for Business, SharePoint Online ed Exchange Online

Microsoft 365 è un ambiente altamente sicuro che offre una protezione estesa in più livelli: protezione dei data center fisici, sicurezza della rete, sicurezza dell'accesso, sicurezza delle applicazioni e sicurezza dei dati.

## <a name="skype-for-business"></a>Skype for Business

I dati dei clienti di Skype for business possono essere archiviati a riposo sotto forma di file o presentazioni caricati dai partecipanti alla riunione. Il servizio Web Conferencing Server crittografa i dati dei clienti utilizzando AES con una chiave a 256 bit. I dati dei clienti crittografati sono archiviati in una condivisione file. Ogni parte dei dati del cliente viene crittografata utilizzando una chiave a 256 bit generata casualmente diversa. Quando una parte dei dati del cliente è condivisa in una conferenza, il Web Conferencing Server indica ai client di conferenza di scaricare i dati dei clienti crittografati tramite HTTPS. Invia la chiave corrispondente ai client in modo che i dati del cliente possano essere decrittografati. Il Web Conferencing Server consente inoltre di autenticare i client di conferenza prima che consenta ai client di accedere ai dati dei clienti delle conferenze. Quando si partecipa a una conferenza Web, ogni client di conferenza stabilisce una finestra di dialogo SIP con il componente Focus per le conferenze in esecuzione all'interno del server front-end su TLS per primo. Lo stato attivo per le conferenze passa al client di conferenza un cookie di autenticazione generato da Web Conferencing Server. Il client di conferenza viene quindi connesso al server Web Conferencing che presenta il cookie di autenticazione per essere autenticato dal server.

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online e OneDrive for Business

Tutti i file dei clienti in SharePoint Online sono protetti da chiavi univoche per file che sono sempre esclusive di un singolo tenant. Le chiavi vengono create e gestite dal servizio SharePoint Online o quando la chiave del cliente viene utilizzata, creata e gestita dai clienti. Quando viene caricato un file, la crittografia viene eseguita da SharePoint Online all'interno del contesto della richiesta di caricamento, prima di essere inviata allo spazio di archiviazione di Azure. Quando si scarica un file, SharePoint Online recupera i dati dei clienti crittografati dall'archiviazione di Azure in base all'identificatore univoco del documento e decrittografa i dati dei clienti prima di inviarli all'utente. Lo spazio di archiviazione di Azure non è in grado di decrittografare o addirittura identificare o comprendere i dati del cliente. Tutte le funzioni di crittografia e decrittografia avvengono negli stessi sistemi che applicano l'isolamento del tenant, ovvero Azure Active Directory e SharePoint Online.

Diversi carichi di lavoro in Microsoft 365 archiviano i dati in SharePoint Online, tra cui Microsoft teams, in cui vengono archiviati tutti i file in SharePoint Online e OneDrive for business, che utilizza SharePoint Online per l'archiviazione. Tutti i dati dei clienti archiviati in SharePoint Online sono crittografati (con una o più chiavi AES 256 bit) e distribuiti in tutto il datacenter come indicato di seguito. (Tutti i passaggi di questo processo di crittografia sono convalidati FIPS 140-2 Level 2. Per ulteriori informazioni sulla conformità FIPS 140-2, vedere [conformità fips 140-2](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).

- Ogni file è suddiviso in uno o più blocchi, a seconda delle dimensioni dei file. Ogni blocco viene crittografato utilizzando la propria chiave AES 256 bit univoca.
- Quando un file viene aggiornato, l'aggiornamento viene gestito nello stesso modo: la modifica viene divisa in uno o più blocchi e ogni blocco viene crittografato con una chiave univoca distinta.
- Questi blocchi – file, pezzi di file e Delta di aggiornamento – sono archiviati come BLOB nell'archiviazione di Azure che vengono distribuiti in modo casuale su più account di archiviazione di Azure.
- Il set di chiavi di crittografia per questi blocchi di dati dei clienti è crittografato.

    - Le chiavi utilizzate per crittografare gli oggetti BLOB sono archiviate nel database del contenuto di SharePoint Online.
    - Il database del contenuto è protetto dai controlli di accesso ai database e dalla crittografia a riposo. La crittografia viene eseguita utilizzando la [crittografia Transparent Data Encryption](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde) in [Azure SQL database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview). Il database SQL di Azure è un servizio di database relazionale generico in Microsoft Azure che supporta strutture quali dati relazionali, JSON, spaziali e XML. Questi segreti sono a livello di servizio per SharePoint Online, non a livello di tenant. Questi segreti (a volte denominati tasti Master) sono archiviati in un repository sicuro separato denominato archivio chiavi. Transparent garantisce la sicurezza a riposo sia per il database attivo che per i backup di database e i registri delle transazioni.
    - Quando i clienti forniscono il tasto facoltativo, la chiave del cliente viene archiviata nel Vault Key di Azure e il servizio utilizza la chiave per crittografare una chiave del tenant, utilizzata per crittografare una chiave del sito, che viene quindi utilizzata per crittografare le chiavi a livello di file. In sostanza, viene introdotta una nuova gerarchia di chiavi quando il cliente fornisce una chiave.
- La mappa utilizzata per riassemblare il file è memorizzata nel database del contenuto insieme alle chiavi crittografate, separatamente dalla chiave master necessaria per decrittografarli.
- Ogni account di archiviazione di Azure dispone di credenziali univoche per ogni tipo di accesso (lettura, scrittura, enumerazione ed eliminazione). Ogni set di credenziali è conservato nell'archivio chiavi protetto e viene regolarmente aggiornato. Come descritto in alto, esistono tre tipi diversi di archivi, ognuno con una funzione distinta:
    - I dati dei clienti vengono archiviati come BLOB crittografati nello spazio di archiviazione di Azure. La chiave di ogni blocco di dati dei clienti viene crittografata e memorizzata separatamente nel database del contenuto. I dati del cliente stesso non contengano alcun indizio su come può essere decrittografato.
    - Il database del contenuto è un database SQL Server. Contiene la mappa necessaria per individuare e riassemblare gli oggetti BLOB dei dati del cliente in archiviazione di Azure, nonché le chiavi necessarie per crittografare tali BLOB. Tuttavia, il set di chiavi è crittografato (come spiegato in precedenza) e conservato in un archivio chiave separato.
    - L'archivio chiavi è fisicamente separato dal database del contenuto e dallo spazio di archiviazione di Azure. Contiene le credenziali per ogni contenitore di archiviazione di Azure e la chiave master per il set di chiavi crittografate contenute nel database del contenuto.

Ognuno di questi tre componenti di archiviazione – l'archivio BLOB di Azure, il database del contenuto e l'archivio delle chiavi – è fisicamente separato. Le informazioni contenute in uno dei componenti sono inutilizzabili da sole. Senza accesso a tutti e tre, non è possibile recuperare le chiavi per i blocchi, decrittografare i tasti per renderli utilizzabili, associare le chiavi ai blocchi corrispondenti, decrittografare ogni blocco o ricostruire un documento dai relativi blocchi costitutivi.

I certificati di BitLocker, che proteggono i volumi del disco fisico nei computer nel centro dati, vengono archiviati in un archivio sicuro (l'archivio segreto di SharePoint Online) protetto dalla chiave della farm.

Le chiavi di Transparent che proteggono le chiavi per BLOB sono archiviate in due posizioni:

- Archivio sicuro, in cui sono ospitati i certificati di BitLocker ed è protetto dalla chiave della farm. e
- In un archivio sicuro gestito da database SQL di Azure.

Le credenziali utilizzate per accedere ai contenitori di archiviazione di Azure vengono inoltre conservate nell'archivio segreto di SharePoint Online e delegate a ogni farm di SharePoint online in base alle esigenze. Queste credenziali sono le firme SAS di archiviazione di Azure, con credenziali distinte utilizzate per leggere o scrivere dati e con i criteri applicati in modo che scadano automaticamente ogni 60 giorni. Le credenziali diverse vengono utilizzate per leggere o scrivere dati (non entrambi) e le farm di SharePoint Online non dispongono delle autorizzazioni per l'enumerazione.

> [!NOTE]
> Per i clienti di Office 365 Stati Uniti, i BLOB di dati sono archiviati nell'archivio governativo degli Stati Uniti di Azure. Inoltre, l'accesso alle chiavi di SharePoint online in Office 365 Stati Uniti è limitato al personale di Office 365 che è stato sottoposto a screening specifico. Il personale delle operazioni governative degli Stati Uniti di Azure non ha accesso all'archivio delle chiavi di SharePoint Online utilizzato per crittografare i BLOB di dati.

Per ulteriori informazioni sulla crittografia dei dati in SharePoint Online e OneDrive for business, vedere [crittografia dei dati in OneDrive for business e SharePoint Online](https://technet.microsoft.com/library/dn905447.aspx).

### <a name="list-items-in-sharepoint-online"></a>Voci di elenco in SharePoint Online

Gli elementi di elenco sono parti più piccole dei dati del cliente creati ad-hoc o che possono vivere più dinamicamente all'interno di un sito, ad esempio le righe di un elenco creato dall'utente, i singoli post in un Blog di SharePoint Online o le voci all'interno di una pagina del wiki di SharePoint Online. Gli elementi di elenco sono archiviati nel database del contenuto (database SQL di Azure) e protetti con Transparent.

## <a name="encryption-of-data-in-transit"></a>Crittografia dei dati in transito

In OneDrive for Business e SharePoint Online, esistono due scenari in cui i dati entrano ed escono dai data center.

- **Comunicazione client con il server** -comunicazione a SharePoint Online e OneDrive for business su Internet utilizza connessioni TLS.
- **Spostamento dei dati tra i datacenter** : il motivo principale per spostare i dati tra i datacenter è la replica geografica per abilitare il ripristino di emergenza. Ad esempio, i registri transazioni di SQL Server e le differenze dell'archiviazione BLOB viaggiano lungo questa pipe. Mentre questi dati vengono già trasmessi utilizzando una rete privata, sono ulteriormente protetti mediante la migliore crittografia.

## <a name="exchange-online"></a>Exchange Online

Exchange Online utilizza BitLocker per tutti i dati delle cassette postali e la configurazione di BitLocker è descritta in [BitLocker per la crittografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md). Crittografia a livello di servizio crittografa tutti i dati delle cassette postali a livello di cassetta postale. 

Oltre alla crittografia dei servizi, Microsoft 365 supporta la chiave del cliente, che si basa sulla crittografia del servizio. Customer Key è un'opzione di chiave gestita da Microsoft per la crittografia del servizio Exchange Online, che è anche nella roadmap di Microsoft. Questo metodo di crittografia garantisce una maggiore protezione non garantita da BitLocker, in quanto fornisce la separazione degli amministratori del server e le chiavi di crittografia necessarie per la decrittografia dei dati e poiché la crittografia viene applicata direttamente ai dati (in contrasto con BitLocker, che applica la crittografia sul volume del disco logico), i dati dei clienti copiati da un server Exchange restano crittografati.

L'ambito della crittografia del servizio Exchange Online è costituito dai dati dei clienti archiviati in Rest all'interno di Exchange Online. (Skype for business archivia quasi tutti i contenuti generati dall'utente all'interno della cassetta postale di Exchange Online dell'utente e quindi eredita la caratteristica di crittografia dei servizi di Exchange Online).
