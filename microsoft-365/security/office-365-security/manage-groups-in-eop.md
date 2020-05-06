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
description: In questo articolo vengono fornite informazioni su come creare e gestire i gruppi abilitati alla posta elettronica per un'organizzazione di Exchange in Exchange Online Protection (EOP).
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034403"
---
# <a name="manage-groups-in-eop"></a>Gestire gruppi in Exchange Online Protection

 È possibile utilizzare Exchange Online Protection (EOP) per creare gruppi abilitati alla posta elettronica per un'organizzazione di Exchange. È inoltre possibile utilizzare EOP per definire o aggiornare le proprietà del gruppo che specificano l'appartenenza, gli indirizzi di posta elettronica e altri aspetti dei gruppi. È possibile creare gruppi di distribuzione e gruppi di sicurezza, a seconda delle proprie esigenze. È possibile creare tali gruppi utilizzando l'interfaccia di amministrazione di Exchange o tramite Windows PowerShell remoto.

## <a name="types-of-mail-enabled-groups"></a>Tipi di gruppi abilitati alla posta elettronica.

È possibile creare due tipi di gruppi per la propria organizzazione di Exchange:

- I gruppi di distribuzione sono insiemi di utenti di posta elettronica, ad esempio un team o un altro gruppo ad hoc, che devono ricevere o inviare messaggi di posta elettronica relativi a un'area comune di interesse. I gruppi di distribuzione servono esclusivamente per la distribuzione di messaggi di posta elettronica. In EOP, un gruppo di distribuzione fa riferimento a qualsiasi gruppo abilitato alla posta elettronica, a prescindere che abbia o meno un contesto di sicurezza.

- I gruppi di sicurezza sono insiemi di utenti di posta elettronica che richiedono autorizzazioni di accesso per i ruoli di amministratore. Ad esempio, si potrebbe voler assegnare a un gruppo specifico di utenti autorizzazioni di ruolo di amministratore in modo che possano configurare impostazioni di protezione dalla posta indesiderata e antimalware.

    > [!NOTE]
    > Per impostazione predefinita, tutti i nuovi gruppi di sicurezza abilitati alla posta elettronica richiedono l'autenticazione di tutti i mittenti. Questo impedisce ai mittenti esterni di inviare messaggi ai gruppi di sicurezza abilitati alla posta elettronica.

## <a name="before-you-begin"></a>Informazioni preliminari

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Gruppi di distribuzione e sicurezza" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).

- Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Tenere presente che durante la creazione e la gestione dei gruppi tramite i cmdlet di PowerShell di Exchange Online Protection, è possibile che si verifichi la limitazione.

- Nelle procedure di PowerShell di questo argomento viene utilizzato un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.

- Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online Protection, vedere [Connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="create-a-group-in-the-eac"></a>Creare un gruppo nell'interfaccia di amministrazione di Exchange

1. Nell'EAC, accedere a **Destinatari** \> **Gruppi**.

2. Fare **New** ![clic su nuova](../../media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi fare clic su **gruppo di distribuzione** o **gruppo di sicurezza**in base alle proprie esigenze.

3. Nella pagina **nuovo** gruppo di distribuzione o **nuovo gruppo di sicurezza** , configurare le seguenti impostazioni:

   - **Nome visualizzato**: digitare un nome visualizzato univoco per l'organizzazione e significativo per gli utenti di EOP. Il nome visualizzato è obbligatorio.

   - **Alias**: digitare un alias di gruppo contenente fino a 64 caratteri univoci per l'organizzazione. EOP gli utenti digita l'alias nella riga a: dei messaggi di posta elettronica e l'alias viene risolto nel nome visualizzato del gruppo. Se si modifica l'alias, anche l'indirizzo SMTP primario per il gruppo cambia e conterrà il nuovo alias. L'alias è obbligatorio.

   - **Descrizione**: digitare una descrizione del gruppo in modo che gli utenti conoscano lo scopo del gruppo.

   - **Proprietari**: per impostazione predefinita, la persona che crea il gruppo è il proprietario. È possibile aggiungere un proprietario scegliendo **Aggiungi** ![icona](../../media/ITPro-EAC-AddIcon.gif). Ogni gruppo deve presentare almeno un proprietario.

     > [!NOTE]
     > I proprietari non sono tenuti a essere membri del gruppo.

   - **Membri**: utilizzare questa sezione per aggiungere membri del gruppo e per specificare se è necessaria l'approvazione per gli utenti di partecipare o lasciare il gruppo. Per aggiungere membri al gruppo, fare clic su **Aggiungi** ![icona](../../media/ITPro-EAC-AddIcon.gif).

4. Scegliere **OK** per tornare alla pagina originale.

5. Al termine, scegliere **Salva** per creare il gruppo. Il nuovo gruppo verrà visualizzato nell'elenco dei gruppi.

## <a name="edit-or-remove-a-group-in-the-eac"></a>Modificare o rimuovere un gruppo nell'interfaccia di amministrazione di Exchange

1. In EAC, accedere a **Destinatari** \> **Gruppi**.

2. Eseguire una delle operazioni seguenti:

   - Per modificare un gruppo: nell'elenco dei gruppi fare clic sul gruppo che si desidera visualizzare o modificare, quindi fare clic su **modifica** ![icona](../../media/ITPro-EAC-EditIcon.gif)modifica. È possibile aggiornare le impostazioni generali, aggiungere o rimuovere proprietari del gruppo e aggiungere o rimuovere i membri del gruppo in base alle esigenze.

   - Per rimuovere un gruppo: selezionare il gruppo e fare **Remove** ![clic su Rimuovi](../../media/ITPro-EAC-RemoveIcon.gif)icona Rimuovi.

3. Dopo avere apportato tutte le modifiche, fare clic su **Salva**.

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Creare, modificare o rimuovere un gruppo utilizzando Windows PowerShell remoto

In questa sezione vengono fornite informazioni sulla creazione di gruppi e sulla modifica delle relative proprietà in PowerShell di Exchange Online Protection. Inoltre, viene illustrato come rimuovere un gruppo esistente.

### <a name="create-a-group-using-remote-windows-powershell"></a>Creare un gruppo utilizzando Windows PowerShell remoto

In questo esempio viene utilizzato il cmdlet [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) per creare un gruppo di distribuzione con alias itadmin e nome Amministratori IT. Inoltre, vengono aggiunti utenti come membri del gruppo.

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**Nota**: per creare un gruppo di sicurezza invece di un gruppo di distribuzione, utilizzare `Security` il valore per il parametro *Type* .

Per verificare che il gruppo amministratori IT sia stato creato correttamente, eseguire il comando riportato di seguito per visualizzare le informazioni sul nuovo gruppo:

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).

Per ottenere un elenco di membri del gruppo, eseguire il comando riportato di seguito:

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).

Per ottenere un elenco completo di tutti i gruppi, eseguire il comando riportato di seguito:

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>Modificare le proprietà di un gruppo utilizzando Windows PowerShell remoto

Un vantaggio dell'utilizzo di PowerShell invece dell'interfaccia di amministrazione di Exchange è la possibilità di modificare le proprietà per più gruppi.

Di seguito sono riportati alcuni esempi di utilizzo di PowerShell di Exchange Online Protection per modificare le proprietà del gruppo.

In questo esempio viene utilizzata la modifica dell'indirizzo SMTP primario (denominato anche indirizzo di risposta) del gruppo Seattle Employees in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).

Per verificare di aver correttamente modificato le proprietà per il gruppo, eseguire il seguente comando per verificare il nuovo valore:

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

In questo esempio vengono aggiornati tutti i membri del gruppo Seattle Employees. Utilizzare una virgola per tutti i membri.

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).

Per ottenere l'elenco di tutti i membri del gruppo Seattle Employees, eseguire il comando riportato di seguito:

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>Rimuovere un gruppo tramite Windows PowerShell remoto

In questo esempio viene rimosso il gruppo di distribuzione denominato amministratori IT.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).

Per verificare che il gruppo sia stato rimosso, eseguire il comando riportato di seguito e verificare che il gruppo (in questo caso "amministratori IT") sia stato eliminato.

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
