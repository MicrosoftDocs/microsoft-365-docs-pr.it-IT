---
title: Isolamento e controllo di accesso in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: "Riepilogo: spiegazione dell'isolamento e del controllo di accesso nelle varie applicazioni di Microsoft 365."
ms.openlocfilehash: 53f60c09b94bdcc2515bcc5ff70dfbcd47f42bb4
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332329"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolamento e controllo di accesso in Microsoft 365

Azure Active Directory (Azure AD) e Microsoft 365 usano un modello di dati altamente complesso che include decine di servizi, centinaia di entità, migliaia di relazioni e decine di migliaia di attributi. A livello elevato, Azure AD e le directory del servizio sono i contenitori di tenant e destinatari mantenuti sincronizzati con protocolli di replica basati sullo stato. Oltre alle informazioni sulla directory contenute in Azure AD, ognuno dei carichi di lavoro del servizio dispone di una propria infrastruttura di servizi directory.
 
![Sincronizzazione dei dati del tenant di Microsoft 365](../media/office-365-isolation-tenant-data-sync.png)

All'interno di questo modello non esiste una singola origine di dati della directory. Sistemi specifici sono proprietari di singole parti di dati, ma nessun singolo sistema contiene tutti i dati. I servizi di Microsoft 365 collaborano con Azure AD in questo modello di dati. Azure AD è il "sistema di verita' per i dati condivisi, che in genere sono dati di piccole dimensioni e statici usati da ogni servizio. Il modello federato usato in Microsoft 365 e Azure AD offre la visualizzazione condivisa dei dati.

Microsoft 365 usa sia l'archiviazione fisica che l'archiviazione cloud di Azure. Exchange Online (incluso Exchange Online Protection) e Skype for Business usano il proprio spazio di archiviazione per i dati dei clienti. SharePoint Online usa sia l SQL Server di archiviazione di Azure che l'archiviazione di Azure, quindi la necessità di un ulteriore isolamento dei dati dei clienti a livello di archiviazione.

## <a name="exchange-online"></a>Exchange Online

Exchange Online archivia i dati dei clienti all'interno delle cassette postali. Le cassette postali sono ospitate all'interno di database ESE (Extensible Storage Engine) denominati database delle cassette postali. Sono incluse le cassette postali degli utenti, le cassette postali collegate, le cassette postali condivise e le cassette postali delle cartelle pubbliche. Le cassette postali degli utenti includono i contenuti salvati di Skype for Business, ad esempio le cronologie delle conversazioni.

Il contenuto della cassetta postale utente include:

- Messaggi di posta elettronica e allegati di posta elettronica
- Calendario e informazioni sulla disponibilità
- Contatti
- Attività
- Note
- Gruppi
- Dati di inferenza

Ogni database delle cassette postali all'interno di Exchange Online contiene cassette postali di più tenant. Un codice di autorizzazione protegge ogni cassetta postale, anche all'interno di un tenancy. Per impostazione predefinita, solo l'utente assegnato ha accesso a una cassetta postale. L'elenco di controllo di accesso (ACL) che protegge una cassetta postale contiene un'identità autenticata da Azure AD a livello di tenant. Le cassette postali per ogni tenant sono limitate alle identità autenticate nel provider di autenticazione del tenant, che include solo gli utenti di tale tenant. Il contenuto nel tenant A non può in alcun modo essere ottenuto dagli utenti nel tenant B, a meno che non venga esplicitamente approvato dal tenant A.

## <a name="skype-for-business"></a>Skype for Business

Skype for Business archivia i dati in varie posizioni:

- Le informazioni su utenti e account, che includono endpoint di connessione, ID tenant, dial plan, impostazioni di roaming, stato presenza, elenchi contatti e così via, vengono archiviate nei server Di Active Directory skype for Business e in diversi server di database Skype for Business. Gli elenchi contatti vengono archiviati nella cassetta postale di Exchange Online dell'utente se l'utente è abilitato per entrambi i prodotti o sui server Skype for Business se l'utente non lo è. I server di database di Skype for Business non sono partizionati per tenant, ma l'isolamento multi-tenancy dei dati viene applicato tramite il controllo dell'accesso basato sui ruoli (RBAC).
- Il contenuto delle riunioni e i dati caricati vengono archiviati in condivisioni DFS (Distributed File System). Questo contenuto può essere archiviato anche in Exchange Online, se abilitato. Le condivisioni DFS non sono partizionate per tenant. il contenuto è protetto con ACL e la multi-tenancy viene applicata tramite RBAC.
- I record dettagli chiamata, che sono la cronologia delle attività, ad esempio la cronologia delle chiamate, le sessioni di messaggistica istantanea, la condivisione delle applicazioni, la cronologia di messaggistica istantanea e così via, possono essere archiviati anche in Exchange Online, ma la maggior parte dei record dettagli chiamata viene temporaneamente archiviata nei server cdR (Call Detail Record). Il contenuto non viene partizionato per tenant, ma la multi-tenancy viene applicata tramite RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online include diversi meccanismi indipendenti che forniscono l'isolamento dei dati. Gli oggetti vengono archiviati come codice astratto all'interno dei database dell'applicazione. Ad esempio, quando un utente carica un file in SharePoint Online, il file viene disassemblato, convertito nel codice dell'applicazione e archiviato in più tabelle in più database.

Se un utente può ottenere l'accesso diretto all'archiviazione contenente i dati, il contenuto non è interpretabile per un essere umano o un sistema diverso da SharePoint Online. Questi meccanismi includono il controllo di accesso di sicurezza e le proprietà. Tutte le risorse di SharePoint Online sono protette dal codice di autorizzazione e dai criteri RBAC, anche all'interno di una tenancy. L'elenco di controllo di accesso (ACL) che protegge una risorsa contiene un'identità autenticata a livello di tenant. I dati di SharePoint Online per un tenant sono limitati alle identità autenticate dal provider di autenticazione per il tenant.

Oltre agli elenchi di controllo di accesso, una proprietà a livello di tenant che specifica il provider di autenticazione (che è Azure AD specifico del tenant), viene scritta una sola volta e non può essere modificata dopo l'impostazione. Dopo che la proprietà del tenant del provider di autenticazione è stata impostata per un tenant, non può essere modificata con le API esposte a un tenant.

Per ogni tenant viene utilizzato un *SubscriptionId* univoco. Tutti i siti dei clienti sono di proprietà di un tenant e a cui è assegnato *un SubscriptionId* univoco per il tenant. La *proprietà SubscriptionId* di un sito viene scritta una sola volta ed è permanente. Una volta assegnato a un tenant, un sito non può essere spostato in un tenant diverso. SubscriptionId *è* la chiave usata per creare l'ambito di sicurezza per il provider di autenticazione ed è associata al tenant.

SharePoint Online usa la SQL Server e Archiviazione di Azure per l'archiviazione dei metadati del contenuto. La chiave di partizione per l'archivio contenuto *è SiteId* in SQL. Quando si esegue una query SQL, SharePoint Online utilizza un *SiteId* verificato come parte di un controllo *SubscriptionId* a livello di tenant.

SharePoint Online archivia il contenuto dei file crittografati nei BLOB di Microsoft Azure. Ogni farm di SharePoint Online dispone di un proprio account Microsoft Azure e tutti i BLOB salvati in Azure vengono crittografati singolarmente con una chiave archiviata nell'archivio SQL contenuto. Chiave di crittografia protetta nel codice dal livello di autorizzazione e non esposta direttamente all'utente finale. SharePoint Online ha un monitoraggio in tempo reale per rilevare quando una richiesta HTTP legge o scrive dati per più tenant. L'identità *della richiesta SubscriptionId* viene monitorata in base *al SubscriptionId* della risorsa a cui si accede. Le richieste di accesso alle risorse di più tenant non devono mai essere effettuate dagli utenti finali. Le richieste di servizio in un ambiente multi-tenant sono l'unica eccezione. Il crawler di ricerca, ad esempio, esegue il pull delle modifiche al contenuto per un intero database contemporaneamente. Ciò implica in genere l'esecuzione di query sui siti di più tenant in una singola richiesta di servizio, operazione che viene eseguita per motivi di efficienza.

