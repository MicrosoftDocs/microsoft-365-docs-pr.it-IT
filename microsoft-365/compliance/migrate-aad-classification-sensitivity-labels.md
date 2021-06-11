---
title: Azure Active Directory di classificazione e riservatezza per Microsoft 365 gruppi
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: In questo articolo vengono illustrate le etichette classiche Azure Active Directory classificazione e riservatezza.
ms.openlocfilehash: 07bc09afb3e490961a8cc5a88857ec49dd962856
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221751"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Azure Active Directory di classificazione e riservatezza per Microsoft 365 gruppi

In questo articolo vengono illustrate le etichette classiche Azure Active Directory classificazione e riservatezza.

Le etichette di riservatezza sono supportate [da questi servizi.](./sensitivity-labels-teams-groups-sites.md)

Per informazioni complete sulle etichette di riservatezza, vedi [Informazioni sulle etichette di riservatezza.](sensitivity-labels.md)

Per ulteriori informazioni sulle etichette di riservatezza e sul relativo comportamento per siti e gruppi di Microsoft 365, vedere Usare etichette di riservatezza per proteggere il contenuto [in Microsoft Teams, gruppi di Microsoft 365](sensitivity-labels-teams-groups-sites.md)e siti SharePoint .

Per le procedure consigliate per la migrazione dalla classificazione AAD classica alle etichette di riservatezza, vedere gli scenari seguenti.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Scenario 1: il tenant non ha mai usato classificazioni AAD classiche o etichette di riservatezza per documenti e messaggi di posta elettronica

- L'amministratore tenant abilita le etichette di riservatezza per i gruppi impostando il flag tenant "EnableMIPLabels" su true tramite il cmdlet di powershell AAD.
- L'amministratore tenant crea le etichette di riservatezza nel [centro Microsoft 365 conformità.](https://compliance.microsoft.com)
    - L'amministratore tenant può scegliere azioni relative a file e posta elettronica come crittografia e filigrana.
    - L'amministratore tenant può scegliere Microsoft 365 gruppi e SharePoint azioni correlate al sito online per le etichette di riservatezza.
- L'amministratore tenant pubblica il criterio.
- **I carichi di lavoro compatibili** mostrano etichette di riservatezza. Utilizzare le etichette di riservatezza per creare gruppi. I carichi di lavoro compatibili sono i servizi che supportano le etichette di riservatezza.
- **I carichi di lavoro non compatibili** sono i servizi che non supportano ancora le etichette di riservatezza. I gruppi possono essere creati, tuttavia, non possono essere associati all'etichetta di riservatezza tramite carichi di lavoro non compatibili. Per associare tali gruppi alle etichette di riservatezza, gli amministratori tenant possono eseguire cmdlet di PowerShell.

Tabella 1. Comportamento dei carichi di lavoro compatibili e non compatibili: creare, modificare o eliminare gruppi

|Carico di lavoro|Quale elenco di etichette viene visualizzato dall'utente nella finestra di gruppo?|Creare un nuovo gruppo |Modifica gruppo |Eliminazione di un gruppo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibile   |etichette di riservatezza. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |
|Non compatibile |Nessuna etichetta di riservatezza visibile. |L'utente può creare un gruppo senza selezionare l'etichetta di riservatezza. <br><br> Nota, l'amministratore può eseguire cmdlet per applicare etichette di riservatezza in background. |**Caso 1:** nessuna etichetta di riservatezza selezionata in precedenza. L'utente può modificare un gruppo.<br><br> **Caso 2:** etichetta di riservatezza applicata in precedenza in background utilizzando il cmdlet. L'utente può modificare correttamente un gruppo, escludendo il caso in cui l'utente seleziona una combinazione non valida di impostazioni di privacy rispetto all'etichetta. |Nessun cambiamento di comportamento.|

> [!NOTE]
> Nel caso di un client desktop Outlook (Win 32), dopo che l'amministratore abilita le etichette di riservatezza nel tenant e l'utente si trova in una versione precedente del client desktop Outlook (Win 32):
>
> - L'utente visualizza le etichette di riservatezza nella versione precedente del client Outlook desktop.
> - Tuttavia, quando l'utente modifica un gruppo e salva il gruppo con un'etichetta di riservatezza, l'impostazione di privacy selezionata viene ignorata dall'impostazione di privacy dell'etichetta di riservatezza applicata.
>
> È consigliabile che gli utenti in una versione precedente di Outlook client l'aggiornamento alla versione più recente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Scenario 2: il tenant usa già classificazioni AAD [classiche](../enterprise/manage-microsoft-365-groups-with-powershell.md)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: Il tenant non ha mai usato etichette di riservatezza per documenti e messaggi di posta elettronica

