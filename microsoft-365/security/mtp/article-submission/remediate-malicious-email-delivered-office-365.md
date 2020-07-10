---
title: Correzione di messaggi di posta elettronica dannosi recapitati in Office 365
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 07/09/2020
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
ms.openlocfilehash: 6842de26bf262158f71f21b23a06554272e8eafb
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091975"
---
# <a name="remediate-malicious-emails-that-were-delivered-in-office-365"></a>Correggere i messaggi di posta elettronica dannosi che sono stati recapitati in Office 365

La correzione comporta l'esecuzione di un'azione proscritta su una minaccia. I messaggi dannosi inviati all'organizzazione possono essere rimossi dal sistema, tramite ZAP (zero-hour auto-Purge) o dai team di sicurezza mediante azioni di correzione come sposta in posta in arrivo, sposta in indesiderata, sposta in cartella elementi eliminati, Elimina o Elimina temporaneamente. Office Advanced Threat Protection (Office ATP) P2/E5 offre ai team delle operazioni di sicurezza la possibilità di mediare le minacce nei messaggi di posta elettronica e di collaborazione tramite la ricerca manuale e le indagini automatizzate.

> [!NOTE]
> Passare a un articolo di indagine [qui](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide).

## <a name="what-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

> [!NOTE]
> Affinché i team di sicurezza possano correggere i messaggi di posta elettronica, è necessario che dispongano di un ruolo di ricerca ed eliminazione. L'assegnazione di ruolo viene fatta tramite le autorizzazioni nel centro sicurezza e conformità. <p>

## <a name="remediations-through-manual-investigation-or-air"></a>Correzioni tramite analisi manuale o aria

La ricerca manuale si verifica quando i team di sicurezza identificano le minacce manualmente, utilizzando le funzionalità di protezione e filtro in Esplora minacce. La **correzione manuale** nei messaggi di posta elettronica può essere attivata tramite qualsiasi visualizzazione della posta (malware, phishing o tutti i messaggi di posta elettronica) dopo aver trovato una serie di messaggi di posta elettronica che devono essere corretti.

![Caccia manuale in Office 365 Threat Explorer per data.](../../../media/tp-RemediationArticle1.png "Esplora minacce")

La selezione dei messaggi di posta elettronica può essere eseguita in più modi tramite Esplora minacce:

1. Messaggi di posta elettronica a mano: questo significa che i team delle operazioni di sicurezza possono utilizzare filtri nelle rispettive visualizzazioni e selezionare alcuni messaggi di posta elettronica provenienti da Esplora minacce che devono essere corretti. Il limite massimo per la selezione dei messaggi di posta elettronica è 100 (100). I team delle operazioni di sicurezza non possono selezionare più di cento messaggi di posta elettronica manualmente.

2. Selezione query: i team delle operazioni di sicurezza possono selezionare un'intera query utilizzando il pulsante Top "Seleziona tutto". La stessa query viene visualizzata anche nei dettagli sull'invio di posta elettronica centro operazioni.

3. Selezione query con esclusione: in alcuni casi è possibile che i team delle operazioni di sicurezza decidano di correggere i messaggi di posta elettronica selezionando un'intera query e escludendo manualmente alcuni messaggi di posta elettronica dalla query. A tale scopo, un amministratore può utilizzare la casella di controllo "Seleziona tutto" e scorrere verso il basso per escludere alcuni messaggi di posta elettronica, manualmente. Il numero massimo di messaggi di posta elettronica che la query può contenere è 1000 (1.000) e il numero massimo di esclusioni è 100 (100), in questo caso.

Dopo aver selezionato i messaggi di posta elettronica da Esplora minacce, la creazione di correzione può iniziare eseguendo un'azione diretta o accodando messaggi di posta elettronica per un'azione:

 - Approvazione diretta: quando le azioni come ' sposta in posta in arrivo ',' Sposta su posta indesiderata ',' sposta in elementi eliminati ',' eliminazione temporanea ',' eliminazione definitiva ' sono selezionate da personale di sicurezza con le autorizzazioni appropriate e i passaggi successivi sono seguiti fino alla creazione di correzione, il processo di correzione inizia ad eseguire un'azione selezionata. Un riquadro a comparsa temporaneo Visualizza la correzione in corso.

 - Approvazione in due passaggi: l'azione ' Aggiungi a correzione ' può essere eseguita da un amministratore che non dispone di autorizzazioni appropriate o che deve attendere più tempo per eseguire l'azione. In questo caso, l'azione di correzione non viene eseguita direttamente. Al contrario, i messaggi di posta elettronica vengono aggiunti a un contenitore di correzione che deve essere approvato per l'esecuzione. Fino a quando non viene approvata la correzione, i messaggi di posta elettronica non verranno corretti. Dopo aver approvato la correzione, verranno intraprese azioni nei messaggi di posta elettronica.

