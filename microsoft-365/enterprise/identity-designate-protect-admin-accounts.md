---
title: 'Passaggio 2: proteggere gli account amministratore globale'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare gli account di amministratore per la massima protezione.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868916"
---
# <a name="step-2-protect-global-administrator-accounts"></a>Passaggio 2: proteggere gli account amministratore globale

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In questo passaggio, è possibile impedire attacchi digitali nell'organizzazione garantendo la massima sicurezza degli account amministratore. Per farlo, è necessario:

- Creare account amministratore globale dedicati con [password molto complesse](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usarli solo se necessario.
- Eseguire attività di amministrazione quotidiane assegnando ruoli di amministratore specifici, come amministratore di Exchange o delle password agli account utente del personale IT in base alle esigenze.

Per gli account di amministratore globale dedicati, è necessario inoltre:

1. Testare l'account di ogni utente o le impostazioni dell'autenticazione a più fattori basata sull'accesso condizionale in un account utente di prova per assicurarsi che l'autenticazione a più fattori funzioni correttamente e come previsto. L'autenticazione a più fattori richiede una seconda forma di autenticazione, come il codice di verifica inviato a uno smartphone.
2. Configurare l'autenticazione a più fattori per ogni account amministratore globale di Office 365 dedicato e usare la forma più forte di autenticazione secondaria disponibile nell'organizzazione. Vedere [Autenticazione a più fattori](identity-multi-factor-authentication.md) per maggiori informazioni.
2. Usare un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale. Per ulteriori informazioni, vedere [Protezione degli account di amministratore](identity-access-prerequisites.md#protecting-administrator-accounts).
4. Utilizzare un criterio Office 365 Cloud App Security per monitorare l'attività dell'account amministratore globale. Per maggiori informazioni, vedere [Configurare un livello di sicurezza maggiore per Office 365](infoprotect-configure-increased-security-office-365.md).

Vedere [Proteggere gli account di amministratore globale di Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) per ulteriori informazioni sulla configurazione.

> [!Note]
> Le organizzazioni dovrebbero utilizzare identità solo cloud per creare account con privilegi, come gli amministratori globali, per scenari di intrusione durante le emergenze, come un cyberattacco. Per ulteriori informazioni, vedere [Gestire gli account amministrativi per accessi di emergenza in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

I risultati di questo passaggio sono:

- Gli unici account utente nell'abbonamento a cui è assegnato il ruolo di amministratore globale sono il nuovo set di account di amministratore globale dedicati. Per verificarlo, usare il comando PowerShell V2 di Windows Azure Active Directory: 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- A tutti gli altri account utente quotidiani che gestiscono l'abbonamento sono assegnati ruoli di amministratore associati ai propri ruoli professionali.

> [!Note]
> Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'installazione del modulo Azure AD V2 PowerShell e su come accedere.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: proteggere gli account amministratore globale](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-global-admin) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Configurare gli amministratori globali su richiesta](identity-privileged-identity-management.md) |

