---
title: Creare un dizionario di parole chiave
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
ms.custom:
- seo-marvel-apr2020
description: Informazioni sulla procedura di base per la creazione di un dizionario di parole chiave nel Centro sicurezza e conformità di Office 365.
ms.openlocfilehash: 1e1aa45c3bf4d31e4c969b0bc0949109fa716467
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841163"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="60c36-103">Creare un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="60c36-103">Create a keyword dictionary</span></span>

<span data-ttu-id="60c36-104">La prevenzione della perdita dei dati consente di identificare, monitorare e proteggere gli elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="60c36-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="60c36-105">Per identificare gli elementi sensibili talvolta è necessario cercare le parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito.</span><span class="sxs-lookup"><span data-stu-id="60c36-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="60c36-106">Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni sensibili, tali elenchi hanno dimensioni limitate e richiedono la modifica di file XML per la loro creazione o modifica.</span><span class="sxs-lookup"><span data-stu-id="60c36-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="60c36-107">I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala più ampia, supportano fino a 1 MB di termini (dopo la compressione) per dizionario, e supportano qualsiasi lingua.</span><span class="sxs-lookup"><span data-stu-id="60c36-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="60c36-108">Anche il limite del tenant è di 1 MB dopo la compressione.</span><span class="sxs-lookup"><span data-stu-id="60c36-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="60c36-109">Il limite di 1 MB dopo la compressione significa che tutti i dizionari combinati di un tenant possono contenere quasi 1 milione di caratteri.</span><span class="sxs-lookup"><span data-stu-id="60c36-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="60c36-110">Limiti dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="60c36-110">Keyword dictionary limits</span></span>

