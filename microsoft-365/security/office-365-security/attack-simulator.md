---
title: Simulatore di attacco in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare Il simulatore di attacco per eseguire attacchi simulati di phishing e password nelle organizzazioni Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 03e6c0077f13c85bfd20ac0583b64ce29e2535a1
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878677"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Simulatore di attacco in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a** [Microsoft Defender per Office 365 piano 2](defender-for-office-365.md)

Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi delle minacce e [risposta,](office-365-ti.md)è possibile utilizzare Simulatore di attacco nel Centro sicurezza & conformità per eseguire scenari di attacco realistici nell'organizzazione. Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sulla linea di fondo. Leggi questo articolo per altre informazioni.

> [!NOTE]
>
> Il simulatore di attacco come descritto in questo articolo è ora di sola lettura ed è stato sostituito dal **training** di simulazione degli attacchi nel nodo di collaborazione **Email &** nel portale di Microsoft 365 Defender all'indirizzo <https://security.microsoft.com> . Per ulteriori informazioni, vedere [Introduzione all'uso del training di simulazione degli attacchi.](attack-simulation-training-get-started.md)
>
> La possibilità di avviare nuove simulazioni da questa versione di Attack Simulator è stata disabilitata. È comunque possibile accedere ai report fino al 24 aprile 2021.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>. Il simulatore di attacco è disponibile **in Threat management** Attack \> **simulator**. Per passare direttamente al simulatore di attacco, apri <https://protection.office.com/attacksimulator> .

- Per altre informazioni sulla disponibilità di Attack Simulator tra diverse sottoscrizioni Microsoft 365, vedi [Microsoft Defender per](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)la descrizione Office 365 servizio .

