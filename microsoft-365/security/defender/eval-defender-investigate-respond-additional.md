---
title: Provare Microsoft 365 Defender di risposta agli incidenti in un ambiente pilota, definire le priorità e gestire gli incidenti, configurare indagini e risposte automatizzate e usare la ricerca avanzata
description: Provare le funzionalità di risposta agli Microsoft 365 Defender per definire le priorità e gestire gli incidenti, automatizzare le indagini e usare la ricerca avanzata nel rilevamento delle minacce.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458114"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>Provare Microsoft 365 Defender di risposta agli incidenti in un ambiente pilota

**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 2 di 2](eval-defender-investigate-respond.md) nel processo di esecuzione di un'indagine e di risposta a un evento imprevisto Microsoft 365 Defender un ambiente pilota. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica.](eval-defender-investigate-respond.md)

Dopo aver eseguito una risposta a un evento [imprevisto per](eval-defender-investigate-respond-simulate-attack.md)un attacco simulato, ecco alcune Microsoft 365 Defender da esplorare:

|Funzionalità |Descrizione |
|:-------|:-----|
| [Assegnare priorità agli incidenti](#prioritize-incidents) | Utilizzare il filtro e l'ordinamento della coda degli eventi imprevisti per determinare quali eventi imprevisti affrontare successivamente. |
| [Gestire gli incidenti](#manage-incidents) | Modificare le proprietà dell'evento imprevisto per garantire l'assegnazione corretta, aggiungere tag e commenti e risolvere un evento imprevisto. |
| [Analisi e risposta automatizzate](#examine-automated-investigation-and-response-with-the-action-center) | Funzionalità di analisi e risposta automatizzate (AIR) che consentono al team delle operazioni di sicurezza di affrontare le minacce in modo più efficiente ed efficiente. Il centro notifiche è un'esperienza di "singolo riquadro di vetro" per le attività relative a eventi imprevisti e avvisi, ad esempio l'approvazione di azioni di correzione in sospeso. |
| [Rilevazione avanzata](#advanced-hunting) | Uno strumento di ricerca delle minacce basato su query che consente di esaminare in modo proattivo gli eventi nella rete e individuare gli indicatori di minaccia e le entità. È inoltre possibile utilizzare la ricerca avanzata durante l'indagine e la correzione di un evento imprevisto. |
||||

## <a name="prioritize-incidents"></a>Assegnare priorità agli eventi imprevisti

Si arriva alla coda degli eventi imprevisti da **Eventi imprevisti &** avvisi > eventi imprevisti sulla barra di avvio veloce del portale di Microsoft 365 Defender ([security.microsoft.com](https://security.microsoft.com)). Di seguito viene riportato un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Esempio di coda degli eventi imprevisti":::

La **sezione Eventi imprevisti e avvisi più** recenti mostra un grafico del numero di avvisi ricevuti e di eventi imprevisti creati nelle ultime 24 ore.

Per esaminare l'elenco degli eventi imprevisti e assegnarne la priorità per l'assegnazione e l'indagine, è possibile: 

- Configurare colonne personalizzabili (selezionare **Scegli** colonne ) per fornire visibilità sulle diverse caratteristiche dell'evento imprevisto o delle entità influenzate. Ciò consente di prendere una decisione informata sulla definizione di priorità degli incidenti per l'analisi.

- Usare il filtro per concentrarsi su uno scenario o una minaccia specifici. L'applicazione di filtri alla coda degli eventi imprevisti consente di determinare quali eventi imprevisti richiedono un'attenzione immediata. 

Dalla coda eventi imprevisti predefinita, selezionare **Filtri** per visualizzare un riquadro **Filtri,** da cui è possibile specificare un set specifico di eventi imprevisti. Ecco un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Esempio del riquadro dei filtri per la coda eventi imprevisti":::

Per ulteriori informazioni, vedere [Prioritize incidents](incident-queue.md).

## <a name="manage-incidents"></a>Gestire gli incidenti

È possibile gestire gli eventi imprevisti dal **riquadro Gestisci eventi imprevisti** per un evento imprevisto. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Esempio del riquadro Gestisci evento imprevisto di un evento imprevisto":::

È possibile visualizzare questo riquadro dal **collegamento Gestisci operazioni** non consentite in:

- Riquadro Proprietà di un evento imprevisto nella coda degli eventi imprevisti.
- **Pagina di** riepilogo di un evento imprevisto.

Ecco i modi in cui è possibile gestire gli eventi imprevisti:

- Modificare il nome dell'evento imprevisto

  Modificare il nome assegnato in modo utomatico in base alle procedure consigliate del team di sicurezza.
  
- Aggiungere tag agli eventi

  Aggiungere tag utilizzati dal team di sicurezza per classificare gli eventi imprevisti, che possono essere filtrati in un secondo momento.
  
- Assegnare l'evento imprevisto a se stessi

  Assegnarlo al nome dell'account utente, che può essere filtrato in un secondo momento.
  
- Risolvere un evento imprevisto

  Chiudere l'evento imprevisto dopo che è stato corretti.
  
- Impostare la classificazione e la determinazione

  Classificare e selezionare il tipo di minaccia quando si risolve un evento imprevisto.
  
- Aggiungere commenti

  Usa i commenti per lo stato, le note o altre informazioni in base alle procedure consigliate del team di sicurezza. La cronologia completa dei commenti è disponibile **nell'opzione Commenti** e cronologia nella pagina dei dettagli di un evento imprevisto.

Per ulteriori informazioni, vedere [Manage incidents](manage-incidents.md).

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>Esaminare l'indagine automatizzata e la risposta con il centro notifiche

A seconda di come vengono configurate le funzionalità di analisi e risposta automatizzate per l'organizzazione, le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione da parte del team delle operazioni di sicurezza. Tutte le azioni, in sospeso o [](m365d-action-center.md)completate, sono elencate nel centro notifiche, in cui sono elencate le azioni di correzione in sospeso e completate per i dispositivi, i contenuti di collaborazione & posta elettronica e le identità in un'unica posizione.

Di seguito viene riportato un esempio.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro notifiche unificato in Microsoft 365 Defender":::

Nel centro notifiche è possibile selezionare le azioni in sospeso e quindi approvarle o rifiutarle nel riquadro a comparsa. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Approvare o rifiutare un’azione":::

Approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che le indagini automatizzate possano procedere e completare in modo appropriato.

Per ulteriori informazioni, vedere [Analisi e risposta automatizzate e](m365d-autoir.md) Centro [notifiche.](m365d-action-center.md)

## <a name="advanced-hunting"></a>Rilevazione avanzata

> [!NOTE]
> Prima di illustrare la simulazione di ricerca avanzata, guardare il video seguente per comprendere i concetti di ricerca avanzati, vedere dove è possibile trovarlo nel portale e sapere come può essere utile nelle operazioni di sicurezza.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


Se la simulazione di attacco [di PowerShell](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) senza file facoltativa era un attacco reale che aveva già raggiunto la fase di accesso alle credenziali, è possibile utilizzare la ricerca avanzata in qualsiasi punto dell'indagine per cercare in modo proattivo gli eventi e i record nella rete usando ciò che si sa già dagli avvisi generati e dalle entità interessate. Ad esempio, è possibile eseguire una query per tutte le connessioni all'indirizzo IP esterno negli ultimi 30 giorni.

### <a name="hunting-environment-requirements"></a>Requisiti dell'ambiente di ricerca

Per questa simulazione è necessaria una singola cassetta postale interna e un dispositivo. Sarà inoltre necessario un account di posta elettronica esterno per inviare il messaggio di prova.

1. Verificare che il tenant abbia [abilitato Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).
2. Identificare una cassetta postale di destinazione da utilizzare per la ricezione della posta elettronica.

   - Questa cassetta postale deve essere monitorata da Microsoft Defender per Office 365

   - Il dispositivo dal requisito 3 deve accedere a questa cassetta postale

3. Configurare un dispositivo di test:

    a. Assicurati di usare la Windows 10 1903 o versione successiva.

    b. Aggiungere il dispositivo di test al dominio di test.

    c. [Attivare Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). In caso di problemi durante l'abilitazione Windows Defender Antivirus, vedere [questo argomento per la risoluzione dei problemi.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

    d. [Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Eseguire la simulazione

1. Da un account di posta elettronica esterno, inviare un messaggio di posta elettronica alla cassetta postale identificata nel passaggio 2 della sezione requisiti dell'ambiente di ricerca. Includere un allegato che sarà consentito tramite i criteri di filtro della posta elettronica esistenti. Questo file non deve essere dannoso o eseguibile. I tipi di file suggeriti <i>sono.pdf</i>, <i>.exe</i> (se consentito) o un tipo Office documento, ad esempio un file di Word.

2. Aprire il messaggio di posta elettronica inviato dal dispositivo configurato come definito nel passaggio 3 della sezione requisiti dell'ambiente di ricerca. Aprire l'allegato o salvare il file nel dispositivo.

#### <a name="go-hunting"></a>Andare a caccia

1. Aprire il [Microsoft 365 Defender portale.](https://security.microsoft.com/)

2. Nel riquadro di spostamento selezionare **Ricerca > ricerca avanzata.**

3. Creare una query che inizia raccogliendo eventi di posta elettronica.

   1. Selezionare **Query > Nuovo**.

   1. In Gruppi **di posta** elettronica in **Ricerca avanzata** fare doppio clic su **EmailEvents.** Dovrebbe essere visualizzato nella finestra della query.

      ```console
      EmailEvents
      ```

   1. Modificare l'intervallo di tempo della query per le ultime 24 ore. Presupponendo che il messaggio di posta elettronica inviato durante l'esecuzione della simulazione precedente sia stato nelle ultime 24 ore, altrimenti modificare l'intervallo di tempo in base alle esigenze.

   1. Selezionare **Esegui query**. I risultati potrebbero variare a seconda dell'ambiente pilota.

      > [!NOTE]
      > Vedere il passaggio successivo per le opzioni di filtro per limitare la restituzione dei dati.

      ![Esempio dei risultati delle query di ricerca avanzata](../../media/mtp/fig19.png)

        > [!NOTE]
        > La ricerca avanzata visualizza i risultati delle query come dati tabulari. È inoltre possibile scegliere di visualizzare i dati in altri tipi di formato, ad esempio grafici.

   1. Esaminare i risultati e verificare se è possibile identificare il messaggio di posta elettronica aperto. La visualizzazione del messaggio nella ricerca avanzata può richiedere fino a due ore. Per limitare i risultati, è possibile aggiungere la condizione **where** alla query per cercare solo i messaggi di posta elettronica con "yahoo.com" come SenderMailFromDomain. Ecco un esempio.

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Fare clic nelle righe risultanti della query in modo da poter esaminare il record.

      ![Esempio del pannello laterale inspect record che si apre quando viene selezionato un risultato di ricerca avanzato](../../media/mtp/fig21.png)

4. Dopo aver verificato che sia possibile visualizzare il messaggio di posta elettronica, aggiungere un filtro per gli allegati. Concentrarsi su tutti i messaggi di posta elettronica con allegati nell'ambiente. Per questa simulazione, concentrarsi sui messaggi di posta elettronica in ingresso, non su quelli inviati dall'ambiente. Rimuovere i filtri aggiunti per individuare il messaggio e aggiungere "| dove **AttachmentCount > 0** e **EmailDirection**  ==  **"Inbound""**

   La query seguente mostrerà il risultato con un elenco più breve rispetto alla query iniziale per tutti gli eventi di posta elettronica:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Includere quindi le informazioni sull'allegato (ad esempio: nome file, hash) nel set di risultati. A tale scopo, unire la **tabella EmailAttachmentInfo.** I campi comuni da utilizzare per l'aggiunta, in questo caso **sono NetworkMessageId** **e RecipientObjectId**.

   La query seguente include anche una riga aggiuntiva "| **project-rename EmailTimestamp=Timestamp**" che consente di identificare il timestamp correlato alla posta elettronica e i timestamp correlati alle azioni dei file che verranno aggiunti nel passaggio successivo.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Usa quindi il **valore SHA256** della tabella **EmailAttachmentInfo** per trovare **DeviceFileEvents** (azioni di file eseguite nell'endpoint) per l'hash. Il campo comune qui sarà l'hash SHA256 per l'allegato.

   La tabella risultante ora include i dettagli dell'endpoint (Microsoft Defender for Endpoint), ad esempio il nome del dispositivo, l'azione eseguita (in questo caso filtrata per includere solo gli eventi FileCreated) e la posizione in cui è stato archiviato il file. Verrà incluso anche il nome dell'account associato al processo.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   A questo punto è stata creata una query che identificherà tutti i messaggi di posta elettronica in ingresso in cui l'utente ha aperto o salvato l'allegato. È inoltre possibile perfezionare questa query in modo da filtrare i domini del mittente specifici, le dimensioni dei file, i tipi di file e così via.

7. Le funzioni sono un tipo speciale di join, che ti consente di estrarre più dati TI su un file come la diffusione, le informazioni sul firmatario e sull'autorità emittente e così via. Per ottenere ulteriori dettagli sul file, utilizzare la **funzione FileProfile():**

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Creare un rilevamento

Dopo aver creato una query che identifica le  informazioni di cui si desidera ricevere un avviso se si verificano in futuro, è possibile creare un rilevamento personalizzato dalla query.

I rilevamenti personalizzati eseguiranno la query in base alla frequenza impostata e i risultati delle query creeranno avvisi di sicurezza, in base alle risorse selezionate. Tali avvisi saranno correlati agli eventi imprevisti e possono essere valutati come qualsiasi altro avviso di sicurezza generato da uno dei prodotti.

1. Nella pagina della query rimuovere le righe 7 e 8 aggiunte al passaggio 7 delle istruzioni di ricerca Go e fare clic **su Crea regola di rilevamento.**

   ![Esempio di posizione in cui è possibile fare clic su Crea regola di rilevamento nella pagina ricerca avanzata](../../media/mtp/fig22.png)

   > [!NOTE]
   > Se si fa **clic su Crea** regola di rilevamento e si verificano errori di sintassi nella query, la regola di rilevamento non verrà salvata. Verificare che la query non presenti errori.

2. Compilare i campi obbligatori con le informazioni che consentiranno al team di sicurezza di comprendere l'avviso, il motivo per cui è stato generato e le azioni previste.

   ![Esempio della pagina crea regola di rilevamento in cui è possibile definire i dettagli dell'avviso](../../media/mtp/fig23.png)

   Assicurarsi di compilare i campi con chiarezza per fornire all'utente successivo una decisione informata su questo avviso della regola di rilevamento

3. Selezionare le entità che vengono influenzate in questo avviso. In questo caso, selezionare **Dispositivo** e **cassetta postale**.

   ![Esempio della pagina crea regola di rilevamento in cui è possibile scegliere i parametri delle entità influenzate](../../media/mtp/fig24.png)

4. Determinare quali azioni devono essere eseguite se l'avviso viene attivato. In questo caso, eseguire un'analisi antivirus, anche se è possibile eseguire altre azioni.

   ![Esempio della pagina crea regola di rilevamento in cui è possibile eseguire un'analisi antivirus quando viene attivato un avviso per risolvere le minacce](../../media/mtp/fig25.png)

5. Selezionare l'ambito per la regola di avviso. Poiché questa query coinvolge i dispositivi, i gruppi di dispositivi sono rilevanti in questo rilevamento personalizzato in base al contesto di Microsoft Defender for Endpoint. Quando si crea un rilevamento personalizzato che non include i dispositivi come entità influenzate, l'ambito non si applica.

   ![Esempio della pagina Crea regola di rilevamento in cui è possibile impostare l'ambito della regola di avviso per gestire le aspettative per i risultati che verranno visualizzati](../../media/mtp/fig26.png)

   Per questo progetto pilota, è consigliabile limitare questa regola a un sottoinsieme di dispositivi di testing nell'ambiente di produzione.

6. Selezionare **Crea**. Seleziona quindi **Regole di rilevamento personalizzate** nel riquadro di spostamento.

   ![Esempio di opzione Regole di rilevamento personalizzate nel menu](../../media/mtp/fig27a.png)

   ![Esempio della pagina delle regole di rilevamento che visualizza i dettagli della regola e dell'esecuzione](../../media/mtp/fig27b.png)

   Da questa pagina è possibile selezionare la regola di rilevamento, che aprirà una pagina dei dettagli.

   ![Esempio di pagina allegati di posta elettronica in cui è possibile visualizzare lo stato dell'esecuzione della regola, attivare avvisi e azioni, modificare il rilevamento e così via](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a>Formazione esperta sulla ricerca avanzata

**Tenere traccia dell'avversario** è una serie di webcast per i nuovi analisti della sicurezza e i cacciatori di minacce esperti. Illustra le nozioni di base della ricerca avanzata fino alla creazione di query sofisticate. 

Per [iniziare, vedi](advanced-hunting-expert-training.md) Formazione di esperti sulla ricerca avanzata.

### <a name="navigation-you-may-need"></a>Spostamento che potrebbe essere necessario

[Creare l'Microsoft 365 Defender di valutazione](eval-create-eval-environment.md)
