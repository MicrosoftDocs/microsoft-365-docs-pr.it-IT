---
title: Abilitare o disabilitare la ricerca dei log di controllo
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Come attivare o disattivare la funzionalità di ricerca dei log di controllo nel Centro sicurezza & conformità per abilitare o disabilitare la possibilità degli amministratori di eseguire ricerche nel log di controllo.
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919282"
---
# <a name="turn-audit-log-search-on-or-off"></a>Abilitare o disabilitare la ricerca dei log di controllo

La registrazione di controllo è attivata per impostazione predefinita per le organizzazioni di Microsoft 365 e Office 365 Enterprise. Ciò include le organizzazioni con abbonamenti E3 / G3 o E5 / G5. Quando la ricerca nei log di controllo nel Centro conformità è attivata, le attività dell'utente e dell'amministratore dell'organizzazione vengono registrate nel log di controllo e conservate per 90 giorni e fino a un anno a seconda della licenza assegnata agli utenti. Tuttavia, l'organizzazione potrebbe avere motivi per non voler registrare e conservare i dati del registro di controllo. In questi casi, un amministratore globale può decidere di disattivare il controllo in Microsoft 365.

> [!IMPORTANT]
> Se si disattiva la ricerca nei log di controllo in Microsoft 365, non è possibile usare l'API di attività di gestione di Office 365 o Azure Sentinel per accedere ai dati di controllo per l'organizzazione. Disattivando la ricerca nei log di controllo seguendo i passaggi descritti in questo articolo, non verrà restituito alcun risultato quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza e conformità di & o quando si esegue il cmdlet **Search-UnifiedAuditLog** in PowerShell di Exchange Online. Questo significa anche che i log di controllo non saranno disponibili tramite l'API di attività di gestione di Office 365 o Azure Sentinel.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Prima di attivare o disattivare la ricerca nel log di controllo

- Per attivare o disattivare la ricerca nei registri di controllo nell'organizzazione di Microsoft 365, è necessario disporre del ruolo Registri di controllo in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella **pagina Autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali in Microsoft 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online. 
    
    > [!NOTE]
    > Gli utenti devono disporre delle autorizzazioni in Exchange Online per attivare o disattivare la ricerca nel log di controllo. Se si assegna agli utenti  il ruolo Log di controllo nella pagina Autorizzazioni nel Centro sicurezza & conformità, non potranno attivare o disattivare la ricerca nei log di controllo. Questo perché il cmdlet sottostante è un cmdlet di PowerShell di Exchange Online. 
    
- Per istruzioni dettagliate sulla ricerca nel log di controllo, vedere [Search the audit log in the Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md) Per altre informazioni sull'API di attività di gestione di Microsoft 365, vedi Introduzione alle API di gestione di [Microsoft 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)

- Per verificare che la ricerca nel registro di controllo sia attivata, è possibile eseguire il comando seguente in Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    Il valore di  `True` per la  _proprietà UnifiedAuditLogIngestionEnabled_ indica che la ricerca nel log di controllo è attivata. 
    
## <a name="turn-on-audit-log-search"></a>Attivare la ricerca nei log di controllo

Se la ricerca nel log di controllo non è attivata per l'organizzazione, è possibile attivarla nel Centro conformità o tramite PowerShell di Exchange Online. L'attivazione della ricerca nel log di controllo può richiedere diverse ore prima di poter restituire i risultati durante la ricerca nel log di controllo.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Usare il Centro conformità per attivare la ricerca nei log di controllo

1. [Passare al Centro conformità ed](https://protection.office.com) eseguire l'accesso.

2. Nel Centro conformità passare a Ricerca **log**  >  **di controllo**.

   Se la ricerca nel log di controllo non è attivata per l'organizzazione, viene visualizzato un banner che indica che il controllo deve essere attivato per registrare le attività di utenti e amministratori.

3. Fare **clic su Attiva controllo.**

    ![Fare clic su Attiva controllo](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Il banner viene aggiornato per dire che il log di controllo è in fase di preparazione e che è possibile cercare attività di utenti e amministratori in poche ore.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Usare PowerShell per attivare la ricerca nei log di controllo

1. [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il comando di PowerShell seguente per attivare la ricerca nei log di controllo in Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Viene visualizzato un messaggio che indica che la modifica potrebbe richiedere fino a 60 minuti.
  
## <a name="turn-off-audit-log-search"></a>Disattivare la ricerca nei log di controllo

È necessario utilizzare PowerShell di Exchange Online per disattivare la ricerca nel log di controllo.
  
1. [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il comando di PowerShell seguente per disattivare la ricerca nei log di controllo.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Dopo un po', verificare che la ricerca nel log di controllo sia disattivata (disabilitata). Questa operazione può essere eseguita in due modi:

    - In PowerShell di Exchange Online, eseguire il comando seguente:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Il valore di  `False` per la  _proprietà UnifiedAuditLogIngestionEnabled_ indica che la ricerca nel log di controllo è disattivata. 

    - Nel Centro [conformità](https://protection.office.com)passare a Ricerca **log** \> **di controllo**.

      Viene visualizzato un banner che indica che il controllo deve essere attivato per registrare le attività degli utenti e degli amministratori.