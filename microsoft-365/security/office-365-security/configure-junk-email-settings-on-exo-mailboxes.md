---
title: Configurare le impostazioni della posta indesiderata sulle cassette postali di Exchange online in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online. Molte di queste impostazioni sono disponibili per gli utenti in Outlook o Outlook sul Web.
ms.openlocfilehash: 2b138830cff7337d7949606cc110ea8f7ae1c0ff
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42897036"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes-in-office-365"></a>Configurare le impostazioni della posta indesiderata sulle cassette postali di Exchange online in Office 365

Le impostazioni di protezione dalla posta indesiderata dell'organizzazione in Exchange Online sono controllate da Exchange Online Protection (EOP). Per ulteriori informazioni, vedere [protezione da posta indesiderata in Office 365](anti-spam-protection.md).

Tuttavia, esistono anche impostazioni di protezione da posta indesiderata specifiche che possono essere configurate dagli amministratori per le singole cassette postali in Exchange Online:

- **Abilitare o disabilitare la regola di posta**indesiderata: la regola di posta indesiderata è una regola di posta in arrivo nascosta chiamata regola di posta indesiderata abilitata per impostazione predefinita in ogni cassetta postale. La regola di posta indesiderata controlla le caratteristiche seguenti:

  - **Spostare i messaggi nella cartella posta indesiderata in base ai criteri**di protezione dalla posta indesiderata: quando un criterio di protezione da posta indesiderata viene configurato con il **messaggio di spostamento dell'azione nella cartella posta indesiderata** per un verdetto del filtro della posta indesiderata, la regola di filtro posta elettronica consente di spostare il messaggio nella cartella posta indesiderata dopo Per ulteriori informazioni sui verdetti di filtraggio della posta indesiderata nei criteri di protezione dalla posta indesiderata, vedere [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md). Analogamente, se lo ZAP (auto Purge) rileva la posta indesiderata o phishing in un messaggio già recapitato, la regola del filtro della posta indesiderata sposta il messaggio nella cartella posta indesiderata per il **messaggio di spostamento in azioni di** filtro della posta indesiderata. Per ulteriori informazioni su ZAP, vedere [zero-hour auto Purge (ZAP)-protezione da posta indesiderata e malware in Office 365](zero-hour-auto-purge.md).
  
  - **Impostazioni della posta indesiderata che gli utenti configurano per se stessi in Outlook o Outlook sul Web**: la raccolta degli elenchi _indirizzi attendibili_ è l'elenco dei mittenti attendibili, l'elenco destinatari attendibili e l'elenco Mittenti bloccati su ogni cassetta postale. Le voci di questi elenchi determinano se la regola di posta indesiderata sposta il messaggio nella cartella posta in arrivo o posta indesiderata. Gli utenti possono configurare la raccolta degli elenchi indirizzi attendibili per la propria cassetta postale in Outlook o Outlook sul Web (in precedenza noto come Outlook Web App). Gli amministratori possono configurare la raccolta degli elenchi indirizzi attendibili sulla cassetta postale di un utente.

Quando la regola di posta indesiderata è abilitata per la cassetta postale, EOP è in grado di spostare i messaggi nella cartella posta indesiderata in base al messaggio di spostamento dell'azione del verdetto del filtro posta indesiderata nella **cartella posta indesiderata** o nell'elenco Mittenti bloccati sulla cassetta postale e impedire che i messaggi vengano recapitati nella cartella posta indesiderata (in base all'

 Quando la regola di posta indesiderata è disabilitata nella cassetta postale, EOP non è in grado di spostare i messaggi nella cartella posta indesiderata in base al **messaggio di spostamento** del verdetto del filtro di posta indesiderata o all'insieme degli elenchi indirizzi attendibili sulla cassetta postale.

Gli amministratori possono utilizzare PowerShell di Exchange Online per disabilitare, abilitare e visualizzare lo stato della regola di posta indesiderata nelle cassette postali. Gli amministratori possono anche utilizzare PowerShell di Exchange Online per configurare le voci nella raccolta degli elenchi indirizzi attendibili nelle cassette postali (l'elenco Mittenti attendibili, l'elenco destinatari attendibili e l'elenco Mittenti bloccati).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per eseguire queste procedure, è possibile utilizzare solo Exchange Online PowerShell. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni assegnate. In particolare, è necessario il ruolo **destinatari di posta elettronica** (assegnato ai gruppi di ruoli Gestione **organizzazione**, **Gestione destinatari**e **destinatari di posta elettronica personalizzati** per impostazione predefinita) o il ruolo **Opzioni utente** (assegnato ai gruppi di ruoli **Gestione organizzazione** e **supporto tecnico** per impostazione predefinita). Per aggiungere utenti ai gruppi di ruoli in Exchange Online, vedere [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups). Si noti che un utente con autorizzazioni predefinite può eseguire le stesse procedure nella propria cassetta postale, purché dispongano dell' [accesso a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- In ambienti EOP autonomi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (note anche come regole di trasporto) in Exchange locale per tradurre il verdetto del filtro della posta indesiderata di EOP in modo che la regola di posta indesiderata possa spostare il messaggio in cartella posta indesiderata. Per informazioni dettagliate, vedere [Configure standalone EOP per recapitare la posta indesiderata nella cartella posta indesiderata in ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Utilizzo di PowerShell di Exchange Online per abilitare o disabilitare la regola di posta indesiderata in una cassetta postale

> [!NOTE]
> È possibile utilizzare solo il cmdlet **Set-MailboxJunkEmailConfiguration** per disabilitare la regola di posta indesiderata in una cassetta postale che è stata aperta in Outlook (in modalità cache) o Outlook sul Web. Se la cassetta postale non è stata aperta, verrà visualizzato l'errore `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` : se si desidera sopprimere questo errore per le operazioni in blocco, `-ErrorAction SlientlyContinue` è possibile aggiungere il comando **Set-MailboxJunkEmailConfiguration**

Per abilitare o disabilitare la regola di posta indesiderata in una cassetta postale, utilizzare la sintassi seguente:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In questo esempio viene disattivata la regola di posta indesiderata sulla cassetta postale ori Epstein.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In questo esempio viene disabilitata la regola di posta indesiderata in tutte le cassette postali dell'organizzazione.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

 **Note**:

- Se l'utente non ha mai aperto la propria cassetta postale, è possibile che venga visualizzato un messaggio di errore quando si esegue il comando precedente. Per eliminare questo errore per le operazioni in blocco `-ErrorAction SlientlyContinue` , aggiungere il comando **Set-MailboxJunkEmailConfiguration** .

- Anche se si disattiva la regola di posta indesiderata, il filtro posta indesiderata di Outlook (a seconda del modo in cui è configurata) può anche determinare se un messaggio è posta indesiderata e spostare i messaggi nella cartella posta in arrivo o posta indesiderata in base al verdetto di posta indesiderata e alla raccolta degli elenchi indirizzi attendibili la cassetta postale. Per ulteriori informazioni, vedere la sezione informazioni [sulle impostazioni di posta indesiderata in Outlook](#about-junk-email-settings-in-outlook) in questo argomento.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta abilitazione o disabilitazione della regola di posta indesiderata in una cassetta postale, utilizzare una delle seguenti procedure:

- Sostituire _ \<MailboxIdentity\> _ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando riportato di seguito per verificare il valore della proprietà **Enabled** :

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

- Sostituire _ \<MailboxIdentity\> _ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando riportato di seguito per verificare il valore della proprietà **Enabled** della regola di posta indesiderata.

  ```PowerShell
  Get-InboxRule "Junk E-mail Rule" -Mailbox "<MailboxIdentity>" -IncludeHidden
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Utilizzo di PowerShell di Exchange Online per configurare la raccolta degli elenchi indirizzi attendibili in una cassetta postale

La raccolta degli elenchi indirizzi attendibili in una cassetta postale include l'elenco dei mittenti attendibili, l'elenco dei destinatari attendibili e l'elenco dei mittenti bloccati. Per impostazione predefinita, gli utenti possono configurare la raccolta degli elenchi indirizzi attendibili nella propria cassetta postale in Outlook o Outlook sul Web. Gli amministratori possono utilizzare i parametri corrispondenti del cmdlet **Set-MailboxJunkEmailConfiguration** per configurare la raccolta degli elenchi indirizzi attendibili sulla cassetta postale di un utente. Questi parametri sono descritti nella tabella seguente.

|||
|---|---|
|**Parametro in Set-MailboxJunkEmailConfiguration**|**Impostazione di Outlook sul Web**|
|_BlockedSendersAndDomains_|**Spostare la posta elettronica da questi mittenti o domini alla cartella posta indesiderata**|
|_ContactsTrusted_|**Attendibilità della posta elettronica dai contatti personali**|
|_TrustedListsOnly_|**Solo attendibilità della posta elettronica da indirizzi nei mittenti attendibili e nell'elenco dei domini e nelle liste di distribuzione sicure**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Non spostare la posta elettronica da questi mittenti alla cartella posta indesiderata**|
|

<sup>\*</sup>**Note**:

- In Exchange Online, le **voci di dominio** nell'elenco Mittenti attendibili o nel parametro _TrustedSendersAndDomains_ non vengono riconosciute, quindi utilizzano solo gli indirizzi di posta elettronica. In EOP autonomo con sincronizzazione della directory, le voci di dominio non vengono sincronizzate per impostazione predefinita, ma è possibile abilitare la sincronizzazione per i domini. Per ulteriori informazioni, vedere [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange).

- Non è possibile modificare direttamente l'elenco dei destinatari attendibili utilizzando il cmdlet **Set-MailboxJunkEmailConfiguration** (il parametro _TrustedRecipientsAndDomains_ non funziona). È possibile modificare l'elenco Mittenti attendibili e tali modifiche vengono sincronizzate nell'elenco destinatari attendibili.

Per configurare la raccolta degli elenchi indirizzi attendibili in una cassetta postale, utilizzare la sintassi seguente:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Per immettere più valori e sovrascrivere le voci esistenti per i parametri _BlockedSendersAndDomains_ e _TrustedSendersAndDomains_ , utilizzare la sintassi seguente `"<Value1>","<Value2>"...`:. Per aggiungere o rimuovere uno o più valori senza alterare altre voci esistenti, utilizzare la sintassi seguente:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In questo esempio vengono configurate le impostazioni seguenti per la raccolta degli elenchi indirizzi attendibili sulla cassetta postale di Epstein:

- Aggiungere il valore shopping@fabrikam.com all'elenco dei mittenti bloccati.

- Rimuovere il valore chris@fourthcoffee.com dall'elenco Mittenti attendibili e dall'elenco destinatari attendibili.

- Configura i contatti nella cartella contatti per essere considerati come mittenti attendibili.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In questo esempio viene rimosso il dominio contoso.com dall'elenco dei mittenti bloccati in tutte le cassette postali degli utenti dell'organizzazione.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

 **Note**:

- Se l'utente non ha mai aperto la propria cassetta postale, è possibile che venga visualizzato un messaggio di errore quando si eseguono i comandi precedenti. Per eliminare questo errore per le operazioni in blocco `-ErrorAction SlientlyContinue` , aggiungere il comando **Set-MailboxJunkEmailConfiguration** .

- Anche se la regola di posta indesiderata è disabilitata per la cassetta postale, è comunque possibile configurare la raccolta degli elenchi indirizzi attendibili e il filtro posta indesiderata di Outlook è in grado di spostare i messaggi nella cartella posta in arrivo o posta indesiderata. Per ulteriori informazioni, vedere la sezione informazioni [sulle impostazioni di posta indesiderata in Outlook](#about-junk-email-settings-in-outlook) in questo argomento.

- Il filtro posta indesiderata di Outlook contiene altre impostazioni della raccolta degli elenchi indirizzi attendibili (ad esempio, **aggiunge automaticamente gli utenti che inviano la posta elettronica all'elenco Mittenti attendibili**). Per ulteriori informazioni, vedere [utilizzo dei filtri di posta indesiderata per controllare quali messaggi vengono visualizzati](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che la raccolta degli elenchi indirizzi attendibili sia stata configurata correttamente in una cassetta postale, utilizzare una delle seguenti procedure:

- Sostituire _ \<MailboxIdentity\> _ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando riportato di seguito per verificare i valori della proprietà:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Se l'elenco di valori è troppo lungo, utilizzare la sintassi seguente:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Informazioni sulle impostazioni di posta indesiderata in Outlook

Per abilitare, disabilitare e configurare le impostazioni del filtro per la posta indesiderata sul retro del client disponibili in Outlook, utilizzare criteri di gruppo. Per ulteriori informazioni, vedere [file dei modelli amministrativi (ADMX/ADML) e strumento di personalizzazione di Office per office 365 ProPlus, office 2019 e office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

Quando il filtro posta indesiderata di Outlook è impostato sul valore predefinito **nessun filtro automatico** nelle \> **Opzioni**di **Opzioni di posta elettronica** **indesiderata** \> in **casa** \> , Outlook non cerca di classificare i massaggi come posta indesiderata, ma utilizza comunque la raccolta degli elenchi indirizzi attendibili (elenco Mittenti attendibili, elenco destinatari attendibili e elenco Mittenti bloccati) per spostare i messaggi nella cartella posta indesiderata dopo Per ulteriori informazioni su queste impostazioni, vedere [Panoramica del filtro della posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Quando il filtro posta indesiderata di Outlook è impostato su **basso** o **alto**, il filtro della posta indesiderata di Outlook utilizza la propria tecnologia di filtro SmartScreen per identificare e spostare la posta indesiderata nella cartella posta elettronica. Questa classificazione di posta indesiderata è separata dal livello di probabilità di posta indesiderata (SCL) determinato da EOP. In effetti, Outlook ignora il SCL da EOP (a meno che EOP non abbia contrassegnato il messaggio per ignorare il filtro posta indesiderata) e utilizzi i propri criteri per determinare se il messaggio è posta indesiderata. Naturalmente, è possibile che il verdetto di posta indesiderata da EOP e Outlook potrebbe essere lo stesso. Per ulteriori informazioni su queste impostazioni, vedere [modificare il livello di protezione del filtro della posta indesiderata](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> Nel novembre 2016, Microsoft ha interrotto la produzione di aggiornamenti delle definizioni di posta indesiderata per i filtri SmartScreen in Exchange e Outlook. Le definizioni di posta indesiderata di SmartScreen esistenti sono state lasciate sul posto, ma la loro efficacia potrebbe peggiorare nel tempo. Per ulteriori informazioni, vedere [Eliminazione del supporto per SmartScreen in Outlook ed Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Pertanto, il filtro posta indesiderata di Outlook è in grado di utilizzare la raccolta degli elenchi indirizzi attendibili della cassetta postale e la sua classificazione di posta indesiderata per spostare i messaggi nella cartella posta indesiderata, anche se la regola di posta indesiderata è disabilitata nella cassetta postale

Outlook e Outlook sul Web supportano entrambi la raccolta degli elenchi indirizzi attendibili. La raccolta degli elenchi indirizzi attendibili viene salvata nella cassetta postale di Exchange Online, quindi le modifiche apportate alla raccolta degli elenchi indirizzi attendibili in Outlook vengono visualizzate in Outlook sul Web e viceversa.
