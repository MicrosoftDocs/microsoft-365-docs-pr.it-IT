---
title: Configurare Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Informazioni su come configurare la sottoscrizione a Microsoft 365 Business Standard.
ms.openlocfilehash: cfc198c749cfcaa76bc3fa6323e1dba8a46e7388
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324447"
---
# <a name="set-up-microsoft-business-standard"></a>Configurare Microsoft Business Standard

Guardare un breve video sulla configurazione di Microsoft 365 Business Standard.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ELKR]

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
 *Queste procedure interessano le aziende e le [organizzazioni no profit](https://go.microsoft.com/fwlink/p/?LinkId=627221) che usano il **[piano Microsoft 365 Business Standard](https://go.microsoft.com/fwlink/p/?LinkId=627220)***.

È possibile guardare un breve video sulla configurazione di Microsoft 365 Business Standard (noto in precedenza come Office 365 Business Premium).<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Aggiungere il proprio dominio per personalizzare l’accesso

Quando si acquista Microsoft 365 Business Standard, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno durante l’iscrizione.

- Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).

1. Autenticarsi allì[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le proprie credenziali globali di amministrazione. 

2. Scegliere **Vai alla configurazione** per avviare la procedura guidata.

3. Nella pagina **Installa le tue app di Office**, è possibile installare le app sul proprio computer.
    
4. Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).

    > [!IMPORTANT]
    > Se un dominio è stato acquistato durante l’iscrizione, il passaggio **Aggiungi un dominio** non comparirà. Proseguire al passaggio [Aggiungi utenti](#add-users-and-assign-licenses).

    
4. Seguire i passaggi della procedura guidata per [creare record DNS presso un provider DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio. Se si conosce l’host del dominio, vedere anche le [istruzioni specifiche dell’host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Aggiungere utenti e assegnare licenze

Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](../add-users/add-users.md) nell’interfaccia di amministrazione. Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Aggiungere utenti nella procedura guidata

A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una licenza di Microsoft 365 Business Standard.

1. Se la sottoscrizione a Microsoft 365 Business Standard include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un’opzione per assegnare le licenze a questi utenti. Procedere aggiungendo le licenze anche per questi utenti.

2. Una volta aggiunti gli utenti, sarà disponibile un’opzione per condividere le credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.

## <a name="connect-your-domain"></a>Connettere il proprio dominio

> [!NOTE]
> Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.
  
Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.
  
1. La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web. Se ciò non si verifica, [Modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**. Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.
    - Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi. Vedere [Informazioni di base sul dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) per maggiori dettagli.

2. Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.

    Una volta completato il processo di iscrizione, si verrà reindirizzati all'interfaccia di amministrazione, in cui si seguirà una procedura guidata per l'installazione delle app di Office, l'aggiunta del dominio, l'aggiunta degli utenti e l'assegnazione delle licenze. Dopo aver completato la configurazione iniziale, è possibile usare la pagina **Configurazione** dell'interfaccia di amministrazione per continuare a configurare i servizi disponibili con gli abbonamenti.

    Per altre informazioni sulla configurazione guidata e sulla pagina **Configurazione** dell'interfaccia di amministrazione, vedere [Differenze tra la configurazione guidata e la pagina Configurazione](o365-setup-wizard-and-setup-page.md).

## <a name="finish-setting-up"></a>Completare la configurazione

### <a name="set-up-outlook-for-email"></a>Configurare Outlook per la posta elettronica

1. Nel menu Start di Windows cercare Outlook e selezionarlo.

    Se si usa un Mac, aprire Outlook dalla barra degli strumenti o cercarlo con il Finder.

    Se Outlook è già stato installato, nella pagina di benvenuto selezionare **Avanti**.

2. Scegliere **File** \> **Informazioni** \> **Aggiungi account**.

3. Immettere il proprio indirizzo di posta elettronica Microsoft e selezionare **Connetti**.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Per altre informazioni, vedere [Configurare Outlook per la posta elettronica](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>Importare la posta elettronica

Se si stava usando Outlook con un altro account di posta elettronica, è possibile importare i messaggi, il calendario e i contatti precedenti nel nuovo account Microsoft.
  
1. **Esportare i vecchi messaggi di posta elettronica**

    In Outlook scegliere **File** \> **Apri ed esporta&amp; ** \> **Importa/Esporta**.

    Selezionare **Esporta in un file** e quindi seguire le istruzioni per esportare il file di dati di Outlook (pst) e le eventuali sottocartelle.

2. **Importare i vecchi messaggi di posta elettronica**

    In Outlook scegliere **File** \> **Apri ed&amp; esporta** \> **Importa/Esporta**.

    Questa volta, selezionare **Importa dati da altri programmi o file** e seguire le istruzioni per importare il file di backup creato al momento dell'esportazione dei vecchi messaggi di posta elettronica.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Per altre informazioni, vedere [Importare la posta elettronica con Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

È anche possibile usare l’interfaccia di amministrazione di Exchange per importare la posta elettronica di tutti gli utenti. Per altre informazioni, vedere [Migrazione di account multipli di posta elettronica](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Usare un sito Web pubblico

Microsoft 365 non include un sito Web pubblico che possa essere usato dall'azienda. Se si vuole configurarne uno, è consigliabile usare un partner Microsoft, come GoDaddy o WIX.
  
1. Nell'interfaccia di amministrazione passare a **Risorse** e quindi selezionare **Sito Web pubblico**.

2. Selezionare **Altre informazioni** sotto una delle opzioni, quindi effettuare l'iscrizione con un partner di siti Web e usare i suoi strumenti per configurare e progettare il sito.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

Per altre informazioni, vedere [Usare un sito Web pubblico](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).