---
title: Panoramica del Centro sicurezza Microsoft 365
description: Vantaggi del Centro sicurezza Microsoft 365, che combina Microsoft Defender per Office 365 (MDO) e Microsoft Defender for Endpoint (MDE), con Microsoft Defender for Identity (MDI) e Microsoft Cloud App Security (MCAS). In questo articolo vengono descritti i progressi del Centro sicurezza Microsoft 365 per gli amministratori.
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, segnalare, identità, dati, dispositivi, app
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
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
ms.openlocfilehash: 43e341111ad1cb9b64ac257903d0e79bf24df5bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903887"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Panoramica del Centro sicurezza Microsoft 365 unificato

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Si applica a:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender per Office 365](../office-365-security/office-365-atp.md)

> Vuoi provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) eseguire il progetto pilota in [produzione.](./mtp-pilot.md?ocid=cx-evalpilot)

Il Centro sicurezza **Microsoft 365** migliorato ( ) combina protezione, rilevamento, indagine e risposta alla posta elettronica, alla collaborazione, all'identità e alle minacce dei [https://security.microsoft.com](https://security.microsoft.com) dispositivi, in un portale centrale.    

Il Centro sicurezza Microsoft 365 riunisce le funzionalità dei portali di sicurezza Microsoft esistenti, come Microsoft Defender Security Center e il Centro sicurezza & e conformità di Office 365. Il centro sicurezza enfatizza l'accesso rapido alle informazioni, ai layout più semplici e alla raccolta delle informazioni correlate per un utilizzo più semplice. Questo centro include:

