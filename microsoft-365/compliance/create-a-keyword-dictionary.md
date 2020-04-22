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
description: Per identificare le informazioni riservate a volte è necessario cercare delle parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito. Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni riservate, questi elenchi hanno dimensioni limitate e richiedono la modifica di file XML per crearli o modificarli. I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala molto più ampia, supportano fino a 100.000 termini per dizionario.
ms.openlocfilehash: 67263c854f764be42d97061632567ec1b25214b4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636464"
---
# <a name="create-a-keyword-dictionary"></a>Creare un dizionario di parole chiave

La prevenzione della perdita di dati (DLP) è in grado di identificare, monitorare e proteggere le informazioni riservate. L'identificazione di informazioni riservate a volte richiede la ricerca di parole chiave, in particolare quando si identifica il contenuto generico (ad esempio la comunicazione correlata all'assistenza sanitaria) o la lingua inappropriata o esplicita. Anche se è possibile creare elenchi di parole chiave in tipi di informazioni riservate, gli elenchi di parole chiave sono di dimensioni limitate e richiedono la modifica di XML per crearli o modificarli. I dizionari keyword offrono una gestione più semplice delle parole chiave e su una scala molto più grande, supportando fino a 100.000 termini per dizionario.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Procedura di base per la creazione di un dizionario di parole chiave

Le parole chiave per il dizionario possono provenire da diverse origini, in genere da un file (ad esempio, un elenco con estensione csv o txt) importato nel servizio o tramite il cmdlet di PowerShell, da un elenco che viene immesso direttamente nel cmdlet di PowerShell o da un dizionario esistente. Quando si crea un dizionario di parole chiave, seguire gli stessi passaggi di base:
  
1. Utilizzare il **Centro sicurezza & Compliance** ([https://protection.office.com](https://protection.office.com)) o connettersi a **PowerShell per Centro sicurezza &amp; e conformità**.
    
2. **Definire o caricare le parole chiave dall'origine desiderata**. La procedura guidata e il cmdlet accettano entrambi un elenco delimitato da virgole di parole chiave per creare un dizionario parola chiave personalizzato, in modo che questo passaggio vari leggermente a seconda di dove provengono le parole chiave. Una volta caricate, le parole chiave vengono codificate e convertite in una matrice di byte prima di essere importate.
    
3. **Creare il dizionario**. Scegliere un nome e una descrizione e creare il dizionario.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Creare un dizionario di parole chiave tramite il Centro sicurezza & Compliance

Seguire la procedura seguente per creare e importare parole chiave per un dizionario personalizzato:

1. Connettersi al centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)).

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

Spesso, quando è necessario creare un dizionario di grandi dimensioni, è possibile utilizzare parole chiave da un file o da un elenco esportato da un'altra origine. In questo caso, è possibile creare un dizionario di parole chiave contenente un elenco di lingue inappropriate da schermare in posta elettronica esterna. È necessario innanzitutto [connettersi a PowerShell &amp; per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Copiare le parole chiave in un file di testo e verificare che ogni parola chiave sia su una riga separata.
    
2. Salvare il file di testo con codifica Unicode. In Blocco note, \> **Salva con nome** \> **codifica** \> **Unicode**.
    
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

La `$dict` stampa mostrerà le varie variabili. Le parole chiave stesse vengono memorizzate in un oggetto nel backend, `$dict.KeywordDictionary` ma contengono una rappresentazione in forma di stringa, che verrà utilizzata per modificare il dizionario. 

Prima di modificare il dizionario, è necessario riportare la stringa di termini in una matrice utilizzando il `.split(',')` metodo. Verranno quindi ripuliti gli spazi indesiderati tra le parole chiave `.trim()` con il metodo, lasciando solo le parole chiave che è possibile utilizzare. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

A questo punto si rimuovono alcuni termini dal dizionario. Il dizionario di esempio include solo alcune parole chiave, quindi è possibile evitare l'esportazione modificando il dizionario direttamente nel Blocco note. In genere, però, i dizionari contengono una grande quantità di testo, quindi è utile conoscere la procedura per modificarli facilmente in PowerShell.
  
Nell'ultimo passaggio le parole chiave sono state salvate in una matrice. Ci sono diversi modi per [rimuovere elementi da una matrice](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), ma l'approccio più diretto consiste nel creare una matrice di termini da rimuovere dal dizionario e quindi copiare solo i termini del dizionario che non si trovano nell'elenco di termini da rimuovere.
  
Eseguire il comando `$terms` per visualizzare l'elenco attuale di termini. L'output del comando avrà questo aspetto: 
  
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

Eseguire il comando `$updatedTerms` per visualizzare l'elenco aggiornato di termini. L'output del comando è simile al seguente (i termini specificati sono stati rimossi): 
  
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

Ora basta aprire il file, aggiungere gli altri termini e salvare il file con la codifica Unicode (UTF-16). A questo punto, è possibile caricare i termini aggiornati e aggiornare il dizionario esistente.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Ora il dizionario esistente è aggiornato. Il campo `Identity` prende il nome del dizionario. Se si vuole modificare anche il nome del dizionario con il cmdlet `set-`, basta aggiungere il parametro con il nuovo nome del dizionario `-Name` al comando precedente. 
  
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


Incollare l'identità nel file XML del tipo di informazioni riservate personalizzato e caricarlo. Il dizionario verrà visualizzato nell'elenco dei tipi di informazioni riservate e potrà essere usato direttamente nei criteri, specificando il numero di parole chiave che devono avere una corrispondenza.
  
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
