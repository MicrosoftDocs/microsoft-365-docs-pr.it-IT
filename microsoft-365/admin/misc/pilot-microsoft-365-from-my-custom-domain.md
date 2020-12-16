---
title: Eseguire il pilota Microsoft 365 dal dominio personalizzato
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Per informazioni su come eseguire il pilota della funzionalità di posta elettronica dal dominio personalizzato a una cassetta postale di Microsoft 365 usando solo due account di test.
ms.openlocfilehash: 6cc5b1163f666af4bd13047ab3b1fda7fd747b5f
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688218"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>Eseguire il pilota Microsoft 365 dal dominio personalizzato

È possibile eseguire il pilota Microsoft 365 con i requisiti e le limitazioni seguenti:

- Il provider di posta elettronica corrente deve supportare l'inoltro dei messaggi di posta elettronica.

- È necessario gestire i record DNS di Microsoft 365 presso il proprio provider di hosting DNS, piuttosto che Microsoft 365 li gestisca per tuo conto.

    Per altre informazioni, vedere [Aggiungere record DNS per connettere il dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

- Le informazioni sulla disponibilità per gli utenti dell'altro server di posta elettronica non sono disponibili.

- Gli amministratori non possono amministrare tutti gli account utente da un'unica posizione.

- Gli utenti potrebbero non essere in grado di usare il filtro della posta indesiderata di Microsoft 365.

- Si consiglia per un numero molto limitato di utenti e si applica unicamente all'utilizzo della posta elettronica per un progetto pilota.

## <a name="set-up-a-microsoft-365-pilot"></a>Configurare un progetto pilota di Microsoft 365

Seguire i passaggi seguenti per configurare un progetto pilota di Microsoft 365:

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>Passaggio 1: accedere all'interfaccia di amministrazione di Microsoft 365

1. Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) con l'account aziendale o dell’istituto di istruzione.

2. Scegliere **Impostazioni** > **Domini** nel riquadro di spostamento sinistro.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>Passaggio 2: verificare di essere proprietari del dominio che si vuole usare

1. Nella pagina **Domini**, selezionare **Aggiungere un dominio**.

2. Digitare il nome di dominio nella casella, selezionare **Usare questo dominio** e quindi selezionare **Continuare**.

3. Selezionare i servizi che si desidera testare con il dominio, ad esempio la posta elettronica e la messaggistica istantanea.

5. Nella pagina **Verifica** dominio, seguire le istruzioni dettagliate e quindi selezionare **Verificare**.

    L'applicazione delle modifiche apportate al DNS richiede da pochi minuti a 72 ore.

    Se la verifica riesce, verrà chiesto di modificare i record DNS.

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>Passaggio 3: Contrassegnare il dominio come condiviso in Exchange Online

1. Nell'interfaccia di amministrazione di Exchange, nella sezione **Flusso di posta**, selezionare **Domini accettati** e quindi selezionare il dominio da modificare.

2. Fare doppio clic per aprire la finestra e quindi selezionare **Inoltro interno**. 

3. Seleziona **Salva**.

    L'applicazione di questa impostazione può richiedere alcuni minuti.

### <a name="step-4-unblock-the-existing-email-server-optional"></a>Passaggio 4: sbloccare il server di posta elettronica esistente (facoltativo)

Microsoft 365 usa Exchange Online Protection (EOP) per la protezione dalla posta indesiderata. EOP potrebbe bloccare il server di posta esistente se rileva un volume elevato di posta indesiderata inviato dal server di posta corrente. Se si ritiene attendibile la protezione dalla posta indesiderata per l'altro provider di posta elettronica, è possibile sbloccare il server in Microsoft 365.

> [!NOTE]
> Se si sblocca il server di posta elettronica esistente, gli eventuali messaggi di posta indesiderata che giungono nel server originale verranno recapitati nelle cassette postali di Microsoft 365 e non sarà possibile valutare quanto sia efficace la prevenzione dalla posta indesiderata di Microsoft 365.

1. Nel riquadro di spostamento dell'interfaccia di amministrazione di Exchange, selezionare **Protezione**, e poi **Filtro connessioni**.

