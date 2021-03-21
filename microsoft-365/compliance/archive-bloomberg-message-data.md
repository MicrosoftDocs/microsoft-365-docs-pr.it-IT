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
description: Gli amministratori possono configurare un connettore dati per importare e archiviare i dati dallo strumento di posta elettronica Bloomberg Message in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, ricerca contenuto e criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: c29f8d0c09ce5e84ecf18830df4585f51361995b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919954"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Configurare un connettore per archiviare i dati dei messaggi bloomberg

Utilizzare un connettore dati nel Centro conformità Microsoft 365 per importare e archiviare i dati di posta elettronica dei servizi finanziari dallo strumento di collaborazione [Bloomberg Message.](https://www.bloomberg.com/professional/product/collaboration/) Dopo aver configurato e configurato un connettore, si connette al sito FTP protetto (SFTP) dell'organizzazione una volta al giorno e importa gli elementi di posta elettronica nelle cassette postali in Microsoft 365.

Dopo aver archiviato i dati dei messaggi Bloomberg nelle cassette postali degli utenti, è possibile applicare ai dati dei messaggi di Bloomberg le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, ricerca contenuto, archiviazione sul posto, controllo, conformità delle comunicazioni e criteri di conservazione di Microsoft 365. Ad esempio, è possibile cercare i messaggi di posta elettronica bloomberg utilizzando lo strumento di ricerca contenuto o associare la cassetta postale che contiene i dati del messaggio Bloomberg a un responsabile in un caso di Advanced eDiscovery. L'utilizzo di un connettore di messaggi Bloomberg per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Panoramica dell'archiviazione dei dati dei messaggi Bloomberg

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati dei messaggi Bloomberg in Microsoft 365.

![Processo di importazione e archiviazione dei messaggi Bloomberg](../media/BloombergMessageArchiving.png)

1. L'organizzazione collabora con Bloomberg per configurare un sito SFTP bloomberg. Potrai inoltre collaborare con Bloomberg per configurare Bloomberg Message in modo da copiare i messaggi di posta elettronica nel sito SFTP di Bloomberg.

2. Una volta ogni 24 ore, i messaggi di posta elettronica provenienti da Bloomberg Message vengono copiati nel sito SFTP di Bloomberg.

3. Il connettore di messaggi Bloomberg creato nel Centro conformità Microsoft 365 si connette al sito SFTP di Bloomberg ogni giorno e trasferisce i messaggi di posta elettronica dalle 24 ore precedenti a un'area di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi dei messaggi di posta elettronica nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata BloombergMessage nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. 

   Il connettore esegue questa operazione utilizzando il valore della proprietà CorporateEmailAddress. Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti utilizzando il valore della *proprietà CorporateEmailAddress,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene un UUID Bloomberg e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente dell'organizzazione. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde all'UUID Bloomberg di un utente, il connettore utilizza la proprietà *CorporateEmailAddress* dell'elemento di posta elettronica. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati dei messaggi bloomberg sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Iscriviti [a Bloomberg anywhere.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) Questa operazione è necessaria per poter accedere a Bloomberg via Internet per accedere al sito SFTP bloomberg che è necessario configurare.

- Configurare un sito Bloomberg SFTP (Secure File Transfer Protocol). Dopo aver lavorato con Bloomberg per configurare il sito SFTP, i dati di Bloomberg Message vengono caricati ogni giorno nel sito SFTP. Il connettore creato nel passaggio 2 si connette a questo sito SFTP e trasferisce i dati di posta elettronica alle cassette postali di Microsoft 365. SFTP crittografa anche i dati del messaggio Bloomberg inviati alle cassette postali durante il processo di trasferimento.

  Per informazioni su Bloomberg SFTP (denominato anche *BB-SFTP):*

  - Vedere il documento "Standard di connettività SFTP" [all'indirizzo Bloomberg Support.](https://www.bloomberg.com/professional/support/documentation/)

  - Contattare [il supporto clienti Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

   > [!NOTE]
   > Se l'organizzazione ha già distribuito un connettore per archiviare i dati di Instant Bloomberg, non è necessario configurare un altro sito SFTP. È possibile utilizzare lo stesso sito SFTP per il connettore di messaggi Bloomberg.

- Dopo aver collaborare con Bloomberg per configurare un sito SFTP, Bloomberg fornirà alcune informazioni dopo aver risposto al messaggio di posta elettronica di implementazione bloomberg. Salvare una copia delle informazioni seguenti. Utilizzarlo per configurare un connettore nel passaggio 3.

  - Codice della società, che è un ID per l'organizzazione e viene utilizzato per accedere al sito SFTP di Bloomberg.

  - Password per il sito SFTP bloomberg

  - URL del sito SFTP bloomberg (ad esempio, sftp.bloomberg.com). Inoltre, Bloomberg può anche fornire un indirizzo IP corrispondente per il sito SFTP bloomberg, che può essere utilizzato anche per configurare il connettore.

  - Numero di porta per il sito SFTP bloomberg

- Il connettore Bloomberg Message può importare un totale di 200.000 elementi in un solo giorno. Se nel sito SFTP sono presenti più di 200.000 elementi, nessuno di questi elementi verrà importato in Microsoft 365.

- All'utente che crea un connettore di messaggi Bloomberg nel passaggio 3 (e che scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori dati** nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Passaggio 1: Ottenere le chiavi pubbliche SSH e PGP

Il primo passaggio consiste nell'ottenere una copia delle chiavi pubbliche per Secure Shell (SSH) e Pretty Good Privacy (PGP). Queste chiavi vengono utilizzate nel passaggio 2 per configurare il sito SFTP bloomberg in modo da consentire al connettore creato nel passaggio 3 di connettersi al sito SFTP e trasferire i dati di posta elettronica del messaggio Bloomberg alle cassette postali di Microsoft 365. È inoltre possibile ottenere un indirizzo IP in questo passaggio, da utilizzare per la configurazione del sito SFTP bloomberg.

1. Vai a [ https://compliance.microsoft.com\ ]( https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Bloomberg Message** product description fare clic su **Add connector**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nel sito Add **credentials for Bloomberg SFTP** al passaggio 1 fare clic sulla chiave **Download SSH,** **download PGP key** e Download IP **address** links per salvare una copia di ogni file nel computer locale. Questi file contengono gli elementi seguenti che vengono utilizzati per configurare il sito SFTP bloomberg nel passaggio 2:

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare Secure Shell (SSH) per abilitare un accesso remoto sicuro quando il connettore si connette al sito SFTP di Bloomberg.

   - Chiave pubblica PGP: questa chiave viene utilizzata per configurare la crittografia dei dati trasferiti dal sito SFTP bloomberg a Microsoft 365.

   - Indirizzo IP: il sito SFTP bloomberg è configurato per accettare una richiesta di connessione solo da questo indirizzo IP, che viene utilizzato dal connettore di messaggi Bloomberg creato nel passaggio 3.

6. Fare **clic su** Annulla per chiudere la procedura guidata. Si torna a questa procedura guidata nel passaggio 3 per creare il connettore.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Passaggio 2: Configurare il sito SFTP bloomberg

> [!NOTE]
> Come indicato in precedenza, se l'organizzazione ha precedentemente configurato un sito SFTP bloomberg per archiviare i dati di Instant Bloomberg, non è necessario configurarne un altro. È possibile specificare lo stesso sito SFTP quando si crea il connettore nel passaggio 3.

Il passaggio successivo consiste nell'utilizzare le chiavi pubbliche SSH e PGP e l'indirizzo IP ottenuto nel passaggio 1 per configurare l'autenticazione SSH e la crittografia PGP per il sito SFTP bloomberg. Ciò consente al connettore di messaggi Bloomberg creato nel passaggio 3 di connettersi al sito SFTP di Bloomberg e trasferire i dati del messaggio Bloomberg a Microsoft 365. È necessario collaborare con il supporto clienti Bloomberg per configurare il sito SFTP bloomberg. Contattare [il supporto clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) per assistenza.

> [!IMPORTANT]
> Bloomberg consiglia di allegare i tre file scaricati nel passaggio 1 a un messaggio di posta elettronica e inviarli al team di supporto dei clienti quando si lavora con loro per configurare il sito SfTP bloomberg.

## <a name="step-3-create-a-bloomberg-message-connector"></a>Passaggio 3: Creare un connettore di messaggi Bloomberg

L'ultimo passaggio consiste nel creare un connettore di messaggi Bloomberg nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito SFTP bloomberg e trasferire i messaggi di posta elettronica alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati** in **Messaggio Bloomberg** fare clic su **Visualizza.**

3. Nella pagina **Bloomberg Message** product description fare clic su **Add connector**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina Aggiungi credenziali per il sito **Bloomberg SFTP,** in Passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

      - **Codice fermo:** ID dell'organizzazione utilizzato come nome utente per il sito SFTP bloomberg.

      - **Password:** Password per il sito SFTP Bloomberg dell'organizzazione.

      - **URL SFTP:** URL per il sito SFTP di Bloomberg (ad esempio, sftp.bloomberg.com).

      - **Porta SFTP:** Numero di porta per il sito SFTP bloomberg. Il connettore utilizza questa porta per connettersi al sito SFTP.

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti e fornire il mapping utente personalizzato in base alle esigenze

7. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su Prepara per creare il connettore.

8. Passare alla **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Il threading dei messaggi di Bloomberg importati in Microsoft 365 non è supportato. I singoli messaggi inviati a una persona vengono importati, ma non vengono presentati in una conversazione a thread. Microsoft sta lavorando per supportare il threading nelle versioni successive del connettore dati Bloomberg Message.