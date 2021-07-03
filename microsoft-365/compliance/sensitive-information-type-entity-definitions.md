---
title: Definizioni delle entità tipo di informazioni sensibili
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Sono disponibili 200 tipi di informazioni riservate che possono essere utilizzati nei criteri DLP. Questo articolo elenca tutti questi tipi di informazioni riservate e mostra cosa cerca un criterio DLP quando rileva ogni tipo.
ms.openlocfilehash: 614649367e72766d8df210fccbb4e3cdc9cdb4b6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287468"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definizioni delle entità tipo di informazioni sensibili

In questo articolo vengono elencate tutte le definizioni di entità del tipo di informazioni riservate. Ogni definizione mostra cosa cerca un criterio DLP per rilevare ogni tipo. Per ulteriori informazioni sui tipi di informazioni riservate, vedere [Tipi di informazioni riservate](sensitive-information-type-learn-about.md)

## <a name="aba-routing-number"></a>Numero di routing ABA

### <a name="format"></a>Formato

nove cifre che possono essere formattate o non formattate

### <a name="pattern"></a>Modello

- due cifre negli intervalli 00-12, 21-32, 61-72 o 80
- due cifre
- un trattino facoltativo
- quattro cifre
- un trattino facoltativo
- una cifra


### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio ha una probabilità media di rilevamento di questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ABA_Routing.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>Parole chiave

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- routing #
- routing no
- routing number
- routing transit number
- routing #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Numero DNI (Argentina National Identity)

### <a name="format"></a>Formato

Otto cifre con o senza punti

### <a name="pattern"></a>Modello

Otto cifre
- due cifre
- un punto facoltativo
- tre cifre
- un punto facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_argentina_national_id trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_argentina_national_id dall'utente.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina - Numero di identità nazionale
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Codice identificativo fiscale univoco argentina (CUIT/CUIL)

### <a name="format"></a>Formato

11 cifre con trattino

### <a name="pattern"></a>Modello

11 cifre con un trattino:
- due cifre in 20, 23, 24, 27, 30, 33 o 34
- un trattino (-)
- otto cifre
- un trattino (-)
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_Argentina_Unique_Tax_Key` trova contenuto che corrisponde al modello.
- Viene trovata una parola `Keyword_Argentina_Unique_Tax_Key` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_Argentina_Unique_Tax_Key` trova contenuto che corrisponde al modello.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- codice univoco di identificazione del personale 
- Clave Única de Identificación Tributaria
- codice identificativo personale univoco
- CUIL
- Chiave di identificazione fiscale univoca
- Chiave di identificazione univoca del personale
- Chiave univoca di identificazione del lavoro
- Codice di identificazione univoco del lavoro
- Identificazione univoca del codice di lavoro
- Chiave di identificazione univoca del lavoro
- Chiave univoca di identificazione del lavoro
- Codice univoco di identificazione fiscale
- Chiave univoca di identificazione fiscale
- Codice di identificazione univoco del lavoro
- Codice univoco di identificazione del lavoro
- Chiave univoca di identificazione del lavoro
- Chiave univoca di identificazione del lavoro
- ID fiscale
- taxID #
- taxId
- taxidnumber
- tax number
- tax no
- tax #
- tax #
- ID contribuente
- numero contribuente
- contribuente no
- contribuente #
- contribuente #
- identità fiscale
- tax identification
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>Numero di conto corrente bancario Australia

### <a name="format"></a>Formato

da sei a 10 cifre con o senza un numero di filiale dello stato della banca

### <a name="pattern"></a>Modello

Il numero di account è da 6 a 10 cifre.

Numero BSB australiano:
- tre cifre
- un trattino
- tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_australia_bank_account_number trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_australia_bank_account_number.
- L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_australia_bank_account_number trova contenuto che corrisponde al modello.

- Viene trovata una parola chiave da Keyword_australia_bank_account_number.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- iaea

## <a name="australia-business-number"></a>Numero di azienda Australia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft


### <a name="format"></a>Formato

11 cifre con delimitatori facoltativi

### <a name="pattern"></a>Modello

11 cifre con delimitatori facoltativi:

- due cifre
- un trattino o uno spazio facoltativo
- tre cifre
- un trattino o uno spazio facoltativo
- tre cifre
- un trattino o uno spazio facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_australian_business_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_australian_business_number parola chiave.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_australian_business_number trova contenuto che corrisponde al modello.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- australia business no
- numero di azienda
- abn #
- businessid #
- business id
- abn
- businessno #

## <a name="australia-company-number"></a>Numero società Australia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

nove cifre con delimitatori

### <a name="pattern"></a>Modello

nove cifre con delimitatori:

- tre cifre
- uno spazio
- tre cifre
- uno spazio
- tre cifre


### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Australian_Company_Number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_Australian_Company_Number.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Australian_Company_Number trova contenuto che corrisponde al modello.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- can
- australia società no
- australia società no #
- australia company number
- società australiana no
- società australiana no #
- numero di società australiano

## <a name="australia-drivers-license-number"></a>Numero di patente australiana

### <a name="format"></a>Formato

nove lettere e cifre

### <a name="pattern"></a>Modello

nove lettere e cifre:

- due cifre o lettere (senza distinzione tra maiuscole e minuscole)
- due cifre
- cinque cifre o lettere (senza distinzione tra maiuscole e minuscole)

OPPURE

- da una a due lettere facoltative (senza distinzione tra maiuscole e minuscole)
- da quattro a nove cifre

OPPURE

