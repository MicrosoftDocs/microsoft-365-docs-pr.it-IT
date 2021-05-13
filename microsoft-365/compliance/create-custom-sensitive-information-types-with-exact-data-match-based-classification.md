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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0bb75db5b6bb1f3a3b18033b5327f014748f6512
ms.sourcegitcommit: aff2331f9a3f22591f8ace1a646809969d28c120
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52464394"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="3fb9a-103">Creare tipi di informazioni sensibili personalizzati con classificazione esatta basata su Exact Data Match</span><span class="sxs-lookup"><span data-stu-id="3fb9a-103">Create custom sensitive information types with Exact Data Match based classification</span></span>



<span data-ttu-id="3fb9a-104">I[ tipi di informazioni riservate personalizzati](sensitive-information-type-learn-about.md)vengono usate per identificare gli elementi sensibili in modo che sia possibile impedire la condivisione inavvertita o inappropriata.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="3fb9a-105">È possibile definire un tipo di informazioni sensibile personalizzato basato su:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="3fb9a-106">criteri</span><span class="sxs-lookup"><span data-stu-id="3fb9a-106">patterns</span></span>
- <span data-ttu-id="3fb9a-107">evidenza di parole chiave, ad esempio *dipendente*,*badge*, o *ID*</span><span class="sxs-lookup"><span data-stu-id="3fb9a-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="3fb9a-108">vicinanza del carattere all'evidenza in un modello specifico</span><span class="sxs-lookup"><span data-stu-id="3fb9a-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="3fb9a-109">livello di probabilità</span><span class="sxs-lookup"><span data-stu-id="3fb9a-109">confidence levels</span></span>

 <span data-ttu-id="3fb9a-110">Questi tipi di informazioni sensibili personalizzati soddisfano le esigenze aziendali di molte organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="3fb9a-111">Ma cosa succede se si vuole un tipo di informazioni sensibili personalizzato che usi valori di dati esatti, anziché uno che trova le corrispondenze in base a criteri generici?</span><span class="sxs-lookup"><span data-stu-id="3fb9a-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="3fb9a-112">Con la classificazione basata su Exact Data Match (EDM) è possibile creare un tipo di informazioni sensibili personalizzato che sia progettato per:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="3fb9a-113">essere dinamico e facilmente aggiornabile</span><span class="sxs-lookup"><span data-stu-id="3fb9a-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="3fb9a-114">offrire maggiore scalabilità</span><span class="sxs-lookup"><span data-stu-id="3fb9a-114">be more scalable</span></span>
- <span data-ttu-id="3fb9a-115">produrre meno falsi positivi</span><span class="sxs-lookup"><span data-stu-id="3fb9a-115">result in fewer false-positives</span></span>
- <span data-ttu-id="3fb9a-116">usare dati sensibili strutturati</span><span class="sxs-lookup"><span data-stu-id="3fb9a-116">work with structured sensitive data</span></span>
- <span data-ttu-id="3fb9a-117">gestire le informazioni sensibili in modo più sicuro</span><span class="sxs-lookup"><span data-stu-id="3fb9a-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="3fb9a-118">essere usato con più servizi cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="3fb9a-118">be used with several Microsoft cloud services</span></span>

![Classificazione basata su EDM](../media/EDMClassification.png)

