---
title: Simulatore di attacco in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare Attack Simulator per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 piano 2.
ms.openlocfilehash: b7d04b3c81791bfc107b48176373ffc84fc8f6c5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845997"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Simulatore di attacco in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se l'organizzazione dispone di Microsoft Defender per Office 365 piano 2, in cui sono incluse le [funzionalità di ricerca e di risposta alle minacce](office-365-ti.md), è possibile utilizzare Attack Simulator nel centro sicurezza & conformità per eseguire scenari di attacco realistici nell'organizzazione. Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base. Leggere questo articolo per ulteriori informazioni.

> [!NOTE]
> I dati relativi alla simulazione e all'addestramento degli attacchi vengono archiviati con altri dati dei clienti per i servizi Microsoft 365. Per ulteriori informazioni, vedere [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>. Simulatore di attacco è disponibile in **Threat Management** \> **Attack Simulator**. Andare direttamente a attacco simulatore, aprire <https://protection.office.com/attacksimulator> .

- Per ulteriori informazioni sulla disponibilità di simulatori di attacco in diverse sottoscrizioni di Microsoft 365, vedere [Descrizione del servizio Microsoft Defender per Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- L'account deve essere configurato per l'autenticazione a più fattori (AMF) per creare e gestire le campagne in Attack Simulator. Per istruzioni, vedere [configurare l'autenticazione](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)a più fattori.

- Le campagne di phishing raccolgono ed elaborano gli eventi per 30 giorni. I dati della campagna cronologica saranno disponibili fino a 90 giorni dopo l'avvio della campagna.

- Non sono disponibili i cmdlet di PowerShell corrispondenti per il simulatore di attacco.

## <a name="spear-phishing-campaigns"></a>Campagne di phishing Spear

Il *phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni sensibili nei messaggi che sembrano provenire da mittenti legittimi o attendibili. *Spear phishing* è un attacco di phishing mirato che utilizza contenuti mirati e personalizzati appositamente personalizzati per i destinatari mirati (in genere, dopo la ricognizione dei destinatari da parte dell'utente malintenzionato).

In Attack Simulator sono disponibili due diversi tipi di campagne di phishing Spear:

- **Spear phishing (Harvest Credentials)** : l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio. Se si fa clic sul collegamento, viene richiesto di immettere le proprie credenziali. In caso contrario, vengono eseguite in una delle posizioni seguenti:

  - Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per il riconoscimento dei messaggi di phishing.

    ![Cosa vedranno gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - Una pagina personalizzata (URL) specificata.

- **Spear phishing (Attachment)** : l'attacco tenta di convincere i destinatari ad aprire un allegato. docx o. pdf nel messaggio. L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " \<Display Name\> , si sta vedendo questo messaggio come un messaggio di posta elettronica recente è stato aperto...".

> [!NOTE]
> Attualmente, le campagne di phishing Spear in Attack Simulator non scadono.

### <a name="create-a-spear-phishing-campaign"></a>Creare una campagna di phishing di Spear

Una parte importante di qualsiasi campagna di phishing Spear è l'aspetto del messaggio di posta elettronica inviato ai destinatari mirati. Per creare e configurare il messaggio di posta elettronica, sono disponibili le seguenti opzioni:

- **Utilizzo di un modello di posta elettronica incorporato** : sono disponibili due modelli incorporati: **Giveaway Prize** and **Payroll Update**. È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica dal modello quando si crea e si avvia la campagna.

- **Creare un modello di posta elettronica riutilizzabile** : dopo aver creato e salvato il modello di posta elettronica, è possibile utilizzarlo nuovamente nelle future campagne di phishing Spear. È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica dal modello quando si crea e si avvia la campagna.

- **Creare il messaggio di posta elettronica nella procedura guidata** : è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata quando si crea e si avvia la campagna di phishing Spear.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Passaggio 1 (facoltativo): creare un modello di posta elettronica personalizzato

Se si intende utilizzare uno dei modelli incorporati o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.

1. Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.

2. Nella pagina **simula attacchi** , nella sezione **spear phishing (credentials Harvest)** o **spear phishing (Attachment)** , fare clic su **Attack Details**.

   Non importa dove creare il modello. Le opzioni disponibili nel modello sono uguali per entrambi i tipi di attacchi di phishing.

3. Nella pagina dei **Dettagli sull'attacco** visualizzata, nella sezione **modelli di phishing** , nell'area **Crea modelli** fare clic su **nuovo modello**.

4. La procedura guidata **Configura modello di phishing** viene avviata in un nuovo riquadro a comparsa. Nel passaggio **iniziale** , immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti**.

5. Nel passaggio **Configure email details** , configurare le seguenti impostazioni:

   - **From (Name)** : il nome visualizzato utilizzato per il mittente del messaggio.

   - **From (posta elettronica)** : l'indirizzo di posta elettronica del mittente.

   - **URL del server di accesso di phishing** : fare clic sul menu a discesa e selezionare uno degli URL disponibili nell'elenco. Questo è l'URL a cui gli utenti saranno tentati di fare clic. Le opzioni disponibili sono:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Tutti gli URL sono intenzionalmente http, non HTTPS.
     >
     > - Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri. Controllare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.

   - **URL della pagina di destinazione personalizzata** : immettere una pagina di destinazione facoltativa in cui gli utenti vengono eseguiti se fanno clic sul collegamento di phishing e immettono le proprie credenziali. Questo collegamento sostituisce la pagina di destinazione predefinita. Ad esempio, se si dispone di un training di sensibilizzazione interno, è possibile specificare l'URL qui.

   - **Categoria** : attualmente, questa impostazione non viene utilizzata (qualsiasi elemento immesso viene ignorato).

   - **Subject** : il campo **Subject** del messaggio di posta elettronica.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio di creazione della **posta elettronica** creare il corpo del messaggio di posta elettronica. È possibile utilizzare la scheda **posta elettronica** (un editor HTML RTF) oppure la scheda **origine** (codice HTML non elaborato).

   La formattazione HTML può essere semplice o complessa come è necessario. È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.

   - `${username}` inserisce il nome del destinatario.

   - `${loginserverurl}` inserisce il valore dell' **URL del server di accesso di phishing** dal passaggio precedente.

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nel passaggio **conferma** fare clic su **fine**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Passaggio 2: creare e avviare la campagna di phishing Spear

1. Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.

2. Nella pagina **simula attacchi** fare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:

   - Nella sezione **spear phishing (raccolta credenziali)** fare clic su **Launch Attack** o fare clic su Attack **Details** \> **Launch Attack**.

   - Nella sezione **spear phishing (Attachment)** , fare clic su **Launch Attack** o fare clic su Attack **Details** \> **Launch Attack**.

3. La procedura guidata **Configura attacco di phishing** viene avviata in un nuovo riquadro a comparsa. Nel passaggio **iniziale** eseguire una delle operazioni seguenti:

   - Nella casella **nome** immettere un nome visualizzato univoco per la campagna. Non fare clic su **Usa modello** perché verrà creato il messaggio di posta elettronica in un secondo momento nella procedura guidata.

   - Fare clic su **Usa modello** e selezionare un modello di posta elettronica incorporato o personalizzato. Dopo aver selezionato il modello, la casella **nome** viene riempita automaticamente in base al modello, ma è possibile modificarne il nome.

   ![Pagina iniziale di phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nel passaggio **destinatari di destinazione** eseguire una delle operazioni seguenti:

   - Fare **clic su Rubrica per** selezionare i destinatari (utenti o gruppi) per la campagna. Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online. Se si fa clic su **Filtra** e **applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.

   - Fare clic su **Importa** quindi **importazione file** per importare un valore separato da virgole (CSV) o un file di indirizzi di posta elettronica separato da una riga. Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **Configure email details** , configurare le seguenti impostazioni:

   Se nel passaggio **iniziale** è stato selezionato un modello, la maggior parte di questi valori è già configurata, ma è possibile modificarli.

   - **From (Name)** : il nome visualizzato utilizzato per il mittente del messaggio.

   - **From (posta elettronica)** : l'indirizzo di posta elettronica del mittente. È possibile immettere un indirizzo di posta elettronica reale o fasullo dal dominio di posta elettronica dell'organizzazione oppure è possibile immettere un indirizzo di posta elettronica esterno reale o fasullo. Un indirizzo di posta elettronica del mittente valido dell'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.

   - **URL del server di accesso di phishing** : fare clic sul menu a discesa e selezionare uno degli URL disponibili nell'elenco. Questo è l'URL a cui gli utenti saranno tentati di fare clic. Le opzioni disponibili sono:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Tutti gli URL sono intenzionalmente http, non HTTPS.
     >
     > - Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri. Controllare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.
     >
     > - È necessario selezionare un URL. Per le campagne di **phishing (Attachment)** , è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un collegamento **che** un allegato).

   - **Tipo di allegato** : questa impostazione è disponibile solo nelle campagne di **phishing (allegato) di Spear** . Fare clic sull'elenco a discesa e selezionare **. DOCX** o **. File PDF** dall'elenco.

   - **Nome allegato** : questa impostazione è disponibile solo nelle campagne di **phishing (allegato) di Spear** . Immettere un nome di file per l'allegato. docx o. pdf.

   - **URL della pagina di destinazione personalizzata** : immettere una pagina di destinazione facoltativa in cui gli utenti vengono eseguiti se fanno clic sul collegamento di phishing e immettono le proprie credenziali. Questo collegamento sostituisce la pagina di destinazione predefinita. Ad esempio, se si dispone di un training di sensibilizzazione interno, è possibile specificare l'URL qui.

   - **Subject** : il campo **Subject** del messaggio di posta elettronica.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio di creazione della **posta elettronica** creare il corpo del messaggio di posta elettronica. Se nel passaggio **iniziale** è stato selezionato un modello, il corpo del messaggio è già configurato, ma è possibile personalizzarlo. È possibile utilizzare la scheda **posta elettronica** (un editor HTML RTF) oppure la scheda **origine** (codice HTML non elaborato).

   La formattazione HTML può essere semplice o complessa come è necessario. È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.

   - `${username}` inserisce il nome del destinatario.

   - `${loginserverurl}` inserisce il valore dell' **URL del server di accesso di phishing** .

   Per le campagne di **phishing (allegato)** , è necessario rimuovere il collegamento dal corpo del messaggio (in caso contrario, il messaggio conterrà sia un collegamento **che** un allegato e i collegamenti non vengono registrati in una campagna di allegato).

   ![Comporre il corpo della posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nel passaggio **conferma** fare clic su **fine** per avviare la campagna. Il messaggio di phishing viene recapitato ai destinatari mirati.

## <a name="password-attack-campaigns"></a>Campagne di attacco tramite password

Un *attacco* per la password cerca di indovinare le password per gli account utente di un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account validi.

In Attack Simulator, sono disponibili due diversi tipi di campagne di attacco per la password per testare la complessità delle password degli utenti:

- **Password forza bruta (attacco dizionario)** : una *forza bruta* o un attacco del *dizionario* utilizza un file di dizionario di parole chiave di grandi dimensioni in un account utente con la speranza che uno di essi funzioni (molte password su un account). Gli errori di blocco delle password non corretti consentono di scoraggiare gli attacchi di password Brute.

  Per l'attacco del dizionario, è possibile specificare una o più password da provare (immessa manualmente o in un file caricato) ed è possibile specificare uno o più utenti.

- **Attacco spray** per la password: un attacco *spray* per la password utilizza la stessa password accuratamente considerata rispetto A un elenco di account utente (una password per molti account). Gli attacchi spray per la password sono più difficili da rilevare rispetto agli attacchi delle password per la forza bruta (la probabilità che il successo aumenti quando un utente malintenzionato cerca una password tra decine o centinaia di account senza il rischio di inciampare nel blocco della password errata dell'utente).

  Per l'attacco spray per la password, è possibile specificare solo una password da provare ed è possibile specificare uno o più utenti.

> [!NOTE]
> Gli attacchi tramite password in Attack Simulator passano il nome utente e le richieste di autenticazione di base delle password a un endpoint, in modo che funzionino anche con gli altri metodi (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via). Per gli utenti che dispongono di un Master abilitato, anche se l'attacco della password tenta la password effettiva, il tentativo si registrerà sempre come un errore (in altre parole, gli utenti dell'AMF non verranno mai visualizzati nel conteggio dei **tentativi riusciti** della campagna). Questo è il risultato previsto. L'AMF è un metodo principale che consente di proteggere gli attacchi delle password.

### <a name="create-and-launch-a-password-attack-campaign"></a>Creare e avviare una campagna di attacco tramite password

1. Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.

2. Nella pagina **simula attacchi** fare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:

   - Nella sezione **password forza bruta (attacco dizionario)** fare clic su **Avvia attacco** o fare clic su Attack **Details** \> **Launch Attack**.

   - nella sezione **attacco spray password** fare clic su **Launch Attack** o su Attack **Details** \> **Launch Attack**.

3. La procedura guidata **Configura attacco password** viene avviata in un nuovo riquadro a comparsa. Nel passaggio **iniziale** , immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti**.

4. Nel passaggio **degli utenti di destinazione** , eseguire una delle operazioni seguenti:

   - Fare **clic su Rubrica per** selezionare i destinatari (utenti o gruppi) per la campagna. Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online. Se si fa clic su **Filtra** e **applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.

   - Fare clic su **Importa** quindi **importazione file** per importare un valore separato da virgole (CSV) o un file di indirizzi di posta elettronica separato da una riga. Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **scegliere le impostazioni di attacco** scegliere le operazioni da eseguire in base al tipo di campagna:

   - **Password forza bruta (attacco dizionario)** : eseguire una delle operazioni seguenti:

     - **Immettere le password manualmente** : nella casella **premere INVIO per aggiungere una password** digitare una password e quindi premere INVIO. Ripetere questo passaggio tutte le volte necessarie.

     - **Caricare password da un file di dizionario** : fare clic su **carica** per importare un file di testo esistente che contiene una password su ogni riga e un'ultima riga vuota. Il file di testo deve avere una dimensione di 10 MB o inferiore e non può contenere più di 30000 password.

   - **Attacco spray** per la password: nelle **password da utilizzare nella casella attacco** , immettere una password.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio **conferma** fare clic su **fine** per avviare la campagna. Le password specificate sono state provate per gli utenti specificati.

## <a name="view-campaign-results"></a>Visualizzare i risultati della campagna

Dopo aver avviato una campagna, è possibile controllare lo stato e i risultati della pagina principale degli **attacchi simulati** .

Le campagne attive visualizzeranno una barra di stato, un valore percentuale completato e il numero "(utenti completati) di (utenti totali)". Se si fa clic sul pulsante **Aggiorna** , verrà aggiornato lo stato di avanzamento di qualsiasi campagna attiva. È inoltre possibile fare clic su **termina** per arrestare una campagna attiva.

Al termine della campagna, lo stato cambia in **attacco completato**. È possibile visualizzare i risultati della campagna eseguendo una delle operazioni seguenti:

- Nella pagina simulazione principale degli **attacchi** , fare clic su **Visualizza report** sotto il nome della campagna.

- Nella pagina simulazione principale degli **attacchi** , fare clic su **attacco dettagli** nella sezione relativa al tipo di attacco. Nella pagina dei **Dettagli sull'attacco** che viene visualizzata, selezionare la campagna nella sezione cronologia degli **attacchi** .

Una delle azioni precedenti consentirà di utilizzare una pagina denominata **Dettagli attacco**. Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Risultati della campagna Spear phishing (Harvest Credentials)

Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti designati**

- **Tentativi riusciti** : il numero di utenti che hanno fatto clic sul collegamento **e** hanno immesso le proprie credenziali ( *qualsiasi* nome utente e valore password).

- **Tasso di successo globale** : percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.

- Più **veloce fare clic su** : quanto tempo è stato necessario per il primo utente per fare clic sul collegamento dopo aver avviato la campagna.

- **Media clic** : la somma del tempo impiegato da tutti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.

- **Fare clic su velocità di successo** : percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento)/ **Totale utenti designati**.

- **Credenziali più veloci** : il tempo impiegato dal primo utente per immettere le credenziali dopo aver avviato la campagna.

- **Credenziali medie** : somma del tempo impiegato da tutti per immettere le proprie credenziali diviso per il numero di utenti che hanno immesso le proprie credenziali.

- **Tasso di successo della credenziale** : percentuale calcolata da (numero di utenti che hanno immesso le proprie credenziali)/ **Totale utenti designati**.

- Grafico a barre che Visualizza il **collegamento selezionato** e i numeri di **credenziale forniti** al giorno.

- Grafico a cerchio che Visualizza il **collegamento fatto clic** , **credenziali fornite** e **Nessuna** percentuale per la campagna.

- Nella sezione **utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:

  - L'indirizzo di posta elettronica dell'utente

  - La data e l'ora in cui si è fatto clic sul collegamento.

  - L'indirizzo IP del client.

  - Dettagli sulla versione dell'utente di Windows e del Web browser.

  È possibile fare clic su **Esporta** per esportare i risultati in un file CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Risultati della campagna di phishing (allegato) Spear

Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti designati**

- **Tentativi riusciti** : il numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non conta).

- **Tasso di successo globale** : percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.

- **Intervallo di tempo di apertura più rapido** : il tempo impiegato dal primo utente per aprire l'allegato dopo aver avviato la campagna.

- **Intervallo di tempo di apertura medio** : la somma di quanto tempo ha impiegato tutti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.

- **Tasso di successo Open Attachment** : percentuale calcolata da (numero di utenti che hanno aperto l'allegato)/ **Totale utenti designati**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Risultati della campagna password forza bruta (attacco dizionario)

Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti designati**

- **Tentativi riusciti** : il numero di utenti che hanno trovato l'utilizzo di una delle password specificate.

- **Tasso di successo globale** : percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.

- La sezione **utenti compromessi** elenca gli indirizzi di posta elettronica degli utenti coinvolti. È possibile fare clic su **Esporta** per esportare i risultati in un file CSV.

### <a name="password-spray-attack-campaign-results"></a>Risultati della campagna di attacco a spruzzo di password

Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti designati**

- **Tentativi riusciti** : il numero di utenti che sono stati trovati a utilizzare la password specificata.

- **Tasso di successo globale** : percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.
