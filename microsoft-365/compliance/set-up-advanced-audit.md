---
title: Configurare il controllo avanzato in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come configurare Advanced Audit in modo da poter eseguire indagini forensi quando gli account utente vengono compromessi o per indagare altri incidenti correlati alla sicurezza.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314360"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>Configurare il controllo avanzato in Microsoft 365

Se l'organizzazione dispone di una sottoscrizione e di una licenza per gli utenti finali che supporta il controllo avanzato, eseguire la procedura seguente per configurare e utilizzare le funzionalità aggiuntive in Advanced Audit.

![Flusso di lavoro per la configurazione di Audit avanzato](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a>Passaggio 1: Configurare il controllo avanzato per gli utenti

Le funzionalità di Audit avanzato, come la possibilità di registrare eventi cruciali come MailItemsAccessed e Send, richiedono una licenza E5 appropriata assegnata agli utenti. Inoltre, è necessario che per tali utenti siano abilitati l'app Controllo avanzato e/o il piano di servizio. Per verificare che l'app Controllo avanzato sia assegnata agli utenti, eseguire la procedura seguente per ogni utente:

1. Nell'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/Adminportal) passare a **Utenti** > **Utenti attivi** e selezionare un utente.

2. Nel riquadro a comparsa delle proprietà utente fare clic su **Licenze e app**.

3. Nella sezione **Licenze** verificare che all'utente sia assegnata una licenza E5 o a una licenza del componente aggiuntivo appropriata. Per un elenco delle licenze che supportano Advanced Audit, vedere [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).

4. Espandere la sezione **App** e verificare che la casella di controllo **Controllo avanzato Microsoft 365** sia selezionata.

5. Se la casella di controllo non è selezionata, selezionarla e quindi fare clic su **Salva modifiche.**

   La registrazione dei record di controllo per MailItemsAccessed e Send inizierà entro 24 ore. È necessario eseguire il passaggio 3 per avviare la registrazione di altri due eventi cruciali di controllo avanzato: SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.

Per le organizzazioni che assegnano licenze ai gruppi di utenti usando le licenze basate su gruppi, è necessario disabilitare l'assegnazione delle licenze per il controllo avanzato di Microsoft 365 per il gruppo. Dopo aver salvato le modifiche, verificare che il controllo avanzato di Microsoft 365 sia disabilitato per il gruppo. Quindi, riabilitare l'assegnazione delle licenze per il gruppo. Per istruzioni sulle licenze basate su gruppi, vedere [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

Inoltre, se sono state personalizzate le azioni delle cassette postali registrate nelle cassette postali degli utenti o nelle cassette postali condivise, eventuali nuovi eventi cruciali rilasciati da Microsoft non verranno controllati automaticamente in tali cassette postali. Per informazioni sulla modifica delle azioni della cassetta postale controllate per ogni tipo di accesso, vedere la sezione "Modificare o ripristinare le azioni della cassetta postale registrate per impostazione predefinita" in [Gestire il controllo delle cassette postali](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).

## <a name="step-2-enable-crucial-events"></a>Passaggio 2: abilitare gli eventi cruciali

È necessario abilitare due eventi cruciali (SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint) per essere registrati quando gli utenti eseguono ricerche in Exchange Online e SharePoint Online. Per abilitare il controllo di questi due eventi per gli utenti, eseguire il comando seguente (per ogni utente) in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

In un ambiente multi-geografico, è necessario eseguire il comando **Set-Mailbox** precedente nella foresta in cui si trova la cassetta postale dell'utente. Per identificare la posizione della cassetta postale dell'utente, eseguire il comando seguente: 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

Se il comando per abilitare il controllo delle query di ricerca è stato eseguito in precedenza in una foresta diversa da quella in cui si trova la cassetta postale dell'utente, è necessario rimuovere il valore SearchQueryInitiated dalla cassetta postale dell'utente eseguendolo e quindi aggiungerlo alla cassetta postale dell'utente nella foresta in cui si trova la cassetta postale `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` dell'utente.

## <a name="step-3-set-up-audit-retention-policies"></a>Passaggio 3: Configurare i criteri di conservazione dei controlli

Oltre ai criteri predefiniti che conservano i record di controllo di Exchange, SharePoint e Azure AD per un anno, puoi creare altri criteri di conservazione del log di audit per soddisfare i requisiti delle operazioni di sicurezza, dell'IT e dei team di conformità dell'organizzazione. Per altre informazioni, vedere [Gestire i criteri di conservazione dei log di controllo](audit-log-retention-policies.md).

## <a name="step-4-search-for-crucial-events"></a>Passaggio 4: ricerca di eventi cruciali

Dopo aver configurato il controllo avanzato per l'organizzazione, è possibile cercare eventi cruciali e altre attività durante l'esecuzione di indagini forensi. Dopo aver completato i passaggi 1 e 2, è possibile cercare nel log di controllo eventi cruciali e altre attività durante indagini forensi su account compromessi e altri tipi di indagini di sicurezza o conformità. Per ulteriori informazioni sull'esecuzione di un'indagine forense sugli account utente compromessi utilizzando l'evento cruciale MailItemsAccessed, vedere [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).
