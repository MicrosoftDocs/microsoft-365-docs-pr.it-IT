---
title: Numero di identificazione nazionale dell'Unione europea
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: c00619ed649db53777fa3629deac0162a3589475
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805939"
---
# <a name="eu-national-identification-number"></a>Numero di identificazione nazionale dell'Unione europea

In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Combinazione a 24 caratteri di lettere, cifre e caratteri speciali
  
### <a name="pattern"></a>Modello

24 caratteri:
  
-  22 lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre o segni più 
    
- Due lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre, segni più o segni uguali
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_austria_eu_national_id_card` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_austria_eu_national_id_card` parola chiave from. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

numero d'identità austriaco
  
numero di identità nazionale
  
numero di identità
  
national id
  
Personalausweis Republik Österreich
  
## <a name="belgium"></a>Belgio

Per informazioni dettagliate, vedere la sezione "numero nazionale belga" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Dieci cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

Dieci cifre senza spazi e delimitatori
  
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Due cifre che corrispondono all'ordine di nascita
    
- Una cifra che corrisponde al sesso: una cifra pari per il maschio e una cifra dispari per la femmina
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_national_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_bulgaria_national_number` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_national_number` trova contenuto che corrisponde al modello. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

EGN
  
EGN #
  
numero nazionale bulgaro
  
numero nazionale
  
social security number
  
nationalnumber #
  
SSN #
  
SSN
  
nationalnumber
  
BNN #
  
BNN
  
numero ID personale
  
personalidnumber #
  
единен граждански номер
  
grazhdanski nomer
  
егн
  
егн #
  
## <a name="croatia"></a>Croazia

Per informazioni dettagliate, vedere la sezione "numero di identità della Croazia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

Dieci cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 Dieci cifre 
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_cyprus_eu_national_id_card` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_cyprus_eu_national_id_card` parola chiave from. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

numero di carta di identità
  
national identification number
  
numero ID personale
  
numero di carta di identità
  
ταυτοτητασ
  
## <a name="czech-republic"></a>Repubblica Ceca

Per informazioni dettagliate, vedere la sezione "numero di identità nazionale ceco" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).
  
## <a name="denmark"></a>Danimarca

Per informazioni dettagliate, vedere la sezione "numero di identificazione personale danese" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
- Una cifra che corrisponde al sesso e al secolo di nascita (numero dispari maschio, anche numero femmina; 1-2: XIX secolo; 3-4: XX secolo; 5-6: XXI secolo)
    
- Sei cifre che corrispondono alla data di nascita (AAMMGG)
    
- Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_estonia_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

codice di identificazione personale
  
numero di identificazione personale
  
national identification number
  
numero nazionale
  
numero ID personale
  
personalidnumber #
  
IK
  
isikukood
  
ID-kaart
  
## <a name="finland"></a>Finlandia

Per informazioni dettagliate, vedere la sezione "Finlandia National ID" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Per informazioni dettagliate, vedere la sezione "Francia National ID Card (CNI)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

11 cifre
  
### <a name="pattern"></a>Modello

11 cifre:
  
-  Una cifra che corrisponde al sesso (1-maschio, 2-Femmina, altri numeri sono possibili anche per i cittadini nati prima del 1900 o cittadini con doppia cittadinanza) 
    
- Sei cifre che corrispondono alla data di nascita (AAMMGG)
    
- Tre cifre che corrispondono a un numero di serie
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_hungary_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

numero di identificazione personale
  
identification number
  
numero ID personale
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato
  
### <a name="pattern"></a>Modello

Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato
  
Dal 01 gennaio 2013 a oggi:
  
-  Sette cifre 
    
- Una cifra di controllo
    
- Uno spazio o la lettera maiuscola "W" (distinzione tra maiuscole e minuscole)
    
Prima del 1 ° gennaio 2013:
  
-  Sette cifre 
    
- Una cifra di controllo
    
- Uno spazio o una lettera maiuscola (distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione trova contenuto che corrisponde al modello.
    
- Viene trovata una parola chiave from.
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione trova contenuto che corrisponde al modello.
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

numero di servizio pubblico personale
  
PPS No
  
reddito e numero di previdenza sociale
  
RSI No
  
numero di identificazione personale
  
identification number
  
numero ID personale
  
uimhir phearsanta seirbhíse poiblí
  
uimh. PSP
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Una combinazione di 16 caratteri di lettere e cifre nel modello specificato
  
### <a name="pattern"></a>Modello

Combinazione di lettere e cifre di 16 caratteri:
  
- Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia
    
- Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome
    
- Due cifre che corrispondono alle ultime cifre dell'anno di nascita
    
- Una lettera che corrisponde alla lettera per il mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)
    
- Due cifre che corrispondono al giorno del mese di nascita, al fine di distinguere tra i sessi, 40 viene aggiunto al giorno di nascita per le donne
    
- Quattro cifre che corrispondono al codice di area specifico per il comune in cui è nata la persona (i codici a livello nazionale vengono utilizzati per i paesi esteri)
    
- Una cifra di parità
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_italy_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

codice personale
  
numero di codice personale
  
numero di certificato personale
  
codice fiscale
  
