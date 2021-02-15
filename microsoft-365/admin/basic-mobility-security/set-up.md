---
title: Impostare Basic Mobility + Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Configurare Dispositivi mobili e sicurezza di base per proteggere e gestire i dispositivi mobili degli utenti.
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876865"
---
# <a name="set-up-basic-mobility-and-security"></a>Impostare Basic Mobility + Security

L'interfaccia di sicurezza e mobilità di base integrata per Microsoft 365 consente di proteggere e gestire i dispositivi mobili degli utenti, ad esempio iPhone, iPad, Android e telefoni Windows. È possibile creare e gestire criteri di sicurezza, cancellare tutti i dati in remoto e visualizzare report dettagliati sui dispositivi.

Hai domande? Per domande frequenti su come risolvere le domande più comuni, vedere Domande frequenti sulla mobilità e la sicurezza di [base.](frequently-asked-questions.md) Tenere presente che non è possibile utilizzare un account amministratore delegato per gestire i dispositivi mobili e la sicurezza di base. Per altre info, vedi [Partner: Offrire l'amministrazione delegata.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

La gestione dei dispositivi fa parte del Centro sicurezza & conformità, quindi è necessario avviarlo per avviare la configurazione di sicurezza e mobilità di base.

## <a name="activate-the-basic-mobility-and-security-service"></a>Attivare il servizio Di base per dispositivi mobili e sicurezza

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Passare a [Attiva mobilità e sicurezza di base.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   L'attivazione di Basic Mobility and Security può richiedere del tempo. Al termine, si riceverà un messaggio di posta elettronica che spiega i passaggi successivi da eseguire.

## <a name="set-up-mobile-device-management"></a>Configurare Gestione dispositivi mobili

Quando il servizio è pronto, completare i passaggi seguenti per completare l'installazione.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Passaggio 1: (obbligatorio) Configurare i domini per dispositivi mobili e sicurezza di base

Se non si dispone di un dominio personalizzato associato a Microsoft 365 o se non si gestiscono i dispositivi Windows, è possibile ignorare questa sezione. In caso contrario, sarà necessario aggiungere record DNS per il dominio presso l'host DNS. If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set. Dopo aver aggiunto i record, gli utenti di Microsoft 365 dell'organizzazione che aseguono l'accesso al proprio dispositivo Windows con un indirizzo di posta elettronica che usa il dominio personalizzato vengono reindirizzati per la registrazione a Basic Mobility and Security.

Serve aiuto per la configurazione dei record? Trovare il registrar e selezionare il nome del registrar per accedere alla Guida dettagliata per la creazione del record DNS nell'elenco fornito in Aggiungere record DNS per connettere [il dominio.](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Usa queste istruzioni per creare record CNAME descritti in [Semplificare la registrazione di Windows senza Azure AD Premium.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

Dopo aver aggiunto i due record CNAME, tornare al Centro sicurezza & conformità e passare a Prevenzione della perdita di dati Gestione dispositivi per completare  >     il passaggio successivo.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Passaggio 2: (obbligatorio) Configurare un certificato APNs per i dispositivi iOS

Per gestire i dispositivi iOS come iPad e iPhone, devi creare un certificato APNs.

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Nel browser digitare:  [https://protection.office.com](https://protection.office.com/) .

3. Selezionare  **Gestione dispositivi per la prevenzione della** perdita dei dati e scegliere Il certificato   >  **** **APNs per i dispositivi iOS.**

4. Nella pagina Impostazioni certificato notifica Push Apple scegliere **Avanti.**

5. Selezionare **Download your CSR file** and save the Certificate signing request to somewhere on your computer that   you'll remember. Selezionare **Avanti.**

6. Nella pagina Crea un certificato APNs:

   - Seleziona Apple APNS Portal per aprire il portale dei certificati Push Apple.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Selezionare Crea un certificato e accettare le Condizioni per l'utilizzo.
   - Passare alla richiesta di firma del certificato scaricata nel computer da Microsoft 365 e selezionareUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Tornare a Microsoft 365 e selezionare **Avanti.**

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selezionare  **Fine.**

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Passaggio 3: (scelta consigliata) Configurare l'autenticazione a più fattori

L'autenticazione a più fattori consente di proteggere l'accesso a Microsoft 365 per la registrazione di dispositivi mobili richiedendo una seconda forma di autenticazione. Gli utenti devono confermare una chiamata telefonica, un SMS o una notifica dell'app sul dispositivo mobile dopo aver immesso correttamente la password dell'account aziendale. Possono registrare il dispositivo solo dopo il completamento di questa seconda forma di autenticazione. Dopo la registrazione dei dispositivi utente in Basic Mobility and Security, gli utenti possono accedere alle risorse di Microsoft 365 solo con il proprio account aziendale.

Per informazioni su come attivare l'autenticazione a più fattori nel portale di Azure AD, vedere [Configurare l'autenticazione a più fattori.](https://go.microsoft.com/fwlink/p/?LinkId=519255)

Dopo aver configurato l'autenticazione a più fattori, tornare al **** Centro sicurezza & conformità e passare a Criteri dispositivo di gestione dei dispositivi per la prevenzione della perdita dei dati per completare   >     >  ****   il passaggio successivo.

### <a name="step-4-recommended-manage-device-security-policies"></a>Passaggio 4: (scelta consigliata) Gestire i criteri di sicurezza dei dispositivi

Il passaggio successivo consiste nel creare e distribuire criteri di sicurezza dei dispositivi per proteggere i dati dell'organizzazione di Microsoft 365. Ad esempio, puoi evitare la perdita di dati se un utente perde il dispositivo creando un criterio per bloccare i dispositivi dopo cinque minuti di inattività e cancellare i dispositivi dopo tre errori di accesso.

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Selezionare [Attiva gestione dispositivi mobili.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) Se il servizio è attivato, i passaggi di attivazione verranno visualizzati con un collegamento a [Gestisci dispositivi.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Vai a **Criteri dispositivo.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni dei criteri di sicurezza e mobilità di base":::

4. Creare e distribuire i criteri di sicurezza dei dispositivi appropriati per l'organizzazione seguendo la procedura descritta in Creare criteri di sicurezza dei dispositivi [in Dispositivi mobili e sicurezza di base.](create-device-security-policies.md)

> [!TIP]
>
> - Quando crei un nuovo criterio, puoi impostare il criterio per consentire l'accesso e segnalare una violazione dei criteri in cui un dispositivo utente non è conforme al criterio. In questo modo è possibile vedere quanti dispositivi mobili sono influenzati dai criteri senza bloccare l'accesso a Microsoft 365.
>
> - Prima di distribuire un nuovo criterio a tutti gli utenti dell'organizzazione, è consigliabile testarlo nei dispositivi usati da un numero limitato di utenti.
>
> - Inoltre, prima di distribuire i criteri, invii all'organizzazione informazioni sui potenziali effetti della registrazione di un dispositivo in Dispositivi mobili e sicurezza di base. A seconda di come sono stati impostati i criteri, i dispositivi che non sono conformi ai criteri (dispositivi non conformi) potrebbero essere bloccati dall'accesso a Microsoft 365. Nei dispositivi non conformi potrebbero essere installate anche app, foto e altre informazioni personali che, in un dispositivo registrato, potrebbero essere eliminate se il dispositivo viene cancellato. Per altre info, vedi [Cancellare un dispositivo mobile in Dispositivi mobili e sicurezza di base.](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>Verificare che gli utenti registrano i propri dispositivi

Dopo aver creato e distribuito un criterio di gestione dei dispositivi mobili, ogni utente di Microsoft 365 con licenza nell'organizzazione a cui si applicano i criteri del dispositivo riceve un messaggio di registrazione al successivo accesso a Microsoft 365 dal dispositivo mobile. Devono completare i passaggi di registrazione e attivazione prima di poter accedere alla posta elettronica e ai documenti di Microsoft 365. Per altre info, vedi [Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Se la lingua preferita di un utente non è supportata dal processo di registrazione, gli utenti potrebbero ricevere notifiche di registrazione e passaggi sui dispositivi mobili in un'altra lingua. Non tutte le lingue supportate in Microsoft 365 sono attualmente supportate per il processo di registrazione nei dispositivi mobili.

Gli utenti con dispositivi Android o iOS devono installare l'app Portale aziendale come parte del processo di registrazione.

## <a name="related-topics"></a>Argomenti correlati

[Funzionalità Basic Mobility + Security](capabilities.md)<br/>
[Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base](create-device-security-policies.md)