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
description: È ora possibile applicare i criteri DLP alle chat e ai canali di Microsoft Teams. Leggi questo articolo per altre informazioni sul suo funzionamento.
ms.openlocfilehash: 13d5d73423cc6ad7db76076f6a53dde668b8fa5c
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279364"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenzione della perdita dei dati e Microsoft Teams

> [!NOTE]
> Le funzionalità di prevenzione della perdita dei dati sono state aggiunte di recente ai messaggi di chat e canali di Microsoft Teams per gli utenti con licenza per Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance o Office 365 Advanced Compliance. Office 365 e Microsoft 365 E3 includono la protezione DLP per SharePoint Online, OneDrive ed Exchange Online. Sono inclusi anche i file condivisi tramite Teams perché Teams usa SharePoint Online e OneDrive per condividere i file.
Il supporto per la protezione DLP in Teams Chat richiede E5.
Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

> [!IMPORTANT]
> DLP per Teams è supportato solo quando l'utente dispone di una cassetta postale in Exchange Online

## <a name="overview-of-dlp-for-microsoft-teams"></a>Panoramica della prevenzione della perdita dei dati per Microsoft Teams

Di recente, [le funzionalità di prevenzione](data-loss-prevention-policies.md) della perdita dei dati (DLP) sono state estese per includere i messaggi di chat e canali di Microsoft Teams, inclusi i messaggi del canale **privato.**

Se l'organizzazione dispone di DLP, è ora possibile definire criteri che impediscono agli utenti di condividere informazioni riservate in un canale di Microsoft Teams o in una sessione di chat. Ecco alcuni esempi del funzionamento di questa protezione:

