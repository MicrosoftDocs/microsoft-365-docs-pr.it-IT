---
title: Correzione di messaggi di posta elettronica dannosi recapitati in Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Correzione delle minacce
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: 9ffa3f71dafec4728294b17530ae1f9490d480da
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656684"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Correzione di messaggi di posta elettronica dannosi recapitati in Office 365

La correzione comporta l'esecuzione di un'azione proscritta su una minaccia. I messaggi dannosi inviati all'organizzazione possono essere rimossi dal sistema, tramite ZAP (zero-hour auto-Purge) o dai team di sicurezza mediante azioni di correzione come sposta in posta in arrivo, sposta in indesiderata, sposta in cartella elementi eliminati, Elimina o Elimina temporaneamente. Office Advanced Threat Protection (Office ATP) P2/E5 offre ai team delle operazioni di sicurezza la possibilità di mediare le minacce nei messaggi di posta elettronica e di collaborazione tramite la ricerca manuale e le indagini automatizzate.

> [!NOTE]
> Affinché i team di sicurezza possano correggere i messaggi di posta elettronica, è necessario che dispongano di un ruolo di ricerca ed eliminazione. L'assegnazione di ruolo viene fatta tramite le autorizzazioni nel centro sicurezza e conformità.

## <a name="what-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

Per eseguire determinate azioni, ad esempio la visualizzazione delle intestazioni dei messaggi o il download del contenuto del messaggio di posta elettronica, è necessario un nuovo ruolo denominato *Anteprima* aggiunto a un altro gruppo di ruoli appropriato. La tabella seguente consente di chiarire i ruoli e le autorizzazioni necessari.

****

|Attività|Gruppo di ruolo|Ruolo di anteprima necessario?|
|---|---|---|
|Utilizzo di Esplora minacce (e rilevamenti in tempo reale) per l'analisi delle minacce |Amministratore globale <br> Amministratore della sicurezza <br> Ruolo con autorizzazioni di lettura per la sicurezza|No|
|Utilizzare Esplora minacce (e rilevamenti in tempo reale) per visualizzare le intestazioni dei messaggi di posta elettronica così come l'anteprima e il download dei messaggi di posta elettronica in quarantena|Amministratore globale <br> Amministratore della sicurezza <br>Ruolo con autorizzazioni di lettura per la sicurezza|No|
|Utilizzare Esplora minacce per visualizzare le intestazioni e scaricare i messaggi di posta elettronica recapitati alle cassette postali|Amministratore globale <br>Amministratore della sicurezza <br> Ruolo con autorizzazioni di lettura per la sicurezza <br> Anteprima|Sì|
|

> [!NOTE]
> L' *Anteprima* è un ruolo e non un gruppo di ruoli. il ruolo di anteprima deve essere aggiunto a un gruppo di ruoli esistente per Office 365. Al ruolo di amministratore globale viene assegnato l'interfaccia di amministrazione di Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) e i ruoli amministratore sicurezza e lettore di sicurezza sono assegnati nel centro sicurezza & Compliance ( [https://protection.office.com](https://protection.office.com) ). Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Gli amministratori possono intraprendere le azioni necessarie per i messaggi di posta elettronica, ma per ottenere le loro azioni approvate, è necessario che il ruolo "Search and Purge" sia assegnato a loro tramite il Centro sicurezza e conformità > autorizzazioni.

## <a name="manual-and-automated-remediation"></a>Correzione automatica e manuale

La ricerca **manuale** si verifica quando i team di sicurezza identificano le minacce manualmente, utilizzando le funzionalità di protezione e filtro in Esplora minacce. La correzione manuale nei messaggi di posta elettronica può essere attivata tramite qualsiasi visualizzazione della posta (malware, phishing o tutti i messaggi di posta elettronica) dopo aver trovato una serie di messaggi di posta elettronica che devono essere corretti.

[Caccia manuale in Office 365 Threat Explorer per data.](../../media/tp-RemediationArticle1.png)

La selezione dei messaggi di posta elettronica può essere eseguita in più modi tramite Esplora minacce:

1. Scelta dei messaggi di posta elettronica a mano: questo significa che i team delle operazioni di sicurezza possono utilizzare i filtri nelle rispettive visualizzazioni e selezionare alcuni messaggi di posta elettronica provenienti da Esplora minacce che devono essere corretti. Il limite massimo per la selezione dei messaggi di posta elettronica è 100 (100). I team delle operazioni di sicurezza non possono selezionare più di cento messaggi di posta elettronica manualmente.

2. Selezione query: i team delle operazioni di sicurezza possono selezionare un'intera query utilizzando il pulsante Top "Seleziona tutto". La stessa query viene visualizzata anche nei dettagli sull'invio di posta elettronica centro operazioni.

3. Selezione query con esclusione: in alcuni casi è possibile che i team delle operazioni di sicurezza decidano di correggere i messaggi di posta elettronica selezionando un'intera query e escludendo manualmente alcuni messaggi di posta elettronica dalla query. A tale scopo, un amministratore può utilizzare la casella di controllo "Seleziona tutto" e scorrere verso il basso per escludere alcuni messaggi di posta elettronica, manualmente. Il numero massimo di messaggi di posta elettronica che la query può contenere è 1000 (1.000) e il numero massimo di esclusioni è 100 (100), in questo caso.

Dopo aver selezionato i messaggi di posta elettronica da Esplora minacce, la creazione di correzione può iniziare eseguendo un'azione diretta o accodando messaggi di posta elettronica per un'azione:

1. Approvazione diretta: quando le azioni come ' sposta in posta in arrivo ',' Sposta su posta indesiderata ',' sposta in elementi eliminati ',' eliminazione temporanea ',' eliminazione definitiva ' sono selezionate da personale di sicurezza con le autorizzazioni appropriate e i passaggi successivi sono seguiti fino alla creazione di correzione, il processo di correzione inizia ad eseguire un'azione selezionata. Un riquadro a comparsa temporaneo Visualizza la correzione in corso.

2. Approvazione in due passaggi: l'azione ' Aggiungi a correzione ' può essere eseguita da un amministratore che non dispone di autorizzazioni appropriate o che deve attendere più tempo per eseguire l'azione. In questo caso, l'azione di correzione non viene eseguita direttamente. Al contrario, i messaggi di posta elettronica vengono aggiunti a un contenitore di correzione che deve essere approvato per l'esecuzione. Fino a quando non viene approvata la correzione, il messaggio di posta elettronica non verrà rimediato. Dopo aver approvato la correzione, verranno intraprese azioni sul messaggio di posta elettronica.

L' **analisi automatizzata e le azioni di risposta (aria)** vengono attivate dagli avvisi o dai team di operazioni di sicurezza dall'interno di Esplora minacce. Possono includere alcune correzioni consigliate che devono essere approvate dai team di operazioni di sicurezza. Queste azioni correttive sono incluse nella scheda azione all'interno dell'indagine automatizzata.

[La posta con malware è una pagina con zapping che mostra il tempo di esecuzione dello zap.](../../media/tp-RemediationArticle3.png)

Tutte le correzioni, ovvero l'approvazione diretta o in due passaggi, create tramite Esplora minacce e le azioni approvate provenienti da indagini automatizzate, vengono visualizzate nell'Action Center, a cui è possibile accedere tramite la struttura di spostamento a sinistra in * Review * > **Action Center**.

[Centro azioni con un elenco di minacce per data e gravità.](../../media/tp-RemediationArticle4.png)

Centro azioni Visualizza tutte le azioni di correzione negli ultimi 30 giorni. Le azioni eseguite tramite Esplora risorse vengono visualizzate con lo stesso nome fornito dai team delle operazioni di sicurezza quando è stata creata la correzione. Le azioni intraprese tramite indagini automatizzate sono riportate in titoli che iniziano con l'avviso correlato che ha attivato l'inchiesta, ad esempio "zap email cluster...".

Ogni elemento di correzione può essere aperto per visualizzarne i dettagli. Quando si apre un elemento di correzione, vengono visualizzati i dettagli di correzione di base, il nome della correzione, la data di creazione, la descrizione, la gravità delle minacce e lo stato. Vengono inoltre visualizzate due schede.

1. **Scheda invio posta**: questo è il numero di messaggi inviati tramite Esplora minacce o indagini automatizzate da correggere. Questi messaggi di posta elettronica possono essere:

   [Il centro azioni con minacce actionable e not actionable.](../../media/tp-RemediationArticle5.png)

   - **Azione**: i messaggi di posta elettronica nei seguenti percorsi delle cassette postali cloud possono essere comportati e spostati, ossia qualsiasi messaggio all'interno della categoria rimedio può essere spostato da una posizione a un'altra:

     - Posta in arrivo
     - Posta indesiderata
     - Cartella eliminata
     - Cartella eliminata morbida

     [!NOTE]
     > Attualmente, solo un utente finale con accesso alla cassetta postale può recuperare gli elementi da una cartella soft delete.

   - **Non**utilizzabile: i messaggi di posta elettronica nei seguenti percorsi non possono essere comportati o spostati come parte delle azioni di posta elettronica ovvero le e-mail in una categoria non risolvibile non possono essere spostate nella categoria non risolvibile o in rimedio. I percorsi non rimediable sono:

     - Quarantena
     - Cartella eliminata in modo rigido
     - On-Prem/External
     - Esito negativo/ritirato

   I messaggi sospetti inviati sono categorizzati come rimediabili o non rimedibili. Nella maggior parte dei casi, i messaggi rimediable e non rimediabili devono aggiungere fino al totale dei messaggi inviati. Tuttavia, è possibile che si verifichino casi rari in cui i messaggi inviati non possono aggiungere fino alla somma degli elementi rimediable e non remediable e potrebbero essere superiori o inferiori al numero totale di messaggi inviati. Ciò può verificarsi a causa di ritardi del sistema, timeout o messaggi scaduti. I messaggi scadono in base al periodo di conservazione dell'organizzazione.

   A meno che non si stiano ripristinando i messaggi obsoleti dopo il periodo di conservazione dell'organizzazione, se si verificano incoerenze nei numeri, è consigliabile riprovare a correggere gli elementi. Per i ritardi di sistema, gli aggiornamenti correttivi vengono in genere aggiornati in poche ore.

   Se il periodo di conservazione dell'organizzazione per la posta elettronica in Esplora risorse è di 30 giorni e si stanno ripristinando i messaggi di posta elettronica che risalgono a 29-30 giorni fa, è possibile che i conteggi dei messaggi di invio non vengano sempre aggiunti come potrebbe essere già iniziato lo spostamento del periodo di conservazione.

   Se le correzioni vengono bloccate in uno stato "in corso" per un po' di tempo, è probabile che si verifichino ritardi del sistema. La correzione potrebbe richiedere fino a poche ore. È possibile che si verifichi una variazione nei conteggi dell'invio di posta elettronica poiché alcuni messaggi di posta elettronica non facevano parte della query durante l'avvio della correzione, a causa di ritardi del sistema. È consigliabile riprovare la correzione in tali casi.

   Per ottenere risultati ottimali, è necessario eseguire la correzione in batch più piccoli di circa 50K o meno.

   Tra tutti i messaggi di posta elettronica nell'invio di messaggi, i messaggi remediable sono gli unici che verranno recapitati durante la correzione. I messaggi di posta elettronica non rimborsabili non possono essere corretti dal sistema di e-mail di Office 365, in quanto non sono archiviati nelle cassette postali cloud.

   Per i messaggi di posta elettronica trovati in quarantena, gli amministratori possono andare in quarantena per intraprendere azioni su tali messaggi di posta elettronica, se necessario, ma i messaggi di posta elettronica scadranno dalla quarantena se non vengono eliminati manualmente. I messaggi di posta elettronica messi in quarantena a causa di contenuti dannosi non sono accessibili dagli utenti finali, quindi il personale della sicurezza non deve intraprendere alcuna azione specifica per eliminare la minaccia in quarantena. Se i messaggi di posta elettronica sono on-Prem o esterni, l'utente finale può essere contattato per risolvere il messaggio di posta elettronica sospetto o utilizzare gli strumenti di sicurezza e server di posta elettronica separati per la rimozione. Questi messaggi di posta elettronica possono essere identificati applicando il percorso di recapito = on-Prem/filtro esterno in Esplora minacce. Per i messaggi di posta elettronica non riusciti o eliminati o che non sono accessibili dall'utente finale, non è necessario che la posta elettronica venga attenuata, in quanto non raggiunge la cassetta postale.

   Questo è il modo in cui un invio viene visualizzato in Action Center. Una correzione può contenere più invii. Se più azioni vengono approvate tramite un'indagine automatizzata, ogni azione del cluster di posta elettronica o di posta elettronica viene visualizzata nella stessa correzione di un altro invio.

   [Riquadro a comparsa di cluster di posta elettronica ZAP.](../../media/tp-RemediationArticle6.png)

   Se si fa clic su un elemento per l'invio di posta elettronica, verranno visualizzati i dettagli di tale correzione, ad esempio la query (quando la correzione viene attivata mediante indagini automatizzate o Esplora minacce tramite la selezione di una query), l'ora di inizio e l'ora di fine della correzione. Viene inoltre visualizzato un elenco di messaggi inviati per la correzione. Quando i messaggi vengono spostati fuori dal periodo di conservazione dell'esploratore, i messaggi scompariranno da questo elenco. In questo elenco vengono inoltre visualizzati i singoli messaggi dall'elenco che sono risolvibili.

2. **Scheda registri azione**: questa scheda consente di visualizzare il risultato dei messaggi corretti, inclusi i dettagli quali la data approvata, il responsabile approvazione (amministratore che ha approvato l'azione), l'azione, lo stato e i conteggi.

   Lo stato è lo stato generale della correzione. Lo stato può essere:

     - **Avviato**: quando viene attivata una correzione.
     - In **coda**: quando la correzione viene accodata per la riduzione dei messaggi di posta elettronica.
     - **In corso**: quando la riduzione è in corso.
     - **Completata**: quando la riduzione su tutti i messaggi di posta elettronica rimediabili viene eseguita correttamente o con alcuni errori.
     - **Operazione non riuscita**: quando non vengono eseguite correzioni.

   Poiché solo i messaggi di posta elettronica rimediabili possono essere recapitati, la pulizia di ogni e-mail viene considerata come riuscita o non riuscita. Dal totale dei messaggi di posta elettronica rimediabili, vengono esposti gli attenuamenti di esito positivo e non riuscito.

   - Operazione **riuscita**: quando l'azione desiderata sui messaggi di posta elettronica rimediabili è compiuta e corrisponde all'intenzione di amministratore. Ad esempio, un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo da eseguire l'azione di eliminare i messaggi di posta elettronica soft. Se un messaggio di posta elettronica risolvibile non viene trovato nella cartella originale dopo l'esecuzione dell'azione, lo stato verrà visualizzato con esito positivo.

   - **Errore**: quando l'azione desiderata sui messaggi di posta elettronica rimediabili ha esito negativo. Ad esempio, un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo da eseguire l'azione di eliminazione dei messaggi di posta elettronica soft. Se nella cassetta postale è ancora presente un messaggio di posta elettronica risolvibile, lo stato verrà visualizzato come non riuscito.

   Se si fa clic su un elemento nel log azione, vengono visualizzati i dettagli relativi alla correzione. Per gli elementi riusciti, se i dettagli dicono, riusciti o non vengono trovati nella cassetta postale, significa che l'elemento è stato già rimosso dalla cassetta postale. A volte sono presenti errori che si verificano a causa di un errore sistemico durante la correzione e, in questi casi, è consigliabile riprovare la correzione.

   La correzione è uno strumento potente per attenuare le minacce e indirizzare i messaggi di posta elettronica sospetti. Questo aiuta a mantenere sicura un'organizzazione.

## <a name="more-info"></a>Altre informazioni

Vedere [indagare la posta involontaria](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)
