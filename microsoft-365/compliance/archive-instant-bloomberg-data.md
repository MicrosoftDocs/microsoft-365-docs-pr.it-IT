---
title: Configurare un connettore per archiviare i dati di Instant Bloomberg
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Informazioni su come gli amministratori possono configurare e usare un connettore dati per importare e archiviare i dati dallo strumento chat di Instant Bloomberg in Microsoft 365.
ms.openlocfilehash: 791b87b6512aa385a8cdcbf7465d01461ce1e649
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221781"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Configurare un connettore per archiviare i dati di Instant Bloomberg

Utilizzare un connettore nativo nel Centro conformità Microsoft 365 per importare e archiviare i dati di chat dei servizi finanziari dallo strumento di collaborazione [Instant Bloomberg.](https://www.bloomberg.com/professional/product/collaboration/) Dopo aver configurato e configurato un connettore, si connette al sito FTP protetto (SFTP) dell'organizzazione una volta al giorno, converte il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali in Microsoft 365.

Dopo aver archiviato i dati di Instant Bloomberg nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, ricerca contenuto, archiviazione In-Place, controllo, conformità delle comunicazioni e criteri di conservazione di Microsoft 365 ai dati di Bloomberg istantanei. Ad esempio, è possibile eseguire ricerche nei messaggi di chat Di Bloomberg istantanei utilizzando Ricerca contenuto o associare la cassetta postale contenente i dati di Instant Bloomberg a un responsabile in un caso di Advanced eDiscovery. L'utilizzo di un connettore Bloomberg istantaneo per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Panoramica dell'archiviazione dei dati di Instant Bloomberg

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati delle chat di Bloomberg istantanee in Microsoft 365. 

![Processo di importazione e archiviazione di Bloomberg istantaneo](../media/InstantBloombergDataArchiving.png)

1. L'organizzazione collabora con Bloomberg per configurare un sito SFTP bloomberg. Potrai inoltre collaborare con Bloomberg per configurare Instant Bloomberg per copiare i messaggi di chat nel sito SFTP di Bloomberg.

2. Una volta ogni 24 ore, i messaggi di chat di Instant Bloomberg vengono copiati nel sito SFTP di Bloomberg.

3. Il connettore Bloomberg istantaneo creato nel Centro conformità Microsoft 365 si connette al sito SFTP di Bloomberg ogni giorno e trasferisce i messaggi di chat dalle 24 ore precedenti a un'area di archiviazione sicura di Azure nel cloud Microsoft. Il connettore converte anche il contenuto di un messaggio di chat in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi dei messaggi di chat nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata InstantBloomberg nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. Il connettore esegue questa operazione utilizzando il valore della *proprietà CorporateEmailAddress.* Ogni messaggio di chat contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Oltre al mapping automatico degli utenti utilizzando il valore della *proprietà CorporateEmailAddress,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere un UUID Bloomberg e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizzerà la proprietà *CorporateEmailAddress* dell'elemento di chat. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento di chat, l'elemento non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Alcuni dei passaggi di implementazione necessari per archiviare i dati di Instant Bloomberg sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Per configurare un connettore Bloomberg istantaneo, è necessario utilizzare chiavi e passphrase per Pretty Good Privacy (PGP) e Secure Shell (SSH). Queste chiavi vengono utilizzate per configurare il sito SFTP di Bloomberg e utilizzate dal connettore per connettersi al sito SFTP di Bloomberg per importare dati in Microsoft 365. La chiave PGP viene utilizzata per configurare la crittografia dei dati trasferiti dal sito SFTP bloomberg a Microsoft 365. La chiave SSH viene utilizzata per configurare la shell sicura per abilitare un accesso remoto sicuro quando il connettore si connette al sito SFTP bloomberg.

  Quando si configura un connettore, è possibile utilizzare le chiavi pubbliche e le passphrase fornite da Microsoft oppure è possibile utilizzare le proprie chiavi private e passphrase. Ti consigliamo di usare le chiavi pubbliche fornite da Microsoft. Tuttavia, se l'organizzazione ha già configurato un sito SFTP bloomberg utilizzando chiavi private, è possibile creare un connettore utilizzando le stesse chiavi private.

- Iscriviti [a Bloomberg anywhere.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) Questa operazione è necessaria per poter accedere a Bloomberg via Internet per accedere al sito SFTP bloomberg che è necessario configurare.

- Configurare un sito Bloomberg SFTP (Secure File Transfer Protocol). Dopo aver lavorato con Bloomberg per configurare il sito SFTP, i dati di Instant Bloomberg vengono caricati ogni giorno nel sito SFTP. Il connettore creato nel passaggio 2 si connette a questo sito SFTP e trasferisce i dati della chat alle cassette postali di Microsoft 365. SFTP crittografa anche i dati della chat di Instant Bloomberg inviati alle cassette postali durante il processo di trasferimento.

  Per informazioni su Bloomberg SFTP (denominato anche *BB-SFTP):*

  - Vedere il documento "Standard di connettività SFTP" [all'indirizzo Bloomberg Support.](https://www.bloomberg.com/professional/support/documentation/)

  - Contattare [il supporto clienti Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

  Dopo aver collaborare con Bloomberg per configurare un sito SFTP, Bloomberg fornirà alcune informazioni dopo aver risposto al messaggio di posta elettronica di implementazione bloomberg. Salvare una copia delle informazioni seguenti. Utilizzarlo per configurare un connettore nel passaggio 3.

  - Codice della società, che è un ID per l'organizzazione e viene utilizzato per accedere al sito SFTP di Bloomberg.

  - Password per il sito SFTP bloomberg

  - URL per il sito SFTP bloomberg (ad esempio, sftp.bloomberg.com)

  - Numero di porta per il sito SFTP bloomberg

- Il connettore Bloomberg istantaneo può importare un totale di 200.000 elementi in un solo giorno. Se nel sito SFTP sono presenti più di 200.000 elementi, nessuno di questi elementi verrà importato in Microsoft 365.

- All'utente che crea un connettore Bloomberg istantaneo nel passaggio 3 (e che scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori dati** nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="set-up-a-connector-using-public-keys"></a>Configurare un connettore con chiavi pubbliche

La procedura descritta in questa sezione illustra come configurare un connettore Bloomberg istantaneo utilizzando le chiavi pubbliche per Pretty Good Privacy (PGP) e Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-and-public-keys"></a>Passaggio 1: Ottenere PGP, SSH e chiavi pubbliche

Il primo passaggio consiste nel ottenere una copia delle chiavi pubbliche per Pretty Good Privacy (PGP) e Secure Shell (SSH). Queste chiavi vengono utilizzate nel passaggio 2 per configurare il sito SFTP bloomberg in modo da consentire al connettore (creato nel passaggio 3) di connettersi al sito SFTP e trasferire i dati della chat Di Bloomberg istantanea alle cassette postali di Microsoft 365. È inoltre possibile ottenere un indirizzo IP in questo passaggio, da utilizzare per la configurazione del sito SFTP bloomberg.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Instant Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Descrizione prodotto Instant Bloomberg** fare clic su **Aggiungi connettore**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine** contenuto fare clic su Voglio usare le chiavi pubbliche PGP e **SSH fornite da Microsoft.**

   ![Selezionare l'opzione per l'utilizzo delle chiavi pubbliche](../media/InstantBloombergPublicKeysOption.png)

6. Nel passaggio 1, fare clic sulla chiave **Download SSH,** **download PGP key** e Download IP **address** links per salvare una copia di ogni file nel computer locale.

   ![Collegamenti per scaricare le chiavi pubbliche e l'indirizzo IP](../media/InstantBloombergPublicKeyDownloadLinks.png)

   Questi file contengono gli elementi seguenti che vengono utilizzati per configurare il sito SFTP bloomberg nel passaggio 2:

   - Chiave pubblica PGP: questa chiave viene utilizzata per configurare la crittografia dei dati trasferiti dal sito SFTP bloomberg a Microsoft 365.

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare la shell sicura per abilitare un accesso remoto sicuro quando il connettore si connette al sito SFTP bloomberg.

   - Indirizzo IP: il sito SFTP bloomberg è configurato per accettare le richieste di connessione da questo indirizzo IP. Lo stesso indirizzo IP viene utilizzato dal connettore Bloomberg istantaneo per connettersi al sito SFTP e trasferire i dati di Instant Bloomberg a Microsoft 365.

7. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 3 per creare il connettore.

### <a name="step-2-configure-the-bloomberg-sftp-site"></a>Passaggio 2: Configurare il sito SFTP bloomberg

Il passaggio successivo consiste nell'usare le chiavi pubbliche PGP e SSH e l'indirizzo IP ottenuto nel passaggio 1 per configurare la crittografia PGP e l'autenticazione SSH per il sito SFTP bloomberg. Ciò consente al connettore Bloomberg istantaneo creato nel passaggio 3 di connettersi al sito SFTP di Bloomberg e trasferire i dati di Instant Bloomberg a Microsoft 365. È necessario collaborare con il supporto clienti Bloomberg per configurare il sito SFTP bloomberg. Contattare [il supporto clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) per assistenza. 

> [!IMPORTANT]
> Bloomberg consiglia di allegare i tre file scaricati nel passaggio 1 a un messaggio di posta elettronica e inviarli al team di supporto dei clienti quando si lavora con loro per configurare il sito SfTP bloomberg.

### <a name="step-3-create-an-instant-bloomberg-connector"></a>Passaggio 3: Creare un connettore Bloomberg istantaneo

L'ultimo passaggio consiste nel creare un connettore Bloomberg istantaneo nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito SFTP bloomberg e trasferire i messaggi di chat alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati** Instant  >  **Bloomberg.**

2. Nella pagina **Descrizione prodotto Instant Bloomberg** fare clic su **Aggiungi connettore**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Nella pagina Aggiungi credenziali per il sito **Bloomberg SFTP,** in Passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

    - **Codice fermo:** ID dell'organizzazione utilizzato come nome utente per il sito SFTP bloomberg.

    - **Password:** Password per il sito SFTP bloomberg.

    - **URL SFTP:** L'URL per il sito SFTP di Bloomberg (ad esempio, `sftp.bloomberg.com` ). È inoltre possibile utilizzare un indirizzo IP per questo valore.

    - **Porta SFTP:** Numero di porta per il sito SFTP di Bloomberg. Il connettore utilizza questa porta per connettersi al sito SFTP.

5. Nella pagina **Selezionare i tipi di dati** da importare selezionare i tipi di dati necessari da importare oltre a **Messaggi**

6. Nella pagina Mappare gli utenti di Bloomberg istantanei agli utenti **di Microsoft 365,** abilitare il mapping automatico degli utenti e fornire il mapping utente personalizzato in base alle esigenze

   > [!NOTE]
   > Il connettore importa gli elementi dei messaggi di chat nella cassetta postale di un utente specifico. Viene creata una **nuova cartella denominata InstantBloomberg** nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. Il connettore utilizza il valore della *proprietà CorporateEmailAddress.* Ogni messaggio di chat contiene questa proprietà e la proprietà viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Oltre al mapping automatico degli utenti utilizzando il valore della *proprietà CorporateEmailAddress,* è anche possibile definire il mapping personalizzato caricando un file di mapping CSV. Il file di mapping deve contenere l'UUID Bloomberg e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizzerà la proprietà *CorporateEmailAddress* dell'elemento di chat. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella *proprietà CorporateEmailAddress* dell'elemento di chat, l'elemento non verrà importato.

7. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

8. Passare alla **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore. Fare clic sul connettore per visualizzare la pagina a comparsa, che contiene informazioni sul connettore.

## <a name="set-up-a-connector-using-private-keys"></a>Configurare un connettore con chiavi private

La procedura descritta in questa sezione illustra come configurare un connettore Bloomberg istantaneo utilizzando le chiavi private PGP e SSH. Questa opzione di configurazione del connettore è destinata alle organizzazioni che hanno già configurato un sito SFTP Bloomberg utilizzando chiavi private.

### <a name="step-1-obtain-an-ip-address-to-configure-the-bloomberg-sftp-site"></a>Passaggio 1: Ottenere un indirizzo IP per configurare il sito SFTP bloomberg

> [!NOTE]
> Se in precedenza l'organizzazione ha configurato un sito SFTP bloomberg per archiviare i dati dei messaggi Bloomberg utilizzando le chiavi private PGP e SSH, non è necessario configurarne un altro. È possibile specificare lo stesso sito SFTP quando si crea il connettore nel passaggio 2.

Se l'organizzazione ha utilizzato le chiavi private PGP e SSH per configurare un sito SFTP bloomberg, è necessario ottenere un indirizzo IP e fornirlo al supporto clienti Bloomberg. Il sito SFTP Bloomberg deve essere configurato per accettare richieste di connessione da questo indirizzo IP. Lo stesso indirizzo IP viene utilizzato dal connettore Bloomberg istantaneo per connettersi al sito SFTP e trasferire i dati di Instant Bloomberg a Microsoft 365.

Per ottenere l'indirizzo IP:

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Instant Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Descrizione prodotto Instant Bloomberg** fare clic su **Aggiungi connettore**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine contenuto** fare clic su Voglio usare le chiavi private **PGP e SSH.**

6. Nel passaggio 1 fare clic **su Scarica indirizzo IP** per salvare una copia del file dell'indirizzo IP nel computer locale.

   ![Scaricare l'indirizzo IP](../media/InstantBloombergConnectorIPAddress.png)

7. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 2 per creare il connettore.

È necessario collaborare con il supporto clienti Bloomberg per configurare il sito SFTP bloomberg per accettare le richieste di connessione da questo indirizzo IP. Contattare [il supporto clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) per assistenza.

### <a name="step-2-create-an-instant-bloomberg-connector"></a>Passaggio 2: Creare un connettore Bloomberg istantaneo

Dopo aver configurato il sito SFTP bloomberg, il passaggio successivo consiste nel creare un connettore Bloomberg istantaneo nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito SFTP bloomberg e trasferire i messaggi di posta elettronica alle caselle delle cassette postali utente corrispondenti in Microsoft 365. Per completare questo passaggio, assicurarsi di disporre di copie delle stesse passphrase e delle stesse chiavi private utilizzate per configurare il sito SFTP di Bloomberg.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Instant Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Descrizione prodotto Instant Bloomberg** fare clic su **Aggiungi connettore**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'origine contenuto** fare clic su Voglio usare le chiavi private **PGP e SSH.**

   ![Selezionare l'opzione per usare le chiavi private](../media/InstantBloombergPrivateKeysOption.png)

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

8. Nella pagina Mappare gli utenti di Bloomberg istantanei agli utenti **di Microsoft 365,** abilitare il mapping automatico degli utenti e fornire il mapping utente personalizzato in base alle esigenze.

   > [!NOTE]
   > Il connettore importa gli elementi dei messaggi di chat nella cassetta postale di un utente specifico. Viene creata una **nuova cartella denominata InstantBloomberg** nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. Il connettore utilizza il valore della *proprietà CorporateEmailAddress.* Ogni messaggio di chat contiene questa proprietà e la proprietà viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Oltre al mapping automatico degli utenti utilizzando il valore della *proprietà CorporateEmailAddress,* è anche possibile definire il mapping personalizzato caricando un file di mapping CSV. Il file di mapping deve contenere l'UUID Bloomberg e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizzerà la proprietà *CorporateEmailAddress* dell'elemento di chat. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella *proprietà CorporateEmailAddress* dell'elemento di chat, l'elemento non verrà importato.

9. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

10. Passare alla **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore. Fare clic sul connettore per visualizzare la pagina a comparsa, che contiene informazioni sul connettore.
