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
description: Gli amministratori possono imparare a configurare le impostazioni della posta indesiderata nelle cassette postali Exchange Online posta indesiderata. Molte di queste impostazioni sono disponibili per gli utenti Outlook o Outlook sul Web.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a401321645530d3d66ebcccd6b8aea27ce21d6e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624802"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organizzazioni con cassette postali in Exchange Online, le impostazioni di protezione da posta indesiderata dell'organizzazione sono controllate da Exchange Online Protection (EOP). Per ulteriori informazioni, vedere [Protezione da posta indesiderata in EOP.](anti-spam-protection.md)

Tuttavia, esistono anche impostazioni di protezione da posta indesiderata specifiche che gli amministratori possono configurare sulle singole cassette postali in Exchange Online:

- **Abilitare o disabilitare la** regola di posta indesiderata : La regola di posta indesiderata è una regola nascosta di Posta in arrivo denominata Regola di posta indesiderata abilitata per impostazione predefinita in ogni cassetta postale. La regola di posta indesiderata controlla le funzionalità seguenti:

  - Spostare i messaggi nella cartella Posta indesiderata in base ai criteri di protezione  da posta **indesiderata:** quando un criterio di protezione da posta indesiderata è configurato con l'azione Sposta il messaggio nella cartella Posta indesiderata per un verdetto di filtro della posta indesiderata, la regola di filtro della posta indesiderata sposta il messaggio nella cartella Posta indesiderata dopo il recapito del messaggio alla cassetta postale. Per ulteriori informazioni sui verdetti di filtro della posta indesiderata nei criteri di protezione da posta indesiderata, vedere [Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md) Analogamente, se l'eliminazione automatica di zero ore (ZAP) determina che un messaggio recapitato è posta indesiderata  o phish, la regola di filtro della posta indesiderata sposta il messaggio nella cartella Posta indesiderata per spostare il messaggio nella cartella Posta indesiderata filtro posta indesiderata azioni di verdetto. Per ulteriori informazioni su ZAP, vedere [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).

  - Impostazioni della posta indesiderata configurate dagli utenti in Outlook o Outlook  **sul Web:** la raccolta degli elenchi indirizzi attendibili è l'elenco Mittenti attendibili, l'elenco Destinatari attendibili e l'elenco Mittenti bloccati in ogni cassetta postale. Le voci in questi elenchi determinano se la regola di posta indesiderata sposta il messaggio nella cartella Posta in arrivo o Posta indesiderata. Gli utenti possono configurare la raccolta dell'elenco indirizzi attendibili per la propria cassetta postale in Outlook o Outlook sul Web (in precedenza noto come Outlook Web App). Gli amministratori possono configurare la raccolta dell'elenco indirizzi attendibili nella cassetta postale di qualsiasi utente.