Le indagini **automatizzate sull'analisi e la risposta (aria)** sono attivate dai criteri di corrispondenza nel sistema (Zap, segnalato dall'utente ecc.) o dai team di operazioni di sicurezza dall'interno di Threat Explorer selezionando manualmente i messaggi di posta elettronica da esaminare. Tali indagini possono includere alcune azioni consigliate che devono essere approvate dai team di operazioni di sicurezza. Queste azioni di correzione vengono visualizzate nella scheda azione all'interno dell'indagine automatizzata.  

:::image type="content" source="../../../media/tp-RemediationArticle3.png" alt-text="La posta con malware è una pagina con zapping che mostra il tempo di esecuzione dello zap.":::

Tutte le correzioni, ovvero l'approvazione diretta o in due passaggi, create manualmente tramite Esplora minacce o azioni approvate provenienti da indagini automatizzate, vengono visualizzate nel centro azioni, che è possibile accedere tramite la struttura di spostamento a sinistra in *Review* >  **Action Center**.

:::image type="content" source="../../../media/tp-RemediationArticle4.png" alt-text="Centro azioni con un elenco di minacce per data e gravità.":::

Centro azioni Visualizza tutte le azioni di correzione negli ultimi 30 giorni. Le azioni eseguite tramite Esplora risorse vengono visualizzate con lo stesso nome fornito dai team delle operazioni di sicurezza quando è stata creata la correzione. Le azioni intraprese tramite indagini automatizzate sono riportate con titoli che iniziano con l'avviso correlato che ha attivato l'indagine, ad esempio, "zap email cluster..."

Ogni elemento di correzione può essere aperto per visualizzarne i dettagli. Quando si apre un elemento di correzione, vengono visualizzati i dettagli di correzione di base, il nome della correzione, la data di creazione, la descrizione, la gravità delle minacce e lo stato. Vengono inoltre visualizzate due schede. 

1. **Scheda invio posta**: questo è il numero di messaggi inviati tramite Esplora minacce o indagini automatizzate da correggere. Questi messaggi di posta elettronica possono essere:

   :::image type="content" source="../../../media/tp-RemediationArticle5.png" alt-text="Il centro azioni con minacce actionable e not actionable.":::

   **Azione**: i messaggi di posta elettronica nei seguenti percorsi delle cassette postali cloud possono essere comportati e spostati, vale a dire che qualsiasi messaggio all'interno della categoria remediable può essere spostato da una posizione a un'altra:
  - Posta in arrivo 
  - Posta indesiderata  
  - Cartella eliminata
  - Cartella eliminata morbida

   > [!NOTE]
   > Attualmente, solo un utente finale con accesso alla cassetta postale può recuperare gli elementi da una cartella soft delete.

   **Non**utilizzabile: i messaggi di posta elettronica nei seguenti percorsi non possono essere comportati o spostati come parte delle azioni di posta elettronica, ad esempio, i messaggi di posta elettronica in una categoria non risolvibile non possono essere spostati nella categoria non risolvibile o in una posizione risolvibile. I percorsi non rimediable sono:

   - Quarantena
   - Cartella eliminata in modo rigido
   - On-Prem/External
   - Esito negativo/ritirato
  
   I messaggi inviati sono categorizzati come rimediabili o non rimedibili. Nella maggior parte dei casi, i messaggi rimediable e non rimediabili devono aggiungere fino al totale dei messaggi inviati. Tuttavia, è possibile che si verifichino casi rari in cui i messaggi inviati non possono aggiungere fino alla somma degli elementi rimediable e non remediable e potrebbero essere superiori o inferiori al numero totale di messaggi inviati. Ciò può verificarsi a causa di ritardi del sistema, timeout o messaggi scaduti. I messaggi scadono in base al periodo di conservazione dell'organizzazione.

   A meno che non si stiano ripristinando i messaggi obsoleti dopo il periodo di conservazione dell'organizzazione, se si verificano incoerenze nei numeri, è consigliabile riprovare a correggere gli elementi. Per i ritardi di sistema, gli aggiornamenti correttivi vengono in genere aggiornati in poche ore.

   Se il periodo di conservazione dell'organizzazione per la posta elettronica in Esplora risorse è di 30 giorni e si stanno ripristinando i messaggi di posta elettronica che risalgono a 29-30 giorni fa, è possibile che i conteggi dei messaggi di invio non vengano sempre aggiunti come potrebbe essere già iniziato lo spostamento del periodo di conservazione.

   Se la correzione è bloccata in uno stato di "in corso" per un po' di tempo, è probabile che si verifichino ritardi del sistema. La correzione potrebbe richiedere fino a poche ore. È possibile che si verifichi una variazione nei conteggi dell'invio di posta elettronica poiché alcuni messaggi di posta elettronica non facevano parte della query durante l'avvio della correzione, a causa di ritardi del sistema. È consigliabile riprovare la correzione in tali casi.  

   Per ottenere risultati ottimali, è necessario eseguire la correzione in batch più piccoli di circa 50K o meno.  

   Tra tutti i messaggi di posta elettronica nell'invio di messaggi, i messaggi remediable sono gli unici che verranno recapitati durante la correzione. I messaggi di posta elettronica non rimborsabili non possono essere corretti dal sistema di e-mail di Office 365, in quanto non sono archiviati nelle cassette postali cloud.

   Per i messaggi di posta elettronica trovati in quarantena, gli amministratori possono andare in quarantena per intraprendere azioni su tali messaggi di posta elettronica, se necessario, ma i messaggi di posta elettronica scadranno dalla quarantena se non vengono eliminati manualmente. I messaggi di posta elettronica messi in quarantena a causa di contenuti dannosi non sono accessibili dagli utenti finali, quindi il personale della sicurezza non deve intraprendere alcuna azione specifica per eliminare la minaccia in quarantena. Se i messaggi di posta elettronica sono on-Prem o esterni, l'utente finale può essere contattato per risolvere il messaggio di posta elettronica sospetto o utilizzare gli strumenti di sicurezza e server di posta elettronica separati per la rimozione. Questi messaggi di posta elettronica possono essere identificati applicando il percorso di recapito = on-Prem/filtro esterno in Esplora minacce. Per i messaggi di posta elettronica non riusciti o eliminati o che non sono accessibili dall'utente finale, non è necessario che la posta elettronica venga attenuata, in quanto non raggiunge la cassetta postale.

   Questo è il modo in cui un invio viene visualizzato in Action Center. Una correzione può contenere più invii. Se più azioni vengono approvate tramite un'indagine automatizzata, ogni azione del cluster di posta elettronica o di posta elettronica viene visualizzata nella stessa correzione di un altro invio.

   :::image type="content" source="../../../media/tp-RemediationArticle6.png" alt-text="Riquadro di volo del cluster di posta elettronica zap.":::

   Se si fa clic su un elemento per l'invio di posta elettronica, verranno visualizzati i dettagli di tale correzione, ad esempio la query (quando la correzione viene attivata mediante indagini automatizzate o Esplora minacce tramite la selezione di una query), l'ora di inizio e l'ora di fine della correzione. Viene inoltre visualizzato un elenco di messaggi inviati per la correzione. Quando i messaggi vengono spostati fuori dal periodo di conservazione dell'esploratore, i messaggi scompariranno da questo elenco. In questo elenco vengono inoltre visualizzati i singoli messaggi dall'elenco che sono risolvibili.

