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
description: Come attivare o disattivare la funzionalità di ricerca dei log di controllo nel Centro sicurezza & conformità per abilitare o disabilitare la capacità degli amministratori di eseguire ricerche nel log di controllo.
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976329"
---
# <a name="turn-audit-log-search-on-or-off"></a>Abilitare o disabilitare la ricerca dei log di controllo

La registrazione di controllo è attivata per impostazione predefinita per le organizzazioni di Microsoft 365 e Office 365 Enterprise. Ciò include le organizzazioni con abbonamenti E3 / G3 o E5 / G5. Quando la ricerca nel log di controllo nel Centro conformità è attivata, le attività degli utenti e degli amministratori dell'organizzazione vengono registrate nel log di controllo e conservate per 90 giorni e fino a un anno a seconda della licenza assegnata agli utenti. Tuttavia, l'organizzazione potrebbe avere motivi per non voler registrare e conservare i dati del log di controllo. In questi casi, un amministratore globale può decidere di disattivare il controllo in Microsoft 365.

> [!IMPORTANT]
> Se si disattiva la ricerca nei log di controllo in Microsoft 365, non è possibile usare l'API Office 365 Management Activity o Azure Sentinel per accedere ai dati di controllo per l'organizzazione. Disattivando la ricerca nel log di controllo seguendo i passaggi descritti in questo articolo, non verrà restituito alcun risultato quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza & conformità o quando si esegue il cmdlet **Search-UnifiedAuditLog** in PowerShell di Exchange Online. Questo significa anche che i log di controllo non saranno disponibili tramite l'API office 365 Management Activity o Azure Sentinel.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Prima di attivare o disattivare la ricerca nei log di controllo

- È necessario essere assegnati al ruolo Log di controllo in Exchange Online per attivare o disattivare la ricerca nei log di controllo nell'organizzazione di Microsoft 365. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella **pagina** Autorizzazioni nell'interfaccia di amministrazione di Exchange. Gli amministratori globali in Microsoft 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online. 
    
    > [!NOTE]
    > Gli utenti devono disporre delle autorizzazioni in Exchange Online per attivare o disattivare la ricerca nel log di controllo. Se si assegna agli utenti  il ruolo Log di controllo nella pagina Autorizzazioni nel Centro sicurezza & conformità, non potranno attivare o disattivare la ricerca nei log di controllo. Questo perché il cmdlet sottostante è un cmdlet di PowerShell di Exchange Online. 
    
- Per istruzioni dettagliate sulla ricerca nel log di controllo, vedere Eseguire una ricerca nel log di [controllo nel Centro sicurezza & conformità.](search-the-audit-log-in-security-and-compliance.md) Per altre informazioni sull'API microsoft 365 Management Activity, vedere Introduzione alle API di gestione [di Microsoft 365.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)

- Per verificare che la ricerca nel registro di controllo sia attivata, è possibile eseguire il comando seguente in Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    Il valore della  `True` proprietà  _UnifiedAuditLogIngestionEnabled_ indica che la ricerca nel log di controllo è attivata. 
    
## <a name="turn-on-audit-log-search"></a>Attivare la ricerca nei log di controllo

Se la ricerca nel log di controllo non è attivata per l'organizzazione, è possibile attivarla nel Centro conformità o utilizzando PowerShell di Exchange Online. L'attivazione della ricerca nel log di controllo potrebbe richiedere diverse ore prima che sia possibile restituire risultati durante la ricerca nel log di controllo.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Usare il Centro conformità per attivare la ricerca nei log di controllo

1. [Accedere al Centro conformità](https://protection.office.com) e accedere.

2. Nel Centro conformità passare a Ricerca **log**  >  **di controllo.**

   Se la ricerca nel log di controllo non è attivata per l'organizzazione, viene visualizzato un banner che indica che il controllo deve essere attivato per registrare le attività degli utenti e degli amministratori.

3. Fare **clic su Attiva controllo.**

    ![Fare clic su Attiva controllo](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Il banner viene aggiornato per dire che il log di controllo è in fase di preparazione e che è possibile cercare le attività degli utenti e degli amministratori in poche ore.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Usare PowerShell per attivare la ricerca nel log di controllo

1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Eseguire il comando di PowerShell seguente per attivare la ricerca nel log di controllo in Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Viene visualizzato un messaggio che indica che l'applicazione della modifica potrebbe richiedere fino a 60 minuti.
  
## <a name="turn-off-audit-log-search"></a>Disattivare la ricerca nei log di controllo

È necessario utilizzare PowerShell di Exchange Online per disattivare la ricerca nel log di controllo.
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Eseguire il seguente comando di PowerShell per disattivare la ricerca nel log di controllo.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Dopo un po' di tempo, verificare che la ricerca nel log di controllo sia disattivata (disabilitata). Questa operazione può essere eseguita in due modi:

    - In PowerShell di Exchange Online, eseguire il comando seguente:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Il valore della  `False` proprietà  _UnifiedAuditLogIngestionEnabled_ indica che la ricerca nel log di controllo è disattivata. 

    - Nel Centro [conformità](https://protection.office.com)passare a Ricerca **log** \> **di controllo.**

      Viene visualizzato un banner che indica che il controllo deve essere attivato per registrare le attività degli utenti e degli amministratori.
