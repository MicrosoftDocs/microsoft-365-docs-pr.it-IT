---
title: Gestione di gruppi in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori nelle organizzazioni autonome di Exchange Online Protection (EOP) possono imparare a creare, modificare e rimuovere gruppi di distribuzione e gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell di Exchange Online Protection (EOP) autonomo.
ms.openlocfilehash: 4f1dbdb503f8baf02b7dd763dbf7fc6acdf5771a
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352192"
---
# <a name="manage-groups-in-eop"></a>Gestire gruppi in Exchange Online Protection

Nelle organizzazioni standalone di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile creare, modificare e rimuovere i seguenti tipi di gruppi:

- **Gruppi di distribuzione**: un insieme di utenti di posta o di altri gruppi di distribuzione. Ad esempio, teams o altri gruppi ad hoc che hanno la necessità di ricevere o inviare messaggi di posta elettronica in un'area di interesse comune. I gruppi di distribuzione sono esclusivamente per la distribuzione dei messaggi di posta elettronica e non sono entità di sicurezza (non possono avere le autorizzazioni assegnate).

- **Gruppi di sicurezza abilitati alla posta elettronica**: un insieme di utenti di posta elettronica e altri gruppi di sicurezza che hanno bisogno delle autorizzazioni di accesso per i ruoli di amministratore Ad esempio, è possibile assegnare autorizzazioni di amministratore a un gruppo specifico di utenti in modo che possano configurare le impostazioni di protezione da posta indesiderata e antimalware.

    > [!NOTE]
    > <ul><li>Per impostazione predefinita, i nuovi gruppi di sicurezza abilitati alla posta elettronica rifiutano i messaggi provenienti da mittenti esterni (non autenticati).</li><li>Non aggiungere gruppi di distribuzione ai gruppi di sicurezza abilitati alla posta elettronica.</li></ul>.

È possibile gestire i gruppi nell'interfaccia di amministrazione di Exchange (EAC) e in EOP PowerShell autonomo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Quando si gestiscono i gruppi in EOP standalone PowerShell, è possibile che si verifichi la limitazione. Nelle procedure di PowerShell di questo argomento viene utilizzato un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. In particolare, è necessario il ruolo gruppi di distribuzione, assegnato ai gruppi di ruoli OrganizationManagement (Global Admins) e RecipientManagement per impostazione predefinita. Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Utilizzare l'interfaccia di amministrazione di Exchange per gestire i gruppi di distribuzione

### <a name="use-the-eac-to-create-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per la creazione di gruppi

1. Nell'EAC, accedere a **Destinatari** \> **Gruppi**.

2. Fare clic su **nuova** ![ icona nuova ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare una delle opzioni seguenti:

   - **Gruppo di distribuzione**

   - **Gruppo di sicurezza abilitato alla posta elettronica**

3. Nella pagina nuovo gruppo che si apre, configurare le impostazioni seguenti. Sono necessarie le impostazioni contrassegnate con un <sup>\*</sup> .

   - <sup>\*</sup>**Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nella riga a: quando il messaggio di posta elettronica viene inviato a questo gruppo e nell'elenco **gruppi** nell'interfaccia di amministrazione di Exchange. Il nome visualizzato è obbligatorio, deve essere univoco e deve essere facile da usare per consentire agli utenti di riconoscere le proprie esigenze.

   - <sup>\*</sup>**Alias**: utilizzare questa casella per digitare il nome dell'alias per il gruppo. L'alias non può superare i 64 caratteri e deve essere univoco. Quando un utente digita l'alias nella riga a di un messaggio di posta elettronica, viene risolto nel nome visualizzato del gruppo.

   - <sup>\*</sup>**Indirizzo di posta elettronica**: l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo (@) e da un dominio sul lato destro. Per impostazione predefinita, il valore di **alias** viene utilizzato per il valore alias, ma è possibile modificarlo. Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.

   - **Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.

   - <sup>\*</sup>**Proprietari**: il proprietario di un gruppo può gestire l'appartenenza ai gruppi. Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario. Ogni gruppo deve presentare almeno un proprietario.

     Per aggiungere proprietari, fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) . Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

     Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Membri**: aggiungere e rimuovere membri del gruppo.

     Per aggiungere membri, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) . Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

     Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. Al termine, fare clic su **Salva** per creare il gruppo di distribuzione.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare gruppi di distribuzione

1. Nell'EAC, accedere a **Destinatari** \> **Gruppi**.

2. Nell'elenco dei gruppi, selezionare il gruppo di distribuzione o il gruppo di sicurezza abilitato alla posta elettronica che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) .

3. Nella pagina delle proprietà del gruppo di distribuzione visualizzata, fare clic su una delle schede seguenti per visualizzare o modificare le proprietà.

   Al termine, scegliere **Salva**.

#### <a name="general"></a>Generale

Utilizzare questa scheda per visualizzare o modificare le informazioni di base sul gruppo.

