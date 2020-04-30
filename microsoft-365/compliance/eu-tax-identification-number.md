---
title: Numero di identificazione fiscale dell'Unione europea
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 5f779974266045d7099b599700c7168162d9d81e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938672"
---
# <a name="eu-tax-identification-number"></a>Numero di identificazione fiscale dell'Unione europea

In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale (TIN) dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Nove cifre con trattino e barra di inoltro opzionali
  
### <a name="pattern"></a>Modello

Nove cifre con trattino e barra di inoltro facoltativi:
  
-  Due cifre 
    
- Una lineetta (facoltativa)
    
- Tre cifre
    
- Una barra (facoltativa)
    
- Quattro cifre
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_austria_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

codice fiscale
  
numero
  
numero di registrazione fiscale
  
tax id
  
st.nr.
  
steuernummer
  
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
- Due cifre
    
- "0" o "1"
    
- Una cifra
    
- "0" o "1" o "2" o "3" 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_belgium_eu_tax_file_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_belgium_eu_tax_file_number` parola chiave from. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

codice fiscale
  
numero di registrazione nazionale
  
numero di registrazione fiscale
  
tax id
  
NIF
  
NIF #
  
numéro de Registre National
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Dieci cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_bulgaria_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
numero civile uniforme
  
bucn #
  
uniformcivilnumber #
  
ID civile uniforme
  
uniforme civile No
  
EGN
  
numero civile uniforme bulgaro
  
uniformcivilno #
  
EGN #
  
униформ граждански номер
  
ID униформ
  
ID граждански униформ
  
униформ граждански не
  
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
- Dieci cifre, scelte casualmente
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_croatia_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

codice fiscale
  
imposte
  
tax id
  
OID
  
OID #
  
Porezni broj
  
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

Otto cifre e una lettera nel modello specificato
  
### <a name="pattern"></a>Modello

Otto cifre e una lettera:
  
-  Un "0" 
    
- Sette cifre
    
- Una lettera (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_cyprus_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

codice fiscale
  
imposte
  
tax id
  
codice di identificazione fiscale
  
TIC
  
TIC #
  
αριθμός φορολογικού μητρώου
  
φορολογική ταυτότητα
  
κωδικός φορολογικού μητρώου
  
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Nove o dieci cifre con una barra rovesciata facoltativa
  
### <a name="pattern"></a>Modello

Nove o dieci cifre con un backslash facoltativo:
  
- Sei cifre 
    
- Una barra rovesciata (facoltativa)
    
- Tre o quattro cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_czech_republic_eu_tax_file_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_czech_republic_eu_tax_file_number` parola chiave from. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

codice fiscale
  
imposte
  
tax id
  
numero personale
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Dieci cifre contenenti un segno meno
  
### <a name="pattern"></a>Modello

Dieci cifre contenenti un segno meno:
  
-  Sei cifre che corrispondono alla data di nascita (GGMMAA) 
    
- Una lineetta
    
- Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde al secolo di nascita e l'ultima cifra corrisponde al sesso dell'individuo (dispari per il maschio e anche per le femmine)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_denmark_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

codice fiscale
  
imposte
  
tax id
  
numero CPR
  
CPR #
  
Nummer di pattinaggio
  
ID pattina
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
-  Una cifra che corrisponde al sesso e al secolo del parto, in cui un numero dispari indica il maschio e il numero pari indica la femmina come segue: 1,2 per il XIX secolo; 3,4 per il XX secolo; e 5,6 per il XXI secolo 
    
- Sei cifre che corrispondono alla data di nascita (AAMMGG)
    
- Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_estonia_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

codice fiscale
  
imposte
  
tax id
  
codice personale
  
maksunumber
  
ID maksu
  
isikukood
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinazione di 11 caratteri di cifre, lettere e segno più e meno
  
### <a name="pattern"></a>Modello

Una combinazione di 11 caratteri di cifre, lettere e segno più e meno:
  
- Sei cifre
    
- Uno dei seguenti: un segno più, un segno di sottrazione o la lettera "A" (senza distinzione tra maiuscole/minuscole), in cui il segno più significa Nato tra 1800-1899, il segno meno significa Nato tra 1900-1999 e "A" significa Nato 2000 e dopo
    
- Tre cifre
    
- Una lettera o un numero
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_finland_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

identification number
  
ID personale
  
numero di identità
  
numero di identificazione nazionale finlandese
  
personalidnumber #
  
national identification number
  
numero ID
  
ID nazionale No.
  
numero ID nazionale
  
ID No
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
numero identiteetti
  
Suomen Kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
Kansallinen tunnus numero
  
## <a name="france"></a>Francia

### <a name="format"></a>Formato

13 cifre per gli utenti e nove cifre per le entità
  
### <a name="pattern"></a>Modello

13 cifre per gli utenti:
  
- Una cifra che deve essere 0, 1, 2 o 3
    
