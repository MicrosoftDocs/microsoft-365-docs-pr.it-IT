---
title: Domande frequenti sulla crittografia del servizio con Customer Key per Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: Oltre alla linea di base, la crittografia a livello di volume abilitata tramite BitLocker e Distributed Key Manager (DKM), Office 365 offre un ulteriore livello di crittografia a livello di applicazione per il contenuto dei clienti in Office 365, inclusi i dati di Exchange Online, Skype for business, SharePoint Online e OneDrive for business. Si tratta della crittografia del servizio.
ms.openlocfilehash: 0dbc3839d5dfda98460db70de667e2f469bc1291
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "38686497"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Domande frequenti sulla crittografia del servizio con Customer Key per Office 365

Oltre alla linea di base, la crittografia a livello di volume abilitata tramite BitLocker e Distributed Key Manager (DKM), Office 365 offre un ulteriore livello di crittografia a livello di applicazione per il contenuto dei clienti in Office 365, inclusi i dati di Exchange Online, Skype for business, SharePoint Online e OneDrive for business. Si tratta della crittografia del servizio.
  
La chiave del cliente è basata sulla crittografia del servizio e consente di fornire e controllare le chiavi utilizzate per crittografare i dati a riposo in Office 365 come descritto nelle [condizioni dei servizi online (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx). La chiave del cliente consente di soddisfare gli obblighi di conformità perché si controllano le chiavi di crittografia utilizzate da Office 365 per decrittografare i dati.
  
Per fornire commenti e suggerimenti sulla chiave del cliente, inclusa la documentazione, inviare le proprie idee, consigli e prospettive a customerkeyfeedback@microsoft.com.
  
## <a name="what-is-service-encryption-with-customer-key"></a>Che cos'è la crittografia del servizio con la chiave del cliente?

La chiave Customer migliora la capacità dell'organizzazione di soddisfare le esigenze dei requisiti di conformità che specificano le soluzioni chiave con il provider di servizi cloud. Con il codice "Customer Key", vengono fornite e controllate le chiavi di crittografia per i dati di Office 365 a livello di applicazione. Di conseguenza, è possibile esercitare il controllo e revocare le chiavi dell'organizzazione, se si decide di uscire dal servizio. Se si revocano le chiavi, i dati non sono leggibili per il servizio. La revoca chiave è il primo passaggio sul percorso verso l'eliminazione dei dati.

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>Quali dati di Office 365 a riposo sono coperti dalla chiave del cliente?
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

Sono inclusi i contenuti del sito di SharePoint Online e i file archiviati nel sito e i file caricati in OneDrive for business. Il contenuto delle cassette postali di Exchange Online (corpo di posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica) è incluso. Le conversazioni di testo provenienti da Skype for business sono coperte, ma le registrazioni di Skype meeting broadcast e i caricamenti di contenuto Skype meeting non sono coperti. I caricamenti di Skype meeting broadcast e Skype meeting content sono crittografati insieme a tutti gli altri contenuti di Office 365, ma al momento non offrono il controllo del cliente delle chiavi di crittografia.
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>Qual è la differenza tra la chiave del cliente e portare la propria chiave (BYOK) con Azure Information Protection per Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Entrambe le opzioni consentono di fornire e controllare le proprie chiavi di crittografia; Tuttavia, la crittografia del servizio con la chiave del cliente crittografa i dati a riposo, risiedendo in Office 365 server at-rest, mentre BYOK con Azure Information Protection per Exchange Online crittografa i dati in transito e fornisce persistente online e offline protezione per i messaggi di posta elettronica e gli allegati per Office 365. La chiave del cliente e BYOK con Azure Information Protection per Exchange Online sono complementari e se si sceglie di usare le chiavi gestite dal servizio Microsoft o le proprie chiavi, la crittografia dei dati a riposo e in transito può fornire una protezione aggiuntiva da attacchi dannosi.
  
BYOK con Azure Information Protection per Exchange Online è disponibile nelle funzionalità di crittografia dei messaggi di Office 365.
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>La crittografia dei messaggi di Office 365 e la propria chiave con Azure Information Protection modifica l'approccio di Microsoft alle richieste di dati di terze parti, ad esempio le citazioni in giudizio?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. La crittografia dei messaggi di Office 365 e l'opzione per fornire e controllare le proprie chiavi di crittografia con Bring your own key (BYOK) per Azure Information Protection non è stato creato per rispondere alle citazioni di polizia. La crittografia dei messaggi di Office 365 con BYOK per AIP è stata progettata per soddisfare i clienti che hanno la necessità di rispettare i propri obblighi di conformità interni o esterni. Microsoft richiede molto sul serio le richieste di terze parti per i dati dei clienti. Come provider di servizi cloud, è sempre favorevole alla privacy dei dati del cliente. Nel caso in cui venga visualizzato un mandato di comparizione, si cerca sempre di reindirizzare la terza parte al cliente per ottenere le informazioni. (Leggere il Blog di Brad Smith: [proteggere i dati dei clienti dallo spionaggio governativo](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Pubblichiamo periodicamente informazioni dettagliate sulla richiesta che riceviamo [qui](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data).
  
Per ulteriori informazioni, vedere il [Centro protezione Microsoft](https://www.microsoft.com/trustcenter/default.aspx) relativo alle richieste di dati di terze parti e alla "divulgazione dei dati del cliente" nelle condizioni per i [servizi online (OST) ](https://www.microsoft.com/Licensing/product-licensing/products.aspx).
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>La crittografia del servizio con la chiave del cliente modifica l'approccio di Microsoft alle richieste di dati di terze parti, ad esempio le citazioni?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. La chiave del cliente non è stata progettata per rispondere alle citazioni di polizia. È stato ideato per i clienti regolamentati per soddisfare gli obblighi di conformità interni o esterni. Microsoft richiede molto sul serio le richieste di terze parti per i dati dei clienti. Come provider di servizi cloud, è sempre favorevole alla privacy dei dati del cliente. Nel caso in cui venga visualizzato un mandato di comparizione, si cerca sempre di reindirizzare la terza parte al cliente per ottenere le informazioni. (Leggere il Blog di Brad Smith: [proteggere i dati dei clienti dallo spionaggio governativo](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Pubblichiamo periodicamente informazioni dettagliate sulla richiesta che riceviamo [qui](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Per ulteriori informazioni, vedere il [Centro protezione Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) relativo alle richieste di dati di terze parti e alla "divulgazione dei dati del cliente" nelle condizioni per i [servizi online (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx) . 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>È disponibile il supporto di FastTrack per l'implementazione del codice "Customer Key"?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. FastTrack viene utilizzato solo per raccogliere le informazioni di configurazione del tenant e del servizio necessarie per la registrazione per la chiave del cliente. Le offerte chiave del cliente sono pubblicate tramite FastTrack in modo che sia opportuno che i clienti e i partner inviino queste informazioni necessarie utilizzando lo stesso metodo e per semplificare l'archiviazione dei dati forniti dai clienti nell'offerta.
  
Se è necessario ulteriore supporto oltre la documentazione, contattare Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) o un partner Microsoft per assistenza.
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>Se le chiavi vengono distrutte, come è possibile eseguire il ripristino?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Il codice di disponibilità fornisce la possibilità di eseguire il ripristino dalla perdita imprevista delle chiavi radice gestite. Se si perdono le chiavi principali, contattare il supporto tecnico Microsoft e Microsoft ti aiuterà nel processo di abilitazione del codice di disponibilità. Si utilizzerà la chiave di disponibilità per eseguire la migrazione a un nuovo criterio di crittografia dei dati con le nuove chiavi provisionate dall'utente. 
  
## <a name="what-is-the-availability-key"></a>Che cos'è la chiave di disponibilità?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La chiave di disponibilità è una chiave radice di cui viene effettuato il provisioning quando si crea un criterio di crittografia dei dati. Il codice di disponibilità è archiviato e protetto all'interno di Office 365 ed è funzionalmente analogo alle due chiavi radice che vengono fornite dall'utente per l'utilizzo con la crittografia del servizio con la chiave del cliente. A differenza delle chiavi fornite e gestite in Azure Key Vault, non è possibile accedere direttamente alla chiave di disponibilità. Lo spazio di archiviazione e il controllo della chiave di disponibilità sono deliberatamente diversi dai tasti del Vault Key di Azure per tre motivi: in primo luogo, la chiave di disponibilità fornisce una funzionalità a disponibilità elevata nel caso in cui i servizi di Office 365 non siano in grado di raggiungere le chiavi ospitate in Azure Key Vault in secondo luogo, il tasto di disponibilità fornisce una funzionalità di "interruzione del vetro" nel caso in cui entrambe le chiavi del Vault Key di Azure siano perse; Infine, la separazione dei controlli logici fornisce una difesa approfondita e protegge dalla perdita di tutte le chiavi da un singolo attacco o da un punto di errore. La responsabilità di proteggere le chiavi, mentre si utilizza una serie di protezioni e processi per la gestione della chiave, riduce la possibilità di perdita o di distruzione di tutte le chiavi (e quindi dei dati). Microsoft fornisce l'autorità esclusiva sulla distruzione del codice di disponibilità. In base alla progettazione, nessuno di Microsoft ha accesso alla chiave di disponibilità, ma è accessibile solo dal codice del servizio di Office 365.
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>Quanti criteri di crittografia dei dati è possibile creare?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for business:** È possibile creare fino a 50 DEPs. 
  
 **SharePoint Online e OneDrive for business:** Una DEP si applica ai dati in una posizione geografica, denominata anche geo. Se si utilizza la caratteristica multi-geo di Office 365, è possibile creare una DEP per Geo. Se non si utilizza multi-Geo, è possibile creare una DEP.
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>È possibile assegnare un criterio di crittografia dei dati prima di eseguire la migrazione di una cassetta postale nel cloud?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Sì. È possibile utilizzare il cmdlet Set-MailUser di Windows PowerShell per assegnare un criterio di crittografia dei dati all'utente prima di eseguire la migrazione della cassetta postale a Office 365. Quando si esegue questa operazione, il contenuto della cassetta postale verrà crittografato utilizzando la funzionalità DEP assegnata al momento della migrazione del contenuto. Questo può essere più efficiente rispetto all'assegnazione di una DEP dopo che la cassetta postale è già stata migrata e quindi in attesa che venga eseguita la crittografia, il che può richiedere ore o eventualmente giorni. 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>Come verificare che la crittografia con la chiave del cliente sia attivata e che Office 365 abbia completato la crittografia con la chiave del cliente.
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for business:** È possibile [connettersi a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) e quindi utilizzare il cmdlet **[Get-MailboxStatistics]** per ogni cassetta postale che si desidera controllare. Nell'output del cmdlet Get-MailboxStatistics, la proprietà _IsEncrypted_ restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** , se non lo è. Se la cassetta postale è crittografata, il valore restituito per la proprietà _DataEncryptionPolicyID_ è il GUID della funzionalità DEP con cui è crittografata la cassetta postale. Per ulteriori informazioni sull'esecuzione di questo cmdlet, vedere [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx) e using PowerShell with Exchange Online. 
  
Se le cassette postali non vengono crittografate dopo aver atteso 72 ore dal momento in cui è stata assegnata la DEP, avviare lo spostamento di una cassetta postale A tale scopo, [connettersi a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) e quindi utilizzare il cmdlet New-MoveRequest e specificare l'alias della cassetta postale come indicato di seguito: 
  
```powershell
New-MoveRequest <alias>
```

 **SharePoint Online e OneDrive for business:** È possibile [connettersi a PowerShell di SharePoint Online](https://technet.microsoft.com/library/fp161372.aspx)e quindi utilizzare il cmdlet **[Get-SPODataEncryptionPolicy]** per controllare lo stato del tenant. La proprietà * * _state_* * restituisce un valore **registrato** se la crittografia a chiave del cliente è abilitata e tutti i file in tutti i siti sono stati crittografati. Se la crittografia è ancora in corso, questo cmdlet fornisce informazioni su quale percentuale di siti è stata completata. 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>Se si desidera passare a un set di chiavi diverso, quanto tempo è necessario per il nuovo set di chiavi per proteggere i dati?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for business:** È possibile richiedere fino a 72 ore per proteggere una cassetta postale in base a un nuovo criterio di crittografia dei dati (DEP) dal momento in cui viene assegnata la nuova funzionalità DEP alla cassetta postale. 
  
 **SharePoint Online e OneDrive for business:** È possibile richiedere fino a quattro ore per rieseguire la crittografia dell'intero tenant dopo che è stata assegnata una nuova chiave. 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>I dati esistenti sono archiviati senza crittografia in qualsiasi momento mentre viene decrittografato o crittografato con la chiave del cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. I dati sono sempre crittografati in rest nel servizio Office 365 con BitLocker e DKM. Per ulteriori informazioni, vedere "informazioni di sicurezza, privacy e conformità per Office 365" e [come Exchange Online protegge i segreti della posta elettronica](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376).
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>Se non si desidera più utilizzare le chiavi di crittografia gestite dal cliente, è possibile passare a chiavi gestite da Microsoft?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for business:** Non ancora. Questo sarà supportato una volta che la crittografia del servizio in Office 365 con le chiavi gestite da Microsoft viene distribuita in senso lato. Si prevede di eseguire il rollback del servizio dopo aver rilasciato la crittografia del servizio con la chiave del cliente. 
  
 **SharePoint Online e OneDrive for business:** Sì. È possibile scegliere di ripristinare le chiavi gestite da Microsoft separatamente per ogni Geo (se si utilizza la caratteristica multi-Geo) o per tutti i dati, se si trova in una singola Geo. 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>Se si perdono le chiavi, quanto tempo è necessario per recuperare la disponibilità del servizio tramite il tasto di ripristino?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for business:** Dopo aver chiamato il tasto disponibilità, le cassette postali saranno accessibili in pochi minuti. 
  
 **SharePoint Online e OneDrive for business:** Questa operazione è proporzionale al numero di siti di cui si dispone. Dopo aver chiamato Microsoft per l'utilizzo della chiave di disponibilità, l'utente sarà completamente online entro circa quattro ore. 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>Come viene utilizzata la chiave di disponibilità con Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Sono disponibili tre modi per utilizzare la chiave di disponibilità con Exchange Online:
  
- Disponibilità del servizio: nel caso in cui le chiavi del Vault Key di Azure siano irraggiungibili.
    
- Azioni avviate dal codice del servizio di Office 365, ad esempio gli spostamenti della creazione o della cassetta postale dell'indice di ricerca.
    
- Recuperare dalla perdita di chiave, ad esempio la perdita di entrambe le chiavi del Vault Key di Azure associate a una singola funzionalità di protezione esecuzione programmi.
    
 **L'utilizzo della chiave di disponibilità per la disponibilità del servizio nelle chiavi del Vault Key di Azure degli eventi non è raggiungibile.**
  
Office 365 utilizza la chiave di disponibilità sia per la disponibilità del servizio che per il ripristino da uno stato di chiave del cliente non integro per Exchange Online. È presente una gerarchia di chiavi utilizzate dal codice "Customer Key". Questa gerarchia è illustrata nella figura seguente.
  
![Un elemento grafico Visualizza la gerarchia delle chiavi nel codice "Customer Key"](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Se entrambe le chiavi di Azure Key Vault di un singolo criterio di crittografia dei dati (DEP, Data Encryption Policy) non sono disponibili, Office 365 può utilizzare il tasto disponibilità per passare a una nuova funzionalità di protezione esecuzione programmi. Office 365 determina se utilizzare la chiave di disponibilità per la disponibilità del servizio in modo diverso a seconda che si tratti di un'attività avviata dall'utente, ad esempio quando un utente Scarica la posta elettronica per il client di Outlook o un'attività avviata dal sistema, ad esempio l'indicizzazione il contenuto delle cassette postali o per le ricerche di eDiscovery ha attivato il processo.
  
Office 365 segue questo processo in risposta alle azioni avviate dall'utente per determinare se utilizzare la chiave di disponibilità per le cassette postali degli utenti:
  
1. Office 365 legge la funzionalità DEP a cui è assegnata la cassetta postale per determinare la posizione delle due chiavi del cliente in Azure Key Vault.
    
2. Office 365 sceglie casualmente una delle due chiavi del cliente dalla DEP e invia una richiesta al Vault Key di Azure per annullare il wrapping del tasto DEP utilizzando il codice "Customer Key".
    
3. Se la richiesta di annullare il wrapping del tasto DEP tramite il tasto Customer ha esito negativo e viene restituito un errore, Office 365 invia una seconda richiesta a Key Vault di Azure, questa volta per istruirlo sull'utilizzo del codice cliente alternativo (secondo).
    
4. Se la seconda richiesta di annullare il wrapping del tasto DEP tramite il tasto Customer ha esito negativo e viene restituito un errore, Office 365 esamina i risultati di entrambe le richieste:
    
  - Se l'esame determina che gli errori non riflettono un'azione esplicita da parte di un'identità del cliente, Office 365 utilizza la chiave di disponibilità per decrittografare il tasto DEP. La chiave DEP viene quindi utilizzata per decrittografare la chiave della cassetta postale e completare la richiesta dell'utente.
    
    In questo caso, il Vault Key di Azure non è in grado di rispondere o irraggiungibile per qualsiasi motivo. Office 365 non consente di determinare se il cliente ha revocato intenzionalmente l'accesso ai tasti.
    
  - Se l'esame indica che è stata eseguita un'azione deliberata per eseguire il rendering delle chiavi del cliente non disponibili, la chiave di disponibilità non verrà utilizzata, la richiesta dell'utente avrà esito negativo e l'utente riceverà un messaggio di errore, ad esempio errori di accesso.
    
    In questo caso, il cliente viene informato del fatto che il servizio è influito e la condizione del codice "Customer Key" non è integro. Ad esempio, se un cliente utilizza una singola funzionalità di protezione per tutte le cassette postali nell'organizzazione, il cliente potrebbe riscontrare un errore diffuso in cui gli utenti non possono accedere alle proprie cassette postali. In questo modo, quando entrambe le chiavi del cliente non sono integre, il cliente viene informato della necessità di correggere la situazione e di ripristinare il servizio in uno stato integro.
    
 **Utilizzo della chiave di disponibilità per le azioni avviate dal codice del servizio di Office 365.**
  
Il codice di servizio di Office 365 ha sempre un token di accesso valido e non può essere bloccato. Di conseguenza, finché il codice di disponibilità non è stato eliminato, può essere utilizzato per le azioni avviate da, o da interno a, Office 365 Service Code, ad esempio la creazione di un indice di ricerca o lo spostamento delle cassette postali.
  
 **Utilizzo della chiave di disponibilità per il ripristino dalla perdita di chiave.**
  
È possibile utilizzare la chiave di disponibilità per eseguire il ripristino dalla perdita di entrambe le chiavi del Vault Key di Azure associate alla stessa funzionalità di protezione esecuzione programmi, come descritto nella sezione risposta alla domanda "se le chiavi vengono distrutte, come è possibile eseguire il ripristino?".
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>Come viene utilizzata la chiave di disponibilità con SharePoint Online e OneDrive for business?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

L'architettura e l'implementazione di SharePoint Online e OneDrive for business per i Key Key e la disponibilità dei clienti sono diverse da Exchange Online e Skype for business.
  
Quando un cliente si sposta su chiavi gestite dal cliente, Office 365 crea un codice a chiave intermedio specifico del tenant. Office 365 crittografa il tick due volte, una volta con ognuna delle chiavi del cliente, e archivia le due versioni crittografate del tick. Vengono memorizzate solo le versioni crittografate del tick e un tick può essere decrittografato solo con le chiavi del cliente. L'oggetto Tick viene quindi utilizzato per crittografare le chiavi del sito, che vengono quindi utilizzate per crittografare le chiavi BLOB. Gli stessi BLOB sono crittografati e archiviati nel servizio di archiviazione BLOB di Microsoft Azure.
  
Office 365 segue questo processo per accedere a un oggetto BLOB contenente i dati del file dei clienti:
  
1. Decrittografare l'elemento tick utilizzando il codice "Customer Key".
    
2. Per decrittografare una chiave del sito, utilizzare l'elemento di crittografia decrittografato.
    
3. Utilizzare la chiave del sito decrittografato per decrittografare una chiave BLOB.
    
4. Utilizzare la chiave BLOB decrittografata per decrittografare il BLOB.
    
Durante la decrittografia di un tipo di codice, Office 365 rilascia due richieste di decrittografia al Vault Key di Azure con una leggera offset. La prima per completare fornisce il risultato, annullando l'altra richiesta.
  
Nel caso in cui il cliente perde l'accesso alle proprie chiavi dei clienti, Office 365 crittografa anche l'oggetto Tick con una chiave di disponibilità e lo archivia insieme all'TIKs crittografato con ogni chiave del cliente. L'utente crittografato con la chiave di disponibilità viene utilizzato solo quando il cliente chiama Microsoft per integrare il percorso di ripristino quando ha perso l'accesso alle chiavi, in modo dannoso o accidentale.
  
Per motivi di disponibilità e scalabilità, le TIKs decrittografate vengono memorizzate nella cache in una memoria limitata nel tempo. Due ore prima che la cache di un sistema di posta in scadenza venga scaduta, Office 365 tenta di decrittografare ogni tick. La decrittografia di TIKs consente di estendere la durata della cache. Se la decrittografia di tick ha esito negativo per un periodo di tempo significativo, Office 365 genera un avviso per notificare l'ingegnerizzazione prima della scadenza della cache. Solo se il cliente chiama Microsoft, Office 365 avvierà l'operazione di ripristino, che implica la decrittografia del tick con la chiave di disponibilità memorizzata nell'archivio segreto di Microsoft e l'onboarding del tenant utilizzando di nuovo il tipo di dati decrittografato e un nuovo set di chiavi del Vault Key di Azure fornite dal cliente.
  
A questo punto, la chiave del cliente è coinvolta nella catena di crittografia e decrittografia dei dati del file di SharePoint Online archiviati nell'archivio BLOB di Azure, ma non elementi o metadati dell'elenco di SharePoint Online archiviati nel database SQL. Office 365 non utilizza la chiave di disponibilità per SharePoint Online o OneDrive for business diversa da quella descritta in alto, ovvero il cliente è stato avviato. L'accesso umano ai dati dei clienti è protetto dall'archivio protetto dei clienti.
  
## <a name="how-is-customer-key-licensed"></a>Come viene concesso in licenza la chiave del cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La chiave del cliente è disponibile nella famiglia di prodotti Office 365 Enterprise, "E5" e la SKU per la conformità avanzata. Inoltre, i clienti devono anche acquistare la licenza appropriata per l'utilizzo di Azure Key Vault.
  
Tutti gli utenti che usufruiscono della chiave del cliente devono essere concessi in licenza se desiderano essere coperti dalla chiave del cliente.
  
Per SharePoint Online, l'amministratore di Office 365 che configura la chiave del cliente deve anche essere concesso in licenza per eseguire la procedura di installazione. Inoltre, gli utenti che traggono vantaggio dalla funzionalità devono essere concessi in licenza: questo include il proprietario del sito e tutti gli utenti che accedono ai file su uno o più siti crittografati con la chiave del cliente. Non è necessario che gli utenti esterni vengano concessi in licenza per accedere ai file su uno o più siti crittografati utilizzando la chiave del cliente.
  
Per Exchange Online, le cassette postali "utente" e "utente di posta" devono essere concessi in licenza. Per tutti gli altri utenti, ad esempio le cassette postali condivise, non è necessario disporre di una licenza per la chiave del cliente. Per verificare la corretta licenza della cassetta postale di Exchange Online, eseguire il cmdlet seguente:
  
```powershell
(Get-Mailbox <alias >).PersistedCapabilities
```

Se la stringa BPOS_S_EquivioAnalytics esiste, la cassetta postale viene adeguatamente concessa. In caso contrario, è necessario applicare la licenza appropriata per utilizzare la caratteristica chiave del cliente per questa cassetta postale.
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>È possibile abilitare la chiave del cliente per una sottoscrizione di valutazione?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Per definizione, le sottoscrizioni di valutazione hanno una durata limitata. Le chiavi di crittografia ospitate nelle sottoscrizioni di valutazione possono essere perse alla fine della durata della prova. Poiché Microsoft non è in grado di impedire ai clienti di inserire importanti dati dei clienti negli abbonamenti di valutazione, è vietato l'utilizzo della chiave del cliente con le sottoscrizioni di valutazione.
  
## <a name="how-much-will-using-customer-key-cost"></a>Quanto verrà utilizzato il costo chiave del cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Oltre alle licenze necessarie per la chiave del cliente, i clienti dovranno pagare un costo per l'utilizzo di Key Vault. In [Azure Key Vault pricing Details](https://azure.microsoft.com/pricing/details/key-vault/) descrive il modello di costo e assisterà alla stima. Non esiste alcun modo per prevedere il costo esatto che un cliente incorrerà perché i modelli di utilizzo variano. L'esperienza ha mostrato che il costo è molto basso e generalmente rientra nell'intervallo compreso tra $0,002 e $0,005 per utente al mese, più il costo dei tasti con backup HSM. Il costo sarà anche variabile in base alla configurazione di registrazione scelta dal cliente e alla quantità di spazio di archiviazione di Azure utilizzata per i log delle chiavi di Azure Key. 
  
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Per iniziare a utilizzare la chiave del cliente, vedere [controllo dei dati in Office 365 utilizzando la chiave del cliente](controlling-your-data-using-customer-key.md).
  

