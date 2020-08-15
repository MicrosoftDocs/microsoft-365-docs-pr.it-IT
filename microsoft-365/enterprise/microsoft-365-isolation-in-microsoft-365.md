---
title: Isolamento e controllo di accesso in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
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
description: "Sintesi: una spiegazione dell'isolamento e del controllo di accesso all'interno delle diverse applicazioni di Microsoft 365."
ms.openlocfilehash: 40a1f1d93fe34333366e456cc006ab2d1c700a83
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691282"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolamento e controllo di accesso in Microsoft 365

Azure Active Directory (Azure AD) e Microsoft 365 utilizzano un modello di dati di elevata complessità che include decine di servizi, centinaia di entità, migliaia di relazioni e decine di migliaia di attributi. A livello elevato, Azure AD e le directory del servizio sono contenitori di tenant e destinatari mantenuti sincronizzati tramite protocolli di replica basati sullo stato. Oltre alle informazioni sulla directory conservate all'interno di Azure AD, ognuno dei carichi di lavoro del servizio ha una propria infrastruttura di servizi directory.
 
![Sincronizzazione dei dati di Microsoft 365 tenant](../media/office-365-isolation-tenant-data-sync.png)

All'interno di questo modello non esiste un'unica origine di dati di directory. I sistemi specifici specificano singoli pezzi di dati, ma nessun singolo sistema contiene tutti i dati. Microsoft 365 Services coopera con Azure AD in questo modello di dati. Azure AD è il "sistema di verità" per i dati condivisi, che in genere sono dati di piccole dimensioni e statici utilizzati da tutti i servizi. Il modello federato utilizzato in Microsoft 365 e Azure AD fornisce la visualizzazione condivisa dei dati.

Microsoft 365 utilizza lo spazio di archiviazione fisico e lo spazio di archiviazione cloud di Azure. Exchange Online (incluso Exchange Online Protection) e Skype for business utilizzano la propria archiviazione per i dati dei clienti. SharePoint Online utilizza l'archiviazione di SQL Server e lo spazio di archiviazione di Azure, quindi la necessità di un ulteriore isolamento dei dati del cliente a livello di archiviazione.

## <a name="exchange-online"></a>Exchange Online

Exchange Online memorizza i dati dei clienti all'interno delle cassette postali. Le cassette postali sono ospitate all'interno dei database ESE (Extensible Storage Engine) chiamati database delle cassette postali Sono incluse le cassette postali utente, le cassette postali collegate, le cassette postali condivise e le cartelle pubbliche. Le cassette postali degli utenti includono il contenuto salvato di Skype for business, ad esempio le storie di conversazione.

Il contenuto della cassetta postale dell'utente include:

- Messaggi di posta elettronica e allegati e-mail
- Informazioni sulla disponibilità e sul calendario
- Contatti
- Attività
- Note
- Gruppi
- Dati di inferenza

Ogni database delle cassette postali in Exchange Online contiene cassette postali provenienti da più tenant. Un codice di autorizzazione protegge ogni cassetta postale, anche all'interno di una locazione. Per impostazione predefinita, solo l'utente assegnato ha accesso a una cassetta postale. L'elenco di controllo di accesso (ACL, Access Control List) che protegge una cassetta postale contiene un'identità autenticata da Azure AD a livello di tenant. Le cassette postali per ogni tenant sono limitate alle identità autenticate con il provider di autenticazione del tenant, che include solo gli utenti di tale tenant. Il contenuto del tenant a non può in alcun modo essere ottenuto dagli utenti nel tenant B, a meno che non sia esplicitamente approvato dal tenant A.

## <a name="skype-for-business"></a>Skype for Business

Skype for business archivia i dati in vari punti:

