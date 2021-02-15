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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati dallo strumento ICE Chat in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 79a18017ce7aa3c646fa6c7230bde4b001ddc4c8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790170"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configurare un connettore per archiviare i dati di ICE Chat

Usare un connettore nativo nel Centro conformità Microsoft 365 per importare e archiviare i dati di chat dei servizi finanziari dallo strumento di collaborazione ICE Chat. Dopo aver configurato e configurato un connettore, si connette al sito SFTP (Secure FTP) ice chat dell'organizzazione una volta al giorno, converte il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali di Microsoft 365.

Dopo aver archiviato i dati della chat ICE nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, come la conservazione per controversia legale, eDiscovery, l'archiviazione, il controllo, la conformità delle comunicazioni e i criteri di conservazione di Microsoft 365 ai dati di ICE Chat. Ad esempio, è possibile cercare i messaggi di ICE Chat utilizzando la ricerca di contenuto o associare la cassetta postale contenente i dati di ICE Chat a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore ICE Chat per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-ice-chat-data"></a>Panoramica dell'archiviazione dei dati di ICE Chat

La seguente panoramica spiega il processo di utilizzo di un connettore per archiviare i dati delle chat ICE in Microsoft 365.

![Flusso di lavoro di archiviazione ice chat](../media/ICEChatConnectorWorkflow.png)

1. L'organizzazione collabora con ICE Chat per configurare un sito ICE Chat SFTP. Si lavora anche con ICE Chat per configurare ICE Chat per copiare i messaggi di chat nel sito ICE Chat SFTP.

2. Una volta ogni 24 ore, i messaggi di chat da ICE Chat vengono copiati nel sito ICE Chat SFTP.

3. Il connettore ICE Chat creato nel Centro conformità Microsoft 365 si connette al sito ICE Chat SFTP ogni giorno e trasferisce i messaggi di chat dalle 24 ore precedenti a una posizione di archiviazione sicura di Azure in Microsoft Cloud. Il connettore converte anche il contenuto di una chat in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi dei messaggi di chat nelle cassette postali di utenti specifici. Nelle cassette postali degli utenti viene creata una nuova cartella denominata **ICE Chat** e gli elementi dei messaggi di chat vengono importati in tale cartella. Il connettore utilizza il valore delle proprietà *SenderEmail* e *RecipientEmail.* Ogni messaggio di chat contiene queste proprietà, che vengono popolate con l'indirizzo di posta elettronica del mittente e ogni destinatario/partecipante del messaggio di chat.

   Oltre al mapping automatico degli utenti che utilizza i valori della proprietà *SenderEmail* e *RecipientEmail* (che significa che il connettore importa un messaggio di chat nella cassetta postale del mittente e nelle cassette postali di ogni destinatario), è anche possibile definire il mapping utente personalizzato caricando un file di mapping CSV. Questo file di mapping contiene ice chat *ImId* e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente dell'organizzazione. Se si abilita il mapping automatico degli utenti e si fornisce un file di mapping personalizzato, per ogni elemento di chat il connettore guarderà innanzitutto il file di mapping personalizzato. Se non viene trovato un account utente di Microsoft 365 valido che corrisponde all'ID chat ICE di un utente, il connettore utilizzerà le proprietà *SenderEmail* e *RecipientEmail* dell'elemento di chat per importare l'elemento nelle cassette postali dei partecipanti alla chat. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nelle proprietà *SenderEmail* e *RecipientEmail,* l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di ICE Chat sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- ICE Chat addebita ai clienti una tariffa per la conformità esterna. L'organizzazione deve contattare il gruppo vendite ICE Chat per discutere e firmare il contratto di servizi dati ice chat, che è possibile ottenere in [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Il presente contratto è tra ICE Chat e l'organizzazione e non coinvolge Microsoft. Dopo aver configurato un sito ICE Chat SFTP nel passaggio 2, ICE Chat fornisce le credenziali FTP direttamente all'organizzazione. L'utente che fornirà tali credenziali a Microsoft durante la configurazione del connettore nel passaggio 3.

- È necessario configurare un sito ICE Chat SFTP prima di creare il connettore nel passaggio 3. Dopo aver utilizzato ICE Chat per configurare il sito SFTP, i dati di ICE Chat vengono caricati nel sito SFTP ogni giorno. Il connettore creato nel passaggio 3 si connette a questo sito SFTP e trasferisce i dati della chat alle cassette postali di Microsoft 365. SFTP crittografa anche i dati ice chat inviati alle cassette postali durante il processo di trasferimento.