- **Esempio 1: Protezione delle informazioni riservate nei messaggi.** Si supponga che qualcuno tenti di condividere informazioni riservate in una chat o in un canale di Teams con utenti guest (utenti esterni). Se si dispone di un criterio DLP definito per evitare questo problema, i messaggi con informazioni riservate inviate a utenti esterni vengono eliminati. Ciò avviene automaticamente e in pochi secondi, in base alla configurazione del criterio DLP.

    > [!NOTE]
    > DLP per Microsoft Teams blocca i contenuti sensibili quando vengono condivisi con gli utenti di Microsoft Teams che hanno:<br/>- [accesso guest](https://docs.microsoft.com/MicrosoftTeams/guest-access) in team e canali; oppure<br/>- [accesso esterno](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) nelle riunioni e nelle sessioni di chat. <p>DLP per le sessioni di chat esterne funzionerà solo se il mittente e il destinatario sono in modalità Solo Teams e usano la [federazione nativa di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-external-access) DLP per Teams non blocca i messaggi in [interoperabilità](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con Skype for Business o le sessioni di chat federate non native.

- **Esempio 2: Protezione delle informazioni riservate nei documenti.** Si supponga che qualcuno tenti di condividere un documento con utenti guest in un canale o in una chat di Microsoft Teams e che il documento contenga informazioni riservate. Se è stato definito un criterio DLP per evitare questo problema, il documento non verrà aperto per tali utenti. Tenere presente che, in questo caso, i criteri DLP devono includere SharePoint e OneDrive per garantire la protezione. Si tratta di un esempio di DLP per SharePoint che viene visualizzato in Microsoft Teams e pertanto richiede che gli utenti siano concessi in licenza per DLP di Office 365 (incluso in Office 365 E3), ma non richiede che gli utenti siano concessi in licenza per Office 365 Advanced Compliance.

## <a name="policy-tips-help-educate-users"></a>I suggerimenti per i criteri aiutano a formare gli utenti

Analogamente al funzionamento della prevenzione della perdita dei dati in [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)sul Web, [SharePoint Online,](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)siti di OneDrive for Business e client desktop di [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)i suggerimenti per i criteri vengono visualizzati quando un'azione è in conflitto con un criterio DLP. Ecco un esempio di suggerimento per i criteri:

![Notifica dei messaggi bloccati in Teams](../media/dlp-teams-blockedmessage-notification.png)

In questo caso, il mittente ha tentato di condividere un numero di previdenza sociale in un canale di Microsoft Teams. Il **collegamento What can I do?** apre una finestra di dialogo in cui sono disponibili opzioni per il mittente per risolvere il problema. Si noti che in questo caso, il mittente può scegliere di ignorare il criterio o informare un amministratore di esaminarlo e risolverlo.

![Opzioni per risolvere i messaggi bloccati](../media/dlp-teams-blockedmessage-possibleactions.png)

Nell'organizzazione, è possibile scegliere di consentire agli utenti di ignorare un criterio DLP. Inoltre, quando si configurano i criteri DLP, è possibile utilizzare i suggerimenti per i criteri predefiniti o personalizzare i suggerimenti per i [criteri](#to-customize-policy-tips) per l'organizzazione.

Tornando all'esempio, in cui un mittente ha condiviso un numero di previdenza sociale in un canale di Teams, ecco cosa ha visto il destinatario:

![Messaggio bloccato](../media/dlp-teams-blockedmessage-notification-to-user.png)

The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.

### <a name="to-customize-policy-tips"></a>Per personalizzare i suggerimenti per i criteri

Per eseguire questa attività, è necessario disporre di un ruolo che dispone delle autorizzazioni per modificare i criteri DLP. Per ulteriori informazioni, vedere [Autorizzazioni.](data-loss-prevention-policies.md#permissions)

1. Accedere al Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) e accedere.

2. Scegliere **Criteri di prevenzione della perdita dei**  >  **dati.**

3. Selezionare un criterio e accanto a Impostazioni **criterio** scegliere **Modifica.**

4. Creare una nuova regola o modificare una regola esistente per il criterio.<br/>![Modifica di una regola per un criterio](../media/dlp-teams-editrule.png)<br/>

5. Nella scheda **Notifiche utente selezionare** Personalizza il testo del messaggio di **posta** elettronica e/o Personalizza le opzioni di testo del **suggerimento per i** criteri.<br/>![Personalizzare le notifiche utente e i suggerimenti per i criteri](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Specificare il testo che si desidera utilizzare per le notifiche di posta elettronica e/o i suggerimenti per i criteri, quindi scegliere **Salva.**

7. Nella scheda **Impostazioni criteri** scegliere **Salva.**

Consentire circa un'ora per consentire alle modifiche di operare nel data center e di eseguire la sincronizzazione con gli account utente.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Aggiungere Microsoft Teams come posizione ai criteri DLP esistenti

Per eseguire questa attività, è necessario disporre di un ruolo che dispone delle autorizzazioni per modificare i criteri DLP. Per ulteriori informazioni, vedere [Autorizzazioni.](data-loss-prevention-policies.md#permissions)

1. Accedere al Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) e accedere.

2. Scegliere **Criteri di prevenzione della perdita dei**  >  **dati.**

3. Selezionare un criterio e osservare i valori in **Posizioni.** Se vengono visualizzati **messaggi di chat e canali di Teams,** è tutto impostato. In caso contrario, fare clic su **Modifica.**<br/>![Percorsi per i criteri esistenti](../media/dlp-teams-editexistingpolicy.png)<br/>

4. Nella colonna **Stato** attivare i criteri per i messaggi di **chat e canali di Teams.**<br/>![DLP per chat e canali di Teams](../media/dlp-teams-addteamschatschannels.png)<br/>

5. Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.** È possibile specificare quanto segue:
    1. fino a 1000 account individuali da includere o escludere
    1. liste di distribuzione e gruppi di sicurezza da includere o escludere. **Si tratta di una funzionalità di anteprima pubblica.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Quindi scegliere **Avanti**.



6. Fare clic su **Salva**.

Consentire circa un'ora per consentire alle modifiche di operare nel data center e di eseguire la sincronizzazione con gli account utente.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definire un nuovo criterio DLP per Microsoft Teams

Per eseguire questa attività, è necessario disporre di un ruolo che dispone delle autorizzazioni per modificare i criteri DLP. Per ulteriori informazioni, vedere [Autorizzazioni.](data-loss-prevention-policies.md#permissions)

1. Accedere al Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) e accedere.

2. Choose **Data loss prevention**  >  **Policy**+ Create a  >  **policy.**

3. Scegliere un [modello](data-loss-prevention-policies.md#dlp-policy-templates)e quindi scegliere **Avanti.**<br/>In questo esempio, è stato scelto il modello di dati di informazioni personali degli Stati Uniti.<br/>![Modello di privacy per i criteri DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Nella scheda **Name your policy** specificare un nome e una descrizione per il criterio e quindi scegliere **Next.**

5. Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.** È possibile specificare quanto segue:
    1. fino a 1000 account individuali da includere o escludere
    1. liste di distribuzione e gruppi di sicurezza da includere o escludere. **Si tratta di una funzionalità di anteprima pubblica.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![Percorsi dei criteri DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> Se si desidera assicurarsi che i documenti contenenti informazioni riservate non siano condivisi in modo inappropriato in Teams, verificare che i siti di **SharePoint** e gli account di **OneDrive** siano attivati, insieme ai messaggi di chat e canali di **Teams.**


6. Nella scheda **Impostazioni criteri,** **in** Personalizza il tipo di contenuto che si desidera proteggere, mantenere le impostazioni semplici predefinite oppure scegliere Usa impostazioni **avanzate** e quindi **scegliere Avanti.** Se si scelgono impostazioni avanzate, è possibile creare o modificare le regole per i criteri. Per informazioni su questo argomento, vedere [Impostazioni semplici e impostazioni avanzate.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  Nella scheda **Impostazioni dei criteri,** in Che cosa vuoi fare se rileviamo **informazioni sensibili,** esamina le impostazioni. Di seguito è possibile scegliere se mantenere i suggerimenti per i criteri predefiniti e le notifiche tramite posta [elettronica](use-notifications-and-policy-tips.md)oppure personalizzarli.<br/>![Impostazioni dei criteri DLP con suggerimenti e notifiche](../media/dlp-teams-policysettings-tipsemails.png)<br/>Al termine della revisione o della modifica delle impostazioni, scegliere **Avanti.**

8. Nella  scheda Impostazioni criteri, in Si desidera attivare il criterio o testare prima gli **elementi?**, scegliere se attivare il [criterio,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)testarlo per primo o mantenerlo disattivato per il momento e quindi scegliere **Avanti.**<br/>![Specificare se attivare il criterio](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. Nella scheda **Controlla le impostazioni** esaminare le impostazioni per il nuovo criterio. Scegliere **Modifica** per apportare modifiche. Al termine, scegliere **Crea.**

Consentire circa un'ora per il funzionamento del nuovo criterio nel data center e la sincronizzazione con gli account utente.

## <a name="prevent-external-access-to-sensitive-documents"></a>Impedire l'accesso esterno ai documenti sensibili

Per assicurarsi che i documenti di SharePoint contenenti informazioni riservate non siano accessibili da utenti guest esterni da SharePoint o Teams per impostazione predefinita, selezionare quanto segue:

- È possibile garantire che i documenti siano protetti fino all'analisi DLP e contrassegnarli come sicuri da condividere contrassegnando i nuovi file come [sensibili per impostazione predefinita](https://docs.microsoft.com/sharepoint/sensitive-by-default)
- Struttura dei criteri DLP consigliata
    - **Condizioni**
        - Il contenuto contiene uno di questi tipi di informazioni riservate: [Selezionare tutto ciò che si applica]
        - Il contenuto viene condiviso da Microsoft 365 con persone esterne all'organizzazione
        <br/>![Condizioni DLP per rilevare la condivisione esterna di contenuti sensibili](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **Azioni**
        - Limitare l'accesso al contenuto per gli utenti esterni
        - Inviare notifiche agli utenti tramite posta elettronica e suggerimenti per i criteri
        - Inviare rapporti operazioni non consentite all'amministratore    
        <br/>![Azione DLP per bloccare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-action.png)<br/>

Criteri DLP in azione quando si tenta di condividere un documento in SharePoint contenente informazioni riservate con un guest esterno:
<br/>![Condivisione esterna bloccata](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


Criteri DLP in azione quando guest tenta di aprire un documento in Teams con blocco esterno:
<br/>![Accesso esterno bloccato](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>Articoli correlati

[Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)

[Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](use-notifications-and-policy-tips.md)