- **[Microsoft Defender per Office 365](../office-365-security/office-365-atp.md)** Microsoft Defender per Office 365 aiuta le organizzazioni a proteggere la propria azienda con un set di funzionalità di prevenzione, rilevamento, indagine e ricerca per proteggere la posta elettronica e le risorse di Office 365.
- **[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** offre protezione preventiva, rilevamento post-violazione, analisi automatizzata e risposta per i dispositivi nell'organizzazione.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** fa parte della soluzione XDR *(Extended Detection and Response)* di Microsoft che sfrutta il portfolio di sicurezza di Microsoft 365 per analizzare automaticamente i dati sulle minacce nei domini e creare un'immagine di un attacco in un singolo dashboard.

Se sono necessarie informazioni sulle modifiche dal Centro sicurezza & e conformità di Office 365 o da Microsoft Defender Security Center, vedere:

- [Defender per Office 365 nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mdo.md)
- [Defender per endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Cosa aspettarsi

Tutti i contenuti di sicurezza utilizzati nel Centro sicurezza e conformità di Office 365 (protection.office.com) e nel Centro sicurezza Microsoft Defender (securitycenter.microsoft.com) sono ora disponibili nel Centro sicurezza *Microsoft 365.*

Il Centro sicurezza Microsoft 365 aiuta i team di sicurezza ad analizzare e rispondere agli attacchi, inondando i segnali provenienti da carichi di lavoro diversi in un'unica esperienza unificata:

- Eventi imprevisti & avvisi
- Hunting
- Centro notifiche
- Analisi delle minacce

Il Centro sicurezza Microsoft 365 sottolinea *l'unità,* la chiarezza e gli obiettivi comuni in quanto unisce Microsoft Defender per Office 365 e Microsoft Defender for Endpoint. L'unione si basa sulle priorità elencate di seguito e viene effettuata senza sacrificare le funzionalità che ogni suite di sicurezza ha portato alla combinazione:

- blocchi predefiniti comuni
- terminologia comune
- entità comuni
- parità delle funzionalità con altri carichi di lavoro

## <a name="unified-investigations"></a>Indagini unificate

La struttura dei centri di sicurezza crea un singolo riquadro per l'analisi di eventuali incidenti in un'organizzazione di Microsoft 365. Un esempio principale è il **nodo Eventi** imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Pagina Eventi imprevisti in MDO.":::

Ad esempio, facendo doppio clic sul  nome di un evento imprevisto con gravità elevata viene visualizzata una pagina che dimostra il vantaggio dei centri convergenza.

![Incidente in più fasi che implica l'escalation dei privilegi su più endpoint, che mostra vedere 16 dispositivi coinvolti e 9 utenti coinvolti.](../../media/converged-incident-info-3.png)

> [!TIP]
> La scheda **Utenti** convergenti è un buon punto per iniziare le richieste di informazioni. Questa singola pagina mostra informazioni per gli utenti provenienti da carichi di lavoro convergenti (Microsoft Defender for Endpoint, Microsoft Defender for Identity e MCAS, se lo si utilizza) e una serie di origini, ad esempio Active Directory locale, Azure Active Directory, utenti sincronizzati, locali e di terze parti. Ulteriori informazioni sulla [nuova esperienza degli utenti.](investigate-users.md)

Le informazioni sugli incidenti mostrano le specifiche dell'utente/identità e i dispositivi a rischio, oltre alle cassette postali interessate. Inoltre, si riferisce a tutte **le informazioni di indagine** e alle prove **raccolte.** In questo modo, gli amministratori e i team delle operazioni di sicurezza possono eseguire il pivot da un avviso ad alto rischio agli utenti e alle cassette postali interessati. Osservando le **schede Operazioni** non consentite nella parte superiore di questa pagina, sono disponibili altri pivot di sicurezza chiave da questa singola posizione.

> [!IMPORTANT]
> Nella parte superiore di qualsiasi pagina per un evento imprevisto specifico, verranno visualizzate le schede **Riepilogo,** **Avvisi,** **Dispositivi,** **Utenti,** Cassette **postali,** Indagini **e** Prova.

Selezionando **Indagini viene** aperta una pagina con un elemento grafico dell'analisi in corso ed è elencato uno stato (ad esempio in attesa di approvazione) per la correzione.  Prendere tempo per selezionare eventi imprevisti specifici nell'ambiente, eseguire il drill-down in queste schede e praticare la creazione di un profilo per diversi tipi di minacce. La familiarità trarrà vantaggio da eventuali indagini urgenti successive.

## <a name="improved-processes"></a>Processi migliorati

I controlli e il contenuto comuni vengono visualizzati nello stesso punto oppure sono suddivisi in un unico feed di dati, semplificando l'individuazione. Ad esempio, impostazioni unificate.

### <a name="unified-settings"></a>Impostazioni unificate

![ha fatto clic su "Ruoli" e ha aperto la pagina Impostazioni, che include impostazioni generali, autorizzazioni, API e regole. Aprire Autorizzazioni e quindi Ruoli. Mostra tutti i ruoli](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Autorizzazioni & ruoli

![Autorizzazioni & ruoli che mostra i ruoli endpoint & gruppi, ruoli e gruppi di dispositivi.](../../media/converged-roles-5.png)

 Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles. Per Defender for Endpoint, vedi [Assegnare l'accesso utente a Microsoft Defender Security Center.](/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access) Per Defender per Office 365, vedere Autorizzazioni nel Centro conformità Microsoft 365 e nel Centro sicurezza [Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Altre informazioni su come gestire [l'accesso a Microsoft 365 Defender](mtp-permissions.md)
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
- [Centro operativo](./mtp-action-center.md)
- [Ricerca di minacce su dispositivi, messaggi di posta elettronica, app e identità](./advanced-hunting-query-emails-devices.md)
- [Regole di rilevamento personalizzate](./custom-detection-rules.md)
- [Avvisi di collaborazione & posta elettronica](../../compliance/alert-policies.md#default-alert-policies)
- [Creare una simulazione di attacco di phishing](../office-365-security/attack-simulation-training.md) e creare un payload per la formazione dei [team](../office-365-security/attack-simulation-training-payloads.md)
 
### <a name="related-information"></a>Informazioni correlate
- [Centro sicurezza Microsoft 365](overview-security-center.md)
- [Microsoft Defender per Office 365 nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender for Endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)
- [Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365](microsoft-365-security-mde-redirection.md)