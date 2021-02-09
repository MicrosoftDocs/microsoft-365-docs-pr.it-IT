---
title: Pagina dell'entità di posta elettronica di Microsoft Defender per Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: How-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: I clienti di Microsoft Defender per Office 365 E5 e ATP P1 e ATP P2 ora possono ottenere una visualizzazione a 360 gradi di ogni messaggio di posta elettronica con la pagina entità di posta elettronica.
ms.openlocfilehash: 3b9198c9d91969d3b57f379d17de33a1c00d37f6
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50143137"
---
# <a name="the-email-entity-page"></a>Pagina Entità posta elettronica

**Contenuto dell'articolo:**
- [Raggiungere la pagina dell'entità di posta elettronica](#reach-the-email-entity-page)
- [Leggere la pagina dell'entità di posta elettronica](#read-the-email-entity-page)
- [Usare le schede delle pagine dell'entità di posta elettronica](#use-email-entity-page-tabs)
- [Novità della pagina dell'entità di posta elettronica](#new-to-the-email-entity-page)

Gli amministratori di Microsoft Defender per Office 365 (o MDO) E5 e MDO P1 e P2 hanno una visualizzazione a 360 gradi della posta elettronica usando la pagina entità posta **elettronica.** Questa pagina di posta elettronica di accesso è stata creata per migliorare le informazioni recapitate nel riquadro a comparsa "Dettagli posta [elettronica" di Esplora minacce.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views)

## <a name="reach-the-email-entity-page"></a>Raggiungere la pagina dell'entità di posta elettronica

Il Centro sicurezza e conformità di Office esistente (protection.office.com) o il nuovo Centro sicurezza Microsoft 365 (security.microsoft.com) consente di visualizzare e usare la pagina dell'entità di posta elettronica.

|Centro  |URL  |Struttura di spostamento  |
|---------|---------|---------|
|Sicurezza e conformità |protection.office.com | Gestione delle minacce > Explorer   |
|Centro sicurezza Microsoft 365 |security.microsoft.com | Esplora & collaborazione > posta elettronica |

In Esplora minacce seleziona l'oggetto di un messaggio di posta elettronica che stai analizzando. Nella parte superiore del riquadro a comparsa del messaggio di posta elettronica verrà visualizzata una barra dorata. Questo invito alla nuova pagina, legge "Prova la nuova pagina dell'entità di posta elettronica con dati arricchiti...". Selezionare questa opzione per visualizzare la nuova pagina.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="You will see a gold banner with the words *Try out our new email entity page with enriched data* to navigate to the new experience.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Questo grafico della pagina dell'entità di posta elettronica si concentra sulle intestazioni che verranno visualizzati. Si noti che l'intestazione del messaggio di posta elettronica viene visualizzata qui.":::

> [!NOTE]
> Le autorizzazioni necessarie per visualizzare e usare questa pagina sono le stesse di Esplora minacce. L'amministratore deve essere membro dell'amministratore globale o del lettore globale oppure amministratore della sicurezza o lettore della sicurezza.

## <a name="read-the-email-entity-page"></a>Leggere la pagina dell'entità di posta elettronica

La struttura è progettata per essere facile da leggere e navigare a colpo d'occhio. Varie schede nella parte superiore della pagina consentono di analizzare in modo più dettagliato. Ecco come funziona il layout:

1. I campi più obbligatori sono sul lato sinistro del riquadro a comparsa. Questi dettagli sono "appiccicosi", ovvero sono ancorati a sinistra indipendentemente dalla scheda a cui ci si sposta nel resto del riquadro a comparsa.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Immagine della pagina dell'entità di posta elettronica con il lato sinistro evidenziato. Il titolo e i fatti relativi al recapito della posta sono disponibili qui.":::

2. Nell'angolo in alto a destra sono disponibili le azioni che è possibile eseguire su un messaggio di posta elettronica. Tutte le azioni che è possibile eseguire tramite Esplora risorse saranno disponibili anche tramite la pagina dell'entità di posta elettronica.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Immagine della pagina dell'entità di posta elettronica con il lato *a destra* evidenziato, questa volta. Sono disponibili azioni come &quot;Anteprima posta elettronica&quot; e &quot;Vai in quarantena&quot;.":::

3. È possibile eseguire un'analisi più approfondita ordinando il resto della pagina. Controllare i dettagli di rilevamento della posta elettronica, lo stato di autenticazione della posta elettronica e l'intestazione. Quest'area deve essere cercata caso per caso, ma le informazioni in queste schede sono disponibili per qualsiasi messaggio di posta elettronica.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Il pannello principale di questa pagina include l'intestazione della posta elettronica e lo stato di autenticazione.":::

### <a name="use-email-entity-page-tabs"></a>Usare le schede delle pagine dell'entità di posta elettronica

Le schede nella parte superiore della pagina dell'entità consentono di analizzare la posta elettronica in modo efficiente.

1. **Sequenza** temporale: la visualizzazione della sequenza temporale per un messaggio di posta elettronica (in base alla sequenza temporale di Esplora minacce) mostra il recapito originale agli eventi di post-recapito che si verificano in un messaggio di posta elettronica. Per i messaggi di posta elettronica che non dispongono di azioni post-recapito, la visualizzazione mostra la riga di recapito originale nella visualizzazione sequenza temporale. Eventi come: Zero-hour auto purge (ZAP), Remediate, URL clicks, et cetera, from sources like: system, admin, and user, show up here, in the order in which they occurred.
2. **Analisi:** l'analisi mostra i campi che consentono agli amministratori di analizzare in modo approfondito un messaggio di posta elettronica. Per i casi in cui gli amministratori devono comprendere meglio i dettagli di rilevamento, mittente/destinatario e autenticazione della posta elettronica, devono usare la scheda Analisi. I collegamenti per allegati e URL sono disponibili anche in questa pagina, in "Entità correlate". Sia gli allegati che le minacce identificate sono numerati qui e facendo clic si visualizzano direttamente le pagine Allegati e URL. Questa scheda ha anche un'opzione Visualizza intestazione per *visualizzare l'intestazione del messaggio di posta elettronica.* Gli amministratori possono confrontare qualsiasi dettaglio dalle intestazioni dei messaggi di posta elettronica, affiancati alle informazioni nel pannello principale, per maggiore chiarezza.
3. **Allegati**: esamina gli allegati trovati nel messaggio di posta elettronica con altri dettagli trovati sugli allegati. Il numero di allegati visualizzati è attualmente limitato a 10. Si noti che i dettagli della detonazione per gli allegati trovati come dannosi sono mostrati qui.
4. **URL:** questa scheda elenca gli URL trovati nel messaggio di posta elettronica con altri dettagli sugli URL. Il numero di URL è limitato a 10 al momento, ma questi 10 hanno la priorità per mostrare prima *gli URL dannosi.* La definizione della priorità consente di risparmiare tempo e congettura. Anche gli URL che sono stati trovati come dannosi e detonati verranno mostrati qui.
5. **Messaggi di posta elettronica simili:** questa scheda elenca tutti i messaggi di posta elettronica simili alla combinazione ID messaggio di rete *+ destinatario* specifica di questo messaggio di posta elettronica. La similarità si basa *solo sul corpo del* messaggio. Le determinazioni effettuate nei messaggi di posta elettronica per classificarle come "simili" non includono una considerazione degli *allegati.*

## <a name="new-to-the-email-entity-page"></a>Novità della pagina dell'entità di posta elettronica

Esistono nuove funzionalità disponibili con questa pagina dell'entità di posta elettronica. Ecco l'elenco.

### <a name="email-preview-for-cloud-mailboxes"></a>Anteprima della posta elettronica per le cassette postali cloud
Gli amministratori possono visualizzare in anteprima i messaggi di posta elettronica nelle ***cassette*** postali cloud, se i messaggi sono ancora presenti nel cloud. In caso di eliminazione recisa (da parte di un amministratore o utente) o ZAP (per la quarantena), i messaggi di posta elettronica non sono più presenti nella posizione cloud. In tal caso, gli amministratori non saranno in grado di visualizzare in anteprima i messaggi di posta elettronica specifici. I messaggi di posta elettronica che sono stati eliminati o in cui il recapito non è riuscito, non sono mai stati effettivamente effettuati nella cassetta postale. Di conseguenza, gli amministratori non saranno in grado di visualizzare in anteprima i messaggi di posta elettronica.

> [!WARNING]
>La visualizzazione in anteprima dei messaggi di posta elettronica richiede un ruolo speciale denominato ***Anteprima** _ da assegnare agli amministratori. È possibile aggiungere questo ruolo andando a _ Autorizzazioni *& ruoli** > **Ruoli** di collaborazione & posta elettronica in *security.microsoft.com* o Autorizzazioni **in** *protection.office.com*. Aggiungere il ***ruolo Anteprima*** a uno qualsiasi dei gruppi di ruoli o una copia di un gruppo di ruoli che consente agli amministratori dell'organizzazione di lavorare in Esplora minacce.

### <a name="detonation-details"></a>Dettagli detonazione

Questi dettagli sono specifici per gli URL e gli allegati di posta elettronica.

Gli utenti visualizzano dettagli di detonazione arricchiti per allegati dannosi noti o collegamenti ipertestuali trovati nelle proprie cassette postali, tra cui la catena di detonazione, il riepilogo della detonazione, lo screenshot e i dettagli sul comportamento osservato per aiutare i clienti a capire perché l'allegato o l'URL è stato considerato dannoso e detonato.
 
- *Catena di detonazione:* una detonazione di un singolo file o URL può attivare più detonazioni. La catena di detonazione tiene traccia del percorso delle detonazioni, incluso il file o l'URL dannoso originale che ha causato il verdetto, e tutti gli altri file o URL causati dalla detonazione. Questi URL o file allegati potrebbero non essere direttamente presenti nel messaggio di posta elettronica, ma l'inclusione di tale analisi è importante per determinare il motivo per cui il file o l'URL è stato trovato dannoso.
- *Riepilogo della detonazione:* fornisce informazioni su:
    - Intervallo di tempo di detonazione.
    - Verdetto del file allegato o dell'URL.
    - Informazioni correlate (numero di file, URL, IP o domini), che sono altre entità esaminate durante la detonazione.
- *Schermata di detonazione:* mostra gli screenshot emersi durante il processo di detonazione.
- *Dettagli della detonazione:* questi sono i dettagli esatti sul comportamento di ogni processo che ha avuto luogo durante la detonazione.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Screenshot of the detonation summary showing the chain, summary, detonation details, and screenshot under the heading *Deep Analysis*.":::

### <a name="other-innovations"></a>Altre innovazioni

*Tag:* si tratta di tag applicati agli utenti. Se l'utente è un destinatario, gli amministratori visualizzano un tag *destinatario.* Analogamente, se l'utente è un mittente, un tag *mittente.* Verrà visualizzato nel lato sinistro della pagina delle entità di posta  elettronica (nella parte descritta come fissa e quindi ancorata alla pagina).

*Posizione di recapito più recente:* la posizione di recapito più recente è la posizione in cui un messaggio di posta elettronica è atterrato dopo le azioni di sistema come ZAP o le azioni di amministratore come Sposta nella posta eliminata, terminare. La posizione di recapito più recente non è progettata per informare gli amministratori della *posizione corrente del* messaggio. Ad esempio, se un utente elimina un messaggio o lo sposta nell'archivio, il percorso di recapito non verrà aggiornato. Tuttavia, se è stata eseguita un'azione di sistema e la posizione è stata aggiornata (ad esempio un ZAP che causa lo spostamento di un messaggio di posta elettronica in quarantena), il percorso di recapito più recente verrà aggiornato in Quarantena.

*Dettagli della posta* elettronica: dettagli necessari per una conoscenza più approfondita della posta elettronica disponibile nella *scheda* Analisi.

- *Regole di trasporto di Exchange (ETR* o regole del flusso di posta): queste regole vengono applicate a un messaggio a livello di trasporto e hanno la precedenza sui verdetti di phish e posta indesiderata. Questi possono essere creati e modificati solo nell'interfaccia di amministrazione di Exchange, ma se un ETR si applica a un messaggio, il nome ETR e il GUID verranno mostrati qui. Informazioni preziose a scopo di monitoraggio.
    
- *Sostituzioni* del sistema: si tratta di un mezzo per creare eccezioni alla posizione di recapito destinata a un messaggio ignorando il percorso di recapito fornito dal sistema (in base alla tecnologia di rilevamento e minaccia).
    
- *Regola cassetta postale indesiderata:*"Posta indesiderata" è una regola di Posta in arrivo nascosta abilitata per impostazione predefinita in ogni cassetta postale.
    - Quando la regola di posta indesiderata è abilitata nella cassetta postale, Exchange Online Protection (EOP) è in grado di spostare i messaggi nella posta indesiderata in base ad alcuni criteri. Lo spostamento può essere basato sull'azione di verdetto filtro posta indesiderata Sposta il messaggio nella cartella Posta indesiderata *o* sull'elenco Mittenti bloccati nella cassetta postale. La disabilitazione della regola di posta indesiderata impedisce il recapito dei messaggi nella cartella Posta indesiderata in base all'elenco *Mittenti* attendibili nella cassetta postale.
    - Quando la regola  di posta indesiderata è disabilitata nella cassetta postale, EOP non può spostare i messaggi nella cartella Posta indesiderata in base all'azione di verdetto filtro posta indesiderata Sposta il messaggio nella cartella Posta indesiderata o sulla raccolta degli elenchi indirizzi attendibili nella cassetta postale.
    
- *Bulk Compliant Level (BCL):* il livello di reclamo in blocco (BCL) del messaggio. Un livello di probabilità di posta indesiderata più alto indica che è più probabile che un messaggio di posta inviata in blocco generi reclami (risultato naturale se è probabile che il messaggio di posta elettronica sia posta indesiderata).
    
- *Livello di probabilità di posta indesiderata (SCL):* il livello di probabilità di posta indesiderata (SCL) del messaggio. Più alto è il valore, maggiore è la probabilità che si tratti di un messaggio di posta indesiderata.

- *Nome dominio*: è il nome di dominio del mittente.
    
- *Proprietario dominio*: specifica il proprietario del dominio di invio.
    
- *Posizione dominio*: specifica il percorso del dominio di invio.
    
- *Domain Created Date*: Specifica la data di creazione del dominio di invio. Un dominio appena creato è qualcosa di cui potresti essere prudente se altri segnali indicano un comportamento sospetto.

*Autenticazione della posta* elettronica: i metodi di autenticazione della posta elettronica utilizzati da Microsoft 365 includono SPF, DKIM e DMARC.

- Sender Policy Framework (**SPF**): descrive i risultati per il controllo SPF del messaggio. I valori possibili possono essere:
    - Pass (indirizzo IP): il controllo SPF per il messaggio è stato superato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o inoltrare la posta elettronica per conto del dominio del mittente.
    - Fail (indirizzo IP): il controllo SPF per il messaggio non è riuscito e include l'indirizzo IP del mittente. Talvolta viene definito controllo non riuscito.
    - Softfail (motivo): il record SPF ha designato l'host come non autorizzato a inviare ma è in transizione.
    - Neutral: il record SPF indica esplicitamente che non afferma se l'indirizzo IP è autorizzato a inviare.
    - Nessuno: il dominio non dispone di un record SPF o il record SPF non restituisce un risultato.
    - Temperror: si è verificato un errore temporaneo. Ad esempio, un errore DNS. Il medesimo controllo potrebbe avere esito positivo in seguito.
    - Permerror: si è verificato un errore permanente. Ad esempio, il dominio presenta un record SPF con formato non valido.

- DomainKeys Identified Mail (**DKIM**):
    - Pass: indica che il controllo DKIM per il messaggio è stato superato.
    - Fail (motivo): indica che il controllo DKIM per il messaggio non è riuscito e il motivo. ad esempio se il messaggio non è stato firmato o se la firma non è stata verificata.
    - Nessuno: indica che il messaggio non è stato firmato. Ciò potrebbe indicare o meno che il dominio dispone di un record DKIM o che il record DKIM non restituisce un risultato, solo che il messaggio non è stato firmato.

- Autenticazione dei messaggi basata su dominio, creazione di report e conformità (**DMARC**):
    - Pass: indica che il controllo DMARC per il messaggio è stato superato.
    - Fail: indica che il controllo DMARC per il messaggio non è riuscito.
    - Bestguesspass: indica che non esiste alcun record TXT DMARC per il dominio, ma se ne esistesse uno, il controllo DMARC per il messaggio sarebbe stato superato.
    - Nessuno: indica che non esiste alcun record TXT DMARC per il dominio di invio in DNS.

*Autenticazione composita:* questo è un valore usato da Microsoft 365 per combinare l'autenticazione di posta elettronica come SPF, DKIM e DMARC, per determinare se il messaggio è autentico. Utilizza il *dominio Da:* della posta come base di valutazione.
