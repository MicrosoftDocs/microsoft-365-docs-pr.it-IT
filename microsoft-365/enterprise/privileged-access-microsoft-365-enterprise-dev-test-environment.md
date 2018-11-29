---
title: Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Utilizzare questa guida dei laboratori di testing per abilitare la gestione degli accessi privilegiato l'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868287"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise

Con le istruzioni riportate in questo articolo, configurare la gestione dei privilegi di accesso per aumentare la protezione dell'ambiente di test Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera configurare la gestione dei privilegi di accesso in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare l'accesso con privilegi management in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test di gestione con privilegi di accesso non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Di seguito viene fornito come opzione in modo che è possibile testare con privilegi accedere a gestione e sperimentare in un ambiente che rappresenta una tipica organizzazione. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configurare la gestione dei privilegi di accesso

In questa fase, configurare un gruppo di responsabili approvazione e abilitare la gestione dell'accesso con privilegi per l'ambiente di testing Microsoft 365 Enterprise. Per ulteriori dettagli e una panoramica dei privilegi di accesso gestione, vedere [accesso privilegiato management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Eseguire la procedura seguente per configurare e utilizzare i privilegi di accesso nella propria organizzazione Office 365:

- [Passaggio 1: Creare il gruppo del revisore](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    Prima di iniziare a utilizzare accesso privilegi, determinare chi avrà autorità approvazione delle richieste in ingresso per l'accesso alle attività con privilegi elevate e privilegiata. Qualsiasi utente che fa parte del gruppo dei responsabili approvazione saranno in grado di approvare le richieste di accesso. Questa opzione è attivata mediante la creazione di un gruppo di protezione abilitati alla posta elettronica in Office 365. Creare un nuovo gruppo di sicurezza denominato "Revisori con privilegi di accesso" nell'ambiente di testing e aggiungere il "utente 3" creato in precedenza nei passaggi Guida laboratorio di testing precedente.

- [Passaggio 2: Abilitare l'accesso con privilegiato](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    Accesso privilegiato deve essere attivata in modo esplicito in Office 365 gruppo responsabile approvazione predefinito, incluso un set di account di sistema che si desidera vengano esclusi dal controllo dell'accesso Gestione accesso privilegiato. È necessario abilitare l'accesso con privilegiato nella propria organizzazione Office 365 prima di avviare fase 3 della presente Guida.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Verificare che l'approvazione è necessaria per le attività con privilegi elevate e privilegiata
In questa fase, verificare che sia attivo il criterio di accesso con privilegi e gli utenti richiedono l'approvazione di eseguire attività con privilegi elevate e privilegiata definita.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Possibilità di eseguire un'attività non è definita nei criteri di accesso con privilegi di testing

Per prima cosa, connettersi a PowerShell per Exchange Management con le credenziali di un utente configurato come amministratore globale nell'ambiente di testing e tenta di creare una nuova regola del Journal. L'attività [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) non è attualmente definito nei criteri di accesso con privilegi per l'organizzazione.

1. Nel computer locale, aprire e accedere ai di Exchange Online Remote PowerShell Module presso **Microsoft Corporation** > **Microsoft Exchange Online PowerShell modulo remoto** tramite Amministratore globale per gli account per l'ambiente di testing.

2. In Exchange Management Powershell, creare una nuova regola del Journal dell'organizzazione:

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. Visualizzazione in cui è stata correttamente la nuova regola di Journal creata in Exchange PowerShell Management.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Creare un nuovo criterio di accesso con privilegi per l'attività New-JournalRule

> [!NOTE]
> Se non sono già stati completati i passaggi 1 e 2 della fase 2 della presente Guida, essere certi segui i passaggi per creare gruppo un responsabile dell'approvazione denominato "Principio dei privilegi responsabili approvazione accesso" e consentire l'accesso con privilegiato nell'ambiente di testing.

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali l'account amministratore globale per l'ambiente di testing.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare **Configura criteri** e selezionare **Aggiungi un criterio**.

5. Dai campi a discesa, selezionare o immettere i valori seguenti:
    
    **Tipo di criterio**: attività

    **Ambito dei criteri**: Exchange

    **Nome del criterio**: nuova regola di Journal

    **Tipo di approvazione**: manuale

    **Gruppo di approvazione**: responsabili approvazione con privilegi di accesso

6. Selezionare **Crea** e quindi **Chiudi**. Potrebbe richiedere alcuni minuti per il criterio da configurare e abilitare completamente. Assicurarsi di concedere il tempo per il criterio da abilitare completamente prima di verificare la richiesta di approvazione nel passaggio successivo.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Richiesta di approvazione per l'attività New-JournalRule definito nei criteri di accesso con privilegi di testing

1. Nel computer locale, aprire e accedere ai di Exchange Online Remote PowerShell Module presso **Microsoft Corporation** > **Microsoft Exchange Online PowerShell modulo remoto** tramite un amministratore globale utilizzando gli account per il test ambiente.

2. In Exchange Management Powershell, creare una nuova regola del Journal dell'organizzazione:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Visualizza l'errore "Insufficiente autorizzazioni" in Exchange Management PowerShell:

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Richiedere l'accesso per creare una nuova regola di Journal tramite l'attività New-JournalRule

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando l'account amministratore globale per l'ambiente di testing.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare **nuova richiesta**. I campi di riepilogo a discesa, selezionare i valori appropriati per l'organizzazione:

    **Tipo di richiesta**: attività

    **Richiedere ambito**: Exchange

    **Richiedere per**: nuova regola di Journal

    **Durata (ore)**: 2

    **Commenti**: richiedere l'autorizzazione per creare una nuova regola di Journal

5. Selezionare **Salva** , quindi **Chiudi**. La richiesta verrà inviata al gruppo del revisore tramite posta elettronica.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Approvare le richieste di accesso con privilegi per la creazione di una nuova regola di Journal

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per l'utente 3 nell'ambiente di testing (membro del gruppo di protezione "Revisori con privilegi di accesso" nell'ambiente di testing).

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare la richiesta in sospeso e scegliere **Approva** per concedere l'accesso all'account amministratore globale per creare una nuova regola del Journal. Verrà inviato un messaggio di posta elettronica di notifica per confermare che è stato concesso l'approvazione per l'account amministratore globale (richiedente utente).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Crea una nuova regola di Journal con privilegi di accesso approvata per l'attività New-JournalRule test

1. Nel computer locale, aprire e accedere ai di Exchange Online Remote PowerShell Module presso **Microsoft Corporation** > **Microsoft Exchange Online PowerShell modulo remoto** tramite Amministratore globale per gli account per l'ambiente di testing.

2. In Exchange Management Powershell, creare una nuova regola del Journal dell'organizzazione:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Visualizzazione in cui è stata correttamente la nuova regola di Journal creata in Exchange PowerShell Management.

## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità aggiuntive [la protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) e le funzionalità nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)