---
title: Configurare un connettore per archiviare i dati dei messaggi di Bloomberg
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
description: Gli amministratori possono configurare un connettore dati per importare e archiviare i dati dallo strumento di posta elettronica Bloomberg Message in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio conservazione a scopo giudiziario, Ricerca contenuto e criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: f9b082dace9301f5a664078e9028c646ffa28483
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790116"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Configurare un connettore per archiviare i dati dei messaggi di Bloomberg

Usare un connettore di dati nel Centro conformità Microsoft 365 per importare e archiviare i dati di posta elettronica dei servizi finanziari dallo strumento di collaborazione [Bloomberg Message.](https://www.bloomberg.com/professional/product/collaboration/) Dopo aver configurato e configurato un connettore, si connette al sito SFTP (Secure FTP) di Bloomberg dell'organizzazione una volta al giorno e importa gli elementi di posta elettronica nelle cassette postali di Microsoft 365.

Dopo aver archiviato i dati dei messaggi di Bloomberg nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo, la conformità delle comunicazioni e i criteri di conservazione di Microsoft 365 ai dati dei messaggi di Bloomberg. Ad esempio, è possibile cercare i messaggi di posta elettronica di Bloomberg utilizzando lo strumento di ricerca del contenuto o associare la cassetta postale contenente i dati del messaggio Bloomberg a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore di messaggi Bloomberg per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Panoramica dell'archiviazione dei dati dei messaggi bloomberg

La seguente panoramica spiega il processo di utilizzo di un connettore per archiviare i dati dei messaggi bloomberg in Microsoft 365.

![Processo di importazione e archiviazione dei messaggi bloomberg](../media/BloombergMessageArchiving.png)

1. L'organizzazione collabora con Bloomberg per configurare un sito SFTP di Bloomberg. Si lavora anche con Bloomberg per configurare Bloomberg Message per copiare i messaggi di posta elettronica nel sito SFTP di Bloomberg.

2. Una volta ogni 24 ore, i messaggi di posta elettronica provenienti da Bloomberg Message vengono copiati nel sito SFTP di Bloomberg.

3. Il connettore di messaggi Bloomberg creato nel Centro conformità Microsoft 365 si connette al sito SFTP di Bloomberg ogni giorno e trasferisce i messaggi di posta elettronica dalle 24 ore precedenti a un'area di archiviazione sicura di Azure in Microsoft Cloud.

4. Il connettore importa gli elementi dei messaggi di posta elettronica nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata BloombergMessage nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. 

   Il connettore esegue questa operazione utilizzando il valore della proprietà CorporateEmailAddress. Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti tramite il valore della proprietà *CorporateEmailAddress,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene un UUID Bloomberg e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente dell'organizzazione. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizza la proprietà *CorporateEmailAddress* dell'elemento di posta elettronica. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati dei messaggi bloomberg sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Sottoscrivi [Bloomberg via Internet.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) Questa operazione è necessaria per poter accedere a Bloomberg via Internet per accedere al sito SFTP di Bloomberg che è necessario configurare.

- Configurare un sito SFTP (Secure File Transfer Protocol) di Bloomberg. Dopo aver lavorato con Bloomberg per configurare il sito SFTP, i dati del messaggio Bloomberg vengono caricati nel sito SFTP ogni giorno. Il connettore creato nel passaggio 2 si connette a questo sito SFTP e trasferisce i dati di posta elettronica alle cassette postali di Microsoft 365. SFTP crittografa anche i dati del messaggio Bloomberg inviati alle cassette postali durante il processo di trasferimento.

  Per informazioni su Bloomberg SFTP (denominato *anche BB-SFTP):*

  - Vedere il documento "Standard di connettività SFTP" in [Bloomberg Support.](https://www.bloomberg.com/professional/support/documentation/)

  - Contattare [il supporto clienti Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

   > [!NOTE]
   > Se l'organizzazione ha già distribuito un connettore per archiviare i dati di Instant Bloomberg, non è necessario configurare un altro sito SFTP. È possibile utilizzare lo stesso sito SFTP per il connettore di messaggi Bloomberg.

- Dopo aver collaborare con Bloomberg per configurare un sito SFTP, Bloomberg fornirà alcune informazioni dopo aver risposto al messaggio di posta elettronica di implementazione di Bloomberg. Salvare una copia delle informazioni seguenti. Viene utilizzato per configurare un connettore nel passaggio 3.

  - Codice della società, che è un ID per l'organizzazione e viene usato per accedere al sito SFTP di Bloomberg.

  - Password per il sito SFTP di Bloomberg

  - URL del sito SFTP di Bloomberg (ad esempio, sftp.bloomberg.com). Inoltre, Bloomberg può anche fornire un indirizzo IP corrispondente per il sito SFTP di Bloomberg, che può essere utilizzato anche per configurare il connettore.

  - Numero di porta per il sito SFTP di Bloomberg

- Il connettore di messaggi Bloomberg può importare un totale di 200.000 elementi in un singolo giorno. Se nel sito SFTP sono presenti più di 200.000 elementi, nessuno di questi elementi verrà importato in Microsoft 365.

- All'utente che crea un connettore di messaggi Bloomberg nel passaggio 3 (e che scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Passaggio 1: Ottenere le chiavi pubbliche SSH e PGP

Il primo passaggio consiste nell'ottenere una copia delle chiavi pubbliche per Secure Shell (SSH) e Pretty Good Privacy (PGP). Queste chiavi vengono usate nel passaggio 2 per configurare il sito SFTP di Bloomberg per consentire al connettore (creato nel passaggio 3) di connettersi al sito SFTP e trasferire i dati di posta elettronica del messaggio Bloomberg alle cassette postali di Microsoft 365. In questo passaggio si ottiene anche un indirizzo IP da utilizzare per la configurazione del sito SFTP di Bloomberg.

1. Andare a [ https://compliance.microsoft.com\ ]( https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati in** **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **di descrizione del prodotto Bloomberg Message,** fare clic **su Aggiungi connettore**

4. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

5. Nel sito Add **credentials for Bloomberg SFTP** al passaggio 1 fare clic sulla chiave **Download SSH,** scaricare la chiave **PGP** e scaricare i collegamenti all'indirizzo **IP** per salvare una copia di ogni file nel computer locale. Questi file contengono gli elementi seguenti che vengono utilizzati per configurare il sito SFTP di Bloomberg nel passaggio 2:

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare Secure Shell (SSH) per abilitare un accesso remoto protetto quando il connettore si connette al sito SFTP di Bloomberg.

   - Chiave pubblica PGP: questa chiave viene usata per configurare la crittografia dei dati trasferiti dal sito SFTP di Bloomberg a Microsoft 365.

   - Indirizzo IP: il sito SFTP di Bloomberg è configurato per accettare una richiesta di connessione solo da questo indirizzo IP, che viene utilizzato dal connettore di messaggi Bloomberg creato nel passaggio 3.

6. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 3 per creare il connettore.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Passaggio 2: Configurare il sito SFTP di Bloomberg

> [!NOTE]
> Come indicato in precedenza, se l'organizzazione ha precedentemente configurato un sito SFTP di Bloomberg per archiviare i dati di Instant Bloomberg, non è necessario configurarne un altro. È possibile specificare lo stesso sito SFTP quando si crea il connettore nel passaggio 3.

Il passaggio successivo consiste nell'usare le chiavi pubbliche SSH e PGP e l'indirizzo IP ottenuto nel passaggio 1 per configurare l'autenticazione SSH e la crittografia PGP per il sito SFTP di Bloomberg. Ciò consente al connettore di messaggi Bloomberg creato nel passaggio 3 di connettersi al sito SFTP di Bloomberg e trasferire i dati dei messaggi bloomberg in Microsoft 365. È necessario collaborare con il supporto clienti bloomberg per configurare il sito SFTP di Bloomberg. Contattare [il supporto clienti Bloomberg per](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) assistenza.

> [!IMPORTANT]
> Bloomberg consiglia di allegare i tre file scaricati nel passaggio 1 a un messaggio di posta elettronica e inviarli al team di supporto clienti quando lavorano con loro per configurare il sito SFTP di Bloomberg.

## <a name="step-3-create-a-bloomberg-message-connector"></a>Passaggio 3: Creare un connettore di messaggi bloomberg

L'ultimo passaggio consiste nel creare un connettore di messaggi Bloomberg nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito SFTP di Bloomberg e trasferire i messaggi di posta elettronica alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati in** **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **di descrizione del prodotto Bloomberg Message,** fare clic **su Aggiungi connettore**

4. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

5. Nella pagina Aggiungi credenziali per il sito **SfTP di Bloomberg,** nel passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

      - **Codice della società:** ID dell'organizzazione utilizzato come nome utente per il sito SFTP di Bloomberg.

      - **Password:** Password per il sito SFTP Bloomberg dell'organizzazione.

      - **URL SFTP:** L'URL del sito SFTP di Bloomberg (ad esempio, sftp.bloomberg.com).

      - **Porta SFTP:** Numero di porta per il sito SFTP di Bloomberg. Il connettore utilizza questa porta per connettersi al sito SFTP.

6. Nella pagina **Mapping utenti abilitare il mapping** automatico degli utenti e fornire il mapping utente personalizzato in base alle esigenze

7. Fare **clic su Avanti,** rivedere le impostazioni e quindi fare clic su Prepara per creare il connettore.

8. Passare alla pagina **Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Il threading della posta elettronica di Bloomberg Message importata in Microsoft 365 non è supportato. I singoli messaggi inviati a una persona vengono importati, ma non vengono presentati in una conversazione in thread. Microsoft sta lavorando per supportare il threading nelle versioni successive del connettore dati dei messaggi Bloomberg.
