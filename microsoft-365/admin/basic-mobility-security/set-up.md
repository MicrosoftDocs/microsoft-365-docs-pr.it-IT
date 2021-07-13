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
- AdminTemplateSet
search.appverid:
- MET150
description: Configura Dispositivi mobili e sicurezza di base per proteggere e gestire i dispositivi mobili degli utenti eseguendo azioni come la pulizia remota di un dispositivo.
ms.openlocfilehash: d878569c691fc25c8c91c5a5a29215e6284a5d71
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393284"
---
# <a name="set-up-basic-mobility-and-security"></a>Impostare Basic Mobility + Security

L'ambiente di mobilità e sicurezza di base integrato per Microsoft 365 consente di proteggere e gestire i dispositivi mobili degli utenti, ad esempio iPhone, iPad, Android e Windows telefoni. È possibile creare e gestire criteri di sicurezza, cancellare tutti i dati in remoto e visualizzare report dettagliati sui dispositivi.

Hai domande? Per domande frequenti su come risolvere le domande più comuni, vedere [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.yml). Tenere presente che non è possibile utilizzare un account amministratore delegato per gestire i dispositivi mobili e la sicurezza di base. Per altre info, vedi [Partner: Offrire l'amministrazione delegata.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

La gestione dei dispositivi fa parte del Centro sicurezza & conformità, quindi dovrai andare lì per avviare la configurazione di base per dispositivi mobili e sicurezza.

## <a name="activate-the-basic-mobility-and-security-service"></a>Attivare il servizio Di base per dispositivi mobili e sicurezza

1. Accedi a Microsoft 365 con il tuo account amministratore globale.

2. Vai a [Attiva mobilità e sicurezza di base.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   L'attivazione di Dispositivi mobili e sicurezza di base può richiedere del tempo. Al termine, riceverai un messaggio di posta elettronica che spiega i passaggi successivi da eseguire.

## <a name="set-up-mobile-device-management"></a>Configurare Gestione dispositivi mobili

Quando il servizio è pronto, completare la procedura seguente per completare l'installazione.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Passaggio 1: (obbligatorio) Configurare i domini per dispositivi mobili e sicurezza di base

Se non hai un dominio personalizzato associato a Microsoft 365 o se non stai gestendo Windows dispositivi, puoi ignorare questa sezione. In caso contrario, sarà necessario aggiungere record DNS per il dominio nell'host DNS. Se i record sono già stati aggiunti, come parte della configurazione del dominio con Microsoft 365, si è tutti impostati. Dopo aver aggiunto i record, gli utenti Microsoft 365 dell'organizzazione che a tale dispositivo a cui accede Windows con un indirizzo di posta elettronica che utilizza il dominio personalizzato vengono reindirizzati per la registrazione a Dispositivi mobili e sicurezza di base.

Serve assistenza per la configurazione dei record? Individuare il registrar e selezionare il nome del registrar per accedere alla Guida dettagliata per la creazione di record DNS nell'elenco fornito in [Add DNS records to connect your domain](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Seguire queste istruzioni per creare record CNAME descritti in [Semplificare Windows registrazione senza Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Dopo aver aggiunto i due record CNAME, tornare al Centro sicurezza e conformità & e passare a Prevenzione della perdita di dati Gestione dei dispositivi per completare  >     il passaggio successivo.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Passaggio 2: (obbligatorio) Configurare un certificato APNs per i dispositivi iOS

Per gestire dispositivi iOS come iPad e iPhone, devi creare un certificato APNs.

1. Accedi a Microsoft 365 con il tuo account amministratore globale.

2. Nel browser digitare:  [https://protection.office.com](https://protection.office.com/) .

3. Seleziona  **Prevenzione della perdita dei dati** Gestione   >  **dei** dispositivi e scegli Certificato **APNs per i dispositivi iOS.**

4. Nella pagina Apple Push Notification Certificate Impostazioni scegliere **Next**.

5. Seleziona **Download your CSR file** and save the Certificate signing request to somewhere on your computer that   you'll remember. Selezionare **Avanti**.

6. Nella pagina Crea un certificato APNs:

   - Seleziona Apple APNS Portal per aprire il portale dei certificati Push Apple.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Selezionare Crea un certificato e accettare le Condizioni per l'utilizzo.
   - Passare alla richiesta di firma del certificato scaricata nel computer Microsoft 365 e selezionareUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Tornare a Microsoft 365 e selezionare **Avanti**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selezionare  **Fine.**

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Passaggio 3: (scelta consigliata) Configurare l'autenticazione a più fattori

L'autenticazione a più fattori consente di proteggere l'accesso Microsoft 365 per la registrazione di dispositivi mobili richiedendo una seconda forma di autenticazione. Gli utenti devono confermare una chiamata telefonica, un SMS o una notifica dell'app sul dispositivo mobile dopo aver immesso correttamente la password dell'account aziendale. Possono registrare il dispositivo solo dopo il completamento di questa seconda forma di autenticazione. Dopo aver registrato i dispositivi utente in Dispositivi mobili e sicurezza di base, gli utenti possono accedere Microsoft 365 risorse con solo l'account aziendale.

Per informazioni su come attivare l'autenticazione a più fattori nel portale di Azure AD, vedere [Configurare l'autenticazione a più fattori.](../security-and-compliance/set-up-multi-factor-authentication.md)

Dopo aver configurato l'autenticazione a più fattori &, tornare **** al Centro sicurezza e conformità e passare a Prevenzione della perdita di dati Criteri dei dispositivi per completare   >     >  ****   il passaggio successivo.

### <a name="step-4-recommended-manage-device-security-policies"></a>Passaggio 4: (scelta consigliata) Gestire i criteri di sicurezza dei dispositivi

Il passaggio successivo consiste nel creare e distribuire i criteri di sicurezza dei dispositivi per proteggere i dati Microsoft 365'organizzazione. Ad esempio, puoi evitare la perdita di dati se un utente perde il dispositivo creando un criterio per bloccare i dispositivi dopo cinque minuti di inattività e cancellare i dispositivi dopo tre errori di accesso.

1. Accedi a Microsoft 365 con il tuo account amministratore globale.

2. Selezionare [Attiva gestione dispositivi mobili](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Se il servizio è attivato, i passaggi di attivazione vedrai un collegamento a [Gestisci dispositivi.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Vai a **Criteri dispositivo**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni di base dei criteri di sicurezza e dispositivi mobili":::

4. Creare e distribuire i criteri di sicurezza dei dispositivi appropriati per l'organizzazione seguendo la procedura descritta in Creare criteri di sicurezza [dei dispositivi in Dispositivi mobili e sicurezza di base.](create-device-security-policies.md)

> [!TIP]
>
> - Quando crei un nuovo criterio, potresti voler impostare il criterio per consentire l'accesso e segnalare una violazione dei criteri in cui un dispositivo utente non è conforme ai criteri. In questo modo puoi vedere quanti dispositivi mobili sono influenzati dal criterio senza bloccare l'accesso a Microsoft 365.
>
> - Prima di distribuire un nuovo criterio a tutti gli utenti dell'organizzazione, è consigliabile testarlo nei dispositivi utilizzati da un numero limitato di utenti.
>
> - Inoltre, prima di distribuire i criteri, invii all'organizzazione i potenziali effetti della registrazione di un dispositivo in Dispositivi mobili e sicurezza di base. A seconda della configurazione dei criteri, è possibile che ai dispositivi non conformi ai criteri (dispositivi non conformi) sia impedito l'accesso Microsoft 365. Nei dispositivi non conformi potrebbero essere installate anche app, foto e altre informazioni personali che, in un dispositivo registrato, potrebbero essere eliminate se il dispositivo viene cancellato. Per altre info, vedi [Cancellare i dati di un dispositivo mobile in Dispositivi mobili e sicurezza di base.](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>Assicurarsi che gli utenti registrano i propri dispositivi

Dopo aver creato e distribuito un criterio di gestione dei dispositivi mobili, ogni utente di Microsoft 365 con licenza nell'organizzazione a cui si applicano i criteri del dispositivo riceve un messaggio di registrazione al successivo accesso a Microsoft 365 dal dispositivo mobile. Devono completare i passaggi di registrazione e attivazione prima di poter accedere Microsoft 365 posta elettronica e documenti. Per altre info, vedi [Registrare il dispositivo mobile usando Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Se la lingua preferita di un utente non è supportata dal processo di registrazione, gli utenti potrebbero ricevere notifiche di registrazione e passaggi sui dispositivi mobili in un'altra lingua. Non tutte le lingue supportate in Microsoft 365 sono attualmente supportate per il processo di registrazione nei dispositivi mobili.

Gli utenti con dispositivi Android o iOS devono installare l'app Portale aziendale come parte del processo di registrazione.

## <a name="related-content"></a>Contenuto correlato

[Funzionalità di base per dispositivi mobili e sicurezza](capabilities.md) (articolo)\
[Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base](create-device-security-policies.md) (articolo)