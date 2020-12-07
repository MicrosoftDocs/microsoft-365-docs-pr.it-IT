---
title: Posizioni dei dati per l'Unione europea
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Determinare dove sono archiviati i dati dei clienti Microsoft 365 nell’Unione europea.
ms.openlocfilehash: 78c2ae75656df017631fce0a189f6e25ee44f20f
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527686"
---
# <a name="data-locations-for-the-european-union"></a>Posizioni dei dati per l'Unione europea



## <a name="your-data-is-your-business"></a>I dati dei clienti sono fondamentali

Microsoft riconosce l'importanza di mantenere la privacy e la riservatezza dei dati aziendali. I dati appartengono all'utente, che può accedervi, modificarli o eliminarli in qualsiasi momento. Microsoft non userà i dati senza il consenso dell'utente e, dopo il consenso, userà i dati solo per fornire i servizi che si sono scelti. Se l’utente lascia uno dei servizi, si garantisce la conservazione dei dati personali da parte dell’utente attraverso la rimozione dei dati dai sistemi secondo rigorosi standard e processi. 

>[!Note]
>I dati dei clienti, noti anche come "dati" o "dati commerciali", includono tutti i dati, tra cui testo, audio, video o file di immagine e il software fornito direttamente dall’utente o per conto dell’utente a Microsoft usando i servizi Microsoft Enterprise online, esclusi Microsoft Professional Services. Include il contenuto dei clienti, ossia i dati caricati per la risorsa di archiviazione o l'elaborazione e le app caricate per la distribuzione tramite un servizio cloud Microsoft aziendale. Ad esempio, il contenuto dei cliente includi la posta elettronica e gli allegati di Exchange Online, il contenuto del sito di Microsoft SharePoint Online* o una conversazione di messaggistica istantanea. 
>

## <a name="data-storage-and-processing"></a>Archiviazione ed elaborazione dei dati

Se si usano i servizi di Microsoft 365, si inizia con il presupposto che i clienti aziendali vorrebbero che i propri dati commerciali venissero archiviati ed elaborati poco lontano. Se possibile, si procede in questo modo. Per mantenere i dati nei data center più vicini, archiviare i dati in base alla sede aziendale fornita durante la creazione del tenant. Per scegliere le posizioni di archiviazione importanti per le attività dell'organizzazione, è possibile creare un numero illimitato di tenant per l'organizzazione.  

### <a name="where-eu-data-is-stored"></a>Dove vengono archiviati i dati UE dei clienti

Il data center GEOS è disponibile in Germania e in Francia e consente di archiviare i dati nel proprio paese, se ivi è ubicata l’azienda. I data center dell'Unione europea si trovano in Austria, Finlandia, Francia, Irlanda e Paesi Bassi. I dati dei servizi seguenti verranno ospitati nelle posizioni seguenti in base all'indirizzo di fatturazione scelto: 

| Nome del servizio | Posizione dei tenant creati con un indirizzo di fatturazione in Francia | Posizione dei tenant creati con un indirizzo di fatturazione in Germania | Posizione dei tenant creati con un indirizzo di fatturazione in altri paesi UE |
|:-------|:-----|:-------|:-------|
| Exchange Online | Francia | Germania | Unione Europea |
| OneDrive for Business | Francia | Germania | Unione Europea |
| SharePoint Online | Francia | Germania | Unione Europea |
| Skype for Business | Unione Europea | Unione Europea | Unione Europea |
| Microsoft Teams | Francia | Germania | Unione Europea |
| Office Online e Mobile | Francia | Germania | Unione Europea |
| Exchange Online Protection | Francia | Germania | Unione Europea |
| Intune | Unione Europea | Unione Europea | Unione Europea |
| MyAnalytics | Francia | Germania | Unione Europea |
| Planner | Unione Europea | Unione Europea | Unione Europea |
| Yammer | Unione Europea | Unione Europea | Unione Europea |
| Servizi di OneNote | Francia | Germania | Unione Europea |
| Stream | Unione Europea | Unione Europea | Unione Europea |
| Whiteboard | Unione Europea | Unione Europea | Unione Europea |
| Forms | Unione Europea | Unione Europea | Unione Europea |
||||| 

>[!Note]
>Se si dispone di un abbonamento a Office 365 Education con un indirizzo di fatturazione in Francia o Germania, i dati potrebbero essere archiviati nei data center dell'Unione europea. Per le posizioni dei dati del tenant all'esterno dell'Unione europea, vedere [Dove sono archiviati i dati dei clienti di Microsoft 365](o365-data-locations.md).
>



### <a name="where-eu-data-is-computed"></a>Dove vengono calcolati i dati nell’Unione europea

Quando si inizia a usare uno dei servizi sopraindicati, i calcoli necessari per fornire il servizio per i dati archiviati in uno dei data center europei locali (o nel proprio paese) vengono eseguiti all'interno di tale confine geografico, a meno che non sia necessario un trasferimento temporaneo dei dati per eseguire il calcolo in un data center Microsoft disponibile più lontano. 

Se è necessario un trasferimento temporaneo, si impiegherà sempre crittografia all'avanguardia per il trasferimento e i dati verranno reindirizzati subito dopo alla posizione di archiviazione dati scelta. Questi trasferimenti temporanei vengono effettuati in conformità al diritto europeo applicando le clausole contrattuali standard (SCCs) per i trasferimenti temporanei, insieme alle misure aggiuntive per garantire la protezione dei dati. 

Per altre informazioni, vedere [Clausole del modello dell'Unione europea](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses).

>[!Note]
>Se si sceglie di usare questi servizi, i dati dei clienti di Sway e Workplace Analytics verranno archiviati e calcolati negli Stati Uniti.
>

>[!Note]
>Dove necessario, i servizi di Microsoft 365 potrebbero eseguire query e archiviare parti di informazioni di directory del tenant/dati di identità in aree diverse dall'UE per facilitare alcuni scenari. Ad esempio, in scenari di routing della posta elettronica transregionale, routing e autenticazione delle chiamate, i sistemi Microsoft 365 potrebbero necessitare di alcune informazioni sui destinatari UE per instradare le richieste in modo appropriato. Anche i sistemi Microsoft 365 variano in base alle funzioni di identità e autenticazione di Azure Active Directory. Per altre informazioni, vedere [archiviazione di dati di identità per clienti europei in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-data-storage-eu).
>

## <a name="how-microsoft-protects-your-data"></a>In che modo Microsoft protegge i dati

### <a name="security-measures"></a>Misure di protezione

Microsoft protegge i dati usando più livelli di protocolli di sicurezza e crittografia. Ottenere una panoramica delle funzionalità di sicurezza dei dati Microsoft [nell'articolo Crittografia di Microsoft 365](../compliance/encryption.md).

Per impostazione predefinita, le chiavi gestite di Microsoft proteggono i dati dei clienti. I dati che rimangono permanenti su qualsiasi supporto fisico sono sempre crittografati con protocolli di crittografia conformi a FIPS 140-2. È anche possibile usare le chiavi gestite dal cliente (CMK), [Doppia crittografia](../compliance/double-key-encryption.md)e/o i moduli di sicurezza hardware (HSM) per una maggiore protezione dei dati.

Tutto il traffico dei dati tra i data center è protetto anche con gli standard di sicurezza IEEE 802.1 AE MAC, evitando gli attacchi fisici "Man-in-the-Middle".

Per impedire l'accesso fisico non autorizzato ai data center, vengono impiegati controlli e processi operativi rigorosi che includono videocontrolli continui, personale di sicurezza addestrato e processi specifici, nonché controlli di accesso multifattoriali come smart card o biometrici. Al termine del ciclo vitale, i dischi dati vengono eliminati e distrutti. Se un'unità disco usata per la risorsa di archiviazione subisce un errore hardware o raggiunge la fine del ciclo vitale, viene cancellata o eliminata in tutta sicurezza. I dati nell'unità vengono completamente sovrascritti per assicurare che non sia possibile recuperare i dati con alcun mezzo. Quando tali dispositivi vengono eliminati, vengono triturati e distrutti in linea con il NIST SP 800-88 R1, linee guida per la sanificazione dei supporti. Le registrazioni dell’avvenuta distruzione vengono conservate e riviste nell'ambito del processo di controllo e conformità Microsoft. Tutti i servizi di Microsoft 365 usano i servizi di gestione delle risorse di archiviazione e smaltimento di supporti approvati.

### <a name="technical-controls"></a>Controlli tecnici

Oltre alle protezioni fisiche e tecnologiche, Microsoft adotta misure efficaci per proteggere i dati dei clienti da accessi non autorizzati da parte del personale e dei subappaltatori Microsoft. L'accesso ai dati dei clienti tramite le operazioni Microsoft e il personale di supporto viene negato per impostazione predefinita. Quasi tutte le operazioni di servizio eseguite da Microsoft sono completamente automatizzate e la partecipazione umana è estremamente controllata ed eliminata dai dati dei clienti. 

Solo in rari casi un tecnico Microsoft deve avere accesso ai dati dei clienti. In genere questa operazione è necessaria solo se si richiede assistenza di Microsoft per risolvere un problema del cliente. L'accesso ai dati dei clienti è estremamente limitato dai controlli di accesso basato sui ruoli, dall'autenticazione a più fattori, dalla riduzione al minimo dei dati e da altri controlli. Tutti gli accessi ai dati dei clienti sono registrati in modo rigoroso e Microsoft e terze parti eseguono verifiche regolari, nonché controlli a campione, per attestare che l'accesso è appropriato.

I clienti possono usare le chiavi gestite dai clienti per evitare che i dati siano leggibili in caso di accesso non autorizzato. Sia la crittografia lato server sia quella lato client possono contare sulle chiavi gestite dal cliente o sulle chiavi fornite dai clienti. In entrambi i casi, Microsoft non è in grado di accedere alle chiavi di crittografia e non può decrittografare i dati. Controllo SOC di un revisore accreditato di AICPA due volte all'anno per verificare l'efficacia dei controlli di sicurezza nell'ambito di controllo. Il report di attestazione del SOC 2 di tipo 2 pubblicato dal revisore spiega in quali casi può verificarsi l'accesso ai dati dei clienti e come. 

Oltre a archiviare ed elaborare i dati quando si usa il servizio online, Microsoft genera i dati di servizio per monitorare l'integrità del sistema e per eseguire operazioni di servizio come la risoluzione dei problemi. Come misura di protezione della privacy, Microsoft genera e si basa su identificatori pseudonimi in questo servizio di dati generati per poter distinguere un utente da un altro senza identificare gli utenti effettivi. Gli identificatori pseudonimi non identificano direttamente una persona e le informazioni che consentono di eseguire il mapping degli identificatori pseudonimi agli utenti effettivi sono protette come parte dei dati.

Per altre informazioni, vedere [Chi può accedere ai dati](https://www.microsoft.com/trust-center/privacy/data-access) e in quali termini e [Subprocessori e privacy dei dati](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4qVL2).

## <a name="how-microsoft-handles-government-requests"></a>Come Microsoft gestisce le richieste di enti pubblici

Se un ente pubblico vuole accedere ai dati di un cliente, deve seguire i processi legali applicabili. La richiesta deve essere inviata a Microsoft con un mandato, un ordine del tribunale, una citazione per informazioni sull'abbonato o altri dati non relativi al contenuto. 

- Tutte le richieste devono essere indirizzate ad account e identificatori specifici.  
- Il team addetto alla conformità legale Microsoft esamina tutte le richieste per assicurarsi che siano valide, rifiuta quelle non valide e fornisce solo i dati specificati.  
- Se Microsoft è costretto per legge a divulgare i dati dei clienti, l'utente riceverà subito una notifica e riceverà una copia della richiesta, a meno che non sia legalmente vietato a Microsoft.
- Microsoft effettua una revisione legale locale di ogni richiesta ricevuta secondo le leggi e gli standard locali. Microsoft controlla inoltre periodicamente i processi di selezione in tutto il mondo per assicurare che vengano seguite le procedure giudiziarie locali e che venga applicata la relativa istruzione di esecuzione globale per i diritti umani.

Per altre informazioni sull'impegno di Microsoft per contestare gli ordini in linea con il GDPR dell'UE, vedere [Nuovi passaggi per difendere i dati](https://blogs.microsoft.com/on-the-issues/2020/11/19/defending-your-data-edpb-gdpr/). 

Quando i governi o le autorità delegate all’applicazione della legge inviano una richiesta legale relativa ai dati dei clienti, Microsoft si impegna a garantire la trasparenza e limita il contenuto accessibile. Due volte all'anno Microsoft pubblica il numero di richieste legali relative ai dati dei clienti ricevute dalle autorità delegate all’applicazione della legge. Vedere [Report sulle richieste di applicazione della legge](https://www.microsoft.com/corporate-responsibility/law-enforcement-requests-report). Questo report non divulga le specifiche di una particolare domanda, incluso il cliente in questione. Due volte all'anno pubblichiamo anche i dati sulle richieste legali ricevute dal governo degli Stati Uniti. Vedere [Report sugli ordini di sicurezza nazionale negli Stati Uniti](https://www.microsoft.com/corporate-responsibility/us-national-security-orders-report) per il report più recente.  

Per altre informazioni, vedere [Domande frequenti](https://blogs.microsoft.com/datalaw/our-practices/) relative alle richieste del governo e delle autorità delegate all'applicazione della legge, incluse le domande sul CLOUD act.

## <a name="additional-resources"></a>Risorse aggiuntive
 
- [Protezione dei dati attendibili](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FhZn) offre una panoramica del modo in cui Microsoft protegge i dati quando si usano i Microsoft Online Services e i servizi professionali. È anche consigliabile consultare i [Microsoft Online Services terms (OST) e la Data Protection Addendum (DPA)](https://www.microsoft.com/licensing/product-licensing/products) che regolano l'uso di questi servizi.
- [Richieste dell'interessato per il GDPR in Office 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365) Aiuta a individuare i dati personali o le informazioni personali ed effettuare operazioni su di essi per rispondere alle richieste degli interessati usando prodotti, servizi e strumenti amministrativi di Microsoft 365. 
- [Valutazione d'impatto sulla protezione dei dati: guida per i titolari del trattamento dei dati che utilizzano Microsoft Office 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365) aiuta a determinare se l'organizzazione deve redigere una bozza di DPIA, offre indicazioni su "come", include un documento modello DPIA personalizzabile e fornisce una matrice di elementi del servizio DPIA per molti servizi Microsoft 365.
- [Informazioni sul modo in cui i moduli](https://docs.microsoft.com/learn/paths/audit-safeguard-customer-data/) sono stati concepiti per le persone che addette a controlli, conformità, rischi e ruoli legali, che cercano una comprensione generale, forniscono una panoramica approfondita delle procedure fondamentali di Microsoft 365 per la sicurezza e la privacy per proteggere i dati dei clienti.
- [Offerte per la conformità Microsoft](https://docs.microsoft.com/microsoft-365/compliance/offering-home) illustra come i servizi Microsoft 365 aiutano l’organizzazione a soddisfare gli standard di conformità normativa. 

