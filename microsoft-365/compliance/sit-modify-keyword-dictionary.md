---
title: Modificare un dizionario di parole chiave
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
description: Informazioni su come modificare un dizionario parole chiave nel Centro Microsoft 365 conformità.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685211"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="736eb-103">Modificare un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="736eb-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="736eb-104">Può essere necessario modificare le parole chiave in uno dei dizionari di parole chiave o modificare uno dei dizionari predefiniti.</span><span class="sxs-lookup"><span data-stu-id="736eb-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="736eb-105">A tale scopo, è possibile utilizzare PowerShell o il Centro conformità.</span><span class="sxs-lookup"><span data-stu-id="736eb-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="736eb-106">Modificare un dizionario parole chiave nel Centro conformità</span><span class="sxs-lookup"><span data-stu-id="736eb-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="736eb-107">I dizionari parole chiave possono essere utilizzati come o in modelli `Primary elements` `Supporting elements` SIT (Sensitive Information Type).</span><span class="sxs-lookup"><span data-stu-id="736eb-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="736eb-108">È possibile modificare un dizionario di parole chiave durante la creazione di un sit o in un sit esistente.</span><span class="sxs-lookup"><span data-stu-id="736eb-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="736eb-109">Ad esempio, per modificare un dizionario parole chiave esistente:</span><span class="sxs-lookup"><span data-stu-id="736eb-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="736eb-110">Apri il modello con il dizionario parole chiave che vuoi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="736eb-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="736eb-111">Trova il dizionario parole chiave che vuoi aggiornare e scegli Modifica.</span><span class="sxs-lookup"><span data-stu-id="736eb-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="736eb-112">Apporta le modifiche usando una parola chiave per riga.</span><span class="sxs-lookup"><span data-stu-id="736eb-112">Make your edits, using one keyword per line.</span></span>

![screenshot modificare parole chiave](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="736eb-114">Scegliere `Done` .</span><span class="sxs-lookup"><span data-stu-id="736eb-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="736eb-115">Modificare un dizionario parole chiave con PowerShell</span><span class="sxs-lookup"><span data-stu-id="736eb-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="736eb-116">Ad esempio, alcuni termini verranno modificati in PowerShell, salvati in locale, dove è possibile modificarli in un editor, e quindi inseriti al posto dei termini esistenti.</span><span class="sxs-lookup"><span data-stu-id="736eb-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="736eb-117">Prima di tutto, recuperare l'oggetto dizionario:</span><span class="sxs-lookup"><span data-stu-id="736eb-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="736eb-118">Se si stampa `$dict`, verranno visualizzate le diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="736eb-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="736eb-119">Le stesse parole chiave vengono archiviate in un oggetto in back-end, ma `$dict.KeywordDictionary` contiene una rappresentazione di queste parole in formato stringa, che verrò usata per modificare il dizionario.</span><span class="sxs-lookup"><span data-stu-id="736eb-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="736eb-120">Prima di modificare il dizionario, è necessario riconvertire la stringa di termini in una matrice usando il metodo `.split(',')`.</span><span class="sxs-lookup"><span data-stu-id="736eb-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="736eb-121">Poi è necessario eliminare gli spazi indesiderati tra le parole chiave con il metodo `.trim()`, lasciando solo le parole chiave da usare.</span><span class="sxs-lookup"><span data-stu-id="736eb-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="736eb-p105">A questo punto si rimuovono alcuni termini dal dizionario. Il dizionario di esempio include solo alcune parole chiave, quindi è possibile evitare l'esportazione modificando il dizionario direttamente nel Blocco note. In genere, però, i dizionari contengono una grande quantità di testo, quindi è utile conoscere la procedura per modificarli facilmente in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="736eb-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="736eb-p106">Nell'ultimo passaggio le parole chiave sono state salvate in una matrice. Ci sono diversi modi per [rimuovere elementi da una matrice](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), ma l'approccio più diretto consiste nel creare una matrice di termini da rimuovere dal dizionario e quindi copiare solo i termini del dizionario che non si trovano nell'elenco di termini da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="736eb-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="736eb-p107">Eseguire il comando `$terms` per visualizzare l'elenco attuale di termini. L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="736eb-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="736eb-128">Eseguire questo comando per specificare i termini da rimuovere:</span><span class="sxs-lookup"><span data-stu-id="736eb-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="736eb-129">Eseguire questo comando per rimuovere effettivamente i termini dall'elenco:</span><span class="sxs-lookup"><span data-stu-id="736eb-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="736eb-p108">Eseguire il comando `$updatedTerms` per visualizzare l'elenco aggiornato di termini. L'output del comando è simile al seguente (i termini specificati sono stati rimossi):</span><span class="sxs-lookup"><span data-stu-id="736eb-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="736eb-p109">Ora basta aprire il file, aggiungere gli altri termini e salvare il file con la codifica Unicode (UTF-16). A questo punto, è possibile caricare i termini aggiornati e aggiornare il dizionario esistente.</span><span class="sxs-lookup"><span data-stu-id="736eb-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="736eb-134">Ora il dizionario esistente è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="736eb-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="736eb-135">Il campo `Identity` prende il nome del dizionario.</span><span class="sxs-lookup"><span data-stu-id="736eb-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="736eb-136">Se si vuole modificare anche il nome del dizionario con il cmdlet `set-`, basta aggiungere il parametro con il nuovo nome del dizionario `-Name` al comando precedente.</span><span class="sxs-lookup"><span data-stu-id="736eb-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="736eb-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="736eb-137">See Also</span></span>
- [<span data-ttu-id="736eb-138">Creare un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="736eb-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="736eb-139">Creare una tipologia personalizzata di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="736eb-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
