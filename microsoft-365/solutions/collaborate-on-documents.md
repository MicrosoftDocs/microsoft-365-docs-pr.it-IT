---
title: Collaborare con gli utenti guest a un documento
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: In questo articolo viene illustrato come collaborare con utenti guest a un documento in SharePoint e OneDrive.
ms.openlocfilehash: 9158ec7692ef90eb2e270242472fceb10d0e60b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920229"
---
# <a name="collaborate-with-guests-on-a-document"></a>Collaborare con gli utenti guest a un documento

Se è necessario collaborare con persone esterne all'organizzazione sui documenti in SharePoint o OneDrive, è possibile inviare loro un collegamento di condivisione al documento. In questo articolo verranno descritti i passaggi di configurazione di Microsoft 365 necessari per configurare i collegamenti di condivisione per SharePoint e OneDrive per le esigenze dell'organizzazione.

## <a name="video-demonstration"></a>Dimostrazione video

Il video mostra la procedura di configurazione descritta in questo documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Impostazioni di collaborazione esterna di Azure

La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni di collaborazione esterna B2B in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Se la condivisione guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.

Controllare le impostazioni di collaborazione esterna B2B per assicurarsi che la condivisione con gli utenti guest non sia bloccata.

![Screenshot della pagina delle impostazioni di Organizational Relationships di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Per configurare le impostazioni di collaborazione esterna.

1. Accedere ad Azure Active Directory su [https://aad.portal.azure.com](https://aad.portal.azure.com).
2. Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.
3. Fare clic su **Identità esterne**.
4. Nella schermata **Attività iniziali**, nel riquadro di spostamento a sinistra, fare clic su **Impostazioni di collaborazione esterna**.
5. Verificare che le opzioni **Amministratori e utenti con il ruolo di guest possono invitare** e **I membri possono invitare** siano entrambe impostate su **Sì**.
6. Se si apportano modifiche, fare clic su **Salva**.

Prendere nota delle impostazioni nella sezione **Restrizioni di collaborazione**. Verificare che i domini degli utenti guest con cui si desidera collaborare non siano bloccati.

Se si lavora con utenti guest da più organizzazioni, è possibile limitare la possibilità di accesso ai dati della directory. In questo modo, non potranno vedere gli altri utenti guest nella directory. A questo scopo in **Restrizioni di accesso degli utenti guest**, selezionare **Gli utenti guest hanno accesso limitato alle proprietà e all'iscrizione delle impostazioni degli oggetti della directory** oppure **L'accesso degli utenti guest è limitato alle proprietà e alle iscrizioni dei propri oggetti della directory**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Impostazioni di condivisione a livello di organizzazione di SharePoint

Per consentire agli utenti esterni all'organizzazione di accedere a un documento in SharePoint o OneDrive, le impostazioni di condivisione a livello di organizzazione di SharePoint e OneDrive devono consentire la condivisione con persone esterne all'organizzazione.

Le impostazioni a livello di organizzazione per SharePoint determinano le impostazioni che saranno disponibili per i singoli siti di SharePoint. Le impostazioni del sito non possono essere più permissive delle impostazioni a livello di organizzazione. L'impostazione a livello di organizzazione per OneDrive determina il livello di condivisione che sarà disponibile nelle raccolte di OneDrive degli utenti.

Per SharePoint e OneDrive, se si desidera consentire la condivisione di file e cartelle non autenticati, scegliere **Chiunque**. Se si desidera verificare che gli utenti esterni all'organizzazione devono eseguire l'autenticazione, scegliere **Guest nuovi ed esistenti.** *I* collegamenti chiunque sono il modo più semplice per condividere: gli utenti esterni all'organizzazione possono aprire il collegamento senza autenticazione e possono passarlo ad altri utenti.

Per SharePoint, scegliere l'impostazione più permissiva che sarà necessaria a qualsiasi sito dell'organizzazione.

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Per configurare le impostazioni di condivisione a livello di organizzazione in SharePoint

1. Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, in **Interfacce di amministrazione**, fare clic su **SharePoint**.
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di SharePoint fare clic su Condivisione **in** **Criteri.**
3. Verificare che la condivisione esterna per SharePoint o OneDrive sia impostata su **Chiunque** o Su Guest **nuovi ed esistenti.** Si noti che l'impostazione di OneDrive non può essere più permissiva dell'impostazione di SharePoint.
4. Se si apportano modifiche, fare clic su **Salva**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint

Le impostazioni predefinite per i collegamenti a file e cartelle determinano le opzioni di collegamento visualizzate dagli utenti per impostazione predefinita durante la condivisione di un file o una cartella. Se si desidera, gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione.

Tenere presente che questa impostazione influisce sui siti di SharePoint nell'organizzazione, nonché su OneDrive.

Scegliere un collegamento da uno dei tipi seguenti, che viene quindi selezionato per impostazione predefinita quando gli utenti condividono file e cartelle:

- **Chiunque abbia il collegamento:** scegliere questa opzione se si prevede di eseguire molte condivisioni di file e cartelle non autenticati. Se si desidera autorizzare *Chiunque* abbia il collegamento, ma si è preoccupati in caso di condivisione accidentale non autenticata, considerare una delle altre opzioni come predefinite. Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione **Chiunque**.
- **Solo gli utenti dell'organizzazione**: scegliere questa opzione se si prevede che la maggior parte delle condivisioni di file e cartelle sia con persone interne all'organizzazione.
- **Utenti specifici**: valutare questa opzione se si prevede di condividere molti file e cartelle con utenti guest. Questo tipo di collegamento funziona con gli utenti guest e richiede l'autenticazione degli utenti.
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Per impostare le impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint e OneDrive

1. Passare alla pagina Condivisione nell'interfaccia di amministrazione di SharePoint.
2. In **Collegamenti a file e cartelle**, selezionare il collegamento di condivisione predefinito che si desidera usare.
3. Se si apportano modifiche, fare clic su **Salva**.

Per impostare l'autorizzazione per il collegamento di condivisione, in **Scegliere l'autorizzazione** selezionata per impostazione predefinita per i collegamenti di condivisione.

1. Selezionare **Visualizza** se non si desidera che gli utenti non autenticati apportare modifiche ai file e alle cartelle.
2. Selezionare **Modifica** se si desidera consentire agli utenti non autenticati di apportare modifiche ai file e alle cartelle.

Si noti che le due opzioni di premissione precedenti possono essere applicate non solo agli utenti guest/esterni, ma anche agli utenti interni. L'opzione di autorizzazione scelta è determinata dalla discrezione dell'utente.

Per impostare le autorizzazioni per i collegamenti che consentono la condivisione con chiunque

1. In Questi **collegamenti è possibile assegnare queste autorizzazioni:** riquadro secondario, 
    1. **Nell'elenco** a discesa File 
        - Selezionare **Visualizza e modifica** se si desidera consentire agli utenti non autenticati di apportare modifiche ai file.
        - Selezionare **Visualizza** se non si desidera che gli utenti non autenticati apportare modifiche ai file.
    2. **Nell'elenco a** discesa Cartelle
        - Selezionare **Visualizza, modifica e carica** se si desidera consentire agli utenti non autenticati di apportare modifiche alle cartelle.
        - Selezionare **Visualizza** se non si desidera che gli utenti non autenticati apportare modifiche alle cartelle.

## <a name="sharepoint-site-level-sharing-settings"></a>Impostazioni di condivisione a livello di sito di SharePoint

Se si condividono file e cartelle presenti in un sito di SharePoint, è inoltre necessario controllare le impostazioni di condivisione a livello di sito per tale sito.

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Per configurare le impostazioni di condivisione a livello di sito

1. Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.
2. Selezionare il sito in cui si desidera condividere file e cartelle con utenti guest.
3. Scorrere verso destra nella riga (in cui è presente il sito selezionato) e fare clic in un punto qualsiasi della **colonna Condivisione** esterna.
4. Nella pagina visualizzata fare clic sulla **scheda** Criteri.
5. Nel riquadro **Condivisione esterna** fare clic su **Modifica.**
6. Verificare che la condivisione sia impostata su **Chiunque** o **Utenti guest nuovi ed esistenti**.
7. Se si apportano modifiche, fare clic su **Salva**.

## <a name="invite-users"></a>Invitare utenti

Le impostazioni di condivisione guest sono ora configurate. in modo che gli utenti possano ora condividere file e cartelle con persone esterne all'organizzazione. Per [ulteriori informazioni, vedere](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) Condividere file e cartelle di OneDrive e file o cartelle di [SharePoint.](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)

## <a name="see-also"></a>Vedere anche

[Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)

[Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest](share-limit-accidental-exposure.md)

[Integrazione di SharePoint e OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview)