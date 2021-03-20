---
title: Gestire gli utenti di posta in Exchange Online Protection autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Informazioni su come gestire gli utenti di posta elettronica in Exchange Online Protection (EOP), tra cui l'utilizzo della sincronizzazione della directory, EAC e PowerShell per gestire gli utenti.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910619"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Gestire gli utenti di posta in Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

Nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, gli utenti di posta elettronica sono il tipo fondamentale di account utente. Un utente di posta elettronica dispone delle credenziali dell'account nell'organizzazione EOP autonoma e può accedere alle risorse (a cui sono assegnate le autorizzazioni). L'indirizzo di posta elettronica di un utente di posta elettronica è esterno, ad esempio nell'ambiente di posta elettronica locale.

> [!NOTE]
> Quando si crea un utente di posta elettronica, l'account utente corrispondente è disponibile nell'interfaccia di amministrazione di Microsoft 365. Quando si crea un account utente nell'interfaccia di amministrazione di Microsoft 365, non è possibile utilizzare tale account per creare un utente di posta elettronica.

Il metodo consigliato per creare e gestire gli utenti di posta in EOP autonomo è quello di utilizzare la sincronizzazione della directory come descritto nella sezione Utilizzare la [sincronizzazione della directory](#use-directory-synchronization-to-manage-mail-users) per gestire gli utenti di posta elettronica più avanti in questo articolo.

Per le organizzazioni EOP autonome con un numero limitato di utenti, è possibile aggiungere e gestire gli utenti di posta nell'interfaccia di amministrazione di Exchange (EAC) o in PowerShell EOP autonomo come descritto in questo articolo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire l'interfaccia di amministrazione di Exchange ( EAC), vedere Interfaccia di amministrazione [di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Quando si creano utenti di posta elettronica in PowerShell di EOP, è possibile che si verifichino limitazioni. Inoltre, i cmdlet di PowerShell di EOP utilizzano un metodo di elaborazione batch che determina un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection. In particolare, è necessario disporre dei ruoli Creazione destinatario di posta **(creazione)** e Destinatari  di posta **(modifica),** assegnati ai gruppi di ruoli **Gestione** organizzazione (amministratori globali) e Gestione destinatari per impostazione predefinita. Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. Visitare il forum [di Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Utilizzare l'interfaccia di amministrazione di Exchange per gestire gli utenti di posta

### <a name="use-the-eac-to-create-mail-users"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare utenti di posta

1. Nell'interfaccia di amministrazione di Exchange, accedere **a Destinatari** \> **Contatti**

2. Fare **clic su** Nuova icona Nuovo ![ ](../../media/ITPro-EAC-AddIcon.png) . Nella pagina **Nuovo utente di** posta elettronica visualizzata configurare le impostazioni seguenti. Le impostazioni contrassegnate con <sup>\*</sup> un sono obbligatorie.

   - **Nome**

   - **Iniziali**: iniziale centrale della persona.

   - **Cognome**

   - <sup>\*</sup>**Nome visualizzato**: per impostazione predefinita, questa casella mostra i valori delle caselle **Nome,** Iniziali **e Cognome.** È possibile accettare questo valore o modificarlo. Il valore deve essere univoco e ha una lunghezza massima di 64 caratteri.

   - <sup>\*</sup>**Alias**: immettere un alias univoco, utilizzando fino a 64 caratteri, per l'utente

   - **Indirizzo di posta elettronica esterno:** immettere l'indirizzo di posta elettronica dell'utente. Il dominio deve essere esterno all'organizzazione basata su cloud.

   - <sup>\*</sup>**ID utente:** immettere l'account che verrà utilizzato dalla persona per accedere al servizio. L'ID utente è costituito da un nome utente a sinistra del simbolo (@) (@) e da un dominio sul lato destro.

   - <sup>\*</sup>**Nuova password** e <sup>\*</sup> **Conferma password**: immettere e immettere di nuovo la password dell'account. Verificare che la password sia conforme ai requisiti di lunghezza, complessità e cronologia della password dell'organizzazione.

3. Al termine fare clic su **Salva** per creare l'utente di posta.

### <a name="use-the-eac-to-modify-mail-users"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare gli utenti di posta

1. Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.

2. Selezionare l'utente di posta elettronica che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/ITPro-EAC-AddIcon.png) .

3. Nella pagina delle proprietà dell'utente di posta elettronica visualizzata fare clic su una delle schede seguenti per visualizzare o modificare le proprietà.

   Al termine, fare clic su **Salva**.

#### <a name="general"></a>Generale

Utilizzare la **scheda Generale** per visualizzare o modificare le informazioni di base sull'utente di posta.

- **Nome**

- **Iniziali**

- **Cognome**

- **Nome visualizzato**: questo nome viene visualizzato nella rubrica dell'organizzazione, nelle righe A: e Da: nei messaggi di posta elettronica e nell'elenco dei contatti nell'interfaccia di amministrazione di Exchange. Questo nome non può contenere spazi vuoti prima o dopo il nome visualizzato.

- **ID utente:** questo è l'account dell'utente in Microsoft 365. Non è possibile modificare questo valore qui.

#### <a name="contact-information"></a>Informazioni di contatto

Utilizzare la **scheda Informazioni di** contatto per visualizzare o modificare le informazioni di contatto dell'utente. Le informazioni di questa pagina vengono visualizzate nella Rubrica.

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

Utilizzare la **scheda** Organizzazione per registrare informazioni dettagliate sul ruolo dell'utente nell'organizzazione.

- **Titolo**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Rimozione degli utenti di posta tramite EAC

1. Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.

2. Selezionare l'utente di posta che si desidera rimuovere e quindi fare clic su **Rimuovi** ![ Icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Utilizzare PowerShell per gestire gli utenti di posta

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Usare PowerShell EOP autonomo per visualizzare gli utenti di posta

Per restituire un elenco riepilogativo di tutti gli utenti di posta elettronica in PowerShell EOP autonomo, eseguire il comando seguente:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Per visualizzare informazioni dettagliate su un utente di posta specifico, sostituire con il nome, l'alias o il nome dell'account dell'utente di posta \<MailUserIdentity\> elettronica ed eseguire i comandi seguenti:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-Recipient](/powershell/module/exchange/get-recipient) e [Get-User](/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Utilizzare PowerShell EOP autonomo per creare utenti di posta

Per creare utenti di posta elettronica in PowerShell EOP autonomo, utilizzare la sintassi seguente:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Note**:

- Il _parametro Name_ è obbligatorio, ha una lunghezza massima di 64 caratteri e deve essere univoco. Se non si utilizza il parametro _DisplayName_, il valore del parametro _Name_ viene utilizzato per il nome visualizzato.
- Se non si utilizza il parametro _Alias,_ viene utilizzato il lato sinistro del parametro _MicrosoftOnlineServicesID_ per l'alias.
- Se non si utilizza il _parametro ExternalEmailAddress,_ viene utilizzato il valore _MicrosoftOnlineServicesID_ per l'indirizzo di posta elettronica esterno.

In questo esempio viene creato un utente di posta con le impostazioni seguenti:

- Il nome è JeffreyZeng e il nome visualizzato è Jeffrey Zeng.
- Il nome è Jeffrey e il cognome è Zeng.
- L'alias è jeffreyz.
- L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.
- Il nome dell'account jeffreyz@contoso.onmicrosoft.com.
- La password è Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-EOPMailUser.](/powershell/module/exchange/new-eopmailuser)

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Utilizzare PowerShell EOP autonomo per modificare gli utenti di posta

Per modificare gli utenti di posta elettronica esistenti in PowerShell EOP autonomo, utilizzare la sintassi seguente:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Utilizzare PowerShell EOP autonomo per rimuovere gli utenti di posta

Per rimuovere gli utenti di posta elettronica in PowerShell EOP autonomo, sostituire con il nome, l'alias o il nome dell'account dell'utente di posta \<MailUserIdentity\> elettronica ed eseguire il comando seguente:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In questo esempio viene rimosso l'utente di posta per Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver creato, modificato o rimosso correttamente gli utenti di posta elettronica in EOP autonomo, utilizzare una delle procedure seguenti:

- Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**. Verificare che l'utente di posta sia elencato (o non sia elencato). Selezionare l'utente di posta elettronica e visualizzare le informazioni nel riquadro Dettagli oppure fare clic **su Modifica** icona Modifica per visualizzare ![ le ](../../media/ITPro-EAC-AddIcon.png) impostazioni.

- In PowerShell EOP autonomo, eseguire il comando seguente per verificare che l'utente di posta sia elencato (o non sia elencato):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Sostituire con il nome, l'alias o il nome dell'account dell'utente di posta elettronica ed eseguire i \<MailUserIdentity\> comandi seguenti per verificare le impostazioni:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Utilizzare la sincronizzazione della directory per gestire gli utenti di posta

In EOP autonomo, la sincronizzazione della directory è disponibile per i clienti con Active Directory locale. È possibile sincronizzare tali account con Azure Active Directory (Azure AD), dove le copie degli account sono archiviate nel cloud. Quando si sincronizzano gli account utente esistenti con Azure  Active Directory, è possibile visualizzare tali utenti nel riquadro Destinatari dell'interfaccia di amministrazione di Exchange (EAC) o in PowerShell EOP autonomo.

**Note**:

- Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365, ma non verranno sincronizzati con Active Directory locale. Tuttavia questi non verranno sincronizzati con Active Directory in locale poiché la sincronizzazione della directory sincronizza solamente i destinatari dall'Active Directory locale al cloud.

- Si consiglia di utilizzare la sincronizzazione della directory con le seguenti funzionalità:

  - **Elenchi Mittenti attendibili di Outlook** e Mittenti bloccati : quando vengono sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro posta indesiderata nel servizio. In questo modo gli utenti possono gestire il proprio elenco Mittenti attendibili e Mittenti bloccati con singole voci di mittente e dominio. Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Directory Based Edge Blocking (DBEB):** per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Accesso dell'utente finale alla** quarantena : per accedere ai messaggi in quarantena, i destinatari devono disporre di un ID utente e di una password validi nel servizio. Per ulteriori informazioni sulla quarantena, vedere [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).

  - Regole del flusso di posta (note anche come regole di **trasporto):** quando si utilizza la sincronizzazione della directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud ed è quindi possibile creare regole del flusso di posta per utenti e/o gruppi specifici senza doverli aggiungere manualmente nel servizio. Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) tramite la sincronizzazione delle directory.

Ottenere le autorizzazioni necessarie e prepararsi per la sincronizzazione della directory, come descritto in Che cos'è l'identità [ibrida con Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Sincronizzare le directory con Azure Active Directory Connect (AAD Connect)

1. Attivare la sincronizzazione della directory come descritto in [Sincronizzazione di Azure AD Connect: informazioni e personalizzazione della sincronizzazione.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

2. Installare e configurare un computer locale per l'esecuzione di AAD Connect, come descritto in [Prerequisiti per Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Selezionare il tipo di installazione da usare per Azure AD Connect:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Personalizzato](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Autenticazione pass-through](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto.

Dopo aver configurato la sincronizzazione, verificare che AAD Connect sia sincronizzato correttamente. In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale.