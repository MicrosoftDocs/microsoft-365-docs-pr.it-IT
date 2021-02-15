---
title: Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Usare questa guida del laboratorio di testing per abilitare la gestione degli accessi con privilegi nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126418"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per le aziende

*Questa guida del laboratorio di testing può essere usata sia per gli ambienti di testing di Microsoft 365 per le aziende che per Office 365 Enterprise.*

Questo articolo descrive come configurare la gestione degli accessi con privilegi per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 per le aziende.

La configurazione della gestione degli accessi priviledged prevede tre fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurare la gestione degli accessi con privilegi](#phase-2-configure-privileged-access-management)
- [Fase 3: verificare che sia necessaria l'approvazione per le attività con privilegi e con privilegi elevati](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se si desidera configurare la gestione degli accessi con privilegi in modo semplificato con i requisiti minimi, seguire le istruzioni in [Configurazione di base semplificata.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se si desidera configurare la gestione degli accessi con privilegi in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Il test della gestione degli accessi con privilegi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Qui viene fornito come opzione per testare la gestione degli accessi con privilegi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: configurare la gestione degli accessi con privilegi

In questa fase, configurare un gruppo di responsabili approvazione e abilitare la gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per le aziende. Per ulteriori dettagli e una panoramica della gestione degli accessi con privilegi, vedere [Privileged Access Management.](../compliance/privileged-access-management-overview.md)

Per configurare e usare l'accesso con privilegi nell'organizzazione, eseguire la procedura seguente.

#### <a name="step-1-create-an-approvers-group"></a>[Passaggio 1: Creare un gruppo di responsabili approvazione](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Prima di iniziare a utilizzare l'accesso con privilegi, determinare chi avrà l'autorità di approvazione per le richieste in arrivo di accesso alle attività con privilegi e con privilegi elevati. Tutti gli utenti che fanno parte del gruppo dei responsabili approvazione possono approvare le richieste di accesso. Per usare l'accesso con privilegi, è necessario creare un gruppo di sicurezza abilitato alla posta elettronica in Microsoft 365. Nell'ambiente di testing assegnare al nuovo gruppo di sicurezza il nome "Responsabili approvazione accesso privilegiato" e aggiungere "Utente 3" precedentemente creato nei passaggi precedenti della guida del laboratorio di testing.

#### <a name="step-2-enable-privileged-access"></a>[Passaggio 2: abilitare l'accesso con privilegi](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

L'accesso con privilegi deve essere attivato in modo esplicito in Microsoft 365 con il gruppo di responsabili approvazione predefinito e deve includere un set di account di sistema che si desidera escludere dal controllo di accesso per la gestione degli accessi con privilegi. Assicurarsi di abilitare l'accesso con privilegi nell'organizzazione prima di iniziare la fase 3 di questa guida.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: verificare che sia necessaria l'approvazione per le attività con privilegi e con privilegi elevati

In questa fase, verificare che il criterio di accesso con privilegi funzioni e che gli utenti richiedano l'approvazione per eseguire attività definite con privilegi e con privilegi.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testare la possibilità di eseguire un'attività NON definita in un criterio di accesso con privilegi

Innanzitutto, connettersi a Exchange Management PowerShell con le credenziali di un utente configurato come amministratore globale nell'ambiente di testing e tentare di creare una nuova regola del journal. [L'attività New-JournalRule](/powershell/module/exchange/new-journalrule) non è attualmente definita in un criterio di accesso privilegiato per l'organizzazione.

1. Nel computer locale, aprire e accedere al modulo PowerShell remoto di Exchange Online in **Microsoft Corporation** Microsoft Exchange Online Remote PowerShell Module utilizzando l'account amministratore globale per  >   l'ambiente di testing.

1. In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Visualizzare che la nuova regola del journal è stata creata correttamente in Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Creare un nuovo criterio di accesso con privilegi per lNew-JournalRule appalto

>[!NOTE]
>Se i passaggi 1 e 2 della fase 2 di questa guida non sono stati ancora completati, eseguire la procedura per creare un gruppo di responsabili approvazione denominato "Responsabili approvazione con privilegi" per abilitare l'accesso con privilegi nell'ambiente di testing.

1. Accedere all'interfaccia [di amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali dell'account amministratore globale per l'ambiente di testing.

2. Nell'interfaccia di amministrazione passare **a** Impostazioni  >  **sicurezza & accesso con privilegi**  >  **di privacy.**

3. Selezionare **Gestisci criteri di accesso e richieste.**

4. Selezionare **Configura criteri** e quindi aggiungi un **criterio.**

5. Nell'elenco a discesa selezionare o immettere i valori seguenti:

    **Tipo di criterio**: Attività

    **Ambito dei criteri**: Exchange

    **Nome criterio**: Nuova regola del journal

    **Tipo di approvazione**: Manuale

    **Gruppo di approvazione**: Responsabili approvazione con accesso privilegiato

6. Selezionare **Crea** e quindi **Chiudi.** La configurazione e l'a attivazione completa del criterio potrebbero richiedere alcuni minuti. Assicurarsi di concedere il tempo necessario per l'attivazione completa del criterio prima di testare il requisito di approvazione nel passaggio successivo.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Test del requisito di approvazione per New-JournalRule attività definita in un criterio di accesso con privilegi

1. Nel computer locale, aprire e accedere al modulo PowerShell remoto di Exchange Online in **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell Module** utilizzando l'account amministratore globale per l'ambiente di testing.

2. In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Visualizzare l'errore "Autorizzazioni insufficienti" in Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Richiedere l'accesso per creare una nuova regola del journal utilizzando l'New-JournalRule attività

1. Accedere all'interfaccia [di amministrazione di Microsoft 365](https://admin.microsoft.com) usando l'account amministratore globale per l'ambiente di testing.

2. Nell'interfaccia di amministrazione passare **a** Impostazioni  >  **sicurezza & accesso con privilegi**  >  **di privacy.**

3. Selezionare **Gestisci criteri di accesso e richieste.**

4. Selezionare **Nuova richiesta.** Nei campi a discesa selezionare i valori appropriati per l'organizzazione:

    **Tipo di richiesta**: Attività

    **Ambito della richiesta**: Exchange

    **Richiesta per**: nuova regola del journal

    **Durata (ore)**: 2

    **Commenti:** richiedere l'autorizzazione per creare una nuova regola del journal

5. Selezionare **Salva** e quindi **Chiudi.** La richiesta verrà inviata al gruppo del responsabile approvazione tramite posta elettronica.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Approvare la richiesta di accesso con privilegi per la creazione di una nuova regola del journal

1. Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) usando le credenziali per l'utente 3 nell'ambiente di testing (membro del gruppo di sicurezza "Responsabili approvazione con accesso privilegiato" nell'ambiente di testing).

2. Nell'interfaccia di amministrazione passare **a** Impostazioni  >  **sicurezza & accesso con privilegi**  >  **di privacy.**

3. Selezionare **Gestisci criteri di accesso e richieste.**

4. Selezionare la richiesta in sospeso e quindi selezionare Approva per **concedere** l'accesso all'account amministratore globale per creare una nuova regola del journal. L'account amministratore globale (l'utente richiedente) riceverà un messaggio di posta elettronica di conferma dell'approvazione concessa.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testare la creazione di una nuova regola del journal con accesso privilegiato approvato per lNew-JournalRule attività

1. Nel computer locale, aprire e accedere al modulo PowerShell remoto di Exchange Online in **Microsoft Corporation** Microsoft Exchange Online Remote PowerShell Module utilizzando l'account amministratore globale per  >   l'ambiente di testing.

1. In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Visualizzare che la nuova regola del journal è stata creata correttamente in Exchange Management PowerShell.

## <a name="next-step"></a>Passaggio successivo

Esplorare le [funzionalità e le funzionalità di](m365-enterprise-test-lab-guides.md#information-protection) protezione delle informazioni aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)