- Il connettore ICE Chat può importare un totale di 200.000 elementi in un singolo giorno. Se nel sito SFTP sono presenti più di 200.000 elementi, nessuno di questi elementi verrà importato in Microsoft 365.

- All'amministratore che crea il connettore ICE Chat nel passaggio 3 (e che scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Passaggio 1: Ottenere le chiavi pubbliche SSH e PGP

Il primo passaggio consiste nell'ottenere una copia delle chiavi pubbliche per Secure Shell (SSH) e Pretty Good Privacy (PGP). Queste chiavi vengono usate nel passaggio 2 per configurare il sito ICE Chat SFTP per consentire al connettore (creato nel passaggio 3) di connettersi al sito SFTP e trasferire i dati di ICE Chat alle cassette postali di Microsoft 365. In questo passaggio verrà inoltre ottenuto un indirizzo IP da utilizzare per la configurazione del sito ICE Chat SFTP.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **ICE Chat** fare clic su **Visualizza.**

3. Nella pagina **ICE Chat** fare clic su **Aggiungi connettore.**

4. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

5. Nella pagina Aggiungi credenziali per il sito **ICE Chat SFTP** al passaggio 1 fare clic sulla chiave **SSH** download, scaricare la chiave **PGP** e scaricare i collegamenti degli indirizzi **IP** per salvare una copia di ogni file nel computer locale. Questi file contengono gli elementi seguenti utilizzati per configurare il sito ICE Chat SFTP nel passaggio 2:

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare Secure SSH per abilitare un accesso remoto protetto quando il connettore si connette al sito ICE Chat SFTP.

   - Chiave pubblica PGP: questa chiave viene usata per configurare la crittografia dei dati trasferiti dal sito ICE Chat SFTP a Microsoft 365.

   - Indirizzo IP: il sito ICE Chat SFTP è configurato per accettare una richiesta di connessione solo da questo indirizzo IP, utilizzato dal connettore ICE Chat creato nel passaggio 3.

6. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 3 per creare il connettore.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Passaggio 2: Configurare il sito ICE Chat SFTP

Il passaggio successivo consiste nell'usare le chiavi pubbliche SSH e PGP e l'indirizzo IP ottenuto nel passaggio 1 per configurare l'autenticazione SSH e la crittografia PGP per il sito ICE Chat SFTP. Ciò consente al connettore ICE Chat creato nel passaggio 3 di connettersi al sito ICE Chat SFTP e trasferire i dati di ICE Chat a Microsoft 365. È necessario collaborare con il supporto clienti ICE Chat per configurare il sito ICE Chat SFTP.

## <a name="step-3-create-an-ice-chat-connector"></a>Passaggio 3: Creare un connettore ice chat

L'ultimo passaggio consiste nel creare un connettore ICE Chat nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito ICE Chat SFTP e trasferire i messaggi di chat alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **ICE Chat** fare clic su **Visualizza.**

3. Nella pagina **ICE Chat** fare clic su **Aggiungi connettore.**

4. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

5. Nella pagina Aggiungi credenziali per il sito **ICE Chat SFTP,** nel passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Convalida connessione.**

   - **Codice della società:** ID dell'organizzazione, utilizzato come nome utente per il sito ICE Chat SFTP.

   - **Password:** La password per il sito ICE Chat SFTP.

   - **URL SFTP:** L'URL del sito ICE Chat SFTP (ad esempio, sftp.theice.com).

   - **Porta SFTP:** Numero di porta per il sito ICE Chat SFTP. Il connettore utilizza questa porta per connettersi al sito SFTP.

6. Dopo aver convalidato la connessione, fare clic su **Avanti.**

7. Nella pagina **Mapping utenti esterni a utenti di Microsoft 365** abilitare il mapping automatico degli utenti e fornire il mapping utente personalizzato in base alle esigenze. È possibile scaricare una copia del file CSV di mapping degli utenti in questa pagina. È possibile aggiungere i mapping utente al file e quindi caricarlo.

   > [!NOTE]
   > Come descritto in precedenza, il file CSV del file di mapping personalizzato contiene l'imid ice chat e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat, il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde all'imid ICE Chat di un utente, il connettore importerà l'elemento nelle cassette postali per gli utenti specificati nelle proprietà *SenderEmail* e *RecipientEmail* dell'elemento di chat. Se il connettore non trova un utente di Microsoft 365 valido tramite il mapping automatico o personalizzato, l'elemento non verrà importato.

8. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

9. Passare alla pagina **Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.
