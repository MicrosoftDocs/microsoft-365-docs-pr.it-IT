---
title: Migrazione delle cassette postali tra tenant
description: Come spostare le cassette postali tra Microsoft 365 o Office 365 tenant.
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
ms.openlocfilehash: f9a4b7679a33d6722336ee5412e4992389ba915f
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694414"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="024ec-103">Migrazione delle cassette postali tra tenant (anteprima)</span><span class="sxs-lookup"><span data-stu-id="024ec-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="024ec-104">In precedenza, quando un tenant di Exchange Online doveva spostare le cassette postali in un altro tenant nello stesso servizio Exchange Online, doveva eseguire l'offboard completo in locale e quindi eseguire l'onboardboard in un nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="024ec-105">Con la nuova funzionalità di migrazione delle cassette postali tra tenant, gli amministratori tenant nei tenant di origine e di destinazione possono spostare le cassette postali tra i tenant con dipendenze minime dell'infrastruttura nei sistemi locali.</span><span class="sxs-lookup"><span data-stu-id="024ec-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="024ec-106">In questo modo viene rimossa la necessità di eseguire l'offboard e l'onboard delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="024ec-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="024ec-107">In genere, durante le fusioni o le cessioni, è necessaria la possibilità di spostare utenti e contenuti in un nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="024ec-108">Quando l'amministratore tenant di destinazione esegue lo spostamento, viene chiamato spostamento pull, in modo analogo alle migrazioni di onboarding in locale e cloud.</span><span class="sxs-lookup"><span data-stu-id="024ec-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="024ec-109">Gli spostamenti delle cassette postali Exchange tra tenant sono completamente self-service dagli amministratori tenant, utilizzando interfacce note che possono essere implementate tramite script nei flussi di lavoro più grandi necessari per la transizione degli utenti alla nuova organizzazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="024ec-110">Gli amministratori possono utilizzare il cmdlet, disponibile tramite il ruolo di gestione Sposta cassette `New-MigrationBatch` postali, per eseguire spostamenti tra tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="024ec-111">Il processo di spostamento include i controlli di autorizzazione del tenant durante la sincronizzazione e la finalizzazione delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="024ec-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="024ec-112">Gli utenti che effettuano la migrazione devono essere presenti nel sistema Exchange Online tenant di destinazione come MailUsers, contrassegnati con attributi specifici per abilitare gli spostamenti tra tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="024ec-113">Il sistema non riuscirà gli spostamenti per gli utenti che non sono correttamente impostati nel tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="024ec-114">Una volta completati gli spostamenti, la cassetta postale del sistema di origine viene convertita in MailUser e targetAddress (visualizzato come ExternalEmailAddress in Exchange) viene contrassegnato con l'indirizzo di routing al tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="024ec-115">Questo processo lascia l'legacy MailUser nel tenant di origine e consente un periodo di coesistenza e routing della posta.</span><span class="sxs-lookup"><span data-stu-id="024ec-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="024ec-116">Quando i processi aziendali lo consentono, il tenant di origine può rimuovere l'oggetto MailUser di origine o convertirlo in un contatto di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="024ec-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="024ec-117">Le migrazioni Exchange cassette postali tra tenant sono supportate solo per i tenant ibridi o cloud o per qualsiasi combinazione di queste due.</span><span class="sxs-lookup"><span data-stu-id="024ec-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="024ec-118">In questo articolo viene descritto il processo per gli spostamenti di cassette postali tra tenant e vengono fornite indicazioni su come preparare i tenant di origine e di destinazione per lo spostamento del contenuto.</span><span class="sxs-lookup"><span data-stu-id="024ec-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="024ec-119">Preparazione dei tenant di origine e di destinazione</span><span class="sxs-lookup"><span data-stu-id="024ec-119">Preparing source and target tenants</span></span>

<span data-ttu-id="024ec-120">La funzionalità di migrazione delle cassette Exchange tra tenant richiede l'autorizzazione e l'ambito per le migrazioni tra tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="024ec-121">Usando l'applicazione Azure Enterprise e le soluzioni di archiviazione dell'insieme di credenziali delle chiavi, gli amministratori tenant sono ora in grado di gestire sia l'autorizzazione che l'ambito delle migrazioni delle cassette postali di Exchange Online da un tenant all'altro.</span><span class="sxs-lookup"><span data-stu-id="024ec-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="024ec-122">Gli spostamenti di cassette postali tra tenant supportano un modello di invito e consenso per stabilire un'applicazione Azure Active Directory (Azure AD) utilizzata per l'autenticazione tra una coppia di tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="024ec-123">Sono inoltre necessari componenti aggiuntivi, ad esempio una relazione organizzativa e un endpoint di migrazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="024ec-124">In questa sezione non sono inclusi i passaggi specifici necessari per preparare gli oggetti utente MailUser nella directory di destinazione, né il comando di esempio per inviare un batch di migrazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="024ec-125">Per queste [informazioni, vedere Preparare gli oggetti utente](#prepare-target-user-objects-for-migration) di destinazione per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="024ec-126">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="024ec-126">Prerequisites</span></span>

<span data-ttu-id="024ec-127">La funzionalità di spostamento delle cassette postali tra tenant richiede [Azure Key Vault](/azure/key-vault/basic-concepts) per stabilire un'applicazione Azure specifica della coppia di tenant per archiviare e accedere in modo sicuro al certificato/segreto utilizzato per autenticare e autorizzare la migrazione delle cassette postali da un tenant all'altro, rimuovendo eventuali requisiti per condividere certificati/segreti tra tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="024ec-128">Prima di iniziare, assicurarsi di disporre delle autorizzazioni necessarie per eseguire gli script di distribuzione per configurare Azure Key Vault, Move Mailbox application, EXO Migration Endpoint e exO Organization Relationship.</span><span class="sxs-lookup"><span data-stu-id="024ec-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="024ec-129">In genere, l'amministratore globale dispone dell'autorizzazione per eseguire tutti i passaggi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="024ec-130">Inoltre, i gruppi di sicurezza abilitati alla posta elettronica nel tenant di origine sono necessari prima di eseguire l'installazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="024ec-131">Questi gruppi vengono utilizzati per l'ambito dell'elenco delle cassette postali che possono essere spostate dal tenant di origine (o talvolta denominato risorsa) al tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="024ec-132">In questo modo l'amministratore del tenant di origine può limitare o limitare l'ambito del set specifico di cassette postali che devono essere spostate, impedendo la migrazione di utenti non intenzionali.</span><span class="sxs-lookup"><span data-stu-id="024ec-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="024ec-133">I gruppi annidati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="024ec-133">Nested groups are not supported.</span></span>

<span data-ttu-id="024ec-134">Sarà inoltre necessario comunicare con l'azienda partner attendibile (con cui verranno trasferite le cassette postali) per ottenere il proprio ID tenant Microsoft 365 attendibile.</span><span class="sxs-lookup"><span data-stu-id="024ec-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="024ec-135">Questo ID tenant viene utilizzato nel campo Relazione `DomainName` organizzativa.</span><span class="sxs-lookup"><span data-stu-id="024ec-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="024ec-136">Per ottenere l'ID tenant di una sottoscrizione, accedere all'Microsoft 365 di amministrazione e passare a [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="024ec-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="024ec-137">Fare clic sull'icona di copia per la proprietà ID tenant per copiarla negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="024ec-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="024ec-138">Ecco come funziona il processo.</span><span class="sxs-lookup"><span data-stu-id="024ec-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparazione del tenant per la migrazione delle cassette postali.":::

