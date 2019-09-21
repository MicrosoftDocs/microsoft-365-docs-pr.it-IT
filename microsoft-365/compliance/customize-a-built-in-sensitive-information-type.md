---
title: Personalizzare una tipologia integrata di informazioni sensibili
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Quando si cercano informazioni sensibili nel contenuto, è necessario descriverle in una regola. La prevenzione della perdita dei dati (DLP) include regole per le tipologie più comuni di informazioni sensibili che è possibile utilizzare immediatamente. Per utilizzare queste regole, è necessario includerle in un criterio. Per modificare queste regole predefinite in modo che soddisfino esigenze specifiche dell'organizzazione, creare informazioni sensibili personalizzate. Questo argomento mostra come personalizzare il file XML che contiene la raccolta di regole esistenti per rilevare una gamma più ampia di potenziali informazioni sulle carte di credito.
ms.openlocfilehash: 99a65e7862eb1657c73c77b526e3b82b7595d248
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083031"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Personalizzare una tipologia integrata di informazioni sensibili

Quando si cercano informazioni sensibili nel contenuto, è necessario descriverle in una *regola*. La prevenzione della perdita dei dati (DLP) include regole per le tipologie più comuni di informazioni sensibili che è possibile utilizzare immediatamente. Per utilizzare queste regole, è necessario includerle in un criterio. Per modificare queste regole predefinite in modo che soddisfino esigenze specifiche dell'organizzazione, creare informazioni sensibili personalizzate. Questo argomento mostra come personalizzare il file XML che contiene la raccolta di regole esistenti per rilevare una gamma più ampia di potenziali informazioni sulle carte di credito. 
  
L'esempio riportato può essere applicato ad altre tipologie di informazioni sensibili predefinite. Per un elenco delle tipologie di informazioni sensibili predefinite e delle definizioni XML, vedere [Cosa individuano le tipologie di informazioni sensibili](what-the-sensitive-information-types-look-for.md). 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>Esportare il file XML delle regole correnti

Per esportare l'XML, è necessario [connettersi al Centro sicurezza e conformità tramite una sessione remota di PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
  
1. In PowerShell, digitare quanto segue per visualizzare le regole dell'organizzazione sullo schermo. Se non sono state create regole proprie, verranno visualizzate solo quelle predefinite con l'etichetta "Pacchetto di regole Microsoft".

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. Archiviare le regole dell'organizzazione in una variabile digitando quanto segue. L'archiviazione di elementi in una variabile li rende subito disponibili in un secondo momento, in un formato adatto per i comandi remoti di PowerShell.

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. Creare un file con formattazione XML con tutti i dati, digitando quanto segue (`Set-content` è la parte del cmdlet che scrive nel file XML). 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> Assicurarsi di utilizzare il percorso in cui è effettivamente archiviato il pacchetto di regole. `C:\custompath\` è un segnaposto. 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>Individuare la regola da modificare nel file XML

Con i cmdlet precedenti è stata esportata l'intera *raccolta di regole*, che include le regole predefinite fornite. Successivamente sarà necessario cercare in modo specifico la regola relativa al numero della carta di credito da modificare. 
  
1. Usare un editor di testo per aprire il file esportato nella sezione precedente.
    
2. Scorrere verso il basso fino al tag `<Rules>`, che corrisponde all'inizio della sezione che contiene le regole di prevenzione della perdita dei dati. Il file XML contiene le informazioni per l'intera raccolta di regole, quindi è necessario andare oltre le informazioni nella parte superiore per arrivare alle regole.
    
3. Cercare *Func_credit_card* per trovare la definizione della regola relativa al numero della carta di credito. Nel codice XML, i nomi delle regole non possono contenere spazi, quindi gli spazi in genere vengono sostituiti con caratteri di sottolineatura e i nomi delle regole vengono a volte abbreviati. Ne è un esempio la regola relativa al numero di previdenza sociale negli Stati Uniti, abbreviata in "SSN". Il codice XML della regola relativa al numero della carta di credito sarà simile all'esempio di codice seguente.
    
  ```xml
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

Dopo aver individuato la definizione della regola relativa al numero della carta di credito nel codice XML, è possibile personalizzare questo codice in base alle proprie esigenze. Come promemoria delle definizioni XML, vedere il [glossario dei termini](#term-glossary) alla fine di questo argomento.
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>Modificare il file XML o creare una nuova tipologia di informazioni sensibili

Prima di tutto, è necessario creare una nuova tipologia di informazioni sensibili, poiché non è possibile modificare direttamente le regole predefinite. Con una nuova tipologia di informazioni sensibili è possibile eseguire un'ampia gamma di operazioni, descritte in [Creare una tipologia personalizzata di informazioni sensibili in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md). Nell'esempio riportato, per una immediata comprensione, verranno rimosse solo le prove corroborative e verranno aggiunte parole chiave alla regola relativa al numero della carta di credito.
  
Tutte le definizioni della regola XML sono basate sul seguente modello generale. È necessario copiare e incollare la definizione XML relativa al numero della carta di credito nel modello, modificare alcuni valori (vedere i segnaposto ". . ." in questo esempio), quindi caricare il codice XML modificato come nuova regola da usare nei criteri.
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

Il risultato è un codice simile al codice XML seguente. I pacchetti di regole e le regole vengono identificati da GUID univoci, quindi è necessario generare due GUID: uno per il pacchetto di regole e uno per sostituire il GUID per la regola sul numero della carta di credito. Il GUID per l'ID entità nel codice di esempio seguente è quello della definizione della regola predefinita, che dovrà essere sostituito con un nuovo GUID. Esistono diversi modi per generare i GUID. Uno dei più semplici consiste nel digitare **[guid]::NewGuid()** in PowerShell. 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>Rimuovere il requisito prove corroborative da una tipologia di informazioni sensibili

Una volta creato un nuovo tipo di informazioni sensibili, è possibile caricarlo nel Centro sicurezza e conformità. Il passaggio successivo consiste nel rendere la regola più specifica. Modificare la regola in modo che cerchi solo numeri di 16 cifre che superano il checksum, ma che non richieda altre prove (corroborative), ad esempio parole chiave. A questo scopo, è necessario rimuovere la parte del codice XML che cerca le prove corroborative. Queste ultime sono molto utili per ridurre i falsi positivi. In questo caso, in genere ci sono parole chiave o la data di scadenza accanto al numero della carta di credito. Se si rimuove questa prova, è necessario anche modificare il valore che indica quanto si ritiene probabile aver trovato un numero di carta di credito, abbassando il valore di `confidenceLevel`, ovvero 85 nell'esempio.
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>Cercare le parole chiave specifiche per l'organizzazione

È anche possibile avere prove corroborative, ma con parole chiave diverse o aggiuntive, così come è possibile cambiare il percorso in cui trovare tali prove. È possibile modificare il `patternsProximity` per espandere o ridurre la finestra delle prove corroborative a 16 cifre. Per aggiungere parole chiave, è necessario definire un elenco di parole chiave e farvi riferimento all'interno della regola. Il codice XML seguente consente di aggiungere le parole chiave "carta aziendale" e "carta Contoso" in modo che i messaggi che contengono queste frasi (nei 150 caratteri del numero della carta di credito) verranno identificati come numero della carta di credito.
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>Caricare una regola

Per caricare una regola, attenersi alla seguente procedura.
  
1. Salvarla come file XML con codifica Unicode. Questo passaggio è fondamentale perché la regola non funziona se il file viene salvato con una codifica diversa.
    
2. [Connettersi al Centro sicurezza e conformità tramite una sessione remota di PowerShell.](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. In PowerShell digitare quanto segue.

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> Assicurarsi di utilizzare il percorso in cui è effettivamente archiviato il pacchetto di regole. `C:\custompath\` è un segnaposto. 
  
4. Per confermare, digitare Y, quindi premere **INVIO**.
5. Verificare che la nuova regola sia stata caricata e il nome visualizzato digitando:

```powershell
Get-DlpSensitiveInformationType
```

Per iniziare a usare la nuova regola per rilevare informazioni sensibili, è necessario aggiungere una regola a un criterio DLP. Per informazioni su come aggiungere una regola a un criterio, vedere [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md).
  
## <a name="term-glossary"></a>Glossario

Di seguito sono riportati i termini incontrati durante la procedura.
  
|**Termine**|**Definizione**|
|:-----|:-----|
|Entità|Le entità sono le tipologie di informazioni sensibili, come i numeri della carta di credito. Ciascuna entità ha un GUID univoco come ID. Copiando un GUID e cercandolo nell'XML, si troverà la definizione della regola XML e tutte le traduzioni localizzate di tale regola XML. Inoltre, la definizione può essere trovata individuando il GUID per la traduzione ed effettuando una ricerca.|
|Funzioni|Il file XML fa riferimento a `Func_credit_card`, una funzione nel codice compilato. Le funzioni vengono utilizzate per eseguire regex complessi e verificare la corrispondenza del checksum alle regole predefinite. Poiché è ciò che accade nel codice, alcune variabili non vengono visualizzate nel file XML.|
|IdMatch|L'identificatore per il quale i criteri cercano corrispondenze, ad esempio un numero di carta di credito.|
|Elenchi di parole chiave|Il file XML fa anche riferimento a `keyword_cc_verification` e `keyword_cc_name`, elenchi di parole chiave, in cui si ricercano corrispondenze per l'entità all'interno di `patternsProximity`. Questi attualmente non vengono visualizzati nell'XML.|
|Modello|Il modello contiene l'elenco di ciò che il tipo di informazione sensibile sta cercando. Questo include parole chiave, RegEx e funzioni interne, che eseguono attività come la verifica dei checksum. I tipi di informazioni sensibili possono avere più modelli con probabilità univoche. Questo è utile quando si crea un tipo di informazioni riservate che restituisce un livello elevato di probabilità se vengono trovate prove corroborative e un livello minore se vengono trovate poche o nessuna prova corroborativa.|
|Modello confidenceLevel|Il livello di affidabilità che il motore DLP individui una corrispondenza. Tale livello di affidabilità è associato a una corrispondenza con i modelli se vengono soddisfatti i requisiti del modello. Questa misura di affidabilità è da prendere in considerazione quando si usano regole di flusso di posta (note anche come regole di trasporto) di Exchange.|
|patternsProximity|Quando viene individuato qualcosa di simile al modello di un numero di carta di credito, `patternsProximity` è la prossimità al numero in cui verranno ricercate prove corroborative.|
|recommendedConfidence|Il livello di affidabilità consigliato per la regola. Si applica a entità e affinità. Per le entità, il numero non viene mai valutato rispetto al valore `confidenceLevel` dei modelli. È semplicemente un suggerimento che consente di scegliere un livello di affidabilità se si desidera applicarne uno. Per le affinità, il valore `confidenceLevel` del modello deve essere maggiore del numero `recommendedConfidence` per richiamare un'azione di regola di flusso di posta. Il valore `recommendedConfidence` è il livello di affidabilità predefinito usato nella regola di flusso di posta che richiama un'azione. Se si desidera, è anche possibile modificare manualmente la regola di flusso di posta da richiamare in base al livello di affidabilità del modello.|
   
## <a name="for-more-information"></a>Ulteriori informazioni

- [Cosa individuano le tipologie di informazioni sensibili](what-the-sensitive-information-types-look-for.md)
    
- [Creare una tipologia personalizzata di informazioni sensibili](create-a-custom-sensitive-information-type.md)
    
- [Panoramica relativa ai criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md)
