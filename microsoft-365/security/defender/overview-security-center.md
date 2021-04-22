---
title: Panoramica del Centro sicurezza Microsoft 365, che combina MDO, MDE, MDI e MCAS
description: Vantaggi del Centro sicurezza Microsoft 365, che combina Microsoft Defender per Office 365 (MDO) e Microsoft Defender for Endpoint (MDE), con Microsoft Defender for Identity (MDI) e Microsoft Cloud App Security (MCAS). In questo articolo vengono descritti i progressi del Centro sicurezza Microsoft 365 per gli amministratori.
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, segnalare, identità, dati, dispositivi, app
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: f9bb0690cf48c4cc694c0d563ba7d4203953358a
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943054"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Panoramica del Centro sicurezza Microsoft 365 unificato

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> Vuoi provare Microsoft 365 Defender? Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).

Il Centro sicurezza **Microsoft 365** migliorato ( ) combina protezione, rilevamento, indagine e risposta alla posta elettronica, alla collaborazione, all'identità e alle minacce dei [https://security.microsoft.com](https://security.microsoft.com) dispositivi, in un portale centrale.    

Il Centro sicurezza Microsoft 365 riunisce le funzionalità dei portali di sicurezza Microsoft esistenti, come Microsoft Defender Security Center e il Centro sicurezza & e conformità di Office 365. Il centro sicurezza enfatizza l'accesso rapido alle informazioni, ai layout più semplici e alla raccolta delle informazioni correlate per un utilizzo più semplice. Questo centro include:

