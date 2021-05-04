---
title: Configurare un connettore per archiviare i dati di ICE Chat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati dallo strumento ICE Chat Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 958a6dde0a4f23933ef6328719fbf43265420c7c
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077301"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configurare un connettore per archiviare i dati di ICE Chat

Utilizzare un connettore nativo nel centro Microsoft 365 conformità per importare e archiviare i dati di chat dei servizi finanziari dallo strumento di collaborazione ICE Chat. Dopo aver configurato e configurato un connettore, si connette al sito FTP protetto (SFTP) ice chat dell'organizzazione una volta al giorno, converte il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali in Microsoft 365.

Dopo aver archiviato i dati della chat ICE nelle cassette postali degli utenti Microsoft 365, è possibile applicare ai dati di ICE Chat funzionalità di conformità come conservazione per controversia legale, eDiscovery, archiviazione, controllo, conformità delle comunicazioni e criteri di conservazione Microsoft 365. Ad esempio, è possibile cercare i messaggi di ICE Chat utilizzando la ricerca di contenuto o associare la cassetta postale che contiene i dati di ICE Chat a un responsabile in un caso Advanced eDiscovery caso. L'utilizzo di un connettore ice chat per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-ice-chat-data"></a>Panoramica dell'archiviazione dei dati di ICE Chat

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati della chat ICE in Microsoft 365.

![Flusso di lavoro di archiviazione ice chat](../media/ICEChatConnectorWorkflow.png)

1. L'organizzazione collabora con ICE Chat per configurare un sito ICE Chat SFTP. Sarà inoltre possibile utilizzare ICE Chat per configurare ICE Chat per copiare i messaggi di chat nel sito SFTP di ICE Chat.

2. Una volta ogni 24 ore, i messaggi di chat da ICE Chat vengono copiati nel sito SFTP di ICE Chat.

3. Il connettore ICE Chat creato nel Centro conformità Microsoft 365 si connette al sito SFTP di ICE Chat ogni giorno e trasferisce i messaggi di chat dalle 24 ore precedenti a una posizione Archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche il contenuto di un messaggio di chat in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi dei messaggi di chat nelle cassette postali di utenti specifici. Viene creata una nuova **cartella denominata ICE Chat** nelle cassette postali degli utenti e gli elementi dei messaggi di chat vengono importati in tale cartella. Il connettore utilizza il valore delle *proprietà SenderEmail* e *RecipientEmail.* Ogni messaggio di chat contiene queste proprietà, che vengono popolate con l'indirizzo di posta elettronica del mittente e di ogni destinatario/partecipante del messaggio di chat.

   Oltre al mapping automatico degli utenti che utilizza i valori delle proprietà *SenderEmail* e *RecipientEmail* (che significa che il connettore importa un messaggio di chat nella cassetta postale del mittente e nelle cassette postali di ogni destinatario), è anche possibile definire il mapping utente personalizzato caricando un file di mapping CSV. Questo file di mapping  contiene l'IMId di ICE Chat e l'indirizzo Microsoft 365 corrispondente per ogni utente dell'organizzazione. Se si abilita il mapping automatico degli utenti e si fornisce un file di mapping personalizzato, per ogni elemento di chat il connettore guarderà innanzitutto il file di mapping personalizzato. Se non viene trovato un account utente Microsoft 365 valido che corrisponde all'ID di chat ICE di un utente, il connettore utilizzerà le proprietà *SenderEmail* e *RecipientEmail* dell'elemento di chat per importare l'elemento nelle cassette postali dei partecipanti alla chat. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nelle proprietà *SenderEmail* e *RecipientEmail,* l'elemento non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Alcuni dei passaggi di implementazione necessari per archiviare i dati di ICE Chat sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- ICE Chat addebita ai clienti una commissione per la conformità esterna. L'organizzazione deve contattare il gruppo di vendita ICE Chat per discutere e firmare il contratto di servizi dati ice chat, che è possibile ottenere all'indirizzo [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Questo contratto è tra ICE Chat e l'organizzazione e non coinvolge Microsoft. Dopo aver configurato un sito ICE Chat SFTP nel passaggio 2, ICE Chat fornisce le credenziali FTP direttamente all'organizzazione. L'utente che fornirà tali credenziali a Microsoft durante la configurazione del connettore nel passaggio 3.

