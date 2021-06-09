---
title: Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geografico
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Informazioni su come amministrare Exchange Online multi-geo nell'ambiente Microsoft 365 con PowerShell.
ms.openlocfilehash: c8f06318313c4192fc2b3a289727933c5a54f3ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905585"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geografico

Exchange Online PowerShell è necessario per visualizzare e configurare più proprietà geografiche nell'Microsoft 365 locale. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

È necessario il [modulo di PowerShell di Microsoft Azure Active Directory](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 o versione successiva in V1. x per visualizzare la proprietà **PreferredDataLocation** sugli oggetti utente. Gli oggetti utente sincronizzati con AAD Connect in AAD non possono contenere i valori **PreferredDataLocation** modificati direttamente tramite ADD PowerShell. Gli oggetti utente solo cloud possono essere modificati tramite AAD PowerShell. Per connettersi a PowerShell di Azure Active Directory, vedere [Connettersi a PowerShell](connect-to-microsoft-365-powershell.md).

In Exchange Online multi-geo, non è necessario eseguire alcuna procedura manuale per aggiungere geo al tenant. Dopo aver ricevuto il post del Centro messaggi che indica che multi-geo è pronto per Exchange Online, tutte le geo disponibili saranno pronte e configurate per l'uso.

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>È possibile connettersi direttamente a una posizione geografica con PowerShell di Exchange Online.

In genere, PowerShell di Exchange Online si connetterà alla posizione geografica centrale. Tuttavia, è anche possibile connettersi alla posizioni geografiche satellite. Per una migliore prestazione, è consigliabile connettersi direttamente alla posizione geografica satellite quando si gestiscono solo gli utenti di tale specifica posizione.

I requisiti per l'installazione e l'uso del modulo EXO V2 sono descritti in [Installazione e gestione del modulo V2 EXO](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

Per connettersi Exchange Online PowerShell a una posizione geografica specifica, il *parametro ConnectionUri* è diverso rispetto alle normali istruzioni di connessione. Il resto dei comandi e i valori sono uguali.

In particolare, è necessario aggiungere il `?email=<emailaddress>` valore alla fine del valore _ConnectionUri._ `<emailaddress>` è l'indirizzo di posta **elettronica di qualsiasi** cassetta postale nella posizione geografica di destinazione. Le autorizzazioni per la cassetta postale o la relazione con le credenziali non sono un fattore. l'indirizzo di posta elettronica indica Exchange Online PowerShell dove connettersi.

Microsoft 365 o Microsoft 365 GCC clienti in genere non devono utilizzare il parametro _ConnectionUri_ per connettersi a Exchange Online PowerShell. Tuttavia, per connettersi a una posizione geografica specifica, è necessario utilizzare il parametro _ConnectionUri_ in modo da poter `?email=<emailaddress>` utilizzare il valore.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Connessione a una posizione geografica in Exchange Online PowerShell

Le istruzioni di connessione seguenti funzionano per gli account che sono o non sono configurati per l'autenticazione a più fattori (MFA).

1. In una finestra di Windows PowerShell caricare il modulo EXO V2 eseguendo il comando seguente:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. Nell'esempio seguente, admin@contoso.onmicrosoft.com è l'account amministratore e la posizione geografica di destinazione è la posizione geografica in cui risiede olga@contoso.onmicrosoft.com cassetta postale.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. Immettere la password per il admin@contoso.onmicrosoft.com nel prompt visualizzato. Se l'account è configurato per MFA, devi anche immettere il codice di sicurezza.

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Visualizzare le posizioni geografiche disponibili configurate nella propria organizzazione di Exchange Online

Per visualizzare l'elenco di località geografiche configurate in Microsoft 365 Multi-Geo, eseguire il comando seguente in PowerShell di Exchange Online:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Visualizzare la posizione geografica centrale per la propria organizzazione di Exchange Online

Per visualizzare la posizione geografica centrale del proprio tenant, eseguire il comando seguente in PowerShell di Exchange Online:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>Individuare la posizione geografica di una cassetta postale

La cmdlet **Get-Mailbox** in PowerShell di Exchange Online mostra le seguenti proprietà multi-geografica relative alle cassette postali:

- **Database**: le prime 3 lettere del nome del database corrispondono al codice geografico, che indica dove la cassetta postale è attualmente ubicata. Per cassette postali di archiviazione Online, sarà necessario usare le proprietà di **ArchiveDatabase**.

- **MailboxRegion**: specifica il codice posizione geografica impostato dall'amministratore (sincronizzato da **PreferredDataLocation** in Azure AD).

- **MailboxRegionLastUpdateTime**: indica quando MailboxRegion è stato aggiornato l’ultima volta (automaticamente o manualmente).

Per visualizzare le proprietà di una cassetta postale, utilizzare la sintassi seguente:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Ad esempio, per visualizzare le informazioni di posizione geografica della cassetta postale chris@contoso.onmicrosoft.com, eseguire il comando seguente:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

L'output del comando avrà questo aspetto:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Se il codice di posizione geografica nel nome del database non corrisponde al valore **MailboxRegion,** la cassetta postale verrà automaticamente inserita in una coda di rilocazione e spostata nella posizione geografica specificata dal valore **MailboxRegion** (Exchange Online cerca una mancata corrispondenza tra questi valori di proprietà).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Spostare una cassetta postale esistente solo nel cloud in una posizione geografica specifica

Un utente solo cloud è un utente non sincronizzato con il tenant tramite AAD Connect. Tale utente è stato creato direttamente in Azure AD. Usare il cmdlet **Get-MsolUser** e **Set-MsolUser** nel modulo di Azure Active Directory per Windows PowerShell per visualizzare o specificare la posizione geografica in cui verrà archiviata la cassetta postale dell'utente solo cloud.

Per visualizzare i valori **PreferredDataLocation** di un utente, utilizzare la sintassi in Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Ad esempio, per visualizzare i valori **PreferredDataLocation** dell’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Per modificare il valore **PreferredDataLocation** per un utente solo cloud, utilizzare la sintassi seguente in Azure AD PowerShell:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Ad esempio, per impostare i valori **PreferredDataLocation** sulla geografica dell’Unione Europea per l’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Come accennato in precedenza, non è possibile utilizzare questa procedura per gli oggetti utente sincronizzati da Active Directory locale. È necessario modificare il valore **PreferredDataLocation** in Active Directory e sincronizzarlo con AAD Connect. Per ulteriori informazioni, vedere [Sincronizzazione di Azure Active Directory Connect: configurare il percorso di dati preferito per le risorse di Microsoft 365](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - Il tempo necessario per spostare una cassetta postale in una nuova posizione geografica dipende da diversi fattori:
>
>   - Le dimensioni e tipo di cassetta postale.
>   - Il numero totale di cassette postali di cui eseguire la migrazione.
>   - La disponibilità delle risorse di spostamento.

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>Spostare una cassetta postale inattiva in una posizione geografica specifica

Non è possibile spostare le cassette postali inattive conservate per motivi di conformità (ad esempio, cassette postali con conservazione per controversia legale) modificando il **relativo valore PreferredDataLocation.** Per spostare una cassetta postale inattiva in una posizione geografica diversa, eseguire la procedura seguente:

1. Ripristinare la cassetta postale inattiva. Per istruzioni, vedere [Recover an inactive mailbox](../compliance/recover-an-inactive-mailbox.md).

2. Impedire all'Assistente cartelle gestite di elaborare la cassetta postale recuperata sostituendo con il nome, l'alias, l'account o l'indirizzo di posta elettronica della cassetta postale ed eseguendo il comando seguente \<MailboxIdentity\> [in Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. Assegnare **una Exchange Online piano 2** alla cassetta postale recuperata. Questo passaggio è necessario per impostare nuovamente il blocco per controversia legale per la cassetta postale. Per istruzioni, vedere [Assegnare licenze agli utenti.](../admin/manage/assign-licenses-to-users.md)

4. Configurare il **valore PreferredDataLocation** nella cassetta postale come descritto nella sezione precedente.

5. Dopo aver confermato che la cassetta postale è stata spostata nella nuova posizione geografica, ripostare la cassetta postale recuperata in Conservazione per controversia legale. Per istruzioni, vedere [Place a mailbox on Litigation Hold](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold).

6. Dopo aver verificato che sia in corso il blocco per controversia legale, consentire all'Assistente cartelle gestite di elaborare di nuovo la cassetta postale sostituendo con il nome, l'alias, l'account o l'indirizzo di posta elettronica della cassetta postale ed eseguendo il comando seguente \<MailboxIdentity\> [in Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. Rendere di nuovo inattiva la cassetta postale rimuovendo l'account utente associato alla cassetta postale. Per istruzioni, vedere [Eliminare un utente dall'organizzazione.](../admin/add-users/delete-a-user.md) Questo passaggio rilascia anche la licenza Exchange Online Piano 2 per altri usi.

**Nota:** quando si sposta una cassetta postale inattiva in una posizione geografica diversa, è possibile che si influisca sui risultati della ricerca di contenuto o sulla possibilità di eseguire ricerche nella cassetta postale dalla posizione geografica precedente. Per ulteriori informazioni, vedere [Ricerca ed esportazione di contenuto in ambienti multi-geografici.](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Creare nuove cassette postali nel cloud in una posizione geografica specifica

Per creare una nuova cassetta postale in una posizione geografica specifica, è necessario procedere come segue:

- Configurare il **valore PreferredDataLocation** come [](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) descritto nella precedente sezione Spostare una  cassetta postale esistente solo cloud in una posizione geografica specifica prima di creare la cassetta postale in Exchange Online. Ad esempio, configurare il **valore PreferredDataLocation** per un utente prima di assegnare una licenza.

- Assegnare una licenza contemporaneamente all’impostazione del valore **PreferredDataLocation**.

Per creare un nuovo utente solo cloud con licenza (non sincronizzato con AAD Connect) in un determinata posizione geografica, usare la sintassi seguente in Azure AD PowerShell:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

In questo esempio crea un nuovo account utente per Elizabeth Brunner con i valori seguenti:

- Nome dell'entità utente: ebrunner@contoso.onmicrosoft.com
- Nome: entrambe
- Cognome: Brunner
- Nome visualizzato: Elizabeth Brunner
- Password: generata casualmente e visualizzata nei risultati del comando (in quanto non vengono usati i parametri della *Password*)
- Licenza: `contoso:ENTERPRISEPREMIUM` (E5)
- Posizione: Australia (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Per ulteriori informazioni sulla creazione di nuovi account utente e la ricerca di valori di LicenseAssignment in Azure AD PowerShell, vedere [Creare account utente con PowerShell](create-user-accounts-with-microsoft-365-powershell.md) e [Visualizzare le licenze e i servizi con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Se si sta utilizzando PowerShell di Exchange Online per abilitare una cassetta postale si desidera che questa sia creata direttamente nella posizione geografica specificata in **PreferredDataLocation**, è necessario utilizzare un cmdlet di Exchange Online come **Enable-Mailbox** o **New-Mailbox** direttamente con il servizio di cloud. Se si usa il cmdlet di Exchange PowerShell locale **Enable-RemoteMailbox**, la cassetta postale verrà creata nella posizione geografica centrale.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Effettuare l’integrazione di cassette postali locali esistenti in una posizione geografica specifica

È possibile usare i processi e gli strumenti standard di integrazione per eseguire la migrazione di una cassetta postale di un'organizzazione di Exchange locale a Exchange Online, tra cui la [Dashboard di migrazione nell'interfaccia](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)e il cmdlet [New-MigrationBatch ](/powershell/module/exchange/new-migrationbatch) in PowerShell di Exchange Online.

Il primo passaggio consiste nel verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e verificare che sia configurato il corretto valore della **PreferredDataLocation** in Azure AD. Gli strumenti di integrazione rispetteranno il valore **PreferredDataLocation** e verrà eseguita la migrazione delle cassette postali direttamente alla posizione geografica specificata.

Oppure, la procedura seguente consente di aggiungere cassette postali direttamente a una posizione geografica specifica tramite il cmdlet [New-MoveRequest](/powershell/module/exchange/new-moverequest) in PowerShell di Exchange Online.

1. Verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e che la **PreferredDataLocation** sia impostata sul valore desiderato in Azure AD. Il valore di **PreferredDataLocation** sarà sincronizzato con l’attributo di **MailboxRegion** del corrispondente oggetto utente di posta in Exchange Online.

2. Connettersi direttamente a specifici posizioni geografiche satellite seguendo le istruzioni di connessione dei passaggi precedenti di questo argomento.

3. Nella finestra di PowerShell di Exchange Online, archiviare le credenziali di amministratore locale usate per eseguire la migrazione delle cassette postali in una variabile, eseguendo il comando seguente:

   ```powershell
   $RC = Get-Credential
   ```

4. Su PowerShell di Exchange Online, creare una nuova **New-MoveRequest** simile all’esempio seguente:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Ripetere il passaggio #4 per ogni cassetta postale di cui è necessario eseguire la migrazione dall’Exchange locale alla posizione satellite con cui si è attualmente connessi.

6. Se è necessario eseguire la migrazione di altre cassette postali a diverse posizioni geografiche satellite, ripetere i passaggi da 2 a 4 per ogni località satellite specifica.

## <a name="multi-geo-reporting"></a>Creazione di report multi-geografici

**I report sull'utilizzo di Multi-Geo** nell’interfaccia di amministrazione di Microsoft 365 mostrano il numero di utenti in base alla località geografica. Il report mostra la distribuzione degli utenti per il mese corrente e fornisce i dati cronologici dagli ultimi 6 mesi.

## <a name="see-also"></a>Vedere anche

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)