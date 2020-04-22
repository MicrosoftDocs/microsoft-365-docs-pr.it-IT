---
title: 'Passaggio 1: creare e proteggere gli account di amministratore globale'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Gli account di amministratore globale devono avere un trattamento speciale per proteggerli dal compromesso delle credenziali.
ms.openlocfilehash: c23a5730bc4c6af1f7fd829a40b63cc7ccc89184
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621307"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>Passaggio 1: creare e proteggere gli account di amministratore globale

![Fase 2 - Identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Proteggere gli account amministratore globale

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione è possibile impedire attacchi digitali nell'organizzazione garantendo la massima sicurezza degli account amministratore. A tale scopo, è necessario:

- Creare più account di amministratore globale dedicati con [password complesse](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) e usarli solo se necessario.
- Eseguire attività di amministrazione quotidiane assegnando ruoli di amministratore specifici, come amministratore di Exchange o delle password ad altri account dedicati per questi ruoli o agli account utente del personale IT in base alle esigenze.

Per gli account di amministratore globale dedicati, è necessario inoltre:

1. Testare l'account di ogni utente o le impostazioni dell'autenticazione a più fattori di Azure basata sull'accesso condizionale in un account utente di prova per assicurarsi che l'autenticazione a più fattori funzioni correttamente e come previsto. L'autenticazione a più fattori richiede una seconda forma di autenticazione, come il codice di verifica inviato a uno smartphone.
2. Creare e attivare un criterio di Accesso Condizionale per gli account di amministratore globale che richiedono l’autenticazione a due fattori e usare la forma più complessa di autenticazione secondaria disponibile nell'organizzazione. Per altre informazioni, vedere [Autenticazione a più fattori di Azure](identity-access-prerequisites.md#protecting-administrator-accounts).

Per protezioni aggiuntive, vedere [Proteggere gli account di amministratore globale](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).

> [!Note]
> Gli account di emergenza per scenari break-glass in situazioni di emergenza come cyberattacco devono essere solo account cloud. Potrebbero essere presenti anche degli account di amministratore globale (idonei o permanenti) che non sono solo cloud. Per altre informazioni, vedere [Gestire gli account amministrativi di accesso di emergenza in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

I risultati di questa sezione sono:

- Gli unici account utente dell'abbonamento a cui è assegnato il ruolo di amministratore globale sono gli account di amministratore globale dedicati. Per verificarlo, usare il comando seguente di Azure Active Directory PowerShell per Graph: 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- A tutti gli altri account utente che gestiscono i servizi dell'abbonamento sono assegnati ruoli di amministratore associati ai propri ruoli professionali.

> [!Note]
> Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'istallazione del modulo Azure Active Directory PowerShell for Graph e sull'accesso.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Per eseguire questa procedura in un ambiente di testing, vedere la Guida al lab di test [Proteggere gli account amministratore globale](protect-global-administrator-accounts-microsoft-365-test-environment.md). |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-global-admin) per questa sezione.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>Configurare gli amministratori su richiesta

*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*

In questa sezione si procederà alla configurazione di Azure AD Privileged Identity Management (PIM) per ridurre la quantità di tempo per la quale gli account amministratore sono vulnerabili agli attacchi da parte di utenti malintenzionati. Su richiesta, PIM fornisce l'assegnazione JIT del ruolo di amministratore, se necessario.  

Invece di essere amministratori permanenti degli account di amministratore, diventano amministratori idonei. Il ruolo di amministratore è inattivo finché qualcuno non lo richiede. Sarà quindi necessario completare un processo di attivazione per aggiungere il ruolo di amministratore all'account di amministratore per un determinato periodo di tempo. Al termine di tale periodo, PIM rimuove il ruolo di amministratore dall'account di amministratore.

PIM è disponibile con Azure Active Directory Premium P2, incluso in Microsoft 365 E5. In alternativa, è possibile acquistare singole licenze di Azure Active Directory Premium P2 per gli account di amministratore.

Per attivare Azure PIM per gli account tenant e amministratore Azure Active Directory, vedere la [procedura per configurare PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici, vedere [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pim) per questa sezione.


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>Gestione accessi con privilegi

La gestione degli accessi con privilegi è abilitata mediante la configurazione di criteri che specificano l'accesso just-in-time per le operazioni basate sulle attività nel tenant. Può aumentare il livello di protezione dell'organizzazione da violazioni che possono usare gli account amministratore con privilegi esistenti con accesso permanente a dati sensibili o con accesso a impostazioni di configurazione cruciali. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant.

In questo passaggio verrà abilitata la gestione degli accessi con privilegi nel tenant e verranno configurati i criteri di accesso con privilegi che garantiscono una maggiore protezione per gli accessi basati sulle attività a impostazioni dati e configurazione dell'organizzazione. Esistono tre passaggi di base per iniziare a usare gli accessi con privilegi nell'organizzazione:

- Creazione di un gruppo responsabile dell'approvazione
- Abilitazione dell’accesso con privilegi
- Creazione di criteri per l'approvazione

Una volta configurata, la gestione degli accessi con privilegi consentirà all'organizzazione di operare con privilegi permanenti uguali a zero e di fornire un livello di protezione contro vulnerabilità che si verificano a causa di questo tipo di accesso amministrativo permanente. L’accesso con privilegi richiede l'approvazione per l'esecuzione di tutte le attività associate a un criterio di approvazione definito. Gli utenti che necessitano di eseguire attività incluse nei criteri di approvazione devono richiedere e ottenere l'approvazione di accesso per disporre delle autorizzazioni necessarie a eseguire le attività definite nel criterio.

Per abilitare la gestione degli accessi con privilegi, consultare l'argomento [Configurare la gestione degli accessi con privilegi](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Per ulteriori informazioni, consultare l'argomento [Gestione degli accessi con privilegi](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Per eseguire questa procedura in un ambiente di testing, vedere la [Guida al lab di test gestione degli accessi privilegiati](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Come checkpoint provvisorio, vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pam) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 2](../media/stepnumbers/Step2.png)| [Proteggere le password](identity-secure-your-passwords.md) |

