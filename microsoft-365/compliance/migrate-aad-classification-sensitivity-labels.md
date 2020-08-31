---
title: Etichette di classificazione e sensitivity di Azure Active Directory per i gruppi di Microsoft 365
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
description: In questo articolo vengono illustrate le etichette classiche di classificazione e sensibilità di Azure Active Directory.
ms.openlocfilehash: 38a3dbe727f3d0759d427944016ae98440f2686f
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308173"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Etichette di classificazione e sensitivity di Azure Active Directory per i gruppi di Microsoft 365

In questo articolo vengono illustrate le etichette classiche di classificazione e sensibilità di Azure Active Directory.

Le etichette di riservatezza sono supportate da [questi servizi](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels).

Per informazioni complete sulle etichette di riservatezza, vedere informazioni [sulle etichette di riservatezza](sensitivity-labels.md).

Per ulteriori informazioni sulle etichette di riservatezza e sul relativo comportamento per i siti e i gruppi di Microsoft 365, vedere [use Sensitivity labels to protect content in Microsoft teams, microsoft 365 Groups e SharePoint sites](sensitivity-labels-teams-groups-sites.md).

Per le procedure consigliate, vedere gli scenari seguenti per la migrazione dalla classificazione AAD classica alle etichette di riservatezza.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Scenario 1: tenant non ha mai usato classi di classificazione AAD o etichette di riservatezza per documenti e messaggi di posta elettronica

- L'amministratore tenant attiva le etichette di riservatezza per i gruppi impostando il flag tenant "EnableMIPLabels" su true tramite il cmdlet AAD PowerShell.
- L'amministratore tenant crea le etichette di riservatezza nel [centro conformità di Microsoft 365](https://compliance.microsoft.com).
    - L'amministratore tenant può scegliere azioni relative a file e messaggi di posta elettronica come la crittografia e la filigrana.
    - L'amministratore tenant può scegliere i gruppi Microsoft 365 e le azioni relative al sito di SharePoint Online per le etichette di riservatezza.
- L'amministratore del tenant pubblica il criterio.
- I **carichi di lavoro compatibili** mostrano le etichette di riservatezza. Utilizzare le etichette di riservatezza per creare gruppi. I carichi di lavoro compatibili sono i servizi che supportano le etichette di riservatezza.
- I **carichi di lavoro non compatibili** sono i servizi che non supportano ancora le etichette di riservatezza. I gruppi possono essere creati, tuttavia, non possono essere associati all'etichetta di riservatezza tramite carichi di lavoro non compatibili. Per associare tali gruppi a etichette di riservatezza, gli amministratori tenant possono eseguire i cmdlet di PowerShell.

Tabella 1. Comportamento dei carichi di lavoro compatibili e non compatibili – creare, modificare o eliminare gruppi

|Carico di lavoro|Quale elenco di etichette viene visualizzato dall'utente nella finestra di gruppo?|Creare un nuovo gruppo |Modifica gruppo |Eliminazione di un gruppo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibile   |etichette di riservatezza. |Nessuna modifica del comportamento. |Nessuna modifica del comportamento. |Nessuna modifica del comportamento. |
|Non compatibile |Non sono visibili etichette di riservatezza. |L'utente può creare un gruppo senza selezionare l'etichetta di riservatezza. <br><br> Si noti che l'amministratore può eseguire i cmdlet per applicare le etichette di riservatezza in background. |**Caso 1**: nessuna etichetta di riservatezza precedentemente selezionata. L'utente può modificare un gruppo.<br><br> **Caso 2**: etichetta di riservatezza applicata precedentemente in background utilizzando il cmdlet. L'utente può modificare un gruppo con esito positivo, escludendo il caso in cui l'utente seleziona la combinazione non valida di impostazione della privacy rispetto all'etichetta. |Nessuna modifica del comportamento.|