<span data-ttu-id="60c36-111">Esiste un limite di 50 tipi di informazioni sensibili basati su dizionario di parole chiave che possono essere creati per tenant.</span><span class="sxs-lookup"><span data-stu-id="60c36-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="60c36-112">Per informazioni sul numero di dizionari di parole chiave disponibili nel tenant, utilizzare le procedure descritte in [Connettersi a PowerShell nel Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell) per connettersi al tenant ed eseguire questo script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60c36-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="60c36-113">Passaggi di base per la creazione di un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="60c36-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="60c36-p103">Le parole chiave per il dizionario possono provenire da diverse origini, in genere da un file (ad esempio, un elenco con estensione csv o txt) importato nel servizio o tramite il cmdlet di PowerShell, da un elenco che viene immesso direttamente nel cmdlet di PowerShell o da un dizionario esistente. Quando si crea un dizionario di parole chiave, seguire gli stessi passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="60c36-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="60c36-116">Usare **Centro sicurezza e conformità** ([https://protection.office.com](https://protection.office.com)) o connettersi a **PowerShell per &amp;Centro sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="60c36-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="60c36-117">**Definire o caricare le parole chiave dall'origine designata**.</span><span class="sxs-lookup"><span data-stu-id="60c36-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="60c36-118">La procedura guidata e il cmdlet accettano un elenco di parole chiave separate da virgole per creare un dizionario di parole chiave personalizzato, quindi questo passaggio può variare leggermente a seconda dell'origine delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="60c36-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="60c36-119">Una volta caricate, le parole chiave vengono codificate e convertite in una matrice di byte prima di essere importate.</span><span class="sxs-lookup"><span data-stu-id="60c36-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="60c36-120">**Creazione del dizionario**.</span><span class="sxs-lookup"><span data-stu-id="60c36-120">**Create your dictionary**.</span></span> <span data-ttu-id="60c36-121">Scegliere un nome e una descrizione e creare il dizionario.</span><span class="sxs-lookup"><span data-stu-id="60c36-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="60c36-122">Creare un dizionario di parole chiave tramite il Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="60c36-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="60c36-123">Seguire la procedura seguente per creare e importare parole chiave per un dizionario personalizzato:</span><span class="sxs-lookup"><span data-stu-id="60c36-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="60c36-124">Connettersi al Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="60c36-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="60c36-125">Accedere a **Classificazioni > Tipi di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="60c36-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="60c36-126">Selezionare **Crea** e immettere un **nome** e una **descrizione** per i tipi di informazioni sensibili, quindi selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="60c36-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="60c36-127">Selezionare **Aggiungere un elemento**, quindi selezionare **Dizionario (parole chiave grandi)** nell'elenco a discesa **Rilevare il contenuto che contiene**.</span><span class="sxs-lookup"><span data-stu-id="60c36-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="60c36-128">Selezionare **Aggiungere un dizionario**.</span><span class="sxs-lookup"><span data-stu-id="60c36-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="60c36-129">Nel controllo Ricerca selezionare **È possibile creare nuovi elementi, come Dizionari di parole chiave, qui**.</span><span class="sxs-lookup"><span data-stu-id="60c36-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="60c36-130">Immettere un **nome** per il dizionario personalizzato.</span><span class="sxs-lookup"><span data-stu-id="60c36-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="60c36-131">Selezionare **Importa** e quindi **Da testo** o **Da CSV** in base al tipo di file con parole chiave.</span><span class="sxs-lookup"><span data-stu-id="60c36-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="60c36-132">Nella finestra di dialogo File selezionare il file delle parole chiave nel computer locale o nella condivisione file di rete, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="60c36-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="60c36-133">Selezionare **Salva**, quindi selezionare il dizionario personalizzato nell'elenco **Dizionari di parole chiave**.</span><span class="sxs-lookup"><span data-stu-id="60c36-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="60c36-134">Selezionare **Aggiungi**, quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="60c36-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="60c36-135">Esaminare e finalizzare le selezioni dei tipi di informazioni sensibili, quindi selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="60c36-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="60c36-136">Creare un dizionario di parole chiave da un file con PowerShell</span><span class="sxs-lookup"><span data-stu-id="60c36-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="60c36-137">Spesso, quando si deve creare un dizionario di grandi dimensioni, vengono usate parole chiave provenienti da un file o da un elenco esportato da un'altra origine.</span><span class="sxs-lookup"><span data-stu-id="60c36-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="60c36-138">In questo caso, si crea un dizionario di parole chiave contenente un elenco di termini inappropriati da filtrare nella posta elettronica esterna.</span><span class="sxs-lookup"><span data-stu-id="60c36-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="60c36-139">Prima di tutto,[connettersi a PowerShell per ](/powershell/exchange/connect-to-scc-powershell) Centro sicurezza e conformità&amp;.</span><span class="sxs-lookup"><span data-stu-id="60c36-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="60c36-140">Copiare le parole chiave in un file di testo e verificare che ogni parola chiave sia su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="60c36-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="60c36-p107">Salvare il file di testo con codifica Unicode. In Blocco note, \> **Salva con nome** \> **codifica** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="60c36-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="60c36-143">Leggere il file in una variabile eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="60c36-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="60c36-144">Creare il dizionario eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="60c36-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="60c36-145">Uso dei dizionari di parole chiave nei tipi di informazioni riservate personalizzati e nei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="60c36-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="60c36-146">I dizionari di parole chiave possono essere usati nell'ambito dei requisiti di corrispondenza per un tipo di informazioni sensibili personalizzato oppure proprio come tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="60c36-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="60c36-147">Entrambi richiedono la [creazione di un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="60c36-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="60c36-148">Seguire le istruzioni nell'articolo collegato per creare un tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="60c36-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="60c36-149">Una volta disponibile il file XML, per usare il dizionario è necessario l'identificatore GUID.</span><span class="sxs-lookup"><span data-stu-id="60c36-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="60c36-150">Per ottenere l'identità del dizionario, eseguire questo comando e copiare il valore della proprietà **Identity**:</span><span class="sxs-lookup"><span data-stu-id="60c36-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="60c36-151">L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="60c36-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="60c36-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="60c36-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="60c36-p109">Incollare l'identità nel file XML del tipo di informazioni riservate personalizzato e caricarlo. Il dizionario verrà visualizzato nell'elenco dei tipi di informazioni riservate e potrà essere usato direttamente nei criteri, specificando il numero di parole chiave che devono avere una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="60c36-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```

> [!NOTE]
> <span data-ttu-id="60c36-155">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte nelle seguenti lingue:</span><span class="sxs-lookup"><span data-stu-id="60c36-155">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="60c36-156">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="60c36-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="60c36-157">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="60c36-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="60c36-158">Coreano</span><span class="sxs-lookup"><span data-stu-id="60c36-158">Korean</span></span>
> - <span data-ttu-id="60c36-159">Giapponese</span><span class="sxs-lookup"><span data-stu-id="60c36-159">Japanese</span></span>
>
><span data-ttu-id="60c36-160">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="60c36-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="60c36-161">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="60c36-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
