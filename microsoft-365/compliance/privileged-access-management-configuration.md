---
title: Introduzione alla gestione degli accessi con privilegi
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Utilizzare questo articolo per ulteriori informazioni sull'abilitazione e la configurazione della gestione degli accessi con privilegi in Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126533"
---
# <a name="get-started-with-privileged-access-management"></a>Introduzione alla gestione degli accessi con privilegi

Questo argomento illustra come abilitare e configurare la gestione degli accessi con privilegi nell'organizzazione. È possibile utilizzare l'Microsoft 365 di amministrazione o Exchange Management PowerShell per gestire e usare l'accesso con privilegi.

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare a usare la gestione degli accessi con privilegi, è consigliabile confermare la sottoscrizione Microsoft 365 [e](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) i componenti aggiuntivi. Per accedere e utilizzare la gestione degli accessi con privilegi, l'organizzazione deve disporre di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:

- Microsoft 365 E5 (versione di valutazione o a pagamento)
- Microsoft 365 E3 (o Office 365 E3 + Enterprise mobility e security E3) + il Microsoft 365 E5 Compliance aggiuntivo
- Qualsiasi Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Business e il componente aggiuntivo Microsoft 365 E5 Insider Risk Management  
- Microsoft 365 Sottoscrizione A5 (versione di valutazione o a pagamento)
- Microsoft 365 Sottoscrizione A3 (o Office 365 A3 + Enterprise Mobility and Security A3) + componente aggiuntivo Conformità Microsoft A5
- Qualsiasi Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Education + il componente aggiuntivo per la gestione dei rischi di Microsoft 365 A5 Insider
- Office 365 Enterprise Abbonamento E5 (versione di valutazione o a pagamento)
- Office 365 Enterprise Sottoscrizione E3 + Office 365 Advanced Compliance componente aggiuntivo (non più disponibile per le nuove sottoscrizioni, vedere nota)

Agli utenti che inviano e rispondono alle richieste di gestione degli accessi con privilegi deve essere assegnata una delle licenze precedenti.

>[!IMPORTANT]
>Office 365 Advanced Compliance non viene più venduto come abbonamento autonomo. Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse o ulteriori funzionalità di conformità.

