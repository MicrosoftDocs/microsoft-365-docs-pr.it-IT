---
title: Pianificare la governance dell'organizzazione e del ciclo di vita per gruppi Microsoft 365 e Microsoft Teams
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opzioni di Lean sulla governance del ciclo di vita per gli strumenti di collaborazione in Microsoft 365
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662677"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Pianificare la governance dell'organizzazione e del ciclo di vita per gruppi Microsoft 365 e Microsoft Teams

I gruppi di Microsoft 365 dispongono di un set completo di strumenti per implementare le funzionalità di governance richieste dall'organizzazione. 

Nella sezione seguente vengono descritte le funzionalità, vengono consigliate le procedure consigliate e vengono fornite indicazioni per porre le domande giuste per determinare i requisiti per la governance e come soddisfarli.

## <a name="control-who-can-create-microsoft-365-groups"></a>Controllare chi può creare gruppi di Microsoft 365

I gruppi possono essere creati dagli utenti finali provenienti da più punti finali, tra cui Outlook, SharePoint, teams e altri ambienti.

![immagine DESC](../media/04.png)

Si consiglia vivamente self-service per consentire ai proprietari del gruppo di aiutare gli utenti a svolgere il proprio lavoro in modo più semplice. La limitazione della creazione di gruppi e team può rallentare la produttività degli utenti perché molti servizi Microsoft 365 richiedono la creazione di gruppi per il servizio.

Si consideri le opzioni di governance seguenti per la creazione dei gruppi:

- Per limitare l'espansione del gruppo, utilizzare i [criteri di scadenza dei gruppi](microsoft-365-groups-expiration-policy.md) per eliminare automaticamente i gruppi che non vengono utilizzati.
- Limitare la creazione di gruppi ai membri di un gruppo di [sicurezza con appartenenza dinamica](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) contenente, ad esempio, tutti i dipendenti a tempo pieno.
- Limitare la creazione di gruppi a un gruppo di sicurezza e richiedere agli utenti di completare l'addestramento nei criteri di utilizzo dei gruppi dell'organizzazione per diventare membri del gruppo di sicurezza.

Se si desidera limitare gli utenti che possono creare i gruppi, vedere [gestire gli utenti autorizzati a creare i gruppi di Microsoft 365](manage-creation-of-groups.md) per informazioni su come configurarlo.

## <a name="group-delete-restore-and-archiving"></a>Eliminazione, ripristino e archiviazione di gruppi

Quando un gruppo di Microsoft 365 viene eliminato, per impostazione predefinita viene conservato per 30 giorni. Questo periodo di 30 giorni è definito di "eliminazione temporanea", perché è ancora possibile ripristinare il gruppo. Dopo 30 giorni, il gruppo e i contenuti associati vengono eliminati definitivamente e non possono essere ripristinati.

Se si dispone di criteri di conservazione sul posto per mantenere la chat, i file o la posta, tali elementi verranno mantenuti dopo l'eliminazione del gruppo. Per informazioni dettagliate, vedere informazioni [sui criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) .

Se si desidera eliminare un gruppo, ma conservare il contenuto di uno o più servizi connessi a un gruppo, vedere [Archive groups, teams e Yammer](end-life-cycle-groups-teams-sites-yammer.md) for Information.

## <a name="group-naming-policy"></a>Criteri di denominazione dei gruppi

I criteri di denominazione dei gruppi consentono di gestire i gruppi in due modi:

- È possibile utilizzare i criteri di denominazione prefisso/suffisso per applicare stringhe fisse o attributi di Azure AD all'inizio o alla fine del nome di un gruppo e dell'indirizzo di posta elettronica associato. In questo modo, è possibile garantire l'inclusione, ad esempio, di nomi di reparto o aree geografiche nei nomi dei gruppi.
- Un criterio di parole bloccate può garantire che alcune parole, ad esempio i nomi dei dirigenti, non vengano utilizzate nei nomi di gruppo.

I criteri di denominazione vengono applicati quando i gruppi vengono creati da tutti i servizi connessi al gruppo.

Se si decide di utilizzare i criteri di denominazione per i gruppi, vedere [criteri di denominazione dei gruppi Microsoft 365](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Criteri di scadenza del gruppo

È possibile specificare un periodo di scadenza e qualsiasi gruppo che raggiunge la fine di quel periodo e non viene rinnovato, verrà eliminato. Il periodo di scadenza inizia quando viene creato il gruppo oppure alla data in cui è stato rinnovato per ultimo.

Dopo aver impostato i gruppi in modo che scadano:
- I proprietari del gruppo ricevono una notifica per il rinnovo del gruppo come scadenza vicinanze.
- I gruppi attivi vengono rinnovati automaticamente.
- Qualsiasi gruppo che non è stato rinnovato viene eliminato.
- Qualsiasi gruppo eliminato può essere ripristinato entro 30 giorni dai proprietari del gruppo o dall'amministratore.

I criteri di scadenza rappresentano un ottimo metodo per limitare l'espansione del gruppo, garantendo che i gruppi che non sono più in uso vengano eliminati. Se si desidera creare un criterio di scadenza del gruppo, vedere [criteri di scadenza del gruppo Microsoft 365](microsoft-365-groups-expiration-policy.md).
