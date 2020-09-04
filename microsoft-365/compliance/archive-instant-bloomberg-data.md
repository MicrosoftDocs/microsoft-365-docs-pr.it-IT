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
description: Informazioni su come gli amministratori possono configurare e utilizzare un connettore di dati per importare e archiviare i dati dallo strumento Instant Bloomberg chat in Microsoft 365.
ms.openlocfilehash: 4df1a67ae9e372efe5c6e8c654f1a6821b5cb30d
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358238"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Configurare un connettore per archiviare i dati di Instant Bloomberg

Utilizzare un connettore nativo nel centro conformità di Microsoft 365 per importare e archiviare i dati della chat dei servizi finanziari dallo strumento [Instant Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) Collaboration. Dopo aver configurato e configurato un connettore, si connette al sito FTP sicuro Bloomberg (SFTP) dell'organizzazione una volta al giorno, converte il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali in Microsoft 365.

Dopo che i dati di Bloomberg istantanei vengono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo, la conformità alla comunicazione e i criteri di conservazione di Microsoft 365 ai dati Ad esempio, è possibile cercare i messaggi di chat di Bloomberg istantanei usando la ricerca di contenuto o associare la cassetta postale che contiene i dati di Bloomberg istantanei con un custode in un caso avanzato di eDiscovery. L'utilizzo di un connettore Bloomberg istantaneo per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Panoramica dell'archiviazione dei dati di messaggistica istantanea di Bloomberg

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di chat immediata di Bloomberg in Microsoft 365. 

![Processo di importazione e archiviazione di Bloomberg istantaneo](../media/InstantBloombergDataArchiving.png)

1. L'organizzazione collabora con Bloomberg per configurare un sito Bloomberg SFTP. È inoltre possibile collaborare con Bloomberg per configurare Instant Bloomberg per copiare i messaggi di chat nel sito Bloomberg SFTP.

2. Una volta ogni 24 ore, i messaggi di chat provenienti da Instant Bloomberg vengono copiati nel sito Bloomberg SFTP.

3. Il connettore Bloomberg istantaneo creato nel centro conformità di Microsoft 365 si connette al sito Bloomberg SFTP ogni giorno e trasferisce i messaggi di chat dalle 24 ore precedenti a un'area di archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche il contenuto di un massaggio chat in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi del messaggio di chat nella cassetta postale di un utente specifico. Verrà creata una nuova cartella denominata InstantBloomberg nella cassetta postale dell'utente specifico e gli elementi verranno importati. Il connettore esegue questa operazione utilizzando il valore della proprietà *CorporateEmailAddress* . Ogni messaggio di chat contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Oltre a eseguire il mapping automatico degli utenti utilizzando il valore della proprietà *CorporateEmailAddress* , è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere un UUID di Bloomberg e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si Abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat il connettore osserverà per prima cosa il file di mapping personalizzato. Se non trova un utente valido di Microsoft 365 che corrisponde all'UUID di Bloomberg di un utente, il connettore utilizzerà la proprietà *CorporateEmailAddress* dell'elemento chat. Se il connettore non trova un utente valido di Microsoft 365 nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento chat, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di Bloomberg istantanei sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel centro conformità.

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente il connettore Bloomberg istantaneo nel passaggio 3.

- Eseguire la sottoscrizione a [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Questa operazione è necessaria per consentire l'accesso a Bloomberg Anywhere per accedere al sito Bloomberg SFTP che è necessario impostare e configurare.

- Configurare un sito Bloomberg SFTP (Secure File Transfer Protocol). Dopo aver lavorato con Bloomberg per configurare il sito SFTP, i dati provenienti da Instant Bloomberg vengono caricati nel sito SFTP ogni giorno. Il connettore creato nel passaggio 2 si connette a questo sito SFTP e trasferisce i dati della chat alle cassette postali di Microsoft 365. SFTP crittografa anche i dati di chat istantanea di Bloomberg inviati alle cassette postali durante il processo di trasferimento.

  Per informazioni su Bloomberg SFTP (denominato anche *BB-SFTP*):

  - Vedere il documento "standard di connettività SFTP" sul [supporto di Bloomberg](https://www.bloomberg.com/professional/support/documentation/).

  - Contattare il servizio di [assistenza clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

  Dopo aver collaborato con Bloomberg per configurare un sito SFTP, Bloomberg fornirà alcune informazioni all'utente dopo aver risposto al messaggio di posta elettronica di implementazione Bloomberg. Salvare una copia delle informazioni seguenti. È possibile utilizzarlo per configurare un connettore nel passaggio 3.

  - Codice fermo, che è un ID per l'organizzazione e che viene utilizzato per accedere al sito Bloomberg SFTP.

  - Password per il sito Bloomberg SFTP

  - URL per il sito di Bloomberg SFTP (ad esempio, sftp.bloomberg.com)

  - Numero di porta per il sito Bloomberg SFTP

- L'utente che crea un connettore Bloomberg istantaneo nel passaggio 3 (e che Scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **connettori dati** del centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Passaggio 1: ottenere le chiavi pubbliche di SSH e PGP

Il primo passaggio consiste nell'ottenere una copia delle chiavi pubbliche per Secure Shell (SSH) e la Pretty Good Privacy (PGP). È possibile utilizzare questi tasti nel passaggio 2 per configurare il sito Bloomberg SFTP per consentire il connettore (creato nel passaggio 3) per connettersi al sito SFTP e trasferire i dati di chat immediata di Bloomberg nelle cassette postali di Microsoft 365. È inoltre possibile ottenere un indirizzo IP in questo passaggio, che viene utilizzato per la configurazione del sito Bloomberg SFTP.

1. Andare a <https://compliance.microsoft.com> e quindi fare clic su **connettori dati**  >  **Instant Bloomberg**.

2. Nella pagina Descrizione prodotto **immediata di Bloomberg** fare clic su **Aggiungi connettore**

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nel **sito Add credentials for Bloomberg SFTP** al passaggio 1, fare clic sul pulsante **Scarica SSH Key**, **scaricare PGP Key**e scaricare i collegamenti agli **indirizzi IP** per salvare una copia di ogni file nel computer locale. Questi file contengono gli elementi seguenti che vengono utilizzati per configurare il sito Bloomberg SFTP nel passaggio 2:

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare Secure Shell (SSH) per abilitare un account di accesso remoto sicuro quando il connettore si connette al sito Bloomberg SFTP.

   - Chiave pubblica PGP: questa chiave viene utilizzata per configurare la crittografia dei dati trasferiti dal sito Bloomberg SFTP a Microsoft 365.

   - Indirizzo IP: il sito Bloomberg SFTP è configurato per accettare una richiesta di connessione solo da questo indirizzo IP, che viene utilizzato dal connettore Bloomberg istantaneo creato nel passaggio 3. 

5. Fare clic su **Annulla** per chiudere la procedura guidata. Per creare il connettore, è possibile tornare a questa procedura guidata nel passaggio 3.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Passaggio 2: configurare il sito Bloomberg SFTP

Il passaggio successivo consiste nell'utilizzare le chiavi pubbliche SSH e PGP e l'indirizzo IP ottenuto nel passaggio 1 per configurare l'autenticazione SSH e la crittografia PGP per il sito Bloomberg SFTP. In questo modo, il connettore Bloomberg istantaneo creato nel passaggio 3 si connette al sito Bloomberg SFTP e trasferisce i dati di Bloomberg istantanei a Microsoft 365. È necessario collaborare con il supporto clienti di Bloomberg per configurare il sito Bloomberg SFTP. Contattare il [supporto clienti di Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) per assistenza. 

> [!IMPORTANT]
> Bloomberg consiglia di collegare i tre file scaricati nel passaggio 1 a un messaggio di posta elettronica e inviarlo al proprio team di supporto clienti quando si lavora con loro per configurare il sito Bloomberg SFTP.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Passaggio 3: creare un connettore Bloomberg istantaneo

L'ultimo passaggio consiste nel creare un connettore Bloomberg istantaneo nel centro conformità di Microsoft 365. Il connettore utilizza le informazioni fornite per la connessione al sito Bloomberg SFTP e trasferisce i messaggi di chat nelle caselle della cassetta postale dell'utente corrispondente in Microsoft 365.

1. Andare a <https://compliance.microsoft.com> e quindi fare clic su **connettori dati**  >  **Instant Bloomberg**.

2. Nella pagina Descrizione prodotto **immediata di Bloomberg** fare clic su **Aggiungi connettore**

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nella pagina **Aggiungi credenziali per il sito Bloomberg SFTP** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.

    - **Codice azienda:** ID dell'organizzazione utilizzato come nome utente per il sito Bloomberg SFTP.

    - **Password:** Password per il sito Bloomberg SFTP.

    - **URL sftp:** URL per il sito Bloomberg SFTP (ad esempio, sftp.bloomberg.com).

    - **Porta SFTP:** Il numero di porta per il sito Bloomberg SFTP. Il connettore utilizza questa porta per la connessione al sito SFTP.

5. Nella pagina **mapping utenti** abilitare il mapping automatico degli utenti e fornire il mapping degli utenti personalizzato come richiesto

   > [!NOTE]
   > Il connettore importa gli elementi del messaggio di chat nella cassetta postale di un utente specifico. Verrà creata una nuova cartella denominata **InstantBloomberg** nella cassetta postale dell'utente specifico e gli elementi verranno importati. Il connettore viene utilizzato utilizzando il valore della proprietà *CorporateEmailAddress* . Ogni messaggio di chat contiene questa proprietà e la proprietà viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Oltre a eseguire il mapping automatico degli utenti utilizzando il valore della proprietà *CorporateEmailAddress* , è anche possibile definire il mapping personalizzato caricando un file di mapping CSV. Il file di mapping deve contenere l'UUID di Bloomberg e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si Abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di chat il connettore osserverà per prima cosa il file di mapping personalizzato. Se non trova un utente valido di Microsoft 365 che corrisponde all'UUID di Bloomberg di un utente, il connettore utilizzerà la proprietà *CorporateEmailAddress* dell'elemento chat. Se il connettore non trova un utente valido di Microsoft 365 nel file di mapping personalizzato o nella proprietà *CorporateEmailAddress* dell'elemento chat, l'elemento non verrà importato.

6. Fare clic su **Avanti**, rivedere le impostazioni e quindi fare clic su **prepara** per creare il connettore.

7. Passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.
