---
title: Configurare Microsoft 365 Business
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni su come configurare Microsoft 365 business.
ms.openlocfilehash: d33839693001f36fbb56541775015f739300b043
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288496"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Configurare Microsoft 365 business nell'installazione guidata

## <a name="add-your-domain-users-and-set-up-policies"></a>Aggiungere il dominio, gli utenti e i criteri di configurazione

[![Label che consente di sapere che l'interfaccia di amministrazione sta cambiando ed è possibile trovare ulteriori dettagli su aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Quando si acquista Microsoft 365 business, si ha la possibilità di utilizzare un dominio che si è proprietari o di acquistarne uno durante l' [iscrizione](sign-up.md).

- Se si è acquistato un nuovo dominio al momento dell'iscrizione, il dominio è tutto configurato ed è possibile spostarsi per [aggiungere utenti e assegnare licenze](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Aggiungere il dominio per personalizzare l'accesso

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali di amministratore globale. 

2. Fare clic su **Aggiungi un dominio** o su **Aggiungi utenti** per avviare la procedura guidata.
    > [!IMPORTANT]
    > Se si è acquistato un dominio durante l'iscrizione, non verrà visualizzato **aggiungere un passaggio di dominio** qui. Andare su [Aggiungi utenti](#add-users-and-assign-licenses) .

    ![Selezionare Aggiungi un dominio.](media/addadomainadmincenter.png)
    
3. Nella procedura guidata, immettere il nome di dominio che si desidera utilizzare (come contoso.com).


    ![Schermata della pagina Personalizza il tuo accesso.](media/personalizesignin.png)

    
4. Seguire i passaggi della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio. Se si conosce l'host di dominio, vedere anche le [istruzioni specifiche dell'host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se il provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e verrà chiesto automaticamente di accedere e di consentire a Microsoft di eseguire l'autenticazione per conto dell'utente:

    ![Nella pagina Conferma accesso GoDaddy selezionare autorizza.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Aggiungere utenti e assegnare licenze

È possibile aggiungere utenti nella procedura guidata, ma è anche possibile [aggiungerli in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione. Inoltre, se si dispone di un controller di dominio locale, è possibile aggiungere utenti con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Aggiungere gli utenti nella procedura guidata

Tutti gli utenti aggiunti nella procedura guidata vengono assegnati automaticamente a una licenza aziendale Microsoft 365.

![Schermata della pagina Aggiungi nuovi utenti nella procedura guidata](media/addnewuserspage.png)

1. Se l'abbonamento a Microsoft 365 business ha utenti esistenti (ad esempio, se è stato utilizzato Azure AD Connect), è possibile assegnare loro le licenze. Procedere con l'aggiunta di licenze anche per questi utenti.

3. Dopo aver aggiunto gli utenti, si otterrà anche un'opzione per condividere le credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.

4. Ignorare il passaggio relativo alla migrazione dei messaggi di posta elettronica e scegliere **Avanti** nella pagina **Esegui la migrazione dei messaggi di posta elettronica**. 

    Se si sta passando da un altro provider di posta elettronica e si desidera copiare i dati in un secondo momento, è possibile [eseguire la migrazione di posta elettronica e contatti a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).


### <a name="connect-your-domain"></a>Connettere il dominio

> [!NOTE]
> Se si è scelto di utilizzare il dominio. onmicrosoft o di Azure AD Connect per configurare gli utenti, questo passaggio non verrà visualizzato.
  
Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.
  
1. La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web. In caso contrario, [modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Se si dispone di record DNS esistenti, ad esempio un sito Web esistente, ma l'host DNS è abilitato per la [connessione al dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Add records for me**. 
    - Se sono presenti record DNS con altri host DNS (non abilitati per la connessione al dominio), è necessario gestire i propri record DNS per assicurarsi che i servizi esistenti siano connessi. Per altre informazioni, vedere [Domain nozioni di base](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .

        ![Connect Your Domain Page con I ' ll manage my own DNS Records.](media/connectyourdomainpage.png)

2. Seguire i passaggi della procedura guidata e la posta elettronica e altri servizi verranno configurati per l'utente.

### <a name="set-up-security-policies-and-device-configurations"></a>Impostare i criteri di sicurezza e le configurazioni dei dispositivi 

I criteri configurati nella procedura guidata vengono applicati automaticamente a un [gruppo di sicurezza](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominato *tutti gli utenti*. È inoltre possibile creare altri gruppi per assegnare criteri nell'interfaccia di amministrazione.

1. Nella pagina **Proteggi i file di lavoro nei dispositivi mobili** , l'opzione **Proteggi i file di lavoro quando i dispositivi vengono persi o rubati** è selezionata per impostazione predefinita. È possibile abilitare la gestione del modo in cui **gli utenti accedono ai file di Office nei dispositivi mobili**e questo è consigliato.

    ![Schermata della pagina Proteggi file di lavoro su dispositivi mobili.](media/protectworkfilesondevices.png)

     - Espandere **Proteggi file di lavoro quando i dispositivi vengono persi o rubati** per visualizzare i [valori predefiniti](protect-work-files-on-lost-or-stolen-device.md):

        ![Screenshot dei valori predefiniti per la protezione di file su dispositivi persi.](media/protectworkfilesondevicesdefault.png)

    - Selezionare **Gestisci la modalità di accesso degli utenti ai file di Office nei dispositivi mobili** ed espanderla per visualizzare i [valori predefiniti](manage-user-access-on-mobile-devices.md). È consigliabile accettare i valori predefiniti durante l'installazione per creare i criteri di applicazione per Android, iOS e Windows 10 che si applicano a tutti gli utenti. È possibile creare altri criteri al termine dell'installazione.

        ![Schermata delle impostazioni di protezione per i file di Office su dispositivi mobili.](media/useraccessonmobile.png)

2. L'ultimo passaggio su Protect data and Devices consente di configurare i criteri per proteggere i dispositivi Windows 10. Queste impostazioni vengono applicate automaticamente quando un utente di Windows 10 si connette all'organizzazione. È possibile espandere i **dispositivi Windows 10 sicuri** per visualizzare e modificare i [valori predefiniti](secure-windows-10-devices.md).
3. È inoltre possibile scegliere di [installare automaticamente Office](install-office-on-windows-10-during-setup.md) nei dispositivi Windows 10.

    ![Schermata della pagina Imposta configurazione dispositivo Windows 10.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Distribuire le app client di Office 365

Se si è scelto di installare automaticamente le app di Office durante la configurazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno effettuato l'accesso a Azure AD dai propri dispositivi Windows con le credenziali di lavoro.
Per installare Office su dispositivi mobili iOS o Android, vedere [configurare i dispositivi mobili per gli utenti aziendali di Microsoft 365](set-up-mobile-devices.md).

È anche possibile installare Office individualmente. Per istruzioni, vedere [installare Office in un PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .
