---
title: Pagina dell'entità di posta elettronica di Microsoft Defender for Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: I clienti di Microsoft Defender per Office 365 E5 e P1 e P2 ora possono ottenere una visualizzazione a 360 gradi di ogni messaggio di posta elettronica con la pagina dell'entità di posta elettronica.
ms.openlocfilehash: aa5d7effb66c4805f6983fa1afac19255bc996e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539096"
---
# <a name="the-email-entity-page"></a>Pagina Entità posta elettronica

**Contenuto dell'articolo:**
- [Raggiungere la pagina dell'entità di posta elettronica](#reach-the-email-entity-page)
- [Leggere la pagina dell'entità di posta elettronica](#read-the-email-entity-page)
- [Usare le schede della pagina dell'entità di posta elettronica](#use-email-entity-page-tabs)
- [Novità della pagina dell'entità di posta elettronica](#new-to-the-email-entity-page)

Gli amministratori di Microsoft Defender per Office 365 (o MDO) E5 e MDO P1 e P2 hanno una visualizzazione a 360 gradi della posta elettronica usando la pagina Entità di posta **elettronica**. Questa pagina di posta elettronica di accesso è stata creata per migliorare le informazioni recapitate nel riquadro a comparsa ["Dettagli posta elettronica" di Threat Explorer.](threat-explorer-views.md)

## <a name="reach-the-email-entity-page"></a>Raggiungere la pagina dell'entità di posta elettronica

Il & Centro sicurezza e conformità (protection.office.com) o il nuovo Centro sicurezza Microsoft 365 (security.microsoft.com) consentono di visualizzare e usare la pagina dell'entità di posta elettronica.

|Centro|URL|Navigazione|
|---|---|---|
|Sicurezza e conformità |protection.office.com|Esplora gestione \> delle minacce|
|Centro sicurezza Microsoft 365 |security.microsoft.com|Esplora & posta \> elettronica|

In Esplora minacce seleziona l'oggetto di un messaggio di posta elettronica che stai analizzando. Nella parte superiore del riquadro a comparsa della posta elettronica verrà visualizzata una barra d'oro. Questo invito alla nuova pagina, legge "Prova la nostra nuova pagina dell'entità di posta elettronica con dati arricchiti...". Selezionare questa opzione per visualizzare la nuova pagina.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Verrà visualizzato un banner d'oro con le parole *Prova la nuova pagina dell'entità di posta elettronica con dati arricchiti* per passare alla nuova esperienza.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Questo grafico della pagina dell'entità di posta elettronica si concentra sui titoli che verranno visualizzati. Nota L'intestazione del messaggio di posta elettronica viene visualizzata qui.":::

> [!NOTE]
> Le autorizzazioni necessarie per visualizzare e usare questa pagina sono le stesse di Esplora minacce. L'amministratore deve essere membro dell'amministratore globale o del lettore globale oppure amministratore della sicurezza o lettore di sicurezza.

## <a name="read-the-email-entity-page"></a>Leggere la pagina dell'entità di posta elettronica

La struttura è progettata per essere facile da leggere e navigare a colpo d'occhio. Varie schede nella parte superiore della pagina consentono di analizzare in modo più dettagliato. Ecco come funziona il layout:

1. I campi più obbligatori sono sul lato sinistro del riquadro a comparsa. Questi dettagli sono "appiccicosi", ovvero sono ancorati a sinistra, indipendentemente dalla scheda a cui si accede nel resto del riquadro a comparsa.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Elemento grafico della pagina dell'entità di posta elettronica con il lato sinistro evidenziato. Il titolo e i fatti relativi al recapito della posta sono qui.":::

2. Nell'angolo in alto a destra sono presenti le azioni che possono essere eseguite su un messaggio di posta elettronica. Tutte le azioni che possono essere eseguite tramite Esplora risorse saranno disponibili anche tramite la pagina dell'entità di posta elettronica.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Grafico della pagina dell'entità di posta elettronica con il lato *a destra* evidenziato, questa volta. Sono disponibili azioni come &quot;Anteprima e-mail&quot; e &quot;Vai in quarantena&quot;.":::

3. È possibile eseguire un'analisi più approfondita ordinando il resto della pagina. Controllare i dettagli di rilevamento della posta elettronica, lo stato di autenticazione della posta elettronica e l'intestazione. Quest'area deve essere cercata caso per caso, ma le informazioni in queste schede sono disponibili per qualsiasi messaggio di posta elettronica.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Il pannello principale di questa pagina include l'intestazione della posta elettronica e lo stato di autenticazione.":::

### <a name="use-email-entity-page-tabs"></a>Usare le schede della pagina dell'entità di posta elettronica

Le schede nella parte superiore della pagina dell'entità consentono di analizzare la posta elettronica in modo efficiente.

1. **Sequenza** temporale: la visualizzazione sequenza temporale per un messaggio di posta elettronica (in base alla sequenza temporale di Threat Explorer) mostra il recapito originale agli eventi di post-recapito che si verificano in un messaggio di posta elettronica. Per i messaggi di posta elettronica che non dispongono di azioni post-recapito, la visualizzazione mostra la riga di recapito originale nella visualizzazione sequenza temporale. Eventi come: Eliminazione automatica a zero ore (ZAP), Correzione, clic url, et cetera, da origini come: sistema, amministratore e utente, vengono visualizzati qui, nell'ordine in cui si sono verificati.
2. **Analisi**: l'analisi mostra i campi che consentono agli amministratori di analizzare in modo approfondito un messaggio di posta elettronica. Per i casi in cui gli amministratori devono comprendere meglio i dettagli di rilevamento, mittente/destinatario e autenticazione della posta elettronica, devono usare la scheda Analisi. I collegamenti per allegati e URL sono disponibili anche in questa pagina, in "Entità correlate". Sia gli allegati che le minacce identificate sono numerati qui e facendo clic si visualizzano direttamente le pagine Allegati e URL. Questa scheda ha anche un'opzione Visualizza intestazione per *visualizzare l'intestazione del messaggio di posta elettronica.* Gli amministratori possono confrontare qualsiasi dettaglio delle intestazioni di posta elettronica, affiancate alle informazioni nel pannello principale, per maggiore chiarezza.
3. **Allegati**: esamina gli allegati trovati nel messaggio di posta elettronica con altri dettagli trovati negli allegati. Il numero di allegati visualizzati è attualmente limitato a 10. Si noti che i dettagli di detonazione per gli allegati trovati dannosi sono mostrati anche qui.
4. **URL**: questa scheda elenca gli URL trovati nel messaggio di posta elettronica con altri dettagli sugli URL. Il numero di URL è limitato a 10 al momento, ma questi 10 hanno la priorità per mostrare prima *gli URL dannosi.* La definizione delle priorità consente di risparmiare tempo e lavoro. Anche gli URL che sono stati trovati dannosi e detonati verranno mostrati qui.
5. **Messaggi di posta elettronica simili:** in questa scheda sono elencati tutti i messaggi di posta elettronica simili alla combinazione id messaggio di rete *+ destinatario* specifico per questo messaggio di posta elettronica. La somiglianza si basa *solo sul corpo del messaggio.* Le determinazioni effettuate sui messaggi di posta per classificarli come "simili" non includono una considerazione degli *allegati.*

## <a name="new-to-the-email-entity-page"></a>Novità della pagina dell'entità di posta elettronica

Esistono nuove funzionalità disponibili con questa pagina dell'entità di posta elettronica. Ecco l'elenco.

### <a name="email-preview-for-cloud-mailboxes"></a>Anteprima della posta elettronica per le cassette postali cloud

Gli amministratori possono visualizzare in anteprima i messaggi di posta elettronica nelle cassette postali ***cloud,*** se i messaggi sono ancora presenti nel cloud. In caso di eliminazione recisa (da parte di un amministratore o di un utente) o ZAP (per la quarantena), i messaggi di posta elettronica non sono più presenti nella posizione cloud. In tal caso, gli amministratori non saranno in grado di visualizzare in anteprima i messaggi di posta elettronica specifici. I messaggi di posta elettronica che sono stati eliminati o in cui il recapito non è riuscito, non sono mai stati effettivamente resi nella cassetta postale. Di conseguenza, gli amministratori non saranno in grado di visualizzare in anteprima i messaggi di posta elettronica.

> [!WARNING]
> L'anteprima dei messaggi di posta elettronica richiede un ruolo speciale denominato ***Anteprima** _ da assegnare agli amministratori. È possibile aggiungere questo ruolo andando a _ *Autorizzazioni & ruoli** > **Ruoli** di collaborazione & posta elettronica in *security.microsoft.com* o **Autorizzazioni** in *protection.office.com*. Aggiungere il ***ruolo Anteprima*** a uno qualsiasi dei gruppi di ruoli o una copia di un gruppo di ruoli che consente agli amministratori dell'organizzazione di lavorare in Esplora minacce.

### <a name="detonation-details"></a>Dettagli detonazione

Questi dettagli sono specifici per gli url e gli allegati di posta elettronica.

Gli utenti potranno visualizzare dettagli di detonazione arricchiti per allegati o collegamenti ipertestuali dannosi noti trovati nelle proprie cassette postali, tra cui catena di detonazione, riepilogo detonazione, screenshot e dettagli sul comportamento osservato per aiutare i clienti a capire perché l'allegato o l'URL è stato ritenuto dannoso e detonato.

- *Catena di detonazione:* una detonazione di un singolo file o URL può attivare più detonazioni. La catena di detonazione tiene traccia del percorso delle detonazioni, incluso il file o l'URL dannoso originale che ha causato il verdetto, e tutti gli altri file o URL emersi dalla detonazione. Questi URL o file allegati potrebbero non essere direttamente presenti nel messaggio di posta elettronica, ma l'inclusione di tale analisi è importante per determinare perché il file o l'URL è stato trovato dannoso.
- *Riepilogo detonazione*: fornisce informazioni su:
  - Intervallo di tempo di detonazione.
  - Verdetto del file allegato o dell'URL.
  - Informazioni correlate (numero di file, URL, IP o domini), che sono altre entità esaminate durante la detonazione.
- *Schermata di detonazione:* mostra gli screenshot emersi durante il processo di detonazione.
- *Dettagli di detonazione*: questi sono i dettagli esatti del comportamento di ogni processo che ha avuto luogo durante la detonazione.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Screenshot of the detonation summary showing the chain, summary, detonation details, and screenshot under the heading *Deep Analysis*.":::

### <a name="other-innovations"></a>Altre innovazioni

*Tag*: si tratta di tag applicati agli utenti. Se l'utente è un destinatario, gli amministratori visualizzano un tag *destinatario.* Analogamente, se l'utente è un mittente, un tag *del mittente.* Verrà visualizzato nella parte sinistra della pagina delle entità di posta  elettronica (nella parte descritta come appiccicoso e quindi ancorata alla pagina).

*Posizione di recapito più recente:* la posizione di recapito più recente è la posizione in cui un messaggio di posta elettronica è atterrato dopo le azioni di sistema come ZAP o le azioni di amministratore come Sposta nella posta eliminata, terminare. La posizione di recapito più recente non è progettata per informare gli amministratori della posizione *corrente del* messaggio. Ad esempio, se un utente elimina un messaggio o lo sposta in archivio, il percorso di recapito non verrà aggiornato. Tuttavia, se è stata eseguita un'azione di sistema e la posizione è stata aggiornata (ad esempio, un ZAP che ha portato a un messaggio di posta elettronica in quarantena), il percorso di recapito più recente verrà aggiornato in Quarantena.

*Dettagli posta elettronica*: dettagli necessari per una conoscenza approfondita della posta elettronica disponibile nella *scheda* Analisi.

- *Exchange transport rules (ETRs or Mailflow rules):* queste regole vengono applicate a un messaggio a livello di trasporto e hanno la precedenza sui verdetti di phish e spam. Questi possono essere creati e modificati solo nell'interfaccia di amministrazione di Exchange, ma se un ETR si applica a un messaggio, il nome ETR e il GUID verranno visualizzati qui. Informazioni preziose a scopo di monitoraggio.

- *Sostituzioni* di sistema: si tratta di un mezzo per fare eccezioni al percorso di recapito destinato a un messaggio ignorando il percorso di recapito fornito dal sistema (in base alla tecnologia di rilevamento e minaccia).

- *Regola cassetta postale indesiderata:* la regola di posta indesiderata è nascosta la regola della posta in arrivo abilitata per impostazione predefinita in ogni cassetta postale.
  - Quando la regola di posta indesiderata è abilitata nella cassetta postale, Exchange Online Protection (EOP) è in grado di spostare i messaggi in Posta indesiderata in base ad alcuni criteri. Lo spostamento può essere basato sull'azione verdetto filtro posta indesiderata Sposta il messaggio nella cartella Posta indesiderata *o* nell'elenco Mittenti bloccati nella cassetta postale. La disabilitazione della regola di posta indesiderata impedisce il recapito dei messaggi nella cartella Posta indesiderata in base *all'elenco Mittenti attendibili* della cassetta postale.
  - Quando la regola  di posta indesiderata è disabilitata nella cassetta postale, EOP non può spostare i messaggi nella cartella Posta indesiderata in base all'azione verdetto filtro posta indesiderata Spostare il messaggio nella cartella Posta indesiderata *o* nella raccolta dell'elenco di indirizzi attendibili nella cassetta postale.

- *Bulk Complaint Level (BCL):* livello di reclamo in blocco (BCL) del messaggio. Un livello di probabilità di posta indesiderata più elevato indica che è più probabile che un messaggio di posta elettronica in blocco generi reclami (il risultato naturale se è probabile che il messaggio di posta elettronica sia posta indesiderata).

- *Livello di probabilità di posta indesiderata (SCL):* livello di probabilità di posta indesiderata del messaggio. Più alto è il valore, maggiore è la probabilità che si tratti di un messaggio di posta indesiderata.

- *Nome dominio*: è il nome di dominio del mittente.

- *Proprietario dominio*: Specifica il proprietario del dominio di invio.

- *Domain Location*: Specifica la posizione del dominio di invio.

- *Domain Created Date*: Specifica la data di creazione del dominio di invio. Un dominio appena creato è qualcosa di cui potresti essere cauto se altri segnali indicano un comportamento sospetto.

*Autenticazione della* posta elettronica : i metodi di autenticazione della posta elettronica Microsoft 365 includono SPF, DKIM e DMARC.

- Sender Policy Framework (**SPF**): Descrive i risultati del controllo SPF per il messaggio. I valori possibili possono essere:
  - Pass (indirizzo IP): il controllo SPF per il messaggio passato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o inoltrare la posta elettronica per conto del dominio del mittente.
  - Fail (indirizzo IP): il controllo SPF per il messaggio non è riuscito e include l'indirizzo IP del mittente. Talvolta viene definito controllo non riuscito.
  - Softfail (motivo): il record SPF ha designato l'host come non autorizzato a inviare ma è in transizione.
  - Neutro: il record SPF indica esplicitamente che non afferma se l'indirizzo IP è autorizzato a inviare.
  - Nessuno: il dominio non dispone di un record SPF o il record SPF non restituisce un risultato.
  - Temperror: si è verificato un errore temporaneo. Ad esempio, un errore DNS. Il medesimo controllo potrebbe avere esito positivo in seguito.
  - Permerror: si è verificato un errore permanente. Ad esempio, il dominio presenta un record SPF con formato non valido.

- DomainKeys Identified Mail (**DKIM**):
  - Pass: indica il controllo DKIM per il messaggio passato.
  - Fail (motivo): indica il controllo DKIM per il messaggio non riuscito e il motivo. ad esempio se il messaggio non è stato firmato o se la firma non è stata verificata.
  - Nessuno: indica che il messaggio non è stato firmato. Ciò potrebbe indicare o meno che il dominio dispone di un record DKIM o che il record DKIM non restituisce un risultato, solo che il messaggio non è stato firmato.

- Autenticazione, creazione di report e conformità dei messaggi basati su dominio (**DMARC**):
  - Pass: indica il controllo DMARC per il messaggio passato.
  - Fail: indica che il controllo DMARC per il messaggio non è riuscito.
  - Bestguesspass: indica che non esiste alcun record TXT DMARC per il dominio, ma se ne esistesse uno, il controllo DMARC per il messaggio sarebbe stato superato.
  - Nessuno: indica che non esiste alcun record TXT DMARC per il dominio di invio in DNS.

*Autenticazione composita*: questo valore viene utilizzato da Microsoft 365 per combinare l'autenticazione di posta elettronica come SPF, DKIM e DMARC, per determinare se il messaggio è autentico. Utilizza il *dominio From:* della posta come base di valutazione.
