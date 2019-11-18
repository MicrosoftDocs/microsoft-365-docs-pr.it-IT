---
title: Configurare un connettore per archiviare i dati di Bloomberg istantanei in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore nativo per importare i dati dallo strumento Instant Bloomberg chat in Office 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Office 365 per consentire l'utilizzo di funzionalità di conformità, ad esempio i criteri di conservazione legale, ricerca contenuto e ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 97923fbd9bec8f5ae5fad822947c57bab08fe218
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "38686369"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365"></a>Configurare un connettore per archiviare i dati di Bloomberg istantanei in Office 365

Utilizzare un connettore nativo nel centro sicurezza & compliance in Office 365 per importare e archiviare i dati della chat dei servizi finanziari dallo strumento [Instant Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) Collaboration. Dopo aver configurato e configurato un connettore, si connette al sito FTP sicuro Bloomberg (SFTP) dell'organizzazione una volta al giorno, converte il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali di Office 365.

Dopo che i dati di Bloomberg istantanei vengono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo, la [conformità alla comunicazione](communication-compliance.md)e i criteri di conservazione di Office 365 ai dati Ad esempio, è possibile cercare i messaggi di chat di Bloomberg istantanei usando la ricerca di contenuto o associare la cassetta postale che contiene i dati di Bloomberg istantanei con un custode in un caso avanzato di eDiscovery. L'utilizzo di un connettore Bloomberg istantaneo per l'importazione e l'archiviazione dei dati in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Panoramica dell'archiviazione dei dati di messaggistica istantanea di Bloomberg

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di chat immediata di Bloomberg in Office 365. 

![Processo di importazione e archiviazione di Bloomberg istantaneo](media/InstantBloombergDataArchiving.png)

1. L'organizzazione collabora con Bloomberg per configurare un sito Bloomberg SFTP. Si lavorerà anche con Bloomberg per configurare Instant Bloomberg per copiare i messaggi di chat nel sito Bloomberg SFTP.

2. Una volta ogni 24 ore, i messaggi di chat provenienti da Instant Bloomberg vengono copiati nel sito Bloomberg SFTP.
    
3. Il connettore Bloomberg istantaneo creato nel centro sicurezza & Compliance si connette al sito Bloomberg SFTP ogni giorno e trasferisce i messaggi di chat dalle 24 ore precedenti a un'area di archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche il contenuto di un massaggio chat in un formato di messaggio di posta elettronica.
    
4. Il connettore importa gli elementi del messaggio di chat nella cassetta postale di un utente specifico o in una cassetta postale alternativa. Il connettore viene utilizzato utilizzando il valore della proprietà *CorporateEmailAddress* . Ogni messaggio di chat contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Se un elemento viene importato in una cassetta postale utente specifica o nella cassetta postale alternativa, si basa sui seguenti criteri:
    
    a. **Elementi che hanno un valore nella proprietà CorporateEmailAddress che corrisponde a un account utente di Office 365:** Se il connettore può associare l'indirizzo di posta elettronica nella proprietà *CorporateEmailAddress* a un account utente specifico in Office 365, l'elemento viene copiato nella cartella posta in arrivo nella cassetta postale di Office 365 dell'utente.
    
    b. **Elementi che dispongono di un valore nella proprietà CorporateEmailAddress che non corrisponde a un account utente di Office 365:** Se il connettore non è in grado di associare un indirizzo di posta elettronica nella proprietà *CorporateEmailAddress* a un account utente specifico di Office 365, l'elemento viene copiato nella cartella posta in arrivo di una cassetta postale alternativa "catch-all" in Office 365.

## <a name="before-you-begin"></a>Prima di iniziare

Molti dei passaggi di implementazione necessari per archiviare i dati di Bloomberg istantanei sono esterni a Office 365 e devono essere completati prima di poter creare il connettore nel centro sicurezza & Compliance.

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente il connettore Bloomberg istantaneo nel passaggio 3.

- Eseguire la sottoscrizione a [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Questa operazione è necessaria per consentire l'accesso a Bloomberg Anywhere per accedere al sito Bloomberg SFTP che è necessario impostare e configurare.

- Configurare un sito Bloomberg SFTP (Secure File Transfer Protocol). Dopo aver lavorato con Bloomberg per configurare il sito SFTP, i dati provenienti da Instant Bloomberg vengono caricati nel sito SFTP ogni giorno. Il connettore creato nel passaggio 2 si connette a questo sito SFTP e trasferisce i dati della chat alle cassette postali di Office 365. SFTP crittografa anche i dati di chat istantanea di Bloomberg inviati alle cassette postali di Office 365 durante il processo di trasferimento.

    Per informazioni su Bloomberg SFTP (denominato anche *BB-SFTP*):

    - Vedere il documento "standard di connettività SFTP" sul [supporto di Bloomberg](https://www.bloomberg.com/professional/support/documentation/).
    
    - Contattare il servizio di [assistenza clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

    Dopo aver collaborato con Bloomberg per configurare un sito SFTP, Bloomberg fornirà alcune informazioni all'utente dopo aver risposto al messaggio di posta elettronica di implementazione Bloomberg. Salvare una copia delle informazioni seguenti. È possibile utilizzarlo per configurare un connettore nel passaggio 3.

    - Codice fermo, che è un ID per l'organizzazione e che viene utilizzato per accedere al sito Bloomberg SFTP.

    - Password per il sito Bloomberg SFTP

    - URL per il sito di Bloomberg SFTP (ad esempio, sftp.bloomberg.com)

    - Numero di porta per il sito Bloomberg SFTP

- L'utente che crea un connettore Bloomberg istantaneo nel passaggio 3 (e che Scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per accedere alla pagina di **archiviazione dei dati di terze parti** nel centro sicurezza & Compliance. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Passaggio 1: ottenere le chiavi pubbliche di SSH e PGP

Il primo passaggio consiste nell'ottenere una copia delle chiavi pubbliche per Secure Shell (SSH) e la Pretty Good Privacy (PGP). È possibile utilizzare questi tasti nel passaggio 2 per configurare il sito Bloomberg SFTP per consentire il connettore (creato nel passaggio 3) per connettersi al sito SFTP e trasferire i dati di chat immediata di Bloomberg nelle cassette postali di Office 365. È inoltre possibile ottenere un indirizzo IP in questo passaggio, che viene utilizzato per la configurazione del sito Bloomberg SFTP.

1. Passare a <https://protection.office.com> e quindi fare clic su **Importa governance \> dei dati** e quindi su **archivia dati di terze parti**.

2. Nella pagina **archiviazione dei dati di terze parti** , fare clic su **Aggiungi connettore**, quindi fare clic su **Instant Bloomberg**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nel **sito Add credentials for Bloomberg SFTP** al passaggio 1, fare clic sul pulsante **Scarica SSH Key**, **scaricare PGP Key**e scaricare i collegamenti agli **indirizzi IP** per salvare una copia di ogni file nel computer locale. Questi file contengono gli elementi seguenti che vengono utilizzati per configurare il sito Bloomberg SFTP nel passaggio 2:

   - Chiave pubblica SSH: questa chiave viene utilizzata per configurare Secure Shell (SSH) per abilitare un account di accesso remoto sicuro quando il connettore si connette al sito Bloomberg SFTP.

   - Chiave pubblica PGP: questa chiave viene utilizzata per configurare la crittografia dei dati trasferiti dal sito Bloomberg SFTP a Office 365.

   - Indirizzo IP: il sito Bloomberg SFTP è configurato per accettare una richiesta di connessione solo da questo indirizzo IP, che viene utilizzato dal connettore Bloomberg istantaneo creato nel passaggio 3. 

5. Fare clic su **Annulla** per chiudere la procedura guidata. Per creare il connettore, è possibile tornare a questa procedura guidata nel passaggio 3.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Passaggio 2: configurare il sito Bloomberg SFTP

Il passaggio successivo consiste nell'utilizzare le chiavi pubbliche SSH e PGP e l'indirizzo IP ottenuto nel passaggio 1 per configurare l'autenticazione SSH e la crittografia PGP per il sito Bloomberg SFTP. In questo modo, il connettore Bloomberg istantaneo creato nel passaggio 3 si connette al sito Bloomberg SFTP e trasferisce i dati di Bloomberg istantanei a Office 365. È necessario collaborare con il supporto clienti di Bloomberg per configurare il sito Bloomberg SFTP. Contattare il [supporto clienti di Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) per assistenza. 

> [!IMPORTANT]
> Bloomberg consiglia di collegare i tre file scaricati nel passaggio 1 a un messaggio di posta elettronica e inviarlo al proprio team di supporto clienti quando si lavora con loro per configurare il sito Bloomberg SFTP.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Passaggio 3: creare un connettore Bloomberg istantaneo

L'ultimo passaggio consiste nel creare un connettore Bloomberg istantaneo nel centro sicurezza & Compliance. Il connettore utilizza le informazioni fornite per la connessione al sito Bloomberg SFTP e trasferisce i messaggi di chat nelle caselle della cassetta postale dell'utente corrispondente in Office 365. 

1. Passare a <https://protection.office.com> e quindi fare clic su **Importa governance \> dei dati** e quindi su **archivia dati di terze parti**.

2. Nella pagina **archiviazione dei dati di terze parti** , fare clic su **Aggiungi connettore**, quindi fare clic su **Instant Bloomberg**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nella pagina **Aggiungi credenziali per il sito Bloomberg SFTP** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.

    - **Codice azienda:** ID dell'organizzazione e utilizzato come nome utente per il sito Bloomberg SFTP.

    - **Password:** Password per il sito Bloomberg SFTP

    - **URL sftp:** URL per il sito Bloomberg SFTP (ad esempio, sftp.bloomberg.com).

    - **Porta SFTP:** Il numero di porta per il sito Bloomberg SFTP. Il connettore utilizza questo per la connessione al sito SFTP.

5. Nella pagina **cassetta postale alternativa** , digitare l'indirizzo di posta elettronica di una cassetta postale che viene utilizzata per archiviare i messaggi di chat da Instant Bloomberg che non sono associati a una cassetta postale dell'utente nell'organizzazione.

   > [!NOTE]
   > Ogni messaggio di chat in ogni conversazione in Instant Bloomberg include una proprietà denominata *CorporateEmailAddress*, che contiene l'indirizzo di posta elettronica dell'organizzazione per il partecipante alla chat. Durante il processo di importazione, il connettore tenta di importare i messaggi di chat in una cassetta postale di un utente in Office 365 che ha gli stessi indirizzi di posta elettronica che corrispondono a quello della proprietà *CorporateEmailAddress* . Se non esiste una cassetta postale di Office 365 con lo stesso indirizzo di quello della proprietà *CorporateEmailAddress* , il connettore importa il messaggio di chat nella cassetta postale alternativa specificata in questa pagina.

6. Fare clic su **Avanti**, rivedere le impostazioni e quindi fare clic su **prepara** per creare il connettore.

7. Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.
