---
title: Creare un tipo di informazioni sensibili personalizzato con Exact Data Match
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 699cea6aec6f11462aed0c08db98ca4620df519a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686560"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="ff5e4-103">Creare tipi di informazioni sensibili personalizzati con classificazione esatta basata su Exact Data Match</span><span class="sxs-lookup"><span data-stu-id="ff5e4-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="ff5e4-104">[Tipi di informazioni sensibili personalizzati](custom-sensitive-info-types.md)  vengono usati per impedire la condivisione accidentale o inappropriata di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="ff5e4-105">Gli amministratori possono usare il Centro sicurezza e conformità o PowerShell per definire un tipo di informazioni sensibili personalizzato in base a modelli, evidenza (parole chiave come *dipendente*, *badge*, *ID* e così via), vicinanza tra caratteri (quant'è vicina l'evidenza ai caratteri in un determinato modello) e livelli di probabilità.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-105">As an administrator, you can use the Security & Compliance Center or PowerShell to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="ff5e4-106">Questi tipi di informazioni sensibili personalizzati soddisfano le esigenze aziendali di molte organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-106">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="ff5e4-107">Ma cosa succede se si vuole un tipo di informazioni sensibili personalizzato che usi valori di dati esatti, anziché modelli generici basati solo sulla corrispondenza?</span><span class="sxs-lookup"><span data-stu-id="ff5e4-107">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="ff5e4-108">Con la classificazione basata su Exact Data Match (EDM) è possibile creare un tipo di informazioni sensibili personalizzato che sia progettato per:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-108">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="ff5e4-109">essere dinamico e aggiornabile;</span><span class="sxs-lookup"><span data-stu-id="ff5e4-109">be dynamic and refreshable;</span></span>
- <span data-ttu-id="ff5e4-110">offrire maggiore scalabilità;</span><span class="sxs-lookup"><span data-stu-id="ff5e4-110">be more scalable;</span></span>
- <span data-ttu-id="ff5e4-111">produrre meno falsi positivi;</span><span class="sxs-lookup"><span data-stu-id="ff5e4-111">result in fewer false-positives;</span></span>
- <span data-ttu-id="ff5e4-112">usare dati sensibili strutturati;</span><span class="sxs-lookup"><span data-stu-id="ff5e4-112">work with structured sensitive data;</span></span>
- <span data-ttu-id="ff5e4-113">gestire le informazioni sensibili in modo più sicuro; e</span><span class="sxs-lookup"><span data-stu-id="ff5e4-113">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="ff5e4-114">essere usato con più servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-114">be used with several Microsoft cloud services.</span></span>

![Classificazione basata su EDM](../media/EDMClassification.png)

<span data-ttu-id="ff5e4-116">La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-116">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="ff5e4-117">Il database può essere aggiornato giornalmente o settimanalmente e può contenere un massimo di 100 milioni di righe di dati.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-117">The database can be refreshed daily or weekly, and it can contain up to 100 million rows of data.</span></span> <span data-ttu-id="ff5e4-118">I dipendenti, i pazienti o i clienti vanno e vengono e i record cambiano, i tipi di informazioni sensibili personalizzati rimangono aggiornati e disponibili.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-118">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="ff5e4-119">È anche possibile usare una classificazione basata su EDM con criteri, ad esempio i  [criteri di prevenzione della perdita dei dati ](data-loss-prevention-policies.md) (DLP) o i  [criteri dei file di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-119">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="ff5e4-120">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte per le lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-120">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="ff5e4-121">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-121">Chinese (simplified)</span></span>
> - <span data-ttu-id="ff5e4-122">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-122">Chinese (traditional)</span></span>
> - <span data-ttu-id="ff5e4-123">Coreano</span><span class="sxs-lookup"><span data-stu-id="ff5e4-123">Korean</span></span>
> - <span data-ttu-id="ff5e4-124">Giapponese</span><span class="sxs-lookup"><span data-stu-id="ff5e4-124">Japanese</span></span>
> 
><span data-ttu-id="ff5e4-125">Questa versione di anteprima è disponibile solo nel cloud commerciale e l'implementazione è limitata ai paesi o alle aree geografiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-125">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="ff5e4-126">Giappone</span><span class="sxs-lookup"><span data-stu-id="ff5e4-126">Japan</span></span>
> - <span data-ttu-id="ff5e4-127">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="ff5e4-127">Korea</span></span>
> - <span data-ttu-id="ff5e4-128">Cina</span><span class="sxs-lookup"><span data-stu-id="ff5e4-128">China</span></span>
> - <span data-ttu-id="ff5e4-129">RAS di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="ff5e4-129">Hong Kong</span></span>
> - <span data-ttu-id="ff5e4-130">RAS di Macao</span><span class="sxs-lookup"><span data-stu-id="ff5e4-130">Macau</span></span>
> - <span data-ttu-id="ff5e4-131">Taiwan</span><span class="sxs-lookup"><span data-stu-id="ff5e4-131">Taiwan</span></span>
>
><span data-ttu-id="ff5e4-132">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-132">This support is available for sensitive information types.</span></span> <span data-ttu-id="ff5e4-133">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-133">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ff5e4-134">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="ff5e4-134">Required licenses and permissions</span></span>

<span data-ttu-id="ff5e4-135">È necessario essere un amministratore globale, di conformità o di Exchange Online per eseguire le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-135">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="ff5e4-136">Per ulteriori informazioni sulle autorizzazioni DLP, vedere  [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-136">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="ff5e4-137">La classificazione basata su EDM è inclusa negli abbonamenti</span><span class="sxs-lookup"><span data-stu-id="ff5e4-137">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="ff5e4-138">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="ff5e4-138">Office 365 E5</span></span>
- <span data-ttu-id="ff5e4-139">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ff5e4-139">Microsoft 365 E5</span></span>
- <span data-ttu-id="ff5e4-140">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ff5e4-140">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="ff5e4-141">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="ff5e4-141">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="ff5e4-142">Collegamenti a portali per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="ff5e4-142">Portal links for your subscription</span></span>


|<span data-ttu-id="ff5e4-143">Portale</span><span class="sxs-lookup"><span data-stu-id="ff5e4-143">Portal</span></span>  |<span data-ttu-id="ff5e4-144">Tutto il mondo/GCC</span><span class="sxs-lookup"><span data-stu-id="ff5e4-144">World Wide/GCC</span></span>  |<span data-ttu-id="ff5e4-145">GCC-High</span><span class="sxs-lookup"><span data-stu-id="ff5e4-145">GCC-High</span></span>  |<span data-ttu-id="ff5e4-146">DOD</span><span class="sxs-lookup"><span data-stu-id="ff5e4-146">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="ff5e4-147">Office SCC</span><span class="sxs-lookup"><span data-stu-id="ff5e4-147">Office SCC</span></span>     |  <span data-ttu-id="ff5e4-148">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="ff5e4-148">protection.office.com</span></span>       |<span data-ttu-id="ff5e4-149">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="ff5e4-149">scc.office365.us</span></span>         |<span data-ttu-id="ff5e4-150">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="ff5e4-150">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="ff5e4-151">Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff5e4-151">Microsoft 365 Security center</span></span>     |<span data-ttu-id="ff5e4-152">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ff5e4-152">security.microsoft.com</span></span>         |<span data-ttu-id="ff5e4-153">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="ff5e4-153">security.microsoft.us</span></span>         |<span data-ttu-id="ff5e4-154">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="ff5e4-154">security.apps.mil</span></span>|
|<span data-ttu-id="ff5e4-155">Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff5e4-155">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="ff5e4-156">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ff5e4-156">compliance.microsoft.com</span></span>         |<span data-ttu-id="ff5e4-157">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="ff5e4-157">compliance.microsoft.us</span></span>         |<span data-ttu-id="ff5e4-158">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="ff5e4-158">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="ff5e4-159">Flusso di lavoro in breve</span><span class="sxs-lookup"><span data-stu-id="ff5e4-159">The work flow at a glance</span></span>

|<span data-ttu-id="ff5e4-160">Fase</span><span class="sxs-lookup"><span data-stu-id="ff5e4-160">Phase</span></span>  |<span data-ttu-id="ff5e4-161">Cosa serve</span><span class="sxs-lookup"><span data-stu-id="ff5e4-161">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="ff5e4-162">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="ff5e4-162">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="ff5e4-163">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-163">(As needed)</span></span><br/><span data-ttu-id="ff5e4-164">- [Modificare lo schema del database](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-164">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="ff5e4-165">- [Rimuovere lo schema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-165">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="ff5e4-166">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-166">- Read access to the sensitive data</span></span><br/><span data-ttu-id="ff5e4-167">- Schema del database nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-167">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="ff5e4-168">- Pacchetto di regole nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-168">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="ff5e4-169">- Autorizzazioni di amministratore al Centro sicurezza e conformità (utilizzando PowerShell)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-169">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="ff5e4-170">Parte 2: Hash e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-170">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="ff5e4-171">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-171">(As needed)</span></span><br/>[<span data-ttu-id="ff5e4-172">Aggiornare i dati</span><span class="sxs-lookup"><span data-stu-id="ff5e4-172">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="ff5e4-173">- Gruppo di sicurezza personalizzato e account utente</span><span class="sxs-lookup"><span data-stu-id="ff5e4-173">- Custom security group and user account</span></span><br/><span data-ttu-id="ff5e4-174">- Accesso come amministratore locale al computer con l’Agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="ff5e4-174">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="ff5e4-175">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-175">- Read access to the sensitive data</span></span><br/><span data-ttu-id="ff5e4-176">- Procedura e programmazione per l'aggiornamento dei dati</span><span class="sxs-lookup"><span data-stu-id="ff5e4-176">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="ff5e4-177">Parte 3: usare la classificazione basata su EDM con i servizi Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="ff5e4-177">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="ff5e4-178">- Abbonamento a Microsoft 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="ff5e4-178">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="ff5e4-179">- Funzionalità della classificazione basata su EDM abilitata</span><span class="sxs-lookup"><span data-stu-id="ff5e4-179">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="ff5e4-180">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="ff5e4-180">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="ff5e4-181">L’impostazione e la configurazione della classificazione basata su EDM implicano il salvataggio di dati sensibili in formato .csv, la definizione di uno schema per il database delle informazioni sensibili, la creazione di un pacchetto di regole e il caricamento del dello schema e del pacchetto di regole.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-181">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="ff5e4-182">Definire lo schema per il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-182">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="ff5e4-183">Identificare le informazioni sensibili da usare.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="ff5e4-184">Esportare i dati in un'app, come Microsoft Excel e salvare il file in formato .csv.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="ff5e4-185">Il file di dati può includere al massimo:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="ff5e4-186">Fino a 100 milioni di righe di dati sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="ff5e4-187">Fino a 32 colonne (campi) per origine dati</span><span class="sxs-lookup"><span data-stu-id="ff5e4-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="ff5e4-188">Fino a 5 colonne (campi) contrassegnate come ricercabile</span><span class="sxs-lookup"><span data-stu-id="ff5e4-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="ff5e4-189">Strutturare i dati sensibili nel file .csv in modo che la prima riga includa i nomi dei campi usati per la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="ff5e4-190">Nel file .csv potrebbero essere presenti nomi di campo, come "ssn", "birthdate", "firstname", "lastname" e così via.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="ff5e4-191">Le intestazioni di colonna non possono includere spazi o caratteri di sottolineatura nei nomi.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-191">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="ff5e4-192">Ad esempio, il file .csv è denominato  *PatientRecords.csv* e le relative colonne sono  *PatientID*,  *MRN*,  *LastName*,  *FirstName*,  *SSN* e così via.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-192">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="ff5e4-193">Definire lo schema per il database delle informazioni sensibili nel formato .xml (come riportato nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-193">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="ff5e4-194">Assegnare al file dello schema il nome  **edm.xml** e configurarlo in modo che per ogni colonna del database sia presente una riga che usi la sintassi:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-194">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="ff5e4-195">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-195">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="ff5e4-196">Usare i nomi delle colonne per i valori  *Field name* .</span><span class="sxs-lookup"><span data-stu-id="ff5e4-196">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="ff5e4-197">Usare  *searchable="true"*  per un massimo di 5 campi che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-197">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="ff5e4-198">È necessario specificare almeno un campo come ricercabile.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-198">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="ff5e4-199">Ad esempio, il seguente file .xml definisce lo schema per un database dei record dei pazienti, con cinque campi specificati come ricercabili:  *PatientID*,  *MRN*,  *SSN*,  *Phone* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-199">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="ff5e4-200">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-200">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

4. <span data-ttu-id="ff5e4-201">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-201">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="ff5e4-202">Per caricare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-202">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="ff5e4-203">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-203">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="ff5e4-204">Conferma</span><span class="sxs-lookup"><span data-stu-id="ff5e4-204">Confirm</span></span>
      >
      > <span data-ttu-id="ff5e4-205">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="ff5e4-205">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="ff5e4-206">Viene importato il nuovo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-206">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="ff5e4-207">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="ff5e4-207">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="ff5e4-208">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 5, usare questo cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="ff5e4-208">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="ff5e4-209">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-209">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="ff5e4-210">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-210">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="ff5e4-211">Ora che lo schema del database delle informazioni riservate è definito, il passaggio successivo consiste nel configurare un pacchetto di regole.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-211">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="ff5e4-212">Passare alla sezione  [Configurare un pacchetto di regole](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-212">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="ff5e4-213">Modificare lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="ff5e4-213">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="ff5e4-214">Se si vogliono apportare modifiche al file **edm.xml**, ad esempio modificare i campi usati per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-214">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="ff5e4-215">Modificare il file **edm.xml** (il file descritto nella sezione  [Definire lo schema](#define-the-schema-for-your-database-of-sensitive-information)  di questo articolo).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-215">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="ff5e4-216">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-216">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="ff5e4-217">Per aggiornare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-217">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="ff5e4-218">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-218">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="ff5e4-219">Conferma</span><span class="sxs-lookup"><span data-stu-id="ff5e4-219">Confirm</span></span>
      >
      > <span data-ttu-id="ff5e4-220">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="ff5e4-220">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="ff5e4-221">Viene aggiornato lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-221">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="ff5e4-222">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="ff5e4-222">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="ff5e4-223">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 3, usare questo cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="ff5e4-223">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="ff5e4-224">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-224">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="ff5e4-225">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-225">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="ff5e4-226">Rimuovere lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="ff5e4-226">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="ff5e4-227">(Se necessario) Se si vuole rimuovere lo schema usato per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-227">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="ff5e4-228">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-228">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="ff5e4-229">Eseguire i cmdlet di PowerShell seguenti, sostituendo il nome dell'archivio dati di "patientrecords" con quello che si vuole rimuovere:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-229">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="ff5e4-230">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-230">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="ff5e4-231">Conferma</span><span class="sxs-lookup"><span data-stu-id="ff5e4-231">Confirm</span></span>
      >
      > <span data-ttu-id="ff5e4-232">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="ff5e4-232">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="ff5e4-233">Viene rimosso lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-233">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="ff5e4-234">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="ff5e4-234">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="ff5e4-235">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 2, usare questo cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="ff5e4-235">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="ff5e4-236">Configurare un pacchetto di regole</span><span class="sxs-lookup"><span data-stu-id="ff5e4-236">Set up a rule package</span></span>

1. <span data-ttu-id="ff5e4-237">Creare un pacchetto di regole nel formato .xml (con codifica Unicode), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-237">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="ff5e4-238">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-238">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="ff5e4-239">Quando si configura il pacchetto di regole, assicurarsi di fare riferimento correttamente al file .csv e al file **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-239">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="ff5e4-240">È possibile copiare, modificare e usare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-240">You can copy, modify, and use our example.</span></span> <span data-ttu-id="ff5e4-241">In questo XML di esempio è necessario personalizzare i campi seguenti per creare un tipo di informazioni sensibili di EDM:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-241">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="ff5e4-242">**RulePack id & ExactMatch id**: usare  [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  per generare un GUID.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-242">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="ff5e4-243">**Datastore**: questo campo specifica l'archivio dati di ricerca EDM da usare.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-243">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="ff5e4-244">È possibile specificare il nome di un'origine dati di uno schema EDM configurato.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-244">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="ff5e4-245">**idMatch**: questo campo punta all'elemento primario per EDM.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-245">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="ff5e4-246">Matches: specifica il campo da usare nella ricerca esatta.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-246">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="ff5e4-247">È possibile specificare il nome campo ricercabile nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-247">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="ff5e4-248">Classification: questo campo specifica la corrispondenza del tipo di informazioni sensibili che attiva la ricerca EDM.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-248">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="ff5e4-249">È possibile specificare il nome o il GUID di una classificazione predefinita o personalizzata esistente.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-249">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="ff5e4-250">**Match:** questo campo indica altre evidenze disponibili in prossimità di idMatch.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-250">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="ff5e4-251">Matches: è possibile specificare qualsiasi nome campo nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-251">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="ff5e4-252">**Resource:** questa sezione specifica il nome e la descrizione per il tipo di informazioni sensibili in più impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-252">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="ff5e4-253">idRef: è possibile specificare il GUID per l'ID ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-253">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="ff5e4-254">Name e descriptions: personalizzare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-254">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

1. <span data-ttu-id="ff5e4-255">Per caricare il pacchetto di regole, eseguire i seguenti cmdlet di PowerShell, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-255">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="ff5e4-256">A questo punto è stata configurata la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-256">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="ff5e4-257">Il passaggio successivo consiste nell'eseguire l’hashing dei i dati sensibili e poi di caricare gli hash per indicizzarli.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-257">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="ff5e4-258">Usare la procedura precedente in cui lo schema di PatientRecords definisce cinque campi come ricercabili:  *PatientID*,  *MRN*,  *SSN*,  *Phone* e  *DOB*.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-258">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="ff5e4-259">Il pacchetto di regole di esempio include questi campi e fa riferimento al file di schema del database (**edm.xml**), con un unico elemento  *ExactMatch*  per ogni campo ricercabile.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-259">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="ff5e4-260">Considerare l'elemento ExactMatch seguente:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-260">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="ff5e4-261">Utilizzando l'esempio proposto, osservare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-261">In this example, note the following:</span></span>

- <span data-ttu-id="ff5e4-262">Il nome dataStore fa riferimento al file .csv creato in precedenza:  **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-262">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="ff5e4-263">Il valore idMatch fa riferimento a un campo ricercabile elencato nel file dello schema del database:  **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-263">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="ff5e4-264">Il valore di classificazione fa riferimento a un tipo di informazioni sensibili esistente o personalizzato:  **classification = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-264">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="ff5e4-265">In questo caso, viene usato il tipo di informazioni sensibili esistente del Numero di previdenza sociale degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-265">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="ff5e4-266">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-266">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="ff5e4-267">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-267">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="ff5e4-268">Parte 2: eseguire hashing e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-268">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="ff5e4-269">In questa fase è possibile impostare un gruppo di sicurezza personalizzato e un account utente e configurare lo strumento Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-269">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="ff5e4-270">Successivamente, è possibile usare lo strumento per eseguire l’hashing dei dati sensibili e poi di caricarli gli hash per poterli indicizzare.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-270">Then, you use the tool to hash the sensitive data, and upload the hashed data so it can be indexed.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="ff5e4-271">Impostare il gruppo di sicurezza e l'account utente</span><span class="sxs-lookup"><span data-stu-id="ff5e4-271">Set up the security group and user account</span></span>

1. <span data-ttu-id="ff5e4-272">Come amministratore globale, passare all'interfaccia di amministrazione usando il [collegamento appropriato per l'abbonamento in uso](#portal-links-for-your-subscription) e [creare un gruppo di sicurezza](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) denominato **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-272">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="ff5e4-273">Aggiungere uno o più utenti al gruppo di sicurezza  **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="ff5e4-273">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="ff5e4-274">(Questi utenti gestiranno il database delle informazioni sensibili.)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-274">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="ff5e4-275">Assicurarsi che ogni utente che gestisce i dati sensibili sia un amministratore locale nel computer usato per l'Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-275">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="ff5e4-276">Impostare l'Agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="ff5e4-276">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="ff5e4-277">Prima di iniziare questa procedura, verificare di essere un membro del gruppo di sicurezza  **EDM\_DataUploaders**  e un amministratore locale nel computer.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-277">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="ff5e4-278">Collegamenti all'agente di caricamento EDM per tipo di abbonamento</span><span class="sxs-lookup"><span data-stu-id="ff5e4-278">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="ff5e4-279">Commerciale + GCC</span><span class="sxs-lookup"><span data-stu-id="ff5e4-279">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="ff5e4-280">GCC-High</span><span class="sxs-lookup"><span data-stu-id="ff5e4-280">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="ff5e4-281">DoD</span><span class="sxs-lookup"><span data-stu-id="ff5e4-281">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="ff5e4-282">Scaricare e installare l'[agente di caricamento EDM](#links-to-edm-upload-agent-by-subscription-type) appropriato per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-282">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription.</span></span> <span data-ttu-id="ff5e4-283">Per impostazione predefinita, il percorso di installazione deve essere **C:\\Programmi\\Microsoft\\EdmUploadAgent**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-283">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

   > [!TIP]
   > <span data-ttu-id="ff5e4-284">Per ottenere un elenco dei parametri di comando supportati, eseguire l'agente senza argomenti,</span><span class="sxs-lookup"><span data-stu-id="ff5e4-284">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="ff5e4-285">ad esempio "EdmUploadAgent.exe".</span><span class="sxs-lookup"><span data-stu-id="ff5e4-285">For example 'EdmUploadAgent.exe'.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ff5e4-286">È possibile caricare i dati con EDMUploadAgent in qualsiasi archivio dati solo due volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-286">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

2. <span data-ttu-id="ff5e4-287">Per autorizzare l'agente di caricamento EDM, aprire il prompt dei comandi di Windows (come amministratore) e quindi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-287">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="ff5e4-288">Accedere con l'account aziendale o dell'istituto di istruzione per Office 365 aggiunto al gruppo di sicurezza EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-288">Sign in with your work or school account for Office 365 that was added to the EDM_DataUploaders security group.</span></span>

<span data-ttu-id="ff5e4-289">Il passaggio successivo consiste nell'usare l’Agente di caricamento di EDM per eseguire l’hashing dei dati sensibili e poi caricare i dati.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-289">The next step is to use the EDM Upload Agent to hash the sensitive data, and then upload the hashed data.</span></span>

#### <a name="hash-and-upload-the-sensitive-data"></a><span data-ttu-id="ff5e4-290">Eseguire hashing e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-290">Hash and upload the sensitive data</span></span>

<span data-ttu-id="ff5e4-291">Salvare il file di dati sensibili (richiamare l'esempio  **PatientRecords.csv**) nell'unità locale del computer.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-291">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="ff5e4-292">(Il file di esempio **PatientRecords.csv** è stato salvato in **C:\\Edm\\Data**.)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-292">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="ff5e4-293">Per eseguire l’hashing e caricare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-293">To hash and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="ff5e4-294">Esempio: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="ff5e4-294">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="ff5e4-295">Per separare ed eseguire l’hashing dei dati sensibili in un ambiente isolato, eseguire le operazioni di hashing e caricamento separatamente.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-295">To separate and execute the hashing of sensitive data in an isolated environment, execute the hashing and upload steps separately.</span></span>

<span data-ttu-id="ff5e4-296">Per eseguire l’hashing dei dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-296">To hash the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="ff5e4-297">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-297">For example:</span></span>

> <span data-ttu-id="ff5e4-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="ff5e4-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="ff5e4-299">Per caricare i dati su cui è stato eseguito l’hashing, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-299">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="ff5e4-300">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-300">For example:</span></span>

> <span data-ttu-id="ff5e4-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="ff5e4-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="ff5e4-302">Per verificare che i dati sensibili siano stati caricati, eseguire il comando seguente nella finestra del prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-302">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="ff5e4-303">Viene visualizzato un elenco degli archivi dati e la data dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-303">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="ff5e4-304">Per visualizzare tutti i caricamenti di dati in un determinato archivio, eseguire il comando seguente in un prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-304">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="ff5e4-305">Procedere alla configurazione della procedura e della programmazione per  [Aggiornare il database delle informazioni sensibili](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-305">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="ff5e4-306">A questo punto si è pronti a usare la classificazione basata su EDM con i servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-306">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="ff5e4-307">Ad esempio, è possibile  [impostare un criterio DLP con la classificazione basata su EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-307">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="ff5e4-308">Aggiornare il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="ff5e4-308">Refreshing your sensitive information database</span></span>

<span data-ttu-id="ff5e4-309">È possibile aggiornare il database delle informazioni sensibili giornalmente o settimanalmente e lo strumento di caricamento di EDM può eseguire nuovamente l’hashing dei dati sensibili e quindi ricaricarli.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-309">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can re-hash the sensitive data and then reupload the hashed data.</span></span>

1. <span data-ttu-id="ff5e4-310">Determinare la procedura e la frequenza (giornaliera o settimanale) dell’aggiornamento del database delle informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-310">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="ff5e4-311">Esportare di nuovo i dati sensibili in un'app, come Microsoft Excel e salvare il file in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-311">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="ff5e4-312">Mantenere il nome e il percorso del file usati dopo aver seguito la procedura descritta in  [Eseguire hashing e caricare i dati sensibili](#hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-312">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="ff5e4-313">Se non sono state apportate modifiche alla struttura (nomi dei campi) del file CSV, non è necessario apportare modifiche al file dello schema del database quando si aggiornano i dati.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-313">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="ff5e4-314">Tuttavia, se è necessario apportare modifiche, accertarsi di modificare di conseguenza lo schema del database e il pacchetto delle regole.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-314">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="ff5e4-315">Usare l' [Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  per automatizzare i passaggi 2 e 3 nella procedura  [Eseguire hashing e caricare i dati sensibili](#hash-and-upload-the-sensitive-data) .</span><span class="sxs-lookup"><span data-stu-id="ff5e4-315">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="ff5e4-316">È possibile pianificare le attività in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-316">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="ff5e4-317">Metodo</span><span class="sxs-lookup"><span data-stu-id="ff5e4-317">Method</span></span>             | <span data-ttu-id="ff5e4-318">Soluzione</span><span class="sxs-lookup"><span data-stu-id="ff5e4-318">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="ff5e4-319">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff5e4-319">Windows PowerShell</span></span>     | <span data-ttu-id="ff5e4-320">Consultare la documentazione dell' [Utilità di pianificazione](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)  e lo  [script di PowerShell di esempio](#example-powershell-script-for-task-scheduler)  illustrato in questo articolo</span><span class="sxs-lookup"><span data-stu-id="ff5e4-320">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="ff5e4-321">API dell'Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="ff5e4-321">Task Scheduler API</span></span>     | <span data-ttu-id="ff5e4-322">Vedere la documentazione dell' [Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="ff5e4-322">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="ff5e4-323">Interfaccia utente Windows</span><span class="sxs-lookup"><span data-stu-id="ff5e4-323">Windows user interface</span></span> | <span data-ttu-id="ff5e4-324">In Windows, fare clic su  **Start** e digitare Utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-324">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="ff5e4-325">Quindi, nell'elenco dei risultati, fare clic con il pulsante destro del mouse sull' **Utilità di pianificazione** e scegliere  **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-325">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="ff5e4-326">Esempio di script di PowerShell per Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="ff5e4-326">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="ff5e4-327">Questa sezione include uno script di PowerShell di esempio che è possibile usare per pianificare le attività di hashing dei dati e il caricamento dei dati sui quali è stato eseguito l’hashing:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-327">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="ff5e4-328">Per pianificare l’hashing e il caricamento in un passaggio combinato</span><span class="sxs-lookup"><span data-stu-id="ff5e4-328">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="ff5e4-329">Per pianificare l'hashing e il caricamento in passaggi separati</span><span class="sxs-lookup"><span data-stu-id="ff5e4-329">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="ff5e4-330">Parte 3: usare la classificazione basata su EDM con i servizi cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff5e4-330">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="ff5e4-331">Questi percorsi sono supportati dai tipi di informazioni riservate EDM:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-331">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="ff5e4-332">DPL per Exchange Online (posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-332">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="ff5e4-333">OneDrive for Business (file)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-333">OneDrive for Business (files)</span></span>
- <span data-ttu-id="ff5e4-334">Microsoft Teams (conversazioni)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-334">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="ff5e4-335">DLP per SharePoint (file)</span><span class="sxs-lookup"><span data-stu-id="ff5e4-335">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="ff5e4-336">Criteri DPL di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ff5e4-336">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="ff5e4-337">I tipi di informazioni sensibili EDM per gli scenari seguenti sono in fase di sviluppo e non sono ancora disponibili:</span><span class="sxs-lookup"><span data-stu-id="ff5e4-337">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="ff5e4-338">Classificazione automatica di etichette di riservatezza ed etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="ff5e4-338">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="ff5e4-339">Creazione di un criterio DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="ff5e4-339">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="ff5e4-340">Passare al Centro sicurezza e conformità usando il [collegamento appropriato per l'abbonamento](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="ff5e4-340">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="ff5e4-341">Scegliere  **Prevenzione della perdita dei dati** \> **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-341">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="ff5e4-342">Scegliere  **Crea un criterio** \> **Personalizzato** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-342">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="ff5e4-343">Nella scheda  **Nome criterio** , specificare un nome e una descrizione, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-343">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="ff5e4-344">Nella scheda  **Scegli posizioni** , selezionare  **Consenti di scegliere posizioni specifiche**, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-344">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="ff5e4-345">Nella colonna  **Stato** , selezionare  **Posta elettronica di Exchange, Account di OneDrive, Chat di Teams e Messaggio del canale** , quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-345">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="ff5e4-346">Nella scheda  **Impostazioni criterio** , scegliere  **Usa impostazioni avanzate**, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-346">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="ff5e4-347">Scegliere  **+ Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-347">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="ff5e4-348">Nella sezione  **Nome** , specificare un nome e una descrizione per la regola.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-348">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="ff5e4-349">Nella sezione  **Condizioni** , nell'elenco  **+ Aggiungi una condizione** , scegliere  **Il contenuto include il tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-349">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Il contenuto contiene tipi di informazioni sensibili](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="ff5e4-351">Cercare il tipo di informazioni sensibili creato quando si configura il pacchetto delle regole, quindi scegliere  **+ Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="ff5e4-351">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="ff5e4-352">Quindi scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-352">Then choose **Done**.</span></span>

12. <span data-ttu-id="ff5e4-353">Infine selezionare le opzioni per la regola, come  **Notifiche utente**,  **Personalizzazioni utente**,  **Report degli eventi** e così via, quindi scegliere  **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-353">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="ff5e4-354">Nella scheda  **Impostazioni criterio** , esaminare le regole, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-354">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="ff5e4-355">Specificare se attivare subito il criterio, testarlo o mantenerlo disattivato.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-355">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="ff5e4-356">Quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-356">Then choose **Next**.</span></span>

15. <span data-ttu-id="ff5e4-357">Nella scheda  **Esamina le impostazioni** , esaminare il criterio.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-357">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="ff5e4-358">Apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-358">Make any needed changes.</span></span> <span data-ttu-id="ff5e4-359">Al termine, scegliere  **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-359">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="ff5e4-360">Il nuovo criterio DLP sarà attivo nel centro dati dopo circa un'ora.</span><span class="sxs-lookup"><span data-stu-id="ff5e4-360">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ff5e4-361">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="ff5e4-361">Related articles</span></span>

- [<span data-ttu-id="ff5e4-362">Definizioni delle entità tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="ff5e4-362">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="ff5e4-363">Tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="ff5e4-363">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="ff5e4-364">Panoramica sui criteri di DLP</span><span class="sxs-lookup"><span data-stu-id="ff5e4-364">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="ff5e4-365">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ff5e4-365">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="ff5e4-366">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="ff5e4-366">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

