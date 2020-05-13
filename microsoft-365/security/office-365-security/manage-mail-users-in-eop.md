---
title: Gestire gli utenti di posta elettronica in EOP autonomo
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
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Informazioni su come gestire gli utenti di posta elettronica in Exchange Online Protection (EOP), tra cui l'utilizzo della sincronizzazione della directory, EAC e PowerShell per la gestione degli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e40465901747bcbd006d437fa527a9803aad1e24
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208646"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Gestire gli utenti di posta elettronica in EOP autonomo

Nelle organizzazioni standalone di Exchange Online Protection (EOP) prive di cassette postali di Exchange Online, gli utenti di posta elettronica sono il tipo fondamentale di account utente. Un utente di posta dispone di credenziali dell'account nell'organizzazione di EOP autonoma e può accedere alle risorse (dispongono delle autorizzazioni assegnate). L'indirizzo di posta elettronica di un utente di posta elettronica è esterno, ad esempio nell'ambiente di posta elettronica locale.

> [!NOTE]
> Quando si crea un utente di posta elettronica, l'account utente corrispondente è disponibile nell'interfaccia di amministrazione di Microsoft 365. Quando si crea un account utente nell'interfaccia di amministrazione di Microsoft 365, non è possibile utilizzare tale account per creare un utente di posta elettronica.

Il metodo consigliato per creare e gestire gli utenti di posta in EOP autonomo consiste nell'utilizzare la sincronizzazione della directory come descritto nella sezione [utilizzo della sincronizzazione della directory per la gestione degli utenti di posta elettronica](#use-directory-synchronization-to-manage-mail-users) più avanti in questo argomento.

Per le organizzazioni di EOP autonome con un numero limitato di utenti, è possibile aggiungere e gestire gli utenti di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) o in EOP standalone PowerShell come descritto in questo argomento.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire l'interfaccia di amministrazione di Exchange (EAC), vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per connettersi a PowerShell di EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Quando si creano utenti di posta elettronica in EOP PowerShell, è possibile che si verifichi la limitazione. Inoltre, i cmdlet di PowerShell di EOP utilizzano un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. In particolare, per impostazione predefinita, sono necessari i ruoli Creazione destinatario di posta elettronica (Crea) e destinatari della posta (modifica), assegnati ai gruppi di ruoli OrganizationManagement (Global Admins) e RecipientManagement. Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. Visitare il forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Utilizzare l'interfaccia di amministrazione di Exchange per gestire gli utenti di posta elettronica

### <a name="use-the-eac-to-create-mail-users"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare utenti di posta

1. Nell'interfaccia di amministrazione di Exchange **Recipients** , accedere a \> **contatti** destinatari

2. Fare clic su **nuova** ![ nuova icona ](../../media/ITPro-EAC-AddIcon.png) . Nella pagina **nuovo utente di posta elettronica** che viene visualizzata, configurare le impostazioni seguenti. Sono necessarie le impostazioni contrassegnate con un <sup>\*</sup> .

   - **Nome**

   - **Iniziali**: la metà iniziale della persona.

   - **Cognome**

   - <sup>\*</sup>**Nome visualizzato**: per impostazione predefinita, questa casella consente di visualizzare i valori delle caselle **nome**, **iniziali**e **Cognome** . È possibile accettare questo valore o modificarlo. Il valore deve essere univoco e ha una lunghezza massima di 64 caratteri.

   - <sup>\*</sup>**Alias**: immettere un alias univoco, con un massimo di 64 caratteri, per l'utente

   - **Indirizzo di posta elettronica esterno**: immettere l'indirizzo di posta elettronica dell'utente. Il dominio deve essere esterno all'organizzazione basata su cloud.

   - <sup>\*</sup>**ID utente**: immettere l'account che verrà utilizzato dalla persona per accedere al servizio. L'ID utente è costituito da un nome utente a sinistra del simbolo @ e da un dominio sul lato destro.

   - <sup>\*</sup>**Nuova password** e <sup>\*</sup> **Conferma password**: immettere e immettere di nuovo la password dell'account. Verificare che la password sia conforme ai requisiti di lunghezza, complessità e cronologia delle password dell'organizzazione.

3. Al termine fare clic su **Salva** per creare l'utente di posta.

### <a name="use-the-eac-to-modify-mail-users"></a>Utilizzo di EAC per modificare gli utenti di posta elettronica

1. Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.

2. Selezionare l'utente di posta che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) .

3. Nella pagina delle proprietà dell'utente di posta che si apre, fare clic su una delle seguenti schede per visualizzare o modificare le proprietà.

   Al termine, scegliere **Salva**.

#### <a name="general"></a>Generale

Utilizzare la scheda **generale** per visualizzare o modificare le informazioni di base sull'utente di posta elettronica.

- **Nome**

- **Iniziali**

- **Cognome**

- **Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nelle righe a e da: nel messaggio di posta elettronica e nell'elenco dei contatti nell'interfaccia di amministrazione di Exchange. Questo nome non può contenere spazi vuoti prima o dopo il nome visualizzato.

- **ID utente**: questo è l'account dell'utente in Microsoft 365. Non è possibile modificare questo valore qui.

#### <a name="contact-information"></a>Informazioni di contatto

Utilizzare la scheda **informazioni di contatto** per visualizzare o modificare le informazioni di contatto dell'utente. Le informazioni di questa pagina vengono visualizzate nella Rubrica.

- **Via**
- **Città**
- **Stato/Provincia**
- **CAP**
- **Paese/area geografica**
- **Ufficio**
- **Cellulare**
- **Fax**
- **Altre opzioni**

  - **Ufficio**
  - **Abitazione**
  - **Pagina Web**
  - **Note**

#### <a name="organization"></a>Organizzazione

Utilizzare la scheda **organizzazione** per registrare informazioni dettagliate sul ruolo dell'utente nell'organizzazione.

- **Titolo**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere utenti di posta

1. Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.

2. Selezionare l'utente di posta che si desidera rimuovere, quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Utilizzo di PowerShell per gestire gli utenti di posta elettronica

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Utilizzo di PowerShell EOP autonomo per visualizzare gli utenti di posta elettronica

Per restituire un elenco riepilogativo di tutti gli utenti di posta elettronica in EOP PowerShell autonomo, eseguire il comando riportato di seguito:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Per visualizzare informazioni dettagliate su un utente di posta elettronica specifico, sostituire \< MailUserIdentity \> con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire i comandi seguenti:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) e [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Utilizzo di PowerShell EOP autonomo per creare utenti di posta elettronica

Per creare utenti di posta elettronica in EOP standalone PowerShell, utilizzare la sintassi seguente:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Note**:

- Il parametro _Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco. Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.
- Se non si utilizza il parametro _alias_ , il lato sinistro del parametro _MicrosoftOnlneServicesID_ viene utilizzato per l'alias.
- Se non si utilizza il parametro _ExternalEmailAddress_ , viene utilizzato il valore _MicrosoftOnlineServicesID_ per l'indirizzo di posta elettronica esterno.

In questo esempio viene creato un utente di posta elettronica con le seguenti impostazioni:

- Il nome è JeffreyZeng e il nome visualizzato è Jeffrey Zeng.
- Il nome è Jeffrey e il cognome è Zeng.
- L'alias è jeffreyz.
- L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.
- Il nome dell'account è jeffreyz@contoso.onmicrosoft.com.
- La password è Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Utilizzo di PowerShell EOP autonomo per modificare gli utenti di posta elettronica

Per modificare gli utenti di posta elettronica esistenti in EOP standalone PowerShell, utilizzare la sintassi seguente:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

In questo esempio viene impostato l'indirizzo di posta elettronica esterno per Pilar Pinilla.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In questo esempio viene impostata la proprietà Company per tutti gli utenti di posta di Contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Utilizzo di PowerShell EOP autonomo per rimuovere gli utenti di posta elettronica

Per rimuovere gli utenti di posta elettronica in EOP PowerShell autonomo, sostituire \< MailUserIdentity \> con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire il comando riportato di seguito:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In questo esempio viene rimosso l'utente di posta elettronica per Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta creazione, modifica o rimozione degli utenti di posta elettronica in EOP autonomo, utilizzare una delle seguenti procedure:

- Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**. Verificare che l'utente di posta elettronica sia elencato (o non sia elencato). Selezionare l'utente di posta elettronica e visualizzare le informazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-AddIcon.png) per visualizzare le impostazioni.

- In EOP standalone PowerShell, eseguire il comando riportato di seguito per verificare che l'utente di posta elettronica sia elencato (o non sia elencato):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Sostituire \< MailUserIdentity \> con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire i comandi seguenti per verificare le impostazioni:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Utilizzare la sincronizzazione della directory per gestire gli utenti di posta

In EOP autonomo, la sincronizzazione della directory è disponibile per i clienti con Active Directory locale. È possibile sincronizzare tali account in Azure Active Directory (Azure AD), in cui vengono archiviate le copie degli account nel cloud. Quando si sincronizzano gli account utente esistenti in Azure Active Directory, è possibile visualizzarli nel riquadro **destinatari** dell'interfaccia di amministrazione di Exchange (EAC) o in EOP standalone PowerShell.

**Note**:

- Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365, ma non verranno sincronizzati con Active Directory locale. Tuttavia questi non verranno sincronizzati con Active Directory in locale poiché la sincronizzazione della directory sincronizza solamente i destinatari dall'Active Directory locale al cloud.

- Si consiglia di utilizzare la sincronizzazione della directory con le seguenti funzionalità:

  - Elenchi di **Mittenti attendibili di Outlook e elenchi di mittenti bloccati**: quando vengono sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro di posta indesiderata nel servizio. Questo consente agli utenti di gestire l'elenco dei mittenti attendibili e l'elenco dei mittenti bloccati con le singole voci del mittente e del dominio. Per ulteriori informazioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).

  - **Blocking Edge basato su directory (DBEB)**: per ulteriori informazioni su DBEB, vedere [use directory based Edge Blocking to Reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Accesso degli utenti finali alla quarantena**: per accedere ai messaggi in quarantena, i destinatari devono disporre di un ID utente e di una password validi nel servizio. Per ulteriori informazioni sulla quarantena, vedere [trovare e rilasciare i messaggi in quarantena come utente](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).

  - **Regole del flusso di posta (note anche come regole di trasporto)**: quando si utilizza la sincronizzazione della directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud ed è quindi possibile creare le regole del flusso di posta che devono essere indirizzate a utenti e/o gruppi specifici senza dover aggiungerle manualmente nel servizio. Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) tramite la sincronizzazione delle directory.

Ottenere le autorizzazioni necessarie e prepararsi per la sincronizzazione della directory, come descritto in [che cos'è Hybrid Identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Sincronizzare le directory con Azure Active Directory Connect (AAD Connect)

1. Attivare la sincronizzazione della directory come descritto in [Azure ad Connect Sync: understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Installare e configurare un computer locale per l'esecuzione di AAD Connect come descritto in [Prerequisites for Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Selezionare il tipo di installazione da utilizzare per Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Personalizzata](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Autenticazione pass-through](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto.

Dopo aver configurato la sincronizzazione, accertarsi di verificare che AAD Connect sia sincronizzato correttamente. In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale.
