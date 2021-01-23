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
description: La prevenzione della perdita di dati (DLP) nel &amp; Centro sicurezza e conformità include 80 tipi di informazioni riservate pronte per l'uso nei criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.
ms.openlocfilehash: b70f335fd0742e6bc34957058c6e695530e83507
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927132"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definizioni delle entità tipo di informazioni sensibili

Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione. Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate. In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.

I tipi di informazioni riservate richiedono una delle sottoscrizioni seguenti:
- Microsoft 365 E3
- Microsoft 365 E5

I tipi di informazioni riservate vengono utilizzati in:

- [Criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) 
- [Etichette di riservatezza](sensitivity-labels.md)
- [Etichette di conservazione](retention.md)
- [Conformità delle comunicazioni](communication-compliance.md)
- [Criteri di etichettatura automatica](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="aba-routing-number"></a>Numero di Routing ABA

### <a name="format"></a>Formato

nove cifre che possono trovarsi in un modello formattato o non formattato

### <a name="pattern"></a>Modello

Formattato
- quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8
- un trattino
- quattro cifre
- un trattino
- una cifra

Non formattato: nove cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8 

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio ha la sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ABA_Routing.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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
- ABA #
- ABA
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- routing #
- instradamento No
- numero di routing
- routing transit number
- routing #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Numero di identità nazionale Argentina (DNI)

### <a name="format"></a>Formato

Otto cifre con o senza periodi

### <a name="pattern"></a>Modello

Otto cifre
- due cifre
- un periodo facoltativo
- tre cifre
- un periodo facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_argentina_national_id trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_argentina_national_id.

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
- DNI 
- documento Nacional de Identidad 
- documento número 
- numero documento 
- Registro Nacional de las personas 
- RNP 
   
## <a name="australia-bank-account-number"></a>Australia-numero di conto corrente bancario

### <a name="format"></a>Formato

da sei a dieci cifre con o senza un numero di succursale dello stato della banca

### <a name="pattern"></a>Modello

Il numero dell'account è compreso tra sei e dieci cifre.

Numero BSB australiano:
- tre cifre 
- un trattino 
- tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_australia_bank_account_number.
- L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.
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
- AIEA

## <a name="australia-business-number"></a>Numero dell'azienda Australia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud


### <a name="format"></a>Formato

11 cifre con delimitatori opzionali

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_australian_business_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_australian_business_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_australian_business_number trova contenuto corrispondente al modello.

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

- Australia business No
- numero aziendale
- ABN #
- businessid #
- ID business
- ABN
- businessno #

## <a name="australia-company-number"></a>Numero dell'azienda Australia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_Australian_Company_Number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_Australian_Company_Number.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_Australian_Company_Number trova contenuto corrispondente al modello.

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

- possibile
- Australia Company No
- Australia Company No #
- numero dell'azienda Australia
- società australiana No
- società australiana No #
- numero dell'azienda australiana

## <a name="australia-drivers-license-number"></a>Australia-numero della patente di guida

### <a name="format"></a>Formato

nove lettere e cifre

### <a name="pattern"></a>Modello

nove lettere e cifre: 

- due cifre o lettere (senza distinzione tra maiuscole e minuscole) 
- due cifre 
- cinque cifre o lettere (senza distinzione tra maiuscole e minuscole)

OPPURE

- da 1 a 2 lettere facoltative (senza distinzione tra maiuscole e minuscole) 
- da quattro a nove cifre

OPPURE

- nove cifre o lettere (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Driver ' LiCS
- Driver'Licence
- Driver'Licences
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
- Driver ' LiCS #
- Driver'Licence #
- Driver'Licences #
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

- AAA
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver ' License
- Driver ' licenses
- Driver' License
- Driver' Licenses
- Secondola
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
- Driver ' License #
- Driver ' licenses #
- Driver' License#
- Driver' Licenses#
- Secondola #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Numero di conto medica australiano

### <a name="format"></a>Formato

10-11 cifre

### <a name="pattern"></a>Modello

10-11 cifre:
- la prima cifra è compresa nell'intervallo 2-6
- la nona cifra è una cifra di controllo
- decima cifra è la cifra del problema
- undicesima cifra (facoltativa) è il numero individuale

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Medicare

   
## <a name="australia-passport-number"></a>Australia-numero di passaporto

### <a name="format"></a>Formato

Una lettera seguita da sette cifre

### <a name="pattern"></a>Modello

Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passaporto #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passaporto
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- esempio
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>Australia-numero di file fiscale

### <a name="format"></a>Formato

otto-nove cifre

### <a name="pattern"></a>Modello

otto-nove cifre in genere presentate con spazi come indicato di seguito:
- tre cifre 
- uno spazio facoltativo 
- tre cifre 
- uno spazio facoltativo 
- da due a tre cifre in cui l'ultima cifra è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- TFN

## <a name="austria-drivers-license-number"></a>Austria-numero della patente di guida

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- L'espressione regolare  `Regex_austria_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_austria_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver ' s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Carta d'identità Austria
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

Combinazione a 24 caratteri di lettere, cifre e caratteri speciali
  
### <a name="pattern"></a>Modello

24 caratteri:
  
-  22 lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre o segni più 
    
- due lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre, segni più o segni uguali
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- L'espressione regolare  `Regex_austria_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_austria_eu_national_id_card` . 
   
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

- numero di identità
- national id
- Personalausweis Republik Österreich

## <a name="austria-passport-number"></a>Numero di passaporto Austria

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_austria_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_austria_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_austria_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_austria_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
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


## <a name="austria-social-security-number"></a>Austria codice di previdenza sociale

### <a name="format"></a>Formato

10 cifre nel formato specificato
  
### <a name="pattern"></a>Modello

10 cifre:
  
- tre cifre che corrispondono a un numero di serie 
- una cifra di controllo
- sei cifre che corrispondono alla data di nascita (GGMMAA)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP ha elevata fiducia nel rilevare questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione  `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
- viene trovata una parola chiave from  `Keywords_austria_eu_ssn_or_equivalent` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- SSN austriaco
- numero team
- Team No
- codice assicurativo
- insurancecode #
- numero assicurativo
- assicurazioni No
- krankenkassennummer
- Krankenversicherung
- socialsecurityno
- socialsecurityno #
- previdenza sociale No
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale Sicherheit kein
- sozialesicherheitkein #
- SSN #
- SSN
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Austria codice di identificazione fiscale

### <a name="format"></a>Formato

nove cifre con trattino e barra di inoltro opzionali
  
### <a name="pattern"></a>Modello

nove cifre con trattino e barra di inoltro facoltativi:
  
- due cifre
- un trattino (facoltativo)
- tre cifre
- una barra (facoltativa)
- quattro cifre
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_austria_eu_tax_file_number` . 
    
Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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

- Österreich
- st.nr.
- steuernummer
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- codice fiscale
 
## <a name="austria-value-added-tax"></a>Tassa sul valore aggiunto Austria
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

motivo alfanumerico di 11 caratteri

### <a name="pattern"></a>Modello

motivo alfanumerico di 11 caratteri:

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_Austria_Value_Added_Tax trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_Austria_Value_Added_Tax.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_Austria_Value_Added_Tax trova contenuto corrispondente al modello.

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

- numero di partita IVA
- IVA #
- numero di partita IVA austriaca
- IVA No.
- vatno #
- numero di imposta sul valore aggiunto
- IVA austriaca
- MWST
- umsatzsteuernummer
- mwstnummer
- UST.-Identifikationsnummer
- umsatzsteuer-identifikationsnummer
- numero di identificazione IVA
- numero ATU
- Numero UID


## <a name="azure-documentdb-auth-key"></a>Chiave di autenticazione di DocumentDB di Azure

### <a name="format"></a>Formato

La stringa "DocumentDb" seguita dai caratteri e dalle stringhe delineate nel modello seguente.

### <a name="pattern"></a>Modello

- La stringa "DocumentDb"
- Qualsiasi combinazione tra 3-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- Un simbolo maggiore di (>), un segno di uguale (=), un segno di virgolette (") oppure un apostrofo (')
- Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)
- Due segni uguali (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova contenuti che corrispondono al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.

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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Stringa di connessione del database di Azure IAAS e stringa di connessione SQL di Azure

### <a name="format"></a>Formato

Stringa "Server", "Server" o "Data Source" seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa "cloudapp. Azure.<!--no-hyperlink-->com "o" cloudapp. Azure.<!--no-hyperlink-->NET "o" database. Windows.<!--no-hyperlink-->NET "e la stringa" password "o" password "o" pwd ".

### <a name="pattern"></a>Modello

- la stringa "Server", "Server" o "Data Source"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "cloudapp. Azure.<!--no-hyperlink-->com "," cloudapp. Azure.<!--no-hyperlink-->NET "o" database. Windows.<!--no-hyperlink-->NET
- qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "password", "password" o "pwd"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')
- un punto e virgola (;), virgolette (") o apostrofo (')

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureConnectionString trova contenuti che corrispondono al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.

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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-iot-connection-string"></a>Stringa di connessione di Azure.

### <a name="format"></a>Formato

La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices.<!--no-hyperlink-->NET "e" SharedAccessKey ".

### <a name="pattern"></a>Modello

- la stringa "HostName"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "Azure-Devices.<!--no-hyperlink-->NET
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "SharedAccessKey"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)
- segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureIoTConnectionString trova contenuti che corrispondono al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.

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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-publish-setting-password"></a>Password per l'impostazione di pubblicazione di Azure

### <a name="format"></a>Formato

La stringa "UserPwd =" seguita da una stringa alfanumerica.

### <a name="pattern"></a>Modello

- la stringa "UserPwd ="
- qualsiasi combinazione di lettere o cifre minuscole di 60
- virgolette (")

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova contenuti che corrispondono al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.


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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-redis-cache-connection-string"></a>Stringa di connessione della cache di Azure Redis

### <a name="format"></a>Formato

La stringa "Redis. cache. Windows.<!--no-hyperlink-->NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".

### <a name="pattern"></a>Modello

- la stringa "Redis. cache. Windows.<!--no-hyperlink-->NET
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "password" o "pwd"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova contenuti che corrispondono al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.

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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-sas"></a>SAS di Azure

### <a name="format"></a>Formato

La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.

### <a name="pattern"></a>Modello

- la stringa "sig"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)
- la stringa "% 3D"
- qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureSAS trova contenuti che corrispondono al modello.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Stringa di connessione bus di servizio di Azure

### <a name="format"></a>Formato

Stringa "EndPoint" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "ServiceBus. Windows.<!--no-hyperlink-->NET "e" SharedAccesKey ".

### <a name="pattern"></a>Modello

- la stringa "EndPoint"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "ServiceBus. Windows.<!--no-hyperlink-->NET
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "SharedAccessKey"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova contenuti che corrispondono al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.

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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-storage-account-key"></a>Chiave dell'account di archiviazione di Azure

### <a name="format"></a>Formato

La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".

### <a name="pattern"></a>Modello

- la stringa "DefaultEndpointsProtocol"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "AccountKey"
- zero a due caratteri dello spazio vuoto
- segno di uguale (=)
- zero a due caratteri dello spazio vuoto
- qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- due segni uguali (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureStorageAccountKey trova contenuti che corrispondono al modello.
- L'espressione regolare CEP_AzureEmulatorStorageAccountFilter **non** trova il contenuto corrispondente al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.

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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-storage-account-key-generic"></a>Chiave dell'account di archiviazione di Azure (generico)

### <a name="format"></a>Formato

Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.

### <a name="pattern"></a>Modello

- zero a uno dei simboli maggiori di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)
- qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- due segni uguali (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova contenuti che corrispondono al modello.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Numero della patente di guida belga

### <a name="format"></a>Formato

dieci cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

dieci cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_belgium_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da `Keywords_eu_driver's_license_number` o `Keywords_belgium_eu_driver's_license_number` viene trovata.
    
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


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver ' s_license_number

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
- numéro Permis conduire


## <a name="belgium-national-number"></a>Numero nazionale belga

### <a name="format"></a>Formato

11 cifre più delimitatori opzionali

### <a name="pattern"></a>Modello

11 cifre più delimitatori:
- sei cifre e due periodi facoltativi nel formato AA. MM.DD per data di nascita 
- Delimitatore facoltativo da dot, Dash, Space 
- tre cifre sequenziali (dispari per i maschi, anche per le femmine) 
- Delimitatore facoltativo da dot, Dash, Space 
- due cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_belgium_national_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_belgium_national_number.
- Il checksum ha esito positivo.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_belgium_national_number trova contenuto corrispondente al modello.
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

- Ultimo aantal
- BNN #
- BNN
- carte d'identité
- identificazione nazionale
- identifiantnational #
- identificatie
- identificazione
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identità
- iscrizione
- numero nazionale
- Registro nazionale
- nationalnumber #
- nationalnumber
- NIF #
- NIF
- numéro d'assuré
- numéro de Registre National
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro nazionale
- numéronational #
- numero ID personale
- personalausweis
- personalidnumber #
- Registratie
- registrazione
- registrationsnumme
- registrierung
- social security number
- SSN #
- SSN
- steuernummer
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #

## <a name="belgium-passport-number"></a>Numero di passaporto belga

### <a name="format"></a>Formato

due lettere seguite da sei cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

due lettere e seguite da sei cifre
  
### <a name="checksum"></a>Checksum

non applicabile
  
### <a name="definition"></a>Definizione

 Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_belgium_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_belgium_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date2` trova la data nel formato dd mm AA o una parola chiave da `Keywords_eu_passport_date` o `Keywords_belgium_eu_passport_number` trovato

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_belgium_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_belgium_eu_passport_number` viene trovata. 

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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro Passeport
- PASPOORT Nr
- PASPOORT-Nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport Livre
- Pass-Nr
- Passnummer
- Reisepass kein


## <a name="belgium-value-added-tax-number"></a>Numero di imposta sul valore aggiunto belga
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

motivo alfanumerico di 12 caratteri

### <a name="pattern"></a>Modello

motivo alfanumerico di 12 caratteri:

- una lettera B o b
- una lettera E o e
- una cifra 0
- una cifra da 1 a 9
- un punto o un segno meno facoltativo o uno spazio
- quattro cifre
- un punto o un segno meno facoltativo o uno spazio
- quattro cifre


### <a name="checksum"></a>Checksum

Sì


### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_belgium_value_added_tax_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_belgium_value_added_tax_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_belgium_value_added_tax_number trova contenuto corrispondente al modello.

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

- n º TVA
- numero di partita IVA
- IVA No
- numéro t. v. a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- BTW
- BTW #
- IVA #


## <a name="brazil-cpf-number"></a>Brasile CPF numero

### <a name="format"></a>Formato

11 cifre che includono una cifra di controllo e possono essere formattate o non formattate

### <a name="pattern"></a>Modello

Formattato
- tre cifre
- un punto
- tre cifre
- un punto
- tre cifre
- un trattino
- due cifre che sono cifre di controllo

Formattato
- 11 cifre dove le ultime due sono cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_brazil_cpf trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_brazil_cpf.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_brazil_cpf trova contenuto corrispondente al modello.
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
- Entrate
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 

   
## <a name="brazil-legal-entity-number-cnpj"></a>Numero di persona giuridica brasiliana (CNPJ)

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
- numero di diramazione a quattro cifre 
- un trattino 
- due cifre che sono cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_brazil_cnpj trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_brazil_cnpj.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_brazil_cnpj trova contenuto corrispondente al modello.
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

   
## <a name="brazil-national-identification-card-rg"></a>Carta di identità nazionale brasiliana (RG)

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
- una cifra che corrisponde a una cifra di controllo

Registro de Identidade (RIC) (nuovo formato):
- dieci cifre 
- un trattino 
- una cifra che corrisponde a una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_brazil_rg trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_brazil_rg.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_brazil_rg trova contenuto corrispondente al modello.
- Il checksum ha esito positivo.

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
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
- RG (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole) 
- RIC (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole) 


## <a name="bulgaria-drivers-license-number"></a>Bulgaria-numero della patente di guida

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

nove cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_bulgaria_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_bulgaria_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver ' s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно d'средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Bulgaria (Uniform Civil Number)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

dieci cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

dieci cifre senza spazi e delimitatori
  
- sei cifre che corrispondono alla data di nascita (AAMMGG) 
- due cifre che corrispondono all'ordine di nascita
- una cifra che corrisponde al sesso: una cifra pari per il maschio e una cifra dispari per la femmina
- una cifra di controllo

### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_bulgaria_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_bulgaria_eu_national_id_card` . 

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- BNN #
- BNN
- bucn #
- bucn
- grazhdanski nomer
- EGN #
- EGN
- identification number
- national id
- numero nazionale
- nationalnumber #
- nationalnumber
- ID personale
- No personale
- numero personale
- personalidnumber #
- social security number
- SSN #
- SSN
- ID civile uniforme
- uniforme civile No
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
- Номер на гражданството
- ID униформ
- ID граждански униформ
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Bulgaria-numero di passaporto

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

nove cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_bulgaria_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_bulgaria_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_bulgaria_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_bulgaria_eu_passport_number` viene trovata. 

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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- Номер на паспорта
- Номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza

## <a name="canada-bank-account-number"></a>Canada-numero di conto corrente bancario

### <a name="format"></a>Formato

sette o dodici cifre

### <a name="pattern"></a>Modello

Un numero di conto corrente canadese comprende 7 o 12 cifre.

Un numero di transito bancario canadese comprende:
- cinque cifre 
- un trattino 
- tre cifre o
- zero "0" 
- otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_canada_bank_account_number.
- L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

   
## <a name="canada-drivers-license-number"></a>Canada-numero della patente di guida

### <a name="format"></a>Formato

Varia in base alla provincia

### <a name="pattern"></a>Modello

Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

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
- Driver ' LiCS
- Driver ' License
- Driver ' licenses
- Driver'Licence
- Driver'Licences
- Driver'Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Secondola
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
- ID
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
- Driver ' LiCS # 
- Driver ' License # 
- Driver ' licenses # 
- Driver'Licence # 
- Driver'Licences # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- Driver'sLic # 
- Driver'sLics # 
- Secondola # 
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
- ID # 
- ID # 
- idcard card# 
- idcard cards# 
- idcard # 
- identification card# 
- identification cards# 
- identificazione # 

   
## <a name="canada-health-service-number"></a>Numero del servizio sanitario in Canada

### <a name="format"></a>Formato

dieci cifre

### <a name="pattern"></a>Modello

dieci cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- psichiatra
- workers compensation
- Disability

      
## <a name="canada-passport-number"></a>Canada-numero di passaporto

### <a name="format"></a>Formato

due lettere maiuscole seguite da sei cifre

### <a name="pattern"></a>Modello

due lettere maiuscole seguite da sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.

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
- Passaporto #
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

   
## <a name="canada-personal-health-identification-number-phin"></a>Canada Personal Health Identification Number (PHIN)

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_canada_phin restituisce contenuti che corrispondono al modello.
- Sono state trovate almeno due parole chiave provenienti da Keyword_canada_phin o Keyword_canada_provinces.

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
- Quebec
- Northwest Territories
- Ontario
- British Columbia
- Filippa
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Canada

   
## <a name="canada-social-insurance-number"></a>Canada-numero di previdenza sociale

### <a name="format"></a>Formato

nove cifre con trattini o spazi facoltativi

### <a name="pattern"></a>Modello

Formattato
- tre cifre 
- un trattino o uno spazio 
- tre cifre 
- un trattino o uno spazio 
- tre cifre

Non formattato: nove cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.
- Almeno due delle seguenti combinazioni:
    - Viene trovata una parola chiave da Keyword_sin.
    - Viene trovata una parola chiave da Keyword_sin_collaborative.
    - La funzione Func_eu_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- peccati 
- SSN 
- SNSS 
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

   
## <a name="chile-identity-card-number"></a>Cile-numero di carta d'identità

### <a name="format"></a>Formato

da sette a otto cifre più delimitatori una cifra di controllo o una lettera

### <a name="pattern"></a>Modello

da sette a otto cifre più delimitatori:
- una o due cifre 
- un periodo facoltativo 
- tre cifre 
- un periodo facoltativo 
- tre cifre 
- un trattino 
- una cifra o una lettera (senza distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_chile_id_card trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_chile_id_card.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_chile_id_card trova contenuto corrispondente al modello.
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

- Cédula de Identidad
- Identificación
- national identification
- national identification number
- national id
- número de identificación Nacional
- ROL único Nacional
- ROL único tributario
- Correre
- CARREGGIATA
- Tarjeta de identificación
- ROL unico Nacional
- ROL unico tributario
- Correre #
- CARREGGIATA #
- nationaluniqueroleID #
- Nacional Identidad
- número identificación
- Identidad número
- numero Identificacion
- numero Identidad
- Identità cilena No.
- Numero dell'identità cilena
- Identità cilena #
- Registro fiscale univoco
- Ruolo tributario univoco
- Ruolo fiscale univoco
- Numero tributario univoco
- Numero nazionale univoco
- Ruolo nazionale univoco
- Ruolo univoco nazionale
- Cile identità n.
- Numero di identità Cile
- Identità Cile #

   
## <a name="china-resident-identity-card-prc-number"></a>Numero di carta di identità residente in Cina (RPC)

### <a name="format"></a>Formato

18 cifre

### <a name="pattern"></a>Modello

18 cifre:
- sei cifre che corrispondono a un codice di indirizzo 
- otto cifre nel formato AAAAMMGG, ovvero la data di nascita 
- tre cifre che sono un codice di ordinazione 
- una cifra che corrisponde a una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_china_resident_id trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_china_resident_id.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_china_resident_id trova contenuto corrispondente al modello.
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
- RPC 
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

da 14 a 16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e che devono superare il test di Luhn.

### <a name="pattern"></a>Modello

Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.

### <a name="checksum"></a>Checksum

Yes, il checksum Luhn

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_credit_card restituisce contenuti che corrispondono al modello.
- Si verifica una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_cc_verification.
    - Viene trovata una parola chiave da Keyword_cc_name.
    - La funzione Func_expiration_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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
- CVN
- ID
- CVC2
- CVV2
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
- Prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- Cod. sicurezza
- cod sicurezza
- n autorizzazione
- Código
- Codigo
- Cod. SEG
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. Segurança
- Cod. seguranca
- Cod. Segurança
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
- VTO
- data de expiração
- data de expiracao
- data em que expira
- validade
- Valor
- vencimento
- delle transazioni
- numero transazione
- numero di riferimento
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- Amex
- american express
- AmericanExpress
- americano espresso
- Esempio
- Mastercard
- master card
- MC
- Mastercard
- master cards
- diner's Club
- diners club
- DinersClub
- individuare
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- CC #
- CC #:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- Bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- CreditCard
- credit cards
- creditcards.com
- Ccn
- card holder
- titolare
- card holders
- titolari
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
- Enroute
- en route
- card type
- Cardmember Acct
- account cardmember
- Cardno
- Scheda aziendale
- Schede Corporate
- Tipo di scheda
- numero account scheda
- account del membro della scheda
- Cardmember Acct.
- card no.
- scheda No
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- Karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- Kreditkarten-Nummer
- carta di credito
- carta credito
- n. carta
- n carta
- Nr. carta
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
- n º. do cartão
- no do cartão
- no do cartao
- No. do cartão
- No. do cartao
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


## <a name="croatia-drivers-license-number"></a>Numero della patente di guida croata

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- L'espressione regolare  `Regex_croatia_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da `Keywords_eu_driver's_license_number` o `Keywords_croatia_eu_driver's_license_number` viene trovata. 

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver ' s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Croazia-numero di carta d'identità
Questa entità di tipo di informazioni riservate è inclusa nel tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea ed è disponibile come entità di tipo di informazioni riservate stand-alone.

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_croatia_id_card trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_croatia_id_card.

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
- numero di cittadino Master
- Nacionalni identifikacijski broj
- national identification number
- OIB #
- OIB
- osobna iskaznica
- ID Osobni
- Osobni identifikacijski broj
- numero di identificazione personale
- Porezni broj
- Porezni identifikacijski broj
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="croatia-passport-number"></a>Numero del passaporto Croatia

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

nove cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_croatia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_croatia_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_croatia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_croatia_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- BR. Putovnice
- BR putovnice
   
## <a name="croatia-personal-identification-oib-number"></a>Numero di identificazione personale (OIB) (Croazia)

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre:
- dieci cifre 
- la cifra finale è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_croatia_oib_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_croatia_eu_tax_file_number.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_croatia_oib_number trova contenuto corrispondente al modello.
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
- numero di cittadino Master
- Nacionalni identifikacijski broj
- national identification number
- OIB #
- OIB
- osobna iskaznica
- ID Osobni
- Osobni identifikacijski broj
- numero di identificazione personale
- Porezni broj
- Porezni identifikacijski broj
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="cyprus-drivers-license-number"></a>Numero della patente di guida cipriota

### <a name="format"></a>Formato

12 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

12 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_cyprus_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_cyprus_eu_driver's_license_number` viene trovata.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver ' s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Carta d'identità di Cipro
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

dieci cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

dieci cifre 
  
### <a name="checksum"></a>Checksum

non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_cyprus_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_cyprus_eu_national_id_card` . 
    
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

- numero di carta di identità
- numero di carta di identità
- Kimlik karti
- national identification number
- numero ID personale
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Numero di passaporto di Cipro

### <a name="format"></a>Formato

una lettera seguita da 6-8 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

una lettera seguita da sei a otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_cyprus_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_cyprus_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_cyprus_eu_passport_date` trova la data nel formato gg/mm/aaaa o una parola chiave from `Keywords_cyprus_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_cyprus_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_cyprus_eu_passport_number` viene trovata.  
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
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
- Pasaport numarası
- Pasaport No.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- scade su
- emesso il


## <a name="cyprus-tax-identification-number"></a>Numero di identificazione fiscale cipriota
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

otto cifre e una lettera nel modello specificato
  
### <a name="pattern"></a>Modello

otto cifre e una lettera:
  
- "0" o "9"
- sette cifre
- una lettera (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_cyprus_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- TIC #
- TIC
- ID Tin
- Tin No
- latta #
- vergi Kimlik Kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Numero della patente di guida ceco

### <a name="format"></a>Formato

due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

otto lettere e cifre:
  
- letterà È (senza distinzione tra maiuscole E minuscole)
- Una lettera
- uno spazio (facoltativo)
- sei cifre

### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_czech_republic_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_czech_republic_eu_driver's_license_number` viene trovata. 

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver ' s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>Numero di passaporto ceco

### <a name="format"></a>Formato

otto cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

otto cifre senza spazi o delimitatori
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_czech_republic_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_czech_republic_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_czech_republic_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_czech_republic_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- Cestovní pas
- číslo Pasu
- Cestovní Pasu
- Passeport No
- čísla Pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="czech-personal-identity-number"></a>Numero di identità personale ceco

### <a name="format"></a>Formato

nove cifre con barra opzionale (vecchio formato) a dieci cifre con barra di inoltro facoltativa (nuovo formato)

### <a name="pattern"></a>Modello

nove cifre (formato obsoleto):
- sei cifre che rappresentano la data di nascita
- barra di inoltro facoltativa
- tre cifre

dieci cifre (nuovo formato):
- sei cifre che rappresentano la data di nascita
- barra di inoltro facoltativa 
- quattro cifre in cui l'ultima cifra è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:

- La funzione Func_czech_id_card trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_czech_id_card.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:

- La funzione Func_czech_id_card_new_format trova contenuto corrispondente al modello.
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
- ID Repubblica Ceca
- czechidno #
- daňové číslo
- identifikační číslo
- identità No
- numero di identità
- identityno #
- identityno
- numero assicurativo
- national identification number
- nationalnumber #
- numero nazionale
- osobní číslo
- personalidnumber #
- numero ID personale
- numero di identificazione personale
- numero personale
- PID #
- PID
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- SSN
- SSN #
- social security number
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- numero di identificazione univoco


## <a name="denmark-drivers-license-number"></a>Danimarca-numero della patente di guida

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_denmark_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_denmark_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver ' s_license_number

- kørekort
- Kørekortnummer


## <a name="denmark-passport-number"></a>Numero di passaporto Danimarca

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

nove cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_denmark_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_denmark_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date2` trova la data nel formato dd mm AA o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_denmark_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_denmark_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- Pasnummer
- Passeport n °
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="denmark-personal-identification-number"></a>Danimarca-numero di identificazione personale

### <a name="format"></a>Formato

dieci cifre contenenti un segno meno

### <a name="pattern"></a>Modello

dieci cifre:
- sei cifre nel formato GGMMAA, ovvero la data di nascita 
- un trattino 
- quattro cifre in cui la cifra finale è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Func_denmark_eu_tax_file_number trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_denmark_id.
- Il checksum ha esito positivo.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- L'espressione regolare Func_denmark_eu_tax_file_number trova contenuti che corrispondono al modello.
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
- CPR
- CPR #
- gesundheitskarte Nummer
- gesundheitsversicherungkarte Nummer
- scheda integrità
- numero di tessera di assicurazione malattia
- numero di assicurazione sanitaria
- identification number
- identifikationsnummer
- identifikationsnummer #
- numero di identità
- krankenkassennummer
- nationalid #
- nationalnumber #
- numero nazionale
- personalidnumber #
- personalidentityno #
- numero ID personale
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- SSN
- SSN #
- ID pattina
- Kode di pattinaggio
- Nummer di pattinaggio
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- codice fiscale
- Travel Health Insurance Card
- uniqueidentityno #
- codice fiscale
- numero di registrazione fiscale
- tax id
- codice di identificazione fiscale
- taxid #
- taxnumber #
- tax no
- taxno #
- taxnumber
- identificazione fiscale No
- latta #
- taxidno #
- taxidnumber #
- tax no #
- ID Tin
- Tin No
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


## <a name="drug-enforcement-agency-dea-number"></a>Numero dell'agenzia di applicazione della droga (DEA)

### <a name="format"></a>Formato

due lettere seguite da sette cifre

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- una lettera (senza distinzione tra maiuscole/minuscole) da questo set di lettere possibili: abcdefghjklmnprstux, che è un codice dichiarante 
- una lettera (senza distinzione tra maiuscole/minuscole), che è la prima lettera del cognome del dichiarante o della cifra "9"
- sette cifre, l'ultima delle quali è la cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_dea_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave `Keyword_dea_number`
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- Dea
- Dea #
- amministrazione di applicazione della droga
- Drug Enforcement Agency


## <a name="estonia-drivers-license-number"></a>Numero della patente di guida estone

### <a name="format"></a>Formato

due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

due lettere e sei cifre:
  
- lettere "ET" (senza distinzione tra maiuscole e minuscole) 
- sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_estonia_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_estonia_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver ' s_license_number

--Permis de conduire
- juhilubade numbrid
- numero juhiloa
- juhiluba


## <a name="estonia-personal-identification-code"></a>Estonia Codice di identificazione personale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
- una cifra che corrisponde al sesso e al secolo di nascita (numero dispari maschio, anche numero femmina; 1-2: XIX secolo; 3-4: XX secolo; 5-6: XXI secolo)
- sei cifre che corrispondono alla data di nascita (AAMMGG)
- tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data
- una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_estonia_eu_national_id_card` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- ID-kaart
- IK
- isikukood #
- isikukood
- ID maksu
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- numero nazionale
- codice personale
- numero ID personale
- codice di identificazione personale
- numero di identificazione personale
- personalidnumber #
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="estonia-passport-number"></a>Numero di passaporto Estonia

### <a name="format"></a>Formato

una lettera seguita da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

una lettera seguita da sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_estonia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_estonia_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_estonia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_estonia_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

Eesti kodaniku pass passinumbrid numero documento n ° dokumendi Nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="eu-debit-card-number"></a>Numero di carta di debito dell'Unione europea

### <a name="format"></a>Formato

16 cifre

### <a name="pattern"></a>Modello

Modello molto complesso e solido

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- CC # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- AmericanExpress 
- americano espresso 
- Amex 
- atm card 
- atm cards 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- Bancontact 
- bank card 
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- titolare 
- titolari 
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
- CB 
- Ccn 
- check card 
- check cards 
- checkcard
- checkcards 
- chequekaart 
- Cirrus 
- Cirrus-Edc-Maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- CreditCard 
- creditcards.com 
- debetkaart 
- carte 
- debit card 
- debit cards 
- debitcard 
- debitcards 
- debito automatico 
- diners club 
- DinersClub 
- individuare 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- EDC 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- JCB 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- Karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- Kreditkarten-Nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- Maestro 
- master card 
- master cards 
- Mastercard 
- Mastercard 
- MC 
- mister cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- No. de tarjeta 
- No. do cartao 
- No. do cartão 
- nr carta 
- Nr. carta 
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
- n º. do cartão 
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
- opzione 
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
- esempio 
- visa plus 
- visa electron 
- visto 
- Visum 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica 
- ID 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- Cod. SEG 
- Cod. seguranca 
- Cod. Segurança 
- Cod. sicurezza 
- codice di sicurezza 
- codice di verifica 
- Codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- crittogramma 
- cryptogramme 
- CV2 
- CVC 
- CVC2 
- CVN 
- CVV 
- CVV2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. Segurança 
- Código 
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
- No. dell'edizione 
- No. di sicurezza 
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
- Prufziffer 
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
- Valor 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- VTO 
- válido hasta 


## <a name="eu-drivers-license-number"></a>Numero della patente di guida dell'Unione europea

Queste sono le entità nel tipo di informazioni riservate del conducente dell'Unione europea.

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
- [Lussemburgo](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Paesi Bassi](#netherlands-drivers-license-number)
- [Polonia](#poland-drivers-license-number) 
- [Portogallo](#portugal-drivers-license-number)
- [Romania](#romania-drivers-license-number)
- [Slovacchia](#slovakia-drivers-license-number)
- [Slovenia](#slovenia-drivers-license-number)
- [Spagna](#spain-drivers-license-number)
- [Svezia](#sweden-drivers-license-number)
- [U.K.](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Numero di identificazione nazionale dell'Unione europea

Queste sono le entità del tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea.

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
- [Lussemburgo](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Paesi Bassi](#netherlands-citizens-service-bsn-number)
- [Polonia](#poland-national-id-pesel)
- [Portogallo](#portugal-citizen-card-number)
- [Romania](#romania-personal-numeric-code-cnp)
- [Slovacchia](#slovakia-personal-number)
- [Slovenia](#slovenia-unique-master-citizen-number)
- [Spagna](#spain-dni)
- [U.K.](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>Numero di passaporto EU 

Queste sono le entità del numero di passaporto typeThese informazioni riservate dell'Unione europea sono le entità nel bundle del numero di passaporto dell'Unione europea.

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
- [Lussemburgo](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Paesi Bassi](#netherlands-passport-number)
- [Polonia](#poland-passport-number)
- [Portogallo](#portugal-passport-number)
- [Romania](#romania-passport-number)
- [Slovacchia](#slovakia-passport-number)
- [Slovenia](#slovenia-passport-number)
- [Spagna](#spain-passport-number)
- [Svezia](#sweden-passport-number)
- [U.K.](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Codice di previdenza sociale dell'Unione europea o identificazione equivalente

Queste sono le entità che si trovano nel codice di previdenza sociale dell'Unione europea o nel tipo di informazioni riservate di identificazione equivalente.

- [Austria](#austria-social-security-number)
- [Belgio](#belgium-national-number)
- [Croazia](#croatia-personal-identification-oib-number)
- [Ceco](#czech-personal-identity-number)
- [Danimarca](#denmark-personal-identification-number)
- [Finlandia](#finland-national-id)
- [Francia](#france-social-security-number-insee-or-equivalent-identification)
- [Germania](#germany-identity-card-number)
- [Grecia](#greece-national-id-card)
- [Ungheria](#hungary-social-security-number-taj)
- [Portogallo](#portugal-citizen-card-number)
- [Spagna](#spain-social-security-number-ssn)
- [Svezia](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>Numero di identificazione fiscale dell'Unione europea

Tali entità sono incluse nel tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea.

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
- [Lussemburgo](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Paesi Bassi](#netherlands-tax-identification-number)
- [Polonia](#poland-tax-identification-number)
- [Portogallo](#portugal-tax-identification-number)
- [Romania](#romania-personal-numeric-code-cnp)
- [Slovacchia](#slovakia-personal-number)
- [Slovenia](#slovenia-tax-identification-number)
- [Spagna](#spain-tax-identification-number)
- [Svezia](#sweden-tax-identification-number)
- [U.K.](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Finlandia-numero della patente di guida

### <a name="format"></a>Formato

dieci cifre e lettere contenenti un trattino
  
### <a name="pattern"></a>Modello

dieci cifre e lettere contenenti un trattino:
  
- sei cifre 
- un trattino
- tre cifre 
- una cifra o una lettera
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_finland_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_finland_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver ' s_license_number

- ajokortti
- permis de conduire
- numero ajokortin
- kuljettaja Lic.
- körkort
- körkortnummer
- förare Lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Finlandia-numero di assicurazione sanitaria europea
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero di 20 cifre

### <a name="pattern"></a>Modello

numero di 20 cifre:

- dieci cifre-8024680246
- uno spazio o un trattino facoltativo
- dieci cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La Regex_Finland_European_Health_Insurance_Number Regex trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_Finland_European_Health_Insurance_Number.

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

- Team #
- Team
- finlandehicnumber #
- Finlandia sjukförsäkringskort
- scheda integrità
- tessera sanitaria
- numero di assicurazione sanitaria
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring Nummer
- sjukförsäkringskort
- Suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>ID nazionale Finlandia

### <a name="format"></a>Formato

sei cifre più un carattere che indica un secolo più tre cifre più una cifra di controllo

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- sei cifre nel formato formato GGMMAA che sono una data di nascita 
- indicatore Century ('-',' +' or ' a') 
- numero di identificazione personale a tre cifre 
- una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- la funzione Func_finnish_national_id trova contenuto che corrisponde al modello
- viene trovata una parola chiave da Keyword_finnish_national_id
- il checksum passa

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- ID No
- numero ID
- identification number
- numero identiteetti
- numero di identità
- NumeroID del
- Kansallinen henkilötunnus
- kansallisen henkilökortin
- carta d'identità nazionale
- ID nazionale No.
- ID personale
- codice identità personale
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- tunnistenumero
- numero tunnus
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Numero di passaporto Finlandia

### <a name="format"></a>Formato
combinazione di nove lettere e cifre

### <a name="pattern"></a>Modello
combinazione di nove lettere e cifre:
- due lettere (senza distinzione tra maiuscole e minuscole) 
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_finland_passport_number trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keywords_eu_passport_number_common o Keyword_finland_passport_number.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Parole chiave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- Suomalainen passi
- numero passin
- passin numero. #
- numero passin #
- passin numero.
- passi #
- numero di passi


## <a name="france-drivers-license-number"></a>Francia-numero della patente di guida

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- la funzione Func_french_drivers_license trova contenuto corrispondente al modello.
- viene trovata una parola chiave da Keyword_french_drivers_license.

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
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- Numéros de licence


## <a name="france-health-insurance-number"></a>Francia-numero di assicurazione malattia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero 21 cifre

### <a name="pattern"></a>Modello

numero 21 cifre:

- dieci cifre
- uno spazio facoltativo
- dieci cifre
- uno spazio facoltativo
- una cifra


### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- la Regex_France_Health_Insurance_Number Regex trova contenuto che corrisponde al modello.
- viene trovata una parola chiave da Keyword_France_Health_Insurance_Number.

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

- scheda assicurazioni
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>Carta di identità nazionale francese (CNI)

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keywords_france_eu_national_id_card.

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
- Carte nationale d'identité
- Carte nationale d'idenite No
- CNI #
- CNI
- compte bancaire
- national identification number
- identità nazionale
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale

   
## <a name="france-passport-number"></a>Francia-numero di passaporto
Questa entità di tipo di informazioni riservate è disponibile nel tipo di informazioni riservate del numero di passaporto dell'Unione europea ed è disponibile come entità di tipo di informazioni riservate stand-alone.

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

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_passport.

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passaporto #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Francia-numero di previdenza sociale (INSEE) o identificazione equivalente
Questa entità di tipo di informazioni riservate è inclusa nel codice di previdenza sociale dell'Unione europea e nel tipo di informazioni riservate ID equivalente ed è disponibile come entità di tipo di informazioni riservate stand-alone.

### <a name="format"></a>Formato

15 cifre

### <a name="pattern"></a>Modello

Deve corrispondere a uno di questi due modelli:
- 13 cifre seguite da uno spazio seguito da due cifre<br/>
o
- 15 cifre consecutive

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:
- La funzione Func_french_insee o Func_fr_insee trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_fr_insee.
- Il checksum ha esito positivo.

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_french_insee o Func_fr_insee trova contenuto corrispondente al modello.
- Non vengono trovate parole chiave da Keyword_fr_insee.
- Il checksum ha esito positivo.

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- INSEE
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- No. d'identité
- numero d'identite
- no d'identite
- No. d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 

## <a name="france-tax-identification-number"></a>Francia-numero di identificazione fiscale

### <a name="format"></a>Formato

13 cifre
  
### <a name="pattern"></a>Modello

13 cifre
  
- Una cifra che deve essere 0, 1, 2 o 3
- 1 cifra
- Uno spazio (facoltativo)
- 2 cifre 
- Uno spazio (facoltativo)
- 3 cifre 
- Uno spazio (facoltativo)
- 3 cifre 
- Uno spazio (facoltativo)
- 3 cifre di controllo 

  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_france_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="france-value-added-tax-number"></a>Francia-numero di imposta sul valore aggiunto
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

13 caratteri alfanumerici

### <a name="pattern"></a>Modello

13 caratteri alfanumerici:

- due lettere-FR (senza distinzione tra maiuscole e minuscole)
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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_france_value_added_tax_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_france_value_added_tax_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_france_value_added_tax_number trova contenuto corrispondente al modello.

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

- numero di partita IVA
- IVA No
- IVA #
- imposta sul valore aggiunto
- identificazione della sirena No Numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n ° TVA
- numéro de TVA
- Sirena d'identification numéro


## <a name="germany-drivers-license-number"></a>Germania-numero della patente di guida

### <a name="format"></a>Formato

combinazione di 11 cifre e lettere

### <a name="pattern"></a>Modello

11 cifre e lettere (senza distinzione tra maiuscole/minuscole):
- una cifra o una lettera 
- due cifre 
- sei cifre o lettere 
- una cifra 
- una cifra o una lettera

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Nr-Führerschein
- Nr-fuhrerschein
- Nr-fuehrerschein
- No-Führerschein
- No-fuhrerschein
- No-fuehrerschein
- n-Führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- dlno


## <a name="germany-identity-card-number"></a>Germania-numero di carta d'identità

### <a name="format"></a>Formato

dal 1 ° novembre 2010: nove lettere e cifre

dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre

### <a name="pattern"></a>Modello

dal 1 ° novembre 2010:
- una lettera (senza distinzione tra maiuscole e minuscole) 
- otto cifre

dal 1 ° aprile 1987 al 31 ottobre 2010:
- dieci cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- L'espressione regolare Regex_germany_id_card trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_germany_id_card.

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
- numero di identità
- ID-Nummer
- ID personale
- personalausweis
- persönliche ID Nummer
- persönliche identifikationsnummer
- persönliche-ID-Nummer


## <a name="germany-passport-number"></a>Germania-numero di passaporto

### <a name="format"></a>Formato

dieci cifre o lettere

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- il primo carattere è una cifra o una lettera di questo set (C, F, G, H, J, K) 
- tre cifre 
- cinque cifre o lettere da questo set (C,-H, J-N, P, R, T, V-Z) 
- una cifra

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_german_passport restituisce contenuti che corrispondono al modello.
- Una parola chiave da `Keyword_german_passport` o `Keywords_eu_passport_number_common` viene trovata.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.
- Una parola chiave da `Keyword_german_passport` o `Keywords_eu_passport_number_common` viene trovata.
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
- Passeport No.
- Passeport No

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto


## <a name="germany-tax-identification-number"></a>Germania-codice fiscale

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_germany_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- ID Steuer
- steueridentifikationsnummer
- steuernummer
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- Zinn #
- Zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Germania-numero di imposta sul valore aggiunto
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

modello alfanumerico a 11 caratteri

### <a name="pattern"></a>Modello

motivo alfanumerico di 11 caratteri:

- una lettera D o d
- una lettera E o e
- uno spazio facoltativo
- tre cifre
- uno spazio o una virgola facoltativo
- tre cifre
- uno spazio o una virgola facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_germany_value_added_tax_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_germany_value_added_tax_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_germany_value_added_tax_number trova contenuto corrispondente al modello.

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

- numero di partita IVA
- IVA No
- IVA #
- IVA # Mehrwertsteuer
- MWST
- mehrwertsteuer identifikationsnummer
- Mehrwertsteuer Nummer


## <a name="greece-drivers-license-number"></a>Grecia-Numero della patente di guida

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

nove cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_greece_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_greece_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver ' s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Carta d'identità nazionale (Grecia)

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_greece_id_card trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_greece_id_card.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- L'espressione regolare Regex_greece_id_card trova contenuti che corrispondono al modello.

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

- ID greco
- ID nazionale greco
- scheda ID personale greco
- ID polizia greco
- carta di identità
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Grecia-numero di passaporto

### <a name="format"></a>Formato

Due lettere seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere seguite da 7 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_greece_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_greece_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_greece_eu_passport_date` trova la data nel formato gg MMM AA (esempio-28 agosto 19) oppure viene trovata una parola chiave `Keywords_greece_eu_passport_date`

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_greece_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_greece_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Grecia-codice di previdenza sociale (AMKA)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

Undici cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

- 6 cifre come data di nascita AAMMGG
- 4 cifre
- una cifra di controllo
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_greece_eu_ssn` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_greece_eu_ssn_or_equivalent` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- SSN
- SSN #
- previdenza sociale No
- socialsecurityno #
- social security number
- AMKA
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Grecia-codice fiscale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- L'espressione regolare  `Regex_greece_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_greece_eu_tax_file_number` . 
    
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

- AFM #
- AFM
- aφμ | aφμ Αριθμός
- aφμ
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- Tax Registry No
- numero del registro di sistema fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- ID Tin
- Tin No
- latta #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Numero di carta di identità (HKID) di Hong Kong

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

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_hong_kong_id_card trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_hong_kong_id_card.
- Il checksum ha esito positivo.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_hong_kong_id_card trova contenuto corrispondente al modello.
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
- carta di identità di Hong Kong
- HKIDC
- id card
- carta di identità
- carta di identità HK
- ID Hong Kong
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

   
## <a name="hungary-drivers-license-number"></a>Numero della patente di guida ungherese

### <a name="format"></a>Formato

Due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Due lettere e sei cifre:
  
- Due lettere (senza distinzione tra maiuscole e minuscole) 
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- L'espressione regolare  `Regex_hungary_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_hungary_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver ' s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Numero di identificazione personale Ungheria
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

11 cifre
  
### <a name="pattern"></a>Modello

11 cifre:
  
- Una cifra che corrisponde al sesso (1-maschio, 2-Femmina, altri numeri sono possibili anche per i cittadini nati prima del 1900 o cittadini con doppia cittadinanza) 
- Sei cifre che corrispondono alla data di nascita (AAMMGG)
- Tre cifre che corrispondono a un numero di serie
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- La funzione  `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_hungary_eu_national_id_card` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
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

- numero ID
- identification number
- SZ IG
- SZ. IG.
- SZ. IG.
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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_hungary_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_hungary_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_hungary_eu_passport_date` trova la data nel formato dd MMM/MMM AA (esempio-01 MÁR/Mar 12) oppure viene trovata una parola chiave from `Keywords_eu_passport_date`

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_hungary_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_hungary_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám


## <a name="hungary-social-security-number-taj"></a>Numero di previdenza sociale (TAJ) Ungheria

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- La funzione  `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_hungary_eu_ssn_or_equivalent` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
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

- codice di previdenza sociale ungherese
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- Taj
- Taj #
- SSN
- SSN #
- previdenza sociale No
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- Magyar ÁFA szám


## <a name="hungary-tax-identification-number"></a>Numero di identificazione fiscale ungherese
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

Dieci cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Dieci cifre:
  
- Una cifra che deve essere "8" 
- Otto cifre
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- La funzione  `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_hungary_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
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
- Tin ungherese
- hungatiantin #
- autorità tributaria No
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- numero di partita IVA


## <a name="hungary-value-added-tax-number"></a>Numero dell'imposta sul valore aggiunto (Ungheria)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

motivo alfanumerico di 10 caratteri

### <a name="pattern"></a>Modello

motivo alfanumerico di 10 caratteri:

- 2 lettere-HU o Hu
- spazio facoltativo
- 8 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:

- La funzione Func_hungarian_value_added_tax_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_hungarian_value_added_tax_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:

- La funzione Func_hungarian_value_added_tax_number trova contenuto corrispondente al modello.

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

- IVA
- numero di imposta sul valore aggiunto
- IVA #
- vatno #
- hungarianvatno #
- tassa no.
- ÁFA d'imposta sul valore aggiunto
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>India-numero di conto permanente (PAN)

### <a name="format"></a>Formato

10 lettere o cifre

### <a name="pattern"></a>Modello

10 lettere o cifre:
- Tre lettere (senza distinzione tra maiuscole e minuscole) 
- Lettera in C, P, H, F, A, T, B, L, J, G (senza distinzione tra maiuscole e minuscole)
- Una lettera
- Quattro cifre 
- Una lettera (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_india_permanent_account_number trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_india_permanent_account_number.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- L'espressione regolare Regex_india_permanent_account_number trova contenuti che corrispondono al modello.


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
   
## <a name="india-unique-identification-aadhaar-number"></a>Numero Aadhaar (India Unique Identification)

### <a name="format"></a>Formato

12 cifre contenenti spazi o trattini facoltativi 

### <a name="pattern"></a>Modello

12 cifre:
- Una cifra che non è 0 o 1
- Tre cifre 
- Uno spazio o un trattino facoltativo  
- Quattro cifre 
- Uno spazio o un trattino facoltativo  
- L'ultimo carattere, ovvero il numero di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_india_aadhaar trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_india_aadhar.
- Il checksum ha esito positivo.
- 
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:

- La funzione Func_india_aadhaar trova contenuto corrispondente al modello.
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
- UID
- आधार
- uidai
   
## <a name="indonesia-identity-card-ktp-number"></a>Numero di carta di identità (KTP) (Indonesia)

### <a name="format"></a>Formato

16 cifre contenenti punti facoltativi 

### <a name="pattern"></a>Modello

16 cifre:
- Codice provincia a due cifre  
- Un punto (facoltativo)  
- Codice città o area a due cifre  
- Codice sotto-distretto a due cifre  
- Un punto (facoltativo)  
- Sei cifre nel formato GGMMAA, ovvero la data di nascita 
- Un punto (facoltativo)  
- Quattro cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:

- L'espressione regolare Regex_indonesia_id_card trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_indonesia_id_card.

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

Codice paese (due lettere) più cifre di controllo (due cifre) più numero BBAN (fino a 30 caratteri)

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:

- Codice paese a due lettere
- Due cifre di controllo (seguite da uno spazio facoltativo) 
- 1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)
- 1-3 lettere o cifre

Il formato di ogni paese è leggermente diverso. Il tipo di informazioni riservate IBAN copre questi 60 paesi:

ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU, NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- Viene trovata una parola chiave da Dictionary_icd_10_updated.
- Viene trovata una parola chiave da Dictionary_icd_10_codes.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- Viene trovata una parola chiave da Dictionary_icd_10_ aggiornata.

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

Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_updated, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.

Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_codes, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Questo tipo di ricerca è solo per i codici assicurativi, non per la descrizione.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Classificazione internazionale delle malattie (ICD-9-CM)

### <a name="format"></a>Formato

Dizionario

### <a name="pattern"></a>Modello

Parola chiave

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- Viene trovata una parola chiave da Dictionary_icd_9_updated.
- Viene trovata una parola chiave da Dictionary_icd_9_codes.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- Viene trovata una parola chiave da Dictionary_icd_9_updated.

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

Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_updated, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.

Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_codes, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Questo tipo di ricerca è solo per i codici assicurativi, non per la descrizione.

## <a name="ip-address"></a>Indirizzo IP

### <a name="format"></a>Formato

#### <a name="ipv4"></a>IPv4
Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4

#### <a name="ipv6"></a>IPv6
Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)

### <a name="pattern"></a>Modello

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Per IPv6, un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.
- Non vengono trovate parole chiave da Keyword_ipaddress.

Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:
- L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ipaddress.

Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:
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

- IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)
- ip address 
- Indirizzi IP
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Numero di patente d'Irlanda

### <a name="format"></a>Formato

Sei cifre seguite da quattro lettere
  
### <a name="pattern"></a>Modello

Sei cifre e quattro lettere:
  
- Sei cifre
- Quattro lettere (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
  
- L'espressione regolare  `Regex_ireland_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_ireland_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver ' s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Irlanda-numero di passaporto

### <a name="format"></a>Formato

Due lettere o cifre seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere o cifre seguite da sette cifre:
  
- Due cifre o lettere (senza distinzione tra maiuscole/minuscole)
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_ireland_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_ireland_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_ireland_eu_passport_date` trova la data nel formato dd MMM/MMM yyyy (example-01 Bea/MAY 1988) oppure viene trovata una parola chiave from `Keywords_eu_passport_date`

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_ireland_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_ireland_eu_passport_number` viene trovata.
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- numero Passeport
- uimhreacha pasanna
- uimhir pas
- uimhir fasi
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="ireland-personal-public-service-pps-number"></a>Irlanda-numero di servizio pubblico personale (PPS)

### <a name="format"></a>Formato

Formato precedente (fino al 31 dicembre 2012):
- sette cifre seguite da 1-2 lettere 

Nuovo formato (1 gen 2013 e successive):
- sette cifre seguite da due lettere

### <a name="pattern"></a>Modello

Formato precedente (fino al 31 dicembre 2012):
- sette cifre 
- una o due lettere (senza distinzione tra maiuscole e minuscole) 

Nuovo formato (1 gen 2013 e successive):
- sette cifre 
- una lettera (senza distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo alfabetica 
- Una lettera facoltativa nell'intervallo A-I o "W"

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_ireland_pps trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_ireland_eu_national_id_card.
- Il checksum ha esito positivo.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_ireland_pps trova contenuto corrispondente al modello.
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
- numero ID personale
- numero di servizio pubblico personale
- servizio personale No
- phearsanta seirbhíse poiblí
- PPS No
- numero PPS
- PP num
- servizio PPS No
- ppsn
- ppsno #
- ppsno
- PSP
- servizio pubblico no
- publicserviceno #
- publicserviceno
- reddito e numero di previdenza sociale
- RSI No
- numero RSI
- rsin
- client di aitheantais di Seirbhís
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="israel-bank-account-number"></a>Israele-numero di conto corrente bancario

### <a name="format"></a>Formato

13 cifre

### <a name="pattern"></a>Modello

Formattato
- due cifre 
- un trattino 
- tre cifre 
- un trattino 
- otto cifre

Formattato
- 13 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
   
## <a name="israel-national-identification-number"></a>Israele-numero di identificazione nazionale

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre consecutive

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
-   NumeroID del #
-   numero ID
-   identità No        
-   identitynumber #
-   numero di identità
-   israeliidentitynumber       
-   ID personale
-   ID univoco  

   
## <a name="italy-drivers-license-number"></a>Italiano numero di patente di guida

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

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_italy_drivers_license_number.

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di brevetto
- patente di guida 
- patente guida
- patenti di guida
- patenti guida

## <a name="italy-fiscal-code"></a>Codice fiscale Italia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

una combinazione di 16 caratteri di lettere e cifre nel modello specificato
  
### <a name="pattern"></a>Modello

Combinazione di lettere e cifre di 16 caratteri:
- tre lettere che corrispondono alle prime tre consonanti del nome di famiglia
- tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome
- due cifre che corrispondono alle ultime cifre dell'anno di nascita
- una lettera che corrisponde alla lettera per il mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)
- due cifre che corrispondono al giorno del mese di nascita, al fine di distinguere tra i sessi, 40 viene aggiunto al giorno di nascita per le donne
- quattro cifre che corrispondono al codice di area specifico per il comune in cui è nata la persona (i codici a livello nazionale vengono utilizzati per i paesi esteri)
- una cifra di parità
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_italy_eu_national_id_card` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- codice Fiscal
- codice fiscale
- codice ID personale
- codice personale
- codice fiscale
- Numero certificato personale
- numero di identificazione fiscale
- numero ID personale
- numero personale
- numero di certificato personale
- codice personale
- codice ID personale
- numero ID personale
- personalcodeno #
- codice fiscale
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- numero dell'identità fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="italy-passport-number"></a>Numero di passaporto Italia

### <a name="format"></a>Formato

due lettere o cifre seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

due lettere o cifre seguite da sette cifre:
  
- due cifre o lettere (senza distinzione tra maiuscole e minuscole)
- sette cifre
    
### <a name="checksum"></a>Checksum

non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_italy_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_italy_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_italy_eu_passport_date` trova la data nel formato dd MMM/MMM yyyy (example-01 gen/gen 1988) oppure viene trovata una parola chiave from `Keywords_eu_passport_date`

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_italy_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_italy_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- Numero passaporto
- numéro Passeport
- numero di passaporto
- numeri del passaporto
- Passeport Italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="italy-value-added-tax-number"></a>Numero di imposta sul valore aggiunto Italia
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

13 caratteri alfanumerici con delimitatori opzionali

### <a name="pattern"></a>Modello

13 caratteri alfanumerici con delimitatori facoltativi:

- I o i
- T o t
- spazio facoltativo, punto, segno meno o virgola
- 11 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_italy_value_added_tax_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_italy_value_added_tax_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_italy_value_added_tax_number trova contenuto corrispondente al modello.

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

- numero di partita IVA
- IVA No
- IVA #
- IVA
- IVA #


## <a name="japan-bank-account-number"></a>Giappone-numero di conto corrente bancario

### <a name="format"></a>Formato

sette o otto cifre

### <a name="pattern"></a>Modello

numero di conto corrente bancario:
- sette o otto cifre
- codice della filiale del conto corrente bancario:
- quattro cifre 
- uno spazio o un trattino (facoltativo) 
- tre cifre

Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_bank_account.
- Si verifica una delle situazioni seguenti:
- La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_bank_branch_code.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

## <a name="japan-drivers-license-number"></a>Giappone-numero della patente di guida

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- secondola
- driverslicenses
- driver'slicenses
- driverlicenses
- DL #
- DLS #
- driver'lic #
- driver'lics #
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


## <a name="japan-my-number---corporate"></a>Giappone My Number-Corporate
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero di 13 cifre

### <a name="pattern"></a>Modello

numero 13 cifre:

- una cifra da 1 a 9
- 12 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_japanese_my_number_corporate trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_japanese_my_number_corporate.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_japanese_my_number_corporate trova contenuto corrispondente al modello.

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


## <a name="japan-my-number---personal"></a>Giappone il mio numero-personale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero di 12 cifre

### <a name="pattern"></a>Modello

numero di 12 cifre:

- quattro cifre
- spazio facoltativo, punto o segno meno
- quattro cifre
- spazio facoltativo, punto o segno meno
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_japanese_my_number_personal trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_japanese_my_number_personal.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_japanese_my_number_personal trova contenuto corrispondente al modello.

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

- numero personale
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード

   
## <a name="japan-passport-number"></a>Giappone-numero di passaporto

### <a name="format"></a>Formato

due lettere seguite da sette cifre

### <a name="pattern"></a>Modello

due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- Passaporto
- Passport Number
- Passaporto No.
- Passport#
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パスポートNo.
- 旅券番号
- 旅券番号＃
- ♯ di 旅券番号
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Giappone-numero di carta di soggiorno

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

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_jp_residence_card_number trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_residence_card_number.

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

- Numero di carta di soggiorno
- Carta di soggiorno No
- Carta di soggiorno #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Giappone-numero di registrazione residente

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

   
## <a name="japan-social-insurance-number-sin"></a>Giappone-numero di previdenza sociale (SIN)

### <a name="format"></a>Formato

7-12 cifre

### <a name="pattern"></a>Modello

7-12 cifre:
- quattro cifre 
- un trattino (facoltativo) 
- sei cifre o
- 7-12 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_sin.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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


## <a name="latvia-drivers-license-number"></a>Numero della patente di guida in Lettonia

### <a name="format"></a>Formato

tre lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

tre lettere e sei cifre:
  
- tre lettere (senza distinzione tra maiuscole e minuscole) 
- sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_latvia_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_latvia_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver ' s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Codice personale Lettonia

### <a name="format"></a>Formato

11 cifre e un segno meno facoltativo
  
### <a name="pattern"></a>Modello

Formato precedente

11 cifre e un trattino:
  
- sei cifre che corrispondono alla data di nascita (GGMMAA) 
- un trattino
- una cifra che corrisponde al secolo di nascita ("0" per il XIX secolo, "1" per il XX secolo e "2" per il XXI secolo)
- quattro cifre, generate in modo casuale

Nuovo formato

11 cifre

- Due cifre "32"
- 9 cifre
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_latvia_eu_national_id_card` o l'espressione Regex `Regex_latvia_eu_national_id_card_new_format` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_latvia_eu_national_id_card` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_latvia_eu_national_id_card` o l'espressione Regex `Regex_latvia_eu_national_id_card_new_format` trova contenuto che corrisponde al modello. 
    
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
- Alvas n ē
- numero di nascita
- numero cittadino
- numero civile
- numero del censimento elettronico
- numero elettronico
- codice fiscale
- numero utente di assistenza sanitaria
- ID #
- ID-code
- identification number
- identifikācijas numurs
- ID-Number
- numero individuale
- Latvija Alva
- ID Nacionālais
- national id
- numero di identificazione nazionale
- numero di identità nazionale
- national insurance number
- numero del registro nazionale
- nodokļa numurs
- ID nodokļu
- nodokļu identifikācija numurs
- numero di certificato personale
- codice personale
- codice ID personale
- numero ID personale
- codice di identificazione personale
- identificatore personale
- numero di identità personale
- numero personale
- codice numerico personale
- personalcodeno #
- personas Kods
- codice di identificazione della popolazione
- numero di servizio pubblico
- registration number
- numero di ricavo
- social insurance number
- social security number
- codice fiscale dello stato
- tax file number
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- numero degli elettori

## <a name="latvia-passport-number"></a>Lettonia-numero di passaporto

### <a name="format"></a>Formato

due lettere o cifre seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

due lettere o cifre seguite da sette cifre:
  
- due cifre o lettere (senza distinzione tra maiuscole e minuscole)
- sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_latvia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_latvia_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_latvia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_latvia_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- Pases numuri
- Pases Nr
- Passeport No
- n ° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="lithuania-drivers-license-number"></a>Lituania-numero della patente di guida

### <a name="format"></a>Formato

otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

otto cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_lithuania_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_lithuania_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver ' s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Codice personale Lituania
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

11 cifre senza spazi e delimitatori:
  
- una cifra (1-6) che corrisponde al sesso e al secolo della nascita della persona
- sei cifre che corrispondono alla data di nascita (AAMMGG) 
- tre cifre che corrispondono al numero di serie della data di nascita
- una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_lithuania_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- numero di servizio Citizen
- ID mokesčių
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- numeri mokesčių
- national identification number
- codice personale
- codice numerico personale
- piliečio paslaugos numeris
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Numero del passaporto della Lituania

### <a name="format"></a>Formato

otto cifre o lettere senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

otto cifre o lettere (senza distinzione tra maiuscole e minuscole)
  
### <a name="checksum"></a>Checksum

non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_lithuania_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_lithuania_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date3` trova la data nel formato dd mm yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_lithuania_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_lithuania_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- numero di Paso
- Paso numeriai
- Paso Nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="luxemburg-drivers-license-number"></a>Numero della patente di guida del Lussemburgo

### <a name="format"></a>Formato

sei cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

sei cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_luxemburg_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_luxemburg_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver ' s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Numero di identificazione nazionale del Lussemburgo (persone fisiche)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre:
  
- 11 cifre 
- due cifre di controllo
    
### <a name="checksum"></a>Checksum

sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_luxemburg_eu_national_id_card` . 

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- ID eindeutige
- ID eindeutige-Nummer
- eindeutigeid #
- ID personnelle
- idpersonnelle #
- idpersonnelle
- codice singolo
- ID individuale
- identificazione individuale
- identità individuale
- personale di Numéro d'identification
- ID personale
- identificazione personale
- identità personale
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- ID univoco
- identità univoca
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Numero di passaporto del Lussemburgo

### <a name="format"></a>Formato

otto cifre o lettere senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

otto cifre o lettere (senza distinzione tra maiuscole e minuscole)
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_luxemburg_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_luxemburg_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date3` trova la data nel formato dd mm yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_luxemburg_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_luxemburg_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- passaggio Lussemburgo
- Lussemburgo Passeport
- passaporto lussemburghese
- No de Passeport
- No-Reisepass
- Nr-Reisepass
- numéro de Passeport
- passare NET
- passare Nr
- passnummer
- Passeport Nombre
- reisepässe
- Reisepass-Nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Numero di identificazione nazionale del Lussemburgo (persone non fisiche)

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_luxemburg_eu_tax_file_number_non_natural` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_luxemburg_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Étain non
- étain #
- d'impôt di identificazione
- identifikatiounsnummer Tax Luxembourg
- numéro d'étain
- luxembourgeois fiscale di Numéro d'identification
- numéro d'identification fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- ID Steier
- Steier identifikatiounsnummer
- Steier Nummer
- ID Steuer
- steueridentifikationsnummer
- steuernummer
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- Zinn #
- Zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Numero di carta di identificazione Malaysia

### <a name="format"></a>Formato

12 cifre contenenti lineette facoltative

### <a name="pattern"></a>Modello

12 cifre:
- sei cifre nel formato AAMMGG, ovvero la data di nascita 
- un trattino (facoltativo) 
- codice posto-di-nascita a due lettere 
- un trattino (facoltativo) 
- tre cifre casuali 
- codice di genere a una cifra

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_malaysia_id_card_number trova contenuti che corrispondono al modello.
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

- scheda dell'applicazione digitale
- i/c
- i/c no
- IC
- IC No
- id card
- Scheda di identificazione
- carta di identità
- k/p
- k/p no
- diri akuan Kad
- Kad Aplikasi digitale
- Kad Pengenalan Malaysia
- KP
- KP No
- MyKad
- MYKAS
- mykid
- mypr
- mytentera
- carta di identità Malaysia
- carta di identità malaysiana
- NRIC
- scheda di identificazione personale

## <a name="malta-drivers-license-number"></a>Numero della patente di guida di Malta

### <a name="format"></a>Formato

Combinazione di due caratteri e di sei cifre nel modello specificato
  
### <a name="pattern"></a>Modello

combinazione di due caratteri e di sei cifre:
  
- due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)
- uno spazio (facoltativo)
- tre cifre
- uno spazio (facoltativo)
- tre cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_malta_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_malta_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver ' s_license_number

- Liċenzja TAS-sewqan
- liċenzji TAS-sewwieq


## <a name="malta-identity-card-number"></a>Numero di carta di identità di Malta
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

sette cifre seguite da una lettera
  
### <a name="pattern"></a>Modello

sette cifre seguite da una lettera:
  
- sette cifre 
- una lettera in "M, G, A, P, L, H, B, Z" (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_malta_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_malta_eu_national_id_card` . 
    
Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- L'espressione regolare  `Regex_malta_eu_national_id_card` trova contenuto che corrisponde al modello. 
    
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

- numero di servizio Citizen
- ID Tat-Taxxa
- identifika numru tal-Biljett
- Kodiċi numerai personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni Tat-Taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru TAS-Servizz taċ-ċittadin
- numru Tat-Taxxa
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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_malta_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_malta_eu_passport_number` viene trovata. 
- Viene trovata una parola chiave `Keywords_eu_passport_date`

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_malta_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_malta_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- NRU tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="malta-tax-identification-number"></a>Numero di identificazione fiscale di Malta

### <a name="format"></a>Formato

Per cittadini maltesi:
- sette cifre e una lettera nel modello specificato
  
Nazionali non maltesi e soggetti maltesi:
- nove cifre
  
### <a name="pattern"></a>Modello

Nazionali maltesi: sette cifre e una lettera
  
- sette cifre 
- una lettera (senza distinzione tra maiuscole e minuscole)
    
Nazionali non maltesi e soggetti maltesi: nove cifre
  
- nove cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La Regex  `Regex_malta_eu_tax_file_number`  o `Regex_malta_eu_tax_file_number_non_maltese_national` trova il contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_malta_eu_tax_file_number` . 
    
Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La Regex  `Regex_malta_eu_tax_file_number` o `Regex_malta_eu_tax_file_number_non_maltese_national` trova il contenuto che corrisponde al modello. 
    
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

- numero di servizio Citizen
- ID Tat-Taxxa
- identifika numru tal-Biljett
- Kodiċi numerai personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni Tat-Taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru TAS-Servizz taċ-ċittadin
- numru Tat-Taxxa
- codice numerico personale
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>Numero di servizio del cittadino (BSN) (Paesi Bassi)

### <a name="format"></a>Formato

otto-nove cifre contenenti spazi facoltativi

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_netherlands_bsn trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_netherlands_bsn.
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
  
- BSN #
- BSN
- burgerservicenummer
- numero di servizio Citizen
- numero persona
- numero personale
- codice numerico personale
- numero relativo alla persona
- persoonlijk Nummer
- codice Numerieke di persoonlijke
- persoonsgebonden
- persoonsnummer
- Sociaal-fiscaal Nummer
- numero di social-Fiscal
- Sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Numero della patente di guida (Paesi Bassi)

### <a name="format"></a>Formato

dieci cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

dieci cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_netherlands_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_netherlands_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver ' s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- Rijbewijs Nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Numero di passaporto per i Paesi Bassi

### <a name="format"></a>Formato

nove lettere o cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

nove lettere o cifre
  
### <a name="checksum"></a>Checksum

non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_netherlands_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_netherlands_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_netherlands_eu_passport_date` trova la data nel formato dd MMM/MMM yyyy (esempio-26 Maa/MAR 2012)

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_netherlands_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_netherlands_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- PASPOORT Nummer
- paspoortnummers
- paspoortnummer
- PASPOORT Nr

## <a name="netherlands-tax-identification-number"></a>Numero di identificazione fiscale per i Paesi Bassi
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

nove cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

nove cifre 
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_netherlands_eu_tax_file_number` . 
    
Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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

- BTW nummer
- identificazione fiscale di Hollânske
- numero ID Impuesto di Hulandes
- identificazione Impuesto di Hulandes
- identificatienummer che dura
- identificatienummer van delasting
- numero di identificazione di Impuesto
- numero Impuesto
- l'ID di Nummer del Nederlands
- Nederlands identificatie di recente
- Nederlands identificatienummer di recente
- Nederlands belastingnummer
- Nederlandse che durerà identificatie
- identificazione fiscale per i Paesi Bassi
- identificazione fiscale per i Paesi Bassi
- Tin olandesi
- stagno degli olandesi
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- identificazione fiscale tal
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- tal fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="netherlands-value-added-tax-number"></a>Paesi Bassi-numero di imposta sul valore aggiunto
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

14 caratteri alfanumerici

### <a name="pattern"></a>Modello

motivo alfanumerico di 14 caratteri:

- N o n
- L o l
- spazio facoltativo, punto o segno meno
- nove cifre
- spazio facoltativo, punto o segno meno
- B o b
- due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_netherlands_value_added_tax_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_netherlands_value_added_tax_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_netherlands_value_added_tax_number trova contenuto corrispondente al modello.

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

- numero di partita IVA
- IVA No
- IVA #
- wearde tafoege Tax Geta
- BTW nûmer
- BTW-nummer


## <a name="new-zealand-bank-account-number"></a>Numero di conto corrente bancario neozelandese
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

modello da 14 a 16 cifre con delimitatore facoltativo

### <a name="pattern"></a>Modello

modello da 14 a 16 cifre con delimitatore facoltativo:

- due cifre
- un trattino o uno spazio facoltativo
- da tre a quattro cifre
- un trattino o uno spazio facoltativo
- sette cifre
- un trattino o uno spazio facoltativo
- da due a tre cifre
- un trattino delle opzioni o uno spazio

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_new_zealand_bank_account_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_new_zealand_bank_account_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_new_zealand_bank_account_number trova contenuto corrispondente al modello.

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


## <a name="new-zealand-drivers-license-number"></a>Numero della patente di guida neozelandese
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

motivo alfanumerico di otto caratteri

### <a name="pattern"></a>Modello

motivo alfanumerico di otto caratteri

- due lettere 
- sei cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_newzealand_driver_license_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_newzealand_driver_license_number.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_newzealand_driver_license_number trova contenuto corrispondente al modello.

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
- LIC del driver
- patente di guida
- licenze per i driver
- driverslic
- driverslicence
- driverslicences
- driver Lic
- driver driver'lics
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's licence
- patenti di guida
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- patenti di guida #
- international driving permit
- international driving permits
- Associazione automobilistica NZ
- Associazione automobilistica neozelandese


## <a name="new-zealand-inland-revenue-number"></a>Numero di ricavo interno della Nuova Zelanda
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

otto o nove cifre con delimitatori opzionali

### <a name="pattern"></a>Modello

otto o nove cifre con delimitatori opzionali

- due o tre cifre
- uno spazio o un trattino facoltativo
- tre cifre
- uno spazio o un trattino facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_new_zealand_inland_revenue_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_new_zealand_inland_revenue_number.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_new_zealand_inland_revenue_number trova contenuto corrispondente al modello.

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

- IRD No.
- IRD No #
- NZ IRD
- Nuova Zelanda IRD
- numero IRD
- numero di ricavo interno


## <a name="new-zealand-ministry-of-health-number"></a>Numero del Ministero della sanità neozelandese

### <a name="format"></a>Formato

tre lettere, uno spazio (facoltativo) e quattro cifre

### <a name="pattern"></a>Modello

- tre lettere (senza distinzione tra maiuscole/minuscole) eccetto ' I ' è O '
- uno spazio (facoltativo) 
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_nz_terms.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Numero dell'indice di integrità nazionale
- numero sanitario
- Nr.
- NHI #
- Indice di integrità nazionale n.
- ID dell'indice di integrità nazionale
- Indice di integrità nazionale #

## <a name="new-zealand-social-welfare-number"></a>Numero di welfare sociale neozelandese

Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre

- tre cifre
- un segno meno facoltativo
- tre cifre
- un segno meno facoltativo
- tre cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_newzealand_social_welfare_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_newzealand_social_welfare_number.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_newzealand_social_welfare_number trova contenuto corrispondente al modello.

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

- previdenza sociale #
- previdenza sociale #
- previdenza sociale No.
- numero di previdenza sociale
- SWN #

   
## <a name="norway-identification-number"></a>Numero di identificazione norvegese

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre:
- sei cifre nel formato GGMMAA, ovvero la data di nascita 
- numero individuale a tre cifre 
- due cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_norway_id_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_norway_id_number.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_norway_id_numbe trova contenuto corrispondente al modello.
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

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Numero di identificazione multifunzione unificato Filippine

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

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_philippines_unified_id trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_philippines_id.

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

## <a name="poland-drivers-license-number"></a>Numero della patente di guida (Polonia)

### <a name="format"></a>Formato

14 cifre contenenti 2 barre
  
### <a name="pattern"></a>Modello

14 cifre e 2 barre:
  
- cinque cifre 
- una barra
- due cifre
- una barra
- sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_poland_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_poland_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver ' s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Carta di identità in Polonia

### <a name="format"></a>Formato

tre lettere e sei cifre

### <a name="pattern"></a>Modello

tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Numero dowodu osobistego
- Nazwa i numeri dowodu osobistego
- Nazwa i Nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. OS.

   
## <a name="poland-national-id-pesel"></a>ID nazionale Polonia (PESEL)

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

- 6 cifre che rappresentano la data di nascita nel formato AAMMGG
- 4 cifre
- 1 cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_pesel_identification_number.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- Dowód osobisty
- dowódosobisty
- numero Niepowtarzalny
- niepowtarzalnynumer
- Nr.-PESEL
- Nr-PESEL
- numero identyfikacyjny
- PESEL
- tożsamości Narodowej

   
## <a name="poland-passport-number"></a>Polonia-numero del passaporto
Questa entità di tipo di informazioni riservate è inclusa nel tipo di informazioni riservate del numero di passaporto dell'Unione europea ed è disponibile come entità di tipo di informazioni riservate stand-alone.

### <a name="format"></a>Formato

due lettere e sette cifre

### <a name="pattern"></a>Modello

Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.
- Il checksum ha esito positivo.

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Numero Paszportu
- Nr. Paszportu
- Paszport

## <a name="poland-regon-number"></a>Polonia numero REGOn
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero di nove cifre o 14 cifre

### <a name="pattern"></a>Modello

numero di nove cifre o 14 cifre:

- nove cifre o 
- nove cifre
- trattino
- cinque cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_polish_regon_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_polish_regon_number.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_polish_regon_number trova contenuto corrispondente al modello.

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

- ID REGON
- numero statistico
- ID statistico
- statistica No
- numero REGON
- regonid #
- regonno #
- ID società
- CompanyID #
- companyidno #
- numero area
- numero REGON
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Polonia-codice fiscale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_poland_eu_tax_file_number` . 
    
  
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

- NIP #
- NIP
- numero Identyfikacji Podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- ID partita IVA #
- ID partita IVA
- IVA No
- numero di partita IVA
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>Portogallo-numero di carta Citizen

### <a name="format"></a>Formato

otto cifre

### <a name="pattern"></a>Modello

otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_portugal_citizen_card trova contenuti che corrispondono al modello.
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

- bilhete de Identidade
- una cartão de Cidadão
- scheda Citizen
- numero del documento
- documento de identificação
- numero ID
- identificazione no
- identification number
- carta di identità No
- numero di carta di identità
- carta d'identità nazionale
- NIC
- número bi de Portugal
- número de identificação Civil
- número de identificação Fiscal
- número do documento
- numero bi Portogallo


## <a name="portugal-drivers-license-number"></a>Portogallo-numero della patente di guida

### <a name="format"></a>Formato

due modelli: due lettere seguite da 5-8 cifre con caratteri speciali
  
### <a name="pattern"></a>Modello

Schema 1: due lettere seguite da 5/6 con caratteri speciali:
- Due lettere (senza distinzione tra maiuscole e minuscole)
- Una lineetta
- Cinque o sei cifre
- Uno spazio
- Una cifra

Schema 2: una lettera seguita da 6/8 cifre con caratteri speciali:
- Una lettera (senza distinzione tra maiuscole e minuscole)
- Una lineetta
- Sei o otto cifre
- Uno spazio
- Una cifra

    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_portugal_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_portugal_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver ' s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- Permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Portogallo-numero di passaporto

### <a name="format"></a>Formato

una lettera seguita da sei cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

una lettera seguita da sei cifre:
  
- una lettera (senza distinzione tra maiuscole e minuscole)
- sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_portugal_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_portugal_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_portugal_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_portugal_eu_passport_number` viene trovata.
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- passaporto portoghese
- Passeport portoghese
- passaporte portoghese
- passaporte n º
- Passeport n º
- números de passaporte
- passaporti portoghesi
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="portugal-tax-identification-number"></a>Portogallo codice di identificazione fiscale

### <a name="format"></a>Formato

nove cifre con spazi facoltativi
  
### <a name="pattern"></a>Modello

- 3 cifre
- uno spazio facoltativo
- 3 cifre
- uno spazio facoltativo
- 3 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_portugal_eu_tax_file_number` . 
    
Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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

- CPF #
- CPF
- NIF #
- NIF
- número de identificação Fisca
- numero fiscale
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="romania-drivers-license-number"></a>Numero della patente di guida Romania

### <a name="format"></a>Formato

un carattere seguito da otto cifre
  
### <a name="pattern"></a>Modello

un carattere seguito da otto cifre:
- una lettera (senza distinzione tra maiuscole e minuscole) o cifra 
- otto cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_romania_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_romania_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver ' s_license_number

- Permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- Permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>Codice numerico personale Romania (CNP)
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

13 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

- 1 cifra da 1-9
- 6 cifre che rappresentano la data di nascita (AAMMGG)
- 2 cifre che possono essere 01-52 o 99
- 4 cifre

### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_romania_eu_national_id_card` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- CNP #
- CNP
- Cod identificare Personal
- Cod numerico personale
- Cod Unic identificare
- codnumericpersonal #
- Nr fiscale codul.
- identificarea fiscală Nr #
- ID-ul taxei
- numero assicurativo
- insurancenumber #
- ID nazionale #
- national id
- national identification number
- Număr identificare Personal
- număr identitate
- Număr personale Unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- codice numerico personale
- pin #
- pin
- Tax File No
- tax file number
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #
- numero di identificazione univoco
- numero di identità univoco
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Numero di passaporto Romania

### <a name="format"></a>Formato

otto o nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

otto o nove cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_romania_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_romania_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_romania_eu_passport_date` trova la data nel formato dd MMM/MMM AA (esempio-01 feb/feb 10) oppure viene trovata una parola chiave `Keywords_eu_passport_date`

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_romania_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_romania_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numarul pașaportului numărul pasaportului numerele pașaportului Pașaport Nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="russia-passport-number-domestic"></a>Numero di passaporto russo nazionale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero di dieci cifre

### <a name="pattern"></a>Modello

numero di dieci cifre:

- due cifre
- uno spazio o un trattino facoltativo
- due cifre
- uno spazio facoltativo
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La Regex_Russian_Passport_Number_Domestic Regex trova contenuto che corrisponde al modello.
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
- Passport No
- passaporto #
- ID passaporto
- passportno #
- passportnumber #
- паспорт нет
- ID паспорт
- pоссийской паспорт
- Pусский Номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Numero di passaporto russo International
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero di nove cifre

### <a name="pattern"></a>Modello

numero di nove cifre:

- due cifre
- uno spazio o un trattino facoltativo
- sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La Regex_Russian_Passport_Number_International Regex trova contenuto che corrisponde al modello.
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
- Passport No
- passaporto #
- ID passaporto
- passportno #
- passportnumber #
- паспорт нет
- ID паспорт
- pоссийской паспорт
- Pусский Номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Arabia Saudita - Identificativo nazionale

### <a name="format"></a>Formato

dieci cifre

### <a name="pattern"></a>Modello

dieci cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Numero di carta di identità di registrazione nazionale (NRIC) (Singapore)

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_singapore_nric trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_singapore_nric.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_singapore_nric trova contenuti che corrispondono al modello.
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

## <a name="slovakia-drivers-license-number"></a>Slovacchia-numero della patente di guida

### <a name="format"></a>Formato

un carattere seguito da sette cifre
  
### <a name="pattern"></a>Modello

un carattere seguito da sette cifre
  
- una lettera (senza distinzione tra maiuscole e minuscole) o cifra
- sette cifre 
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_slovakia_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_slovakia_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver ' s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Slovacchia-numero personale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

nove o dieci cifre che contengono una barra rovesciata facoltativa
  
### <a name="pattern"></a>Modello

- 6 cifre che rappresentano la data di nascita
- barra facoltativa (/)
- 3 cifre
- 1 cifra di controllo facoltativa
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_slovakia_eu_national_id_card` . 
    
Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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
- číslo Národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- numero ID
- identificazione no
- identification number
- identifikačná Karta č
- identifikačné číslo
- carta di identità No
- numero di carta di identità
- Národná identifikačná značka č
- numero nazionale
- nationalnumber #
- Nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- SSN #
- SSN
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- Tax File No
- tax file number
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #

## <a name="slovakia-passport-number"></a>Slovacchia-numero di passaporto

### <a name="format"></a>Formato

una cifra o una lettera seguita da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_slovakia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_slovakia_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_slovakia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_slovakia_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo Pasu
- čísla pasov
- pas č.
- Passeport n °
- n ° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="slovenia-drivers-license-number"></a>Numero della patente di guida sloveno

### <a name="format"></a>Formato

nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

nove cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_slovenia_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_slovenia_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver ' s_license_number

- vozniško dovoljenje
- licenza di številka vozniška
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Slovenia numero di cittadini Master Unique
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre nel modello specificato:
  
- sette cifre che corrispondono alla data di nascita (DDMMLLL), dove "LLL" corrisponde alle ultime tre cifre dell'anno di nascita 
- due cifre che corrispondono all'area di nascita "50"
- tre cifre che corrispondono a una combinazione di genere e numero di serie per le persone nate nello stesso giorno (000-499 per il maschio e 500-999 per le femmine)
- una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_slovenia_eu_national_id_card` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- ID Nacionalna
- elenco potni di Nacionalni
- national id
- osebna izkaznica
- osebni Koda
- osebni ne
- osebni številka
- codice personale
- numero personale
- codice numerico personale
- številka državljana
- numero di cittadino univoco
- numero ID univoco
- numero di identità univoco
- numero di cittadino Master univoco
- numero di registrazione univoco
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Slovenia-numero di passaporto

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_slovenia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_slovenia_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_eu_passport_date1` trova la data nel formato dd. mm. yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_slovenia_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_slovenia_eu_passport_number` viene trovata. 
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- Potek veljavnosti
- elenco potni #
- rojstva Datum
- elenco potni
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="slovenia-tax-identification-number"></a>Slovenia-numero di identificazione fiscale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

otto cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

- una cifra da 1-9
- sei cifre
- una cifra di controllo
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_slovenia_eu_tax_file_number` . 
    
Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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
- Tax File No
- tax file number
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="south-africa-identification-number"></a>Numero di identificazione Sud Africa

### <a name="format"></a>Formato

13 cifre che possono contenere spazi

### <a name="pattern"></a>Modello

13 cifre:
- sei cifre nel formato AAMMGG, ovvero la data di nascita 
- quattro cifre 
- un indicatore di cittadinanza a una cifra 
- la cifra "8" o "9" 
- una cifra che corrisponde a una cifra di checksum

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_south_africa_identification_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_south_africa_identification_number.
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
   
## <a name="south-korea-resident-registration-number"></a>Numero di registrazione residente in Corea del sud

### <a name="format"></a>Formato

13 cifre contenenti un segno meno

### <a name="pattern"></a>Modello

13 cifre:
- sei cifre nel formato AAMMGG, ovvero la data di nascita 
- un trattino 
- una cifra determinata dal secolo e dal sesso 
- codice regione-di-nascita a quattro cifre 
- una cifra utilizzata per distinguere gli utenti per i quali i numeri precedenti sono identici 
- una cifra di controllo.

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_south_korea_resident_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_south_korea_resident_number.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_south_korea_resident_number trova contenuto corrispondente al modello.
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

## <a name="spain-drivers-license-number"></a>Spagna-numero della patente di guida

### <a name="format"></a>Formato

otto cifre seguite da un carattere
  
### <a name="pattern"></a>Modello

otto cifre seguite da un carattere:
  
- otto cifre 
- una cifra o una lettera (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` trova il contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_spain_eu_driver's_license_number` viene trovata. 

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` trova il contenuto che corrisponde al modello. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver ' s_license_number

- Permiso de conducción
- Permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- Permiso de conducir
- permisos de conducir
- permisos conducir
- carnet conducir
- Carnet de conducir
- licencia de manejo
- licencia Manejo

## <a name="spain-dni"></a>DNI Spagna
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` trova il contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_spain_eu_national_id_card"` . 

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` trova il contenuto che corrisponde al modello. 

    
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

- Carné de Identidad
- DNI #
- DNI
- dninúmero #
- documento Nacional de Identidad
- Identidad único
- identidadúnico #
- numero assicurativo
- national identification number
- identità nazionale
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número Nacional Identidad
- numero di identificazione personale
- identità personale No
- numero di identità univoco
- UniqueId #

## <a name="spain-passport-number"></a>Spagna-numero di passaporto

### <a name="format"></a>Formato

combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

combinazione di lettere e numeri di otto o nove caratteri:
  
- due cifre o lettere 
- una cifra o una lettera (facoltativa)
- sei cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_spain_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_spain_eu_passport_number` viene trovata. 
- L'espressione regolare `Regex_spain_eu_passport_date` trova la data nel formato dd-mm-yyyy o una parola chiave from `Keywords_eu_passport_date` si trova

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_spain_eu_passport_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_passport_number` o `Keywords_spain_eu_passport_number` viene trovata.
    
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

- passaporto #
- passaporto #
- passportid
- passaporti
- passportno
- Passport No
- passportnumber
- passport number
- passportnumbers
- numeri di passaporto

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- pasaporte España
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte No
- Passeport n °
- n ° Passeport
- pasaporte No.
- pasaporte n °
- passaporto della Spagna

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Data di emissione
- Data di scadenza


## <a name="spain-social-security-number-ssn"></a>Spagna-codice di previdenza sociale (SSN)

### <a name="format"></a>Formato

11-12 cifre

### <a name="pattern"></a>Modello

11-12 cifre:
- due cifre 
- una barra (facoltativa) 
- da sette a otto cifre 
- una barra (facoltativa) 
- due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

Nessuno

## <a name="spain-tax-identification-number"></a>Spagna-codice fiscale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

sette o otto cifre e una o due lettere nel modello specificato
  
### <a name="pattern"></a>Modello

Persone fisiche spagnole con carta d'identità nazionale spagnola:
  
- otto cifre 
- una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
Spagnoli non residenti senza una carta d'identità nazionale spagnola
  
- una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)
- sette cifre
- una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:
  
- una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)
- sette cifre 
- una lettera maiuscola (con distinzione tra maiuscole e minuscole)
    
Stranieri con il numero di identificazione di un forestiero
  
- una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole) 
- sette cifre
- una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
Stranieri senza il numero di identificazione di un forestiero
  
- una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole) 
- sette cifre
- una lettera maiuscola (con distinzione tra maiuscole e minuscole) 
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_tax_file_number` o `Func_spain_eu_DL_and_NI_number_citizen` trova il contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_spain_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_spain_eu_tax_file_number` o `Func_spain_eu_DL_and_NI_number_citizen` trova il contenuto che corrisponde al modello. 
    
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

- CIF
- cifid #
- cifnúmero #
- número de contribuyente
- número de Identificación Fiscal
- número de Impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- Tax File No
- tax file number
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="sql-server-connection-string"></a>Stringa di connessione di SQL Server

### <a name="format"></a>Formato

Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.

### <a name="pattern"></a>Modello

- stringa "ID utente", "ID utente", "UID" o "UserId"
- qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- la stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola
- segno di uguale (=)
- qualsiasi carattere che non sia un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), il simbolo (@), le virgolette ("), il punto e virgola (;), parentesi graffa sinistra ([) o parentesi quadra sinistra ({)
- qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")
- un punto e virgola (;) o virgolette (")

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare CEP_Regex_SQLServerConnectionString trova contenuti che corrispondono al modello.
- **Non** viene trovata una parola chiave da CEP_GlobalFilter.
- L'espressione regolare CEP_PasswordPlaceHolder **non** trova il contenuto corrispondente al modello.
- L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.

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

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- Password o pwd seguito da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (*)-----------------
- Password o pwd seguito da:
    - Segno di uguale (=)
    - Meno di simbolo (<)
    - Qualsiasi combinazione di 1-200 caratteri che sono lettere maiuscole o minuscole, cifre, asterisco (*), segno meno (-), sottolineatura (_) o carattere dello spazio vuoto
    - Valore maggiore di Symbol (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- contoso
- Fabrikam
- Northwind
- sandbox
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="sweden-drivers-license-number"></a>Svezia-numero della patente di guida

### <a name="format"></a>Formato

dieci cifre contenenti un segno meno
  
### <a name="pattern"></a>Modello

dieci cifre contenenti un trattino:
  
- sei cifre 
- un trattino
- quattro cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare  `Regex_sweden_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
- Una parola chiave da  `Keywords_eu_driver's_license_number` o `Keywords_sweden_eu_driver's_license_number` viene trovata. 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- LIC del driver
- driver driver'lics
- driver license
- driver licenses
- patente di guida
- licenze per i driver
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- driver Lic
- driver driver'lics
- drivers license
- drivers licenses
- drivers licence
- licenze per i conducenti
- driver'lic
- driver ' LiCS
- driver ' License
- driver ' licenses
- driver'licence
- driver'licences
- LIC del driver
- driver ' driver'lics
- patente di guida
- licenze per i driver
- patente di guida
- patenti del conducente
- driver'slic
- driver'slics
- secondola
- driver'slicenses
- driver'slicence
- driver'slicences
- LIC del conducente
- driver'lics del conducente
- driver's license
- driver's licenses
- driver's licence
- patenti di guida
- DL #
- DLS #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- LIC del driver #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- licenze per i driver #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- driver Lic #
- driver driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- licenze per i conducenti #
- driver'lic #
- driver ' LiCS #
- driver ' License #
- driver ' licenses #
- driver'licence #
- driver'licences #
- LIC del driver #
- driver ' driver'lics #
- patente di guida #
- licenze per i driver #
- patente di guida #
- patenti del conducente #
- driver'slic #
- driver'slics #
- secondola #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- LIC del conducente #
- driver'lics del conducente #
- patente di guida #
- licenze del conducente #
- patente di guida #
- patenti di guida #
- driving licence 
- driving license
- dlno #
- driv Lic
- driv licen
- licenza di driv
- licenze di driv
- licenza driv
- licenze di driv
- driver licen
- driver licen
- licei del conducente
- Guida di Lic
- Guida licen
- patenti di guida
- driving licence
- driving licences
- permesso di guida
- DL No
- dlno
- numero DL


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver ' s_license_number

- ajokortti
- Permis de conducere
- numero ajokortin
- kuljettajat Lic.
- driver Lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare Lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Svezia-ID nazionale

### <a name="format"></a>Formato

dieci o 12 cifre e un delimitatore facoltativo

### <a name="pattern"></a>Modello

dieci o 12 cifre e un delimitatore facoltativo:
- due cifre (facoltativa) 
- Sei cifre nel formato data AAMMGG 
- delimitatore di "-" o "+" (facoltativo)
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione `Func_swedish_national_identifier` trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave `Keywords_swedish_national_identifier`
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- ID No
- numero ID
- ID #
- identificazione no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- documento di identità
- identità No
- numero di identità
- ID-Nummer
- ID personale
- personnummer #
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>Svezia-numero del passaporto
Questa entità di tipo di informazioni riservate è inclusa nel tipo di informazioni riservate del numero di passaporto dell'Unione europea ed è disponibile come entità di tipo di informazioni riservate stand-alone.

### <a name="format"></a>Formato

otto cifre

### <a name="pattern"></a>Modello

otto cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- l'espressione regolare Regex_sweden_passport_number trova contenuti che corrispondono al modello.
- si verifica una delle condizioni seguenti:
    - viene trovata una parola chiave da Keyword_passport.
    - viene trovata una parola chiave da Keyword_sweden_passport.

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Passaporto # 
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


## <a name="sweden-tax-identification-number"></a>Svezia-codice fiscale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

dieci cifre e un simbolo nel modello specificato
  
### <a name="pattern"></a>Modello

dieci cifre e un simbolo:
  
- sei cifre che corrispondono alla data di nascita (AAMMGG) 
- un segno di addizione o segno meno
- tre cifre che rendono il numero di identificazione univoco dove: 
  - per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati
  - la cifra nella nona posizione indica il sesso per il maschio o per la femmina.
- una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_sweden_eu_tax_file_number` . 
    
Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

- numero ID personale
- personnummer
- ID pattinat Nummer
- Identifikation skatet
- skattebetalarens identifikationsnummer
- Tin Sverige
- file fiscale
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- codice fiscale
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #


## <a name="swift-code"></a>Codice SWIFT

### <a name="format"></a>Formato

quattro lettere seguite da 5-31 lettere o cifre

### <a name="pattern"></a>Modello

quattro lettere seguite da 5-31 lettere o cifre:
- codice bancario di quattro lettere (senza distinzione tra maiuscole e minuscole) 
- uno spazio facoltativo 
- 4-28 lettere o cifre (BBAN) 
- uno spazio facoltativo 
- una o tre lettere o cifre (parte restante del BBAN)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- BIC #
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
- コード SWIFT
- 番号 SWIFT
- BIC 番号
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Svizzera SSN numero dell'AVS
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

numero di 13 cifre

### <a name="pattern"></a>Modello

numero 13 cifre:

- tre cifre-756
- un punto facoltativo
- quattro cifre
- un punto facoltativo
- quattro cifre
- un punto facoltativo
- due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_swiss_social_security_number_ahv trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keywords_swiss_social_security_number_ahv.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_swiss_social_security_number_ahv trova contenuto corrispondente al modello.

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

- AVS
- SSN
- PID
- numero assicurativo
- personalidno #
- social security number
- numero ID personale
- identificazione personale No.
- insuranceno #
- uniqueidno #
- identificazione univoca No.
- numero AVS
- identità personale no Versicherungsnummer
- identifikationsnummer
- einzigartige Identität nicht
- sozialversicherungsnummer
- ID personnelle di identificazione
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Numero di identificazione nazionale di Taiwan

### <a name="format"></a>Formato

una lettera (in lingua inglese) seguita da nove cifre

### <a name="pattern"></a>Modello

una lettera (in lingua inglese) seguita da nove cifre:
- una lettera (in inglese, senza distinzione tra maiuscole e minuscole) 
- la cifra "1" o "2" 
- otto cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_taiwanese_national_id.
- Il checksum ha esito positivo.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
   
## <a name="taiwan-passport-number"></a>Taiwan-numero di passaporto

### <a name="format"></a>Formato

- numero di passaporto biometrico: nove cifre
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

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_taiwan_passport trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_taiwan_passport.

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
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Numero di certificato residente taiwanese (ARC/TARC Tax)

### <a name="format"></a>Formato

dieci lettere e cifre

### <a name="pattern"></a>Modello

dieci lettere e cifre:
- due lettere (senza distinzione tra maiuscole e minuscole) 
- otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- L'espressione regolare Regex_taiwan_resident_certificate trova contenuti che corrispondono al modello.
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
- TARC Tax 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>Codice di identificazione della popolazione tailandese

### <a name="format"></a>Formato

13 cifre

### <a name="pattern"></a>Modello

13 cifre:
- la prima cifra non è pari a zero o nove 
- 12 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_Thai_Citizen_Id trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_Thai_Citizen_Id trova contenuto corrispondente al modello.

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

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_Turkish_National_Id trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_Turkish_National_Id.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_Turkish_National_Id trova contenuto corrispondente al modello.

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
- Numarası Kimlik TC
- Vatandaşlık numarası
- Vatandaşlık No

## <a name="uk-drivers-license-number"></a>U.K. numero della patente di guida
Questa entità di tipo di informazioni riservate è inclusa nel tipo di informazioni riservate del conducente dell'Unione europea ed è disponibile come entità di tipo di informazioni riservate stand-alone.

### <a name="format"></a>Formato

Combinazione di 18 lettere e numeri nel formato specificato

### <a name="pattern"></a>Modello

18 lettere e cifre:
- cinque lettere (senza distinzione tra maiuscole/minuscole) o la cifra "9" al posto di una lettera 
- una cifra 
- cinque cifre nel formato data MMDDY per data di nascita (il settimo carattere viene incrementato di 50 se il driver è di tipo femminile, ovvero 51 a 62 invece di 01 a 12)
- due lettere (senza distinzione tra maiuscole/minuscole) o la cifra "9" al posto di una lettera 
- cinque cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_uk_drivers_license.
- Il checksum ha esito positivo.

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quadbikes 
- motor cars 
- 125cc 
- sidecar 
- tricicli 
- moto 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>U.K. numero di registrazione elettorale

### <a name="format"></a>Formato

due lettere seguite da 1-4 cifre

### <a name="pattern"></a>Modello

due lettere (senza distinzione tra maiuscole/minuscole) seguite da 1-4 numeri

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

   
## <a name="uk-national-health-service-number"></a>U.K. numero del servizio sanitario nazionale

### <a name="format"></a>Formato

10-17 cifre separate da spazi

### <a name="pattern"></a>Modello

10-17 cifre:
- tre o dieci cifre 
- uno spazio 
- tre cifre 
- uno spazio 
- quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- NHS 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB 
- D. O. B 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>U.K. numero di assicurazione nazionale (NINO)
Questa entità di tipo di informazioni riservate è inclusa nel tipo di informazioni riservate del numero di Identificaiton nazionale dell'Unione europea ed è disponibile come entità di tipo di informazioni riservate stand-alone.

### <a name="format"></a>Formato

sette caratteri o nove caratteri separati da spazi o trattini

### <a name="pattern"></a>Modello

due modelli possibili:

- due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)
- sei cifre
- ' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)

OPPURE

- due lettere
- uno spazio o un trattino
- due cifre
- uno spazio o un trattino
- due cifre
- uno spazio o un trattino
- due cifre
- uno spazio o un trattino
- ' A ',' B ',' c'o ' d'

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_uk_nino.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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
- Insurance
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- Numero NI
- NI No.
- NI #
- NI #
- Insurance #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>U.K. Numero di riferimento del contribuente univoco
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori
 
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione  `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello. 
- Viene trovata una parola chiave from  `Keywords_uk_eu_tax_file_number` . 
    
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

- codice fiscale
- file fiscale
- tax id
- identificazione fiscale No
- codice di identificazione fiscale
- tax no #
- tax no
- numero di registrazione fiscale
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID Tin
- Tin No
- latta #

## <a name="us-bank-account-number"></a>Numero di conto corrente bancario degli Stati Uniti

### <a name="format"></a>Formato

6-17 cifre

### <a name="pattern"></a>Modello

6-17 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
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

## <a name="us-drivers-license-number"></a>Numero della patente di guida statunitense

### <a name="format"></a>Formato

Varia in base allo stato

### <a name="pattern"></a>Modello

dipende dallo stato, ad esempio New York:
- nove cifre formattate come ddd ddd ddd corrisponderanno.
- nove cifre come ddddddddd non corrispondono.

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.
- Viene trovata una parola chiave da Keyword_us_drivers_license.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
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
- DRIVER'LIC 
- DRIVER'LIC # 

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
- Driver ' LiCS 
- Driver ' License 
- Driver ' licenses 
- Driver'Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- Driver'sLic 
- Driver'sLics 
- Secondola 
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
- Driver ' LiCS # 
- Driver ' License # 
- Driver ' licenses # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver'sLic # 
- Driver'sLics # 
- Secondola # 
- Driver'sLicenses # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- abbreviazione dello stato (ad esempio, "NY") 
- nome dello stato (ad esempio, "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Numero di identificazione individuale del contribuente statunitense (it)

### <a name="format"></a>Formato

nove cifre che iniziano con un "9" e contengono "7" o "8" come quarta cifra, formattata facoltativamente con spazi o trattini

### <a name="pattern"></a>Modello

formattato
- la cifra "9" 
- due cifre 
- uno spazio o un trattino 
- a "7" o "8" 
- una cifra 
- uno spazio o un trattino 
- quattro cifre

formattato
- la cifra "9" 
- due cifre 
- a "7" o "8" 
- cinque cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_itin.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_itin.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_formatted_itin o Func_unformatted_itin trova contenuto corrispondente al modello.

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
- Itin 
- i.t.i.n.
- SSN 
- latta 
- social security 
- tax payer 
- itins 
- taxid 
- individual taxpayer 


## <a name="us-social-security-number-ssn"></a>Codice di previdenza sociale degli Stati Uniti (SSN)

### <a name="format"></a>Formato

nove cifre, che possono trovarsi in un modello formattato o non formattato

> [!NOTE]
> Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).

### <a name="pattern"></a>Modello

quattro funzioni cercano SNSS in quattro modelli diversi:
- Func_ssn trova SNSS con una formattazione complessa pre2011 formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)
- Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)
- Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)
- Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)

### <a name="checksum"></a>Checksum

No


### <a name="definition"></a>Definizione

Un criterio DLP è estremamente sicuro che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_ssn restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_unformatted_ssn trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP ha poca fiducia che ha rilevato questo tipo di informazioni riservate se, entro 300 caratteri:
- La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:
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

- Numero SSA
- social security number
- previdenza sociale #
- previdenza sociale #
- previdenza sociale No
- Social Security#
- Soc Sec
- SSN
- SNSS
- SSN #
- SS #
- SSID
   
## <a name="us--uk-passport-number"></a>STATI UNITI/REGNO UNITO passport number
Regno Unito numero di passaporto le informazioni riservate entità sono disponibili nel tipo di informazioni riservate del numero di passaporto dell'Unione europea e sono disponibili come entità di tipo di informazioni riservate stand-alone.

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_passport.

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Passaporto # 
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

## <a name="ukraine-passport-domestic"></a>Passaporto ucraino nazionale
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

nove cifre

### <a name="pattern"></a>Modello

nove cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La Regex_Ukraine_Passport_Domestic Regex trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_Ukraine_Passport_Domestic.

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

- passaporto ucraino
- passport number
- Passport No
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Ukraine Passport International
Questo tipo di informazioni riservate è disponibile solo per l'utilizzo in:
- criteri di prevenzione della perdita di dati
- criteri di conformità della comunicazione
- governance delle informazioni
- gestione dei record
- Sicurezza delle app di Microsoft Cloud

### <a name="format"></a>Formato

motivo alfanumerico di otto caratteri

### <a name="pattern"></a>Modello

motivo alfanumerico di otto caratteri:
- due lettere o cifre
- sei cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una sicurezza media che ha rilevato questo tipo di informazioni riservate se, in prossimità di 300 caratteri:
- La Regex_Ukraine_Passport_International Regex trova contenuto che corrisponde al modello.
- Viene trovata una parola chiave da Keyword_Ukraine_Passport_International.

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

- passaporto ucraino
- passport number
- Passport No
- паспорт України
- номер паспорта