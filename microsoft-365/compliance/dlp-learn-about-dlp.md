---
title: Informazioni sulla prevenzione della perdita di dati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Informazioni su come proteggere le informazioni riservate usando Microsoft 365 criteri e strumenti di prevenzione della perdita dei dati ed eseguire un'analisi del ciclo di vita DLP.
ms.openlocfilehash: 291a9ab09d14e24d58604644d77381d7f41214d6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226852"
---
# <a name="learn-about-data-loss-prevention"></a>Informazioni sulla prevenzione della perdita di dati

Le organizzazioni dispongono di informazioni riservate sotto il loro controllo, ad esempio dati finanziari, dati proprietari, numeri di carta di credito, registri sanitari o numeri di previdenza sociale. Per proteggere questi dati sensibili e ridurre i rischi, è necessario un modo per impedire agli utenti di condividerli in modo inappropriato con persone che non dovrebbero averne. Questa procedura è denominata prevenzione della perdita dei dati (DLP).

In Microsoft 365, è possibile implementare la prevenzione della perdita dei dati definendo e applicando i criteri DLP. Con un criterio DLP, è possibile identificare, monitorare e proteggere automaticamente gli elementi sensibili tra:

- Microsoft 365 servizi quali Teams, Exchange, SharePoint e OneDrive
- Office applicazioni quali Word, Excel e PowerPoint
- Windows 10 endpoint
- app cloud non Microsoft
- condivisioni file locali e SharePoint.

Microsoft 365 rileva gli elementi sensibili utilizzando un'analisi approfondita del contenuto, non semplicemente tramite una semplice analisi del testo. Il contenuto viene analizzato per le corrispondenze dei dati principali alle parole chiave, tramite la valutazione delle espressioni regolari, la convalida delle funzioni interne e le corrispondenze dei dati secondari che si trovano in prossimità della corrispondenza dei dati primari. Oltre a ciò, DLP usa anche algoritmi di machine learning e altri metodi per rilevare il contenuto che corrisponde ai criteri DLP.

## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>DLP fa parte dell'offerta di conformità Microsoft 365 più ampia

Microsoft 365 DLP è solo uno degli Microsoft 365 di conformità che verranno utilizzati per proteggere gli elementi sensibili ovunque vivano o in viaggio. È consigliabile comprendere gli altri strumenti del set di Microsoft 365 conformità, il modo in cui si interrelano e funzionano meglio insieme.  Per ulteriori [informazioni sul processo di](protect-information.md) protezione delle informazioni, vedere Microsoft 365 strumenti di conformità.

## <a name="protective-actions-of-dlp-policies"></a>Azioni di protezione dei criteri DLP

Microsoft 365 I criteri DLP consentono di monitorare le attività che gli utenti esereranno su elementi sensibili in pausa, elementi sensibili in transito o elementi sensibili in uso ed eseguire azioni di protezione. Ad esempio, quando un utente tenta di eseguire un'azione non consentita, ad esempio copiando un elemento sensibile in una posizione non approvata o condividendo informazioni mediche in un messaggio di posta elettronica o in altre condizioni previste in un criterio, DLP può:

- mostrare un suggerimento per i criteri popup all'utente che li avvisa che potrebbe tentare di condividere un elemento sensibile in modo inappropriato
- bloccare la condivisione e, tramite un suggerimento per i criteri, consentire all'utente di ignorare il blocco e acquisire la giustificazione degli utenti
- bloccare la condivisione senza l'opzione di sostituzione
- per i dati in pausa, gli elementi sensibili possono essere bloccati e spostati in un percorso di quarantena sicuro
- per Teams chat, le informazioni riservate non verranno visualizzate

Tutte le attività monitorate DLP vengono registrate nel Microsoft 365 di controllo [per](search-the-audit-log-in-security-and-compliance.md) impostazione predefinita e instradate a [Esplora attività.](data-classification-activity-explorer.md) Quando un utente esegue un'azione che soddisfa i criteri di un criterio DLP e sono stati configurati avvisi, DLP fornisce avvisi nel dashboard di gestione degli avvisi [DLP.](dlp-configure-view-alerts-policies.md)

## <a name="dlp-lifecycle"></a>Ciclo di vita DLP

Un'implementazione DLP in genere segue queste fasi principali.