personalcodeno #
  
numero ID personale
  
codice ID personale
  
codice personale
  
Numero certificato personale
  
numero personale
  
numero ID personale
  
codice ID personale
  
codice fiscale
  
## <a name="latvia"></a>Lettonia

### <a name="format"></a>Formato

11 cifre e un trattino nel formato specificato
  
### <a name="pattern"></a>Modello

11 cifre e un trattino:
  
-  Sei cifre che corrispondono alla data di nascita (GGMMAA) 
    
- Una lineetta
    
- Una cifra che corrisponde al secolo di nascita ("0" per il XIX secolo, "1" per il XX secolo e "2" per il XXI secolo)
    
- Quattro cifre, generate in modo casuale
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_latvia_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

codice personale
  
numero di codice personale
  
numero di certificato personale
  
personalcodeno #
  
numero ID personale
  
codice ID personale
  
personas Kods
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre senza spazi e delimitatori:
  
- Una cifra corrispondente al sesso e al secolo della nascita della persona
    
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Tre cifre che corrispondono al numero di serie della data di nascita
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_lithuania_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

codice numerico personale
  
numero di identificazione univoco
  
numero di servizio Citizen
  
numero di identità univoco
  
uniqueidentityno #
  
codice personale.
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas.
  
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre
  
- Una cifra corrispondente al sesso e al secolo della nascita della persona
    
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Tre cifre che corrispondono al numero di serie della data di nascita
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_luxemburg_eu_national_id_card` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_luxemburg_eu_national_id_card` parola chiave from. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

ID personale
  
numero ID personale
  
personalidno #
  
numero ID univoco
  
personalidnumber #
  
chiave ID univoco
  
codice ID personale
  
uniqueidkey #
  
codice singolo
  
ID individuale
  
ID eindeutige-Nummer
  
ID eindeutige
  
ID personnelle
  
personale di Numéro d'identification
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Sette cifre seguite da una lettera
  
### <a name="pattern"></a>Modello

Sette cifre seguite da una lettera:
  
-  Sette cifre 
    
- Una lettera maiuscola (distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_malta_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
  
- L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

codice numerico personale
  
numero di identificazione univoco
  
numero di servizio Citizen
  
numero di identità univoco
  
uniqueidentityno #
  
Kodiċi numerai personali
  
numru ta ' identifikazzjoni uniku
  
numru TAS-Servizz taċ-ċittadin
  
numru ta ' identità uniku
  
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

Nove cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una parola chiave from.
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

codice numerico personale
  
numero di identificazione univoco
  
numero di servizio Citizen
  
numero di identità univoco
  
uniqueidentityno #
  
BSN
  
BSN #
  
codice Numerieke di persoonlijke
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>Polonia

Per informazioni dettagliate, vedere la sezione "Poland National ID (PESEL)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portogallo

Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).
  
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

13 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

13 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_romania_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

codice numerico personale
  
numero di identificazione univoco
  
CNP
  
CNP #
  
pin
  
pin #
  
numero assicurativo
  
insurancenumber #
  
numero di identità univoco
  
uniqueidentityno #
  
Cod numerico personale
  
Cod identificare Personal
  
Cod Unic identificare
  
Număr personale Unic
  
număr identitate
  
Număr identificare Personal
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

Dieci cifre contenenti una barra rovesciata
  
### <a name="pattern"></a>Modello

Dieci cifre che contengono una barra rovesciata:
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovakia_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

numero di nascita
  
national identification number
  
numero di identificazione personale
  
social security number
  
nationalnumber #
  
SSN #
  
SSN
  
numero nazionale
  
numero ID personale
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre nel modello specificato:
  
-  Sette cifre che corrispondono alla data di nascita (DDMMLLL), dove "LLL" corrisponde alle ultime tre cifre dell'anno di nascita 
    
- Due cifre che corrispondono all'area di nascita
    
- Tre cifre che corrispondono a una combinazione di genere e numero di serie per le persone nate nello stesso giorno (000-499 per il maschio e 500-999 per le femmine)
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovenia_eu_national_id_card` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

codice numerico personale
  
numero di identificazione univoco
  
numero di registrazione univoco
  
numero di identità univoco
  
uniqueidentityno #
  
numero di cittadino Master univoco
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Sette cifre seguite da un carattere
  
### <a name="pattern"></a>Modello

Sette cifre seguite da un carattere
  
- Sette cifre
    
- Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_spain_eu_national_id_card` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_spain_eu_national_id_card"` parola chiave from. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

DNI
  
national identification number
  
numero di identità nazionale
  
numero assicurativo
  
numero di identificazione personale
  
identità nazionale
  
identità personale No
  
numero di identità univoco
  
nationalidno #
  
UniqueId #
  
DNI #
  
nationalid #
  
nie #
  
nie
  
nienúmero #
  
nie número
  
documento Nacional de Identidad
  
Identidad único
  
número Nacional Identidad
  
DNI número
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>Svezia

Per informazioni dettagliate, vedere la sezione "Sweden National ID" per [individuare i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vedere anche

[Tipi di informazioni riservate disponibili da cercare](what-the-sensitive-information-types-look-for.md)