- **Nome visualizzato**: questo nome viene visualizzato nella rubrica, nella riga a quando il messaggio di posta elettronica viene inviato a questo gruppo e nell' **elenco gruppi**. Il nome visualizzato è obbligatorio e deve essere un nome descrittivo facilmente riconoscibile dagli utenti. Inoltre, deve essere univoco nel dominio in uso.

  Se sono stati implementati criteri di denominazione dei gruppi, il nome visualizzato deve essere conforme al formato di denominazione definito dai criteri.

- **Alias**: questa è la parte dell'indirizzo di posta elettronica che viene visualizzata a sinistra del simbolo di chiocciola (@). Se si modifica l'alias, verrà modificato anche l'indirizzo SMTP primario del gruppo in modo che contenga il nuovo alias. Inoltre, l'indirizzo di posta elettronica con il precedente alias verrà conservato come indirizzo proxy del gruppo.

- **Indirizzo di posta elettronica**: l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo (@) e da un dominio sul lato destro. Per impostazione predefinita, il valore di **alias** viene utilizzato per il valore alias, ma è possibile modificarlo. Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.

- **Descrizione**: questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.

#### <a name="ownership"></a>Ownership

Utilizzare questa scheda per assegnare i proprietari del gruppo. Il proprietario di un gruppo può gestire l'appartenenza A un gruppo. Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario. Ogni gruppo deve presentare almeno un proprietario.

Per aggiungere proprietari, fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) . Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario e quindi fare clic su **Add->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

Per rimuovere un proprietario, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Appartenenza

Utilizzare questa scheda per aggiungere o rimuovere membri del gruppo. Non è necessario che i proprietari del gruppo siano membri del gruppo.

Per aggiungere membri, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) . Nella finestra di dialogo che viene visualizzata, individuare e selezionare un destinatario o un gruppo, quindi fare clic su **Add->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

Per rimuovere un membro, selezionarlo e quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere i gruppi

1. Nell'EAC, accedere a **Destinatari** \> **Gruppi**.

2. Nell'elenco dei gruppi, selezionare il gruppo di distribuzione che si desidera rimuovere, quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Utilizzo di PowerShell per gestire i gruppi

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Utilizzo di PowerShell EOP autonomo per visualizzare i gruppi

Per restituire un elenco riepilogativo di tutti i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica in EOP PowerShell autonomo, eseguire il comando riportato di seguito:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Per restituire l'elenco dei membri del gruppo, sostituire \< groupIdentity \> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Utilizzo di PowerShell EOP autonomo per creare gruppi

Per creare gruppi di distribuzione o gruppi di sicurezza abilitati alla posta elettronica in EOP PowerShell autonomo, utilizzare la sintassi seguente:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Note**:

- Il parametro _Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco. Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.

- Se non si utilizza il parametro _alias_ , il parametro _Name_ viene utilizzato per il valore alias. Gli spazi vengono rimossi e i caratteri non supportati vengono convertiti in punti interrogativi (?).

- Se non si utilizza il parametro _PrimarySmtpAddress_ , il valore alias viene utilizzato nel parametro _PrimarySmtpAddress_ .

- Se non si utilizza il parametro _Type_ , il valore predefinito è Distribution.

In questo esempio viene creato un gruppo di distribuzione denominato amministratori IT con le proprietà specificate.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Utilizzo di PowerShell EOP autonomo per modificare i gruppi

Per modificare i gruppi in EOP autonomo PowerShell, utilizzare la sintassi seguente:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In questo esempio viene utilizzata la modifica dell'indirizzo SMTP primario (denominato anche indirizzo di risposta) del gruppo Seattle Employees in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

In questo esempio vengono sostituiti i membri correnti del gruppo del team di sicurezza con Kitty Petersen e Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

In questo esempio viene aggiunto un nuovo utente denominato Tyson Fawcett al gruppo denominato Security Team mantenendo i membri correnti del gruppo.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Rimuovere un gruppo tramite Windows PowerShell remoto

In questo esempio viene rimosso il gruppo di distribuzione denominato amministratori IT.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta creazione, modifica o rimozione di un gruppo di distribuzione o di un gruppo di sicurezza abilitato alla posta elettronica, eseguire una delle operazioni seguenti:

- Nell'EAC, accedere a **Destinatari** \> **Gruppi**. Verificare che il gruppo sia elencato (o non elencato) e verificare il valore del **tipo di gruppo** . Selezionare il gruppo e visualizzare le informazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) per visualizzare le impostazioni.

- In EOP standalone PowerShell, eseguire il comando riportato di seguito per verificare che il gruppo sia elencato (o non sia elencato):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Sostituire \< groupIdentity \> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito per verificare le impostazioni:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Per visualizzare i membri del gruppo, sostituire \< groupIdentity \> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando riportato di seguito:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
