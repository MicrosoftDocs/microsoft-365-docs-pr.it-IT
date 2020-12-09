---
title: Valutazione della produttività Microsoft-privacy
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
description: Modalità di protezione della privacy con il Punteggio di produttività.
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604327"
---
# <a name="privacy-controls-for-productivity-score"></a>Controlli sulla privacy per il Punteggio di produttività

Produttività Score fornisce informazioni dettagliate sul percorso di trasformazione digitale dell'organizzazione tramite l'utilizzo di Microsoft 365 e le esperienze tecnologiche che lo supportano.  Il Punteggio dell'organizzazione riflette le misure relative a utenti e tecnologie e può essere paragonato ai benchmark di organizzazioni simili ai propri. Per ulteriori informazioni, vedere [Panoramica del Punteggio di produttività](productivity-score.md).

La privacy è importante per Microsoft. Per informazioni su come proteggiamo la privacy, vedere l' [informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement). Il Punteggio di produttività fornisce all'amministratore IT dell'organizzazione l'accesso alle impostazioni di privacy per garantire che le informazioni sul punteggio di produttività visualizzate siano utilizzabili, senza compromettere la fiducia che l'organizzazione inserisce in Microsoft.

All'interno dell'area persone esperienze, le metriche sono disponibili solo a livello organizzativo. In questa sezione viene illustrato il modo in cui gli utenti utilizzano Microsoft 365 esaminando le categorie di collaborazione del contenuto, mobilità, riunioni, lavoro di squadra e comunicazione. Sono disponibili diversi livelli di controlli che consentono di soddisfare le esigenze dei criteri di privacy interni.
I controlli forniscono:

- Ruoli di amministratore flessibili per controllare gli utenti che possono visualizzare le informazioni nel punteggio di produttività.
- La possibilità di escludere l'area persone.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Ruoli di amministratore flessibili per controllare gli utenti che possono visualizzare le informazioni nel punteggio di produttività

Per visualizzare l'intero Punteggio di produttività, è necessario essere uno dei ruoli di amministratore seguenti:

- Amministratore globale
- Amministratori di Exchange
- Amministratore di SharePoint
- Amministratore di Skype for Business
- Amministratore di Teams
- Lettore globale
- Amministratore che legge i report
- Reader report di riepilogo utilizzo

Assegnare il lettore report o il ruolo Reader report di riepilogo utilizzo a tutti coloro che sono responsabili della gestione delle modifiche e dell'adozione, ma non necessariamente di un amministratore IT. Questo ruolo consente di accedere all'interfaccia di amministrazione di Microsoft 365.

Il ruolo Reader dei report di riepilogo di utilizzo dovrà essere assegnato tramite i cmdlet di PowerShell fino a quando non diventerà assegnabile dall'interfaccia di amministrazione di Microsoft 365 più avanti nel 2020.

Per assegnare il ruolo Reader dei report di riepilogo di utilizzo con PowerShell:

- Eseguire la seguente PowerShell:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>Possibilità di escludere le esperienze degli utenti

È inoltre possibile escludere l'area persone esperienze del Punteggio di produttività. In caso di disattivazione, nessuno dell'organizzazione sarà in grado di visualizzare queste metriche e l'organizzazione verrà rimossa da qualsiasi calcolo che comprenda la comunicazione, le riunioni, il lavoro di squadra, la collaborazione di contenuto e la mobilità. È necessario essere un amministratore globale per scegliere la propria organizzazione fuori dai rapporti sulle esperienze degli utenti.

Per scegliere l'opzione put:

1. Nell'interfaccia di amministrazione, passare alla sezione **Impostazioni**   >   **organizzazione** e in scheda **Servizi** , selezionare **report**.
2. Deselezionare la casella che indica che  **è possibile utilizzare i dati di utilizzo di Microsoft 365 per gli utenti con esperienze approfondite**. Per informazioni su come modificare le impostazioni di condivisione dei dati per l'analisi di endpoint in Gestione configurazione di Intune, selezionare **Learn more**.
3. Selezionare  **Salva**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Pagina delle impostazioni dell'organizzazione in cui è possibile escludere le esperienze degli utenti.":::