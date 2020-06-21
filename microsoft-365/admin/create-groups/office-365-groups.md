---
title: Panoramica dei gruppi di Microsoft 365 per gli amministratori
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni sui gruppi di Microsoft 365.
ms.openlocfilehash: 14bc1211aaa65fb2daeebdb22729fce10154f204
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780410"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Panoramica dei gruppi di Microsoft 365 per gli amministratori

Microsoft 365 groups è il servizio di appartenenza di base che guida tutto il lavoro di squadra in Microsoft 365. Con i gruppi di Microsoft 365, è possibile consentire a un gruppo di utenti di accedere a una raccolta di risorse di collaborazione per gli utenti da condividere. Tali risorse includono:

- Cartella posta in arrivo condivisa di Outlook
- Un calendario condiviso
- Una raccolta documenti di SharePoint
- Un pianificatore
- Un blocco appunti di OneNote
- Power BI
- Yammer (se il gruppo è stato creato da Yammer)
- Un team (se il gruppo è stato creato da Teams)
- Roadmap (se si dispone di un progetto per il Web)

Con un gruppo di Microsoft 365, non è necessario assegnare manualmente le autorizzazioni a ognuna di queste risorse, perché l'aggiunta di persone al gruppo dà automaticamente loro le autorizzazioni necessarie per gli strumenti forniti dal gruppo.

Qualsiasi utente può creare un gruppo, a meno che non si [limiti la creazione del gruppo a un insieme specifico di utenti](manage-creation-of-groups.md). Tenere presente che se si limita la creazione dei gruppi, gli utenti che non sono in grado di creare un gruppo non potranno creare siti, pianificatori o team di SharePoint. Questi servizi richiedono agli utenti di crearli per poter creare un gruppo. Gli utenti possono comunque partecipare alle attività di gruppo, ad esempio la creazione di attività in Planner o l'utilizzo di teams chat, purché siano membri del gruppo.

I gruppi dispongono dei ruoli seguenti:

- **Proprietari** -i proprietari del gruppo possono aggiungere o rimuovere membri e disporre di autorizzazioni univoche come la possibilità di eliminare le conversazioni dalla posta in arrivo condivisa o modificare diverse impostazioni relative al gruppo. I proprietari del gruppo possono rinominare il gruppo, aggiornare la descrizione o l'immagine e altro ancora.
- **Membri** -i membri possono accedere a tutto il gruppo, ma non possono modificare le impostazioni del gruppo. Per impostazione predefinita, i membri del gruppo possono invitare gli ospiti ad unirsi al gruppo, anche se è possibile [controllare tale impostazione](manage-guest-access-in-groups.md).
- **Gli ospiti** del gruppo sono membri provenienti dall'esterno dell'organizzazione.

Solo gli amministratori globali, gli amministratori degli utenti e i gruppi possono creare e gestire i gruppi nell'interfaccia di amministrazione di Microsoft 365. Non sono consentiti amministratori delegati, ad esempio consulenti con deleghe di amministratore per conto di altri.

In qualità di amministratore, è possibile:

- [Specificare gli utenti autorizzati a creare gruppi](manage-creation-of-groups.md)
- [Creare un criterio di denominazione per i gruppi nell'organizzazione](groups-naming-policy.md)
- [Scegliere il dominio da utilizzare per la creazione di un gruppo](choose-domain-to-create-groups.md)
- [Gestire l'accesso guest ai gruppi](manage-guest-access-in-groups.md)
- [Recuperare un gruppo eliminato](restore-deleted-group.md) (entro 30 giorni dall'eliminazione)

Se si preferisce un modo più automatico per gestire il ciclo di vita dei gruppi di Microsoft 365, è possibile utilizzare i criteri di scadenza per scadere i gruppi a un intervallo di tempo specifico. I proprietari del gruppo riceveranno un messaggio di posta elettronica di 30, 15 e 1 giorni prima della scadenza del gruppo che consente di rinnovare facilmente il gruppo, se necessario. Vedere: [criteri di scadenza del gruppo Microsoft 365](office-365-groups-expiration-policy.md).

È possibile amministrare i gruppi dall'interfaccia di amministrazione di Microsoft 365 o [tramite PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).

Se si dispone di un numero elevato di utenti, ad esempio in una società o un'organizzazione di grandi dimensioni, potrebbe essere necessario disporre di numerosi utenti che creano gruppi per diversi scopi. È consigliabile esaminare il [piano di governance nei gruppi Microsoft 365](plan-for-groups-governance.md) per le procedure consigliate.

## <a name="group-limits"></a>Limiti del gruppo

I limiti seguenti si applicano ai gruppi di Microsoft 365:

|Numero massimo di...|Valore|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Gruppi che un amministratore può creare|Fino al limite predefinito del tenant di 500K|
|Numero di membri|Più di 1.000, anche se solo 1.000 può accedere alle conversazioni di gruppo contemporaneamente. <br>Gli utenti possono notare ritardi durante l'accesso al calendario e le conversazioni in gruppi di grandi dimensioni in Outlook.|
|Numero di gruppi a cui un utente può essere membro|1.000|
|Archivio file|1 terabyte + 10 GB per utente sottoscritto + qualsiasi altro spazio di archiviazione acquistato. È possibile acquistare una quantità illimitata di spazio di archiviazione aggiuntivo.|
|Dimensione della cassetta postale del gruppo|50 GB|

Il numero massimo predefinito di gruppi di Microsoft 365 che un'organizzazione può avere è 500.000, ma può essere aumentato di una richiesta. Per ulteriori informazioni sui limiti relativi ai gruppi di Microsoft 365, vedere [gruppi di microsoft 365-Guida](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)per gli amministratori.

La gestione dei gruppi Microsoft 365 è più efficace quando si dispone di informazioni sull'utilizzo dei gruppi. Nell'interfaccia di amministrazione di Microsoft 365 è disponibile uno strumento per la creazione di report che consente di visualizzare elementi quali l'utilizzo dell'archiviazione, il numero di gruppi attivi e la modalità di utilizzo dei gruppi da parte degli utenti. Vedere: [Microsoft 365 segnalazioni nell'](../activity-reports/office-365-groups.md) interfaccia di amministrazione per ulteriori informazioni.

## <a name="sensitivity-labels"></a>Etichette di riservatezza

È possibile creare etichette di riservatezza che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Microsoft 365. Con le etichette di riservatezza, è possibile configurare: 

- Privacy (pubblico o privato)
- Accesso di utenti esterni
- Accesso ai dispositivi non gestiti

Ad esempio, è possibile creare un'etichetta denominata *altamente riservata* e specificare che qualsiasi gruppo creato con questa etichetta sarà privato e non consentirà agli utenti esterni. Quando gli utenti dell'organizzazione selezionano questa etichetta durante la creazione del gruppo, il gruppo verrà impostato su privato e ai membri del gruppo non verrà consentito di aggiungere utenti esterni al gruppo.

> [!IMPORTANT]
> Se attualmente si utilizzano le etichette di classificazione, non saranno più disponibili per gli utenti che creano gruppi una volta abilitate le etichette di riservatezza. 

Per informazioni sulla creazione, la gestione e l'utilizzo di etichette di riservatezza, vedere [use Sensitivity labels to protect content in Microsoft teams, microsoft 365 Groups e SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="which-microsoft-365-plans-include-groups"></a>Quali piani di Microsoft 365 includono gruppi?

Qualsiasi sottoscrizione Microsoft 365 con Exchange Online e SharePoint Online sosterrà i gruppi. Che include i piani Business Essentials e Business Premium e i piani Enterprise E1, E3 ed E5. Il gruppo assume la licenza della persona che crea il gruppo (noto anche come "Organizzatore" del gruppo). Se l'organizzatore dispone della licenza appropriata per tutte le funzionalità che si desidera che il gruppo abbia, la licenza verrà trasmessa al gruppo.

> [!NOTE]
> Per ulteriori informazioni sulle famiglie di servizi e sui piani di Microsoft 365, vedere [Opzioni di pianificazione di microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Se si dispone di un piano di Exchange, è comunque possibile ottenere la posta in arrivo condivisa e le caratteristiche del calendario condiviso di gruppi in Outlook, ma non si otterrà la raccolta documenti, planner o una qualsiasi delle altre funzionalità.

I gruppi Microsoft 365 sono compatibili con Azure Active Directory (AAD). Le funzionalità dei gruppi che si ottengono dipendono dalla sottoscrizione di Azure Active Directory e dalle licenze assegnate all'organizzatore del gruppo.

> [!IMPORTANT]
> Per tutte le funzionalità dei gruppi, se si dispone di un abbonamento a Azure AD Premium, gli utenti possono iscriversi al gruppo indipendentemente dal fatto che dispongano di una licenza AAD P1 assegnata. La gestione delle licenze non viene applicata.
> Verranno generati periodicamente rapporti di utilizzo che indicano gli utenti che non dispongono di una licenza e che devono essere assegnati a loro per essere conformi ai requisiti di licenza. Si supponga, ad esempio, che un utente non disponga di una licenza e che venga aggiunto a un gruppo in cui viene applicato il criterio di denominazione. Il report segnala che è necessaria una licenza.

## <a name="related-articles"></a>Articoli correlati

[Informazioni sui gruppi di Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Aggiornare le liste di distribuzione ai gruppi di Microsoft 365](../manage/upgrade-distribution-lists.md)

[Gestire i gruppi Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[Limiti di SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
