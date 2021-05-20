---
title: Prevenzione della perdita dei dati e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Ora puoi applicare i criteri DLP Microsoft Teams chat e canali. Leggi questo articolo per saperne di più su come funziona.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572466"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenzione della perdita dei dati e Microsoft Teams

> [!NOTE]
> Le funzionalità di prevenzione della perdita di dati sono state recentemente aggiunte ai messaggi di chat e canale Microsoft Teams per gli utenti con licenza Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance o Office 365 Advanced Compliance. Office 365 e Microsoft 365 E3 includono la protezione DLP per SharePoint online, OneDrive e Exchange Online. Ciò include anche i file condivisi tramite Teams perché Teams utilizza SharePoint Online e OneDrive per condividere file.
Il supporto per la protezione DLP Teams Chat richiede E5.
Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Panoramica di DLP e Microsoft Teams

Di recente, [le funzionalità di prevenzione](dlp-learn-about-dlp.md) della perdita di dati sono state estese per includere Microsoft Teams di chat e canali, inclusi i messaggi di canale **privati**. 

> [!IMPORTANT]
> DLP attualmente si applica solo ai messaggi effettivi nel thread di chat o canale. Le notifiche di attività, che includono una breve anteprima del  messaggio e vengono visualizzate in base alle impostazioni di notifica di un utente, non sono Teams DLP in questo momento. Tutte le informazioni riservate presenti nella parte del messaggio visualizzata nell'anteprima rimarranno visibili nella notifica anche dopo l'applicazione del criterio DLP e la rimozione delle informazioni riservate del messaggio stesso.

Se l'organizzazione dispone di DLP, è ora possibile definire criteri che impediscano agli utenti di condividere informazioni riservate in un canale Microsoft Teams o in una sessione di chat. Ecco alcuni esempi di come funziona questa protezione:

