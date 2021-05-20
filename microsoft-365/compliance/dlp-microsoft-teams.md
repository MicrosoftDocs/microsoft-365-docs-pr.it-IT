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
description: Microsoft Teams chat e canali supporta i criteri di prevenzione della perdita dei dati (DLP).
ms.openlocfilehash: e55bfa34b2495465f573bcede3ebda2308dbbbbc
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583389"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenzione della perdita dei dati e Microsoft Teams

Se l'organizzazione dispone di prevenzione della perdita dei dati (DLP), è possibile definire criteri che impediscono agli utenti di condividere informazioni riservate in un canale Microsoft Teams o una sessione di chat. Ecco alcuni esempi del funzionamento di questa protezione:

- **Esempio 1: Protezione delle informazioni riservate nei messaggi**. Si supponga che un utente tenti di condividere informazioni riservate in Teams chat o canale con utenti guest (utenti esterni). Se si dispone di un criterio DLP definito per evitare questo problema, i messaggi con informazioni riservate inviate a utenti esterni vengono eliminati. Ciò avviene automaticamente e in pochi secondi, in base alla configurazione del criterio DLP.

    > [!NOTE]
    > DLP per Microsoft Teams blocca il contenuto sensibile se condiviso con Microsoft Teams utenti che hanno:<br/>- [accesso guest](/MicrosoftTeams/guest-access) in team e canali; o<br/>- [accesso esterno](/MicrosoftTeams/manage-external-access) nelle riunioni e nelle sessioni di chat. <p>DLP per le sessioni di chat esterne funzionerà solo se sia il mittente che il destinatario sono in modalità solo Teams e utilizzano Microsoft Teams [federazione nativa.](/microsoftteams/manage-external-access) DLP per Teams non blocca i messaggi in [interoperabilità](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con Skype for Business o con sessioni di chat federate non native.

- **Esempio 2: protezione delle informazioni riservate nei documenti**. Si supponga che un utente tenti di condividere un documento con gli utenti guest in un canale Microsoft Teams o in una chat e che il documento contenga informazioni riservate. Se si dispone di un criterio DLP definito per evitare questo problema, il documento non verrà aperto per tali utenti. Il criterio di prevenzione della perdita dei dati deve includere SharePoint e OneDrive per far sì che la protezione sia in vigore. Si tratta di un esempio di DLP per SharePoint che viene visualizzato in Microsoft Teams e pertanto richiede che gli utenti siano concessi in licenza per Office 365 DLP (incluso in Office 365 E3), ma non richiedono agli utenti di essere concessi in licenza per Office 365 Advanced Compliance.

## <a name="dlp-licensing-for-microsoft-teams"></a>Licenze DLP per Microsoft Teams

[Le funzionalità di prevenzione della](dlp-learn-about-dlp.md) perdita dei dati sono state estese Microsoft Teams messaggi di chat e canali, inclusi i messaggi del canale **privato** per:

- Office 365 E5/A5
- Microsoft 365 E5/A5
- Microsoft 365 Protezione e governance delle informazioni
- Office 365 Advanced Compliance

Office 365 e Microsoft 365 E3 includono la protezione DLP per SharePoint Online, OneDrive e Exchange Online. Sono inclusi anche i file condivisi tramite Teams perché Teams utilizza SharePoint Online e OneDrive per condividere i file.

Il supporto per la protezione DLP in Teams Chat richiede E5.

Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

> [!IMPORTANT]
> DLP si applica solo ai messaggi effettivi nel thread di chat o canale. Le notifiche di attività, che includono un'anteprima breve dei  messaggi e vengono visualizzate in base alle impostazioni di notifica di un utente, non sono incluse in Teams DLP. Tutte le informazioni riservate presenti nella parte del messaggio visualizzata nell'anteprima rimarranno visibili nella notifica anche dopo l'applicazione del criterio DLP e la rimozione delle informazioni riservate del messaggio stesso.

## <a name="scope-of-dlp-protection"></a>Ambito della protezione DLP

La protezione DLP viene applicata in modo diverso Teams entità.

|Account utente/Gruppi/Elenco  |Teams Entità |Protezione DLP disponibile|
|---------|---------|---------|
|singoli account utente     |1:1/n chat         |sì         |
|     |chat generali         |no         |
|     |canali condivisi         |no         |
|     |canali privati         |sì         |
|gruppi di sicurezza/liste di distribuzione  | 1:1/n chat         |sì         |
|     |chat generali         |no         |
|     |canali condivisi         |no      |
|     |canali privati         |sì        |
|Microsoft 365 gruppo    |1:1/n chat          |no         |
|     |chat generali          |sì        |
|     |canali condivisi|sì |
|     |canali privati|no| 


## <a name="policy-tips-help-educate-users"></a>I suggerimenti per i criteri aiutano a formare gli utenti

Analogamente al funzionamento di DLP in [Exchange, Outlook, Outlook sul Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint Online, siti OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e client desktop [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), i suggerimenti per i criteri vengono visualizzati quando viene attivata un'azione con un criterio DLP. Ecco un esempio di suggerimento per i criteri:

![Notifica dei messaggi bloccati in Teams](../media/dlp-teams-blockedmessage-notification.png)

In questo caso, il mittente ha tentato di condividere un numero di previdenza sociale in Microsoft Teams canale. Il **collegamento What can I do?** apre una finestra di dialogo che consente al mittente di risolvere il problema. Si noti che il mittente può scegliere di ignorare il criterio o inviare una notifica a un amministratore per esaminarlo e risolverlo.

![Opzioni per risolvere i messaggi bloccati](../media/dlp-teams-blockedmessage-possibleactions.png)

Nell'organizzazione, è possibile scegliere di consentire agli utenti di ignorare un criterio DLP. Quando si configurano i criteri DLP, è possibile utilizzare i suggerimenti per i criteri predefiniti o [personalizzare i suggerimenti per](#to-customize-policy-tips) i criteri per l'organizzazione.

Tornando all'esempio, in cui un mittente ha condiviso un numero di previdenza sociale in un canale Teams, ecco cosa ha visto il destinatario:

> [!div class="mx-imgBorder"]
> ![Messaggio bloccato](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Personalizzare suggerimenti per i criteri

Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati. Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

1. Passare al Centro conformità ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e accedere.

2. Scegliere **Prevenzione della perdita dei dati** > **Criteri**.

3. Selezionare un criterio e accanto a **Impostazioni criteri** scegliere **Modifica.**

4. Creare una nuova regola o modificare una regola esistente per il criterio.

    > [!div class="mx-imgBorder"]
    > ![Modifica di una regola per un criterio](../media/dlp-teams-editrule.png)

5. Nella scheda **Notifiche utente** seleziona Personalizza il testo del messaggio **di posta** elettronica e/o Personalizza le opzioni del testo del **suggerimento per i** criteri.

    > [!div class="mx-imgBorder"]
    > ![Personalizzare le notifiche utente e i suggerimenti per i criteri](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Specificare il testo che si desidera utilizzare per le notifiche di posta elettronica e/o i suggerimenti per i criteri, quindi scegliere **Salva**.

7. Nella scheda **Impostazioni criteri** scegliere **Salva**.

Consentire circa un'ora che le modifiche funzionino nel data center e si sincronizzano con gli account utente.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Aggiungere Microsoft Teams come ubicazione per i criteri di prevenzione della perdita dei dati esistenti

Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati. Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

1. Passare al Centro conformità ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e accedere.

2. Scegliere **Prevenzione della perdita dei dati** > **Criteri**.

3. Selezionare un criterio e osservare i valori in **Posizioni**. Se vengono visualizzati **Teams messaggi di chat e canali,** è tutto impostato. In caso contrario, fare clic su **Modifica.**

    > [!div class="mx-imgBorder"]
    > ![Percorsi per i criteri esistenti](../media/dlp-teams-editexistingpolicy.png)

4. Nella colonna **Stato** attivare il criterio per i messaggi di chat e canali **Teams messaggi di chat e canali.**

    > [!div class="mx-imgBorder"]
    > ![DLP per Teams chat e canali](../media/dlp-teams-addteamschatschannels.png)

5. Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.** È possibile specificare quanto segue:

    1. fino a 1000 singoli account da includere o escludere
    1. liste di distribuzione e gruppi di sicurezza da includere o escludere. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Quindi scegliere **Avanti**.

7. Fare clic su **Salva**.

Consentire circa un'ora che le modifiche funzionino nel data center e si sincronizzano con gli account utente.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definire nuovi criteri di prevenzione della perdita dei dati per Microsoft Teams

Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati. Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

1. Passare al Centro conformità ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e accedere.

2. Scegliere **Prevenzione della perdita dei dati** > **Criteri** > **+ Crea un criterio**.

3. Scegliere un [modello](data-loss-prevention-policies.md#dlp-policy-templates)e quindi scegliere **Avanti**.

    In questo esempio è stato scelto il modello Dati personali degli Stati Uniti.

    > [!div class="mx-imgBorder"]
    > ![Modello di privacy per i criteri DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Nella scheda **Assegnare un nome al** criterio specificare un nome e una descrizione per il criterio e quindi scegliere **Avanti**.

5. Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.** È possibile specificare quanto segue:

    1. fino a 1000 singoli account da includere o escludere
    1. liste di distribuzione e gruppi di sicurezza da includere o escludere. **Si tratta di una funzionalità di anteprima pubblica.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Percorsi dei criteri DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Se si desidera verificare che i documenti contenenti informazioni riservate non siano condivisi in modo inappropriato in Teams, verificare che i siti e gli account **OneDrive** di **SharePoint** siano attivati, insieme ai messaggi di chat e canali di **Teams**.

6. Nella scheda **Impostazioni criteri,** in **Personalizza** il tipo di contenuto che si desidera proteggere, mantenere le impostazioni semplici predefinite oppure scegliere **Usa impostazioni avanzate** e quindi **avanti.** Se si scelgono impostazioni avanzate, è possibile creare o modificare le regole per i criteri. Per informazioni su questo argomento, vedere [Impostazioni semplici e impostazioni avanzate.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  Nella scheda **Impostazioni dei criteri,** in Cosa vuoi fare se rileviamo **informazioni riservate?** esamina le impostazioni. Ecco dove puoi scegliere se mantenere i suggerimenti e le notifiche di [posta](use-notifications-and-policy-tips.md)elettronica predefiniti o personalizzarli.

    > [!div class="mx-imgBorder"]
    > ![Impostazioni dei criteri DLP con suggerimenti e notifiche](../media/dlp-teams-policysettings-tipsemails.png)

    Al termine della revisione o della modifica delle impostazioni, scegliere **Avanti.**

8. Nella  scheda Impostazioni criteri, in Si desidera attivare il criterio o testare prima gli **elementi?**, scegliere se attivare il [criterio,](dlp-overview-plan-for-dlp.md#policy-deployment)testarlo per primo o mantenerlo disattivato per il momento e quindi scegliere **Avanti**.

    > [!div class="mx-imgBorder"]
    > ![Specificare se attivare il criterio](../media/dlp-teams-policysettings-turnonnow.png)

9. Nella scheda **Rivedere le impostazioni** esaminare le impostazioni per il nuovo criterio. Scegliere **Modifica** per apportare modifiche. Al termine, scegliere **Crea**.

Consentire circa un'ora per il funzionamento del nuovo criterio nel data center e la sincronizzazione con gli account utente.

## <a name="prevent-external-access-to-sensitive-documents"></a>Prevenire l'accesso esterno ai documenti sensibili

Per assicurarsi che SharePoint documenti contenenti informazioni riservate non siano accessibili da utenti guest esterni da SharePoint o Teams per impostazione predefinita, selezionare quanto segue:

- È possibile assicurarsi che i documenti siano protetti fino all'analisi DLP e li contrassegni come sicuri da condividere contrassegnando i nuovi [file come sensibili per impostazione predefinita.](/sharepoint/sensitive-by-default)

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

Criteri DLP in azione quando si tenta di condividere un documento in SharePoint contenente informazioni riservate con un guest esterno:

> [!div class="mx-imgBorder"]
> ![Condivisione esterna bloccata](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


Criteri DLP in azione quando guest tenta di aprire un documento in Teams con blocco esterno:

> [!div class="mx-imgBorder"]
> ![Accesso esterno bloccato](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Articoli correlati

- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](use-notifications-and-policy-tips.md)