## <a name="teams"></a>Teams

I dati di Teams vengono archiviati in modo diverso, a seconda del tipo di contenuto. 

Per una discussione approfondita, vedere la sessione di [breakout di Ignite](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) sull'architettura di Microsoft Teams.

### <a name="core-teams-customer-data"></a>Dati dei clienti di Teams di base

Se viene effettuato il provisioning del tenant in Australia, Canada, Unione Europea, Francia, Germania, India, Giappone, Sudafrica, Corea del Sud, Svizzera (che include Liechtenstein), Emirati Arabi Uniti, Regno Unito o Stati Uniti, Microsoft archivia i seguenti dati dei clienti in pace solo all'interno di tale posizione:

- Chat di Teams, conversazioni di team e canali, immagini, messaggi di segreteria telefonica e contatti.
- Contenuto del sito di SharePoint Online e i file archiviati all'interno del sito.
- File caricati in OneDrive per l'ambiente di lavoro o dell'istituto di istruzione.

#### <a name="chat-channel-messages-team-structure"></a>Chat, messaggi di canale, struttura del team

Ogni team di Teams è supportato da un gruppo di Microsoft 365 e dal sito di SharePoint e dalla cassetta postale di Exchange. Le chat private (incluse le chat di gruppo), i messaggi inviati come parte di una conversazione in un canale e la struttura di team e canali vengono archiviati in un servizio di chat in esecuzione in Azure. I dati vengono archiviati anche in una cartella nascosta nelle cassette postali di utenti e gruppi per abilitare le funzionalità di Information Protection.

#### <a name="voicemail-and-contacts"></a>Segreteria telefonica e contatti

I messaggi vocali sono archiviati in Exchange. I contatti vengono archiviati nell'archivio dati cloud basato su Exchange. Exchange e l'archivio cloud basato su Exchange forniscono già la residenza dei dati in ognuna delle posizioni geografiche dei datacenter a livello mondiale. Per tutti i team, la segreteria telefonica e i contatti sono archiviati nel paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sudafrica, Corea del Sud, Svizzera (che include Liechtenstein) e Stati Uniti. Per tutti gli altri paesi, i file vengono archiviati negli Stati Uniti, in Europa o Asia-Pacific percorso in base all'affinità tenant.

#### <a name="images-and-media"></a>Immagini ed elementi multimediali

I contenuti multimediali usati nelle chat (ad eccezione delle GIF Giphy che non sono archiviate ma sono un collegamento di riferimento all'URL del servizio Giphy originale, Giphy è un servizio non Microsoft) vengono archiviati in un servizio multimediale basato su Azure distribuito nelle stesse posizioni del servizio chat.

#### <a name="files"></a>File

I file (inclusi OneNote e Wiki) condivisi da un utente in un canale vengono archiviati nel sito di SharePoint del team. I file condivisi in una chat privata o in una chat durante una riunione o una chiamata vengono caricati e archiviati nell'account di OneDrive per l'istituto di istruzione o aziendale dell'utente che condivide il file. Exchange, SharePoint e OneDrive forniscono già la residenza dei dati in ogni area geografica del datacenter internazionale. Pertanto, per i clienti esistenti, tutti i file, i blocchi appunti di OneNote, il contenuto wiki di Teams e le cassette postali che fanno parte dell'esperienza di Teams sono già archiviati nel percorso in base all'affinità del tenant. I file vengono archiviati nel paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sudafrica, Corea del Sud e Svizzera (che include Liechtenstein). Per tutti gli altri paesi, i file vengono archiviati nella posizione USA, Europa o Asia Pacifico in base all'affinità tenant.
