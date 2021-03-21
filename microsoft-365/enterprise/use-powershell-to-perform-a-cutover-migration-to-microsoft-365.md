---
title: Utilizzare PowerShell per eseguire una migrazione completa a Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Informazioni su come usare PowerShell per spostare il contenuto da un sistema di posta elettronica di origine contemporaneamente eseguendo una migrazione completa a Microsoft 365.
ms.openlocfilehash: 60bd3cb246e04aba37be06f7a951abbf25708412
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924805"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="22a8f-103">Utilizzare PowerShell per eseguire una migrazione completa a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22a8f-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="22a8f-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="22a8f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="22a8f-105">È possibile eseguire la migrazione del contenuto delle cassette postali degli utenti da un sistema di posta elettronica di origine a Microsoft 365 contemporaneamente utilizzando una migrazione completa.</span><span class="sxs-lookup"><span data-stu-id="22a8f-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="22a8f-106">In questo articolo vengono illustrate le attività per una migrazione completa della posta elettronica tramite PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="22a8f-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="22a8f-107">Esaminando l'argomento What [you need to know about a cutover email migration to Microsoft 365,](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)you can get an overview of the migration process.</span><span class="sxs-lookup"><span data-stu-id="22a8f-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), you can get an overview of the migration process.</span></span> <span data-ttu-id="22a8f-108">Una volta appresi i contenuti di questo articolo, utilizzarlo per iniziare la migrazione delle cassette postali da un sistema di posta elettronica a un altro.</span><span class="sxs-lookup"><span data-stu-id="22a8f-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="22a8f-109">Inoltre, è possibile utilizzare l'interfaccia di amministrazione di Exchange per eseguire una migrazione completa.</span><span class="sxs-lookup"><span data-stu-id="22a8f-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="22a8f-110">Vedere [Eseguire una migrazione completa della posta elettronica a Microsoft 365.](/Exchange/mailbox-migration/cutover-migration-to-office-365)</span><span class="sxs-lookup"><span data-stu-id="22a8f-110">See [Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="22a8f-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="22a8f-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="22a8f-112">Tempo stimato per il completamento di questa attività: tra i 2 e i 5 minuti per creare un batch di migrazione.</span><span class="sxs-lookup"><span data-stu-id="22a8f-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="22a8f-113">Dopo l'avvio del batch di migrazione, la durata della migrazione varia in base al numero di cassette postali nel batch, alla dimensione di ogni cassetta postale e alla capacità di rete disponibile.</span><span class="sxs-lookup"><span data-stu-id="22a8f-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="22a8f-114">Per informazioni su altri fattori che influiscono sul tempo necessario per eseguire la migrazione delle cassette postali a Microsoft 365, vedere [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span><span class="sxs-lookup"><span data-stu-id="22a8f-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="22a8f-p105">È necessario disporre delle autorizzazioni per poter eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Migrazione" in una tabella nell'argomento [Autorizzazioni di destinatari](/exchange/recipients-permissions-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="22a8f-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="22a8f-p106">Per utilizzare i cmdlet di PowerShell di Exchange Online, è necessario eseguire l'accesso e importare i cmdlet nella sessione di Windows PowerShell locale. Per le istruzioni, vedere [Connettersi a Exchange Online tramite Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="22a8f-p106">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="22a8f-119">Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="22a8f-119">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="22a8f-120">Procedura della migrazione</span><span class="sxs-lookup"><span data-stu-id="22a8f-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="22a8f-121">Passaggio 1: predisporre una migrazione completa</span><span class="sxs-lookup"><span data-stu-id="22a8f-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="22a8f-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="22a8f-123">**Aggiungere l'organizzazione exchange locale come dominio accettato dell'organizzazione di Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="22a8f-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="22a8f-124">Il servizio di migrazione utilizza l'indirizzo SMTP delle cassette postali locali per creare l'ID utente Microsoft Online Services e l'indirizzo di posta elettronica per le nuove cassette postali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="22a8f-125">La migrazione avrà esito negativo se il dominio di Exchange non è un dominio accettato o il dominio principale dell'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="22a8f-126">Per ulteriori informazioni, vedere [Verify your domain](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="22a8f-126">For more information, see [Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="22a8f-p108">**Configurare Outlook via Internet nel server Exchange locale** Nel servizio di migrazione della posta elettronica viene utilizzato RPC su HTTP, anche denominato Outlook via Internet, per connettersi al server Exchange locale. Per informazioni sull'installazione di Outlook via Internet per Exchange 2010, Exchange 2007 ed Exchange 2003, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a8f-p108">**Configure Outlook Anywhere on your on-premises Exchange server.** The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server. For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - <span data-ttu-id="22a8f-130">[Exchange 2010: Abilita Outlook via Internet](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="22a8f-130">[Exchange 2010: Enable Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span></span>

  - <span data-ttu-id="22a8f-131">[Exchange 2007: Come abilitare Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="22a8f-131">[Exchange 2007: How to Enable Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span></span>

  - <span data-ttu-id="22a8f-132">[Exchange 2003: Scenari di distribuzione per RPC su HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="22a8f-132">[Exchange 2003: Deployment Scenarios for RPC over HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span></span>

  - <span data-ttu-id="22a8f-133">[Configurazione di Outlook via Internet con Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="22a8f-133">[How to Configure Outlook Anywhere with Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="22a8f-p109">È necessario configurare Outlook via Internet con un certificato considerato attendibile da un'autorità di certificazione (CA, Certificate Authority). Non può essere configurato con un certificato autofirmato. Per ulteriori informazioni, vedere [Come configurare SSL per Outlook via Internet](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span><span class="sxs-lookup"><span data-stu-id="22a8f-p109">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA). It can't be configured with a self-signed certificate. For more information, see [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span></span>

- <span data-ttu-id="22a8f-p110">**Verificare che sia possibile connettersi all'organizzazione di Exchange tramite Outlook via Internet** Provare uno di questi metodi per testare le impostazioni di connessione:</span><span class="sxs-lookup"><span data-stu-id="22a8f-p110">**Verify that you can connect to your Exchange organization using Outlook Anywhere.** Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="22a8f-139">Utilizzare Microsoft Outlook all'esterno della rete aziendale per connettersi alla cassetta postale di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="22a8f-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="22a8f-p111">Utilizzare Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) per testare le impostazioni della connessione. Utilizzare Outlook via Internet (RPC su HTTP) o i test di individuazione automatica di Outlook.</span><span class="sxs-lookup"><span data-stu-id="22a8f-p111">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings. Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="22a8f-142">In PowerShell di Exchange Online, eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="22a8f-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="22a8f-143">**Assegnare a un account utente locale le autorizzazioni necessarie per accedere alle cassette postali nella propria organizzazione di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="22a8f-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="22a8f-144">L'account utente locale utilizzato per connettersi all'organizzazione di Exchange locale (denominato anche amministratore della migrazione) deve disporre delle autorizzazioni necessarie per accedere alle cassette postali locali di cui si desidera eseguire la migrazione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="22a8f-145">Questo account utente viene utilizzato per creare un endpoint di migrazione per la propria organizzazione locale.</span><span class="sxs-lookup"><span data-stu-id="22a8f-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="22a8f-p113">Nel seguente elenco vengono mostrati i privilegi amministrativi necessari per migrare le cassette postali tramite una migrazione completa. Esistono tre opzioni possibili.</span><span class="sxs-lookup"><span data-stu-id="22a8f-p113">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration. There are three possible options.</span></span>

  - <span data-ttu-id="22a8f-148">L'amministratore di migrazione deve essere un membro del gruppo **Domain Admins** in Active Directory nell'organizzazione locale.</span><span class="sxs-lookup"><span data-stu-id="22a8f-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="22a8f-149">Oppure</span><span class="sxs-lookup"><span data-stu-id="22a8f-149">Or</span></span>

  - <span data-ttu-id="22a8f-150">All'amministratore di migrazione è assegnata l'autorizzazione **FullAccess** per ogni cassetta postale locale.</span><span class="sxs-lookup"><span data-stu-id="22a8f-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="22a8f-151">Oppure</span><span class="sxs-lookup"><span data-stu-id="22a8f-151">Or</span></span>

  - <span data-ttu-id="22a8f-152">All'amministratore di migrazione deve essere assegnata l'autorizzazione **Receive As** nel database di cassette postali locali in cui si trovano le cassette postali dell'utente.</span><span class="sxs-lookup"><span data-stu-id="22a8f-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="22a8f-p114">**Disabilitare la messaggistica unificata.** Se le cassette postali locali di cui si sta eseguendo la migrazione sono abilitate per la messaggistica unificata, è necessario disabilitare la messaggistica stessa prima di eseguire la migrazione. È possibile quindi riabilitare la messaggistica unificata al termine della migrazione.</span><span class="sxs-lookup"><span data-stu-id="22a8f-p114">**Disable Unified Messaging.** If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them. You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="22a8f-156">**Gruppi di sicurezza e delegati** Il servizio di migrazione della posta elettronica non è in grado di rilevare se i gruppi di Active Directory locali sono gruppi di sicurezza o meno, quindi non può effettuare il provisioning di gruppi migrati come gruppi di sicurezza in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="22a8f-157">Se si desidera avere gruppi di sicurezza nel tenant di Microsoft 365, è innanzitutto necessario effettuare il provisioning di un gruppo di sicurezza vuoto abilitato alla posta elettronica nel tenant di Microsoft 365 prima di avviare la migrazione completa.</span><span class="sxs-lookup"><span data-stu-id="22a8f-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="22a8f-158">Inoltre, questo metodo di migrazione consente di spostare solo le cassette postali, gli utenti di posta, i contatti di posta e gruppi abilitati alla posta.</span><span class="sxs-lookup"><span data-stu-id="22a8f-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="22a8f-159">Se un altro oggetto di Active Directory, ad esempio un utente che non viene migrato in Microsoft 365, viene assegnato come manager o delegato a un oggetto di cui viene eseguita la migrazione, deve essere rimosso dall'oggetto prima di eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="22a8f-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="22a8f-160">Passaggio 2: creare un endpoint di migrazione</span><span class="sxs-lookup"><span data-stu-id="22a8f-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="22a8f-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="22a8f-162">Per eseguire correttamente la migrazione della posta elettronica, Microsoft 365 deve connettersi e comunicare con il sistema di posta elettronica di origine.</span><span class="sxs-lookup"><span data-stu-id="22a8f-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="22a8f-163">A tale scopo, Microsoft 365 usa un endpoint di migrazione.</span><span class="sxs-lookup"><span data-stu-id="22a8f-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="22a8f-164">Per creare un endpoint di migrazione di Outlook via Internet per una migrazione completa, è necessario innanzitutto [connettersi a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="22a8f-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="22a8f-165">Per un elenco completo dei comandi di migrazione, vedere [Cmdlet di spostamento e migrazione](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="22a8f-165">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="22a8f-166">In PowerShell di Exchange Online, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a8f-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="22a8f-167">Nell'esempio viene utilizzato il cmdlet [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) per ottenere e verificare le impostazioni di connessione al server di Exchange locale. In seguito, tali impostazioni vengono utilizzate per creare l'endpoint di migrazione denominato "CutoverEndpoint".</span><span class="sxs-lookup"><span data-stu-id="22a8f-167">The example uses the [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="22a8f-p117">Il cmdlet **New-MigrationEndpoint** può essere utilizzato per specificare un database per il servizio da utilizzare tramite l'opzione **-TargetDatabase**. In caso contrario, un database viene assegnato in modo casuale dal sito di Active Directory Federation Services (ADFS) 2.0 in cui si trova la cassetta postale di gestione.</span><span class="sxs-lookup"><span data-stu-id="22a8f-p117">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="22a8f-170">Verificare che il passaggio di migrazione sia avvenuto correttamente</span><span class="sxs-lookup"><span data-stu-id="22a8f-170">Verify it worked</span></span>

<span data-ttu-id="22a8f-171">In PowerShell di Exchange Online, eseguire il comando riportato di seguito per visualizzare le informazioni sull'endpoint di migrazione "CutoverEndpoint":</span><span class="sxs-lookup"><span data-stu-id="22a8f-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="22a8f-172">Passaggio 3: creare il batch di migrazione completa</span><span class="sxs-lookup"><span data-stu-id="22a8f-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="22a8f-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="22a8f-p118">È possibile utilizzare il cmdlet **New-MigrationBatch** in PowerShell di Exchange Online per creare un batch di migrazione per una migrazione completa. È possibile creare un batch di migrazione e avviarlo automaticamente includendo il parametro _AutoStart_. In alternativa, è possibile creare il batch di migrazione, per poi avviarlo utilizzando il cmdlet **Start-MigrationBatch**. In questo esempio viene creato un batch di migrazione denominato "CutoverBatch" e viene utilizzato l'endpoint di migrazione creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="22a8f-p118">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="22a8f-p119">In questo esempio viene inoltre creato un batch di migrazione denominato "CutoverBatch" e viene utilizzato l'endpoint di migrazione creato nel passaggio precedente. Poiché il parametro  _AutoStart_ non è incluso, il batch di migrazione deve essere avviato manualmente nel dashboard di migrazione oppure utilizzando il cmdlet **Start-MigrationBatch**. Come illustrato in precedenza, può esistere solo un batch di migrazione completa alla volta.</span><span class="sxs-lookup"><span data-stu-id="22a8f-p119">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="22a8f-181">Verificare che il passaggio di migrazione sia avvenuto correttamente</span><span class="sxs-lookup"><span data-stu-id="22a8f-181">Verify it worked</span></span>

<span data-ttu-id="22a8f-182">Per verificare che sia stato creato correttamente un batch di migrazione per una migrazione completa, eseguire il seguente comando in PowerShell di Exchange Online per visualizzare informazioni sul nuovo batch di migrazione:</span><span class="sxs-lookup"><span data-stu-id="22a8f-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="22a8f-183">Passaggio 4: avviare il batch di migrazione completa</span><span class="sxs-lookup"><span data-stu-id="22a8f-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="22a8f-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="22a8f-p120">Per avviare il batch di migrazione in PowerShell di Exchange Online, eseguire il comando riportato di seguito. In tal modo verrà creato un batch di migrazione denominato "CutoverBatch".</span><span class="sxs-lookup"><span data-stu-id="22a8f-p120">To start the migration batch in Exchange Online PowerShell, run the following command. This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="22a8f-187">Verificare che il passaggio di migrazione sia avvenuto correttamente</span><span class="sxs-lookup"><span data-stu-id="22a8f-187">Verify it worked</span></span>

<span data-ttu-id="22a8f-p121">Se un batch di migrazione è avviato correttamente, il relativo stato sul dashboard di migrazione viene indicato come Sincronizzazione in corso. Per verificare che sia stato avviato correttamente un batch di migrazione tramite PowerShell di Exchange Online, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="22a8f-p121">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing. To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="22a8f-190">Passaggio 5: Instradare la posta elettronica a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22a8f-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="22a8f-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="22a8f-192">I sistemi di posta elettronica utilizzano un record DNS denominato record MX per individuare dove recapitare i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="22a8f-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="22a8f-193">Durante il processo di migrazione della posta elettronica, il record MX fa riferimento al sistema di posta elettronica di origine.</span><span class="sxs-lookup"><span data-stu-id="22a8f-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="22a8f-194">Ora che la migrazione della posta elettronica a Microsoft 365 è stata completata, è il momento di puntare il record MX a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="22a8f-195">In questo modo si garantisce che la posta elettronica sia recapitata alle cassette postali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="22a8f-196">Spostando il record MX, è inoltre possibile disattivare il sistema di posta elettronica precedente al momento più opportuno.</span><span class="sxs-lookup"><span data-stu-id="22a8f-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="22a8f-197">Per molti provider DNS, sono disponibili istruzioni specifiche per modificare il record MX.</span><span class="sxs-lookup"><span data-stu-id="22a8f-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="22a8f-198">Se il proprio provider DNS non è incluso o se si preferisce ottenere indicazioni generali, vedere le [istruzioni generali sui record MX](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).</span><span class="sxs-lookup"><span data-stu-id="22a8f-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="22a8f-p124">È possibile che i sistemi di posta elettronica dei propri clienti e partner impieghino fino a 72 ore per riconoscere il record MX modificato. Attendere almeno 72 ore prima di procedere con l'attività successiva: [Passaggio 6: eliminare il batch di migrazione completa](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="22a8f-p124">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="22a8f-201">Passaggio 6: eliminare il batch di migrazione completa</span><span class="sxs-lookup"><span data-stu-id="22a8f-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="22a8f-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="22a8f-203">Dopo aver modificato il record MX e aver verificato che tutti i messaggi di posta elettronica vengano instradati alle cassette postali di Microsoft 365, informare gli utenti che la posta verrà inviata a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="22a8f-204">Dopo questa operazione, è possibile eliminare il batch di migrazione completa.</span><span class="sxs-lookup"><span data-stu-id="22a8f-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="22a8f-205">Verificare le seguenti condizioni prima di eliminare il batch di migrazione.</span><span class="sxs-lookup"><span data-stu-id="22a8f-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="22a8f-206">Tutti gli utenti utilizzano le cassette postali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="22a8f-207">Dopo l'eliminazione del batch, la posta inviata alle cassette postali nel Exchange Server locale non viene copiata nelle cassette postali di Microsoft 365 corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="22a8f-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="22a8f-208">Le cassette postali di Microsoft 365 sono state sincronizzate almeno una volta dopo l'invio diretto della posta.</span><span class="sxs-lookup"><span data-stu-id="22a8f-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="22a8f-209">A tale scopo, assicurarsi che il valore nella casella Data ultima sincronizzazione per il batch di migrazione sia più recente rispetto all'avvio del routing della posta direttamente alle cassette postali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="22a8f-210">Per eliminare il batch di migrazione "CutoverBatch" in PowerShell di Exchange Online, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="22a8f-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="22a8f-211">Sezione 7: assegnare licenze utente</span><span class="sxs-lookup"><span data-stu-id="22a8f-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="22a8f-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="22a8f-213">**Attivare gli account utente di Microsoft 365 per gli account migrati assegnando licenze.**</span><span class="sxs-lookup"><span data-stu-id="22a8f-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="22a8f-214">Se non si assegna una licenza, la cassetta postale viene disabilitata al termine del periodo di prova (30 giorni).</span><span class="sxs-lookup"><span data-stu-id="22a8f-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="22a8f-215">Per assegnare una licenza nell'interfaccia di amministrazione di Microsoft 365, vedere Assegnare o [annullare l'assegnazione delle licenze.](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="22a8f-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="22a8f-216">Passaggio 8: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="22a8f-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="22a8f-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="22a8f-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="22a8f-218">**Creare un record DNS di individuazione automatica affinché gli utenti possano accedere facilmente alle proprie cassette postali.**</span><span class="sxs-lookup"><span data-stu-id="22a8f-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="22a8f-219">Dopo aver eseguito la migrazione di tutte le cassette postali locali a Microsoft 365, è possibile configurare un record DNS di individuazione automatica per l'organizzazione di Microsoft 365 per consentire agli utenti di connettersi facilmente alle nuove cassette postali di Microsoft 365 con Outlook e client mobili.</span><span class="sxs-lookup"><span data-stu-id="22a8f-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="22a8f-220">Questo nuovo record DNS di individuazione automatica deve usare lo stesso spazio dei nomi utilizzato per l'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a8f-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="22a8f-221">Ad esempio, se lo spazio dei nomi basato su cloud è cloud.contoso.com, il record DNS di individuazione automatica che deve essere creato è autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="22a8f-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="22a8f-222">Se si mantiene il Exchange Server, è inoltre necessario assicurarsi che il record CNAME DNS di individuazione automatica punti a Microsoft 365 nel DNS interno ed esterno dopo la migrazione, in modo che il client Outlook si connetta alla cassetta postale corretta.</span><span class="sxs-lookup"><span data-stu-id="22a8f-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="22a8f-223">In Exchange 2007, Exchange 2010 e Exchange 2013 è inoltre necessario impostare  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` su `Null`.</span><span class="sxs-lookup"><span data-stu-id="22a8f-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="22a8f-224">Microsoft 365 utilizza un record CNAME per implementare il servizio di individuazione automatica per Outlook e i client mobili.</span><span class="sxs-lookup"><span data-stu-id="22a8f-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="22a8f-225">Il record CNAME di individuazione automatica deve includere le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="22a8f-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="22a8f-226">**Alias:** individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="22a8f-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="22a8f-227">**Destinazione:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="22a8f-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="22a8f-228">Per ulteriori informazioni, vedere [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="22a8f-228">For more information, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="22a8f-229">**Rimuovere i server di Exchange locali.**</span><span class="sxs-lookup"><span data-stu-id="22a8f-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="22a8f-230">Dopo aver verificato che tutti i messaggi di posta elettronica vengono instradati direttamente alle cassette postali di Microsoft 365 e non è più necessario mantenere l'organizzazione di posta elettronica locale o non si prevede di implementare una soluzione Single Sign-on (SSO), è possibile disinstallare Exchange dai server e rimuovere l'organizzazione di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="22a8f-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="22a8f-231">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a8f-231">For more information, see the following:</span></span>

  - <span data-ttu-id="22a8f-232">[Modifica o eliminazione di Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="22a8f-232">[Modify or Remove Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span></span>

  - <span data-ttu-id="22a8f-233">[Come rimuovere un'organizzazione di Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="22a8f-233">[How to Remove an Exchange 2007 Organization](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span></span>

  - <span data-ttu-id="22a8f-234">[Disinstallazione di Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="22a8f-234">[How to Uninstall Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span></span>