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
ms.openlocfilehash: e00466e4648ebe93f0658383515d1543f858e1b0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919373"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Modificare lo schema Exact Data Match per usare la corrispondenza configurabile

La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili. Se occorre autorizzare le varianti per una stringa esatta, è possibile usare la *corrispondenza configurabile* per comunicare a Microsoft 365 di ignorare il caso e alcuni delimitatori. 

> [!IMPORTANT]
> Usare questa procedura per modificare lo schema EDM e il file di dati esistenti.

1. Disinstallare dal computer **EdmUploadAgent.exe** che viene usato per connettersi a Microsoft 365 per caricare il file di dati e lo schema EDM.

2. Scaricare il file **EdmUploadAgent.exe** appropriato per l'abbonamento tramite i collegamenti seguenti:
    - [Commerciale + GCC](https://go.microsoft.com/fwlink/?linkid=2088639): consigliato per la maggior parte dei clienti commerciali
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521): specifico per gli abbonati al cloud di enti pubblici con sicurezza elevata
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807): specifico per i clienti del cloud del Dipartimento della difesa degli Stati Uniti

3. Autorizzare l'agente di caricamento di EDM, aprire la finestra del prompt dei comandi (come amministratore) ed eseguire il comando seguente:

   `EdmUploadAgent.exe /Authorize`

4. Se non si dispone di una copia attuale dello schema esistente, è necessario scaricarne una copia eseguendo questo comando:

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. Personalizzare lo schema in modo che ogni colonna utilizzi "caseInsensitive" e/o "ignoredDelimiters".  Il valore predefinito per "caseInsensitive" è "false" e per "ignoredDelimiters" è una stringa vuota. 

> [!NOTE]
> Il tipo di informazioni sensibili personalizzato, riportato di seguito, o il tipo di informazioni sensibili incorporato usato per rilevare il modello di Regex generico deve supportare il rilevamento degli input di variazione elencati con ignoredDelimiters. Ad esempio, il tipo di informazioni sensibili incorporate nel codice di previdenza sociale statunitense (SSN) può rilevare le variazioni dei dati che includono trattini, spazi o mancanza di spazi tra i numeri raggruppati che compongono il SSN. Di conseguenza, gli unici delimitatori rilevanti da includere in ignoredDelimiters di EDM per i dati SSN sono: trattino e spazio.

Di seguito è riportato uno schema di esempio che simula la corrispondenza senza distinzione tra maiuscole e minuscole tramite la creazione di colonne aggiuntive necessarie per riconoscere le variazioni tra maiuscole e minuscole nei dati sensibili.

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

Nell'esempio riportato in precedenza, le variazioni della colonna `PolicyNumber` originale non saranno più necessarie se vengono aggiunti `caseInsensitive` e `ignoredDelimiters`.

Per aggiornare questo schema in modo che EDM usi la corrispondenza configurabile, usare i contrassegni `caseInsensitive` e `ignoredDelimiters`.  Ecco come:

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

Il contrassegno `ignoredDelimiters` supporta qualsiasi carattere non alfanumerico. Ecco alcuni esempi:
- \.
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

Il contrassegno `ignoredDelimiters` non supporta:
- Caratteri 0-9
- A-Z
- a-z
- \"
- \,

6. Connettersi al Centro sicurezza e conformità seguendo le procedure contenute in [Connettersi a PowerShell per Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).

7. Aggiornare lo schema eseguendo questi cmdlet uno alla volta:

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. Se necessario, aggiornare il file di dati in base alla nuova versione dello schema

> [!TIP]
> In alternativa, è possibile eseguire una convalida nel file CSV prima di caricarlo, tramite l’esecuzione di:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>Per altre informazioni sui parametri supportati da EdmUploadAgent.exe>, eseguire
>
> `EdmUploadAgent.exe /?`

9. Aprire la finestra del prompt dei comandi (come amministratore) ed eseguire il comando seguente per l’hashing e il caricamento dei dati sensibili:

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>Articoli correlati

- [Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).
- [Definizioni delle entità tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)
- [Tipi di informazioni sensibili personalizzati](./sensitive-information-type-learn-about.md)
- [Panoramica sui criteri di DLP](data-loss-prevention-policies.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)