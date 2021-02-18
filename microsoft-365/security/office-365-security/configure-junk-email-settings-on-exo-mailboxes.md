---
title: Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online. Molte di queste impostazioni sono disponibili per gli utenti in Outlook o Outlook sul Web.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31f247ec74f1780d05aaeb79753abd0075401d9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290118"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online, le impostazioni di protezione dalla posta indesiderata dell'organizzazione sono controllate da Exchange Online Protection (EOP). Per ulteriori informazioni, vedere [Protezione da posta indesiderata in EOP.](anti-spam-protection.md)

Tuttavia, esistono anche impostazioni di protezione dalla posta indesiderata specifiche che gli amministratori possono configurare sulle singole cassette postali in Exchange Online:

- **Abilitare o disabilitare la** regola di posta indesiderata: la regola di posta indesiderata è una regola posta in arrivo nascosta denominata Regola di posta indesiderata abilitata per impostazione predefinita in ogni cassetta postale. La regola di posta indesiderata controlla le funzionalità seguenti:

  - Spostare i messaggi nella cartella Posta indesiderata in base ai criteri di protezione  dalla posta **indesiderata:** quando un criterio di protezione da posta indesiderata è configurato con l'azione Sposta messaggio nella cartella Posta indesiderata per un verdetto filtro posta indesiderata, la regola di filtro della posta indesiderata sposta il messaggio nella cartella Posta indesiderata dopo il recapito del messaggio alla cassetta postale. Per ulteriori informazioni sui verdetti del filtro posta indesiderata nei criteri di protezione da posta indesiderata, vedere Configurare i criteri di protezione da posta [indesiderata in EOP.](configure-your-spam-filter-policies.md) Allo stesso modo, se zap (zero-hour auto purge) determina che un messaggio recapitato è posta  indesiderata o phish, la regola di filtro della posta indesiderata sposta il messaggio nella cartella Posta indesiderata per spostare il messaggio nella cartella Posta indesiderata per le azioni di verdetto del filtro della posta indesiderata. Per ulteriori informazioni su ZAP, vedere [Zero-hour auto purge (ZAP) in Exchange Online.](zero-hour-auto-purge.md)

  - Impostazioni della posta indesiderata configurate dagli utenti in  Outlook o **Outlook sul Web:** la raccolta degli elenchi indirizzi attendibili è l'elenco Mittenti attendibili, l'elenco Destinatari attendibili e l'elenco Mittenti bloccati in ogni cassetta postale. Le voci in questi elenchi determinano se la regola di posta indesiderata sposta il messaggio nella cartella Posta in arrivo o Posta indesiderata. Gli utenti possono configurare la raccolta dell'elenco indirizzi attendibili per la propria cassetta postale in Outlook o Outlook sul Web (in precedenza noto come Outlook Web App). Gli amministratori possono configurare la raccolta dell'elenco indirizzi attendibili nella cassetta postale di qualsiasi utente.

