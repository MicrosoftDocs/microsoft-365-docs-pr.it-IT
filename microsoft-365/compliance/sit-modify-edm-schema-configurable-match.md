---
title: Modificare lo schema Exact Data Match per usare la corrispondenza configurabile
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
description: Informazioni su come modificare uno schema EDM per usare la corrispondenza configurabile.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114194"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="421f8-103">Modificare lo schema Exact Data Match per usare la corrispondenza configurabile</span><span class="sxs-lookup"><span data-stu-id="421f8-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="421f8-104">La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="421f8-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="421f8-105">Se occorre autorizzare le varianti per una stringa esatta, è possibile usare la *corrispondenza configurabile* per comunicare a Microsoft 365 di ignorare il caso e alcuni delimitatori.</span><span class="sxs-lookup"><span data-stu-id="421f8-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="421f8-106">Usare questa procedura per modificare lo schema EDM e il file di dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="421f8-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="421f8-107">Disinstallare dal computer **EdmUploadAgent.exe** che viene usato per connettersi a Microsoft 365 per caricare il file di dati e lo schema EDM.</span><span class="sxs-lookup"><span data-stu-id="421f8-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="421f8-108">Scaricare il file **EdmUploadAgent.exe** appropriato per l'abbonamento tramite i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="421f8-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="421f8-109">[Commerciale + GCC](https://go.microsoft.com/fwlink/?linkid=2088639): consigliato per la maggior parte dei clienti commerciali</span><span class="sxs-lookup"><span data-stu-id="421f8-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="421f8-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521): specifico per gli abbonati al cloud di enti pubblici con sicurezza elevata</span><span class="sxs-lookup"><span data-stu-id="421f8-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="421f8-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807): specifico per i clienti del cloud del Dipartimento della difesa degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="421f8-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="421f8-112">Autorizzare l'agente di caricamento di EDM, aprire la finestra del prompt dei comandi (come amministratore) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="421f8-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="421f8-113">Se non si dispone di una copia attuale dello schema esistente, è necessario scaricarne una copia eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="421f8-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="421f8-114">Personalizzare lo schema in modo che ogni colonna utilizzi "caseInsensitive" e/o "ignoredDelimiters".</span><span class="sxs-lookup"><span data-stu-id="421f8-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="421f8-115">Il valore predefinito per "caseInsensitive" è "false" e per "ignoredDelimiters" è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="421f8-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="421f8-116">Il tipo di informazioni sensibili personalizzato, riportato di seguito, o il tipo di informazioni sensibili incorporato usato per rilevare il modello di Regex generico deve supportare il rilevamento degli input di variazione elencati con ignoredDelimiters.</span><span class="sxs-lookup"><span data-stu-id="421f8-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="421f8-117">Ad esempio, il tipo di informazioni sensibili incorporate nel codice di previdenza sociale statunitense (SSN) può rilevare le variazioni dei dati che includono trattini, spazi o mancanza di spazi tra i numeri raggruppati che compongono il SSN.</span><span class="sxs-lookup"><span data-stu-id="421f8-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="421f8-118">Di conseguenza, gli unici delimitatori rilevanti da includere in ignoredDelimiters di EDM per i dati SSN sono: trattino e spazio.</span><span class="sxs-lookup"><span data-stu-id="421f8-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="421f8-119">Di seguito è riportato uno schema di esempio che simula la corrispondenza senza distinzione tra maiuscole e minuscole tramite la creazione di colonne aggiuntive necessarie per riconoscere le variazioni tra maiuscole e minuscole nei dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="421f8-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="421f8-120">Nell'esempio riportato in precedenza, le variazioni della colonna `PolicyNumber` originale non saranno più necessarie se vengono aggiunti `caseInsensitive` e `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="421f8-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="421f8-121">Per aggiornare questo schema in modo che EDM usi la corrispondenza configurabile, usare i contrassegni `caseInsensitive` e `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="421f8-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="421f8-122">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="421f8-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="421f8-123">Il contrassegno `ignoredDelimiters` supporta qualsiasi carattere non alfanumerico. Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="421f8-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="421f8-124">\.</span><span class="sxs-lookup"><span data-stu-id="421f8-124">\.</span></span>
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

<span data-ttu-id="421f8-125">Il contrassegno `ignoredDelimiters` non supporta:</span><span class="sxs-lookup"><span data-stu-id="421f8-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="421f8-126">Caratteri 0-9</span><span class="sxs-lookup"><span data-stu-id="421f8-126">characters 0-9</span></span>
- <span data-ttu-id="421f8-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="421f8-127">A-Z</span></span>
- <span data-ttu-id="421f8-128">a-z</span><span class="sxs-lookup"><span data-stu-id="421f8-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="421f8-129">Connettersi al Centro sicurezza e conformità seguendo le procedure contenute in [Connettersi a PowerShell per Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="421f8-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="421f8-130">Se l'organizzazione ha configurato [Customer Key per Microsoft 365 a livello di tenant (anteprima pubblica)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact Data Match userà automaticamente la relativa funzionalità di crittografia.</span><span class="sxs-lookup"><span data-stu-id="421f8-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="421f8-131">Questa opzione è disponibile solo per i tenant con licenza E5 nel cloud commerciale.</span><span class="sxs-lookup"><span data-stu-id="421f8-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="421f8-132">Aggiornare lo schema eseguendo questi cmdlet uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="421f8-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="421f8-133">Se necessario, aggiornare il file di dati in base alla nuova versione dello schema</span><span class="sxs-lookup"><span data-stu-id="421f8-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="421f8-134">In alternativa, è possibile eseguire una convalida nel file CSV prima di caricarlo, tramite l’esecuzione di:</span><span class="sxs-lookup"><span data-stu-id="421f8-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="421f8-135">Per altre informazioni sui parametri supportati da EdmUploadAgent.exe>, eseguire</span><span class="sxs-lookup"><span data-stu-id="421f8-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="421f8-136">Aprire la finestra del prompt dei comandi (come amministratore) ed eseguire il comando seguente per l’hashing e il caricamento dei dati sensibili:</span><span class="sxs-lookup"><span data-stu-id="421f8-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="421f8-137">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="421f8-137">Related articles</span></span>

- <span data-ttu-id="421f8-138">[Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="421f8-138">[Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span></span>
- [<span data-ttu-id="421f8-139">Definizioni delle entità tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="421f8-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="421f8-140">Tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="421f8-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="421f8-141">Informazioni sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="421f8-141">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="421f8-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="421f8-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="421f8-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="421f8-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)