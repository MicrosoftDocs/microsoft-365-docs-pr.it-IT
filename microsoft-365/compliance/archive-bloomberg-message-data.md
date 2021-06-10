---
title: Configurare un connettore per archiviare i dati dei messaggi bloomberg
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
description: Gli amministratori possono configurare un connettore dati per importare e archiviare i dati dallo strumento di posta elettronica Bloomberg Message Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, ricerca contenuto e criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 7029b95e4b9ceb91859e2a4b38afb5205e3307b2
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222545"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Configurare un connettore per archiviare i dati dei messaggi bloomberg

Utilizzare un connettore dati nel centro Microsoft 365 conformità per importare e archiviare i dati di posta elettronica dei servizi finanziari dallo strumento di collaborazione [Bloomberg Message.](https://www.bloomberg.com/professional/product/collaboration/) Dopo aver configurato e configurato un connettore, si connette al sito FTP protetto (SFTP) dell'organizzazione una volta al giorno e importa gli elementi di posta elettronica nelle cassette postali in Microsoft 365.

Dopo l'archiviazione dei dati dei messaggi Bloomberg nelle cassette postali degli utenti, è possibile applicare ai dati dei messaggi bloomberg funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, ricerca contenuto, archiviazione sul posto, controllo, conformità delle comunicazioni e criteri di conservazione Microsoft 365. Ad esempio, è possibile cercare i messaggi di posta elettronica bloomberg utilizzando lo strumento di ricerca contenuto o associare la cassetta postale che contiene i dati del messaggio Bloomberg a un responsabile in un caso Advanced eDiscovery caso. L'utilizzo di un connettore di messaggi Bloomberg per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Panoramica dell'archiviazione dei dati dei messaggi Bloomberg

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati dei messaggi Bloomberg in Microsoft 365.

![Processo di importazione e archiviazione dei messaggi Bloomberg](../media/BloombergMessageArchiving.png)

1. L'organizzazione collabora con Bloomberg per configurare un sito SFTP bloomberg. Potrai inoltre collaborare con Bloomberg per configurare Bloomberg Message in modo da copiare i messaggi di posta elettronica nel sito SFTP di Bloomberg.

2. Una volta ogni 24 ore, i messaggi di posta elettronica provenienti da Bloomberg Message vengono copiati nel sito SFTP di Bloomberg.

3. Il connettore di messaggi Bloomberg creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito SFTP di Bloomberg e trasferisce i messaggi di posta elettronica dalle 24 ore precedenti a un'area di Archiviazione di Azure sicura in Microsoft Cloud.

4. Il connettore importa gli elementi dei messaggi di posta elettronica nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata BloombergMessage nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa.

   Il connettore esegue questa operazione utilizzando il valore della proprietà CorporateEmailAddress. Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti utilizzando il valore della *proprietà CorporateEmailAddress,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene un UUID Bloomberg e l'indirizzo Microsoft 365 corrispondente per ogni utente dell'organizzazione. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizza la proprietà *CorporateEmailAddress* dell'elemento di posta elettronica. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Alcuni dei passaggi di implementazione necessari per archiviare i dati dei messaggi bloomberg sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Per configurare un connettore di messaggi Bloomberg, è necessario utilizzare chiavi e passphrase per Pretty Good Privacy (PGP) e Secure Shell (SSH). Queste chiavi vengono utilizzate per configurare il sito SFTP di Bloomberg e utilizzate dal connettore per connettersi al sito SFTP di Bloomberg per importare i dati in Microsoft 365. La chiave PGP viene utilizzata per configurare la crittografia dei dati trasferiti dal sito SFTP bloomberg a Microsoft 365. La chiave SSH viene utilizzata per configurare la shell sicura per abilitare un accesso remoto sicuro quando il connettore si connette al sito SFTP bloomberg.

  Quando si configura un connettore, è possibile utilizzare le chiavi pubbliche e le passphrase fornite da Microsoft oppure è possibile utilizzare le proprie chiavi private e passphrase. Ti consigliamo di usare le chiavi pubbliche fornite da Microsoft. Tuttavia, se l'organizzazione ha già configurato un sito SFTP bloomberg utilizzando chiavi private, è possibile creare un connettore utilizzando le stesse chiavi private.

- Iscriviti [a Bloomberg anywhere.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) Questa operazione è necessaria per poter accedere a Bloomberg via Internet per accedere al sito SFTP bloomberg che è necessario configurare.

- Configurare un sito Bloomberg SFTP (Secure File Transfer Protocol). Dopo aver lavorato con Bloomberg per configurare il sito SFTP, i dati di Bloomberg Message vengono caricati ogni giorno nel sito SFTP. Il connettore creato nel passaggio 2 si connette a questo sito SFTP e trasferisce i dati di posta elettronica Microsoft 365 cassette postali. SFTP crittografa anche i dati del messaggio Bloomberg inviati alle cassette postali durante il processo di trasferimento.

  Per informazioni su Bloomberg SFTP (denominato anche *BB-SFTP):*

  - Vedere il documento "Standard di connettività SFTP" [all'indirizzo Bloomberg Support.](https://www.bloomberg.com/professional/support/documentation/)

  - Contattare [il supporto clienti Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

- Dopo aver collaborare con Bloomberg per configurare un sito SFTP, Bloomberg fornirà alcune informazioni dopo aver risposto al messaggio di posta elettronica di implementazione bloomberg. Salvare una copia delle informazioni seguenti. Utilizzarlo per configurare un connettore nel passaggio 3.

  - Codice della società, che è un ID per l'organizzazione e viene utilizzato per accedere al sito SFTP di Bloomberg.

  - Password per il sito SFTP bloomberg

  - URL del sito SFTP bloomberg (ad esempio, sftp.bloomberg.com). Inoltre, Bloomberg può anche fornire un indirizzo IP corrispondente per il sito SFTP bloomberg, che può essere utilizzato anche per configurare il connettore.

  - Numero di porta per il sito SFTP bloomberg

- Il connettore Bloomberg Message può importare un totale di 200.000 elementi in un solo giorno. Se nel sito SFTP sono presenti più di 200.000 elementi, nessuno di questi elementi verrà importato in Microsoft 365.

- All'utente che crea un connettore di messaggi Bloomberg nel passaggio 3 (e che scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="set-up-a-connector-using-public-keys"></a>Configurare un connettore con chiavi pubbliche

La procedura descritta in questa sezione illustra come configurare un connettore di messaggi Bloomberg utilizzando le chiavi pubbliche per Pretty Good Privacy (PGP) e Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Passaggio 1: Ottenere le chiavi pubbliche PGP e SSH

Il primo passaggio consiste nel ottenere una copia delle chiavi pubbliche PGP e SSH. Queste chiavi vengono utilizzate nel passaggio 2 per configurare il sito SFTP di Bloomberg in modo da consentire al connettore (creato nel passaggio 3) di connettersi al sito SFTP e trasferire i dati di posta elettronica del messaggio Bloomberg alle cassette postali di Microsoft 365. È inoltre possibile ottenere un indirizzo IP in questo passaggio, da utilizzare per la configurazione del sito SFTP bloomberg.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Bloomberg Message** product description fare clic su **Add connector**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine** contenuto fare clic su Voglio usare le chiavi pubbliche PGP e **SSH fornite da Microsoft.**

   ![Selezionare l'opzione per l'utilizzo delle chiavi pubbliche](../media/BloombergMessagePublicKeysOption.png)

6. Nel passaggio 1, fare clic sulla chiave **Download SSH,** **download PGP key** e Download IP **address** links per salvare una copia di ogni file nel computer locale.

   ![Collegamenti per scaricare le chiavi pubbliche e l'indirizzo IP](../media/BloombergMessagePublicKeyDownloadLinks.png)

   Questi file contengono gli elementi seguenti che vengono utilizzati per configurare il sito SFTP bloomberg nel passaggio 2:

   - Chiave pubblica PGP: questa chiave viene utilizzata per configurare la crittografia dei dati trasferiti dal sito SFTP bloomberg a Microsoft 365.

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare la shell sicura per abilitare un accesso remoto sicuro quando il connettore si connette al sito SFTP bloomberg.

   - Indirizzo IP: il sito SFTP bloomberg è configurato per accettare le richieste di connessione da questo indirizzo IP. Lo stesso indirizzo IP viene utilizzato dal connettore Bloomberg Message per connettersi al sito SFTP e trasferire i dati del messaggio Bloomberg Microsoft 365.

7. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 3 per creare il connettore.

### <a name="step-2-configure-the-bloomberg-sftp-site"></a>Passaggio 2: Configurare il sito SFTP bloomberg

> [!NOTE]
> Se l'organizzazione ha precedentemente configurato un sito SFTP bloomberg per archiviare i dati di Instant Bloomberg utilizzando chiavi PGP e SSH pubbliche, non è necessario configurarne un altro. È possibile specificare lo stesso sito SFTP quando si crea il connettore nel passaggio 3.

Il passaggio successivo consiste nell'usare le chiavi pubbliche PGP e SSH e l'indirizzo IP ottenuto nel passaggio 1 per configurare la crittografia PGP e l'autenticazione SSH per il sito SFTP bloomberg. Ciò consente al connettore di messaggi Bloomberg creato nel passaggio 3 di connettersi al sito SFTP di Bloomberg e di trasferire i dati del messaggio Bloomberg Microsoft 365. È necessario collaborare con il supporto clienti Bloomberg per configurare il sito SFTP bloomberg. Contattare [il supporto clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) per assistenza.

> [!IMPORTANT]
> Bloomberg consiglia di allegare i tre file scaricati nel passaggio 1 a un messaggio di posta elettronica e inviarli al team di supporto dei clienti quando si lavora con loro per configurare il sito SfTP bloomberg.

### <a name="step-3-create-a-bloomberg-message-connector"></a>Passaggio 3: Creare un connettore di messaggi Bloomberg

L'ultimo passaggio consiste nel creare un connettore di messaggi Bloomberg nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito SFTP bloomberg e trasferire i messaggi di posta elettronica alle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Bloomberg Message** product description fare clic su **Add connector**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine** contenuto fare clic su Voglio usare le chiavi pubbliche PGP e **SSH fornite da Microsoft.**

6. In Passaggio 3 immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Convalida connessione**.

      - **Nome:** Nome del connettore. Deve essere univoco nell'organizzazione.

      - **Codice fermo:** ID dell'organizzazione utilizzato come nome utente per il sito SFTP bloomberg.

      - **Password:** Password per il sito SFTP Bloomberg dell'organizzazione.

      - **URL SFTP:** L'URL per il sito SFTP di Bloomberg (ad esempio, `sftp.bloomberg.com` ). È inoltre possibile utilizzare un indirizzo IP per questo valore.

      - **Porta SFTP:** Numero di porta per il sito SFTP bloomberg. Il connettore utilizza questa porta per connettersi al sito SFTP.

7. Dopo aver convalidato correttamente la connessione, fare clic su **Avanti.**

8. Nella pagina **Map Bloomberg Message users to Microsoft 365 users** abilita il mapping automatico degli utenti e fornisci il mapping utente personalizzato in base alle esigenze.

   > [!NOTE]
   > Il connettore importa gli elementi dei messaggi nella cassetta postale di un utente specifico. Viene creata una **nuova cartella denominata BloombergMessage** nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. Il connettore utilizza il valore della *proprietà CorporateEmailAddress.* Ogni messaggio di chat contiene questa proprietà e la proprietà viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Oltre al mapping automatico degli utenti utilizzando il valore della *proprietà CorporateEmailAddress,* è anche possibile definire il mapping personalizzato caricando un file di mapping CSV. Il file di mapping deve contenere l'UUID Bloomberg e l'indirizzo Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento del messaggio il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizzerà la proprietà *CorporateEmailAddress* dell'elemento di chat. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento del messaggio, l'elemento non verrà importato.

9. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

10. Passare alla **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore. Fare clic sul connettore per visualizzare la pagina a comparsa, che contiene informazioni sul connettore.

## <a name="set-up-a-connector-using-private-keys"></a>Configurare un connettore con chiavi private

La procedura descritta in questa sezione illustra come configurare un connettore di messaggi Bloomberg utilizzando le chiavi private PGP e SSH. Questa opzione di configurazione del connettore è destinata alle organizzazioni che hanno già configurato un sito SFTP Bloomberg utilizzando chiavi private.

### <a name="step-1-obtain-an-ip-address-to-configure-the-bloomberg-sftp-site"></a>Passaggio 1: Ottenere un indirizzo IP per configurare il sito SFTP bloomberg

> [!NOTE]
> Se l'organizzazione ha precedentemente configurato un sito SFTP bloomberg per archiviare i dati di Instant Bloomberg utilizzando le chiavi private PGP e SSH, non è necessario configurarne un altro. È possibile specificare lo stesso sito SFTP quando si crea il connettore nel passaggio 2.

Se l'organizzazione ha utilizzato le chiavi private PGP e SSH per configurare un sito SFTP bloomberg, è necessario ottenere un indirizzo IP e fornirlo al supporto clienti Bloomberg. Il sito SFTP Bloomberg deve essere configurato per accettare richieste di connessione da questo indirizzo IP. Lo stesso indirizzo IP viene utilizzato dal connettore Bloomberg Message per connettersi al sito SFTP e trasferire i dati del messaggio Bloomberg Microsoft 365.

Per ottenere l'indirizzo IP:

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Bloomberg Message** product description fare clic su **Add connector**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine contenuto** fare clic su Voglio usare le chiavi private **PGP e SSH.**

6. Nel passaggio 1 fare clic **su Scarica indirizzo IP** per salvare una copia del file dell'indirizzo IP nel computer locale.

   ![Scaricare l'indirizzo IP](../media/BloombergMessageConnectorIPAddress.png)

7. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 2 per creare il connettore.

È necessario collaborare con il supporto clienti Bloomberg per configurare il sito SFTP bloomberg per accettare le richieste di connessione da questo indirizzo IP. Contattare [il supporto clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) per assistenza.

### <a name="step-2-create-a-bloomberg-message-connector"></a>Passaggio 2: Creare un connettore di messaggi Bloomberg

Dopo aver configurato il sito SFTP bloomberg, il passaggio successivo consiste nel creare un connettore di messaggi Bloomberg nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito SFTP bloomberg e trasferire i messaggi di posta elettronica alle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365. Per completare questo passaggio, assicurarsi di disporre di copie delle stesse passphrase e delle stesse chiavi private utilizzate per configurare il sito SFTP di Bloomberg.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Bloomberg Message** product description fare clic su **Add connector**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine contenuto** fare clic su Voglio usare le chiavi private **PGP e SSH.**

   ![Selezionare l'opzione per usare le chiavi private](../media/BloombergMessagePrivateKeysOption.png)

6. In Passaggio 3 immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Convalida connessione**.

      - **Nome:** Nome del connettore. Deve essere univoco nell'organizzazione.

      - **Codice fermo:** ID dell'organizzazione utilizzato come nome utente per il sito SFTP bloomberg.

      - **Password:** Password per il sito SFTP Bloomberg dell'organizzazione.

      - **URL SFTP:** L'URL per il sito SFTP di Bloomberg (ad esempio, `sftp.bloomberg.com` ). È inoltre possibile utilizzare un indirizzo IP per questo valore.

      - **Porta SFTP:** Numero di porta per il sito SFTP bloomberg. Il connettore utilizza questa porta per connettersi al sito SFTP.

      - **Chiave privata PGP:** Chiave privata PGP per il sito SFTP bloomberg. Assicurarsi di includere l'intero valore della chiave privata, incluse le righe iniziale e finale del blocco di chiavi.

      - **Passphrase chiave PGP:** Passphrase per la chiave privata PGP.

      - **Chiave privata SSH:** Chiave privata SSH per il sito SFTP bloomberg. Assicurarsi di includere l'intero valore della chiave privata, incluse le righe iniziale e finale del blocco di chiavi.

      - **Passphrase chiave SSH:** Passphrase per la chiave privata SSH.

7. Dopo aver convalidato correttamente la connessione, fare clic su **Avanti.**

8. Nella pagina **Map Bloomberg Message users to Microsoft 365 users** abilita il mapping automatico degli utenti e fornisci il mapping utente personalizzato in base alle esigenze.

   > [!NOTE]
   > Il connettore importa gli elementi dei messaggi nella cassetta postale di un utente specifico. Viene creata una **nuova cartella denominata BloombergMessage** nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. Il connettore utilizza il valore della *proprietà CorporateEmailAddress.* Ogni messaggio di chat contiene questa proprietà e la proprietà viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Oltre al mapping automatico degli utenti utilizzando il valore della *proprietà CorporateEmailAddress,* è anche possibile definire il mapping personalizzato caricando un file di mapping CSV. Il file di mapping deve contenere l'UUID Bloomberg e l'indirizzo Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento del messaggio il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizzerà la proprietà *CorporateEmailAddress* dell'elemento di chat. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento del messaggio, l'elemento non verrà importato.

9. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

10. Passare alla **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore. Fare clic sul connettore per visualizzare la pagina a comparsa, che contiene informazioni sul connettore.

## <a name="known-issues"></a>Problemi noti

- Il threading dei messaggi bloomberg importati in Microsoft 365 non è supportato. I singoli messaggi inviati a una persona vengono importati, ma non vengono presentati in una conversazione a thread. Microsoft sta lavorando per supportare il threading nelle versioni successive del connettore dati Bloomberg Message.
