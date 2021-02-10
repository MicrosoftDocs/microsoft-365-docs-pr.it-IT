---
title: Correggere i messaggi di posta elettronica dannosi recapitati in Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Correzione delle minacce
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f623957a79ccd76702482cd23b4d8ce219603f6
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166880"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Correggere i messaggi di posta elettronica dannosi recapitati in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-    [Microsoft Defender per Office 365 piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)

La correzione significa eseguire un'azione prescritta contro una minaccia. La posta elettronica dannosa inviata all'organizzazione può essere pulita dal sistema, tramite l'eliminazione automatica a zero ore (ZAP) o dai team di sicurezza attraverso azioni di correzione come lo spostamento nella posta in *arrivo,* lo spostamento nella posta *indesiderata,* lo spostamento agli elementi *eliminati,* l'eliminazione reverssione *o* l'eliminazione *permanente.* Microsoft Defender per Office 365 P2/E5 consente ai team di sicurezza di correggere le minacce nelle funzionalità di posta elettronica e collaborazione tramite un'indagine manuale e automatizzata.

> [!NOTE]
> Per correggere la posta elettronica dannosa, i team di sicurezza necessitano *del* ruolo di ricerca ed eliminazione assegnato. L'assegnazione di ruolo viene eseguita tramite le autorizzazioni nel Centro sicurezza e conformità.

## <a name="what-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

Gli amministratori possono eseguire le azioni necessarie sui messaggi di posta  elettronica, ma per ottenere l'approvazione di tali azioni, devono disporre del ruolo di ricerca ed eliminazione assegnato loro tramite autorizzazioni del Centro sicurezza **&** \> **conformità.** Senza il ruolo "ricerca ed eliminazione" aggiunto a uno dei gruppi di ruoli, non saranno in grado di eseguire l'azione.

## <a name="manual-and-automated-remediation"></a>Correzione manuale e automatica

*La ricerca manuale* avviene quando i team di sicurezza identificano manualmente le minacce utilizzando le funzionalità di ricerca e filtro in Esplora minacce. La correzione manuale della posta elettronica può essere attivata tramite qualsiasi visualizzazione della posta elettronica (*Malware,* *Phish* o *Tutta* la posta elettronica ) dopo aver identificato un set di messaggi di posta elettronica che devono essere corretti.

> [!div class="mx-imgBorder"]
> [![Ricerca manuale in Office 365 Threat Explorer per data.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

I team di sicurezza possono usare Esplora minacce per selezionare i messaggi di posta elettronica in diversi modi:

- Scegliere manualmente i messaggi di posta elettronica: usare i filtri in varie visualizzazioni. Selezionare fino a 100 messaggi di posta elettronica da correggere.

- Selezione query: selezionare un'intera query utilizzando il pulsante **Seleziona tutto in** alto. La stessa query viene visualizzata anche nei dettagli dell'invio di posta elettronica nel centro notifiche.

- Selezione delle query con esclusione: a volte i team delle operazioni di sicurezza potrebbero voler correggere i messaggi di posta elettronica selezionando un'intera query ed escludendo manualmente determinati messaggi di posta elettronica dalla query. A tale scopo, un amministratore può usare la **casella di** controllo Seleziona tutto e scorrere verso il basso per escludere manualmente i messaggi di posta elettronica. La query può contenere un massimo di 1.000 messaggi di posta elettronica. Il numero massimo di esclusioni è 100.

Dopo aver selezionato i messaggi di posta elettronica tramite Esplora minacce, è possibile avviare la correzione tramite un'azione diretta o l'accodamento dei messaggi di posta elettronica per un'azione:

- Approvazione diretta: quando azioni come lo spostamento nella posta in *arrivo,* lo spostamento nella posta *indesiderata,* lo spostamento agli elementi *eliminati,* l'eliminazione recisa o l'eliminazione definitiva vengono selezionati dal personale di sicurezza che dispone delle autorizzazioni appropriate e vengono seguiti i passaggi successivi per la correzione, il processo di correzione inizia a eseguire l'azione selezionata.  Un riquadro a comparsa temporaneo mostra la correzione in corso.

- Approvazione in due passaggi: un'azione di "aggiunta alla correzione" può essere eseguita dagli amministratori che non dispongono delle autorizzazioni appropriate o che devono attendere di eseguire l'azione. In questo caso, i messaggi di posta elettronica di destinazione vengono aggiunti a un contenitore di correzione. L'approvazione è necessaria prima dell'esecuzione della correzione.

**Le azioni automatizzate di analisi e** risposta vengono attivate da avvisi o dai team delle operazioni di sicurezza da Esplora minacce. Tali azioni possono includere azioni di correzione consigliate che devono essere approvate da un team delle operazioni di sicurezza. Queste azioni sono incluse **nella** scheda Azione nell'indagine automatizzata.

> [!div class="mx-imgBorder"]
> [![Posta con malware nella pagina "Zapped" che mostra l'ora di esecuzione di Zap.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Tutte le correzioni (approvazione diretta o approvazione in due passaggi) create in Esplora minacce e le azioni approvate provenienti da indagini automatizzate vengono visualizzate nel centro notifiche. Accedi a questi elementi tramite il riquadro di spostamento a sinistra in **Centro** \> **notifiche revisione.**

> [!div class="mx-imgBorder"]
> [![Centro notifiche con un elenco di minacce in base alla data e alla gravità.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Il centro notifiche mostra tutte le azioni correttive degli ultimi 30 giorni. Le azioni eseguite tramite Esplora minacce sono elencate in base al nome fornito dal team delle operazioni di sicurezza al momento della creazione della correzione. Le azioni intraprese tramite indagini automatizzate hanno titoli che iniziano con l'avviso correlato che ha attivato l'indagine, ad esempio "Cluster di posta elettronica Zap... ."

Aprire qualsiasi elemento di correzione per visualizzarne i dettagli, tra cui il nome, la data di creazione, la descrizione, la gravità della minaccia e lo stato. Vengono inoltre illustrate le due schede seguenti.

- **Scheda Invio** posta: visualizza il numero di messaggi di posta elettronica inviati tramite Esplora minacce o indagini automatizzate da correggere. Questi messaggi di posta elettronica possono essere utilizzabili o non utilizzabili.

  > [!div class="mx-imgBorder"]
  > [![Centro notifiche con minacce utilizzabili e non utilizzabili.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Utilizzabile:** i messaggi di posta elettronica nelle seguenti posizioni della cassetta postale cloud possono essere agiti e spostati:
    - Posta in arrivo
    - Posta indesiderata
    - Cartella eliminata
    - Cartella eliminata in modo resciso

      > [!NOTE]
      > Attualmente, solo un utente con accesso alla cassetta postale può recuperare gli elementi da una cartella eliminata in modo reverso.

  - **Non utilizzabile:** i messaggi di posta elettronica nelle posizioni seguenti non possono essere agiti o spostati nelle azioni correttive:
    - Quarantena
    - Cartella eliminata definitivamente
    - Locale/esterno
    - Non riuscito/eliminato

  I messaggi sospetti sono classificati come corretti o non corretti. Nella maggior parte dei casi, i messaggi corretti e non corretti vengono combinati in modo da essere uguali al numero totale di messaggi inviati. Ma in rari casi potrebbe non essere vero. Ciò può verificarsi a causa di ritardi, timeout o messaggi scaduti del sistema. I messaggi scadono in base al periodo di conservazione di Esplora minacce per l'organizzazione.

  A meno che non vengano corretti i vecchi messaggi dopo il periodo di conservazione di Esplora minacce dell'organizzazione, è consigliabile riprovare a correggere gli elementi se vengono visualizzati numeri incoerenze. Per i ritardi del sistema, gli aggiornamenti delle correzioni vengono in genere aggiornati entro poche ore.

  Se il periodo di conservazione dell'organizzazione per la posta elettronica in Esplora minacce è di 30 giorni e si stanno corretti i messaggi di posta elettronica che tornano indietro di 29-30 giorni, il conteggio degli invii di posta elettronica potrebbe non essere sempre sommato. I messaggi di posta elettronica potrebbero aver già iniziato a uscire dal periodo di conservazione.

  Se le correzioni sono bloccate nello stato "In corso" per un po', è probabile che sia dovuto a ritardi del sistema. La correzione potrebbe richiedere fino a alcune ore. You might see variations in mail submission counts, as some of the emails may not have been included the query at the start of remediation due to system delays. È buona idea riprovare a correggere i problemi in questi casi.

  > [!NOTE]
  > Per ottenere risultati ottimali, è consigliabile eseguire la correzione in batch di un massimo di 50.000.

  Durante la correzione vengono utilizzati solo i messaggi di posta elettronica corretti. I messaggi di posta elettronica non correttibili non possono essere corretti dal sistema di posta elettronica di Office 365, poiché non sono archiviati nelle cassette postali cloud.

  Gli amministratori possono eseguire azioni sui messaggi di posta elettronica in quarantena, se necessario, ma tali messaggi scadranno dalla quarantena se non vengono eliminati manualmente. I messaggi di posta elettronica messi in quarantena a causa di contenuti dannosi non sono accessibili dagli utenti, quindi il personale di sicurezza non deve eseguire alcuna azione per eliminare le minacce in quarantena. Se i messaggi di posta elettronica sono locali o esterni, l'utente può essere contattato per risolvere il messaggio di posta elettronica sospetto. Oppure gli amministratori possono usare strumenti di sicurezza/server di posta elettronica separati per la rimozione. Questi messaggi di posta elettronica possono essere identificati applicando il percorso di recapito *= filtro* esterno locale in Esplora minacce. Per la posta elettronica non riuscita o eliminata o la posta elettronica non accessibile dagli utenti, non ci sarà alcun messaggio di posta elettronica da mitigare, poiché questi messaggi non raggiungono la cassetta postale.

  L'immagine seguente mostra l'aspetto di un invio nel centro notifiche. Una correzione può contenere più invii. Se più azioni vengono approvate tramite un'analisi automatizzata, ogni azione del cluster di posta elettronica o di posta elettronica viene visualizzata nella stessa correzione di un invio diverso.

  > [!div class="mx-imgBorder"]
  > [![Riquadro a comparsa del cluster di posta elettronica ZAP.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Selezionare un elemento di invio della posta per visualizzare i dettagli di tale correzione, ad esempio la query (quando la correzione viene attivata tramite indagini automatizzate o Esplora minacce tramite la selezione di una query) e l'ora di inizio e fine della correzione. Viene inoltre visualizzato un elenco dei messaggi inviati per la correzione. Quando i messaggi vengono spostati al di fuori del periodo di conservazione di Esplora minacce, i messaggi scompaiono da questo elenco. L'elenco mostra anche i singoli messaggi che sono corretti.

- **Log azioni:** questa scheda mostra i messaggi corretti, tra cui la data approvata, l'amministratore che ha approvato l'azione, l'azione, lo stato e i conteggi.

  Lo stato può essere:

  - **Avviato:** viene attivata la correzione.
  - **In coda:** la correzione viene accodata per la mitigazione dei messaggi di posta elettronica.
  - **In corso:** è in corso la mitigazione.
  - **Completato:** mitigazione di tutti i messaggi di posta elettronica corretti o completati correttamente o con alcuni errori.
  - **Failed:** nessuna correzione riuscita.

  Poiché è possibile intervenire solo sui messaggi di posta elettronica corretti, la pulizia di ogni messaggio di posta elettronica viene visualizzata come completata o non riuscita. Dai messaggi di posta elettronica correttivi totali, vengono segnalate le mitigazioni riuscite e non riuscite.

  - **Operazione** riuscita: è stata eseguita l'azione desiderata per correggere i messaggi di posta elettronica. Ad esempio: un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo che l'amministratore esempli l'azione di eliminazione recisa dei messaggi di posta elettronica. Se un messaggio di posta elettronica correttiva non viene trovato nella cartella originale dopo l'esecuzione dell'azione, lo stato verrà visualizzato come corretto.

  - **Errore:** l'azione desiderata per correggere i messaggi di posta elettronica non è riuscita. Ad esempio: un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo che l'amministratore esempli l'azione di eliminazione recisa dei messaggi di posta elettronica. Se nella cassetta postale viene ancora trovato un messaggio di posta elettronica correttiva dopo l'azione, lo stato verrà visualizzato come non riuscito.

  Selezionare un elemento nel registro azioni per visualizzare i dettagli della correzione. Se i dettagli sono "riuscito" o "non trovato nella cassetta postale", l'elemento è già stato rimosso dalla cassetta postale. A volte si verifica un errore sistemico durante la correzione. In questi casi, è buona idea ritentare la correzione.

  In caso di correzione di batch di grandi dimensioni, è anche possibile esportare i messaggi inviati per la correzione tramite l'invio di posta e i messaggi che sono stati corretti tramite i registri azioni. Il limite di esportazione viene aumentato a 100.000 record.

  La correzione è uno strumento potente per ridurre le minacce e risolvere i messaggi di posta elettronica sospetti. Consente di proteggere un'organizzazione.