Quando la regola di posta indesiderata è abilitata nella cassetta postale, EOP è in  grado di spostare i messaggi nella cartella Posta indesiderata in base all'azione di filtro della posta indesiderata Spostare i messaggi nella cartella Posta indesiderata o nell'elenco Mittenti bloccati nella cassetta postale e impedire che i messaggi vengano recapitati nella cartella Posta indesiderata (in base all'elenco Mittenti attendibili nella cassetta postale).

 Quando la regola di posta indesiderata è disabilitata nella cassetta postale, EOP non può  spostare i messaggi nella cartella Posta indesiderata in base all'azione di filtro della posta indesiderata Sposta il messaggio nella cartella Posta indesiderata o nella raccolta dell'elenco indirizzi attendibili nella cassetta postale.

Gli amministratori possono utilizzare PowerShell di Exchange Online per disabilitare, abilitare e visualizzare lo stato della regola di posta indesiderata nelle cassette postali. Gli amministratori possono inoltre utilizzare PowerShell di Exchange Online per configurare le voci nella raccolta degli elenchi indirizzi attendibili nelle cassette postali (l'elenco Mittenti attendibili, l'elenco Destinatari attendibili e l'elenco Mittenti bloccati).

> [!NOTE]
> I messaggi provenienti da mittenti aggiunti dagli utenti ai propri elenchi Mittenti attendibili ignorano il filtro connessioni come parte di EOP (il livello di probabilità di posta indesiderata è -1). Per impedire agli utenti di aggiungere voci all'elenco Mittenti attendibili in Outlook, utilizzare Criteri di gruppo come indicato nella sezione Informazioni sulle impostazioni di posta indesiderata  [in Outlook](#about-junk-email-settings-in-outlook) più avanti in questo articolo. Il filtro dei criteri, il filtro contenuto e i controlli di Defender per Office 365 verranno comunque applicati ai messaggi.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- È possibile utilizzare Exchange Online PowerShell solo per eseguire le procedure descritte in questo articolo. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online. In particolare,  è necessario il ruolo Destinatari di posta (assegnato  ai gruppi di ruoli Gestione  **organizzazione,** Gestione destinatari e  Destinatari di posta elettronica personalizzati per impostazione predefinita) o Il ruolo Opzioni utente (assegnato per impostazione predefinita ai gruppi di ruoli Gestione organizzazione e **Help Desk).**  Per aggiungere utenti ai gruppi di ruoli in Exchange Online, vedere [Modificare i gruppi di ruoli in Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) Si noti che gli utenti con autorizzazioni predefinite possono eseguire le stesse procedure nella propria cassetta postale, purché possano accedere [a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- Negli ambienti di EOP autonomi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (anche note come regole di trasporto) in Exchange locale per tradurre il verdetto filtro posta indesiderata in modo che la regola della posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- I mittenti attendibili per le cassette postali condivise non vengono sincronizzati con Azure AD ed EOP da progettazione.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Abilitazione o disabilitazione della regola di posta indesiderata in una cassetta postale tramite PowerShell di Exchange Online

> [!NOTE]
> È possibile utilizzare il cmdlet **Set-MailboxJunkEmailConfiguration** solo per disabilitare la regola di posta indesiderata in una cassetta postale aperta in Outlook (in modalità cache) o Outlook sul Web. Se la cassetta postale non è stata aperta, verrà visualizzato l'errore: Se si desidera eliminare questo errore per le operazioni in blocco, è possibile aggiungere al `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` comando **Set-MailboxJunkEmailConfiguration.**

Per abilitare o disabilitare la regola di posta indesiderata in una cassetta postale, utilizzare la sintassi seguente:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In questo esempio viene disabilitata la regola di posta indesiderata nella cassetta postale di Ori Ep altro.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In questo esempio viene disabilitata la regola di posta indesiderata in tutte le cassette postali degli utenti nell'organizzazione.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-MailboxJunkEmailConfiguration.](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - Se l'utente non ha mai aperto la propria cassetta postale, potrebbe essere visualizzato un errore quando si esegue il comando precedente. Per eliminare questo errore per le operazioni in blocco, aggiungere `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Anche se si disabilita la regola di posta indesiderata, il filtro per la posta indesiderata di Outlook (a seconda di come è configurato) può anche determinare se un messaggio è posta indesiderata e può spostare i messaggi nella cartella Posta in arrivo o Posta indesiderata in base al verdetto della posta indesiderata e all'elenco indirizzi attendibili della cassetta postale. Per ulteriori informazioni, vedere la sezione [Informazioni sulle impostazioni di posta indesiderata in Outlook](#about-junk-email-settings-in-outlook) in questo articolo.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che la regola di posta indesiderata in una cassetta postale sia stata abilitata o disabilitata correttamente, utilizzare una delle seguenti procedure:

- Sostituire _\<MailboxIdentity\>_ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando seguente per verificare il valore della proprietà **Enabled:**

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Utilizzare PowerShell di Exchange Online per configurare la raccolta dell'elenco indirizzi attendibili in una cassetta postale

La raccolta degli elenchi indirizzi attendibili in una cassetta postale include l'elenco Mittenti attendibili, l'elenco Destinatari attendibili e l'elenco Mittenti bloccati. Per impostazione predefinita, gli utenti possono configurare la raccolta dell'elenco indirizzi attendibili nella propria cassetta postale in Outlook o Outlook sul Web. Gli amministratori possono utilizzare i parametri corrispondenti nel cmdlet **Set-MailboxJunkEmailConfiguration** per configurare la raccolta degli elenchi indirizzi attendibili nella cassetta postale di un utente. Questi parametri sono descritti nella tabella seguente.

****

|Parametro su Set-MailboxJunkEmailConfiguration|Impostazione di Outlook sul Web|
|---|---|
|_BlockedSendersAndDomains_|**Spostare la posta elettronica da questi mittenti o domini nella cartella Posta indesiderata**|
|_ContactsTrusted_|**Considerare attendibile la posta elettronica dai contatti personali**|
|_TrustedListsOnly_|**Considera attendibili solo i messaggi di posta elettronica provenienti da indirizzi presenti nell'elenco Mittenti e domini attendibili e negli elenchi indirizzi attendibili**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Non spostare la posta elettronica da questi mittenti nella cartella Posta indesiderata**|
|

<sup>\*</sup>**Note:**

- In Exchange Online, le voci **di** dominio nell'elenco Mittenti attendibili o nel parametro _TrustedSendersAndDomains_ non vengono riconosciute, quindi utilizzare solo gli indirizzi di posta elettronica. In EOP autonomo con sincronizzazione della directory, le voci di dominio non vengono sincronizzate per impostazione predefinita, ma è possibile abilitare la sincronizzazione per i domini. Per ulteriori informazioni, vedere [KB3019657.](https://support.microsoft.com/help/3019657)

- Non è possibile modificare direttamente l'elenco Destinatari attendibili utilizzando il cmdlet **Set-MailboxJunkEmailConfiguration** (il parametro _TrustedRecipientsAndDomains_ non funziona). L'elenco Mittenti attendibili viene modificato e le modifiche vengono sincronizzate con l'elenco Destinatari attendibili.

Per configurare la raccolta dell'elenco indirizzi attendibili in una cassetta postale, utilizzare la sintassi seguente:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Per immettere più valori e sovrascrivere le voci esistenti per i parametri _BlockedSendersAndDomains_ e _TrustedSendersAndDomains,_ utilizzare la sintassi seguente: `"<Value1>","<Value2>"...` . Per aggiungere o rimuovere uno o più valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In questo esempio vengono configurate le seguenti impostazioni per la raccolta degli elenchi indirizzi attendibili nella cassetta postale di Ori Ep altro:

- Aggiungere il valore shopping@fabrikam.com all'elenco Mittenti bloccati.

- Rimuovere il valore chris@fourthcoffee.com dall'elenco Mittenti attendibili e dall'elenco Destinatari attendibili.

- Configura i contatti nella cartella Contatti in modo che siano considerati mittenti attendibili.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In questo esempio viene rimosso il contoso.com dall'elenco Mittenti bloccati in tutte le cassette postali utente dell'organizzazione.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-MailboxJunkEmailConfiguration.](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - Se l'utente non ha mai aperto la propria cassetta postale, potrebbe essere visualizzato un errore quando si eseguono i comandi precedenti. Per eliminare questo errore per le operazioni in blocco, aggiungere `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Anche se la regola di posta indesiderata è disabilitata nella cassetta postale, è comunque possibile configurare la raccolta dell'elenco indirizzi attendibili e il filtro per la posta indesiderata di Outlook è in grado di spostare i messaggi nella cartella Posta in arrivo o Posta indesiderata. Per ulteriori informazioni, vedere la sezione [Informazioni sulle impostazioni di posta indesiderata in Outlook](#about-junk-email-settings-in-outlook) in questo articolo.
>
> - Il filtro per la posta indesiderata di Outlook include ulteriori impostazioni per la raccolta degli elenchi indirizzi attendibili (ad esempio, Aggiungi automaticamente persone a cui è stato inviato un messaggio di posta **elettronica all'elenco Mittenti attendibili).** Per ulteriori informazioni, vedere [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta configurazione della raccolta dell'elenco indirizzi attendibili in una cassetta postale, utilizzare una delle seguenti procedure:

- Sostituire _\<MailboxIdentity\>_ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando seguente per verificare i valori della proprietà:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Se l'elenco dei valori è troppo lungo, utilizzare la sintassi seguente:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Informazioni sulle impostazioni della posta indesiderata in Outlook

Per abilitare, disabilitare e configurare le impostazioni del filtro per la posta indesiderata sul lato client disponibili in Outlook, utilizzare Criteri di gruppo. Per ulteriori informazioni, vedere File dei modelli amministrativi (ADMX/ADML) e Strumento di personalizzazione di Office per [Microsoft 365 Apps for enterprise, Office 2019 e Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) e Come distribuire le impostazioni di posta indesiderata, ad esempio l'elenco Mittenti attendibili, tramite Criteri [di gruppo.](https://support.microsoft.com/help/2252421)

Quando il filtro per la posta indesiderata di Outlook è impostato sul valore predefinito No **automatic filtering** in **Home** \> **Junk** \> **E-Mail Options,** Outlook non tenta di classificare i messaggi come posta indesiderata, ma utilizza comunque \> l'insieme degli elenchi indirizzi attendibili (elenco Mittenti attendibili, Destinatari attendibili e Mittenti bloccati) per spostare i messaggi nella cartella Posta indesiderata dopo il recapito. Per ulteriori informazioni su queste impostazioni, vedere [Overview of the Junk Email Filter.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

Quando il filtro per la posta indesiderata di Outlook è impostato su **Basso** o **Alto,** il filtro per la posta indesiderata di Outlook utilizza la propria tecnologia di filtro SmartScreen per identificare e spostare la posta indesiderata nella cartella Posta indesiderata. Questa classificazione della posta indesiderata è separata dal livello di probabilità di posta indesiderata (SCL) determinato da EOP. Infatti, Outlook ignora il livello di probabilità di posta indesiderata da EOP (a meno che EOP non ha contrassegnato il messaggio per ignorare il filtro posta indesiderata) e utilizza i propri criteri per determinare se il messaggio è posta indesiderata. Naturalmente, è possibile che il verdetto di posta indesiderata da EOP e Outlook sia lo stesso. Per ulteriori informazioni su queste impostazioni, vedere [Change the level of protection in the Junk Email Filter.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> A novembre 2016, Microsoft ha smesso di produrre aggiornamenti delle definizioni di posta indesiderata per i filtri SmartScreen in Exchange e Outlook. Le definizioni di posta indesiderata di SmartScreen esistenti sono state lasciata sul posto, ma è probabile che la loro efficacia si degradi nel tempo. Per ulteriori informazioni, vedere [Eliminazione del supporto per SmartScreen in Outlook ed Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Pertanto, il filtro per la posta indesiderata di Outlook è in grado di utilizzare la raccolta degli elenchi indirizzi attendibili della cassetta postale e la propria classificazione della posta indesiderata per spostare i messaggi nella cartella Posta indesiderata, anche se la regola di posta indesiderata è disabilitata nella cassetta postale.

Outlook e Outlook sul Web supportano entrambi la raccolta degli elenchi indirizzi attendibili. La raccolta degli elenchi indirizzi attendibili viene salvata nella cassetta postale di Exchange Online, quindi le modifiche apportate alla raccolta degli elenchi indirizzi attendibili in Outlook vengono visualizzate in Outlook sul Web e viceversa.

## <a name="limits-for-junk-email-settings"></a>Limiti per le impostazioni della posta indesiderata

Anche la raccolta degli elenchi indirizzi attendibili (elenco Mittenti attendibili, Destinatari attendibili e Mittenti bloccati) archiviata nella cassetta postale dell'utente viene sincronizzata con EOP. Con la sincronizzazione della directory, la raccolta degli elenchi indirizzi attendibili viene sincronizzata con Azure AD.

- La raccolta degli elenchi indirizzi attendibili nella cassetta postale dell'utente ha un limite di 510 KB, che include tutti gli elenchi, oltre a impostazioni aggiuntive per il filtro della posta indesiderata. Se un utente supera questo limite, riceverà un errore di Outlook simile al seguente:

  > Impossibile aggiungere agli elenchi di posta indesiderata del server. Le dimensioni consentite nel server sono oltre le dimensioni consentite. Il filtro per la posta indesiderata sul server verrà disabilitato fino a quando gli elenchi di posta indesiderata non saranno stati ridotti alle dimensioni consentite dal server.

  Per ulteriori informazioni su questo limite e su come modificarlo, vedere [KB2669081.](https://support.microsoft.com/help/2669081)

- La raccolta degli elenchi indirizzi attendibili sincronizzati in EOP presenta i seguenti limiti di sincronizzazione:

  - 1024 voci totali nell'elenco Mittenti attendibili, nell'elenco  Destinatari attendibili e nei contatti esterni se la posta elettronica attendibile dei contatti è abilitata.
  - 500 voci totali nell'elenco Mittenti bloccati e nell'elenco Domini bloccati.

  Quando viene raggiunto il limite di immissione 1024, si verifica quanto segue:

  - L'elenco smette di accettare voci in PowerShell e Outlook sul Web, ma non viene visualizzato alcun errore.

    Gli utenti di Outlook possono continuare ad aggiungere più di 1024 voci fino a raggiungere il limite di Outlook di 510 KB. Outlook può utilizzare queste voci aggiuntive, purché un filtro EOP non blocchi il messaggio prima del recapito alla cassetta postale (regole del flusso di posta, anti-spoofing e così via).

- Con la sincronizzazione della directory, le voci vengono sincronizzate con Azure AD nell'ordine seguente:

  1. Contatti di posta elettronica **se l'opzione Considera attendibile la posta elettronica dei contatti** personali è abilitata.
  2. L'elenco Mittenti attendibili e l'elenco Destinatari attendibili vengono combinati, de duplicati e ordinati in ordine alfabetico ogni volta che viene apportata una modifica per le prime 1024 voci.

  Vengono utilizzate le prime 1024 voci e le informazioni rilevanti vengono contrassegnate nelle intestazioni del messaggio.

  Le voci oltre il 1024 che non sono state sincronizzate con Azure AD vengono elaborate da Outlook (non da Outlook sul Web) e nessuna informazione viene contrassegnata nelle intestazioni del messaggio.

Come si può vedere, l'abilitazione dell'impostazione Considera attendibile la posta elettronica dai contatti consente di ridurre il numero di mittenti attendibili e destinatari attendibili che possono essere sincronizzati.  Se si tratta di un problema, ti consigliamo di usare Criteri di gruppo per disattivare questa funzionalità:

- Nome file: outlk16.opax
- Impostazione dei criteri: **Considera attendibili i messaggi di posta elettronica provenienti dai contatti**