- 12 cifre
    
Nove cifre per le entità
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_france_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

codice di identificazione fiscale
  
codice fiscale
  
tax id
  
numéro d'identification fiscale
  
## <a name="germany"></a>Germania

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
-  Dieci cifre 
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_germany_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

codice fiscale
  
tassa no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
taxid #
  
codice di identificazione fiscale
  
codice fiscale n.
  
steuernummer
  
ID Steuer
  
steueridentifikationsnummer
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_greece_eu_tax_file_number` parola chiave from. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

AFM
  
latta
  
ID IVA No.
  
ID IVA No
  
codice di identificazione fiscale
  
numero del registro di sistema fiscale
  
Registro fiscale No.
  
AFM #
  
latta #
  
taxidno #
  
taxregistryno #
  
αριθμός φορολογικού μητρώου
  
aφμ
  
aφμ αριθμός
  
φορολογικού μητρώου νο.
  
τον αριθμό φορολογικού μητρώου
  
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Dieci cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Dieci cifre:
  
-  Una cifra che deve essere "8" 
    
- Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dell'individuo
    
- Tre cifre che corrispondono al numero generato dalla possibilità di distinguere gli individui nati nello stesso giorno
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_hungary_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

numero di identificazione fiscale ungherese
  
Tin ungherese
  
numero di ID fiscale
  
numero di partita IVA
  
autorità tributaria No
  
numero dell'identità fiscale dell'ID fiscale
  
taxidnumber #
  
latta #
  
hungatiantin #
  
identificazione fiscale No
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Sette cifre seguite da una lettera senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Sette cifre seguite da una lettera:
  
-  Sette cifre 
    
- Una lettera (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_ireland_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

servizio pubblico no
  
servizio pubblico personale No
  
PPS No
  
servizio personale No
  
servizio PPS No
  
ppsno #
  
Irish PPS No
  
publicserviceno #
  
numero di servizio pubblico personale
  
uimhir phearsanta seirbhíse poiblí
  
PPS uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

16 lettere e cifre nel modello specificato
  
### <a name="pattern"></a>Modello

16 lettere e cifre:
  
-  Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia 
    
- Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome
    
- Due cifre che corrispondono alle ultime cifre dell'anno di nascita
    
- Una cifra corrispondente al mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)
    
- Due cifre che corrispondono al giorno del mese di nascita in cui 40 viene aggiunto al giorno di nascita per le femmine per differenziare dai maschi
    
- Quattro cifre che corrispondono a un codice di area specifico per il comune in cui è nata la persona: vengono utilizzati codici a livello nazionale per i paesi esteri
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_italy_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

codice fiscale
  
tassa no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
taxid #
  
codice fiscale
  
codice fiscale
  
## <a name="latvia"></a>Lettonia

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre nel modello specificato
  
-  Sei cifre che corrispondono alla data di nascita (GGMMAA) 
    
- Una cifra che corrisponde al secolo di nascita dove "0" corrisponde al XIX secolo, "1" corrisponde al 20 ° secolo e "2" corrisponde al XXI secolo
    
- Quattro cifre
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_latvia_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

codice fiscale
  
tassa no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
taxid #
  
codice di identificazione fiscale
  
codice fiscale n.
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_lithuania_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

codice fiscale
  
tassa no.
  
tax no #
  
taxnumber #
  
taxnumber
  
tax id
  
taxid #
  
codice di identificazione fiscale
  
codice fiscale n.
  
ID mokesčių
  
numeri mokesčių
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre:
  
-  11 cifre 
    
- Due cifre di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_luxemburg_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

codice fiscale
  
tassa no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
taxid #
  
codice di identificazione fiscale
  
codice fiscale n.
  
steuernummer
  
ID Steuer
  
steueridentifikationsnummer
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Per cittadini maltesi: 7 cifre e una lettera nel modello specificato
  
Nazionali non maltesi e soggetti maltesi: 9 cifre
  
### <a name="pattern"></a>Modello

Cittadini maltesi: 7 cifre e una lettera
  
-  Sette cifre 
    
- Una lettera (senza distinzione tra maiuscole e minuscole)
    
Nazionali non maltesi e soggetti maltesi: 9 cifre
  
-  9 cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_malta_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
  
- La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

codice fiscale
  
tassa no.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
taxid #
  
codice di identificazione fiscale
  
codice fiscale n.
  
numru Tat-Taxxa
  
ID Tat-Taxxa
  
numru ta ' identifikazzjoni Tat-Taxxa
  
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

Nove cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

9 cifre 
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_netherlands_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

numero di identificazione fiscale per i Paesi Bassi
  
identificazione fiscale per i Paesi Bassi
  
numero di identificazione fiscale per i Paesi Bassi
  
identificazione fiscale per i Paesi Bassi
  
codice di identificazione fiscale
  
ID delle tasse olandesi
  
numero di identificazione fiscale olandese
  
tax id
  
ID fiscale #
  
codice fiscale
  
tax no #
  
imposte #
  
latta
  
latta #
  
Tin olandesi
  
stagno degli olandesi
  
Nederlands identificatienummer di recente
  
identificatienummer van delasting
  
identificatienummer che dura
  
Nederlands identificatie di recente
  
l'ID di Nummer del Nederlands
  
Nederlands belastingnummer
  
BTW nummer
  
Nederlandse che durerà identificatie
  
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

Undici cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Undici cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_poland_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

codice fiscale
  
tassa no.
  
taxno #
  
taxnumber #
  
taxnumber
  
NIP
  
NIP #
  
tax id
  
ID fiscale #
  
ID NIP
  
ID NIP #
  
codice di identificazione fiscale
  
codice fiscale n.
  
numero di partita IVA
  
IVA No.
  
vatno #
  
ID partita IVA
  
ID partita IVA #
  
numero Identyfikacji Podatkowej
  
Polski numero Identyfikacji Podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>Portogallo

### <a name="format"></a>Formato

Nove cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_portugal_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

codice fiscale
  
tassa no.
  
taxno #
  
taxnumber #
  
taxnumber
  
NIF
  
NIF #
  
numero fiscale
  
número de identificação Fiscal
  
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_romania_eu_tax_file_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_romania_eu_tax_file_number` parola chiave from. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