- Le informazioni sull'utente e sugli account, che includono gli endpoint di connessione, gli ID tenant, i dial plan, le impostazioni di roaming, lo stato di presenza, gli elenchi di contatti e così via, vengono archiviati nei server Skype for business Active Directory e in vari server di database di Skype for business. Gli elenchi di contatti vengono archiviati nella cassetta postale di Exchange Online dell'utente se l'utente è abilitato per entrambi i prodotti o su server Skype for business se l'utente non lo è. I server di database di Skype for business non sono partizionati per-tenant, ma l'isolamento dei dati in più locazioni viene applicato tramite il controllo di accesso basato sui ruoli (RBAC).
- Il contenuto delle riunioni e i dati caricati sono archiviati in condivisioni di file System (DFS) distribuiti. Questo contenuto può anche essere archiviato in Exchange Online se abilitato. Le condivisioni DFS non sono partizionate per-tenant. il contenuto è protetto con gli elenchi di controllo di accesso e la multilocazione viene applicata tramite RBAC.
- I record dettagli chiamata, ovvero la cronologia delle attività, ad esempio la cronologia delle chiamate, le sessioni di messaggistica istantanea, la condivisione di applicazioni, la cronologia di messaggistica istantanea e così via, possono essere archiviati anche in Exchange Online, ma la maggior parte dei record dettagli chiamata è temporaneamente memorizzata nei server registrazione dettagli chiamata (CDR). Il contenuto non viene partizionato per tenant, ma viene applicato tramite RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online dispone di diversi meccanismi indipendenti che forniscono l'isolamento dei dati. Archivia gli oggetti come codice astratto all'interno dei database dell'applicazione. Ad esempio, quando un utente carica un file in SharePoint Online, il file viene disassemblato, convertito nel codice dell'applicazione e archiviato in più tabelle tra più database.

Se un utente può accedere direttamente allo spazio di archiviazione contenente i dati, il contenuto non può essere interpretato da un essere umano o da un sistema diverso da SharePoint Online. Tali meccanismi includono il controllo dell'accesso alla sicurezza e le proprietà. Tutte le risorse di SharePoint Online sono protette dal codice di autorizzazione e dai criteri RBAC, anche all'interno di una locazione. L'elenco di controllo di accesso (ACL, Access Control List) che protegge una risorsa contiene un'identità autenticata a livello di tenant. I dati di SharePoint Online per un tenant sono limitati alle identità autenticate dal provider di autenticazione per il tenant.

Oltre agli elenchi ACL, una proprietà a livello di tenant che specifica il provider di autenticazione (ovvero Azure AD specifico del tenant), viene scritta una sola volta e non può essere modificata dopo l'impostazione. Dopo aver impostato la proprietà tenant del provider di autenticazione per un tenant, non è possibile modificarla utilizzando le API esposte a un tenant.

Per ogni tenant viene utilizzato un *SubscriptionId* univoco. Tutti i siti dei clienti sono di proprietà di un tenant e sono assegnati a un *SubscriptionId* univoco per il tenant. La proprietà *SubscriptionId* di un sito viene scritta una volta ed è permanente. Una volta assegnata a un tenant, un sito non può essere spostato in un altro tenant. *SubscriptionId* è la chiave utilizzata per creare l'ambito di sicurezza per il provider di autenticazione ed è associato al tenant.

SharePoint Online utilizza SQL Server e lo spazio di archiviazione di Azure per l'archiviazione dei metadati del contenuto. La chiave di partizione per l'archivio di contenuto è *siteID* in SQL. Quando si esegue una query SQL, SharePoint Online utilizza un *siteID* verificato come parte di un controllo *SubscriptionId* a livello di tenant.

SharePoint Online archivia il contenuto del file crittografato nei BLOB di Microsoft Azure. Ogni farm di SharePoint Online dispone di un proprio account di Microsoft Azure e tutti gli oggetti BLOB salvati in Azure vengono crittografati singolarmente con una chiave memorizzata nell'archivio di contenuto SQL. La chiave di crittografia protetta nel codice dal livello di autorizzazione e non esposta direttamente all'utente finale. SharePoint Online ha Monitoring in tempo reale per rilevare quando una richiesta HTTP legge o scrive i dati per più di un tenant. La richiesta Identity *SubscriptionId* viene registrata in base alla *SubscriptionId* della risorsa a cui si accede. Le richieste di accesso alle risorse di più tenant non devono mai essere eseguite dagli utenti finali. Le richieste di servizio in un ambiente multi-tenant sono l'unica eccezione. Ad esempio, il crawler di ricerca estrae tutte le modifiche del contenuto per un intero database contemporaneamente. Questo comporta di solito l'esecuzione di query su siti di più tenant in una singola richiesta di servizio, operazione eseguita per motivi di efficienza.