2. In **Elenco indirizzi IP consentiti**, selezionare **+** e quindi aggiungere l'indirizzo IP del server della posta per il provider di posta elettronica corrente. 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>Passaggio 5: Creare gli account utente e impostare l'indirizzo primario per le risposte

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Utenti** > **Utenti attivi**.

2. Creare due account di test aggiungendo due utenti esistenti.

    Per ciascun account, selezionare **+ Aggiungi un utente** e compilare le informazioni richieste, includendo il metodo di password che si desidera verificare.

    Per assicurarsi che la posta elettronica di un utente rimanga invariata, il campo **nome utente** deve corrispondere all'indirizzo di posta elettronica corrente dell'utente.

3. Scegliere la licenza appropriata, fare clic su **Avanti** e quindi fare clic su **Completa l'aggiunta**. 

4. Accanto a **Nome utente** selezionare il nome di dominio personalizzato nell'elenco a discesa. 

5. Selezionare **Crea** > **Chiudi**.

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a>Passaggio 6: **Configurare il flusso di posta da Microsoft 365 o Office 365 al server di posta elettronica

Esistono due procedure:

1. Configurare il proprio ambiente Microsoft 365 o Office 365.

2. Configurare un connettore da Microsoft 365 o Office 365 al server di posta elettronica.

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a>1. Configurare il proprio ambiente Microsoft 365 o Office 365.

Assicurarsi di aver completato le operazioni seguenti in Microsoft 365 o Office 365:

1. Per configurare i connettori, è necessario ricevere le autorizzazioni prima di iniziare. Per sapere quali sono le autorizzazioni necessarie, vedere la voce relativa ai connettori Microsoft 365 e Office 365 nell'argomento[Autorizzazioni di funzionalità in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop).

2. Se si desidera che EOP o Exchange Online inoltrino i messaggi dai server di posta elettronica a Internet, scegliere tra:

   - Usare un certificato configurato con un nome di oggetto che corrisponda a un dominio accettato in Microsoft 365 o Office 365. È consigliabile che il nome comune del certificato o il nome alternativo dell'oggetto corrisponda al dominio SMTP primario per l'organizzazione. Per informazioni dettagliate, vedere [Prerequisiti per l'ambiente di posta elettronica locale](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).

   -OPPURE-

   - Verificare che tutti i domini mittente dell'organizzazione e i sottodomini siano configurati come domini accettati in Microsoft 365 o Office 365.

   Per altre informazioni su come definire i domini accettati, vedere [Gestione dei domini accettati in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) e [Abilitazione del flusso di posta per i sottodomini in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

3. Decidere se si desidera usare le regole del flusso di posta (conosciute anche come regole di trasporto) o i nomi di dominio per recapitare la posta da Microsoft 365 o Office 365 ai server di posta elettronica. La maggior parte delle aziende sceglie di recapitare la posta per tutti i domini accettati. Per ulteriori informazioni, vedere [Scenario: Routing condizionale della posta in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).

> [!NOTE]
> È possibile configurare le regole del flusso di posta come descritto in [Azioni relative alla regola del flusso di posta in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) Ad esempio, è possibile utilizzare le regole del flusso di posta con i connettori se la posta è attualmente diretta tramite liste di distribuzione a più siti.

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a>2. Configurare un connettore da Microsoft 365 o Office 365 al server di posta elettronica

Per creare un connettore in Microsoft 365 o Office 365, fare clic su **Admin** e quindi su **Exchange** per accedere all'Interfaccia di amministrazione di Exchange. Successivamente, fare clic su **Flusso di posta** e scegliere **Connettori**.

Configurare i connettori usando la procedura guidata.

Per avviare la procedura guidata, fare clic sul simbolo più **+**. Nella prima schermata, scegliere **da** Office 365 e **per** il server di posta elettronica dell'organizzazione.

Fare clic su **Successivo** e seguire le istruzioni della procedura guidata. Fare clic sui collegamenti **Guida** o **Ulteriori informazioni** se si necessita di maggiori delucidazioni. La procedura guidata mostrerà le operazioni da eseguire per la configurazione. Al termine, verificare che il connettore venga convalidato. Se il connettore non viene convalidato, fare doppio clic sul messaggio visualizzato per ottenere ulteriori informazioni e vedere [Convalidare i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) per ricevere assistenza per la risoluzione dei problemi.



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a>Passaggio 7: Aggiornare i record DNS presso il provider di hosting DNS

Accedere al sito Web del proprio provider di hosting DNS e seguire le istruzioni in [Aggiungere i record DNS per connettere il dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

**Fare le seguenti due eccezioni:**

- Non creare un nuovo record MX né modificare il record MX esistente.

- Se si dispone già di un record SPF (Sender Policy Framework) per il provider di posta elettronica precedente, invece di creare un nuovo record SPF (TXT) per Exchange Online, aggiungere semplicemente "include:spf.protection.outlook.com" al record TXT corrente.

    Ad esempio, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".

    Se non si dispone ancora di un record SPF, modificare quello consigliato da Microsoft 365 in modo da includere il dominio del provider di posta elettronica corrente e aggiungere spf.protection.outlook.com. In questo modo vengono autorizzati i messaggi in uscita da entrambi i sistemi di posta elettronica. 

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a>Passaggio 8: Configurare l'inoltro della posta elettronica presso il provider corrente

Presso il provider di posta elettronica corrente impostare l'inoltro per gli account di posta elettronica sul proprio dominio onmicrosoft.com:

- Imposta l’inoltro della cassetta postale dell’utente A su usera@yourcompany.onmicrosoft.com

- Imposta l’inoltro della cassetta postale dell’utente B su userb@yourcompany.onmicrosoft.com

Al termine di questo passaggio, tutti i messaggi di posta elettronica inviati a usera@yourcompany.com e userb@yourcompany.com saranno disponibili in Microsoft 365.

> [!NOTE]
> Contattare il provider di posta elettronica corrente per l’esatta procedura di configurazione dell'inoltro della posta elettronica.<br/>
> Non è necessario conservare una copia dei messaggi presso il provider di posta elettronica corrente.<br/>
> La maggior parte dei provider inoltra la posta elettronica lasciando intatto l'indirizzo di risposta del mittente in modo che le risposte vengano recapitate al mittente originale.

### <a name="step-9-test-mail-flow"></a>Passaggio 9: Testare il flusso di posta

1. Accedere a Outlook Web App con le credenziali dell’utente A.

2. Eseguire i test seguenti:

    - Testare la posta elettronica locale di Microsoft inviando un messaggio di posta elettronica, ad esempio, all'utente B. Il messaggio viene recapitato immediatamente. In questo caso, il messaggio non viene instradato alla cassetta postale dell'utente B nel server originale perché la cassetta postale di Microsoft 365 è locale.

    - Testare la posta elettronica di un utente nel sistema di posta elettronica esistente inviando un messaggio di posta elettronica, ad esempio, all'utente C. Il messaggio viene recapitato nella cassetta postale dell'utente C nel server di posta originale.

    - Verificare che l'inoltro sia configurato correttamente da un account esterno o da un account di posta elettronica di un dipendente nel sistema di posta elettronica esistente. Ad esempio, dall'account del server originale per l’account dell’utente C o di un account Hotmail, inviare un messaggio di posta elettronica all’utente A e verificare che arrivi alla cassetta postale di Microsoft 365 dell'utente A.

### <a name="step-10-move-mailbox-contents"></a>Passaggio 10: Spostare il contenuto delle cassette postali

Dal momento che si stanno spostando solo due utenti di test e gli utenti A e B usano Outlook, è possibile spostare la posta elettronica aprendo il precedente file .PST nel nuovo profilo di Outlook e copiando i messaggi, gli elementi del calendario, i contatti e così via. Per altre informazioni, vedere [Importare posta elettronica, contatti e calendario da un file .pst di Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).

Dopo l'importazione nelle posizioni appropriate nella cassetta postale di Microsoft 365, è possibile accedere agli elementi ovunque e da qualsiasi dispositivo.

