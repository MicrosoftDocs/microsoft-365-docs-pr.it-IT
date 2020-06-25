---
title: Configurare Microsoft 365 Business Basic
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
description: Informazioni su come configurare la sottoscrizione a Microsoft 365 Business Basic.
ms.openlocfilehash: 9b448db2a6b8c78bb5265b1e80a01e93c9a6c6ca
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778902"
---
# <a name="set-up-microsoft-365-business-basic"></a>Configurare Microsoft 365 Business Basic

 È possibile guardare un breve video sulla configurazione di Microsoft 365 Business Basic.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Aggiungere il proprio dominio per personalizzare l’accesso

Quando si acquista Microsoft 365 Business Basic, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno durante l’iscrizione.

- Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Se si usa Office 365 Germany, passare a questa [interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041).

::: moniker-end

::: moniker range="o365-21vianet"

1. Se si usa Office 365 gestito da 21Vianet, passare a questa [interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627).

::: moniker-end 

2. Scegliere **Vai alla configurazione** per avviare la procedura guidata.
    
3. Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).

    > [!IMPORTANT]
    > Se un dominio è stato acquistato durante l’iscrizione, il passaggio **Aggiungi un dominio** non comparirà. Proseguire al passaggio [Aggiungi utenti](#add-users-and-assign-licenses).

    
4. Seguire i passaggi della procedura guidata per [creare record DNS presso un provider DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio. Se si conosce l’host del dominio, vedere anche le [istruzioni specifiche dell’host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Aggiungere utenti e assegnare licenze

Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](../add-users/add-users.md) nell’interfaccia di amministrazione. Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Aggiungere utenti nella procedura guidata

A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una licenza di Microsoft 365 Business Basic.

1. Se la sottoscrizione a Microsoft 365 Business Basic include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un’opzione per assegnare le licenze a questi utenti. Procedere aggiungendo le licenze anche per questi utenti.

2. Una volta aggiunti gli utenti, sarà disponibile un’opzione per condividere le credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.

## <a name="connect-your-domain"></a>Connettere il proprio dominio

> [!NOTE]
> Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.
  
Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.
  
1. La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web. Se ciò non si verifica, [Modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**. Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.
    - Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi. Vedere [Informazioni di base sul dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) per maggiori dettagli.

2. Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.

    Una volta completato il processo di iscrizione si verrà reindirizzati all’interfaccia di amministrazione, dove è possibile aggiungere gli utenti e assegnare le licenze. Dopo aver completato la configurazione iniziale, è possibile usare la pagina **Configurazione** dell'interfaccia di amministrazione per continuare a configurare i servizi disponibili con gli abbonamenti.

    Per altre informazioni sulla configurazione guidata e sulla pagina **Configurazione** dell'interfaccia di amministrazione, vedere [Differenze tra la configurazione guidata e la pagina Configurazione](o365-setup-wizard-and-setup-page.md).