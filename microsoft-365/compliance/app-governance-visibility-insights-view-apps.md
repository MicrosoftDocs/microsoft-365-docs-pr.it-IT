---
title: Visualizzare le app
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Visualizzare le app.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420131"
---
# <a name="view-your-apps"></a>Visualizzare le app

>*[Indicazioni sulle licenze di Microsoft 365 per la sicurezza e la conformità](https://aka.ms/ComplianceSD).*

La governance delle app Microsoft consente di ottenere rapidamente dati analitici approfonditi sulle app Microsoft 365 nel tenant. Ad esempio, è possibile visualizzare:

- Un elenco di app nel tenant abilitate per OAuth che usano l'API Microsoft Graph, oltre ai relativi metadati e dati di utilizzo.
- I dettagli delle app con dati analitici e informazioni approfondite selezionando un'app nell'elenco.

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>Ottenere un elenco di tutte le app del tenant

Per un riepilogo delle app nel tenant, passare a **Centro conformità Microsoft 365 > Protezione e governance delle app > App**.

![Pagina di riepilogo dell'app MAPG nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> L'account di accesso deve disporre di uno di [questi ruoli](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance delle app.
>

Verrà visualizzato un elenco di app e le informazioni seguenti:

- Nome dell’app
- Autore
- Certificazione delle app

  Indica se l'app è compatibile con le tecnologie Microsoft, conforme alle procedure consigliate per la sicurezza delle app cloud e supportata da Microsoft.

- Data ultima modifica

  Mostra la data in cui la governance dell'app è stata installata nel client e se tale data è più recente della data dell'ultima modifica dell'app.

- Data di installazione
- Livello di privilegio
- Numero di utenti
- Accesso ai dati

  Somma dei dati dell'app caricati e scaricati nel tenant nell'ultimo giorno, oltre alla modifica nel giorno precedente.

La governance delle app ordina l'elenco delle app in base al **nome dell'app** per impostazione predefinita. Per ordinare l'elenco in base a un altro attributo dell'app, selezionare il nome dell'attributo.

È anche possibile selezionare **Cerca** per cercare un'app in base al nome.

## <a name="getting-detailed-information-on-an-app"></a>Ottenere informazioni dettagliate su un'app

Per ottenere informazioni dettagliate su un'app specifica nel tenant, passare a **Centro conformità Microsoft 365 > Governance delle app >Pagina app > *nome app***.

![Riquadro dei dettagli dell'app di governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

Il riquadro dei dettagli dell'app fornisce informazioni aggiuntive nelle schede seguenti:

| Nome scheda | Descrizione |
|:-------|:-----|
| Dettagli | È possibile visualizzare dati aggiuntivi sull'app, ad esempio la data del primo consenso e l'ID dell'app. Per visualizzare le proprietà dell'app registrate in Azure AD, selezionare **Visualizza app in Azure AD**. |
| Utilizzo | È possibile visualizzare i dati a cui accede l'app nel tenant, tracciare l'utilizzo dei dati e mostrare l'utilizzo da parte degli \<x> utenti principali e degli utenti con [account prioritari](/microsoft-365/admin/setup/priority-accounts). |
| Utenti | È possibile visualizzare un elenco di utenti che usano l'app, se dispongono di un account prioritario e la quantità dei dati scaricati e caricati. |
| Autorizzazioni | È possibile visualizzare un riepilogo delle autorizzazioni concesse e usate dall'app, nonché l'elenco delle autorizzazioni specifiche. Per altre informazioni, vedere i [riferimenti delle autorizzazioni di Microsoft Graph](/graph/permissions-reference). |
|||

Per un'app abilitata, è disponibile anche un controllo **Disabilita app** per disabilitare l'uso dell'app selezionata e un controllo **Abilita app** per abilitare l'uso dell'app disabilitata. Queste azioni seguenti richiedono i seguenti [ruoli di amministratore](app-governance-get-started.md#administrator-roles):

- Amministratore di conformità
- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza

## <a name="next-step"></a>Passaggio successivo

[Determinare la postura di conformità generale dell'app](app-governance-visibility-insights-compliance-posture.md).
