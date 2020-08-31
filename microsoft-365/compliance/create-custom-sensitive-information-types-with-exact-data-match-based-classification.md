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
ms.openlocfilehash: f4bbbe8726370297e9ef6317cd468789bb3b3bfe
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300434"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="897dd-103">Creare tipi di informazioni sensibili personalizzati con classificazione esatta basata su Exact Data Match</span><span class="sxs-lookup"><span data-stu-id="897dd-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="897dd-104">[I tipi di informazioni riservate personalizzati](custom-sensitive-info-types.md) vengono usate per identificare gli elementi sensibili in modo che sia possibile impedire la condivisione inavvertita o inappropriata.</span><span class="sxs-lookup"><span data-stu-id="897dd-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="897dd-105">È possibile definire un tipo di informazioni sensibile personalizzato basato su:</span><span class="sxs-lookup"><span data-stu-id="897dd-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="897dd-106">criteri</span><span class="sxs-lookup"><span data-stu-id="897dd-106">patterns</span></span>
- <span data-ttu-id="897dd-107">evidenza di parole chiave, ad esempio  *dipendente*, *badge*, o *ID*</span><span class="sxs-lookup"><span data-stu-id="897dd-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="897dd-108">vicinanza del carattere all'evidenza in un modello specifico</span><span class="sxs-lookup"><span data-stu-id="897dd-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="897dd-109">livello di probabilità</span><span class="sxs-lookup"><span data-stu-id="897dd-109">confidence levels</span></span>

 <span data-ttu-id="897dd-110">Questi tipi di informazioni sensibili personalizzati soddisfano le esigenze aziendali di molte organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="897dd-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="897dd-111">Ma cosa succede se si vuole un tipo di informazioni sensibili personalizzato che usi valori di dati esatti, anziché uno che trova le corrispondenze in base a criteri generici ?</span><span class="sxs-lookup"><span data-stu-id="897dd-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="897dd-112">Con la classificazione basata su Exact Data Match (EDM) è possibile creare un tipo di informazioni sensibili personalizzato che sia progettato per:</span><span class="sxs-lookup"><span data-stu-id="897dd-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="897dd-113">essere dinamico e aggiornabile</span><span class="sxs-lookup"><span data-stu-id="897dd-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="897dd-114">offrire maggiore scalabilità</span><span class="sxs-lookup"><span data-stu-id="897dd-114">be more scalable</span></span>
- <span data-ttu-id="897dd-115">produrre meno falsi positivi</span><span class="sxs-lookup"><span data-stu-id="897dd-115">result in fewer false-positives</span></span>
- <span data-ttu-id="897dd-116">usare dati sensibili strutturati</span><span class="sxs-lookup"><span data-stu-id="897dd-116">work with structured sensitive data</span></span>
- <span data-ttu-id="897dd-117">gestire le informazioni sensibili in modo più sicuro</span><span class="sxs-lookup"><span data-stu-id="897dd-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="897dd-118">essere usato con più servizi cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="897dd-118">be used with several Microsoft cloud services</span></span>

![Classificazione basata su EDM](../media/EDMClassification.png)

<span data-ttu-id="897dd-120">La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="897dd-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="897dd-121">Il database può essere aggiornato giornalmente e può contenere un massimo di 100 milioni di righe di dati.</span><span class="sxs-lookup"><span data-stu-id="897dd-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="897dd-122">I dipendenti, i pazienti o i clienti vanno e vengono e i record cambiano, i tipi di informazioni sensibili personalizzati rimangono aggiornati e disponibili.</span><span class="sxs-lookup"><span data-stu-id="897dd-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="897dd-123">È anche possibile usare una classificazione basata su EDM con criteri, ad esempio i  [criteri di prevenzione della perdita dei dati ](data-loss-prevention-policies.md) (DLP) o i  [criteri dei file di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="897dd-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="897dd-124">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte per le lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="897dd-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="897dd-125">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="897dd-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="897dd-126">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="897dd-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="897dd-127">Coreano</span><span class="sxs-lookup"><span data-stu-id="897dd-127">Korean</span></span>
> - <span data-ttu-id="897dd-128">Giapponese</span><span class="sxs-lookup"><span data-stu-id="897dd-128">Japanese</span></span>
> 
><span data-ttu-id="897dd-129">Questa versione di anteprima è disponibile solo nel cloud commerciale e l'implementazione è limitata ai paesi o alle aree geografiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="897dd-129">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="897dd-130">Giappone</span><span class="sxs-lookup"><span data-stu-id="897dd-130">Japan</span></span>
> - <span data-ttu-id="897dd-131">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="897dd-131">Korea</span></span>
> - <span data-ttu-id="897dd-132">Cina</span><span class="sxs-lookup"><span data-stu-id="897dd-132">China</span></span>
> - <span data-ttu-id="897dd-133">RAS di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="897dd-133">Hong Kong</span></span>
> - <span data-ttu-id="897dd-134">RAS di Macao</span><span class="sxs-lookup"><span data-stu-id="897dd-134">Macau</span></span>
> - <span data-ttu-id="897dd-135">Taiwan</span><span class="sxs-lookup"><span data-stu-id="897dd-135">Taiwan</span></span>
>
><span data-ttu-id="897dd-136">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="897dd-136">This support is available for sensitive information types.</span></span> <span data-ttu-id="897dd-137">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="897dd-137">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="897dd-138">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="897dd-138">Required licenses and permissions</span></span>

<span data-ttu-id="897dd-139">È necessario essere un amministratore globale, di conformità o di Exchange Online per eseguire le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="897dd-139">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="897dd-140">Per ulteriori informazioni sulle autorizzazioni DLP, vedere  [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="897dd-140">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="897dd-141">La classificazione basata su EDM è inclusa negli abbonamenti</span><span class="sxs-lookup"><span data-stu-id="897dd-141">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="897dd-142">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="897dd-142">Office 365 E5</span></span>
- <span data-ttu-id="897dd-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="897dd-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="897dd-144">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="897dd-144">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="897dd-145">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="897dd-145">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="897dd-146">Collegamenti a portali per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="897dd-146">Portal links for your subscription</span></span>


|<span data-ttu-id="897dd-147">Portale</span><span class="sxs-lookup"><span data-stu-id="897dd-147">Portal</span></span>  |<span data-ttu-id="897dd-148">Tutto il mondo/GCC</span><span class="sxs-lookup"><span data-stu-id="897dd-148">World Wide/GCC</span></span>  |<span data-ttu-id="897dd-149">GCC-High</span><span class="sxs-lookup"><span data-stu-id="897dd-149">GCC-High</span></span>  |<span data-ttu-id="897dd-150">DOD</span><span class="sxs-lookup"><span data-stu-id="897dd-150">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="897dd-151">Office SCC</span><span class="sxs-lookup"><span data-stu-id="897dd-151">Office SCC</span></span>     |  <span data-ttu-id="897dd-152">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="897dd-152">protection.office.com</span></span>       |<span data-ttu-id="897dd-153">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="897dd-153">scc.office365.us</span></span>         |<span data-ttu-id="897dd-154">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="897dd-154">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="897dd-155">Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="897dd-155">Microsoft 365 Security center</span></span>     |<span data-ttu-id="897dd-156">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="897dd-156">security.microsoft.com</span></span>         |<span data-ttu-id="897dd-157">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="897dd-157">security.microsoft.us</span></span>         |<span data-ttu-id="897dd-158">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="897dd-158">security.apps.mil</span></span>|
|<span data-ttu-id="897dd-159">Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="897dd-159">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="897dd-160">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="897dd-160">compliance.microsoft.com</span></span>         |<span data-ttu-id="897dd-161">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="897dd-161">compliance.microsoft.us</span></span>         |<span data-ttu-id="897dd-162">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="897dd-162">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="897dd-163">Flusso di lavoro in breve</span><span class="sxs-lookup"><span data-stu-id="897dd-163">The work flow at a glance</span></span>

|<span data-ttu-id="897dd-164">Fase</span><span class="sxs-lookup"><span data-stu-id="897dd-164">Phase</span></span>  |<span data-ttu-id="897dd-165">Cosa serve</span><span class="sxs-lookup"><span data-stu-id="897dd-165">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="897dd-166">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="897dd-166">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="897dd-167">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="897dd-167">(As needed)</span></span><br/><span data-ttu-id="897dd-168">- [Modificare lo schema del database](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="897dd-168">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="897dd-169">- [Rimuovere lo schema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="897dd-169">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="897dd-170">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-170">- Read access to the sensitive data</span></span><br/><span data-ttu-id="897dd-171">- Schema del database nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="897dd-171">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="897dd-172">- Pacchetto di regole nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="897dd-172">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="897dd-173">- Autorizzazioni di amministratore al Centro sicurezza e conformità (utilizzando PowerShell)</span><span class="sxs-lookup"><span data-stu-id="897dd-173">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="897dd-174">Parte 2: Hash e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-174">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="897dd-175">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="897dd-175">(As needed)</span></span><br/>[<span data-ttu-id="897dd-176">Aggiornare i dati</span><span class="sxs-lookup"><span data-stu-id="897dd-176">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="897dd-177">- Gruppo di sicurezza personalizzato e account utente</span><span class="sxs-lookup"><span data-stu-id="897dd-177">- Custom security group and user account</span></span><br/><span data-ttu-id="897dd-178">- Accesso come amministratore locale al computer con l’Agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="897dd-178">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="897dd-179">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-179">- Read access to the sensitive data</span></span><br/><span data-ttu-id="897dd-180">- Procedura e programmazione per l'aggiornamento dei dati</span><span class="sxs-lookup"><span data-stu-id="897dd-180">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="897dd-181">Parte 3: usare la classificazione basata su EDM con i servizi Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="897dd-181">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="897dd-182">- Abbonamento a Microsoft 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="897dd-182">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="897dd-183">- Funzionalità della classificazione basata su EDM abilitata</span><span class="sxs-lookup"><span data-stu-id="897dd-183">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="897dd-184">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="897dd-184">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="897dd-185">L’impostazione e la configurazione di una classificazione basata su EDM implica:</span><span class="sxs-lookup"><span data-stu-id="897dd-185">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="897dd-186">Salvare dei dati sensibili in formato .csv</span><span class="sxs-lookup"><span data-stu-id="897dd-186">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="897dd-187">Definire lo schema del database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-187">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="897dd-188">Creare un pacchetto di regole</span><span class="sxs-lookup"><span data-stu-id="897dd-188">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="897dd-189">Salvare dei dati sensibili in formato .csv</span><span class="sxs-lookup"><span data-stu-id="897dd-189">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="897dd-190">Identificare le informazioni sensibili da usare.</span><span class="sxs-lookup"><span data-stu-id="897dd-190">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="897dd-191">Esportare i dati in un'app, come Microsoft Excel e salvare il file in formato .csv.</span><span class="sxs-lookup"><span data-stu-id="897dd-191">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="897dd-192">Il file di dati può includere al massimo:</span><span class="sxs-lookup"><span data-stu-id="897dd-192">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="897dd-193">Fino a 100 milioni di righe di dati sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-193">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="897dd-194">Fino a 32 colonne (campi) per origine dati</span><span class="sxs-lookup"><span data-stu-id="897dd-194">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="897dd-195">Fino a 5 colonne (campi) contrassegnate come ricercabile</span><span class="sxs-lookup"><span data-stu-id="897dd-195">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="897dd-196">Strutturare i dati sensibili nel file .csv in modo che la prima riga includa i nomi dei campi usati per la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="897dd-196">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="897dd-197">Nel file .csv potrebbero essere presenti nomi di campo, come "ssn", "birthdate", "firstname", "lastname".</span><span class="sxs-lookup"><span data-stu-id="897dd-197">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="897dd-198">I nomi delle intestazioni di colonna non possono includere spazi o caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="897dd-198">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="897dd-199">Ad esempio, il file .cvs di esempio usato in questo articoloè denominato *PatientRecords. csv*e le relative colonne includono *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*e così via.</span><span class="sxs-lookup"><span data-stu-id="897dd-199">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="897dd-200">Definire lo schema per il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-200">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="897dd-201">Definire lo schema per il database delle informazioni sensibili nel formato .xml (come riportato nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="897dd-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="897dd-202">Assegnare al file dello schema il nome  **edm.xml** e configurarlo in modo che per ogni colonna del database sia presente una riga che usi la sintassi:</span><span class="sxs-lookup"><span data-stu-id="897dd-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="897dd-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="897dd-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="897dd-204">Usare i nomi delle colonne per i valori  *Field name* .</span><span class="sxs-lookup"><span data-stu-id="897dd-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="897dd-205">Usare  *searchable="true"*  per un massimo di 5 campi che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="897dd-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="897dd-206">Almeno un campo deve essere disponibile per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="897dd-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="897dd-207">Ad esempio, il seguente file .xml definisce lo schema per un database dei record dei pazienti, con cinque campi specificati come ricercabili:  *PatientID*,  *MRN*,  *SSN*,  *Phone* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="897dd-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="897dd-208">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="897dd-208">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="897dd-209">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="897dd-209">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="897dd-210">Per caricare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="897dd-210">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="897dd-211">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="897dd-211">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="897dd-212">Conferma</span><span class="sxs-lookup"><span data-stu-id="897dd-212">Confirm</span></span>
      >
      > <span data-ttu-id="897dd-213">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="897dd-213">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="897dd-214">Viene importato il nuovo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="897dd-214">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="897dd-215">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="897dd-215">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="897dd-216">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 5, usare questo cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="897dd-216">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="897dd-217">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="897dd-217">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="897dd-218">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="897dd-218">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="897dd-219">Configurare un pacchetto di regole</span><span class="sxs-lookup"><span data-stu-id="897dd-219">Set up a rule package</span></span>

1. <span data-ttu-id="897dd-220">Creare un pacchetto di regole nel formato .xml (con codifica Unicode), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="897dd-220">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="897dd-221">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="897dd-221">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="897dd-222">Quando si configura il pacchetto di regole, assicurarsi di fare riferimento correttamente al file .csv e al file **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="897dd-222">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="897dd-223">È possibile copiare, modificare e usare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="897dd-223">You can copy, modify, and use our example.</span></span> <span data-ttu-id="897dd-224">In questo XML di esempio è necessario personalizzare i campi seguenti per creare un tipo di informazioni sensibili di EDM:</span><span class="sxs-lookup"><span data-stu-id="897dd-224">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="897dd-225">**RulePack id & ExactMatch id**: usare  [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  per generare un GUID.</span><span class="sxs-lookup"><span data-stu-id="897dd-225">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="897dd-226">**Datastore**: questo campo specifica l'archivio dati di ricerca EDM da usare.</span><span class="sxs-lookup"><span data-stu-id="897dd-226">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="897dd-227">È possibile specificare il nome di un'origine dati di uno schema EDM configurato.</span><span class="sxs-lookup"><span data-stu-id="897dd-227">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="897dd-228">**idMatch**: questo campo punta all'elemento primario per EDM.</span><span class="sxs-lookup"><span data-stu-id="897dd-228">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="897dd-229">Matches: specifica il campo da usare nella ricerca esatta.</span><span class="sxs-lookup"><span data-stu-id="897dd-229">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="897dd-230">È possibile specificare il nome campo ricercabile nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="897dd-230">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="897dd-231">Classification: questo campo specifica la corrispondenza del tipo di informazioni sensibili che attiva la ricerca EDM.</span><span class="sxs-lookup"><span data-stu-id="897dd-231">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="897dd-232">È possibile specificare il nome o il GUID di una classificazione predefinita o personalizzata esistente.</span><span class="sxs-lookup"><span data-stu-id="897dd-232">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="897dd-233">**Match:** questo campo indica altre evidenze disponibili in prossimità di idMatch.</span><span class="sxs-lookup"><span data-stu-id="897dd-233">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="897dd-234">Matches: è possibile specificare qualsiasi nome campo nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="897dd-234">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="897dd-235">**Resource:** questa sezione specifica il nome e la descrizione per il tipo di informazioni sensibili in più impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="897dd-235">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="897dd-236">idRef: è possibile specificare il GUID per l'ID ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="897dd-236">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="897dd-237">Name e descriptions: personalizzare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="897dd-237">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="897dd-238">Per caricare il pacchetto di regole, eseguire i seguenti cmdlet di PowerShell, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="897dd-238">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="897dd-239">A questo punto è stata configurata la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="897dd-239">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="897dd-240">Il passaggio successivo consiste nell'eseguire l’hashing dei i dati sensibili e poi di caricare gli hash per indicizzarli.</span><span class="sxs-lookup"><span data-stu-id="897dd-240">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="897dd-241">Usare la procedura precedente in cui lo schema di PatientRecords definisce cinque campi come ricercabili:  *PatientID*,  *MRN*,  *SSN*,  *Phone* e  *DOB*.</span><span class="sxs-lookup"><span data-stu-id="897dd-241">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="897dd-242">Il pacchetto di regole di esempio include questi campi e fa riferimento al file di schema del database (**edm.xml**), con un unico elemento  *ExactMatch*  per ogni campo ricercabile.</span><span class="sxs-lookup"><span data-stu-id="897dd-242">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="897dd-243">Considerare l'elemento ExactMatch seguente:</span><span class="sxs-lookup"><span data-stu-id="897dd-243">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="897dd-244">Utilizzando l'esempio proposto, osservare:</span><span class="sxs-lookup"><span data-stu-id="897dd-244">In this example, note that:</span></span>

- <span data-ttu-id="897dd-245">Il nome dataStore fa riferimento al file .csv creato in precedenza:  **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="897dd-245">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="897dd-246">Il valore idMatch fa riferimento a un campo ricercabile elencato nel file dello schema del database:  **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="897dd-246">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="897dd-247">Il valore di classificazione fa riferimento a un tipo di informazioni sensibili esistente o personalizzato:  **classification = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="897dd-247">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="897dd-248">In questo caso, viene usato il tipo di informazioni sensibili esistente del Numero di previdenza sociale degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="897dd-248">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="897dd-249">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="897dd-249">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="897dd-250">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="897dd-250">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="897dd-251">Modificare lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="897dd-251">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="897dd-252">Se si vogliono apportare modifiche al file **edm.xml**, ad esempio modificare i campi usati per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="897dd-252">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="897dd-253">Modificare il file **edm.xml** (il file descritto nella sezione  [Definire lo schema](#define-the-schema-for-your-database-of-sensitive-information)  di questo articolo).</span><span class="sxs-lookup"><span data-stu-id="897dd-253">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="897dd-254">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="897dd-254">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="897dd-255">Per aggiornare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="897dd-255">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="897dd-256">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="897dd-256">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="897dd-257">Conferma</span><span class="sxs-lookup"><span data-stu-id="897dd-257">Confirm</span></span>
      >
      > <span data-ttu-id="897dd-258">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="897dd-258">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="897dd-259">Viene aggiornato lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="897dd-259">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="897dd-260">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="897dd-260">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="897dd-261">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 3, usare questo cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="897dd-261">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="897dd-262">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="897dd-262">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="897dd-263">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="897dd-263">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="897dd-264">Rimuovere lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="897dd-264">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="897dd-265">(Se necessario) Se si vuole rimuovere lo schema usato per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="897dd-265">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="897dd-266">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="897dd-266">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="897dd-267">Eseguire i cmdlet di PowerShell seguenti, sostituendo il nome dell'archivio dati di "patient records" con quello che si vuole rimuovere:</span><span class="sxs-lookup"><span data-stu-id="897dd-267">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="897dd-268">Verrà richiesto di confermare:</span><span class="sxs-lookup"><span data-stu-id="897dd-268">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="897dd-269">Conferma</span><span class="sxs-lookup"><span data-stu-id="897dd-269">Confirm</span></span>
      >
      > <span data-ttu-id="897dd-270">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="897dd-270">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="897dd-271">Viene rimosso lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="897dd-271">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="897dd-272">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="897dd-272">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="897dd-273">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 2, usare questo cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="897dd-273">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="897dd-274">Parte 2: eseguire hashing e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-274">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="897dd-275">In questa fase è possibile impostare un gruppo di sicurezza personalizzato e un account utente e configurare lo strumento Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="897dd-275">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="897dd-276">Successivamente, è possibile usare lo strumento per eseguire l’hashing con i valori salt dei dati sensibili, e poi caricarli.</span><span class="sxs-lookup"><span data-stu-id="897dd-276">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="897dd-277">L’hashing e il caricamento può essere eseguito con un computer oppure è possibile separare la procedura di hashing da quello di caricamento per una maggiore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="897dd-277">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="897dd-278">Se si vuole eseguire l'hashing e il caricamento da un computer, è necessario farlo da uno che può connettersi direttamente al tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="897dd-278">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="897dd-279">È necessario che i file dati di testo sensibili non crittografati siano presenti sul computer per l'hashing.</span><span class="sxs-lookup"><span data-stu-id="897dd-279">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="897dd-280">Se non si vuole esporre file dati di testo sensibili non crittografati, è possibile inserirlo in un computer in un percorso sicuro e quindi copiare il file hash e il file salt in un computer che può connettersi direttamente al tenant di Microsoft 365 per il caricamento.</span><span class="sxs-lookup"><span data-stu-id="897dd-280">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="897dd-281">In questo scenario sarà necessario l’EDMUploadAgent su entrambi i computer.</span><span class="sxs-lookup"><span data-stu-id="897dd-281">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="897dd-282">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="897dd-282">Prerequisites</span></span>

- <span data-ttu-id="897dd-283">un account aziendale o dell'Istituto di istruzione per Microsoft 365, che verrà aggiunto al gruppo di sicurezza **EDM\_datauploaders**</span><span class="sxs-lookup"><span data-stu-id="897dd-283">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="897dd-284">un computer Windows 10 o Windows Server 2016 con versione .NET 4.6.2 per l'esecuzione di EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="897dd-284">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="897dd-285">una directory nel computer di caricamento per:</span><span class="sxs-lookup"><span data-stu-id="897dd-285">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="897dd-286">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="897dd-286">EDMUploadAgent</span></span>
    - <span data-ttu-id="897dd-287">il file di elemento sensibile in formato CSV **PatientRecords. csv** negli esempi</span><span class="sxs-lookup"><span data-stu-id="897dd-287">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="897dd-288">e i file di output hash e salt</span><span class="sxs-lookup"><span data-stu-id="897dd-288">and the output hash and salt files</span></span>
    - <span data-ttu-id="897dd-289">il nome del datastore dal file **edm.xml**, for quest’esempio `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="897dd-289">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="897dd-290">Impostare il gruppo di sicurezza e l'account utente</span><span class="sxs-lookup"><span data-stu-id="897dd-290">Set up the security group and user account</span></span>

1. <span data-ttu-id="897dd-291">Come amministratore globale, passare all'interfaccia di amministrazione usando il [collegamento appropriato per l'abbonamento in uso](#portal-links-for-your-subscription) e [creare un gruppo di sicurezza](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) denominato **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="897dd-291">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="897dd-292">Aggiungere uno o più utenti al gruppo di sicurezza  **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="897dd-292">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="897dd-293">(Questi utenti gestiranno il database delle informazioni sensibili.)</span><span class="sxs-lookup"><span data-stu-id="897dd-293">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="897dd-294">Hashing e caricamento da un computer</span><span class="sxs-lookup"><span data-stu-id="897dd-294">Hash and upload from one computer</span></span>

<span data-ttu-id="897dd-295">Il computer deve avere accesso diretto al tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="897dd-295">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="897dd-296">Prima di iniziare questa procedura, verificare di essere un membro del gruppo di sicurezza  **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="897dd-296">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="897dd-297">Collegamenti all'agente di caricamento EDM per tipo di abbonamento</span><span class="sxs-lookup"><span data-stu-id="897dd-297">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="897dd-298">Commerciale + GCC</span><span class="sxs-lookup"><span data-stu-id="897dd-298">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="897dd-299">GCC-High</span><span class="sxs-lookup"><span data-stu-id="897dd-299">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="897dd-300">DoD</span><span class="sxs-lookup"><span data-stu-id="897dd-300">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="897dd-301">Creare una directory di lavoro per EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="897dd-301">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="897dd-302">Ad esempio, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="897dd-302">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="897dd-303">Posizionare il **file PatientRecords.csv** lì.</span><span class="sxs-lookup"><span data-stu-id="897dd-303">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="897dd-304">Scaricare e installare l'[agente di caricamento EDM](#links-to-edm-upload-agent-by-subscription-type) appropriato per l'abbonamento nella directory creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="897dd-304">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="897dd-305">L’EDMUploadAgent nei collegamenti precedenti è stato aggiornato in modo da aggiungere automaticamente un valore salt ai dati hash.</span><span class="sxs-lookup"><span data-stu-id="897dd-305">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="897dd-306">In alternativa, è possibile specificare un valore salt personalizzato.</span><span class="sxs-lookup"><span data-stu-id="897dd-306">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="897dd-307">Dopo aver usato questa versione, non sarà possibile usare la versione precedente di EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="897dd-307">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="897dd-308">È possibile caricare i dati con EDMUploadAgent in qualsiasi archivio dati solo due volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="897dd-308">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="897dd-309">Per ottenere un elenco dei parametri di comando supportati, eseguire l'agente senza argomenti,</span><span class="sxs-lookup"><span data-stu-id="897dd-309">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="897dd-310">ad esempio "EdmUploadAgent.exe".</span><span class="sxs-lookup"><span data-stu-id="897dd-310">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="897dd-311">Autorizzare l'agente di caricamento EDM, aprire il prompt dei comandi di Windows (come amministratore), passare alla directory **C:\EDM\Data** ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="897dd-311">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="897dd-312">Accedere con l'account aziendale o dell'istituto di istruzione per Microsoft 365 aggiunto al gruppo di sicurezza EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="897dd-312">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="897dd-313">Le informazioni del tenant vengono estratte dall'account utente per creare la connessione.</span><span class="sxs-lookup"><span data-stu-id="897dd-313">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="897dd-314">Per eseguire l’hashing e caricare i dati sensibili, eseguire il seguente comando nella finestra dei prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="897dd-314">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="897dd-315">Esempio: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="897dd-315">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="897dd-316">Verrà automaticamente aggiunto un valore salt generato casualmente all'hash per una maggiore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="897dd-316">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="897dd-317">Facoltativamente, se si vuole usare il proprio valore salt, aggiungere il **/Salt <saltvalue>** al comando.</span><span class="sxs-lookup"><span data-stu-id="897dd-317">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="897dd-318">Questo valore deve avere una lunghezza 64 caratteri e può contenere solo caratteri a-z e i caratteri 0-9.</span><span class="sxs-lookup"><span data-stu-id="897dd-318">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="897dd-319">Per controllare lo stato di caricamento, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="897dd-319">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="897dd-320">Esempio: **EdmUploadAgent. exe/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="897dd-320">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="897dd-321">Cercare lo stato in **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="897dd-321">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="897dd-322">Controllare di nuovo, ogni due minuti, finché lo stato non cambia in **Completato**.</span><span class="sxs-lookup"><span data-stu-id="897dd-322">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="897dd-323">Una volta che lo stato è completato, i dati EDM sono pronti per l'uso.</span><span class="sxs-lookup"><span data-stu-id="897dd-323">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="897dd-324">Separare hashing e caricamento</span><span class="sxs-lookup"><span data-stu-id="897dd-324">Separate Hash and upload</span></span>

<span data-ttu-id="897dd-325">Eseguire l’hashing in un computer in un ambiente protetto.</span><span class="sxs-lookup"><span data-stu-id="897dd-325">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="897dd-326">Eseguire il comando seguente nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="897dd-326">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="897dd-327">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="897dd-327">For example:</span></span>

> <span data-ttu-id="897dd-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="897dd-328">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="897dd-329">Verrà generato un file hash e un file salt con queste estensioni se non è stata specificata l'opzione **/Salt <saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="897dd-329">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="897dd-330">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="897dd-330">.EdmHash</span></span>
- <span data-ttu-id="897dd-331">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="897dd-331">.EdmSalt</span></span>

2. <span data-ttu-id="897dd-332">Copiare i file in modo sicuro nel computer che si userà per caricare il file CSV degli elementi sensibili (PatientRecords) nel tenant.</span><span class="sxs-lookup"><span data-stu-id="897dd-332">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="897dd-333">Per caricare i dati su cui è stato eseguito l’hashing, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="897dd-333">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="897dd-334">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="897dd-334">For example:</span></span>

> <span data-ttu-id="897dd-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="897dd-335">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="897dd-336">Per verificare che i dati sensibili siano stati caricati, eseguire il comando seguente nella finestra del prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="897dd-336">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="897dd-337">Viene visualizzato un elenco degli archivi dati e la data dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="897dd-337">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="897dd-338">Per visualizzare tutti i caricamenti di dati in un determinato archivio, eseguire il comando seguente in un prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="897dd-338">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="897dd-339">Procedere alla configurazione della procedura e della programmazione per  [Aggiornare il database delle informazioni sensibili](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="897dd-339">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="897dd-340">A questo punto si è pronti a usare la classificazione basata su EDM con i servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="897dd-340">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="897dd-341">Ad esempio, è possibile  [impostare un criterio DLP con la classificazione basata su EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="897dd-341">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="897dd-342">Aggiornare il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="897dd-342">Refreshing your sensitive information database</span></span>

<span data-ttu-id="897dd-343">È possibile aggiornare il database delle informazioni sensibili giornalmente e lo strumento di caricamento di EDM può reindicizzare i dati sensibili e quindi ricaricarli.</span><span class="sxs-lookup"><span data-stu-id="897dd-343">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="897dd-344">Determinare la procedura e la frequenza (giornaliera o settimanale) dell’aggiornamento del database delle informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="897dd-344">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="897dd-345">Esportare di nuovo i dati sensibili in un'app, come Microsoft Excel e salvare il file in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="897dd-345">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="897dd-346">Mantenere il nome e il percorso del file usati dopo aver seguito la procedura descritta in  [Eseguire hashing e caricare i dati sensibili](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="897dd-346">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="897dd-347">Se non sono state apportate modifiche alla struttura (nomi dei campi) del file CSV, non è necessario apportare modifiche al file dello schema del database quando si aggiornano i dati.</span><span class="sxs-lookup"><span data-stu-id="897dd-347">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="897dd-348">Tuttavia, se è necessario apportare modifiche, accertarsi di modificare di conseguenza lo schema del database e il pacchetto delle regole.</span><span class="sxs-lookup"><span data-stu-id="897dd-348">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="897dd-349">Usare l' [Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  per automatizzare i passaggi 2 e 3 nella procedura  [Eseguire hashing e caricare i dati sensibili](#part-2-hash-and-upload-the-sensitive-data) .</span><span class="sxs-lookup"><span data-stu-id="897dd-349">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="897dd-350">È possibile pianificare le attività in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="897dd-350">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="897dd-351">Metodo</span><span class="sxs-lookup"><span data-stu-id="897dd-351">Method</span></span>             | <span data-ttu-id="897dd-352">Soluzione</span><span class="sxs-lookup"><span data-stu-id="897dd-352">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="897dd-353">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="897dd-353">Windows PowerShell</span></span>     | <span data-ttu-id="897dd-354">Consultare la documentazione dell' [Utilità di pianificazione](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)  e lo  [script di PowerShell di esempio](#example-powershell-script-for-task-scheduler)  illustrato in questo articolo</span><span class="sxs-lookup"><span data-stu-id="897dd-354">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="897dd-355">API dell'Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="897dd-355">Task Scheduler API</span></span>     | <span data-ttu-id="897dd-356">Vedere la documentazione dell' [Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="897dd-356">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="897dd-357">Interfaccia utente Windows</span><span class="sxs-lookup"><span data-stu-id="897dd-357">Windows user interface</span></span> | <span data-ttu-id="897dd-358">In Windows, fare clic su  **Start** e digitare Utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="897dd-358">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="897dd-359">Quindi, nell'elenco dei risultati, fare clic con il pulsante destro del mouse sull' **Utilità di pianificazione** e scegliere  **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="897dd-359">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="897dd-360">Esempio di script di PowerShell per Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="897dd-360">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="897dd-361">Questa sezione include uno script di PowerShell di esempio che è possibile usare per pianificare le attività di hashing dei dati e il caricamento dei dati sui quali è stato eseguito l’hashing:</span><span class="sxs-lookup"><span data-stu-id="897dd-361">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="897dd-362">Per pianificare l’hashing e il caricamento in un passaggio combinato</span><span class="sxs-lookup"><span data-stu-id="897dd-362">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="897dd-363">Per pianificare l'hashing e il caricamento in passaggi separati</span><span class="sxs-lookup"><span data-stu-id="897dd-363">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="897dd-364">Parte 3: usare la classificazione basata su EDM con i servizi cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="897dd-364">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="897dd-365">Questi percorsi sono supportati dai tipi di informazioni riservate EDM:</span><span class="sxs-lookup"><span data-stu-id="897dd-365">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="897dd-366">DPL per Exchange Online (posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="897dd-366">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="897dd-367">OneDrive for Business (file)</span><span class="sxs-lookup"><span data-stu-id="897dd-367">OneDrive for Business (files)</span></span>
- <span data-ttu-id="897dd-368">Microsoft Teams (conversazioni)</span><span class="sxs-lookup"><span data-stu-id="897dd-368">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="897dd-369">DLP per SharePoint (file)</span><span class="sxs-lookup"><span data-stu-id="897dd-369">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="897dd-370">Criteri DPL di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="897dd-370">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="897dd-371">I tipi di informazioni sensibili EDM per gli scenari seguenti sono in fase di sviluppo e non sono ancora disponibili:</span><span class="sxs-lookup"><span data-stu-id="897dd-371">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="897dd-372">Classificazione automatica di etichette di riservatezza ed etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="897dd-372">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="897dd-373">Creazione di un criterio DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="897dd-373">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="897dd-374">Passare al Centro sicurezza e conformità usando il [collegamento appropriato per l'abbonamento](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="897dd-374">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="897dd-375">Scegliere  **Prevenzione della perdita dei dati** \> **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="897dd-375">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="897dd-376">Scegliere  **Crea un criterio** \> **Personalizzato** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="897dd-376">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="897dd-377">Nella scheda  **Nome criterio** , specificare un nome e una descrizione, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="897dd-377">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="897dd-378">Nella scheda  **Scegli posizioni** , selezionare  **Consenti di scegliere posizioni specifiche**, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="897dd-378">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="897dd-379">Nella colonna  **Stato** , selezionare  **Posta elettronica di Exchange, Account di OneDrive, Chat di Teams e Messaggio del canale** , quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="897dd-379">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="897dd-380">Nella scheda  **Impostazioni criterio** , scegliere  **Usa impostazioni avanzate**, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="897dd-380">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="897dd-381">Scegliere  **+ Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="897dd-381">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="897dd-382">Nella sezione  **Nome** , specificare un nome e una descrizione per la regola.</span><span class="sxs-lookup"><span data-stu-id="897dd-382">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="897dd-383">Nella sezione  **Condizioni** , nell'elenco  **+ Aggiungi una condizione** , scegliere  **Il contenuto include il tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="897dd-383">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Il contenuto contiene tipi di informazioni sensibili](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="897dd-385">Cercare il tipo di informazioni sensibili creato quando si configura il pacchetto delle regole, quindi scegliere  **+ Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="897dd-385">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="897dd-386">Quindi scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="897dd-386">Then choose **Done**.</span></span>

12. <span data-ttu-id="897dd-387">Infine selezionare le opzioni per la regola, come  **Notifiche utente**,  **Personalizzazioni utente**,  **Report degli eventi** e così via, quindi scegliere  **Salva**.</span><span class="sxs-lookup"><span data-stu-id="897dd-387">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="897dd-388">Nella scheda  **Impostazioni criterio** , esaminare le regole, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="897dd-388">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="897dd-389">Specificare se attivare subito il criterio, testarlo o mantenerlo disattivato.</span><span class="sxs-lookup"><span data-stu-id="897dd-389">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="897dd-390">Quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="897dd-390">Then choose **Next**.</span></span>

15. <span data-ttu-id="897dd-391">Nella scheda  **Esamina le impostazioni** , esaminare il criterio.</span><span class="sxs-lookup"><span data-stu-id="897dd-391">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="897dd-392">Apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="897dd-392">Make any needed changes.</span></span> <span data-ttu-id="897dd-393">Al termine, scegliere  **Crea**.</span><span class="sxs-lookup"><span data-stu-id="897dd-393">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="897dd-394">Il nuovo criterio DLP sarà attivo nel centro dati dopo circa un'ora.</span><span class="sxs-lookup"><span data-stu-id="897dd-394">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="897dd-395">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="897dd-395">Related articles</span></span>

- [<span data-ttu-id="897dd-396">Definizioni delle entità tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="897dd-396">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="897dd-397">Tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="897dd-397">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="897dd-398">Panoramica sui criteri di DLP</span><span class="sxs-lookup"><span data-stu-id="897dd-398">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="897dd-399">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="897dd-399">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="897dd-400">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="897dd-400">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

