---
title: Punteggio produttività Microsoft - Privacy
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Modalità di protezione della privacy con il punteggio di produttività.
ms.openlocfilehash: 5b5997532ddcd1fdf43b4124f8e2d8183bb3d89e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579171"
---
# <a name="privacy-controls-for-productivity-score"></a>Controlli della privacy per il punteggio di produttività

Il punteggio di produttività fornisce informazioni approfondite sul percorso di trasformazione digitale dell'organizzazione attraverso l'uso di Microsoft 365 e le esperienze tecnologiche che la supportano.  Il punteggio dell'organizzazione riflette le misurazioni delle persone e dell'esperienza tecnologica e può essere confrontato con i benchmark di organizzazioni simili al tuo. Per ulteriori dettagli, vedi panoramica [del punteggio di produttività.](productivity-score.md)

La privacy è importante per Microsoft. Per informazioni su come proteggiamo la tua privacy, vedi [l'informativa sulla privacy di Microsoft.](https://privacy.microsoft.com/privacystatement) Il punteggio di produttività consente all'amministratore IT dell'organizzazione di accedere alle impostazioni di privacy per assicurarsi che le informazioni sul punteggio di produttività visualizzate siano utilizzabili, senza compromettere l'attendibilità dell'organizzazione in Microsoft.

Nell'area esperienze utente, le metriche sono disponibili solo a livello di organizzazione. In quest'area viene illustrato il modo Microsoft 365 utenti esaminando le categorie di collaborazione dei contenuti, mobilità, riunioni, lavoro di team e comunicazione. Microsoft ti consente di utilizzare diversi livelli di controlli per soddisfare le tue esigenze di privacy interne.
I controlli offrono:

- Ruoli di amministratore flessibili per controllare chi può visualizzare le informazioni in Productivity Score.
- Possibilità di rifiutare esplicitamente l'area esperienze utente.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Ruoli di amministratore flessibili per controllare chi può visualizzare le informazioni in Productivity Score

Per visualizzare l'intero punteggio di produttività, è necessario essere uno dei ruoli di amministratore seguenti:

- Amministratore globale
- Amministratori di Exchange
- Amministratore di SharePoint
- Amministratore di Skype for Business
- Amministratore di Teams
- Lettore globale
- Amministratore che legge i report
- Amministratore che legge i report Riepilogo utilizzo

Assegnare il ruolo Lettore report o Lettore report di riepilogo utilizzo a chiunque sia responsabile della gestione e dell'adozione delle modifiche, ma non necessariamente un amministratore IT. Questo ruolo consente loro di accedere all'esperienza completa del punteggio di produttività nell Microsoft 365 intervana di amministrazione.

Il ruolo Lettore report di riepilogo utilizzo dovrà essere assegnato tramite i cmdlet di PowerShell finché non diventa assegnabile dall'interfaccia di amministrazione di Microsoft 365 più avanti nel 2020.

Per assegnare il ruolo Lettore report di riepilogo utilizzo con PowerShell:

- Eseguire powershell seguente:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>Possibilità di rifiutare esplicitamente le esperienze degli utenti

Puoi anche rifiutare esplicitamente l'area esperienze utente del punteggio di produttività. Se si rifiuta esplicitamente, nessuno dell'organizzazione sarà in grado di visualizzare queste metriche e l'organizzazione verrà rimossa da qualsiasi calcolo che implica comunicazioni, riunioni, lavoro in team, collaborazione sui contenuti e mobilità. Devi essere un amministratore globale per rifiutare esplicitamente all'organizzazione i report sulle esperienze degli utenti.

Per rifiutare esplicitamente:

1. Nell'interfaccia di amministrazione, andare a **Impostazioni**   >   **org Impostazioni** produttività  >  **.**
2. Deseleziona la casella Consenti l'uso Microsoft 365 dati di utilizzo per le **esperienze utente.** Per informazioni su come modificare le impostazioni di condivisione dei dati per Endpoint Analytics in Gestione configurazione Intune, selezionare **Altre informazioni.**
3. Selezionare  **Salva**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Pagina Impostazioni organizzazione in cui è possibile rifiutare esplicitamente le esperienze degli utenti.":::
