---
title: Linee guida per i pacchetti di test
description: Esaminare le linee guida relative al pacchetto di test
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323045"
---
# <a name="test-package-guidelines"></a>Linee guida per i pacchetti di test

## <a name="1---script-referencing"></a>1. Script che fa riferimento

Quando carichi un file .zip nel portale, tutto il contenuto di tale file viene decompresso in una cartella radice. Non è necessario scrivere codice per eseguire questa operazione di decompressione iniziale. Puoi anche fare riferimento a qualsiasi file all'interno del .zip usando il percorso relativo al file ZIP caricato.

Nell'esempio seguente viene illustrato come fare riferimento ai file binari/script dal campo di input nella scheda Attività. Il testo in blu deve essere immesso nel campo **Percorso script** **senza virgolette.**

È importante conoscere il contenuto all'interno del file ZIP prima di caricarlo. Spesso, quando si comprime una cartella, il computer locale crea una cartella principale sotto il file ZIP. In questo caso, il riferimento sarà come illustrato in **grassetto di** seguito:

 **Contoso_App_Folder.zip**
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**
  - Script.ps1 – **"Contoso_App_Folder/cartella1/script.ps1"**

Altre volte, il file ZIP potrebbe avere i file o il contenuto direttamente sotto di esso, ad esempio nessuna cartella di secondo livello:

 **Zip_file_uploaded.zip**
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - ScriptX.ps1 – **"ScriptX.ps1"**
  - Script.ps1 - **"cartella1/script.ps1"**
  
## <a name="2---script-execution"></a>2. Esecuzione dello script

**Test out-of-box:** Il pacchetto dell'applicazione deve contenere almeno tre script di PowerShell che eseguono l'installazione, l'avvio e la chiusura automatica dell'applicazione e delle relative dipendenze. Ogni script deve gestire il controllo dei propri prerequisiti, convalidarlo con esito positivo, nonché eseguire la pulizia dopo se stesso (se necessario).

**Test funzionali:** Il pacchetto dell'applicazione deve contenere almeno uno script di PowerShell. Se vengono forniti più script, gli script vengono eseguiti in sequenza di caricamento e un errore in uno script specifico interrompe l'esecuzione degli script successivi.

### <a name="script-requirements"></a>Requisiti degli script

• PowerShell versione 5.1+     

• Esecuzione automatica    

• Codice restituito errore               

• Convalidare l'esito positivo            

• Registrazione in una cartella di registro specifica dello script

Ogni script deve essere eseguito completamente automatico per essere eseguito correttamente nella pipeline di test.

> [!Note]
> Gli script devono restituire "0" al completamento corretto e un codice di errore diverso da zero se si verifica un errore durante l'esecuzione.

Ogni script deve verificare che sia stato eseguito correttamente. Ad esempio, lo script di installazione deve verificare l'esistenza di determinati file binari e/o chiavi del Registro di sistema nel sistema, al termine dell'esecuzione del file binario del programma di installazione per garantire con un ragionevole grado di sicurezza che l'installazione sia stata eseguita correttamente. 

Ciò è necessario per diagnosticare correttamente dove si verificano errori durante un'esecuzione di test, ad esempio non è possibile installare correttamente l'applicazione anziché non avviarla.

> [!Important]
> **Evitare quanto segue:** Gli script non devono riavviare il computer, se è necessario un riavvio, specificarlo durante il caricamento degli script.

## <a name="3---log-collection"></a>3. Raccolta log

Ogni script deve generare i log generati in una cartella denominata ```logs``` . Tutte le cartelle nella directory denominata ```logs``` verranno copiate e presentate per il download nella ```Test Results``` pagina.

Ad esempio, lo script di installazione (che può trovarsi nella directory **App/scripts/install)** può determinare l'output dei registri in: **logs/install.log**, in modo che il log finale sia in: **Apps/scripts/install/logs/install.log**

Il sistema preleva il file insieme ad altri file all'interno di altre cartelle ```install.log``` ```logs``` e lo fascicola per il download.


## <a name="4---application-binaries"></a>4. File binari dell'applicazione

Tutti i file binari e le dipendenze devono essere inclusi nel singolo file ZIP. 

Devono includere tutto il necessario per l'installazione dell'applicazione (ad esempio, il programma di installazione dell'applicazione); se l'applicazione ha una dipendenza da qualsiasi framework, ad esempio .NET Core/Standard o .NET Framework, questi devono essere inclusi nel file e fare riferimento correttamente negli script forniti.


> [!Note]
> Il file ZIP caricato non può contenere spazi o caratteri speciali nel nome

## <a name="next-steps"></a>Passaggi successivi

Passare all'articolo successivo per visualizzare alcune **domande frequenti**
> [!div class="nextstepaction"]
> [Passaggio successivo](faq.md)
