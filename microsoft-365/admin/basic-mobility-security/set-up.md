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
description: Configurare la sicurezza e la mobilità di base per proteggere e gestire i dispositivi mobili degli utenti.
ms.openlocfilehash: 079593381d6395c18cd80f3eeab2e16837a2d27a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545809"
---
# <a name="set-up-basic-mobility-and-security"></a>Impostare Basic Mobility + Security

La sicurezza e mobilità di base integrata per Microsoft 365 consente di proteggere e gestire i dispositivi mobili degli utenti, ad esempio iPhone, iPad, Android e Windows Phone. È possibile creare e gestire criteri di sicurezza, cancellare tutti i dati in remoto e visualizzare report dettagliati sui dispositivi.

Sono richieste informazioni? Per informazioni sulle domande frequenti su questioni comuni, vedere [domande frequenti su mobilità e sicurezza di base](frequently-asked-questions.md). Tenere presente che non è possibile utilizzare un account amministratore delegato per gestire la mobilità e la sicurezza di base. Per altre informazioni, vedere [Partners: offer Delegated Administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

La gestione dei dispositivi è parte integrante del Centro sicurezza & Compliance, quindi è necessario andare lì per avviare l'installazione di MDM.

## <a name="activate-the-basic-mobility-and-security-service"></a>Attivare il servizio di sicurezza e mobilità di base

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Andare a [attivare la sicurezza e la mobilità di base](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).

   È possibile richiedere del tempo per attivare la sicurezza e la mobilità di base. Al termine della procedura, si riceverà un messaggio di posta elettronica che spiega i passaggi successivi da eseguire.

## <a name="set-up-mobile-device-management"></a>Configurare la gestione dei dispositivi mobili

Quando il servizio è pronto, completare i passaggi seguenti per completare l'installazione.

### <a name="step-1-required-configure-domains-for-mdm"></a>Passaggio 1: (obbligatorio) configurare i domini per MDM

Se non si dispone di un dominio personalizzato associato a Microsoft 365 o se non si è in grado di gestire i dispositivi Windows, è possibile ignorare questa sezione. In caso contrario, è necessario aggiungere i record DNS per il dominio nell'host DNS. Se i record sono già stati aggiunti, come parte della configurazione del dominio con Microsoft 365, è tutto pronto. Dopo aver aggiunto i record, gli utenti di Microsoft 365 nell'organizzazione che effettuano l'accesso al dispositivo Windows con un indirizzo di posta elettronica che utilizza il dominio personalizzato vengono reindirizzati per la registrazione alla sicurezza e alla mobilità di base.

Serve assistenza per la configurazione dei record? Trovare il registrar e selezionare il nome del registrar per passare alla guida dettagliata per la creazione di record DNS nell'elenco fornito in [Add DNS Records to Connect Your Domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Utilizzare queste istruzioni per creare i record CNAME descritti in [semplificare la registrazione di Windows senza Azure ad Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Dopo aver aggiunto i due record CNAME, tornare al centro sicurezza & compliance e passare alla gestione **dei**  >  **dispositivi**   per la prevenzione della perdita di dati per completare il passaggio successivo.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Passaggio 2: (obbligatorio) configurare un certificato APNs per i dispositivi iOS

Per gestire i dispositivi iOS come iPad e iPhone, è necessario creare un certificato di APNs.

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Nel tipo di browser:  [https://protection.office.com](https://protection.office.com/) .

3. Selezionare Gestione dei dispositivi per la prevenzione della perdita di **dati**   >  **Device management**e scegliere **APNs certificate for iOS Devices**.

4. Nella pagina impostazioni del certificato di notifica push di Apple scegliere **Avanti**.

5. Selezionare **Scarica il file CSR**   e salvare la richiesta di firma del certificato in un punto qualsiasi del computer da ricordare. Selezionare **Avanti**.

6. Nella pagina Create an APNs certificate:

   - Selezionare il portale Apple APNS per aprire il portale Apple Push Certificates.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Selezionare Create a certificate e accettate le condizioni per l'utilizzo.
   - Passare alla richiesta di firma del certificato scaricata nel computer da Microsoft 365 e selectUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Tornare a Microsoft 365 e selezionare **Avanti**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selezionare  **fine**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Passaggio 3: (scelta consigliata) configurare l'autenticazione a più fattori

Mae aiuta a garantire l'accesso a Microsoft 365 per la registrazione dei dispositivi mobili richiedendo una seconda forma di autenticazione. Gli utenti sono tenuti a riconoscere una telefonata, un messaggio di testo o una notifica delle app sul proprio dispositivo mobile dopo aver inserito correttamente la password dell'account di lavoro. È possibile registrare il proprio dispositivo solo dopo aver completato la seconda forma di autenticazione. Dopo la registrazione dei dispositivi utente in mobilità e sicurezza di base, gli utenti possono accedere alle risorse di Microsoft 365 solo con il proprio account di lavoro.

Per informazioni su come abilitare l'utilizzo dell'AMF nel portale di Azure AD, vedere [configurare l'autenticazione](https://go.microsoft.com/fwlink/p/?LinkId=519255)a più fattori.

Dopo aver configurato l'AMF, tornare al centro sicurezza & compliance e passare a **Data loss prevention**   >  **Device management**   >  **Criteri dispositivo**di prevenzione della perdita   di dati per completare il passaggio successivo.

### <a name="step-4-recommended-manage-device-security-policies"></a>Passaggio 4: (scelta consigliata) gestire i criteri di sicurezza del dispositivo

Il passaggio successivo consiste nel creare e distribuire i criteri di sicurezza dei dispositivi per proteggere i dati dell'organizzazione di Microsoft 365. Ad esempio, è possibile impedire la perdita di dati se un utente perde il dispositivo creando un criterio per bloccare i dispositivi dopo cinque minuti di inattività e cancellare i dispositivi dopo tre errori di accesso.

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Selezionare [Attiva gestione dispositivi mobili](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Se il servizio è attivato, i passaggi di attivazione vedranno un collegamento per la [gestione dei dispositivi](https://admin.microsoft.com/adminportal/home#/MifoDevices)   .

3. Passare a **Criteri dispositivo**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni di base per i criteri di sicurezza e dispositivi mobili":::

4. Creare e distribuire i criteri di sicurezza dei dispositivi adatti all'organizzazione seguendo i passaggi descritti in creare i criteri di sicurezza per i [dispositivi in mobilità e sicurezza di base](create-device-security-policies.md).

> [!TIP]
>
> - Quando si crea un nuovo criterio, è possibile impostare il criterio per consentire l'accesso e la violazione dei criteri di report in cui un dispositivo utente non è conforme ai criteri. In questo modo è possibile visualizzare il numero di dispositivi mobili influenzati dal criterio senza bloccare l'accesso a Microsoft 365.
>
> - Prima di distribuire un nuovo criterio a tutti gli utenti dell'organizzazione, è consigliabile testarlo sui dispositivi utilizzati da un numero limitato di utente.
>
> - Inoltre, prima di distribuire i criteri, informare l'organizzazione sull'impatto potenziale di registrazione di un dispositivo in mobilità e sicurezza di base. A seconda di come si configurano i criteri, i dispositivi che non sono conformi ai criteri (dispositivi non conformi) potrebbero essere bloccati dall'accesso a Microsoft 365. I dispositivi non conformi possono anche disporre di app installate, foto e altre informazioni personali che, in un dispositivo registrato, potrebbero essere eliminate se il dispositivo è stato cancellato. Per altre informazioni, vedere [Wipe a Mobile Device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="make-sure-users-enroll-their-devices"></a>Verificare che gli utenti registrino i propri dispositivi

Dopo aver creato e distribuito un criterio di gestione dei dispositivi mobili, ogni utente con licenza Microsoft 365 nell'organizzazione a cui si applica il criterio dispositivo riceve un messaggio di registrazione la volta successiva che accede a Microsoft 365 dal proprio dispositivo mobile. È necessario completare i passaggi di registrazione e attivazione prima di poter accedere ai documenti e ai messaggi di posta elettronica di Microsoft 365. Per altre informazioni, vedere [registrazione del dispositivo mobile utilizzando la sicurezza e la mobilità di base](enroll-your-mobile-device.md).

> [!IMPORTANT]
> Se la lingua preferita di un utente non è supportata dal processo di registrazione, è possibile che gli utenti ricevano notifiche di registrazione e passaggi sui propri dispositivi mobili in un'altra lingua. Non tutte le lingue supportate in Microsoft 365 sono attualmente supportate per il processo di registrazione sui dispositivi mobili.

Gli utenti con dispositivi Android o iOS sono tenuti a installare l'app portale aziendale come parte del processo di registrazione.

## <a name="related-topics"></a>Argomenti correlati

[Funzionalità di mobilità e sicurezza di base](capabilities.md)<br/>
[Creare criteri di sicurezza per i dispositivi in mobilità e sicurezza di base](create-device-security-policies.md)