- **[Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender per Office 365 aiuta le organizzazioni a proteggere la propria azienda con un set di funzionalità di prevenzione, rilevamento, indagine e ricerca per proteggere la posta elettronica e le risorse di Office 365.
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** offre protezione preventiva, rilevamento post-violazione, analisi automatizzata e risposta per i dispositivi nell'organizzazione.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** fa parte della soluzione XDR *(Extended Detection and Response)* di Microsoft che sfrutta il portfolio di sicurezza di Microsoft 365 per analizzare automaticamente i dati sulle minacce nei domini e creare un'immagine di un attacco in un singolo dashboard.

Se sono necessarie informazioni sulle modifiche dal Centro sicurezza & e conformità di Office 365 o da Microsoft Defender Security Center, vedere:

- [Defender per Office 365 nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mdo.md)
- [Defender per endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)

> [!NOTE]
> Il portale di sicurezza di Microsoft 365 usa e applica l'accesso basato sui ruoli esistenti e sposta ogni modello di sicurezza nel portale unificato. Ogni carico di lavoro convergente (ad esempio MDO o MDE) dispone di un proprio accesso basato sui ruoli. I ruoli già presenti nei prodotti verranno convergenti automaticamente nel portale di sicurezza di Microsoft 365. Tuttavia, i ruoli e le autorizzazioni per MCAS verranno comunque gestiti in MCAS.

## <a name="what-to-expect"></a>Cosa aspettarsi

Tutti i contenuti di sicurezza utilizzati nel Centro sicurezza e conformità di Office 365 (protection.office.com) e nel Centro sicurezza Microsoft Defender (securitycenter.microsoft.com) sono ora disponibili nel Centro sicurezza *Microsoft 365.*

Il Centro sicurezza Microsoft 365 consente ai team di sicurezza di analizzare e rispondere agli attacchi, inviare segnali da carichi di lavoro diversi in un set di esperienze unificate per:

- Eventi imprevisti & avvisi
- Ricerca
- Centro notifiche
- Analisi delle minacce

Il Centro sicurezza Microsoft 365 sottolinea *l'unità,* la chiarezza e gli obiettivi comuni in quanto unisce Microsoft Defender per Office 365 e Microsoft Defender for Endpoint. L'unione si basa sulle priorità elencate di seguito e viene effettuata senza sacrificare le funzionalità che ogni suite di sicurezza ha apportato alla combinazione di:

- Blocchi predefiniti comuni
- Terminologia comune
- Entità comuni
- Parità delle funzionalità con altri carichi di lavoro

> [!NOTE]
> Il Centro sicurezza Microsoft 365 unificato sarà accessibile senza la necessità per i clienti di eseguire operazioni di migrazione o acquistare una nuova licenza. Ad esempio, questo nuovo portale sarà accessibile agli amministratori con una sottoscrizione E3, così come per quelli con Microsoft Defender per Office 365 Piano 1 e Piano 2; Tuttavia, i clienti di Exchange Online Protection o MDO Piano 1 potranno visualizzare solo le funzionalità di sicurezza supportate dalla licenza di sottoscrizione. L'obiettivo del nuovo centro è centralizzare la sicurezza.

## <a name="unified-investigations"></a>Indagini unificate

I centri di sicurezza convergenza creano un'unica posizione per l'analisi degli incidenti di sicurezza in Microsoft 365. Un esempio principale è **Eventi imprevisti** in **Eventi & avvisi** sulla barra di avvio veloce del Centro sicurezza Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Pagina Eventi imprevisti nel Centro sicurezza Microsoft 365.":::

Se si seleziona un nome di evento imprevisto, verrà visualizzata una pagina in cui viene illustrato il valore dei Centri sicurezza convergenza.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Esempio della pagina Riepilogo per un evento imprevisto nel Centro sicurezza Microsoft 365":::

<!--
![Example of the Summary page for an incident in the Microsoft 365 security center](../../media/converged-incident-info-3.png)
--> 

Nella parte superiore della pagina di un evento imprevisto verranno visualizzate le schede **Riepilogo,** **Avvisi,** **Dispositivi,** **Utenti,** Cassette **postali,** Indagini **e** Prova. Selezionare queste schede per informazioni più dettagliate. Ad esempio,  nella scheda Utenti vengono visualizzate informazioni per gli utenti provenienti da carichi di lavoro convergenti (Microsoft Defender for Endpoint, Microsoft Defender for Identity e Microsoft Cloud App Security) e una serie di origini, ad esempio Servizi di dominio Active Directory locale, Azure Active Directory (Azure AD) e provider di identità di terze parti. Per ulteriori informazioni, vedere [analizzare gli utenti.](investigate-users.md)

Prendere il tempo necessario per esaminare gli eventi imprevisti nell'ambiente, eseguire il drill-down in queste schede e fare pratica per comprendere come accedere alle informazioni fornite per gli incidenti per diversi tipi di minacce.

Per ulteriori informazioni, vedere eventi imprevisti nel Centro sicurezza [Microsoft 365.](incidents-overview.md)

## <a name="improved-processes"></a>Processi migliorati

I controlli e il contenuto comuni vengono visualizzati nello stesso punto oppure sono suddivisi in un unico feed di dati, semplificando l'individuazione. Ad esempio, impostazioni unificate.

### <a name="unified-settings"></a>Impostazioni unificate

![ha fatto clic su "Ruoli" e ha aperto la pagina Impostazioni, che include impostazioni generali, autorizzazioni, API e regole. Aprire Autorizzazioni e quindi Ruoli. Mostra tutti i ruoli](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Autorizzazioni & ruoli

![Autorizzazioni & ruoli che mostra i ruoli endpoint & gruppi, ruoli e gruppi di dispositivi.](../../media/converged-roles-5.png)

 Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles. Per Defender for Endpoint, vedi [Assegnare l'accesso utente a Microsoft Defender Security Center.](/microsoft-365/security/defender-endpoint/assign-portal-access) Per Defender per Office 365, vedere Autorizzazioni nel Centro conformità Microsoft 365 e nel Centro sicurezza [Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Altre informazioni su come gestire [l'accesso a Microsoft 365 Defender](m365d-permissions.md)
- Ulteriori informazioni su come creare [ruoli personalizzati](custom-roles.md) nel Centro sicurezza Microsoft 365

> [!NOTE]
> Microsoft Defender for Endpoint nel centro sicurezza Microsoft 365 supporta la concessione dell'accesso ai provider di servizi di sicurezza gestiti [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) nello stesso modo in cui viene concesso l'accesso nel Centro sicurezza [Microsoft Defender.](./mssp-access.md)

### <a name="integrated-reports"></a>Report integrati

I report vengono inoltre unificati nel Centro sicurezza Microsoft 365. Gli amministratori possono iniziare con un report di sicurezza generale e creare report specifici sugli endpoint, la posta elettronica & collaborazione. I collegamenti qui vengono generati in modo dinamico in base alla configurazione del carico di lavoro.

### <a name="quickly-view-your-microsoft-365-environment"></a>Visualizzare rapidamente l'ambiente Microsoft 365

La **home** page mostra molte delle schede comuni necessarie ai team di sicurezza. La composizione di schede e dati dipende dal ruolo utente. Poiché il Centro sicurezza Microsoft 365 utilizza il controllo dell'accesso basato sui ruoli, diversi ruoli visualizzano schede più significative per i loro processi quotidiani.  

Queste informazioni dettagliate consentono di tenere il passo con le attività più recenti dell'organizzazione. Il Centro sicurezza Microsoft 365 riunisce segnali provenienti da origini diverse per presentare una visione olistica dell'ambiente Microsoft 365.

Le carte rientrano nelle categorie seguenti:

- **Identità:** monitorare le identità nell'organizzazione e tenere traccia di comportamenti sospetti o rischiosi. [Ulteriori informazioni sulla protezione delle identità.](/azure/active-directory/identity-protection/overview-identity-protection)
- **Dati:** consente di tenere traccia delle attività degli utenti che potrebbero portare alla divulgazione non autorizzata dei dati.
- **Dispositivi:** ottenere informazioni aggiornate su avvisi, attività di violazione e altre minacce nei dispositivi.
- **App:** informazioni dettagliate sull'uso delle app cloud nell'organizzazione. [Altre informazioni sulle app individuate da Cloud App Security.](/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Analisi delle minacce con una migliore copertura dei dati
Tenere traccia e rispondere alle minacce emergenti con la seguente esperienza integrata di Analisi delle minacce di Microsoft 365 Defender:

- Una migliore copertura dei dati tra Microsoft Defender for Endpoint e Microsoft Defender per Office 365, rendendo possibile la gestione combinata degli incidenti, l'indagine automatica, la correzione e la ricerca proattiva o reattiva delle minacce nel dominio. 
- Rilevamenti e mitigazioni correlati alla posta elettronica da Microsoft Defender per Office 365, oltre ai dati dell'endpoint già disponibili da Microsoft Defender per Endpoint.
- Una visualizzazione degli eventi imprevisti correlati alle minacce che aggregano gli avvisi in storie di attacco end-to-end in Microsoft Defender for Endpoint e Microsoft Defender per Office 365 per ridurre la coda di lavoro, oltre a semplificare e velocizzare l'indagine.
- Tentativi di attacco rilevati e bloccati dalle soluzioni Microsoft 365 Defender. Sono inoltre disponibili dati che è possibile utilizzare per guidare azioni preventive che attenuano il rischio di ulteriore esposizione e aumentano la resilienza. 
- Progettazione avanzata che mette sotto i riflettori le informazioni utili per identificare rapidamente i dati su cui concentrarsi, analizzare e sfruttare i report.

## <a name="a-centralized-learning-hub"></a>Hub di apprendimento centralizzato

Il Centro sicurezza Microsoft 365 include un hub di apprendimento che fornisce indicazioni ufficiali da risorse come il blog sulla sicurezza Microsoft, la community di sicurezza Microsoft su YouTube e la documentazione ufficiale su docs.microsoft.com.

All'interno dell'hub di apprendimento, le indicazioni per la collaborazione di Email & (Microsoft Defender per Office 365 o MDO) sono affiancate a Endpoint (Microsoft Defender for Endpoint o MDE) e alle risorse di apprendimento di Microsoft 365 Defender.

L'hub di apprendimento si apre con percorsi di apprendimento organizzati attorno ad argomenti come "Come analizzare l'uso di Microsoft 365 Defender?" e "Procedure consigliate per Microsoft Defender per Office 365". Questa sezione è attualmente curata dal gruppo di prodotti di sicurezza all'interno di Microsoft. Ogni percorso di apprendimento riflette il tempo proiettato necessario per ottenere i concetti. Ad esempio, "La procedura da eseguire quando un account utente di Microsoft Defender per Office 365 viene compromesso" è proiettato in 8 minuti ed è utile per imparare in tempo reale.

Dopo aver fatto clic sul contenuto, può essere utile aggiungere un segnalibro al sito e organizzare i segnalibri in una cartella "Sicurezza" o "Critica". Per visualizzare tutti i percorsi di apprendimento, fai clic sul collegamento Mostra tutto nel pannello principale.

> [!NOTE]
> Nella parte  superiore dell'hub di apprendimento del Centro sicurezza Microsoft 365 sono disponibili filtri utili che consentono di scegliere tra i prodotti (attualmente Microsoft 365 Defender, Microsoft Defender for Endpoint e Microsoft Defender per Office 365). Si noti che è elencato il numero di risorse di apprendimento per ogni sezione, che può aiutare gli studenti a tenere traccia del numero di risorse a disposizione per la formazione e l'apprendimento.
>
> Oltre al filtro prodotto, sono elencati gli argomenti correnti, i tipi di risorse (dai video ai webinar), i livelli di familiarità o di esperienza con le aree di sicurezza, i ruoli di sicurezza e le funzionalità del prodotto.

> [!TIP]
> Esistono molte altre opportunità di apprendimento in [Microsoft Learn.](https://docs.microsoft.com/e/learn/) Troverai corsi di formazione sulla certificazione come [Corso MS-500T02-A: Implementazione di Microsoft 365 Threat Protection.](https://docs.microsoft.com/learn/certifications/courses/ms-500t02)

## <a name="send-us-your-feedback"></a>Inviaci il tuo feedback

Abbiamo bisogno del tuo feedback. Stiamo sempre cercando di migliorare, quindi se c'è qualcosa che vuoi vedere, inviaci il tuo feedback su [Microsoft 365 Defender.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

Puoi anche lasciare commenti e suggerimenti da questo articolo. Nella sezione "Feedback" alla fine in "Invia e visualizza feedback per", le opzioni sono Questo *prodotto* o *Questa pagina.*

Usa il **pulsante Questo prodotto** per il feedback *del* prodotto:

1. Seleziona *Questo prodotto* nella parte inferiore dell'articolo.
    1. Fai clic con il pulsante destro del mouse sul pulsante e su "Apri in una nuova scheda" se vuoi continuare a leggere queste indicazioni stradali.
2. Verrà visualizzato il **forum uservoice**.
3. Sono disponibili 2 opzioni:
    1. Scorrere verso il basso fino alla casella di testo Come migliorare la conformità o proteggere meglio gli utenti *in Office 365?* e incollare nel Centro sicurezza *Microsoft 365.* Puoi cercare nei risultati un'idea come la tua e votarla o usare il pulsante **per Pubblicare una nuova idea.**
    1. Se si è certi che questo problema sia già stato segnalato e si desidera alzarne il profilo con un voto (o voti), utilizzare la casella Invia *feedback* sul lato destro di UserVoice. Cercare il *Centro sicurezza Microsoft 365,* **individuare il problema** e usare il pulsante di voto per alzarne lo stato.

Usa *questa pagina per* il feedback sull'articolo stesso. Grazie per il feedback. La tua voce ci aiuta a migliorare i prodotti.

### <a name="explore-what-the-security-center-has-to-offer"></a>Scopri cosa offre il Centro sicurezza

Continuare a esplorare le funzionalità e le funzionalità del Centro sicurezza Microsoft 365:

- [Gestire eventi imprevisti e avvisi](manage-incidents.md)
- [Tenere traccia e rispondere alle minacce emergenti con l'analisi delle minacce](threat-analytics.md)
- [Centro operativo](m365d-action-center.md)
- [Cercare minacce tra dispositivi, posta elettronica, app e identità](./advanced-hunting-query-emails-devices.md)
- [Regole di rilevamento personalizzate](./custom-detection-rules.md)
- [Avvisi posta elettronica e collaborazione](../../compliance/alert-policies.md#default-alert-policies)
- [Creare una simulazione di attacco di phishing](../office-365-security/attack-simulation-training.md) e creare un payload per la formazione dei [team](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Informazioni correlate
- [Centro sicurezza Microsoft 365](overview-security-center.md)
- [Defender per Office 365 nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender for Endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)
- [Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365](microsoft-365-security-mde-redirection.md)