Quando la regola di posta indesiderata è abilitata sulla cassetta postale, EOP è in  grado di spostare i messaggi nella cartella Posta indesiderata in base all'azione verdetto filtro posta indesiderata Spostare il messaggio nella cartella Posta indesiderata o nell'elenco Mittenti bloccati nella cassetta postale e impedire il recapito dei messaggi nella cartella Posta indesiderata (in base all'elenco Mittenti attendibili nella cassetta postale).

 Quando la regola di posta indesiderata è disabilitata nella cassetta postale, EOP non può  spostare i messaggi nella cartella Posta indesiderata in base all'azione verdetto filtro posta indesiderata Spostare il messaggio nella cartella Posta indesiderata o nella raccolta dell'elenco indirizzi attendibili nella cassetta postale.

Gli amministratori possono usare Exchange Online PowerShell per disabilitare, abilitare e visualizzare lo stato della regola di posta indesiderata nelle cassette postali. Gli amministratori possono inoltre utilizzare Exchange Online PowerShell per configurare le voci nella raccolta degli elenchi indirizzi attendibili nelle cassette postali (l'elenco Mittenti attendibili, l'elenco Destinatari attendibili e l'elenco Mittenti bloccati).

> [!NOTE]
> I messaggi provenienti da mittenti che gli utenti hanno aggiunto ai propri elenchi di mittenti attendibili ignorano il filtro connessioni come parte di EOP (il livello di probabilità di posta indesiderata è -1). Per impedire agli utenti di aggiungere voci all'elenco Mittenti attendibili in Outlook, utilizzare Criteri di gruppo come indicato nella sezione Informazioni sulle impostazioni della posta indesiderata [in Outlook](#about-junk-email-settings-in-outlook) più avanti in questo articolo. Il filtro dei criteri, il filtro contenuto e Defender per Office 365 verranno comunque applicati ai messaggi.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- È possibile utilizzare solo Exchange Online PowerShell per eseguire le procedure descritte in questo articolo. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni Exchange Online in questo articolo. In particolare,  è necessario il ruolo Destinatari di posta (assegnato  ai gruppi di ruoli Gestione  **organizzazione,** Gestione destinatari e  Destinatari di posta elettronica personalizzati per impostazione predefinita) o Il ruolo Opzioni utente (assegnato per impostazione predefinita ai gruppi di ruoli Gestione organizzazione e Help **Desk).**  Per aggiungere utenti ai gruppi di ruoli in Exchange Online, vedere [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups). Si noti che gli utenti con autorizzazioni predefinite possono eseguire le stesse procedure nella propria cassetta postale, purché possano accedere a [Exchange Online PowerShell.](/powershell/exchange/disable-access-to-exchange-online-powershell)

- Negli ambienti ibridi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (note anche come regole di trasporto) in Exchange locale per tradurre il verdetto del filtro della posta indesiderata di EOP in modo che la regola di posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per informazioni dettagliate, [vedere Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

- I mittenti attendibili per le cassette postali condivise non vengono sincronizzati con Azure AD ed EOP in base alla progettazione.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Utilizzare Exchange Online PowerShell per abilitare o disabilitare la regola di posta indesiderata in una cassetta postale

> [!NOTE]
> È possibile utilizzare solo il cmdlet **Set-MailboxJunkEmailConfiguration** per disabilitare la regola di posta indesiderata su una cassetta postale aperta in Outlook (in modalità cache Exchange) o Outlook sul Web. Se la cassetta postale non è stata aperta, verrà visualizzato l'errore: Se si desidera eliminare questo errore per le operazioni in blocco, è possibile aggiungere al `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` comando **Set-MailboxJunkEmailConfiguration.**

Per abilitare o disabilitare la regola di posta indesiderata in una cassetta postale, utilizzare la sintassi seguente:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In questo esempio viene disabilitata la regola di posta indesiderata nella cassetta postale di Ori Epstein.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In questo esempio viene disabilitata la regola di posta indesiderata per tutte le cassette postali degli utenti nell'organizzazione.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Se l'utente non ha mai aperto la propria cassetta postale, è possibile che venga visualizzato un errore quando si esegue il comando precedente. Per eliminare questo errore per le operazioni in blocco, aggiungere `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Anche se si disabilita la regola di posta indesiderata, il filtro per la posta indesiderata di Outlook (a seconda di come è configurato) può anche determinare se un messaggio è posta indesiderata e può spostare i messaggi nella cartella Posta in arrivo o Posta indesiderata in base al proprio verdetto di posta indesiderata e alla raccolta dell'elenco indirizzi attendibili nella cassetta postale. Per ulteriori informazioni, vedere la sezione [Informazioni sulle impostazioni della](#about-junk-email-settings-in-outlook) posta indesiderata in Outlook in questo articolo.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che la regola di posta indesiderata in una cassetta postale sia stata abilitata o disabilitata correttamente, utilizzare una delle procedure seguenti:

- Sostituire _\<MailboxIdentity\>_ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando seguente per verificare il **valore della proprietà Enabled:**

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Utilizzare Exchange Online PowerShell per configurare la raccolta dell'elenco indirizzi attendibili in una cassetta postale

La raccolta degli elenchi indirizzi attendibili in una cassetta postale include l'elenco Mittenti attendibili, l'elenco Destinatari attendibili e l'elenco Mittenti bloccati. Per impostazione predefinita, gli utenti possono configurare la raccolta dell'elenco indirizzi attendibili nella propria cassetta postale Outlook o Outlook sul Web. Gli amministratori possono utilizzare i parametri corrispondenti nel cmdlet **Set-MailboxJunkEmailConfiguration** per configurare la raccolta dell'elenco indirizzi attendibili nella cassetta postale di un utente. Questi parametri sono descritti nella tabella seguente.

****

|Parametro su Set-MailboxJunkEmailConfiguration|Outlook sul Web|
|---|---|
|_BlockedSendersAndDomains_|**Spostare la posta elettronica da questi mittenti o domini nella cartella Posta indesiderata**|
|_ContactsTrusted_|**Considerare attendibile la posta elettronica dai contatti**|
|_TrustedListsOnly_|**Considera attendibili solo i messaggi di posta elettronica provenienti dagli indirizzi nell'elenco Mittenti e domini attendibili e nelle liste di distribuzione attendibili**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Non spostare la posta elettronica da questi mittenti nella cartella Posta indesiderata**|
|

<sup>\*</sup>**Note**:

- In Exchange Online **le** voci di dominio nell'elenco Mittenti attendibili o nel parametro _TrustedSendersAndDomains_ non vengono riconosciute, quindi utilizzare solo gli indirizzi di posta elettronica. In EOP autonomo con sincronizzazione della directory, le voci di dominio non vengono sincronizzate per impostazione predefinita, ma è possibile abilitare la sincronizzazione per i domini. Per ulteriori informazioni, vedere [KB3019657](https://support.microsoft.com/help/3019657).

- Non è possibile modificare direttamente l'elenco destinatari attendibili utilizzando il cmdlet **Set-MailboxJunkEmailConfiguration** (il _parametro TrustedRecipientsAndDomains_ non funziona). L'elenco Mittenti attendibili viene modificato e le modifiche vengono sincronizzate con l'elenco Destinatari attendibili.

Per configurare la raccolta dell'elenco indirizzi attendibili in una cassetta postale, utilizzare la sintassi seguente:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Per immettere più valori e sovrascrivere le voci esistenti per i _parametri BlockedSendersAndDomains_ e _TrustedSendersAndDomains,_ utilizzare la sintassi seguente: `"<Value1>","<Value2>"...` . Per aggiungere o rimuovere uno o più valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In questo esempio vengono configurate le impostazioni seguenti per la raccolta degli elenchi indirizzi attendibili nella cassetta postale di Ori Epstein:

- Aggiungere il valore shopping@fabrikam.com all'elenco Mittenti bloccati.

- Rimuovere il valore chris@fourthcoffee.com dall'elenco Mittenti attendibili e Destinatari attendibili.

- Configura i contatti nella cartella Contatti in modo che siano considerati mittenti attendibili.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In questo esempio viene rimosso il contoso.com dall'elenco Mittenti bloccati in tutte le cassette postali utente dell'organizzazione.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Se l'utente non ha mai aperto la propria cassetta postale, è possibile che venga visualizzato un errore quando si eseguono i comandi precedenti. Per eliminare questo errore per le operazioni in blocco, aggiungere `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Anche se la regola di posta indesiderata è disabilitata nella cassetta postale, è comunque possibile configurare la raccolta degli elenchi indirizzi attendibili e il filtro della posta indesiderata di Outlook è in grado di spostare i messaggi nella cartella Posta in arrivo o Posta indesiderata. Per ulteriori informazioni, vedere la sezione [Informazioni sulle impostazioni della](#about-junk-email-settings-in-outlook) posta indesiderata in Outlook in questo articolo.
>
> - Il Outlook posta indesiderata include ulteriori impostazioni di raccolta dell'elenco indirizzi attendibili (ad esempio, Aggiungi automaticamente le persone che e-mail **all'elenco Mittenti attendibili**). Per ulteriori informazioni, vedere [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che la raccolta dell'elenco indirizzi attendibili sia stata configurata correttamente in una cassetta postale, eseguire una delle procedure seguenti:

- Sostituire _\<MailboxIdentity\>_ con il nome, l'alias o l'indirizzo di posta elettronica della cassetta postale ed eseguire il comando seguente per verificare i valori delle proprietà:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Se l'elenco dei valori è troppo lungo, utilizzare la sintassi seguente:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Informazioni sulle impostazioni della posta indesiderata in Outlook

Per abilitare, disabilitare e configurare le impostazioni del filtro della posta indesiderata sul lato client disponibili in Outlook, utilizzare Criteri di gruppo. Per ulteriori informazioni, vedere [Administrative Template files (ADMX/ADML) e Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019 e Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) e [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy.](https://support.microsoft.com/help/2252421)

Quando il filtro per la posta indesiderata di Outlook è  impostato sul valore predefinito Nessun filtro automatico **in** Opzioni home per la posta indesiderata, Outlook non tenta di classificare i messaggi come posta indesiderata, ma utilizza comunque \>  \>  \> l'insieme degli elenchi indirizzi attendibili (elenco Mittenti attendibili, Destinatari attendibili e Mittenti bloccati) per spostare i messaggi nella cartella Posta indesiderata dopo il recapito. Per ulteriori informazioni su queste impostazioni, vedere [Overview of the Junk Email Filter.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

Quando il filtro Outlook posta indesiderata  è impostato su Basso o **Alto,** il filtro per la posta indesiderata di Outlook utilizza la propria tecnologia di filtro SmartScreen per identificare e spostare la posta indesiderata nella cartella Posta indesiderata. Questa classificazione della posta indesiderata è separata dal livello di probabilità di posta indesiderata (SCL) determinato da EOP. In realtà, Outlook ignora il livello di probabilità di posta indesiderata da EOP (a meno che EOP non ha contrassegnato il messaggio per ignorare il filtro posta indesiderata) e utilizza i propri criteri per determinare se il messaggio è posta indesiderata. Naturalmente, è possibile che il verdetto di posta indesiderata da EOP e Outlook potrebbe essere lo stesso. Per ulteriori informazioni su queste impostazioni, vedere [Change the level of protection in the Junk Email Filter.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> A novembre 2016, Microsoft ha smesso di produrre aggiornamenti delle definizioni di posta indesiderata per i filtri SmartScreen in Exchange e Outlook. Le definizioni di posta indesiderata smartscreen esistenti sono state lasciati sul posto, ma la loro efficacia probabilmente si degraderà nel tempo. Per ulteriori informazioni, vedere [Eliminazione del supporto per SmartScreen in Outlook ed Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Pertanto, il filtro posta indesiderata Outlook è in grado di utilizzare la raccolta dell'elenco indirizzi attendibili della cassetta postale e la propria classificazione della posta indesiderata per spostare i messaggi nella cartella Posta indesiderata, anche se la regola di posta indesiderata è disabilitata nella cassetta postale.

Outlook e Outlook sul Web entrambi supportano la raccolta dell'elenco indirizzi attendibili. La raccolta degli elenchi indirizzi attendibili viene salvata nella cassetta postale di Exchange Online, quindi le modifiche apportate alla raccolta degli elenchi indirizzi attendibili in Outlook vengono visualizzate in Outlook sul Web e viceversa.

## <a name="limits-for-junk-email-settings"></a>Limiti per le impostazioni della posta indesiderata

Anche la raccolta degli elenchi indirizzi attendibili (elenco Mittenti attendibili, Destinatari attendibili e Mittenti bloccati) archiviata nella cassetta postale dell'utente viene sincronizzata con EOP. Con la sincronizzazione della directory, la raccolta degli elenchi indirizzi attendibili viene sincronizzata con Azure AD.

- La raccolta degli elenchi indirizzi attendibili nella cassetta postale dell'utente ha un limite di 510 KB, che include tutti gli elenchi, oltre a impostazioni aggiuntive per il filtro della posta indesiderata. Se un utente supera questo limite, riceverà un errore Outlook simile al seguente:

  > Impossibile aggiungere elenchi di posta indesiderata al server. Le dimensioni consentite nel server sono oltre le dimensioni consentite. Il filtro posta indesiderata sul server verrà disabilitato fino a quando gli elenchi di posta indesiderata non saranno stati ridotti alle dimensioni consentite dal server.

  Per ulteriori informazioni su questo limite e su come modificarlo, [vedere KB2669081](https://support.microsoft.com/help/2669081).

- La raccolta degli elenchi indirizzi attendibili sincronizzati in EOP presenta i limiti di sincronizzazione seguenti:

  - 1024 voci totali nell'elenco Mittenti attendibili, nell'elenco Destinatari attendibili e nei contatti esterni se è abilitata l'opzione Considera attendibile la posta **elettronica** dai miei contatti.
  - 500 voci totali nell'elenco Mittenti bloccati e Domini bloccati.

  Quando viene raggiunto il limite di immissione 1024, si verificano le operazioni seguenti:

  - L'elenco smette di accettare voci in PowerShell e Outlook sul Web, ma non viene visualizzato alcun errore.

    Outlook utenti possono continuare ad aggiungere più di 1024 voci fino a raggiungere il Outlook di 510 KB. Outlook possono utilizzare queste voci aggiuntive, purché un filtro EOP non blocchi il messaggio prima del recapito alla cassetta postale (regole del flusso di posta, anti-spoofing e così via).

- Con la sincronizzazione della directory, le voci vengono sincronizzate con Azure AD nell'ordine seguente:

  1. Contatti di posta se **è abilitata l'opzione** Considera attendibile la posta elettronica dei contatti personali.
  2. L'elenco Mittenti attendibili e l'elenco Destinatari attendibili vengono combinati, de-duplicati e ordinati alfabeticamente ogni volta che viene apportata una modifica per le prime voci 1024.

  Vengono utilizzate le prime 1024 voci e le informazioni rilevanti vengono contrassegnate nelle intestazioni dei messaggi.

  Le voci oltre 1024 che non sono state sincronizzate con Azure AD vengono elaborate da Outlook (non Outlook sul Web) e nessuna informazione viene contrassegnata nelle intestazioni dei messaggi.

Come si può vedere, l'abilitazione dell'impostazione Considera attendibile la posta elettronica dai miei contatti riduce il numero di mittenti attendibili e destinatari attendibili che possono essere sincronizzati.  Se si tratta di un problema, è consigliabile usare Criteri di gruppo per disattivare questa funzionalità:

- Nome file: outlk16.opax
- Impostazione dei criteri: **Considera attendibili i messaggi di posta elettronica dai contatti**