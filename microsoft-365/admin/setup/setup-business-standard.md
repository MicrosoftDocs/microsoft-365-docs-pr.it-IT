---
title: Configurare Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Quando si acquista Microsoft 365 Business Standard, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno al momento dell'iscrizione.
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393812"
---
# <a name="set-up-microsoft-business-standard"></a>Configurare Microsoft Business Standard



## <a name="add-your-domain-to-personalize-sign-in"></a>Aggiungere il proprio dominio per personalizzare l’accesso

Quando si acquista Microsoft 365 Business Standard, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno durante l’iscrizione.

- Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).

1. Autenticarsi allì[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le proprie credenziali globali di amministrazione. 

2. Scegliere **Vai alla configurazione** per avviare la procedura guidata.

3. Nella pagina **Installa le tue app di Office**, è possibile installare le app sul proprio computer.
    
4. Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).

    > [!IMPORTANT]
    > Se un dominio è stato acquistato durante l'iscrizione, il passaggio **Aggiungi un dominio** non comparirà. In alternativa, andare a [Aggiungi utenti](#add-users-and-assign-licenses).

    
4. Seguire i passaggi della procedura guidata per [creare record DNS presso un provider DNS per Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio. Se si conosce l'host del dominio, vedere anche [Aggiungere un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Aggiungere utenti e assegnare licenze

Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](../add-users/add-users.md) nell’interfaccia di amministrazione. Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Aggiungere utenti nella procedura guidata

A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una licenza di Microsoft 365 Business Standard.

1. Se l'abbonamento a Microsoft 365 Business Standard include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un’opzione per assegnare le licenze a questi utenti.

2. Dopo aver aggiunto gli utenti, sarà disponibile anche un'opzione per la condivisione delle credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.

## <a name="connect-your-domain"></a>Connettere il proprio dominio

> [!NOTE]
> Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.
  
Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.
  
1. La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web. Se ciò non si verifica, [Modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**. Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.
    - Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi. Vedere [dati principali domini](/office365/admin/get-help-with-domains/dns-basics) per altre informazioni.

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

## <a name="watch-set-up-outlook-for-email"></a>Video: Configurare Outlook per la posta elettronica

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Per altre informazioni, vedere [Configurare Outlook per la posta elettronica](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>Importare la posta elettronica

Se si stava usando Outlook con un altro account di posta elettronica, è possibile importare i messaggi, il calendario e i contatti precedenti nel nuovo account Microsoft.
  
1. **Esportare i vecchi messaggi di posta elettronica**

    In Outlook scegliere **File** \> **Apri ed esporta&amp;** \> **Importa/Esporta**.

    Selezionare **Esporta in un file** e quindi seguire le istruzioni per esportare il file di dati di Outlook (pst) e le eventuali sottocartelle.

2. **Importare i vecchi messaggi di posta elettronica**

    In Outlook scegliere **File** \> **Apri ed&amp; esporta** \> **Importa/Esporta**.

    Questa volta, selezionare **Importa dati da altri programmi o file** e seguire le istruzioni per importare il file di backup creato al momento dell'esportazione dei vecchi messaggi di posta elettronica.

## <a name="watch-import-and-redirect-email"></a>Video: Importare e reindirizzare la posta elettronica

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Per altre informazioni, vedere [Importare la posta elettronica con Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

È anche possibile usare l’interfaccia di amministrazione di Exchange per importare la posta elettronica di tutti gli utenti. Per altre informazioni, vedere [Migrazione di account multipli di posta elettronica](/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Usare un sito Web pubblico

Microsoft 365 non include un sito Web pubblico che possa essere usato dall'azienda. Se si vuole configurarne uno, è consigliabile usare un partner Microsoft, come GoDaddy o WIX.
  
1. Nell'interfaccia di amministrazione passare a **Risorse** e quindi selezionare **Sito Web pubblico**.

2. Selezionare **Altre informazioni** sotto una delle opzioni, quindi effettuare l'iscrizione con un partner di siti Web e usare i suoi strumenti per configurare e progettare il sito.

## <a name="watch-create-your-business-website"></a>Video: Creare il sito Web dell'azienda

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a>Contenuto correlato

[Creare un sito Web](../../business-video/create-web-site.md) (video)\
[Microsoft 365 per l'azienda](../../business-video/index.yml) (collegamento alla pagina)
