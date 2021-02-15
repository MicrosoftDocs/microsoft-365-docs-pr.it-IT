---
title: Microsoft Productivity Score - Privacy
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: In che modo la privacy è protetta con il punteggio di produttività.
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604327"
---
# <a name="privacy-controls-for-productivity-score"></a>Controlli della privacy per il punteggio di produttività

Il punteggio di produttività fornisce informazioni dettagliate sul percorso di trasformazione digitale dell'organizzazione attraverso l'uso di Microsoft 365 e le esperienze tecnologiche che lo supportano.  Il punteggio dell'organizzazione riflette le misurazioni delle persone e dell'esperienza tecnologica e può essere confrontato con i benchmark di organizzazioni simili al tuo. Per altri dettagli, vedi la panoramica [del punteggio di produttività.](productivity-score.md)

La privacy dell'utente è importante per Microsoft. Per informazioni su come microsoft protegge la privacy dell'utente, vedere [l'informativa sulla privacy di Microsoft.](https://privacy.microsoft.com/privacystatement) Punteggio di produttività consente all'amministratore IT dell'organizzazione di accedere alle impostazioni di privacy per assicurarsi che tutte le informazioni sul punteggio di produttività visualizzate siano utilizzabili, senza compromettere la fiducia dell'organizzazione in Microsoft.

Nell'area delle esperienze utente, le metriche sono disponibili solo a livello di organizzazione. In quest'area viene illustrato come gli utenti usano Microsoft 365 esaminando le categorie di collaborazione sui contenuti, mobilità, riunioni, lavoro in team e comunicazione. Microsoft ti consente di utilizzare diversi livelli di controlli per aiutarti a soddisfare le tue esigenze di informativa sulla privacy interna.
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

Assegnare il ruolo Lettore report o Lettore report di riepilogo utilizzo a chiunque sia responsabile della gestione e dell'adozione delle modifiche, ma non necessariamente un amministratore IT. Questo ruolo consente loro di accedere all'esperienza del punteggio di produttività completa nell'interfaccia di amministrazione di Microsoft 365.

Il ruolo lettore di report di riepilogo sull'utilizzo dovrà essere assegnato tramite i cmdlet di PowerShell fino a quando non diventa assegnabile dall'interfaccia di amministrazione di Microsoft 365 più avanti nel 2020.

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

Puoi anche rifiutare esplicitamente l'area esperienze utente del punteggio di produttività. Se si rifiuta esplicitamente, nessuno dell'organizzazione sarà in grado di visualizzare queste metriche e l'organizzazione verrà rimossa da qualsiasi calcolo che implica comunicazioni, riunioni, lavoro in team, collaborazione sui contenuti e mobilità. È necessario essere un amministratore globale per rifiutare esplicitamente all'organizzazione i report sull'esperienza utente.

Per scegliere di inserire:

1. Nell'interfaccia di amministrazione passare a Impostazioni organizzazione e nella scheda   >   Servizi selezionare **Report.** 
2. Deselezionare la casella consenti l'uso dei dati di utilizzo di **Microsoft 365 per le informazioni dettagliate sulle esperienze degli utenti.** Per informazioni su come modificare le impostazioni di condivisione dei dati per Endpoint Analytics in Gestione configurazione Intune, selezionare **Altre informazioni.**
3. Selezionare **Salva.**

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Pagina delle impostazioni dell'organizzazione in cui puoi rifiutare esplicitamente le esperienze degli utenti.":::