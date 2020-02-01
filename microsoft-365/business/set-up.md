---
title: Configurare Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni su come configurare Microsoft 365 business.
ms.openlocfilehash: c370a5b3fd735e704eea56ac1079bb2e5dad4c4b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594270"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Configurare Microsoft 365 business nell'installazione guidata

Guardare questo video per una panoramica della configurazione di Microsoft 365 business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se il video è stato utile, consultare la [serie di formazione completa a Microsoft 365 per le piccole e nuove imprese](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Aggiungere il dominio, gli utenti e i criteri di configurazione

[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Quando si acquista Microsoft 365 business, si ha la possibilità di utilizzare un dominio che si è proprietari o di acquistarne uno durante l' [iscrizione](sign-up.md).

- Se si è acquistato un nuovo dominio al momento dell'iscrizione, il dominio è tutto configurato ed è possibile spostarsi per [aggiungere utenti e assegnare licenze](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Aggiungere il dominio per personalizzare l'accesso

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali di amministratore globale. 

2. Scegliere **Vai a installazione** per avviare la procedura guidata.

    ![Selezionare Vai a installazione.](media/gotosetupinadmincenter.png)

3. Nella pagina **installa le app di Office** , è possibile installare le app nel proprio computer.
    
4. Nel passaggio **Aggiungi dominio** , immettere il nome di dominio che si desidera utilizzare (come contoso.com).

    > [!IMPORTANT]
    > Se si è acquistato un dominio durante l'iscrizione, non verrà visualizzato **aggiungere un passaggio di dominio** qui. Andare su [Aggiungi utenti](#add-users-and-assign-licenses) .

    ![Schermata della pagina Personalizza il tuo accesso.](media/adddomain.png)

    
4. Seguire i passaggi della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio. Se si conosce l'host di dominio, vedere anche le [istruzioni specifiche dell'host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se il provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e verrà automaticamente chiesto di accedere e di consentire a Microsoft di eseguire l'autenticazione per conto dell'utente.

    ![Nella pagina Conferma accesso GoDaddy selezionare autorizza.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Aggiungere utenti e assegnare licenze

È possibile aggiungere utenti nella procedura guidata, ma è anche possibile [aggiungerli in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione. Inoltre, se si dispone di un controller di dominio locale, è possibile aggiungere utenti con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Aggiungere gli utenti nella procedura guidata

Tutti gli utenti aggiunti nella procedura guidata vengono assegnati automaticamente a una licenza aziendale Microsoft 365.

![Schermata della pagina Aggiungi nuovi utenti nella procedura guidata](media/addnewuserspage.png)

1. Se l'abbonamento a Microsoft 365 business ha utenti esistenti (ad esempio, se è stato utilizzato Azure AD Connect), è possibile assegnare loro le licenze. Procedere con l'aggiunta di licenze anche per questi utenti.

2. Dopo aver aggiunto gli utenti, si otterrà anche un'opzione per condividere le credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.

### <a name="connect-your-domain"></a>Connettere il dominio

> [!NOTE]
> Se si è scelto di utilizzare il dominio. onmicrosoft o di Azure AD Connect per configurare gli utenti, questo passaggio non verrà visualizzato.
  
Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.
  
1. La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web. In caso contrario, [modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Se si dispone di record DNS esistenti, ad esempio un sito Web esistente, ma l'host DNS è abilitato per la [connessione al dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Add records for me**. Nella pagina **scegliere i servizi online** accettare tutte le impostazioni predefinite e scegliere **Avanti**, quindi fare clic su **autorizza** nella pagina dell'host DNS.
    - Se sono presenti record DNS con altri host DNS (non abilitati per la connessione al dominio), è necessario gestire i propri record DNS per assicurarsi che i servizi esistenti siano connessi. Per altre informazioni, vedere [Domain nozioni di base](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .

        ![Attiva la pagina dei record.](media/activaterecords.png)

2. Seguire i passaggi della procedura guidata e la posta elettronica e altri servizi verranno configurati per l'utente.

### <a name="protect-your-organization"></a>Proteggere l'organizzazione 

I criteri configurati nella procedura guidata vengono applicati automaticamente a un [gruppo di sicurezza](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominato *tutti gli utenti*. È inoltre possibile creare altri gruppi per assegnare criteri nell'interfaccia di amministrazione.

1. Per **aumentare la protezione da minacce informatiche avanzate**, è consigliabile accettare le impostazioni predefinite per consentire a [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) di eseguire l'analisi dei file di protezione dalle minacce e i collegamenti nelle app di Office.

    ![Schermata della pagina aumenta protezione.](media/increasetreatprotection.png)


2. Nella pagina **Impedisci perdite di dati sensibili** , accettare le impostazioni predefinite per abilitare la prevenzione della perdita di dati (DLP) di Office 365 per tenere sotto controllo i dati sensibili nelle app di Office e impedire la condivisione accidentale di questi all'esterno dell'organizzazione.

3. Nella pagina **Proteggi dati in Office per dispositivi** mobili, lascia la gestione delle app per dispositivi mobili, Espandi le impostazioni e rivedile e quindi seleziona **Crea criteri di gestione delle app per dispositivi mobili**.

    ![Schermata della pagina Proteggi dati in Office per dispositivi mobili.](media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteggere i PC Windows 10

Sulla barra di spostamento sinistra, selezionare **installazione** e quindi, in **sing-in e sicurezza**, scegliere **Proteggi i computer Windows 10**. Scegliere **View** per iniziare. Per istruzioni complete, vedere [proteggere i computer Windows 10](secure-win-10-pcs.md) .

## <a name="deploy-office-365-client-apps"></a>Distribuire le app client di Office 365

Se si è scelto di installare automaticamente le app di Office durante l'installazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno effettuato l'accesso a Azure AD dai propri dispositivi Windows, utilizzando le proprie credenziali di lavoro.

Per installare Office su dispositivi mobili iOS o Android, vedere [configurare i dispositivi mobili per gli utenti aziendali di Microsoft 365](set-up-mobile-devices.md).

È anche possibile installare Office individualmente. Per istruzioni, vedere [installare Office in un PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .

## <a name="see-also"></a>Vedere anche

[Video per la formazione di Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