<span data-ttu-id="024ec-140">[Vedi una versione più grande di questa immagine.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="024ec-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="024ec-141">Preparare i tenant</span><span class="sxs-lookup"><span data-stu-id="024ec-141">Prepare tenants</span></span>

<span data-ttu-id="024ec-142">A livello generale, durante l'esecuzione degli script di installazione vengono eseguite le azioni di configurazione seguenti.</span><span class="sxs-lookup"><span data-stu-id="024ec-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="024ec-143">Preparare il tenant di destinazione:</span><span class="sxs-lookup"><span data-stu-id="024ec-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="024ec-144">Se non viene fornito un gruppo di risorse di Azure esistente, ne viene creato uno nuovo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="024ec-145">Se non viene fornito un insieme di credenziali delle chiavi esistente, ne viene creato uno nuovo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="024ec-146">Viene creato un nuovo criterio di accesso per l'Office 365 Exchange Online di migrazione delle cassette postali (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="024ec-147">Viene creato un nuovo certificato (o uno esistente, se specificato) per contenere il segreto per l'applicazione di migrazione (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="024ec-148">Viene creata una nuova applicazione Azure AD (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="024ec-149">Il certificato/segreto viene caricato nell'applicazione di migrazione (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="024ec-150">Le autorizzazioni di migrazione delle cassette postali vengono assegnate all'applicazione (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="024ec-151">Lo script di distribuzione viene sospeso finché l'amministratore di destinazione non acconsente alla propria applicazione (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="024ec-152">L'amministratore tenant di destinazione acconsente alle autorizzazioni concesse all'applicazione (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="024ec-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="024ec-153">Viene creata una relazione organizzativa con il tenant di destinazione (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="024ec-154">Viene creato un endpoint di migrazione per il pull delle cassette postali nel tenant di destinazione (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="024ec-155">Preparare il tenant di origine:</span><span class="sxs-lookup"><span data-stu-id="024ec-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="024ec-156">L'amministratore del tenant di origine accetta il consenso all'invito all'applicazione di migrazione delle cassette postali dal tenant di destinazione (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="024ec-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="024ec-157">L'amministratore del tenant di origine crea un gruppo di sicurezza abilitato alla posta elettronica nel tenant per contenere l'elenco delle cassette postali che possono essere spostate dall'applicazione di migrazione (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="024ec-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="024ec-158">Viene creata una relazione organizzativa con il tenant di destinazione che specifica che l'applicazione di migrazione delle cassette postali deve essere utilizzata per la verifica OAuth per accettare la richiesta di spostamento (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="024ec-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="024ec-159">Istruzioni dettagliate per l'amministratore tenant di destinazione</span><span class="sxs-lookup"><span data-stu-id="024ec-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="024ec-160">Scaricare lo script SetupCrossTenantRelationshipForTargetTenant.ps1 per la configurazione del tenant di destinazione [dall'GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="024ec-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="024ec-161">Salvare lo script (SetupCrossTenantRelationshipForTargetTenant.ps1) nel computer da cui verrà eseguito lo script.</span><span class="sxs-lookup"><span data-stu-id="024ec-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="024ec-162">Creare una connessione remota di PowerShell al tenant Exchange Online destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="024ec-163">Anche in questo caso, assicurarsi di disporre delle autorizzazioni necessarie per eseguire gli script di distribuzione per configurare l'archiviazione e il certificato dell'insieme di credenziali delle chiavi di Azure, l'applicazione Sposta cassetta postale, l'endpoint di migrazione EXO e la relazione dell'organizzazione EXO.</span><span class="sxs-lookup"><span data-stu-id="024ec-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="024ec-164">Modificare la directory della cartella dei file nel percorso dello script o verificare che lo script sia attualmente salvato nel percorso attualmente nella sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="024ec-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="024ec-165">Eseguire lo script con i parametri e i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="024ec-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="024ec-166">Parametro</span><span class="sxs-lookup"><span data-stu-id="024ec-166">Parameter</span></span> | <span data-ttu-id="024ec-167">Valore</span><span class="sxs-lookup"><span data-stu-id="024ec-167">Value</span></span> | <span data-ttu-id="024ec-168">Obbligatorio o facoltativo</span><span class="sxs-lookup"><span data-stu-id="024ec-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="024ec-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="024ec-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="024ec-170">Dominio tenant di destinazione, ad esempio fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="024ec-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="024ec-171">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-171">Required</span></span> |
    | <span data-ttu-id="024ec-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="024ec-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="024ec-173">Dominio tenant di origine, ad esempio contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="024ec-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="024ec-174">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-174">Required</span></span> |
    | <span data-ttu-id="024ec-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="024ec-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="024ec-176">Indirizzo di posta elettronica dell'amministratore tenant di origine.</span><span class="sxs-lookup"><span data-stu-id="024ec-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="024ec-177">Questo è l'amministratore tenant di origine che acconsentirà all'utilizzo dell'applicazione di migrazione delle cassette postali inviata dall'amministratore di destinazione. Questo è l'amministratore che riceverà l'invito tramite posta elettronica per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="024ec-178">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-178">Required</span></span> |
    | <span data-ttu-id="024ec-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="024ec-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="024ec-180">ID organizzazione tenant di origine (GUID).</span><span class="sxs-lookup"><span data-stu-id="024ec-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="024ec-181">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-181">Required</span></span> |
    | <span data-ttu-id="024ec-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="024ec-182">-SubscriptionId</span></span>                             | <span data-ttu-id="024ec-183">Sottoscrizione di Azure da usare per la creazione di risorse.</span><span class="sxs-lookup"><span data-stu-id="024ec-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="024ec-184">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-184">Required</span></span> |
    | <span data-ttu-id="024ec-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="024ec-185">-ResourceGroup</span></span>                              | <span data-ttu-id="024ec-186">Nome del gruppo di risorse di Azure che contiene o conterrà l'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="024ec-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="024ec-187">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-187">Required</span></span> |
    | <span data-ttu-id="024ec-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="024ec-188">-KeyVaultName</span></span>                               | <span data-ttu-id="024ec-189">Istanza di Azure Key Vault che archivierà il certificato/segreto dell'applicazione di migrazione delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="024ec-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="024ec-190">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-190">Required</span></span> |
    | <span data-ttu-id="024ec-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="024ec-191">-CertificateName</span></span>                            | <span data-ttu-id="024ec-192">Nome del certificato durante la generazione o la ricerca del certificato nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="024ec-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="024ec-193">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-193">Required</span></span> |
    | <span data-ttu-id="024ec-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="024ec-194">-CertificateSubject</span></span>                         | <span data-ttu-id="024ec-195">Nome del soggetto del certificato dell'insieme di credenziali delle chiavi di Azure, ad esempio CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="024ec-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="024ec-196">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-196">Required</span></span> |
    | <span data-ttu-id="024ec-197">-AzureResourceLocation</span><span class="sxs-lookup"><span data-stu-id="024ec-197">-AzureResourceLocation</span></span>                      | <span data-ttu-id="024ec-198">Percorso del gruppo di risorse di Azure e dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="024ec-198">The location of the Azure resource group and key vault.</span></span> | <span data-ttu-id="024ec-199">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-199">Required</span></span> |
    | <span data-ttu-id="024ec-200">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="024ec-200">-ExistingApplicationId</span></span>                      | <span data-ttu-id="024ec-201">Applicazione di migrazione della posta da utilizzare se ne è già stata creata una.</span><span class="sxs-lookup"><span data-stu-id="024ec-201">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="024ec-202">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="024ec-202">Optional</span></span> |
    | <span data-ttu-id="024ec-203">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="024ec-203">-AzureAppPermissions</span></span>                        | <span data-ttu-id="024ec-204">Le autorizzazioni necessarie per l'applicazione di migrazione delle cassette postali, ad esempio Exchange o MSGraph (Exchange per lo spostamento delle cassette postali, MSGraph per l'utilizzo di questa applicazione per inviare un invito di collegamento di consenso al tenant di risorse).</span><span class="sxs-lookup"><span data-stu-id="024ec-204">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="024ec-205">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="024ec-205">Required</span></span> |
    | <span data-ttu-id="024ec-206">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="024ec-206">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="024ec-207">Parametro per l'utilizzo dell'applicazione creata per la migrazione da utilizzare per l'invio dell'invito al collegamento di consenso all'amministratore del tenant di origine. Se non presente, verranno richieste le credenziali dell'amministratore di destinazione per connettersi a Azure Invitation Manager e inviare l'invito come amministratore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-207">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="024ec-208">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="024ec-208">Optional</span></span> |
    | <span data-ttu-id="024ec-209">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="024ec-209">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="024ec-210">Account di archiviazione in cui verranno archiviati i log di controllo di Key Vault.</span><span class="sxs-lookup"><span data-stu-id="024ec-210">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="024ec-211">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="024ec-211">Optional</span></span> |
    | <span data-ttu-id="024ec-212">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="024ec-212">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="024ec-213">Gruppo di risorse che contiene l'account di archiviazione per l'archiviazione dei log di controllo dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="024ec-213">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="024ec-214">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="024ec-214">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="024ec-215">Assicurarsi di aver installato il modulo Azure AD PowerShell prima di eseguire gli script.</span><span class="sxs-lookup"><span data-stu-id="024ec-215">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="024ec-216">Fare riferimento a ![ qui per la procedura di ](/powershell/azure/install-az-ps?view=azps-5.1.0) installazione</span><span class="sxs-lookup"><span data-stu-id="024ec-216">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="024ec-217">Lo script verrà sospeso e verrà richiesto di accettare o acconsentire all'applicazione Exchange cassetta postale creata durante questo processo.</span><span class="sxs-lookup"><span data-stu-id="024ec-217">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="024ec-218">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-218">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. <span data-ttu-id="024ec-219">Nella sessione remota di PowerShell verrà visualizzato un URL.</span><span class="sxs-lookup"><span data-stu-id="024ec-219">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="024ec-220">Copiare il collegamento fornito per il consenso del tenant e incollarlo in un Web browser.</span><span class="sxs-lookup"><span data-stu-id="024ec-220">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="024ec-221">Accedi con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="024ec-221">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="024ec-222">Quando viene visualizzata la schermata seguente, selezionare **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="024ec-222">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Finestra di dialogo Accetta autorizzazioni":::

9. <span data-ttu-id="024ec-224">Tornare alla sessione remota di PowerShell e premere INVIO per procedere.</span><span class="sxs-lookup"><span data-stu-id="024ec-224">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="024ec-225">Lo script configurerà gli oggetti di installazione rimanenti.</span><span class="sxs-lookup"><span data-stu-id="024ec-225">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="024ec-226">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-226">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="024ec-227">La configurazione dell'amministratore di destinazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="024ec-227">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="024ec-228">Istruzioni dettagliate per l'amministratore tenant di origine</span><span class="sxs-lookup"><span data-stu-id="024ec-228">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="024ec-229">Accedi alla cassetta postale come -ResourceTenantAdminEmail specificato dall'amministratore di destinazione durante la configurazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-229">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="024ec-230">Trova l'invito tramite posta elettronica dal tenant di destinazione e quindi seleziona il **pulsante Informazioni di base** posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="024ec-230">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Finestra di dialogo Sei stato invitato":::

2. <span data-ttu-id="024ec-232">Selezionare **Accetta** per accettare l'invito.</span><span class="sxs-lookup"><span data-stu-id="024ec-232">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Finestra di dialogo per accettare le autorizzazioni":::

   > [!NOTE]
   > <span data-ttu-id="024ec-234">Se non si ottiene questo messaggio di posta elettronica o non è possibile trovarlo, all'amministratore tenant di destinazione è stato fornito un URL diretto che può essere assegnato all'utente per accettare l'invito.</span><span class="sxs-lookup"><span data-stu-id="024ec-234">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="024ec-235">L'URL deve essere nella trascrizione della sessione remota di PowerShell dell'amministratore tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-235">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="024ec-236">Nell'interfaccia di amministrazione di Microsoft 365 o in una sessione remota di PowerShell, creare uno o più gruppi di sicurezza abilitati alla posta elettronica per controllare l'elenco delle cassette postali consentite dal tenant di destinazione per il pull (spostamento) dal tenant di origine al tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-236">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="024ec-237">Non è necessario popolare questo gruppo in anticipo, ma è necessario fornire almeno un gruppo per eseguire la procedura di installazione (script).</span><span class="sxs-lookup"><span data-stu-id="024ec-237">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="024ec-238">I gruppi nest non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="024ec-238">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="024ec-239">Scaricare lo script SetupCrossTenantRelationshipForResourceTenant.ps1 per la configurazione del tenant di origine dal repository GitHub repository qui: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="024ec-239">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="024ec-240">Creare una connessione remota di PowerShell al tenant di origine con le autorizzazioni Exchange amministratore.</span><span class="sxs-lookup"><span data-stu-id="024ec-240">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="024ec-241">Le autorizzazioni di amministratore globale non sono necessarie per configurare il tenant di origine, ma solo il tenant di destinazione a causa del processo di creazione dell'applicazione Azure.</span><span class="sxs-lookup"><span data-stu-id="024ec-241">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="024ec-242">Modificare la directory nel percorso dello script o verificare che lo script sia attualmente salvato nel percorso attualmente nella sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="024ec-242">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="024ec-243">Eseguire lo script con i parametri e i valori obbligatori seguenti.</span><span class="sxs-lookup"><span data-stu-id="024ec-243">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="024ec-244">Parametro</span><span class="sxs-lookup"><span data-stu-id="024ec-244">Parameter</span></span> | <span data-ttu-id="024ec-245">Valore</span><span class="sxs-lookup"><span data-stu-id="024ec-245">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="024ec-246">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="024ec-246">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="024ec-247">Gruppo di sicurezza abilitato alla posta creato dal tenant di origine per le identità/cassette postali nell'ambito della migrazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-247">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="024ec-248">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="024ec-248">-ResourceTenantDomain</span></span> | <span data-ttu-id="024ec-249">Nome di dominio tenant di origine, ad esempio contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="024ec-249">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="024ec-250">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="024ec-250">-ApplicationId</span></span> | <span data-ttu-id="024ec-251">ID applicazione Azure (GUID) dell'applicazione usata per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-251">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="024ec-252">ID applicazione disponibile tramite il portale di Azure (Azure AD, Enterprise Applicazioni, nome dell'app, ID applicazione) o incluso nel messaggio di posta elettronica di invito.</span><span class="sxs-lookup"><span data-stu-id="024ec-252">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="024ec-253">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="024ec-253">-TargetTenantDomain</span></span> | <span data-ttu-id="024ec-254">Nome di dominio tenant di destinazione, ad esempio fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="024ec-254">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="024ec-255">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="024ec-255">-TargetTenantId</span></span> | <span data-ttu-id="024ec-256">ID tenant del tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-256">Tenant ID of the target tenant.</span></span> <span data-ttu-id="024ec-257">Ad esempio, l'ID tenant di Azure AD di contoso \. onmicrosoft.com tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-257">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="024ec-258">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-258">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="024ec-259">La configurazione dell'amministratore di origine è stata completata.</span><span class="sxs-lookup"><span data-stu-id="024ec-259">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="024ec-260">Verificare l'installazione</span><span class="sxs-lookup"><span data-stu-id="024ec-260">Verify setup</span></span>

<span data-ttu-id="024ec-261">Verificare che le relazioni dell'organizzazione nei tenant di origine e di destinazione e nell'endpoint di migrazione nella destinazione siano state create correttamente.</span><span class="sxs-lookup"><span data-stu-id="024ec-261">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="024ec-262">Tenant di destinazione</span><span class="sxs-lookup"><span data-stu-id="024ec-262">Target tenant</span></span>

<span data-ttu-id="024ec-263">**Relazione organizzativa**</span><span class="sxs-lookup"><span data-stu-id="024ec-263">**Organization relationship**</span></span>

<span data-ttu-id="024ec-264">Verificare che l'oggetto relazione organizzativa sia stato creato e configurato con questo comando.</span><span class="sxs-lookup"><span data-stu-id="024ec-264">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="024ec-265">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="024ec-265">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="024ec-266">**Endpoint di migrazione**</span><span class="sxs-lookup"><span data-stu-id="024ec-266">**Migration endpoint**</span></span>

<span data-ttu-id="024ec-267">Verificare che l'oggetto endpoint di migrazione sia stato creato e configurato con questo comando.</span><span class="sxs-lookup"><span data-stu-id="024ec-267">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="024ec-268">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-268">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="024ec-269">Tenant di origine</span><span class="sxs-lookup"><span data-stu-id="024ec-269">Source tenant</span></span>

<span data-ttu-id="024ec-270">**Relazione organizzativa**</span><span class="sxs-lookup"><span data-stu-id="024ec-270">**Organization relationship**</span></span>

<span data-ttu-id="024ec-271">Verificare che l'oggetto relazione organizzativa sia stato creato e configurato con questo comando.</span><span class="sxs-lookup"><span data-stu-id="024ec-271">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="024ec-272">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-272">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="024ec-273">Verificare lo script di installazione</span><span class="sxs-lookup"><span data-stu-id="024ec-273">Verify Setup Script</span></span>

<span data-ttu-id="024ec-274">Se si ricevono errori durante la configurazione dei tenant di origine o di [](https://github.com/microsoft/cross-tenant/releases/tag/Preview) destinazione, è possibile eseguire lo script VerifySetup.ps1 in GitHub ed esaminare l'output.</span><span class="sxs-lookup"><span data-stu-id="024ec-274">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="024ec-275">Ecco un esempio di esecuzione di VerifySetup.ps1 nel tenant di destinazione:</span><span class="sxs-lookup"><span data-stu-id="024ec-275">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="024ec-276">Ecco un esempio di VerifySetup.ps1 nel tenant di origine:</span><span class="sxs-lookup"><span data-stu-id="024ec-276">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="024ec-277">Spostare di nuovo le cassette postali nell'origine originale</span><span class="sxs-lookup"><span data-stu-id="024ec-277">Move mailboxes back to the original source</span></span>

<span data-ttu-id="024ec-278">Se è necessario uno spostamento di una cassetta postale nel tenant di origine originale, sarà necessario eseguire lo stesso set di passaggi e script sia nei tenant di origine che nei nuovi tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-278">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="024ec-279">L'oggetto Organization Relationship esistente verrà aggiornato o accodato, non ricreato.</span><span class="sxs-lookup"><span data-stu-id="024ec-279">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="024ec-280">Preparare gli oggetti utente di destinazione per la migrazione</span><span class="sxs-lookup"><span data-stu-id="024ec-280">Prepare target user objects for migration</span></span>

<span data-ttu-id="024ec-281">Gli utenti che effettuano la migrazione devono essere presenti nel tenant di destinazione e nel sistema Exchange Online (come MailUsers) contrassegnati con attributi specifici per abilitare gli spostamenti tra tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-281">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="024ec-282">Il sistema non riuscirà gli spostamenti per gli utenti che non sono correttamente impostati nel tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-282">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="024ec-283">Nella sezione seguente vengono dettagliati i requisiti dell'oggetto MailUser per il tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-283">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="024ec-284">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="024ec-284">Prerequisites</span></span>
  
<span data-ttu-id="024ec-285">È necessario verificare che nell'organizzazione di destinazione siano impostati gli oggetti e gli attributi seguenti.</span><span class="sxs-lookup"><span data-stu-id="024ec-285">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="024ec-286">Per qualsiasi cassetta postale che si sposta da un'organizzazione di origine, è necessario effettuare il provisioning di un oggetto MailUser nell'organizzazione di destinazione:</span><span class="sxs-lookup"><span data-stu-id="024ec-286">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="024ec-287">L'oggetto MailUser di destinazione deve disporre di questi attributi dalla cassetta postale di origine o assegnato con il nuovo oggetto User:</span><span class="sxs-lookup"><span data-stu-id="024ec-287">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="024ec-288">ExchangeGUID (flusso diretto dall'origine alla destinazione): il GUID della cassetta postale deve corrispondere.</span><span class="sxs-lookup"><span data-stu-id="024ec-288">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="024ec-289">Il processo di spostamento non procede se non è presente nell'oggetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-289">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="024ec-290">ArchiveGUID (flusso diretto dall'origine alla destinazione): il GUID di archiviazione deve corrispondere.</span><span class="sxs-lookup"><span data-stu-id="024ec-290">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="024ec-291">Il processo di spostamento non procede se non è presente nell'oggetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-291">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="024ec-292">Questa operazione è necessaria solo se la cassetta postale di origine è abilitata per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-292">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="024ec-293">LegacyExchangeDN (flusso come proxyAddress, "x500: ") - Il LegacyExchangeDN deve essere presente nella destinazione <LegacyExchangeDN> MailUser come x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="024ec-293">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="024ec-294">I processi di spostamento non procedono se non è presente nell'oggetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-294">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="024ec-295">UserPrincipalName : UPN verrà allineato all'identità NEW o alla società di destinazione dell'utente (ad esempio, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="024ec-295">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="024ec-296">Primary SMTPAddress : l'indirizzo SMTP primario verrà allineato alla nuova società dell'utente (ad esempio, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="024ec-296">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="024ec-297">TargetAddress/ExternalEmailAddress - MailUser farà riferimento alla cassetta postale corrente dell'utente ospitata nel tenant di origine (ad esempio, user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="024ec-297">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="024ec-298">Quando si assegna questo valore, verificare di disporre o anche assegnare PrimarySMTPAddress oppure questo valore imposta PrimarySMTPAddress che causerà errori di spostamento.</span><span class="sxs-lookup"><span data-stu-id="024ec-298">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="024ec-299">Non è possibile aggiungere indirizzi proxy smtp legacy dalla cassetta postale di origine a MailUser di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-299">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="024ec-300">Ad esempio, non è possibile gestire contoso.com'utente per l'utente singolo negli fabrikam.onmicrosoft.com tenant).</span><span class="sxs-lookup"><span data-stu-id="024ec-300">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="024ec-301">I domini sono associati a un solo tenant Exchange Online Azure AD.</span><span class="sxs-lookup"><span data-stu-id="024ec-301">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="024ec-302">Esempio **di oggetto** MailUser di destinazione:</span><span class="sxs-lookup"><span data-stu-id="024ec-302">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="024ec-303">Attributo</span><span class="sxs-lookup"><span data-stu-id="024ec-303">Attribute</span></span>             | <span data-ttu-id="024ec-304">Valore</span><span class="sxs-lookup"><span data-stu-id="024ec-304">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="024ec-305">Alias</span><span class="sxs-lookup"><span data-stu-id="024ec-305">Alias</span></span>                 | <span data-ttu-id="024ec-306">LaraN</span><span class="sxs-lookup"><span data-stu-id="024ec-306">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="024ec-307">RecipientType</span><span class="sxs-lookup"><span data-stu-id="024ec-307">RecipientType</span></span>         | <span data-ttu-id="024ec-308">MailUser</span><span class="sxs-lookup"><span data-stu-id="024ec-308">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="024ec-309">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="024ec-309">RecipientTypeDetails</span></span>  | <span data-ttu-id="024ec-310">MailUser</span><span class="sxs-lookup"><span data-stu-id="024ec-310">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="024ec-311">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="024ec-311">UserPrincipalName</span></span>     | <span data-ttu-id="024ec-312">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="024ec-312">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="024ec-313">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="024ec-313">PrimarySmtpAddress</span></span>    | <span data-ttu-id="024ec-314">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="024ec-314">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="024ec-315">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="024ec-315">ExternalEmailAddress</span></span>  | <span data-ttu-id="024ec-316">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="024ec-316">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="024ec-317">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="024ec-317">ExchangeGuid</span></span>          | <span data-ttu-id="024ec-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="024ec-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="024ec-319">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="024ec-319">LegacyExchangeDN</span></span>      | <span data-ttu-id="024ec-320">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="024ec-320">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="024ec-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d1900687694985035Lara</span><span class="sxs-lookup"><span data-stu-id="024ec-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="024ec-322">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="024ec-322">EmailAddresses</span></span>        | <span data-ttu-id="024ec-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="024ec-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="024ec-324">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="024ec-324">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="024ec-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="024ec-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="024ec-326">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="024ec-326">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="024ec-327">Esempio **di oggetto** Mailbox di origine:</span><span class="sxs-lookup"><span data-stu-id="024ec-327">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="024ec-328">Attributo</span><span class="sxs-lookup"><span data-stu-id="024ec-328">Attribute</span></span>             | <span data-ttu-id="024ec-329">Valore</span><span class="sxs-lookup"><span data-stu-id="024ec-329">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="024ec-330">Alias</span><span class="sxs-lookup"><span data-stu-id="024ec-330">Alias</span></span>                 | <span data-ttu-id="024ec-331">LaraN</span><span class="sxs-lookup"><span data-stu-id="024ec-331">LaraN</span></span>                                                                    |
     | <span data-ttu-id="024ec-332">RecipientType</span><span class="sxs-lookup"><span data-stu-id="024ec-332">RecipientType</span></span>         | <span data-ttu-id="024ec-333">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="024ec-333">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="024ec-334">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="024ec-334">RecipientTypeDetails</span></span>  | <span data-ttu-id="024ec-335">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="024ec-335">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="024ec-336">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="024ec-336">UserPrincipalName</span></span>     | <span data-ttu-id="024ec-337">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="024ec-337">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="024ec-338">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="024ec-338">PrimarySmtpAddress</span></span>    | <span data-ttu-id="024ec-339">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="024ec-339">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="024ec-340">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="024ec-340">ExchangeGuid</span></span>          | <span data-ttu-id="024ec-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="024ec-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="024ec-342">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="024ec-342">LegacyExchangeDN</span></span>      | <span data-ttu-id="024ec-343">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="024ec-343">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="024ec-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="024ec-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="024ec-345">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="024ec-345">EmailAddresses</span></span>        | <span data-ttu-id="024ec-346">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="024ec-346">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="024ec-347">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="024ec-347">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="024ec-348">Altri attributi possono essere inclusi in Exchange write back ibrido già.</span><span class="sxs-lookup"><span data-stu-id="024ec-348">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="024ec-349">In caso contrario, devono essere inclusi.</span><span class="sxs-lookup"><span data-stu-id="024ec-349">If not, they should be included.</span></span> 
   - <span data-ttu-id="024ec-350">msExchBlockedSendersHash - Scrive i dati dei mittenti attendibili e bloccati online dai client in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="024ec-350">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="024ec-351">msExchSafeRecipientsHash - Scrive i dati dei mittenti attendibili e bloccati online dai client in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="024ec-351">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="024ec-352">msExchSafeSendersHash: scrive i dati dei mittenti sicuri e bloccati online dai client in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="024ec-352">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="024ec-353">Se la cassetta postale di origine è in LitigationHold e la dimensione degli elementi ripristinabili della cassetta postale di origine è maggiore del valore predefinito del database (30 GB), gli spostamenti non verranno eserciti poiché la quota di destinazione è inferiore alla dimensione della cassetta postale di origine.</span><span class="sxs-lookup"><span data-stu-id="024ec-353">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="024ec-354">È possibile aggiornare l'oggetto MailUser di destinazione per la transizione dei flag della cassetta postale ELC dall'ambiente di origine alla destinazione, che attiva il sistema di destinazione per espandere la quota di MailUser a 100 GB, consentendo così lo spostamento alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-354">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="024ec-355">Queste istruzioni funzionano solo per l'identità ibrida che esegue Azure AD Connessione, poiché i comandi per l'indicatore dei flag ELC non sono esposti agli amministratori tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-355">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="024ec-356">ESEMPIO: NESSUNA GARANZIA</span><span class="sxs-lookup"><span data-stu-id="024ec-356">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="024ec-357">Questo script presuppone una connessione sia alla cassetta postale di origine (per ottenere i valori di origine) che alla destinazione di Active Directory locale (per timbrare l'oggetto ADUser).</span><span class="sxs-lookup"><span data-stu-id="024ec-357">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="024ec-358">Se nell'origine è abilitata la controversia legale o il ripristino di un singolo elemento, imposta questo valore nell'account di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-358">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="024ec-359">In questo modo le dimensioni del dumpster dell'account di destinazione verranno aumentate a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="024ec-359">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="024ec-360">I tenant di destinazione non ibridi possono modificare la quota nella cartella Elementi ripristinabili per MailUsers prima della migrazione eseguendo il comando seguente per abilitare il blocco per controversia legale sull'oggetto MailUser e aumentare la quota a 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="024ec-360">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="024ec-361">Si noti che non funzionerà per i tenant in ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="024ec-361">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="024ec-362">Gli utenti nell'organizzazione di destinazione devono disporre di una licenza con le Exchange Online appropriate applicabili per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-362">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="024ec-363">È possibile applicare una licenza prima dello spostamento di una cassetta postale, ma solo dopo che l'oggetto MailUser di destinazione è configurato correttamente con ExchangeGUID e indirizzi proxy.</span><span class="sxs-lookup"><span data-stu-id="024ec-363">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="024ec-364">L'applicazione di una licenza prima dell'applicazione di ExchangeGUID comporta il provisioning di una nuova cassetta postale nell'organizzazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-364">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="024ec-365">Quando si applica una licenza a un oggetto Mailbox o MailUser, tutti i proxyAddress di tipo SMTP vengono scrubbed per garantire che solo i domini verificati siano inclusi nella matrice Exchange EmailAddresses.</span><span class="sxs-lookup"><span data-stu-id="024ec-365">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="024ec-366">È necessario verificare che l'oggetto MailUser di destinazione non abbia un ExchangeGuid precedente che non corrisponda a Source ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="024ec-366">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="024ec-367">Ciò può verificarsi se l'utente meu di destinazione è stato precedentemente concesso in licenza per Exchange Online ed è stato effettuato il provisioning di una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="024ec-367">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="024ec-368">Se l'oggetto MailUser di destinazione è stato concesso in licenza in precedenza o aveva un ExchangeGuid che non corrisponde a Source ExchangeGuid, è necessario eseguire una pulizia del cloud MEU.</span><span class="sxs-lookup"><span data-stu-id="024ec-368">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="024ec-369">Per queste unità meU cloud, è possibile eseguire `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="024ec-369">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="024ec-370">Questo processo è irreversibile.</span><span class="sxs-lookup"><span data-stu-id="024ec-370">This process is irreversible.</span></span> <span data-ttu-id="024ec-371">Se l'oggetto dispone di una cassetta postale softDeleted, non può essere ripristinato dopo questo punto.</span><span class="sxs-lookup"><span data-stu-id="024ec-371">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="024ec-372">Una volta deselezionata, tuttavia, è possibile sincronizzare il ExchangeGuid corretto con l'oggetto di destinazione e MRS connetterà la cassetta postale di origine alla cassetta postale di destinazione appena creata.</span><span class="sxs-lookup"><span data-stu-id="024ec-372">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="024ec-373">Riferimento al blog EHLO sul nuovo parametro.</span><span class="sxs-lookup"><span data-stu-id="024ec-373">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="024ec-374">Trovare gli oggetti che in precedenza erano cassette postali utilizzando questo comando.</span><span class="sxs-lookup"><span data-stu-id="024ec-374">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="024ec-375">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-375">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="024ec-376">Cancella la cassetta postale eliminata in modo recidiva utilizzando questo comando.</span><span class="sxs-lookup"><span data-stu-id="024ec-376">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="024ec-377">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-377">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="024ec-378">Eseguire le migrazioni delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="024ec-378">Perform mailbox migrations</span></span>

<span data-ttu-id="024ec-379">Le migrazioni delle cassette Exchange tra tenant vengono inviate come batch di migrazione avviati dal tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-379">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="024ec-380">Questo è simile al modo in cui i batch di migrazione di on-boarding funzionano durante la migrazione da Exchange locale a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="024ec-380">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="024ec-381">Creare batch di migrazione</span><span class="sxs-lookup"><span data-stu-id="024ec-381">Create Migration batches</span></span>

<span data-ttu-id="024ec-382">Ecco un cmdlet batch di migrazione di esempio per avviare gli spostamenti.</span><span class="sxs-lookup"><span data-stu-id="024ec-382">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="024ec-383">L'indirizzo di posta elettronica nel file CSV deve essere quello specificato nel tenant di destinazione, non nel tenant di origine.</span><span class="sxs-lookup"><span data-stu-id="024ec-383">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="024ec-384">L'invio in batch di migrazione è supportato anche dal nuovo Exchange admin center quando si seleziona l'opzione cross-tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-384">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="024ec-385">Aggiornare MailUsers locali</span><span class="sxs-lookup"><span data-stu-id="024ec-385">Update on-premises MailUsers</span></span>

<span data-ttu-id="024ec-386">Una volta che la cassetta postale si sposta dall'origine alla destinazione, è necessario assicurarsi che gli utenti di posta locale, sia di origine che di destinazione, siano aggiornati con il nuovo targetAddress.</span><span class="sxs-lookup"><span data-stu-id="024ec-386">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="024ec-387">Negli esempi, targetDeliveryDomain utilizzato nello spostamento è **contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="024ec-387">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="024ec-388">Aggiornare gli utenti di posta con questo targetAddress.</span><span class="sxs-lookup"><span data-stu-id="024ec-388">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="024ec-389">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="024ec-389">Frequently asked questions</span></span>

<span data-ttu-id="024ec-390">**È necessario aggiornare RemoteMailboxes nell'origine locale dopo lo spostamento?**</span><span class="sxs-lookup"><span data-stu-id="024ec-390">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="024ec-391">Sì, è consigliabile aggiornare targetAddress (RemoteRoutingAddress/ExternalEmailAddress) degli utenti locali di origine quando la cassetta postale del tenant di origine si sposta nel tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-391">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="024ec-392">Anche se il routing della posta può seguire le segnalazioni tra più utenti di posta con targetAddresses diversi, le ricerche sulla disponibilità per gli utenti di posta devono essere mirate alla posizione dell'utente della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="024ec-392">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="024ec-393">Le ricerche sulla disponibilità non inseguono più reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="024ec-393">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="024ec-394">**Eseguire Teams le riunioni tra tenant?**</span><span class="sxs-lookup"><span data-stu-id="024ec-394">**Do Teams meetings migrate cross-tenant?**</span></span>  

<span data-ttu-id="024ec-395">Le riunioni verranno spostate, ma l'URL Teams riunione non viene aggiornato quando gli elementi vengono migrati tra tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-395">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="024ec-396">Poiché l'URL non sarà valido nel tenant di destinazione, sarà necessario rimuovere e ricreare le Teams riunioni.</span><span class="sxs-lookup"><span data-stu-id="024ec-396">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="024ec-397">**Il contenuto Teams della cartella chat viene migrato tra tenant?**</span><span class="sxs-lookup"><span data-stu-id="024ec-397">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="024ec-398">No, il contenuto Teams della cartella chat non esegue la migrazione tra tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-398">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="024ec-399">**Come è possibile visualizzare solo gli spostamenti tra tenant, non gli spostamenti di onboarding e off-boarding?**</span><span class="sxs-lookup"><span data-stu-id="024ec-399">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="024ec-400">Utilizzare il `-flags` parametro .</span><span class="sxs-lookup"><span data-stu-id="024ec-400">Use the `-flags` parameter.</span></span> <span data-ttu-id="024ec-401">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-401">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="024ec-402">**È possibile fornire script di esempio per la copia degli attributi utilizzati nei test?**</span><span class="sxs-lookup"><span data-stu-id="024ec-402">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="024ec-403">ESEMPIO: NESSUNA GARANZIA</span><span class="sxs-lookup"><span data-stu-id="024ec-403">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="024ec-404">Questo script presuppone una connessione sia alla cassetta postale di origine (per ottenere i valori di origine) che alla destinazione di Servizi di dominio Active Directory locale (per timbrare l'oggetto ADUser).</span><span class="sxs-lookup"><span data-stu-id="024ec-404">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="024ec-405">Se nell'origine è abilitata la controversia legale o il ripristino di un singolo elemento, imposta questo valore nell'account di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-405">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="024ec-406">In questo modo le dimensioni del dumpster dell'account di destinazione verranno aumentate a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="024ec-406">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit" 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects 
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="024ec-407">**Come si accede a Outlook giorno 1 dopo lo spostamento della cassetta postale di utilizzo?**</span><span class="sxs-lookup"><span data-stu-id="024ec-407">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="024ec-408">Poiché un solo tenant può essere proprietario di un dominio, l'ex SMTPAddress primario non verrà associato all'utente nel tenant di destinazione al termine dello spostamento della cassetta postale. solo i domini associati al nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-408">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="024ec-409">Outlook utilizza il nuovo UPN degli utenti per eseguire l'autenticazione nel servizio e il profilo Outlook prevede di trovare l'SMTPAddress primario legacy in modo che corrisponda alla cassetta postale nel sistema di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-409">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="024ec-410">Poiché l'indirizzo legacy non è nel sistema di destinazione, il profilo di Outlook non si connetterà per trovare la cassetta postale appena spostata.</span><span class="sxs-lookup"><span data-stu-id="024ec-410">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="024ec-411">Per questa distribuzione iniziale, gli utenti dovranno ricreare il proprio profilo con il nuovo UPN, l'indirizzo SMTP primario e risincronizzazione del contenuto OST.</span><span class="sxs-lookup"><span data-stu-id="024ec-411">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="024ec-412">Pianificare di conseguenza quando gli utenti vengono evasi in batch per il completamento.</span><span class="sxs-lookup"><span data-stu-id="024ec-412">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="024ec-413">È necessario conto dell'utilizzo e della capacità della rete quando Outlook vengono creati profili client e i successivi file OST e Rubrica offline vengono scaricati nei client.</span><span class="sxs-lookup"><span data-stu-id="024ec-413">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="024ec-414">**Di Exchange ruoli RBAC di cui è necessario essere membri per configurare o completare uno spostamento tra tenant?**</span><span class="sxs-lookup"><span data-stu-id="024ec-414">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="024ec-415">Esiste una matrice di ruoli basata sull'assunzione di compiti delegati durante l'esecuzione di uno spostamento delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="024ec-415">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="024ec-416">Attualmente sono necessari due ruoli:</span><span class="sxs-lookup"><span data-stu-id="024ec-416">Currently, two roles are required:</span></span>  

- <span data-ttu-id="024ec-417">Il primo ruolo è per un'attività di installazione unica che stabilisce l'autorizzazione per lo spostamento del contenuto all'interno o all'esterno del limite tenant/organizzazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-417">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="024ec-418">Poiché lo spostamento dei dati dal controllo dell'organizzazione è un problema critico per tutte le società, è stato scelto il ruolo più alto assegnato di Amministratore organizzazione (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="024ec-418">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="024ec-419">Questo ruolo deve modificare o configurare una nuova OrganizationRelationship che definisce -MailboxMoveCapability con l'organizzazione remota.</span><span class="sxs-lookup"><span data-stu-id="024ec-419">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="024ec-420">Solo OrgAdmin può modificare l'impostazione MailboxMoveCapability, mentre altri attributi in OrganizationRelationhip possono essere gestiti dall'amministratore della condivisione federata.</span><span class="sxs-lookup"><span data-stu-id="024ec-420">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="024ec-421">Il ruolo dell'esecuzione dei comandi di spostamento effettivi può essere delegato a una funzione di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="024ec-421">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="024ec-422">Al ruolo di Spostare cassette postali viene assegnata la possibilità di spostare le cassette postali all'interno o all'uscita dall'organizzazione utilizzando il `-RemoteTenant` parametro .</span><span class="sxs-lookup"><span data-stu-id="024ec-422">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="024ec-423">**Come viene selezionato l'indirizzo SMTP selezionato per targetAddress (TargetDeliveryDomain) nella cassetta postale convertita (conversione di MailUser)?**</span><span class="sxs-lookup"><span data-stu-id="024ec-423">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="024ec-424">Exchange cassetta postale si sposta utilizzando MRS crea il targetAddress sulla cassetta postale di origine quando si esegue la conversione in un oggetto MailUser corrispondente a un indirizzo di posta elettronica (proxyAddress) nell'oggetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-424">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="024ec-425">Il processo accetta il valore -TargetDeliveryDomain passato al comando di spostamento, quindi verifica la presenza di un proxy corrispondente per il dominio sul lato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-425">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="024ec-426">Quando viene trovata una corrispondenza, viene utilizzato il proxyAddress corrispondente per impostare ExternalEmailAddress (targetAddress) sull'oggetto cassetta postale convertita (ora MailUser).</span><span class="sxs-lookup"><span data-stu-id="024ec-426">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="024ec-427">**Come si esegue la transizione delle autorizzazioni delle cassette postali?**</span><span class="sxs-lookup"><span data-stu-id="024ec-427">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="024ec-428">Le autorizzazioni per le cassette postali includono Invia per conto di e Accesso alle cassette postali:</span><span class="sxs-lookup"><span data-stu-id="024ec-428">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="024ec-429">Send On Behalf Of (AD:publicDelegates) archivia il DN dei destinatari con accesso alla cassetta postale di un utente come delegato.</span><span class="sxs-lookup"><span data-stu-id="024ec-429">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="024ec-430">Questo valore viene archiviato in Active Directory e attualmente non viene spostato come parte della transizione della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="024ec-430">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="024ec-431">Se la cassetta postale di origine ha publicDelegates impostato, sarà necessario impostare publicDelegates sulla cassetta postale di destinazione una volta completata la conversione da MEU a Cassetta postale nell'ambiente di destinazione eseguendo `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="024ec-431">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="024ec-432">Cassette postali Le autorizzazioni archiviate nella cassetta postale verranno spostate con la cassetta postale quando sia l'entità che il delegato vengono spostati nel sistema di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-432">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="024ec-433">Ad esempio, all'utente TestUser_7 viene concesso FullAccess alla cassetta postale TestUser_8 nel tenant SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="024ec-433">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="024ec-434">Al termine dello spostamento delle cassette postali TargetCompany.onmicrosoft.com, le stesse autorizzazioni vengono impostate nella directory di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-434">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="024ec-435">Di seguito sono riportati esempi di utilizzo di *Get-MailboxPermission* TestUser_7 nei tenant di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-435">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="024ec-436">Exchange cmdlet vengono prefissi di origine e di destinazione di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="024ec-436">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="024ec-437">Ecco un esempio dell'output dell'autorizzazione della cassetta postale prima di uno spostamento.</span><span class="sxs-lookup"><span data-stu-id="024ec-437">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="024ec-438">Ecco un esempio dell'output dell'autorizzazione della cassetta postale dopo lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="024ec-438">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="024ec-439">Le autorizzazioni per la cassetta postale e il calendario tra tenant NON sono supportate.</span><span class="sxs-lookup"><span data-stu-id="024ec-439">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="024ec-440">È necessario organizzare le entità e i delegati in batch di spostamento consolidati in modo che le cassette postali connesse siano trasferite contemporaneamente dal tenant di origine.</span><span class="sxs-lookup"><span data-stu-id="024ec-440">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="024ec-441">**Quale proxy X500 deve essere aggiunto agli indirizzi proxy MailUser di destinazione per abilitare la migrazione?**</span><span class="sxs-lookup"><span data-stu-id="024ec-441">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="024ec-442">La migrazione delle cassette postali tra tenant richiede che il valore LegacyExchangeDN dell'oggetto cassetta postale di origine sia contrassegnato come indirizzo di posta elettronica x500 nell'oggetto MailUser di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-442">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="024ec-443">Esempio:</span><span class="sxs-lookup"><span data-stu-id="024ec-443">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="024ec-444">Oltre a questo proxy X500, sarà necessario copiare tutti i proxy X500 dalla cassetta postale nell'origine alla cassetta postale nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-444">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="024ec-445">**Dove avviare la risoluzione dei problemi se gli spostamenti non funzionano?**</span><span class="sxs-lookup"><span data-stu-id="024ec-445">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="024ec-446">Iniziare eseguendo lo script di VerifySetup.ps1 in [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ed esaminare l'output.</span><span class="sxs-lookup"><span data-stu-id="024ec-446">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="024ec-447">Ecco un esempio di esecuzione di VerifySetup.ps1 nel tenant di destinazione:</span><span class="sxs-lookup"><span data-stu-id="024ec-447">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="024ec-448">Ecco un eExample dell'esecuzione VerifySetup.ps1 nel tenant di origine:</span><span class="sxs-lookup"><span data-stu-id="024ec-448">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="024ec-449">**Il tenant di origine e di destinazione può utilizzare lo stesso nome di dominio?**</span><span class="sxs-lookup"><span data-stu-id="024ec-449">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="024ec-450">No.</span><span class="sxs-lookup"><span data-stu-id="024ec-450">No.</span></span> <span data-ttu-id="024ec-451">I nomi di dominio tenant di origine e di destinazione devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="024ec-451">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="024ec-452">Ad esempio, un dominio di origine di contoso.com e il dominio di destinazione di fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="024ec-452">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="024ec-453">**Le cassette postali condivise verranno spostate e funzionano ancora?**</span><span class="sxs-lookup"><span data-stu-id="024ec-453">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="024ec-454">Sì, tuttavia, le autorizzazioni dello Store vengono conservate solo come descritto in questi articoli:</span><span class="sxs-lookup"><span data-stu-id="024ec-454">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="024ec-455">Microsoft Docs | Gestire le autorizzazioni per i destinatari in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="024ec-455">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="024ec-456">Supporto tecnico Microsoft | Come concedere Exchange e Outlook cassette postali in Office 365 dedicate</span><span class="sxs-lookup"><span data-stu-id="024ec-456">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="024ec-457">**È necessario Azure Key Vault e quando vengono effettuate le transazioni?**</span><span class="sxs-lookup"><span data-stu-id="024ec-457">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="024ec-458">Sì, è necessaria una sottoscrizione di Azure per usare l'insieme di credenziali delle chiavi per archiviare il certificato per autorizzare la migrazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-458">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="024ec-459">A differenza delle migrazioni di onboarding che utilizzano il nome utente & password per l'autenticazione nell'origine, le migrazioni di cassette postali tra tenant utilizzano OAuth e questo certificato come segreto/credenziale.</span><span class="sxs-lookup"><span data-stu-id="024ec-459">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="024ec-460">L'accesso all'insieme di credenziali delle chiavi deve essere mantenuto in tutte le migrazioni di cassette postali, in quanto è possibile accedervi una volta all'inizio e alla fine della migrazione, nonché una volta ogni 24 ore durante i tempi di sincronizzazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="024ec-460">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="024ec-461">È possibile esaminare i dettagli di costing AKV [qui]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="024ec-461">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="024ec-462">**Sono presenti suggerimenti per i batch?**</span><span class="sxs-lookup"><span data-stu-id="024ec-462">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="024ec-463">Non superare le 2000 cassette postali per batch.</span><span class="sxs-lookup"><span data-stu-id="024ec-463">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="024ec-464">È consigliabile inviare batch due settimane prima della data di scadenza, in quanto non vi è alcun impatto sugli utenti finali durante la sincronizzazione. Se sono necessarie indicazioni per le quantità di cassette postali oltre 50.000, è possibile contattare la lista di distribuzione di Engineering Feedback all'crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="024ec-464">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="024ec-465">**Cosa succede se si utilizza la crittografia del servizio con customer key?**</span><span class="sxs-lookup"><span data-stu-id="024ec-465">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="024ec-466">La cassetta postale verrà decrittografata prima dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="024ec-466">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="024ec-467">Verificare che customer key sia configurato nel tenant di destinazione, se è ancora necessario.</span><span class="sxs-lookup"><span data-stu-id="024ec-467">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="024ec-468">Vedi [qui](../compliance/customer-key-overview.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="024ec-468">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="024ec-469">**Qual è il tempo stimato per la migrazione?**</span><span class="sxs-lookup"><span data-stu-id="024ec-469">**What is the estimated migration time?**</span></span>

<span data-ttu-id="024ec-470">Per facilitare la pianificazione della [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) migrazione, nella tabella riportata di seguito sono riportate le linee guida su quando prevedere il completamento delle migrazioni di cassette postali in blocco o singole migrazioni.</span><span class="sxs-lookup"><span data-stu-id="024ec-470">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="024ec-471">Queste stime si basano su un'analisi dei dati delle migrazioni precedenti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="024ec-471">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="024ec-472">Poiché ogni ambiente è univoco, la velocità di migrazione esatta può variare.</span><span class="sxs-lookup"><span data-stu-id="024ec-472">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="024ec-473">Ricorda che questa funzionalità è attualmente in anteprima e il contratto di servizio e i livelli di servizio applicabili non si applicano ad alcun problema di prestazioni o disponibilità durante lo stato di anteprima di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="024ec-473">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="024ec-474">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="024ec-474">Known issues</span></span>  

-  <span data-ttu-id="024ec-475">**Problema: gli archivi espansi automaticamente non possono essere migrati.**</span><span class="sxs-lookup"><span data-stu-id="024ec-475">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="024ec-476">La funzionalità di migrazione tra tenant supporta le migrazioni della cassetta postale principale e della cassetta postale di archiviazione per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="024ec-476">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="024ec-477">Se l'utente nell'origine dispone tuttavia di un archivio espanso automaticamente, ovvero più di una cassetta postale di archiviazione, la funzionalità non è in grado di eseguire la migrazione degli archivi aggiuntivi e dovrebbe avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="024ec-477">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="024ec-478">**Problema: Cloud MailUsers con proxyAddress smtp non di proprietà blocca lo spostamento MRS in background.**</span><span class="sxs-lookup"><span data-stu-id="024ec-478">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="024ec-479">Quando si creano oggetti MailUser del tenant di destinazione, è necessario verificare che tutti gli indirizzi proxy SMTP appartengano all'organizzazione tenant di destinazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-479">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="024ec-480">Se nell'utente di posta di destinazione esiste un proxyAddress SMTP che non appartiene al tenant locale, la conversione di MailUser in Mailbox non è consentita.</span><span class="sxs-lookup"><span data-stu-id="024ec-480">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="024ec-481">Ciò è dovuto alla garanzia che gli oggetti cassetta postale possono inviare posta solo da domini per i quali il tenant è autorevole (domini rivendicati dal tenant):</span><span class="sxs-lookup"><span data-stu-id="024ec-481">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="024ec-482">Quando si sincronizzano gli utenti da locale con Azure AD Connessione, si effettua il provisioning degli oggetti MailUser locali con ExternalEmailAddress che punta al tenant di origine in cui è presente la cassetta postale (laran@contoso.onmicrosoft.com) e si contrassegna PrimarySMTPAddress come dominio che risiede nel tenant di destinazione (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="024ec-482">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="024ec-483">Questi valori vengono sincronizzati con il tenant e viene eseguito il provisioning di un utente di posta appropriato e pronto per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="024ec-483">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="024ec-484">Di seguito è riportato un oggetto di esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-484">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="024ec-485">*L contoso.onmicrosoft.com* non *è* presente nella matrice EmailAddresses/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="024ec-485">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="024ec-486">**Problema: gli oggetti MailUser con indirizzi SMTP primari "esterni" vengono modificati/ reimpostati su domini "interni" della società**</span><span class="sxs-lookup"><span data-stu-id="024ec-486">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="024ec-487">Gli oggetti MailUser sono puntatori a cassette postali non locali.</span><span class="sxs-lookup"><span data-stu-id="024ec-487">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="024ec-488">Nel caso delle migrazioni di cassette postali tra tenant, vengono utilizzati oggetti MailUser per rappresentare la cassetta postale di origine (dal punto di vista dell'organizzazione di destinazione) o la cassetta postale di destinazione (dal punto di vista dell'organizzazione di origine).</span><span class="sxs-lookup"><span data-stu-id="024ec-488">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="024ec-489">MailUsers avrà un ExternalEmailAddress (targetAddress) che punta all'indirizzo smtp della cassetta postale effettiva (ProxyTest@fabrikam.onmicrosoft.com) e all'indirizzo PRIMARYSMTP che rappresenta l'indirizzo SMTP visualizzato dell'utente della cassetta postale nella directory.</span><span class="sxs-lookup"><span data-stu-id="024ec-489">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="024ec-490">Alcune organizzazioni scelgono di visualizzare l'indirizzo SMTP primario come indirizzo SMTP esterno, non come indirizzo di proprietà/verificato dal tenant locale (ad esempio fabrikam.com anziché come contoso.com).</span><span class="sxs-lookup"><span data-stu-id="024ec-490">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="024ec-491">Tuttavia, una volta applicato un oggetto piano di servizio di Exchange all'oggetto MailUser tramite operazioni di licenza, l'indirizzo SMTP primario viene modificato in modo da essere visualizzato come dominio verificato dall'organizzazione locale (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="024ec-491">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="024ec-492">Esistono due possibili motivi:</span><span class="sxs-lookup"><span data-stu-id="024ec-492">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="024ec-493">Quando un piano di servizio di Exchange viene applicato a un oggetto MailUser, il processo di Azure AD inizia a applicare lo scrubbing del proxy per garantire che l'organizzazione locale non sia in grado di inviare posta, spoofing o posta da un altro tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-493">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="024ec-494">Qualsiasi indirizzo SMTP in un oggetto destinatario con questi piani di servizio verrà rimosso se l'indirizzo non viene verificato dall'organizzazione locale.</span><span class="sxs-lookup"><span data-stu-id="024ec-494">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="024ec-495">Come nel caso dell'esempio, il dominio Fabikam.com non viene verificato dal tenant di contoso.onmicrosoft.com, quindi lo scrubbing rimuove tale fabrikam.com dominio.</span><span class="sxs-lookup"><span data-stu-id="024ec-495">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="024ec-496">Se si desidera mantenere questi domini esterni in MailUser, prima della migrazione o dopo la migrazione, è necessario modificare i processi di migrazione per rimuovere le licenze al termine dello spostamento o prima dello spostamento per assicurarsi che agli utenti sia applicata la personalizzazione esterna prevista.</span><span class="sxs-lookup"><span data-stu-id="024ec-496">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="024ec-497">È necessario verificare che l'oggetto cassetta postale sia correttamente concesso in licenza per non influire sul servizio di posta.</span><span class="sxs-lookup"><span data-stu-id="024ec-497">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="024ec-498">Di seguito è riportato uno script di esempio per rimuovere i piani di servizio in un oggetto MailUser Contoso.onmicrosoft.com tenant.</span><span class="sxs-lookup"><span data-stu-id="024ec-498">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="024ec-499">I risultati nel set di ServicePlan assegnati sono mostrati qui.</span><span class="sxs-lookup"><span data-stu-id="024ec-499">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="024ec-500">PrimarySMTPAddress dell'utente non viene più rimosso.</span><span class="sxs-lookup"><span data-stu-id="024ec-500">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="024ec-501">Il fabrikam.com non è di proprietà del tenant contoso.onmicrosoft.com e verrà mantenuto come indirizzo SMTP primario visualizzato nella directory.</span><span class="sxs-lookup"><span data-stu-id="024ec-501">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="024ec-502">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="024ec-502">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="024ec-503">Quando msExchRemoteRecipientType è impostato su 8 (DeprovisionMailbox), per gli utenti mailuser locali migrati nel tenant di destinazione, la logica di scrubbing del proxy in Azure rimuoverà i domini non proprietari e reimposta il primarySMTP su un dominio di proprietà.</span><span class="sxs-lookup"><span data-stu-id="024ec-503">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="024ec-504">Deselezionando msExchRemoteRecipientType nell'oggetto MailUser locale, la logica di scrubt proxy non si applica più.</span><span class="sxs-lookup"><span data-stu-id="024ec-504">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="024ec-505">Di seguito è riportato il set completo di possibili piani di servizio che includono Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="024ec-505">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="024ec-506">Nome</span><span class="sxs-lookup"><span data-stu-id="024ec-506">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="024ec-507">Advanced eDiscovery Archiviazione (500 GB)</span><span class="sxs-lookup"><span data-stu-id="024ec-507">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="024ec-508">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="024ec-508">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="024ec-509">Prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="024ec-509">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="024ec-510">Exchange Enterprise servizi CAL (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="024ec-510">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="024ec-511">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="024ec-511">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="024ec-512">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="024ec-512">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="024ec-513">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="024ec-513">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="024ec-514">Exchange Online (Piano 1)</span><span class="sxs-lookup"><span data-stu-id="024ec-514">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="024ec-515">Exchange Online (Piano 2)</span><span class="sxs-lookup"><span data-stu-id="024ec-515">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="024ec-516">Archiviazione Exchange Online per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="024ec-516">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="024ec-517">Archiviazione Exchange Online per Exchange Server</span><span class="sxs-lookup"><span data-stu-id="024ec-517">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="024ec-518">Exchange Online Componente aggiuntivo utente inattivo</span><span class="sxs-lookup"><span data-stu-id="024ec-518">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="024ec-519">Chiosco Exchange Online</span><span class="sxs-lookup"><span data-stu-id="024ec-519">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="024ec-520">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="024ec-520">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="024ec-521">Exchange Online Piano 1</span><span class="sxs-lookup"><span data-stu-id="024ec-521">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="024ec-522">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="024ec-522">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="024ec-523">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="024ec-523">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="024ec-524">Ostacoli alle informazioni</span><span class="sxs-lookup"><span data-stu-id="024ec-524">Information Barriers</span></span>                              |
   | <span data-ttu-id="024ec-525">Information Protection per Office 365 - Premium</span><span class="sxs-lookup"><span data-stu-id="024ec-525">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="024ec-526">Information Protection for Office 365 - Standard</span><span class="sxs-lookup"><span data-stu-id="024ec-526">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="024ec-527">Dati analitici di MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="024ec-527">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="024ec-528">Microsoft 365 Controllo avanzato</span><span class="sxs-lookup"><span data-stu-id="024ec-528">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="024ec-529">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="024ec-529">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="024ec-530">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="024ec-530">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="024ec-531">Microsoft MyAnalytics (completo)</span><span class="sxs-lookup"><span data-stu-id="024ec-531">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="024ec-532">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="024ec-532">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="024ec-533">Microsoft Defender per Office 365 (Piano 1)</span><span class="sxs-lookup"><span data-stu-id="024ec-533">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="024ec-534">Microsoft Defender per Office 365 (Piano 2)</span><span class="sxs-lookup"><span data-stu-id="024ec-534">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="024ec-535">Office 365 Gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="024ec-535">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="024ec-536">Premium Crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="024ec-536">Premium Encryption in Office 365</span></span>                  |
