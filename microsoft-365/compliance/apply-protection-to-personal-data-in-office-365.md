---
title: Applicare protezione ai dati personali
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come usare i criteri di prevenzione della perdita dei dati (DLP) nel Centro conformità per proteggere i dati personali in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f5c82a1f841cca1eea9a79d8f9dbcc1f81a3ad74
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035178"
---
# <a name="apply-protection-to-personal-data"></a>Applicare protezione ai dati personali

La protezione delle informazioni personali di Microsoft 365 include l'uso delle funzionalità di prevenzione della perdita dei dati. I criteri di prevenzione della perdita dei dati del centro conformità permettono di identificare, monitorare e proteggere automaticamente le informazioni sensibili in tutto Microsoft 365.

In questo argomento viene descritto come usare la prevenzione della perdita dei dati per proteggere i dati personali. Inoltre, vengono elencate altre funzionalità di protezione che possono essere usate per raggiungere la conformità con il GDPR, tra cui l'impostazione delle autorizzazioni nelle raccolte di SharePoint e l'uso di criteri di accesso ai dispositivi.

## <a name="apply-protection-using-data-loss-prevention-in-microsoft-365"></a>Applicare la protezione utilizzando la prevenzione della perdita di dati in Microsoft 365

Con DLP, è possibile:

-   Identificare informazioni riservate in più percorsi.

-   Impedire la condivisione accidentale di informazioni riservate.

-   Fornire agli utenti informazioni su come garantire la conformità senza interrompere il flusso di lavoro.

-   Visualizzare report DLP che indicano i contenuti corrispondenti ai criteri DLP dell'organizzazione.

Per ulteriori informazioni, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).

![Opzioni per la creazione del criterio DLP](../media/Apply-protection-to-personal-data-in-Office-365-image1.png)

L'illustrazione seguente mostra le opzioni per la creazione di un criterio DLP:

-   Scegliere la protezione da applicare. La protezione può includere:

    -   Suggerimenti per i criteri per gli utenti

    -   Report di posta elettronica per gli amministratori

    -   Impedire la condivisione esternamente, internamente o entrambe

-   Scegliere i criteri per l'applicazione della protezione. Applicare la protezione ai documenti con questo tipo di contenuto: è possibile configurare il criterio per utilizzare tipi e/o etichette di informazioni riservate.

### <a name="using-dlp-for-gdpr-compliance"></a>Usare DLP per la conformità con l'RGPD

Uno dei principali utilizzi di DLP di Microsoft 365 è quello di identificare dati personali correlati a soggetti dei dati europei nell'ambiente di Microsoft 365. DLP di Microsoft 365 è in grado di informare i team della conformità su dove le informazioni personali sono archiviate in SharePoint Online e OneDrive for Business oppure quando gli utenti inviano posta elettronica contenente informazioni personali. DLP è inoltre in grado di fornire suggerimenti per i criteri ai dipendenti quando utilizzano informazioni personali correlate a residenti nell'Unione Europea.

Formare e aumentare la consapevolezza di dove sono archiviate le informazioni sui residenti dell'Unione Europea nel proprio ambiente e sulle modalità di trattamento da parte dei dipendenti rappresenta un livello di protezione delle informazioni con DLP di Microsoft 365. Spesso, i dipendenti che hanno già accesso a questo tipo di informazioni richiedono questo accesso per svolgere le proprie attività quotidiane. L'applicazione dei criteri DLP per consentire il rispetto del GDPR potrebbe non richiedere la limitazione dell'accesso.

Tuttavia, rispettare l'RGPD generalmente presenta una valutazione basata sul rischio dell'organizzazione da una prospettiva di sicurezza delle informazioni e legale, l'identificazione del tipo e di dove sono archiviate le informazioni e se esiste una giustificazione legale per archiviare ed elaborare tali informazioni. In base a questa valutazione, l'implementazione dei criteri per proteggere l'organizzazione e rispettare l'RGPD potrebbe richiedere la rimozione dell'accesso dei dipendenti ai documenti contenenti informazioni personali sui soggetti dei dati europei. Nei casi in cui è richiesta ulteriore protezione, è possibile configurare protezione DLP aggiuntiva.

