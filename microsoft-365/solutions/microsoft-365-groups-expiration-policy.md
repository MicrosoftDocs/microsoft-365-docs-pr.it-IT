---
title: Criteri di scadenza dei gruppi di Microsoft 365
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
ms.openlocfilehash: 8232e7df2a8390b905386773ed0656eb8239d5c5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920917"
---
# <a name="microsoft-365-group-expiration-policy"></a>Criteri di scadenza dei gruppi di Microsoft 365

Con l'aumento dell'utilizzo dei gruppi di Microsoft 365 e Microsoft Teams, amministratori e utenti hanno bisogno di un modo per pulire i gruppi e i team inutilizzati. Un criterio di scadenza dei gruppi di Microsoft 365 può aiutare a rimuovere i gruppi inattivi dal sistema e rendere le cose più pulite.

Alla scadenza di un gruppo, vengono eliminati anche tutti i servizi associati (cassetta postale, Planner, sito di SharePoint, team e così via).

Quando un gruppo scade, viene "eliminato in modo reversito", il che significa che può essere ripristinato fino a 30 giorni.

Gli amministratori possono specificare un periodo di scadenza e qualsiasi gruppo inattivo che raggiunge la fine di tale periodo e non viene rinnovato verrà eliminato. Sono inclusi i team archiviati. Il periodo di scadenza inizia quando il gruppo viene creato o alla data dell'ultimo rinnovo. I proprietari del gruppo riceveranno automaticamente un messaggio di posta elettronica prima della scadenza che consente loro di rinnovare il gruppo per un altro intervallo di scadenza. Gli utenti di Teams visualizzano notifiche persistenti in Teams.

I gruppi attivamente in uso vengono rinnovati automaticamente. Una delle azioni seguenti consente di rinnovare automaticamente un gruppo:
- SharePoint: consente di visualizzare, modificare, scaricare, spostare, condividere o caricare file. La visualizzazione di una pagina di SharePoint non viene conteggiato come azione per il rinnovo automatico.
- Outlook - Partecipare al gruppo, leggere o scrivere un messaggio di gruppo dal gruppo e come un messaggio (Outlook sul Web).
- Teams : visitando un canale di teams.

> [!IMPORTANT]
> Quando si modifica il criterio di scadenza, il servizio ricalcola la data di scadenza per ogni gruppo. Inizia sempre il conteggio a partire dalla data di creazione del gruppo e quindi applica il nuovo criterio di scadenza.

È importante sapere che la scadenza è disattivata per impostazione predefinita. Gli amministratori devono abilitarlo per l'organizzazione se desiderano usarlo.

> [!NOTE]
> La configurazione e l'uso dei criteri di scadenza per i gruppi di Microsoft 365 richiedono di possedere, ma non necessariamente assegnare licenze Di Azure AD Premium per i membri di tutti i gruppi a cui viene applicato il criterio di scadenza. Per ulteriori informazioni, vedere [Introduzione ad Azure Active Directory Premium.](/azure/active-directory/active-directory-get-started-premium)

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Chi può configurare e usare i criteri di scadenza dei gruppi di Microsoft 365?

|Ruolo|Cosa possono fare|
|---------|---------|
|Amministratore globale di Office 365 (in Azure, amministratore della società), Amministratore utente|Creare, leggere, aggiornare o eliminare le impostazioni dei criteri di scadenza dei gruppi di Microsoft 365.|
|Utente|Rinnovare [o ripristinare](/azure/active-directory/users-groups-roles/groups-restore-deleted) un gruppo di Microsoft 365 di cui sono proprietari|

## <a name="how-to-set-the-expiration-policy"></a>Come impostare i criteri di scadenza

Come indicato in precedenza, la scadenza è disattivata per impostazione predefinita. Un amministratore dovrà abilitare i criteri di scadenza e impostare le proprietà in modo che abbia effetto. Per abilitarlo, passare a **Scadenza gruppi di Azure Active**  >    >  Directory. Qui puoi impostare la durata predefinita del gruppo e specificare con quale anticipo vuoi che le notifiche di prima e seconda scadenza passino al proprietario del gruppo.

La durata del gruppo è specificata in giorni e può essere impostata su 180, 365 o su un valore personalizzato specificato. Il valore personalizzato deve essere di almeno 30 giorni.

Se il gruppo non dispone di un proprietario, i messaggi di posta elettronica di scadenza verranno inviata all'amministratore specificato.

È possibile impostare il criterio per tutti i gruppi, solo i gruppi selezionati o disattivarlo completamente selezionando **Nessuno.** Si noti che attualmente non è possibile avere criteri diversi per gruppi diversi.

![Screenshot delle impostazioni di scadenza dei gruppi in Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Funzionamento della scadenza con i criteri di conservazione

Se è stato configurato un criterio di conservazione per i gruppi nel Centro sicurezza e conformità, i criteri di scadenza funzionano senza problemi con i criteri di conservazione. Quando un gruppo scade, le conversazioni e i file delle cassette postali del gruppo nel sito del gruppo vengono conservati nel contenitore di conservazione per il numero specifico di giorni definito nel criterio di conservazione. Gli utenti non potranno tuttavia visualizzare il gruppo o il relativo contenuto dopo la scadenza.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Come e quando il proprietario di un gruppo apprende se i gruppi scadono

I proprietari del gruppo riceveranno una notifica solo tramite posta elettronica. Se il gruppo è stato creato tramite Planner, SharePoint o qualsiasi altra app, le notifiche di scadenza verranno sempre inviate tramite posta elettronica. Se il gruppo è stato creato tramite Teams, il proprietario del gruppo riceverà una notifica da rinnovare tramite la sezione attività. Non è consigliabile abilitare la scadenza per un gruppo se il proprietario del gruppo non dispone di un indirizzo di posta elettronica valido.

Trenta giorni prima della scadenza del gruppo, i proprietari del gruppo (o gli indirizzi di posta elettronica specificati per i gruppi che non dispongono di un proprietario) riceveranno un messaggio di posta elettronica che consente loro di rinnovare facilmente il gruppo. Se non lo rinnovano, riceveranno un altro messaggio di posta elettronica di rinnovo 15 giorni prima della scadenza. Se non lo hanno ancora rinnovato, riceveranno un'altra notifica tramite posta elettronica il giorno prima della scadenza.

Se per qualche motivo nessuno dei proprietari o degli amministratori rinnova il gruppo prima della scadenza, l'amministratore può comunque ripristinare il gruppo fino a 30 giorni dopo la scadenza. Per informazioni dettagliate, [vedere: Ripristinare un gruppo di Microsoft 365 eliminato.](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)

## <a name="archiving-group-contents"></a>Contenuto del gruppo di archiviazione

Se si dispone di un gruppo che non si prevede più di utilizzare, ma si desidera conservarne il contenuto, vedere [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) per informazioni su come esportare le informazioni dai diversi servizi di gruppi.

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Panoramica dei criteri di conservazione](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Assegnare un nuovo proprietario a un gruppo orfano](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configurare la scadenza dei gruppi di Microsoft 365](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)