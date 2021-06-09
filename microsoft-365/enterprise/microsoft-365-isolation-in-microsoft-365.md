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

Azure Active Directory (Azure AD) e Microsoft 365 usano un modello di dati estremamente complesso che include decine di servizi, centinaia di entità, migliaia di relazioni e decine di migliaia di attributi. A livello elevato, Azure AD e le directory del servizio sono i contenitori di tenant e destinatari mantenuti sincronizzati utilizzando protocolli di replica basati sullo stato. Oltre alle informazioni sulla directory contenute in Azure AD, ognuno dei carichi di lavoro del servizio dispone di una propria infrastruttura di servizi directory.
 
![Microsoft 365 sincronizzazione dei dati del tenant](../media/office-365-isolation-tenant-data-sync.png)

All'interno di questo modello non esiste una singola origine di dati della directory. Sistemi specifici sono proprietari di singole parti di dati, ma nessun singolo sistema contiene tutti i dati. Microsoft 365 collaborano con Azure AD in questo modello di dati. Azure AD è il "sistema di verita' per i dati condivisi, che in genere sono dati di piccole dimensioni e statici usati da ogni servizio. Il modello federato usato in Microsoft 365 e Azure AD fornisce la visualizzazione condivisa dei dati.

Microsoft 365 usa sia l'archiviazione fisica che l'archiviazione cloud di Azure. Exchange Online (inclusi Exchange Online Protection) e Skype for Business utilizzare il proprio spazio di archiviazione per i dati dei clienti. SharePoint Online usa sia SQL Server di archiviazione che Archiviazione di Azure, quindi la necessità di un ulteriore isolamento dei dati dei clienti a livello di archiviazione.

## <a name="exchange-online"></a>Exchange Online

Exchange Online i dati dei clienti all'interno delle cassette postali. Le cassette postali sono ospitate all'interno di database ESE (Extensible Archiviazione Engine) denominati database delle cassette postali. Sono incluse le cassette postali degli utenti, le cassette postali collegate, le cassette postali condivise e le cassette postali delle cartelle pubbliche. Le cassette postali degli utenti includono Skype for Business contenuti salvati, ad esempio le cronologie delle conversazioni.

Il contenuto della cassetta postale utente include:

- Messaggi di posta elettronica e allegati di posta elettronica
- Calendario e informazioni sulla disponibilità
- Contatti
- Attività
- Note
- Gruppi
- Dati di inferenza

Ogni database delle cassette postali Exchange Online contiene cassette postali di più tenant. Un codice di autorizzazione protegge ogni cassetta postale, anche all'interno di una tenancy. Per impostazione predefinita, solo l'utente assegnato ha accesso a una cassetta postale. L'elenco di controllo di accesso (ACL) che protegge una cassetta postale contiene un'identità autenticata da Azure AD a livello di tenant. Le cassette postali per ogni tenant sono limitate alle identità autenticate nel provider di autenticazione del tenant, che include solo gli utenti di tale tenant. Il contenuto nel tenant A non può in alcun modo essere ottenuto dagli utenti nel tenant B, a meno che non venga esplicitamente approvato dal tenant A.

## <a name="skype-for-business"></a>Skype for Business

Skype for Business i dati vengono archiviati in diverse posizioni:

- Le informazioni su utenti e account, che includono endpoint di connessione, ID tenant, dial plan, impostazioni mobili, stato presenza, elenchi contatti e così via, vengono archiviate nei server Active Directory di Skype for Business e in vari server di database Skype for Business. Gli elenchi contatti vengono archiviati nella cassetta postale Exchange Online'utente se l'utente è abilitato per entrambi i prodotti o nei server Skype for Business se l'utente non lo è. Skype for Business server di database non sono partizionati per tenant, ma l'isolamento multi-tenancy dei dati viene applicato tramite il controllo dell'accesso basato sui ruoli (RBAC).
- Il contenuto delle riunioni e i dati caricati vengono archiviati in condivisioni DFS (Distributed File System). Questo contenuto può anche essere archiviato in Exchange Online se abilitato. Le condivisioni DFS non sono partizionate per tenant. il contenuto è protetto con gli ACL e la multi-tenancy viene applicata tramite RBAC.
- I record dettagli chiamata, che sono la cronologia attività, ad esempio la cronologia delle chiamate, le sessioni di messaggistica istantanea, la condivisione applicazioni, la cronologia messaggistica istantanea e così via, possono essere archiviati anche in Exchange Online, ma la maggior parte dei record dettagli chiamata viene temporaneamente archiviata nei server cdR (Call Detail Record). Il contenuto non viene partizionato per tenant, ma la multi-tenancy viene applicata tramite RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online ha diversi meccanismi indipendenti che forniscono l'isolamento dei dati. Gli oggetti vengono archiviati come codice astratto all'interno dei database dell'applicazione. Ad esempio, quando un utente carica un file in SharePoint Online, il file viene disassemblato, convertito in codice dell'applicazione e archiviato in più tabelle in più database.

Se un utente può ottenere l'accesso diretto all'archiviazione contenente i dati, il contenuto non è interpretabile per un essere umano o qualsiasi sistema diverso da SharePoint Online. Questi meccanismi includono il controllo di accesso di sicurezza e le proprietà. Tutte SharePoint online sono protette dal codice di autorizzazione e dal criterio RBAC, incluso all'interno di una tenancy. L'elenco di controllo di accesso (ACL) che protegge una risorsa contiene un'identità autenticata a livello di tenant. SharePoint I dati online per un tenant sono limitati alle identità autenticate dal provider di autenticazione per il tenant.