- nove cifre o lettere (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_australia_drivers_license_number.
- Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Patente di guida
- Patenti di guida
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic #
- Driver'Lics #
- Patente di guida #
- Patenti di guida #
- Driver' Lic#
- Driver'Lics#
- Driver'Licence#
- Driver' Licences#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences#

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'License
- Driver'Licenses
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense #
- DriverLicenses #
- Driver License#
- Driver Licenses#
- DriversLicense #
- DriversLicenses #
- Drivers License#
- Drivers Licenses#
- Driver'License #
- Driver'Licenses #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#

## <a name="australia-medical-account-number"></a>Numero di conto medico Australia

### <a name="format"></a>Formato

10-11 cifre

### <a name="pattern"></a>Modello

10-11 cifre:
- La prima cifra è compresa nell'intervallo 2-6
- La nona cifra è una cifra di controllo
- La decima cifra è la cifra del problema
- L'undicesima cifra (facoltativa) è il numero singolo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.
- Il checksum ha esito positivo.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare


## <a name="australia-passport-number"></a>Numero di passaporto australiano

### <a name="format"></a>Formato

otto o nove caratteri alfanumerici

### <a name="pattern"></a>Modello

- una lettera (N, E, D, F, A, C, U, X) seguita da sette cifre o
- Due lettere (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ) seguite da sette cifre.

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione `Regex_australia_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una parola `Keyword_australia_passport_number` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione `Regex_australia_passport_number` regolare trova contenuto che corrisponde al modello.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority


## <a name="australia-tax-file-number"></a>Numero di file fiscale australia

### <a name="format"></a>Formato

da otto a nove cifre

### <a name="pattern"></a>Modello

da otto a nove cifre in genere presentate con spazi come segue:
- tre cifre
- uno spazio facoltativo
- tre cifre
- uno spazio facoltativo
- da due a tre cifre in cui l'ultima cifra è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.
- Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.
- Il checksum ha esito positivo.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn

## <a name="austria-drivers-license-number"></a>Austria - Numero di patente di guida

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- L'espressione  `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_austria_eu_driver's_license_number` .

```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver's_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Carta d'identità Austria
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Una combinazione di 24 caratteri di lettere, cifre e caratteri speciali

### <a name="pattern"></a>Modello

24 caratteri:

-  22 lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre o segni più

- due lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre, segni più o segni di uguale

### <a name="checksum"></a>Checksum

Non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- L'espressione  `Regex_austria_eu_national_id_card` regolare trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_austria_eu_national_id_card` chiave from.

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- identity number
- national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Numero di passaporto austriano

### <a name="format"></a>Formato

Una lettera seguita da uno spazio facoltativo e sette cifre

### <a name="pattern"></a>Modello

Combinazione di una lettera, sette cifre e uno spazio:

- una lettera (senza distinzione tra maiuscole e minuscole)
- uno spazio (facoltativo)
- sette cifre

### <a name="checksum"></a>Checksum

non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_austria_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_austria_eu_passport_number` .

```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza

## <a name="austria-social-security-number"></a>Austria - Numero di previdenza sociale

### <a name="format"></a>Formato

10 cifre nel formato specificato

### <a name="pattern"></a>Modello

10 cifre:

- tre cifre che corrispondono a un numero di serie
- una cifra di controllo
- sei cifre che corrispondono alla data di nascita (DDMMYY)

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.
- viene trovata una  `Keywords_austria_eu_ssn_or_equivalent` parola chiave da.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- austrian ssn
- ehic number
- ehic no
- codice assicurativo
- insurancecode #
- numero di assicurazione
- assicurazione no
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- social security no
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Numero di identificazione fiscale Austria

### <a name="format"></a>Formato

nove cifre con trattino facoltativo e barra

### <a name="pattern"></a>Modello

nove cifre con trattino facoltativo e barra:

- due cifre
- un trattino (facoltativo)
- tre cifre
- una barra (facoltativo)
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_austria_eu_tax_file_number` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr.
- steuernummer
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- tax number

## <a name="austria-value-added-tax"></a>Imposta sul valore aggiunto dell'Austria
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Motivo alfanumerico a 11 caratteri

### <a name="pattern"></a>Modello

Motivo alfanumerico di 11 caratteri:

- A o a
- T o t
- Spazio facoltativo
- U o u
- spazio facoltativo
- due o tre cifre
- spazio facoltativo
- quattro cifre
- spazio facoltativo
- una o due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Austria_Value_Added_Tax trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_Austria_Value_Added_Tax da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Austria_Value_Added_Tax trova contenuto che corrisponde al modello.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- partita IVA
- vat #
- austrian vat number
- iva n.
- vatno #
- numero di imposta sul valore aggiunto
- austrian vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- partita IVA
- atu number
- uid number


## <a name="azure-documentdb-auth-key"></a>Chiave di autenticazione di Azure DocumentDB

### <a name="format"></a>Formato

La stringa "DocumentDb" seguita dai caratteri e dalle stringhe descritti nel modello seguente.

### <a name="pattern"></a>Modello

- Stringa "DocumentDb"
- Qualsiasi combinazione di 3-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- Un simbolo di maggiore di (>), un segno di uguale (=), una virgoletta (") o un apostrofo (')
- Qualsiasi combinazione di 86 lettere minuscole o maiuscole, cifre, barra (/) o segno più (+)
- Due segni di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova contenuto che corrisponde al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Stringa di connessione del database IAAS di Azure e stringa di connessione SQL azure

### <a name="format"></a>Formato

Stringa "Server", "server" o "origine dati" seguita dai caratteri e dalle stringhe descritti nel modello seguente, inclusa la stringa "cloudapp.azure.<!--no-hyperlink-->com" o "cloudapp.azure.<!--no-hyperlink-->net" o "database.windows.<!--no-hyperlink-->net" e la stringa "Password" o "password" o "pwd".

### <a name="pattern"></a>Modello

- la stringa "Server", "server" o "origine dati"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- Stringa "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net" o "database.windows.<!--no-hyperlink-->net"
- qualsiasi combinazione tra 1 e 300 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "Password", "password" o "pwd"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- uno o più caratteri che non sono un punto e virgola (;), virgolette (") o apostrofo (')
- un punto e virgola (;), virgolette (") o apostrofo (')

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureConnectionString trova contenuto che corrisponde al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Azure IoT stringa di connessione

### <a name="format"></a>Formato

La stringa "HostName" seguita dai caratteri e dalle stringhe descritti nel modello seguente, incluse le stringhe "azure-devices.<!--no-hyperlink-->net" e "SharedAccessKey".

### <a name="pattern"></a>Modello

- la stringa "HostName"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "azure-devices.<!--no-hyperlink-->net"
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "SharedAccessKey"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 43 lettere minuscole o maiuscole, cifre, barra (/) o segno più (+)
- un segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureIoTConnectionString trova contenuto che corrisponde al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Password dell'impostazione di pubblicazione di Azure

### <a name="format"></a>Formato

Stringa "userpwd=" seguita da una stringa alfanumerica.

### <a name="pattern"></a>Modello

- la stringa "userpwd="
- qualsiasi combinazione di 60 lettere minuscole o cifre
- virgolette (")

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova contenuto che corrisponde al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Stringa di connessione della cache di Azure Redis

### <a name="format"></a>Formato

Stringa "redis.cache.windows.<!--no-hyperlink-->net" seguito dai caratteri e dalle stringhe descritti nel modello seguente, inclusa la stringa "password" o "pwd".

### <a name="pattern"></a>Modello

- la stringa "redis.cache.windows.<!--no-hyperlink-->net"
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "password" o "pwd"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 43 caratteri minuscoli o maiuscoli, cifre, barra (/) o segno più (+)
- un segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova contenuto che corrisponde al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Firma di accesso condiviso di Azure

### <a name="format"></a>Formato

La stringa "sig" seguita dai caratteri e dalle stringhe delineati nel modello seguente.

### <a name="pattern"></a>Modello

- la stringa "sig"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di caratteri compresi tra 43 e 53 caratteri che siano lettere minuscole o maiuscole, cifre o il segno di percentuale (%)
- stringa "%3d"
- qualsiasi carattere che non sia una lettera minuscola o maiuscola, una cifra o un segno di percentuale (%)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureSAS trova contenuto che corrisponde al modello.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Stringa di connessione del bus di servizio di Azure

### <a name="format"></a>Formato

La stringa "EndPoint" seguita dai caratteri e dalle stringhe descritti nel modello seguente, incluse le stringhe "servicebus.windows.<!--no-hyperlink-->net" e "SharedAccesKey".

### <a name="pattern"></a>Modello

- la stringa "EndPoint"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "servicebus.windows.<!--no-hyperlink-->net"
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "SharedAccessKey"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 43 caratteri minuscoli o maiuscoli, cifre, barra (/) o segno più (+)
- un segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova contenuto che corrisponde al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Chiave dell'account di archiviazione di Azure

### <a name="format"></a>Formato

Stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe descritti nel modello seguente, inclusa la stringa "AccountKey".

### <a name="pattern"></a>Modello

- la stringa "DefaultEndpointsProtocol"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "AccountKey"
- da zero a due spazi vuoti
- un segno di uguale (=)
- da zero a due spazi vuoti
- qualsiasi combinazione di 86 caratteri minuscoli o maiuscoli, cifre, barra (/) o segno più (+)
- due segni di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureStorageAccountKey trova contenuto che corrisponde al modello.
- L'espressione CEP_AzureEmulatorStorageAccountFilter non trova contenuto corrispondente al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Tecnicamente, questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Archiviazione di Azure account utente (generica)

### <a name="format"></a>Formato

Qualsiasi combinazione di 86 lettere minuscole o maiuscole, cifre, barra (/) o segno più (+), preceduta o seguita dai caratteri indicati nel modello seguente.

### <a name="pattern"></a>Modello

- da zero a uno dei simboli di maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o simbolo di numero (#)
- qualsiasi combinazione di 86 caratteri minuscoli o maiuscoli, cifre, barra (/) o segno più (+)
- due segni di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova contenuto che corrisponde al modello.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Numero di patente di guida belgio

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_belgium_eu_driver's_license_number` .

```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver's_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Belgio - Numero nazionale

### <a name="format"></a>Formato

11 cifre più delimitatori facoltativi

### <a name="pattern"></a>Modello

11 cifre più delimitatori:
- sei cifre e due punti facoltativi nel formato AA. MM.DD per la data di nascita
- Delimitatore facoltativo da punto, trattino, spazio
- tre cifre sequenziali (dispari per i maschi, anche per le femmine)
- Delimitatore facoltativo da punto, trattino, spazio
- due cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_belgium_national_number.
- Il checksum ha esito positivo.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- identificazione
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identity
- iscrizione
- numero nazionale
- national register
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- personal id number
- personalausweis
- personalidnumber #
- registratie
- registrazione
- registrationsnumme
- registrierung
- social security number
- ssn #
- ssn
- steuernummer
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="belgium-passport-number"></a>Belgio - numero di passaporto

### <a name="format"></a>Formato

due lettere seguite da sei cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

due lettere e seguito da sei cifre

### <a name="checksum"></a>Checksum

non applicabile

### <a name="definition"></a>Definizione

 Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_belgium_eu_passport_number` .
- L'espressione `Regex_eu_passport_date2` regolare trova la data nel formato GG MM AA o una parola chiave da o viene `Keywords_eu_passport_date` `Keywords_belgium_eu_passport_number` trovata

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_belgium_eu_passport_number` .

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport livre
- Pass-Nr
- Passnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza

## <a name="belgium-value-added-tax-number"></a>Numero di imposta sul valore aggiunto del Belgio
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Motivo alfanumerico a 12 caratteri

### <a name="pattern"></a>Modello

Motivo alfanumerico a 12 caratteri:

- una lettera B o b
- una lettera E o e
- una cifra 0
- una cifra da 1 a 9
- un punto facoltativo o un trattino o uno spazio
- quattro cifre
- un punto facoltativo o un trattino o uno spazio
- quattro cifre


### <a name="checksum"></a>Checksum

Sì


### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_belgium_value_added_tax_number trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keywords_belgium_value_added_tax_number.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_belgium_value_added_tax_number trova contenuto che corrisponde al modello.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- partita IVA
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>Brasile - Numero CPF

### <a name="format"></a>Formato

11 cifre che includono una cifra di controllo e possono essere formattate o non formattate

### <a name="pattern"></a>Modello

Formattato:
- tre cifre
- un punto
- tre cifre
- un punto
- tre cifre
- un trattino
- due cifre che sono cifre di controllo

Non formattato:
- 11 cifre dove le ultime due sono cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_brazil_cpf.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Identificazione
- Registrazione
- Ricavi
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>Numero della persona giuridica del Brasile (CNPJ)

### <a name="format"></a>Formato

14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori

### <a name="pattern"></a>Modello

14 cifre più delimitatori:

- due cifre
- un punto
- tre cifre
- un punto
- tre cifre (queste prime otto cifre sono il numero di registrazione)
- una barra
- Numero di ramo a quattro cifre
- un trattino
- due cifre che sono cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_brazil_cnpj da un utente.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ
- CNPJ/MF
- CNPJ-MF
- Codice fiscale persone giuridiche
- Registro contribuenti
- Persona giuridica
- Persone giuridiche
- Stato della registrazione
- Business
- Company
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Situação cadastral
- Inscrição
- Empresa


## <a name="brazil-national-identification-card-rg"></a>Carta di identità nazionale (RG) del Brasile

### <a name="format"></a>Formato

Registro Geral (formato precedente): nove cifre

Registro de Identidade (RIC) (nuovo formato): 11 cifre

### <a name="pattern"></a>Modello

Registro Geral (formato precedente):
- due cifre
- un punto
- tre cifre
- un punto
- tre cifre
- un trattino
- una cifra che è una cifra di controllo

Registro de Identidade (RIC) (nuovo formato):
- 10 cifre
- un trattino
- una cifra che è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_brazil_rg trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave Keyword_brazil_rg.
- Il checksum ha esito positivo.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- carta di identità
- national id
- número de rregistro
- registro de Iidentidade
- registro geral
- RG (questa parola chiave fa distinzione tra maiuscole e minuscole)
- RIC (questa parola chiave fa distinzione tra maiuscole e minuscole)


## <a name="bulgaria-drivers-license-number"></a>Numero di patente di guida bulgaria

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_bulgaria_eu_driver's_license_number` .

```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver's_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Numero civile uniforme Bulgaria
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

10 cifre senza spazi e delimitatori

- sei cifre che corrispondono alla data di nascita (AAMMDD)
- due cifre che corrispondono all'ordine di nascita
- una cifra che corrisponde al sesso: una cifra pari per il maschio e una cifra dispari per la donna
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_bulgaria_eu_national_id_card` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_bulgaria_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_bulgaria_eu_national_id_card` trova contenuto che corrisponde al modello.

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn #
- bnn
- bucn #
- bucn
- nomer edinen grazhdanski
- egn #
- egn
- identification number
- national id
- numero nazionale
- nationalnumber #
- nationalnumber
- id personale
- personal no
- numero personale
- personalidnumber #
- social security number
- ssn #
- ssn
- uniform civil id
- uniform civil no
- numero civile uniforme
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- numero di cittadinanza univoco
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Numero di passaporto bulgaro

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_bulgaria_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_bulgaria_eu_passport_number` .

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- сасооотт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza

## <a name="canada-bank-account-number"></a>Canada - Numero di conto corrente bancario

### <a name="format"></a>Formato

7 o 12 cifre

### <a name="pattern"></a>Modello

Un numero di conto corrente bancario canadese è di 7 o 12 cifre.

Un numero di transito bancario canadese comprende:
- cinque cifre
- un trattino
- tre cifre OR
- zero "0"
- otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_canada_bank_account_number.
- L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_canada_bank_account_number.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit


## <a name="canada-drivers-license-number"></a>Canada - Numero di patente di guida

### <a name="format"></a>Formato

Varia in base alla provincia

### <a name="pattern"></a>Modello

Vari modelli che coprono:
- Alberta
- British Columbia
- Manitoba
- New Brunswick
- Terranova/Labrador
- Nova Scotia
- Ontario
- Prince Edward Island
- Québec
- Saskatchewan

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.
- Viene trovata una parola chiave da Keyword_canada_drivers_license.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- L'abbreviazione della provincia, ad esempio, AB
- Il nome della provincia, ad esempio, Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Patente di guida
- Patenti di guida
- Driver'Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- identificazione
- DL #
- DLS #
- CDL #
- CDLS #
- DriverLic #
- DriverLics #
- DriverLicense #
- DriverLicenses #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- Driver Lics#
- Driver License#
- Driver Licenses#
- Driver License#
- Driver Licences#
- DriversLic #
- DriversLics #
- DriversLicense #
- DriversLicenses #
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic #
- Driver'Lics #
- Driver'License #
- Driver'Licenses #
- Patente di guida #
- Patenti di guida #
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicense #
- Driver'sLicenses #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#
- Driver's Lics#
- Driver's License#
- Driver's Licenses#
- Driver's Licence#
- Driver's Licences#
- Permis de Conduire#
- id #
- ids #
- idcard card#
- idcard cards#
- idcard #
- identification card#
- identification cards#
- identificazione #


## <a name="canada-health-service-number"></a>Numero del servizio sanitario canadese

### <a name="format"></a>Formato

 10 cifre

### <a name="pattern"></a>Modello

10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_canada_health_service_number.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- uno psicologo
- workers compensation
- disabilità


## <a name="canada-passport-number"></a>Numero di passaporto canadese

### <a name="format"></a>Formato

due lettere maiuscole seguite da sei cifre

### <a name="pattern"></a>Modello

due lettere maiuscole seguite da sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola Keyword_canada_passport_number o Keyword_passport viene trovata.

```xml
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °


## <a name="canada-personal-health-identification-number-phin"></a>Canada personal health identification number (PHIN)

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_phin restituisce contenuti che corrispondono al modello.
- Vengono trovate almeno due parole Keyword_canada_phin o Keyword_canada_provinces.

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- Québec
- Northwest Territories
- Ontario
- British Columbia
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Canada


## <a name="canada-social-insurance-number"></a>Canada - Numero di previdenza sociale

### <a name="format"></a>Formato

nove cifre con trattini o spazi facoltativi

### <a name="pattern"></a>Modello

Formattato:
- tre cifre
- un trattino o uno spazio
- tre cifre
- un trattino o uno spazio
- tre cifre

Non formattato: nove cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.
- Almeno due dei modelli seguenti:
    - Viene trovata una parola chiave da Keyword_sin.
    - Viene trovata una parola chiave da Keyword_sin_collaborative.
    - La funzione Func_eu_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_sin.
- Il checksum ha esito positivo.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_sin"></a>Keyword_sin

- sin
- social insurance
- numero d'assurance sociale
- sins
- ssn
- ssns
- social security
- numero d'assurance social
- national identification number
- national id
- sin #
- soc ins
- social ins

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license
- drivers license
- driver's licence
- drivers licence
- DOB
- Data di nascita
- Compleanno
- Date of Birth


## <a name="chile-identity-card-number"></a>Numero di carta di identità cileno

### <a name="format"></a>Formato

da sette a otto cifre più delimitatori una cifra di controllo o una lettera

### <a name="pattern"></a>Modello

da sette a otto cifre più delimitatori:
- da una a due cifre
- un punto facoltativo
- tre cifre
- un punto facoltativo
- tre cifre
- un trattino
- una cifra o una lettera (senza distinzione tra maiuscole e minuscole), che è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_chile_id_card trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_chile_id_card parola chiave.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_chile_id_card trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- Correre
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- Correre #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Identità cilena n.
- Numero di identità cileno
- Identità cilena #
- Registro fiscale univoco
- Ruolo tributario univoco
- Ruolo fiscale univoco
- Numero tributario univoco
- Numero nazionale univoco
- Ruolo nazionale univoco
- Ruolo univoco nazionale
- Identità Cile n.
- Numero di identità cileno
- Identità cileno #


## <a name="china-resident-identity-card-prc-number"></a>Numero di carta d'identità (PRC) residente in Cina

### <a name="format"></a>Formato

18 cifre

### <a name="pattern"></a>Modello

18 cifre:
- sei cifre che sono un codice indirizzo
- otto cifre nel formato AAAAMMDD, ovvero la data di nascita
- tre cifre che sono un codice d'ordine
- una cifra che è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_china_resident_id trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_china_resident_id.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_china_resident_id trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Carta d’identità per residenti
- PRC
- Carta d’identità
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定


## <a name="credit-card-number"></a>Numero di carta di credito

### <a name="format"></a>Formato

Da 14 a 16 cifre che possono essere formattate o non formattate (dddddddd) e che devono superare il test Luhn.

### <a name="pattern"></a>Modello

Rileva le carte di tutte le principali marche in tutto il mondo, tra cui Visa, MasterCard, Discover Card, JCB, American Express, carte regalo e carte da pranzo.

### <a name="checksum"></a>Checksum

Yes, il checksum Luhn

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_credit_card restituisce contenuti che corrispondono al modello.
- Si verifica una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_cc_verification.
    - Viene trovata una parola chiave da Keyword_cc_name.
    - La funzione Func_expiration_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_credit_card restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- 
cód. segurança
- cod. seguranca

- cod. segurança

- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- transazione
- numero di transazione
- numero di riferimento
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso
- Visa
- mastercard
- master card
- mc
- mastercard
- master cards
- diner's Club
- diners club
- dinersclub
- discover
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc #
- cc#:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- cardholder
- card holders
- titolari di carte
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
- atm card
- atmcard
- atm cards
- atmcards
- enroute
- en route
- card type
- Cardmember Acct
- cardmember account
- Cardno
- Scheda aziendale
- Schede aziendali
- Tipo di scheda
- numero dell'account della carta
- account membro della carta
- Cardmember Acct.
- card no.
- scheda no
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninchabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- No. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- no do cartao
- No. do cartão
- no. do cartao

- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Croatia driver's license number

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- L'espressione  `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_croatia_eu_driver's_license_number` .

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver's_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Numero di carta d'identità della Croazia
Questa entità è inclusa nel tipo di informazioni riservate NUMERO DI IDENTIFICAZIONE NAZIONALE UE. È disponibile come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_croatia_id_card trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_croatia_id_card da un utente.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- master citizen number
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- numero di identificazione personale
- porezni broj
- porezni identifikacijski broj
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="croatia-passport-number"></a>Numero di passaporto croato

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_croatia_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_croatia_eu_passport_number` .

```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>Numero di identificazione personale (OIB) della Croazia

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre:
- 10 cifre
- la cifra finale è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_croatia_eu_tax_file_number da un utente.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- master citizen number
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- numero di identificazione personale
- porezni broj
- porezni identifikacijski broj
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="cyprus-drivers-license-number"></a>Numero di licenza per i driver di Cipro

### <a name="format"></a>Formato

12 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

12 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_cyprus_eu_driver's_license_number` .

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver's_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Carta d'identità di Cipro
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

10 cifre

### <a name="checksum"></a>Checksum

non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_cyprus_eu_national_id_card` regolare trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_cyprus_eu_national_id_card` chiave from.

```xml
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id numero di carta
- numero di carta di identità
- kimlik karti
- national identification number
- personal id number
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Numero di passaporto di Cipro

### <a name="format"></a>Formato

una lettera seguita da 6-8 cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

una lettera seguita da sei a otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_cyprus_eu_passport_number` .
- L'espressione `Regex_cyprus_eu_passport_date` regolare trova la data nel formato GG/MM/AAAA o viene trovata una parola chiave `Keywords_cyprus_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_cyprus_eu_passport_number` .

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- scade il
- rilasciato il


## <a name="cyprus-tax-identification-number"></a>Codice fiscale di Cipro
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

otto cifre e una lettera nello schema specificato

### <a name="pattern"></a>Modello

otto cifre e una lettera:

- a "0" o "9"
- sette cifre
- una lettera (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_cyprus_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- codice di identificazione fiscale
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- tin id
- tin no
- tin #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Numero di patente di guida ceco

### <a name="format"></a>Formato

due lettere seguite da sei cifre

### <a name="pattern"></a>Modello

otto lettere e cifre:

- lettera "E" (senza distinzione tra maiuscole e minuscole)
- Una lettera
- uno spazio (facoltativo)
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_czech_republic_eu_driver's_license_number` .

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver's_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských prýkazých


## <a name="czech-passport-number"></a>Numero di passaporto ceco

### <a name="format"></a>Formato

otto cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

otto cifre senza spazi o delimitatori

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_czech_republic_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_czech_republic_eu_passport_number` .

```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="czech-personal-identity-number"></a>Numero di identità personale ceco

### <a name="format"></a>Formato

nove cifre con barra facoltativa (formato precedente) 10 cifre con barra facoltativa (nuovo formato)

### <a name="pattern"></a>Modello

nove cifre (formato precedente):
- sei cifre che rappresentano la data di nascita
- una barra facoltativa
- tre cifre

10 cifre (nuovo formato):
- sei cifre che rappresentano la data di nascita
- una barra facoltativa
- quattro cifre in cui l'ultima cifra è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione Func_czech_id_card trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_czech_id_card da un utente.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione Func_czech_id_card_new_format trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- numero di nascita
- czech republic id
- czechidno #
- daňové číslo
- identifikační číslo
- identity no
- identity number
- identityno #
- identityno
- numero di assicurazione
- national identification number
- nationalnumber #
- numero nazionale
- osobní číslo
- personalidnumber #
- personal id number
- numero di identificazione personale
- numero personale
- pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- social security number
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- numero di identificazione univoco


## <a name="denmark-drivers-license-number"></a>Numero di patente di guida danimarca

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_denmark_eu_driver's_license_number` .

```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver's_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Numero di passaporto danimarca

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_denmark_eu_passport_number` .
- L'espressione `Regex_eu_passport_date2` regolare trova la data nel formato GG MM AA o una parola chiave `Keywords_eu_passport_date` da.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_denmark_eu_passport_number` .

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="denmark-personal-identification-number"></a>Numero di identificazione personale Danimarca

### <a name="format"></a>Formato

10 cifre contenenti una lineetta

### <a name="pattern"></a>Modello

10 cifre:
- sei cifre nel formato DDMMYY, ovvero la data di nascita
- un trattino
- quattro cifre in cui la cifra finale è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Func_denmark_eu_tax_file_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_denmark_id da un utente.
- Il checksum ha esito positivo.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Func_denmark_eu_tax_file_number trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- health card
- numero della carta di assicurazione sanitaria
- numero di assicurazione sanitaria
- identification number
- identifikationsnummer
- identifikationsnummer #
- identity number
- krankenkassennummer
- nationalid #
- nationalnumber #
- numero nazionale
- personalidnumber #
- personalidentityno #
- personal id number
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- skat id
- skat kode
- skat nummer
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- codice fiscale
- carta di assicurazione sanitaria di viaggio
- uniqueidentityno #
- tax number
- numero di registrazione fiscale
- tax id
- codice fiscale
- rullato #
- taxnumber #
- tax no
- taxno #
- taxnumber
- identificazione fiscale no
- tin #
- taxidno #
- taxidnumber #
- tax no #
- tin id
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>Numero dea (Drug Enforcement Agency)

### <a name="format"></a>Formato

due lettere seguite da sette cifre

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- una lettera (senza distinzione tra maiuscole e minuscole) da questo set di lettere possibili: abcdefghjklmnprstux, che è un codice registrante
- una lettera (senza distinzione tra maiuscole e minuscole), ovvero la prima lettera del cognome o della cifra "9" del dichiarante
- sette cifre, l'ultima delle quali è la cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_dea_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola `Keyword_dea_number` chiave da
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_dea_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea #
- drug enforcement administration
- drug enforcement agency


## <a name="estonia-drivers-license-number"></a>Numero di patente di guida estonia

### <a name="format"></a>Formato

due lettere seguite da sei cifre

### <a name="pattern"></a>Modello

due lettere e sei cifre:

- le lettere "ET" (senza distinzione tra maiuscole e minuscole)
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_estonia_eu_driver's_license_number` .

```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver's_license_number

-- permis de conduire
- juhilubade numbrid
- juhiloa number
- juhiluba


## <a name="estonia-personal-identification-code"></a>Estonia Personal Identification Code
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

11 cifre:

- una cifra che corrisponde al sesso e al secolo di nascita (numero dispari maschile, numero pari femminile; 1-2: 19° secolo; 3-4: 20° secolo; 5-6: 21° secolo)
- sei cifre che corrispondono alla data di nascita (AAMMDD)
- tre cifre che corrispondono a un numero seriale che separa le persone nate nella stessa data
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_estonia_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.

```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- numero nazionale
- codice personale
- personal id number
- codice di identificazione personale
- numero di identificazione personale
- personalidnumber #
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="estonia-passport-number"></a>Numero di passaporto estone

### <a name="format"></a>Formato

una lettera seguita da sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

una lettera seguita da sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_estonia_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_estonia_eu_passport_number` .

```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku pass passi number passinumbrid document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="eu-debit-card-number"></a>Numero di carta di debito dell'Unione europea

### <a name="format"></a>Formato

16 cifre

### <a name="pattern"></a>Modello

Modello complesso e affidabile

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.
- Si verifica almeno una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_eu_debit_card.
    - Viene trovata una parola chiave da Keyword_card_terms_dict.
    - Viene trovata una parola chiave da Keyword_card_security_terms_dict.
    - Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.
    - La funzione Func_expiration_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number
- card number
- card no.
- security number
- cc #

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr
- acct num
- acct no
- american express
- americanexpress
- americano espresso
- amex
- atm card
- atm cards
- atm kaart
- atmcard
- atmcards
- atmkaart
- atmkaarten
- bancontact
- bank card
- bankkaart
- card holder
- card holders
- card num
- card number
- card numbers
- card type
- cardano numerico
- cardholder
- titolari di carte
- cardnumber
- cardnumbers
- carta bianca
- carta credito
- carta di credito
- cartao de credito
- cartao de crédito
- cartao de debito
- ○cartao de débito
- carte bancaire
- carte blanche
- carte bleue
- carte de credit
- carte de crédit
- carte di credito
- carteblanche
- cartão de credito
- cartão de crédito
- cartão de debito
- cartão de débito
- cb
- ccn
- check card
- check cards
- checkcard
- checkcards
- chequekaart
- cirrus
- cirrus-edc-maestro
- controlekaart
- controlekaarten
- credit card
- credit cards
- creditcard
- creditcards
- debetkaart
- debetkaarten
- debit card
- debit cards
- debitcard
- debitcards
- debito automatico
- diners club
- dinersclub
- discover
- discover card
- discover cards
- discovercard
- discovercards
- débito automático
- edc
- eigentümername
- european debit card
- hoofdkaart
- hoofdkaarten
- in viaggio
- japanese card bureau
- japanse kaartdienst
- jcb
- kaart
- kaart num
- kaartaantal
- kaartaantallen
- kaarthouder
- kaarthouders
- karte
- karteninhaber
- karteninchabers
- kartennr
- kartennummer
- kreditkarte
- kreditkarten-nummer
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartennummer
- kreditkartentyp
- maestro
- master card
- master cards
- mastercard
- mastercard
- mc
- mister cash
- n carta
- carta
- no de tarjeta
- no do cartao
- no do cartão
- no. de tarjeta

- no. do cartao

- no. do cartão

- nr carta
- nr. carta

- numeri di scheda
- numero carta
- numero de cartao
- numero de carte
- numero de cartão
- numero de tarjeta
- numero della carta
- numero di carta
- numero di scheda
- numero do cartao
- numero do cartão
- numéro de carte
- nº carta
- nº de carte
- nº de la carte
- nº de tarjeta
- nº do cartao
- nº do cartão
- nº. do cartão

- número de cartao
- número de cartão
- número de tarjeta
- número do cartao
- scheda dell'assegno
- scheda dell'atmosfera
- scheda dell'atmosfera
- scheda della banca
- scheda di controllo
- scheda di debito
- scheda matrice
- schede dell'atmosfera
- schede di controllo
- schede di debito
- schede matrici
- scoprono la scheda
- scoprono le schede
- solo
- supporti di scheda
- supporto di scheda
- switch
- tarjeta atm
- tarjeta credito
- tarjeta de atm
- tarjeta de credito
- tarjeta de debito
- tarjeta debito
- tarjeta no
- tarjetahabiente
- tipo della scheda
- ufficio giapponese della
- scheda
- v pay
- v-pay
- visa
- visa plus
- visa electron
- visto
- visum
- vpay

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification
- cardi la verifica
- cid
- cod seg
- cod seguranca
- cod segurança
- cod sicurezza
- cod. seg

- cod. seguranca

- cod. segurança

- cod. sicurezza

- codice di sicurezza
- codice di verifica
- codigo
- codigo de seguranca
- codigo de segurança
- crittogramma
- crittogramma
- cryptogramme
- cv2
- cvc
- cvc2
- cvn
- cvv
- cvv2
- cód seguranca
- cód segurança
- cód. seguranca

- cód. segurança

- código
- código de seguranca
- código de segurança
- de kaart controle
- geeft nr uit
- issue no
- issue number
- kaartidentificatienummer
- kreditkartenprufnummer
- kreditkartenprüfnummer
- kwestieaantal
- no. dell'edizione

- no. di sicurezza

- numero de securite
- numero de verificacao
- numero dell'edizione
- numero di identificazione della
- scheda
- numero di sicurezza
- numero van veiligheid
- numéro de sécurité
- nº autorizzazione
- número de verificação
- perno il blocco
- pin block
- prufziffer
- prüfziffer
- security code
- security no
- security number
- sicherheits kode
- sicherheitscode
- sicherheitsnummer
- speldblok
- veiligheid nr
- veiligheidsaantal
- veiligheidscode
- veiligheidsnummer
- verfalldatum

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf
- data de expiracao
- data de expiração
- data del exp
- data di exp
- data di scadenza
- data em que expira
- data scad
- data scadenza
- date de validité
- datum afloop
- datum van exp
- de afloop
- espira
- espira
- exp date
- exp datum
- scadenza
- scadenza
- scade
- scadenza
- fecha de expiracion
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- valable
- validade
- valido hasta
- valor
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta


## <a name="eu-drivers-license-number"></a>Numero di patente di guida UE

Queste entità sono nel numero di patente di guida dell'UE e sono tipi di informazioni riservate.

- [Austria](#austria-drivers-license-number)
- [Belgio](#belgium-drivers-license-number)
- [Bulgaria](#bulgaria-drivers-license-number)
- [Croazia](#croatia-drivers-license-number)
- [Cipro](#cyprus-drivers-license-number)
- [Ceco](#czech-drivers-license-number)
- [Danimarca](#denmark-drivers-license-number)
- [Estonia](#estonia-drivers-license-number)
- [Finlandia](#finland-drivers-license-number)
- [Francia](#france-drivers-license-number)
- [Germania](#germany-drivers-license-number)
- [Grecia](#greece-drivers-license-number)
- [Ungheria](#hungary-drivers-license-number)
- [Irlanda](#ireland-drivers-license-number)
- [Italia](#italy-drivers-license-number)
- [Lettonia](#latvia-drivers-license-number)
- [Lituania](#lithuania-drivers-license-number)
- [Luxemburg](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Paesi Bassi](#netherlands-drivers-license-number)
- [Polonia](#poland-drivers-license-number)
- [Portogallo](#portugal-drivers-license-number)
- [Romania](#romania-drivers-license-number)
- [Slovacchia](#slovakia-drivers-license-number)
- [Slovenia](#slovenia-drivers-license-number)
- [Spagna](#spain-drivers-license-number)
- [Svezia](#sweden-drivers-license-number)
- [Regno Unito](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Numero di identificazione nazionale DELL

Queste entità sono nel numero di identificazione nazionale dell'UE e sono tipi di informazioni riservate.

- [Austria](#austria-identity-card)
- [Belgio](#belgium-national-number)
- [Bulgaria](#bulgaria-uniform-civil-number)
- [Croazia](#croatia-identity-card-number)
- [Cipro](#cyprus-identity-card)
- [Ceco](#czech-personal-identity-number)
- [Danimarca](#denmark-personal-identification-number)
- [Estonia](#estonia-personal-identification-code)
- [Finlandia](#finland-national-id)
- [Francia](#france-national-id-card-cni)
- [Germania](#germany-identity-card-number)
- [Grecia](#greece-national-id-card)
- [Ungheria](#hungary-personal-identification-number)
- [Irlanda](#ireland-personal-public-service-pps-number)
- [Italia](#italy-fiscal-code)
- [Lettonia](#latvia-personal-code)
- [Lituania](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Paesi Bassi](#netherlands-citizens-service-bsn-number)
- [Polonia](#poland-national-id-pesel)
- [Portogallo](#portugal-citizen-card-number)
- [Romania](#romania-personal-numeric-code-cnp)
- [Slovacchia](#slovakia-personal-number)
- [Slovenia](#slovenia-unique-master-citizen-number)
- [Spagna](#spain-dni)
- [Regno Unito](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>Numero di passaporto UE

Queste entità sono nel numero di passaporto ue e sono tipi di informazioni riservate. Queste entità sono nel bundle del numero di passaporto ue.

- [Austria](#austria-passport-number)
- [Belgio](#belgium-passport-number)
- [Bulgaria](#bulgaria-passport-number)
- [Croazia](#croatia-passport-number)
- [Cipro](#cyprus-passport-number)
- [Ceco](#czech-passport-number)
- [Danimarca](#denmark-passport-number)
- [Estonia](#estonia-passport-number)
- [Finlandia](#finland-passport-number)
- [Francia](#france-passport-number)
- [Germania](#germany-passport-number)
- [Grecia](#greece-passport-number)
- [Ungheria](#hungary-passport-number)
- [Irlanda](#ireland-passport-number)
- [Italia](#italy-passport-number)
- [Lettonia](#latvia-passport-number)
- [Lituania](#lithuania-passport-number)
- [Luxemburg](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Paesi Bassi](#netherlands-passport-number)
- [Polonia](#poland-passport-number)
- [Portogallo](#portugal-passport-number)
- [Romania](#romania-passport-number)
- [Slovacchia](#slovakia-passport-number)
- [Slovenia](#slovenia-passport-number)
- [Spagna](#spain-passport-number)
- [Svezia](#sweden-passport-number)
- [Regno Unito](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Numero di previdenza sociale ue o identificazione equivalente

Queste entità presenti nel numero di previdenza sociale dell'Unione Europea o in un'identificazione equivalente e sono tipi di informazioni riservate.

- [Austria](#austria-social-security-number)
- [Belgio](#belgium-national-number)
- [Croazia](#croatia-personal-identification-oib-number)
- [Ceco](#czech-personal-identity-number)
- [Danimarca](#denmark-personal-identification-number)
- [Finlandia](#finland-national-id)
- [Francia](#france-social-security-number-insee)
- [Germania](#germany-identity-card-number)
- [Grecia](#greece-national-id-card)
- [Ungheria](#hungary-social-security-number-taj)
- [Portogallo](#portugal-citizen-card-number)
- [Spagna](#spain-social-security-number-ssn)
- [Svezia](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>Codice fiscale UE

Queste entità sono nel tipo di informazioni riservate del numero di identificazione fiscale UE.

- [Austria](#austria-tax-identification-number)
- [Belgio](#belgium-national-number)
- [Bulgaria](#bulgaria-uniform-civil-number)
- [Croazia](#croatia-identity-card-number)
- [Cipro](#cyprus-tax-identification-number)
- [Ceco](#czech-personal-identity-number)
- [Danimarca](#denmark-personal-identification-number)
- [Estonia](#estonia-personal-identification-code)
- [Finlandia](#finland-national-id)
- [Francia](#france-tax-identification-number)
- [Germania](#germany-tax-identification-number)
- [Grecia](#greece-tax-identification-number)
- [Ungheria](#hungary-tax-identification-number)
- [Irlanda](#ireland-personal-public-service-pps-number)
- [Italia](#italy-fiscal-code)
- [Lettonia](#latvia-personal-code)
- [Lituania](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Paesi Bassi](#netherlands-tax-identification-number)
- [Polonia](#poland-tax-identification-number)
- [Portogallo](#portugal-tax-identification-number)
- [Romania](#romania-personal-numeric-code-cnp)
- [Slovacchia](#slovakia-personal-number)
- [Slovenia](#slovenia-tax-identification-number)
- [Spagna](#spain-tax-identification-number)
- [Svezia](#sweden-tax-identification-number)
- [Regno Unito](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Numero di patente di guida finlandia

### <a name="format"></a>Formato

10 cifre contenenti una lineetta

### <a name="pattern"></a>Modello

10 cifre contenenti un trattino:

- sei cifre
- un trattino
- tre cifre
- una cifra o una lettera

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_finland_eu_driver's_license_number` .

```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver's_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Finlandia - Numero di assicurazione sanitaria europea
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Numero a 20 cifre

### <a name="pattern"></a>Modello

Numero a 20 cifre:

- 10 cifre - 8024680246
- uno spazio o un trattino facoltativo
- 10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione Regex_Finland_European_Health_Insurance_Number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_Finland_European_Health_Insurance_Number da un utente.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska sjukförsäkringskort
- health card
- carta di assicurazione sanitaria
- numero di assicurazione sanitaria
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>Id nazionale Finlandia

### <a name="format"></a>Formato

sei cifre più un carattere che indica un secolo più tre cifre più una cifra di controllo

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- sei cifre nel formato DDMMYY, che sono una data di nascita
- indicatore del secolo ('-', '+' o 'a')
- Numero di identificazione personale a tre cifre
- una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- la funzione Func_finnish_national_id trova contenuto che corrisponde al modello
- viene trovata una parola chiave Keyword_finnish_national_id viene trovata
- il checksum passa

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- la funzione Func_finnish_national_id trova contenuto che corrisponde al modello
- il checksum passa

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- id number
- identification number
- identiteetti numero
- identity number
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- carta d'identità nazionale
- national id no.
- id personale
- codice di identità personale
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Numero di passaporto finlandia

Questa entità è disponibile nel tipo di informazioni riservate Numero di passaporto UE ed è disponibile come entità di tipo di informazioni riservate autonoma.

### <a name="format"></a>Formato
combinazione di nove lettere e cifre

### <a name="pattern"></a>Modello
combinazione di nove lettere e cifre:
- due lettere (senza distinzione tra maiuscole e minuscole)
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione `Regex_finland_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keyword_finland_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione `Regex_finland_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keyword_finland_passport_number` .

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- passi number

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza

## <a name="france-drivers-license-number"></a>Francia - Numero di patente di guida

Questa entità è disponibile nel tipo di informazioni riservate Numero di patente dell'UE ed è disponibile come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- la funzione Func_french_drivers_license trova contenuto che corrisponde al modello.
- viene trovata una parola chiave Keyword_french_drivers_license ricerca.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>Numero dell'assicurazione sanitaria francese
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Numero a 21 cifre

### <a name="pattern"></a>Modello

Numero a 21 cifre:

- 10 cifre
- uno spazio facoltativo
- 10 cifre
- uno spazio facoltativo
- una cifra


### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- l'espressione Regex_France_Health_Insurance_Number trova contenuto che corrisponde al modello.
- viene trovata una parola chiave Keyword_France_Health_Insurance_Number viene trovata.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- carta assicurativa
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>Carta d'identità francese (CNI)

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.
- Viene trovata una parola Keywords_france_eu_national_id_card dall'utente.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- national identification number
- identità nazionale
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale


## <a name="france-passport-number"></a>Francia - numero di passaporto
Questa entità è disponibile nel tipo di informazioni riservate Numero di passaporto UE. È disponibile anche come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

nove cifre e lettere

### <a name="pattern"></a>Modello

nove cifre e lettere:
- due cifre
- due lettere (senza distinzione tra maiuscole e minuscole)
- cinque cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_fr_passport` trova contenuto che corrisponde al modello.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keywords_france_eu_passport_number` .
- L'espressione `Regex_eu_passport_date3` regolare trova la data nel formato GG MM AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_fr_passport` trova contenuto che corrisponde al modello.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keywords_france_eu_passport_number` .


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport carte
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="france-social-security-number-insee"></a>Numero di previdenza sociale francia (INSEE)

### <a name="format"></a>Formato

15 cifre

### <a name="pattern"></a>Modello

Deve corrispondere a uno di questi due modelli:
- 13 cifre seguite da uno spazio seguito da due cifre<br/>
oppure
- 15 cifre consecutive

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_french_insee` trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_fr_insee.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- 
no. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- 
no. d'identite
- ssn
- ssn #
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- social security number
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>Numero di identificazione fiscale francia

### <a name="format"></a>Formato

13 cifre

### <a name="pattern"></a>Modello

13 cifre

- Una cifra che deve essere 0, 1, 2 o 3
- Una cifra
- Uno spazio (facoltativo)
- Due cifre
- Uno spazio (facoltativo)
- Tre cifre
- Uno spazio (facoltativo)
- Tre cifre
- Uno spazio (facoltativo)
- Tre cifre di controllo


### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_france_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>Numero di imposta sul valore aggiunto della Francia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Motivo alfanumerico a 13 caratteri

### <a name="pattern"></a>Modello

Motivo alfanumerico a 13 caratteri:

- due lettere - FR (senza distinzione tra maiuscole e minuscole)
- uno spazio o un trattino facoltativo
- due lettere o cifre
- uno spazio facoltativo, un punto, un trattino o una virgola
- tre cifre
- uno spazio facoltativo, un punto, un trattino o una virgola
- tre cifre
- uno spazio facoltativo, un punto, un trattino o una virgola
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_france_value_added_tax_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_france_value_added_tax_number da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_france_value_added_tax_number trova contenuto che corrisponde al modello.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- partita IVA
- vat no
- vat #
- imposta sul valore aggiunto
- identificazione della sirena no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>Germania - Numero di patente di guida

Questa entità tipo di informazioni riservate è inclusa nel tipo di informazioni riservate Numero di patente dell'UE. È disponibile anche come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

combinazione di 11 cifre e lettere

### <a name="pattern"></a>Modello

11 cifre e lettere (senza distinzione tra maiuscole e minuscole):
- una cifra o una lettera
- due cifre
- sei cifre o lettere
- una cifra
- una cifra o una lettera

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_german_drivers_license_number.
- Il checksum ha esito positivo.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-führerschein
- no-fuhrerschein
- no-fuehrerschein
- n-führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dlno


## <a name="germany-identity-card-number"></a>Numero carta d'identità Germania

### <a name="format"></a>Formato

dal 1° novembre 2010: nove lettere e cifre

dal 1° aprile 1987 al 31 ottobre 2010: 10 cifre

### <a name="pattern"></a>Modello

dal 1° novembre 2010:
- una lettera (senza distinzione tra maiuscole e minuscole)
- otto cifre

dal 1° aprile 1987 al 31 ottobre 2010:
- 10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_germany_id_card trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_germany_id_card da un utente.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- identificazione
- identifikation
- identifizierungsnummer
- carta di identità
- identity number
- id-nummer
- id personale
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Germania - Numero di passaporto

Questa entità è inclusa nel tipo di informazioni riservate NUMERO PASSAPORTO UE ed è disponibile come entità di tipo di informazioni riservate autonoma.

### <a name="format"></a>Formato

10 cifre o lettere

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- first character is a digit or a letter from this set (C, F, G, H, J, K)
- tre cifre
- cinque cifre o lettere di questo set (C, -H, J-N, P, R, T, V-Z)
- una cifra

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_german_passport restituisce contenuti che corrispondono al modello.
- Viene trovata una `Keyword_german_passport` parola chiave da o `Keywords_eu_passport_number_common` .
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.
- Viene trovata una `Keyword_german_passport` parola chiave da o `Keywords_eu_passport_number_common` .
- Il checksum ha esito positivo.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto


## <a name="germany-tax-identification-number"></a>Numero di identificazione fiscale Germania

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

11 cifre

- Due cifre
- Uno spazio facoltativo
- Tre cifre
- Uno spazio facoltativo
- Tre cifre
- Uno spazio facoltativo
- Due cifre
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_germany_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
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

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Numero di imposta sul valore aggiunto della Germania
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Motivo alfanumerico a 11 caratteri

### <a name="pattern"></a>Modello

Motivo alfanumerico di 11 caratteri:

- una lettera D o d
- una lettera E o e
- uno spazio facoltativo
- tre cifre
- uno spazio facoltativo o una virgola
- tre cifre
- uno spazio facoltativo o una virgola
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_germany_value_added_tax_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_germany_value_added_tax_number da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_germany_value_added_tax_number trova contenuto che corrisponde al modello.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- partita IVA
- vat no
- vat #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Numero di patente di guida in Grecia

Questa entità è inclusa nel tipo di informazioni riservate numero di patente ue. È inoltre disponibile come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_greece_eu_driver's_license_number` .

```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver's_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Carta d'identità nazionale della Grecia

### <a name="format"></a>Formato

Combinazione di 7-8 lettere e numeri, oltre a un trattino

### <a name="pattern"></a>Modello

Sette lettere e numeri (formato precedente):
- Una lettera (qualsiasi lettera dell'alfabeto greco) 
- Un trattino
- Sei cifre

Otto lettere e numeri (nuovo formato):
- Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) 
- Un trattino
- Sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_greece_id_card trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave Keyword_greece_id_card'utente.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_greece_id_card trova contenuto che corrisponde al modello.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- greek id
- greek national id
- carta d'identità greco
- id polizia greco
- carta di identità
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Numero di passaporto della Grecia

### <a name="format"></a>Formato

Due lettere seguite da sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

Due lettere seguite da 7 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_greece_eu_passport_number` .
- L'espressione regolare trova la data nel formato `Regex_greece_eu_passport_date` DD MMM AA (esempio - 28 agosto 19) o viene trovata una parola chiave `Keywords_greece_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_greece_eu_passport_number` .

```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Grecia - Numero di previdenza sociale (AMKA)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

- Sei cifre come data di nascita AAMMDD
- Quattro cifre
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_greece_eu_ssn` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_greece_eu_ssn_or_equivalent` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_greece_eu_ssn` trova contenuto che corrisponde al modello.

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- social security no
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Numero di identificazione fiscale della Grecia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

9 cifre

### <a name="checksum"></a>Checksum

Non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- L'espressione  `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_greece_eu_tax_file_number` chiave from.

```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm #
- afm
- aμμ|aμμ αριθμός
- aμμ
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- tax registry no
- tax registry number
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- tin id
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Numero della carta di identità (HKID) di Hong Kong

### <a name="format"></a>Formato

Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi

### <a name="pattern"></a>Modello

Combinazione di 8-9 lettere:
- 1-2 lettere (senza distinzione tra maiuscole e minuscole)
- Sei cifre
- L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_hong_kong_id_card.
- Il checksum ha esito positivo.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- hong kong identity card
- HKIDC
- id card
- carta di identità
- hk identity card
- hong kong id
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証


## <a name="hungary-drivers-license-number"></a>Numero di patente di guida ungherese

### <a name="format"></a>Formato

Due lettere seguite da sei cifre

### <a name="pattern"></a>Modello

Due lettere e sei cifre:

- Due lettere (senza distinzione tra maiuscole e minuscole)
- Sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- L'espressione  `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_hungary_eu_driver's_license_number` .

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver's_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Numero di identificazione personale ungherese
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre:

- Una cifra che corrisponde al sesso, 1 per il maschio, 2 per la donna. Altri numeri sono possibili anche per i cittadini nati prima del 1900 o per i cittadini con doppia cittadinanza.
- Sei cifre che corrispondono alla data di nascita (AAMMDD)
- Tre cifre che corrispondono a un numero seriale
- Una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione  `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_hungary_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione  `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id number
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Numero di passaporto ungherese

### <a name="format"></a>Formato

Due lettere seguite da sei o sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

Due lettere seguite da sei o sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_hungary_eu_passport_number` .
- L'espressione regolare trova la data nel formato `Regex_hungary_eu_passport_date` DD MMM/MMM AA (esempio - 01 MÁR/MAR 12) o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_hungary_eu_passport_number` .

```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="hungary-social-security-number-taj"></a>Codice di previdenza sociale ungherese (TAJ)

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

9 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione  `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_hungary_eu_ssn_or_equivalent` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione  `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- numero di previdenza sociale ungherese
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- ssn
- ssn #
- social security no
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Numero di identificazione fiscale ungherese
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

10 cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

10 cifre:

- Una cifra che deve essere "8"
- Otto cifre
- Una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione  `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_hungary_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione  `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- ungherese stagno
- hungatiantin #
- tax authority no
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- partita IVA


## <a name="hungary-value-added-tax-number"></a>Numero di imposta sul valore aggiunto dell'Ungheria
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Motivo alfanumerico a 10 caratteri

### <a name="pattern"></a>Modello

Motivo alfanumerico a 10 caratteri:

- due lettere - HU o hu
- spazio facoltativo
- otto cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione Func_hungarian_value_added_tax_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_hungarian_value_added_tax_number da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione Func_hungarian_value_added_tax_number trova contenuto che corrisponde al modello.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- vat
- numero di imposta sul valore aggiunto
- vat #
- vatno #
- hungarianvatno #
- tax no.
- imposta sul valore aggiunto áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>India - Numero di account permanente (PAN)

### <a name="format"></a>Formato

10 lettere o cifre

### <a name="pattern"></a>Modello

10 lettere o cifre:
- Tre lettere (senza distinzione tra maiuscole e minuscole)
- Lettera in C, P, H, F, A, T, B, L, J, G (senza distinzione tra maiuscole e minuscole)
- Una lettera
- Quattro cifre
- Una lettera che è una cifra di controllo alfabetica

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_india_permanent_account_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_india_permanent_account_number.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_india_permanent_account_number trova contenuto che corrisponde al modello.


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number
- PAN

## <a name="india-unique-identification-aadhaar-number"></a>India - Numero di identificazione univoca (Aadhaar)

### <a name="format"></a>Formato

12 cifre contenenti spazi o trattini facoltativi 

### <a name="pattern"></a>Modello

12 cifre:
- Una cifra che non è 0 o 1
- Tre cifre
- Uno spazio o un trattino facoltativo 
- Quattro cifre
- Uno spazio o un trattino facoltativo 
- La cifra finale, che è la cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_india_aadhaar trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_india_aadhar da un utente.
- Il checksum ha esito positivo.
-
Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione Func_india_aadhaar trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai

## <a name="indonesia-identity-card-ktp-number"></a>Numero della carta di identità indonesiana (KTP)

### <a name="format"></a>Formato

16 cifre contenenti punti facoltativi 

### <a name="pattern"></a>Modello

16 cifre:
- Codice provincia a due cifre 
- Un punto (facoltativo) 
- Codice città o area a due cifre 
- Codice sotto-distretto a due cifre 
- Un punto (facoltativo) 
- Sei cifre nel formato DDMMYY, ovvero la data di nascita
- Un punto (facoltativo) 
- Quattro cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- L'espressione regolare Regex_indonesia_id_card trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_indonesia_id_card da un utente.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan

## <a name="international-banking-account-number-iban"></a>Numero di conto bancario internazionale (IBAN)

### <a name="format"></a>Formato

Codice paese (due lettere) più cifre di controllo (due cifre) più numero bban (fino a 30 caratteri)

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:

- Codice paese a due lettere
- Due cifre di controllo (seguite da uno spazio facoltativo)
- 1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)
- 1-3 lettere o cifre

Il formato per ogni paese è leggermente diverso. Il tipo di informazioni riservate IBAN riguarda questi 60 paesi:

- annuncio
- ae
- al
- at
- az
- ba
- be
- bg
- bh
- ch
- cr
- cy
- cz
- de
- dk
- do
- ee
- es
- fi
- fo
- fr
- gb
- ge
- gi
- gl
- gr
- hr
- hu
- ie
- il
- is
- it
- kw
- kz
- lb
- li
- lt
- lu
- lv
- mc
- md
- me
- mk
- mr
- mt
- mu
- nl
- no
- pl
- pt
- ro
- rs
- sa
- se
- si
- sk
- sm
- tn
- tr
- vg

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- La funzione Func_iban restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

Nessuno


## <a name="international-classification-of-diseases-icd-10-cm"></a>Classificazione internazionale delle malattie (ICD-10-CM)

### <a name="format"></a>Formato

Dizionario

### <a name="pattern"></a>Modello

Parola chiave

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- Viene trovata una parola Dictionary_icd_10_updated parola chiave.
- Viene trovata una parola Dictionary_icd_10_codes da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- Viene trovata una parola Dictionary_icd_10_ viene aggiornata.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>Parole chiave

Qualsiasi termine del dizionario Dictionary_icd_10_updated parole chiave, basato sulla classificazione internazionale delle malattie, decima revisione, modifica clinica [(ICD-10-CM).](https://go.microsoft.com/fwlink/?linkid=852604) Questo tipo cerca solo il termine e non i codici di assicurazione.

Qualsiasi termine del dizionario Dictionary_icd_10_codes parole chiave, basato sulla classificazione internazionale delle malattie, decima revisione, modifica clinica [(ICD-10-CM).](https://go.microsoft.com/fwlink/?linkid=852604) Questo tipo cerca solo i codici di assicurazione, non la descrizione.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Classificazione internazionale delle malattie (ICD-9-CM)

### <a name="format"></a>Formato

Dizionario

### <a name="pattern"></a>Modello

Parola chiave

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- Viene trovata una parola Dictionary_icd_9_updated da un utente.
- Viene trovata una parola Dictionary_icd_9_codes.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- Viene trovata una parola Dictionary_icd_9_updated da un utente.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

Qualsiasi termine del dizionario Dictionary_icd_9_updated parole chiave, basato sulla classificazione internazionale delle malattie, nona revisione, modifica clinica [(ICD-9-CM).](https://go.microsoft.com/fwlink/?linkid=852605) Questo tipo cerca solo il termine e non i codici di assicurazione.

Qualsiasi termine del dizionario Dictionary_icd_9_codes parole chiave, basato sulla classificazione internazionale delle malattie, nona revisione, modifica clinica [(ICD-9-CM).](https://go.microsoft.com/fwlink/?linkid=852605) Questo tipo cerca solo i codici di assicurazione, non la descrizione.

## <a name="ip-address"></a>Indirizzo IP

### <a name="format"></a>Formato

#### <a name="ipv4"></a>IPv4:
Modello complesso che rappresenta le versioni formattate (punti) e non formattate (senza punti) degli indirizzi IPv4

#### <a name="ipv6"></a>IPv6:
Modello complesso che rappresenta i numeri IPv6 formattati (che includono i due punti)

### <a name="pattern"></a>Modello

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Per IPv6, un criterio DLP ha una probabilità elevata di aver rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.
- Non vengono trovate parole chiave da Keyword_ipaddress.

Per IPv4, un criterio DLP ha una probabilità elevata di aver rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ipaddress.

Per IPv6, un criterio DLP ha una probabilità elevata di aver rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.
- Non vengono trovate parole chiave da Keyword_ipaddress.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (questa parola chiave fa distinzione tra maiuscole e minuscole)
- ip address
- Indirizzi IP
- internet protocol
- IP-כתובת ה

## <a name="ireland-drivers-license-number"></a>Numero di patente di guida in Irlanda

### <a name="format"></a>Formato

Sei cifre seguite da quattro lettere

### <a name="pattern"></a>Modello

Sei cifre e quattro lettere:

- Sei cifre
- Quattro lettere (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:

- L'espressione  `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_ireland_eu_driver's_license_number` .

```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver's_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Numero di passaporto dell'Irlanda

### <a name="format"></a>Formato

Due lettere o cifre seguite da sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

Due lettere o cifre seguite da sette cifre:

- Due cifre o lettere (senza distinzione tra maiuscole e minuscole)
- Sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_ireland_eu_passport_number` .
- L'espressione regolare trova la data nel formato `Regex_ireland_eu_passport_date` DD MMM/MMM AAAA (esempio - 01 BEA/MAGGIO 1988) o viene trovata una parola chiave da `Keywords_eu_passport_date`

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_ireland_eu_passport_number` .

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="ireland-personal-public-service-pps-number"></a>Numero del servizio pubblico personale (PPS) dell'Irlanda

### <a name="format"></a>Formato

Formato precedente (fino al 31 dicembre 2012):
- sette cifre seguite da 1-2 lettere

Nuovo formato (1 gennaio 2013 e dopo):
- sette cifre seguite da due lettere

### <a name="pattern"></a>Modello

Formato precedente (fino al 31 dicembre 2012):
- sette cifre
- da una a due lettere (senza distinzione tra maiuscole e minuscole)

Nuovo formato (1 gennaio 2013 e dopo):
- sette cifre
- una lettera (senza distinzione tra maiuscole e minuscole) che è una cifra di controllo alfabetica
- Lettera facoltativa nell'intervallo A-I o "W"

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_ireland_pps trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_ireland_eu_national_id_card da un utente.
- Il checksum ha esito positivo.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_ireland_pps trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- servizio identità client
- identification number
- personal id number
- numero di servizio pubblico personale
- servizio personale no
- phearsanta seirbhíse poiblí
- pps no
- pps number
- pps num
- pps service no
- ppsn
- ppsno #
- ppsno
- psp
- servizio pubblico no
- publicserviceno #
- publicserviceno
- ricavi e numero di previdenza sociale
- rsi no
- rsi number
- rsin
- seirbhís aitheantais client
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="israel-bank-account-number"></a>Numero di conto corrente bancario Israele

### <a name="format"></a>Formato

13 cifre

### <a name="pattern"></a>Modello

Formattato:
- due cifre
- un trattino
- tre cifre
- un trattino
- otto cifre

Non formattato:
- 13 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_israel_bank_account_number.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number
- Bank Account
- Account Number
- מספר חשבון בנק

## <a name="israel-national-identification-number"></a>Numero di identificazione nazionale Israele

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre consecutive

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_Israel_National_ID.
- Il checksum ha esito positivo.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber #
-   id number
-   identity no        
-   identitynumber #
-   identity number
-   israeliidentitynumber       
-   id personale
-   id univoco  


## <a name="italy-drivers-license-number"></a>Numero di patente di guida italiana

Questa entità di tipo è inclusa nel tipo di informazioni riservate numero di patente ue. È inoltre disponibile come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

una combinazione di 10 lettere e cifre

### <a name="pattern"></a>Modello

una combinazione di 10 lettere e cifre:
- una lettera (senza distinzione tra maiuscole e minuscole)
- la lettera "A" o "V" (senza distinzione tra maiuscole e minuscole)
- sette cifre
- una lettera (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione `Regex_italy_drivers_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una `Keywords_eu_driver's_license_number` parola chiave da o `Keyword_italy_drivers_license_number` .

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di brevetto
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>Codice fiscale italiano
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

una combinazione di 16 caratteri di lettere e cifre nel modello specificato

### <a name="pattern"></a>Modello

Una combinazione di 16 caratteri di lettere e cifre:
- tre lettere che corrispondono alle prime tre consonanti nel nome della famiglia
- tre lettere che corrispondono alla prima, alla terza e alla quarta consonanti nel nome
- due cifre che corrispondono alle ultime cifre dell'anno di nascita
- una lettera che corrisponde alla lettera del mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da A a E, H, L, M, P, R a T (quindi, gennaio è A e ottobre è R)
- due cifre che corrispondono al giorno del mese di nascita per distinguere i generi, 40 viene aggiunto al giorno di nascita per le donne
- quattro cifre che corrispondono al codice di area specifico del comune in cui è nata la persona (i codici a livello nazionale vengono utilizzati per i paesi esterni)
- una cifra di parità

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_italy_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
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

- codice fiscale
- codice fiscale
- codice id personale
- codice personale
- codice fiscale
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- numero di certificato personale
- codice personale
- codice ID personale
- personal id number
- personalcodeno #
- codice fiscale
- tax id
- identificazione fiscale no
- codice fiscale
- tax identity number
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="italy-passport-number"></a>Numero di passaporto italiano

### <a name="format"></a>Formato

due lettere o cifre seguite da sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

due lettere o cifre seguite da sette cifre:

- due cifre o lettere (senza distinzione tra maiuscole e minuscole)
- sette cifre

### <a name="checksum"></a>Checksum

non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_italy_eu_passport_number` .
- L'espressione regolare trova la data nel formato `Regex_italy_eu_passport_date` DD MMM/MMM AAAA (esempio - 01 GEN/JAN 1988) o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_italy_eu_passport_number` .

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiano
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="italy-value-added-tax-number"></a>Numero di imposta sul valore aggiunto dell'Italia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Motivo alfanumerico a 13 caratteri con delimitatori facoltativi

### <a name="pattern"></a>Modello

Motivo alfanumerico a 13 caratteri con delimitatori facoltativi:

- I o i
- T o t
- spazio facoltativo, punto, trattino o virgola
- 11 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_italy_value_added_tax_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_italy_value_added_tax_number dall'utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_italy_value_added_tax_number trova contenuto che corrisponde al modello.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- partita IVA
- vat no
- vat #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Numero di conto corrente bancario giappone

### <a name="format"></a>Formato

sette o otto cifre

### <a name="pattern"></a>Modello

numero di conto corrente bancario:
- sette o otto cifre
- codice filiale del conto corrente bancario:
- quattro cifre
- uno spazio o un trattino (facoltativo)
- tre cifre

Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_bank_account.
- Si verifica una delle situazioni seguenti:
- La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_bank_branch_code.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_bank_account.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number
- Checking Account
- Checking Account #
- Checking Acct Number
- Checking Acct #
- Checking Acct No.
- Checking Account No.
- Bank Account Number
- Bank Account
- Bank Account #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bank Account No.
- Savings Account Number
- Savings Account
- Savings Account #
- Savings Acct Number
- Savings Acct #
- Savings Acct No.
- Savings Account No.
- Debit Account Number
- Debit Account
- Debit Account #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Debit Account No.
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>Numero di patente di guida giapponese

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_drivers_license_number.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- dl #
- dls #
- lic #
- lics #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Giappone Il mio numero - Corporate
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Numero a 13 cifre

### <a name="pattern"></a>Modello

Numero a 13 cifre:

- una cifra da una a nove
- 12 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_japanese_my_number_corporate trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_japanese_my_number_corporate.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_japanese_my_number_corporate trova contenuto che corrisponde al modello.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- numero aziendale
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>Giappone Il mio numero - Personale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Numero a 12 cifre

### <a name="pattern"></a>Modello

Numero a 12 cifre:

- quattro cifre
- uno spazio facoltativo, un punto o un trattino
- quattro cifre
- uno spazio facoltativo, un punto o un trattino
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_japanese_my_number_personal trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_japanese_my_number_personal.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_japanese_my_number_personal trova contenuto che corrisponde al modello.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- il mio numero
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード


## <a name="japan-passport-number"></a>Numero di passaporto giappone

### <a name="format"></a>Formato

due lettere seguite da sette cifre

### <a name="pattern"></a>Modello

due lettere (senza distinzione tra maiuscole e minuscole) seguite da sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_passport.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Passport
- Passport Number
- Passport No.
- Passport#
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パスポートNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Numero di carta di residenza giappone

### <a name="format"></a>Formato

12 lettere e cifre

### <a name="pattern"></a>Modello

12 lettere e cifre:
- due lettere (senza distinzione tra maiuscole e minuscole)
- otto cifre
- due lettere (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_jp_residence_card_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_jp_residence_card_number da un utente.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Numero della carta di residenza
- Carta di residenza no
- Carta di residenza #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Numero di registrazione residente in Giappone

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_resident_registration_number.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Residents Basic Registry Number
- Resident Registration No.
- Resident Register No.
- Residents Basic Registry No.
- Basic Resident Register No.
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証


## <a name="japan-social-insurance-number-sin"></a>Giappone - Numero di previdenza sociale (SIN)

### <a name="format"></a>Formato

7-12 cifre

### <a name="pattern"></a>Modello

7-12 cifre:
- quattro cifre
- un trattino (facoltativo)
- sei cifre OR
- 7-12 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_sin.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_sin.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No.
- Social Insurance Num
- Social Insurance Number
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Numero di patente lettone

### <a name="format"></a>Formato

tre lettere seguite da sei cifre

### <a name="pattern"></a>Modello

tre lettere e sei cifre:

- tre lettere (senza distinzione tra maiuscole e minuscole)
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_latvia_eu_driver's_license_number` .

```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver's_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Codice personale Lettone

### <a name="format"></a>Formato

11 cifre e un trattino facoltativo

### <a name="pattern"></a>Modello

Formato precedente

11 cifre e un trattino:

- sei cifre che corrispondono alla data di nascita (DDMMYY)
- un trattino
- una cifra che corrisponde al secolo di nascita ("0" per il 19° secolo, "1" per il 20° secolo e "2" per il 21° secolo)
- quattro cifre generate in modo casuale

Nuovo formato

11 cifre

- Due cifre "32"
- 9 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_latvia_eu_national_id_card` o l'espressione regolare `Regex_latvia_eu_national_id_card_new_format` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_latvia_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_latvia_eu_national_id_card` o l'espressione regolare `Regex_latvia_eu_national_id_card_new_format` trova contenuto che corrisponde al modello.

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- numero amministrativo
- alvas nē
- numero di nascita
- citizen number
- numero civile
- numero censimento elettronico
- numero elettronico
- codice fiscale
- numero utente sanitario
- id #
- id-code
- identification number
- identifikācijas numurs
- id-number
- numero singolo
- latvija alva
- nacionālais id
- national id
- national identifying number
- national identity number
- national insurance number
- national register number
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- numero di certificato personale
- codice personale
- codice ID personale
- personal id number
- codice di identificazione personale
- identificatore personale
- numero di identità personale
- numero personale
- codice numerico personale
- personalcodeno #
- personas kods
- codice di identificazione della popolazione
- numero di servizio pubblico
- registration number
- revenue number
- social insurance number
- social security number
- codice fiscale dello stato
- tax file number
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- voter's number

## <a name="latvia-passport-number"></a>Numero di passaporto lettone

### <a name="format"></a>Formato

due lettere o cifre seguite da sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

due lettere o cifre seguite da sette cifre:

- due cifre o lettere (senza distinzione tra maiuscole e minuscole)
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_latvia_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_latvia_eu_passport_number` .

```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="lithuania-drivers-license-number"></a>Numero di patente di guida lituania

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_lithuania_eu_driver's_license_number` .

```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver's_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Codice personale Lituania
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

11 cifre senza spazi e delimitatori:

- una cifra (da 1 a 6) che corrisponde al sesso e al secolo di nascita della persona
- sei cifre che corrispondono alla data di nascita (AAMMDD)
- tre cifre che corrispondono al numero seriale della data di nascita
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_lithuania_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- citizen service number
- mokesči sua id
- mokesči? identifikavimas numeris
- mokesči? identifikavimo numeris
- mokesči? numeris
- national identification number
- codice personale
- codice numerico personale
- piliečio paslaugos numeris
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Numero di passaporto lituania

### <a name="format"></a>Formato

otto cifre o lettere senza spazi o delimitatori

### <a name="pattern"></a>Modello

otto cifre o lettere (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_lithuania_eu_passport_number` .
- L'espressione `Regex_eu_passport_date3` regolare trova la data nel formato GG MM AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_lithuania_eu_passport_number` .

```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="luxemburg-drivers-license-number"></a>Numero di patente di guida di Luxemburg

### <a name="format"></a>Formato

sei cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_luxemburg_eu_driver's_license_number` .

```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver's_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Numero di identificazione nazionale di Lussemburgo (persone fisiche)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

13 cifre:

- 11 cifre
- due cifre di controllo

### <a name="checksum"></a>Checksum

sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_luxemburg_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- codice individuale
- individual id
- identificazione individuale
- identità individuale
- numéro d'identification personnel
- id personale
- identificazione personale
- identità personale
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- id univoco
- identità univoca
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Numero di passaporto di Luxemburg

### <a name="format"></a>Formato

otto cifre o lettere senza spazi o delimitatori

### <a name="pattern"></a>Modello

otto cifre o lettere (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_luxemburg_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_luxemburg_eu_passport_number` .
- L'espressione `Regex_eu_passport_date3` regolare trova la data nel formato GG MM AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_luxemburg_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_luxemburg_eu_passport_number` .

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- luxembourg pass
- luxembourg passeport
- passaporto lussemburghese
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Numero di identificazione nazionale di Luxemburg (persone non naturali)

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre

- due cifre
- uno spazio facoltativo
- tre cifre
- uno spazio facoltativo
- tre cifre
- uno spazio facoltativo
- due cifre
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_luxemburg_eu_tax_file_number_non_natural` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_luxemburg_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_luxemburg_eu_tax_file_number_non_natural` trova contenuto che corrisponde al modello.

```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- luxembourg tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Numero di carta di identità malese

### <a name="format"></a>Formato

12 cifre contenenti lineette facoltative

### <a name="pattern"></a>Modello

12 cifre:
- sei cifre nel formato AAMMDD, ovvero la data di nascita
- un trattino (facoltativo)
- Codice luogo di nascita a due lettere
- un trattino (facoltativo)
- tre cifre casuali
- codice di genere a una cifra

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_malaysia_id_card_number trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_malaysia_id_card_number.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- scheda applicazione digitale
- i/c
- i/c no
- ic
- ic no
- id card
- carta di identificazione
- carta di identità
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- malaysia identity card
- malaysian identity card
- nric
- carta di identità personale

## <a name="malta-drivers-license-number"></a>Numero di patente di guida di Malta

### <a name="format"></a>Formato

Combinazione di due caratteri e sei cifre nel formato specificato

### <a name="pattern"></a>Modello

combinazione di due caratteri e sei cifre:

- due caratteri (cifre o lettere, senza distinzione tra maiuscole e minuscole)
- uno spazio (facoltativo)
- tre cifre
- uno spazio (facoltativo)
- tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_malta_eu_driver's_license_number` .

```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver's_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Numero di carta d'identità di Malta
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

sette cifre seguite da una lettera

### <a name="pattern"></a>Modello

sette cifre seguite da una lettera:

- sette cifre
- una lettera in "M, G, A, P, L, H, B, Z" (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

Non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_malta_eu_national_id_card` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.

```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
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

- citizen service number
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- codice numerico personale
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #


## <a name="malta-passport-number"></a>Numero di passaporto di Malta

### <a name="format"></a>Formato

sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_malta_eu_passport_number` .
- Viene trovata una parola `Keywords_eu_passport_date` chiave da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_malta_eu_passport_number` .

```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="malta-tax-identification-number"></a>Numero di identificazione fiscale di Malta

### <a name="format"></a>Formato

Per i cittadini maltesi:
- sette cifre e una lettera nello schema specificato

Nazionali non maltesi ed entità maltesi:
- nove cifre

### <a name="pattern"></a>Modello

Nazionali maltesi: sette cifre e una lettera

- sette cifre
- una lettera (senza distinzione tra maiuscole e minuscole)

Nazionali non maltesi ed entità maltesi: nove cifre

- nove cifre

### <a name="checksum"></a>Checksum

Non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_malta_eu_tax_file_number`  regolare o trova contenuto che corrisponde al `Regex_malta_eu_tax_file_number_non_maltese_national` modello.
- Viene trovata una parola  `Keywords_malta_eu_tax_file_number` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_malta_eu_tax_file_number` regolare o trova contenuto che corrisponde al `Regex_malta_eu_tax_file_number_non_maltese_national` modello.

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- citizen service number
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- codice numerico personale
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #


## <a name="medicare-beneficiary-identifier-mbi-card"></a>Carta MBI (Medicare Beneficiary Identifier)

### <a name="format"></a>Formato

Motivo alfanumerico a 11 caratteri

### <a name="pattern"></a>Modello

- una cifra compresa tra 1 e 9
- una lettera esclusa S, L, O, I, B, Z
- una cifra o una lettera esclusa S, L, O, I, B, Z
- una cifra
- un trattino facoltativo
- una lettera esclusa S, L, O, I, B, Z
- una cifra o una lettera esclusa S, L, O, I, B, Z
- una cifra
- un trattino facoltativo
- due lettere escluse S, L, O, I, B, Z
- due cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_mbi_card` regolare trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keyword_mbi_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_mbi_card` regolare trova contenuto che corrisponde al modello.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi #
- medicare beneficiario #
- identificatore del beneficiario medicare
- medicare beneficiario no
- medicare numero beneficiario
- medicare beneficiario #


## <a name="mexico-unique-population-registry-code-curp"></a>Codice CURP (Unique Population Registry Code) del Messico

### <a name="format"></a>Formato

Motivo alfanumerico a 18 caratteri

### <a name="pattern"></a>Modello

- quattro lettere (senza distinzione tra maiuscole e minuscole)
- sei cifre che indicano una data valida
- una lettera - H/h o M/m
- due lettere che indicano un codice di stato messicano valido
- tre lettere
- una lettera o una cifra
- una cifra

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_mexico_population_registry_code` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keyword_mexico_population_registry_code` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_mexico_population_registry_code` trova contenuto che corrisponde al modello.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Codice del Registro di sistema del popolamento univoco 
- codice di popolazione univoco
- CURP
- ID personale
- ID univoco
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave personal Identidad
- personal Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>Numero BSN (Netherlands citizen's service)

### <a name="format"></a>Formato

otto o nove cifre contenenti spazi facoltativi

### <a name="pattern"></a>Modello

otto-nove cifre:
- tre cifre
- uno spazio (facoltativo)
- tre cifre
- uno spazio (facoltativo)
- due-tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_netherlands_bsn trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_netherlands_bsn.
- Il checksum ha esito positivo.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- bsn #
- bsn
- hamburgerservicenummer
- citizen service number
- numero di persona
- numero personale
- codice numerico personale
- numero correlato alla persona
- persoonlijk nummer
- persoonlijke numerieke code
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- social-fiscal number
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Numero di patente olandese

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_netherlands_eu_driver's_license_number` .

```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver's_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Numero di passaporto olandese

### <a name="format"></a>Formato

nove lettere o cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

nove lettere o cifre

### <a name="checksum"></a>Checksum

non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_netherlands_eu_passport_number` .
- L'espressione regolare trova la data nel formato `Regex_netherlands_eu_passport_date` DD MMM/MMM AAAA (esempio - 26 MAA/MAR 2012)

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_netherlands_eu_passport_number` .

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Numero di identificazione fiscale Paesi Bassi
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

nove cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_netherlands_eu_tax_file_number` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- Identificazione fiscale hollânske
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- numero di identificazione impuesto
- impuesto number
- nederland belasting id nummer
- nederland belasting identificatie
- nederland belasting identificatienummer
- nederland belastingnummer
- nederlande belasting identificatie
- identificazione fiscale paesi Bassi
- identificazione fiscale di netherland
- netherlands tin
- stagno di netherland
- tax id
- identificazione fiscale no
- codice fiscale
- identificazione fiscale tal
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- tax tal
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>Numero di imposta sul valore aggiunto dei Paesi Bassi
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Motivo alfanumerico a 14 caratteri

### <a name="pattern"></a>Modello

Motivo alfanumerico a 14 caratteri:

- N o n
- L o l
- spazio facoltativo, punto o trattino
- nove cifre
- spazio facoltativo, punto o trattino
- B o b
- due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_netherlands_value_added_tax_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_netherlands_value_added_tax_number da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_netherlands_value_added_tax_number trova contenuto che corrisponde al modello.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- partita IVA
- vat no
- vat #
- wearde tafoege tax getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Numero di conto corrente bancario della Nuova Zelanda
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Formato da 14 a 16 cifre con delimitatore facoltativo

### <a name="pattern"></a>Modello

Motivo da 14 a 16 cifre con delimitatore facoltativo:

- due cifre
- un trattino o uno spazio facoltativo
- da tre a quattro cifre
- un trattino o uno spazio facoltativo
- sette cifre
- un trattino o uno spazio facoltativo
- da due a tre cifre
- un trattino o uno spazio delle opzioni

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_zealand_bank_account_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_new_zealand_bank_account_number.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_zealand_bank_account_number trova contenuto che corrisponde al modello.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- conto corrente bancario
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Numero di patente di guida neozelandese
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

schema alfanumerico a otto caratteri

### <a name="pattern"></a>Modello

schema alfanumerico a otto caratteri

- due lettere
- sei cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_newzealand_driver_license_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keywords_newzealand_driver_license_number da un utente.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_newzealand_driver_license_number trova contenuto che corrisponde al modello.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- driver lic
- patente di guida
- patenti di guida
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- driver licences
- driver'lic
- driver'lics
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's licence
- patenti di guida
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- patente di guida #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- patenti di guida #
- international driving permit
- international driving permits
- nz automobile association
- new zealand automobile association


## <a name="new-zealand-inland-revenue-number"></a>New Zealand inland revenue number
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

otto o nove cifre con delimitatori facoltativi

### <a name="pattern"></a>Modello

otto o nove cifre con delimitatori facoltativi

- due o tre cifre
- uno spazio o un trattino facoltativo
- tre cifre
- uno spazio o un trattino facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_zealand_inland_revenue_number trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave Keywords_new_zealand_inland_revenue_number'utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_zealand_inland_revenue_number trova contenuto che corrisponde al modello.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird no.
- ird no #
- nz ird
- new zealand ird
- ird number
- inland revenue number


## <a name="new-zealand-ministry-of-health-number"></a>Numero del ministero della sanità della Nuova Zelanda

### <a name="format"></a>Formato

tre lettere, uno spazio (facoltativo) e quattro cifre

### <a name="pattern"></a>Modello

- tre lettere (senza distinzione tra maiuscole e minuscole) tranne "I" e "O"
- uno spazio (facoltativo)
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_nz_terms.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- Sanità
- trattamento
- National Health Index Number
- nhi number
- nhi no.
- NHI #
- National Health Index No.
- ID indice sanitario nazionale
- Indice sanitario nazionale #

## <a name="new-zealand-social-welfare-number"></a>Numero di previdenza sociale neozelandese

Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre

- tre cifre
- un trattino facoltativo
- tre cifre
- un trattino facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_newzealand_social_welfare_number trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave Keywords_newzealand_social_welfare_number'utente.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_newzealand_social_welfare_number trova contenuto che corrisponde al modello.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- social assistenzial #
- social assistenzial #
- social assistenziale No.
- numero di previdenza sociale
- swn #


## <a name="norway-identification-number"></a>Numero di identificazione norvegia

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre:
- sei cifre nel formato DDMMYY, ovvero la data di nascita
- numero individuale a tre cifre
- due cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_norway_id_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_norway_id_number.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_norway_id_numbe trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Codice PIN
- Numero ID norvegese
- Numero ID

- Identificazione
- Personnummer
- Fødselsnummer


## <a name="philippines-unified-multi-purpose-identification-number"></a>Numero di identificazione multivalore unificato delle Filippine

### <a name="format"></a>Formato

12 cifre separate da dei segni meno

### <a name="pattern"></a>Modello

12 cifre:
- quattro cifre
- un trattino
- sette cifre
- un trattino
- una cifra

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_philippines_unified_id trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_philippines_id da un utente.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- ID multifunzione unificato
- UMID
- Carta di identità
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Numero di patente di guida polonia

### <a name="format"></a>Formato

14 cifre contenenti due barre

### <a name="pattern"></a>Modello

14 cifre e due barre:

- cinque cifre
- una barra
- due cifre
- una barra
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_poland_eu_driver's_license_number` .

```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver's_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Carta di identità polonia

### <a name="format"></a>Formato

tre lettere e sei cifre

### <a name="pattern"></a>Modello

tre lettere (senza distinzione tra maiuscole e minuscole) seguite da sei cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_polish_national_id restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.
- Il checksum ha esito positivo.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.



## <a name="poland-national-id-pesel"></a>ID nazionale Polonia (PESEL)

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

- sei cifre che rappresentano la data di nascita nel formato AAMMDD
- quattro cifre
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_pesel_identification_number.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>Numero di passaporto polonia
Questa entità tipo di informazioni riservate è inclusa nel tipo di informazioni riservate Numero di passaporto UE. È disponibile anche come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

due lettere e sette cifre

### <a name="pattern"></a>Modello

Due lettere (senza distinzione tra maiuscole e minuscole) seguite da sette cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_polish_passport_number_v2` trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keyword_polish_national_passport_number` .
- Viene trovata una parola `Keywords_eu_passport_date` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_polish_passport_number_v2` trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keyword_polish_national_passport_number` .

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_polish_passport_number_v2` trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="poland-regon-number"></a>Numero REGON Polonia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Numero a 9 o 14 cifre

### <a name="pattern"></a>Modello

numero a nove cifre o a 14 cifre:

- nove cifre o
- nove cifre
- trattino
- cinque cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_polish_regon_number trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave Keywords_polish_regon_number'utente.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_polish_regon_number trova contenuto che corrisponde al modello.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- numero statistico
- id statistico
- statistiche no
- numero di rigon
- regonid #
- regonno #
- id società
- companyid #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Numero di identificazione fiscale polonia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

11 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_poland_eu_tax_file_number` chiave from.


```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
- nip
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- vat id #
- vat id
- vat no
- partita IVA
- vatid #
- vatid
- vatno #


## <a name="portugal-citizen-card-number"></a>Numero di carta di cittadinanza portoghese

### <a name="format"></a>Formato

otto cifre

### <a name="pattern"></a>Modello

otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_portugal_citizen_card trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_portugal_citizen_card.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- citizen card
- numero documento
- documento de identificação
- id number
- identificazione no
- identification number
- carta di identità no
- numero di carta di identità
- carta d'identità nazionale
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi number


## <a name="portugal-drivers-license-number"></a>Numero di patente di guida portoghese

### <a name="format"></a>Formato

due modelli - due lettere seguite da 5-8 cifre con caratteri speciali

### <a name="pattern"></a>Modello

Modello 1: due lettere seguite da 5/6 con caratteri speciali:
- Due lettere (senza distinzione tra maiuscole e minuscole)
- Una lineetta
- Cinque o sei cifre
- Uno spazio
- Una cifra

Modello 2: una lettera seguita da 6/8 cifre con caratteri speciali:
- Una lettera (senza distinzione tra maiuscole e minuscole)
- Una lineetta
- Sei o otto cifre
- Uno spazio
- Una cifra


### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_portugal_eu_driver's_license_number` .

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver's_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Numero di passaporto portoghese

### <a name="format"></a>Formato

una lettera seguita da sei cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

una lettera seguita da sei cifre:

- una lettera (senza distinzione tra maiuscole e minuscole)
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_portugal_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_portugal_eu_passport_number` .

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- passaporto portoghese
- passeport portoghese
- passaporte portoghese
- passaporte nº
- passeport nº
- números de passaporte
- passaporti portoghesi
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="portugal-tax-identification-number"></a>Numero di identificazione fiscale del Portogallo

### <a name="format"></a>Formato

nove cifre con spazi facoltativi

### <a name="pattern"></a>Modello

- tre cifre
- uno spazio facoltativo
- tre cifre
- uno spazio facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_portugal_eu_tax_file_number` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf #
- cpf
- nif #
- nif
- número de identificação fisca
- numero fiscale
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>Numero di patente di guida romania

### <a name="format"></a>Formato

un carattere seguito da otto cifre

### <a name="pattern"></a>Modello

un carattere seguito da otto cifre:
- una lettera (senza distinzione tra maiuscole e minuscole) o una cifra
- otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_romania_eu_driver's_license_number` .

```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver's_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>Codice numerico personale Romania (CNP)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

13 cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

- una cifra da 1 a 9
- sei cifre che rappresentano la data di nascita (AAMMDD)
- due cifre, che possono essere 01-52 o 99
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_romania_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.

```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
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

- cnp #
- cnp
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- numero di assicurazione
- insurancenumber #
- national id #
- national id
- national identification number
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- codice numerico personale
- pin #
- pin
- tax file no
- tax file number
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Numero di passaporto romania

### <a name="format"></a>Formato

otto o nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

otto o nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_romania_eu_passport_number` .
- L'espressione regolare trova la data nel formato `Regex_romania_eu_passport_date` DD MMM/MMM AA (esempio- 01 FEB/FEB 10) o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_romania_eu_passport_number` .

```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul paşaportului numarul pasaportului numerele paşaportului Paşaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="russia-passport-number-domestic"></a>Russia - Numero di passaporto nazionale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Numero a 10 cifre

### <a name="pattern"></a>Modello

Numero a 10 cifre:

- due cifre
- uno spazio o un trattino facoltativo
- due cifre
- uno spazio facoltativo
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione Regex_Russian_Passport_Number_Domestic trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- сасоооо id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- сасооорid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Russia numero di passaporto internazionale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

numero a nove cifre

### <a name="pattern"></a>Modello

numero a nove cifre:

- due cifre
- uno spazio o un trattino facoltativo
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione Regex_Russian_Passport_Number_International trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- сасоооо id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- сасооорid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Arabia Saudita - Identificativo nazionale

### <a name="format"></a>Formato

10 cifre

### <a name="pattern"></a>Modello

10 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card
- I card number
- ID number
- الوطنية الهوية بطاقة رقم


## <a name="singapore-national-registration-identity-card-nric-number"></a>Numero NRIC (National Registration Identity Card) di Singapore

### <a name="format"></a>Formato

nove lettere e cifre

### <a name="pattern"></a>Modello

- nove lettere e cifre:
- la lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole)
- sette cifre
- una cifra di controllo alfabetica

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_singapore_nric trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_singapore_nric.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_singapore_nric trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- Carta di identità di registrazione nazionale
- Numero di carta di identità
- NRIC
- IC
- Numero di identificazione per stranieri
- FIN
- 身份证
- 身份證

## <a name="slovakia-drivers-license-number"></a>Numero di patente di guida slovacchia

### <a name="format"></a>Formato

un carattere seguito da sette cifre

### <a name="pattern"></a>Modello

un carattere seguito da sette cifre

- una lettera (senza distinzione tra maiuscole e minuscole) o una cifra
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_slovakia_eu_driver's_license_number` .

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver's_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Numero personale Slovacchia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

nove o 10 cifre contenenti barra rovesciata facoltativa

### <a name="pattern"></a>Modello

- sei cifre che rappresentano la data di nascita
- barra facoltativa (/)
- tre cifre
- una cifra di controllo facoltativa

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_slovakia_eu_national_id_card` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- numero di nascita
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- id number
- identificazione no
- identification number
- identifikačná karta č
- identifikačné číslo
- carta di identità no
- numero di carta di identità
- národná identifikačná značka č
- numero nazionale
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- tax file no
- tax file number
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="slovakia-passport-number"></a>Numero di passaporto slovacchia

### <a name="format"></a>Formato

una cifra o una lettera seguita da sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

una cifra o una lettera (senza distinzione tra maiuscole e minuscole) seguita da sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_slovakia_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_slovakia_eu_passport_number` .

```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="slovenia-drivers-license-number"></a>Numero di patente di guida slovena

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_slovenia_eu_driver's_license_number` .

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver's_license_number

- vozniško dovoljenje
- licenza vozniška številka
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Slovenia Unique Master Citizen Number
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

13 cifre nel modello specificato:

- sette cifre che corrispondono alla data di nascita (DDMMLLL), dove "LLL" corrisponde alle ultime tre cifre dell'anno di nascita
- due cifre che corrispondono all'area di nascita "50"
- tre cifre che corrispondono a una combinazione di sesso e numero di serie per le persone nate nello stesso giorno. 000-499 per gli uomini e 500-999 per le femmine.
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_slovenia_eu_national_id_card` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
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

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- carta di identità
- nacionalna id
- nacionalni potni list
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- codice personale
- numero personale
- codice numerico personale
- številka državljana
- numero cittadino univoco
- numero ID univoco
- numero di identità univoco
- numero cittadino master univoco
- numero di registrazione univoco
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Numero di passaporto slovenia

### <a name="format"></a>Formato

due lettere seguite da sette cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

due lettere seguite da sette cifre:

- la lettera "P"
- una lettera maiuscola
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_slovenia_eu_passport_number` .
- L'espressione `Regex_eu_passport_date1` regolare trova la data nel formato GG.MM.AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_slovenia_eu_passport_number` .

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni list #
- datum rojstva
- potni list
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="slovenia-tax-identification-number"></a>Numero di identificazione fiscale Slovenia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

otto cifre senza spazi o delimitatori

### <a name="pattern"></a>Modello

- una cifra da 1 a 9
- sei cifre
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_slovenia_eu_tax_file_number` chiave from.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- tax file no
- tax file number
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="south-africa-identification-number"></a>Numero di identificazione sudafricano

### <a name="format"></a>Formato

13 cifre che possono contenere spazi

### <a name="pattern"></a>Modello

13 cifre:
- sei cifre nel formato AAMMDD, ovvero la data di nascita
- quattro cifre
- indicatore di cittadinanza a una cifra
- la cifra "8" o "9"
- una cifra, ovvero una cifra di checksum

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_south_africa_identification_number trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_south_africa_identification_number da un utente.
- Il checksum ha esito positivo.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Carta di identità
- ID
- Identificazione

## <a name="south-korea-resident-registration-number"></a>South Korea resident registration number

### <a name="format"></a>Formato

13 cifre contenenti un segno meno

### <a name="pattern"></a>Modello

13 cifre:
- sei cifre nel formato AAMMDD, ovvero la data di nascita
- un trattino
- una cifra determinata dal secolo e dal sesso
- Codice paese di nascita a quattro cifre
- una cifra utilizzata per distinguere le persone per le quali i numeri precedenti sono identici
- una cifra di controllo.

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave Keyword_south_korea_resident_number'utente.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- Carta di identità
- Numero di registrazione del cittadino
- Jumin deungnok beonho
- RRN
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Numero di patente di guida in Spagna

### <a name="format"></a>Formato

otto cifre seguite da un carattere

### <a name="pattern"></a>Modello

otto cifre seguite da un carattere:

- otto cifre
- una cifra o una lettera (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o trova contenuto che corrisponde al `Func_spain_eu_DL_and_NI_number_foreigner` modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_spain_eu_driver's_license_number` .

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o trova contenuto che corrisponde al `Func_spain_eu_DL_and_NI_number_foreigner` modello.

```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver's_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- permisos conducir
- carnet conducir
- carnet de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>Spagna DNI
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

otto cifre seguite da un carattere

### <a name="pattern"></a>Modello

sette cifre seguite da un carattere

- otto cifre
- Uno spazio o un trattino facoltativo
- una lettera di controllo (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o trova contenuto che corrisponde al `Func_spain_eu_DL_and_NI_number_foreigner` modello.
- Viene trovata una parola  `Keywords_spain_eu_national_id_card"` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o trova contenuto che corrisponde al `Func_spain_eu_DL_and_NI_number_foreigner` modello.


```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- numero di assicurazione
- national identification number
- identità nazionale
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- numero di identificazione personale
- identità personale no
- numero di identità univoco
- uniqueid #

## <a name="spain-passport-number"></a>Numero di passaporto spagnolo

### <a name="format"></a>Formato

una combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori

### <a name="pattern"></a>Modello

una combinazione di otto o nove caratteri di lettere e numeri:

- due cifre o lettere
- una cifra o una lettera (facoltativo)
- sei cifre

### <a name="checksum"></a>Checksum

Non applicabile

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_spain_eu_passport_number` .
- L'espressione `Regex_spain_eu_passport_date` regolare trova la data nel formato GG-MM-AAAA o viene trovata una parola chiave `Keywords_eu_passport_date` da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_passport_number` parola chiave da o `Keywords_spain_eu_passport_number` .

```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- spagna passport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="spain-social-security-number-ssn"></a>Spagna - Numero di previdenza sociale (SSN)


### <a name="format"></a>Formato

11-12 cifre

### <a name="pattern"></a>Modello

11-12 cifre:
- due cifre
- una barra (facoltativo)
- da sette a otto cifre
- una barra (facoltativo)
- due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.
- - Viene trovata una parola  `Keywords_spain_eu_ssn_or_equivalent` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn #
- socialsecurityno
- social security no
- social security number
- número de la seguridad social

## <a name="spain-tax-identification-number"></a>Numero di identificazione fiscale spagna
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

sette o otto cifre e una o due lettere nel modello specificato

### <a name="pattern"></a>Modello

Spagnolo Natural Persons with a Spain National Identity Card:

- otto cifre
- una lettera maiuscola (maiuscole/minuscole)

Spagnoli non residenti senza carta di identità nazionale di Spagna

- una lettera maiuscola "L" (maiuscole/minuscole)
- sette cifre
- una lettera maiuscola (maiuscole/minuscole)

Spagnoli residenti di età inferiore a 14 anni senza carta d'identità nazionale spagna:

- una lettera maiuscola "K" (maiuscole/minuscole)
- sette cifre
- una lettera maiuscola (maiuscole/minuscole)

Stranieri con numero di identificazione di uno straniero

- una lettera maiuscola che è "X", "Y" o "Z" (maiuscole/minuscole)
- sette cifre
- una lettera maiuscola (maiuscole/minuscole)

Stranieri senza numero di identificazione di uno straniero

- una lettera maiuscola che è "M" (maiuscole/minuscole)
- sette cifre
- una lettera maiuscola (maiuscole/minuscole)

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_tax_file_number` o trova contenuto che corrisponde al `Func_spain_eu_DL_and_NI_number_citizen` modello.
- Viene trovata una parola  `Keywords_spain_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_tax_file_number` o trova contenuto che corrisponde al `Func_spain_eu_DL_and_NI_number_citizen` modello.

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- tax file no
- tax file number
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server stringa di connessione

### <a name="format"></a>Formato

La stringa "User Id", "User ID", "uid" o "UserId" seguita dai caratteri e dalle stringhe descritti nel modello seguente.

### <a name="pattern"></a>Modello

- la stringa "User Id", "User ID", "uid" o "UserId"
- qualsiasi combinazione di 1-200 lettere minuscole o maiuscole, cifre, simboli, caratteri speciali o spazi
- la stringa "Password" o "pwd" dove "pwd" non è preceduta da una lettera minuscola
- un segno di uguale (=)
- qualsiasi carattere che non sia un simbolo del dollaro ($), un simbolo di percentuale (%), un simbolo di maggiore di (>), un simbolo di simbolo (@), virgolette ("), un punto e virgola (;), una parentesi graffa sinistra([) o una parentesi quadra sinistra ({)
- qualsiasi combinazione di 7-128 caratteri che non siano un punto e virgola (;), barra (/) o virgolette (")
- un punto e virgola (;) o virgolette (")

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_SQLServerConnectionString trova contenuto che corrisponde al modello.
- Una parola chiave CEP_GlobalFilter non viene trovata.
- L'espressione CEP_PasswordPlaceHolder non trova contenuto corrispondente al modello.
- L'espressione CEP_CommonExampleKeywords non trova contenuto corrispondente al modello.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- somepassword
- secretPassword
- esempio

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

Questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- Password o pwd seguiti da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (*) -OR-
- Password o pwd seguito da:
    - Segno di uguale (=)
    - Simbolo minore di (<)
    - Qualsiasi combinazione di 1-200 caratteri maiuscoli o minuscoli, cifre, asterisco (*), trattino (-), sottolineatura (_) o spazi vuoti
    - Simbolo maggiore di (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare e non un elenco di parole chiave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>Numero di patente di guida in Svezia

### <a name="format"></a>Formato

10 cifre contenenti una lineetta

### <a name="pattern"></a>Modello

10 cifre contenenti un trattino:

- sei cifre
- un trattino
- quattro cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione  `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.
- Viene trovata una  `Keywords_eu_driver's_license_number` parola chiave da o `Keywords_sweden_eu_driver's_license_number` .

```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver's_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Svezia - ID nazionale

### <a name="format"></a>Formato

10 o 12 cifre e un delimitatore facoltativo

### <a name="pattern"></a>Modello

10 o 12 cifre e un delimitatore facoltativo:
- due cifre (facoltativo)
- Sei cifre nel formato data AAMMGG
- delimitatore di "-" o "+" (facoltativo)
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_swedish_national_identifier` trova contenuto che corrisponde al modello.
- Viene trovata una parola `Keywords_swedish_national_identifier` chiave da
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_swedish_national_identifier` trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id number
- id #
- identificazione no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- documento di identità
- identity no
- identity number
- id-nummer
- id personale
- personnummer #
- personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>Svezia - numero di passaporto

### <a name="format"></a>Formato

otto cifre

### <a name="pattern"></a>Modello

otto cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- l'espressione regolare Regex_sweden_passport_number trova contenuto che corrisponde al modello.
- viene trovata `Keywords_eu_passport_number` una parola chiave da o `Keyword_sweden_passport` .
- l'espressione regolare trova una data nel formato `Regex_sweden_eu_passport_date` DD MMM/MMM AA (01 JAN/JAN 12) o viene trovata una parola chiave `Keywords_eu_passport_date` da.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- l'espressione regolare Regex_sweden_passport_number trova contenuto che corrisponde al modello.
- viene trovata `Keywords_eu_passport_number` una parola chiave da o `Keyword_sweden_passport` .


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- carta di registrazione di alieno
- g3 spese di elaborazione
- più voci
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- pass nr
- visto schengen
- visti schengen
- voce singola
- sverige pass
- visa requirements
- visa processing
- visa type

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data di emissione
- data di scadenza


## <a name="sweden-tax-identification-number"></a>Numero di identificazione fiscale svezia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

10 cifre e un simbolo nel motivo specificato

### <a name="pattern"></a>Modello

10 cifre e un simbolo:

- sei cifre che corrispondono alla data di nascita (AAMMDD)
- segno più o meno
- tre cifre che rendono univoco il numero di identificazione dove:
  - per i numeri emessi prima del 1990, la settima e l'ottava cifra identificano la provincia di nascita o i nati all'estero
  - la cifra nella nona posizione indica il sesso per dispari per il maschio o anche per la donna
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_sweden_eu_tax_file_number` chiave from.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.

```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- personal id number
- personnummer
- skatt id nummer
- identifikation skatt
- skattebetalarens identifikationsnummer
- sverige tin
- tax file
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- tax number
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="swift-code"></a>Codice SWIFT

### <a name="format"></a>Formato

quattro lettere seguite da 5-31 lettere o cifre

### <a name="pattern"></a>Modello

quattro lettere seguite da 5-31 lettere o cifre:
- Codice bancario di quattro lettere (senza distinzione tra maiuscole e minuscole)
- uno spazio facoltativo
- 4-28 lettere o cifre (BBAN)
- uno spazio facoltativo
- da una a tre lettere o cifre (resto del BBAN)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_swift.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコード
- SWIFT番号
- BIC番号
- BICコード
- SWIFT コード
- SWIFT 番号
- BiC 番号
- BiC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Svizzera - Numero AVS SSN
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

Numero a 13 cifre

### <a name="pattern"></a>Modello

Numero a 13 cifre:

- tre cifre - 756
- un punto facoltativo
- quattro cifre
- un punto facoltativo
- quattro cifre
- un punto facoltativo
- due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_swiss_social_security_number_ahv trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave Keywords_swiss_social_security_number_ahv'utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_swiss_social_security_number_ahv trova contenuto che corrisponde al modello.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- numero di assicurazione
- personalidno #
- social security number
- personal id number
- identificazione personale n.
- insuranceno #
- uniqueidno #
- identificazione univoca no.
- avs number
- identità personale no versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- id personale di identificazione
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>Taiwan - Numero di identificazione nazionale

### <a name="format"></a>Formato

una lettera (in inglese) seguita da nove cifre

### <a name="pattern"></a>Modello

una lettera (in inglese) seguita da nove cifre:
- una lettera (in inglese, senza distinzione tra maiuscole e minuscole)
- la cifra "1" o "2"
- otto cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_taiwanese_national_id.
- Il checksum ha esito positivo.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號
- 身份證
- 身份證號碼
- 身份證號
- 身分證字號
- 身分證
- 身分證號碼
- 身份證號
- 身分證統一編號
- 國民身分證統一編號
- 簽名
- 蓋章
- 簽名或蓋章
- 簽章

## <a name="taiwan-passport-number"></a>Numero di passaporto taiwanese

### <a name="format"></a>Formato

- Numero di passaporto biometrico: nove cifre
- numero di passaporto non biometrico: nove cifre

### <a name="pattern"></a>Modello
numero di passaporto biometrico:
- il carattere "3"
- otto cifre

numero di passaporto non biometrico:
- nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_taiwan_passport trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_taiwan_passport da un utente.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- Numero passaporto ROC
- Numero passaporto
- N° passaporto
- Num. passaporto

- Passport #
- 护照
- 中華民國護照
- Zhōnghuá Mínguó hùzhào

## <a name="taiwan-resident-certificate-arctarc-number"></a>Numero di certificato residente a Taiwan (ARC/TARC)

### <a name="format"></a>Formato

10 lettere e cifre

### <a name="pattern"></a>Modello

10 lettere e cifre:
- due lettere (senza distinzione tra maiuscole e minuscole)
- otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_taiwan_resident_certificate trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Certificato di residenza
- Cert. di resid

- Cert. di resid.

- Carta d’identità
- Certificato residente straniero
- ARC
- Certificato residente nell’area di Taiwan
- TARC
- 居留證
- 外僑居留證
- 台灣地區居留證

## <a name="thai-population-identification-code"></a>Codice di identificazione della popolazione thai

### <a name="format"></a>Formato

13 cifre

### <a name="pattern"></a>Modello

13 cifre:
- la prima cifra non è zero o nove
- 12 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_Thai_Citizen_Id da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- Numero ID
- Numero di identificazione
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน

## <a name="turkish-national-identification-number"></a>Numero di identificazione nazionale turco

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_Turkish_National_Id da un utente.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>Regno Unito numero di patente di guida

### <a name="format"></a>Formato

Combinazione di 18 lettere e numeri nel formato specificato

### <a name="pattern"></a>Modello

18 lettere e cifre:
- Cinque lettere (senza distinzione tra maiuscole e minuscole) o la cifra "9" al posto di una lettera.
- Una cifra.
- Cinque cifre nel formato di data MMDDY per la data di nascita. Il settimo carattere viene incrementato di 50 se driver è femminile. per exampe, da 51 a 62 invece che da 01 a 12.
- Due lettere (senza distinzione tra maiuscole e minuscole) o la cifra "9" al posto di una lettera.
- Cinque cifre.

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_uk_drivers_license` trova contenuto che corrisponde al modello.
- Viene trovata una parola `Keywords_eu_driver's_license_number` chiave from.
- Il checksum ha esito positivo.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione `Func_uk_drivers_license` trova contenuto che corrisponde al modello.
- Il checksum ha esito positivo.

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- patente di guida
- patenti di guida
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- driver licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- patente di guida
- patenti di guida
- driver' lic
- driver' lics
- patente di guida
- licenze del driver
- patente di guida
- patenti di guida
- driver'slic
- calici del driver
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- licenze driver #
- patenti di guida #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- driver license #
- driver licenses #
- driver licence #
- driver licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- patente di guida #
- patenti di guida #
- driver' lic #
- driver' lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driver'slic #
- calici del driver #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- driver's lics #
- patente di guida #
- licenze del driver #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- licenza driv
- licenze driv
- licenza driv
- driv licences
- driver licen
- drivers licen
- licen del driver
- driving lic
- driving licen
- licenze di guida
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


## <a name="uk-electoral-roll-number"></a>Regno Unito numero di rullino elettorale

### <a name="format"></a>Formato

due lettere seguite da 1-4 cifre

### <a name="pattern"></a>Modello

due lettere (senza distinzione tra maiuscole e minuscole) seguite da 1-4 numeri

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_uk_electoral.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination
- nomination form
- electoral register
- electoral roll


## <a name="uk-national-health-service-number"></a>Regno Unito numero del servizio sanitario nazionale

### <a name="format"></a>Formato

10-17 cifre separate da spazi

### <a name="pattern"></a>Modello

10-17 cifre:
- 3 o 10 cifre
- uno spazio
- tre cifre
- uno spazio
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.
- Si verifica una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_uk_nhs_number.
    - Viene trovata una parola chiave da Keyword_uk_nhs_number1.
    - Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.
- Il checksum ha esito positivo.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service
- nhs
- health services authority
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id
- patient identification
- patient no
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- Criteri di gruppo
- DOB
- D.O.B
- Date of Birth
- Birth Date

## <a name="uk-national-insurance-number-nino"></a>Regno Unito national insurance number (NINO)
Questa entità del tipo di informazioni riservate è inclusa nel tipo di informazioni riservate NUMERO DI IDENTIFICAZIONE NAZIONALE UE. È disponibile anche come entità di tipo di informazioni riservate autonomo.

### <a name="format"></a>Formato

sette o nove caratteri separati da spazi o trattini

### <a name="pattern"></a>Modello

due modelli possibili:

- due lettere (i VALORI NINO validi utilizzano solo determinati caratteri in questo prefisso, convalidato da questo modello, senza distinzione tra maiuscole e minuscole)
- sei cifre
- 'A', 'B', 'C' o 'D' (come il prefisso, nel suffisso sono consentiti solo determinati caratteri, senza distinzione tra maiuscole e minuscole)

OPPURE

- due lettere
- uno spazio o un trattino
- due cifre
- uno spazio o un trattino
- due cifre
- uno spazio o un trattino
- due cifre
- uno spazio o un trattino
- "A", "B", "C" o "D"

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_uk_nino.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- assicurazione
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI Number
- NI No.
- NI #
- NI #
- assicurazione #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>Regno Unito Numero di riferimento fiscale univoco
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori


### <a name="pattern"></a>Modello

10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione  `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello.
- Viene trovata una parola  `Keywords_uk_eu_tax_file_number` chiave from.

```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- tax number
- tax file
- tax id
- identificazione fiscale no
- codice fiscale
- tax no #
- tax no
- numero di registrazione fiscale
- rullato #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="us-bank-account-number"></a>Numero di conto corrente bancario statunitense

### <a name="format"></a>Formato

6-17 cifre

### <a name="pattern"></a>Modello

6-17 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_usa_Bank_Account.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number
- Checking Account
- Checking Account #
- Checking Acct Number
- Checking Acct #
- Checking Acct No.
- Checking Account No.
- Bank Account Number
- Bank Account #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bank Account No.
- Savings Account Number
- Savings Account.
- Savings Account #
- Savings Acct Number
- Savings Acct #
- Savings Acct No.
- Savings Account No.
- Debit Account Number
- Debit Account
- Debit Account #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Debit Account No.

## <a name="us-drivers-license-number"></a>Numero di patente di guida statunitense

### <a name="format"></a>Formato

Varia in base allo stato

### <a name="pattern"></a>Modello

dipende dallo stato, ad esempio New York:
- le nove cifre formattate come ddd ddd ddd corrisponderanno.
- nove cifre come dddddddddd non corrispondono.

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.
- Viene trovata una parola chiave da Keyword_us_drivers_license.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.
- Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.
- Non vengono trovate parole chiave da Keyword_us_drivers_license.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL
- DLS
- CDL
- CDLS
- ID
- ID
- DL #
- DLS #
- CDL #
- CDLS #
- ID #
- ID #
- ID number
- ID numbers
- LIC
- LIC #

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- DriversLic
- DriversLics
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- identification number
- identification numbers
- identification#
- id card
- id cards
- identification card
- identification cards
- DriverLic #
- DriverLics #
- DriverLicense #
- DriverLicenses #
- Driver Lic#
- Driver Lics#
- Driver License#
- Driver Licenses#
- DriversLic #
- DriversLics #
- DriversLicense #
- DriversLicenses #
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Driver'Lic #
- Driver'Lics #
- Driver'License #
- Driver'Licenses #
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicense #
- Driver'sLicenses #
- Driver's Lic#
- Driver's Lics#
- Driver's License#
- Driver's Licenses#
- id card#
- id cards#
- identification card#
- identification cards#


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- abbreviazione dello stato (ad esempio, "NY")
- nome dello stato (ad esempio, "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Numero di identificazione del singolo contribuente statunitense (ITIN)

### <a name="format"></a>Formato

nove cifre che iniziano con "9" e contengono "7" o "8" come quarta cifra, facoltativamente formattate con spazi o trattini

### <a name="pattern"></a>Modello

formattato:
- la cifra "9"
- due cifre
- uno spazio o un trattino
- a "7" o "8"
- una cifra
- uno spazio o un trattino
- quattro cifre

non formattato:
- la cifra "9"
- due cifre
- a "7" o "8"
- cinque cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_itin.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_itin.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_formatted_itin o Func_unformatted_itin trova contenuto che corrisponde al modello.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_itin"></a>Keyword_itin

- contribuente
- tax id
- tax identification
- itin
- i.t.i.n.
- ssn
- tin
- social security
- tax payer
- itins
- rullato
- individual taxpayer


## <a name="us-social-security-number-ssn"></a>Numero di previdenza sociale statunitense (SSN)

### <a name="format"></a>Formato

nove cifre, che possono essere formattate o non formattate

> [!NOTE]
> Se emesso prima della metà del 2011, un SSN ha una formattazione solida in cui alcune parti del numero devono rientrare in determinati intervalli per essere valide (ma non è presente alcun checksum).

### <a name="pattern"></a>Modello

Quattro funzioni ricercano i nomi SSN in quattro modelli diversi:
- Func_ssn trova SSN con formattazione forte precedente alla 2011 formattata con trattini o spazi (ddd-dd-dddd OR ddd ddddd)
- Func_unformatted_ssn trova SSN con formattazione forte precedente alla versione 2011 non formattata come nove cifre consecutive (ddddddddd)
- Func_randomized_formatted_ssn trova sSN post-2011 formattati con trattini o spazi (ddd-dd-dddd OR ddd ddddd)
- Func_randomized_unformatted_ssn trova SSN post-2011 non formattati come nove cifre consecutive (ddddddddd)

### <a name="checksum"></a>Checksum

No


### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_ssn restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_unformatted_ssn trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP ha una bassa probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ssn.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_ssn"></a>Keyword_ssn

- SSA Number
- social security number
- social security #
- social security #
- social security no
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID

## <a name="us--uk-passport-number"></a>Stati Uniti / Regno Unito passport number

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha un'elevata probabilità che sia stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keywords_uk_eu_passport_number` .
- Viene trovata una parola `Keywords_eu_passport_date` chiave da

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.
- Viene trovata una `Keywords_eu_passport_number` parola chiave da o `Keywords_uk_eu_passport_number` .

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passaporti
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- passaporto inglese
- uk passport


## <a name="ukraine-passport-domestic"></a>Passaporto ucraino nazionale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione Regex_Ukraine_Passport_Domestic trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_Ukraine_Passport_Domestic da un utente.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- passaporto dell'Ucraina
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Passaporto internazionale in Ucraina
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità delle comunicazioni
- governance delle informazioni
- gestione dei record
- Sicurezza delle app cloud Microsoft

### <a name="format"></a>Formato

schema alfanumerico a otto caratteri

### <a name="pattern"></a>Modello

Schema alfanumerico a otto caratteri:
- due lettere o cifre
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione Regex_Ukraine_Passport_International trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_Ukraine_Passport_International parola chiave.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- passaporto dell'Ucraina
- passport number
- passport no
- паспорт України
- номер паспорта