> [!NOTE]
> Nel caso di client desktop di Outlook (Win 32), dopo che l'amministratore ha abilitato le etichette di riservatezza sul tenant e il relativo utente si trova su una versione precedente del client desktop di Outlook (Win 32):
> - L'utente visualizza le etichette di riservatezza nella versione precedente del client desktop di Outlook.
> - Tuttavia, quando l'utente modifica un gruppo e salva il gruppo con un'etichetta di riservatezza, l'impostazione di privacy selezionata viene ignorata dall'impostazione di privacy dell'etichetta di riservatezza applicata.
> È consigliabile che gli utenti in una versione precedente di Outlook client vengano aggiornate alla versione più recente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Scenario 2: tenant utilizza già [classificazioni](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell) AAD classiche

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: tenant non ha mai utilizzato etichette di riservatezza per documenti e messaggi di posta elettronica

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com), è consigliabile creare etichette di riservatezza con lo stesso nome delle etichette di Azure ad esistenti classiche.
2. Utilizzare il cmdlet di PowerShell per applicare queste etichette di riservatezza ai gruppi Microsoft 365 e ai siti di SharePoint esistenti utilizzando il mapping dei nomi.
3. L'amministratore può scegliere di eliminare le etichette di Azure AD classiche:
    - I carichi di lavoro compatibili mostrano che queste etichette di riservatezza e i gruppi vengono creati con loro.
    - I carichi di lavoro non compatibili funzionano quando si creano gruppi, ma non è associata alcuna etichetta di riservatezza.
4. Gli amministratori possono eseguire i cmdlet di PowerShell per applicare etichette di riservatezza a questi gruppi senza etichette.
    - In alternativa, un amministratore può scegliere di mantenere le etichette di Azure AD classiche:
        - I carichi di lavoro compatibili mostrano queste etichette di riservatezza e i gruppi vengono creati con essi. I carichi di lavoro compatibili sono i servizi che supportano le etichette di riservatezza.
        - I carichi di lavoro non compatibili funzionano durante la creazione di gruppi e mostrano le etichette di Azure AD. Queste etichette di Azure AD classico sono associate a questi gruppi creati con carichi di lavoro non compatibili.
5. È consigliabile che gli amministratori eseguano i cmdlet di PowerShell per applicare etichette di riservatezza a questi gruppi con etichette di Azure AD.

Tabella 2. Comportamento dei carichi di lavoro compatibili e non compatibili – creare, modificare o eliminare gruppi

|Carico di lavoro|Quale elenco di etichette viene visualizzato dall'utente nella finestra di gruppo?|Creare un nuovo gruppo |Modifica gruppo |Eliminazione di un gruppo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibile   |etichette di riservatezza. |Nessuna modifica del comportamento. |Nessuna modifica del comportamento. |Nessuna modifica del comportamento. |
|Non compatibile |Vecchie etichette AAD classiche. |L'utente può creare un gruppo con l'etichetta di Azure AD classica selezionata. <br><br>Si noti che l'amministratore può eseguire i cmdlet per applicare le etichette di riservatezza in background. |**Caso 1**: nessuna etichetta di riservatezza precedentemente selezionata. L'utente può modificare un gruppo.<br><br> **Caso 2**: etichette AAD classiche precedentemente selezionate. L'utente può modificare un gruppo.<br><br> **Caso 3**: etichetta di riservatezza applicata in precedenza in background tramite il cmdlet. L'utente dovrebbe essere in grado di modificare un gruppo, escludendo un caso in cui l'utente seleziona la combinazione non valida di impostazione della privacy rispetto all'etichetta. |L'utente può eliminare un gruppo. |

> [!NOTE]
> Nel caso di client desktop di Outlook (Win 32), dopo che l'amministratore ha abilitato le etichette di riservatezza sul tenant e il relativo utente si trova su una versione precedente del client desktop di Outlook (Win 32):
> - L'utente visualizza le etichette di riservatezza nella versione precedente del client desktop di Outlook.
> - Tuttavia, quando l'utente modifica un gruppo e salva il gruppo con un'etichetta di riservatezza, l'impostazione di privacy selezionata viene ignorata dall'impostazione di privacy dell'etichetta di riservatezza applicata.
> È consigliabile che gli utenti in una versione precedente di Outlook client vengano aggiornate alla versione più recente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: etichette di riservatezza utilizzate dal tenant per documenti e messaggi di posta elettronica

1. Non appena l'amministratore abilita la caratteristica etichetta di riservatezza sul tenant impostando il contrassegno ' EnableMIPLabels ' del tenant su true, vengono visualizzate le etichette di riservatezza del documento e della posta elettronica nelle finestre di dialogo Creazione e modifica di gruppo/sito/team.
2. Un amministratore può utilizzare lo stesso documento e le etichette di riservatezza della posta elettronica per applicare la privacy e l'accesso degli utenti esterni sul gruppo/sito/team specificando le impostazioni di gruppo correlate:
    1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)selezionare la scheda **siti e gruppi** .
    2. Modificare un'etichetta di riservatezza del documento o della posta elettronica.

## <a name="sample-script"></a>Script di esempio

Per uno script di esempio per eseguire la migrazione di gruppi con etichette AAD classiche a etichette di riservatezza, vedere [Classic Azure ad Group Classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

