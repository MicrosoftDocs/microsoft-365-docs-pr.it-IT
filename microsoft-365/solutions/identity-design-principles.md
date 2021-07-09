---
title: Microsoft 365 pianificazione delle risorse dell'organizzazione - Architettura di sicurezza
description: Informazioni sulle principali strategie di progettazione per l'architettura Enterprise Microsoft da Alex Shteynberg, Technical Principal Architect di Microsoft.
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
ms.openlocfilehash: a3be13624c3b3cc9d7be667e28e435c76c513fc3
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341725"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Verso l'identità e oltre: il punto di vista di un architetto

In questo articolo, [Alex Shteynberg,](https://www.linkedin.com/in/alex-shteynberg/)Principal Technical Architect di Microsoft, illustra le principali strategie di progettazione per le organizzazioni aziendali che adottano Microsoft 365 e altri servizi cloud Microsoft.

## <a name="about-the-author"></a>Informazioni sull'autore

![Foto di Alex Shteynberg](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Sono un principal technical architect presso il [Microsoft Technology Center](https://www.microsoft.com/mtc?rtc=1)di New York. Lavoro principalmente con clienti di grandi dimensioni e requisiti complessi. Il mio punto di vista e le mie opinioni si basano su queste interazioni e potrebbero non essere applicabili a ogni situazione. Tuttavia, nella mia esperienza, se possiamo aiutare i clienti con le sfide più complesse, possiamo aiutare tutti i clienti.

In genere lavoro con più di 100 clienti ogni anno. Anche se ogni organizzazione ha caratteristiche uniche, è interessante vedere tendenze e caratteristiche comuni. Ad esempio, una tendenza è l'interesse per molti clienti. Dopo tutto, una filiale bancaria può anche essere un bar e un centro community.

Nel mio ruolo, mi concentro sull'aiutare i clienti a raggiungere la soluzione tecnica migliore per affrontare i loro obiettivi aziendali specifici. Ufficialmente, mi concentro su identità, sicurezza, privacy e conformità. Mi piace il fatto che questi tocchino tutto ciò che facciamo. Mi offre l'opportunità di essere coinvolto nella maggior parte dei progetti. Questo mi mantiene piuttosto occupato e mi piace questo ruolo.

Vivo a New York (la migliore!) e mi piace molto la diversità della sua cultura, del suo cibo e delle persone (non del traffico). Amo viaggiare quando posso e speriamo di vedere la maggior parte del mondo nella mia vita. Attualmente sto cercando un viaggio in Africa per conoscere la natura selvaggia.

## <a name="guiding-principles"></a>Principi guida

- **Semplice è spesso meglio:** puoi fare (quasi) qualsiasi cosa con la tecnologia, ma non significa che dovresti farlo. Soprattutto nello spazio di sicurezza, molti clienti esegnere soluzioni. Mi piace [questo video della](https://www.youtube.com/watch?v=SOQgABDSYZE) conferenza Stripe di Google per sottolineare questo punto.
- **Persone, processo, tecnologia:** [progettare per le persone per](https://en.wikipedia.org/wiki/Human-centered_design) migliorare i processi, non per primi la tecnologia. Non esistono soluzioni "perfette". Dobbiamo bilanciare diversi fattori di rischio e le decisioni saranno diverse per ogni azienda. Troppi clienti progettano un approccio che gli utenti evitano in seguito.
- **Focus on 'why' first and 'how' later**: Be the fastidioso 7-yr old kid with a million questions. Non possiamo arrivare alla risposta giusta se non si conoscono le domande giuste da porre. Molti clienti fanno supposizioni su come devono funzionare le cose invece di definire il problema aziendale. È sempre possibile eseguire più percorsi.
- **Lunga coda delle procedure consigliate precedenti:** riconoscere che le procedure consigliate stanno cambiando a velocità ridotta. Se hai esaminato Azure AD più di tre mesi fa, probabilmente non sei aggiornato. Tutto è soggetto a modifiche dopo la pubblicazione. L'opzione "Migliore" oggi potrebbe non essere la stessa tra sei mesi.

## <a name="baseline-concepts"></a>Concetti di base

Non ignorare questa sezione. Spesso è necessario tornare a questi argomenti, anche per i clienti che usano servizi cloud da anni.
Purtroppo, la lingua non è uno strumento preciso. Spesso usiamo la stessa parola per indicare concetti diversi o parole diverse per indicare lo stesso concetto. Questo diagramma viene spesso usato di seguito per stabilire una terminologia di base e un "modello di gerarchia".
<br><br>

![Illustrazione di tenant, sottoscrizione, servizio e dati](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)

<br>

Quando impari a fare il bagno, è meglio iniziare in piscina e non in mezzo all'oceano. Non sto cercando di essere tecnicamente accurato con questo diagramma. È un modello per discutere di alcuni concetti di base.

Nel diagramma:

- Tenant = un'istanza di Azure AD. Si trova nella "parte superiore" di una gerarchia o livello 1 nel diagramma. Possiamo considerare questo come il "[limite](/azure/active-directory/users-groups-roles/licensing-directory-independence)" in cui si verifica tutto il resto ([Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) a parte). Tutti i servizi cloud aziendali Microsoft fanno parte di uno di questi tenant. I servizi consumer sono separati. "Tenant" viene visualizzato nella documentazione Office 365 tenant di Azure, tenant di Azure, tenant WVD e così via. Spesso queste varianti causano confusione per i clienti.
- Servizi/sottoscrizioni, livello 2 nel diagramma, appartengono a un solo tenant. La maggior parte dei servizi SaaS è 1:1 e non può essere spostata senza migrazione. Azure è diverso, è possibile [spostare la fatturazione](/azure/cost-management-billing/manage/billing-subscription-transfer) e/o una [sottoscrizione](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) in un altro tenant. Sono molti i clienti che devono spostare le sottoscrizioni di Azure. Ciò ha varie implicazioni. Gli oggetti esistenti all'esterno della sottoscrizione non vengono spostati(ad esempio, il controllo dell'accesso basato sui ruoli o RBAC di Azure e gli oggetti di Azure AD inclusi gruppi, app, criteri e così via). Inoltre, alcuni servizi (ad esempio Azure Key Vault, Data Bricks e così via). Non eseguire la migrazione dei servizi senza una buona necessità aziendale. Alcuni script che possono essere utili per la migrazione vengono [condivisi in GitHub](https://github.com/lwajswaj/azure-tenant-migration).
- Un determinato servizio in genere ha una sorta di limite di "sottolivello" o livello 3 (L3). Ciò è utile per comprendere la separazione di sicurezza, criteri, governance e così via. Purtroppo, non esiste un nome uniforme che io sappia. Alcuni esempi di nomi per L3 sono: Sottoscrizione di Azure = [risorsa;](/azure/azure-resource-manager/management/manage-resources-portal) Dynamics 365 CE = [istanza](/dynamics365/admin/new-instance-management); Power BI = [workspace](/power-bi/service-create-the-new-workspaces); Power Apps = [ambiente](/power-platform/admin/environments-overview); E così via.
- Il livello 4 è il luogo in cui vivono i dati effettivi. Questo "piano dati" è un argomento complesso. Alcuni servizi usano Azure AD per RBAC, altri no. Ne parlerò un po' quando parleremo degli argomenti relativi alla delega.

Alcuni concetti aggiuntivi che molti clienti (e dipendenti Microsoft) sono confusi o hanno domande su:

- Chiunque può [creare](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) molti tenant [senza costi](https://azure.microsoft.com/pricing/details/active-directory/)aggiuntivi. Non è necessario un servizio di cui è stato eseguito il provisioning al suo interno. Ne ho decine. Ogni nome tenant è univoco nel servizio cloud di Microsoft in tutto il mondo (in altre parole, nessun tenant può avere lo stesso nome). Sono tutti nel formato TenantName.onmicrosoft.com. Esistono anche processi che creano i tenant automaticamente ([tenant non gestiti](/azure/active-directory/users-groups-roles/directory-self-service-signup)). Ad esempio, ciò può verificarsi quando un utente si i signs up for an enterprise service with an email domain that does not exist in any other tenant.
- In un tenant gestito, molti [domini DNS](/azure/active-directory/fundamentals/add-custom-domain) possono essere registrati in esso. In questo modo non viene modificato il nome del tenant originale. Attualmente non esiste un modo semplice per rinominare un tenant (a parte la migrazione). Anche se il nome del tenant non è tecnicamente critico in questi giorni, alcuni potrebbero trovare questo limite.
- È consigliabile riservare un nome tenant per l'organizzazione anche se non si prevede ancora di distribuire alcun servizio. In caso contrario, qualcuno può prenderlo da te e non esiste un processo semplice per riportarlo indietro (stesso problema dei nomi DNS). Si sente così spesso dai clienti. Anche il nome del tenant deve essere un argomento di discussione.
- Se si possiede uno o più spazi dei nomi DNS, è necessario aggiungerli tutti ai tenant. In caso contrario, è possibile [creare un tenant](/azure/active-directory/users-groups-roles/directory-self-service-signup) non gestito con questo nome, causando un'interruzione per [renderlo gestito.](/azure/active-directory/users-groups-roles/domains-admin-takeover)
- Lo spazio dei nomi DNS (ad esempio contoso.com) può appartenere a un solo Tenant. Ciò ha implicazioni per diversi scenari (ad esempio, la condivisione di un dominio di posta elettronica durante una fusione o un'acquisizione e così via). Esiste un modo per registrare un sub DNS (ad esempio div.contoso.com) in un tenant diverso, ma è consigliabile evitarlo. Registrando un nome di dominio di primo livello, si presuppone che tutti i sottodomini appartengano allo stesso tenant. Negli scenari multi-tenant (vedere di seguito) in genere è consigliabile usare un altro nome di dominio di primo livello (ad esempio contoso.ch o ch-contoso.com).
- Who "proprietario" di un tenant? Spesso vedo clienti che non sanno chi è attualmente proprietario del proprio tenant. Questa è una grande bandiera rossa. Chiamare il supporto Tecnico Microsoft al più presto. Lo stesso problema si verifica quando un proprietario del servizio (spesso un Exchange amministratore) è designato per gestire un tenant. Il tenant conterrà tutti i servizi desiderati in futuro. Il proprietario del tenant deve essere un gruppo che può prendere decisioni per l'abilitazione di tutti i servizi cloud in un'organizzazione. Un altro problema è quando viene richiesto a un gruppo di proprietari tenant di gestire tutti i servizi. Questo non si adatta alle organizzazioni di grandi dimensioni.
- Non esiste alcun concetto di tenant secondario/super. Per qualche motivo, questo mito continua a ripetersi. Questo vale anche per i tenant [B2C](/azure/active-directory-b2c/) di Azure AD. Si sente troppe volte "Il mio ambiente B2C si trova nel tenant XYZ" o "Come si sposta il tenant di Azure nel tenant di Office 365?"
- Questo documento si concentra principalmente sul cloud commerciale in tutto il mondo, in quanto questo è ciò che la maggior parte dei clienti usa. A volte è utile conoscere i [cloud sovrani.](/azure/active-directory/develop/authentication-national-cloud) I cloud sovrani hanno implicazioni aggiuntive per discutere quali sono fuori dall'ambito di questa discussione.

## <a name="baseline-identity-topics"></a>Argomenti relativi all'identità di base

C'è molta documentazione sulla piattaforma di identità di Microsoft – Azure Active Directory (Azure AD). Per coloro che stanno iniziando, spesso sembra travolgente. Anche dopo aver appreso questo tipo di informazioni, tenere il passo con l'innovazione e il cambiamento costanti può essere difficile. Nelle interazioni con i clienti spesso mi ritrovo a fungere da "traduttore" tra gli obiettivi aziendali e gli approcci "Buono, Migliore, Migliore" per affrontare questi argomenti (e le "note sulla scogliera" umane per questi argomenti). Raramente esiste una risposta perfetta e la decisione "giusta" è un equilibrio tra vari fattori di rischio. Di seguito sono riportate alcune delle domande comuni e le aree di confusione che tendo a discutere con i clienti.

### <a name="provisioning"></a>Provisioning

Azure AD non risolve la mancanza di governance nel mondo dell'identità. [La governance dell'identità](/azure/active-directory/governance/identity-governance-overview) deve essere un elemento critico indipendentemente dalle decisioni del cloud. I requisiti di governance cambiano nel tempo, motivo per cui è un programma e non uno strumento.

[Azure AD Connessione](/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) o altro (terze parti o personalizzato)? Risparmiati un sacco di mal di testa ora e in futuro e vai con Azure AD Connessione. Esistono tutti i tipi di smart in questo strumento per affrontare le configurazioni dei clienti peculiari e le innovazioni in corso.

Alcuni casi perimetrali che possono guidare verso un'architettura più complessa:

- Ho più foreste ad Active Directory senza connettività di rete tra queste. È disponibile una nuova opzione denominata [Provisioning cloud.](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Non si dispone di Active Directory né si desidera installarlo. Azure AD Connessione può essere configurato per la sincronizzazione [da LDAP](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (potrebbe essere necessario un partner).
- È necessario eseguire il provisioning degli stessi oggetti in più tenant. Questo non è tecnicamente supportato, ma dipende dalla definizione di "stesso".

È consigliabile personalizzare le regole di sincronizzazione predefinite ([oggetti filtro,](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [attributi di modifica,](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) [ID di accesso](/azure/active-directory/hybrid/plan-connect-userprincipalname)alternativo e così via)? Evitalo! Una piattaforma di identità è utile solo quanto i servizi che la usano. Sebbene sia possibile eseguire tutti i tipi di configurazioni di base, per rispondere a questa domanda è necessario esaminare l'impatto sulle applicazioni. Se si filtrano gli oggetti abilitati alla posta, l'elenco indirizzi globale per i servizi online sarà incompleto. se l'applicazione si basa su attributi specifici, il filtro avrà un impatto imprevedibile; E così via. Non è una decisione del team di identità.

XYZ SaaS supporta il provisioning just-in-time (JIT), perché mi stai richiedendo la sincronizzazione? Vedere sopra. Molte applicazioni necessitano di informazioni di "profilo" per la funzionalità. Non è possibile disporre di un elenco indirizzi globale se non sono disponibili tutti gli oggetti abilitati alla posta elettronica. Lo stesso vale per [il provisioning degli](/azure/active-directory/app-provisioning/user-provisioning) utenti nelle applicazioni integrate con Azure AD.

### <a name="authentication"></a>Autenticazione

[Sincronizzazione hash delle](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) password (PHS) e [autenticazione pass-through](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) e [federazione](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

In genere c'è un acceso [confronto sulla](/azure/active-directory/hybrid/choose-ad-authn) federazione. Più semplice in genere è meglio e quindi usare PHS a meno che non si abbia un buon motivo per non usarlo. È inoltre possibile configurare metodi di autenticazione diversi per domini DNS diversi nello stesso tenant.

Alcuni clienti abilitano la federazione + PHS principalmente per:

- Opzione di [cui eseguire il fall back](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) (per il ripristino di emergenza) se il servizio federativo non è disponibile.
- Funzionalità aggiuntive (ad esempio: [Servizi di dominio Azure AD)](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)e servizi di sicurezza (ad esempio: credenziali [trapelate](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Supporto per i servizi in Azure che non comprendono l'autenticazione federata (ad esempio, [File di Azure](/azure/storage/files/storage-files-active-directory-overview)).

Spesso i clienti passano attraverso il flusso di autenticazione client per chiarire alcuni errori. Il risultato è simile all'immagine seguente, che non è così buona come il processo interattivo di arrivare lì.

![Conversazione di esempio sulla lavagna](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Questo tipo di disegno della lavagna illustra dove vengono applicati i criteri di sicurezza all'interno del flusso di una richiesta di autenticazione. In questo esempio, i criteri applicati tramite Active Directory Federation Service (AD FS) vengono applicati alla prima richiesta di servizio, ma non alle richieste di servizio successive. Questo è almeno un motivo per spostare i controlli di sicurezza nel cloud il più possibile.

Abbiamo inseguito il sogno del [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO) per tutto il tempo che posso ricordare. Alcuni clienti ritengono di poter ottenere questo risultato scegliendo il provider di federazione "giusto". Azure AD può aiutare in modo significativo [a abilitare le funzionalità SSO,](/azure/active-directory/manage-apps/plan-sso-deployment) ma nessun servizio token di sicurezza è magico. Esistono troppi metodi di autenticazione "legacy" ancora utilizzati per le applicazioni critiche. L'estensione di Azure AD [con soluzioni partner](/azure/active-directory/saas-apps/tutorial-list) può risolvere molti di questi scenari. SSO è una strategia e un percorso. Non è possibile raggiungere questo livello senza passare agli [standard per le applicazioni](/azure/active-directory/develop/v2-app-types). Correlato a questo argomento è un percorso verso [l'autenticazione senza password,](/azure/active-directory/authentication/concept-authentication-passwordless) che inoltre non ha una risposta magica.

[L'autenticazione a più](/azure/active-directory/authentication/concept-mfa-howitworks) fattori (MFA) è essenziale oggi[(per](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) altre informazioni). Aggiungi ad esso [l'analisi del comportamento](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) degli utenti e hai una soluzione che impedisce gli attacchi informatici più comuni. Anche i servizi consumer si stanno spostando per richiedere l'autenticazione a più fattori. Tuttavia, incontro ancora molti clienti che non vogliono passare agli approcci [di autenticazione](../enterprise/hybrid-modern-auth-overview.md) moderni. L'argomento più importante è che inciderà sugli utenti e sulle applicazioni legacy. A volte un buon calcio potrebbe aiutare i clienti a spostarsi avanti - Exchange Online [modifiche annunciate](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282). Sono ora disponibili numerosi [report](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) di Azure AD per aiutare i clienti con questa transizione.

### <a name="authorization"></a>Autorizzazione

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization), "autorizzare" è definire un criterio di accesso. Molti utenti la guardano come la possibilità di definire i controlli di accesso a un oggetto (file, servizio e così via). Nell'attuale mondo delle minacce informatiche, questo concetto si sta evolvendo rapidamente verso un criterio dinamico in grado di reagire a vari vettori di minacce e regolare rapidamente i controlli di accesso in risposta a questi. Ad esempio, se accedono al mio conto corrente bancario da una posizione insolita, ottengo ulteriori passaggi di conferma. Per affrontare questo problema, è necessario considerare non solo il criterio stesso, ma l'ecosistema delle metodologie di rilevamento delle minacce e correlazione dei segnali.

Il motore dei criteri di Azure AD viene implementato usando i [criteri di accesso condizionale.](/azure/active-directory/conditional-access/overview) Questo sistema dipende dalle informazioni di un'ampia gamma di altri sistemi di rilevamento delle minacce per prendere decisioni dinamiche. Una visualizzazione semplice è simile alla figura seguente:

![Motore dei criteri in Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

La combinazione di tutti questi segnali consente criteri dinamici come questi:

- Se viene rilevata una minaccia nel dispositivo, l'accesso ai dati verrà ridotto al Web solo senza la possibilità di scaricarlo.
- Se si sta scaricando un volume insolitamente elevato di dati, tutto ciò che si scarica verrà crittografato e limitato.
- Se accedi a un servizio da un dispositivo non gestito, ti verrà impedito di accedere a dati altamente riservati, ma potrai accedere a dati senza restrizioni senza la possibilità di copiarlo in un'altra posizione.

Se si accetta questa definizione estesa di autorizzazione, è necessario implementare soluzioni aggiuntive. Le soluzioni implementate dipendono dal livello di dinamicità del criterio e dalle minacce a cui assegnare la priorità. Alcuni esempi di tali sistemi sono:

- [Azure AD Identity Protection](/azure/active-directory/identity-protection/)
- [Microsoft Defender per identità](/azure-advanced-threat-protection/)
- [Microsoft Defender ATP](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender per Office 365](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security](/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Information Protection](../compliance/information-protection.md) (MIP)
- [Azure Sentinel](/azure/sentinel/)

Naturalmente, oltre ad Azure AD, diversi servizi e applicazioni dispongono di modelli di autorizzazione specifici. Alcuni di questi vengono descritti più avanti nella sezione delega.

### <a name="audit"></a>Audit

Azure AD dispone di funzionalità [dettagliate di controllo e creazione di report.](/azure/active-directory/reports-monitoring/) Tuttavia, questa non è in genere l'unica fonte di informazioni necessarie per prendere decisioni sulla sicurezza. Per ulteriori informazioni, vedere la sezione delega.

## <a name="theres-no-exchange"></a>Non c'è Exchange

Don't Panic! Questo non significa che Exchange deprecato (o SharePoint e così via). È ancora un servizio di base. Ciò che voglio dire è che, da tempo, i provider di tecnologia passano da esperienze utente (UX) a componenti di più servizi. In Microsoft 365, un semplice esempio è "[allegati](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)moderni " in cui gli allegati alla posta elettronica vengono archiviati in SharePoint Online o OneDrive for Business.

![Allegare un file a un messaggio di posta elettronica](../media/solutions-architecture-center/modern-attachments.png)

Osservando il client Outlook è possibile vedere molti servizi "connessi" come parte di questa esperienza, non solo Exchange. Sono inclusi Azure AD, Microsoft Search, app, profilo, conformità e Office 365 gruppi.

![Outlook interfaccia utente con callout](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Per informazioni [Microsoft Fluid Framework'anteprima](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) delle funzionalità future. In anteprima ora, posso leggere e rispondere a Teams conversazioni direttamente in Outlook. Infatti, il [Teams client](https://products.office.com/microsoft-teams/download-app) è uno degli esempi più importanti di questa strategia.

Nel complesso, è sempre più difficile tracciare una linea chiara tra Office 365 e altri servizi nei cloud Microsoft. Lo vedo come un grande vantaggio per i clienti perché possono trarre vantaggio dall'innovazione totale in tutto ciò che facciamo anche se usano un componente. Molto interessante e ha implicazioni di vasta portata per molti clienti.

Oggi, molti gruppi IT dei clienti sono strutturati attorno ai "prodotti". È logico per un mondo locale poiché è necessario un esperto per ogni prodotto specifico. Tuttavia, sono del tutto contento che non sia necessario eseguire di nuovo il debug di un database di Active Directory o Exchange poiché questi servizi si sono spostati nel cloud. L'automazione (che tipo di cloud è) rimuove determinati processi manuali ripetitivi (guarda cosa è successo alle factory). Tuttavia, questi sono sostituiti da requisiti più complessi per comprendere l'interazione tra servizi, l'impatto, le esigenze aziendali e così via. Se si vuole [imparare,](/learn/)esistono grandi opportunità abilitate dalla trasformazione cloud. Prima di passare alla tecnologia, spesso si parla ai clienti della gestione del cambiamento nelle competenze IT e nelle strutture del team.

Per tutti SharePoint fan e sviluppatori, smettere di chiedere "Come posso fare XYZ in SharePoint online?" Usa [Power Automate](/power-automate/) (o Flow) per il flusso di lavoro, è una piattaforma molto più potente. Usa [Azure Bot Framework](/azure/bot-service/) per creare un'esperienza utente migliore per l'elenco di elementi da 500 K. Iniziare a [usare Microsoft Graph](https://developer.microsoft.com/graph/) invece di CSOM. [Microsoft Teams](/MicrosoftTeams/Teams-overview) include SharePoint ma anche un mondo più. Ci sono molti altri esempi che posso elencare. C'è un vasto e fantastico universo là fuori. Apri la porta e [inizia a esplorare]().

L'altro impatto comune è nell'area di conformità. Questo approccio tra servizi sembra confondere completamente molti criteri di conformità. Continuo a vedere le organizzazioni che hanno lo stato "Devo eseguire il journal di tutte le comunicazioni di posta elettronica in un sistema eDiscovery". Cosa significa realmente quando la posta elettronica non è più solo posta elettronica, ma una finestra in altri servizi? Office 365 ha un approccio completo per [la](../compliance/index.yml)conformità, ma il cambiamento di persone e processi spesso è molto più difficile della tecnologia.

Ci sono molte altre persone e implicazioni di processo. A mio parere, si tratta di un'area critica e sottose discussa. Forse più in un altro articolo.

## <a name="tenant-structure-options"></a>Opzioni per la struttura del tenant

### <a name="single-tenant-vs-multi-tenant"></a>Confronto tra tenant singolo e multi-tenant

In generale, la maggior parte dei clienti deve avere un solo tenant di produzione. Esistono molti motivi per cui più tenant sono impegnativi (fornire una Bing [ricerca](https://www.bing.com/search?q=office%20365%20multiple%20tenants)) o leggere questo [white paper](https://aka.ms/multi-tenant-user). Allo stesso tempo, molti clienti aziendali con cui lavoro hanno un altro tenant (piccolo) per l'apprendimento, il testing e la sperimentazione IT. L'accesso ad Azure tra tenant è semplificato con [Azure Lighthouse.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 e molti altri servizi SaaS hanno limiti per gli scenari tra tenant. C'è molto da considerare negli scenari [B2B di Azure AD.](/azure/active-directory/b2b/what-is-b2b)

Molti clienti finiscono con più tenant di produzione dopo una fusione e un'acquisizione (M&A) e desiderano consolidare. Oggi non è semplice e richiederebbe Microsoft Consulting Services (MCS) o un partner più software di terze parti. Sono in corso attività di progettazione per affrontare diversi scenari con clienti multi-tenant in futuro.

Alcuni clienti scelgono di utilizzare più tenant. Questa dovrebbe essere una decisione molto attenta e quasi sempre basata sul motivo aziendale. Di seguito sono riportati alcuni esempi:

- Struttura aziendale di tipo holding in cui non è necessaria una facile collaborazione tra entità diverse e sono presenti forti esigenze amministrative e di isolamento.
- Dopo un'acquisizione, viene presa una decisione aziendale per mantenere separate due entità.
- Simulazione dell'ambiente di un cliente che non modifica l'ambiente di produzione del cliente.
- Sviluppo di software per i clienti.

In questi scenari multi-tenant, i clienti spesso desiderano mantenere una configurazione uguale tra i tenant o segnalare le modifiche alla configurazione e le derivazioni. Questo spesso significa passare dalle modifiche manuali alla configurazione come codice. Il supporto di Microsoft Premiere offre un workshop per questi tipi di requisiti in base a questo IP pubblico: <https://Microsoft365dsc.com> .

### <a name="multi-geo"></a>Multi-Geo

To [Multi-Geo](../enterprise/microsoft-365-multi-geo.md) or not to Multi-Geo, that is the question. Con Office 365 Multi-Geo, è possibile effettuare il provisioning e archiviare i dati a riposo nelle posizioni geografiche scelte per soddisfare i requisiti [di residenza dei](../enterprise/o365-data-locations.md) dati. Ci sono molti traintesi su questa funzionalità. Tenere presente quanto segue:

- Non offre vantaggi in termini di prestazioni. Potrebbe peggiorare le prestazioni se [la progettazione della](https://aka.ms/office365networking) rete non è corretta. Avvicinare i dispositivi alla rete Microsoft, non necessariamente ai dati.
- Non è una soluzione per la conformità [al GDPR.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) Il GDPR non si concentra sulla sovranità dei dati o sulle posizioni di archiviazione. Esistono altri framework di conformità per questo.
- Non risolve la delega dell'amministrazione (vedi sotto) o [le barriere di informazione](../compliance/information-barriers.md).
- Non è uguale a multi-tenant e richiede flussi di lavoro [di provisioning degli utenti](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md) aggiuntivi.
- Non sposta [il tenant](../enterprise/moving-data-to-new-datacenter-geos.md) (Azure AD) in un'altra area geografica.

## <a name="delegation-of-administration"></a>Delega dell'amministrazione

Nella maggior parte delle organizzazioni di grandi dimensioni, la separazione dei compiti e il controllo degli accessi in base al ruolo (RBAC) è una realtà necessaria. Mi scuso in anticipo. Non è così semplice come alcuni clienti vogliono che sia. I requisiti dei clienti, legali, di conformità e di altro tipo sono diversi e talvolta in conflitto in tutto il mondo. La semplicità e la flessibilità si trovano spesso su lati opposti l'uno dall'altro. Non trai sdermi, possiamo fare un lavoro migliore in questo. Nel tempo sono stati apportati (e saranno) miglioramenti significativi. Visitare il [Microsoft Technology Center locale](https://www.microsoft.com/mtc) per trovare il modello più adatto alle proprie esigenze aziendali senza leggere la documentazione 379230. In questo caso, mi concentrerò su ciò a cui dovresti pensare e non sul motivo per cui è così. Di seguito sono riportate cinque diverse aree da pianificare e alcune delle domande più comuni che ho riscontrato.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD e le Microsoft 365 di amministrazione

Esiste un elenco lungo e crescente di [ruoli incorporati.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Ogni ruolo è costituito da un elenco di autorizzazioni di ruolo raggruppate per consentire l'esecuzione di azioni specifiche. Queste autorizzazioni sono disponibili nella scheda "Descrizione" all'interno di ogni ruolo. In alternativa, puoi vedere una versione più leggibile in Amministrazione Microsoft 365 Center. Le definizioni per i ruoli predefiniti non possono essere modificate. In genere, raggruppare questi elementi in tre categorie:

- **Amministratore globale:** questo ruolo "tutto potente" deve essere [altamente protetto](../enterprise/protect-your-global-administrator-accounts.md) come in altri sistemi. I consigli tipici includono: nessuna assegnazione permanente e uso di Azure AD Privileged Identity Management (PIM); autenticazione avanzata; E così via. È interessante notare che questo ruolo non consente di accedere a tutti gli elementi per impostazione predefinita. In genere, vedo confusione sull'accesso di conformità e l'accesso di Azure, descritto più avanti. Tuttavia, questo ruolo può sempre assegnare l'accesso ad altri servizi nel tenant.
- **Amministratori di servizi specifici:** alcuni servizi (Exchange, SharePoint, Power BI e così via) utilizzano ruoli di amministrazione di alto livello da Azure AD. Questo non è coerente in tutti i servizi e più ruoli specifici del servizio sono descritti più avanti.
- **Funzionale:** esiste un lungo elenco (e in crescita) di ruoli incentrati su operazioni specifiche (guest inviter e così via). Periodicamente, ne vengono aggiunte di più in base alle esigenze dei clienti.

Non è possibile delegare tutto (anche se il gap sta diminuendo), il che significa che a volte è necessario utilizzare il ruolo di amministratore globale. È consigliabile considerare la configurazione come codice e l'automazione anziché l'appartenenza degli utenti a questo ruolo.

**Nota:** il interfaccia di amministrazione di Microsoft 365 ha un'interfaccia più intuitiva, ma ha un sottoinsieme di funzionalità rispetto all'esperienza di amministrazione di Azure AD. Entrambi i portali usano gli stessi ruoli di Azure AD, quindi le modifiche si verificano nella stessa posizione. Suggerimento: se vuoi un'interfaccia utente di amministrazione incentrata sulla gestione delle identità senza tutta la confusione di Azure, usa <https://aad.portal.azure.com> .

Qual è il nome? Non fare supposizioni dal nome del ruolo. La lingua non è uno strumento molto preciso. L'obiettivo deve essere definire le operazioni che devono essere delegate prima di vedere quali ruoli sono necessari. L'aggiunta di qualcuno al ruolo "Lettore sicurezza" non fa in modo che vedano le impostazioni di sicurezza in tutti gli elementi.

La possibilità di creare [ruoli personalizzati è](/azure/active-directory/users-groups-roles/roles-custom-overview) una domanda comune. Questo è limitato in Azure AD oggi (vedi sotto) ma crescerà nelle funzionalità nel tempo. Questi elementi sono applicabili alle funzioni in Azure AD e potrebbero non estendersi "verso il basso" nel modello gerarchico (descritto in precedenza). Ogni volta che mi occupo di "personalizzato", tendo a tornare al mio principale di "semplice è meglio".

Un'altra domanda comune è la possibilità di ambito dei ruoli in un sottoinsieme di una directory. Un esempio è "Amministratore helpdesk solo per gli utenti nell'UE". [Le unità amministrative](/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) hanno lo scopo di risolvere questo problema. Come in precedenza, questi elementi sono applicabili alle funzioni in Azure AD e potrebbero non estendersi verso il basso. Naturalmente, alcuni ruoli non hanno senso per l'ambito (amministratori globali, amministratori del servizio e così via).

Oggi, tutti questi ruoli richiedono l'appartenenza diretta (o l'assegnazione dinamica se si usa [Azure AD PIM](/azure/active-directory/privileged-identity-management/)). Ciò significa che i clienti devono gestire questi elementi direttamente in Azure AD e non possono essere basati sull'appartenenza a un gruppo di sicurezza. I'm not a fan of creating scripts to manage these as it would need to run with elevated rights. In genere consiglio l'integrazione delle API con sistemi di processo come ServiceNow o l'uso di strumenti di governance dei partner come Saviynt. È in corso un lavoro di progettazione per risolvere questo problema nel tempo.

Ho [menzionato Azure AD PIM](/azure/active-directory/privileged-identity-management/) alcune volte. Esiste una soluzione PAM [(Privileged Access Management)](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) Microsoft Identity Manager (MIM) corrispondente per i controlli locali. È anche consigliabile esaminare [Privileged Access Workstations](/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) e [Azure AD Identity Governance](/azure/active-directory/governance/identity-governance-overview). Esistono anche diversi strumenti di terze parti, che possono abilitare l'elevazione dei ruoli just-in-time, just-enough e dinamica. Ciò fa in genere parte di una discussione più ampia per la protezione di un ambiente.

A volte gli scenari chiamano l'aggiunta di un utente esterno a un ruolo (vedere la sezione multi-tenant, sopra). Funziona correttamente. [Azure AD B2B](/azure/active-directory/b2b/) è un altro argomento di grandi dimensioni e divertente da illustrare ai clienti, ad esempio in un altro articolo.

### <a name="security-and-compliance-center-scc"></a>Centro sicurezza e conformità

[Le autorizzazioni nel Office 365 Sicurezza & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) sono una raccolta di "gruppi di ruoli", separati e distinti dai ruoli di Azure AD. Ciò può creare confusione perché alcuni di questi gruppi di ruoli hanno lo stesso nome dei ruoli di Azure AD (ad esempio, Lettore di sicurezza), ma possono avere appartenenze diverse. È preferibile usare i ruoli di Azure AD. Ogni gruppo di ruoli è costituito da uno o più "ruoli" (vedere cosa si intende per riutilizzare la stessa parola?) e avere membri di Azure AD, che sono oggetti abilitati alla posta elettronica. Inoltre, è possibile creare un gruppo di ruoli con lo stesso nome di un ruolo, che può o meno contenere tale ruolo (evitare questa confusione).

In un certo senso, si tratta di un'evoluzione del modello Exchange dei gruppi di ruoli. Tuttavia, Exchange Online dispone di una propria [interfaccia di gestione dei gruppi di](/exchange/permissions-exo) ruoli. Alcuni gruppi di ruoli in Exchange Online sono bloccati e gestiti da Azure AD o dal Centro sicurezza e conformità &, ma altri potrebbero avere nomi uguali o simili e sono gestiti in Exchange Online (aggiungendo confusione). Ti consigliamo di evitare di usare l'Exchange Online utente a meno che non siano necessari ambiti per la Exchange gestione.

Non è possibile creare ruoli personalizzati. I ruoli sono definiti dai servizi creati da Microsoft e aumentano man quando vengono introdotti nuovi servizi. Questo concetto è simile ai [ruoli definiti dalle applicazioni](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) in Azure AD. Quando vengono abilitati nuovi servizi, spesso è necessario creare nuovi gruppi di ruoli per concedere o delegare l'accesso a tali servizi (ad esempio, gestione [dei rischi insider).](../compliance/insider-risk-management-configure.md)

Questi gruppi di ruoli richiedono anche l'appartenenza diretta e non possono contenere gruppi di Azure AD. Purtroppo, oggi questi gruppi di ruoli non sono supportati da Azure AD PIM. Come i ruoli di Azure AD, tendo a consigliare la gestione di questi elementi tramite API o un prodotto di governance dei partner come Saviynt o altri.

I & del Centro sicurezza e conformità si estendono Microsoft 365 e non è possibile impostare l'ambito di questi gruppi di ruoli in un sottoinsieme dell'ambiente (come è possibile con le unità amministrative in Azure AD). Molti clienti si chiedono come possono eseguire la subdelegate. Ad esempio, "creare un criterio DLP solo per gli utenti dell'UE". Oggi, se si dispone dei diritti per una funzione specifica nel Centro sicurezza & conformità, si dispone dei diritti per tutti gli elementi coperti da questa funzione nel tenant. Tuttavia, molti criteri dispongono di funzionalità per la destinazione di un sottoinsieme dell'ambiente (ad esempio, "rendere queste etichette [disponibili](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) solo per questi utenti"). Una governance e una comunicazione corrette sono un componente chiave per evitare conflitti. Alcuni clienti scelgono di implementare un approccio "configurazione come codice" per affrontare la sottodelegazione nel Centro sicurezza & conformità. Alcuni servizi specifici supportano la sottodelegazione (vedere di seguito).

Vale la pena notare che i controlli attualmente gestiti tramite il Centro sicurezza & conformità (protection.office.com) sono in fase di migrazione in due portali di amministrazione separati: security.microsoft.com e compliance.microsoft.com. La modifica è l'unica costante.

### <a name="service-specific"></a>Specifico del servizio

Come indicato in precedenza, molti clienti desiderano ottenere un modello di delega più granulare. Esempio comune: "Gestire il servizio XYZ solo per gli utenti e le posizioni di Divisione X" (o un'altra dimensione). La possibilità di eseguire questa operazione dipende da ogni servizio e non è coerente tra servizi e funzionalità. Inoltre, ogni servizio può avere un modello RBAC distinto e univoco. Invece di discutere di tutti questi elementi (ci sarà un'eternità), aggiungo collegamenti pertinenti per ogni servizio. Questo non è un elenco completo, ma ti permetterà di iniziare.

- **Exchange Online** - (/exchange/permissions-exo/permissions-exo)
- **SharePoint Online** - (/sharepoint/manage-site-collection-administrators)
- **Microsoft Teams** - (/microsoftteams/itadmin-readiness)
- **eDiscovery** - (.. /compliance/index.yml)
  - **Filtro autorizzazioni** - (.. /compliance/index.yml)
  - **Limiti di conformità** - (.. /compliance/set-up-compliance-boundaries.md)
  - **Advanced eDiscovery** - (.. /compliance/overview-ediscovery-20.md)
- **Yammer** - (/yammer/manage-yammer-users/manage-yammer-admins)
- **Multi-geo** - (.. /enterprise/add-a-sharepoint-geo-admin.md)
- **Dynamics 365** – (/dynamics365/)

  Nota: questo collegamento è alla radice della documentazione. Esistono più tipi di servizi con varianti nel modello di amministrazione/delega.

- **Power Platform** - (/power-platform/admin/admin-documentation)
  - **Power Apps** - (/power-platform/admin/wp-security)

    Nota: esistono più tipi con varianti nei modelli di amministrazione/delega.

  - **Power Automate** - (/power-automate/environments-overview-admin)
  - **Power BI** - (/power-bi/service-admin-governance)

    Nota: la sicurezza e la delega della piattaforma dati (che Power BI è un componente) è un'area complessa.

- **MEM/Intune** - (/mem/intune/fundamentals/role-based-access-control)
- **Microsoft Defender for Endpoint** - (/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - (.. /security/defender/m365d-permissions.md)
- **Microsoft Cloud App Security** - (/cloud-app-security/manage-admins)
- **Stream** - (/stream/assign-administrator-user-role)
- **Ostacoli alle informazioni** - (.. /compliance/information-barriers.md)

### <a name="activity-logs"></a>Log attività

Office 365 dispone di un [log di controllo unificato.](../compliance/search-the-audit-log-in-security-and-compliance.md) Si tratta di un [registro molto dettagliato,](/office/office-365-management-api/office-365-management-activity-api-schema)ma non leggere troppo nel nome. Potrebbe non contenere tutto ciò che si desidera o necessario per le esigenze di sicurezza e conformità. Inoltre, alcuni clienti sono molto interessati a [Advanced Audit.](../compliance/advanced-audit.md)

Di seguito sono Microsoft 365 di log a cui si accede tramite altre API:

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (attività non correlate Office 365)
- [Exchange Verifica messaggi](/powershell/module/exchange/get-messagetrace)
- Sistemi threat/UEBA descritti in precedenza (ad esempio, Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender for Endpoint e così via)
- [Microsoft Information Protection](../compliance/data-classification-activity-explorer.md)
- [Microsoft Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

È importante identificare innanzitutto tutte le origini dei registri necessarie per un programma di sicurezza e conformità. Tenere inoltre presente che log diversi hanno limiti di conservazione in linea diversi.

Dal punto di vista della delega dell'amministratore, la maggior parte Microsoft 365 di attività non dispone di un modello RBAC incorporato. Se si dispone dell'autorizzazione per visualizzare un registro, è possibile visualizzare tutti gli elementi in esso presenti. Un esempio comune di requisito del cliente è: "Voglio essere in grado di eseguire query sull'attività solo per gli utenti dell'Unione Europea" (o un'altra dimensione). Per ottenere questo requisito, è necessario trasferire i log in un altro servizio. Nel cloud Microsoft, è consigliabile trasferirlo in [Azure Sentinel](/azure/sentinel/overview) o [Log Analytics.](/azure/azure-monitor/learn/quick-create-workspace)

Diagramma di alto livello:

![Diagramma delle origini dei log per un programma di sicurezza e conformità](../media/solutions-architecture-center/identity-beyond-illustration-4.png)

Il diagramma precedente rappresenta funzionalità integrate per l'invio di log all'hub eventi e/o Archiviazione di Azure e/o ad Azure Log Analytics.The diagram above represents built-in capabilities to send logs to Event Hub and/or Archiviazione di Azure and/or Azure Log Analytics. Non tutti i sistemi includono ancora questa funzionalità. Esistono tuttavia altri approcci per inviare questi log allo stesso repository. Ad esempio, vedere [Protezione dei Teams con Azure Sentinel.](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)

La combinazione di tutti i log in un'unica posizione di archiviazione include vantaggi aggiunti, ad esempio correlazioni incrociate, tempi di conservazione personalizzati, aumento dei dati necessari per supportare il modello RBAC e così via. Una volta che i dati sono in questo sistema di archiviazione, è possibile creare un dashboard di Power BI (o un altro tipo di visualizzazione) con un modello RBAC appropriato.

I log non devono essere indirizzati a una sola posizione. Potrebbe anche essere utile integrare Office 365 [log](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) con Microsoft Cloud App Security o un modello RBAC personalizzato in [Power BI](../admin/usage-analytics/usage-analytics.md). Archivi diversi hanno vantaggi e gruppi di destinatari diversi.

Vale la pena ricordare che esiste un sistema di analisi incorporato molto ricco per sicurezza, minacce, vulnerabilità e così via in un servizio denominato [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md).

Molti clienti di grandi dimensioni desiderano trasferire questi dati di registro in un sistema di terze parti(ad esempio, SIEM). Esistono diversi approcci a questo scopo, ma in generale [Azure Event Hub](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) e Graph sono buoni punti di partenza. [](/graph/security-integration)

### <a name="azure"></a>Azure

Viene spesso chiesto se esiste un modo per separare i ruoli con privilegi elevati tra Azure AD, Azure e SaaS (ad esempio: Amministratore globale per Office 365 ma non Azure).  Non proprio.  L'architettura multi-tenant è necessaria se è necessaria una separazione amministrativa completa, ma ciò aggiunge [una complessità significativa](https://aka.ms/multi-tenant-user) (vedere sopra). Tutti questi servizi fanno parte dello stesso limite di sicurezza/identità (osservare il modello gerarchico precedente).

È importante comprendere le relazioni tra vari servizi nello stesso tenant. Sto lavorando con molti clienti che stanno creando soluzioni aziendali che si estendono su Azure, Office 365 e Power Platform (e spesso anche servizi cloud locali e di terze parti). Un esempio comune:

1. Voglio collaborare a un set di documenti/immagini/etc (Office 365)
2. Inviare ognuno di essi tramite un processo di approvazione (Power Platform)
3. Dopo l'approvazione di tutti i componenti, assemblare questi componenti in [un'API Microsoft Graph](/azure/active-directory/develop/microsoft-graph-intro) unificato è il tuo migliore amico.  Non impossibile, ma significativamente più complesso progettare una soluzione che si estende [su più tenant.](/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based Access Control (RBAC) consente una gestione degli accessi granulare per Azure. Utilizzando RBAC, è possibile gestire l'accesso alle risorse concedendo agli utenti il numero minimo di autorizzazioni necessarie per eseguire i propri processi. I dettagli non sono nell'ambito di questo documento, ma per ulteriori informazioni sul controllo degli accessi in base al ruolo, vedere Che cos'è il controllo di accesso basato sui ruoli [(RBAC) in Azure?](/azure/role-based-access-control/overview) Il controllo degli accessi in base al ruolo è importante, ma solo parte delle considerazioni sulla governance per Azure. [Cloud Adoption Framework è](/azure/cloud-adoption-framework/govern/) un ottimo punto di partenza per saperne di più. Mi piace il modo in cui il mio amico, Andres Ravinet, guida i clienti passo dopo passo, anche se diversi componenti per decidere l'approccio. La visualizzazione di alto livello per vari elementi (non buona come il processo per arrivare al modello di cliente effettivo) è simile alla seguente:

![Visualizzazione di alto livello dei componenti di Azure per l'amministrazione delegata](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Come si può vedere dall'immagine precedente, molti altri servizi devono essere considerati come parte [](/azure/governance/management-groups/)della progettazione (ad esempio: Criteri di [Azure,](/azure/governance/policy/overview) [Blueprint di Azure,](/azure/governance/blueprints/overview)gruppi di gestione e così via).

## <a name="conclusion"></a>Conclusione

Iniziato come breve riepilogo, è finito più a lungo di quanto mi aspettassi.  Mi auguriamo che tu sia ora pronto ad affrontare un'approfondita conoscenza della creazione del modello di delega per la tua organizzazione.  Questa conversazione è molto comune con i clienti. Non esiste un modello che funzioni per tutti. In attesa di alcuni miglioramenti pianificati dalla progettazione Microsoft prima di documentare i modelli comuni che vediamo tra i clienti. Nel frattempo, è possibile collaborare con il team dell'account Microsoft per organizzare una visita al [Microsoft Technology Center più vicino.](https://www.microsoft.com/mtc)  Ci vediamo lì!