L'elenco seguente elenca tre configurazioni per aumentare la protezione con DLP. La prima configurazione, le informazioni sulla presenza, può essere usata come punto di partenza e livello minimo di protezione per l'RGPD.

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a>Livelli di protezione di esempio possono essere configurati con criteri DLP e usati per la conformità RGPD

<table>
<thead>
<tr class="header">
<th align="left"><strong>Livello di protezione</strong></th>
<th align="left"><strong>Configurazione DLP per i documenti con informazioni personali di soggetti di dati dell'Unione Europea</strong></th>
<th align="left"><strong>Vantaggi e rischi</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Informazioni sulla presenza</td>
<td align="left"><p>Inviare notifiche tramite posta elettronica ai team di conformità quando questi dati vengono individuati nei documenti su SharePoint Online e OneDrive for Business.</p>
<p>Personalizzare e mostrare suggerimenti per i criteri ai dipendenti in SharePoint e OneDrive for Business quando si accede ai documenti contenenti questi dati.</p>
<p>Rilevare e segnalare quando questi dati vengono condivisi.</p></td>
<td align="left"><p>Sensibilizzare il team di conformità e i dipendenti in merito a dove vengono archiviati questi dati.</p>
<p>Formare i dipendenti sui criteri aziendali per la gestione dei documenti contenenti questi dati.</p>
<p>Non impedire ai dipendenti di condividere questi dati internamente o esternamente.</p>
<p>È possibile esaminare i report DLP sui dati condivisi e decidere se è necessario aumentare la protezione.</p></td>
</tr>
<tr class="even">
<td align="left">Impedire la condivisione esterna</td>
<td align="left"><p>Limitare l'accesso ai documenti contenenti questi dati in SharePoint Online e OneDrive for Business quando i contenuti vengono condivisi con gli utenti esterni.</p>
<p>Impedire l'invio di messaggi di posta elettronica con documenti contenenti questi dati a destinatari esterni.</p>
<p>Rilevare e segnalare quando questi dati vengono condivisi.</p></td>
<td align="left"><p>Impedisce la condivisione esterna di questi dati, consentendo ai dipendenti di lavorare a questi dati internamente.</p>
<p>È possibile esaminare i report DLP sui dati condivisi internamente e decidere se è necessario aumentare la protezione.</p></td>
</tr>
<tr class="odd">
<td align="left">Impedire la condivisione interna ed esterna</td>
<td align="left"><p>Limitare l'accesso ai documenti contenenti questi dati in SharePoint Online e OneDrive for Business quando i contenuti vengono condivisi internamente o esternamente.</p>
<p>Impedire l'invio di messaggi di posta elettronica contenenti questi dati a destinatari esterni e interni.</p></td>
<td align="left"><p>Impedisce la condivisione interna ed esterna di questi dati.</p>
<p>I dipendenti potrebbero non essere in grado di completare attività che richiedono di utilizzare questi dati.</p>
<p>È possibile esaminare i report DLP sui dati condivisi internamente ed esternamente e decidere se è necessario formare l'utente finale.</p></td>
</tr>
</tbody>
</table>

Nota: man mano che aumentano i livelli di protezione, la capacità degli utenti di accedere potrebbe ridursi in alcuni casi e ciò potrebbe influire potenzialmente sulla produttività o sulla capacità di completare le attività quotidiane. L'aumento dei livelli di protezione implementando criteri che hanno un impatto sui dipendenti è generalmente accompagnato dalla formazione dell'utente finale, educando gli utenti sui nuovi criteri di sicurezza e sulle procedure per aiutarli a continuare a essere produttivi in un ambiente più sicuro.

### <a name="example-dlp-policy-for-gdpr--awareness"></a>Esempio di criterio DLP per RGPD - Informazioni sulla presenza 

Nome: Informazioni sulla presenza di dati personali soggetti all'RGPD

