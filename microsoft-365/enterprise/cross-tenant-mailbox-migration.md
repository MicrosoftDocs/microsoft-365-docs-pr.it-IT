---
title: Migrazione delle cassette postali tra tenant
description: Come spostare le cassette postali tra Microsoft 365 o i tenant di Office 365.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 06a82fda31e602ed2feb53d00e8839daf801bf7e
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277495"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migrazione delle cassette postali tra tenant (anteprima)

In precedenza, quando un tenant di Exchange Online aveva bisogno di spostare le cassette postali in un altro tenant nello stesso servizio Exchange Online, avrebbe dovuto trasferisce completamente in locale e quindi Onboard a un nuovo tenant. Con la nuova funzionalità di migrazione delle cassette postali Cross-tenant, gli amministratori tenant in entrambi i tenant di origine e di destinazione possono spostare le cassette postali tra i tenant con dipendenze dell'infrastruttura minime nei rispettivi sistemi locali. In questo modo viene eliminata la necessità di trasferisce e delle cassette postali.

In genere, durante le fusioni o dismissioni, è necessaria la possibilità di spostare gli utenti e il contenuto in un nuovo tenant. Quando l'amministratore del tenant di destinazione esegue lo spostamento, viene chiamato spostamento di tipo pull, analogo a quello locale per le migrazioni di onboarding sul cloud.

Gli spostamenti delle cassette postali di Exchange tra tenant sono completamente autogestiti dagli amministratori tenant, utilizzando interfacce ben note che possono essere inserite nello script nei flussi di lavoro di grandi dimensioni necessari per la transizione degli utenti alla nuova organizzazione. Gli amministratori possono utilizzare il `New-MigrationBatch` cmdlet, disponibile tramite il ruolo di gestione Sposta cassette postali, per eseguire gli spostamenti tra tenant. Il processo di spostamento include controlli di autorizzazione tenant durante la sincronizzazione e la finalizzazione delle cassette postali. 
 
Gli utenti che eseguono la migrazione devono essere presenti nel sistema di Exchange Online tenant di destinazione come MailUsers, contrassegnati con attributi specifici per abilitare gli spostamenti tra tenant. Il sistema avrà esito negativo per gli utenti che non sono stati configurati correttamente nel tenant di destinazione. 

Al termine degli spostamenti, la cassetta postale del sistema di origine viene convertita in MailUser e l'oggetto targetAddress (visualizzato come ExternalEmailAddress in Exchange) viene contrassegnato con l'indirizzo di routing del tenant di destinazione. Questo processo lascia l'MailUser legacy nel tenant di origine e consente un periodo di coesistenza e instradamento della posta. Quando i processi aziendali lo consentono, il tenant di origine potrebbe rimuovere l'MailUser di origine oppure convertirlo in un contatto di posta elettronica. 

Le migrazioni delle cassette postali di Exchange cross-tenant sono supportate per i tenant in modalità ibrida o solo cloud o per qualsiasi combinazione dei due.

In questo articolo viene descritto il processo per gli spostamenti delle cassette postali Cross-tenant e vengono fornite indicazioni su come preparare i tenant di origine e di destinazione per lo spostamento di contenuto. 

## <a name="preparing-source-and-target-tenants"></a>Preparazione degli inquilini di origine e di destinazione

La funzionalità di migrazione delle cassette postali di Exchange cross-tenant richiede l'autorizzazione e l'ambito delle migrazioni tra tenant. Utilizzando le soluzioni di archiviazione di Azure Enterprise Application e Key Vault, gli amministratori dei tenant sono ora autorizzati a gestire sia l'autorizzazione che l'ambito delle migrazioni delle cassette postali di Exchange Online da un tenant all'altro. Gli spostamenti delle cassette postali tra tenant supportano un modello di invito e consenso per stabilire un'applicazione Azure Active Directory (Azure AD) utilizzata per l'autenticazione tra una coppia di tenant. Sono inoltre necessari componenti aggiuntivi, ad esempio una relazione organizzativa e un endpoint di migrazione.

In questa sezione non sono inclusi i passaggi specifici necessari per preparare gli oggetti utente di MailUser nella directory di destinazione, né include il comando di esempio per l'invio di un batch di migrazione. Per queste informazioni, vedere [preparare gli oggetti utente di destinazione per la migrazione](#prepare-target-user-objects-for-migration) .

## <a name="prerequisites"></a>Prerequisiti

La funzionalità di spostamento delle cassette postali Cross-tenant richiede [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) per creare un'applicazione Azure specifica per la coppia di tenant per archiviare e accedere in modo sicuro al certificato/segreto utilizzato per autenticare e autorizzare la migrazione delle cassette postali da un tenant all'altro, eliminando i requisiti per la condivisione di certificati/segreti tra i tenant. 

Prima di iniziare, verificare di disporre delle autorizzazioni necessarie per eseguire gli script di distribuzione per configurare l'archiviazione delle chiavi di Azure, spostare l'applicazione cassetta postale, l'endpoint di migrazione EXO e la relazione dell'organizzazione EXO. In genere, l'amministratore globale dispone dell'autorizzazione necessaria per eseguire tutti i passaggi di configurazione.

