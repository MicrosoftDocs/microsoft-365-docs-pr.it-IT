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
ms.openlocfilehash: 202ebc8b79368c8d41fd3727b67359ddcb8a08fa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206613"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Correggere i messaggi di posta elettronica dannosi recapitati in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)

La correzione significa eseguire un'azione prescritta contro una minaccia. I messaggi di posta elettronica dannosi inviati all'organizzazione possono essere puliti dal sistema, tramite l'eliminazione automatica a zero ore (ZAP) o dai team di sicurezza tramite azioni di correzione come lo spostamento nella posta in *arrivo,* lo spostamento nella posta *indesiderata,* lo spostamento agli elementi *eliminati,* l'eliminazione reversa *o* l'eliminazione *permanente.* Microsoft Defender per Office 365 P2/E5 consente ai team di sicurezza di correggere le minacce nelle funzionalità di posta elettronica e collaborazione tramite indagini manuali e automatizzate.

> [!NOTE]
> Per correggere la posta elettronica dannosa, i team di sicurezza necessitano del ruolo di ricerca *ed eliminazione* assegnato. L'assegnazione di ruolo viene eseguita tramite le autorizzazioni nel Centro sicurezza e conformità.

## <a name="what-you-need-to-know-before-you-begin"></a>Informazioni necessarie prima di iniziare

Gli amministratori possono eseguire le azioni necessarie nei messaggi di posta  elettronica, ma per ottenere l'approvazione di tali azioni, è necessario che gli sia assegnato il ruolo di ricerca ed eliminazione tramite Autorizzazioni del Centro **sicurezza &** \> **conformità**. Senza il ruolo "ricerca ed eliminazione" aggiunto a uno dei gruppi di ruoli, non saranno in grado di eseguire l'azione.

## <a name="manual-and-automated-remediation"></a>Correzione manuale e automatica

*La ricerca manuale* si verifica quando i team di sicurezza identificano manualmente le minacce utilizzando le funzionalità di ricerca e filtro in Esplora minacce. La correzione manuale della posta elettronica può essere attivata tramite qualsiasi visualizzazione della posta elettronica (*Malware,* *Phish* o *Tutti* i messaggi di posta elettronica ) dopo aver identificato un set di messaggi di posta elettronica da correggere.

> [!div class="mx-imgBorder"]
> [![Ricerca manuale in Office 365 Threat Explorer per data.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

I team di sicurezza possono usare Esplora minacce per selezionare i messaggi di posta elettronica in diversi modi:

- Scegliere manualmente i messaggi di posta elettronica: usare i filtri in diverse visualizzazioni. Selezionare fino a 100 messaggi di posta elettronica da correggere.

- Selezione query: selezionare un'intera query utilizzando il pulsante **seleziona tutto in** alto. La stessa query viene visualizzata anche nei dettagli di invio della posta elettronica del centro notifiche.

- Selezione delle query con esclusione: a volte i team delle operazioni di sicurezza potrebbero voler correggere i messaggi di posta elettronica selezionando un'intera query ed escludendo manualmente alcuni messaggi di posta elettronica dalla query. A tale scopo, un amministratore può usare la **casella di** controllo Seleziona tutto e scorrere verso il basso per escludere manualmente i messaggi di posta elettronica. La query può contenere un massimo di 1.000 messaggi di posta elettronica. Il numero massimo di esclusioni è 100.

Dopo aver selezionato i messaggi di posta elettronica tramite Threat Explorer, puoi avviare la correzione mediante un'azione diretta o l'accodamento dei messaggi di posta elettronica per un'azione:

- Approvazione diretta: quando azioni come lo spostamento nella posta in *arrivo,* lo spostamento nella posta *indesiderata,* lo spostamento agli elementi *eliminati,* l'eliminazione reversibili o l'eliminazione definitiva vengono selezionati dal personale di sicurezza che dispone delle autorizzazioni appropriate e vengono seguite le operazioni successive di correzione, il processo di correzione inizia a eseguire l'azione selezionata.  Un riquadro a comparsa temporaneo mostra la correzione in corso.

- Approvazione in due passaggi: un'azione di "aggiunta alla correzione" può essere eseguita dagli amministratori che non dispongono delle autorizzazioni appropriate o che devono attendere l'esecuzione dell'azione. In questo caso, i messaggi di posta elettronica di destinazione vengono aggiunti a un contenitore di correzione. L'approvazione è necessaria prima dell'esecuzione della correzione.

**Le azioni di indagine e risposta** automatizzate vengono attivate dagli avvisi o dai team delle operazioni di sicurezza di Threat Explorer. Possono includere azioni di correzione consigliate che devono essere approvate da un team delle operazioni di sicurezza. Queste azioni sono incluse nella scheda **Azione** dell'indagine automatizzata.

> [!div class="mx-imgBorder"]
> [![Mail with malware in "Zapped" page showing time of Zap execution.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Tutte le correzioni (approvazione diretta o approvazione in due passaggi) create in Esplora minacce e le azioni approvate provenienti da indagini automatizzate vengono visualizzate nel Centro notifiche. Accedi a questi elementi tramite il riquadro di spostamento sinistro in **Centro** \> **notifiche revisione.**

> [!div class="mx-imgBorder"]
> [![Centro notifiche con un elenco di minacce per data e gravità.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Il Centro notifiche mostra tutte le azioni di correzione degli ultimi 30 giorni. Le azioni eseguite tramite Esplora minacce sono elencate in base al nome fornito dal team delle operazioni di sicurezza al momento della creazione della correzione. Le azioni intraprese tramite indagini automatizzate hanno titoli che iniziano con l'avviso correlato che ha attivato l'indagine, ad esempio "Zap email cluster... ."

Aprire qualsiasi elemento di correzione per visualizzarne i dettagli, inclusi il nome, la data di creazione, la descrizione, la gravità della minaccia e lo stato. Vengono inoltre mostrate le due schede seguenti.

- **Scheda Invio** posta: visualizza il numero di messaggi di posta elettronica inviati tramite Threat Explorer o indagini automatizzate da correggere. Questi messaggi di posta elettronica possono essere utilizzabili o non utilizzabili.

  > [!div class="mx-imgBorder"]
  > [![Centro notifiche con minacce utilizzabili e non utilizzabili.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Utilizzabile:** i messaggi di posta elettronica nelle seguenti posizioni delle cassette postali cloud possono essere agiti e spostati:
    - Posta in arrivo
    - Posta indesiderata
    - Cartella eliminata
    - Cartella eliminata in modo recidiva

      > [!NOTE]
      > Attualmente, solo un utente con accesso alla cassetta postale può recuperare gli elementi da una cartella eliminata in modo reverso.

  - **Non utilizzabile:** i messaggi di posta elettronica nelle posizioni seguenti non possono essere agiti o spostati nelle azioni di correzione:
    - Quarantena
    - Cartella eliminata definitivamente
    - Locale/esterno
    - Non riuscito/eliminato

  I messaggi sospetti vengono classificati come corretti o non corretti. Nella maggior parte dei casi, i messaggi correttivi e non corretti sono uguali al totale dei messaggi inviati. Ma in rari casi questo potrebbe non essere vero. Ciò può verificarsi a causa di ritardi del sistema, timeout o messaggi scaduti. I messaggi scadono in base al periodo di conservazione di Esplora minacce per l'organizzazione.

  A meno che non si remediating old messages after your organization's Threat Explorer retention period, it's advisable to retry remediating items if you see number inconsistencies. Per i ritardi del sistema, gli aggiornamenti di correzione vengono in genere aggiornati entro poche ore.

  Se il periodo di conservazione dell'organizzazione per la posta elettronica in Threat Explorer è di 30 giorni e si stanno correggere i messaggi di posta elettronica che tornano indietro di 29-30 giorni, il conteggio degli invii di posta elettronica potrebbe non sempre sommarsi. I messaggi di posta elettronica potrebbero aver già iniziato a uscire dal periodo di conservazione.

  Se le correzioni sono bloccate nello stato "In corso" per un po', è probabile che siano dovute a ritardi del sistema. La correzione potrebbe richiedere fino a poche ore. Potrebbero essere presenti varianti nel conteggio degli invii di posta elettronica, perché alcuni dei messaggi di posta elettronica potrebbero non essere stati inclusi nella query all'inizio della correzione a causa di ritardi del sistema. È buona idea ripetere la correzione in questi casi.

  > [!NOTE]
  > Per ottenere risultati ottimali, è consigliabile eseguire la correzione in batch di 50.000 o meno.

  Durante la correzione vengono agiti solo i messaggi di posta elettronica corretti. I messaggi di posta elettronica non correttibili non possono essere corretti dal sistema di posta elettronica di Office 365, poiché non vengono archiviati nelle cassette postali cloud.

  Se necessario, gli amministratori possono eseguire azioni sui messaggi di posta elettronica in quarantena, ma tali messaggi scadranno dalla quarantena se non vengono eliminati manualmente. I messaggi di posta elettronica messi in quarantena a causa di contenuti dannosi non sono accessibili dagli utenti, quindi il personale di sicurezza non deve eseguire alcuna azione per eliminare le minacce in quarantena. Se i messaggi di posta elettronica sono locali o esterni, l'utente può essere contattato per risolvere il messaggio di posta elettronica sospetto. Oppure gli amministratori possono usare strumenti di sicurezza/server di posta elettronica separati per la rimozione. Questi messaggi di posta elettronica possono essere identificati applicando il percorso di recapito *= filtro esterno* locale in Threat Explorer. Per i messaggi di posta elettronica non riusciti o eliminati o non accessibili dagli utenti, non ci saranno messaggi di posta elettronica da mitigare, dal momento che questi messaggi non raggiungono la cassetta postale.

  L'immagine seguente mostra l'aspetto di un invio nel Centro notifiche. Una correzione può contenere più invii. Se più azioni vengono approvate tramite un'indagine automatizzata, ogni azione del cluster di posta elettronica o di posta elettronica viene visualizzata nella stessa correzione di un invio diverso.

  > [!div class="mx-imgBorder"]
  > [![Riquadro a comparsa del cluster di posta elettronica ZAP.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Selezionare un elemento di invio della posta per visualizzare i dettagli di tale correzione, ad esempio la query (quando la correzione viene attivata tramite indagini automatizzate o Esplora minacce tramite la selezione di una query) e l'ora di inizio e fine della correzione. Viene inoltre visualizzato un elenco dei messaggi inviati per la correzione. Quando i messaggi vengono spostati al di fuori del periodo di conservazione di Esplora minacce, i messaggi scompaiono da questo elenco. L'elenco mostra anche i singoli messaggi corretti.

- **Log azioni:** questa scheda mostra i messaggi corretti, inclusa la data approvata, l'amministratore che ha approvato l'azione, l'azione, lo stato e i conteggi.

  Lo stato può essere:

  - **Avviato:** viene attivata la correzione.
  - **In coda:** la correzione viene accodata per la mitigazione dei messaggi di posta elettronica.
  - **In corso:** mitigazione in corso.
  - **Completato:** mitigazione di tutti i messaggi di posta elettronica correttibili completati correttamente o con alcuni errori.
  - **Operazione** non riuscita: nessuna correzione è riuscita.

  Poiché è possibile intervenire solo sui messaggi di posta elettronica corretti, la pulizia di ogni messaggio di posta elettronica viene visualizzata come completata o non riuscita. Dai messaggi di posta elettronica correttivi totali, vengono segnalate le mitigazioni riuscite e non riuscite.

  - **Operazione** riuscita: l'azione desiderata per correggere i messaggi di posta elettronica è stata eseguita. Ad esempio: un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo che l'amministratore esempli l'azione di eliminazione recidiva dei messaggi di posta elettronica. Se non viene trovato un messaggio di posta elettronica di correzione nella cartella originale dopo l'esecuzione dell'azione, lo stato verrà visualizzato come corretto.

  - **Errore:** l'azione desiderata per la correzione dei messaggi di posta elettronica non è riuscita. Ad esempio: un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, in modo che l'amministratore esempli l'azione di eliminazione recidiva dei messaggi di posta elettronica. Se nella cassetta postale viene ancora trovato un messaggio di posta elettronica di correzione dopo l'azione, lo stato verrà visualizzato come non riuscito.
  
  - **Già nella destinazione**: L'azione desiderata è già stata eseguita sul messaggio di posta elettronica OPPURE il messaggio di posta elettronica esiste già nel percorso di destinazione. Ad esempio: un messaggio di posta elettronica è stato eliminato in modo recidivo dall'amministratore tramite Explorer il primo giorno. Quindi messaggi di posta elettronica simili vengono visualizzati il giorno 2, che vengono nuovamente eliminati in modo recidiva dall'amministratore. Durante la selezione di questi messaggi di posta elettronica, l'amministratore finisce per raccogliere alcuni messaggi di posta elettronica dal primo giorno che sono già eliminati in modo recidiva. Ora questi messaggi di posta elettronica non verranno più visualizzati come "già in destinazione", poiché non è stata eseguita alcuna azione su di essi come esistevano nella posizione di destinazione.

  Selezionare qualsiasi elemento nel registro azioni per visualizzare i dettagli di correzione. Se i dettagli dicono "operazione riuscita" o "non trovata nella cassetta postale", l'elemento è già stato rimosso dalla cassetta postale. A volte si verifica un errore di sistema durante la correzione. In questi casi, è buona idea ritentare la correzione.

  In caso di correzione di batch di grandi dimensioni, è anche possibile esportare i messaggi inviati per la correzione tramite Invio posta e i messaggi corretti tramite i log azioni. Il limite di esportazione viene aumentato a 100.000 record.

Il team di sicurezza può richiedere fino a 50 correzioni manuali simultanee; Tuttavia, non è impostato alcun limite per le azioni di indagine e risposta automatizzate.

  La correzione è uno strumento potente per ridurre le minacce e affrontare i messaggi di posta elettronica sospetti. Consente di proteggere un'organizzazione.