tax id
  
numero di ID fiscale
  
Tax File No
  
tax file number
  
tax no
  
codice fiscale
  
taxid #
  
taxno #
  
ID-ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

10 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_slovakia_eu_tax_file_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovakia_eu_tax_file_number` parola chiave from. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

tax id
  
numero di ID fiscale
  
ID Tin
  
Tin No
  
ID Tin slovacco
  
latta
  
Tax File No
  
tax file number
  
tax no
  
codice fiscale
  
taxid #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

Otto cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovenia_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

tax id
  
numero di ID fiscale
  
ID Tin
  
Tin No
  
ID Tin sloveno
  
latta
  
Tax File No
  
tax file number
  
tax no
  
codice fiscale
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
številka davčne datoteke
  
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Sette o otto cifre e una o due lettere nel modello specificato
  
### <a name="pattern"></a>Modello

Persone fisiche spagnole con carta d'identità nazionale spagnola:
  
-  Otto cifre 
    
- Una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
Spagnoli non residenti senza una carta d'identità nazionale spagnola
  
- Una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)
    
- Sette cifre
    
- Una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:
  
- Una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)
    
-  Sette cifre 
    
- Una lettera maiuscola (con distinzione tra maiuscole e minuscole)
    
Stranieri con il numero di identificazione di un forestiero
  
- Una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole) 
    
- Sette cifre
    
- Una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
Stranieri senza il numero di identificazione di un forestiero
  
- Una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole) 
    
- Sette cifre
    
- Una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_spain_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

tax id
  
numero di ID fiscale
  
ID CIF
  
CIF No
  
ID CIF spagnolo
  
CIF
  
Tax File No
  
numero CIF spagnolo
  
tax file number
  
Spagnolo CIF No
  
tax no
  
codice fiscale
  
taxid #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de Impuesto corporativo
  
número de Identificación Fiscal
  
número CIF
  
cifnúmero #
  
## <a name="sweden"></a>Svezia

### <a name="format"></a>Formato

Dieci cifre e un simbolo nel modello specificato
  
### <a name="pattern"></a>Modello

Dieci cifre e un simbolo:
  
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Segno di addizione, segno meno o barra rovesciata
    
- Tre cifre che rendono il numero di identificazione univoco dove: 
    
  - Per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati
    
  - La cifra nella nona posizione indica il sesso per il maschio o per la femmina.
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_sweden_eu_tax_file_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

tax id
  
ID IVA No.
  
numero di ID fiscale
  
tax identification
  
identificazione fiscale #
  
tassa no.
  
imposte #
  
taxid #
  
file fiscale
  
Tax File No.
  
numero ID personale
  
ID pattinat Nummer
  
Identifikation skatet
  
personnummer
  
## <a name="uk"></a>Regno Unito

### <a name="format"></a>Formato

Riferimento per i contribuenti unici (UTR): 10 cifre senza spazi e delimitatori
  
Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
### <a name="pattern"></a>Modello

Riferimento per i contribuenti unici (UTR): 10 cifre
  
Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_uk_eu_tax_file_number` parola chiave from. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

tax id
  
ID IVA No.
  
numero di ID fiscale
  
tax identification
  
identificazione fiscale #
  
tassa no.
  
imposte #
  
taxid #
  
file fiscale
  
Tax File No.
  
## <a name="see-also"></a>Vedere anche

[Tipi di informazioni riservate disponibili da cercare](what-the-sensitive-information-types-look-for.md)

