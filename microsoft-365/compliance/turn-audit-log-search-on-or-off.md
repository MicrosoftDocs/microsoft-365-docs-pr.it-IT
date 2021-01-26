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
description: Informazioni su come attivare o disattivare la funzionalità di ricerca del registro di controllo nel centro sicurezza & Compliance per abilitare o disabilitare la possibilità per gli amministratori di eseguire ricerche nel log di controllo.
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976329"
---
# <a name="turn-audit-log-search-on-or-off"></a>Abilitare o disabilitare la ricerca dei log di controllo

La registrazione di controllo è attivata per impostazione predefinita per le organizzazioni Enterprise di Microsoft 365 e Office 365. Sono incluse le organizzazioni con abbonamenti E3/G3 o E5/G5. Quando la ricerca del registro di controllo nel centro conformità è attivata, l'attività dell'utente e dell'amministratore dell'organizzazione viene registrata nel registro di controllo e conservata per 90 giorni e fino a un anno, a seconda della licenza assegnata agli utenti. Tuttavia, è possibile che l'organizzazione abbia motivi per non voler registrare e conservare i dati del log di controllo. In questi casi, un amministratore globale può decidere di disattivare il controllo in Microsoft 365.

> [!IMPORTANT]
> Se si disattiva la ricerca del registro di controllo in Microsoft 365, non è possibile utilizzare l'API di attività di gestione di Office 365 o la sentinella di Azure per accedere ai dati di controllo per l'organizzazione. La disattivazione della ricerca del registro di controllo seguendo i passaggi descritti in questo articolo indica che non verranno restituiti risultati quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza & conformità o quando si utilizza il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell. Questo significa anche che i registri di controllo non saranno disponibili tramite l'API di attività di gestione di Office 365 o la sentinella di Azure.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Prima di abilitare o disabilitare la ricerca del registro di controllo

- È necessario essere assegnati al ruolo registri di controllo in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo nell'organizzazione Microsoft 365. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali di Microsoft 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online. 
    
    > [!NOTE]
    > Gli utenti devono disporre delle autorizzazioni in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo. Se si assegnano gli utenti al ruolo registri di controllo nella pagina **autorizzazioni** nel centro sicurezza & Compliance, non sarà possibile abilitare o disabilitare la ricerca del registro di controllo. Ciò è dovuto al fatto che il cmdlet sottostante è un cmdlet di Exchange Online PowerShell. 
    
- Per istruzioni dettagliate sulla ricerca nel registro di controllo, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md). Per ulteriori informazioni sull'API Microsoft 365 Management Activity, vedere [Introduzione a microsoft 365 Management Apis](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

- Per verificare che la ricerca del registro di controllo sia attivata, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    Il valore della  `True` proprietà  _UnifiedAuditLogIngestionEnabled_ indica che la ricerca del registro di controllo è attivata. 
    
## <a name="turn-on-audit-log-search"></a>Attiva ricerca log di controllo

Se la ricerca del registro di controllo non è attivata per l'organizzazione, è possibile attivarla nel centro conformità o tramite PowerShell di Exchange Online. Dopo aver eseguito la ricerca nel registro di controllo, potrebbero essere necessarie diverse ore dopo aver attivato la ricerca del registro di controllo.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Utilizzare il centro conformità per abilitare la ricerca nel registro di controllo

1. [Accedere al centro conformità](https://protection.office.com) e accedere.

2. Nel centro conformità, andare alla ricerca del registro di controllo della **ricerca**  >  .

   Se la ricerca del registro di controllo non è attivata per l'organizzazione, viene visualizzato un banner che indica che è necessario che il controllo sia attivato per registrare l'attività dell'utente e dell'amministratore.

3. Fare clic **su Attiva controllo**.

    ![Fare clic su Attiva controllo](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Il banner viene aggiornato per indicare che il registro di controllo è in fase di preparazione e che è possibile cercare l'attività dell'utente e dell'amministratore in poche ore.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Utilizzo di PowerShell per abilitare la ricerca nel registro di controllo

1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Eseguire il seguente comando di PowerShell per abilitare la ricerca del registro di controllo in Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Viene visualizzato un messaggio in cui viene indicato che potrebbe essere necessario fino a 60 minuti per rendere effettive le modifiche.
  
## <a name="turn-off-audit-log-search"></a>Disattiva la ricerca nel registro di controllo

Per disattivare la ricerca del registro di controllo, è necessario utilizzare Exchange Online PowerShell.
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Eseguire il seguente comando di PowerShell per disattivare la ricerca del registro di controllo.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Dopo un po' di tempo, verificare che la ricerca del registro di controllo sia disattivata (disattivata). Questa operazione può essere eseguita in due modi:

    - In Exchange Online PowerShell, eseguire il comando riportato di seguito:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Il valore della  `False` proprietà  _UnifiedAuditLogIngestionEnabled_ indica che la ricerca del registro di controllo è disattivata. 

    - Nel [centro conformità](https://protection.office.com), andare alla ricerca del registro di controllo della **ricerca** \> .

      Viene visualizzato un banner che indica che è necessario che il controllo sia attivato per registrare l'attività dell'utente e dell'amministratore.
