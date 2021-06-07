---
title: Panoramica dei gruppi di Microsoft 365 per gli amministratori
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Con Microsoft 365 gruppi, è possibile guidare il lavoro di team Microsoft 365 offrendo a un gruppo di persone l'accesso a una raccolta di risorse condivise.
ms.openlocfilehash: 69f7e47bcfb9e0704f8c373cf1addf98ef898cfa
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782394"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Panoramica dei gruppi di Microsoft 365 per gli amministratori

Microsoft 365 I gruppi sono il servizio di appartenenza di base che guida tutto il lavoro in team Microsoft 365. Con Microsoft 365, è possibile concedere a un gruppo di utenti l'accesso a una raccolta di risorse condivise. Queste risorse includono:

- Posta in arrivo Outlook condivisa
- Calendario condiviso
- Raccolta SharePoint documenti
- A Planner
- Un blocco appunti di OneNote
- Power BI
- Yammer (se il gruppo è stato creato da Yammer)
- Un team (se il gruppo è stato creato da Teams)
- Roadmap (se si dispone di Project per il Web)
- Stream

Con un Microsoft 365, non è necessario assegnare manualmente le autorizzazioni a ognuna di queste risorse. L'aggiunta automatica di persone al gruppo offre loro le autorizzazioni necessarie.

Qualsiasi utente può creare un gruppo a meno che non si limiti la creazione [del gruppo a un set specifico di persone.](../../solutions/manage-creation-of-groups.md) Se si limita la creazione di gruppi, gli utenti che non possono creare gruppi non potranno creare siti di SharePoint, planner, team, calendari di gruppi di Outlook, gruppi di flusso, gruppi di Yammer, raccolte condivise in OneDrive o aree di lavoro Power BI condivise. Questi servizi richiedono che gli utenti che li creano siano in grado di creare un gruppo. Gli utenti possono comunque partecipare ad attività di gruppo, ad esempio la creazione di attività in Planner o Teams chat, purché siano membri del gruppo.

I gruppi hanno i ruoli seguenti:

- **Proprietari:** i proprietari del gruppo possono aggiungere o rimuovere membri e disporre di autorizzazioni univoche, ad esempio la possibilità di eliminare conversazioni dalla posta in arrivo condivisa o di modificare impostazioni diverse sul gruppo. I proprietari dei gruppi possono rinominare il gruppo, aggiornare la descrizione o l'immagine e altro ancora.
- **Membri:** i membri possono accedere a tutti gli elementi del gruppo, ma non possono modificare le impostazioni del gruppo. Per impostazione predefinita, i membri del gruppo possono invitare gli utenti guest a partecipare al gruppo, anche se è possibile [controllare tale impostazione.](manage-guest-access-in-groups.md)
- **Guest:** gli utenti guest del gruppo sono membri esterni all'organizzazione.

Solo gli amministratori globali, gli amministratori utente e i gruppi gli amministratori possono creare e gestire i gruppi nell'Microsoft 365 di amministrazione. Non sono consentiti amministratori delegati, ad esempio consulenti con deleghe di amministratore per conto di altri.

Gli amministratori possono:

- [Specificare chi può creare gruppi](../../solutions/manage-creation-of-groups.md)
- [Creare criteri di denominazione per i gruppi nell'organizzazione](../../solutions/groups-naming-policy.md)
- [Scegliere il dominio da utilizzare per la creazione di un gruppo](../../solutions/choose-domain-to-create-groups.md)
- [Gestire l'accesso guest ai gruppi](manage-guest-access-in-groups.md)
- [Ripristinare un gruppo eliminato](restore-deleted-group.md) (entro 30 giorni dall'eliminazione)

Se si preferisce un modo più automatizzato per gestire il ciclo di vita dei gruppi di Microsoft 365, è possibile utilizzare i criteri di scadenza per scadere i gruppi a un intervallo di tempo specifico. I proprietari del gruppo riceveranno un messaggio di posta elettronica 30, 15 e 1 giorno prima della scadenza del gruppo che consente loro di rinnovare il gruppo se è ancora necessario. Vedere: Microsoft 365 [criteri di scadenza del gruppo](../../solutions/microsoft-365-groups-expiration-policy.md).

È possibile amministrare i gruppi dall'Microsoft 365 di amministrazione o [tramite PowerShell.](../../enterprise/manage-microsoft-365-groups-with-powershell.md)

Se si dispone di molti utenti, ad esempio in una grande azienda o in un'azienda, è possibile che molti utenti creino gruppi per vari scopi. È consigliabile consultare [Plan for governance in Microsoft 365 groups](../../solutions/collaboration-governance-overview.md) for best practices.

## <a name="group-limits"></a>Limiti di gruppo

I limiti seguenti si applicano Microsoft 365 gruppi:

|Massimo...|Valore|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Gruppi che un amministratore può creare|Fino al limite predefinito del tenant di 500 K|
|Numero di membri|Più di 1.000, anche se solo 1.000 possono accedere contemporaneamente alle conversazioni di gruppo. <br>Gli utenti potrebbero notare ritardi durante l'accesso al calendario e alle conversazioni in gruppi di grandi dimensioni in Outlook.|
|Numero di gruppi di cui un utente può essere membro|7,000|
|Archivio file|1 Terabyte + 10 GB per utente sottoscritto + qualsiasi altro spazio di archiviazione acquistato. È possibile acquistare una quantità illimitata di spazio di archiviazione aggiuntivo.|
|Dimensioni cassetta postale di gruppo|50 GB|

Il numero massimo predefinito di Microsoft 365 che un'organizzazione può avere è 500.000. Per superare il limite predefinito, è necessario contattare il supporto tecnico Microsoft. Per ulteriori informazioni sui limiti Microsoft 365 gruppi, vedere Microsoft 365 [Groups - Guida per gli amministratori.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

La gestione dei Microsoft 365 è più efficace quando si dispone di informazioni utili sull'utilizzo dei gruppi. L'Microsoft 365 di amministrazione dispone di uno strumento di creazione di report che consente di visualizzare l'uso dello spazio di archiviazione, il numero di gruppi attivi e il modo in cui gli utenti usano i gruppi. Vedi: [Microsoft 365 report nell'interfaccia di amministrazione](../activity-reports/office-365-groups.md) per altre informazioni.

## <a name="sensitivity-labels"></a>Etichette di riservatezza

È possibile creare etichette di riservatezza che gli utenti dell'organizzazione possono impostare quando creano un Microsoft 365 gruppo. Con le etichette di riservatezza, è possibile configurare: 

- Privacy (pubblica o privata)
- Accesso di utenti esterni
- Accesso al dispositivo non gestito

Ad esempio, è possibile creare un'etichetta denominata *Estremamente* riservato e specificare che qualsiasi gruppo creato con questa etichetta sarà privato e non consentirà agli utenti esterni. Quando gli utenti dell'organizzazione selezionano questa etichetta durante la creazione del gruppo, il gruppo verrà impostato su privato e ai membri del gruppo non sarà consentito aggiungere utenti esterni al gruppo.

> [!IMPORTANT]
> Se attualmente si utilizzano etichette di classificazione, non saranno più disponibili per gli utenti che creano gruppi dopo aver abilitato le etichette di riservatezza. 

Per informazioni sulla creazione, la gestione e l'utilizzo delle etichette di riservatezza, vedere Use [sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../../compliance/sensitivity-labels-teams-groups-sites.md).

## <a name="which-microsoft-365-plans-include-groups"></a>Quali Microsoft 365 includono i gruppi?

Qualsiasi Microsoft 365 che dispone di Exchange Online e SharePoint Online supporterà i gruppi. Sono inclusi i piani di Premium Business Essentials e Business e i piani Enterprise E1, E3 ed E5. Il gruppo accetta le licenze della persona che crea il gruppo (noto anche come "organizzatore" del gruppo). Se l'organizzatore ha la licenza appropriata per tutte le funzionalità che si desidera che il gruppo abbia, tale licenza verrà comunicata al gruppo.

> [!NOTE]
> Per ulteriori informazioni sulle Microsoft 365 e sui piani di servizio, vedere Microsoft 365 [opzioni del piano.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Se si dispone di un piano solo Exchange, è comunque possibile ottenere la posta in arrivo condivisa e le caratteristiche di calendario condivise dei gruppi in Outlook ma non si otterrà la raccolta documenti, Planner o qualsiasi altra funzionalità.

Microsoft 365 gruppi funzionano con Azure Active Directory. Le funzionalità dei gruppi disponibili dipendono dall Azure Active Directory di sottoscrizione e dalle licenze assegnate all'organizzatore del gruppo.

> [!IMPORTANT]
> Per tutte le funzionalità dei gruppi, se si dispone di una sottoscrizione di Azure AD Premium, gli utenti possono partecipare al gruppo indipendentemente dal fatto che gli sia assegnata o meno una licenza AAD P1. Le licenze non vengono applicate.
> Periodicamente verranno generati report sull'utilizzo che segnalano quali utenti mancano di una licenza e ne è necessaria una assegnata per essere conforme ai requisiti di licenza. Si supponga ad esempio che un utente non abbia una licenza e che sia stato aggiunto a un gruppo in cui viene applicato il criterio di denominazione. Il report contrassegnerà per l'utente la necessità di una licenza.

## <a name="related-content"></a>Contenuto correlato

[Informazioni sui Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (articolo)\
[Aggiornare le liste di distribuzione Microsoft 365 gruppi](../manage/upgrade-distribution-lists.md) (articolo)\
[Gestire Microsoft 365 gruppi con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (articolo)\
[SharePoint Online Limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (articolo)\
[Organizzare gruppi e canali in Microsoft Stream](/stream/groups-channels-organization) (articolo)