- È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore** sicurezza. Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- L'account deve essere configurato per l'autenticazione a più fattori (MFA) per creare e gestire campagne in Attack Simulator. Per istruzioni, vedere [Configurare l'autenticazione a più fattori.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Il simulatore di attacco funziona solo sulle cassette postali basate sul cloud.

- Le campagne di phishing raccoglieranno ed eelaborare gli eventi per 30 giorni. I dati cronologici della campagna saranno disponibili fino a 90 giorni dopo l'avvio della campagna.

- I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti Microsoft 365 servizi. Per ulteriori informazioni, [vedere Microsoft 365 di dati](../../enterprise/o365-data-locations.md).

- Non sono disponibili cmdlet di PowerShell corrispondenti per Il simulatore di attacco.

## <a name="spear-phishing-campaigns"></a>Campagne di spear phishing

*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili. *Il spear phishing* è un attacco di phishing mirato che usa contenuti mirati e personalizzati appositamente personalizzati per i destinatari di destinazione (in genere, dopo la ricognizione dei destinatari da parte dell'autore dell'attacco).

In Attack Simulator sono disponibili due diversi tipi di campagne di spear phishing:

- **Spear phishing (raccolta delle credenziali):** l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio. Se fa clic sul collegamento, viene richiesto di immettere le proprie credenziali. In caso contrario, vengono portati in una delle posizioni seguenti:

  - Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per riconoscere i messaggi di phishing.

    ![Cosa vedono gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - Pagina personalizzata (URL) specificata.

- **Spear phishing (allegato):** l'attacco tenta di convincere i destinatari ad aprire un .docx o .pdf allegato nel messaggio. L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " , questo messaggio viene visualizzato come un messaggio di posta elettronica recente \<Display Name\> aperto...".

> [!NOTE]
> Attualmente, le campagne di spear phishing in Attack Simulator non scadono.

### <a name="create-a-spear-phishing-campaign"></a>Creare una campagna di spear phishing

Una parte importante di qualsiasi campagna di spear phishing è l'aspetto del messaggio di posta elettronica inviato ai destinatari di destinazione. Per creare e configurare il messaggio di posta elettronica, sono disponibili le opzioni seguenti:

- **Usa un modello di posta elettronica predefinito:** sono disponibili due modelli predefiniti: **Giveaway per** premi e **aggiornamento delle buste paga.** È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando si crea e si avvia la campagna.

- **Creare un modello di posta** elettronica riutilizzabile: dopo aver creato e salvato il modello di posta elettronica, è possibile utilizzarlo di nuovo nelle future campagne di spear phishing. È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando si crea e si avvia la campagna.

- **Creare il messaggio di posta elettronica nella** procedura guidata: è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata durante la creazione e l'avvio della campagna di spear phishing.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Passaggio 1 (facoltativo): creare un modello di posta elettronica personalizzato

Se si desidera utilizzare uno dei modelli predefiniti o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.

1. Nel Centro sicurezza & conformità passare a **Gestione delle** minacce \> **Simulatore di attacco.**

2. Nella sezione **Spear** **Phishing (Credentials Harvest)** o **Spear Phishing (allegato)** della pagina Simula attacchi fare clic su **Dettagli attacco.**

   Non importa dove si crea il modello. Le opzioni disponibili nel modello sono le stesse per entrambi i tipi di attacchi di phishing.

3. Nella pagina **Dettagli attacco** visualizzata, nell'area Crea  modelli della sezione Modelli di **phishing** fare clic su **Nuovo modello.**

4. La **procedura guidata Configura modello** di phishing viene avviata in un nuovo riquadro a comparsa. Nel passaggio **Start** immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti.**

5. Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:

   - **From (Name):** nome visualizzato utilizzato per il mittente del messaggio.

   - **From (Email)**: Indirizzo di posta elettronica del mittente.

   - **URL server di accesso phishing**: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco. Questo è l'URL su cui gli utenti saranno tentati di fare clic. Le opzioni disponibili sono:

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
     > Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri. Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.

   - **URL pagina di destinazione personalizzato:** immettere una pagina di destinazione facoltativa in cui vengono presi gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali. Questo collegamento sostituisce la pagina di destinazione predefinita. Ad esempio, se hai un training di sensibilizzazione interno, puoi specificare questo URL qui.

   - **Categoria**: attualmente questa impostazione non viene utilizzata (tutto ciò che viene immesso viene ignorato).

   - **Subject**: Campo **Subject** del messaggio di posta elettronica.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio **Componi messaggio di** posta elettronica creare il corpo del messaggio di posta elettronica. È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la **scheda Origine** (codice HTML non elaborato).

   La formattazione HTML può essere semplice o complessa come necessario. È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.

   - `${username}` inserisce il nome del destinatario.

   - `${loginserverurl}` inserisce il **valore URL del server** di accesso phishing del passaggio precedente.

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nel passaggio **Conferma** fare clic su **Fine.**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Passaggio 2: creare e avviare la campagna di spear phishing

1. Nel Centro sicurezza & conformità passare a **Gestione delle** minacce \> **Simulatore di attacco.**

2. Nella pagina **Simula attacchi** effettuare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:

   - Nella sezione **Spear Phishing (Credentials Harvest)** fai clic su **Launch Attack** o fai clic su **Attack Details** Launch \> **Attack.**

   - Nella sezione **Spear Phishing (allegato)** fai clic su **Avvia attacco** o fai clic su **Dettagli attacco** Launch \> **Attack**.

3. La **procedura guidata Configura attacco di** phishing viene avviata in un nuovo riquadro a comparsa. Nel passaggio **Start** eseguire una delle operazioni seguenti:

   - Nella casella **Nome** immettere un nome visualizzato univoco per la campagna. Non fare clic su **Usa modello** perché il messaggio di posta elettronica verrà creato più avanti nella procedura guidata.

   - Fare **clic su Usa** modello e selezionare un modello di posta elettronica predefinito o personalizzato. Dopo aver selezionato il modello, la **casella Nome** viene compilata automaticamente in base al modello, ma è possibile modificare il nome.

   > [!div class="mx-imgBorder"]
   > ![Pagina iniziale phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nel passaggio **Destinatari di** destinazione eseguire una delle operazioni seguenti:

   - Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna. Ogni destinatario di destinazione deve disporre di Exchange Online cassetta postale. Se si fa **clic su Filtro** e **Applica** senza immettere criteri di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.

   - Fare **clic su** **Importa, quindi su** Importazione file per importare un valore delimitato da virgole (CSV) o un file di indirizzi di posta elettronica separati da righe. Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:

   Se è stato selezionato un modello nel **passaggio Start,** la maggior parte di questi valori è già configurata, ma è possibile modificarli.

   - **From (Name):** nome visualizzato utilizzato per il mittente del messaggio.

   - **From (Email)**: Indirizzo di posta elettronica del mittente. È possibile immettere un indirizzo di posta elettronica reale o falso dal dominio di posta elettronica dell'organizzazione oppure un indirizzo di posta elettronica esterno reale o falso. Un indirizzo di posta elettronica del mittente valido dall'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.

   - **URL server di accesso phishing**: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco. Questo è l'URL su cui gli utenti saranno tentati di fare clic. Le opzioni disponibili sono:

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
     > - Tutti gli URL sono intenzionalmente http, non https.
     >
     > - Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri. Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.
     >
     > - È necessario selezionare un URL. Per **le campagne di spear phishing (allegato),** è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un **collegamento** che un allegato).

   - **Tipo di allegato:** questa impostazione è disponibile solo nelle campagne **di spear phishing (allegato).** Fare clic sull'elenco a **discesa e.DOCX** o **.PDF** dall'elenco.

   - **Nome allegato**: questa impostazione è disponibile solo nelle campagne **di spear phishing (allegato).** Immettere un nome di file per .docx o .pdf allegato.

   - **URL pagina di destinazione personalizzato:** immettere una pagina di destinazione facoltativa in cui vengono presi gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali. Questo collegamento sostituisce la pagina di destinazione predefinita. Ad esempio, se hai un training di sensibilizzazione interno, puoi specificare questo URL qui.

   - **Subject**: Campo **Subject** del messaggio di posta elettronica.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio **Componi messaggio di** posta elettronica creare il corpo del messaggio di posta elettronica. Se è stato selezionato un modello nel **passaggio Start,** il corpo del messaggio è già configurato, ma è possibile personalizzarlo. È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la **scheda Origine** (codice HTML non elaborato).

   La formattazione HTML può essere semplice o complessa come necessario. È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.

   - `${username}` inserisce il nome del destinatario.

   - `${loginserverurl}` inserisce il valore **URL del server di accesso** phishing.

   Per le campagne **di spear phishing (allegato),** è consigliabile rimuovere il collegamento dal  corpo del messaggio (in caso contrario, il messaggio conterrà sia un collegamento che un allegato e i clic sui collegamenti non vengono monitorati in una campagna allegato).

   > [!div class="mx-imgBorder"]
   > ![Componi corpo del messaggio di posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna. Il messaggio di phishing viene recapitato ai destinatari di destinazione.

## <a name="password-attack-campaigns"></a>Campagne di attacco con password

Un *attacco tramite password* tenta di indovinare le password per gli account utente in un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account utente validi.

In Attack Simulator sono disponibili due diversi tipi di campagne di attacco delle password per testare la complessità delle password degli utenti:

- **Brute force password (attacco dizionario):** un  attacco di forza *bruta* o dizionario usa un file di dizionario di grandi dimensioni di password su un account utente con la speranza che una di esse funzioni (molte password su un account). I blocchi delle password non corretti consentono di scoraggiare gli attacchi di forza bruta delle password.

  Per l'attacco al dizionario, puoi specificare una o più password da provare (immesse manualmente o in un file caricato) e puoi specificare uno o più utenti.

- **Attacco con spray per password**: un attacco con *spray* per password usa la stessa password attentamente considerata per un elenco di account utente (una password per molti account). Gli attacchi di tipo password spray sono più difficili da rilevare rispetto agli attacchi di forza bruta delle password (la probabilità di successo aumenta quando un utente malintenzionato tenta una password su decine o centinaia di account senza il rischio di inciampare nel blocco non corretto della password dell'utente).

  Per l'attacco con spray per le password, è possibile specificare una sola password da provare e uno o più utenti.

> [!NOTE]
> Gli attacchi alle password in Attack Simulator passano le richieste di autenticazione di base e nome utente a un endpoint, quindi funzionano anche con altri metodi di autenticazione (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via). Per gli utenti con MFA abilitata, anche se l'attacco con password tenta la password effettiva, il tentativo  verrà sempre registrato come errore (in altre parole, gli utenti MFA non verranno mai visualizzati nel conteggio dei tentativi riusciti della campagna). Questo è il risultato previsto. L'autenticazione a più fattori è un metodo principale per proteggere dagli attacchi delle password.

### <a name="create-and-launch-a-password-attack-campaign"></a>Creare e avviare una campagna di attacco tramite password

1. Nel Centro sicurezza & conformità passare a **Gestione delle** minacce \> **Simulatore di attacco.**

2. Nella pagina **Simula attacchi** effettuare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:

   - Nella sezione **Brute Force Password (Dictionary Attack)** fai clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**

   - nella sezione **Attacco spray password** fare clic su Avvia **attacco** o su **Dettagli attacco** \> **Attacco.**

3. La **procedura guidata Configura attacco password** viene avviata in un nuovo riquadro a comparsa. Nel passaggio **Start** immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti.**

4. Nel passaggio **Utenti di** destinazione eseguire una delle operazioni seguenti:

   - Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna. Ogni destinatario di destinazione deve disporre di Exchange Online cassetta postale. Se si fa **clic su Filtro** e **Applica** senza immettere criteri di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.

   - Fare **clic su** **Importa, quindi su** Importazione file per importare un valore delimitato da virgole (CSV) o un file di indirizzi di posta elettronica separati da righe. Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **Scegliere le impostazioni di** attacco scegliere l'operazione da eseguire in base al tipo di campagna:

   - **Brute Force Password (Dictionary Attack):** eseguire una delle operazioni seguenti:

     - **Immettere manualmente le password:** nella **casella Premere INVIO per aggiungere** una password digitare una password e quindi premere INVIO. Ripetere questo passaggio tutte le volte necessarie.

     - **Upload password da** un file di  dizionario: fare clic su Upload per importare un file di testo esistente contenente una password in ogni riga e un'ultima riga vuota. Le dimensioni del file di testo devono essere pari o inferiori a 10 MB e non possono contenere più di 30000 password.

   - **Attacco con spray per la** password : in Le password da usare nella casella **di** attacco immettere una password.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna. Le password specificate vengono tentate per gli utenti specificati.

## <a name="view-campaign-results"></a>Visualizzare i risultati della campagna

Dopo aver avviato una campagna, puoi controllare l'avanzamento e i risultati nella pagina **principale Simula attacchi.**

Le campagne attive mostreranno una barra di stato, un valore percentuale completato e il conteggio "(utenti completati) di (utenti totali)". Facendo clic **sul** pulsante Aggiorna verrà aggiornato lo stato di avanzamento di tutte le campagne attive. Puoi anche fare clic **su Termina** per interrompere una campagna attiva.

Al termine della campagna, lo stato viene modificato in **Attacco completato.** È possibile visualizzare i risultati della campagna eseguendo una delle operazioni seguenti:

- Nella pagina principale **Simula attacchi** fare clic su **Visualizza report** sotto il nome della campagna.

- Nella pagina principale **Simula attacchi** fare clic su **Dettagli** attacco nella sezione relativa al tipo di attacco. Nella pagina **Dettagli attacco** visualizzata selezionare la campagna nella sezione **Cronologia** attacchi.

Una delle azioni precedenti consente di accedere a una pagina denominata **Dettagli attacco.** Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Risultati della campagna Spear Phishing (Credentials Harvest)

Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti di destinazione**

- **Tentativi riusciti**: numero di utenti che hanno fatto clic sul **collegamento** e hanno immesso le proprie credenziali *(qualsiasi valore* di nome utente e password).

- **Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**

- **Clic più rapido:** tempo impiegato dal primo utente per fare clic sul collegamento dopo l'avvio della campagna.

- **Media clic**: somma del tempo impiegato da tutti gli utenti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.

- **Click Success Rate**: Percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento) / **Totale utenti mirati**.

- **Credenziali più veloci**: tempo impiegato dal primo utente per immettere le credenziali dopo l'avvio della campagna.

- **Credenziali medie**: somma del tempo impiegato da tutti per immettere le credenziali diviso per il numero di utenti che hanno immesso le proprie credenziali.

- **Percentuale di successo delle** credenziali : percentuale calcolata da (numero di utenti che hanno immesso le credenziali) / **Totale utenti di destinazione.**

- Grafico a barre che mostra i **numeri di collegamento** su cui è stato fatto clic e i numeri forniti per le **credenziali** al giorno.

- Grafico a cerchi che mostra **le** percentuali Collegamento fatto **clic,** Credenziali fornite e **Nessuna** per la campagna.

- Nella **sezione Utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:

  - L'indirizzo di posta elettronica dell'utente

  - Data/ora in cui è stato fatto clic sul collegamento.

  - L'indirizzo IP del client.

  - Dettagli sulla versione dell'utente di Windows web browser.

  È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Risultati della campagna spear phishing (allegato)

Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti di destinazione**

- **Tentativi riusciti:** numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non viene conteggiato).

- **Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**

- **Tempo di apertura dell'allegato** più rapido: tempo impiegato dal primo utente per aprire l'allegato dopo l'avvio della campagna.

- **Tempo medio di apertura degli allegati**: somma del tempo impiegato da tutti gli utenti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.

- **Percentuale di esito positivo dell'apertura** degli allegati : percentuale calcolata da (numero di utenti che hanno aperto l'allegato) / **Totale utenti di destinazione.**

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Risultati della campagna Brute Force Password (Dictionary Attack)

Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti di destinazione**

- **Tentativi** riusciti: numero di utenti che sono stati trovati che utilizzano una delle password specificate.

- **Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**

- Nella **sezione Utenti compromessi** sono elencati gli indirizzi di posta elettronica degli utenti interessati. È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.

### <a name="password-spray-attack-campaign-results"></a>Risultati della campagna di attacco con spray per password

Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti di destinazione**

- **Tentativi riusciti**: numero di utenti che sono stati trovati che utilizzano la password specificata.

- **Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**
