---
title: Pianificazione delle risorse aziendali di Microsoft 365 - Architettura di sicurezza
description: Informazioni sulle principali strategie di progettazione per l'architettura Microsoft Enterprise di Alex Shteynberg, Technical Principal Architect di Microsoft.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 00fede86da826b940026b894a4ba2a9774ae4dc2
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771908"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Verso l'identità e oltre: il punto di vista di un architetto

In questo articolo, [Alex Shteynberg,](https://www.linkedin.com/in/alex-shteynberg/)Principal Technical Architect di Microsoft, illustra le principali strategie di progettazione per le organizzazioni aziendali che adottano Microsoft 365 e altri servizi cloud Microsoft.

## <a name="about-the-author"></a>Informazioni sull'autore

![Foto di Alex Shteynberg](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Sono principal Technical Architect presso il [Microsoft Technology Center](https://www.microsoft.com/mtc?rtc=1)di New York. Lavoro principalmente con clienti di grandi dimensioni e requisiti complessi. Il mio punto di vista e le mie opinioni si basano su queste interazioni e potrebbero non essere applicabili a tutte le situazioni. Tuttavia, nella mia esperienza, se possiamo aiutare i clienti con le sfide più complesse, possiamo aiutare tutti i clienti.

In genere lavoro con oltre 100 clienti ogni anno. Anche se ogni organizzazione ha caratteristiche uniche, è interessante vedere tendenze e caratteristiche comuni. Ad esempio, una tendenza è l'interesse per molti clienti nel settore. Dopo tutto, una filiale bancaria può anche essere un bar e un centro community.

Nel mio ruolo, mi concentro sull'aiutare i clienti a raggiungere la soluzione tecnica migliore per raggiungere i loro obiettivi aziendali univoci. Ufficialmente, mi concentro su identità, sicurezza, privacy e conformità. Mi piace il fatto che questi tocchino tutto ciò che facciamo. Mi offre l'opportunità di essere coinvolto nella maggior parte dei progetti. Questo mi mantiene molto occupato e si diverte a questo ruolo.

Io vivo a New York (il migliore!) e mi piace molto la diversità della sua cultura, del suo cibo e delle persone (non del traffico). Mi piace viaggiare quando posso e mi auguriamo di vedere la maggior parte del mondo nella mia vita. Attualmente sono alla ricerca di un viaggio in Africa per informazioni sulla conservazione.

## <a name="guiding-principles"></a>Principi guida

- **La semplicità è spesso migliore:** puoi (quasi) fare qualsiasi cosa con la tecnologia, ma questo non significa che dovresti farlo. Soprattutto nello spazio di sicurezza, molti clienti hanno a che fare con soluzioni più efficaci. Questo [video della conferenza](https://www.youtube.com/watch?v=SOQgABDSYZE) Stripe di Google mi piace per sottolineare questo punto.
- **Persone, processo, tecnologia:** [progettare per le persone](https://en.wikipedia.org/wiki/Human-centered_design) per migliorare il processo, non per la tecnologia. Non esistono soluzioni "perfette". È necessario bilanciare diversi fattori di rischio e le decisioni saranno diverse per ogni azienda. Troppi clienti progettano un approccio che in seguito gli utenti evitano.
- **Concentrati sul "perché" prima e "come" più avanti:** essere il fastidioso vecchio figlio di 7 anni con un milione di domande. Non possiamo arrivare alla risposta giusta se non si conoscono le domande giuste da porre. Molti clienti fanno supposizioni su come devono funzionare le cose invece di definire il problema aziendale. È sempre possibile eseguire più percorsi.
- **Lunga coda delle procedure consigliate precedenti:** è necessario riconoscere che le procedure consigliate cambiano alla velocità della luce. Se hai esaminato Azure AD più di tre mesi fa, è probabile che tu non sia aggiornato. Tutto ciò che si trova qui è soggetto a modifiche dopo la pubblicazione. L'opzione "Migliore" oggi potrebbe non essere la stessa tra sei mesi.

## <a name="baseline-concepts"></a>Concetti di base

Non ignorare questa sezione. Spesso è necessario tornare a questi argomenti, anche per i clienti che usano i servizi cloud da anni.
Purtroppo, la lingua non è uno strumento preciso. Spesso usiamo la stessa parola per indicare concetti diversi o parole diverse per indicare lo stesso concetto. Spesso si usa questo diagramma per stabilire una terminologia di base e un "modello gerarchico".
<br><br>

![Illustrazione di tenant, sottoscrizione, servizio e dati](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Quando impari a imparare a farlo, è meglio iniziare in pool e non in mezzo all'oceano. Non sto cercando di essere tecnicamente accurato con questo diagramma. Si tratta di un modello per illustrare alcuni concetti di base.

Nel diagramma:

- Tenant = un'istanza di Azure AD. Si trova nella "parte superiore" di una gerarchia o livello 1 nel diagramma. Possiamo considerare questo come il "[limite](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" in cui si verifica tutto il resto ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) a parte). Tutti i servizi cloud aziendali Microsoft fanno parte di uno di questi tenant. I servizi consumer sono separati. "Tenant" viene visualizzato nella documentazione come tenant di Office 365, tenant di Azure, tenant WVD e così via. Spesso queste varianti causano confusione per i clienti.
- I servizi/sottoscrizioni, livello 2 nel diagramma, appartengono a un solo tenant. La maggior parte dei servizi SaaS è 1:1 e non può essere spostata senza migrazione. Azure è diverso, è possibile [spostare la fatturazione](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) e/o una [sottoscrizione](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) in un altro tenant. Sono molti i clienti che devono spostare le sottoscrizioni di Azure. Ciò ha varie implicazioni. Gli oggetti esistenti all'esterno della sottoscrizione non vengono spostati (ad esempio, il controllo dell'accesso basato sui ruoli o RBAC di Azure e gli oggetti di Azure AD, inclusi gruppi, app, criteri e così via). Inoltre, alcuni servizi (ad esempio Azure Key Vault, Data Bricks e così via). Non eseguire la migrazione dei servizi senza una buona esigenza aziendale. Alcuni script che possono essere utili per la migrazione sono [condivisi su GitHub.](https://github.com/lwajswaj/azure-tenant-migration)
- Un determinato servizio ha in genere un limite di "sottolivello" o livello 3 (L3). Ciò è utile per comprendere la separazione di sicurezza, criteri, governance e così via. Purtroppo non esiste un nome uniforme che io sappia. Alcuni esempi di nomi per L3 sono: Sottoscrizione di Azure = [risorsa;](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal) Dynamics 365 CE = [istanza](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = area [di lavoro;](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces) Power Apps = [environment](https://docs.microsoft.com/power-platform/admin/environments-overview); E così via.
- Il livello 4 è il luogo in cui si trova il dato effettivo. Questo "piano dati" è un argomento complesso. Alcuni servizi usano Azure AD per RBAC, altri no. Ne parleremo un po' quando verranno trattati gli argomenti relativi alla delega.

Alcuni concetti aggiuntivi su cui si trovano molti clienti (e dipendenti Microsoft) sono confusi o hanno domande su quanto segue:

- Chiunque può [creare](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) molti tenant [senza costi aggiuntivi.](https://azure.microsoft.com/pricing/details/active-directory/) Non è necessario eseguire il provisioning di un servizio al suo interno. Ne ho decine. Ogni nome tenant è univoco nel servizio cloud di Microsoft in tutto il mondo (in altre parole, nessun tenant può avere lo stesso nome). Sono tutti nel formato di TenantName.onmicrosoft.com. Esistono anche processi che creano automaticamente tenant ([tenant non gestiti).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) Ad esempio, ciò può verificarsi quando un utente si i registrazione a un servizio aziendale con un dominio di posta elettronica che non esiste in nessun altro tenant.
- In un tenant gestito, molti [domini DNS](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) possono essere registrati in esso. Questo non modifica il nome del tenant originale. Attualmente non esiste un modo semplice per rinominare un tenant (oltre alla migrazione). Anche se il nome del tenant non è tecnicamente critico in questi giorni, alcuni potrebbero trovarlo limitato.
- È consigliabile riservare un nome tenant per l'organizzazione anche se non si prevede ancora di distribuire alcun servizio. In caso contrario, qualcuno può prenderlo da te e non esiste un processo semplice per riportarlo indietro (stesso problema dei nomi DNS). I hear this way too often from customers. Il nome del tenant deve essere anche un argomento di discussione.
- Se si è proprietari di spazi dei nomi DNS, è necessario aggiungerli tutti ai tenant. In caso contrario, si potrebbe [creare un tenant](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) non gestito con questo nome, causando un'interruzione per [renderlo gestito.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)
- Lo spazio dei nomi DNS (ad esempio contoso.com) può appartenere a un solo tenant. Ciò ha implicazioni per diversi scenari (ad esempio, la condivisione di un dominio di posta elettronica durante una fusione o un'acquisizione e così via). Esiste un modo per registrare un sub DNS (ad esempio div.contoso.com) in un tenant diverso, ma è consigliabile evitarlo. Registrando un nome di dominio di primo livello, si presuppone che tutti i sottodomini appartengano allo stesso tenant. In scenari multi-tenant (vedere di seguito) in genere è consigliabile usare un altro nome di dominio di primo livello (ad esempio contoso.ch o ch-contoso.com).
- Chi deve "possedere" un tenant? Spesso si vedono clienti che non sanno chi è attualmente proprietario del proprio tenant. Questo è un grande contrassegno rosso. Chiamare il supporto tecnico Microsoft al più presto. Proprio come quando un proprietario del servizio (spesso un amministratore di Exchange) è designato per gestire un tenant. Il tenant conterrà tutti i servizi che potrebbero essere necessari in futuro. Il proprietario del tenant deve essere un gruppo che può prendere decisioni per l'abilitazione di tutti i servizi cloud in un'organizzazione. Un altro problema è quando a un gruppo proprietario del tenant viene richiesto di gestire tutti i servizi. Questo non è scalabile per le organizzazioni di grandi dimensioni.
- Non esiste alcun concetto di tenant secondario/super. Per qualche motivo, questo mito continua a ripetersi. Questo vale anche per i tenant [B2C](https://docs.microsoft.com/azure/active-directory-b2c/) di Azure AD. Si sente troppe volte "L'ambiente B2C è nel tenant XYZ" o "Come si sposta il tenant di Azure nel tenant di Office 365?"
- Questo documento si concentra principalmente sul cloud commerciale in tutto il mondo, in quanto è ciò che la maggior parte dei clienti usa. A volte è utile conoscere i [cloud sovrani.](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud) I cloud sovrani hanno implicazioni aggiuntive per discutere di quali sono fuori dall'ambito di questa discussione.

## <a name="baseline-identity-topics"></a>Argomenti relativi all'identità di base

C'è molta documentazione sulla piattaforma di gestione delle identità di Microsoft: Azure Active Directory (Azure AD). Per gli utenti appena avviati, spesso si sente travolgente. Anche dopo aver appreso queste informazioni, tenere il passo con l'innovazione e il cambiamento costanti può essere difficile. Nelle interazioni con i clienti spesso mi ritrovo a fungere da "traduttore" tra gli obiettivi aziendali e gli approcci "Buona, Migliore, Migliore" per affrontare questi argomenti (e le "note di scoglio" umane per questi argomenti). Raramente esiste una risposta perfetta e la decisione "giusta" è un equilibrio di diversi fattori di rischio. Di seguito sono riportate alcune delle domande comuni e delle aree di confusione di cui si tende a discutere con i clienti.

### <a name="provisioning"></a>Provisioning

Azure AD non risolve la mancanza di governance nel mondo delle identità. [La governance delle](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) identità deve essere un elemento critico indipendentemente da qualsiasi decisione del cloud. I requisiti di governance cambiano nel tempo, per questo motivo si tratta di un programma e non di uno strumento.

[Confronto tra Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) e Microsoft Identity [Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) e altre informazioni (terze parti o personalizzate)? Risparmiati un po' di problemi ora e in futuro e vai con Azure AD Connect. Esistono tutti i tipi di smart in questo strumento per affrontare le configurazioni dei clienti particolari e le innovazioni in corso.

Alcuni casi perimetrali che possono guidare verso un'architettura più complessa:

- Ho più foreste ad Active Directory senza connettività di rete tra queste. È disponibile una nuova opzione denominata [Provisioning cloud.](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Non si dispone di Active Directory, né si desidera installarlo. Azure AD Connect può essere configurato per la sincronizzazione [da LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (potrebbe essere necessario un partner).
- È necessario eseguire il provisioning degli stessi oggetti in più tenant. Questo non è tecnicamente supportato, ma dipende dalla definizione di "same".

È consigliabile personalizzare le regole di sincronizzazione predefinite ([oggetti filtro,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [attributi di modifica,](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) [ID di accesso](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)alternativo e così via)? Evitalo! Una piattaforma di identità è importante solo quanto i servizi che la usano. Anche se è possibile eseguire tutti i tipi di configurazioni di base, per rispondere a questa domanda è necessario esaminare l'impatto sulle applicazioni. Se si filtrano gli oggetti abilitati alla posta elettronica, l'elenco indirizzi globale per i servizi online sarà incompleto. se l'applicazione si basa su attributi specifici, l'applicazione di filtri avrà un impatto imprevedibile; E così via. Non si tratta di una decisione del team di identità.

SaaS XYZ supporta il provisioning JIT (Just-in-Time), perché è necessario eseguire la sincronizzazione? Vedere sopra. Molte applicazioni necessitano di informazioni sul "profilo" per la funzionalità. Non è possibile disporre di un elenco indirizzi globale se non sono disponibili tutti gli oggetti abilitati alla posta elettronica. Lo stesso vale per [il provisioning](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) degli utenti nelle applicazioni integrate con Azure AD.

### <a name="authentication"></a>Autenticazione

[Sincronizzazione hash delle password](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) e [autenticazione pass-through](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) e [federazione](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

In genere c'è un acceso [confronto sulla](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) federazione. Più semplice è in genere meglio e quindi usare PHS, a meno che tu non abbia un buon motivo per non usarlo. È inoltre possibile configurare metodi di autenticazione diversi per domini DNS diversi nello stesso tenant. 

Alcuni clienti abilitano la federazione + PHS principalmente per:

- Opzione per [eseguire il fall back](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) (per il ripristino di emergenza) se il servizio federativo non è disponibile.
- Funzionalità aggiuntive (ad esempio: [Azure AD DS)](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)e servizi di sicurezza (ad esempio: [credenziali perse)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- Supporto per i servizi in Azure che non comprendono l'autenticazione federata (ad esempio, [File di Azure).](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)

Spesso i clienti passano attraverso il flusso di autenticazione client per chiarire alcuni degli errori. Il risultato è simile all'immagine seguente, che non è buona come il processo interattivo di arrivare.

![Conversazione di esempio sulla lavagna](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Questo tipo di disegno della lavagna illustra dove vengono applicati i criteri di sicurezza all'interno del flusso di una richiesta di autenticazione. In questo esempio, i criteri applicati tramite Active Directory Federation Service (AD FS) vengono applicati alla prima richiesta di servizio, ma non alle richieste di servizio successive. Questo è almeno un motivo per spostare il più possibile i controlli di sicurezza nel cloud.

Abbiamo insegueto il sodimo del [single sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO) per tutto il tempo che riesco a ricordare. Alcuni clienti ritengono di poter ottenere questo risultato scegliendo il provider di federazione "giusto". Azure AD può aiutare in modo significativo [a abilitare le funzionalità SSO,](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) ma nessun servizio token di sicurezza è magico. Esistono troppi metodi di autenticazione "legacy" ancora utilizzati per le applicazioni critiche. L'estensione di Azure AD [con soluzioni partner](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) può risolvere molti di questi scenari. SSO è una strategia e un percorso. Non è possibile raggiungere questo livello senza passare agli [standard per le applicazioni.](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types) Correlato a questo argomento è un percorso verso [l'autenticazione senza password,](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) che non ha anche una risposta magica.

[L'autenticazione a più](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) fattori (MFA) è essenziale oggi[(per](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) altre informazioni). Aggiungi ad essa [l'analisi del comportamento](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) degli utenti e hai una soluzione che impedisce gli attacchi informatici più comuni. Anche i servizi consumer stanno per richiedere l'autenticazione a più fattori. Tuttavia, ho ancora molti clienti che non vogliono passare agli [approcci di autenticazione](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview) moderna. L'argomento più importante che si sente è che inciderà sugli utenti e sulle applicazioni legacy. A volte un buon inizio può aiutare i clienti a muoversi: Le modifiche [annunciate da](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)Exchange Online. Sono ora disponibili numerosi [report di](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) Azure AD per aiutare i clienti con questa transizione.

### <a name="authorization"></a>Autorizzazione

Per [Wikipedia,](https://en.wikipedia.org/wiki/Authorization)"autorizzare" è definire un criterio di accesso. Molti utenti lo osservano come la possibilità di definire i controlli di accesso a un oggetto (file, servizio e così via). Nell'attuale mondo delle minacce informatiche, questo concetto si sta rapidamente evolvendo in un criterio dinamico in grado di rispondere a vari vettori di minacce e regolare rapidamente i controlli di accesso in risposta a questi. Ad esempio, se si accede al conto corrente bancario da una posizione insolita, si ottengono ulteriori passaggi di conferma. Per affrontare questo problema, è necessario considerare non solo il criterio stesso, ma anche l'ecosistema delle metodologie di rilevamento delle minacce e correlazione dei segnali.

Il motore dei criteri di Azure AD viene implementato usando i [criteri di accesso condizionale.](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Questo sistema dipende dalle informazioni di un'ampia gamma di altri sistemi di rilevamento delle minacce per prendere decisioni dinamiche. Una visualizzazione semplice è simile alla figura seguente:

![Motore dei criteri in Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

La combinazione di tutti questi segnali consente criteri dinamici come questi:

- Se viene rilevata una minaccia nel dispositivo, l'accesso ai dati verrà ridotto al Web solo senza la possibilità di eseguire il download.
- Se si sta scaricando un volume di dati insolitamente elevato, tutto ciò che si scarica verrà crittografato e limitato.
- Se accedi a un servizio da un dispositivo non gestito, ti verrà impedito di accedere a dati altamente riservati, ma potrai accedere a dati senza restrizioni senza la possibilità di copiarlo in un'altra posizione.

Se si accetta questa definizione estesa di autorizzazione, è necessario implementare soluzioni aggiuntive. Le soluzioni implementate dipendono dalla dinamica desiderata per il criterio e dalle minacce di cui si desidera definire la priorità. Alcuni esempi di questi sistemi sono:

- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Che cosa è Microsoft Defender per identità?](https://docs.microsoft.com/azure-advanced-threat-protection/)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/)

Naturalmente, oltre ad Azure AD, diversi servizi e applicazioni dispongono di modelli di autorizzazione specifici. Alcune di queste vengono illustrate più avanti nella sezione relativa alla delega.

### <a name="audit"></a>Audit

Azure AD include funzionalità di controllo e [creazione di report](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) dettagliate. Tuttavia, questa non è in genere l'unica fonte di informazioni necessarie per prendere decisioni relative alla sicurezza. Per ulteriori informazioni su questo argomento, vedere la sezione relativa alla delega.

## <a name="theres-no-exchange"></a>Exchange non è disponibile

Niente paura! Questo non significa che Exchange sia deprecato (o SharePoint e così via). È ancora un servizio di base. Ciò che voglio dire è che, da molto tempo, i provider di tecnologia passano da esperienze utente (UX) a componenti di più servizi. In Microsoft 365, un semplice esempio è "[allegati](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)moderni " in cui gli allegati alla posta elettronica sono archiviati in SharePoint Online o OneDrive for Business.

![Allegare un file a un messaggio di posta elettronica](../media/solutions-architecture-center/modern-attachments.png)

Osservando il client Outlook è possibile vedere molti servizi "connessi" come parte di questa esperienza, non solo Exchange. Sono inclusi Azure AD, Microsoft Search, App, Profilo, conformità e gruppi di Office 365. 

![Interfaccia di Outlook con callout](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Informazioni su [Microsoft Fluid Framework per](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) un'anteprima delle funzionalità future. In anteprima ora, è possibile leggere e rispondere alle conversazioni di Teams direttamente in Outlook. Infatti, il [client Teams](https://products.office.com/microsoft-teams/download-app) è uno degli esempi più importanti di questa strategia. 

Nel complesso, è sempre più difficile tracciare una linea chiara tra Office 365 e altri servizi nei cloud Microsoft. Lo vedo come un grande vantaggio per i clienti, perché possono trarre vantaggio dall'innovazione totale in tutte le nostre attività, anche se usano un componente. Molto interessante e ha implicazioni di vasta portata per molti clienti.

Oggi, molti gruppi IT dei clienti sono strutturati intorno ai "prodotti". È logico per un ambiente locale poiché è necessario un esperto per ogni prodotto specifico. Tuttavia, sono del tutto contento di non avere bisogno di eseguire di nuovo il debug di un database di Active Directory o Exchange poiché questi servizi sono stati spostati nel cloud. L'automazione (che tipo di cloud è) rimuove determinati processi manuali ripetitivi (osservare cosa è successo alle factory). Tuttavia, questi sono stati sostituiti con requisiti più complessi per comprendere l'interazione tra servizi, l'impatto, le esigenze aziendali e così via. Se si è disposti a [imparare,](https://docs.microsoft.com/learn/)esistono grandi opportunità abilitate dalla trasformazione cloud. Prima di passare alla tecnologia, spesso parlo con i clienti della gestione del cambiamento nelle competenze IT e nelle strutture del team.

Per tutti i fan e gli sviluppatori di SharePoint, smettere di chiedere "Come è possibile eseguire XYZ in SharePoint online?" Usare [Power Automate](https://docs.microsoft.com/power-automate/) (o Flow) per il flusso di lavoro, è una piattaforma molto più potente. Usare [Azure Bot Framework per](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) creare un'esperienza utente migliore per l'elenco di elementi da 500 K. Iniziare a [usare Microsoft Graph](https://developer.microsoft.com/graph/) anziché CSOM. [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) include SharePoint, ma anche un mondo in più. Ci sono molti altri esempi che posso elencare. Esiste un vasto e straordinario mondo. Apri la porta e [inizia a esplorare](https://docs.microsoft.com).

L'altro impatto comune è nell'area di conformità. Questo approccio tra servizi sembra confondere completamente molti criteri di conformità. Continuo a vedere le organizzazioni che hanno lo stato "Devo eseguire il journal di tutte le comunicazioni di posta elettronica in un sistema eDiscovery". Cosa significa realmente quando la posta elettronica non è più solo posta elettronica, ma finestra in altri servizi? Office 365 ha un approccio completo alla [conformità,](https://docs.microsoft.com/microsoft-365/compliance/)ma il cambiamento di persone e processi spesso è molto più difficile della tecnologia.

Esistono molte altre persone e implicazioni per i processi. A mio parere, si tratta di un'area critica e discussa. Forse più in un altro articolo.

## <a name="tenant-structure-options"></a>Opzioni per la struttura del tenant

### <a name="single-tenant-vs-multi-tenant"></a>Confronto tra singolo tenant e multi-tenant

In generale, la maggior parte dei clienti deve avere un solo tenant di produzione. Esistono molti motivi per cui più tenant sono difficili (assegnare una ricerca [Di Bing)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)o leggere questo [white paper.](https://aka.ms/multi-tenant-user) Allo stesso tempo, molti clienti aziendali con cui lavoro hanno un altro (piccolo) tenant per l'apprendimento, il testing e la sperimentazione IT. L'accesso ad Azure tra tenant è più semplice con [Azure Lighthouse.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 e molti altri servizi SaaS hanno limiti per gli scenari tra tenant. C'è molto da considerare negli scenari [B2B di Azure AD.](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)

Molti clienti finiscono con più tenant di produzione dopo una fusione e un'acquisizione (M&A) e vogliono consolidare. Oggi non è semplice e richiedeRebbe Microsoft Consulting Services (MCS) o un partner più software di terze parti. Sono in corso attività di progettazione per affrontare vari scenari con clienti multi-tenant in futuro.

Alcuni clienti scelgono di utilizzare più tenant. Questa dovrebbe essere una decisione molto attenta e quasi sempre basata su motivi aziendali. Di seguito sono riportati alcuni esempi:

- Una struttura aziendale di tipo holding in cui non è necessaria una facile collaborazione tra entità diverse e sono presenti forti esigenze di isolamento amministrativo e di altro tipo.
- Dopo un'acquisizione, viene presa una decisione aziendale di mantenere separate due entità.
- Simulazione dell'ambiente di un cliente che non modifica l'ambiente di produzione del cliente. 
- Sviluppo di software per i clienti.

In questi scenari multi-tenant, i clienti spesso desiderano mantenere una configurazione uguale tra i tenant o segnalare le modifiche e le deriva della configurazione. Questo spesso significa passare dalle modifiche manuali alla configurazione come codice. Il supporto di Microsoft Premiere offre un workshop per questi tipi di requisiti in base a questo IP pubblico: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .

### <a name="multi-geo"></a>Multi-Geo

Per [Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo) o meno a Multi-Geo, questa è la domanda. Con Office 365 Multi-Geo, è possibile effettuare il provisioning e archiviare i dati a riposo nelle posizioni geografiche scelte per soddisfare i requisiti di [residenza dei](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations) dati. Esistono molti concepimenti erre su questa funzionalità. Tenere presente quanto segue:

- Non offre vantaggi in termini di prestazioni. Se la progettazione della rete non è corretta, le prestazioni [potrebbero](https://aka.ms/office365networking) peggiorare. Ottenere i dispositivi "vicini" alla rete Microsoft, non necessariamente ai dati.
- Non è una soluzione per la [conformità al GDPR.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) Il GDPR non si concentra sulla sovranità dei dati o sulle posizioni di archiviazione. Esistono altri framework di conformità per questo.
- Non risolve la delega dell'amministrazione (vedere di seguito) o le [barriere in fatto di informazioni.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)
- Non è uguale a multi-tenant e richiede flussi di lavoro [di provisioning utente](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) aggiuntivi.
- Non sposta [il tenant](https://docs.microsoft.com/microsoft-365/enterprise/moving-data-to-new-datacenter-geos) (Azure AD) in un'altra area geografica. 

## <a name="delegation-of-administration"></a>Delega dell'amministrazione

Nella maggior parte delle organizzazioni di grandi dimensioni, la separazione dei compiti e il controllo dell'accesso basato sui ruoli (RBAC) è una realtà necessaria. Mi scuso in anticipo. Non è così semplice come alcuni clienti lo desiderano. I requisiti dei clienti, legali, di conformità e di altro tipo sono diversi e talvolta in conflitto in tutto il mondo. La semplicità e la flessibilità si trovano spesso su lati opposti l'uno dall'altro. Non trai qualche problema, possiamo fare un lavoro migliore. Nel tempo sono stati apportati (e saranno) miglioramenti significativi. Visitare il [Microsoft Technology Center locale](https://www.microsoft.com/mtc) per trovare il modello più adatto alle proprie esigenze aziendali senza leggere la documentazione 379230. In questo caso, mi concentro su cosa dovresti pensare e non sul motivo per cui è così. Di seguito sono riportate cinque diverse aree da pianificare e alcune delle domande più comuni che ho riscontrato.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Interfaccia di amministrazione di Azure AD e Microsoft 365

Esiste un lungo e crescente elenco di [ruoli incorporati.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Ogni ruolo è costituito da un elenco di autorizzazioni di ruolo raggruppate per consentire l'esecuzione di azioni specifiche. Queste autorizzazioni sono disponibili nella scheda "Descrizione" all'interno di ogni ruolo. In alternativa, è possibile vedere una versione più leggibile nell'interfaccia di amministrazione di Microsoft 365. Le definizioni dei ruoli incorporati non possono essere modificate. In genere, raggruppa questi elementi in tre categorie:

- **Amministratore globale:** questo ruolo "potente" deve essere [altamente protetto](https://docs.microsoft.com/microsoft-365/enterprise/protect-your-global-administrator-accounts) come in altri sistemi. I consigli tipici includono: nessuna assegnazione permanente e utilizzo di Azure AD Privileged Identity Management (PIM); autenticazione avanzata; E così via. È interessante notare che questo ruolo non consente l'accesso a tutti gli elementi per impostazione predefinita. In genere, si verifica confusione sull'accesso di conformità e l'accesso di Azure, illustrato più avanti. Tuttavia, questo ruolo può sempre assegnare l'accesso ad altri servizi nel tenant. 
- **Amministratori di servizi specifici:** alcuni servizi (Exchange, SharePoint, Power BI e così via) utilizzano ruoli di amministrazione di alto livello da Azure AD. Questo non è coerente in tutti i servizi e sono disponibili altri ruoli specifici del servizio illustrati più avanti.
- **Funzionale:** esiste un lungo elenco (e in crescita) di ruoli incentrati su operazioni specifiche (mittente dell'invito guest e così via). Periodicamente, ne vengono aggiunte altre in base alle esigenze dei clienti.

Non è possibile delegare tutto (anche se il gap è in diminuzione), il che significa che a volte è necessario usare il ruolo di amministratore globale. È consigliabile considerare la configurazione come codice e l'automazione anziché l'appartenenza degli utenti a questo ruolo.

**Nota:** l'interfaccia di amministrazione di Microsoft 365 ha un'interfaccia più intuitiva, ma presenta un sottoinsieme di funzionalità rispetto all'esperienza di amministrazione di Azure AD. Entrambi i portali usano gli stessi ruoli di Azure AD, quindi le modifiche si verificano nella stessa posizione. Suggerimento: se vuoi un'interfaccia utente di amministrazione incentrata sulla gestione delle identità senza tutta la confusione di Azure, usa [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

Qual è il nome? Non fare supposizioni dal nome del ruolo. La lingua non è uno strumento molto preciso. L'obiettivo deve essere quello di definire le operazioni che devono essere delegate prima di vedere quali ruoli sono necessari. L'aggiunta di un utente al ruolo "Lettore di sicurezza" non fa in modo che veda le impostazioni di sicurezza in tutti gli elementi.

La possibilità di creare [ruoli personalizzati è](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) una domanda comune. Questo è limitato in Azure AD oggi (vedere di seguito) ma crescerà nelle funzionalità nel tempo. Questi elementi sono applicabili alle funzioni in Azure AD e potrebbero non estendersi "verso il basso" nel modello gerarchico (descritto in precedenza). Ogni volta che si tratta di "personalizzato", si tende a tornare al principale di "semplice è meglio".

Un'altra domanda comune è la possibilità di impostare l'ambito dei ruoli su un sottoinsieme di una directory. Un esempio è simile a "Amministratore helpdesk solo per gli utenti dell'Unione Europea". [Le unità amministrative](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) hanno lo scopo di risolvere questo problema. Come in precedenza, questi elementi sono applicabili alle funzioni in Azure AD e potrebbero non estendersi "verso il basso". Naturalmente, alcuni ruoli non hanno senso nell'ambito (amministratori globali, amministratori dei servizi e così via).

Oggi, tutti questi ruoli richiedono l'appartenenza diretta (o l'assegnazione dinamica se si usa [AZURE AD PIM).](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) Ciò significa che i clienti devono gestire questi elementi direttamente in Azure AD e non possono basarsi sull'appartenenza a un gruppo di sicurezza. Non sono un fan della creazione di script per gestire questi elementi in quanto dovrebbe essere eseguito con diritti elevati. In genere consiglio l'integrazione delle API con sistemi di processo come ServiceNow o l'uso di strumenti di governance dei partner come Saviynt. È in corso un lavoro di progettazione per risolvere questo problema nel tempo.

Ho [menzionato Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) alcune volte. Esiste una soluzione Microsoft Identity Manager (MIM) [Privileged Access Management](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) corrispondente per i controlli locali. È inoltre consigliabile esaminare [Privileged Access Workstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) e [Azure AD Identity Governance.](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) Esistono anche vari strumenti di terze parti, che possono abilitare l'elevazione dei ruoli just-in-time, just-enough e dinamica. Ciò fa in genere parte di una discussione più ampia per la protezione di un ambiente. 

A volte gli scenari chiamano l'aggiunta di un utente esterno a un ruolo (vedi la sezione multi-tenant, sopra). Questa operazione funziona correttamente. [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) è un altro argomento di grandi dimensioni e divertente per illustrare ai clienti, magari in un altro articolo.

### <a name="security-and-compliance-center-scc"></a>Centro sicurezza e conformità (SCC)

Le autorizzazioni nel Centro sicurezza & e conformità di [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) sono una raccolta di "gruppi di ruoli", separati e distinti dai ruoli di Azure AD. Ciò può creare confusione perché alcuni di questi gruppi di ruoli hanno lo stesso nome dei ruoli di Azure AD (ad esempio, Security Reader), ma possono essere membri diversi. Io prediligo l'uso dei ruoli di Azure AD. Ogni gruppo di ruoli è costituito da uno o più "ruoli" (vedere cosa si intende per riutilizzare la stessa parola?) e avere membri di Azure AD, che sono oggetti abilitati alla posta elettronica. Inoltre, è possibile creare un gruppo di ruoli con lo stesso nome di un ruolo, che può contenere o meno tale ruolo (evitare questa confusione).

In un certo senso, si tratta di un'evoluzione del modello dei gruppi di ruoli di Exchange. Tuttavia, Exchange Online dispone di una propria [interfaccia di gestione dei gruppi di](https://docs.microsoft.com/exchange/permissions-exo) ruoli. Alcuni gruppi di ruoli in Exchange Online sono bloccati e gestiti da Azure AD o dal Centro sicurezza & conformità, mentre altri potrebbero avere lo stesso nome o nomi simili e sono gestiti in Exchange Online (con un'aggiunta di confusione). Si consiglia di evitare di utilizzare l'interfaccia utente di Exchange Online, a meno che non siano necessari ambiti per la gestione di Exchange.

Non è possibile creare ruoli personalizzati. I ruoli sono definiti dai servizi creati da Microsoft e aumentano man quando vengono introdotti nuovi servizi. Questo concetto è simile ai [ruoli definiti dalle applicazioni](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) in Azure AD. Quando vengono abilitati nuovi servizi, spesso è necessario creare nuovi gruppi di ruoli per concedere o delegare l'accesso a tali servizi (ad esempio, gestione [dei rischi Insider).](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)

Questi gruppi di ruoli richiedono anche l'appartenenza diretta e non possono contenere gruppi di Azure AD. Purtroppo, oggi questi gruppi di ruoli non sono supportati da AZURE AD PIM. Come i ruoli di Azure AD, tendo a consigliare la gestione tramite API o un prodotto di governance partner come Saviynt o altri.

I ruoli del Centro sicurezza & conformità si estendono su Microsoft 365 e non è possibile impostare l'ambito di questi gruppi di ruoli su un sottoinsieme dell'ambiente (come con le unità amministrative in Azure AD). Molti clienti si chiedono come possono eseguire il subdelegate. Ad esempio, "creare un criterio DLP solo per gli utenti dell'Unione Europea". Oggi, se si dispone dei diritti per una funzione specifica nel Centro sicurezza & conformità, si hanno diritti su tutto ciò che riguarda questa funzione nel tenant. Tuttavia, molti criteri dispongono di funzionalità per un sottoinsieme dell'ambiente (ad esempio, "rendere [queste](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) etichette disponibili solo per questi utenti"). Una governance e una comunicazione corrette sono un componente chiave per evitare conflitti. Alcuni clienti scelgono di implementare un approccio "configurazione come codice" per affrontare la sottodelegazione nel Centro sicurezza & conformità. Alcuni servizi specifici supportano la subdelegazione (vedere di seguito).

Vale la pena notare che i controlli attualmente gestiti tramite il Centro sicurezza & conformità (protection.office.com) sono in fase di migrazione in due portali di amministrazione separati: security.microsoft.com e compliance.microsoft.com. La modifica è l'unica costante.

### <a name="service-specific"></a>Specifico del servizio

Come indicato in precedenza, molti clienti desiderano ottenere un modello di delega più granulare. Esempio comune: "Gestire il servizio XYZ solo per gli utenti e le posizioni della Divisione X" (o per altre dimensioni). La possibilità di eseguire questa operazione dipende da ogni servizio e non è coerente tra i servizi e le funzionalità. Inoltre, ogni servizio può avere un modello RBAC distinto e univoco. Invece di discutere di tutti questi elementi (ci sarà sempre tempo), aggiungo collegamenti pertinenti per ogni servizio. Non si tratta di un elenco completo, ma ti permetterà di iniziare.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Filtro autorizzazioni**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Limiti di conformità**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Advanced eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Nota: questo collegamento è alla radice della documentazione. Esistono più tipi di servizi con varianti nel modello di amministrazione/delega.
- **Power Platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power Apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Nota: esistono più tipi con varianti nei modelli di amministrazione/delega.
  + **Power Automate**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **Power BI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Nota: la protezione e la delega della piattaforma dati (che Power BI è un componente) è un'area complessa.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender per endpoint**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Barriere in fatto di informazioni**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Per il resto, la ricerca in Documenti è stata molto buona ultimamente- [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) . 

### <a name="activity-logs"></a>Log attività

Office 365 dispone di un log [di controllo unificato.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Si tratta di un [registro molto dettagliato,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)ma non leggere troppo nel nome. Potrebbe non contenere tutto ciò che ti serve per le tue esigenze di sicurezza e conformità. Inoltre, alcuni clienti sono molto interessati ad [Advanced Audit.](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)

Di seguito sono riportati alcuni esempi di log di Microsoft 365 a cui si accede tramite altre API:

- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (attività non correlate a Office 365)
- [Verifica messaggi di Exchange](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace)
- Sistemi di minacce/UEBA descritti in precedenza (ad esempio, Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender for Endpoint e così via)
- [Protezione delle informazioni Microsoft](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

È importante identificare innanzitutto tutte le origini dei log necessarie per un programma di sicurezza e conformità. Si noti inoltre che log diversi hanno limiti di conservazione in linea diversi. 

Dal punto di vista della delega dell'amministratore, la maggior parte dei log attività di Microsoft 365 non dispone di un modello RBAC incorporato. Se si dispone dell'autorizzazione per visualizzare un registro, è possibile visualizzare tutti gli elementi in esso presenti. Un esempio comune di un requisito del cliente è: "Voglio essere in grado di eseguire query sull'attività solo per gli utenti dell'Unione Europea" (o per un'altra dimensione). Per ottenere questo requisito, è necessario trasferire i log in un altro servizio. Nel cloud Microsoft, è consigliabile trasferirlo in [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) o [Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 

Diagramma di alto livello:

![Diagramma delle origini dei log per un programma di sicurezza e conformità](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Il diagramma precedente rappresenta le funzionalità integrate per l'invio di log all'Hub eventi e/o all'archiviazione di Azure e/o ad Azure Log Analytics. Non tutti i sistemi includono ancora questo tipo di funzionalità. Esistono tuttavia altri approcci per inviare questi log allo stesso repository. Ad esempio, vedere [Protezione di Teams con Azure Sentinel.](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)

La combinazione di tutti i log in un'unica posizione di archiviazione include un ulteriore vantaggio, ad esempio correlazioni incrociate, tempi di conservazione personalizzati, aumento dei dati necessari per supportare il modello RBAC e così via. Una volta che i dati sono nel sistema di archiviazione, è possibile creare un dashboard di Power BI (o un altro tipo di visualizzazione) con un modello RBAC appropriato.

Non è necessario che i log siano indirizzati a una sola posizione. Potrebbe inoltre essere utile integrare i log di [Office 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) con Microsoft Cloud App Security o un modello RBAC personalizzato in [Power BI.](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide) Archivi diversi hanno vantaggi e gruppi di destinatari diversi.

Vale la pena ricordare che esiste un sistema di analisi incorporato molto ricco per sicurezza, minacce, vulnerabilità e così via in un servizio denominato [Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)

Molti clienti di grandi dimensioni desiderano trasferire questi dati di log in un sistema di terze parti (ad esempio, SIEM). Esistono diversi approcci a questo scopo, ma in generale [Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) e [Graph](https://docs.microsoft.com/graph/security-integration) sono ottimi punti di partenza.

### <a name="azure"></a>Azure

Spesso viene chiesto se esiste un modo per separare i ruoli con privilegi elevati tra Azure AD, Azure e SaaS (ad esempio: Amministratore globale di Office 365 ma non Azure).  Non proprio.  L'architettura multi-tenant è necessaria se è necessaria una separazione amministrativa completa, ma ciò aggiunge [una complessità significativa](https://aka.ms/multi-tenant-user) (vedere sopra). Tutti questi servizi fanno parte dello stesso limite di sicurezza/identità (osservare il modello gerarchico precedente).  

È importante comprendere le relazioni tra vari servizi nello stesso tenant. Lavoro con molti clienti che stanno creando soluzioni aziendali che si estendono su Azure, Office 365 e Power Platform (e spesso anche servizi cloud locali e di terze parti). Un esempio comune:

1. Voglio collaborare su un set di documenti/immagini/ecc.( Office 365)
2. Inviare ognuno di essi tramite un processo di approvazione (Power Platform)
3.  Dopo l'approvazione di tutti i componenti, assemblare questi in un'API unificata per i risultati finali (Azure) [di Microsoft Graph](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) è il tuo migliore amico per questi prodotti.  Non impossibile, ma significativamente più complesso progettare una soluzione che si estende [su più tenant.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based Access Control (RBAC) consente una gestione degli accessi granulare per Azure. Utilizzando RBAC, è possibile gestire l'accesso alle risorse concedendo agli utenti il numero minimo di autorizzazioni necessarie per eseguire il proprio lavoro. I dettagli non sono nell'ambito di questo documento, ma per ulteriori informazioni su RBAC, vedere Che cos'è il controllo dell'accesso basato sui ruoli [(RBAC) in Azure?](https://docs.microsoft.com/azure/role-based-access-control/overview) RBAC è importante, ma solo parte delle considerazioni sulla governance per Azure. [Cloud Adoption Framework è](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) un ottimo punto di partenza per saperne di più. Mi piace il modo in cui il mio amico, Andres Ravinet, guida i clienti passo passo, anche se diversi componenti decidono l'approccio. La visualizzazione di alto livello per vari elementi (non buona come il processo per ottenere il modello di cliente effettivo) è simile alla seguente:

![Visualizzazione di alto livello dei componenti di Azure per l'amministrazione delegata](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Come si può vedere dall'immagine precedente, molti altri servizi devono essere considerati come parte [](https://docs.microsoft.com/azure/governance/management-groups/)della progettazione (ad esempio: Criteri di [Azure,](https://docs.microsoft.com/azure/governance/policy/overview)progetti [di Azure,](https://docs.microsoft.com/azure/governance/blueprints/overview)gruppi di gestione e così via).

## <a name="conclusion"></a>Conclusione

Iniziato come breve riepilogo, è finito più a lungo del previsto.  Mi auguriamo che tu sia ora pronto per iniziare a vedere in modo approfondito la creazione del modello di delega per l'organizzazione.  Questa conversazione è molto comune con i clienti. Non esiste un modello che funzioni per tutti. In attesa di alcuni miglioramenti pianificati dall'ingegneria Microsoft prima di documentare i modelli comuni che vediamo tra i clienti. Nel frattempo, è possibile collaborare con il team dell'account Microsoft per organizzare una visita al [Microsoft Technology Center più vicino.](https://www.microsoft.com/mtc)  Ci vediamo qui.
