---
title: Gestione di gruppi in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori delle organizzazioni di Exchange Online Protection (EOP) autonome possono imparare a creare, modificare e rimuovere gruppi di distribuzione e gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell di Exchange Online Protection (EOP) autonomo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d03b8a5129eb3b070f30de46b9b9c7bcc8e9898d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286802"
---
# <a name="manage-groups-in-eop"></a>Gestire gruppi in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

Nelle organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile creare, modificare e rimuovere i seguenti tipi di gruppi:

- **Gruppi di distribuzione**: raccolta di utenti di posta o di altri gruppi di distribuzione. Ad esempio, team o altri gruppi ad hoc che devono ricevere o inviare messaggi di posta elettronica in un'area comune di interesse. I gruppi di distribuzione sono esclusivamente per la distribuzione dei messaggi di posta elettronica e non sono entità di sicurezza (non possono avere autorizzazioni assegnate).

- **Gruppi di sicurezza abilitati alla posta** elettronica : raccolta di utenti di posta elettronica e altri gruppi di sicurezza che necessitano delle autorizzazioni di accesso per i ruoli di amministratore. Ad esempio, è possibile assegnare a un gruppo specifico di utenti le autorizzazioni di amministratore in modo che possano configurare le impostazioni di protezione da posta indesiderata e antimalware.

    > [!NOTE]
    >
    > - Per impostazione predefinita, i nuovi gruppi di sicurezza abilitati alla posta elettronica rifiutano i messaggi provenienti da mittenti esterni (non autenticati).
    >
    > - Non aggiungere gruppi di distribuzione ai gruppi di sicurezza abilitati alla posta elettronica.

È possibile gestire i gruppi nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell EOP autonomo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire l'interfaccia di amministrazione di Exchange, vedere l'interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Quando si gestiscono i gruppi in PowerShell EOP autonomo, è possibile che si verifichino limitazioni. Le procedure di PowerShell descritte in questo articolo utilizzano un metodo di elaborazione batch che determina un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection. In particolare, è necessario il ruolo Gruppi  **di**  distribuzione, assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari per impostazione predefinita. Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Problemi? Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Utilizzare l'interfaccia di amministrazione di Exchange per gestire i gruppi di distribuzione

### <a name="use-the-eac-to-create-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare gruppi

1. Nell'EAC, accedere a **Destinatari** \> **Gruppi**.

2. Fare **clic** ![ sull'icona ](../../media/ITPro-EAC-AddIcon.png) Nuovo e quindi selezionare una delle opzioni seguenti:

   - **Gruppo di distribuzione**

   - **Gruppo di sicurezza abilitato alla posta elettronica**

3. Nella pagina del nuovo gruppo visualizzata, configurare le impostazioni seguenti. Le impostazioni contrassegnate con un <sup>\*</sup> valore sono obbligatorie.

   - <sup>\*</sup>**Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nella riga A:  quando viene inviato un messaggio di posta elettronica a questo gruppo e nell'elenco Gruppi nell'interfaccia di amministrazione di Exchange. Il nome visualizzato è obbligatorio, deve essere univoco e deve essere descrittivo in modo che gli utenti riconosca cosa sia.

   - <sup>\*</sup>**Alias**: utilizzare questa casella per digitare il nome dell'alias per il gruppo. L'alias non può superare i 64 caratteri e deve essere univoco. Quando un utente digitare l'alias nella riga A di un messaggio di posta elettronica, viene risolto nel nome visualizzato del gruppo.

   - <sup>\*</sup>**Indirizzo di** posta elettronica : l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo di posta elettronica (@) e da un dominio sul lato destro. Per impostazione predefinita, il valore **di Alias** viene utilizzato per il valore dell'alias, ma è possibile modificarlo. Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.

   - **Descrizione:** questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.

   - <sup>\*</sup>**Proprietari:** il proprietario di un gruppo può gestire l'appartenenza al gruppo. Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario. Ogni gruppo deve presentare almeno un proprietario.

     Per aggiungere proprietari, fare clic **sull'icona** ![ ](../../media/ITPro-EAC-AddIcon.png) Aggiungi. Nella finestra di dialogo visualizzata individuare e selezionare un destinatario o un gruppo e quindi fare clic **su aggiungi ->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

     Per rimuovere un proprietario, selezionarlo e quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.

   - **Membri**: aggiungere e rimuovere membri del gruppo.

     Per aggiungere membri, fare clic **sull'icona** ![ ](../../media/ITPro-EAC-AddIcon.png) Aggiungi. Nella finestra di dialogo visualizzata individuare e selezionare un destinatario o un gruppo e quindi fare clic **su aggiungi ->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

     Per rimuovere un membro, selezionarlo e quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.

4. Al termine, fare clic su **Salva per** creare il gruppo di distribuzione.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare i gruppi di distribuzione

1. Nell'EAC, accedere a **Destinatari** \> **Gruppi**.

2. Nell'elenco dei gruppi selezionare il gruppo di distribuzione o il gruppo di sicurezza abilitato alla posta elettronica che si desidera modificare e quindi fare clic **sull'icona** ![ Modifica ](../../media/ITPro-EAC-AddIcon.png) modifica.

3. Nella pagina delle proprietà del gruppo di distribuzione visualizzata fare clic su una delle schede seguenti per visualizzare o modificare le proprietà.

   Al termine, fare clic su **Salva**.

#### <a name="general"></a>Generale

Utilizzare questa scheda per visualizzare o modificare le informazioni di base sul gruppo.

- **Nome visualizzato**: questo nome viene visualizzato nella rubrica, nella riga A quando viene inviato un messaggio di posta elettronica a questo gruppo e nell'elenco **Gruppi.** Il nome visualizzato è obbligatorio e deve essere un nome descrittivo facilmente riconoscibile dagli utenti. Inoltre, deve essere univoco nel dominio in uso.

  Se sono stati implementati criteri di denominazione dei gruppi, il nome visualizzato deve essere conforme al formato di denominazione definito dai criteri.

- **Alias**: si tratta della parte dell'indirizzo di posta elettronica visualizzata a sinistra del simbolo @. Se si modifica l'alias, verrà modificato anche l'indirizzo SMTP primario del gruppo in modo che contenga il nuovo alias. Inoltre, l'indirizzo di posta elettronica con il precedente alias verrà conservato come indirizzo proxy del gruppo.

- **Indirizzo di** posta elettronica : l'indirizzo di posta elettronica è costituito dall'alias a sinistra del simbolo di posta elettronica (@) e da un dominio sul lato destro. Per impostazione predefinita, il valore **di Alias** viene utilizzato per il valore dell'alias, ma è possibile modificarlo. Per il valore del dominio, fare clic sull'elenco a discesa e selezionare e accettare il dominio nell'organizzazione.

- **Descrizione:** questa descrizione viene visualizzata nella rubrica e nel riquadro dei dettagli nell'interfaccia di amministrazione di Exchange.

#### <a name="ownership"></a>Ownership

Utilizzare questa scheda per assegnare i proprietari del gruppo. Il proprietario di un gruppo può gestire l'appartenenza al gruppo. Per impostazione predefinita, la persona che crea un gruppo ne diventa proprietario. Ogni gruppo deve presentare almeno un proprietario.

Per aggiungere proprietari, fare clic **sull'icona** ![ ](../../media/ITPro-EAC-AddIcon.png) Aggiungi. Nella finestra di dialogo visualizzata, trovare e selezionare un destinatario, quindi fare clic su **aggiungi ->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

Per rimuovere un proprietario, selezionarlo e quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.

#### <a name="membership"></a>Appartenenza

Utilizzare questa scheda per aggiungere o rimuovere membri del gruppo. I proprietari del gruppo non devono essere membri del gruppo.

Per aggiungere membri, fare clic **sull'icona** ![ ](../../media/ITPro-EAC-AddIcon.png) Aggiungi. Nella finestra di dialogo visualizzata individuare e selezionare un destinatario o un gruppo e quindi fare clic **su aggiungi ->**. Ripetere questo passaggio tutte le volte necessarie. Al termine, fare clic su **OK**.

Per rimuovere un membro, selezionarlo e quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.

### <a name="use-the-eac-to-remove-groups"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere gruppi

1. Nell'EAC, accedere a **Destinatari** \> **Gruppi**.

2. Nell'elenco dei gruppi selezionare il gruppo di distribuzione che si desidera rimuovere e quindi fare clic **sull'icona** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rimuovi.

## <a name="use-powershell-to-manage-groups"></a>Usare PowerShell per gestire i gruppi

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Utilizzare PowerShell EOP autonomo per visualizzare i gruppi

Per ottenere un elenco riepilogativo di tutti i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica in PowerShell EOP autonomo, eseguire il comando seguente:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Per restituire l'elenco dei membri del gruppo, sostituire con il nome, l'alias o l'indirizzo di posta elettronica del gruppo \<GroupIdentity\> ed eseguire il comando seguente:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Utilizzare PowerShell EOP autonomo per creare gruppi

Per creare gruppi di distribuzione o gruppi di sicurezza abilitati alla posta elettronica in PowerShell EOP autonomo, utilizzare la sintassi seguente:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Note**:

- Il _parametro Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco. Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.

- Se non si utilizza il parametro _Alias,_ viene utilizzato il parametro _Name_ per il valore dell'alias. Gli spazi vengono rimossi e i caratteri non supportati vengono convertiti in punti interrogativi (?).

- Se non si utilizza il parametro _PrimarySmtpAddress,_ il valore alias viene utilizzato nel _parametro PrimarySmtpAddress._

- Se non si utilizza il parametro _Type,_ il valore predefinito è Distribution.

In questo esempio viene creato un gruppo di distribuzione denominato IT Administrators con le proprietà specificate.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Utilizzare PowerShell EOP autonomo per modificare i gruppi

Per modificare i gruppi in PowerShell EOP autonomo, utilizzare la sintassi seguente:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In questo esempio viene utilizzato l'indirizzo SMTP primario (denominato anche indirizzo di risposta) per il gruppo Seattle Employees in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

In questo esempio vengono sostituiti i membri correnti del gruppo Security Team con Kitty Petersen e Tyson Fawcett.

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

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) [e Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)

### <a name="remove-a-group-using-remote-windows-powershell"></a>Rimuovere un gruppo tramite l'Windows PowerShell

In questo esempio viene utilizzato il gruppo di distribuzione denominato IT Administrators.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta creazione, modifica o rimozione di un gruppo di distribuzione o di un gruppo di sicurezza abilitato alla posta elettronica, eseguire una delle operazioni seguenti:

- Nell'EAC, accedere a **Destinatari** \> **Gruppi**. Verificare che il gruppo sia elencato (o non elencato) e verificare il **valore tipo di** gruppo. Selezionare il gruppo e visualizzare le informazioni nel riquadro Dei dettagli oppure fare clic **sull'icona** ![ Modifica per visualizzare le ](../../media/ITPro-EAC-AddIcon.png) impostazioni.

- In PowerShell EOP autonomo, eseguire il comando seguente per verificare che il gruppo sia elencato (o non sia elencato):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Sostituire \<GroupIdentity\> con il nome, l'alias o l'indirizzo di posta elettronica del gruppo ed eseguire il comando seguente per verificare le impostazioni:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Per visualizzare i membri del gruppo, sostituire con il nome, l'alias o l'indirizzo di posta elettronica del gruppo \<GroupIdentity\> ed eseguire il comando seguente:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
