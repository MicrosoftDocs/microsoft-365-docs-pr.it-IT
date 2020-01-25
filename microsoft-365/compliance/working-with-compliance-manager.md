---
title: Collaborare con Microsoft Compliance Manager (anteprima)
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai prodotti Microsoft.
ms.openlocfilehash: db63f1b5cba2166ae8e4f922b84672677b52c4e9
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515867"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a>Collaborare con Microsoft Compliance Manager (anteprima)

> [!IMPORTANT]
> Microsoft Compliance Manager è un dashboard e uno strumento di gestione che fornisce un riepilogo della protezione dei dati e della conformità e suggerimenti per migliorare la protezione dei dati e la conformità. Le azioni dei clienti fornite in Compliance Manager sono raccomandazioni. spetta alla propria organizzazione valutare l'efficacia di tali raccomandazioni nei rispettivi ambienti normativi prima dell'implementazione. Le indicazioni rilevate in Compliance Manager non devono essere interpretate come garanzia di conformità.

## <a name="access-compliance-manager"></a>Access Compliance Manager

Chiunque abbia un account Microsoft o un account organizzativo di Azure Active Directory può accedere a Compliance Manger dal Service Trust Portal.
  
1. Passare a [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).

2. Accedere con l'account del servizio Microsoft, ovvero l'account utente di Office 365, Microsoft 365 o Azure Active Directory (Azure AD).

3. Nel Service Trust Portal, è consigliabile selezionare **Compliance Manager**, ovvero la versione di anteprima con le funzionalità più recenti. **Compliance Manager (Classic)** consente di eseguire la versione precedente di Compliance Manager.

4. Quando viene visualizzato il contratto di non divulgazione, leggerlo e selezionare **concordare**, che visualizza quindi il dashboard di Compliance Manager.

Per iniziare, una valutazione ISO/IEC 27001:2103 per Office 365 viene visualizzata per impostazione predefinita per l'organizzazione.

## <a name="administration"></a>Amministrazione

Esistono funzioni amministrative specifiche disponibili solo per l'amministratore globale e visibili solo quando si esegue l'accesso con un account di amministratore globale. L'amministratore globale può assegnare le autorizzazioni utente e può abilitare gli aggiornamenti automatici del Punteggio sicuro per tutte le azioni.
  
### <a name="assigning-compliance-manager-roles-to-users"></a>Assegnazione di ruoli Compliance Manager agli utenti

Dopo che l'amministratore ha assegnato i ruoli di Compliance Manager ad altri utenti, gli utenti possono visualizzare i dati in Compliance Manager ed eseguire azioni determinate dal loro ruolo. L'amministratore può anche fornire accesso in sola lettura a Compliance Manager assegnando all'utente il [ruolo di lettore globale in Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).

Ogni ruolo di Compliance Manager ha autorizzazioni leggermente diverse. È possibile visualizzare le autorizzazioni assegnate a ogni ruolo, vedere gli utenti in cui si trovano i ruoli e aggiungere o rimuovere utenti da tale ruolo tramite il Service Trust Portal. Selezionare la voce di menu di **Amministrazione** e scegliere **Settings** to view.
  
![Menu di amministrazione STP: impostazioni selezionate](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
Per aggiungere o rimuovere utenti da ruoli Compliance Manager.
  
1. Passare a [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).

2. Accedere con l'account di amministratore globale di Azure Active Directory.

3. Sulla barra dei menu del Service Trust Portal in alto, selezionare **amministratore** e quindi scegliere **Impostazioni**.

4. Nell'elenco a discesa **Seleziona ruolo** selezionare il ruolo che si desidera gestire.

5. Gli utenti aggiunti a ciascun ruolo sono aggiunti nella pagina **Seleziona ruolo**.

6. Per aggiungere utenti a questo ruolo, fare clic su **Aggiungi**. Nella finestra di dialogo **Aggiungi utenti** selezionare il campo utente. È possibile scorrere l'elenco degli utenti disponibili o iniziare a digitare il nome utente per filtrare l'elenco in base al termine di ricerca. Selezionare l'utente per aggiungere quell'account all'elenco **Aggiungi utenti** provisioning con tale ruolo. Se si desidera aggiungere più utenti contemporaneamente, iniziare a digitare un nome utente per filtrare l'elenco e quindi selezionare l'utente da aggiungere all'elenco. Selezionare **Salva** per eseguire il provisioning del ruolo selezionato per gli utenti. 

    ![Compliance Manager-aggiungere utenti](media/compliance-manager-add-users.png)
  
7. Per rimuovere gli utenti da questo ruolo, selezionarli e selezionare **Elimina**.

    ![Compliance Manager-eliminare gli utenti](media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a>Controllo degli aggiornamenti automatici del Punteggio sicuro

Gli aggiornamenti del Punteggio sicuro possono essere attivati automaticamente per tutte le azioni, disattivate per tutte le azioni o impostate per azione individuale attenendosi alla seguente procedura.

1. Accedere al [Service Trust Portal](https://servicetrust.microsoft.com) con l'account di amministratore globale.

2. Nella barra dei menu del servizio di attendibilità del Service Top, in **altro**, selezionare **amministratore** e quindi scegliere **Impostazioni**.

3. Nella scheda **Punteggio sicuro** selezionare il pulsante corrispondente per **attivarla per tutte le azioni**, disattivarla **per tutte le azioni**o **impostare per azione.**

Se si sceglie **imposta per azione,** eseguire i passaggi aggiuntivi per abilitare gli aggiornamenti dei punti di sicurezza per le singole azioni:

4. Scegliere **Compliance Manager** dal menu in alto (Nota: non selezionare "Compliance Manager (Classic)").

5. Selezionare **gestione tenant** nell'angolo in alto a destra dello schermo.

6. Nel riquadro **azioni cliente** individuare l'azione desiderata con puntini di sospensione (**...**) nella colonna **azioni coinvolte** . Fare clic sui puntini di ellisse e selezionare **modifica.**

7. Cambiare l'opzione attiva/disattiva **aggiornamento continuo Punteggio** **su attivato.**

8. Selezionare **Salva.** Secure Score il monitoraggio continuo è ora attivato per tale azione.

**Nota:** Solo l'amministratore globale può abilitare o disattivare gli aggiornamenti automatici per tutte le azioni. L'amministratore di Compliance Manager può abilitare gli aggiornamenti automatici per singole azioni, ma non per tutte le azioni a livello globale.

## <a name="groups"></a>Gruppi

I gruppi sono contenitori che consentono di organizzare valutazioni e condividere le informazioni comuni e le attività del flusso di lavoro tra le valutazioni che dispongono dello stesso o dei controlli gestiti dal cliente.

È possibile raggruppare le valutazioni in modo logico, ad esempio per anno, standard, di servizio o in base ai team, alle divisioni o alle aree geografiche dell'organizzazione. Di seguito sono riportati alcuni esempi di due gruppi e le relative valutazioni sottostanti:
  
- **FFIEC è valutazioni 2020**
  - Office 365 + FFIEC è
  - Intune + FFIEC è
- **Sicurezza dei dati e valutazione della privacy**
  - Office 365 e ISO 27001:2013
  - Office 365 e ISO 27018:2014

> [!NOTE]
> È consigliabile determinare una strategia di raggruppamento per l'organizzazione *prima* di aggiungere nuove valutazioni. Per impostazione predefinita, un gruppo denominato "gruppo predefinito" è disponibile per le valutazioni iniziali.

### <a name="how-to-create-a-group"></a>Come creare un gruppo

I gruppi non possono essere creati come entità autonome. Un gruppo deve contenere sempre almeno una valutazione, quindi per creare un gruppo è necessario innanzitutto creare una valutazione da inserire nel gruppo. Seguire la procedura riportata di seguito per creare un gruppo:

1. Creare una nuova valutazione selezionando **+ Aggiungi valutazione** nei pressi della parte superiore del dashboard.
2. Nel riquadro a comparsa di **valutazione** , immettere un titolo per la valutazione e selezionare un modello dal menu a discesa.
3. In **selezionare un gruppo o aggiungere un nuovo**gruppo, selezionare **Aggiungi un nuovo gruppo** e immettere il nome del gruppo nel campo sottostante.
4. Per copiare le informazioni da un gruppo esistente, attivare o disattivare l'opzione **consente di copiare i dati da un gruppo esistente?** passare a attivato **.** Selezionare il gruppo che si desidera copiare dal menu a discesa sottostante e selezionare le caselle di controllo dei campi che si desidera riportare nella nuova valutazione del nuovo gruppo.
5. Selezionare **Salva**. Al termine, il riquadro a comparsa viene chiuso e il nuovo gruppo viene visualizzato automaticamente nel dashboard.

Cosa sapere quando si lavora con i gruppi:
  
- I nomi dei gruppi (denominati anche *ID gruppo*) devono essere univoci all'interno dell'organizzazione.
- I gruppi non dispongono di alcuna proprietà di sicurezza. Tutte le autorizzazioni sono associate alle valutazioni.
- Dopo aver aggiunto una valutazione a un gruppo, non è possibile modificare il raggruppamento. È possibile rinominare il gruppo di valutazione, che modifica il nome del gruppo di valutazione per tutte le valutazioni associate a tale gruppo.
- I controlli relativi alla valutazione in diverse valutazioni all'interno dello stesso gruppo vengono aggiornati automaticamente quando sono stati completati.
- Se si aggiunge una nuova valutazione a un gruppo esistente, le informazioni comuni provenienti da valutazioni di quel gruppo vengono copiate nella nuova valutazione.
- I gruppi possono contenere valutazioni per la stessa certificazione o regolamentazione, ma ogni gruppo può contenere solo una valutazione per una coppia specifica di certificazione di prodotto. Ad esempio, un gruppo non può contenere due valutazioni per Office 365 e NIST CSF. Un gruppo può contenere più valutazioni per lo stesso prodotto solo se la certificazione o la normativa corrispondente per ognuna di esse è diversa.
- Se si nasconde una valutazione, la relazione tra tale valutazione e il gruppo viene interrotta. Qualsiasi ulteriore aggiornamento ad altre valutazioni correlate non viene più riflesso nella valutazione nascosta. ([Informazioni su come nascondere le valutazioni).](#hide-a-template-or-an-assessment)
- Non è possibile eliminare i gruppi.

## <a name="tenant-management"></a>Gestione tenant

Compliance Manager (Preview) include una nuova interfaccia per la gestione dei nuovi elementi di dati denominati **gestione tenant**. Questa interfaccia consente di gestire le impostazioni a livello di tenant:

- **Dimensioni:** Consente di visualizzare i metadati per i modelli, le valutazioni e gli elementi di azione che consentono di creare pivot personalizzati per i filtri.
- **Proprietari:** Specificare un proprietario per ogni elemento di azione.
- **Azioni dei clienti:** Gestire l'elenco completo degli elementi delle azioni inclusi in Compliance Manager (Preview) e abilitare/disabilitare il monitoraggio del Punteggio sicuro per le azioni che sono integrate con Secure score.

Selezionare **gestione tenant** per aprire l'interfaccia di gestione e seguire i passaggi seguenti per gestire le **dimensioni**, i **proprietari**e le **azioni dei clienti**.

### <a name="dimensions"></a>Dimensioni

Le dimensioni sono insiemi di metadati che forniscono informazioni su un modello, una valutazione o un elemento di azione. Le dimensioni utilizzano il concetto di chiavi e valori, in cui la chiave Dimension rappresenta una proprietà e il valore della dimensione rappresenta valori validi per la proprietà. Ad esempio, in Compliance Manager esistono tre tipi di azioni. Sono definite da una chiave di dimensione per il **tipo di azione** e i valori di dimensione della **documentazione**, **operativo**e **tecnico**. È possibile modificare o eliminare le dimensioni esistenti.

> [!IMPORTANT]
> È possibile aggiungere nuove dimensioni, che possono essere assegnate ai modelli già importati. È inoltre possibile aggiungere nuove dimensioni a qualsiasi nuovo modello creato.

### <a name="owners"></a>Proprietari

I proprietari vengono utilizzati per identificare l'entità responsabile per ogni controllo. Tutti i controlli incorporati sono di proprietà di Microsoft, dei clienti o di entrambi. È possibile creare valori personalizzati per i proprietari che possono essere utilizzati per specificare le responsabilità più granulari all'interno dell'organizzazione. Ad esempio, è possibile creare proprietari che rappresentano gruppi, team o unità aziendali specifici all'interno dell'organizzazione.

#### <a name="add-an-owner"></a>Aggiungere un proprietario

1. Aprire **gestione tenant** e selezionare **proprietari**.
2. Selezionare **+ Aggiungi proprietario**.
3. Specificare un nome e una descrizione per il proprietario e selezionare **Salva**. La descrizione viene visualizzata nella colonna Owner.

#### <a name="edit-an-owner"></a>Modifica di un proprietario

Non è possibile modificare il nome di un proprietario, bensì modificare la descrizione visualizzata nella colonna Owner.

1. Aprire **gestione tenant** e selezionare **proprietari**.
2. Individuare il proprietario che si desidera modificare, selezionare i puntini di ellissi (...) accanto e selezionare **modifica**.
3. Modificare la descrizione in base alle esigenze e selezionare **Salva**.

#### <a name="delete-an-owner"></a>Eliminare un proprietario

1. Aprire **gestione tenant** e selezionare **proprietari**.
2. Individuare il proprietario che si desidera eliminare, selezionare i puntini di ellissi (...) accanto e selezionare **Elimina**.
3. Quando viene visualizzato il messaggio di conferma, selezionare **Elimina**.

### <a name="customer-actions"></a>Azioni dei clienti

L'area azioni clienti Visualizza tutte le azioni dei clienti per tutti i modelli e le valutazioni in Compliance Manager (Preview).

![Compliance Manager-aggiungere utenti](media/compliance-manager-customer-actions.png "Azioni dei clienti di Compliance Manager")

A colpo d'occhio, è possibile visualizzare il titolo, il proprietario, la categoria, l'applicazione e il Punteggio di un'azione e determinare se è integrata con il Punteggio sicuro. È possibile espandere un'azione e selezionare **Leggi altro** per leggere la descrizione dell'azione e accedere a qualsiasi collegamento nella descrizione. È inoltre possibile utilizzare questa interfaccia per abilitare e disabilitare l'integrazione del Punteggio sicuro in base all'azione e per aggiungere azioni personalizzate. Le azioni che dispongono di funzionalità di integrazione con punteggio sicuro dispongono di puntini di sospensione (...) accanto a essi (si noti che le azioni personalizzate dispongono anche di puntini di sospensione accanto a essi).

#### <a name="enable-or-disable-secure-score-integration"></a>Abilitazione o disabilitazione dell'integrazione del Punteggio sicuro

1. Selezionare i puntini di ellisse (...) per l'azione che si desidera modificare e selezionare **modifica**.
2. Attiva o disattiva l'opzione per l'aggiornamento continuo del Punteggio sicuro su attivato o disattivato per attivare o disattivare il monitoraggio continuo tramite il Punteggio sicuro.
3. Selezionare **Salva**.

Quando le organizzazioni distribuiscono per la prima volta Microsoft 365 o Office 365, sono necessari circa sette giorni per ottenere un punteggio sicuro per raccogliere completamente i dati e fattorizzarli nella partitura. Durante questo periodo, l'impostazione dell'opzione aggiornamento continuo Punteggio sicuro su **disattivato** e l'impostazione manuale di un'azione su **implementata** consentiranno di contare tale azione verso il punteggio. Dopo sette giorni iniziali, la riattivazione dell'aggiornamento continuo dei punteggi sicuri consentirà il monitoraggio continuo da quel momento in poi.

Tutte le azioni che non sono supportate dall'integrazione del Punteggio sicuro possono essere implementate manualmente. Un'implementazione manuale consentirà di fattorizzare lo score del gruppo dell'azione.

#### <a name="add-a-customer-action"></a>Aggiungere un'azione del cliente

1. Selezionare **+ Aggiungi azione del cliente**.
2. Specificare un titolo univoco per l'azione nel campo **titolo** .
3. Fornire un punteggio di conformità per l'azione nel campo **Punteggio di conformità massimo** (può essere qualsiasi numero compreso tra 1-99).
4. Utilizzare l'elenco a discesa **tipo di azione** per specificare il tipo di azione che si sta aggiungendo. Se il tipo di azione non esiste, è possibile aggiungerlo aggiungendo il valore alla chiave della dimensione tipo di azione.
5. Utilizzare l'elenco a discesa **dimensioni** per specificare o aggiungere le chiavi e i valori delle dimensioni per l'azione.
6. Utilizzare l'elenco a discesa **proprietario** per specificare il proprietario per l'azione.
7. Selezionare **+** questa sezione per aggiungere un titolo di descrizione e descrizione per l'azione.
8. Selezionare la **X** per chiudere la lama Descrizione.
9. Fare clic su **Salva** per salvare l'azione del cliente.

#### <a name="delete-a-customer-action"></a>Eliminare un'azione del cliente

1. Selezionare i puntini di ellisse (...) per l'azione che si desidera modificare e selezionare **Elimina**.
2. Quando viene visualizzato il messaggio di conferma, selezionare **Elimina**.

## <a name="assessments"></a>Valutazioni

### <a name="add-an-assessment"></a>Aggiungere una valutazione
  
1. Nel dashboard valutazioni selezionare **+ Aggiungi valutazione**.

2. Quando si apre il Blade, immettere le informazioni seguenti:

    - **Titolo (obbligatorio):** Immettere un titolo per la valutazione
    - **Selezionare un modello (obbligatorio):** Selezionare un modello standard o personalizzato
    - **Selezionare un gruppo o aggiungere un nuovo gruppo (obbligatorio):** Selezionare un gruppo esistente oppure scegliere di aggiungere un nuovo gruppo e specificare un nome di gruppo univoco
    - **Si desidera copiare i dati da un gruppo esistente? (facoltativo):** attiva o disattiva il controllo per abilitare la copia del gruppo e quindi:
        - **Selezionare un gruppo (facoltativo):** Se è abilitata la copia di gruppo, selezionare il gruppo da cui copiare
            - **Dettagli sull'implementazione (facoltativa):** Selezionare per copiare i dettagli dell'implementazione nel nuovo gruppo
            - **Piano di Test & ulteriori informazioni (facoltativo):** Selezionare per copiare il piano di testing e ulteriori informazioni dettagliate sul nuovo gruppo
            - **Documenti (facoltativo):** Selezionare per copiare i documenti nel nuovo gruppo

3. Selezionare **Salva** per creare la valutazione.

 La nuova valutazione viene visualizzata nel dashboard di valutazione e visualizza le informazioni seguenti:

- Il titolo della valutazione.
- Le dimensioni della valutazione, tra cui la certificazione, l'ambiente e il prodotto applicati alla valutazione.
- La data in cui è stata creata e la data in cui è stata modificata per l'ultima volta.
- Il Punteggio di valutazione visualizzato come percentuale. Questo punteggio include automaticamente i punteggi dei controlli gestiti da Microsoft e dal punteggio sicuro.
- Indicatori di stato che indicano il numero di controlli gestiti da Microsoft e Customer-mangd.

### <a name="copying-information-from-existing-assessments"></a>Copiare le informazioni da valutazioni esistenti

Quando si crea una valutazione, si ha la possibilità di copiare le informazioni da un gruppo esistente. In questo modo è possibile applicare le informazioni immesse nella valutazione copiata agli stessi controlli nella nuova valutazione. Ad esempio, se si dispone di un gruppo per tutte le valutazioni correlate a FFIEC nell'organizzazione, è possibile copiare le informazioni seguenti dalle valutazioni esistenti:

- Dettagli sull'implementazione
- Piano di test & ulteriori informazioni
- Documenti

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a>Copia delle informazioni da una valutazione esistente a una nuova valutazione
  
1. Nel dashboard di valutazione selezionare **+ Aggiungi valutazione**.
    
2. Nella finestra **Aggiungi una valutazione** , completare le seguenti informazioni

    - **Titolo (obbligatorio):** Immettere un titolo per la valutazione.
    - **Selezionare un modello (obbligatorio):** Selezionare un modello standard o personalizzato.
    - **Selezionare un gruppo o aggiungere un nuovo gruppo (obbligatorio):** Scegliere **aggiungere un nuovo gruppo** e specificare un nome di gruppo univoco.
    - **Si desidera copiare i dati da un gruppo esistente? (facoltativo):** alternare il controllo a attivato per abilitare la copia del gruppo e quindi:- **selezionare un gruppo (facoltativo):** se la copia del gruppo è abilitata, selezionare il gruppo da cui copiare.
            - **Dettagli sull'implementazione (facoltativa):** Selezionare per copiare i dettagli dell'implementazione nel nuovo gruppo.
            - **Piano di Test & ulteriori informazioni (facoltativo):** Selezionare per copiare il piano di testing e ulteriori informazioni dettagliate sul nuovo gruppo.
            - **Documenti (facoltativo):** Selezionare per copiare i documenti nel nuovo gruppo.

3. Selezionare **Salva** per creare la valutazione.

### <a name="view-an-assessment"></a>Visualizzazione di una valutazione
  
1. Nel dashboard valutazioni selezionare il nome della valutazione per aprirlo e visualizzare le informazioni sugli elementi di azione e sui controlli.

Di seguito è riportato un esempio di valutazione per Office 365 e ISO 27001. Nella prima visualizzazione viene illustrata la nuova visualizzazione elementi azione in Compliance Manager (Preview).

![Visualizzazione elementi azione di Compliance Manager](media/compliance-manager-action-items.png)

Le azioni sono elencate in ordine alfabetico e a ogni azione viene assegnato un punteggio e un proprietario. Selezionare il collegamento **Leggi altro** per leggere i dettagli di ogni azione. 

![Visualizzazione elementi azione di Compliance Manager](media/compliance-manager-actions-read-more.png)

Selezionare il collegamento **Revisione** per gestire, assegnare, implementare e testare l'azione. Di seguito è riportato un esempio di azione.

![Visualizzazione azione di Compliance Manager](media/compliance-manager-action.png)

Nelle versioni precedenti di Compliance Manager, il flusso di lavoro per l'implementazione dei requisiti è stato eseguito a livello di controllo. Un responsabile della conformità assegnerà un controllo a un utente per implementare il controllo. Sono stati due gli svantaggi seguenti:

- I controlli spesso sono associati a più azioni e l'utente a cui è stato assegnato un controllo potrebbe non essere la persona giusta per completare tutte le azioni necessarie per implementare il controllo.
- La combinazione di attività separate in una singola azione ha impedito l'insieme dei segnali e della telemetria utilizzati per registrare automaticamente le modifiche alla configurazione tenant in Compliance Manager (Preview).

In Compliance Manager (Preview), il processo del flusso di lavoro è stato spostato dal livello di controllo al livello di azione. Quando si esamina un'azione, è possibile utilizzare i campi seguenti per gestire il flusso di lavoro dell'azione:

- **Assegnare un utente:** Selezionare questo campo per scegliere o immettere l'utente a cui deve essere assegnata l'azione. È possibile scorrere l'elenco o digitare un nome per trovarlo, quindi selezionarlo.
- **Gestire i documenti:** È possibile caricare la prova dell'implementazione in formato documenti di Office, file di immagine e schermate, output di PowerShell in formato CSV o TXT e file PDF.
- **Stato implementazione:** Utilizzato per indicare lo stato di implementazione corrente dell'azione. I valori possibili non sono implementati, implementati, l'implementazione alternativa, pianificata e non nell'ambito.
- **Data di implementazione:** La data in cui è stata eseguita l'azione.
- **Risultato del test:** Utilizzato per indicare i risultati della convalida dell'implementazione. I valori possibili non sono valutati, superato, non riuscito-rischio basso, non riuscito-rischio medio, rischio non riuscito-elevato e non nell'ambito.
- **Data test:** La data in cui si è verificata la convalida.
- **Note sull'implementazione:** Immettere i dettagli sull'implementazione per l'organizzazione, insieme a tutte le note che si desidera includere.
- **Piano di testing:** Immettere i dettagli del piano di test per questa azione, insieme a tutte le note che si desidera includere.
- **Ulteriori informazioni:** Immettere eventuali informazioni aggiuntive su questa azione o su come è stata implementata nell'organizzazione, insieme a tutte le note che si desidera includere.

Compliance Manager (Preview) include anche il pivot basato sul controllo trovato nelle versioni precedenti. Selezionare il dashboard **informazioni controlli** per visualizzarlo. È possibile visualizzare le informazioni per i controlli a livello di valutazione e di modello. Di seguito è riportato un esempio del dashboard delle informazioni sui controlli per le valutazioni.

![Controllo delle informazioni sui controlli Compliance Manager](media/compliance-manager-controls-info.png)

Per le valutazioni, viene visualizzato il dashboard informazioni controlli:

- Un elenco a discesa di **gruppo** per selezionare il gruppo da visualizzare (quando si utilizzano più gruppi).
- Un elenco a discesa di **valutazione** che consente di selezionare la valutazione da visualizzare.
- Metadati relativi alla valutazione selezionata, tra cui:
    - Indicatore di stato per i **controlli valutati** che indicano il numero di controlli valutati rispetto al numero totale di controlli.
    - Il **Punteggio di conformità** corrente per la valutazione, visualizzato come percentuale.
    - Informazioni dettagliate sulla **certificazione** e sul **prodotto** utilizzati per la valutazione.
    - Lo **stato** corrente e la data dell'ultima **modifica** per la valutazione.
- Elenco dei **servizi di ambito** per la valutazione.
- Informazioni dettagliate sui controlli, raggruppati in base alla famiglia di controlli, con collegamenti a azioni dei clienti e dettagli sull'implementazione Microsoft:
    - Nelle **azioni** vengono visualizzate le azioni dei clienti che è possibile eseguire per soddisfare alcuni o tutti i requisiti del controllo. Molti controlli dispongono di più azioni associate e tutte le azioni associate a un controllo vengono visualizzate qui. Le azioni qui hanno la stessa interfaccia utente di quelle elencate nel dashboard Actions.
    - **Microsoft Actions** Visualizza l'elenco dei controlli del Framework interno Microsoft che si applicano al controllo di certificazione selezionato. Per ogni controllo interno, selezionare **implementato** per visualizzare i dettagli relativi all'implementazione e ai test di Microsoft, insieme al risultato del test e alla data di test, come illustrato di seguito.

![Visualizzazione azione Microsoft Compliance Manager](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a>Esportare una valutazione

È possibile esportare una valutazione in un file di Excel per la conformità delle parti interessate nell'organizzazione o per i revisori esterni e regolatori. Il report è un'istantanea della valutazione alla data e all'ora in cui viene creato il report. Il report contiene i dettagli per tutti i controlli Microsoft e gestiti dal cliente per la valutazione, lo stato di implementazione del controllo, la data del test di controllo, i risultati dei test e fornisce collegamenti ai documenti di prova caricati. È necessario esportare il report di valutazione prima di archiviare una valutazione, in quanto le valutazioni archiviate non conservano i collegamenti ai documenti caricati.
  
### <a name="export-an-assessment-report"></a>Esportare un report di valutazione
  
1. Nel dashboard di Compliance Manager selezionare **controlli scheda informazioni** .
2. Selezionare il **gruppo** e la **valutazione** nei menu a discesa per la valutazione che si desidera esportare.
3. Selezionare il pulsante **Esporta** .

Il report di valutazione viene scaricato come file di Excel nella sessione del browser. Il nome dei file per il file di Excel è predefinito per il titolo della valutazione.

### <a name="hide-a-template-or-an-assessment"></a>Nascondere un modello o una valutazione

Al termine di un modello o di una valutazione e non è più necessario ai fini della conformità, è possibile nasconderlo dalla visualizzazione. Quando un modello o una valutazione è nascosta, viene rimossa dalla visualizzazione predefinita ed è necessario selezionare **Includi** casella di controllo nascosta per visualizzarla.

![Visualizzazione modello nascosto Compliance Manager](media/compliance-manager-hidden-template.png "Modello nascosto di Compliance Manager")

> [!IMPORTANT]
> Le valutazioni nascoste non conservano i collegamenti ai documenti di prova caricati. È consigliabile esportare la valutazione prima di nasconderla per mantenere i collegamenti ai documenti di prova nel report.
  
#### <a name="hiding-a-template"></a>Nascondere un modello

1. Aprire il dashboard dei **modelli** .
2. Individuare il modello che si desidera nascondere e nei puntini di ellissi della relativa riga selezionare **Nascondi**.
3. Quando viene visualizzato il messaggio di conferma, selezionare **Nascondi**.

#### <a name="hide-an-assessment"></a>Nascondere una valutazione

1. Aprire il dashboard **valutazioni** .
2. Selezionare il **gruppo** dall'elenco a discesa contenente la valutazione che si desidera nascondere.
3. Individuare la valutazione che si desidera nascondere e i puntini di ellisse, selezionare **Nascondi**.
4. Quando viene visualizzato il messaggio di conferma, selezionare **Nascondi**.

#### <a name="view-hidden-assessments"></a>Visualizzazione di valutazioni nascoste
  
1. Aprire la scheda Dashboard **valutazioni** e selezionare la casella di controllo **Includi nascosto** .
2. Le valutazioni nascoste vengono visualizzate nella sezione **valutazioni nascoste** .

#### <a name="unhide-an-assessment"></a>Scoprire una valutazione

1. Nella scheda **valutazioni** selezionare la casella di controllo **Includi nascosto** .
2. Le valutazioni nascoste vengono visualizzate nella sezione **valutazioni nascoste** .
3. Individuare la valutazione che si desidera visualizzare e i puntini di ellisse, selezionare **Scopri**.
4. Quando viene visualizzato il messaggio di conferma, seleziona **Scopri**.

## <a name="controls-and-actions"></a>Controlli e azioni

I controlli e le azioni sono i principali pivot di dati utilizzati in Compliance Manager (Preview). Il pivot di controllo, che esisteva nelle versioni precedenti di Compliance Manager, è stato migliorato per mostrare i controlli Microsoft e dei clienti nelle stesse famiglie di controllo. Questa visualizzazione consolidata consente di visualizzare più facilmente il modello di responsabilità condivisa completo in base ai singoli controlli. Il pivot azione è una novità di Compliance Manager (Preview) ed è stato creato per fornire una visualizzazione semplificata di tutte le azioni consigliate da Microsoft.

### <a name="controls"></a>Controlli

I controlli possono essere visualizzati dal dashboard info Controls. I controlli rappresentano i requisiti di una norma, una certificazione, una regolamentazione o un Framework. Per eseguire il mapping di tali requisiti su più standard, normative e così via, per associarli a azioni, tutto viene considerato come un Framework di controllo. Ad esempio, come un Framework di controllo, i regolamenti, come HIPAA, sono stati suddivisi per sezione e i controlli HIPAA in Compliance Manager utilizzano lo stesso schema di numerazione di quelle sezioni, come illustrato di seguito:

![Dettagli sui controlli di Compliance Manager Microsoft](media/compliance-manager-control-details.png)

Sono disponibili tre tipi di controlli:

1. **Controlli gestiti da Microsoft:** questi sono i controlli per cui solo Microsoft ha la responsabilità. Vengono visualizzati nei modelli in-box e vengono aggiunti a Compliance Manager da Microsoft.
2. **Controlli gestiti dal cliente:** sono controlli per i quali solo i clienti hanno la responsabilità. Vengono visualizzati nei modelli in-box e vengono aggiunti a Compliance Manager dai clienti.
3. **Controlli di gestione condivisi:** sono i controlli in cui la responsabilità è condivisa tra Microsoft e il cliente. Questi vengono visualizzati nei modelli in-box e vengono aggiunti a Compliance Manager da Microsoft. Il cliente può anche modificare o disabilitare i controlli gestiti da Microsoft.

### <a name="actions-items"></a>Elementi Actions

Gli elementi Actions sono le attività consigliate per l'implementazione dei requisiti di una norma o di una regolamentazione o per testare, verificare e documentare i requisiti di implementazione dell'organizzazione. Le azioni sono associate a uno o più controlli. A ogni controllo è associata una o più azione e ogni azione può essere associata a uno o più controlli. Le azioni fanno parte del flusso di lavoro di base in Compliance Manager (Preview), in quanto sono gli oggetti assegnati, monitorati e convalidati dall'organizzazione.

#### <a name="assign-action-items"></a>Assegnare elementi azione
  
1. Nel dashboard **elementi azione** selezionare il **gruppo** contenente le valutazioni di cui si desidera assegnare l'azione.
2. Nell'elenco a discesa **valutazione** selezionare la valutazione di cui si desidera assegnare l'azione oppure selezionare **tutto** dall'elenco a discesa per visualizzare tutte le azioni disponibili.
3. Individuare l'azione che si desidera assegnare e, nella colonna **proprietario** , selezionare il collegamento per la **Revisione**, **implementato** o **testare**.
4. Selezionare il campo **assegna utente** e visualizzare un elenco di utenti dell'organizzazione. Scorrere l'elenco e selezionare utente oppure filtrare l'elenco per selezionare un utente digitando il nome dell'utente.
5. Nel campo note di implementazione immettere le note che si desidera trasmettere all'utente assegnato.
6. Selezionare **Salva** per assegnare l'azione.

#### <a name="reassign-action-items"></a>Riassegnare gli elementi di azione

Questa funzione consente a un'organizzazione di rimuovere eventuali dipendenze attive o inevase dall'account utente riassegnando un'azione a un nuovo utente.

1. Nel dashboard **elementi azione** selezionare il **gruppo** contenente le valutazioni di cui si desidera riassegnare l'azione.
2. Nell'elenco a discesa **valutazione** selezionare la valutazione di cui si desidera riassegnare l'azione oppure selezionare **tutto** dall'elenco a discesa per visualizzare tutte le azioni disponibili.
3. Individuare l'azione che si desidera riassegnare e, nella colonna **proprietario** , selezionare il collegamento per la **Revisione**, **implementato**o **test**.
4. Eliminare l'utente esistente dal campo **assign user** e scegliere un utente diverso dall'elenco di utenti oppure filtrare l'elenco per selezionare un utente digitando il nome dell'utente.
5. Nel campo note di implementazione immettere le note che si desidera trasmettere all'utente.
6. Selezionare **Salva** per riassegnare l'azione.

## <a name="templates"></a>Modelli

Un modello è l'oggetto di base in Compliance Manager (Preview) associato a un prodotto e a una certificazione (ad esempio, standard, Regulation, Control Framework e così via). I modelli possono essere visualizzati e aggiunti dal dashboard dei modelli.

![Dashboard di Microsoft template di Compliance Manager](media/compliance-manager-template-dashboard.png)
 
Il dashboard Visualizza ogni modello, insieme alla certificazione e al prodotto associati al modello, le date in cui è stato creato il modello e l'ultima modifica, il numero di controlli Customer e Managed Microsoft, il Punteggio di conformità massimo per la Modello e lo stato del modello (ad esempio, approvato, in attesa di approvazione, importato).

I modelli incorporati dispongono di una valutazione incorporata, ma è possibile creare valutazioni aggiuntive basate su modelli incorporati ed è possibile importare i modelli personalizzati e creare valutazioni personalizzate in base a quelle.

### <a name="create-a-template"></a>Creare un modello

È possibile creare un modello copiando un modello esistente o importando un modello personalizzato. È presente un formato e uno schema specifici che devono essere utilizzati per i dati dei modelli o che non verranno importati in Compliance Manager. Da qui è possibile scaricare un file con lo schema e i dati di esempio corretti.
Ogni modello personalizzato deve trovarsi in una cartella di lavoro di Excel distinta (in formato. xls o. xlsx) contenente cinque schede:

1. Valutazione del modello
2. ControlFamily
3. Azioni
4. Ownership
5. Dimensioni

Lo schema utilizzato all'interno di ogni scheda è dettagliato di seguito.

#### <a name="template-assessment-tab"></a>Scheda valutazione modello

Questa scheda contiene una singola colonna:

- **inScopeServices**: elenco delimitato da virgole di prodotti o servizi che rientrano nell'ambito del modello.

#### <a name="controlfamily-tab"></a>Scheda ControlFamily

Questa scheda include colonne che definiscono i controlli mappati alle azioni elencate nella scheda azioni e include dettagli quali nome del controllo, famiglia, titolo e descrizione.  Le colonne di questa scheda, che devono essere ordinate all'interno di Excel nell'ordine elencato di seguito, sono: 

- **ControlName:** Nome del controllo da certificazione/standard/normative, ecc.
- **controlFamily:** Controllare la famiglia dalla certificazione/standard, dalla regolamentazione e così via.
- **controlTitle:** Titolo di controllo da certificazione/standard/normative, ecc.
- **controlDescription:** Descrizione del controllo da certificazione/standard/normative, ecc.
- **controlVersion:** Informazioni sulla versione del controllo facoltativo.  Esempio: per il NIST 800-53, il valore corrente è Rev 4, quindi controlVersion è 4.  Per CSA CCM, è 3.0.1.
- **disattivato:** Utilizzare TRUE o FALSE per indicare se il controllo è stato disabilitato.
- **ControlType:** Utilizzare CC per indicare che si tratta di controlli gestiti dal cliente.
- **controlComplianceScore:** Somma dello score di tutte le azioni assegnate al controllo.
- **controlActionTitle:** Doppio elenco delimitato da punti e virgola di tutti i actionTitles per questo controllo come elencato nella scheda azioni. 

#### <a name="actions-tab"></a>Scheda azioni

Questa scheda include colonne che definiscono singole azioni e include dettagli quali titolo, proprietà e dimensioni dell'azione. Le colonne di questa scheda, che devono essere ordinate all'interno di Excel nell'ordine elencato di seguito, sono: 

- **actionTitle:** Titolo dell'azione. Ogni titolo deve essere univoco e si consiglia di utilizzare il caso Pascal.
- **actionRelatedODVs:** Doppio elenco delimitato da punti e virgola di actionTitles che sono genitori del figlio elencato nella colonna actionTitle. In una relazione padre/figlio, l'elemento padre rappresenta la filigrana alta. Pertanto, se si completa un'azione padre, vengono completate anche tutte le azioni figlio. Ad esempio, se si dispone di requisiti simili ma di valori definiti standard diversi, come la lunghezza della password, in cui uno standard/regolamentazione richiede un minimo di 15 caratteri e un altro richiede almeno 12 o 10. 15 è l'elemento padre in questo esempio e, se si configura un minimo di 15 caratteri, si soddisfano anche le azioni che consigliano 12 o 10 caratteri in altre valutazioni.

    > [!NOTE]
    > La colonna actionRelatedODVs è una colonna obbligatoria per lo schema. Tuttavia, la caratteristica (azioni correlate) non è disponibile in Compliance Manager (Preview).  È previsto l'aggiunta in una versione successiva.

- **actionDimensionValues:** Doppio elenco delimitato da punti e virgola delle dimensioni applicabili dalla scheda dimensioni, utilizzando il formato seguente:

    ```Markdown
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    Ad esempio:

    ```Markdown
    Product::Office 365;;Certification::NIST CSF
    ```

    Tutte le dimensioni utilizzate in un modello personalizzato devono essere elencate nella scheda dimensioni del file di importazione, anche se sono già elencate nel dashboard dimensioni.
- **actionScore:** Valore numerico per ogni azione, che rappresenta il punteggio per tale azione. Si consiglia di seguire il modello di punteggio utilizzato dalle valutazioni predefinite, che si basano sulla finalità e sull'applicazione di ogni azione.
- **actionOwnership:** Doppio elenco delimitato da punti e virgola dei proprietari. Tutti i proprietari elencati devono essere inclusi nella scheda Proprietà.
- **actionDescription:** Testo di ogni azione, che deve essere univoco. Questo campo supporta la lingua Markdown come descritto di seguito.

#### <a name="ownership-tab"></a>Scheda Proprietà

In questa scheda sono incluse le colonne che definiscono i proprietari per ogni azione.  Le colonne di questa scheda, che devono essere ordinate all'interno di Excel nell'ordine elencato di seguito, sono:

- **proprietàName:** Nome univoco del proprietario/parte responsabile.
- **ownershipDescription:** Descrizione del proprietario/parte responsabile.

#### <a name="dimensions-tab"></a>Scheda dimensioni

In questa scheda sono incluse le colonne che definiscono le dimensioni che possono essere associate a un'azione.  Le colonne di questa scheda, che devono essere ordinate all'interno di Excel nell'ordine elencato di seguito, sono:

- **dimensionKey:** Elenco delle chiavi utilizzate per le dimensioni. Ad esempio, il prodotto, la certificazione e così via.
- **dimensionValue:** Valore univoco per ogni chiave della dimensione. Ad esempio, Office 365, Intune, Azure, Custom Product e così via.
- **allowMultiSelect:** Utilizzare il valore TRUE o FALSE per indicare che è possibile selezionare più valori di dimensione per una singola chiave di dimensione.

#### <a name="using-markdown-language-in-description-fields"></a>Utilizzo della lingua Markdown nei campi Descrizione

I modelli e le valutazioni supportano l'utilizzo della lingua Markdown per alcuni elementi di testo e la formattazione.  Sono disponibili tre elementi di formattazione della lingua di Markdown che vengono utilizzati in Compliance Manager:

- Elenchi puntati e numerati
- Collegamenti ipertestuali
- Grassetto

Gli elenchi puntati sono rappresentati come asterischi anziché punti elenco di Word o Excel. Ad esempio:

```Markdown
* Item A
* Item B
* Item C
```

I numeri sono rappresentati come numeri, ma con spazi per il rientro (tre spazi per ogni livello) e solo i numeri utilizzati per tutti i sottolivelli (ad esempio, nessuna lettera).  Ad esempio:
   1. Elemento A
   2. Elemento B
      1. Elemento secondario A
      2. Sottoelemento B
   3. Elemento C
   4. Elemento D
      1. Elemento secondario A
      2. Sottoelemento B
   5. Elemento E

I collegamenti ipertestuali vengono costruiti posizionando le parentesi attorno al testo del collegamento ipertestuale e il collegamento ipertestuale stesso tra parentesi immediatamente accanto alla parentesi chiusa.  Ad esempio:

```Markdown
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
Il testo viene eseguito nel modo seguente: fare clic [qui](https://www.microsoft.com) per accedere alla Home page di Microsoft.

Come illustrato nell'esempio precedente, Compliance Manager non esegue il rendering degli URL con la sottolineatura.

Il testo di grassetto è costituito da due asterischi su ogni parte del testo da applicare in grassetto.  Ad esempio:

```Markdown
**This text will render in bold**
```
**Questo testo viene eseguito il rendering in grassetto**

### <a name="create-a-template"></a>Creare un modello

È possibile creare un modello copiando un modello esistente o importando i dati dei modelli da Excel. Quando si importano dati da Excel, il modello richiede due diversi amministratori di Compliance Manager per pubblicare i dati (uno per la pubblicazione e uno per l'approvazione).

#### <a name="create-a-template-by-copying-an-existing-template"></a>Creare un modello copiando un modello esistente

1. Aprire il dashboard **modelli** e selezionare **+ Aggiungi modello**.
2. Nel campo **immettere il nome del modello** specificare un nome univoco per il modello.
3. Controllare la **copia da una** casella di controllo modello esistente e selezionare il modello che si desidera copiare dall'elenco a discesa.
4. Facoltativamente, aggiungere altre dimensioni.
5. Selezionare **Aggiungi a Dashboard**.

#### <a name="create-a-template-by-importing-data"></a>Creare un modello importando i dati

1. Aprire il dashboard **modelli** e selezionare **+ Aggiungi modello**.
2. Nel campo **immettere il nome del modello** specificare un nome univoco per il modello.
3. Selezionare almeno una dimensione dall'elenco disponibile.
4. Selezionare **Sfoglia** per passare al percorso del file di importazione, selezionarlo e selezionare **Apri**.
5. Il file di importazione verrà convalidato e indicherà il numero di controlli e famiglie di controllo rilevati. Se si verificano errori, verrà fornito un collegamento a una versione modificata del file di importazione che include informazioni dettagliate sull'errore. Tutti gli errori devono essere risolti prima che i dati vengano importati.
6. Dopo che i dati hanno superato la convalida, selezionare **Aggiungi a Dashboard**.
7. Il modello importato viene visualizzato nel dashboard **modelli** ed è stato **importato**. Selezionare i puntini di ellisse (...) e selezionare **pubblica** per pubblicare il modello. Quando viene visualizzato il messaggio di conferma, selezionare **pubblica**. Lo stato del modello cambia nell' **approvazione in sospeso**.
8. Un altro utente con il ruolo di amministratore di Compliance Manager deve approvare il modello nel dashboard dei modelli. È necessario selezionare i puntini di ellisse (...) e selezionare **approva**. Quando viene visualizzato il messaggio di conferma, selezionare **approva**. Il modello è ora pronto per l'uso.

> [!IMPORTANT]
> Quando si crea un modello, è necessario includere le dimensioni per il **prodotto** e la **certificazione** per garantire che il modello venga visualizzato nel punteggio di conformità.

### <a name="customize-a-template"></a>Personalizzare un modello

I modelli possono essere personalizzati tramite l'aggiunta di controlli personalizzati. Tutti i controlli personalizzati sono considerati controlli gestiti dal cliente.

#### <a name="add-a-custom-control-to-a-template"></a>Aggiungere un controllo personalizzato a un modello

1. Aprire il **modello** che si desidera modificare.
2. Selezionare **+ Aggiungi** controllo personalizzato.
3. Selezionare una **famiglia di controlli** dall'elenco a discesa oppure immettere una nuova famiglia di controlli, se non esiste.
4. Specificare un nome o un ID univoco per il controllo nel campo **ID controllo** .
5. Specificare il titolo del controllo nel campo **titolo** .
6. Fornire i requisiti e altre informazioni per il controllo nel campo **Descrizione** .
7. Selezionare **Assegna azione del cliente** .
8. Individuare le azioni che si desidera assegnare al controllo:
    - Utilizzare il **filtro in base alla dimensione** per utilizzare le dimensioni assegnate alle azioni da individuare e elencarle.
    - Utilizzare **filtro in base al proprietario** per utilizzare il proprietario o i proprietari assegnati alle azioni da individuare ed elencarli.
    - Selezionare un **tipo di azione** dal menu a discesa per elencare le azioni per tipo.
    - Immettere il titolo dell'azione per individuarlo ed elencarlo.
9. Utilizzando i criteri del passaggio 8, verrà visualizzato un elenco di **azioni corrispondenti** . Selezionare la prima azione che si desidera assegnare al controllo.
10. Vengono visualizzati i dettagli dell'azione. Selezionare la **Descrizione** che si desidera utilizzare e fare clic su **fine**.
11. Ripetere i passaggi 9 e 10 per ogni azione aggiuntiva che si desidera assegnare.
12. Quando sono state selezionate tutte le azioni applicabili, selezionare **assegna**.
13. Fare clic su **Salva** per salvare il nuovo controllo.

> [!NOTE]
> Tutte le modifiche apportate a un modello non verranno riflesse nelle valutazioni esistenti. Gli aggiornamenti dei modelli devono essere eseguiti prima e quindi applicati a una nuova valutazione, in modo che le modifiche vengano visualizzate.

### <a name="export-a-template-to-json"></a>Esportare un modello in JSON

Compliance Manager (Preview) supporta anche l'esportazione di modelli in formato JSON (JavaScript Object Notation). In questo modo è possibile scambiare i dati di Compliance Manager con altri sistemi che supportano JSON.

## <a name="reports"></a>Report

È possibile esportare una valutazione in un file di Excel per la conformità delle parti interessate nell'organizzazione o per i revisori esterni e regolatori. Il report è un'istantanea della valutazione alla data e all'ora dell'esportazione. Il report contiene i dettagli per i controlli Microsoft e gestiti dal cliente per la valutazione, lo stato di implementazione del controllo, la data del test di controllo, i risultati dei test e i collegamenti ai documenti di prova caricati. Le valutazioni devono essere esportate prima dell'archiviazione, in quanto le valutazioni archiviate non conservano i collegamenti ai documenti caricati.

### <a name="export-an-assessment"></a>Esportare una valutazione

1. Nel dashboard di Compliance Manager selezionare **controlli scheda informazioni** .
2. Selezionare il gruppo e la valutazione nei menu a discesa per la valutazione che si desidera esportare.
3. Selezionare Esporta. L'esportazione di valutazione viene scaricata come file di Excel.

![Rapporto Excel di valutazione di Compliance Manager](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a>Autorizzazioni

Nella tabella seguente vengono descritte le autorizzazioni di Compliance Manager e gli elementi che consente all'utente di eseguire la procedura. La tabella indica anche il ruolo a cui è assegnata ogni autorizzazione.

||**Lettore globale di Azure AD**|**Compliance Manager - Lettore**|**Compliance Manager - Collaboratore**|**Compliance Manager - Valutatore**|**Compliance Manager - Amministratore**|**Amministratore del portale**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Leggere i dati:** Gli utenti possono leggere ma non modificare i dati (ad eccezione dei dati del modello e della gestione tenant).  <br> | X | X | X | X | X  | X |
|**Modificare i dati:** Gli utenti possono modificare tutti i campi, tranne i campi risultato del test e data di test (ad eccezione dei dati del modello e della gestione tenant).  <br> ||| X | X  | X | X |
|**Modificare i risultati dei test:** Gli utenti possono modificare i campi risultato del test e data del test.  <br> |||| X | X | X |
|**Gestire le valutazioni:** Gli utenti possono creare, archiviare ed eliminare valutazioni.  <br> ||||| X | X |
|**Gestire i dati master:** Gli utenti possono visualizzare, modificare ed eliminare i dati dei modelli e la gestione dei tenant.  <br> ||||| X | X |
|**Gestire gli utenti:** Gli utenti possono aggiungere altri utenti all'interno dell'organizzazione ai ruoli lettore, collaboratore, valutatore e amministratore. Solo gli utenti che dispongono del ruolo di amministratore globale nell'organizzazione possono aggiungere o rimuovere utenti dal ruolo di amministratore del portale.  <br> |||||| X |
