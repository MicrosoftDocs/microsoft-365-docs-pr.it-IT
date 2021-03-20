---
title: Pianificare la governance dell'organizzazione e del ciclo di vita per i gruppi di Microsoft 365 e Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informazioni sulle opzioni di governance del ciclo di vita per gli strumenti di collaborazione in Microsoft 365
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907929"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Pianificare la governance dell'organizzazione e del ciclo di vita per i gruppi di Microsoft 365 e Microsoft Teams

I gruppi di Microsoft 365 hanno un ricco set di strumenti per implementare le funzionalità di governance necessarie all'organizzazione. 

Nella sezione seguente vengono descritte le funzionalità, vengono consigliate le procedure consigliate e vengono fornite indicazioni per porre le domande giuste per determinare i requisiti per la governance e come soddisfarle.

## <a name="control-who-can-create-microsoft-365-groups"></a>Controllare chi può creare gruppi di Microsoft 365

I gruppi possono essere creati dagli utenti finali da più punti finali, tra cui Outlook, SharePoint, Teams e altri ambienti.

![image desc](../media/04.png)

Consigliamo vivamente il self-service per consentire ai proprietari dei gruppi di aiutare gli utenti a lavorare più facilmente. La limitazione della creazione di gruppi e team può rallentare la produttività degli utenti perché molti servizi di Microsoft 365 richiedono la creazione di gruppi per il funzionamento del servizio.

Considerare le opzioni di governance seguenti per la creazione di gruppi:

- Per limitare l'espansione dei gruppi, utilizzare i criteri di [scadenza dei](microsoft-365-groups-expiration-policy.md) gruppi per eliminare automaticamente i gruppi che non vengono utilizzati.
- Limitare la creazione di gruppi ai membri di un gruppo [di sicurezza con](/azure/active-directory/users-groups-roles/groups-create-rule) appartenenza dinamica contenente, ad esempio, tutti i dipendenti a tempo pieno.
- Limitare la creazione di gruppi a un gruppo di sicurezza e richiedere agli utenti di completare la formazione nei criteri di utilizzo dei gruppi dell'organizzazione per diventare membri del gruppo di sicurezza.

Se si desidera limitare gli utenti che possono creare gruppi, vedere Gestire chi può creare gruppi di [Microsoft 365](manage-creation-of-groups.md) per informazioni su come configurarlo.

## <a name="group-delete-restore-and-archiving"></a>Eliminazione, ripristino e archiviazione del gruppo

Quando un gruppo di Microsoft 365 viene eliminato, per impostazione predefinita viene conservato per 30 giorni. Questo periodo di 30 giorni è definito di "eliminazione temporanea", perché è ancora possibile ripristinare il gruppo. Dopo 30 giorni, il gruppo e i contenuti associati vengono eliminati definitivamente e non possono essere ripristinati.

Se sono stati applicati criteri di conservazione per conservare chat, file o posta elettronica, tali elementi verranno mantenuti dopo l'eliminazione del gruppo. Per [informazioni dettagliate, vedere](../compliance/retention.md) Informazioni sui criteri di conservazione.

Se si desidera eliminare un gruppo ma conservare il contenuto di uno o più servizi connessi al gruppo, vedere [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.

## <a name="group-naming-policy"></a>Criteri di denominazione dei gruppi

I criteri di denominazione dei gruppi consentono di gestire i gruppi in due modi:

- Un criterio di denominazione prefisso/suffisso può essere usato per applicare stringhe fisse o attributi di Azure AD all'inizio o alla fine del nome di un gruppo e dell'indirizzo di posta elettronica associato. In questo modo, è possibile garantire l'inclusione, ad esempio, di nomi di reparto o aree geografiche nei nomi dei gruppi.
- Un criterio di parole bloccate può garantire che determinate parole, ad esempio i nomi dei dirigenti, non siano utilizzate nei nomi dei gruppi.

I criteri di denominazione vengono applicati quando i gruppi vengono creati da uno dei servizi connessi al gruppo.

Se si decide di utilizzare i criteri di denominazione per i gruppi, vedere Criteri di denominazione dei gruppi di [Microsoft 365.](groups-naming-policy.md)

## <a name="group-expiration-policy"></a>Criteri di scadenza gruppo

È possibile specificare un periodo di scadenza e qualsiasi gruppo che raggiunge la fine di tale periodo e non viene rinnovato verrà eliminato. Il periodo di scadenza inizia quando il gruppo viene creato o alla data dell'ultimo rinnovo.

Dopo aver impostato i gruppi in modo che scada:
- Ai proprietari del gruppo viene notificato di rinnovare il gruppo quando si avvicina la scadenza.
- I gruppi attivi vengono rinnovati automaticamente.
- Tutti i gruppi non rinnovati vengono eliminati.
- Qualsiasi gruppo eliminato può essere ripristinato entro 30 giorni dai proprietari del gruppo o dall'amministratore.

I criteri di scadenza sono un buon modo per limitare l'espansione dei gruppi assicurando che i gruppi non più in uso siano eliminati. Se si desidera creare un criterio di scadenza del gruppo, vedere Criteri di scadenza gruppo [di Microsoft 365.](microsoft-365-groups-expiration-policy.md)

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)