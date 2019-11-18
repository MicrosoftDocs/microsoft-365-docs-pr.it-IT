---
title: Abilitare o disabilitare la ricerca nel log di controllo di Office 365
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
description: È possibile abilitare la funzionalità di ricerca del registro di controllo nel centro sicurezza & Compliance. Se si cambia idea, è possibile attivarlo in qualsiasi momento. Quando la ricerca del registro di controllo è disattivata, gli amministratori non possono eseguire ricerche nel log di controllo di Office 365 per l'attività dell'utente e dell'amministratore nell'organizzazione.
ms.openlocfilehash: 4e382c9916a9460d2c837a336607734427416a1a
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686600"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Abilitare o disabilitare la ricerca nel log di controllo di Office 365

L'utente (o un altro amministratore) deve attivare la registrazione di controllo prima di iniziare la ricerca nel registro di controllo di Office 365. Quando la ricerca del registro di controllo nel centro sicurezza & conformità è attivata, l'attività dell'utente e dell'amministratore dell'organizzazione viene registrata nel registro di controllo e conservata per 90 giorni. Tuttavia, è possibile che l'organizzazione non desideri registrare e conservare i dati del log di controllo. In alternativa, è possibile utilizzare un'applicazione di sicurezza di terze parti e la gestione eventi (SIEM) per accedere ai dati di controllo. In questi casi, un amministratore globale può disattivare la ricerca del registro di controllo in Office 365.
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario essere assegnati al ruolo registri di controllo in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo nell'organizzazione di Office 365. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online. 
    
    > [!IMPORTANT]
    > Gli utenti devono disporre delle autorizzazioni in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo. Se si assegnano gli utenti al ruolo registri di controllo nella pagina **autorizzazioni** nel centro sicurezza & Compliance, non sarà possibile abilitare o disabilitare la ricerca del registro di controllo. Ciò è dovuto al fatto che il cmdlet sottostante è un cmdlet di Exchange Online. 
  
- Se si disattiva la ricerca del registro di controllo in Office 365, non è possibile utilizzare l'API di attività di gestione di Office 365 per accedere ai dati di controllo per l'organizzazione. La disattivazione della ricerca del registro di controllo seguendo i passaggi descritti in questo articolo indica che non verranno restituiti risultati quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza & conformità o quando si utilizza il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell. Questo significa anche che i registri di controllo non saranno disponibili tramite l'API di attività di gestione di Office 365.  
    
- Per istruzioni dettagliate sulla ricerca nel registro di controllo di Office 365, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
    
## <a name="turn-on-audit-log-search"></a>Attiva ricerca log di controllo

È possibile utilizzare il Centro sicurezza & conformità o PowerShell per abilitare la ricerca del registro di controllo in Office 365. Dopo aver eseguito la ricerca nel registro di controllo, potrebbero essere necessarie diverse ore dopo aver attivato la ricerca del registro di controllo. Per abilitare la ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online.
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>Utilizzare il Centro sicurezza & conformità per abilitare la ricerca nel registro di controllo

1. Nel centro sicurezza & conformità, andare alla **ricerca del registro di controllo**della **ricerca** \> .
    
   Viene visualizzato un banner che indica che è necessario che il controllo sia attivato per registrare l'attività dell'utente e dell'amministratore.

2. Fare clic **su Attiva controllo**.
    
    ![Fare clic su Attiva controllo](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Il banner viene aggiornato per indicare che il registro di controllo è in fase di preparazione e che è possibile cercare l'attività dell'utente e dell'amministratore in poche ore.
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>Utilizzo di PowerShell per abilitare la ricerca nel registro di controllo

1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Eseguire il seguente comando di PowerShell per abilitare la ricerca del registro di controllo in Office 365.
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Viene visualizzato un messaggio in cui viene indicato che potrebbe essere necessario fino a 60 minuti per rendere effettive le modifiche.
  
## <a name="turn-off-audit-log-search"></a>Disattiva la ricerca nel registro di controllo

Per disattivare la ricerca del registro di controllo, è necessario utilizzare Remote PowerShell connesso all'organizzazione di Exchange Online. Analogamente all'attivazione della ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online per disattivare la ricerca del registro di controllo.
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Eseguire il seguente comando di PowerShell per disattivare la ricerca del registro di controllo in Office 365.
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Dopo un po' di tempo, verificare che la ricerca del registro di controllo sia disattivata (disattivata). Questa operazione può essere eseguita in due modi:
    
    - In PowerShell, eseguire il comando riportato di seguito:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      Il valore della `False` proprietà _UnifiedAuditLogIngestionEnabled_ indica che la ricerca del registro di controllo è disattivata. 
    
    - Nel centro sicurezza & conformità, andare alla **ricerca del registro di controllo**della **ricerca** \> .
    
      Viene visualizzato un banner che indica che è necessario che il controllo sia attivato per registrare l'attività dell'utente e dell'amministratore.
