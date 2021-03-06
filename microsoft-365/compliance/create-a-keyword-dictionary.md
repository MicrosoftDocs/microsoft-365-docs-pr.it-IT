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
ms.openlocfilehash: 8d313650f298f2ab26989bec9df1260918f7dd5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300108"
---
# <a name="create-a-keyword-dictionary"></a>Creare un dizionario di parole chiave

La prevenzione della perdita dei dati consente di identificare, monitorare e proteggere gli elementi sensibili. Per identificare gli elementi sensibili talvolta è necessario cercare le parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito. Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni sensibili, tali elenchi hanno dimensioni limitate e richiedono la modifica di file XML per la loro creazione o modifica. I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala più ampia, supportano fino a 1 MB di termini (dopo la compressione) per dizionario, e supportano qualsiasi lingua. Anche il limite del tenant è di 1 MB dopo la compressione. Il limite di 1 MB dopo la compressione significa che tutti i dizionari combinati di un tenant possono contenere quasi 1 milione di caratteri.

## <a name="keyword-dictionary-limits"></a>Limiti dizionario di parole chiave

Esiste un limite di 50 tipi di informazioni sensibili basati su dizionario di parole chiave che possono essere creati per tenant. Per informazioni sul numero di dizionari di parole chiave disponibili nel tenant, utilizzare le procedure descritte in [Connettersi a PowerShell nel Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell) per connettersi al tenant ed eseguire questo script di PowerShell.

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Passaggi di base per la creazione di un dizionario di parole chiave

Le parole chiave per il dizionario possono provenire da diverse origini, in genere da un file (ad esempio, un elenco con estensione csv o txt) importato nel servizio o tramite il cmdlet di PowerShell, da un elenco che viene immesso direttamente nel cmdlet di PowerShell o da un dizionario esistente. Quando si crea un dizionario di parole chiave, seguire gli stessi passaggi di base:
  
1. Usare **Centro sicurezza e conformità** ([https://protection.office.com](https://protection.office.com)) o connettersi a **PowerShell per &amp;Centro sicurezza e conformità**.
    
2. **Definire o caricare le parole chiave dall'origine designata**. La procedura guidata e il cmdlet accettano un elenco di parole chiave separate da virgole per creare un dizionario di parole chiave personalizzato, quindi questo passaggio può variare leggermente a seconda dell'origine delle parole chiave. Una volta caricate, le parole chiave vengono codificate e convertite in una matrice di byte prima di essere importate.
    
3. **Creazione del dizionario**. Scegliere un nome e una descrizione e creare il dizionario.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Creare un dizionario di parole chiave tramite il Centro sicurezza e conformità.

Seguire la procedura seguente per creare e importare parole chiave per un dizionario personalizzato:

1. Connettersi al Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)).

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

Spesso, quando si deve creare un dizionario di grandi dimensioni, vengono usate parole chiave provenienti da un file o da un elenco esportato da un'altra origine. In questo caso, si crea un dizionario di parole chiave contenente un elenco di termini inappropriati da filtrare nella posta elettronica esterna. Prima di tutto,[connettersi a PowerShell per ](/powershell/exchange/connect-to-scc-powershell) Centro sicurezza e conformità&amp;.
  
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
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Uso dei dizionari di parole chiave nei tipi di informazioni riservate personalizzati e nei criteri di prevenzione della perdita dei dati

I dizionari di parole chiave possono essere usati nell'ambito dei requisiti di corrispondenza per un tipo di informazioni sensibili personalizzato oppure proprio come tipo di informazioni sensibili. Entrambi richiedono la [creazione di un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type-in-scc-powershell.md). Seguire le istruzioni nell'articolo collegato per creare un tipo di informazioni sensibili. Una volta disponibile il file XML, per usare il dizionario è necessario l'identificatore GUID.
  
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

> [!NOTE]
> Microsoft 365 Information Protection supporta i set di caratteri a due byte nelle seguenti lingue:
> - Cinese (semplificato)
> - Cinese (tradizionale)
> - Coreano
> - Giapponese
>
>Il supporto è disponibile per i tipi di informazioni sensibili. Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).

> [!TIP]
> Per rilevare modelli contenenti caratteri cinesi/giapponesi e caratteri a byte singolo o per rilevare modelli contenenti caratteri cinesi/giapponesi e inglesi, definire due varianti della parola chiave o dell'espressione regolare. 
>
> Ad esempio, per rilevare una parola chiave come "机密的document", usare due varianti della parola chiave: una con uno spazio tra il testo giapponese e quello inglese e un'altra senza spazio tra il testo giapponese e quello inglese. Quindi, le parole chiave da aggiungere nel SIT devono essere "机密的 document" e "机密的document". Analogamente, per rilevare la frase "東京オリンピック2020", devono essere usate due varianti: "東京オリンピック 2020" e "東京オリンピック2020".
>
> Quando si crea un'espressione regolare usando un trattino a byte doppio o un punto a byte doppio, assicurarsi di eseguire l'escape di entrambi i caratteri come si farebbe con un trattino o un punto in un'espressione regolare. Di seguito è riportata un'espressione regolare di esempio per riferimento:
>
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> È consigliabile usare una corrispondenza di stringhe anziché una corrispondenza di parole in un elenco di parole chiave.