<span data-ttu-id="3fb9a-120">La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="3fb9a-121">Il database può essere aggiornato giornalmente e può contenere un massimo di 100 milioni di righe di dati.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="3fb9a-122">I dipendenti, i pazienti o i clienti vanno e vengono e i record cambiano, i tipi di informazioni sensibili personalizzati rimangono aggiornati e disponibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="3fb9a-123">È anche possibile usare una classificazione basata su EDM con criteri, ad esempio i [criteri di prevenzione della perdita dei dati](dlp-learn-about-dlp.md) o i [criteri dei file di Microsoft Cloud App Security](/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="3fb9a-124">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte nelle seguenti lingue:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-124">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="3fb9a-125">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="3fb9a-126">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="3fb9a-127">Coreano</span><span class="sxs-lookup"><span data-stu-id="3fb9a-127">Korean</span></span>
> - <span data-ttu-id="3fb9a-128">Giapponese</span><span class="sxs-lookup"><span data-stu-id="3fb9a-128">Japanese</span></span>
> 
> <span data-ttu-id="3fb9a-129">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="3fb9a-130">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
 

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="3fb9a-131">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="3fb9a-131">Required licenses and permissions</span></span>

<span data-ttu-id="3fb9a-132">È necessario essere un amministratore globale, di conformità o di Exchange Online per eseguire le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="3fb9a-133">Per ulteriori informazioni sulle autorizzazioni DLP, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="3fb9a-134">La classificazione basata su EDM è inclusa negli abbonamenti</span><span class="sxs-lookup"><span data-stu-id="3fb9a-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="3fb9a-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="3fb9a-135">Office 365 E5</span></span>
- <span data-ttu-id="3fb9a-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3fb9a-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="3fb9a-137">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3fb9a-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="3fb9a-138">Microsoft E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="3fb9a-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="3fb9a-139">Collegamenti a portali per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="3fb9a-139">Portal links for your subscription</span></span>


|<span data-ttu-id="3fb9a-140">Portale</span><span class="sxs-lookup"><span data-stu-id="3fb9a-140">Portal</span></span>  |<span data-ttu-id="3fb9a-141">Tutto il mondo/GCC</span><span class="sxs-lookup"><span data-stu-id="3fb9a-141">World Wide/GCC</span></span>  |<span data-ttu-id="3fb9a-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="3fb9a-142">GCC-High</span></span>  |<span data-ttu-id="3fb9a-143">DOD</span><span class="sxs-lookup"><span data-stu-id="3fb9a-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="3fb9a-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="3fb9a-144">Office SCC</span></span>     |  <span data-ttu-id="3fb9a-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="3fb9a-145">protection.office.com</span></span>       |<span data-ttu-id="3fb9a-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="3fb9a-146">scc.office365.us</span></span>         |<span data-ttu-id="3fb9a-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="3fb9a-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="3fb9a-148">Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fb9a-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="3fb9a-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3fb9a-149">security.microsoft.com</span></span>         |<span data-ttu-id="3fb9a-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="3fb9a-150">security.microsoft.us</span></span>         |<span data-ttu-id="3fb9a-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="3fb9a-151">security.apps.mil</span></span>|
|<span data-ttu-id="3fb9a-152">Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fb9a-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="3fb9a-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3fb9a-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="3fb9a-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="3fb9a-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="3fb9a-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="3fb9a-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="3fb9a-156">Flusso di lavoro in breve</span><span class="sxs-lookup"><span data-stu-id="3fb9a-156">The work flow at a glance</span></span>

|<span data-ttu-id="3fb9a-157">Fase</span><span class="sxs-lookup"><span data-stu-id="3fb9a-157">Phase</span></span>  |<span data-ttu-id="3fb9a-158">Cosa serve</span><span class="sxs-lookup"><span data-stu-id="3fb9a-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="3fb9a-159">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="3fb9a-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="3fb9a-160">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-160">(As needed)</span></span><br/><span data-ttu-id="3fb9a-161">- [Modificare lo schema del database](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="3fb9a-162">- [Rimuovere lo schema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="3fb9a-163">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="3fb9a-164">- Schema del database nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="3fb9a-165">- Pacchetto di regole nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="3fb9a-166">- Autorizzazioni di amministratore al Centro sicurezza e conformità (utilizzando PowerShell)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="3fb9a-167">Parte 2: Hash e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="3fb9a-168">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-168">(As needed)</span></span><br/>[<span data-ttu-id="3fb9a-169">Aggiornare i dati</span><span class="sxs-lookup"><span data-stu-id="3fb9a-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="3fb9a-170">- Gruppo di sicurezza personalizzato e account utente</span><span class="sxs-lookup"><span data-stu-id="3fb9a-170">- Custom security group and user account</span></span><br/><span data-ttu-id="3fb9a-171">- Accesso come amministratore locale al computer con l’Agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="3fb9a-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="3fb9a-172">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="3fb9a-173">- Procedura e programmazione per l'aggiornamento dei dati</span><span class="sxs-lookup"><span data-stu-id="3fb9a-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="3fb9a-174">Parte 3: usare la classificazione basata su EDM con i servizi Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="3fb9a-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="3fb9a-175">- Abbonamento a Microsoft 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="3fb9a-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="3fb9a-176">- Funzionalità della classificazione basata su EDM abilitata</span><span class="sxs-lookup"><span data-stu-id="3fb9a-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="3fb9a-177">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="3fb9a-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="3fb9a-178">L’impostazione e la configurazione di una classificazione basata su EDM implica:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="3fb9a-179">Salvare dei dati sensibili in formato .csv</span><span class="sxs-lookup"><span data-stu-id="3fb9a-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="3fb9a-180">Definire lo schema del database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="3fb9a-181">Creare un pacchetto di regole</span><span class="sxs-lookup"><span data-stu-id="3fb9a-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="3fb9a-182">Salvare dei dati sensibili in formato .csv</span><span class="sxs-lookup"><span data-stu-id="3fb9a-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="3fb9a-183">Identificare le informazioni sensibili da usare.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="3fb9a-184">Esportare i dati in un'app, come Microsoft Excel e salvare il file in formato .csv.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="3fb9a-185">Il file di dati può includere al massimo:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="3fb9a-186">Fino a 100 milioni di righe di dati sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="3fb9a-187">Fino a 32 colonne (campi) per origine dati</span><span class="sxs-lookup"><span data-stu-id="3fb9a-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="3fb9a-188">Fino a 5 colonne (campi) contrassegnate come ricercabile</span><span class="sxs-lookup"><span data-stu-id="3fb9a-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="3fb9a-189">Strutturare i dati sensibili nel file .csv in modo che la prima riga includa i nomi dei campi usati per la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="3fb9a-190">Nel file .csv potrebbero essere presenti nomi di campo, come "ssn", "birthdate", "firstname", "lastname".</span><span class="sxs-lookup"><span data-stu-id="3fb9a-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="3fb9a-191">I nomi delle intestazioni di colonna non possono includere spazi o caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="3fb9a-192">Ad esempio, il file .cvs di esempio usato in questo articolo è denominato *PatientRecords. csv* e le relative colonne includono *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* e così via.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="3fb9a-193">Prestare attenzione al formato dei campi di dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-193">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="3fb9a-194">In particolare, durante l'analisi con lo strumento EDM, i campi che possono contenere virgole (ad esempio un indirizzo contenente il valore "Seattle,WA") sarebbero analizzati come due campi separati.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-194">In particular, fields that may contain commas in their content (e.g. a street address that contains the value "Seattle,WA") would be parsed as two separate fields when parsed by the EDM tool.</span></span> <span data-ttu-id="3fb9a-195">Per evitare il problema, bisogna assicurare che tali campi siano racchiusi da virgolette singole o doppie nella tabella dei dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-195">In order to avoid this, you need to ensure such fields are surrounded by single or double quotes in the sensitive data table.</span></span> <span data-ttu-id="3fb9a-196">Se i campi con virgole possono contenere anche spazi, è necessario creare un tipo di informazioni sensibili personalizzato associato al formato corrispondente, ad esempio una stringa con più parole contenente virgole e spazi, per assicurare che la stringa sia abbinata correttamente quando il documento viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-196">If fields with commas in them may also contain spaces, you would need to create a custom Sensitive Information Type that matches the corresponding format (e.g. a multi-word string with commas and spaces in it) to ensure the string is correctly matched when the document is scanned.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="3fb9a-197">Definire lo schema per il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-197">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="3fb9a-198">Se, per motivi aziendali o tecnici, si preferisse non usare PowerShell o la riga di comando per creare il proprio schema e un modello per le informazioni sensibili di tipo EDM (pacchetto di regole), sarebbe possibile usare [lo schema Exact Data Match e la procedura guidata per il tipo di informazioni sensibili](sit-edm-wizard.md) per crearli.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-198">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="3fb9a-199">Una volta completata la creazione dello schema e il modello per le informazioni sensibili di tipo EDM, completare tutti i passaggi necessari per rendere le informazioni sensibili basate sul tipo EDM disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-199">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="3fb9a-200">Lo schema Exact Data Match e la procedura guidata per il tipo di informazioni sensibili sono disponibili unicamente per i cloud World Wide e GCC.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-200">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="3fb9a-201">Definire lo schema per il database delle informazioni sensibili nel formato .xml (come riportato nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="3fb9a-202">Assegnare al file dello schema il nome **edm.xml** e configurarlo in modo che per ogni colonna del database sia presente una riga che usi la sintassi:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="3fb9a-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="3fb9a-204">Usare i nomi delle colonne per i valori dei *nomi dei campi*.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="3fb9a-205">Usare *searchable="true"* per un massimo di 5 campi che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="3fb9a-206">Almeno un campo deve essere disponibile per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="3fb9a-207">Ad esempio, il seguente file XML definisce lo schema per un database dei record dei pazienti, con cinque campi specificati come ricercabili: *IDPaziente*, *MRN*, *CF*, *Telefono* e *Data nasc.*.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="3fb9a-208">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-208">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
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

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="3fb9a-209">Corrispondenza configurabile con i campi caseInsensitive e ignoredDelimiters</span><span class="sxs-lookup"><span data-stu-id="3fb9a-209">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="3fb9a-210">L'esempio XML riportato in precedenza usa i campi `caseInsensitive` e `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-210">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span> 

<span data-ttu-id="3fb9a-211">Se si include il campo \***caseInsensitive** _ impostato sul valore `true` nella definizione dello schema, EDM non escluderà un elemento in base alle differenze tra maiuscole e minuscole per il campo `PatientID`.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-211">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="3fb9a-212">EDM identificherà `PatientID` _ *FOO-1234*\* e **fOo-1234** come identici.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-212">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="3fb9a-213">Quando si include il campo \***ignoredDelimiters** _ con caratteri supportati, EDM ignorerà tali caratteri in `PatientID`.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-213">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="3fb9a-214">Pertanto, EDM considererà `PatientID` _ *FOO-1234*\* e `PatientID` **FOO#1234** identici.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-214">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="3fb9a-215">Il contrassegno `ignoredDelimiters` supporta qualsiasi carattere non alfanumerico. Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-215">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="3fb9a-216">\.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-216">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \; 

<span data-ttu-id="3fb9a-217">Il contrassegno `ignoredDelimiters` non supporta:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-217">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="3fb9a-218">Caratteri 0-9</span><span class="sxs-lookup"><span data-stu-id="3fb9a-218">characters 0-9</span></span>
- <span data-ttu-id="3fb9a-219">A-Z</span><span class="sxs-lookup"><span data-stu-id="3fb9a-219">A-Z</span></span>
- <span data-ttu-id="3fb9a-220">a-z</span><span class="sxs-lookup"><span data-stu-id="3fb9a-220">a-z</span></span>
- \"
- \,

<span data-ttu-id="3fb9a-221">In questo esempio in cui vengono usati `caseInsensitive` e `ignoredDelimiters`, EDM identifica **FOO-1234** e **fOo # 1234** come identici e classifica l'elemento come un tipo di informazioni sensibili del record del paziente.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-221">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span> 

4. <span data-ttu-id="3fb9a-222">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-222">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="3fb9a-223">Per caricare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-223">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="3fb9a-224">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-224">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="3fb9a-225">Conferma</span><span class="sxs-lookup"><span data-stu-id="3fb9a-225">Confirm</span></span>
      >
      > <span data-ttu-id="3fb9a-226">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="3fb9a-226">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="3fb9a-227">Viene importato il nuovo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-227">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="3fb9a-228">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="3fb9a-228">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="3fb9a-229">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 5, usare questo cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="3fb9a-229">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="3fb9a-230">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-230">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="3fb9a-231">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-231">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="3fb9a-232">Configurare un pacchetto di regole</span><span class="sxs-lookup"><span data-stu-id="3fb9a-232">Set up a rule package</span></span>

1. <span data-ttu-id="3fb9a-233">Creare un pacchetto di regole nel formato .xml (con codifica Unicode), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-233">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="3fb9a-234">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-234">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="3fb9a-235">Quando si configura il pacchetto di regole, assicurarsi di fare riferimento correttamente al file .csv e al file **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-235">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="3fb9a-236">È possibile copiare, modificare e usare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-236">You can copy, modify, and use our example.</span></span> <span data-ttu-id="3fb9a-237">In questo XML di esempio è necessario personalizzare i campi seguenti per creare un tipo di informazioni sensibili di EDM:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-237">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="3fb9a-238">**RulePack id & ExactMatch id**: usare [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) per generare un GUID.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-238">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="3fb9a-239">**Datastore**: questo campo specifica l'archivio dati di ricerca EDM da usare.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-239">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="3fb9a-240">È possibile specificare il nome di un'origine dati di uno schema EDM configurato.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-240">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="3fb9a-241">**idMatch**: questo campo punta all'elemento primario per EDM.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-241">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="3fb9a-242">Matches: specifica il campo da usare nella ricerca esatta.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-242">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="3fb9a-243">È possibile specificare il nome campo ricercabile nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-243">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="3fb9a-244">Classification: questo campo specifica la corrispondenza del tipo di informazioni sensibili che attiva la ricerca EDM.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-244">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="3fb9a-245">È possibile specificare il nome o il GUID di un tipo di informazioni sensibili predefinito o personalizzato esistente.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-245">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="3fb9a-246">Tenere presente che qualsiasi stringa che corrisponde al tipo di informazioni sensibili specificato verrà sottoposta ad hashing e confrontata con ogni voce nella tabella delle informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-246">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="3fb9a-247">Per evitare di causare problemi di prestazioni, se in EDM si usa un tipo di informazioni sensibili personalizzato come elemento Classification, evitare di usarne uno che corrisponda a una percentuale elevata di contenuto, ad esempio "qualsiasi numero" o "qualsiasi parola di cinque lettere". A questo scopo, aggiungere parole chiave di supporto o includere la formattazione nella definizione del tipo di informazioni sensibili per la classificazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-247">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span> 

      - <span data-ttu-id="3fb9a-248">**Match:** questo campo indica altre evidenze disponibili in prossimità di idMatch.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-248">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="3fb9a-249">Matches: è possibile specificare qualsiasi nome campo nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-249">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="3fb9a-250">**Resource:** questa sezione specifica il nome e la descrizione per il tipo di informazioni sensibili in più impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-250">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="3fb9a-251">idRef: è possibile specificare il GUID per l'ID ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-251">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="3fb9a-252">Name e descriptions: personalizzare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-252">Name & descriptions: customize as required.</span></span>

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

2. <span data-ttu-id="3fb9a-253">Per caricare il pacchetto di regole, eseguire i seguenti cmdlet di PowerShell, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-253">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="3fb9a-254">A questo punto è stata configurata la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-254">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="3fb9a-255">Il passaggio successivo consiste nell'eseguire l’hashing dei i dati sensibili e poi di caricare gli hash per indicizzarli.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-255">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="3fb9a-256">Ricordarsi della procedura precedente in cui lo schema di PatientRecords definisce cinque campi come ricercabili: *PatientID*, *MRN*, *SSN*, *Telefono* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-256">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="3fb9a-257">Il pacchetto di regole di esempio include questi campi e fa riferimento al file schema di database (**edm.xml**), con un unico elemento *ExactMatch* per ogni campo ricercabile.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-257">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="3fb9a-258">Considerare l'elemento ExactMatch seguente:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-258">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="3fb9a-259">Utilizzando l'esempio proposto, osservare:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-259">In this example, note that:</span></span>

- <span data-ttu-id="3fb9a-260">Il nome del dataStore fa riferimento al file .csv creato in precedenza: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-260">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="3fb9a-261">Il valore idMatch fa riferimento a un campo ricercabile elencato nel file di schema del database: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-261">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="3fb9a-262">Il valore di classificazione fa riferimento a un tipo di informazioni riservate esistente o personalizzato: **classificazione = "Stati Uniti - Numero di previdenza sociale (SSN)”**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-262">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="3fb9a-263">In questo caso, viene usato il tipo di informazioni sensibili esistente del Numero di previdenza sociale degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-263">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="3fb9a-264">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-264">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="3fb9a-265">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-265">The update must complete before you execute steps that use the additions.</span></span>
 
<span data-ttu-id="3fb9a-266">Dopo aver importato il pacchetto di regole con il tipo di informazioni sensibili EDM e la tabella dei dati sensibili, è possibile testare il tipo appena creato usando la funzione **Test** nelle procedura guidata EDM nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-266">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="3fb9a-267">Per istruzioni sull’utilizzo di questa funzionalità, vedere [Usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili](sit-edm-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-267">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="3fb9a-268">Modificare lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="3fb9a-268">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="3fb9a-269">Se si vogliono apportare modifiche al file **edm.xml**, ad esempio modificare i campi usati per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-269">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="3fb9a-270">È possibile modificare lo schema EDM e il file di dati per sfruttare la **corrispondenza configurabile**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-270">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="3fb9a-271">Se configurato, EDM ignora le differenze tra maiuscole e minuscole e alcuni delimitatori nella valutazione di un elemento.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-271">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="3fb9a-272">Ciò consente di definire più facilmente gli schemi XML e i file di dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-272">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="3fb9a-273">Per altre informazioni, vedere [Modificare lo schema Exact Data Match per usare la corrispondenza configurabile](sit-modify-edm-schema-configurable-match.md).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-273">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="3fb9a-274">Modificare il file **edm.xml** (il file descritto nella sezione [Definisci lo schema](#define-the-schema-for-your-database-of-sensitive-information) di questo articolo).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-274">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="3fb9a-275">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-275">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="3fb9a-276">Per aggiornare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-276">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="3fb9a-277">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-277">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="3fb9a-278">Conferma</span><span class="sxs-lookup"><span data-stu-id="3fb9a-278">Confirm</span></span>
      >
      > <span data-ttu-id="3fb9a-279">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="3fb9a-279">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="3fb9a-280">Viene aggiornato lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-280">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="3fb9a-281">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="3fb9a-281">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="3fb9a-282">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 3, usare questo cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="3fb9a-282">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="3fb9a-283">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-283">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="3fb9a-284">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-284">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="3fb9a-285">Rimuovere lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="3fb9a-285">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="3fb9a-286">(Se necessario) Se si vuole rimuovere lo schema usato per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-286">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="3fb9a-287">Connettersi al Centro sicurezza e conformità seguendo le procedure in [Connettersi a PowerShell per Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-287">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="3fb9a-288">Eseguire i cmdlet di PowerShell seguenti, sostituendo il nome dell'archivio dati di "patient records" con quello che si vuole rimuovere:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-288">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="3fb9a-289">Verrà richiesto di confermare:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-289">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="3fb9a-290">Conferma</span><span class="sxs-lookup"><span data-stu-id="3fb9a-290">Confirm</span></span>
      >
      > <span data-ttu-id="3fb9a-291">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="3fb9a-291">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="3fb9a-292">Viene rimosso lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-292">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="3fb9a-293">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="3fb9a-293">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="3fb9a-294">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 2, usare questo cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="3fb9a-294">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="3fb9a-295">Parte 2: eseguire hashing e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-295">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="3fb9a-296">In questa fase è possibile impostare un gruppo di sicurezza personalizzato e un account utente e configurare lo strumento Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-296">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="3fb9a-297">Successivamente, è possibile usare lo strumento per eseguire l’hashing con i valori salt dei dati sensibili, e poi caricarli.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-297">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="3fb9a-298">L’hashing e il caricamento può essere eseguito con un computer oppure è possibile separare la procedura di hashing da quello di caricamento per una maggiore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-298">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="3fb9a-299">Se si vuole eseguire l'hashing e il caricamento da un computer, è necessario farlo da uno che può connettersi direttamente al tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-299">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="3fb9a-300">È necessario che i file dati di testo sensibili non crittografati siano presenti sul computer per l'hashing.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-300">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="3fb9a-p129">Se non si vuole esporre file dati di testo sensibili non crittografati, è possibile eseguirne l’hashing su un computer in una posizione sicura e quindi copiare il file hash e il file salt in un computer che può connettersi direttamente al tenant di Microsoft 365 per il caricamento. In questo scenario, sarà necessario l’EDMUploadAgent su entrambi i computer.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-p129">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload. In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fb9a-303">Se si usa lo schema Exact Data Match e la procedura guidata per il tipo di informazioni sensibili per creare il proprio schema e i file modello, è ***necessario*** scaricare lo schema per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-303">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="3fb9a-304">Se l'organizzazione ha configurato [Customer Key per Microsoft 365 a livello di tenant (anteprima pubblica)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact Data Match userà automaticamente la relativa funzionalità di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-304">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="3fb9a-305">Questa opzione è disponibile solo per i tenant con licenza E5 nel cloud commerciale.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-305">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="3fb9a-306">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3fb9a-306">Prerequisites</span></span>

- <span data-ttu-id="3fb9a-307">un account aziendale o dell'Istituto di istruzione per Microsoft 365, che verrà aggiunto al gruppo di sicurezza **EDM\_datauploaders**</span><span class="sxs-lookup"><span data-stu-id="3fb9a-307">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="3fb9a-308">un computer Windows 10 o Windows Server 2016 con versione .NET 4.6.2 per l'esecuzione di EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="3fb9a-308">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="3fb9a-309">una directory nel computer di caricamento per:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-309">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="3fb9a-310">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="3fb9a-310">EDMUploadAgent</span></span>
    - <span data-ttu-id="3fb9a-311">il file di elemento sensibile in formato CSV **PatientRecords. csv** negli esempi</span><span class="sxs-lookup"><span data-stu-id="3fb9a-311">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="3fb9a-312">e i file di output hash e salt</span><span class="sxs-lookup"><span data-stu-id="3fb9a-312">and the output hash and salt files</span></span>
    - <span data-ttu-id="3fb9a-313">il nome del datastore dal file **edm.xml**, for quest’esempio `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="3fb9a-313">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="3fb9a-314">Se si usano [lo schema Exact Data Match e la procedura guidata per il tipo di informazioni sensibili](sit-edm-wizard.md) è ***necessario*** scaricarli</span><span class="sxs-lookup"><span data-stu-id="3fb9a-314">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="3fb9a-315">Impostare il gruppo di sicurezza e l'account utente</span><span class="sxs-lookup"><span data-stu-id="3fb9a-315">Set up the security group and user account</span></span>

1. <span data-ttu-id="3fb9a-316">Come amministratore globale, passare all'interfaccia di amministrazione usando il [collegamento appropriato per l'abbonamento in uso](#portal-links-for-your-subscription) e [creare un gruppo di sicurezza](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) denominato **EDM\_ DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-316">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="3fb9a-317">Aggiungere uno o più utenti al gruppo di sicurezza **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-317">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="3fb9a-318">(Questi utenti gestiranno il database delle informazioni sensibili.)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-318">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="3fb9a-319">Hashing e caricamento da un computer</span><span class="sxs-lookup"><span data-stu-id="3fb9a-319">Hash and upload from one computer</span></span>

<span data-ttu-id="3fb9a-320">Il computer deve avere accesso diretto al tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-320">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="3fb9a-321">Prima di iniziare questa procedura, verificare di essere un membro del gruppo di sicurezza **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-321">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

> [!TIP]
> <span data-ttu-id="3fb9a-322">In alternativa, è possibile eseguire una convalida nel file CSV prima di caricarlo tramite l’esecuzione di:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-322">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
><span data-ttu-id="3fb9a-323">Per altre informazioni sui parametri supportati da EdmUploadAgent.exe>, eseguire</span><span class="sxs-lookup"><span data-stu-id="3fb9a-323">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="3fb9a-324">Collegamenti all'agente di caricamento EDM per tipo di abbonamento</span><span class="sxs-lookup"><span data-stu-id="3fb9a-324">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="3fb9a-325">[Commerciale + GCC](https://go.microsoft.com/fwlink/?linkid=2088639): consigliato per la maggior parte dei clienti commerciali</span><span class="sxs-lookup"><span data-stu-id="3fb9a-325">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="3fb9a-326">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521): specifico per gli abbonati al cloud di enti pubblici con sicurezza elevata</span><span class="sxs-lookup"><span data-stu-id="3fb9a-326">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="3fb9a-327">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807): specifico per i clienti del cloud del Dipartimento della difesa degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="3fb9a-327">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="3fb9a-328">Creare una directory di lavoro per EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-328">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="3fb9a-329">Ad esempio, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-329">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="3fb9a-330">Posizionare il **file PatientRecords.csv** lì.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-330">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="3fb9a-331">Scaricare e installare l'[agente di caricamento EDM](#links-to-edm-upload-agent-by-subscription-type) appropriato per l'abbonamento nella directory creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-331">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3fb9a-332">L’EDMUploadAgent nei collegamenti precedenti è stato aggiornato in modo da aggiungere automaticamente un valore salt ai dati hash.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-332">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="3fb9a-333">In alternativa, è possibile specificare un valore salt personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-333">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="3fb9a-334">Dopo aver usato questa versione, non sarà possibile usare la versione precedente di EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-334">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="3fb9a-335">È possibile caricare i dati con EDMUploadAgent in qualsiasi archivio dati solo due volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-335">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="3fb9a-p134">Per ottenere un elenco dei parametri di comando supportati, eseguire l'agente senza argomenti. Ad esempio, “EdmUploadAgent.exe”.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-p134">To a get a list out of the supported command parameters, run the agent no arguments. For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="3fb9a-338">Autorizzare l'agente di caricamento EDM, aprire il prompt dei comandi di Windows (come amministratore), passare alla directory **C:\EDM\Data** ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-338">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="3fb9a-339">Accedere con l'account aziendale o dell'istituto di istruzione per Microsoft 365 aggiunto al gruppo di sicurezza EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-339">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="3fb9a-340">Le informazioni del tenant vengono estratte dall'account utente per creare la connessione.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-340">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="3fb9a-341">FACOLTATIVO: se si usa lo schema Exact Data Match e la procedura guidata per il tipo di informazioni sensibili per creare il proprio schema e i file modello, eseguire il seguente comando in una finestra del prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-341">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   `EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. <span data-ttu-id="3fb9a-342">Per eseguire l’hashing e caricare i dati sensibili, eseguire il seguente comando nella finestra dei prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-342">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file]`

   <span data-ttu-id="3fb9a-343">Esempio: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="3fb9a-343">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="3fb9a-344">Verrà automaticamente aggiunto un valore salt generato casualmente all'hash per una maggiore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-344">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="3fb9a-345">Facoltativamente, se si vuole usare il proprio valore salt, aggiungere il **/Salt <saltvalue>** al comando.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-345">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="3fb9a-346">Questo valore deve avere una lunghezza 64 caratteri e può contenere solo caratteri a-z e i caratteri 0-9.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-346">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="3fb9a-347">Per controllare lo stato di caricamento, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-347">Check the upload status by running this command:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

   <span data-ttu-id="3fb9a-348">Esempio: **EdmUploadAgent. exe/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="3fb9a-348">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="3fb9a-349">Cercare lo stato in **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-349">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="3fb9a-350">Controllare di nuovo, ogni due minuti, finché lo stato non cambia in **Completato**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-350">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="3fb9a-351">Una volta che lo stato è completato, i dati EDM sono pronti per l'uso.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-351">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="3fb9a-352">Separare hashing e caricamento</span><span class="sxs-lookup"><span data-stu-id="3fb9a-352">Separate Hash and upload</span></span>

<span data-ttu-id="3fb9a-353">Eseguire l’hashing in un computer in un ambiente protetto.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-353">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="3fb9a-354">FACOLTATIVO: se si usa lo schema Exact Data Match e la procedura guidata per il tipo di informazioni sensibili per creare il proprio schema e i file modello, eseguire il seguente comando in una finestra del prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-354">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. <span data-ttu-id="3fb9a-355">Eseguire il comando seguente nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-355">Run the following command in Command Prompt windows:</span></span>

   `EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

   <span data-ttu-id="3fb9a-356">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-356">For example:</span></span>

   > <span data-ttu-id="3fb9a-357">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="3fb9a-357">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="3fb9a-358">Verrà generato un file hash e un file salt con queste estensioni se non è stata specificata l'opzione **/Salt <saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-358">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
   - <span data-ttu-id="3fb9a-359">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="3fb9a-359">.EdmHash</span></span>
   - <span data-ttu-id="3fb9a-360">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="3fb9a-360">.EdmSalt</span></span>

2. <span data-ttu-id="3fb9a-361">Copiare i file in modo sicuro nel computer che si userà per caricare il file CSV degli elementi sensibili (PatientRecords) nel tenant.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-361">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="3fb9a-362">Per caricare i dati su cui è stato eseguito l’hashing, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-362">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   `EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

   <span data-ttu-id="3fb9a-363">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-363">For example:</span></span>

   > <span data-ttu-id="3fb9a-364">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="3fb9a-364">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


   <span data-ttu-id="3fb9a-365">Per verificare che i dati sensibili siano stati caricati, eseguire il comando seguente nella finestra del prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-365">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /GetDataStore`

   <span data-ttu-id="3fb9a-366">Viene visualizzato un elenco degli archivi dati e la data dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-366">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="3fb9a-367">Per visualizzare tutti i caricamenti di dati in un determinato archivio, eseguire il comando seguente in un prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-367">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

   <span data-ttu-id="3fb9a-368">Procedere alla configurazione della procedura e della programmazione per [Aggiornamento del database delle informazioni sensibili](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-368">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="3fb9a-369">A questo punto si è pronti a usare la classificazione basata su EDM con i servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-369">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="3fb9a-370">Ad esempio, è possibile [impostare un criterio di DLP con la classificazione basata su EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-370">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="3fb9a-371">Aggiornare il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="3fb9a-371">Refreshing your sensitive information database</span></span>

<span data-ttu-id="3fb9a-372">È possibile aggiornare il database delle informazioni sensibili giornalmente e lo strumento di caricamento di EDM può reindicizzare i dati sensibili e quindi ricaricarli.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-372">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="3fb9a-373">Determinare la procedura e la frequenza (giornaliera o settimanale) dell’aggiornamento del database delle informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-373">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="3fb9a-374">Esportare di nuovo i dati sensibili in un'app, come Microsoft Excel e salvare il file in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-374">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="3fb9a-375">Mantenere il nome e il percorso del file usati dopo aver seguito la procedura descritta in [Eseguire hashing e caricare i dati sensibili](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-375">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="3fb9a-376">Se non sono state apportate modifiche alla struttura (nomi dei campi) del file CSV, non è necessario apportare modifiche al file dello schema del database quando si aggiornano i dati.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-376">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="3fb9a-377">Tuttavia, se è necessario apportare modifiche, accertarsi di modificare di conseguenza lo schema del database e il pacchetto delle regole.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-377">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="3fb9a-378">Usare [l'Utilità di pianificazione](/windows/desktop/TaskSchd/task-scheduler-start-page) per automatizzare i passaggi 2 e 3 nella procedura [Eseguire hashing e caricare i dati sensibili](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-378">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="3fb9a-379">È possibile pianificare le attività in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-379">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="3fb9a-380">Metodo</span><span class="sxs-lookup"><span data-stu-id="3fb9a-380">Method</span></span>             | <span data-ttu-id="3fb9a-381">Soluzione</span><span class="sxs-lookup"><span data-stu-id="3fb9a-381">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="3fb9a-382">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fb9a-382">Windows PowerShell</span></span>     | <span data-ttu-id="3fb9a-383">Consultare la documentazione dell’[Utilità di pianificazione](/powershell/module/scheduledtasks/?view=win10-ps) e [gli script di PowerShell di esempio](#example-powershell-script-for-task-scheduler) illustrati in questo articolo</span><span class="sxs-lookup"><span data-stu-id="3fb9a-383">See the [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="3fb9a-384">API dell’Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="3fb9a-384">Task Scheduler API</span></span>     | <span data-ttu-id="3fb9a-385">Consultare la documentazione dell’[Utilità di pianificazione](/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-385">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="3fb9a-386">Interfaccia utente Windows</span><span class="sxs-lookup"><span data-stu-id="3fb9a-386">Windows user interface</span></span> | <span data-ttu-id="3fb9a-387">In Windows, fare clic su **Start** e digitare Utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-387">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="3fb9a-388">Quindi, nell'elenco dei risultati, fare clic con il pulsante destro del mouse sull’**Utilità di pianificazione** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-388">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="3fb9a-389">Esempio di script di PowerShell per Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="3fb9a-389">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="3fb9a-390">Questa sezione include uno script di PowerShell di esempio che è possibile usare per pianificare le attività di hashing dei dati e il caricamento dei dati sui quali è stato eseguito l’hashing:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-390">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="3fb9a-391">Per pianificare l’hashing e il caricamento in un passaggio combinato</span><span class="sxs-lookup"><span data-stu-id="3fb9a-391">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="3fb9a-392">Per pianificare l'hashing e il caricamento in passaggi separati</span><span class="sxs-lookup"><span data-stu-id="3fb9a-392">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="3fb9a-393">Parte 3: usare la classificazione basata su EDM con i servizi cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="3fb9a-393">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="3fb9a-394">Questi percorsi sono supportati dai tipi di informazioni riservate EDM:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-394">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="3fb9a-395">DPL per Exchange Online (posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-395">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="3fb9a-396">OneDrive for Business (file)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-396">OneDrive for Business (files)</span></span>
- <span data-ttu-id="3fb9a-397">Microsoft Teams (conversazioni)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-397">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="3fb9a-398">DLP per SharePoint (file)</span><span class="sxs-lookup"><span data-stu-id="3fb9a-398">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="3fb9a-399">Criteri DPL di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3fb9a-399">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="3fb9a-400">Criteri di etichettatura automatica sul lato server</span><span class="sxs-lookup"><span data-stu-id="3fb9a-400">Server-side auto-labeling policies</span></span>

<span data-ttu-id="3fb9a-401">I tipi di informazioni sensibili EDM per gli scenari seguenti sono in fase di sviluppo e non sono ancora disponibili:</span><span class="sxs-lookup"><span data-stu-id="3fb9a-401">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="3fb9a-402">Classificazione automatica di etichette di riservatezza ed etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="3fb9a-402">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="3fb9a-403">Creazione di un criterio DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="3fb9a-403">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="3fb9a-404">Passare al Centro sicurezza e conformità usando il [collegamento appropriato per l'abbonamento](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="3fb9a-404">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="3fb9a-405">Scegliere **Prevenzione della perdita dei dati**\>**Criteri**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-405">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="3fb9a-406">Scegliere **Creare un criterio** \> **Personalizzato** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-406">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="3fb9a-407">Nella scheda **Nome criterio**, specificare un nome e una descrizione, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-407">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="3fb9a-408">Nella scheda **Scegli posizioni**, selezionare **Consenti di scegliere posizioni specifiche** e poi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-408">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="3fb9a-409">Nella colonna **Stato** selezionare **Posta elettronica di Exchange, Account di OneDrive, Chat di Team e Messaggio del canale** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-409">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="3fb9a-410">Nella scheda **Impostazioni criterio**, scegliere **Usa impostazioni avanzate** e poi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-410">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="3fb9a-411">Scegliere **+ Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-411">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="3fb9a-412">Nella sezione **Nome**, specificare un nome e una descrizione per la regola. </span><span class="sxs-lookup"><span data-stu-id="3fb9a-412">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="3fb9a-413">Nella sezione **Condizioni**, nell'elenco **+ Aggiungi una condizione**, scegliere **Il contenuto include il tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-413">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![Il contenuto contiene tipi di informazioni sensibili](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="3fb9a-415">Cercare il tipo di informazioni sensibili creato quando si configura il pacchetto delle regole e quindi scegliere **+ Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="3fb9a-415">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="3fb9a-416">Poi scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-416">Then choose **Done**.</span></span>

12. <span data-ttu-id="3fb9a-417">Infine selezionare le opzioni per la regola, come **Notifiche utente**, **Personalizzazioni utente**, **Report degli eventi** e così via, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-417">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="3fb9a-418">Nella scheda **Impostazioni criterio**, esaminare le regole e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-418">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="3fb9a-419">Specificare se attivare subito il criterio, testarlo o mantenerlo disattivato.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-419">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="3fb9a-420">Quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-420">Then choose **Next**.</span></span>

15. <span data-ttu-id="3fb9a-421">Nella scheda **Esamina le impostazioni**, controlla il criterio.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-421">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="3fb9a-422">Apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-422">Make any needed changes.</span></span> <span data-ttu-id="3fb9a-423">Al termine, scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-423">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="3fb9a-424">Il nuovo criterio DLP sarà attivo nel centro dati dopo circa un'ora.</span><span class="sxs-lookup"><span data-stu-id="3fb9a-424">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3fb9a-425">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="3fb9a-425">Related articles</span></span>

- [<span data-ttu-id="3fb9a-426">Definizioni delle entità tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="3fb9a-426">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="3fb9a-427">Ulteriori informazioni sui tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="3fb9a-427">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="3fb9a-428">Informazioni sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="3fb9a-428">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="3fb9a-429">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3fb9a-429">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="3fb9a-430">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="3fb9a-430">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="3fb9a-431">Modificare lo schema Exact Data Match per usare la corrispondenza configurabile</span><span class="sxs-lookup"><span data-stu-id="3fb9a-431">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
