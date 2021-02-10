---
title: Panoramica del Centro sicurezza Microsoft 365
description: Vantaggi del Centro sicurezza Microsoft 365, che combina Microsoft Defender per Office 365 (MDO) e Microsoft Defender for Endpoint (MDE), con Microsoft Defender for Identity (MDI) e Microsoft Cloud App Security (MCAS). Questo articolo descrive i progressi del Centro sicurezza Microsoft 365 per gli amministratori.
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, report, identità, dati, dispositivi, app
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
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167202"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Panoramica del Centro sicurezza Microsoft 365 unificato

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Si applica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender per Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Si vuole provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)

Il Centro sicurezza **Microsoft 365** migliorato ( ) combina protezione, rilevamento, indagine e risposta alle minacce di posta elettronica, collaborazione, identità e [https://security.microsoft.com](https://security.microsoft.com) dispositivi, in un portale centrale.    

Il Centro sicurezza Microsoft 365 riunisce le funzionalità dei portali di sicurezza Microsoft esistenti, come Microsoft Defender Security Center e il Centro sicurezza & e conformità di Office 365. Il Centro sicurezza sottolinea l'accesso rapido alle informazioni, ai layout più semplici e alla creazione di informazioni correlate per un utilizzo più semplice. Questo centro include:

- **[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender per Office 365 consente alle organizzazioni di proteggere la propria azienda con un set di funzionalità di prevenzione, rilevamento, indagine e ricerca per proteggere la posta elettronica e le risorse di Office 365.
- **[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** offre protezione preventiva, rilevamento post-violazione, analisi automatizzata e risposta per i dispositivi dell'organizzazione.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** fa parte della soluzione XDR *(Extended Detection and Response)* di Microsoft che sfrutta il portfolio di sicurezza di Microsoft 365 per analizzare automaticamente i dati sulle minacce in tutti i domini e creare un'immagine di un attacco in un singolo dashboard.

Se sono necessarie informazioni sulle modifiche del Centro sicurezza & e conformità di Office 365 o di Microsoft Defender Security Center, vedere:

- [Defender per Office 365 nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mdo.md)
- [Defender per Endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Cosa aspettarsi

Tutti i contenuti sulla sicurezza utilizzati nel Centro sicurezza e conformità di Office 365 (protection.office.com) e nel Centro sicurezza Microsoft Defender (securitycenter.microsoft.com) sono ora disponibili nel Centro sicurezza *Microsoft 365.*

Il Centro sicurezza Microsoft 365 consente ai team di sicurezza di analizzare e rispondere agli attacchi brining dei segnali provenienti da carichi di lavoro diversi in un'unica esperienza unificata:

- Eventi imprevisti & avvisi
- Ricerca
- Centro notifiche
- Analisi delle minacce

Il Centro sicurezza Microsoft 365 sottolinea *l'unità,* la chiarezza e gli obiettivi comuni in quanto unisce Microsoft Defender per Office 365 e Microsoft Defender for Endpoint. L'unione si basa sulle priorità elencate di seguito e viene effettuata senza sacrificare le funzionalità che ogni famiglia di prodotti di sicurezza ha portato alla combinazione:

- blocchi predefiniti comuni
- terminologia comune
- entità comuni
- parità di funzionalità con altri carichi di lavoro

## <a name="unified-investigations"></a>Indagini unificate

La snellizione dei centri di sicurezza crea un unico riquadro per l'analisi di eventuali incidenti in un'organizzazione di Microsoft 365. Un esempio principale è il **nodo Eventi** imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Pagina Eventi imprevisti in MDO.":::

Ad esempio, facendo doppio clic sul  nome di un evento imprevisto con gravità elevata viene visualizzata una pagina che dimostra il vantaggio dei centri convergenza.

![Incidente in più fasi che implica l'escalation dei privilegi su più endpoint, che mostra come vedere 16 dispositivi coinvolti e 9 utenti coinvolti.](../../media/converged-incident-info-3.png)

> [!TIP]
> La scheda **Utenti** convergenti è un buon punto per iniziare le richieste. Questa singola pagina consente di visualizzare informazioni per gli utenti provenienti da carichi di lavoro convergenti (Microsoft Defender per Endpoint, Microsoft Defender for Identity e MCAS, se lo si utilizza) e una serie di origini come Active Directory locale, Azure Active Directory, sincronizzato, locale e utenti di terze parti. Ulteriori informazioni sulla [nuova esperienza degli utenti.](investigate-users.md)

Le informazioni sull'incidente mostrano le specifiche dell'utente/identità e i dispositivi a rischio, oltre alle cassette postali interessate. Inoltre, correla tutte le **informazioni dell'indagine** e raccoglie **prove.** Ciò consente agli amministratori e ai team delle operazioni di sicurezza di eseguire il pivot da un avviso ad alto rischio agli utenti e alle cassette postali interessati. Osservando le schede **Operazioni** non consentite nella parte superiore di questa pagina, sono disponibili altri pivot di sicurezza chiave da questa singola posizione.

> [!IMPORTANT]
> Nella parte superiore di qualsiasi pagina per un evento imprevisto specifico verranno visualizzate le schede **Riepilogo,** **Avvisi,** **Dispositivi,** **Utenti,** Cassette **postali,** Indagini e **Prove.**

Se **si seleziona Analisi,** viene aperta una pagina con un grafico dell'analisi in corso e uno stato, ad esempio in attesa di approvazione, per la correzione. Prendere tempo per selezionare eventi imprevisti specifici nell'ambiente, eseguire il drill-down in queste schede e praticare la creazione di un profilo per diversi tipi di minacce. La familiarità trarrà vantaggio da eventuali indagini più urgenti.

## <a name="improved-processes"></a>Processi migliorati

I controlli e il contenuto comuni vengono visualizzati nella stessa posizione oppure vengono compressi in un unico feed di dati, facilitando l'individuazione. Ad esempio, impostazioni unificate.

### <a name="unified-settings"></a>Impostazioni unificate

![Ha fatto clic su "Ruoli" e ha aperto la pagina Impostazioni, che include impostazioni generali, autorizzazioni, API e regole. Aprire Autorizzazioni e quindi Ruoli. Mostra tutti i ruoli](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Autorizzazioni & ruoli

![Autorizzazioni & ruoli che mostra i ruoli endpoint &, ruoli e gruppi di dispositivi.](../../media/converged-roles-5.png)

 L'accesso al Centro sicurezza Microsoft 365 è configurato con ruoli globali di Azure Active Directory o tramite ruoli personalizzati. Per Defender for Endpoint, vedi [Assegnare l'accesso utente a Microsoft Defender Security Center.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access) Per Defender per Office 365, vedere Autorizzazioni nel Centro conformità Microsoft 365 e nel Centro [sicurezza Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Altre informazioni su come gestire [l'accesso a Microsoft 365 Defender](mtp-permissions.md)
- Ulteriori informazioni su come creare [ruoli personalizzati](custom-roles.md) nel Centro sicurezza Microsoft 365

### <a name="integrated-reports"></a>Report integrati

I report sono anche unificati nel Centro sicurezza Microsoft 365. Gli amministratori possono iniziare con un report di sicurezza generale e creare report specifici sugli endpoint, la posta elettronica & collaborazione. I collegamenti qui riportati vengono generati dinamicamente in base alla configurazione del carico di lavoro.

### <a name="quickly-view-your-microsoft-365-environment"></a>Visualizzare rapidamente l'ambiente di Microsoft 365

La **home** page mostra molte delle schede comuni necessarie ai team di sicurezza. La composizione di schede e dati dipende dal ruolo dell'utente. Poiché il Centro sicurezza Microsoft 365 usa il controllo dell'accesso basato sui ruoli, ruoli diversi visualizzano schede più significative per il loro lavoro quotidiano.  

Queste informazioni a colpo d'occhio consentono di tenere il passo con le attività più recenti nell'organizzazione. Il Centro sicurezza Microsoft 365 riunisce segnali provenienti da origini diverse per presentare una visione olistica dell'ambiente Microsoft 365.

Le carte rientrano nelle seguenti categorie:

- **Identità:** monitorare le identità nell'organizzazione e tenere traccia di comportamenti sospetti o rischiosi. [Ulteriori informazioni sulla protezione delle identità.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **Dati:** consente di tenere traccia delle attività degli utenti che potrebbero portare alla divulgazione non autorizzata dei dati.
- **Dispositivi:** ottenere informazioni aggiornate su avvisi, attività di violazione e altre minacce nei dispositivi.
- **App:** informazioni dettagliate sull'uso delle app cloud nell'organizzazione. [Altre informazioni sulle app individuate di Cloud App Security.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Analisi delle minacce con una migliore copertura dei dati
Tenere traccia e rispondere alle minacce emergenti con la seguente esperienza integrata di Analisi delle minacce di Microsoft 365 Defender:

- Una migliore copertura dei dati tra Microsoft Defender per Endpoint e Microsoft Defender per Office 365, rendendo possibile la gestione combinata degli incidenti, l'indagine automatica, la correzione e la ricerca proattiva o reattiva delle minacce nel dominio. 
- Rilevamenti e mitigazioni correlati alla posta elettronica da Microsoft Defender per Office 365, oltre ai dati dell'endpoint già disponibili da Microsoft Defender per Endpoint.
- Una visualizzazione degli eventi imprevisti correlati alle minacce che aggregano gli avvisi in storie di attacco end-to-end in Microsoft Defender for Endpoint e Microsoft Defender per Office 365 per ridurre la coda di lavoro, oltre a semplificare e velocizzare l'indagine.
- Tentativi di attacco rilevati e bloccati dalle soluzioni di Microsoft 365 Defender. Sono inoltre disponibili dati che è possibile utilizzare per eseguire azioni preventive che attenuano il rischio di ulteriore esposizione e aumentano la resilienza. 
- Progettazione avanzata che mette sotto i riflettori informazioni utili per identificare rapidamente i dati su cui concentrarsi, analizzare e sfruttare i report.

## <a name="a-centralized-learning-hub"></a>Hub di apprendimento centralizzato

Il Centro sicurezza Microsoft 365 include un hub di apprendimento che fornisce indicazioni ufficiali da risorse come il blog sulla sicurezza Microsoft, la community sulla sicurezza Microsoft su YouTube e la documentazione ufficiale su docs.microsoft.com.

All'interno dell'hub di apprendimento, le indicazioni per La collaborazione tramite e-mail & (Microsoft Defender per Office 365 o MDO) sono affiancate a Endpoint (Microsoft Defender per Endpoint o MDE) e alle risorse di apprendimento di Microsoft 365 Defender.

L'hub di apprendimento si apre con percorsi di apprendimento organizzati su argomenti come "Come analizzare l'uso di Microsoft 365 Defender?" e "Procedure consigliate di Microsoft Defender per Office 365". Questa sezione è attualmente curata dal gruppo di prodotti di sicurezza all'interno di Microsoft. Ogni percorso di apprendimento riflette il tempo proiettato necessario per ottenere i concetti. Ad esempio, "La procedura da eseguire quando un account utente di Microsoft Defender per Office 365 viene compromesso" potrebbe richiedere 8 minuti ed è un valido apprendimento in tempo reale.

Dopo aver fatto clic sul contenuto, può essere utile aggiungere un segnalibro a questo sito e organizzare i segnalibri in una cartella "Sicurezza" o "Critica". Per visualizzare tutti i percorsi di apprendimento, fai clic sul collegamento Mostra tutto nel pannello principale.

> [!NOTE]
> Nella parte  superiore dell'hub di apprendimento del Centro sicurezza Microsoft 365 sono disponibili filtri utili che consentono di scegliere tra i prodotti (attualmente Microsoft 365 Defender, Microsoft Defender for Endpoint e Microsoft Defender per Office 365). Si noti che è elencato il numero di risorse di apprendimento per ogni sezione, che può aiutare gli studenti a tenere traccia del numero di risorse disponibili per la formazione e l'apprendimento.
>
> Oltre al filtro prodotto, sono elencati argomenti correnti, tipi di risorse (dai video ai webinar), livelli di familiarità o esperienza con le aree di sicurezza, i ruoli di sicurezza e le funzionalità del prodotto.

## <a name="send-us-your-feedback"></a>Inviaci il tuo feedback

Abbiamo bisogno del tuo feedback. We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

Puoi anche lasciare feedback da questo articolo. Nella sezione "Feedback" alla fine in "Invia e visualizza il feedback per", le opzioni sono Questo *prodotto* o *Questa pagina.*

Usa il **pulsante Questo prodotto** per il feedback *del* prodotto:

1. Seleziona *questo prodotto* nella parte inferiore dell'articolo.
    1. Fai clic con il pulsante destro del mouse sul pulsante e su "Apri in una nuova scheda" se vuoi continuare a leggere queste indicazioni.
2. Verrà visualizzato il **forum uservoice.**
3. Sono disponibili 2 opzioni:
    1. Scorrere verso il basso fino alla casella di testo Come è possibile migliorare la conformità o proteggere meglio gli utenti *in Office 365?* e incollare nel Centro sicurezza *Microsoft 365.* Puoi cercare nei risultati un'idea come la tua e votarla in modo up-vote oppure usare il pulsante **Per pubblicare una nuova idea.**
    1. Se si è certi che il problema sia già stato segnalato e si  desidera aumentarne il profilo con un voto (o voti), usare la casella Commenti e suggerimenti sul lato destro di UserVoice. Cercare il Centro sicurezza *Microsoft 365,* **individuare il problema e usare il pulsante di voto** per aumentarne lo stato.

Usa *questa pagina per* commenti e suggerimenti sull'articolo stesso. Grazie per il feedback. La tua voce ci aiuta a migliorare i prodotti.

### <a name="explore-what-the-security-center-has-to-offer"></a>Scopri cosa offre il Centro sicurezza

Continuare a esplorare le funzionalità e le funzionalità nel Centro sicurezza Microsoft 365:

- [Gestire eventi imprevisti e avvisi](manage-incidents.md)
- [Tenere traccia e rispondere alle minacce emergenti con l'analisi delle minacce](threat-analytics.md)
- [Centro operativo](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Cercare minacce su dispositivi, messaggi di posta elettronica, app e identità](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [Regole di rilevamento personalizzate](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [Avvisi di collaborazione & messaggi di posta elettronica](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [Creare una simulazione di attacco di phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) e creare un payload per la formazione dei [team](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Informazioni correlate
- [Centro sicurezza Microsoft 365](overview-security-center.md)
- [Microsoft Defender per Office 365 nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)
- [Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365](microsoft-365-security-mde-redirection.md)