- È necessario configurare un sito SFTP ice chat prima di creare il connettore nel passaggio 3. Dopo aver lavorato con ICE Chat per configurare il sito SFTP, i dati di ICE Chat vengono caricati ogni giorno nel sito SFTP. Il connettore creato nel passaggio 3 si connette a questo sito SFTP e trasferisce i dati della chat Microsoft 365 cassette postali. SFTP crittografa anche i dati di ICE Chat inviati alle cassette postali durante il processo di trasferimento.

- Per configurare un connettore ice chat, è necessario utilizzare chiavi e passphrase per Pretty Good Privacy (PGP) e Secure Shell (SSH). Queste chiavi vengono utilizzate per configurare il sito ICE Chat SFTP e utilizzate dal connettore per connettersi al sito SFTP di ICE Chat per importare i dati in Microsoft 365. La chiave PGP viene utilizzata per configurare la crittografia dei dati trasferiti dal sito ICE Chat SFTP a Microsoft 365. La chiave SSH viene utilizzata per configurare la shell sicura per abilitare un accesso remoto sicuro quando il connettore si connette al sito ICE Chat SFTP.

  Quando si configura un connettore, è possibile utilizzare le chiavi pubbliche e le passphrase fornite da Microsoft oppure è possibile utilizzare le proprie chiavi private e passphrase. Ti consigliamo di usare le chiavi pubbliche fornite da Microsoft. Tuttavia, se l'organizzazione ha già configurato un sito SFTP ice chat utilizzando chiavi private, è possibile creare un connettore utilizzando le stesse chiavi private.

- Il connettore ICE Chat può importare un totale di 200.000 elementi in un solo giorno. Se nel sito SFTP sono presenti più di 200.000 elementi, nessuno di questi elementi verrà importato in Microsoft 365.

- All'amministratore che crea il connettore ICE Chat nel passaggio 3 (e che scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="set-up-a-connector-using-public-keys"></a>Configurare un connettore con chiavi pubbliche

La procedura descritta in questa sezione illustra come configurare un connettore ice chat utilizzando le chiavi pubbliche per Pretty Good Privacy (PGP) e Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Passaggio 1: Ottenere le chiavi pubbliche PGP e SSH

Il primo passaggio consiste nel ottenere una copia delle chiavi pubbliche per Pretty Good Privacy (PGP) e Secure Shell (SSH). Queste chiavi vengono utilizzate nel passaggio 2 per configurare il sito ICE Chat SFTP in modo da consentire al connettore creato nel passaggio 3 di connettersi al sito SFTP e trasferire i dati di ICE Chat nelle cassette postali di Microsoft 365. Verrà inoltre ottenuto un indirizzo IP in questo passaggio, che verrà utilizzato durante la configurazione del sito SFTP di ICE Chat.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **ICE Chat** fare clic su **Visualizza.**

3. Nella pagina **ICE Chat** fare clic su **Aggiungi connettore.**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine** contenuto fare clic su Voglio usare le chiavi pubbliche PGP e **SSH fornite da Microsoft.**

   ![Selezionare l'opzione per l'utilizzo delle chiavi pubbliche](../media/ICEChatPublicKeysOption.png)

