---
title: Etichette di classificazione e riservatezza di Azure Active Directory per i gruppi di Microsoft 365
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: In questo articolo vengono illustrate le etichette classiche di classificazione e riservatezza di Azure Active Directory.
ms.openlocfilehash: 2506e7f467a485878f1e26a23ee1071907b41614
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545660"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Etichette di classificazione e riservatezza di Azure Active Directory per i gruppi di Microsoft 365

In questo articolo vengono illustrate le etichette classiche di classificazione e riservatezza di Azure Active Directory.

Le etichette di riservatezza sono supportate [da questi servizi.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)

Per informazioni complete sulle etichette di riservatezza, vedere [Informazioni sulle etichette di riservatezza.](sensitivity-labels.md)

Per ulteriori informazioni sulle etichette di riservatezza e sul relativo comportamento per i siti e i gruppi di Microsoft 365, vedere Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di [Microsoft 365](sensitivity-labels-teams-groups-sites.md)e siti di SharePoint.

Per le procedure consigliate per la migrazione dalla classificazione AAD classica alle etichette di riservatezza, vedere gli scenari seguenti.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Scenario 1: Il tenant non ha mai usato classificazioni AAD classiche o etichette di riservatezza per documenti e messaggi di posta elettronica

- L'amministratore tenant abilita le etichette di riservatezza per i gruppi impostando il flag tenant "EnableMIPLabels" su true tramite il cmdlet di PowerShell di AAD.
- L'amministratore tenant crea le etichette di riservatezza nel Centro conformità [Microsoft 365.](https://compliance.microsoft.com)
    - L'amministratore tenant può scegliere azioni relative a file e posta elettronica come crittografia e filigrana.
    - L'amministratore tenant può scegliere gruppi di Microsoft 365 e azioni correlate al sito di SharePoint Online per le etichette di riservatezza.
- L'amministratore tenant pubblica il criterio.
- **I carichi di lavoro compatibili** mostrano etichette di riservatezza. Usare le etichette di riservatezza per creare gruppi. I carichi di lavoro compatibili sono i servizi che supportano le etichette di riservatezza.
- **I carichi di lavoro non compatibili** sono i servizi che non supportano ancora le etichette di riservatezza. I gruppi possono essere creati, tuttavia, non possono essere associati all'etichetta di riservatezza tramite carichi di lavoro non compatibili. Per associare tali gruppi alle etichette di riservatezza, gli amministratori tenant possono eseguire cmdlet di PowerShell.

Tabella 1. Comportamento dei carichi di lavoro compatibili e non compatibili: creare, modificare o eliminare gruppi

|Carico di lavoro|Quale elenco di etichette viene visualizzato dall'utente nella finestra di gruppo?|Creare un nuovo gruppo |Modifica gruppo |Eliminazione di un gruppo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibile   |etichette di riservatezza. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |
|Non compatibile |Nessuna etichetta di riservatezza visibile. |L'utente può creare un gruppo senza selezionare l'etichetta di riservatezza. <br><br> Nota: l'amministratore può eseguire cmdlet per applicare etichette di riservatezza in background. |**Caso 1:** nessuna etichetta di riservatezza selezionata in precedenza. L'utente può modificare un gruppo.<br><br> **Caso 2:** etichetta di riservatezza applicata in precedenza in background utilizzando il cmdlet. L'utente può modificare correttamente un gruppo, escluso il caso in cui l'utente seleziona una combinazione non valida di impostazioni di privacy rispetto all'etichetta. |Nessun cambiamento di comportamento.|

> [!NOTE]
> Nel caso del client desktop di Outlook (Win 32), dopo che l'amministratore abilita le etichette di riservatezza nel tenant e l'utente si trova in una versione precedente del client desktop di Outlook (Win 32):
>
> - L'utente visualizza le etichette di riservatezza nella versione precedente del client desktop di Outlook.
> - Tuttavia, quando l'utente modifica un gruppo e lo salva con un'etichetta di riservatezza, l'impostazione di privacy selezionata viene ignorata dall'impostazione di privacy dell'etichetta di riservatezza applicata.
>
> Si consiglia agli utenti di una versione precedente del client Outlook di eseguire l'aggiornamento alla versione più recente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Scenario 2: il tenant usa già le classificazioni AAD [classiche](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: Il tenant non ha mai usato etichette di riservatezza per documenti e messaggi di posta elettronica

