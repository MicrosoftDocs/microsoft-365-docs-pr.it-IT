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
description: Utilizzare questo articolo per ulteriori informazioni sull'abilitazione e sulla configurazione della gestione degli accessi con privilegi in Office 365.
ms.openlocfilehash: d75a8944cdacb6df2d6ee6570c0ce327d0e7ae00
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341204"
---
# <a name="get-started-with-privileged-access-management"></a>Introduzione alla gestione degli accessi con privilegi

In questo argomento viene illustrata la possibilità di abilitare e configurare la gestione degli accessi con privilegi nell'organizzazione. È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare accesso privilegiato.

## <a name="before-you-begin"></a>Informazioni preliminari

Prima di iniziare a utilizzare la gestione degli accessi con privilegi, è necessario confermare la [sottoscrizione Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e gli eventuali componenti aggiuntivi. Per accedere e utilizzare la gestione degli accessi con privilegi, è necessario che l'organizzazione disponga di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:

- Sottoscrizione Microsoft 365 E5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 E3 (o abbonamento a Office 365 E3 + sottoscrizione Enterprise Mobility and Security E3) + componente aggiuntivo Microsoft 365 E5 Compliance
- Qualsiasi sottoscrizione Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Business + Microsoft 365 E5 Insider Risk Management Add-on  
- Sottoscrizione Microsoft 365 a5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 a3 (o abbonamento a Office 365 a3 + sottoscrizione Enterprise Mobility and Security a3) + componente aggiuntivo Microsoft a5 Compliance
- Qualsiasi componente aggiuntivo Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Education + Microsoft 365 a5 Insider Risk Management Add-on
- Abbonamento a Office 365 Enterprise E5 (a pagamento o versione di valutazione)
- Abbonamento a Office 365 Enterprise E3 + il componente aggiuntivo Office 365 Advanced Compliance (non più disponibile per le nuove sottoscrizioni, vedere note)

Gli utenti che inviano e rispondono alle richieste di gestione degli accessi con privilegi devono essere assegnati a una delle licenze precedenti.

>[!IMPORTANT]
>La conformità avanzata di Office 365 non viene più venduta come sottoscrizione autonoma. Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse funzionalità di conformità o aggiuntive.

Se non si dispone di un piano Office 365 Enterprise E5 esistente e si desidera tentare la gestione degli accessi con privilegi, è possibile [aggiungere microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) alla propria sottoscrizione a Office 365 esistente oppure [iscriversi per una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Microsoft 365 Enterprise E5.

## <a name="enable-and-configure-privileged-access-management"></a>Abilitare e configurare la gestione degli accessi con privilegi

Eseguire la procedura seguente per configurare e usare l'accesso privilegiato nell'organizzazione:

- [Passaggio 1: creare un gruppo del responsabile approvazione](privileged-access-management-configuration.md#step1)

    Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi deve disporre dell'autorizzazione di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati. Qualsiasi utente che fa parte del gruppo responsabili approvazione è in grado di approvare le richieste di accesso. Questo gruppo è abilitato mediante la creazione di un gruppo di sicurezza abilitato alla posta elettronica in Office 365.

- [Passaggio 2: abilitare l'accesso con privilegi](privileged-access-management-configuration.md#step2)

    L'accesso con privilegi deve essere abilitato in modo esplicito in Office 365 con il gruppo di approvazione predefinito, incluso un set di account di sistema che si desidera escludere dal controllo di accesso alla gestione degli accessi con privilegi.

- [Passaggio 3: creare un criterio di accesso](privileged-access-management-configuration.md#step3)

    La creazione di un criterio di approvazione consente di definire i requisiti di approvazione specifici con ambito a singole attività. Le opzioni relative al tipo di approvazione sono **automatiche** o **manuali**.

- [Passaggio 4: invio/approvazione delle richieste di accesso privilegiate](privileged-access-management-configuration.md#step4)

    Una volta abilitata, l'accesso con privilegi richiede le approvazioni per qualsiasi attività in cui sia stato definito un criterio di approvazione associato. Per le attività incluse in un criterio di approvazione, è necessario che gli utenti dispongano dell'autorizzazione di accesso e che dispongano delle autorizzazioni necessarie per eseguire l'attività.

Dopo aver concesso l'approvazione, l'utente richiedente può eseguire l'attività desiderata e l'accesso privilegiato autorizzerà ed eseguirà l'attività per conto dell'utente. L'approvazione rimane valida per la durata richiesta (la durata predefinita è di 4 ore), durante la quale il richiedente può eseguire l'attività desiderata più volte. Tutte queste esecuzioni vengono registrate e rese disponibili per il controllo di sicurezza e conformità. 

>[!NOTE]
>Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to Connect to Exchange Online PowerShell with your Office 365 Credentials. Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione per l'utilizzo dei passaggi per abilitare l'accesso privilegiato durante la connessione a PowerShell di Exchange Online. La connessione con l'autenticazione a più fattori consente di creare un token OAuth utilizzato dall'accesso privilegiato per la firma delle richieste.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Passaggio 1: creare un gruppo del responsabile approvazione

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **gruppi**  >  **aggiungere un gruppo**.

3. Selezionare **gruppo di sicurezza abilitato alla posta elettronica** e quindi completare il **nome**, l' **indirizzo di posta elettronica del gruppo**e i campi **Descrizione** per il nuovo gruppo.

4. Salvare il gruppo. Il gruppo può richiedere alcuni minuti completamente configurati e comparire nell'interfaccia di amministrazione di Microsoft 365.

5. Selezionare il gruppo del nuovo responsabile approvazione e selezionare **modifica** per aggiungere gli utenti al gruppo.

6. Salvare il gruppo.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Passaggio 2: abilitare l'accesso con privilegi

### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **org**impostazioni di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Abilitare il controllo **Richiedi approvazioni per le attività privilegiate** .

4. Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **gruppo dei responsabili approvazione predefiniti**.

5. **Salva** e **Chiudi**.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per abilitare l'accesso con privilegi e assegnare il gruppo del responsabile dell'approvazione, eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Esempio:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>La funzionalità account di sistema è disponibile per garantire che alcuni automatismi all'interno delle organizzazioni possano funzionare senza dipendenza dall'accesso privilegiato, tuttavia è consigliabile che tali esclusioni siano eccezionali e quelle consentite debbano essere approvate e controllate regolarmente.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Passaggio 3: creare un criterio di accesso

È possibile creare e configurare fino a 30 criteri di accesso privilegiato per l'organizzazione.

### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **org**impostazioni di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **Configure policies** e selezionare **Add a Policy**.

5. Nei campi a discesa selezionare i valori corretti per l'organizzazione:
    
    **Tipo di criterio**: attività, ruolo o gruppo di ruoli

    **Ambito di criteri**: Exchange

    **Nome criterio**: scegliere tra i criteri disponibili

    **Tipo di approvazione**: manuale o automatico

    **Gruppo di approvazione**: selezionare il gruppo responsabili approvazione creato nel passaggio 1

6. Selezionare **Crea** e quindi **Chiudi**. È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per creare e definire un criterio di approvazione, eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Esempio:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Passaggio 4: invio/approvazione delle richieste di accesso privilegiate

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Richiesta di autorizzazione all'elevazione per l'esecuzione di attività privilegiate

Le richieste di accesso con privilegi sono valide per un massimo di 24 ore dopo l'invio della richiesta. Se non è stato approvato o negato, le richieste scadono e Access non è approvato.

#### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le proprie credenziali.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **org**impostazioni di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **nuova richiesta**. Nei campi a discesa selezionare i valori corretti per l'organizzazione:

    **Tipo di richiesta**: attività, ruolo o gruppo di ruoli

    **Ambito delle richieste**: Exchange

    **Richiesta per**: selezionare i criteri disponibili

    **Durata (ore)**: numero di ore di accesso richiesto. Non è previsto un limite per il numero di ore che è possibile richiedere.

    **Commenti**: campo di testo per i commenti relativi alla richiesta di accesso

5. Selezionare **Salva** e quindi **Chiudi**. La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per creare e inviare una richiesta di approvazione al gruppo del responsabile dell'approvazione:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Esempio:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Visualizzare lo stato delle richieste di elevazione

Dopo la creazione di una richiesta di approvazione, lo stato della richiesta di elevazione può essere esaminato nell'interfaccia di amministrazione o in Exchange Management PowerShell utilizzando l'ID della richiesta associato.

#### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le proprie credenziali.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **org**impostazioni di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **Visualizza** per filtrare le richieste inviate mediante lo stato **in sospeso**, **approvato**, **negato**o **protetto dall'archivio dei clienti** .

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare lo stato di una richiesta di approvazione per un ID di richiesta specifico:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Esempio:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Approvazione di una richiesta di autorizzazione elevazione

Quando viene creata una richiesta di approvazione, i membri del gruppo di approvazione pertinente ricevono una notifica tramite posta elettronica e possono approvare la richiesta associata all'ID della richiesta. Il richiedente riceve una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.

#### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le proprie credenziali.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **org**impostazioni di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare una richiesta elencata per visualizzare i dettagli e per eseguire l'azione sulla richiesta.

5. Selezionare **approva** per approvare la richiesta oppure selezionare **Nega** per rifiutare la richiesta. Le richieste approvate in precedenza possono avere accesso revocato selezionando **revoca**.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per approvare una richiesta di autorizzazione elevazione, eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Esempio:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Per rifiutare una richiesta di autorizzazione elevazione, eseguire il comando seguente in PowerShell di Exchange Online:

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

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **org**impostazioni di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **Configure policies**.

5. Selezionare il criterio che si desidera eliminare, quindi selezionare **Rimuovi criterio**.

6. Selezionare **Chiudi**.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per eliminare un criterio di accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Disabilitare l'accesso con privilegi in Office 365

Se necessario, è possibile disabilitare la gestione degli accessi con privilegi per l'organizzazione. La disabilitazione dell'accesso con privilegi non comporta l'eliminazione di criteri di approvazione associati o gruppi di approvatori.

### <a name="in-the-microsoft-365-admin-center"></a>Nell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**  >  **org**impostazioni di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Per disabilitare l'accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:

```PowerShell
Disable-ElevatedAccessControl
```
