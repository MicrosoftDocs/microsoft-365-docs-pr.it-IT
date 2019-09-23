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
ms.openlocfilehash: 6da9d635506eafc2b976cf6a87f68370f40e327a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082890"
---
# <a name="gdpr-for-sharepoint-server"></a><span data-ttu-id="dec7b-103">GDPR per SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="dec7b-103">GDPR for SharePoint Server</span></span>

<span data-ttu-id="dec7b-104">Nell'ambito di protezione delle informazioni personali, si consiglia quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dec7b-104">As part of safeguarding personal information, we recommend the following:</span></span>

-   <span data-ttu-id="dec7b-105">Classificare i propri dati utilizzando Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="dec7b-105">Classify your data, using Azure Information Protection.</span></span>

-   <span data-ttu-id="dec7b-p101">Eseguire SharePoint Server con una configurazione con privilegi minimi. Per ulteriori informazioni, vedere [Pianificare l'amministrazione con privilegi minimi in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) e [Sicurezza per SharePoint Server](https://docs.microsoft.com/it-IT/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).</span><span class="sxs-lookup"><span data-stu-id="dec7b-p101">Run SharePoint Server in a least-privileged configuration. See [Plan for least-privileged administration in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) and [Security for SharePoint Server](https://docs.microsoft.com/it-IT/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) for more information.</span></span>

-   <span data-ttu-id="dec7b-108">[Attivare la crittografia BitLocker nei server](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="dec7b-108">[Enable BitLocker encryption on your servers](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span></span>

## <a name="user-generated-content"></a><span data-ttu-id="dec7b-109">Contenuti generato dall'utente</span><span class="sxs-lookup"><span data-stu-id="dec7b-109">User Generated content</span></span>

<span data-ttu-id="dec7b-110">L'approccio consigliato per i contenuti generati dall'utente inclusi nei siti e nelle raccolte di SharePoint Server è il seguente:</span><span class="sxs-lookup"><span data-stu-id="dec7b-110">The basic recommended approach for user generated content contained in SharePoint Server sites and libraries is:</span></span>

-   <span data-ttu-id="dec7b-111">Utilizzare Azure Information Protection per etichettare dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="dec7b-111">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="dec7b-112">Utilizzare [Servizio di ricerca di SharePoint Server](https://docs.microsoft.com/SharePoint/search/search) ed [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) per recuperare i dati riservati.</span><span class="sxs-lookup"><span data-stu-id="dec7b-112">Use [SharePoint Server search](https://docs.microsoft.com/SharePoint/search/search) and [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) to retrieve sensitive data.</span></span>

<span data-ttu-id="dec7b-113">L'approccio consigliato per le condivisioni file e per i siti e le raccolte di SharePoint include i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="dec7b-113">The recommended approach for files shares and SharePoint sites and libraries includes these steps:</span></span>

1.  <span data-ttu-id="dec7b-114">**[Installare e configurare lo scanner di Azure Information Protection.](https://docs.microsoft.com/it-IT/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span><span class="sxs-lookup"><span data-stu-id="dec7b-114">**[Install and configure Azure Information Protection scanner.](https://docs.microsoft.com/it-IT/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span></span>

    -   <span data-ttu-id="dec7b-115">Scegliere i tipi di dati sensibili da usare.</span><span class="sxs-lookup"><span data-stu-id="dec7b-115">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="dec7b-116">Specificare i siti di SharePoint da usare.</span><span class="sxs-lookup"><span data-stu-id="dec7b-116">Specify which SharePoint sites to use.</span></span>

2.  <span data-ttu-id="dec7b-117">**Completare un ciclo di individuazione.**</span><span class="sxs-lookup"><span data-stu-id="dec7b-117">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="dec7b-118">Eseguire lo scanner in modalità di individuazione e convalidare i risultati.</span><span class="sxs-lookup"><span data-stu-id="dec7b-118">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="dec7b-119">Se necessario, ottimizzare le condizioni e i tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="dec7b-119">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="dec7b-120">Valutare l'impatto previsto dell'applicazione automatica delle etichette.</span><span class="sxs-lookup"><span data-stu-id="dec7b-120">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="dec7b-121">**Eseguire lo scanner di Azure Information Protection per applicare etichette a documenti idonei**.</span><span class="sxs-lookup"><span data-stu-id="dec7b-121">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="dec7b-122">**Per la protezione:**</span><span class="sxs-lookup"><span data-stu-id="dec7b-122">**For protection:**</span></span>

    <span data-ttu-id="dec7b-p102">a.  Configurare le regole di prevenzione della perdita dei dati di Exchange per proteggere i documenti con l'etichetta desiderata.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p102">a.  Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    <span data-ttu-id="dec7b-p103">b.  Assicurarsi di utilizzare le autorizzazioni per definire chi può accedere ai file.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p103">b.  Be sure permissions to limit who can access files.</span></span>

    <span data-ttu-id="dec7b-p104">c.  Per SharePoint, utilizzare la Protezione IRM per le raccolte.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p104">c.  For SharePoint, use IRM-protection for libraries.</span></span>

5.  <span data-ttu-id="dec7b-129">**Per il monitoraggio, integrare i log di Windows Server con uno strumento informazioni di sicurezza e gestione degli eventi.**</span><span class="sxs-lookup"><span data-stu-id="dec7b-129">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    <span data-ttu-id="dec7b-p105">a.  Per ottenere i dati personali per le richieste degli interessati, utilizzare Centro ricerche o eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p105">a.  To find personal data for data subject requests, use Search Center or eDiscovery.</span></span>

<span data-ttu-id="dec7b-p106">Quando si applicano etichette a dati sensibili, assicurarsi di assegnare un'etichetta non configurata con la protezione. La protezione include la crittografia che impedisce ai servizi di rilevare i dati sensibili nei file.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p106">When applying labels to sensitive data, be sure to use a label that is not configured with protection. Protection includes encryption which prevents services from detecting sensitive data in the files.</span></span>

<span data-ttu-id="dec7b-134">Per ulteriori informazioni sull'uso dello scanner di Azure Information Protection per individuare ed etichettare dati personali, vedere [Toolkit per l'individuazione di dati GDPR di Microsoft](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).</span><span class="sxs-lookup"><span data-stu-id="dec7b-134">For more information on using Azure Information Protection scanner to find and label personal data, see the [Microsoft GDPR Data Discovery Toolkit](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).</span></span>

<span data-ttu-id="dec7b-p107">Per informazioni sulla configurazione dello scanner per le condizioni e l'utilizzo della prevenzione della perdita dei dati (DLP) di Office 365 con tipi di informazioni riservate, vedere [Come configurare le condizioni per la classificazione automatica e consigliata per Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Si noti che i nuovi tipi di informazioni riservate di Office 365 non saranno immediatamente disponibili per l'uso con lo scanner e che i tipi di informazioni riservate personalizzate non possono essere usati con lo scanner.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p107">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>

## <a name="removing-personal-information-from-office-files"></a><span data-ttu-id="dec7b-137">Rimozione delle informazioni personali dal file di Office</span><span class="sxs-lookup"><span data-stu-id="dec7b-137">Removing personal information from Office files</span></span>

<span data-ttu-id="dec7b-p108">La rimozione delle informazioni personali (come ad esempio metadati o commenti in un documento di Word) dai file di Office archiviati nella raccolta documenti di SharePoint deve essere eseguita manualmente. Per eseguirla attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="dec7b-p108">Removing personal information (such as metadata or comments in a Word document) from Office files that are stored in a SharePoint document library must be done manually. Follow these steps:</span></span>

1.  <span data-ttu-id="dec7b-140">Scaricare una copia del documento da SharePoint Server al disco locale.</span><span class="sxs-lookup"><span data-stu-id="dec7b-140">Download a copy of the document from SharePoint Server to your local disk.</span></span>

2.  <span data-ttu-id="dec7b-141">Eliminare il documento dalla raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dec7b-141">Delete the document from the SharePoint document library.</span></span>

3.  <span data-ttu-id="dec7b-142">Attenersi alla procedura descritta in [Rimuovere dati nascosti e informazioni personali tramite il controllo dei documenti](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span><span class="sxs-lookup"><span data-stu-id="dec7b-142">Follow the steps in [Remove hidden data and personal information by inspecting documents](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span></span>

4.  <span data-ttu-id="dec7b-143">Caricare nuovamente il documento nella raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dec7b-143">Upload the document back to the SharePoint document library.</span></span>

## <a name="telemetry-and-log-files"></a><span data-ttu-id="dec7b-144">Telemetria e file di log</span><span class="sxs-lookup"><span data-stu-id="dec7b-144">Telemetry and log files</span></span>

### <a name="uls-logs"></a><span data-ttu-id="dec7b-145">Registri ULS</span><span class="sxs-lookup"><span data-stu-id="dec7b-145">ULS Logs</span></span>

<span data-ttu-id="dec7b-p109">Il servizio di registrazione unificato (ULS) e la Registrazione di utilizzo in SharePoint Server consentono di tracciare una varietà di funzioni di sistema e possono contenere le informazioni utente. I Registri ULS e i registri di utilizzo consistono in file di testo che è possibile cercare con molti strumenti di ricerca. Il [cmdlet Merge-SPLogFile PowerShell](https://docs.microsoft.com/it-IT/powershell/module/sharepoint-server/merge-splogfile) consente di restituire i record dai Registri ULS su più server in una farm.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p109">Unified Logging Service (ULS) and Usage logging in SharePoint Server track a variety of system functions and can contain user information. ULS logs and usage logs are text files and can be searched using a variety of searching tools. The [Merge-SPLogFile PowerShell cmdlet](https://docs.microsoft.com/it-IT/powershell/module/sharepoint-server/merge-splogfile) provides a way to return records from the ULS logs on multiple servers in a farm.</span></span>

<span data-ttu-id="dec7b-p110">È consigliabile impostare i criteri di conservazione dei registri per il valore minimo richiesto per le attività aziendali. Per informazioni sulla configurazione della registrazione in SharePoint Server, vedere [Configurare la registrazione diagnostica in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="dec7b-p110">Consider setting log retention policies to the minimum value needed for your business purposes. For information about configuring logging in SharePoint Server, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

<span data-ttu-id="dec7b-151">Si noti che alcuni eventi di sistema vengono registrati anche nel Registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="dec7b-151">Note that some system events are also logged to the Windows Event Log.</span></span>

### <a name="usage-database"></a><span data-ttu-id="dec7b-152">Database del servizio di utilizzo</span><span class="sxs-lookup"><span data-stu-id="dec7b-152">Usage Database</span></span>

<span data-ttu-id="dec7b-p111">Il database del servizio di utilizzo di SharePoint Server (nome predefinito WSS_Logging) contiene un sottoinsieme delle informazioni presenti nei Registri ULS. Il periodo massimo di conservazione dei dati in questo database è di 30 giorni. È consigliabile configurarlo per la durata minima consentita dalle esigenze dell'azienda. Per ulteriori informazioni, vedere [Configurare la registrazione diagnostica in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="dec7b-p111">The SharePoint Server Usage database (default name WSS_Logging) contains a subset of the information found in the ULS logs. The maximum retention of data in this database is 30 days. We recommend that you configure it for the shortest duration allowable by your business needs. For more information, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

## <a name="personal-information-and-search"></a><span data-ttu-id="dec7b-157">Ricerca e informazioni personali</span><span class="sxs-lookup"><span data-stu-id="dec7b-157">Personal information and search</span></span>

<span data-ttu-id="dec7b-158">La cronologia query di ricerca e i record utilizzo contengono riferimenti ai nomi utente.</span><span class="sxs-lookup"><span data-stu-id="dec7b-158">The search query history and usage records contain references to user names.</span></span>

### <a name="query-history-and-favorite-queries"></a><span data-ttu-id="dec7b-159">Cronologia query e query preferite</span><span class="sxs-lookup"><span data-stu-id="dec7b-159">Query history and favorite queries</span></span>

<span data-ttu-id="dec7b-p112">In SharePoint Server, la cronologia delle query e le query "preferite" scadono automaticamente dopo 365 giorni. Se un utente lascia l'organizzazione, è possibile rimuovere i riferimenti a un nome utente dalla cronologia delle query tramite la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p112">In SharePoint Server, query histories and ‘favorite’ queries automatically expire after 365 days. If a user leaves your organization, it is possible to remove references to a user's name from the query history using the steps below.</span></span>

<span data-ttu-id="dec7b-162">Le seguenti query SQL si applicano a SharePoint Server e consentono di:</span><span class="sxs-lookup"><span data-stu-id="dec7b-162">The following SQL queries apply to SharePoint Server and make it possible to:</span></span>

-   <span data-ttu-id="dec7b-163">Esportare la cronologia query o le query preferite di un utente</span><span class="sxs-lookup"><span data-stu-id="dec7b-163">Export a user’s query history or favorite queries</span></span>

-   <span data-ttu-id="dec7b-164">Rimuovere i riferimenti ai nomi utente nella cronologia query</span><span class="sxs-lookup"><span data-stu-id="dec7b-164">Remove references to user names in the query history</span></span>

#### <a name="export-a-users-queries-since-a-specific-date"></a><span data-ttu-id="dec7b-165">Esportare le query di un utente fino a una data specifica</span><span class="sxs-lookup"><span data-stu-id="dec7b-165">Export a user’s queries since a specific date</span></span> 

<span data-ttu-id="dec7b-166">Utilizzare la procedura seguente per esportare le query dalle tabelle dei log di query di Link Store eseguite da @NomeUtente a partire da@DataInizio.</span><span class="sxs-lookup"><span data-stu-id="dec7b-166">Use the following procedure to export queries from the Link Store query log tables, performed by @UserName since @StartTime.</span></span>

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

#### <a name="export-a-users-queries-from-the-past-100-days"></a><span data-ttu-id="dec7b-167">Esportare le query di un utente relative a un periodo di 100 giorni</span><span class="sxs-lookup"><span data-stu-id="dec7b-167">Export a user’s queries from the past 100 days</span></span>

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a><span data-ttu-id="dec7b-168">Esportare le query preferite di un utente</span><span class="sxs-lookup"><span data-stu-id="dec7b-168">Export a user’s favorite queries</span></span>

<span data-ttu-id="dec7b-169">Utilizzare la procedura seguente per esportare le query preferite di un utente dalle tabelle dei risultati personali del DB di amministrazione ricerca, eseguite da @NomeUtente, a partire da <DateTime>.</span><span class="sxs-lookup"><span data-stu-id="dec7b-169">Use the following procedure to export a user's favorite queries from the Search Admin DB personal result tables, performed by @UserName, since <DateTime>.</span></span>

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

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a><span data-ttu-id="dec7b-170">Esportare le query preferite di un utente relative a un periodo di 100 giorni</span><span class="sxs-lookup"><span data-stu-id="dec7b-170">Export a user’s favorite queries from the past 100 days</span></span> 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a><span data-ttu-id="dec7b-171">Rimuovere i riferimenti ai nomi utente creati da più di X giorni</span><span class="sxs-lookup"><span data-stu-id="dec7b-171">Remove references to user names that are more than X days old</span></span>

<span data-ttu-id="dec7b-p113">Utilizzare la procedura seguente per rimuovere i riferimenti a *tutti* i nomi utente creati più di @NumeroGiorni prima dalle tabelle dei log di query di Link Store. Questa procedura rimuove soltanto i riferimenti passati fino al raggiungimento di @DataUltimaPulizia.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p113">Use the following procedure to remove references to *all* user names that are more than @Days old, from the Links Store query log tables. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a><span data-ttu-id="dec7b-174">Rimuovere i riferimenti a uno specifico nome utente creato da più di X giorni</span><span class="sxs-lookup"><span data-stu-id="dec7b-174">Remove references to a specific user name that’s more than X days old</span></span>

<span data-ttu-id="dec7b-p114">Utilizzare la procedura seguente per rimuovere i riferimenti a uno *specifico* nome utente che risalgono a più di @NumeroGiorni dalle tabelle dei log di query di Link Store. Questa procedura rimuove soltanto i riferimenti passati fino al raggiungimento di @DataUltimaPulizia.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p114">Use the following procedure to remove references to a *specific* user name from the Links Store query log tables, where the references are more than @Days old. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a><span data-ttu-id="dec7b-177">Rimuovere i riferimenti a tutti i nomi utente nella cronologia query a partire da una data e per un periodo massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="dec7b-177">Remove references to all user names in the query history from a date and up to the past 30 days</span></span>

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a><span data-ttu-id="dec7b-178">Eliminare i record di utilizzo</span><span class="sxs-lookup"><span data-stu-id="dec7b-178">Delete usage records</span></span>

<span data-ttu-id="dec7b-p115">SharePoint Server elimina automaticamente i record di utilizzo dopo 3 anni. È possibile eliminare manualmente questi record tramite la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="dec7b-p115">SharePoint Server automatically deletes usage records after 3 years. You can manually delete such records using the procedure below:</span></span>

<span data-ttu-id="dec7b-181">Per eliminare tutti i record di utilizzo associati ai documenti eliminati:</span><span class="sxs-lookup"><span data-stu-id="dec7b-181">To delete all usage records associated with deleted documents:</span></span> 

1.  <span data-ttu-id="dec7b-182">Assicurarsi di avere installato l'aggiornamento più recente di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dec7b-182">Ensure that you have the latest SharePoint update installed.</span></span> 

2.  <span data-ttu-id="dec7b-183">Avviare una SharePoint Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dec7b-183">Start a SharePoint Management shell.</span></span>

3.  <span data-ttu-id="dec7b-184">Interrompere e cancellare l'analisi utilizzo:</span><span class="sxs-lookup"><span data-stu-id="dec7b-184">Stop and Clear the Usage Analytics analysis:</span></span> 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  <span data-ttu-id="dec7b-185">Attendere il riavvio dell'analisi (potrebbe richiedere fino a 24 ore).</span><span class="sxs-lookup"><span data-stu-id="dec7b-185">Wait for the analysis to start again (might take up to 24 hours).</span></span> 

5.  <span data-ttu-id="dec7b-p116">La successiva esecuzione dell'analisi eliminerà tutti i record dal Database di report di analisi. Il backup completo di un database contenente un numero elevato di voci potrebbe richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p116">On the next run of the analysis, it will dump all records from the Analytics Reporting database. This full dump may take a while for a large database with many entries.</span></span>

6.  <span data-ttu-id="dec7b-p117">Attendere 10 giorni. L'analisi verrà eseguita ogni giorno e i record associati ai documenti eliminati verranno rimossi dopo la decima esecuzione. Se dovesse essere necessario eliminare molti record, quest'ultima esecuzione potrebbe richiedere più tempo del normale.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p117">Wait for 10 days. The analysis runs daily, and records associated with deleted documents will be removed after the 10^th^ run. This run may take longer than normal if many records need to be deleted.</span></span> 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a><span data-ttu-id="dec7b-191">Ricerca e informazioni personali in SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="dec7b-191">Personal information and search in SharePoint Server 2010</span></span>

#### <a name="fast-search-server-2010-for-sharepoint"></a><span data-ttu-id="dec7b-192">FAST Search Server 2010 for SharePoint</span><span class="sxs-lookup"><span data-stu-id="dec7b-192">FAST Search Server 2010 for SharePoint</span></span> 

<span data-ttu-id="dec7b-p118">Oltre ad archiviare i file nell'indice, il componente aggiuntivo di FAST Search Server 2010 archivia i file in un formato intermedio denominato FiXML. I File FiXML vengono compattati regolarmente, per impostazione predefinita, ogni notte tra le 03:00 e le 05:00. La compattazione rimuove automaticamente i file eliminati dai file FiXML. Per garantire la rimozione tempestiva delle informazioni appartenenti agli utenti o ai documenti eliminati, assicurarsi che la compattazione sia sempre abilitata.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p118">In addition to storing files in the index, the FAST Search Server 2010 Add-On also stores files in an intermediate format called FixML. FiXML files are compacted regularly, by default between 3 am and 5 am every night. Compaction removes deleted files from the FiXML files automatically. To ensure timely removal of information belonging to deleted users or documents, ensure that compaction is always enabled.</span></span>

### <a name="hybrid-search"></a><span data-ttu-id="dec7b-197">Ricerca ibrida</span><span class="sxs-lookup"><span data-stu-id="dec7b-197">Hybrid Search</span></span> 

<span data-ttu-id="dec7b-p119">Le azioni consigliate per le soluzioni di ricerca ibrida sono le stesse consigliate per la ricerca in SharePoint Server o SharePoint Online. Esistono due soluzioni di ricerca ibrida:</span><span class="sxs-lookup"><span data-stu-id="dec7b-p119">The recommended actions for hybrid search solutions are the same as for search in SharePoint Server or SharePoint Online. There are two hybrid search solutions:</span></span>

<span data-ttu-id="dec7b-p120">**Soluzione di ricerca ibrida cloud -** Con la soluzione di ricerca ibrida cloud per SharePoint, è possibile inserire tutti i contenuti sottoposti a una ricerca per indicizzazione, compresi quelli locali, nell'indice di ricerca in Office 365. Quando gli utenti eseguono query dell'indice di ricerca in Office 365, ottengono risultati di ricerca sia dai contenuti locali sia da quelli di Office 365. Quando i documenti vengono eliminati dall'ambiente di SharePoint Server, saranno rimossi anche dall'indice di ricerca di Office 365. [Leggere ulteriori informazioni riguardanti la soluzione di ricerca ibrida cloud](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) e su [come i componenti di ricerca e i database interagiscono nella ricerca ibrida cloud](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) per comprendere meglio come il GDPR influisce sull'ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p120">**The cloud hybrid search solution -** With the cloud hybrid search solution for SharePoint, you index all your crawled content, including on-premises content, in your search index in Office 365. When users query your search index in Office 365, they get search results from both on-premises and Office 365 content. When documents are deleted from the SharePoint Server environment, they are also deleted from the search index in Office 365. [Read more about the cloud hybrid search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) and [how search components and databases interact in cloud hybrid search](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

<span data-ttu-id="dec7b-p121">**Soluzione di ricerca federata ibrida -** Con la soluzione di ricerca federata ibrida, si utilizza sia l'indice in SharePoint Server sia quello in Office 365. Entrambi i servizi di ricerca di SharePoint Server e SharePoint Online possono eseguire una query sull'indice di ricerca nell'altro ambiente e restituire risultati federati. Quando gli utenti eseguono ricerche da un Centro ricerche, i risultati della ricerca provengono dall'indice di ricerca in SharePoint Server e dall'indice di ricerca in Office 365.[Leggere ulteriori informazioni riguardanti la soluzione di ricerca federata ibrida](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) per comprendere meglio come il GDPR influisce sull'ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p121">**The hybrid federated search solution -** With the hybrid federated search solution, you use both your index in SharePoint Server and your index in Office 365. Both SharePoint Server and SharePoint Online Search services can query the search index in the other environment and return federated results. When users search from a Search Center, the search results come from both your search index in SharePoint Server and your search index in Office 365. [Read more about the hybrid federated search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

## <a name="on-prem-to-cloud-migrations"></a><span data-ttu-id="dec7b-208">Migrazioni da locale al cloud</span><span class="sxs-lookup"><span data-stu-id="dec7b-208">On Prem to Cloud Migrations</span></span>

<span data-ttu-id="dec7b-p122">Durante la migrazione dei dati da SharePoint Server a SharePoint Online, è possibile riscontrare l'esistenza di dati duplicati in entrambe le posizioni per un determinato periodo. Se si dispone di dati da eliminare che sono ancora in corso di migrazione, si consiglia di completare prima la migrazione e quindi di eliminare i dati da entrambe le posizioni. È possibile eseguire una query dei dati da esportare da entrambe le posizioni.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p122">While migrating data from SharePoint Server to SharePoint Online, duplicate data may exist in both locations for a time. If you have data that you need to delete that is in mid-migration, we recommend that you complete the migration first, and then delete the data from both locations. You can query data for export from either location.</span></span>

## <a name="user-profile-data"></a><span data-ttu-id="dec7b-212">Dati profilo utente</span><span class="sxs-lookup"><span data-stu-id="dec7b-212">User Profile data</span></span>

<span data-ttu-id="dec7b-p123">Il servizio profili utente consente di importare i dati dei profili da una varietà di origini esterne. Gli aggiornamenti e le query relative a tali dati profili utente dovranno essere gestiti dal sistema di appartenenza dei dati. Se si aggiorna il sistema esterno, assicurarsi di sincronizzare nuovamente i profili utente in SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p123">The User Profile Service allows for import of profile data from a variety of external sources. Queries for and update of such user profile data should be handled in the systems in which the data is mastered. If you make updates to the external system, be sure to synchronize the user profiles in SharePoint Server again.</span></span>

<span data-ttu-id="dec7b-216">Seguire questi semplici passaggi per rimuovere le informazioni personali di un utente dal relativo profilo utente in SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="dec7b-216">Follow these basic steps to remove a user’s personal information from their SharePoint Server user profile:</span></span>

1.  <span data-ttu-id="dec7b-p124">Rimuovere le informazioni utente da tutti i sistemi esterni che vengono inseriti nel profilo utente di SharePoint Server. Se si esegue la sincronizzazione della directory, l'utente dovrà essere rimosso dall'ambiente Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p124">Remove the user information from any external systems that feed into the SharePoint Server user profile. If you are using directory synchronization, the user must be removed from the on-premises Active Directory environment.</span></span>

2.  <span data-ttu-id="dec7b-219">Eseguire una[sincronizzazione dei profili](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) su SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="dec7b-219">Run a [profile synchronization](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) on SharePoint Server.</span></span>

3.  <span data-ttu-id="dec7b-p125">Eliminare il profilo di SharePoint Server. Una volta terminata la procedura, SharePoint Server rimuoverà completamente il profilo dal Database profili utente entro 30 giorni. La pagina del profilo e il sito personale dell'utente saranno cancellati.</span><span class="sxs-lookup"><span data-stu-id="dec7b-p125">Delete the profile from SharePoint Server. Once this is done, SharePoint Server will fully remove the profile from the User Profile Database in 30 days. The user’s profile page and personal site will be deleted.</span></span>

<span data-ttu-id="dec7b-p126">Dopo l'eliminazione di un profilo utente, alcune informazioni limitate (ad esempio l'ID utente) potrebbero risultare ancora registrate nelle raccolte siti visitate dall'utente. Se si sceglie di eliminare i dati da una raccolta siti, questa operazione può essere eseguita utilizzando CSOM. Qui di seguito è riportato uno script di esempio:</span><span class="sxs-lookup"><span data-stu-id="dec7b-p126">After deleting a user’s profile, some limited information (such as user ID) may still be recorded in site collections that the user has visited. If you choose to delete this data from a given site collection, this can be done using CSOM. A sample script is provided below:</span></span>

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
