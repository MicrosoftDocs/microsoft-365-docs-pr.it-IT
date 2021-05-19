---
title: Microsoft 365 criteri di scadenza del gruppo
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
recommendations: false
description: Informazioni sui criteri Microsoft 365 di scadenza dei gruppi.
ms.openlocfilehash: 90807d6c178061804e64db4440af42050a1d8e77
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530851"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 criteri di scadenza del gruppo

Con l'aumento dell'utilizzo Microsoft 365 gruppi e Microsoft Teams, gli amministratori e gli utenti hanno bisogno di un modo per pulire i gruppi e i team inutilizzati. Un Microsoft 365 di scadenza dei gruppi può aiutare a rimuovere i gruppi inattivi dal sistema e a rendere più puliti gli elementi.

Alla scadenza di un gruppo, vengono eliminati anche tutti i servizi associati (cassetta postale, Planner, SharePoint sito, team e così via).

Quando un gruppo scade, viene "eliminato in modo reversito", il che significa che può essere ripristinato fino a 30 giorni.

Gli amministratori possono specificare un periodo di scadenza e qualsiasi gruppo inattivo che raggiunge la fine di tale periodo e non viene rinnovato verrà eliminato. Sono inclusi i team archiviati. Il periodo di scadenza inizia quando il gruppo viene creato o alla data dell'ultimo rinnovo. I proprietari del gruppo riceveranno automaticamente un messaggio di posta elettronica prima della scadenza che consente loro di rinnovare il gruppo per un altro intervallo di scadenza. Teams gli utenti visualizzano notifiche persistenti in Teams.

I gruppi attivamente in uso vengono rinnovati automaticamente. Una delle azioni seguenti consente di rinnovare automaticamente un gruppo:
- SharePoint: visualizzare, modificare, scaricare, spostare, condividere o caricare file. La visualizzazione di una SharePoint non viene conteggiato come azione per il rinnovo automatico.
- Outlook - Partecipare al gruppo, leggere o scrivere un messaggio di gruppo dal gruppo e come un messaggio (Outlook sul Web).
- Teams: visitare un canale di teams.

L'unica attività Yammer che attiverà un rinnovo automatico di gruppo è il caricamento di un documento SharePoint all'interno della community.

> [!IMPORTANT]
> Quando si modifica il criterio di scadenza, il servizio ricalcola la data di scadenza per ogni gruppo. Inizia sempre il conteggio a partire dalla data di creazione del gruppo e quindi applica il nuovo criterio di scadenza.

È importante sapere che la scadenza è disattivata per impostazione predefinita. Gli amministratori devono abilitarlo per l'organizzazione se desiderano usarlo.

> [!NOTE]
> La configurazione e l'uso dei criteri di scadenza per i gruppi di Microsoft 365 richiedono di disporre, ma non necessariamente di assegnare licenze di azure AD Premium per i membri di tutti i gruppi a cui viene applicato il criterio di scadenza. Per ulteriori informazioni, vedere [Introduzione a Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Who configurare e usare i criteri di scadenza Microsoft 365 gruppi?

|Ruolo|Cosa possono fare|
|---------|---------|
|Office 365 amministratore globale (in Azure, l'amministratore della società), Amministratore utente|Creare, leggere, aggiornare o eliminare le impostazioni Microsoft 365 criteri di scadenza dei gruppi.|
|Utente|Rinnovare [o ripristinare](/azure/active-directory/users-groups-roles/groups-restore-deleted) un Microsoft 365 di cui sono proprietari|

## <a name="how-to-set-the-expiration-policy"></a>Come impostare i criteri di scadenza

Come indicato in precedenza, la scadenza è disattivata per impostazione predefinita. Un amministratore dovrà abilitare i criteri di scadenza e impostare le proprietà in modo che abbia effetto. Per abilitarlo, passare a **Azure Active Directory**  >  **scadenza**  >  **gruppi**. Qui puoi impostare la durata predefinita del gruppo e specificare con quale anticipo vuoi che le notifiche di prima e seconda scadenza passino al proprietario del gruppo.

La durata del gruppo è specificata in giorni e può essere impostata su 180, 365 o su un valore personalizzato specificato. Il valore personalizzato deve essere di almeno 30 giorni.

Se il gruppo non dispone di un proprietario, i messaggi di posta elettronica di scadenza verranno inviata all'amministratore specificato.

È possibile impostare il criterio per tutti i gruppi, solo i gruppi selezionati (fino a 500) o disattivarlo completamente selezionando **Nessuno.** Si noti che attualmente non è possibile avere criteri diversi per gruppi diversi.

![Screenshot of Groups expiration settings in Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Funzionamento della scadenza con i criteri di conservazione

Se è stato configurato un criterio di conservazione per i gruppi nel Centro sicurezza e conformità, i criteri di scadenza funzionano senza problemi con i criteri di conservazione. Quando un gruppo scade, le conversazioni e i file delle cassette postali del gruppo nel sito del gruppo vengono conservati nel contenitore di conservazione per il numero specifico di giorni definito nel criterio di conservazione. Gli utenti non potranno tuttavia visualizzare il gruppo o il relativo contenuto dopo la scadenza.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Come e quando il proprietario di un gruppo apprende se i gruppi scadono

I proprietari del gruppo riceveranno una notifica solo tramite posta elettronica. Se il gruppo è stato creato tramite Planner, SharePoint o qualsiasi altra app, le notifiche di scadenza verranno sempre inviate tramite posta elettronica. Se il gruppo è stato creato tramite Teams, il proprietario del gruppo riceverà una notifica da rinnovare tramite la sezione attività. Non è consigliabile abilitare la scadenza per un gruppo se il proprietario del gruppo non dispone di un indirizzo di posta elettronica valido.

Trenta giorni prima della scadenza del gruppo, i proprietari del gruppo (o gli indirizzi di posta elettronica specificati per i gruppi che non dispongono di un proprietario) riceveranno un messaggio di posta elettronica che consente loro di rinnovare facilmente il gruppo. Se non lo rinnovano, riceveranno un altro messaggio di posta elettronica di rinnovo 15 giorni prima della scadenza. Se non lo hanno ancora rinnovato, riceveranno un'altra notifica tramite posta elettronica il giorno prima della scadenza.

Se per qualche motivo nessuno dei proprietari o degli amministratori rinnova il gruppo prima della scadenza, l'amministratore può comunque ripristinare il gruppo fino a 30 giorni dopo la scadenza. Per informazioni dettagliate, [vedere: Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Contenuto del gruppo di archiviazione

Se si dispone di un gruppo che non si prevede più di utilizzare, ma si desidera conservarne il contenuto, vedere [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) per informazioni su come esportare le informazioni dai diversi servizi di gruppi.

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Panoramica dei criteri di conservazione](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Assegnare un nuovo proprietario a un gruppo orfano](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configurare la scadenza Microsoft 365 gruppi di lavoro](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
