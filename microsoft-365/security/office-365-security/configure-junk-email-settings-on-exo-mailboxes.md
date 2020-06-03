---
title: Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online
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
ms.openlocfilehash: 40364db9d4af9e093d8f2f74ee3c0f0373b1671a
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498664"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online

In Microsoft 365 organizzazioni con cassette postali in Exchange Online, le impostazioni di protezione dalla posta indesiderata dell'organizzazione sono controllate da Exchange Online Protection (EOP). Per ulteriori informazioni, vedere [protezione da posta indesiderata in EOP](anti-spam-protection.md).

Tuttavia, esistono anche impostazioni di protezione da posta indesiderata specifiche che possono essere configurate dagli amministratori per le singole cassette postali in Exchange Online:

- **Abilitare o disabilitare la regola di posta**indesiderata: la regola di posta indesiderata è una regola di posta in arrivo nascosta chiamata regola di posta indesiderata abilitata per impostazione predefinita in ogni cassetta postale. La regola di posta indesiderata controlla le caratteristiche seguenti:

  - **Spostare i messaggi nella cartella posta indesiderata in base ai criteri**di protezione dalla posta indesiderata: quando un criterio di protezione da posta indesiderata viene configurato con il **messaggio di spostamento dell'azione nella cartella posta indesiderata** per un verdetto del filtro della posta indesiderata, la regola di filtro posta elettronica consente di spostare il messaggio nella cartella posta indesiderata dopo Per ulteriori informazioni sui verdetti del filtro della posta indesiderata nei criteri di protezione da posta indesiderata, vedere [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md). Analogamente, se zero-hour auto Purge (ZAP) determina un messaggio recapitato è spam o phishing, la regola di filtro posta indesiderata sposta il messaggio nella cartella posta indesiderata per il **messaggio di spostamento nella cartella** posta indesiderata che filtra la posta indesiderata. Per ulteriori informazioni su ZAP, vedere [zero-hour auto Purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).
  
  - **Impostazioni della posta indesiderata che gli utenti configurano per se stessi in Outlook o Outlook sul Web**: la raccolta degli elenchi _indirizzi attendibili_ è l'elenco dei mittenti attendibili, l'elenco destinatari attendibili e l'elenco Mittenti bloccati su ogni cassetta postale. Le voci di questi elenchi determinano se la regola di posta indesiderata sposta il messaggio nella cartella posta in arrivo o posta indesiderata. Gli utenti possono configurare la raccolta degli elenchi indirizzi attendibili per la propria cassetta postale in Outlook o Outlook sul Web (in precedenza noto come Outlook Web App). Gli amministratori possono configurare la raccolta degli elenchi indirizzi attendibili sulla cassetta postale di un utente.

Quando la regola di posta indesiderata è abilitata per la cassetta postale, EOP è in grado di spostare i messaggi nella cartella posta indesiderata in base al messaggio di spostamento dell'azione del verdetto del filtro posta indesiderata nella **cartella posta indesiderata** o nell'elenco Mittenti bloccati sulla cassetta postale e impedire che i messaggi vengano recapitati nella cartella posta indesiderata (in base all'

 Quando la regola di posta indesiderata è disabilitata nella cassetta postale, EOP non è in grado di spostare i messaggi nella cartella posta indesiderata in base al **messaggio di spostamento** del verdetto del filtro di posta indesiderata o all'insieme degli elenchi indirizzi attendibili sulla cassetta postale.

Gli amministratori possono utilizzare PowerShell di Exchange Online per disabilitare, abilitare e visualizzare lo stato della regola di posta indesiderata nelle cassette postali. Gli amministratori possono anche utilizzare PowerShell di Exchange Online per configurare le voci nella raccolta degli elenchi indirizzi attendibili nelle cassette postali (l'elenco Mittenti attendibili, l'elenco destinatari attendibili e l'elenco Mittenti bloccati).

> [!NOTE]
> I messaggi provenienti da mittenti che gli utenti hanno aggiunto ai propri elenchi di mittenti attendibili ignoreranno il filtro delle connessioni come parte di EOP (SCL è-1). Per impedire agli utenti di aggiungere voci all'elenco dei mittenti attendibili in Outlook, utilizzare criteri di gruppo come indicato nella sezione [informazioni sulle impostazioni di posta indesiderata in Outlook](#about-junk-email-settings-in-outlook) più avanti in questo argomento. Il filtro dei criteri, il filtro contenuto e i controlli di protezione avanzata dalle minacce (ATP, Advanced Threat Protection) verranno ancora applicati ai messaggi.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per eseguire queste procedure, è possibile utilizzare solo Exchange Online PowerShell. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni assegnate. In particolare, è necessario il ruolo **destinatari di posta elettronica** (assegnato ai gruppi di ruoli Gestione **organizzazione**, **Gestione destinatari**e **destinatari di posta elettronica personalizzati** per impostazione predefinita) o il ruolo **Opzioni utente** (assegnato ai gruppi di ruoli **Gestione organizzazione** e **supporto tecnico** per impostazione predefinita). Per aggiungere utenti ai gruppi di ruoli in Exchange Online, vedere [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups). Si noti che un utente con autorizzazioni predefinite può eseguire le stesse procedure nella propria cassetta postale, purché dispongano dell' [accesso a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- Negli ambienti di EOP autonomi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (anche note come regole di trasporto) in Exchange locale per tradurre il verdetto filtro posta indesiderata in modo che la regola della posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- I mittenti attendibili per le cassette postali condivise non vengono sincronizzati con Azure AD e EOP in base alla progettazione.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Utilizzo di PowerShell di Exchange Online per abilitare o disabilitare la regola di posta indesiderata in una cassetta postale

> [!NOTE]
> È possibile utilizzare solo il cmdlet **Set-MailboxJunkEmailConfiguration** per disabilitare la regola di posta indesiderata in una cassetta postale che è stata aperta in Outlook (in modalità cache) o Outlook sul Web. Se la cassetta postale non è stata aperta, verrà visualizzato l'errore: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` se si desidera sopprimere questo errore per le operazioni in blocco, è possibile aggiungere `-ErrorAction SlientlyContinue` il comando **Set-MailboxJunkEmailConfiguration** .

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

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Se l'utente non ha mai aperto la propria cassetta postale, è possibile che venga visualizzato un messaggio di errore quando si esegue il comando precedente. Per eliminare questo errore per le operazioni in blocco, aggiungere `-ErrorAction SlientlyContinue` il comando **Set-MailboxJunkEmailConfiguration** .
> 
> - Anche se si disattiva la regola di posta indesiderata, il filtro posta indesiderata di Outlook (a seconda del modo in cui è configurata) può anche determinare se un messaggio è spam e spostare i messaggi nella cartella posta in arrivo o posta indesiderata in base al verdetto di posta indesiderata e alla raccolta degli elenchi indirizzi attendibili sulla cassetta postale. Per ulteriori informazioni, vedere la sezione informazioni [sulle impostazioni di posta indesiderata in Outlook](#about-junk-email-settings-in-outlook) in questo argomento.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta abilitazione o disabilitazione della regola di posta indesiderata in una cassetta postale, utilizzare una delle seguenti procedure:

- Sostituire _\<MailboxIdentity\>_ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando riportato di seguito per verificare il valore della proprietà **Enabled** :

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
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

Per immettere più valori e sovrascrivere le voci esistenti per i parametri _BlockedSendersAndDomains_ e _TrustedSendersAndDomains_ , utilizzare la sintassi seguente: `"<Value1>","<Value2>"...` . Per aggiungere o rimuovere uno o più valori senza alterare altre voci esistenti, utilizzare la sintassi seguente:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

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

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Se l'utente non ha mai aperto la propria cassetta postale, è possibile che venga visualizzato un messaggio di errore quando si eseguono i comandi precedenti. Per eliminare questo errore per le operazioni in blocco, aggiungere `-ErrorAction SlientlyContinue` il comando **Set-MailboxJunkEmailConfiguration** .
> 
> - Anche se la regola di posta indesiderata è disabilitata per la cassetta postale, è comunque possibile configurare la raccolta degli elenchi indirizzi attendibili e il filtro posta indesiderata di Outlook è in grado di spostare i messaggi nella cartella posta in arrivo o posta indesiderata. Per ulteriori informazioni, vedere la sezione informazioni [sulle impostazioni di posta indesiderata in Outlook](#about-junk-email-settings-in-outlook) in questo argomento.
> 
> - Il filtro posta indesiderata di Outlook contiene altre impostazioni della raccolta degli elenchi indirizzi attendibili (ad esempio, **aggiunge automaticamente gli utenti che inviano la posta elettronica all'elenco Mittenti attendibili**). Per ulteriori informazioni, vedere [utilizzo dei filtri di posta indesiderata per controllare quali messaggi vengono visualizzati](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che la raccolta degli elenchi indirizzi attendibili sia stata configurata correttamente in una cassetta postale, utilizzare una delle seguenti procedure:

- Sostituire _\<MailboxIdentity\>_ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando riportato di seguito per verificare i valori della proprietà:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Se l'elenco di valori è troppo lungo, utilizzare la sintassi seguente:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Informazioni sulle impostazioni di posta indesiderata in Outlook

Per abilitare, disabilitare e configurare le impostazioni del filtro per la posta indesiderata sul retro del client disponibili in Outlook, utilizzare criteri di gruppo. Per ulteriori informazioni, vedere [file dei modelli amministrativi (ADMX/ADML) e strumento di personalizzazione di Office per le app di Microsoft 365 per Enterprise, office 2019 e office 2016](https://www.microsoft.com/download/details.aspx?id=49030) e [come distribuire le impostazioni di posta indesiderata, ad esempio l'elenco Mittenti attendibili, utilizzando criteri di gruppo](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi).

Quando il filtro posta indesiderata di Outlook è impostato sul valore predefinito **nessun filtro automatico** nelle opzioni di opzioni di posta elettronica indesiderata in **casa** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook non cerca di classificare i massaggi come posta indesiderata, ma utilizza comunque la raccolta degli elenchi indirizzi attendibili (elenco Mittenti attendibili, elenco destinatari attendibili e elenco Mittenti bloccati) per spostare i messaggi nella cartella posta indesiderata dopo Per ulteriori informazioni su queste impostazioni, vedere [Panoramica del filtro della posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Quando il filtro posta indesiderata di Outlook è impostato su **basso** o **alto**, il filtro della posta indesiderata di Outlook utilizza la propria tecnologia di filtro SmartScreen per identificare e spostare la posta indesiderata nella cartella posta elettronica. Questa classificazione di posta indesiderata è separata dal livello di probabilità di posta indesiderata (SCL) determinato da EOP. In effetti, Outlook ignora il SCL da EOP (a meno che EOP non abbia contrassegnato il messaggio per ignorare il filtro posta indesiderata) e utilizzi i propri criteri per determinare se il messaggio è posta indesiderata. Naturalmente, è possibile che il verdetto di posta indesiderata da EOP e Outlook potrebbe essere lo stesso. Per ulteriori informazioni su queste impostazioni, vedere [modificare il livello di protezione del filtro della posta indesiderata](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> Nel novembre 2016, Microsoft ha interrotto la produzione di aggiornamenti delle definizioni di posta indesiderata per i filtri SmartScreen in Exchange e Outlook. Le definizioni di posta indesiderata di SmartScreen esistenti sono state lasciate sul posto, ma la loro efficacia potrebbe peggiorare nel tempo. Per ulteriori informazioni, vedere [Eliminazione del supporto per SmartScreen in Outlook ed Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Pertanto, il filtro posta indesiderata di Outlook è in grado di utilizzare la raccolta degli elenchi indirizzi attendibili della cassetta postale e la sua classificazione di posta indesiderata per spostare i messaggi nella cartella posta indesiderata, anche se la regola di posta indesiderata è disabilitata nella cassetta postale

Outlook e Outlook sul Web supportano entrambi la raccolta degli elenchi indirizzi attendibili. La raccolta degli elenchi indirizzi attendibili viene salvata nella cassetta postale di Exchange Online, quindi le modifiche apportate alla raccolta degli elenchi indirizzi attendibili in Outlook vengono visualizzate in Outlook sul Web e viceversa.

## <a name="limits-for-junk-email-settings"></a>Limiti per le impostazioni della posta indesiderata

La raccolta degli elenchi indirizzi attendibili (elenco Mittenti attendibili, elenco destinatari attendibili e elenco Mittenti bloccati) memorizzata nella cassetta postale dell'utente viene sincronizzata anche con EOP. Con la sincronizzazione della directory, la raccolta degli elenchi indirizzi attendibili viene sincronizzata con Azure AD.

- La raccolta dell'elenco indirizzi attendibili nella cassetta postale dell'utente ha un limite di 510 KB, che include tutti gli elenchi, oltre alle impostazioni aggiuntive del filtro posta indesiderata. Se un utente supera questo limite, riceverà un errore di Outlook simile al seguente:

  > Impossibile/non è possibile aggiungere gli elenchi di posta indesiderata del server. Le dimensioni sono consentite sul server. Il filtro di posta indesiderata sul server verrà disabilitato fino a quando gli elenchi di posta indesiderata non sono stati ridotti alle dimensioni consentite dal server.

  Per ulteriori informazioni su questo limite e su come modificarlo, vedere [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit).

- La raccolta degli elenchi indirizzi attendibili sincronizzati in EOP presenta i seguenti limiti di sincronizzazione:

  - 1024 totale voci nell'elenco Mittenti attendibili, nell'elenco destinatari attendibili e nei contatti esterni se la **posta elettronica attendibile dei contatti personali** è abilitata.
  - 500 totale voci nell'elenco Mittenti bloccati e nei domini bloccati.

  Quando viene raggiunto il limite di voce 1024, vengono eseguite le operazioni seguenti:
  
  - L'elenco interrompe l'accettazione delle voci in PowerShell e Outlook sul Web, ma non viene visualizzato alcun messaggio di errore.

    Gli utenti di Outlook possono continuare ad aggiungere più di 1024 voci fino a raggiungere il limite di Outlook di 510 KB. Outlook è in grado di utilizzare queste voci aggiuntive, purché un filtro di EOP non blocchi il messaggio prima del recapito alla cassetta postale (regole del flusso di posta, anti-spoofing e così via).

- Con la sincronizzazione della directory, le voci vengono sincronizzate con Azure AD nell'ordine seguente:

  1. Contatti di posta elettronica se **la posta elettronica attendibile dei contatti** è abilitata.
  2. L'elenco dei mittenti attendibili e l'elenco di destinatari attendibili sono combinati, deduplicati e ordinati in ordine alfabetico ogni volta che viene apportata una modifica per le prime voci di 1024.

  Vengono utilizzate le prime voci di 1024 e le relative informazioni vengono contrassegnate nelle intestazioni del messaggio.
  
  Le voci superiori a 1024 che non sono state sincronizzate con Azure AD vengono elaborate da Outlook (non Outlook sul Web) e nessuna informazione viene contrassegnata nelle intestazioni del messaggio.

Come si può notare, se si Abilita la **posta elettronica attendibile dall'impostazione contatti** è possibile ridurre il numero di mittenti attendibili e destinatari attendibili che possono essere sincronizzati. Se si tratta di un problema, è consigliabile utilizzare criteri di gruppo per disattivare questa funzionalità:

- Nome file: outlk16. file OPAX
- Impostazione dei criteri: **considerare attendibile la posta elettronica dai contatti**
