---
title: Correzione di messaggi di posta elettronica dannosi recapitati in Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: O365-seccomp
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Correzione delle minacce
appliesto:
- Microsoft 365 Defender
ms.openlocfilehash: 67b27102ff9319e334b5ff1e006fe49f14d3f1ed
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620576"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Rimediare la posta elettronica dannosa recapitata in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La correzione comporta l'esecuzione di un'azione prescritta nei confronti di una minaccia. I messaggi di posta elettronica dannosi inviati all'organizzazione possono essere rimossi dal sistema, tramite lo zapping automatico zero-hour (ZAP) o dai team di sicurezza tramite azioni correttive come *Sposta in posta in arrivo*, *Sposta su posta indesiderata*, *Sposta su elementi eliminati*, Elimina o Elimina *temporaneamente* *.* Microsoft Defender per Office 365 P2/E5 consente ai team di sicurezza di correggere le minacce nelle funzionalità di posta elettronica e collaborazione tramite l'analisi manuale e automatizzata.

> [!NOTE]
> Per correggere il messaggio di posta elettronica dannoso, i team di sicurezza devono essere assegnati al ruolo di *ricerca ed eliminazione* . L'assegnazione di ruolo viene fatta tramite le autorizzazioni nel centro sicurezza e conformità.

## <a name="what-you-need-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

Gli amministratori possono intraprendere le azioni necessarie per i messaggi di posta elettronica, ma per ottenere queste operazioni approvate, è necessario che il ruolo di *ricerca e Purge* venga assegnato tramite le autorizzazioni del **Centro sicurezza & conformità** \> . Senza il ruolo "Search and Purge" aggiunto a uno dei gruppi di ruoli, non saranno in grado di eseguire l'azione.

## <a name="manual-and-automated-remediation"></a>Correzione automatica e manuale

La *caccia manuale* si verifica quando i team di sicurezza identificano le minacce manualmente utilizzando le funzionalità di ricerca e filtro in Esplora minacce. La correzione dei messaggi di posta elettronica manuale può essere attivata tramite qualsiasi visualizzazione di posta elettronica (*malware*, *phishing* o *tutti i messaggi di posta elettronica*) dopo aver identificato un insieme di messaggi di posta elettronica che devono essere corretti.

> [!div class="mx-imgBorder"]
> [![Caccia manuale in Office 365 Threat Explorer per data.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

I team di sicurezza possono utilizzare la gestione delle minacce per selezionare i messaggi di posta elettronica in diversi modi:

- Scegliere i messaggi di posta elettronica manualmente: utilizzare filtri in diverse visualizzazioni. Selezionare fino a 100 messaggi di posta elettronica per la correzione.

- Selezione query: selezionare un'intera query utilizzando il pulsante **Seleziona tutto** in alto. La stessa query viene visualizzata anche nei dettagli sull'invio di posta elettronica del centro informazioni.

- Selezione di query con esclusione: a volte i team delle operazioni di sicurezza possono decidere di correggere i messaggi di posta elettronica selezionando un'intera query e escludendo manualmente alcuni messaggi di posta elettronica dalla query. A tale scopo, un amministratore può utilizzare la casella di controllo **Seleziona tutto** e scorrere verso il basso per escludere manualmente i messaggi di posta elettronica. La query può contenere un massimo di 1.000 messaggi di posta elettronica. Il numero massimo di esclusioni è 100.

Dopo aver selezionato i messaggi di posta elettronica tramite Threat Explorer, è possibile avviare la correzione mediante l'esecuzione di un'azione diretta o accodando messaggi di posta elettronica per un'azione:

- Approvazione diretta: quando si selezionano azioni come *Sposta in posta in arrivo*, sposta su posta *indesiderata*, *Sposta su elementi eliminati*, *eliminazione* temporanea o *eliminazione* definitiva da personale della sicurezza che dispone delle autorizzazioni appropriate e che vengono seguiti i passaggi successivi per la correzione, il processo di correzione inizia ad eseguire l'azione selezionata. Un riquadro a comparsa temporaneo Visualizza la correzione in corso.

- Approvazione in due passaggi: un'azione "Aggiungi a correzione" può essere eseguita dagli amministratori che non dispongono delle autorizzazioni appropriate o che devono attendere l'esecuzione dell'azione. In questo caso, i messaggi di posta elettronica mirati vengono aggiunti a un contenitore di correzione. L'approvazione è necessaria prima dell'esecuzione della correzione.

L' **analisi automatizzata e** le azioni di risposta vengono attivate dagli avvisi o dai team di operazioni di sicurezza di Threat Explorer. Possono includere azioni di correzione che devono essere approvate da un team di operazioni di sicurezza. Queste azioni sono incluse nella scheda **azione** nell'indagine automatizzata.

> [!div class="mx-imgBorder"]
> [![Posta elettronica con malware nella pagina "zapped" che mostra il tempo di esecuzione dello zap.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Nell'Action Center vengono visualizzate tutte le correzioni, ovvero l'approvazione diretta o in due passaggi, che sono state create in Esplora minacce e le azioni approvate provenienti da indagini automatizzate. Accedere a questi tramite il riquadro di spostamento a sinistra in **Review** \> **Action Center**.

> [!div class="mx-imgBorder"]
> [![Centro azioni con un elenco di minacce per data e gravità.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Centro azioni Visualizza tutte le azioni di correzione negli ultimi 30 giorni. Le azioni eseguite tramite Esplora minacce sono elencate in base al nome che il team delle operazioni di sicurezza ha fornito quando è stata creata la correzione. Le azioni intraprese tramite indagini automatizzate dispongono di titoli che iniziano con l'avviso correlato che ha attivato l'indagine, ad esempio "zap email cluster...".

Aprire qualsiasi elemento di correzione per visualizzarne i dettagli, inclusi il nome, la data di creazione, la descrizione, la gravità delle minacce e lo stato. Vengono inoltre visualizzate le due schede seguenti.

- Scheda **invio posta** : Visualizza il numero di messaggi di posta elettronica inviati tramite Esplora minacce o indagini automatizzate da correggere. Questi messaggi di posta elettronica possono essere fattibili o non utilizzabili.

  > [!div class="mx-imgBorder"]
  > [![Il centro azioni con minacce actionable e not actionable.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Azione**: i messaggi di posta elettronica nei seguenti percorsi delle cassette postali cloud possono essere attivati e spostati:
    - Posta in arrivo
    - Posta indesiderata
    - Cartella eliminata
    - Cartella eliminata temporaneamente

      > [!NOTE]
      > Attualmente, solo un utente con accesso alla cassetta postale può recuperare gli elementi da una cartella eliminata temporaneamente.

  - **Non** utilizzabile: i messaggi di posta elettronica nei seguenti percorsi non possono essere attivati o spostati in azioni di correzione:
    - Quarantena
    - Cartella eliminata definitivamente
    - Locali/esterni
    - Esito negativo/ritirato

  I messaggi sospetti sono classificati come rimediable o nonremediable. Nella maggior parte dei casi, i messaggi remediable e nonremediable Combine sono uguali al totale dei messaggi inviati. In rari casi, tuttavia, potrebbe non essere vero. Ciò può verificarsi a causa di ritardi di sistema, timeout o messaggi scaduti. I messaggi scadono in base al periodo di conservazione di Threat Explorer per l'organizzazione.

  A meno che non si stiano ripristinando i messaggi obsoleti dopo il periodo di conservazione dell'organizzazione, è consigliabile riprovare gli elementi se vengono visualizzate incoerenze dei numeri. Per i ritardi di sistema, gli aggiornamenti correttivi vengono in genere aggiornati in poche ore.

  Se il periodo di conservazione dell'organizzazione per la posta elettronica in Threat Explorer è di 30 giorni e si stanno ripristinando i messaggi di posta elettronica che risalgono a 29-30 giorni, il numero di messaggi di invio potrebbe non essere sempre sommato. I messaggi di posta elettronica potrebbero essere già stati spostati fuori dal periodo di conservazione.

  Se le correzioni vengono bloccate nello stato "in corso" per un po' di tempo, è probabile che si verifichino ritardi del sistema. La correzione potrebbe richiedere fino a poche ore. È possibile che vengano visualizzate le variazioni nei conteggi dell'invio di posta elettronica, in quanto alcuni messaggi di posta elettronica potrebbero non essere stati inclusi nella query all'inizio della correzione a causa di ritardi del sistema. È consigliabile riprovare la correzione in tali casi.

  > [!NOTE]
  > Per ottenere risultati ottimali, è necessario eseguire la correzione in batch di 50.000 o meno.

  Durante la correzione vengono attivati solo i messaggi di posta elettronica rimediabili. I messaggi di posta elettronica di Nonremediable non possono essere corretti dal sistema di e-mail di Office 365, in quanto non vengono archiviati nelle cassette postali cloud.

  Gli amministratori possono eseguire azioni sui messaggi di posta elettronica in quarantena, se necessario, ma tali messaggi di posta elettronica scadranno fuori dalla quarantena se non vengono eliminati manualmente. I messaggi di posta elettronica in quarantena a causa di contenuti dannosi non sono accessibili dagli utenti, quindi il personale della sicurezza non deve intraprendere alcuna azione per eliminare le minacce in quarantena. Se i messaggi di posta elettronica sono in locale o esterno, l'utente può essere contattato per risolvere il messaggio di posta elettronica sospetto. Gli amministratori possono utilizzare i server di posta elettronica o gli strumenti di sicurezza separati per la rimozione. Questi messaggi di posta elettronica possono essere identificati applicando il filtro esterno *posizione di recapito = on-Prem* in Esplora minacce. Per i messaggi di posta elettronica non riusciti o eliminati o non sono accessibili dagli utenti, non vi sarà alcun messaggio di posta elettronica da attenuare, poiché questi messaggi non raggiungono la cassetta postale.

  Nell'immagine seguente viene illustrato il modo in cui l'invio viene visualizzato in Action Center. Una correzione può contenere più invii. Se più azioni vengono approvate tramite un'indagine automatizzata, ogni azione del cluster di posta elettronica o di posta elettronica viene visualizzata nella stessa correzione di un altro invio.

  > [!div class="mx-imgBorder"]
  > [![Riquadro a comparsa di cluster di posta elettronica ZAP.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Selezionare un elemento per l'invio della posta per visualizzare i dettagli di tale correzione, ad esempio la query (quando la correzione viene attivata tramite indagini automatizzate o Esplora minacce tramite la selezione di una query) e gli orari di inizio e fine della correzione. Viene inoltre visualizzato un elenco di messaggi inviati per la correzione. Quando i messaggi vengono spostati dal periodo di conservazione di Threat Explorer, i messaggi scompaiono da questo elenco. L'elenco Visualizza anche i singoli messaggi che sono risolvibili.

- **Registri azione**: questa scheda Visualizza i messaggi corretti, inclusa la data approvata, l'amministratore che ha approvato l'azione, l'azione, lo stato e i conteggi.

  Lo stato può essere:

  - **Avviato**: viene attivata la correzione.
  - **Accodamento**: la correzione è in coda per la riduzione dei messaggi di posta elettronica.
  - **In corso**: attenuazione in corso.
  - **Completata**: la mitigazione su tutti i messaggi di posta elettronica rimediable è stata completata correttamente o con alcuni errori.
  - **Errore**: nessuna correzione ha avuto esito positivo.

  Poiché solo i messaggi di posta elettronica rimediabili possono essere attivati, la pulizia di ogni e-mail viene visualizzata con esito positivo o negativo. Dal totale dei messaggi di posta elettronica rimediabili, le attenuazioni riuscite e non riuscite sono segnalate.

  - **Success**: l'azione desiderata sui messaggi di posta elettronica rimediabili è stata compiuta. Ad esempio, un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, quindi l'amministratore esegue l'azione di eliminazione dei messaggi di posta elettronica soft. Se un messaggio di posta elettronica risolvibile non viene trovato nella cartella originale dopo l'esecuzione dell'azione, lo stato verrà visualizzato come riuscito.

  - **Errore**: Impossibile eseguire l'azione desiderata sui messaggi di posta elettronica rimediable. Ad esempio, un amministratore vuole rimuovere i messaggi di posta elettronica dalle cassette postali, quindi l'amministratore esegue l'azione di eliminazione dei messaggi di posta elettronica soft. Se un messaggio di posta elettronica risolvibile viene ancora trovato nella cassetta postale dopo l'operazione, lo stato verrà visualizzato come non riuscito.

  Selezionare un elemento nel log azione per visualizzare i dettagli di correzione. Se i dettagli dicono "riuscito" o "non trovato nella cassetta postale", tale elemento è già stato rimosso dalla cassetta postale. A volte si verifica un errore sistemico durante la correzione. In questi casi, è consigliabile riprovare la correzione.

  In caso di correzione di batch di grandi dimensioni, è anche possibile esportare i messaggi inviati per la correzione tramite invio e messaggi di posta elettronica che sono stati risolti tramite i log di azione. Il limite di esportazione viene aumentato a 100K Records.

  La correzione è uno strumento potente per attenuare le minacce e indirizzare i messaggi di posta elettronica sospetti. Aiuta a mantenere sicura un'organizzazione.