## <a name="teams"></a>Teams

I dati dei team vengono archiviati in modo diverso, a seconda del tipo di contenuto. 

Consultare la [sessione Ignite breakout su Microsoft teams Architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) per una discussione approfondita.

### <a name="core-teams-customer-data"></a>Dati dei clienti del team di base

Se il tenant è provisioning in Australia, Canada, Unione europea, Francia, Germania, India, Giappone, Sud Africa, Corea del sud, Svizzera (che include il Liechtenstein), Emirati Arabi Uniti, Regno Unito o Stati Uniti, Microsoft archivia i seguenti dati dei clienti a riposo solo all'interno di tale percorso:

- Chat Team, conversazioni di team e di canale, immagini, messaggi vocali e contatti.
- Contenuto del sito di SharePoint Online e i file archiviati all'interno del sito.
- File caricati in OneDrive per il lavoro o la scuola.

#### <a name="chat-channel-messages-team-structure"></a>Chat, messaggi di canale, struttura del team

Ogni team in teams è affiancato da un gruppo di Microsoft 365 e dal relativo sito di SharePoint e dalla cassetta postale di Exchange. Chat private (incluse le chat di gruppo), i messaggi inviati come parte di una conversazione in un canale e la struttura di team e canali sono archiviati in un servizio chat in esecuzione in Azure. I dati vengono archiviati anche in una cartella nascosta nelle cassette postali di utenti e gruppi per abilitare le funzionalità di protezione delle informazioni.

#### <a name="voicemail-and-contacts"></a>Segreteria telefonica e contatti

I messaggi vocali vengono archiviati in Exchange. I contatti sono archiviati nell'archivio dati del cloud basato su Exchange. Exchange e l'archivio cloud basato su Exchange forniscono già la residenza dei dati in ognuna delle centrali del datacenter GEOS. Per tutti i team, la segreteria telefonica e i contatti vengono archiviati in-Country per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sud Africa, Corea del sud, Svizzera (che include il Liechtenstein) e Stati Uniti. Per tutti gli altri paesi, i file vengono archiviati nella posizione Stati Uniti, Europa o Asia-Pacifico in base all'affinità tenant.

#### <a name="images-and-media"></a>Immagini e supporti

Supporto utilizzato nelle chat (ad eccezione di Giphy gif che non sono archiviate ma sono un collegamento di riferimento all'URL del servizio di Giphy originale, Giphy è un servizio non Microsoft) è archiviato in un servizio multimediale basato su Azure distribuito negli stessi percorsi del servizio chat.

#### <a name="files"></a>File

File (inclusi OneNote e wiki) in cui una persona condivide un canale viene archiviata nel sito di SharePoint del team. I file condivisi in una chat privata o in una chat durante una riunione o una chiamata vengono caricati e archiviati nell'account OneDrive for Work o School dell'utente che condivide il file. Exchange, SharePoint e OneDrive già forniscono la residenza dei dati in ciascuna delle centrali geoglobali GEOS. Pertanto, per i clienti esistenti, tutti i file, i blocchi appunti di OneNote, il contenuto wiki di team e le cassette postali che fanno parte dell'esperienza teams sono già archiviati nel percorso basato sull'affinità tenant. I file vengono archiviati in un paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sud Africa, Corea del sud e Svizzera (che include il Liechtenstein). Per tutti gli altri paesi, i file vengono archiviati nella posizione Stati Uniti, Europa o Asia Pacific in base all'affinità tenant.
