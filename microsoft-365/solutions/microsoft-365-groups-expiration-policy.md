---
title: Criteri di scadenza del gruppo Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Informazioni sui criteri di scadenza dei gruppi di Microsoft 365.
ms.openlocfilehash: 8fc9c48d5a86c68eabd4139ad0a2d0dc1e83da0f
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377224"
---
# <a name="microsoft-365-group-expiration-policy"></a>Criteri di scadenza del gruppo Microsoft 365

Con l'aumento dell'utilizzo di gruppi Microsoft 365 e Microsoft teams, gli amministratori e gli utenti hanno bisogno di un modo per pulire i gruppi e i team inutilizzati. Un criterio di scadenza dei gruppi di Microsoft 365 può contribuire a rimuovere i gruppi inattivi dal sistema e a rendere gli elementi più puliti.

Quando un gruppo scade, vengono eliminati anche tutti i servizi associati (la cassetta postale, il pianificatore, il sito di SharePoint, il team e così via).

Quando un gruppo scade è "Soft-deleted", il che significa che può essere ancora recuperato fino a 30 giorni.

Gli amministratori possono specificare un periodo di scadenza e qualsiasi gruppo inattivo che raggiunge la fine di quel periodo e non viene rinnovato, verrà eliminato. (Include team archiviati). Il periodo di scadenza inizia quando viene creato il gruppo oppure alla data in cui è stato rinnovato per ultimo. I proprietari del gruppo invieranno automaticamente un messaggio di posta elettronica prima della scadenza che consente loro di rinnovare il gruppo per un altro intervallo di scadenza. Gli utenti di team vedranno notifiche permanenti nei team.

I gruppi che sono attivamente in uso vengono rinnovati automaticamente. Una delle azioni seguenti consente di rinnovare automaticamente un gruppo:
- SharePoint: visualizzazione, modifica, download, spostamento, condivisione o caricamento dei file.
- Outlook-join Group, lettura o scrittura di un messaggio di gruppo dal gruppo e come un messaggio (Outlook sul Web).
- Teams-visiting a teams Channel.

> [!IMPORTANT]
> Quando si modifica il criterio di scadenza, il servizio ricalcola la data di scadenza per ogni gruppo. Inizia sempre a contare dalla data in cui è stato creato il gruppo e quindi applica il nuovo criterio di scadenza.

È importante sapere che la scadenza è disattivata per impostazione predefinita. Gli amministratori devono abilitarla per l'organizzazione se desiderano utilizzarla.

> [!NOTE]
> La configurazione e l'utilizzo dei criteri di scadenza per i gruppi di Microsoft 365 richiede di possedere ma non necessariamente di assegnare le licenze di Azure AD Premium per i membri di tutti i gruppi a cui viene applicato il criterio di scadenza. Per ulteriori informazioni, vedere [Guida introduttiva a Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Chi può configurare e usare i criteri di scadenza dei gruppi di Microsoft 365?

|Ruolo|Cosa possono fare|
|---------|---------|
|Amministratore globale di Office 365 (in Azure, amministratore della società), amministratore utente|Creare, leggere, aggiornare o eliminare le impostazioni dei criteri di scadenza per i gruppi di Microsoft 365.|
|Utente|Rinnovare o [ripristinare](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) un gruppo di Microsoft 365 che possiede|

## <a name="how-to-set-the-expiration-policy"></a>Informazioni su come impostare i criteri di scadenza

Come indicato in alto, la scadenza è disattivata per impostazione predefinita. Un amministratore dovrà abilitare i criteri di scadenza e impostare le proprietà per rendere effettive le stesse. Per abilitarlo, passare alla scadenza per i gruppi di **Azure Active Directory**  >  **Groups**  >  **Expiration**. In questa sezione è possibile impostare la durata predefinita del gruppo e specificare quanto in anticipo si desidera che la prima e la seconda notifica di scadenza vadano al proprietario del gruppo.

La durata del gruppo è specificata in giorni e può essere impostata su 180, 365 o su un valore personalizzato specificato. Il valore personalizzato deve essere di almeno 30 giorni.

Se il gruppo non dispone di un proprietario, i messaggi di posta elettronica di scadenza andranno all'amministratore specificato.

È possibile impostare il criterio per tutti i gruppi, solo per i gruppi selezionati o disattivarlo completamente selezionando **nessuno**. Si noti che attualmente non è possibile disporre di criteri diversi per i diversi gruppi.

![Schermata delle impostazioni di scadenza dei gruppi in Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Come funziona la scadenza con il criterio di conservazione

Se è stato configurato un criterio di conservazione per i gruppi nel centro sicurezza e conformità, i criteri di scadenza funzionano perfettamente con i criteri di conservazione. Quando un gruppo scade, le conversazioni e i file delle cassette postali del gruppo nel sito del gruppo vengono mantenuti nel contenitore di conservazione per il numero specifico di giorni definito nel criterio di conservazione. Gli utenti non vedranno il gruppo o il relativo contenuto, dopo la scadenza.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Come e quando un proprietario del gruppo apprende se i propri gruppi scadono

I proprietari del gruppo saranno informati solo tramite posta elettronica. Se il gruppo è stato creato tramite Planner, SharePoint o qualsiasi altra applicazione, le notifiche di scadenza vengono sempre inviate tramite posta elettronica. Se il gruppo è stato creato tramite Team, il proprietario del gruppo riceverà una notifica per il rinnovo tramite la sezione attività. Non è consigliabile abilitare la scadenza di un gruppo se il proprietario del gruppo non dispone di un indirizzo di posta elettronica valido.

Trenta giorni prima della scadenza del gruppo, i proprietari del gruppo (o gli indirizzi di posta elettronica specificati per i gruppi che non dispongono di un proprietario) riceveranno un messaggio di posta elettronica che consente di rinnovare facilmente il gruppo. Se non lo rinnovano, riceveranno un'altra e-mail di rinnovo 15 giorni prima della scadenza. Se non sono ancora state rinnovate, riceveranno una notifica di posta elettronica di più il giorno prima della scadenza.

Se per qualche motivo nessuno dei proprietari o degli amministratori rinnova il gruppo prima della scadenza, l'amministratore può comunque ripristinare il gruppo fino a 30 giorni dopo la data di scadenza. Per informazioni dettagliate, vedere: [ripristinare un gruppo di Microsoft 365 eliminato](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Contenuto del gruppo di archiviazione

Se si dispone di un gruppo che non si intende più utilizzare, ma si desidera conservarne il contenuto, vedere [gruppi di archiviazione, teams e Yammer](end-life-cycle-groups-teams-sites-yammer.md) per informazioni su come esportare informazioni dai diversi servizi di gruppi.

## <a name="related-articles"></a>Articoli correlati

[Panoramica dei criteri di conservazione](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Assegnare un nuovo proprietario a un gruppo orfano](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configurare la data di scadenza per i gruppi Microsoft 365](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
