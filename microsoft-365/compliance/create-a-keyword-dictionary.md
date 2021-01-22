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
ms.openlocfilehash: 488e39921f36a6557378a6214269fcb399114972
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921578"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="43441-103">Creare un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="43441-103">Create a keyword dictionary</span></span>

<span data-ttu-id="43441-104">La prevenzione della perdita dei dati consente di identificare, monitorare e proteggere gli elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="43441-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="43441-105">Per identificare gli elementi sensibili talvolta è necessario cercare le parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito.</span><span class="sxs-lookup"><span data-stu-id="43441-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="43441-106">Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni sensibili, tali elenchi hanno dimensioni limitate e richiedono la modifica di file XML per la loro creazione o modifica.</span><span class="sxs-lookup"><span data-stu-id="43441-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="43441-107">I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala più ampia, supportano fino a 1 MB di termini (dopo la compressione) per dizionario, e supportano qualsiasi lingua.</span><span class="sxs-lookup"><span data-stu-id="43441-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="43441-108">Anche il limite del tenant è di 1 MB dopo la compressione.</span><span class="sxs-lookup"><span data-stu-id="43441-108">The tenant limit is also 1MB after compression.</span></span> <span data-ttu-id="43441-109">Il limite di 1 MB dopo la compressione significa che tutti i dizionari combinati di un tenant possono contenere quasi 1 milione di caratteri.</span><span class="sxs-lookup"><span data-stu-id="43441-109">1MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million character.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43441-110">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte per le lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="43441-110">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="43441-111">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="43441-111">Chinese (simplified)</span></span>
> - <span data-ttu-id="43441-112">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="43441-112">Chinese (traditional)</span></span>
> - <span data-ttu-id="43441-113">Coreano</span><span class="sxs-lookup"><span data-stu-id="43441-113">Korean</span></span>
> - <span data-ttu-id="43441-114">Giapponese</span><span class="sxs-lookup"><span data-stu-id="43441-114">Japanese</span></span>
>
><span data-ttu-id="43441-115">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="43441-115">This support is available for sensitive information types.</span></span> <span data-ttu-id="43441-116">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="43441-116">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="43441-117">Procedura di base per la creazione di un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="43441-117">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="43441-p103">Le parole chiave per il dizionario possono provenire da diverse origini, in genere da un file (ad esempio, un elenco con estensione csv o txt) importato nel servizio o tramite il cmdlet di PowerShell, da un elenco che viene immesso direttamente nel cmdlet di PowerShell o da un dizionario esistente. Quando si crea un dizionario di parole chiave, seguire gli stessi passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="43441-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="43441-120">Usare **Centro sicurezza e conformità** ([https://protection.office.com](https://protection.office.com)) o connettersi a **PowerShell per &amp;Centro sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="43441-120">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="43441-121">**Definire o caricare le parole chiave dall'origine designata**.</span><span class="sxs-lookup"><span data-stu-id="43441-121">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="43441-122">La procedura guidata e il cmdlet accettano un elenco di parole chiave separate da virgole per creare un dizionario di parole chiave personalizzato, quindi questo passaggio può variare leggermente a seconda dell'origine delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="43441-122">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="43441-123">Una volta caricate, le parole chiave vengono codificate e convertite in una matrice di byte prima di essere importate.</span><span class="sxs-lookup"><span data-stu-id="43441-123">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="43441-124">**Creazione del dizionario**.</span><span class="sxs-lookup"><span data-stu-id="43441-124">**Create your dictionary**.</span></span> <span data-ttu-id="43441-125">Scegliere un nome e una descrizione e creare il dizionario.</span><span class="sxs-lookup"><span data-stu-id="43441-125">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="43441-126">Creare un dizionario di parole chiave tramite il Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="43441-126">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="43441-127">Seguire la procedura seguente per creare e importare parole chiave per un dizionario personalizzato:</span><span class="sxs-lookup"><span data-stu-id="43441-127">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="43441-128">Connettersi al Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="43441-128">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="43441-129">Accedere a **Classificazioni > Tipi di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="43441-129">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="43441-130">Selezionare **Crea** e immettere un **nome** e una **descrizione** per i tipi di informazioni sensibili, quindi selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="43441-130">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="43441-131">Selezionare **Aggiungere un elemento**, quindi selezionare **Dizionario (parole chiave grandi)** nell'elenco a discesa **Rilevare il contenuto che contiene**.</span><span class="sxs-lookup"><span data-stu-id="43441-131">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="43441-132">Selezionare **Aggiungere un dizionario**.</span><span class="sxs-lookup"><span data-stu-id="43441-132">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="43441-133">Nel controllo Ricerca selezionare **È possibile creare nuovi elementi, come Dizionari di parole chiave, qui**.</span><span class="sxs-lookup"><span data-stu-id="43441-133">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="43441-134">Immettere un **nome** per il dizionario personalizzato.</span><span class="sxs-lookup"><span data-stu-id="43441-134">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="43441-135">Selezionare **Importa** e quindi **Da testo** o **Da CSV** in base al tipo di file con parole chiave.</span><span class="sxs-lookup"><span data-stu-id="43441-135">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="43441-136">Nella finestra di dialogo File selezionare il file delle parole chiave nel computer locale o nella condivisione file di rete, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="43441-136">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="43441-137">Selezionare **Salva**, quindi selezionare il dizionario personalizzato nell'elenco **Dizionari di parole chiave**.</span><span class="sxs-lookup"><span data-stu-id="43441-137">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="43441-138">Selezionare **Aggiungi**, quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="43441-138">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="43441-139">Esaminare e finalizzare le selezioni dei tipi di informazioni sensibili, quindi selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="43441-139">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="43441-140">Creare un dizionario di parole chiave da un file con PowerShell</span><span class="sxs-lookup"><span data-stu-id="43441-140">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="43441-141">Spesso, quando si deve creare un dizionario di grandi dimensioni, vengono usate parole chiave provenienti da un file o da un elenco esportato da un'altra origine.</span><span class="sxs-lookup"><span data-stu-id="43441-141">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="43441-142">In questo caso, si crea un dizionario di parole chiave contenente un elenco di termini inappropriati da filtrare nella posta elettronica esterna.</span><span class="sxs-lookup"><span data-stu-id="43441-142">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="43441-143">Prima di tutto,[connettersi a PowerShell per ](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Centro sicurezza e conformità&amp;.</span><span class="sxs-lookup"><span data-stu-id="43441-143">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="43441-144">Copiare le parole chiave in un file di testo e verificare che ogni parola chiave sia su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="43441-144">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="43441-p107">Salvare il file di testo con codifica Unicode. In Blocco note, \> **Salva con nome** \> **codifica** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="43441-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="43441-147">Leggere il file in una variabile eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="43441-147">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="43441-148">Creare il dizionario eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="43441-148">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="43441-149">Modifica di un dizionario di parole chiave esistente</span><span class="sxs-lookup"><span data-stu-id="43441-149">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="43441-150">Può essere necessario modificare le parole chiave in uno dei dizionari di parole chiave o modificare uno dei dizionari predefiniti.</span><span class="sxs-lookup"><span data-stu-id="43441-150">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="43441-151">Attualmente è possibile aggiornare solo un dizionario di parole chiave personalizzato con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43441-151">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="43441-152">Ad esempio, alcuni termini verranno modificati in PowerShell, salvati in locale, dove è possibile modificarli in un editor, e quindi inseriti al posto dei termini esistenti.</span><span class="sxs-lookup"><span data-stu-id="43441-152">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="43441-153">Prima di tutto, recuperare l'oggetto dizionario:</span><span class="sxs-lookup"><span data-stu-id="43441-153">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="43441-154">Se si stampa `$dict`, verranno visualizzate le diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="43441-154">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="43441-155">Le stesse parole chiave vengono archiviate in un oggetto in back-end, ma `$dict.KeywordDictionary` contiene una rappresentazione di queste parole in formato stringa, che verrò usata per modificare il dizionario.</span><span class="sxs-lookup"><span data-stu-id="43441-155">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="43441-156">Prima di modificare il dizionario, è necessario riconvertire la stringa di termini in una matrice usando il metodo `.split(',')`.</span><span class="sxs-lookup"><span data-stu-id="43441-156">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="43441-157">Poi è necessario eliminare gli spazi indesiderati tra le parole chiave con il metodo `.trim()`, lasciando solo le parole chiave da usare.</span><span class="sxs-lookup"><span data-stu-id="43441-157">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="43441-p111">A questo punto si rimuovono alcuni termini dal dizionario. Il dizionario di esempio include solo alcune parole chiave, quindi è possibile evitare l'esportazione modificando il dizionario direttamente nel Blocco note. In genere, però, i dizionari contengono una grande quantità di testo, quindi è utile conoscere la procedura per modificarli facilmente in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43441-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="43441-p112">Nell'ultimo passaggio le parole chiave sono state salvate in una matrice. Ci sono diversi modi per [rimuovere elementi da una matrice](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), ma l'approccio più diretto consiste nel creare una matrice di termini da rimuovere dal dizionario e quindi copiare solo i termini del dizionario che non si trovano nell'elenco di termini da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="43441-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="43441-p113">Eseguire il comando `$terms` per visualizzare l'elenco attuale di termini. L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="43441-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="43441-164">Eseguire questo comando per specificare i termini da rimuovere:</span><span class="sxs-lookup"><span data-stu-id="43441-164">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="43441-165">Eseguire questo comando per rimuovere effettivamente i termini dall'elenco:</span><span class="sxs-lookup"><span data-stu-id="43441-165">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="43441-p114">Eseguire il comando `$updatedTerms` per visualizzare l'elenco aggiornato di termini. L'output del comando è simile al seguente (i termini specificati sono stati rimossi):</span><span class="sxs-lookup"><span data-stu-id="43441-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="43441-p115">Ora basta aprire il file, aggiungere gli altri termini e salvare il file con la codifica Unicode (UTF-16). A questo punto, è possibile caricare i termini aggiornati e aggiornare il dizionario esistente.</span><span class="sxs-lookup"><span data-stu-id="43441-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="43441-p116">Ora il dizionario esistente è aggiornato. Il campo `Identity` prende il nome del dizionario. Se si vuole modificare anche il nome del dizionario con il cmdlet `set-`, basta aggiungere il parametro con il nuovo nome del dizionario `-Name` al comando precedente.</span><span class="sxs-lookup"><span data-stu-id="43441-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="43441-173">Uso dei dizionari di parole chiave nei tipi di informazioni riservate personalizzati e nei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="43441-173">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="43441-174">I dizionari di parole chiave possono essere usati nell'ambito dei requisiti di corrispondenza per un tipo di informazioni sensibili personalizzato oppure proprio come tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="43441-174">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="43441-175">Entrambi richiedono la [creazione di un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="43441-175">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="43441-176">Seguire le istruzioni nell'articolo collegato per creare un tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="43441-176">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="43441-177">Una volta disponibile il file XML, per usare il dizionario è necessario l'identificatore GUID.</span><span class="sxs-lookup"><span data-stu-id="43441-177">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="43441-178">Per ottenere l'identità del dizionario, eseguire questo comando e copiare il valore della proprietà **Identity**:</span><span class="sxs-lookup"><span data-stu-id="43441-178">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="43441-179">L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="43441-179">The output of the command looks like this:</span></span>
  
<span data-ttu-id="43441-180">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="43441-180">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="43441-p118">Incollare l'identità nel file XML del tipo di informazioni riservate personalizzato e caricarlo. Il dizionario verrà visualizzato nell'elenco dei tipi di informazioni riservate e potrà essere usato direttamente nei criteri, specificando il numero di parole chiave che devono avere una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="43441-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
