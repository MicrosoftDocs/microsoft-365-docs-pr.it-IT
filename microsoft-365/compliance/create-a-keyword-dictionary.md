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
# <a name="create-a-keyword-dictionary"></a>Creare un dizionario di parole chiave

La prevenzione della perdita di dati (DLP) è in grado di identificare, monitorare e proteggere le informazioni riservate. L'identificazione di informazioni riservate a volte richiede la ricerca di parole chiave, in particolare quando si identifica il contenuto generico (ad esempio la comunicazione correlata all'assistenza sanitaria) o la lingua inappropriata o esplicita. Anche se è possibile creare elenchi di parole chiave in tipi di informazioni riservate, gli elenchi di parole chiave sono di dimensioni limitate e richiedono la modifica di XML per crearli o modificarli. I dizionari keyword offrono una gestione più semplice delle parole chiave e su una scala molto più grande, supportando fino a 100.000 termini per dizionario.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Procedura di base per la creazione di un dizionario di parole chiave

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. Utilizzare il **Centro sicurezza & Compliance** ( [https://protection.office.com](https://protection.office.com) ) o connettersi **a &amp; PowerShell per Centro sicurezza e conformità**.
    
2. **Definire o caricare le parole chiave dall'origine desiderata**. La procedura guidata e il cmdlet accettano entrambi un elenco delimitato da virgole di parole chiave per creare un dizionario parola chiave personalizzato, in modo che questo passaggio vari leggermente a seconda di dove provengono le parole chiave. Una volta caricate, le parole chiave vengono codificate e convertite in una matrice di byte prima di essere importate.
    
3. **Creare il dizionario**. Scegliere un nome e una descrizione e creare il dizionario.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Creare un dizionario di parole chiave tramite il Centro sicurezza & Compliance

Seguire la procedura seguente per creare e importare parole chiave per un dizionario personalizzato:

1. Connettersi al centro sicurezza & Compliance ( [https://protection.office.com](https://protection.office.com) ).

2. Accedere a **Classificazioni > Tipi di informazioni sensibili**.

3. Selezionare **Crea** e immettere un **nome** e una **descrizione** per i tipi di informazioni sensibili, quindi selezionare **Avanti**

4. Selezionare **Aggiungere un elemento**, quindi selezionare **Dizionario (parole chiave grandi)** nell'elenco a discesa **Rilevare il contenuto che contiene**.

5. Selezionare **Aggiungere un dizionario**.

6. Nel controllo Ricerca selezionare **È possibile creare nuovi elementi, come Dizionari di parole chiave, qui**.

7. Immettere un **nome** per il dizionario personalizzato.

8. Selezionare **Importa** e quindi **Da testo** o **Da CSV** in base al tipo di file con parole chiave.

9. Nella finestra di dialogo File selezionare il file delle parole chiave nel computer locale o nella condivisione file di rete, quindi selezionare **Apri**.

10. Selezionare **Salva**, quindi selezionare il dizionario personalizzato nell'elenco **Dizionari di parole chiave**.

11. Selezionare **Aggiungi**, quindi **Avanti**.

12. Esaminare e finalizzare le selezioni dei tipi di informazioni sensibili, quindi selezionare **Fine**.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Creare un dizionario di parole chiave da un file con PowerShell

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Copiare le parole chiave in un file di testo e verificare che ogni parola chiave sia su una riga separata.
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
3. Leggere il file in una variabile eseguendo questo cmdlet:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Creare il dizionario eseguendo questo cmdlet:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Modifica di un dizionario di parole chiave esistente

Può essere necessario modificare le parole chiave in uno dei dizionari di parole chiave o modificare uno dei dizionari predefiniti. Attualmente è possibile aggiornare solo un dizionario di parole chiave personalizzato con PowerShell. 

Ad esempio, modificheremo alcuni termini in PowerShell, salviamo i termini localmente in cui è possibile modificarli in un editor e quindi aggiorniamo i termini precedenti sul posto. 

Prima di tutto, recuperare l'oggetto dizionario:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

`$dict`La stampa mostrerà le varie variabili. Le parole chiave stesse vengono memorizzate in un oggetto nel backend, ma `$dict.KeywordDictionary` contengono una rappresentazione in forma di stringa, che verrà utilizzata per modificare il dizionario. 

Prima di modificare il dizionario, è necessario riportare la stringa di termini in una matrice utilizzando il `.split(',')` metodo. Verranno quindi ripuliti gli spazi indesiderati tra le parole chiave con il `.trim()` metodo, lasciando solo le parole chiave che è possibile utilizzare. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
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

Eseguire questo comando per specificare i termini da rimuovere:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Eseguire questo comando per rimuovere effettivamente i termini dall'elenco:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
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

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Uso dei dizionari di parole chiave nei tipi di informazioni riservate personalizzati e nei criteri di prevenzione della perdita dei dati

I dizionari per parole chiave possono essere utilizzati come parte dei requisiti di corrispondenza per un tipo di informazioni riservate personalizzato oppure come tipo di informazioni riservate. Entrambi richiedono la creazione di un [tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type-in-scc-powershell.md). Seguire le istruzioni riportate nell'articolo collegato per creare un tipo di informazioni riservate. Dopo aver utilizzato il codice XML, è necessario l'identificatore GUID del dizionario per utilizzarlo.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Per ottenere l'identità del dizionario, eseguire questo comando e copiare il valore della proprietà **Identity**: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

L'output del comando avrà questo aspetto:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
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