1. Nel Centro [conformità Microsoft 365,](https://compliance.microsoft.com)è consigliabile creare etichette di riservatezza con lo stesso nome delle etichette di Azure AD classiche esistenti.
2. Utilizzare il cmdlet di PowerShell per applicare queste etichette di riservatezza ai gruppi di Microsoft 365 e ai siti di SharePoint esistenti utilizzando il mapping dei nomi.
3. L'amministratore può scegliere di eliminare le etichette classiche di Azure AD:
    - I carichi di lavoro compatibili mostrano che queste etichette di riservatezza e i gruppi vengono creati con loro.
    - I carichi di lavoro non compatibili funzionano durante la creazione dei gruppi, ma non vi è associata alcuna etichetta di riservatezza.
4. Gli amministratori possono eseguire cmdlet di PowerShell per applicare etichette di riservatezza a questi gruppi senza etichette.
    - In alternativa, un amministratore può scegliere di mantenere le etichette classiche di Azure AD:
        - I carichi di lavoro compatibili mostrano queste etichette di riservatezza e i gruppi vengono creati con loro. I carichi di lavoro compatibili sono i servizi che supportano le etichette di riservatezza.
        - I carichi di lavoro non compatibili funzionano durante la creazione di gruppi e mostrano le etichette classiche di Azure AD. Queste etichette classiche di Azure AD sono associate a questi gruppi creati con carichi di lavoro non compatibili.
5. Si consiglia vivamente agli amministratori di eseguire cmdlet di PowerShell per applicare etichette di riservatezza a questi gruppi con etichette classiche di Azure AD.

Tabella 2. Comportamento dei carichi di lavoro compatibili e non compatibili: creare, modificare o eliminare gruppi

|Carico di lavoro|Quale elenco di etichette viene visualizzato dall'utente nella finestra di gruppo?|Creare un nuovo gruppo |Modifica gruppo |Eliminazione di un gruppo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibile   |etichette di riservatezza. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |Nessun cambiamento di comportamento. |
|Non compatibile |Etichette AAD classiche. |L'utente può creare un gruppo con l'etichetta di Azure AD classica selezionata. <br><br>Nota: l'amministratore può eseguire cmdlet per applicare etichette di riservatezza in background. |**Caso 1:** nessuna etichetta di riservatezza selezionata in precedenza. L'utente può modificare un gruppo.<br><br> **Caso 2:** etichette AAD classiche precedentemente selezionate. L'utente può modificare un gruppo.<br><br> **Caso 3:** etichetta di riservatezza applicata in precedenza in background utilizzando il cmdlet. L'utente deve essere in grado di modificare un gruppo, ad eccezione di un caso in cui l'utente seleziona una combinazione non valida di impostazioni di privacy rispetto all'etichetta. |L'utente può eliminare un gruppo. |

> [!NOTE]
> Nel caso del client desktop di Outlook (Win 32), dopo che l'amministratore abilita le etichette di riservatezza nel tenant e l'utente si trova in una versione precedente del client desktop di Outlook (Win 32):
>
> - L'utente visualizza le etichette di riservatezza nella versione precedente del client desktop di Outlook.
> - Tuttavia, quando l'utente modifica un gruppo e lo salva con un'etichetta di riservatezza, l'impostazione di privacy selezionata viene ignorata dall'impostazione di privacy dell'etichetta di riservatezza applicata.
>
> Si consiglia agli utenti di una versione precedente del client Outlook di eseguire l'aggiornamento alla versione più recente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: Il tenant ha usato etichette di riservatezza per documenti e messaggi di posta elettronica

1. Non appena l'amministratore abilita la funzionalità delle etichette di riservatezza nel tenant impostando il contrassegno del tenant "EnableMIPLabels" su true, vengono visualizzate le etichette di riservatezza del documento e della posta elettronica nelle finestre di dialogo di creazione e modifica di gruppo/sito/team.
2. Un amministratore può usare gli stessi documenti e le stesse etichette di riservatezza della posta elettronica per applicare la privacy e l'accesso degli utenti esterni nel gruppo/sito/team specificando le impostazioni di gruppo correlate:
    1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)selezionare la **scheda Siti e** gruppi.
    2. Modificare un documento o un'etichetta di riservatezza tramite posta elettronica.

## <a name="sample-script"></a>Script di esempio

Per uno script di esempio per eseguire la migrazione di gruppi con etichette AAD classiche alle etichette di riservatezza, vedere Classificazione dei gruppi di [Azure AD classica.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)