2. **Scheda registri azione**: questa scheda consente di visualizzare il risultato dei messaggi corretti, inclusi i dettagli quali la data approvata, il responsabile approvazione (amministratore che ha approvato l'azione), l'azione, lo stato e i conteggi.  

   Lo stato è lo stato generale della correzione. Lo stato può essere:

   - **Avviato**: quando viene attivata una correzione.
   - In **coda**: quando la correzione viene accodata per la riduzione dei messaggi di posta elettronica.
   - **In corso**: quando la riduzione è in corso.
   - **Completata**: quando la riduzione su tutti i messaggi di posta elettronica rimediabili viene eseguita correttamente o con alcuni errori. 
   - **Operazione non riuscita**: quando non vengono eseguite correzioni.

   Poiché solo i messaggi di posta elettronica rimediabili possono essere recapitati, la pulizia di ogni e-mail viene considerata come riuscita o non riuscita. Dal totale dei messaggi di posta elettronica rimediabili, vengono esposti gli attenuamenti di esito positivo e non riuscito.

   - Operazione **riuscita**: quando viene eseguita l'azione desiderata sui messaggi di posta elettronica rimediabili, ovvero corrisponde al percorso di destinazione desiderato e all'intenzione di amministratore. Ad esempio, un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo da eseguire l'azione di eliminare i messaggi di posta elettronica soft. Se un messaggio di posta elettronica risolvibile viene trovato nella cartella Soft Deleted dopo che è stata eseguita l'azione, lo stato verrà visualizzato come riuscito.  

   - **Errore**: quando l'azione desiderata sui messaggi di posta elettronica rimediabili ha esito negativo. Ad esempio, un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo da eseguire l'azione di eliminazione dei messaggi di posta elettronica soft. Se nella cassetta postale è ancora presente un messaggio di posta elettronica risolvibile, lo stato verrà visualizzato come non riuscito.

   Se si fa clic su un elemento nel log azione, vengono visualizzati i dettagli relativi alla correzione. Per gli elementi riusciti, se i dettagli dicono, riusciti o non vengono trovati nella cassetta postale, significa che l'elemento è stato già rimosso dalla cassetta postale. A volte sono presenti errori che si verificano a causa di un errore sistemico durante la correzione e, in questi casi, è consigliabile riprovare la correzione.  

La correzione è uno strumento potente per attenuare le minacce e indirizzare i messaggi di posta elettronica sospetti. Questo aiuta a mantenere sicura un'organizzazione.  

## <a name="more-info"></a>Altre informazioni

Vedere [indagare la posta elettronica dannosa che è stata recapitata in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide).