- [Piano per la prevenzione della perdita dei dati](#plan-for-dlp)
- [Preparare la prevenzione della perdita dei dati](#prepare-for-dlp)
- [Distribuire i criteri nell'ambiente di produzione](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>Piano per la prevenzione della perdita dei dati

Microsoft 365 Il monitoraggio e la protezione DLP sono nativi delle applicazioni che gli utenti usano ogni giorno. Ciò consente di proteggere gli elementi sensibili delle organizzazioni dalle attività rischiose anche se gli utenti non sono abituati a pensare e pratiche di prevenzione della perdita di dati. Se l'organizzazione e gli utenti sono nuovi delle procedure di prevenzione della perdita dei dati, l'adozione della prevenzione della perdita dei dati potrebbe richiedere una modifica ai processi aziendali e vi sarà un cambiamento di cultura per gli utenti. Tuttavia, con una pianificazione, un test e un'ottimizzazione adeguati, i criteri DLP proteggono gli elementi sensibili riducendo al minimo eventuali interruzioni del processo aziendale.

**Pianificazione della tecnologia per DLP**

Tenere presente che DLP come tecnologia è in grado di monitorare e proteggere i dati in pausa, i dati in uso e i dati in movimento tra servizi Microsoft 365, dispositivi Windows 10, condivisioni file locali e SharePoint locale. Esistono implicazioni di pianificazione per le diverse posizioni, il tipo di dati che si desidera monitorare e proteggere e le azioni da eseguire quando si verifica una corrispondenza dei criteri.

**Pianificazione dei processi aziendali per DLP**

I criteri DLP possono bloccare le attività proibite, ad esempio la condivisione inappropriata di informazioni riservate tramite posta elettronica. Durante la pianificazione dei criteri DLP, è necessario identificare i processi aziendali che toccano gli elementi sensibili. I proprietari dei processi aziendali possono aiutare a identificare i comportamenti degli utenti appropriati che devono essere consentiti e comportamenti utente inappropriati da proteggere. È consigliabile pianificare i criteri e distribuirli [](data-classification-activity-explorer.md) in modalità test e valutarne l'impatto tramite Esplora attività prima di applicarli in modalità più restrittive.

**Pianificazione della cultura organizzativa per DLP**

Un'implementazione DLP corretta dipende tanto dal fatto che gli utenti vengono addestrati e acclimati alle procedure di prevenzione della perdita dei dati, quanto da criteri ben pianificati e ottimizzati. Poiché gli utenti sono molto coinvolti, assicurarsi di pianificare la formazione anche per loro. Puoi usare strategicamente i suggerimenti per i criteri per aumentare la consapevolezza con gli utenti prima di modificare l'applicazione dei criteri dalla modalità di test a quella più restrittiva.

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>Preparare la prevenzione della perdita dei dati

È possibile applicare i criteri DLP ai dati in fase di riposo, ai dati in uso e ai dati in movimento nelle posizioni, ad esempio:

- Exchange Online posta elettronica
- Siti di SharePoint Online
- Account di OneDrive
- Messaggi di chat e canali di Teams
- Microsoft Cloud App Security
- Dispositivi Windows 10
- Archivi locali

Ognuno di essi dispone di prerequisiti diversi. Gli elementi sensibili in alcune posizioni, come Exchange online, possono essere portati sotto l'ombrello DLP semplicemente configurando un criterio che si applica a loro. Altri, ad esempio archivi di file locali, richiedono una distribuzione dello scanner Azure Information Protection (AIP). Dovrai preparare l'ambiente, codificare i criteri e testarli accuratamente prima di attivare eventuali azioni di blocco.

### <a name="deploy-your-policies-in-production"></a>Distribuire i criteri nell'ambiente di produzione

#### <a name="design-your-policies"></a>Progettare i criteri

Per iniziare, definire gli obiettivi di controllo e come si applicano a ogni rispettivo carico di lavoro. Bozza di un criterio che rappresenta gli obiettivi. È possibile iniziare con un carico di lavoro alla volta o tra tutti i carichi di lavoro: non c'è ancora alcun impatto.

#### <a name="implement-policy-in-test-mode"></a>Implementare criteri in modalità test

Valutare l'impatto dei controlli implementandoli con un criterio DLP in modalità test. È possibile applicare il criterio a tutti i carichi di lavoro in modalità test, in modo da ottenere l'intera gamma di risultati, ma è possibile iniziare con un carico di lavoro, se necessario.

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>Monitorare i risultati e ottimizzare i criteri

Durante la modalità di test, monitorare i risultati del criterio e ottimizzarlo in modo che soddisfi gli obiettivi di controllo, garantendo al contempo di non influire negativamente o inavvertitamente sui flussi di lavoro e sulla produttività degli utenti validi. Ecco alcuni esempi di elementi da ottimizzare:

- regolazione delle posizioni e delle persone/luoghi all'interno o all'esterno dell'ambito
- ottimizzare le condizioni e le eccezioni utilizzate per determinare se un elemento e l'operazione eseguita corrispondono al criterio
- definizione/e delle informazioni riservate
- le azioni
- livello di restrizioni
- aggiungere nuovi controlli
- aggiungere nuovi utenti
- aggiungere nuove app con restrizioni
- aggiungere nuovi siti con restrizioni

#### <a name="enable-the-control-and-tune-your-policies"></a>Abilitare il controllo e ottimizzare i criteri

Una volta che il criterio soddisfa tutti gli obiettivi, attivalo. Continuare a monitorare i risultati dell'applicazione dei criteri e ottimizzare in base alle esigenze. In generale, i criteri hanno effetto circa un'ora dopo essere stati attivati.

<!--See, LINK TO topic for SLAs for location specific  details-->

## <a name="dlp-policy-configuration-overview"></a>Panoramica della configurazione dei criteri DLP

È possibile creare e configurare i criteri DLP in modo flessibile. Puoi iniziare da un modello predefinito e creare un criterio in pochi clic oppure puoi progettarne uno personalizzato da zero. Indipendentemente dalla scelta, tutti i criteri DLP richiedono le stesse informazioni.

1. **Scegliere ciò che si desidera monitorare:** Microsoft 365 con molti modelli di criteri predefiniti che consentono di iniziare o è possibile creare criteri personalizzati.
    - Un modello di criteri predefinito: dati finanziari, dati medici e sanitari, dati sulla privacy tutti per vari paesi e aree geografiche.
    - Criteri personalizzati che utilizzano i tipi di informazioni riservate, le etichette di conservazione e le etichette di riservatezza disponibili.
2. **Scegliere dove si desidera monitorare:** si selezionano una o più posizioni che si desidera che DLP monitori per le informazioni riservate. È possibile monitorare:

posizione | includo/escluso da|
|---------|---------|
|Posta elettronica di Exchange| gruppi di distribuzione|
|Siti di SharePoint |siti |
|Account di OneDrive |account o gruppi di distribuzione |
|Messaggi di chat e canali di Teams |account |
|Dispositivi Windows 10 |utente o gruppo |
|Microsoft Cloud App Security |istanza |
|Archivi locali| percorso del file repository|

3. **Scegliere le condizioni che devono essere soddisfatte** per applicare un criterio a un elemento. È possibile accettare condizioni preconfigurate o definire condizioni personalizzate. Ecco alcuni esempi:

- contiene un tipo specificato di informazioni riservate utilizzate in un determinato contesto. Ad esempio, 95 numeri di previdenza sociale da inviare tramite posta elettronica al destinatario all'esterno dell'organizzazione.
- l'elemento ha un'etichetta di riservatezza specificata
- l'elemento con informazioni riservate viene condiviso internamente o esternamente

4. **Scegliere l'azione da eseguire quando vengono soddisfatte** le condizioni dei criteri: le azioni dipendono dalla posizione in cui si sta verificando l'attività.  Ecco alcuni esempi:

- SharePoint/Exchange/OneDrive: bloccare gli utenti esterni all'organizzazione che accedono al contenuto. Mostra all'utente un suggerimento e invia loro una notifica tramite posta elettronica che sta prendendo un'azione non consentita dal criterio DLP.
- Teams Chat e canale: impedire la condivisione di informazioni riservate nella chat o nel canale
- Windows 10 Dispositivi: controlla o limita la copia di un elemento sensibile in un dispositivo USB rimovibile
- Office App: mostra un popup che informa l'utente che sta impegnandosi in un comportamento rischioso e blocca o blocca ma consente l'override.
- Condivisioni file locali: spostare il file da cui è archiviato in una cartella di quarantena

> [!NOTE]
> Le condizioni e le azioni da eseguire sono definite in un oggetto denominato Rule.

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

Dopo aver creato un criterio DLP nel Centro conformità, questo viene archiviato in un archivio dei criteri centrale e quindi sincronizzato con le varie origini di contenuto, tra cui:

- Exchange Online e da qui con Outlook sul Web e Outlook.
- Siti di OneDrive for Business.
- Siti di SharePoint Online.
- Applicazioni desktop di Office (Excel, PowerPoint e Word).
- Messaggi di chat e canali di Microsoft Teams.

In seguito alla sincronizzazione del criterio con il percorso corretto, viene avviata la valutazione del contenuto e l'applicazione delle azioni.

## <a name="viewing-policy-application-results"></a>Visualizzazione dei risultati dell'applicazione dei criteri

DLP segnala una grande quantità di informazioni in Microsoft 365 monitoraggio, corrispondenze e azioni dei criteri e attività degli utenti. Dovrai usare e agire su queste informazioni per ottimizzare i criteri e le azioni di triage eseguite su elementi sensibili. La telemetria viene prima [Microsoft 365](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) log di controllo del Centro conformità, viene elaborata e si trasforma in diversi strumenti di creazione di report. Ogni strumento di creazione di report ha uno scopo diverso.

### <a name="dlp-alerts-dashboard"></a>Dashboard avvisi DLP

Quando DLP esegue un'azione su un elemento sensibile, è possibile ricevere una notifica di tale azione tramite un avviso configurabile. Anziché disporre di questi avvisi in pila in una cassetta postale per il set di dati, il Centro conformità li rende disponibili nel dashboard di gestione degli avvisi [DLP.](dlp-configure-view-alerts-policies.md) Utilizzare il dashboard degli avvisi DLP per configurare gli avvisi, esaminarli, valutarli e tenere traccia della risoluzione degli avvisi DLP. Ecco un esempio di avvisi generati dalle corrispondenze dei criteri e dalle attività Windows 10 dispositivi.

> [!div class="mx-imgBorder"]
> ![Info sugli avvisi](../media/Alert-info-1.png)

È anche possibile visualizzare i dettagli dell'evento associato con metadati completi nello stesso dashboard

> [!div class="mx-imgBorder"]
> ![info sull'evento](../media/Event-info-1.png)

### <a name="reports"></a>Report

I [report DLP mostrano](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) tendenze generali nel tempo e forniscono informazioni specifiche su:

- **Criteri DLP Corrisponde nel** tempo e filtra per intervallo di date, posizione, criterio o azione
- **Le corrispondenze degli eventi** imprevisti DLP mostrano anche le corrispondenze nel tempo, ma i pivot sugli elementi anziché sulle regole dei criteri.
- **I falsi positivi e le sostituzioni DLP** mostrano il conteggio dei falsi positivi e, se configurati, le sostituzioni dell'utente insieme alla giustificazione dell'utente.

### <a name="dlp-activity-explorer"></a>Esplora attività DLP

Nella scheda Esplora attività della  pagina DLP il filtro Attività è stato preimpostato *su DLPRuleMatch.* Usa questo strumento per esaminare le attività relative al contenuto che contiene informazioni riservate o a cui sono state applicate etichette, ad esempio quali etichette sono state modificate, i file sono stati modificati e sono state applicate corrispondenze a una regola.

![Screenshot of the DLPRuleMatch scoped activity explorer](../media/dlp-activity-explorer.png)

Per altre informazioni, vedi [Introduzione a Esplora attività](data-classification-activity-explorer.md)

Per ulteriori informazioni su Microsoft 365 DLP, vedere:

- [Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365](endpoint-dlp-learn-about.md)
- [Informazioni sul criterio predefinito per la prevenzione della perdita di dati in Microsoft Teams (anteprima)](dlp-teams-default-policy.md)
- [Informazioni sullo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)](dlp-on-premises-scanner-learn.md)
- [Informazioni sull'Estensione della conformità Microsoft (anteprima)](dlp-chrome-learn-about.md)
- [Informazioni sulla dashboard degli avvisi per la prevenzione delle perdita dei dati](dlp-alerts-dashboard-learn.md)

Per informazioni su come usare la prevenzione della perdita dei dati per conformarsi alle normative sulla privacy dei dati, vedere [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).
