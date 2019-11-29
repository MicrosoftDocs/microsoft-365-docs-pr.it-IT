---
title: GDPR per SharePoint Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Informazioni su come gestire i requisiti GDPR nell'ambiente SharePoint Server locale.
ms.openlocfilehash: dba20f2f85bc9a474b39e427ed2628a2f9c9f437
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "39625401"
---
# <a name="gdpr-for-sharepoint-server"></a>GDPR per SharePoint Server

Si applica a:
- SharePoint Server 2013
- SharePoint Server 2016
- SharePoint Server 2019

Nell'ambito di protezione delle informazioni personali, si consiglia quanto segue:

-   Classificare i propri dati utilizzando Azure Information Protection

-   Eseguire SharePoint Server con una configurazione con privilegi minimi. Per ulteriori informazioni, vedere [Pianificare l'amministrazione con privilegi minimi in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) e [Sicurezza per SharePoint Server](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).

-   [Attivare la crittografia BitLocker nei server](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).

## <a name="user-generated-content"></a>Contenuti generato dall'utente

L'approccio consigliato per i contenuti generati dall'utente inclusi nei siti e nelle raccolte di SharePoint Server è il seguente:

-   Utilizzare Azure Information Protection per etichettare dati sensibili.

-   Utilizzare [Servizio di ricerca di SharePoint Server](https://docs.microsoft.com/SharePoint/search/search) ed [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) per recuperare i dati riservati.

L'approccio consigliato per le condivisioni file e per i siti e le raccolte di SharePoint include i seguenti passaggi:

1.  **[Installare e configurare lo scanner di Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**

    -   Scegliere i tipi di dati sensibili da usare.

    -   Specificare i siti di SharePoint da usare.

2.  **Completare un ciclo di individuazione.**

    -   Eseguire lo scanner in modalità di individuazione e convalidare i risultati.

    -   Se necessario, ottimizzare le condizioni e i tipi di informazioni riservate.

    -   Valutare l'impatto previsto dell'applicazione automatica delle etichette.

3.  **Eseguire lo scanner di Azure Information Protection per applicare etichette a documenti idonei**.

4.  **Per la protezione:**

    a.  Configurare le regole di prevenzione della perdita dei dati di Exchange per proteggere i documenti con l'etichetta desiderata.

    b.  Assicurarsi di utilizzare le autorizzazioni per definire chi può accedere ai file.

    c.  Per SharePoint, utilizzare la Protezione IRM per le raccolte.

5.  **Per il monitoraggio, integrare i log di Windows Server con uno strumento informazioni di sicurezza e gestione degli eventi.**

    a.  Per ottenere i dati personali per le richieste degli interessati, utilizzare Centro ricerche o eDiscovery.

Quando si applicano etichette a dati sensibili, assicurarsi di assegnare un'etichetta non configurata con la protezione. La protezione include la crittografia che impedisce ai servizi di rilevare i dati sensibili nei file.

Per ulteriori informazioni sull'uso dello scanner di Azure Information Protection per individuare ed etichettare dati personali, vedere [Toolkit per l'individuazione di dati GDPR di Microsoft](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners).

Per informazioni sulla configurazione dello scanner per le condizioni e l'utilizzo della prevenzione della perdita dei dati (DLP) di Office 365 con tipi di informazioni riservate, vedere [Come configurare le condizioni per la classificazione automatica e consigliata per Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Si noti che i nuovi tipi di informazioni riservate di Office 365 non saranno immediatamente disponibili per l'uso con lo scanner e che i tipi di informazioni riservate personalizzate non possono essere usati con lo scanner.

## <a name="removing-personal-information-from-office-files"></a>Rimozione delle informazioni personali dal file di Office

La rimozione delle informazioni personali (come ad esempio metadati o commenti in un documento di Word) dai file di Office archiviati nella raccolta documenti di SharePoint deve essere eseguita manualmente. Per eseguirla attenersi alla seguente procedura:

1.  Scaricare una copia del documento da SharePoint Server al disco locale.

2.  Eliminare il documento dalla raccolta documenti di SharePoint.

3.  Attenersi alla procedura descritta in [Rimuovere dati nascosti e informazioni personali tramite il controllo dei documenti](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).

4.  Caricare nuovamente il documento nella raccolta documenti di SharePoint.

## <a name="telemetry-and-log-files"></a>Telemetria e file di log

### <a name="uls-logs"></a>Registri ULS

Il servizio di registrazione unificato (ULS) e la Registrazione di utilizzo in SharePoint Server consentono di tracciare una varietà di funzioni di sistema e possono contenere le informazioni utente. I Registri ULS e i registri di utilizzo consistono in file di testo che è possibile cercare con molti strumenti di ricerca. Il [cmdlet Merge-SPLogFile PowerShell](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) consente di restituire i record dai Registri ULS su più server in una farm.

È consigliabile impostare i criteri di conservazione dei registri per il valore minimo richiesto per le attività aziendali. Per informazioni sulla configurazione della registrazione in SharePoint Server, vedere [Configurare la registrazione diagnostica in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

Si noti che alcuni eventi di sistema vengono registrati anche nel Registro eventi di Windows.

### <a name="usage-database"></a>Database del servizio di utilizzo

Il database del servizio di utilizzo di SharePoint Server (nome predefinito WSS_Logging) contiene un sottoinsieme delle informazioni presenti nei Registri ULS. Il periodo massimo di conservazione dei dati in questo database è di 30 giorni. È consigliabile configurarlo per la durata minima consentita dalle esigenze dell'azienda. Per ulteriori informazioni, vedere [Configurare la registrazione diagnostica in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

## <a name="personal-information-and-search"></a>Ricerca e informazioni personali

La cronologia query di ricerca e i record utilizzo contengono riferimenti ai nomi utente.

### <a name="query-history-and-favorite-queries"></a>Cronologia query e query preferite

In SharePoint Server, la cronologia delle query e le query "preferite" scadono automaticamente dopo 365 giorni. Se un utente lascia l'organizzazione, è possibile rimuovere i riferimenti a un nome utente dalla cronologia delle query tramite la procedura seguente.

Le seguenti query SQL si applicano a SharePoint Server e consentono di:

-   Esportare la cronologia query o le query preferite di un utente

-   Rimuovere i riferimenti ai nomi utente nella cronologia query

#### <a name="export-a-users-queries-since-a-specific-date"></a>Esportare le query di un utente fino a una data specifica 

Utilizzare la procedura seguente per esportare le query dalle tabelle dei log di query di Link Store eseguite da @NomeUtente a partire da@DataInizio.

```sql
[In dbo].[LinkStore_<ID>]:
CREATE PROCEDURE proc_MSS_GetQueryTermsForUser 
( 
    @UserName nvarchar(256), 
    @StartTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT searchTime, queryString 
    FROM 
        dbo.MSSQLogPageImpressionQuery 
    WITH 
        (NOLOCK) 
    WHERE 
        userName = @UserName AND 
        searchTime > @StartTime 
END 
GO 
```

#### <a name="export-a-users-queries-from-the-past-100-days"></a>Esportare le query di un utente relative a un periodo di 100 giorni

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a>Esportare le query preferite di un utente

Utilizzare la procedura seguente per esportare le query preferite di un utente dalle tabelle dei risultati personali del DB di amministrazione ricerca, eseguite da @NomeUtente, a partire da <DateTime>.

```sql
In [dbo].[Search_<ID>]:
CREATE PROCEDURE proc_MSS_GetPersonalFavoriteQueries 
( 
    @UserName nvarchar(256), 
    @SearchTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT max(queries.SearchTime) as SearchTime, 
           max(queries.querystring) as queryString, 
           max(url.url) as URL 
    FROM MSSQLogOwner owners WITH(NOLOCK) 
    JOIN MSSQLogPersonalResults results WITH(NOLOCK) on owners.OwnerId = results.OwnerId 
    JOIN MSSQLogUrl url WITH(NOLOCK) on results.ClickedUrlId = url.urlId 
    JOIN MSSQLogPersonalQueries queries WITH(NOLOCK) on results.OwnerId = queries.OwnerId 
    WHERE queries.SearchTime > @SearchTime 
        AND queries.UserName = @UserName 
        GROUP BY queries.QueryString,url.url 
END 
GO 
```

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a>Esportare le query preferite di un utente relative a un periodo di 100 giorni 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a>Rimuovere i riferimenti ai nomi utente creati da più di X giorni

Utilizzare la procedura seguente per rimuovere i riferimenti a *tutti* i nomi utente creati più di @NumeroGiorni prima dalle tabelle dei log di query di Link Store. Questa procedura rimuove soltanto i riferimenti passati fino al raggiungimento di @DataUltimaPulizia.

```sql
In [dbo].[LinksStore_<ID>]:  
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a>Rimuovere i riferimenti a uno specifico nome utente creato da più di X giorni

Utilizzare la procedura seguente per rimuovere i riferimenti a uno *specifico* nome utente che risalgono a più di @NumeroGiorni dalle tabelle dei log di query di Link Store. Questa procedura rimuove soltanto i riferimenti passati fino al raggiungimento di @DataUltimaPulizia.

```sql
In [dbo].[LinksStore_<ID>]:
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @UserName nvarchar(256),
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a>Rimuovere i riferimenti a tutti i nomi utente nella cronologia query a partire da una data e per un periodo massimo di 30 giorni.

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a>Eliminare i record di utilizzo

SharePoint Server elimina automaticamente i record di utilizzo dopo 3 anni. È possibile eliminare manualmente questi record tramite la procedura seguente:

Per eliminare tutti i record di utilizzo associati ai documenti eliminati: 

1.  Assicurarsi di avere installato l'aggiornamento più recente di SharePoint. 

2.  Avviare una SharePoint Management Shell.

3.  Interrompere e cancellare l'analisi utilizzo: 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  Attendere il riavvio dell'analisi (potrebbe richiedere fino a 24 ore). 

5.  La successiva esecuzione dell'analisi eliminerà tutti i record dal Database di report di analisi. Il backup completo di un database contenente un numero elevato di voci potrebbe richiedere molto tempo.

6.  Attendere 10 giorni. L'analisi verrà eseguita ogni giorno e i record associati ai documenti eliminati verranno rimossi dopo la decima esecuzione. Se dovesse essere necessario eliminare molti record, quest'ultima esecuzione potrebbe richiedere più tempo del normale. 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a>Ricerca e informazioni personali in SharePoint Server 2010

#### <a name="fast-search-server-2010-for-sharepoint"></a>FAST Search Server 2010 for SharePoint 

Oltre ad archiviare i file nell'indice, il componente aggiuntivo di FAST Search Server 2010 archivia i file in un formato intermedio denominato FiXML. I File FiXML vengono compattati regolarmente, per impostazione predefinita, ogni notte tra le 03:00 e le 05:00. La compattazione rimuove automaticamente i file eliminati dai file FiXML. Per garantire la rimozione tempestiva delle informazioni appartenenti agli utenti o ai documenti eliminati, assicurarsi che la compattazione sia sempre abilitata.

### <a name="hybrid-search"></a>Ricerca ibrida 

Le azioni consigliate per le soluzioni di ricerca ibrida sono le stesse consigliate per la ricerca in SharePoint Server o SharePoint Online. Esistono due soluzioni di ricerca ibrida:

**Soluzione di ricerca ibrida cloud -** Con la soluzione di ricerca ibrida cloud per SharePoint, è possibile inserire tutti i contenuti sottoposti a una ricerca per indicizzazione, compresi quelli locali, nell'indice di ricerca in Office 365. Quando gli utenti eseguono query dell'indice di ricerca in Office 365, ottengono risultati di ricerca sia dai contenuti locali sia da quelli di Office 365. Quando i documenti vengono eliminati dall'ambiente di SharePoint Server, saranno rimossi anche dall'indice di ricerca di Office 365. [Leggere ulteriori informazioni riguardanti la soluzione di ricerca ibrida cloud](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) e su [come i componenti di ricerca e i database interagiscono nella ricerca ibrida cloud](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) per comprendere meglio come il GDPR influisce sull'ambiente ibrido.

**Soluzione di ricerca federata ibrida -** Con la soluzione di ricerca federata ibrida, si utilizza sia l'indice in SharePoint Server sia quello in Office 365. Entrambi i servizi di ricerca di SharePoint Server e SharePoint Online possono eseguire una query sull'indice di ricerca nell'altro ambiente e restituire risultati federati. Quando gli utenti eseguono ricerche da un Centro ricerche, i risultati della ricerca provengono dall'indice di ricerca in SharePoint Server e dall'indice di ricerca in Office 365.[Leggere ulteriori informazioni riguardanti la soluzione di ricerca federata ibrida](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) per comprendere meglio come il GDPR influisce sull'ambiente ibrido.

## <a name="on-prem-to-cloud-migrations"></a>Migrazioni da locale al cloud

Durante la migrazione dei dati da SharePoint Server a SharePoint Online, è possibile riscontrare l'esistenza di dati duplicati in entrambe le posizioni per un determinato periodo. Se si dispone di dati da eliminare che sono ancora in corso di migrazione, si consiglia di completare prima la migrazione e quindi di eliminare i dati da entrambe le posizioni. È possibile eseguire una query dei dati da esportare da entrambe le posizioni.

## <a name="user-profile-data"></a>Dati profilo utente

Il servizio profili utente consente di importare i dati dei profili da una varietà di origini esterne. Gli aggiornamenti e le query relative a tali dati profili utente dovranno essere gestiti dal sistema di appartenenza dei dati. Se si aggiorna il sistema esterno, assicurarsi di sincronizzare nuovamente i profili utente in SharePoint Server.

Seguire questi semplici passaggi per rimuovere le informazioni personali di un utente dal relativo profilo utente in SharePoint Server:

1.  Rimuovere le informazioni utente da tutti i sistemi esterni che vengono inseriti nel profilo utente di SharePoint Server. Se si esegue la sincronizzazione della directory, l'utente dovrà essere rimosso dall'ambiente Active Directory locale.

2.  Eseguire una[sincronizzazione dei profili](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) su SharePoint Server.

3.  Eliminare il profilo di SharePoint Server. Una volta terminata la procedura, SharePoint Server rimuoverà completamente il profilo dal Database profili utente entro 30 giorni. La pagina del profilo e il sito personale dell'utente saranno cancellati.

Dopo l'eliminazione di un profilo utente, alcune informazioni limitate (ad esempio l'ID utente) potrebbero risultare ancora registrate nelle raccolte siti visitate dall'utente. Se si sceglie di eliminare i dati da una raccolta siti, questa operazione può essere eseguita utilizzando CSOM. Qui di seguito è riportato uno script di esempio:

```powershell
$username = "<admin@company.sharepoint.com>"
$password = "password"
$url = "<https://site.sharepoint.com>"
$securePassword = ConvertTo-SecureString $Password -AsPlainText -Force

# the path here may need to change if you used e.g. C:Lib.
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.dll"
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.Runtime.dll"

# connect/authenticate to SharePoint Online and get ClientContext object.
$clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($username, $securePassword)
$clientContext.Credentials = $credentials
if (!$clientContext.ServerObjectIsNull.Value)
{
    Write-Host "Connected to SharePoint Online site: '$Url'" -ForegroundColor Green
}

# Get user
$user = $clientContext.Web.SiteUsers.GetByLoginName("i:0#.f|membership|user@company.sharepoint.com")

# Redact user
$user.Email = "Redacted"
$user.Title = "Redacted"
$user.Update()
$clientContext.Load($user)
$clientContext.ExecuteQuery()

# Get users
$users = $clientContext.Web.SiteUsers

# Remove user from site
$users.RemoveById($user.Id)
$clientContext.Load($users)
$clientContext.ExecuteQuery()
```
