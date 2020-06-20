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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni sui passaggi di base per la creazione di un dizionario di parole chiave nel centro conformità & sicurezza di Office 365.
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818055"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="be26f-103">Creare un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="be26f-103">Create a keyword dictionary</span></span>

<span data-ttu-id="be26f-104">La prevenzione della perdita di dati (DLP) è in grado di identificare, monitorare e proteggere le informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="be26f-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive information.</span></span> <span data-ttu-id="be26f-105">L'identificazione di informazioni riservate a volte richiede la ricerca di parole chiave, in particolare quando si identifica il contenuto generico (ad esempio la comunicazione correlata all'assistenza sanitaria) o la lingua inappropriata o esplicita.</span><span class="sxs-lookup"><span data-stu-id="be26f-105">Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="be26f-106">Anche se è possibile creare elenchi di parole chiave in tipi di informazioni riservate, gli elenchi di parole chiave sono di dimensioni limitate e richiedono la modifica di XML per crearli o modificarli.</span><span class="sxs-lookup"><span data-stu-id="be26f-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="be26f-107">I dizionari keyword offrono una gestione più semplice delle parole chiave e su una scala molto più grande, supportando fino a 100.000 termini per dizionario.</span><span class="sxs-lookup"><span data-stu-id="be26f-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="be26f-108">Procedura di base per la creazione di un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="be26f-108">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="be26f-109">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span><span class="sxs-lookup"><span data-stu-id="be26f-109">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span></span> <span data-ttu-id="be26f-110">When you create a keyword dictionary, you follow the same core steps:</span><span class="sxs-lookup"><span data-stu-id="be26f-110">When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="be26f-111">Utilizzare il **Centro sicurezza & Compliance** ( [https://protection.office.com](https://protection.office.com) ) o connettersi **a &amp; PowerShell per Centro sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="be26f-111">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="be26f-112">**Definire o caricare le parole chiave dall'origine desiderata**.</span><span class="sxs-lookup"><span data-stu-id="be26f-112">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="be26f-113">La procedura guidata e il cmdlet accettano entrambi un elenco delimitato da virgole di parole chiave per creare un dizionario parola chiave personalizzato, in modo che questo passaggio vari leggermente a seconda di dove provengono le parole chiave.</span><span class="sxs-lookup"><span data-stu-id="be26f-113">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="be26f-114">Una volta caricate, le parole chiave vengono codificate e convertite in una matrice di byte prima di essere importate.</span><span class="sxs-lookup"><span data-stu-id="be26f-114">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="be26f-115">**Creare il dizionario**.</span><span class="sxs-lookup"><span data-stu-id="be26f-115">**Create your dictionary**.</span></span> <span data-ttu-id="be26f-116">Scegliere un nome e una descrizione e creare il dizionario.</span><span class="sxs-lookup"><span data-stu-id="be26f-116">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="be26f-117">Creare un dizionario di parole chiave tramite il Centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="be26f-117">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="be26f-118">Seguire la procedura seguente per creare e importare parole chiave per un dizionario personalizzato:</span><span class="sxs-lookup"><span data-stu-id="be26f-118">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="be26f-119">Connettersi al centro sicurezza & Compliance ( [https://protection.office.com](https://protection.office.com) ).</span><span class="sxs-lookup"><span data-stu-id="be26f-119">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="be26f-120">Accedere a **Classificazioni > Tipi di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="be26f-120">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="be26f-121">Selezionare **Crea** e immettere un **nome** e una **descrizione** per i tipi di informazioni sensibili, quindi selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="be26f-121">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="be26f-122">Selezionare **Aggiungere un elemento**, quindi selezionare **Dizionario (parole chiave grandi)** nell'elenco a discesa **Rilevare il contenuto che contiene**.</span><span class="sxs-lookup"><span data-stu-id="be26f-122">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="be26f-123">Selezionare **Aggiungere un dizionario**.</span><span class="sxs-lookup"><span data-stu-id="be26f-123">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="be26f-124">Nel controllo Ricerca selezionare **È possibile creare nuovi elementi, come Dizionari di parole chiave, qui**.</span><span class="sxs-lookup"><span data-stu-id="be26f-124">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="be26f-125">Immettere un **nome** per il dizionario personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be26f-125">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="be26f-126">Selezionare **Importa** e quindi **Da testo** o **Da CSV** in base al tipo di file con parole chiave.</span><span class="sxs-lookup"><span data-stu-id="be26f-126">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="be26f-127">Nella finestra di dialogo File selezionare il file delle parole chiave nel computer locale o nella condivisione file di rete, quindi selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="be26f-127">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="be26f-128">Selezionare **Salva**, quindi selezionare il dizionario personalizzato nell'elenco **Dizionari di parole chiave**.</span><span class="sxs-lookup"><span data-stu-id="be26f-128">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="be26f-129">Selezionare **Aggiungi**, quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="be26f-129">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="be26f-130">Esaminare e finalizzare le selezioni dei tipi di informazioni sensibili, quindi selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="be26f-130">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="be26f-131">Creare un dizionario di parole chiave da un file con PowerShell</span><span class="sxs-lookup"><span data-stu-id="be26f-131">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="be26f-132">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span><span class="sxs-lookup"><span data-stu-id="be26f-132">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="be26f-133">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span><span class="sxs-lookup"><span data-stu-id="be26f-133">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="be26f-134">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="be26f-134">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="be26f-135">Copiare le parole chiave in un file di testo e verificare che ogni parola chiave sia su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="be26f-135">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="be26f-136">Save the text file with Unicode encoding.</span><span class="sxs-lookup"><span data-stu-id="be26f-136">Save the text file with Unicode encoding.</span></span> <span data-ttu-id="be26f-137">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="be26f-137">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="be26f-138">Leggere il file in una variabile eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="be26f-138">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="be26f-139">Creare il dizionario eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="be26f-139">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="be26f-140">Modifica di un dizionario di parole chiave esistente</span><span class="sxs-lookup"><span data-stu-id="be26f-140">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="be26f-141">Può essere necessario modificare le parole chiave in uno dei dizionari di parole chiave o modificare uno dei dizionari predefiniti.</span><span class="sxs-lookup"><span data-stu-id="be26f-141">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="be26f-142">Attualmente è possibile aggiornare solo un dizionario di parole chiave personalizzato con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be26f-142">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="be26f-143">Ad esempio, modificheremo alcuni termini in PowerShell, salviamo i termini localmente in cui è possibile modificarli in un editor e quindi aggiorniamo i termini precedenti sul posto.</span><span class="sxs-lookup"><span data-stu-id="be26f-143">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="be26f-144">Prima di tutto, recuperare l'oggetto dizionario:</span><span class="sxs-lookup"><span data-stu-id="be26f-144">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="be26f-145">`$dict`La stampa mostrerà le varie variabili.</span><span class="sxs-lookup"><span data-stu-id="be26f-145">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="be26f-146">Le parole chiave stesse vengono memorizzate in un oggetto nel backend, ma `$dict.KeywordDictionary` contengono una rappresentazione in forma di stringa, che verrà utilizzata per modificare il dizionario.</span><span class="sxs-lookup"><span data-stu-id="be26f-146">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="be26f-147">Prima di modificare il dizionario, è necessario riportare la stringa di termini in una matrice utilizzando il `.split(',')` metodo.</span><span class="sxs-lookup"><span data-stu-id="be26f-147">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="be26f-148">Verranno quindi ripuliti gli spazi indesiderati tra le parole chiave con il `.trim()` metodo, lasciando solo le parole chiave che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="be26f-148">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="be26f-149">Now you'll remove some terms from the dictionary.</span><span class="sxs-lookup"><span data-stu-id="be26f-149">Now you'll remove some terms from the dictionary.</span></span> <span data-ttu-id="be26f-150">Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be26f-150">Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="be26f-151">In the last step, you saved the keywords to an array.</span><span class="sxs-lookup"><span data-stu-id="be26f-151">In the last step, you saved the keywords to an array.</span></span> <span data-ttu-id="be26f-152">There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span><span class="sxs-lookup"><span data-stu-id="be26f-152">There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="be26f-153">Run the command  `$terms` to show the current list of terms.</span><span class="sxs-lookup"><span data-stu-id="be26f-153">Run the command  `$terms` to show the current list of terms.</span></span> <span data-ttu-id="be26f-154">The output of the command looks like this:</span><span class="sxs-lookup"><span data-stu-id="be26f-154">The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="be26f-155">Eseguire questo comando per specificare i termini da rimuovere:</span><span class="sxs-lookup"><span data-stu-id="be26f-155">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="be26f-156">Eseguire questo comando per rimuovere effettivamente i termini dall'elenco:</span><span class="sxs-lookup"><span data-stu-id="be26f-156">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="be26f-157">Run the command  `$updatedTerms` to show the updated list of terms.</span><span class="sxs-lookup"><span data-stu-id="be26f-157">Run the command  `$updatedTerms` to show the updated list of terms.</span></span> <span data-ttu-id="be26f-158">The output of the command looks like this (the specified terms have been removed):</span><span class="sxs-lookup"><span data-stu-id="be26f-158">The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="be26f-159">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="be26f-159">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16).</span></span> <span data-ttu-id="be26f-160">Now you'll upload the updated terms and update the dictionary in place.</span><span class="sxs-lookup"><span data-stu-id="be26f-160">Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="be26f-161">Now the dictionary has been updated in place.</span><span class="sxs-lookup"><span data-stu-id="be26f-161">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="be26f-162">Note that the  `Identity` field takes the name of the dictionary.</span><span class="sxs-lookup"><span data-stu-id="be26f-162">Note that the  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="be26f-163">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span><span class="sxs-lookup"><span data-stu-id="be26f-163">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="be26f-164">Uso dei dizionari di parole chiave nei tipi di informazioni riservate personalizzati e nei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="be26f-164">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="be26f-165">I dizionari per parole chiave possono essere utilizzati come parte dei requisiti di corrispondenza per un tipo di informazioni riservate personalizzato oppure come tipo di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="be26f-165">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="be26f-166">Entrambi richiedono la creazione di un [tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="be26f-166">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="be26f-167">Seguire le istruzioni riportate nell'articolo collegato per creare un tipo di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="be26f-167">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="be26f-168">Dopo aver utilizzato il codice XML, è necessario l'identificatore GUID del dizionario per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="be26f-168">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="be26f-169">Per ottenere l'identità del dizionario, eseguire questo comando e copiare il valore della proprietà **Identity**:</span><span class="sxs-lookup"><span data-stu-id="be26f-169">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="be26f-170">L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="be26f-170">The output of the command looks like this:</span></span>
  
<span data-ttu-id="be26f-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="be26f-171">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="be26f-172">Paste the identity into your custom sensitive information type's XML and upload it.</span><span class="sxs-lookup"><span data-stu-id="be26f-172">Paste the identity into your custom sensitive information type's XML and upload it.</span></span> <span data-ttu-id="be26f-173">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span><span class="sxs-lookup"><span data-stu-id="be26f-173">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