1. Nel Centro [Microsoft 365 conformità](https://compliance.microsoft.com)è consigliabile creare etichette di riservatezza con lo stesso nome delle etichette di Azure AD classiche esistenti.
2. Utilizzare il cmdlet PowerShell per applicare queste etichette di riservatezza ai gruppi Microsoft 365 esistenti e SharePoint siti utilizzando il mapping dei nomi.
3. L'amministratore può scegliere di eliminare le etichette classiche di Azure AD:
    - I carichi di lavoro compatibili mostrano queste etichette di riservatezza e i gruppi vengono creati con loro.
    - I carichi di lavoro non compatibili funzionano durante la creazione di gruppi, ma ad essi non è associata alcuna etichetta di riservatezza.
4. Gli amministratori possono eseguire cmdlet di PowerShell per applicare etichette di riservatezza a questi gruppi senza etichette.
    - In alternativa, un amministratore può scegliere di mantenere le etichette classiche di Azure AD:
        - I carichi di lavoro compatibili mostrano queste etichette di riservatezza e i gruppi vengono creati con esse. I carichi di lavoro compatibili sono i servizi che supportano le etichette di riservatezza.
        - I carichi di lavoro non compatibili funzionano durante la creazione di gruppi e mostrano le etichette classiche di Azure AD. Queste etichette classiche di Azure AD sono associate a questi gruppi creati con carichi di lavoro non compatibili.
5. Si consiglia vivamente agli amministratori di eseguire cmdlet di PowerShell per applicare etichette di riservatezza a questi gruppi con etichette classiche di Azure AD.

Tabella 2. Comportamento dei carichi di lavoro compatibili e non compatibili: creare, modificare o eliminare gruppi

|Carico di lavoro|Quale elenco di etichette viene visualizzato dall'utente nella finestra di gruppo?|Creare un nuovo gruppo |Modifica gruppo |Eliminazione di un gruppo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibile   |etichette di riservatezza. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |
|Non compatibile |Etichette AAD classiche vecchie. |L'utente può creare un gruppo con l'etichetta classica di Azure AD selezionata. <br><br>Nota, l'amministratore può eseguire cmdlet per applicare etichette di riservatezza in background. |**Caso 1:** nessuna etichetta di riservatezza selezionata in precedenza. L'utente può modificare un gruppo.<br><br> **Caso 2:** etichette AAD classiche precedentemente selezionate. L'utente può modificare un gruppo.<br><br> **Caso 3:** etichetta di riservatezza applicata in precedenza in background utilizzando il cmdlet. L'utente deve essere in grado di modificare un gruppo, escludendo un caso in cui l'utente seleziona una combinazione non valida di impostazioni di privacy rispetto all'etichetta. |L'utente può eliminare un gruppo. |

> [!NOTE]
> Nel caso di un client desktop Outlook (Win 32), dopo che l'amministratore abilita le etichette di riservatezza nel tenant e l'utente si trova in una versione precedente del client desktop Outlook (Win 32):
>
> - L'utente visualizza le etichette di riservatezza nella versione precedente del client Outlook desktop.
> - Tuttavia, quando l'utente modifica un gruppo e salva il gruppo con un'etichetta di riservatezza, l'impostazione di privacy selezionata viene ignorata dall'impostazione di privacy dell'etichetta di riservatezza applicata.
>
> È consigliabile che gli utenti in una versione precedente di Outlook client l'aggiornamento alla versione più recente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: il tenant ha usato etichette di riservatezza per documenti e messaggi di posta elettronica

1. Non appena l'amministratore abilita la funzionalità dell'etichetta di riservatezza nel tenant impostando il flag del tenant "EnableMIPLabels" su true, vengono visualizzate le etichette di riservatezza del documento e della posta elettronica nelle finestre di dialogo di creazione e modifica del gruppo/sito/team.
2. Un amministratore può usare lo stesso documento e le stesse etichette di riservatezza della posta elettronica per applicare la privacy e l'accesso degli utenti esterni al gruppo/sito/team specificando le impostazioni di gruppo correlate:
    1. Nel Centro [Microsoft 365 conformità](https://compliance.microsoft.com)selezionare la scheda **Siti e** gruppi.
    2. Modificare un documento o un'etichetta di riservatezza della posta elettronica.

## <a name="sample-script"></a>Script di esempio

Per uno script di esempio per eseguire la migrazione di gruppi con etichette AAD classiche alle etichette di riservatezza, vedere Classificazione classica dei gruppi [di Azure AD.](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification)