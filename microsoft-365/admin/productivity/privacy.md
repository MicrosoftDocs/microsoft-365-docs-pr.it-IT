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
ms.openlocfilehash: 8686c7c86249a408fe8d4fda14c2ae23a168cafe
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999407"
---
# <a name="privacy-controls-for-productivity-score"></a>Controlli sulla privacy per il Punteggio di produttività

Il Punteggio di produttività consente alle organizzazioni di trasformare il lavoro svolto con le metriche che consentono di valutare e migliorare le esperienze di persone e tecnologie. Consente di acquisire visibilità sul funzionamento dell'organizzazione e di fornire metriche che consentano di concentrarsi sull'abilitazione di esperienze migliorate.  È inoltre possibile connettere le metriche alle azioni che consentono di aggiornare le competenze e i sistemi in modo che tutti possano svolgere il proprio lavoro. Lo Score riflette le prestazioni dell'organizzazione e consente inoltre di confrontare in modo sicuro il punteggio con altre organizzazioni come la propria.  Per ulteriori informazioni, vedere [Panoramica del Punteggio di produttività](productivity-score.md).

La privacy è importante per noi. Per informazioni su come proteggiamo la privacy, vedere l' [informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement). Il Punteggio di produttività fornisce informazioni importanti sul modo in cui le persone nelle organizzazioni collaborano con i controlli per assicurarsi che le informazioni siano azionabili senza compromettere la fiducia che si sta svolgendo in Microsoft.

All'interno dell'area persone esperienze, le metriche sono disponibili a livello organizzativo e includono tutti gli utenti nel tenant Microsoft 365. In questa sezione viene illustrato il modo in cui gli utenti utilizzano Microsoft 365 esaminando le categorie di collaborazione del contenuto, mobilità, riunioni, lavoro di squadra e comunicazione. Per aiutarti a guidare la formazione e la consapevolezza al giusto set di persone che potrebbero aver bisogno di supporto con i nostri prodotti, ti sono state fornite anche informazioni a livello individuale. Anche se si fornisce questo livello di trasparenza, è inoltre possibile utilizzare diversi livelli di controlli che consentono di soddisfare le esigenze di criteri di privacy interne.
I seguenti controlli forniscono:

- Ruoli di amministratore flessibili per controllare gli utenti che possono visualizzare le informazioni nel punteggio di produttività.
- La possibilità di deidentificare le metriche a livello di utente.
- Possibilità di escludere le esperienze degli utenti.
- La possibilità di escludere l'area delle esperienze degli utenti

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Ruoli di amministratore flessibili per controllare gli utenti che possono visualizzare le informazioni nel punteggio di produttività

Per visualizzare l'intero Punteggio di produttività, incluse le metriche a livello di tenant e i dettagli per utente, il ruolo deve essere uno dei ruoli di amministratore seguenti:

- Amministratore globale
- Amministratori di Exchange
- Amministratore di SharePoint
- Amministratore di Skype for Business
- Amministratore di Teams
- Ruolo con autorizzazioni di lettura globali
- Lettore report

Assegnare il ruolo lettore report a tutti coloro che sono responsabili della gestione delle modifiche e dell'adozione. Questo ruolo consente di accedere all'esperienza completa, incluse le metriche a livello di tenant e i dettagli a livello di utente.

Il rapporto persone esperienze contiene dettagli attività per utente per ogni pagina di dettaglio categoria. Assegnare un ruolo personalizzato denominato Reader report di riepilogo di utilizzo (disponibile a partire dal 29 ottobre 2020) per consentire l'accesso solo alle metriche di aggregazione delle esperienze degli utenti. Questo ruolo dovrà essere assegnato tramite i cmdlet di PowerShell fino a quando non diventa assegnabile dall'interfaccia di amministrazione di Microsoft su 11/15/2020.

Per assegnare il ruolo Reader dei report di riepilogo di utilizzo con PowerShell:

- Eseguire la seguente PowerShell:

```powershell
Connect-AzureAD
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Pagina comunicazioni nei report sulla produttività.":::

## <a name="de-identification-of-user-level-metrics"></a>De-identificazione delle metriche a livello di utente

Per rendere anonimi i dati raccolti per tutti i report, è necessario essere un amministratore globale. Questa azione nasconderà informazioni identificabili, ad esempio i nomi di utenti, gruppi e siti, in tutti i report, tra cui il Punteggio di produttività e l'utilizzo di Microsoft 365.

1. Nell'interfaccia di amministrazione passare alla **pagina Impostazioni**   >   **organizzazione** e quindi in scheda **Servizi** scegliere **report**.
2. Selezionare  **report** e quindi scegliere di  **visualizzare gli identificatori anonimi per i nomi di utenti, gruppi e siti nei report di produttività e utilizzo**. Questa impostazione viene applicata sia ai report di utilizzo che all'app modello.
3. Selezionare  **Salva modifiche**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Rendere anonime le informazioni utente per i report.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Possibilità di escludere le esperienze degli utenti

Quando il Punteggio di produttività è in genere disponibile, è anche possibile scegliere tra l'area persone esperienze del Punteggio di produttività. Se si sceglie di non essere in grado di visualizzare queste metriche, l'organizzazione verrà rimossa da qualsiasi calcolo che comprenda comunicazioni, riunioni, lavoro di squadra, collaborazione di contenuto e mobilità.

1. Nell'interfaccia di amministrazione passare alla **pagina Impostazioni**   >   **organizzazione** e quindi in scheda **Servizi** scegliere **report**.
2. Selezionare  **report** e quindi deselezionare la casella che indica che è possibile  **utilizzare i dati di utilizzo di Microsoft 365 per gli utenti con esperienze approfondite**. Per informazioni su come modificare le impostazioni di condivisione dei dati per l'analisi di endpoint in Gestione configurazione di Intune, fare clic su **Scopri di più**.
3. Selezionare  **Salva modifiche**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Pagina delle impostazioni dell'organizzazione in cui è possibile escludere le esperienze degli utenti.":::