Descrizione: visualizzare suggerimenti per i criteri ai dipendenti, informare i team di conformità quando questi dati vengono trovati nei documenti su SharePoint Online e OneDrive for Business, rilevare e segnalare quando questi dati vengono condivisi al di fuori dell'organizzazione.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controllo</strong></th>
<th align="left"><strong>Impostazioni</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Scegliere le informazioni da proteggere</td>
<td align="left">Selezionare un modello di criteri personalizzato.</td>
</tr>
<tr class="even">
<td align="left">Sedi</td>
<td align="left">Tutti i percorsi in Microsoft 365</td>
</tr>
<tr class="odd">
<td align="left">Trovare contenuto contenente</td>
<td align="left">Fare clic su "Modifica" e aggiungere tutti i tipi di informazioni riservate curate per il proprio ambiente.</td>
</tr>
<tr class="even">
<td align="left">Rilevare quando il contenuto è condiviso</td>
<td align="left">Selezionare questa casella e "con utenti esterni all'organizzazione".</td>
</tr>
<tr class="odd">
<td align="left">Comunicare agli utenti quando il contenuto corrisponde alle impostazioni dei criteri</td>
<td align="left"><p>Selezionare questa casella ("Mostra suggerimenti per i criteri agli utenti e invia loro una notifica tramite posta elettronica").</p>
<p>Fare clic su "Personalizza suggerimento e messaggio di posta elettronica" e aggiornali per il proprio ambiente. Vedere le notifiche predefinite in questo articolo: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Invio di notifiche tramite posta elettronica e visualizzazione dei suggerimenti per i criteri per i criteri DLP</a>.</p></td>
</tr>
<tr class="even">
<td align="left">Rilevare quando una determinata quantità di informazioni riservata viene condivisa in una sola volta</td>
<td align="left"><p>"Rilevare quando il contenuto condiviso contiene: almeno ____ istanze dello stesso tipo di informazioni riservate" — Impostare su 1.</p>
<p>"Invia rapporti operazioni non consentite tramite posta elettronica" — selezionare questa casella di controllo. Fare clic su "Scegli cosa includere nel rapporto e i destinatari". Non dimenticare di aggiungere il team di conformità.</p>
<p>"Limita chi può ricevere il contenuto e sovrascrivi il criterio" — deselezionare questa casella di controllo per ricevere notifiche sulle informazioni riservate senza impedire gli utenti di accedere a tali informazioni.</p></td>
</tr>
</tbody>
</table>

Tutti i percorsi includono:

- SharePoint Online

- Account OneDrive for Business

- Cassette postali di Exchange

Poiché Ricerca contenuto al momento non consente di testare tipi di informazioni riservate con la posta elettronica, prendere in considerazione l'idea di creare criteri separati per Exchange con un set secondario di informazioni riservate in ogni criterio, monitorando l'implementazione di questi criteri.

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-microsoft-365"></a>Ulteriore livello di protezione che è possibile applicare per proteggere i dati personali in Microsoft 365

I tipi, le etichette e i criteri di protezione della perdita di dati per le informazioni riservate consentono di identificare i documenti contenenti dati specifici e di applicare protezione. Tuttavia, queste protezioni dipendono dalle autorizzazioni appropriate stabilite per l'accesso a dati, utenti con account non danneggiati e dispositivi integri.

La seguente illustrazione mostra l'ulteriore livello di protezione che è possibile applicare per proteggere l'accesso ai dati personali.

![Ulteriore livello di protezione per proteggere l'accesso ai dati personali](../media/Apply-protection-to-personal-data-in-Office-365-image2.png)

Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Ambito della protezione</strong></th>
<th align="left"><strong>Funzionalità</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Protezione a livello di posta elettronica e documento (include posta in transito, ma non le cassette postali inattive al momento)</td>
<td align="left"><p>Tipi di informazioni riservate</p>
<p>Etichette di Office</p>
<p>Criteri di prevenzione della perdita dei dati</p>
<p>Crittografia dei messaggi di Microsoft 365</p></td>
</tr>
<tr class="even">
<td align="left">Protezione a livello di sito e raccolta (include siti di SharePoint Online e OneDrive for Business)</td>
<td align="left"><p>Autorizzazioni per siti e raccolte di SharePoint Online e OneDrive for Business</p>
<p>Criteri di condivisione esterna per SharePoint Online e OneDrive for Business (a livello di sito)</p>
<p>Criteri di accesso ai dispositivi a livello di sito
</p></td>
</tr>
<tr class="odd">
<td align="left">Protezione dell'accesso al servizio (include l'accesso a tutti i servizi in Microsoft 365)</td>
<td align="left"><p>Protezione dell'accesso a identità e dispositivi nella famiglia di prodotti Enterprise Mobility + Security (EMS)</p>
<p>Gestione accessi con privilegi</p>
<p>Funzionalità di sicurezza di Windows 10</p></td>
</tr>
</tbody>
</table>

Il resto di questo articolo fornisce informazioni su ciascuna delle categorie di protezione.

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a>Funzionalità che possono essere usate con l'RGPD

È possibile utilizzare le seguenti funzionalità in un ambiente configurato per la conformità RGPD. Queste funzionalità non sono necessarie per la conformità RGPD, ma possono essere utilizzate senza influenzare in modo negativo la capacità di individuare, proteggere, monitorare e segnalare dati in merito alla conformità RGPD.

Customer Key - Consente ai clienti di fornire e mantenere il controllo sulle chiavi di crittografia utilizzate per crittografare i dati inattivi in Microsoft 365. Consigliata solo per i clienti con l'esigenza normativa di gestire le proprie chiavi di crittografia.

Customer Lockbox — Customer Lockbox consente di controllare il modo in cui un tecnico del supporto Microsoft accede ai dati, se necessario, per risolvere un problema tecnico caso per caso. È possibile controllare se fornirgli l'accesso ai dati o meno. Per ogni richiesta, è previsto un tempo di scadenza.

## <a name="site-and-library-level-protection"></a>Protezione a livello di sito e raccolta

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a>Autorizzazioni per raccolte di SharePoint e OneDrive for Business

Usare le autorizzazioni in SharePoint per fornire o limitare l'accesso degli utenti al sito o ai suoi contenuti. Aggiungere i singoli utenti o gruppi di Azure Active Directory ai gruppi di SharePoint predefiniti. In alternativa, creare un gruppo personalizzato per un controllo più dettagliato.

![Livelli di autorizzazione dal controllo completo alla sola visualizzazione](../media/Apply-protection-to-personal-data-in-Office-365-image3.png)

L'illustrazione traccia i livelli di autorizzazione da Controllo completo a Solo visualizzazione. Nella seguente tabella sono incluse le stesse informazioni.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controllo completo</strong></th>
<th align="left"><strong>Progettazione</strong></th>
<th align="left"><strong>Modifica</strong></th>
<th align="left"><strong>Collaborazione</strong></th>
<th align="left"><strong>Lettura</strong></th>
<th align="left"><strong>Solo visualizzazione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left">Collaborazione + approvazione e personalizzazione</td>
<td align="left">Collaborazione + aggiunta, modifica ed eliminazione di elenchi (non solo delle voci degli elenchi)</td>
<td align="left">Visualizzazione, aggiunta, aggiornamento, eliminazione dei documenti e delle voci di elenchi</td>
<td align="left">Visualizzazione e download</td>
<td align="left">Visualizzazione senza download</td>
</tr>
</tbody>
</table>

Ulteriori informazioni:

-   [Informazioni sui i livelli di autorizzazione in SharePoint](https://support.office.com/it-IT/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [Informazioni sui gruppi di SharePoint](https://support.office.com/it-IT/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a>Criteri di condivisione esterna per le raccolte di SharePoint Online e OneDrive for Business

Molte organizzazioni consentono la condivisione esterna per supportare la collaborazione. È necessario capire come sono configurate le impostazioni nel tenant. Quindi rivedere le impostazioni di condivisione esterna per i siti che contengono dati personali.

Un utente esterno è un utente esterno all'organizzazione che viene invitato ad accedere ai siti e documenti di SharePoint Online, ma che non ha la licenza della sottoscrizione di SharePoint Online o Microsoft 365.

Criteri di condivisione esterna per SharePoint Online e OneDrive for Business.

-   È necessario essere un amministratore di SharePoint Online per configurare i criteri di condivisione.

-   È necessario essere il proprietario del sito o avere le autorizzazioni controllo complete per condividere un sito o documento con utenti esterni.

Nella tabella riportata di seguito vengono riassunti i controlli che è possibile configurare.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Categoria di controllo</strong></th>
<th align="left"><strong>Opzioni</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo di condivisione</td>
<td align="left"><p>Non consentire la condivisione all'esterno dell'organizzazione (può essere impostata per singole raccolte siti)</p>
<p>Consentire la condivisione solo con utenti esterni autenticati (consentire nuovo o limitare agli esistenti, può essere impostata per singole raccolte siti)</p>
<p>Consentire la condivisione con utenti esterni con un collegamento per l'accesso anonimo (può essere impostata per singole raccolte siti)</p>
<p>Limitare la condivisione esterna tramite i domini (consentire e rifiutare elenchi)</p>
<p>Scegliere il tipo di collegamento predefinito (anonimo, condivisibile con l'azienda o limitato)</p>
</td>
</tr>
<tr class="even">
<td align="left">Cosa possono fare gli utenti esterni</td>
<td align="left"><p>Impedire agli utenti esterni di condividere file, cartelle, siti che non possiedono</p>
<p>Richiedere agli utenti esterni di accettare la condivisione degli inviti con lo stesso account a cui è stato inviato l'invio</p></td>
</tr>
<tr class="odd">
<td align="left">Notifiche</td>
<td align="left"><p>Attualmente disponibile solo in OneDrive for Business. Inviare una notifica ai proprietari quando:</p>
- <p>Gli utenti invitano altri utenti esterni ai file condivisi</p>
- <p>Gli utenti esterni accettano gli inviti per accedere ai file</p>
- <p>Un collegamento per l'accesso anonimo viene creato o modificato</p></td>
</tr>
</tbody>
</table>

Ulteriori informazioni:

-   [Gestire la condivisione esterna per l'ambiente di SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [Condividere siti o documenti con utenti esterni alla propria organizzazione](https://support.office.com/it-IT/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a>Criteri di accesso al dispositivo a livello di sito

SharePoint Online e OneDrive for Business consentono di configurare i criteri di accesso dei dispositivi a livello di sito. Ciò consente di configurare una maggiore protezione per i siti con dati riservati.

Se si configurano criteri di accesso ai dispositivi a livello di sito, assicurarsi di coordinarli con i criteri a livello di tenant e con i criteri di accesso configurati in Azure Active Directory, Intune e Intune App Management

I criteri di accesso ai dispositivi per SharePoint e OneDrive for Business richiedono criteri di supporto in Azure Active Directory e Microsoft Intune a seconda dello scenario che si sta implementando. Nella tabella seguente vengono riassunti gli obiettivi raggiungibili con i criteri di accesso ai dispositivi e vengono indicati quali prodotti richiedono criteri di supporto.

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Consentire l'accesso solo da indirizzi IP specifici</th>
<th align="left">Impedire agli utenti di scaricare file su dispositivi non aggiunti al dominio.</th>
<th align="left">Bloccare l'accesso nei dispositivi non aggiunti al dominio</th>
<th align="left">Impedire agli utenti di scaricare file nei dispositivi non conformi</th>
<th align="left">Bloccare l'accesso nei dispositivi non conformi</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Interfaccia di amministrazione di SharePoint</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
</tr>
<tr class="even">
<td align="left">Azure Active Directory</td>
<td align="left"></td>
<td align="left">Sì</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
</tr>
<tr class="odd">
<td align="left">Microsoft Intune</td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left">Sì</td>
<td align="left">Sì</td>
</tr>
</tbody>
</table>

Altre informazioni: [Interfaccia di amministrazione di SharePoint Online: controllare l'accesso da dispositivi non gestiti](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).

## <a name="service-access-protection-for-identities-and-devices"></a>Protezione dell'accesso al servizio per identità e dispositivi

Microsoft consiglia di configurare la protezione per identità e dispositivi che accedono al servizio. La protezione dell'accesso ai servizi di Microsoft 365 può anche essere usata per proteggere l'accesso ad altri servizi SaaS, PaaS e anche app in altri provider cloud.

La protezione dell'accesso per identità e dispositivi offre un livello di protezione di base per garantire che le identità non siano compromesse, i dispositivi siano sicuri e i dati dell'organizzazione aperti sui dispositivi siano isolati e protetti.

Per suggerimenti iniziali e indicazioni sulla configurazione, vedere [Guida alla sicurezza Microsoft per campagne politiche, organizzazioni no profit e altre organizzazioni Agile](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).

Per ambienti con identità ibride con AD FS, vedere [Configurazioni e criteri di sicurezza consigliati](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).

La seguente illustrazione descrive il modo in cui si relazionano i servizi cloud (SaaS, PaaS), i tipi di account (account del dominio tenant vs account B2B) e le funzionalità di accesso al servizio. È importante notare quali funzionalità possono essere usate con gli account B2B.

![Servizi cloud, tipi di account e funzionalità di accesso](../media/Apply-protection-to-personal-data-in-Office-365-image4.png)

Ai fini dell'accessibilità, il resto di questa sezione descrive l'illustrazione seguente.

### <a name="cloud-services"></a>Servizi cloud

Azure Active Directory fornisce l'accesso per le identità a qualsiasi servizio cloud, tra cui provider di terze parti non Microsoft come Amazon Web Services. L'illustrazione mostra Microsoft 365, "altre app SaaS" e "app PaaS". Le frecce puntano da Azure Active Directory a ognuno di questi servizi, mostrando che Azure Active Directory può essere usato per l'autenticazione di tutti questi tipi di app.

### <a name="types-of-accounts"></a>Tipi di account

Gli account del dominio tenant sono account aggiunti al tenant e gestiti direttamente. Gli account B2B sono account per utenti al di fuori dell'organizzazione invitati a collaborare. Possono essere altri account Microsoft 365, account di altre organizzazioni o account consumer (come Gmail). L'illustrazione mostra entrambi i tipi di account in Azure Active Directory.

### <a name="capabilities"></a>Funzionalità

Le funzionalità nella tabella seguente proteggono identità e dispositivi. La tabella indica quali funzionalità possono essere usate con gli account B2B, come l'illustrazione.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Funzionalità</strong></th>
<th align="left"><strong>Funziona con gli account del dominio tenant</strong></th>
<th align="left"><strong>Funziona con gli account B2B Azure (senza ulteriori licenze)</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Autenticazione a più fattori e accesso condizionale</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
</tr>
<tr class="even">
<td align="left">Azure AD Identity Protection</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
</tr>
<tr class="odd">
<td align="left">Azure AD Privileged Identity Management</td>
<td align="left">Sì</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Gestione di applicazioni mobili (MAM)</td>
<td align="left">Sì</td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left">Gestione e registrazione del dispositivo</td>
<td align="left">Sì</td>
<td align="left">Solo un'organizzazione può gestire un dispositivo</td>
</tr>
<tr class="even">
<td align="left">Funzionalità di sicurezza di Windows 10 (l'accesso condizionale basato sulla conformità dei dispositivi richiede la gestione dei dispositivi)</td>
<td align="left">Sì</td>
<td align="left">Sì</td>
</tr>
</tbody>
</table>

È possibile aggiungere licenze ad account B2B per fornire agli utenti funzionalità aggiuntive, se necessario, per proteggere l'accesso ai dati personali nel proprio ambiente.