- **Esempio 1: protezione delle informazioni riservate nei messaggi**. Si supponga che qualcuno tenti di condividere informazioni riservate in Teams chat o canale con ospiti (utenti esterni). Se per evitare questo problema è stato definito un criterio DLP, i messaggi con informazioni riservate inviati a utenti esterni vengono eliminati. Ciò avviene automaticamente e in pochi secondi, in base alla configurazione dei criteri DLP.

    > [!NOTE]
    > DLP per Microsoft Teams blocca il contenuto sensibile quando condiviso con Microsoft Teams utenti che hanno:<br/>- [accesso degli ospiti](/MicrosoftTeams/guest-access) in team e canali; o<br/>- [accesso esterno nelle](/MicrosoftTeams/manage-external-access) riunioni e nelle sessioni di chat. <p>DLP per le sessioni di chat esterne funzionerà solo se sia il mittente che il destinatario sono in modalità Teams solo [e utilizzano Microsoft Teams federazione nativa](/microsoftteams/manage-external-access). DLP per Teams non blocca i messaggi in [interoperabilità](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con Skype for Business o sessioni di chat federate non native.

- **Esempio 2: Protezione delle informazioni riservate nei documenti**. Si supponga che qualcuno tenti di condividere un documento con gli ospiti in un canale Microsoft Teams o in una chat e che il documento contenga informazioni riservate. Se per evitare questo problema è stato definito un criterio DLP, il documento non si aprirà per tali utenti. Si noti che in questo caso, i criteri DLP devono includere SharePoint e OneDrive per consentire l'allora in vigore della protezione. Si tratta di un esempio di DLP per SharePoint visualizzato in Microsoft Teams e richiede pertanto che gli utenti siano concessi in licenza Office 365 per un DLP (incluso in Office 365 E3), ma non richiedano che gli utenti siano concessi in licenza per Office 365 Advanced Compliance.

## <a name="policy-tips-help-educate-users"></a>I suggerimenti per i criteri aiutano a educare gli utenti

Analogamente al funzionamento di DLP nei client desktop [Exchange, Outlook, Outlook sul Web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business e](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)nei client desktop [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), i suggerimenti per i criteri vengono visualizzati quando un'azione è in conflitto con un criterio DLP. Ecco un esempio di suggerimento per i criteri:

![Notifica messaggi bloccata in Teams](../media/dlp-teams-blockedmessage-notification.png)

In questo caso, il mittente ha tentato di condividere un numero di previdenza sociale in un Microsoft Teams canale. Il **collegamento Cosa posso fare?** apre una finestra di dialogo che fornisce al mittente le opzioni per risolvere il problema. Si noti che in questo caso, il mittente può scegliere di ignorare il criterio o notificare a un amministratore di esaminarlo e risolverlo.

![Opzioni per risolvere il messaggio bloccato](../media/dlp-teams-blockedmessage-possibleactions.png)

Nell'organizzazione è possibile scegliere di consentire agli utenti di ignorare un criterio DLP. Inoltre, quando si configurano i criteri DLP, è possibile utilizzare i suggerimenti per i criteri predefiniti o personalizzare [i suggerimenti per i criteri](#to-customize-policy-tips) per l'organizzazione.

Tornando al nostro esempio, in cui un mittente ha condiviso un numero di previdenza sociale in un Teams, ecco cosa ha visto il destinatario:

> [!div class="mx-imgBorder"]
> ![Messaggio bloccato](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Personalizzare suggerimenti per i criteri

Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati. Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

1. Passare al Centro conformità & sicurezza ( [https://protection.office.com](https://protection.office.com) ) e accedere.

2. Scegliere **Prevenzione della perdita dei dati** > **Criteri**.

3. Selezionare un criterio e accanto a **Impostazioni criterio** scegliere **Modifica**.

4. Creare una nuova regola o modificare una regola esistente per il criterio.

    > [!div class="mx-imgBorder"]
    > ![Modifica di una regola per un criterio](../media/dlp-teams-editrule.png)

5. Nella scheda **Notifiche utente selezionare** Personalizza il testo della posta elettronica **e/o** Personalizza le opzioni di testo **del suggerimento per i** criteri.

    > [!div class="mx-imgBorder"]
    > ![Personalizzare le notifiche degli utenti e i suggerimenti per i criteri](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Specificare il testo da utilizzare per le notifiche tramite posta elettronica e/o i suggerimenti per i criteri e quindi scegliere **Salva**.

7. Nella scheda **Impostazioni criteri** scegliere **Salva**.

Consentire a circa un'ora che le modifiche si disercino nel data center e si sincronizzino con gli account utente.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Aggiungere Microsoft Teams come ubicazione per i criteri di prevenzione della perdita dei dati esistenti

Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati. Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

1. Passare al Centro conformità & sicurezza ( [https://protection.office.com](https://protection.office.com) ) e accedere.

2. Scegliere **Prevenzione della perdita dei dati** > **Criteri**.

3. Selezionare un criterio e esaminare i valori in **Percorsi**. Se vedi Teams **messaggi di chat e** canale , sei pronto. In caso di pertanto, fare clic su **Modifica**.

    > [!div class="mx-imgBorder"]
    > ![Percorsi per i criteri esistenti](../media/dlp-teams-editexistingpolicy.png)

4. Nella colonna **Stato** attivare i criteri per i messaggi **di Teams chat e canale**.

    > [!div class="mx-imgBorder"]
    > ![DLP per Teams chat e canali](../media/dlp-teams-addteamschatschannels.png)

5. Nella scheda **Scegli percorsi** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Lascia **che scelga percorsi specifici**. È possibile specificare quanto segue:

    1. fino a 1000 singoli account da includere o escludere
    1. liste di distribuzione e gruppi di sicurezza da includere o escludere. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Quindi scegliere **Avanti**.

7. Fare clic su **Salva**.

Consentire a circa un'ora che le modifiche si disercino nel data center e si sincronizzino con gli account utente.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definire nuovi criteri di prevenzione della perdita dei dati per Microsoft Teams

Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati. Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

1. Passare al Centro conformità & sicurezza ( [https://protection.office.com](https://protection.office.com) ) e accedere.

2. Scegliere **Prevenzione della perdita dei dati** > **Criteri** > **+ Crea un criterio**.

3. Scegliere un [modello](data-loss-prevention-policies.md#dlp-policy-templates)e quindi **Avanti**.

    Nel nostro esempio, abbiamo scelto il modello dati di informazioni di identificazione personale degli Stati Uniti.

    > [!div class="mx-imgBorder"]
    > ![Modello di privacy per i criteri DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Nella scheda **Nome criterio** specificare un nome e una descrizione per il criterio e quindi scegliere **Avanti**.

5. Nella scheda **Scegli percorsi** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Lascia **che scelga percorsi specifici**. È possibile specificare quanto segue:

    1. fino a 1000 singoli account da includere o escludere
    1. liste di distribuzione e gruppi di sicurezza da includere o escludere. **Questa è una funzione di anteprima pubblica.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Percorsi dei criteri DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Se si desidera assicurarsi che i documenti che contengono informazioni riservate non siano condivisi in modo inappropriato nel Teams, assicurarsi **che i siti SharePoint** e gli account **OneDrive** siano attivati, insieme Teams messaggi di chat **e canale**.

6. Nella scheda **Impostazioni criteri,** in **Personalizza il tipo di contenuto che si desidera proteggere**, mantenere le impostazioni semplici predefinite oppure scegliere Usa impostazioni **avanzate** e quindi **Avanti**. Se si scelgono impostazioni avanzate, è possibile creare o modificare regole per i criteri. Per ottenere assistenza in questo senso, [vedere Impostazioni semplici e impostazioni](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)avanzate.

7.  Nella scheda **Impostazioni criteri,** in **Cosa si vuole fare se si rilevano informazioni riservate?**, esaminare le impostazioni. È qui che è possibile scegliere di mantenere i suggerimenti per i [criteri predefiniti e le notifiche tramite posta](use-notifications-and-policy-tips.md)elettronica o personalizzarli.

    > [!div class="mx-imgBorder"]
    > ![Impostazioni dei criteri DLP con suggerimenti e notifiche](../media/dlp-teams-policysettings-tipsemails.png)

    Al termine della revisione o della modifica delle impostazioni, scegliere **Avanti**.

8. Nella **scheda Impostazioni criteri,** in Attivare o **testare prima i criteri?**, scegliere se attivare il criterio, [testarlo prima](dlp-overview-plan-for-dlp.md#policy-deployment)o tenerlo disattivato per il momento e quindi scegliere **Avanti**.

    > [!div class="mx-imgBorder"]
    > ![Specificare se attivare il criterio](../media/dlp-teams-policysettings-turnonnow.png)

9. Nella scheda **Rivedi impostazioni** esaminare le impostazioni per il nuovo criterio. Scegliere **Modifica** per apportare modifiche. Al termine, scegliere **Crea**.

Consentire a circa un'ora che i nuovi criteri si disercino nel data center e si sincronizzino con gli account utente.

## <a name="prevent-external-access-to-sensitive-documents"></a>Prevenire l'accesso esterno ai documenti sensibili

Per assicurarsi che SharePoint documenti contenenti informazioni riservate non possano essere accessibili da ospiti esterni da SharePoint o Teams per impostazione predefinita, selezionare quanto segue:

- È possibile assicurarsi che i documenti siano protetti fino a quando DLP non esegue l'analisi e li contrassegna come sicuri da condividere [contrassegnando i nuovi file come sensibili per impostazione predefinita](/sharepoint/sensitive-by-default).

- Struttura consigliata per il criterio DLP

    - **Condizioni**
        - Il contenuto contiene uno di questi tipi di informazioni riservate: [Selezionare tutto ciò che si applica]
        
        - Il contenuto viene condiviso da Microsoft 365 persone esterne all'organizzazione
        
          > [!div class="mx-imgBorder"]
          > ![Condizioni DLP per rilevare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-condition.png)

    - **Azioni**
        - Limitare l'accesso al contenuto per gli utenti esterni
        
        - Inviare una notifica agli utenti tramite messaggio di posta elettronica e suggerimenti per i criteri
        
        - Inviare i report degli incidenti all'amministratore
        
        > [!div class="mx-imgBorder"]
        > ![Azione DLP per bloccare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-action.png)

Criteri DLP in azione quando si tenta di condividere un documento in SharePoint contenente informazioni riservate con un ospite esterno:

> [!div class="mx-imgBorder"]
> ![Condivisione esterna bloccata](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


Criteri DLP in azione quando l'ospite tenta di aprire un documento in Teams con blocco esterno:

> [!div class="mx-imgBorder"]
> ![Accesso esterno bloccato](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Articoli correlati

[Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)

[Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](use-notifications-and-policy-tips.md)
