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
description: Informazioni sui gruppi di Microsoft 365.
ms.openlocfilehash: 5d5c15c13d46738ac9de701b5a39f47274b9f1e5
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094734"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Panoramica dei gruppi di Microsoft 365 per gli amministratori

Gruppi di Microsoft 365 è il servizio di appartenenza di base che guida tutto il lavoro in team in Microsoft 365. Con i gruppi di Microsoft 365, è possibile concedere a un gruppo di persone l'accesso a una raccolta di risorse condivise. Queste risorse includono:

- Posta in arrivo di Outlook condivisa
- Calendario condiviso
- Una raccolta documenti di SharePoint
- A Planner
- Un blocco appunti di OneNote
- Power BI
- Yammer (se il gruppo è stato creato da Yammer)
- Un team (se il gruppo è stato creato da Teams)
- Roadmap (se si dispone di Project per il Web)

Con un gruppo di Microsoft 365, non è necessario assegnare manualmente le autorizzazioni a ognuna di queste risorse. L'aggiunta di persone al gruppo assegna automaticamente le autorizzazioni necessarie.

Qualsiasi utente può creare un gruppo a meno che non si limiti la creazione del gruppo [a un set specifico di persone.](manage-creation-of-groups.md) Se si limita la creazione di gruppi, gli utenti che non possono creare gruppi non potranno creare siti, planner o team di SharePoint. Questi servizi richiedono che gli utenti che li creano siano in grado di creare un gruppo. Gli utenti possono comunque partecipare ad attività di gruppo, ad esempio la creazione di attività in Planner o l'uso della chat di Teams, purché siano membri del gruppo.

I gruppi hanno i ruoli seguenti:

- **Proprietari:** i proprietari del gruppo possono aggiungere o rimuovere membri e disporre di autorizzazioni univoche, ad esempio la possibilità di eliminare conversazioni dalla posta in arrivo condivisa o modificare impostazioni diverse sul gruppo. I proprietari del gruppo possono rinominare il gruppo, aggiornare la descrizione o l'immagine e altro ancora.
- **Membri:** i membri possono accedere a tutti gli elementi del gruppo, ma non possono modificare le impostazioni del gruppo. Per impostazione predefinita, i membri del gruppo possono invitare guest a unirsi al gruppo, anche se è possibile [controllare questa impostazione.](manage-guest-access-in-groups.md)
- **Guest:** gli utenti guest del gruppo sono membri esterni all'organizzazione.

Solo gli amministratori globali, gli amministratori utente e i gruppi possono creare e gestire i gruppi nell'interfaccia di amministrazione di Microsoft 365. Non sono consentiti amministratori delegati, ad esempio consulenti con deleghe di amministratore per conto di altri.

Gli amministratori possono:

- [Specificare gli utenti che possono creare gruppi](manage-creation-of-groups.md)
- [Creare un criterio di denominazione per i gruppi nell'organizzazione](groups-naming-policy.md)
- [Scegliere il dominio da usare per la creazione di un gruppo](choose-domain-to-create-groups.md)
- [Gestire l'accesso guest ai gruppi](manage-guest-access-in-groups.md)
- [Recuperare un gruppo eliminato](restore-deleted-group.md) (entro 30 giorni dall'eliminazione)

Se si preferisce un modo più automatizzato per gestire il ciclo di vita dei gruppi di Microsoft 365, è possibile usare i criteri di scadenza per scadere i gruppi a un intervallo di tempo specifico. I proprietari del gruppo riceveranno un messaggio di posta elettronica 30, 15 e 1 giorno prima della scadenza del gruppo che consente loro di rinnovare il gruppo se è ancora necessario. Vedere: [Criteri di scadenza del gruppo di Microsoft 365.](office-365-groups-expiration-policy.md)

È possibile amministrare i gruppi dall'interfaccia di amministrazione di Microsoft 365 [o tramite PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

Se sono presenti molti utenti, ad esempio in un'azienda di grandi dimensioni, è possibile che molti utenti creino gruppi per vari scopi. Per le procedure consigliate, è consigliabile consultare Pianificare la governance nei gruppi di [Microsoft 365.](plan-for-groups-governance.md)

## <a name="group-limits"></a>Limiti relativi ai gruppi

I limiti seguenti si applicano ai gruppi di Microsoft 365:

|Massimo...|Valore|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Gruppi che un amministratore può creare|Fino al limite predefinito del tenant di 500 K|
|Numero di membri|Più di 1.000, anche se solo 1.000 possono accedere contemporaneamente alle conversazioni di gruppo. <br>Gli utenti potrebbero notare ritardi durante l'accesso al calendario e alle conversazioni in gruppi di grandi dimensioni in Outlook.|
|Numero di gruppi di cui un utente può essere membro|7,000|
|Archivio file|1 Terabyte + 10 GB per utente sottoscritto + qualsiasi altro spazio di archiviazione acquistato. È possibile acquistare una quantità illimitata di spazio di archiviazione aggiuntivo.|
|Dimensioni della cassetta postale del gruppo|50 GB|

Il numero massimo predefinito di gruppi di Microsoft 365 che un'organizzazione può avere è 500.000. Per superare il limite predefinito, è necessario contattare il supporto tecnico Microsoft. Per altre informazioni sui limiti dei gruppi di Microsoft 365, vedere Gruppi di [Microsoft 365 - Guida per gli amministratori.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

La gestione dei gruppi di Microsoft 365 è più efficace quando si dispone di informazioni utili sull'utilizzo dei gruppi. L'interfaccia di amministrazione di Microsoft 365 include uno strumento per la creazione di report che consente di visualizzare l'uso dello spazio di archiviazione, il numero di gruppi attivi e il modo in cui gli utenti usano i gruppi. Per altre [informazioni, vedere: Report di Microsoft 365 nell'interfaccia](../activity-reports/office-365-groups.md) di amministrazione.

## <a name="sensitivity-labels"></a>Etichette di riservatezza

È possibile creare etichette di riservatezza che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Microsoft 365. Con le etichette di riservatezza, è possibile configurare: 

- Privacy (pubblica o privata)
- Accesso di utenti esterni
- Accesso ai dispositivi non gestiti

Ad esempio, è possibile creare un'etichetta denominata *Estremamente* riservato e specificare che qualsiasi gruppo creato con questa etichetta sarà privato e non consentirà gli utenti esterni. Quando gli utenti dell'organizzazione selezionano questa etichetta durante la creazione del gruppo, il gruppo verrà impostato su privato e ai membri del gruppo non sarà consentito aggiungere utenti esterni al gruppo.

> [!IMPORTANT]
> Se attualmente si usano etichette di classificazione, non saranno più disponibili per gli utenti che creano gruppi dopo aver abilitato le etichette di riservatezza. 

Per informazioni sulla creazione, la gestione e l'uso delle etichette di riservatezza, vedere Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)e siti di SharePoint.

## <a name="which-microsoft-365-plans-include-groups"></a>Quali piani di Microsoft 365 includono i gruppi?

Qualsiasi abbonamento a Microsoft 365 con Exchange Online e SharePoint Online supporterà i gruppi. Sono inclusi i piani Business Essentials e Business Premium e i piani Enterprise E1, E3 ed E5. Il gruppo assume le licenze della persona che crea il gruppo (noto anche come "organizzatore" del gruppo). Finché l'organizzatore ha la licenza appropriata per tutte le funzionalità che vuoi che il gruppo abbia, tale licenza verrà comunicata al gruppo.

> [!NOTE]
> Per ulteriori informazioni sulle famiglie di servizi e i piani di Microsoft 365, vedere Opzioni dei piani di [Microsoft 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Se si dispone di un piano solo di Exchange, è comunque possibile ottenere la posta in arrivo condivisa e le funzionalità del calendario condiviso dei gruppi in Outlook, ma non si otterrà la raccolta documenti, Planner o altre funzionalità.

I gruppi di Microsoft 365 funzionano con Azure Active Directory. Le funzionalità dei gruppi disponibili dipendono dall'abbonamento ad Azure Active Directory di cui si dispone e dalle licenze assegnate all'organizzatore del gruppo.

> [!IMPORTANT]
> Per tutte le funzionalità dei gruppi, se hai una sottoscrizione ad Azure AD Premium, gli utenti possono aggiungersi al gruppo indipendentemente dal fatto che gli siano assegnate o meno una licenza AAD P1. Le licenze non vengono applicate.
> Periodicamente verranno generati report sull'utilizzo che segnalano quali utenti non hanno una licenza e ne occorre uno assegnato per essere conformi ai requisiti di licenza. Si supponga, ad esempio, che un utente non abbia una licenza e che sia stato aggiunto a un gruppo in cui vengono applicati i criteri di denominazione. Il report contrassegnerà l'utente che ha bisogno di una licenza.

## <a name="related-articles"></a>Articoli correlati

[Informazioni sui gruppi di Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Aggiornare le liste di distribuzione ai gruppi di Microsoft 365](../manage/upgrade-distribution-lists.md)

[Gestire i gruppi di Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Limiti di SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