Inoltre, i gruppi di sicurezza abilitati alla posta elettronica nel tenant di origine sono necessari prima di eseguire il programma di installazione. Tali gruppi vengono utilizzati per l'ambito dell'elenco delle cassette postali che possono passare dal tenant di origine (o talvolta denominato risorsa) al tenant di destinazione. In questo modo l'amministratore del tenant di origine può limitare o applicare l'ambito del set specifico di cassette postali da spostare, impedendo la migrazione degli utenti indesiderati. I gruppi nidificati non sono supportati.

Sarà inoltre necessario comunicare con la società partner attendibile (con cui si spostano le cassette postali) per ottenere l'ID tenant Microsoft 365. Questo ID tenant viene utilizzato nel campo relazione organizzativa `DomainName` .

Per ottenere l'ID tenant di un abbonamento, accedere all'interfaccia di amministrazione di Microsoft 365 e passare a [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Fare clic sull'icona copia per la proprietà Tenant ID per copiarla negli Appunti.

Di seguito viene illustrato il funzionamento del processo.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparazione del tenant per la migrazione delle cassette postali.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a>Preparare i tenant

A livello elevato, durante l'esecuzione degli script di installazione, vengono eseguite le operazioni di configurazione seguenti.

Preparare il tenant di destinazione:

1. Se non è disponibile un gruppo di risorse di Azure esistente, ne viene creato uno nuovo (SCRIPT).
2. Se non è disponibile un Vault Key esistente, ne viene creato uno nuovo (SCRIPT).
3. Viene creato un nuovo criterio di accesso per l'applicazione di migrazione delle cassette postali di Office 365 Exchange Online (SCRIPT).
4. Viene creato un nuovo certificato (o uno esistente, se specificato) per conservare il segreto nell'applicazione di migrazione (SCRIPT).
5. Viene creata una nuova applicazione Azure AD (SCRIPT).
6. Il certificato/segreto viene caricato nell'applicazione di migrazione (SCRIPT).
7. Le autorizzazioni per la migrazione delle cassette postali vengono assegnate all'applicazione (SCRIPT).
8. Lo script di distribuzione viene interrotto fino a quando l'amministratore di destinazione non acconsente alla propria applicazione (SCRIPT).
9. L'amministratore del tenant di destinazione acconsente alle autorizzazioni concesse all'applicazione (manuale).
10. Viene creata una relazione organizzativa con il tenant di destinazione (SCRIPT).
11. Viene creato un endpoint di migrazione per estrarre le cassette postali nel tenant di destinazione (SCRIPT).

Preparare il tenant di origine:

1. L'amministratore del tenant di origine accetta il consenso all'invito all'applicazione di migrazione delle cassette postali dal tenant di destinazione (manuale).
2. L'amministratore del tenant di origine crea un gruppo di sicurezza abilitato alla posta elettronica nel proprio tenant per contenere l'elenco delle cassette postali che possono essere spostate dall'applicazione di migrazione (manuale).
3. Viene creata una relazione organizzativa con il tenant di destinazione specificando che l'applicazione di migrazione delle cassette postali deve essere utilizzata per la verifica OAuth per accettare la richiesta di spostamento (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Istruzioni dettagliate per l'amministratore del tenant di destinazione

1. Scaricare lo script SetupCrossTenantRelationshipForTargetTenant.ps1 per la configurazione del tenant di destinazione dall' [Archivio GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Salvare lo script (SetupCrossTenantRelationshipForTargetTenant.ps1) nel computer in cui verrà eseguito lo script.
3. Creare una connessione remota di PowerShell al tenant di destinazione di Exchange Online. Anche in questo caso, verificare di disporre delle autorizzazioni necessarie per eseguire gli script di distribuzione per configurare il certificato e l'archiviazione delle chiavi di Azure, l'applicazione di spostamento della cassetta postale, l'endpoint di migrazione EXO e la relazione dell'organizzazione EXO.
4. Modificare la directory della cartella file nel percorso dello script o verificare che lo script sia attualmente salvato nel percorso corrente nella sessione di PowerShell remota.
5. Eseguire lo script con i parametri e i valori seguenti.

    | Parametro | Valore | Obbligatorio o facoltativo
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | Dominio tenant di origine, ad esempio Fabrikam \. onmicrosoft.com. | Obbligatorio |
    | -ResourceTenantAdminEmail                   | Indirizzo di posta elettronica dell'amministratore del tenant di origine. Si tratta dell'amministratore del tenant di origine che consentirà l'utilizzo dell'applicazione di migrazione delle cassette postali inviata dall'amministratore di destinazione. Questo è l'amministratore che riceverà l'invito di posta elettronica per l'applicazione. | Obbligatorio |
    | -TargetTenantDomain                         | Dominio del tenant di destinazione, ad esempio contoso \. onmicrosoft.com. | Obbligatorio |
    | -ResourceTenantId                           | ID dell'organizzazione tenant di origine (GUID). | Obbligatorio |
    | -SubscriptionId                             | La sottoscrizione di Azure da utilizzare per la creazione di risorse. | Obbligatorio |
    | -ResourceGroup                              | Nome del gruppo di risorse di Azure che contiene o conterrà il Vault chiave. | Obbligatorio |
    | -Portavaultname                               | Istanza del Vault Key di Azure in cui verrà memorizzato il certificato/segreto dell'applicazione di migrazione delle cassette postali. | Obbligatorio |
    | -Certificate                            | Nome del certificato durante la generazione o la ricerca di un certificato in Key Vault. | Obbligatorio |
    | -CertificateSubject consente                         | Nome del soggetto del certificato Vault Key di Azure, ad esempio CN = contoso_fabrikam. | Obbligatorio |
    | -ExistingApplicationId                      | Applicazione di migrazione della posta elettronica da utilizzare se ne è stata già creata una. | Facoltativo |
    | -AzureAppPermissions                        | Le autorizzazioni necessarie per l'applicazione di migrazione delle cassette postali, ad esempio Exchange o MSGraph (Exchange per lo spostamento delle cassette postali, MSGraph per l'utilizzo di questa applicazione per l'invio di un invito di collegamento di consenso al tenant delle risorse). | Obbligatorio |
    | -UseAppAndCertGeneratedForSendingInvitation | Parametro per l'utilizzo dell'applicazione creata per la migrazione da utilizzare per l'invio dell'invito al collegamento di consenso all'amministratore del tenant di origine. Se non è presente, viene richiesto di richiedere le credenziali dell'amministratore di destinazione per connettersi a Azure invito Manager e inviare l'invito come amministratore di destinazione. | Facoltativo |
    | -KeyVaultAuditStorageAccountName            | L'account di archiviazione in cui verranno archiviati i registri di controllo del Vault chiave. | Facoltativo |
    | -KeyVaultAuditStorageResourceGroup          | Il gruppo di risorse che contiene l'account di archiviazione per l'archiviazione dei registri di controllo del Vault Key. | Facoltativo |
    ||||

6. Lo script interromperà e chiederà di accettare o acconsentire all'applicazione di migrazione delle cassette postali di Exchange che è stata creata durante questo processo. Ecco un esempio.

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ``` 

7. Un URL verrà visualizzato nella sessione di PowerShell remota. Copiare il collegamento fornito per il consenso del tenant e incollarlo in un Web browser.

8. Accedere con le credenziali di amministratore globale. Quando viene visualizzata la schermata seguente, selezionare **accetta**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Finestra di dialogo accetta autorizzazioni.":::
    
9. Passare alla sessione remota di PowerShell e premere INVIO per continuare.

10. Lo script configurerà gli oggetti di installazione rimanenti. Ecco un esempio.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

La configurazione dell'amministratore di destinazione è ora completata.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Istruzioni dettagliate per l'amministratore del tenant di origine

1.  Accedere alla cassetta postale come-ResourceTenantAdminEmail specificata dall'amministratore di destinazione durante la configurazione. Trovare l'invito di posta elettronica dal tenant di destinazione, quindi selezionare il pulsante **inizia** .

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Finestra di dialogo invitato.":::

2. Selezionare **accetta** per accettare l'invito.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Finestra di dialogo per accettare le autorizzazioni":::

   > [!NOTE]
   > Se non si riceve questo messaggio di posta elettronica o non è possibile trovarlo, l'amministratore del tenant di destinazione ha fornito un URL diretto che può essere assegnato all'utente per accettare l'invito. L'URL dovrebbe essere nella sezione nella trascrizione della sessione remota di PowerShell dell'amministratore del tenant di destinazione.

3. Nell'interfaccia di amministrazione di Microsoft 365 o in una sessione di PowerShell remota, creare uno o più gruppi di sicurezza abilitati alla posta elettronica per controllare l'elenco delle cassette postali consentite dal tenant di destinazione per il pull (spostamento) dal tenant di origine al tenant di destinazione. Non è necessario popolare questo gruppo in anticipo, ma è necessario fornire almeno un gruppo per eseguire la procedura di installazione (script). I gruppi di annidamento non sono supportati. 

4. Scaricare lo script SetupCrossTenantRelationshipForTargetResource.ps1 per il programma di installazione tenant di origine dall' [Archivio GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 

5. Creare una connessione remota di PowerShell al tenant di origine con le autorizzazioni di amministratore di Exchange. Le autorizzazioni di amministratore globale non sono necessarie per configurare il tenant di origine, solo il tenant di destinazione a causa del processo di creazione di applicazioni di Azure.

6. Passare alla directory del percorso dello script o verificare che lo script sia attualmente salvato nel percorso corrente nella sessione di PowerShell remota.

7. Eseguire lo script con i parametri e i valori necessari seguenti.

    | Parametro | Valore |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Gruppo di sicurezza abilitato alla posta elettronica creato dal tenant di origine per le identità/cassette postali che rientrano nell'ambito della migrazione. |
    | -ResourceTenantDomain | Nome di dominio del tenant di origine, ad esempio Fabrikam \. onmicrosoft.com. |
    | -TargetTenantDomain | Nome di dominio del tenant di destinazione, ad esempio contoso \. onmicrosoft.com. |
    | -ApplicationId | ID applicazione di Azure (GUID) dell'applicazione utilizzata per la migrazione. ID applicazione disponibile tramite il portale di Azure (Azure AD, applicazioni Enterprise, nome app, ID applicazione) o incluso nel messaggio di posta elettronica di invito.  |
    | -TargetTenantId | ID tenant del tenant di destinazione. Ad esempio, l'ID tenant Azure AD del \. tenant contoso onmicrosoft.com. |
    |||
    
    Ecco un esempio.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

La configurazione dell'amministratore di origine è stata completata.

### <a name="verify-setup"></a>Verificare l'installazione

Verificare che le relazioni dell'organizzazione nei tenant di origine e di destinazione e nell'endpoint di migrazione nella destinazione siano state create correttamente.

#### <a name="target-tenant"></a>Tenant di destinazione

**Relazione organizzativa**

Verificare che l'oggetto relazione organizzativa sia stato creato e configurato con questo comando.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Ecco un esempio:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Endpoint di migrazione**

Verificare che l'oggetto endpoint di migrazione sia stato creato e configurato con questo comando.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Ecco un esempio.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Tenant di origine

**Relazione organizzativa**

Verificare che l'oggetto relazione organizzativa sia stato creato e configurato con questo comando.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
Ecco un esempio.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Spostare le cassette postali nell'origine originale

Se è richiesta una cassetta postale di origine, è necessario eseguire lo stesso set di passaggi e script sia nella nuova origine sia nei nuovi tenant di destinazione. L'oggetto relazione dell'organizzazione esistente verrà aggiornato o accodato, non ricreato.

## <a name="prepare-target-user-objects-for-migration"></a>Preparare gli oggetti utente di destinazione per la migrazione

Gli utenti che eseguono la migrazione devono essere presenti nel tenant di destinazione e in Exchange Online System (come MailUsers) contrassegnati con attributi specifici per abilitare gli spostamenti tra tenant. Il sistema avrà esito negativo per gli utenti che non sono stati configurati correttamente nel tenant di destinazione. Nella sezione seguente vengono illustrati i requisiti dell'oggetto MailUser per il tenant di destinazione.

### <a name="prerequisites"></a>Prerequisiti
  
È necessario verificare che nell'organizzazione di destinazione siano impostati gli oggetti e gli attributi riportati di seguito.  

1. Per qualsiasi cassetta postale che si sposta da un'organizzazione di origine, è necessario eseguire il provisioning di un oggetto MailUser nell'organizzazione di destinazione: 
   - L'utente di posta elettronica di destinazione deve disporre di questi attributi dalla cassetta postale di origine o assegnato al nuovo oggetto User:
      - ExchangeGUID (flusso diretto dall'origine alla destinazione) – il GUID della cassetta postale deve corrispondere. Il processo di spostamento non proseguirà se non è presente nell'oggetto di destinazione. 
      - Proprietà ArchiveGuid (flusso diretto dall'origine alla destinazione) – il GUID dell'archivio deve corrispondere. Il processo di spostamento non proseguirà se non è presente nell'oggetto di destinazione. (È necessario solo se la cassetta postale di origine è abilitata per l'archiviazione). 
      - LegacyExchangeDN (Flow As proxyAddress, "X500: <LegacyExchangeDN> ") – l'attributo legacyExchangeDN deve essere presente nell'oggetto MailUser di destinazione come X500: ProxyAddress. I processi di spostamento non verranno continuati se questo non è presente nell'oggetto di destinazione. 
      - UserPrincipalName – UPN verrà allineato alla nuova identità o società di destinazione dell'utente (ad esempio, user@northwindtraders.onmicrosoft.com). 
      - SMTPAddress primario – l'indirizzo SMTP primario si allinea alla nuova società dell'utente (ad esempio, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser farà riferimento alla cassetta postale corrente dell'utente ospitata nel tenant di origine (ad esempio user@contoso.onmicrosoft.com). Quando si assegna questo valore, verificare che sia stata assegnata o che sia PrimarySMTPAddress o che questo valore imposti la PrimarySMTPAddress che provocherà errori di spostamento. 
      - Non è possibile aggiungere indirizzi proxy SMTP legacy dalla cassetta postale di origine alla destinazione MailUser. Ad esempio, non è possibile mantenere contoso.com sul MEU negli oggetti tenant fabrikam.onmicrosoft.com. I domini sono associati a un solo tenant Azure AD o Exchange Online.
 
    Oggetto MailUser di **destinazione** di esempio:
 
    | Attributo             | Valore                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Alias                 | LaraN                                                                                                                    |
    | RecipientType         | MailUser                                                                                                                 |
    | RecipientTypeDetails  | MailUser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = First Organization/ou = gruppo amministrativo di Exchange                                                                   |
    |                       | (FYDIBOHF23SPDLT)/cn = Recipients/cn = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | X500:/o = First Organization/ou = Exchange Administrative Group (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | SMTP: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Lara \. Newton@northwind.com                                                                                           |
    |||

   Oggetto cassetta postale di **origine** di esempio:

   | Attributo             | Valore                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Alias                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = First Organization/ou = gruppo amministrativo di Exchange                   |
   |                       | (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | SMTP: LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP: Lara \. Newton@contoso.com          |
   |||

   - Gli attributi aggiuntivi possono essere già inclusi in Exchange Hybrid write back. In caso contrario, dovrebbero essere inclusi. 
   - msExchBlockedSendersHash – scrive di nuovo i dati dei mittenti online sicuri e bloccati dai client in Active Directory locale.
   - msExchSafeRecipientsHash – scrive di nuovo i dati dei mittenti online sicuri e bloccati dai client in Active Directory locale.
   - msExchSafeSendersHash – scrive di nuovo i dati dei mittenti online sicuri e bloccati dai client in Active Directory locale.

2. Se la cassetta postale di origine è su LitigationHold e la dimensione degli elementi ripristinabili delle cassette postali di origine è maggiore di quella predefinita (30 GB), gli spostamenti non verranno continuati poiché la quota di destinazione è inferiore alla dimensione della cassetta postale di origine. È possibile aggiornare l'oggetto MailUser di destinazione per la transizione dei flag della cassetta postale ELC dall'ambiente di origine alla destinazione, che attiva il sistema di destinazione per espandere la quota di MailUser a 100 GB, consentendo in tal modo lo spostamento verso la destinazione. Queste istruzioni funzioneranno solo per l'identità ibrida che esegue Azure AD Connect, in quanto i comandi per contrassegnare i flag ELC non vengono esposti agli amministratori dei tenant.

    >[!Note]
    > ESEMPIO – COME È, NESSUNA GARANZIA<br/>Questo script presuppone una connessione a entrambe le cassette postali di origine (per ottenere i valori di origine) e a Active Directory di destinazione (per contrassegnare l'oggetto ADUser). Se l'origine ha un contenzioso o il ripristino di un singolo elemento abilitato, impostarlo sull'account di destinazione.  In questo modo, le dimensioni del dumpster dell'account di destinazione verranno incrementate a 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. I tenant di destinazione non ibridi possono modificare la quota nella cartella elementi ripristinabili per MailUsers prima della migrazione eseguendo il comando seguente per abilitare il blocco per controversia legale sull'oggetto MailUser e aumentare la quota a 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Si noti che questo non funzionerà per i tenant in modalità ibrida.

4. Gli utenti nell'organizzazione di destinazione devono essere concessi in licenza con le sottoscrizioni di Exchange Online appropriate applicabili per l'organizzazione. È possibile applicare una licenza in anticipo rispetto allo spostamento di una cassetta postale, ma solo dopo che l'utente di posta elettronica di destinazione è stato configurato correttamente con ExchangeGUID e gli indirizzi proxy. L'applicazione di una licenza prima dell'applicazione di ExchangeGUID comporterà la provisioning di una nuova cassetta postale nell'organizzazione di destinazione. 

    > [!Note]
    > Quando si applica una licenza su un oggetto Mailbox o MailUser, tutti i tipi di proxyAddresses di tipo SMTP vengono rimosse per garantire che solo i domini verificati siano inclusi nella matrice di indirizzi di posta elettronica di Exchange. 

5. È necessario assicurarsi che l'oggetto MailUser di destinazione non disponga di ExchangeGuid precedenti che non corrisponda al ExchangeGuid di origine. Questo problema può verificarsi se l'utente di destinazione è stato precedentemente concesso in licenza per Exchange Online e ha eseguito il provisioning di una cassetta postale. Se l'utente di posta elettronica di destinazione è stato precedentemente concesso in licenza o aveva un ExchangeGuid che non corrisponde al ExchangeGuid di origine, è necessario eseguire una pulizia del cloud MEU. Per questi cloud MEUs, è possibile eseguire il `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` comando. 

    > [!Caution]
    > Questo processo è irreversibile. Se l'oggetto dispone di una cassetta postale di softDeleted, non può essere ripristinato dopo questo punto. Una volta deselezionata, tuttavia, è possibile sincronizzare la ExchangeGuid corretta per l'oggetto di destinazione e MRS collegherà la cassetta postale di origine alla cassetta postale di destinazione appena creata. (Blog di riferimento EHLO sul nuovo parametro). 
 
    Individuare gli oggetti precedentemente presenti nelle cassette postali utilizzando questo comando.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    Ecco un esempio. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    Cancellare la cassetta postale eliminata temporaneamente usando questo comando.

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    Ecco un esempio.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>Eseguire le migrazioni delle cassette postali

Le migrazioni delle cassette postali di Exchange tra tenant vengono inviate come batch di migrazione avviate dal tenant di destinazione. Questo è analogo al modo in cui i batch di migrazione a bordo funzionano quando si esegue la migrazione da Exchange locale a Microsoft 365. 

### <a name="create-migration-batches"></a>Creare batch di migrazione

Di seguito è riportato un esempio di cmdlet batch di migrazione per gli spostamenti di avvio.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> L'indirizzo di posta elettronica nel file CSV deve essere quello specificato nel tenant di destinazione, non il tenant di origine.

L'invio in batch di migrazione è supportato anche dalla nuova interfaccia di amministrazione di Exchange quando si seleziona l'opzione Cross-tenant.
 
#### <a name="update-on-premises-mailusers"></a>Aggiornare MailUsers locale

Dopo che la cassetta postale si sposta dall'origine alla destinazione, è necessario assicurarsi che gli utenti di posta elettronica locali, sia di origine che di destinazione, vengano aggiornati con il nuovo targetAddress. Negli esempi, la targetDeliveryDomain utilizzata nello spostamento è **contoso \. onmicrosoft.com**. Aggiornare gli utenti di posta elettronica con questo targetAddress.
 
## <a name="frequently-asked-questions"></a>Domande frequenti
 
**È necessario aggiornare RemoteMailboxes in source locale dopo lo spostamento?**
 
Sì, è necessario aggiornare il metodo targetAddress (RemoteRoutingAddress/ExternalEmailAddress) degli utenti locali di origine quando la cassetta postale di origine del tenant si sposta sul tenant di destinazione.  Mentre il routing della posta può seguire i riferimenti su più utenti di posta con diverse targetAddresses, le ricerche sulla disponibilità per gli utenti di posta devono essere indirizzate alla posizione dell'utente della cassetta postale. Le ricerche sulla disponibilità non inseguono più reindirizzamenti. 
 
**Il contenuto della cartella chat teams migra Cross-tenant?** 

No, il contenuto della cartella chat del team non esegue la migrazione tra tenant. 
 
**In che modo è possibile visualizzare solo gli spostamenti di tipo cross-tenant, non gli spostamenti di onboarding e Offboarding?**

Utilizzare il `-flags` parametro. Ecco un esempio.

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**È possibile fornire script di esempio per la copia degli attributi utilizzati per il testing?**

> [!Note]
> ESEMPIO – COME È, NESSUNA GARANZIA<br/>Questo script presuppone una connessione a entrambe le cassette postali di origine (per ottenere i valori di origine) e ai servizi di dominio Active Directory locali di destinazione (per contrassegnare l'oggetto ADUser). Se l'origine ha un contenzioso o il ripristino di un singolo elemento abilitato, impostarlo sull'account di destinazione.  In questo modo, le dimensioni del dumpster dell'account di destinazione verranno incrementate a 100 GB.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**Come si accede a Outlook il giorno 1 dopo lo spostamento della cassetta postale di utilizzo?**

Poiché un solo tenant può disporre di un dominio, l'ex SMTPAddress primario non verrà associato all'utente nel tenant di destinazione al termine dello spostamento della cassetta postale. solo i domini associati al nuovo tenant. Outlook utilizza il nuovo UPN degli utenti per eseguire l'autenticazione nel servizio e il profilo di Outlook prevede di trovare l'SMTPAddress principale legacy in modo che corrisponda alla cassetta postale nel sistema di destinazione. Poiché l'indirizzo legacy non è presente nel sistema di destinazione, il profilo di Outlook non si connetterà per trovare la cassetta postale appena spostata. 

Per questa distribuzione iniziale, gli utenti dovranno ricreare il proprio profilo con il nuovo UPN, l'indirizzo SMTP primario e la risincronizzazione del contenuto OST. 

> [!Note]
> Pianificare di conseguenza il batch degli utenti per il completamento. È necessario tenere conto dell'utilizzo della rete e della capacità quando vengono creati i profili client di Outlook e i successivi file OST e OAB vengono scaricati nei client. 
 
**Quali ruoli di Exchange RBAC devono essere membri di per impostare o completare uno spostamento Cross-tenant?**
 
Esiste una matrice di ruoli in base all'ipotesi di dazi delegati durante l'esecuzione di uno spostamento di cassette postali. Attualmente, sono necessari due ruoli:  

- Il primo ruolo è per un'attività di installazione singola che stabilisce l'autorizzazione di spostamento del contenuto all'interno o all'esterno del limite tenant/organizzativa. Poiché il trasferimento dei dati dal controllo organizzativo è un problema critico per tutte le società, è stato scelto il ruolo di amministratore dell'organizzazione più elevato assegnato (OrgAdmin). Questo ruolo deve modificare o impostare un nuovo OrganizationRelationship che definisce l'-MailboxMoveCapability con l'organizzazione remota. Solo OrgAdmin può modificare l'impostazione MailboxMoveCapability, mentre gli altri attributi di OrganizationRelationhip possono essere gestiti dall'amministratore di condivisione federata. 
 
- È possibile delegare il ruolo di esecuzione dei comandi di spostamento effettivi a una funzione di livello inferiore. Al ruolo delle cassette postali di spostamento viene assegnata la possibilità di spostare le cassette postali all'interno o all'esterno dell'organizzazione utilizzando il `-RemoteTenant` parametro.  

**Come si intende individuare l'indirizzo SMTP selezionato per targetAddress (TargetDeliveryDomain) nella cassetta postale convertita (per la conversione di MailUser)?**
 
Lo spostamento delle cassette postali di Exchange viene utilizzato dall'onorevole Craft il targetAddress nella cassetta postale di origine originale durante la conversione in un oggetto MailUser mediante la corrispondenza di un indirizzo di posta elettronica (proxyAddress) sull'obiettivo. Il processo prende il valore-TargetDeliveryDomain passato nel comando Move, quindi verifica la corrispondenza di un proxy corrispondente per il dominio sul fianco di destinazione. Quando viene trovata una corrispondenza, viene utilizzato il proxyAddress corrispondente per impostare il ExternalEmailAddress (targetAddress) sull'oggetto Mailbox convertito (ora MailUser).
 
**Come si esegue la transizione delle autorizzazioni delle cassette postali?**

Le autorizzazioni per le cassette postali includono inviare per conto di e accesso alla cassetta postale: 

- Invia per conto di (AD: publicDelegates) archivia il DN dei destinatari con accesso alla cassetta postale di un utente come delegati. Questo valore viene archiviato in Active Directory e attualmente non viene spostato come parte della transizione delle cassette postali. Se la cassetta postale di origine è impostata su publicDelegates, sarà necessario ristampare la publicDelegates sulla cassetta postale di destinazione dopo aver completato la conversione di MEU alla cassetta postale nell'ambiente di destinazione utilizzando il `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` comando. 
 
- Le autorizzazioni per le cassette postali archiviate nella cassetta postale verranno spostate con la cassetta postale quando sia l'entità che il delegato vengono spostati nel sistema di destinazione. Ad esempio, all'utente TestUser_7 viene concessa FullAccess alla TestUser_8 della cassetta postale nel tenant SourceCompany.onmicrosoft.com. Dopo che lo spostamento della cassetta postale è stato completato in TargetCompany.onmicrosoft.com, le stesse autorizzazioni sono configurate nella directory di destinazione. Di seguito sono riportati alcuni esempi che utilizzano *Get-MailboxPermission* per TestUser_7 in entrambi i tenant di origine e di destinazione. I cmdlet di Exchange sono preceduti con l'origine e la destinazione di conseguenza. 
 
Di seguito è riportato un esempio dell'output dell'autorizzazione cassetta postale prima di uno spostamento. 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Di seguito è riportato un esempio dell'output dell'autorizzazione della cassetta postale dopo lo spostamento. 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Le autorizzazioni per le cassette postali e i calendari Cross-tenant non sono supportate. È necessario organizzare le entità e i delegati in batch di spostamento consolidati in modo che queste cassette postali connesse vengano passate contemporaneamente dal tenant di origine. 
 
## <a name="known-issues"></a>Problemi noti 

-  **Problema: non è possibile eseguire la migrazione degli archivi con espansione automatica.** La funzionalità di migrazione cross-tenant supporta le migrazioni della cassetta postale principale e della cassetta postale di archiviazione per un utente specifico. Se l'utente nell'origine ha un archivio automatico espanso, ovvero più di una cassetta postale di archiviazione, la funzionalità non è in grado di eseguire la migrazione degli archivi aggiuntivi.

- **Problema: cloud MailUsers with non-owned SMTP proxyAddress Block MRS Moves background.** Quando si creano oggetti di MailUser tenant di destinazione, è necessario assicurarsi che tutti gli indirizzi proxy SMTP appartengano all'organizzazione tenant di destinazione. Se un proxyAddress SMTP esiste sull'utente di posta elettronica di destinazione che non appartiene al tenant locale, la conversione di MailUser in cassetta postale è impedita. Ciò è dovuto alla nostra certezza che gli oggetti cassetta postale possono solo inviare messaggi di posta elettronica da domini per i quali il tenant è autorevole (domini rivendicati dal tenant): 
- 
   - Quando si sincronizzano gli utenti da un ambiente locale con Azure AD Connect, è possibile eseguire il provisioning di oggetti MailUser locali con ExternalEmailAddress che punta al tenant di origine in cui si trova la cassetta postale (laran@contoso \. onmicrosoft.com) e si timbra la PrimarySmtpAddress come un dominio che risiede nel tenant di destinazione (Lara. Newton@northwind \. com). Questi valori vengono sincronizzati con il tenant e viene eseguito il provisioning di un utente di posta elettronica appropriato e pronto per la migrazione. Di seguito è riportato un oggetto di esempio.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > L'indirizzo *contoso. onmicrosoft \. com* *non* è presente nella matrice EmailAddresses/proxyAddresses.

- **Problema: gli oggetti MailUser con indirizzi SMTP primari "esterni" vengono modificati/ripristinati nei domini rivendicati dall'azienda "interna"**

   Gli oggetti MailUser sono puntatori a cassette postali non locali. Nel caso delle migrazioni tra tenant, è possibile utilizzare gli oggetti MailUser per rappresentare la cassetta postale di origine (dal punto di vista dell'organizzazione di destinazione) o la cassetta postale di destinazione (dal punto di vista dell'organizzazione di origine). MailUsers avrà un ExternalEmailAddress (targetAddress) che punta all'indirizzo SMTP della cassetta postale effettiva (ProxyTest \@ fabrikam \. onmicrosoft.com) e all'indirizzo primarySMTP che rappresenta l'indirizzo SMTP visualizzato dell'utente della cassetta postale nella directory. Alcune organizzazioni scelgono di visualizzare l'indirizzo SMTP primario come indirizzo SMTP esterno, non come indirizzo posseduto/verificato dal tenant locale (ad esempio fabrikam.com anziché come contoso.com).  Tuttavia, dopo l'applicazione di un oggetto piano di Exchange all'MailUser tramite le operazioni di gestione delle licenze, l'indirizzo SMTP primario viene modificato in modo che venga visualizzato come dominio verificato dall'organizzazione locale (contoso.com). Esistono due possibili motivi:
   
   - Quando un piano del servizio di Exchange viene applicato a un MailUser, il processo di Azure AD inizia a applicare il lavaggio dei proxy per garantire che l'organizzazione locale non sia in grado di inviare messaggi di posta elettronica, falsificazione o posta elettronica da un altro tenant. Tutti gli indirizzi SMTP su un oggetto destinatario con questi piani di servizio verranno rimossi se l'indirizzo non viene verificato dall'organizzazione locale. Come nel caso dell'esempio, il \. dominio com di FABIKAM non viene verificato dal tenant di contoso \. onmicrosoft.com, quindi il lavaggio rimuove il \. dominio com di Fabrikam. Se si desidera mantenere questo dominio esterno su MailUser, prima della migrazione o dopo la migrazione, è necessario modificare i processi di migrazione per eliminare le licenze dopo che lo spostamento è stato completato o prima dello spostamento per assicurarsi che gli utenti abbiano applicato il marchio esterno previsto. Sarà necessario assicurarsi che l'oggetto cassetta postale sia adeguatamente concesso in licenza per non influire sul servizio di posta.<br/><br/>Di seguito viene mostrato uno script di esempio per rimuovere i piani di servizio in un oggetto MailUser nel tenant di Contoso \. onmicrosoft.com.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Di seguito sono riportati i risultati del set di ServicePlans assegnato.

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       Il PrimarySMTPAddress dell'utente non è più stato rimosso. Il dominio fabrikam.com non è di proprietà del tenant contoso.onmicrosoft.com e verrà salvato in modo permanente come indirizzo SMTP principale visualizzato nella directory.

       Ecco un esempio.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Quando msExchRemoteRecipientType è impostato su 8 (DeprovisionMailbox), per i MailUsers locali migrati al tenant di destinazione, la logica di lavaggio del proxy in Azure rimuoverà i domini non posseduti e reimposterà la primarySMTP a un dominio di proprietà. Deselezionando msExchRemoteRecipientType nell'MailUser locale, il proxy scrub Logic non è più applicabile. <br/><br>Di seguito è riportato il set completo di piani di servizio possibili che includono Exchange Online.

   | Nome                                              |
   |---------------------------------------------------|
   | Archiviazione avanzata di eDiscovery (500GB)               |
   | Customer Lockbox                                  |
   | Prevenzione della perdita di dati                              |
   | Servizi CAL di Exchange Enterprise (EOP, DLP)       |
   | Elementi essenziali di Exchange                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (piano 1)                          |
   | Exchange Online (piano 2)                          |
   | Archiviazione Exchange Online per Exchange Online     |
   | Archiviazione Exchange Online per Exchange Server     |
   | Componente aggiuntivo per utenti inattivi di Exchange Online              |
   | Chiosco Exchange Online                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Piano 1                            |
   | POP Exchange Online                               |
   | Exchange Online Protection                        |
   | Barriere informative                              |
   | Protezione delle informazioni per Office 365-Premium   |
   | Protezione delle informazioni per Office 365-standard  |
   | Insights by analisi analitica                           |
   | Microsoft 365 Advanced audit                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft analisi (completa)                      |
   | Office 365 Advanced eDiscovery                    |
   | Protezione avanzata dalle minacce di Office 365 (piano 1)    |
   | Protezione avanzata dalle minacce di Office 365 (piano 2)    |
   | Gestione degli accessi con privilegi di Office 365           |
   | Outlook Customer Manager                          |
   | Crittografia avanzata in Office 365                  |
   || 
 