Se non si dispone di un piano Office 365 Enterprise E5 esistente e si desidera provare la gestione degli accessi con privilegi, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento Office 365 esistente o iscriversi [a](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 Enterprise E5.

## <a name="enable-and-configure-privileged-access-management"></a>Abilitare e configurare la gestione degli accessi con privilegi

Seguire questa procedura per configurare e usare l'accesso con privilegi nell'organizzazione:

- [Passaggio 1: Creare un gruppo di responsabili approvazione](privileged-access-management-configuration.md#step1)

    Prima di iniziare a usare l'accesso privilegiato, determinare chi ha bisogno dell'autorità di approvazione per le richieste in arrivo per l'accesso ad attività elevate e privilegiate. Qualsiasi utente che fa parte del gruppo Responsabili approvazione può approvare le richieste di accesso. Questo gruppo viene abilitato creando un gruppo di sicurezza abilitato alla posta elettronica in Office 365.

- [Passaggio 2: Abilitare l'accesso con privilegi](privileged-access-management-configuration.md#step2)

    L'accesso privilegiato deve essere abilitato in modo esplicito in Office 365 con il gruppo responsabile approvazione predefinito, incluso un set di account di sistema da escludere dal controllo di Privileged Access Management.

- [Passaggio 3: Creare un criterio di accesso](privileged-access-management-configuration.md#step3)

    La creazione di criteri di approvazione consente di definire i requisiti di approvazione specifici per l'ambito delle singole attività. Sono disponibili due tipi di approvazione: **Automatica** e **Manuale**.

- [Passaggio 4: Inviare/approvare richieste di accesso con privilegi](privileged-access-management-configuration.md#step4)

    Una volta abilitato, l'accesso privilegiato richiede l'approvazione per tutte le attività con un criterio di approvazione associato definito. Per le attività incluse in un criterio di approvazione, gli utenti devono richiedere e ottenere l'approvazione dell'accesso per avere le autorizzazioni necessarie per eseguire l'attività.

Una volta concessa l'approvazione, l'utente richiedente può eseguire l'attività prevista e l'accesso privilegiato autorizzerà l'esecuzione dell'attività per conto dell'utente. L'approvazione rimane valida per la durata richiesta (la durata predefinita è di 4 ore), durante la quale il richiedente può eseguire l'attività prevista più volte. Tutte queste esecuzioni vengono registrate e sono disponibili per il controllo di sicurezza e conformità. 

>[!NOTE]
>Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire i passaggi descritti in [Connessione Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) usando l'autenticazione a più fattori per connettersi a Exchange Online PowerShell con le credenziali Office 365. Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione per utilizzare la procedura per abilitare l'accesso con privilegi durante la connessione a Exchange Online PowerShell. La connessione con l'autenticazione a più fattori crea un token OAuth utilizzato dall'accesso con privilegi per firmare le richieste.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Passaggio 1: Creare un gruppo di responsabili approvazione

1. Accedere [all'Microsoft 365 di amministrazione usando](https://admin.microsoft.com) le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione passare a **Gruppi**  >  **Aggiungere un gruppo.**

3. Selezionare **il gruppo di sicurezza abilitato alla** posta elettronica e quindi completare i campi **Nome,** Indirizzo **di** posta elettronica gruppo e **Descrizione** per il nuovo gruppo.

4. Salvare il gruppo. La configurazione completa del gruppo e la visualizzazione nell'interfaccia di amministrazione di Microsoft 365 possono richiedere alcuni minuti.

5. Selezionare il gruppo del nuovo responsabile approvazione e selezionare **Modifica** per aggiungere utenti al gruppo.

6. Salvare il gruppo.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Passaggio 2: Abilitare l'accesso con privilegi

### <a name="in-the-microsoft-365-admin-center"></a>Nell'Microsoft 365 admin center

1. Accedi [all'Microsoft 365 admin center](https://admin.microsoft.com) usando le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **Org Impostazioni** Sicurezza & Accesso con privilegi di  >    >  **privacy**.

3. Abilitare il **controllo Richiedi approvazioni per le attività con** privilegi.

4. Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **gruppo Responsabili approvazione predefiniti**.

5. **Salva** e **chiudi**.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per abilitare l'accesso con privilegi e assegnare il gruppo del responsabile approvazione, eseguire il comando seguente in Exchange Online PowerShell:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Esempio:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>La funzionalità degli account di sistema è disponibile per garantire che determinate automazioni all'interno delle organizzazioni possano funzionare senza dipendenza dall'accesso privilegiato, tuttavia è consigliabile che tali esclusioni siano eccezionali e che quelle consentite debbano essere approvate e verificate regolarmente.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Passaggio 3: Creare un criterio di accesso

È possibile creare e configurare fino a 30 criteri di accesso con privilegi per l'organizzazione.

### <a name="in-the-microsoft-365-admin-center"></a>Nell'Microsoft 365 admin center

1. Accedi [all'Microsoft 365 admin center](https://admin.microsoft.com) usando le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **Org Impostazioni** Sicurezza & Accesso con privilegi di  >    >  **privacy**.

3. Selezionare **Gestisci criteri e richieste di accesso**.

4. Selezionare **Configura criteri** e selezionare Aggiungi un **criterio.**

5. Nell'elenco a discesa selezionare i valori appropriati per l'organizzazione:
    
    **Tipo di criterio**: Attività, Ruolo o Gruppo di ruoli

    **Ambito del criterio**: Exchange

    **Nome del criterio**: selezionare uno dei criteri disponibili

    **Tipo di approvazione**: Manuale o Automatica

    **Gruppo di approvazione**: selezionare il gruppo Responsabili approvazione creato nel passaggio 1

6. Selezionare **Crea** e quindi **Chiudi.** La configurazione e l'a attivazione completa del criterio potrebbero richiedere alcuni minuti.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per creare e definire un criterio di approvazione, eseguire il comando seguente in Exchange Online PowerShell:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Esempio:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Passaggio 4: Inviare/approvare richieste di accesso con privilegi

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Richiesta di autorizzazione di elevazione per eseguire attività con privilegi

Le richieste di accesso privilegiato sono valide per un massimo di 24 ore dopo l'invio della richiesta. Se non approvate o negate, le richieste scadono e l'accesso non viene concesso.

#### <a name="in-the-microsoft-365-admin-center"></a>Nell'Microsoft 365 admin center

1. Accedi [all'Microsoft 365 admin center](https://admin.microsoft.com) usando le credenziali.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **Org Impostazioni** Sicurezza & Accesso con privilegi di  >    >  **privacy**.

3. Selezionare **Gestisci criteri e richieste di accesso**.

4. Selezionare **Nuova richiesta.** Nell'elenco a discesa selezionare i valori appropriati per l'organizzazione:

    **Tipo di richiesta**: Attività, Ruolo o Gruppo di ruoli

    **Ambito della richiesta**: Exchange

    **Richiesta di**: selezionare uno dei criteri disponibili

    **Durata (ore)**: numero di ore di accesso richiesto. Non esiste un limite al numero di ore che possono essere richieste.

    **Commenti:** campo di testo per i commenti correlati alla richiesta di accesso

5. Selezionare **Salva** e quindi **Chiudi.** La richiesta verrà inviata al gruppo del responsabile approvazione tramite posta elettronica.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Eseguire il comando seguente in Exchange Online PowerShell per creare e inviare una richiesta di approvazione al gruppo del responsabile approvazione:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Esempio:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Visualizzare lo stato delle richieste di elevazione

Dopo aver creato una richiesta di approvazione, lo stato della richiesta di elevazione può essere esaminato nell'interfaccia di amministrazione o in Exchange Management PowerShell usando l'ID richiesta associato.

#### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere [all'Microsoft 365 di amministrazione con](https://admin.microsoft.com) le credenziali.

2. Nell'interfaccia di amministrazione passare a **Impostazioni**  >  **Org Impostazioni** Sicurezza & Accesso con privilegi di  >    >  **privacy**.

3. Selezionare **Gestisci criteri e richieste di accesso**.

4. Selezionare **Visualizza per** filtrare le richieste inviate in base allo stato **In** **sospeso,** **Approvato,** Rifiutato o **Customer Lockbox.**

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Eseguire il comando seguente in Exchange Online PowerShell per visualizzare lo stato di una richiesta di approvazione per un ID richiesta specifico:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Esempio:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Approvazione di una richiesta di autorizzazione di elevazione

Quando viene creata una richiesta di approvazione, i membri del gruppo di responsabili approvazione pertinente ricevono una notifica tramite posta elettronica e possono approvare la richiesta associata all'ID richiesta. Il richiedente riceve notifica dell'approvazione o rifiuto della richiesta tramite posta elettronica.

#### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere [all'Microsoft 365 di amministrazione con](https://admin.microsoft.com) le credenziali.

2. Nell'interfaccia di amministrazione passare a **Impostazioni**  >  **Org Impostazioni** Sicurezza & Accesso con privilegi di  >    >  **privacy**.

3. Selezionare **Gestisci criteri e richieste di accesso**.

4. Selezionare una richiesta elencata per visualizzare i dettagli ed eseguire un'azione sulla richiesta.

5. Selezionare **Approva** per approvare la richiesta o **Nega** per rifiutare la richiesta. Le richieste approvate in precedenza possono avere accesso revocato selezionando **Revoca**.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per approvare una richiesta di autorizzazione di elevazione dei privilegi, eseguire il comando seguente in Exchange Online PowerShell:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Esempio:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Per negare una richiesta di autorizzazione di elevazione dei privilegi, eseguire il comando seguente in Exchange Online PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Esempio:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Eliminare un criterio di accesso con privilegi in Office 365

Se non è più necessario nell'organizzazione, è possibile eliminare un criterio di accesso con privilegi.

### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere [all'Microsoft 365 di amministrazione usando](https://admin.microsoft.com) le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione passare a **Impostazioni**  >  **Org Impostazioni** Sicurezza & Accesso con privilegi di  >    >  **privacy**.

3. Selezionare **Gestisci criteri e richieste di accesso**.

4. Selezionare **Configura criteri**.

5. Seleziona il criterio che vuoi eliminare, quindi seleziona **Rimuovi criterio.**

6. Selezionare **Chiudi**.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per eliminare un criterio di accesso con privilegi, eseguire il comando seguente in Exchange Online PowerShell:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Disabilitare l'accesso con privilegi in Office 365

Se necessario, è possibile disabilitare la gestione degli accessi con privilegi per l'organizzazione. La disabilitazione dell'accesso con privilegi non elimina i criteri di approvazione o i gruppi di responsabili approvazione associati.

### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere [all'Microsoft 365 di amministrazione con](https://admin.microsoft.com) le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **Org Impostazioni** Sicurezza & Accesso con privilegi di  >    >  **privacy**.

3. Abilitare **l'opzione Richiedi approvazioni per il controllo dell'accesso con** privilegi.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per disabilitare l'accesso con privilegi, eseguire il comando seguente in Exchange Online PowerShell:

```PowerShell
Disable-ElevatedAccessControl
```
