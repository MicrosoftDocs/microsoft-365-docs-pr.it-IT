---
title: Configurare Microsoft 365 Business Premium
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Individuare i passaggi di installazione per Microsoft 365 Business Premium, tra cui l'aggiunta di un dominio e degli utenti, la configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: cc20637d7a78bd34ecb61a4ed46eb06d564d63df
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324497"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Configurare Microsoft 365 Business Premium nell'installazione guidata

Guardare questo video per una panoramica della configurazione di Microsoft 365 Business Premium.<br><br>

## <a name="add-your-domain-users-and-set-up-policies"></a>Aggiungere il dominio, gli utenti e i criteri di configurazione

Quando si acquista Microsoft 365 Business Premium, si ha la possibilità di utilizzare un dominio che si è proprietari o di acquistarne uno durante l' [iscrizione](sign-up.md).

- Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Aggiungere il proprio dominio per personalizzare l’accesso

1. Autenticarsi allì[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le proprie credenziali globali di amministrazione. 

2. Scegliere **Vai alla configurazione** per avviare la procedura guidata.

    ![Selezionare Vai a installazione.](../media/gotosetupinadmincenter.png)

3. Nella pagina **Installa le tue app di Office**, è possibile installare le app sul proprio computer.
    
4. Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).

    > [!IMPORTANT]
    > Se un dominio è stato acquistato durante l’iscrizione, il passaggio **Aggiungi un dominio** non comparirà. Proseguire al passaggio [Aggiungi utenti](#add-users-and-assign-licenses).

    ![Schermata della pagina Personalizza il tuo accesso.](../media/adddomain.png)

    
4. Seguire i passaggi della procedura guidata per [creare record DNS presso un provider di hosting DNS per Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio. Se si conosce l’host del dominio, vedere anche le [istruzioni specifiche dell’host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Aggiungere utenti e assegnare licenze

Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](add-users-m365b.md) nell’interfaccia di amministrazione. Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Aggiungere utenti nella procedura guidata

Tutti gli utenti aggiunti nella procedura guidata vengono assegnati automaticamente a una licenza Microsoft 365 Business Premium.

![Schermata della pagina Aggiungi nuovi utenti nella procedura guidata](../media/addnewuserspage.png)

1. Se l'abbonamento Microsoft 365 Business Premium ha utenti esistenti (ad esempio, se è stato utilizzato Azure AD Connect), è possibile assegnare loro le licenze adesso. Procedere aggiungendo le licenze anche per questi utenti.

2. Una volta aggiunti gli utenti, sarà disponibile un’opzione per condividere le credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.

### <a name="connect-your-domain"></a>Connettere il proprio dominio

> [!NOTE]
> Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.
  
Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.
  
1. La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web. In caso contrario, [modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**. Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.
    - Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi. Vedere [Informazioni di base sul dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) per maggiori dettagli.

        ![Attiva la pagina dei record.](../media/activaterecords.png)

2. Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.

### <a name="protect-your-organization"></a>Proteggere l'organizzazione 

I criteri configurati nella procedura guidata vengono applicati automaticamente a un [gruppo di sicurezza](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominato *tutti gli utenti*. È inoltre possibile creare altri gruppi per assegnare criteri nell'interfaccia di amministrazione.

1. Per **aumentare la protezione da minacce informatiche avanzate**, è consigliabile accettare le impostazioni predefinite per consentire a [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) di eseguire l'analisi dei file di protezione dalle minacce e i collegamenti nelle app di Office.

    ![Schermata della pagina aumenta protezione.](../media/increasetreatprotection.png)


2. Nella pagina **Impedisci perdite di dati sensibili** , accettare le impostazioni predefinite per abilitare la prevenzione della perdita di dati (DLP) di Office 365 per tenere sotto controllo i dati sensibili nelle app di Office e impedire la condivisione accidentale di questi all'esterno dell'organizzazione.

3. Nella pagina **Proteggi dati in Office per dispositivi** mobili, lascia la gestione delle app per dispositivi mobili, Espandi le impostazioni e rivedile e quindi seleziona **Crea criteri di gestione delle app per dispositivi mobili**.

    ![Schermata della pagina Proteggi dati in Office per dispositivi mobili.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteggere i PC Windows 10

Sulla barra di spostamento sinistra, selezionare **installazione** e quindi, in **accesso e sicurezza**, scegliere **Proteggi i computer Windows 10**. Scegliere **View** per iniziare. Per istruzioni complete, vedere [proteggere i computer Windows 10](secure-win-10-pcs.md) .

## <a name="deploy-office-365-client-apps"></a>Distribuire le app client di Office 365

Se si è scelto di installare automaticamente le app di Office durante l'installazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno effettuato l'accesso a Azure AD dai propri dispositivi Windows, utilizzando le proprie credenziali di lavoro.

Per installare Office su dispositivi mobili iOS o Android, vedere [configurare i dispositivi mobili per gli utenti di Microsoft 365 Business Premium](set-up-mobile-devices.md).

È anche possibile installare Office individualmente. Per istruzioni, vedere [installare Office in un PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) .

## <a name="see-also"></a>Vedere anche

[Video di formazione su Microsoft 365 per le aziende](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