6. Nel passaggio 1, fare clic sulla chiave **Download SSH,** **download PGP key** e Download IP **address** links per salvare una copia di ogni file nel computer locale.

   ![Collegamenti per scaricare le chiavi pubbliche e l'indirizzo IP](../media/ICEChatPublicKeyDownloadLinks.png)

   Questi file contengono gli elementi seguenti che vengono utilizzati per configurare il sito SFTP ice chat nel passaggio 2:

   - Chiave pubblica PGP: questa chiave viene utilizzata per configurare la crittografia dei dati trasferiti dal sito ICE Chat SFTP a Microsoft 365.

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare Secure SSH per abilitare un accesso remoto sicuro quando il connettore si connette al sito ICE Chat SFTP.

   - Indirizzo IP: il sito ICE Chat SFTP è configurato per accettare una richiesta di connessione solo da questo indirizzo IP, che viene utilizzato dal connettore ICE Chat creato nel passaggio 3.

7. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 3 per creare il connettore.

### <a name="step-2-configure-the-ice-chat-sftp-site"></a>Passaggio 2: Configurare il sito SFTP di ICE Chat

Il passaggio successivo consiste nell'utilizzare le chiavi pubbliche PGP e SSH e l'indirizzo IP ottenuto nel passaggio 1 per configurare la crittografia PGP e l'autenticazione SSH per il sito SFTP di ICE Chat. In questo modo il connettore ICE Chat creato nel passaggio 3 si connette al sito SFTP di ICE Chat e trasferisce i dati di ICE Chat Microsoft 365. Per configurare il sito ICE Chat SFTP, è necessario collaborare con il supporto tecnico ice chat.

### <a name="step-3-create-an-ice-chat-connector"></a>Passaggio 3: Creare un connettore ice chat

L'ultimo passaggio consiste nel creare un connettore ICE Chat nel centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito ICE Chat SFTP e trasferire i messaggi di chat alle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **ICE Chat** fare clic su **Visualizza.**

3. Nella pagina **ICE Chat** fare clic su **Aggiungi connettore.**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine contenuto** fare clic su Voglio usare le chiavi pubbliche **PGP e SSH.**

6. In Passaggio 3 immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Convalida connessione**.

   - **Codice fermo:** ID dell'organizzazione, utilizzato come nome utente per il sito SFTP di ICE Chat.

   - **Password:** Password per il sito SFTP di ICE Chat.

   - **URL SFTP:** URL per il sito SFTP di ICE Chat (ad esempio, `sftp.theice.com` ). È inoltre possibile utilizzare un indirizzo IP per questo valore.

   - **Porta SFTP:** Numero di porta per il sito SFTP ice chat. Il connettore utilizza questa porta per connettersi al sito SFTP.

7. Dopo aver convalidato correttamente la connessione, fare clic su **Avanti.**

8. Nella pagina **Mapping utenti esterni a Microsoft 365** utenti, abilitare il mapping automatico degli utenti e fornire il mapping utente personalizzato in base alle esigenze. È possibile scaricare una copia del file CSV di mapping degli utenti in questa pagina. È possibile aggiungere i mapping utente al file e quindi caricarlo.

   > [!NOTE]
   > Come spiegato in precedenza, il file CSV del file di mapping personalizzato contiene l'imid ice chat e l'indirizzo Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat, il connettore guarderà innanzitutto il file di mapping personalizzato. Se non viene trovato un utente Microsoft 365 valido che corrisponde all'imid ICE Chat di un utente, il connettore importerà l'elemento nelle cassette postali per gli utenti specificati nelle proprietà *SenderEmail* e *RecipientEmail* dell'elemento di chat. Se il connettore non trova un utente Microsoft 365 un mapping automatico o personalizzato, l'elemento non verrà importato.

9. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

10. Passare alla **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="set-up-a-connector-using-private-keys"></a>Configurare un connettore con chiavi private

La procedura descritta in questa sezione illustra come configurare un connettore ice chat utilizzando le chiavi private PGP e SSH. Questa opzione di configurazione del connettore è destinata alle organizzazioni che hanno già configurato un sito SFTP ice chat utilizzando chiavi private.

### <a name="step-1-obtain-an-ip-address-to-configure-the-ice-chat-sftp-site"></a>Passaggio 1: Ottenere un indirizzo IP per configurare il sito SFTP di ICE Chat

Se l'organizzazione ha utilizzato le chiavi private PGP e SSH per configurare un sito SFTP ice chat, è necessario ottenere un indirizzo IP e fornirlo al supporto clienti ice chat. Il sito ICE Chat SFTP deve essere configurato per accettare le richieste di connessione da questo indirizzo IP. Lo stesso indirizzo IP viene utilizzato dal connettore ICE Chat per connettersi al sito SFTP e trasferire i dati di ICE Chat Microsoft 365.

Per ottenere l'indirizzo IP:

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **ICE Chat** fare clic su **Visualizza.**

3. Nella pagina **Descrizione del prodotto ICE Chat** fare clic su Aggiungi **connettore**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine contenuto** fare clic su Voglio usare le chiavi private **PGP e SSH.**

   ![Selezionare l'opzione per usare le chiavi private](../media/ICEChatPrivateKeysOption.png)

6. Nel passaggio 1 fare clic **su Scarica indirizzo IP** per salvare una copia del file dell'indirizzo IP nel computer locale.

   ![Scaricare l'indirizzo IP](../media/ICEChatConnectorIPAddress.png)

7. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 2 per creare il connettore.

È necessario collaborare con il supporto clienti ice chat per configurare il sito SFTP ice chat in modo da accettare le richieste di connessione da questo indirizzo IP.

### <a name="step-2-create-an-ice-chat-connector"></a>Passaggio 2: Creare un connettore ice chat

Dopo aver configurato il sito ICE Chat SFTP, il passaggio successivo consiste nel creare un connettore ice chat nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito ICE Chat SFTP e trasferire i messaggi di posta elettronica alle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365. Per completare questo passaggio, assicurarsi di disporre di copie delle stesse passphrase e delle stesse chiavi private utilizzate per configurare il sito SFTP di ICE Chat.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **ICE Chat** fare clic su **Visualizza.**

3. Nella pagina **Descrizione del prodotto ICE Chat** fare clic su Aggiungi **connettore**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine contenuto** fare clic su Voglio usare le chiavi private **PGP e SSH.**

6. In Passaggio 3 immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Convalida connessione**.

      - **Nome:** Nome del connettore. Deve essere univoco nell'organizzazione.

      - **Codice fermo:** ID dell'organizzazione utilizzato come nome utente per il sito SFTP di ICE Chat.

      - **Password:** Password per il sito SFTP ICE Chat dell'organizzazione.

      - **URL SFTP:** URL per il sito SFTP di ICE Chat (ad esempio, `sftp.theice.com` ). È inoltre possibile utilizzare un indirizzo IP per questo valore.

      - **Porta SFTP:** Numero di porta per il sito SFTP ice chat. Il connettore utilizza questa porta per connettersi al sito SFTP.

      - **Chiave privata PGP:** Chiave privata PGP per il sito SFTP di ICE Chat. Assicurarsi di includere l'intero valore della chiave privata, incluse le righe iniziale e finale del blocco di chiavi.

      - **Passphrase chiave PGP:** Passphrase per la chiave privata PGP.

      - **Chiave privata SSH:** Chiave privata SSH per il sito SFTP di ICE Chat. Assicurarsi di includere l'intero valore della chiave privata, incluse le righe iniziale e finale del blocco di chiavi.

      - **Passphrase chiave SSH:** Passphrase per la chiave privata SSH.

7. Dopo aver convalidato correttamente la connessione, fare clic su **Avanti.**

8. Nella pagina Mapping utenti ice chat Microsoft 365 **utenti,** abilitare il mapping automatico degli utenti e fornire il mapping utente personalizzato in base alle esigenze.

   > [!NOTE]
   > Come spiegato in precedenza, il file CSV del file di mapping personalizzato contiene l'imid ice chat e l'indirizzo Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat, il connettore guarderà innanzitutto il file di mapping personalizzato. Se non viene trovato un utente Microsoft 365 valido che corrisponde all'imid ICE Chat di un utente, il connettore importerà l'elemento nelle cassette postali per gli utenti specificati nelle proprietà *SenderEmail* e *RecipientEmail* dell'elemento di chat. Se il connettore non trova un utente Microsoft 365 un mapping automatico o personalizzato, l'elemento non verrà importato.

9. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

10. Passare alla **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore. Fare clic sul connettore per visualizzare la pagina a comparsa, che contiene informazioni sul connettore.
