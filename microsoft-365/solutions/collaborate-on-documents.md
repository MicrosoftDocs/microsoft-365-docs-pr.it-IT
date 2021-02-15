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
description: In questo articolo viene illustrato come collaborare con gli utenti guest su un documento in SharePoint e OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663512"
---
# <a name="collaborate-with-guests-on-a-document"></a>Collaborare con gli utenti guest a un documento

Se è necessario collaborare con persone esterne all'organizzazione sui documenti in SharePoint o OneDrive, è possibile inviare loro un collegamento di condivisione al documento. In questo articolo verranno descritti i passaggi di configurazione di Microsoft 365 necessari per configurare i collegamenti di condivisione per SharePoint e OneDrive per le esigenze dell'organizzazione.

## <a name="video-demonstration"></a>Dimostrazione video

In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Impostazioni di collaborazione esterna di Azure

La condivisione in Microsoft 365 è regolata al livello più alto dalle impostazioni di collaborazione esterna [B2B in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) Se la condivisione guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.

Controllare le impostazioni di collaborazione esterna B2B per assicurarsi che la condivisione con gli utenti guest non sia bloccata.

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Per impostare le impostazioni di collaborazione esterna

1. Accedere ad Azure Active Directory all'indirizzo [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Nel riquadro di spostamento sinistro fare clic **su Azure Active Directory.**
3. Fare **clic su Identità esterne.**
4. Nel riquadro **di spostamento sinistro** della schermata Introduzione fare clic su Impostazioni collaborazione **esterna.**
5. Verificare che **gli amministratori e gli utenti** nel  ruolo di mittente dell'invito guest possano invitare e che i membri possano invitare siano entrambi impostati su **Sì.**
6. Se si apportano modifiche, fare clic su **Salva**.

Prendere nota delle impostazioni nella **sezione Restrizioni di** collaborazione. Assicurarsi che i domini dei guest con cui si vuole collaborare non siano bloccati.

Se si lavora con utenti guest di più organizzazioni, è possibile limitare la possibilità di accedere ai dati della directory. Ciò impedirà loro di vedere chi altro è un guest nella directory. A tale scopo, in Restrizioni di accesso degli utenti **guest,** selezionare Gli utenti guest hanno accesso limitato alle proprietà e l'appartenenza alle impostazioni degli oggetti **directory** o l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti **directory.**

## <a name="sharepoint-organization-level-sharing-settings"></a>Impostazioni di condivisione a livello di organizzazione di SharePoint

Per consentire agli utenti esterni all'organizzazione di accedere a un documento in SharePoint o OneDrive, le impostazioni di condivisione a livello di organizzazione di SharePoint e OneDrive devono consentire la condivisione con persone esterne all'organizzazione.

Le impostazioni a livello di organizzazione per SharePoint determinano le impostazioni che saranno disponibili per i singoli siti di SharePoint. Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione. L'impostazione a livello di organizzazione per OneDrive determina il livello di condivisione che sarà disponibile nelle raccolte di OneDrive degli utenti.

Per SharePoint e OneDrive, se si desidera consentire la condivisione di file e cartelle non autenticati, scegliere **Chiunque.** Se si desidera assicurarsi che gli utenti esterni all'organizzazione devono eseguire l'autenticazione, scegliere Utenti **guest nuovi ed esistenti.** *Tutti* i collegamenti sono il modo più semplice per condividere: gli utenti esterni all'organizzazione possono aprire il collegamento senza autenticazione e possono passarlo ad altri utenti.

Per SharePoint, scegliere l'impostazione più permissiva che sarà necessaria a qualsiasi sito dell'organizzazione.

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Per configurare le impostazioni di condivisione a livello di organizzazione di SharePoint

1. Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, in **Interfaccia di amministrazione,** fare clic su **SharePoint.**
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di SharePoint fare **clic** su Condivisione in **Criteri.**
3. Verificare che la condivisione esterna per SharePoint o OneDrive sia impostata su **Chiunque** o **Utenti guest nuovi ed esistenti.** Si noti che l'impostazione di OneDrive non può essere più permissiva dell'impostazione di SharePoint.
4. Se si apportano modifiche, fare clic su **Salva**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint

Le impostazioni predefinite dei collegamenti a file e cartelle determinano l'opzione di collegamento che verrà visualizzata agli utenti per impostazione predefinita quando condividono un file o una cartella. Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione, se lo si desidera.

Tenere presente che questa impostazione influisce sui siti di SharePoint nell'organizzazione, nonché su OneDrive.

Scegliere un collegamento da uno dei tipi seguenti, che viene quindi selezionato per impostazione predefinita quando gli utenti condividono file e cartelle:

- **Chiunque abbia il collegamento:** scegliere questa opzione se si prevede di eseguire molte attività di condivisione di file e cartelle non autenticati. Se si desidera consentire collegamenti *chiunque* ma si è preoccupati per la condivisione accidentale non autenticata, prendere in considerazione una delle altre opzioni come impostazione predefinita. Questo tipo di collegamento è disponibile solo se è stata abilitata la **condivisione chiunque.**
- **Solo gli utenti dell'organizzazione:** scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con utenti interni all'organizzazione.
- **Persone specifiche:** considerare questa opzione se si prevede di eseguire molte attività di condivisione di file e cartelle con utenti guest. Questo tipo di collegamento funziona con gli utenti guest e richiede l'autenticazione.
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Per configurare le impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint e OneDrive

1. Passare alla pagina Condivisione nell'interfaccia di amministrazione di SharePoint.
2. In **Collegamenti a file e cartelle** selezionare il collegamento di condivisione predefinito che si desidera utilizzare.
3. Se si apportano modifiche, fare clic su **Salva**.

Per impostare l'autorizzazione per il collegamento di condivisione, in **Scegliere l'autorizzazione** selezionata per impostazione predefinita per i collegamenti di condivisione.

1. Selezionare **Visualizza** se non si desidera che gli utenti non autenticati apportare modifiche ai file e alle cartelle.
2. Selezionare **Modifica** se si desidera consentire agli utenti non autenticati di apportare modifiche ai file e alle cartelle.

Si noti che le due opzioni di premissione precedenti possono essere applicate non solo per gli utenti guest/esterni, ma anche per gli utenti interni. L'opzione di autorizzazione scelta è determinata dalla discrezione dell'utente.

Per impostare le autorizzazioni per i collegamenti che consentono la condivisione con chiunque

1. In questi **collegamenti è possibile assegnare queste autorizzazioni:** riquadro secondario, 
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

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di SharePoint espandere **Siti** e fare clic su **Siti attivi.**
2. Selezionare il sito in cui si desidera condividere file e cartelle con utenti guest.
3. Scorrere verso destra nella riga in cui è presente il sito selezionato e fare clic in un punto qualsiasi della **colonna Condivisione** esterna.
4. Nella pagina visualizzata fare clic sulla **scheda** Criteri.
5. Nel riquadro **Condivisione esterna** fare clic su **Modifica.**
6. Verificare che la condivisione sia impostata **su Chiunque o** Utenti guest nuovi ed **esistenti.**
7. Se si apportano modifiche, fare clic su **Salva**.

## <a name="invite-users"></a>Invitare utenti

Le impostazioni di condivisione guest sono ora configurate; in modo che gli utenti possano ora condividere file e cartelle con persone esterne all'organizzazione. Per [ulteriori informazioni, vedere](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) Condividere file e cartelle di OneDrive e file o cartelle di [SharePoint.](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)

## <a name="see-also"></a>Vedere anche

[Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)

[Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest](share-limit-accidental-exposure.md)

[Integrazione di SharePoint e OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
