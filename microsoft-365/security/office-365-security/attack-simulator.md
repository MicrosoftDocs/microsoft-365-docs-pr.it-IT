---
title: Simulatore di attacchi in Microsoft Defender per Office 365
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
description: Gli amministratori possono imparare a usare il simulatore di attacchi per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9d3d55c17e5d77ee18bd822899fea2f64136e1a3
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233601"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Simulatore di attacchi in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a** [Microsoft Defender per Office 365 piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)

Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi e risposta alle [minacce,](office-365-ti.md)è possibile utilizzare il simulatore di attacchi nel Centro sicurezza & e conformità per eseguire scenari di attacco realistici nell'organizzazione. Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sulla linea di fondo. Leggi questo articolo per altre informazioni.

> [!NOTE]
> L'esperienza del simulatore di attacchi v1 è stata passata alla modalità di sola lettura e sostituita dal training del simulatore di attacco descritto in Introduzione all'uso della formazione per la simulazione [degli attacchi.](attack-simulation-training-get-started.md)
> La possibilità di avviare nuove simulazioni da questo sito è stata disabilitata. Tuttavia, è comunque possibile accedere ai report per le simulazioni eseguite per un periodo di 90 giorni dal 24 gennaio 2021.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>. Il simulatore  di attacco è disponibile nel \> **simulatore di attacco per la gestione delle minacce.** Vai direttamente al simulatore di attacco, apri <https://protection.office.com/attacksimulator> .

- Per ulteriori informazioni sulla disponibilità del simulatore di attacchi tra diversi abbonamenti a Microsoft 365, vedere Descrizione del servizio [Microsoft Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore** sicurezza. Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Il tuo account deve essere configurato per l'autenticazione a più fattori (MFA) per creare e gestire campagne in Simulatore di attacchi. Per istruzioni, vedere [Configurare l'autenticazione a più fattori.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)

- Le campagne di phishing raccoglieranno ed eelaborare gli eventi per 30 giorni. I dati cronologici della campagna saranno disponibili fino a 90 giorni dopo l'avvio della campagna.

- I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti per i servizi di Microsoft 365. Per ulteriori informazioni, vedere [Percorsi dei dati di Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)

- Non sono disponibili cmdlet di PowerShell corrispondenti per il simulatore di attacchi.

## <a name="spear-phishing-campaigns"></a>Campagne di phishing con phishing

*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili. *Il phishing* di phishing mirato è un attacco di phishing mirato che usa contenuti mirati e personalizzati appositamente personalizzati per i destinatari di destinazione (in genere, dopo la ricognizione sui destinatari da parte dell'autore dell'attacco).

Nel simulatore di attacchi sono disponibili due diversi tipi di campagne di phishing:

- **Spear phishing (raccolta di credenziali):** l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio. Se fa clic sul collegamento, viene richiesto di immettere le proprie credenziali. In caso contrario, vengono portati in una delle posizioni seguenti:

  - Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per il riconoscimento dei messaggi di phishing.

    ![Cosa viene visualizzato dagli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - Una pagina personalizzata (URL) specificata dall'utente.

- **Spear phishing (allegato):** l'attacco tenta di convincere i destinatari ad aprire un allegato .docx o .pdf nel messaggio. L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " , il messaggio viene visualizzato come un messaggio di posta elettronica recente \<Display Name\> aperto...".

> [!NOTE]
> Attualmente, le campagne di spear phishing nel simulatore di attacchi non scadono.

### <a name="create-a-spear-phishing-campaign"></a>Creare una campagna di phishing con phishing

Una parte importante di qualsiasi campagna di phishing è l'aspetto del messaggio di posta elettronica inviato ai destinatari di destinazione. Per creare e configurare il messaggio di posta elettronica, sono disponibili le opzioni seguenti:

- **Usa un modello di posta elettronica predefinito:** sono disponibili due modelli predefiniti: **Evaso** e Aggiornamento **paghe.** Puoi personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando crei e avvii la campagna.

- **Creare un modello di** posta elettronica riutilizzabile: dopo aver creato e salvato il modello di posta elettronica, è possibile usarlo di nuovo nelle future campagne di phishing di phishing. Puoi personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando crei e avvii la campagna.

- **Creare il messaggio di posta elettronica nella** procedura guidata: è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata durante la creazione e l'avvio della campagna di phishing.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Passaggio 1 (facoltativo): Creare un modello di posta elettronica personalizzato

Se si desidera utilizzare uno dei modelli predefiniti o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.

1. Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**

2. Nella pagina **Simulate attacks** fare clic su Attack **Details** nelle sezioni Spear **Phishing (Credentials Harvest)** o **Spear Phishing (Attachment).**

   Non importa dove si crea il modello. Le opzioni disponibili nel modello sono le stesse per entrambi i tipi di attacchi di phishing.

3. Nella pagina **Dettagli attacco** visualizzata, nell'area Crea  modelli della sezione Modelli di **phishing** fare clic su **Nuovo modello.**

4. La **procedura guidata Configura modello di** phishing viene avviata in un nuovo riquadro a comparsa. Nel passaggio **iniziale** immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti.**

5. Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:

   - **Da (nome):** nome visualizzato utilizzato per il mittente del messaggio.

   - **Da (posta elettronica):** indirizzo di posta elettronica del mittente.

   - **URL del server di accesso** phishing: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco. Questo è l'URL su cui gli utenti saranno tentati di fare clic. Le opzioni disponibili sono:

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
     > Un servizio di reputazione URL può identificare uno o più url come non sicuri. Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzarlo in una campagna di phishing.

   - **URL pagina di destinazione personalizzata:** immettere una pagina di destinazione facoltativa in cui gli utenti vengono presi se fanno clic sul collegamento di phishing e immettono le proprie credenziali. Questo collegamento sostituisce la pagina di destinazione predefinita. Ad esempio, se hai una formazione di sensibilizzazione interna, puoi specificare questo URL qui.

   - **Categoria:** attualmente questa impostazione non viene utilizzata (tutto ciò che immetti viene ignorato).

   - **Oggetto:** campo **Oggetto** del messaggio di posta elettronica.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio **Componi messaggio di posta** elettronica, creare il corpo del messaggio di posta elettronica. È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la scheda **Origine** (codice HTML non elaborato).

   La formattazione HTML può essere semplice o complessa come necessario. È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.

   - `${username}` inserisce il nome del destinatario.

   - `${loginserverurl}` inserisce il valore **URL del server** di accesso phishing del passaggio precedente.

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nel passaggio **Conferma** fare clic su **Fine.**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Passaggio 2: creare e avviare la campagna di phishing con phishing

1. Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**

2. Nella pagina **Simula attacchi** effettuare una delle seguenti selezioni in base al tipo di campagna che si desidera creare:

   - Nella sezione **Spear Phishing (Credentials Harvest)** fare clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**

   - Nella sezione **Spear Phishing (allegato),** fare clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**

3. La **procedura guidata Configura attacco di phishing** viene avviata in un nuovo riquadro a comparsa. Nel passaggio **Start** eseguire una delle operazioni seguenti:

   - Nella casella **Nome** immettere un nome visualizzato univoco per la campagna. Non fare clic su **Usa modello** perché il messaggio di posta elettronica verrà creato più avanti nella procedura guidata.

   - Fare **clic su Usa** modello e selezionare un modello di posta elettronica predefinito o personalizzato. Dopo aver selezionato il modello, la **casella Nome** viene compilata automaticamente in base al modello, ma è possibile modificare il nome.

   > [!div class="mx-imgBorder"]
   > ![Pagina iniziale phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nel passaggio **Destinatari di** destinazione eseguire una delle operazioni seguenti:

   - Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna. Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online. Se si fa **clic su Filtro** e **Applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.

   - Fare **clic su** Importa e quindi **importa** file per importare un valore con valori delimitati da virgole (CSV) o un file di indirizzi di posta elettronica separati da riga. Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:

   Se è stato selezionato un modello nel **passaggio Start,** la maggior parte di questi valori è già configurata, ma è possibile modificarli.

   - **Da (nome):** nome visualizzato utilizzato per il mittente del messaggio.

   - **Da (posta elettronica):** indirizzo di posta elettronica del mittente. È possibile immettere un indirizzo di posta elettronica reale o falso dal dominio di posta elettronica dell'organizzazione oppure un indirizzo di posta elettronica esterno reale o falso. Un indirizzo di posta elettronica del mittente valido dell'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.

   - **URL del server di accesso** phishing: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco. Questo è l'URL su cui gli utenti saranno tentati di fare clic. Le opzioni disponibili sono:

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
     > - Un servizio di reputazione URL può identificare uno o più url come non sicuri. Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzarlo in una campagna di phishing.
     >
     > - È necessario selezionare un URL. Per **le campagne di phishing** (allegato), è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un **collegamento** che un allegato).

   - **Tipo di allegato:** questa impostazione è disponibile solo nelle campagne **di phishing (allegato).** Fare clic sull'elenco a discesa e selezionare **. DOCX** o **. PDF** dall'elenco.

   - **Nome allegato:** questa impostazione è disponibile solo nelle campagne **di phishing (allegato).** Immettere un nome di file per l'allegato .docx o .pdf.

   - **URL pagina di destinazione personalizzata:** immettere una pagina di destinazione facoltativa in cui gli utenti vengono presi se fanno clic sul collegamento di phishing e immettono le proprie credenziali. Questo collegamento sostituisce la pagina di destinazione predefinita. Ad esempio, se hai una formazione di sensibilizzazione interna, puoi specificare questo URL qui.

   - **Oggetto:** campo **Oggetto** del messaggio di posta elettronica.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio **Componi messaggio di posta** elettronica, creare il corpo del messaggio di posta elettronica. Se è stato selezionato un modello nel **passaggio Start,** il corpo del messaggio è già configurato, ma è possibile personalizzarlo. È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la scheda **Origine** (codice HTML non elaborato).

   La formattazione HTML può essere semplice o complessa come necessario. È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.

   - `${username}` inserisce il nome del destinatario.

   - `${loginserverurl}`inserisce il valore **URL del server di accesso phishing.**

   Per le campagne di **spear phishing (allegato),** è necessario rimuovere il collegamento dal corpo  del messaggio (in caso contrario, il messaggio conterrà sia un collegamento che un allegato e i clic sul collegamento non vengono monitorati in una campagna allegato).

   > [!div class="mx-imgBorder"]
   > ![Comporre il corpo del messaggio di posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna. Il messaggio di phishing viene recapitato ai destinatari di destinazione.

## <a name="password-attack-campaigns"></a>Campagne di attacco con password

Un *attacco con password* tenta di indovinare le password per gli account utente in un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account utente validi.

Nel simulatore di attacchi sono disponibili due diversi tipi di campagne di attacco con password per testare la complessità delle password degli utenti:

- **Brute force password (attacco** con dizionario):  un attacco di forza *bruta* o dizionario usa un file di dizionario di grandi dimensioni di password su un account utente con la volontà che una di esse funzioni (molte password su un account). I blocchi delle password non corretti consentono di dissuadere gli attacchi di forza bruta alle password.

  Per l'attacco con dizionario, è possibile specificare una o più password da provare (immesse manualmente o in un file caricato) e specificare uno o più utenti.

- **Attacco con password spray:** un attacco *di tipo password spray* utilizza la stessa password considerata con attenzione rispetto a un elenco di account utente (una password contro molti account). Gli attacchi di tipo password spray sono più difficili da rilevare rispetto agli attacchi di forza bruta delle password (la probabilità di successo aumenta quando un utente malintenzionato tenta una password su decine o centinaia di account senza il rischio di inciampare nel blocco non corretto della password dell'utente).

  Per l'attacco di tipo password spray, è possibile specificare una sola password da provare e uno o più utenti.

> [!NOTE]
> Gli attacchi alle password in Attack Simulator passano le richieste di autenticazione di base di nome utente e password a un endpoint, quindi funzionano anche con altri metodi di autenticazione (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via). Per gli utenti che hanno abilitato l'autenticazione a più fattori, anche se l'attacco con password tenta la  password effettiva, il tentativo verrà sempre registrato come errore (in altre parole, gli utenti MFA non verranno mai visualizzati nel conteggio tentativi riusciti della campagna). Questo è il risultato previsto. L'autenticazione a più fattori è un metodo principale per la protezione da attacchi con password.

### <a name="create-and-launch-a-password-attack-campaign"></a>Creare e avviare una campagna di attacco con password

1. Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**

2. Nella pagina **Simula attacchi** effettuare una delle seguenti selezioni in base al tipo di campagna che si desidera creare:

   - Nella sezione **Brute Force Password (Dictionary Attack)** fai clic su **Launch Attack** o **su Attack Details** Launch \> **Attack.**

   - nella sezione **Attacco con password spray,** fare clic **su Launch Attack** o su **Attack Details** \> **Launch Attack.**

3. La **procedura guidata Configura attacco password** viene avviata in un nuovo riquadro a comparsa. Nel passaggio **iniziale** immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti.**

4. Nel passaggio **Utenti di** destinazione eseguire una delle operazioni seguenti:

   - Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna. Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online. Se si fa **clic su Filtro** e **Applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.

   - Fare **clic su** Importa e quindi **importa** file per importare un valore con valori delimitati da virgole (CSV) o un file di indirizzi di posta elettronica separati da riga. Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **Scegliere le impostazioni di attacco** scegliere cosa fare in base al tipo di campagna:

   - **Brute Force Password (Dictionary Attack):** eseguire una delle operazioni seguenti:

     - **Immettere manualmente le password:** nella casella Premere INVIO per aggiungere una **password,** digitare una password e quindi premere INVIO. Ripetere questo passaggio tutte le volte necessarie.

     - **Caricare le password da un file di dizionario:** fare clic su Carica per importare un file di testo esistente contenente una password per ogni riga e un'ultima riga vuota.  Le dimensioni del file di testo devono essere pari o inferiori a 10 MB e non possono contenere più di 30000 password.

   - **Attacco con password spray:** nelle **password da** usare nella casella di attacco, immettere una password.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna. Le password specificate vengono tentate per gli utenti specificati.

## <a name="view-campaign-results"></a>Visualizzare i risultati della campagna

Dopo aver avviato una campagna, puoi controllare l'avanzamento e i risultati nella pagina principale **Simula attacchi.**

Le campagne attive mostreranno una barra di stato, un valore percentuale completato e il conteggio "(utenti completati) di (utenti totali)". Facendo clic **sul** pulsante Aggiorna viene aggiornato lo stato di avanzamento delle campagne attive. Puoi anche fare clic su **Termina** per interrompere una campagna attiva.

Al termine della campagna, lo stato cambia in **Attacco completato.** Puoi visualizzare i risultati della campagna eseguendo una delle azioni seguenti:

- Nella pagina principale **Simulate attacks** fai clic **su View Report** sotto il nome della campagna.

- Nella pagina principale **Simulate attacks** fare clic **su Attack Details** nella sezione relativa al tipo di attacco. Nella pagina **dei dettagli dell'attacco** che si apre, selezionare la campagna nella sezione **Cronologia** attacchi.

Una delle azioni precedenti consente di accedere a una pagina denominata **Dettagli attacco.** Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Risultati della campagna spear phishing (Credentials Harvest)

Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti a cui è stata destinata**

- **Tentativi riusciti:** numero di utenti che hanno fatto clic sul **collegamento** e immesso le proprie credenziali *(qualsiasi valore* di nome utente e password).

- **Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**

- **Clic più rapido:** tempo impiegato dal primo utente per fare clic sul collegamento dopo l'avvio della campagna.

- **Media clic**: somma del tempo impiegato da tutti gli utenti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.

- **Click Success Rate**: percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento) / **Totale utenti mirati.**

- **Credenziali più veloci:** tempo impiegato dal primo utente per immettere le credenziali dopo l'avvio della campagna.

- **Media credenziali**: somma del tempo impiegato da tutti per immettere le credenziali diviso per il numero di utenti che hanno immesso le credenziali.

- **Percentuale di successo delle** credenziali : percentuale calcolata da (numero di utenti che hanno immesso le credenziali) / **Totale utenti di destinazione.**

- Grafico a barre che mostra i **numeri di** collegamento su cui è stato fatto clic e i numeri forniti per le **credenziali** al giorno.

- Grafico a cerchi che mostra le percentuali **di** clic **sul** collegamento, le credenziali fornite e **nessuna** percentuale per la campagna.

- Nella **sezione Utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:

  - L'indirizzo di posta elettronica dell'utente

  - Data/ora in cui hanno fatto clic sul collegamento.

  - L'indirizzo IP del client.

  - Dettagli sulla versione di Windows e del Web browser dell'utente.

  È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Risultati della campagna di phishing (allegato)

Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti a cui è stata destinata**

- **Tentativi riusciti**: numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non viene conteggiato).

- **Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**

- **Tempo di apertura dell'allegato** più rapido: tempo impiegato dal primo utente per aprire l'allegato dopo l'avvio della campagna.

- **Tempo medio di apertura** dell'allegato: somma del tempo impiegato da tutti gli utenti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.

- **Percentuale di successo apertura** allegato : percentuale calcolata da (numero di utenti che hanno aperto l'allegato) / **Totale utenti destinatari.**

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Risultati della campagna Brute Force Password (attacco con dizionario)

Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti a cui è stata destinata**

- **Tentativi** riusciti: numero di utenti che hanno rilevato l'utilizzo di una delle password specificate.

- **Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**

- Nella **sezione Utenti compromessi** sono elencati gli indirizzi di posta elettronica degli utenti interessati. È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.

### <a name="password-spray-attack-campaign-results"></a>Risultati della campagna di attacco con password spray

Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:

- Durata (data/ora di inizio e data/ora di fine) della campagna.

- **Totale utenti a cui è stata destinata**

- **Tentativi riusciti**: numero di utenti che hanno rilevato l'utilizzo della password specificata.

- **Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**