Oltre agli elenchi di controllo di accesso, una proprietà a livello di tenant che specifica il provider di autenticazione (che è Azure AD specifico del tenant), viene scritta una sola volta e non può essere modificata una volta impostata. Dopo aver impostato la proprietà del tenant del provider di autenticazione per un tenant, non può essere modificata utilizzando le API esposte a un tenant.

Per ogni tenant viene utilizzato un *Valore SubscriptionId* univoco. Tutti i siti dei clienti sono di proprietà di un tenant e a cui viene *assegnato un SubscriptionId* univoco per il tenant. La *proprietà SubscriptionId* in un sito viene scritta una sola volta ed è permanente. Una volta assegnato a un tenant, un sito non può essere spostato in un tenant diverso. *SubscriptionId è* la chiave utilizzata per creare l'ambito di sicurezza per il provider di autenticazione ed è associata al tenant.

SharePoint Online usa SQL Server e Archiviazione di Azure per l'archiviazione dei metadati del contenuto. La chiave di partizione per l'archivio del contenuto *è SiteId* in SQL. Quando si esegue una query SQL, SharePoint Online usa un *SiteId* verificato come parte di un controllo *SubscriptionId* a livello di tenant.

SharePoint Online archivia il contenuto dei file crittografati in Microsoft Azure BLOB. Ogni farm SharePoint Online ha un proprio account Microsoft Azure e tutti i BLOB salvati in Azure vengono crittografati singolarmente con una chiave archiviata nell'SQL di contenuto. Chiave di crittografia protetta nel codice dal livello di autorizzazione e non esposta direttamente all'utente finale. SharePoint Online ha un monitoraggio in tempo reale per rilevare quando una richiesta HTTP legge o scrive dati per più tenant. L'identità della richiesta *SubscriptionId* viene rilevata in *base al SubscriptionId* della risorsa a cui si accede. Le richieste di accesso alle risorse di più tenant non devono mai essere effettuate dagli utenti finali. Le richieste di servizio in un ambiente multi-tenant sono l'unica eccezione. Ad esempio, il crawler di ricerca estrae le modifiche al contenuto per un intero database contemporaneamente. Ciò comporta in genere l'esecuzione di query sui siti di più tenant in una singola richiesta di servizio, operazione eseguita per motivi di efficienza.

## <a name="teams"></a>Teams

I Teams vengono archiviati in modo diverso, a seconda del tipo di contenuto. 

Per una discussione approfondita, vedere la sessione di Microsoft Teams [Ignite](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) sull'architettura.

### <a name="core-teams-customer-data"></a>Dati Teams di base dei clienti

Se viene effettuato il provisioning del tenant in Australia, Canada, Unione Europea, Francia, Germania, India, Giappone, Sud Africa, Corea del Sud, Svizzera (che include Liechtenstein), Emirati Arabi Uniti, Regno Unito o Stati Uniti, Microsoft archivia i seguenti dati dei clienti a riposo solo all'interno di tale posizione:

- Teams chat, conversazioni di team e canali, immagini, messaggi di segreteria telefonica e contatti.
- Contenuto del sito di SharePoint Online e i file archiviati all'interno del sito.
- File caricati in OneDrive per lavoro o per istituto di istruzione.

#### <a name="chat-channel-messages-team-structure"></a>Chat, messaggi di canale, struttura del team

Ogni team in Teams è supportato da un gruppo Microsoft 365 e dal relativo sito SharePoint e dalla Exchange cassetta postale. Le chat private (incluse le chat di gruppo), i messaggi inviati come parte di una conversazione in un canale e la struttura di team e canali vengono archiviati in un servizio di chat in esecuzione in Azure. I dati vengono inoltre archiviati in una cartella nascosta nelle cassette postali di utenti e gruppi per abilitare le funzionalità di Information Protection.

#### <a name="voicemail-and-contacts"></a>Segreteria telefonica e contatti

I messaggi vocali vengono archiviati in Exchange. I contatti vengono archiviati in un Exchange di dati cloud basato su cloud. Exchange e l'Exchange cloud basato su Exchange forniscono già la residenza dei dati in ogni data center globale. Per tutti i team, la segreteria telefonica e i contatti sono archiviati nel paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sudafrica, Corea del Sud, Svizzera (che include liechtenstein) e Stati Uniti. Per tutti gli altri paesi, i file vengono archiviati negli Stati Uniti, in Europa o Asia-Pacific in base all'affinità tenant.

#### <a name="images-and-media"></a>Immagini ed elementi multimediali

I supporti usati nelle chat (ad eccezione delle GIF Giphy che non sono archiviate ma che sono un collegamento di riferimento all'URL del servizio Giphy originale, Giphy è un servizio non Microsoft) vengono archiviati in un servizio multimediale basato su Azure distribuito nelle stesse posizioni del servizio chat.

#### <a name="files"></a>File

I file (OneNote e Wiki) condivisi da un utente in un canale vengono archiviati nel sito SharePoint team. I file condivisi in una chat privata o in una chat durante una riunione o una chiamata vengono caricati e archiviati nel OneDrive per l'account aziendale o dell'istituto di istruzione dell'utente che condivide il file. Exchange, SharePoint e OneDrive forniscono già la residenza dei dati in ognuno dei dati geografici del datacenter mondiale. Pertanto, per i clienti esistenti, tutti i file, i blocchi appunti OneNote, il contenuto wiki Teams e le cassette postali che fanno parte dell'esperienza Teams sono già archiviati nel percorso in base all'affinità tenant. I file vengono archiviati nel paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sudafrica, Corea del Sud e Svizzera (che include il Liechtenstein). Per tutti gli altri paesi, i file vengono archiviati nella posizione Usa, Europa o Asia Pacifico in base all'affinità tenant.
