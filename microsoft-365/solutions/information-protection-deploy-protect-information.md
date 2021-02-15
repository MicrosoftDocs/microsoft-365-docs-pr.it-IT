---
title: Proteggere le informazioni soggette alle normative sulla privacy dei dati
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Distribuire le funzionalità di sicurezza e conformità di Microsoft 365 e proteggere le informazioni personali.
ms.openlocfilehash: f17568c5a19446644cfb7ee64aac3e0f9eae5793
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988483"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteggere le informazioni soggette alle normative sulla privacy dei dati

Nell'abbonamento è possibile utilizzare diversi controlli di protezione delle informazioni per soddisfare le esigenze e le normative di conformità alla privacy dei dati. Questi includono il Regolamento generale sulla protezione dei dati (GDPR), HIPAA-HITECH (united States health care privacy act), California Consumer Protection Act (CCPA) e il Brazil Data Protection Act (LGPD).

Questi controlli sono all'interno delle aree della soluzione seguenti:

- Etichette di riservatezza
- Prevenzione della perdita di dati (DLP)
- Crittografia messaggi di Office (OME)
- Controlli di accesso a Teams e siti

![Servizi chiave per proteggere le informazioni personali soggette alle normative sulla privacy dei dati](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Questa soluzione descrive le funzionalità di sicurezza e conformità per proteggere le informazioni soggette alle normative sulla privacy dei dati. Per un elenco completo delle funzionalità di sicurezza in Microsoft 365, vedere la documentazione sulla sicurezza [di Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/) Per un elenco completo delle funzionalità di conformità in Microsoft 365, vedere la [documentazione di conformità di Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/)
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Normative sulla privacy dei dati che influiscono sui controlli di protezione delle informazioni

Ecco un elenco di esempio delle normative sulla privacy dei dati che possono riguardare i controlli di protezione delle informazioni:

- ARTICOLO 5(1)(f))
- Articolo GDPR (32)(1)(a)
- Articolo LGPD 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Vedere [l'articolo valutare i rischi](information-protection-deploy-assess.md) per la privacy dei dati e identificare gli elementi sensibili per ulteriori informazioni su ognuno di questi articoli.

Le normative sulla privacy dei dati per la protezione delle informazioni consigliano:

- Protezione contro la perdita o l'accesso non autorizzato, l'utilizzo e/o la trasmissione.
- Applicazione basata sul rischio di meccanismi di protezione.
- Utilizzo della crittografia, se appropriato.

L'organizzazione potrebbe anche voler proteggere i contenuti di Microsoft 365 per altri scopi, ad esempio per altre esigenze di conformità o per motivi aziendali. La definizione dello schema di protezione delle informazioni per la privacy dei dati deve essere effettuata nell'ambito della pianificazione, dell'implementazione e della gestione generali della protezione delle informazioni.

Per iniziare a usare uno schema di protezione delle informazioni in Microsoft 365, la sezione seguente include un breve elenco delle funzionalità correlate e delle azioni di miglioramento per Microsoft 365. L'elenco include funzionalità e azioni di miglioramento applicabili alle normative sulla privacy dei dati. Tuttavia, l'elenco non include le tecnologie meno recenti se esiste una funzionalità più recente che sostituisce in gran parte quella precedente. Ad esempio, Information Rights Management (IRM) per SharePoint e OneDrive non è incluso nell'elenco, ma sono incluse le etichette di riservatezza.

## <a name="managing-information-protection-in-microsoft-365"></a>Gestione della protezione delle informazioni in Microsoft 365

Le [soluzioni microsoft di protezione delle](../compliance/information-protection.md) informazioni includono una serie di funzionalità integrate in Microsoft 365, Microsoft Azure e Microsoft Windows. In Microsoft 365, le soluzioni di protezione delle informazioni includono:

- [Crittografia del servizio con Customer Key](../compliance/customer-key-overview.md)
- [Tipi di informazioni riservate](../compliance/what-the-sensitive-information-types-look-for.md) (descritti nell'articolo valutare i rischi per la privacy dei [dati e identificare gli elementi sensibili)](information-protection-deploy-assess.md)
- [Etichette di riservatezza](../compliance/sensitivity-labels.md) 
  - Servizio/livello contenitore
  - Lato client/livello di contenuto
  - Automatizzato per i dati in pausa in SharePoint e OneDrive
- Prevenzione della perdita dei dati (DLP)
- [Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (anteprima)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- [Office 365 Message Encryption new capabilities (OME)](../compliance/ome.md) and OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md)

Inoltre, la protezione a livello di sito e raccolta è un meccanismo importante da includere in qualsiasi schema di protezione.

Per informazioni su altre funzionalità di protezione delle informazioni esterne a Microsoft 365, vedere:

- [Microsoft Cloud Application Security (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Le etichette di riservatezza del framework di Microsoft Information Protection consentono di classificare e proteggere i dati dell'organizzazione senza ostacolare la produttività degli utenti e la loro capacità di collaborare.

![Etichette di riservatezza in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Prerequisiti per le etichette di riservatezza

Completa queste attività prima di implementare una qualsiasi delle funzionalità basate su etichette di riservatezza evidenziate di seguito:

1. Comprendere quanto segue:
   - **Requisiti aziendali.** Stabilire i motivi aziendali per l'applicazione delle etichette di riservatezza nell'organizzazione. Ad esempio, i requisiti di privacy dei dati per la protezione delle informazioni.
   - **Funzionalità delle etichette di riservatezza.** L'etichettatura di riservatezza può essere complessa, quindi assicurati di leggere la documentazione relativa alle etichette di [riservatezza](../compliance/sensitivity-labels.md) prima di iniziare.
   - **Aspetti principali da ricordare** Le etichette di riservatezza vengono gestite nell'interfaccia di amministrazione di Conformità Microsoft, ma le opzioni di destinazione e applicazione variano in modo significativo.
      - Esistono etichette di riservatezza per siti, gruppi e Teams a livello di contenitore (le impostazioni non si applicano al contenuto all'interno del contenitore). Vengono pubblicati per gli utenti e i gruppi che li applicano quando viene eseguito il provisioning di un sito, un gruppo o un team.
      - Sono disponibili etichette di riservatezza per il contenuto attivo. Vengono pubblicati anche per utenti o gruppi, che possono applicarli manualmente o vengono applicati automaticamente quando:
        - Il file viene aperto,modificato/salvato sul desktop dell'utente o in un sito di SharePoint.
        - Un messaggio di posta elettronica viene redatto e inviato.
      - Esistono etichette di riservatezza per l'applicazione automatica ai file in pausa in SharePoint e OneDrive oltre ai messaggi di posta elettronica in transito tramite Exchange. Sono destinati a tutti i siti o a quelli specifici e vengono applicati automaticamente ai file in stato di inquieto in questi ambienti.

2. Razionalizzare l'etichettatura di riservatezza corrente con metodi alternativi o precedenti

   - Azure Information Protection

      Lo schema di etichettatura di riservatezza corrente potrebbe dover essere riconciliato con qualsiasi implementazione di [etichettatura](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) di Azure Information Protection esistente.
   - OME

      Se si prevede di utilizzare l'etichettatura di riservatezza moderna per la protezione della posta elettronica e sono presenti metodi di crittografia della posta elettronica esistenti come OME, possono coesistere, ma è necessario comprendere gli scenari in cui devono essere applicati. Vedere [Office 365 Message Encryption new capabilities (OME),](#office-365-message-encryption-ome-new-capabilities)che include una tabella che confronta la protezione moderna del tipo di etichetta di riservatezza con la protezione basata su OME.

3. Pianificare l'integrazione in uno schema di protezione delle informazioni più ampio. Oltre alla coesistenza con OME, le etichette di riservatezza correnti possono essere usate insieme a funzionalità come la prevenzione della perdita di dati (DLP) di Microsoft 365 e Microsoft Cloud App Security. Vedere [Etichette di riservatezza e Microsoft Cloud App Security](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) per raggiungere gli obiettivi di protezione delle informazioni correlati alla privacy dei dati.

4. Sviluppare una classificazione e uno schema di controllo delle etichette di riservatezza. Vedere [Classificazione dei dati e tassonomia delle etichette di riservatezza.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>Indicazioni generali

1. **Definizione dello schema.** Prima di usare le funzionalità tecniche per applicare etichette e protezione, lavorare all'interno dell'organizzazione per definire uno schema di classificazione. Potrebbe essere già presente uno schema di classificazione, che semplifica l'aggiunta di dati personali. 
2. **Guida introduttiva.** Iniziare decidendo il numero e i nomi delle etichette da implementare. Eseguire questa attività senza preoccuparsi della tecnologia da usare e della modalità di applicazione delle etichette. Applicare questo schema universalmente all'interno dell'organizzazione, inclusi i dati che risiedono in locale e in altri servizi cloud.
3. **Consigli aggiuntivi** Durante la progettazione e l'implementazione di criteri, etichette e condizioni, è consigliabile seguire questi suggerimenti:

   - **Utilizzare lo schema di classificazione esistente (se presente).** Molte organizzazioni usano già la classificazione dei dati in qualche modo. Valutare attentamente lo schema di etichette esistente e, se possibile, utilizzarlo così come è. L'uso di etichette note e riconoscibili per gli utenti finali inseporterà l'adozione.
   - **Iniziare con un valore piccolo.** Il numero di etichette che è possibile creare è praticamente illimitato. Tuttavia, un numero elevato di etichette ed etichette secondarie può rallentare l'adozione.
   - **Utilizzare scenari e casi d'uso.** Identificare i casi d'uso comuni all'interno dell'organizzazione e gli scenari di utilizzo derivati dalle normative sulla privacy dei dati a cui si è soggetti. Verificare se la configurazione dell'etichetta e della classificazione previsto funzionerà nella pratica.
   - **Interrogare ogni richiesta di una nuova etichetta.** Ogni scenario o caso d'uso ha effettivamente bisogno di una nuova etichetta o è possibile usare ciò che si ha già? Mantenere il numero minimo di etichette migliora l'adozione.
   - **Utilizzare etichette secondarie per i reparti chiave.** Alcuni reparti hanno esigenze specifiche che richiedono etichette specifiche. Definire queste etichette come etichette secondarie a un'etichetta esistente e prendere in considerazione l'uso di criteri con ambito assegnati ai gruppi di utenti anziché a livello globale.
   - **Considerare i criteri con ambito.** I criteri destinati a sottoinsiemi di utenti impediranno il sovraccarico delle etichette. Un criterio con ambito consente di assegnare etichette o etichette secondarie specifiche del ruolo o del reparto solo ai dipendenti che lavorano per quel reparto specifico. 
   - **Utilizzare nomi di etichetta significativi.** Cerca di non usare il gergo, gli standard o gli acronimi come nomi di etichetta. Prova a usare nomi che risuonano con l'utente finale per migliorare l'adozione. Invece di usare etichette come PII, PCI, HIPAA, LBI, MBI e HBI, prendi in considerazione nomi come Non aziendale, Pubblico, Generale, Riservato ed Estremamente riservato.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Creare e distribuire etichette di riservatezza per siti, gruppi e team

Quando si creano [etichette di riservatezza](../compliance/sensitivity-labels-teams-groups-sites.md) nel Centro conformità Microsoft 365, è ora possibile applicarle a questi contenitori:

- Siti di Microsoft Teams
- Gruppi di Microsoft 365 (in precedenza gruppi di Office 365)
- Siti di SharePoint

Usare le impostazioni di etichetta seguenti per proteggere il contenuto in tali contenitori:

- Privacy (pubblica o privata) dei siti di Teams connessi al gruppo di Microsoft 365
- Accesso utenti esterni
- Accesso da dispositivi non gestiti

Per la privacy dei dati, per impedire la condivisione esterna per i contenitori che verranno utilizzati per l'archiviazione di contenuto con dati personali sensibili, contrassegnare i file contenenti i dati come privati e richiedere dispositivi gestiti.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Creare e distribuire etichette di riservatezza per il contenuto

Le etichette di riservatezza applicate ai file consentono di crittografarne il contenuto, applicare una filigrana al contenuto e definire altri controlli per il contenuto delle applicazioni di Office, tra cui Outlook e Office sul Web.

Quando si è pronti per iniziare a proteggere i dati dell'organizzazione con etichette di riservatezza:

1. **Creare le etichette.** Creare e assegnare un nome alle etichette di riservatezza in base alla tassonomia di classificazione dell'organizzazione per i diversi livelli di riservatezza del contenuto. Per ulteriori informazioni sullo sviluppo di una tassonomia di classificazione, vedere il white paper Classificazione dei dati e [tassonomia](https://aka.ms/dataclassificationwhitepaper)delle etichette di riservatezza.
2. **Definire le caratteristiche di ogni etichetta.** Configurare le impostazioni di protezione che si vogliono associare a ciascuna etichetta. Ad esempio, potrebbe essere necessario applicare solo un'intestazione o un piè di pagina a contenuto con riservatezza inferiore (ad esempio un'etichetta "Generale"), mentre a un contenuto con maggiore riservatezza (ad esempio un'etichetta "Riservato") deve essere applicata una filigrana e la crittografia è abilitata.
3. **Pubblicare le etichette.** Dopo aver configurato le etichette di riservatezza, pubblicarle usando un criterio di etichetta. Decidere quali utenti e gruppi devono avere le etichette e quali impostazioni dei criteri usare. Una singola etichetta è riutilizzabile. È possibile definirla una sola volta e quindi includerla in diversi criteri di etichetta assegnati a utenti diversi.

Dopo aver pubblicato le etichette di riservatezza dal Centro conformità Microsoft 365, iniziano a essere visualizzate nelle app di [Office](../compliance/sensitivity-labels-office-apps.md) per consentire agli utenti di classificare e proteggere il contenuto durante la creazione o la modifica.

![Flusso di distribuzione delle etichette di riservatezza in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Per la privacy dei dati, si applica manualmente un'etichetta di riservatezza con crittografia e altre regole alla posta elettronica o al contenuto contenente informazioni personali riservate.

>[!Note]
>Le etichette di riservatezza con la crittografia abilitata alla posta elettronica hanno alcune funzionalità sovrapposte con OME. Vedere [Confronto tra scenari di posta elettronica sicura e OME e etichette di riservatezza.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Applicazione automatica di etichette sul lato client quando gli utenti modificano documenti o compongono messaggi di posta elettronica

Quando si crea un'etichetta [](../compliance/apply-sensitivity-label-automatically.md) di riservatezza, è possibile assegnarla automaticamente al contenuto, incluso il messaggio di posta elettronica, quando soddisfa le condizioni specificate.

La possibilità di applicare automaticamente etichette di riservatezza al contenuto è importante perché:

- Non è necessario spiegare agli utenti quando usare le singole classificazioni.
- Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.
- Gli utenti non hanno più bisogno di conoscere i criteri e possono concentrarsi sul loro lavoro.

L'applicazione automatica di etichette supporta la raccomandazione di un'etichetta agli utenti, nonché l'applicazione automatica di un'etichetta. In entrambi i casi, comunque, l'utente decide se accettarla o rifiutarla, per garantire la corretta etichettatura del contenuto.

Questa etichettatura lato client ha un ritardo minimo per i documenti perché l'etichetta può essere applicata anche prima di salvare il documento. Tuttavia, non tutte le app client supportano l'etichettatura automatica. Questa funzionalità è supportata dal client di etichettatura unificata di Azure Information Protection e da [alcune versioni delle app di Office.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Per istruzioni sulla configurazione, vedere [Come configurare l'etichettatura automatica per le app di Office.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Per la privacy dei dati, si applicano automaticamente etichette di riservatezza per il contenuto contenente informazioni personali riservate.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Applicazione automatica di etichette sul lato servizio quando il contenuto è già salvato

Questo metodo è denominato classificazione automatica con etichette di riservatezza. Si potrebbe anche sentire come applicazione automatica di etichette per i dati in stato di inquieto (per i documenti in SharePoint e OneDrive) e i dati in transito (per i messaggi di posta elettronica inviati o ricevuti da Exchange). Per Exchange, non include i messaggi di posta elettronica nelle cassette postali in stato di inquieto.
 
Poiché questa etichettatura viene applicata dal servizio stesso anziché dall'applicazione utente, non è necessario preoccuparsi delle app degli utenti e della versione. Di conseguenza, questa funzionalità è immediatamente disponibile nell'intera organizzazione ed è adatta per l'applicazione di etichette su vasta scala. I criteri di applicazione automatica di etichette non supportano l'applicazione di etichette consigliate perché l'utente non interagisce con il processo di etichettatura. L'amministratore esegue invece i criteri in modalità di simulazione per garantire la corretta etichettatura del contenuto prima dell'applicazione effettiva dell'etichetta.

Per istruzioni sulla configurazione, vedere Come configurare i criteri di applicazione automatica di etichette [per SharePoint, OneDrive ed Exchange.](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

Per la privacy dei dati all'interno dei siti di interesse, inserire etichette di riservatezza per la crittografia automatica dei contenuti contenenti informazioni personali riservate.

## <a name="data-loss-prevention"></a>Prevenzione della perdita di dati 

È possibile utilizzare la prevenzione della perdita dei dati [(DLP)](../compliance/data-loss-prevention-policies.md) in Microsoft 365 per rilevare, avvisare e bloccare la condivisione rischiosa, involontaria o inappropriata, ad esempio la condivisione di dati contenenti informazioni personali, sia internamente che esternamente.

DLP consente di:

- Identificare e monitorare le attività di condivisione rischiose.
- Formare gli utenti con indicazioni nel contesto per prendere le decisioni corrette.
- Applicare criteri di utilizzo dei dati al contenuto senza inibire la produttività.
- Integrare con la classificazione e l'etichettatura per rilevare e proteggere i dati quando vengono condivisi.

### <a name="supported-workloads-for-dlp"></a>Carichi di lavoro supportati per DLP

Con un criterio DLP nel Centro conformità Microsoft 365, è possibile identificare, monitorare e proteggere automaticamente gli elementi sensibili in molte posizioni in Microsoft 365, ad esempio Exchange Online, SharePoint, OneDrive e Microsoft Teams.

Ad esempio, è possibile identificare qualsiasi documento contenente un numero di carta di credito archiviato in qualsiasi sito di OneDrive oppure monitorare solo i siti di OneDrive di persone specifiche.

È inoltre possibile monitorare e proteggere gli elementi sensibili nelle versioni installate localmente di Excel, PowerPoint e Word, che includono la possibilità di identificare gli elementi sensibili e applicare i criteri DLP. DLP fornisce un monitoraggio continuo quando gli utenti condividono il contenuto di queste app di Office.

![Carichi di lavoro supportati per DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

Questa figura mostra un esempio di prevenzione della perdita dei dati (DLP) che protegge i dati personali.

![Esempio di protezione dei dati personali tramite DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP viene utilizzato per identificare un documento o un messaggio di posta elettronica contenente un record di integrità e quindi blocca automaticamente l'accesso a tale documento o impedisce l'invio del messaggio di posta elettronica. Dlp invia quindi una notifica al destinatario con un suggerimento per i criteri e invia un avviso all'utente finale e all'amministratore.

### <a name="planning-for-dlp"></a>Pianificazione della prevenzione della perdita dei dati

Pianificare i criteri DLP per: 

- Requisiti aziendali.

- Una valutazione basata sui rischi dell'organizzazione, come descritto nell'articolo valutare i rischi per la privacy dei [dati e identificare gli elementi sensibili.](information-protection-deploy-assess.md)

- Altri meccanismi di protezione delle informazioni e governance in atto o nella pianificazione della privacy dei dati.

- I tipi di informazioni riservate identificati per i dati personali in base al lavoro di valutazione, come descritto nell'articolo valutare i rischi per la privacy dei dati e [identificare gli elementi sensibili.](information-protection-deploy-assess.md) Le condizioni dei criteri DLP possono essere basate sia sui tipi di informazioni riservate che sulle etichette di conservazione.

- Le etichette di conservazione necessarie per specificare le condizioni DLP. Per ulteriori [informazioni, vedere l'articolo](information-protection-deploy-govern.md) sulla governance delle informazioni soggette alla normativa sulla privacy dei dati nell'articolo dell'organizzazione.

- Gestione continua dei criteri DLP, che richiede a un utente dell'organizzazione di operare e ottimizzare i criteri per le modifiche ai tipi di informazioni riservate, alle etichette di conservazione, alle normative e ai criteri di conformità.

Anche se le etichette di riservatezza non possono essere utilizzate nelle condizioni dei criteri DLP, alcuni scenari di protezione per impedire l'accesso possono essere raggiungibili solo con etichette di riservatezza che possono essere applicate automaticamente in base ai tipi di informazioni riservate. Se è presente un'etichettatura di riservatezza affidabile, valutare se la prevenzione della perdita dei dati deve essere utilizzata per aumentare la protezione perché:

  - DLP può impedire la condivisione di file. Le etichette di riservatezza possono semplicemente impedire l'accesso.

  - DLP ha livelli di controllo più granulari in termini di regole, condizioni e azioni.

  - I criteri DLP possono essere applicati ai messaggi di chat e canali di Teams. Le etichette di riservatezza possono essere applicate solo a documenti e messaggi di posta elettronica.


### <a name="dlp-policies"></a>Criteri di prevenzione della perdita di dati (DLP)

I criteri DLP vengono configurati nell'interfaccia di amministrazione di Conformità Microsoft e specificano il livello di protezione, il tipo di informazioni riservate ricercate dal criterio e i carichi di lavoro di destinazione. I componenti di base sono costituiti dall'identificazione della protezione e dei tipi di dati.

![Configurazione dei criteri DLP in Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Ecco un esempio di criterio DLP per la consapevolezza del GDPR.

![Esempio di criterio DLP per la consapevolezza del GDPR](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Vedere [questo articolo](../compliance/create-test-tune-dlp-policy.md) per ulteriori informazioni sulla creazione e l'applicazione di criteri DLP.

### <a name="protection-levels-for-data-privacy"></a>Livelli di protezione per la privacy dei dati

Nella tabella seguente sono elencate tre configurazioni per aumentare la protezione tramite DLP.

![Livelli di protezione della privacy dei dati con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

La prima configurazione, Consapevolezza, può essere usata come punto di partenza e livello minimo di protezione per soddisfare le esigenze di conformità per le normative sulla privacy dei dati.

>[!Note]
>Con l'aumentare dei livelli di protezione, la capacità degli utenti di condividere e accedere alle informazioni diminuisce in alcuni casi e potrebbe influire potenzialmente sulla produttività o sulla capacità di completare le attività quotidiane.
>

Per aiutare i dipendenti a continuare a essere produttivi in un ambiente più sicuro quando aumentano i livelli di protezione, prendere il tempo necessario per formarli ed educarli su nuovi criteri e procedure di sicurezza.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Esempio di utilizzo delle etichette di riservatezza con DLP

Le etichette di riservatezza possono collaborare con DLP per garantire la privacy dei dati in un ambiente altamente regolamentato. Ecco i passaggi principali della distribuzione integrata:

1. Sono documentati i requisiti normativi e aziendali per la privacy dei dati.
2. Le origini dati, i tipi e la proprietà di destinazione sono caratterizzati da problematiche relative alla privacy dei dati.
3. Viene stabilita una strategia generale per soddisfare i requisiti e proteggere e gestire gli hotspot di privacy dei dati.
4. È stato messo in atto un piano d'azione in più fasi per affrontare la strategia di controllo della privacy dei dati.

Una volta determinati questi elementi, è possibile utilizzare i tipi di informazioni riservate, la tassonomia di etichettatura di riservatezza e i criteri DLP insieme. Questa figura mostra un esempio.

![Esempio di etichette di riservatezza che funzionano con DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Vedere una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Di seguito sono riportati alcuni scenari di protezione dei dati che utilizzano le etichette di riservatezza e DLP insieme, come illustrato nella figura.

| Scenario | Procedura |
|:-------|:-----|
| A | <ol><li>Le etichette di riservatezza per il contenuto vengono pubblicate da un amministratore per utenti e gruppi per l'applicazione manuale o automatica al contenuto e alla posta elettronica. </li><li>L'utente A applica le etichette manualmente o automaticamente quando interagisce con il contenuto, con la crittografia o altre impostazioni applicate. </li><li>L'utente A invia un messaggio di posta elettronica o un file protetto all'utente B, un utente guest. </li></ol> |
| B | Il criterio DLP pubblicato da un amministratore per l'utente A impedisce all'utente A di inviare la posta elettronica e/o il file all'utente B. |
| C |  L'etichetta di riservatezza con l'impostazione "Il proprietario non può invitare utenti guest" viene pubblicata per l'utente A, che effettua il provisioning di un team di Teams o di un sito di SharePoint. Un altro utente del sito tenta in modo selettivo di condividere un file con l'utente B, ma DLP lo blocca. |
| D | L'etichetta di riservatezza per l'applicazione automatica al contenuto del sito viene pubblicata in uno o più siti, fornendo un altro livello di protezione, con conseguente creazione di un sito protetto. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Nuove funzionalità di Office 365 Message Encryption (OME)

Le persone spesso usano la posta elettronica per scambiare elementi sensibili, ad esempio informazioni sulla salute dei pazienti o informazioni su clienti e dipendenti. La crittografia dei messaggi di posta elettronica garantisce che solo i destinatari previsti possano visualizzare il contenuto del messaggio.

Con [OME,](../compliance/ome.md)è possibile inviare e ricevere messaggi crittografati tra persone interne ed esterne all'organizzazione. OME funziona con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. OME garantisce che solo i destinatari previsti possano visualizzare il contenuto dei messaggi.

Per la privacy dei dati, utilizzare OME per proteggere i messaggi interni contenenti elementi sensibili. Crittografia messaggi di Office 365 è un servizio online basato su Microsoft Azure Rights Management (Azure RMS) che fa parte di Azure Information Protection. Sono inclusi i criteri di crittografia, identità e autorizzazione per proteggere la posta elettronica. È possibile crittografare i messaggi utilizzando modelli di Rights Management, l'opzione Non inoltrare e l'opzione solo crittografia.

È inoltre possibile definire le regole del flusso di posta per applicare questa protezione. Ad esempio, è possibile creare una regola che richiede la crittografia di tutti i messaggi indirizzati a un destinatario specifico o che contiene parole chiave specifiche nella riga dell'oggetto e inoltre specificare che i destinatari non possono copiare o stampare il contenuto del messaggio.

Inoltre, OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md) consente di soddisfare gli obblighi di conformità che richiedono controlli più flessibili sui destinatari esterni e il loro accesso ai messaggi di posta elettronica crittografati. Con OME Advanced Message Encryption in Microsoft 365, è possibile controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che rilevano i tipi di informazioni riservate. 

Per la privacy dei dati, se è necessario condividere la posta elettronica con una parte esterna, è possibile specificare una data di scadenza e revocare i messaggi. È possibile revocare e impostare una data di scadenza solo per i messaggi inviati a destinatari esterni.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Confronto tra scenari di posta elettronica sicuri e OME e etichette di riservatezza

Le etichette di riservatezza e OME applicate alla posta elettronica con crittografia si sovrappongono, quindi è importante comprendere a quali scenari possono applicarsi, come illustrato in questa tabella.

| Scenario | Etichette di riservatezza | OME |
|:-------|:-----|:-------|
| Internal + partners <br> Comunicare e collaborare in modo sicuro tra utenti interni e partner attendibili | Consigliato: etichette con classificazione e protezione completamente personalizzate | Sì: crittografa solo la protezione o Non inoltrare senza classificazione |
| Parti esterne <br> Comunicare e collaborare in modo sicuro con qualsiasi utente esterno/consumer | Sì: predefinire i destinatari nell'etichetta | Consigliato: protezione just-in-time in base ai destinatari |
| Interno + partner, con scadenza/revoca <br> Controllare l'accesso alla posta e al contenuto con utenti interni e partner attendibili con scadenza e revoca | Consigliato: protezione completamente personalizzata con durata di accesso, l'utente può tenere traccia e revocare manualmente i file | No: nessuna revoca o scadenza per la posta interna |
| Parti esterne con scadenza/revoca <br> Controllare l'accesso alla posta e al contenuto con utenti esterni/consumer con scadenza e revoca | Sì: l'utente può tenere traccia manualmente dei file | Consigliato (E5): l'amministratore può revocare la posta dal Centro sicurezza & conformità |
| Etichettatura automatica <br> L'organizzazione desidera proteggere automaticamente la posta/gli allegati con contenuti sensibili specifici e/o destinatari specifici | Consigliato (E5) - Applicazione automatica di etichette nei client Exchange e Outlook, aumenta le regole del flusso di posta e i criteri DLP | Sì: regole del flusso di posta e criteri DLP con protezione Solo crittografia o Non inoltrare |
||||

Tra questi due metodi ci saranno anche differenze nell'esperienza degli utenti finali e degli amministratori.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams con protezione per i dati altamente sensibili

Per le organizzazioni che pianificano di archiviare i dati personali soggetti alle normative sulla privacy dei dati in Teams, vedere Configurare un [team](secure-teams-security-isolation.md)con isolamento della sicurezza, che fornisce istruzioni dettagliate e procedure di configurazione per:

- Accesso a identità e dispositivi
- Creazione di un team privato
- Blocco delle autorizzazioni del sito del team sottostanti
- Un'etichetta di riservatezza basata su gruppo con crittografia
