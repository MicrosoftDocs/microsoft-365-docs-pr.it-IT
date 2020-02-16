---
title: Tipi di informazioni riservate disponibili da cercare
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
description: La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include 80 tipi di informazioni riservate pronte per l'uso nei criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.
ms.openlocfilehash: 517ff6ae711d61b783e837aebeeb991dfaa53daa
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084335"
---
# <a name="what-the-sensitive-information-types-look-for"></a>Tipi di informazioni riservate disponibili da cercare

La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni. Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione. Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate. In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.
  
## <a name="aba-routing-number"></a>Numero di registrazione ABA

### <a name="format"></a>Formato

9 cifre formattate o meno

### <a name="pattern"></a>Modello

Formattato
- Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8
- Una lineetta
- Quattro cifre
- Una lineetta
- Una cifra

Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8 

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ABA_Routing.

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>Parole chiave

#### <a name="keyword_aba_routing"></a>Keyword_ABA_Routing

- ABA
- aba #
- aba routing #
- aba routing number
- ABA #
- abarouting #
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bank routing number
- bankrouting #
- bankroutingnumber
- routing transit number
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>Argentina - Numero di identità nazionale (DNI)

### <a name="format"></a>Formato

Otto cifre separate da spazi

### <a name="pattern"></a>Modello

Otto cifre
- Due cifre
- Un punto 
- Tre cifre
- Un punto 
- Tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
- Identità 
- Carta di identità nazionale di identificazione 
- DNI 
- Registro nazionale delle persone di NIC 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>Australia - Numero di conto bancario

### <a name="format"></a>Formato

6-10 cifre con o senza un numero BSB (Bank/State/Branch)

### <a name="pattern"></a>Modello

Il numero di conto comprende 6-10 cifre.
Numero BSB australiano:
- Tre cifre 
- Una lineetta 
- Tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_australia_bank_account_number.
- L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

   
## <a name="australia-drivers-license-number"></a>Australia - Numero della patente di guida

### <a name="format"></a>Formato

Nove lettere e numeri

### <a name="pattern"></a>Modello

Nove lettere e numeri: 

- Due cifre o lettere (senza distinzione tra maiuscole/minuscole) 
- Due cifre 
- Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)

OPPURE

- 1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole) 
- 4-9 cifre

OPPURE

- Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="australia-medical-account-number"></a>Australia - Numero di tessera sanitaria

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:
- La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
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

   
## <a name="australia-passport-number"></a>Australia - Numero di passaporto

### <a name="format"></a>Formato

Una lettera seguita da sette cifre

### <a name="pattern"></a>Modello

Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="australia-tax-file-number"></a>Australia - Identificativo fiscale

### <a name="format"></a>Formato

8-9 cifre

### <a name="pattern"></a>Modello

8-9 cifre in genere presentate con spazi, come mostrato di seguito:
- Tre cifre 
- Uno spazio facoltativo 
- Tre cifre 
- Uno spazio facoltativo 
- 2-3 cifre e l'ultima è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.
- Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.
- Il checksum ha esito positivo.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_australia_tax_file_number"></a>Keyword_Australia_Tax_File_Number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number

#### <a name="keyword_number_exclusions"></a>Keyword_number_exclusions

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

- La stringa "Server", "Server" o "Data Source"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "cloudapp. Azure.<!--no-hyperlink-->com "," cloudapp. Azure.<!--no-hyperlink-->NET "o" database. Windows.<!--no-hyperlink-->NET
- Qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "password", "password" o "pwd"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')
- Un punto e virgola (;), virgolette (") o apostrofo (')

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

## <a name="azure-iot-connection-string"></a>Stringa di connessione di Azure.

### <a name="format"></a>Formato

La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices.<!--no-hyperlink-->NET "e" SharedAccessKey ".

### <a name="pattern"></a>Modello

- La stringa "HostName"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "Azure-Devices.<!--no-hyperlink-->NET
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "SharedAccessKey"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)
- Segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

## <a name="azure-publish-setting-password"></a>Password per l'impostazione di pubblicazione di Azure

### <a name="format"></a>Formato

La stringa "UserPwd =" seguita da una stringa alfanumerica.

### <a name="pattern"></a>Modello

- La stringa "UserPwd ="
- Qualsiasi combinazione di lettere o cifre minuscole di 60
- Virgolette (")

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

## <a name="azure-redis-cache-connection-string"></a>Stringa di connessione della cache di Azure Redis

### <a name="format"></a>Formato

La stringa "Redis. cache. Windows.<!--no-hyperlink-->NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".

### <a name="pattern"></a>Modello

- La stringa "Redis. cache. Windows.<!--no-hyperlink-->NET
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "password" o "pwd"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- Segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

## <a name="azure-sas"></a>SAS di Azure

### <a name="format"></a>Formato

La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.

### <a name="pattern"></a>Modello

- La stringa "sig"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)
- La stringa "% 3D"
- Qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

- La stringa "EndPoint"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "ServiceBus. Windows.<!--no-hyperlink-->NET
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "SharedAccessKey"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- Segno di uguale (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

## <a name="azure-storage-account-key"></a>Chiave dell'account di archiviazione di Azure

### <a name="format"></a>Formato

La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".

### <a name="pattern"></a>Modello

- La stringa "DefaultEndpointsProtocol"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "AccountKey"
- 0-2 caratteri dello spazio vuoto
- Segno di uguale (=)
- 0-2 caratteri dello spazio vuoto
- Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- Due segni uguali (=)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

#### <a name="cep_azureemulatorstorageaccountfilter"></a>CEP_AzureEmulatorStorageAccountFilter

Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

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

## <a name="azure-storage-account-key-generic"></a>Chiave dell'account di archiviazione di Azure (generico)

### <a name="format"></a>Formato

Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.

### <a name="pattern"></a>Modello

- 0-1 del simbolo maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)
- Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)
- Due segni uguali (=)


### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova contenuti che corrispondono al modello.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a>Belgio - Numero nazionale

### <a name="format"></a>Formato

11 cifre più delimitatori

### <a name="pattern"></a>Modello

11 cifre più delimitatori:
- Sei cifre e due punti nel formato AA.MM.GG per data di nascita  
- Una lineetta 
- Tre cifre sequenziali (dispari sia per uomini che per donne)  
- Un punto 
- Due cifre, ovvero una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_belgium_national_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_belgium_national_number.
- Il checksum ha esito positivo.

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- Identità
- Registrazione
- Identificazione 
- ID 
- Identiteitskaart
- Registratie nummer 
- Identificatie nummer 
- Identiteit
- Registratie
- Identificatie 
- Carte d’identité 
- numéro d'immatriculation
- numéro d'identification
- identité 
- iscrizione 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## <a name="brazil-cpf-number"></a>Numero CPF Brasile

### <a name="format"></a>Formato

11 cifre che includono una cifra di controllo e possono essere formattate o non formattate

### <a name="pattern"></a>Modello

Formattato
- Tre cifre 
- Un punto  
- Tre cifre 
- Un punto  
- Tre cifre 
- Una lineetta 
- Due cifre, ovvero le cifre di controllo

Formattato
- 11 cifre dove le ultime due sono cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_brazil_cpf trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_brazil_cpf.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="brazil-legal-entity-number-cnpj"></a>Brasile - Codice fiscale persone giuridiche (CNPJ)

### <a name="format"></a>Formato

14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori

### <a name="pattern"></a>Modello
14 cifre più delimitatori:
- Due cifre 
- Un punto  
- Tre cifre 
- Un punto  
- Tre cifre (le prime otto sono il numero di registrazione)  
- Una barra 
- Numero del ramo a quattro cifre  
- Una lineetta 
- Due cifre, ovvero le cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_brazil_cnpj trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_brazil_cnpj.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
- Piccole e medie imprese 
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
   
## <a name="brazil-national-id-card-rg"></a>	Carta d'identità (Brasile) (RG)

### <a name="format"></a>Formato

Registro Geral (formato precedente): nove cifre

Registro de Identidade (RIC) (nuovo formato): 11 cifre

### <a name="pattern"></a>Modello

Registro Geral (formato precedente):
- Due cifre 
- Un punto  
- Tre cifre 
- Un punto  
- Tre cifre 
- Una lineetta 
- Una cifra, ovvero una cifra di controllo

Registro de Identidade (RIC) (nuovo formato):
- 10 cifre 
- Una lineetta 
- Una cifra, ovvero una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_brazil_rg trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_brazil_rg.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole) 
   
## <a name="canada-bank-account-number"></a>Canada - Numero di conto bancario

### <a name="format"></a>Formato

7 o 12 cifre

### <a name="pattern"></a>Modello

Un numero di conto corrente canadese comprende 7 o 12 cifre.

Un numero di transito bancario canadese comprende:
- Cinque cifre 
- Una lineetta 
- Tre cifre o
- Uno zero "0" 
- Otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_canada_bank_account_number.
- L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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
   
## <a name="canada-drivers-license-number"></a>Canada - Numero della patente di guida

### <a name="format"></a>Formato

Varia in base alla provincia

### <a name="pattern"></a>Modello

Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="canada-health-service-number"></a>Canada - Codice del servizio sanitario

### <a name="format"></a>Formato

10 cifre

### <a name="pattern"></a>Modello

10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
      
## <a name="canada-passport-number"></a>Canada - Numero di passaporto

### <a name="format"></a>Formato

Due lettere maiuscole seguite da 6 cifre

### <a name="pattern"></a>Modello

Due lettere maiuscole seguite da 6 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="canada-personal-health-identification-number-phin"></a>Canada - Numero di identificazione sanitaria personale (PHIN)

### <a name="format"></a>Formato

9 cifre

### <a name="pattern"></a>Modello

9 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto corrispondente al modello.
Sono state trovate almeno due parole chiave provenienti da Keyword_canada_phin o Keyword_canada_provinces..

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
   
## <a name="canada-social-insurance-number"></a>Canada - Numero di assicurazione sociale

### <a name="format"></a>Formato

9 cifre con spazi o lineette facoltativi

### <a name="pattern"></a>Modello

Formattato
- Tre cifre 
- Una lineetta o uno spazio 
- Tre cifre 
- Una lineetta o uno spazio 
- Tre cifre

Non formattato: nove cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.
- Almeno due delle seguenti combinazioni:
    - Viene trovata una parola chiave da Keyword_sin.
    - Viene trovata una parola chiave da Keyword_sin_collaborative.
    - La funzione Func_eu_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="chile-identity-card-number"></a>	Cile - Numero di carta di identità

### <a name="format"></a>Formato

7-8 cifre più delimitatori una cifra di controllo o una lettera

### <a name="pattern"></a>Modello

7-8 cifre più delimitatori:
- 1-2 cifre 
- Un punto  
- Tre cifre 
- Un punto  
- Tre cifre 
- Un trattino 
- Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_chile_id_card trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_chile_id_card.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

- Numero di carta d’identità 
- Carta di identità 
- ID 
- Identificazione 
- Rol Único Nacional 
- Correre 
- Rol Único Tributario 
- CARREGGIATA 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## <a name="china-resident-identity-card-prc-number"></a>	Numero carta di identità per residenti in Cina (RPC)

### <a name="format"></a>Formato

18 cifre

### <a name="pattern"></a>Modello

18 cifre:
- Sei cifre, ovvero un codice indirizzo  
- Otto cifre nel formato AAAAMMGG, ovvero la data di nascita  
- Tre cifre, ovvero un codice di ordine  
- Una cifra, ovvero una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_china_resident_id trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_china_resident_id.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="credit-card-number"></a>Credit Card Number

### <a name="format"></a>Formato

16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e devono superare il test di Luhn.

### <a name="pattern"></a>Modello

Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.

### <a name="checksum"></a>Checksum

Yes, il checksum Luhn

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_credit_card restituisce contenuti che corrispondono al modello.
- Si verifica una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_cc_verification.
    - Viene trovata una parola chiave da Keyword_cc_name.
    - La funzione Func_expiration_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
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
- Cod. SEGURANCA Cod. Segurança
- cód. seguranca
- cód segurança
- Cod SEGURANCA Cod Segurança
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
- Venc 

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- Amex
- american express
- AmericanExpress
- Esempio
- Mastercard
- master card
- MC 
- Mastercard
- master cards
- diner's Club
- diners club
- DinersClub
- discover card
- discovercard
- discover cards
- JCB
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
- carta
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
   
## <a name="croatia-identity-card-number"></a>Numero di carta di identità della Croazia

### <a name="format"></a>Formato

9 cifre

### <a name="pattern"></a>Modello

9 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

- Carta d’identità croata
- Osobna iskaznica

   
## <a name="croatia-personal-identification-oib-number"></a>Numero di identificazione personale (OIB) - Croazia

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre:
- 10 cifre 
- La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_croatia_oib_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_croatia_oib_number.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_croatia_oib_number trova contenuto corrispondente al modello.
- Il checksum ha esito positivo.

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- Codice PIN
- Osobni identifikacijski broj 
- OIB 

   
## <a name="czech-personal-identity-number"></a>Numero di identità personale ceco

### <a name="format"></a>Formato

Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)

### <a name="pattern"></a>Modello

Nove cifre (formato obsoleto):
- 9 cifre

OPPURE

- Sei cifre che rappresentano la data di nascita
- Una barra
- Tre cifre

10 cifre (nuovo formato):
- 10 cifre

OPPURE

- Sei cifre che rappresentano la data di nascita
- Una barra 
- Quattro cifre in cui l'ultima cifra è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto corrispondente al modello.
Viene trovata una parola chiave da Keyword_czech_id_card.
Il checksum ha esito positivo.

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>Parole chiave

- numero di identità personale ceco
- Rodné číslo
   
## <a name="denmark-personal-identification-number"></a>Codice PIN - Danimarca

### <a name="format"></a>Formato

10 cifre contenenti una lineetta

### <a name="pattern"></a>Modello

10 cifre:
- Sei cifre nel formato GGMMAA, ovvero la data di nascita 
- Una lineetta 
- Quattro cifre, dove l'ultima è una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto corrispondente al modello.
Viene trovata una parola chiave da Keyword_denmark_id.
Il checksum ha esito positivo.

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- Codice PIN
- CPR
- Det Centrale Personregister
- Personnummer
   
## <a name="drug-enforcement-agency-dea-number"></a>Numero della Drug Enforcement Agency (DEA)

### <a name="format"></a>Formato

Due lettere seguite da 7 cifre

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante 
- Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante 
- 7 cifre e l'ultima è quella di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_dea_number restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

Nessuno

   
## <a name="eu-debit-card-number"></a>Unione Europea - Numero di carta di debito

### <a name="format"></a>Formato

16 cifre

### <a name="pattern"></a>Modello

Modello molto complesso e solido

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).
  
## <a name="eu-national-identification-number"></a>Numero di identificazione nazionale dell'Unione europea

Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).
  
## <a name="eu-passport-number"></a>Numero di passaporto EU

Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).
  
## <a name="eu-social-security-number-or-equivalent-id"></a>Codice di previdenza sociale dell'Unione europea o ID equivalente

Per ulteriori informazioni, vedere [codice di previdenza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).
  
## <a name="eu-tax-identification-number"></a>Numero di identificazione fiscale dell'Unione europea

Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).
  
## <a name="finland-national-id"></a>Finland National ID

### <a name="format"></a>Formato

6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- Sei cifre nel formato DDMMYY che corrisponde alla data di nascita 
- Indicatore del secolo ("-", "+" o "a") 
- Codice PIN di 3 cifre 
- Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_finnish_national_id.
- Il checksum ha esito positivo.

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

- Keyword_finnish_national_id
- Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## <a name="finland-passport-number"></a>Finlandia - Numero di passaporto

Combinazione di formato di nove lettere e combinazioni di caratteri di nove lettere e cifre: due lettere (senza distinzione tra maiuscole/minuscole) sette cifre checksum nessuna definizione un criterio DLP è 75% sicuro che sia stato rilevato questo tipo di informazioni riservate se, all'interno di un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number trova il contenuto corrispondente al modello.
Viene trovata una parola chiave da Keyword_finland_passport_number.
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity>
Parole chiave Keyword_finland_passport_number Passport proc
   
## <a name="france-drivers-license-number"></a>Francia - Numero della patente di guida

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.
- Si verifica almeno una delle situazioni seguenti:
- Viene trovata una parola chiave da Keyword_french_drivers_license.
- La funzione Func_eu_date rileva una data nel formato corretto.

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers

## <a name="france-national-id-card-cni"></a>Francia - Carta d'identità nazionale (CNI)

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
- L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

Nessuno
   
## <a name="france-passport-number"></a>Francia - Numero di passaporto

### <a name="format"></a>Formato

Nove cifre e lettere

### <a name="pattern"></a>Modello

Nove cifre e lettere:
- Due cifre 
- Due lettere (senza distinzione tra maiuscole/minuscole) 
- Cinque cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

      
## <a name="france-social-security-number-insee"></a>Francia - Numero di previdenza sociale (INSEE)

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:
- La funzione Func_french_insee o Func_fr_insee trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_fr_insee.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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
   
## <a name="german-drivers-license-number"></a>Germania - Numero della patente di guida

### <a name="format"></a>Formato

Combinazione di 11 cifre e lettere

### <a name="pattern"></a>Modello

11 cifre e lettere (senza distinzione tra maiuscole/minuscole):
- Una cifra o una lettera 
- Due cifre 
- Sei cifre o lettere 
- Una cifra 
- Una cifra o una lettera

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.
- Si verifica almeno una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_german_drivers_license_number.
    - Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.
    - Viene trovata una parola chiave da Keyword_german_drivers_license.
- Il checksum ha esito positivo.

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- Führerschein
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr
- Fuhrerschein- Nr
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr 
- Fuhrerschein- Nr 
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- DL 
- DLS
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein
- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein 

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
   
## <a name="german-passport-number"></a>Germania - Numero di passaporto

### <a name="format"></a>Formato

10 cifre o lettere

### <a name="pattern"></a>Modello

Il modello deve includere tutti gli elementi seguenti:
- Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K 
- Tre cifre 
- Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z 
- Una cifra

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_german_passport restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave fra le cinque elencate.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave fra le cinque elencate.
- Il checksum ha esito positivo.

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepass
- reisepasse
- reisepassnummer
- passaporto
- passaporti

#### <a name="keyword_german_passport_collaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keyword_german_passport_number"></a>Keyword_german_passport_number

No-Reisepass Nr-Reisepass

#### <a name="keyword_german_passport1"></a>Keyword_german_passport1

Reisepass-Nr

#### <a name="keyword_german_passport2"></a>Keyword_german_passport2

bnationalit. t
   
## <a name="germany-identity-card-number"></a>Germania - Numero carta di identità

### <a name="format"></a>Formato

Dal 1 ° novembre 2010: nove lettere e cifre

Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre

### <a name="pattern"></a>Modello

A partire dal 1° novembre 2010:
- Una lettera (senza distinzione tra maiuscole/minuscole) 
- Otto cifre

Dal 1 ° aprile 1987 al 31 ottobre 2010:
- 10 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
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

- Carta di identità
- ID
- Identificazione
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## <a name="greece-national-id-card"></a>Carta d'identità (Grecia)

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- L'espressione regolare Regex_greece_id_card trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_greece_id_card.

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- Carta d’identità greca
- Tautotita
- Δελτίο αστυνομικής ταυτότητας
- Ταυτότητα
   
## <a name="hong-kong-identity-card-hkid-number"></a>Hong Kong - Numero di carta di identità (HKID)

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_hong_kong_id_card trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_hong_kong_id_card.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
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
   
## <a name="india-permanent-account-number-pan"></a>India - Numero di conto permanente (PAN)

### <a name="format"></a>Formato

10 lettere o cifre

### <a name="pattern"></a>Modello

10 lettere o cifre:
- Cinque lettere (senza distinzione tra maiuscole e minuscole) 
- Quattro cifre 
- Una lettera, ovvero una cifra di controllo alfabetica

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- L'espressione regolare Regex_india_permanent_account_number trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_india_permanent_account_number.
- Il checksum ha esito positivo.

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- PAN 
   
## <a name="india-unique-identification-aadhaar-number"></a>India - Numero di identificazione univoco (Aadhaar)

### <a name="format"></a>Formato

12 cifre contenenti spazi o trattini facoltativi 

### <a name="pattern"></a>Modello

12 cifre:
- Quattro cifre 
- Uno spazio o un trattino facoltativo  
- Quattro cifre 
- Uno spazio o un trattino facoltativo  
- L'ultimo carattere, ovvero il numero di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto corrispondente al modello.
Viene trovata una parola chiave da Keyword_india_aadhar.
Il checksum ha esito positivo.
Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto corrispondente al modello.
Il checksum ha esito positivo.
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
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>Indonesia - Numero di carta di identità (KTP)

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- L'espressione regolare Regex_indonesia_id_card trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_indonesia_id_card.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- L'espressione regolare Regex_indonesia_id_card trova contenuti che corrispondono al modello.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
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

ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU , NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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
   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Classificazione internazionale delle malattie (ICD-10-CM)

### <a name="format"></a>Formato

Dizionario

### <a name="pattern"></a>Modello

Parola chiave

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- Viene trovata una parola chiave da Dictionary_icd_10_updated.
- Viene trovata una parola chiave da Dictionary_icd_10_codes.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

Parole chiave

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- Viene trovata una parola chiave da Dictionary_icd_9_updated.
- Viene trovata una parola chiave da Dictionary_icd_9_codes.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

## <a name="ireland-personal-public-service-pps-number"></a>Irlanda - Numero personale di servizio pubblico (PPS)

### <a name="format"></a>Formato

Formato precedente (fino al 31 dicembre 2012):
- Sette cifre seguite da 1-2 lettere  

Nuovo formato (1 gen 2013 e successive):
- Sette cifre seguite da due lettere

### <a name="pattern"></a>Modello

Formato precedente (fino al 31 dicembre 2012):
- Sette cifre 
- 1-2 lettere (senza distinzione tra maiuscole e minuscole) 

Nuovo formato (1 gen 2013 e successive):
- Sette cifre 
- Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica  
- La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_ireland_pps trova contenuto corrispondente al modello.
- Si verifica una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_ireland_pps.
    - La funzione Func_eu_date rileva una data nel formato corretto.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
- La funzione Func_ireland_pps trova contenuto corrispondente al modello.
- Il checksum ha esito positivo.

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_ireland_pps"></a>Keyword_ireland_pps

- Numero personale di servizio pubblico 
- Numero PPS 
- Num. PPS
 
- N° PPS 
- PPS # 
- PPS # 
- PPSN 
- Scheda servizi pubblici 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Uimh. PSP 
- PSP 
   
## <a name="israel-bank-account-number"></a>Israele - Numero di conto bancario

### <a name="format"></a>Formato

13 cifre

### <a name="pattern"></a>Modello

Formattato
- Due cifre 
- Un trattino 
- Tre cifre 
- Un trattino 
- Otto cifre

Formattato
- 13 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="israel-national-id"></a>Carta di identità (Israele)

### <a name="format"></a>Formato

9 cifre

### <a name="pattern"></a>Modello

9 cifre consecutive

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

- מספר זהות 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>Italia - Numero della patente di guida

### <a name="format"></a>Formato

Una combinazione di 10 lettere e cifre

### <a name="pattern"></a>Modello

- Una combinazione di 10 lettere e cifre:
- Una lettera (senza distinzione tra maiuscole/minuscole) 
- La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole) 
- 7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura 
- Una lettera (senza distinzione tra maiuscole/minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

- numero di patente di guida 
- patente di guida 
   
## <a name="japan-bank-account-number"></a>Giappone - Numero di conto bancario

### <a name="format"></a>Formato

Sette o otto cifre

### <a name="pattern"></a>Modello

Numero di conto corrente:
- Sette o otto cifre
- Codice della filiale del conto corrente:
- Quattro cifre 
- Uno spazio o un trattino (facoltativo) 
- Tre cifre

Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_bank_account.
- Si verifica una delle situazioni seguenti:
- La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_bank_branch_code.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
- 口座番号を当座預金口座の確認 
- #アカウントの確認 、 勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番号 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座＃ 
- 貯蓄勘定の数 
- 貯蓄勘定＃ 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号＃ 
- デビットのacct番号 
- デビット勘定＃ 
- デビットACCTの番号 
- デビット口座番号 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>Giappone - Numero della patente di guida

### <a name="format"></a>Formato

12 cifre

### <a name="pattern"></a>Modello

12 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

- DL # 
- DL 
- DLS # 
- DLS 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- driver'lic # 
- DRIVER'LIC 
- driver'lics # 
- state id 
- state identification 
- state identification number 
- 低所得国＃ 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>Giappone - Numero di passaporto

### <a name="format"></a>Formato

Due lettere seguite da 7 cifre

### <a name="pattern"></a>Modello

Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
   
## <a name="japan-resident-registration-number"></a>Giappone - Numero di registrazione dei residenti

### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
- Resident Register Number 
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 住民登録番号、登録番号をレジデント 
- 住民基本登録番号、登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>Giappone - Numero di assicurazione sociale (SIN)

### <a name="format"></a>Formato

7-12 cifre

### <a name="pattern"></a>Modello

7-12 cifre:
- Quattro cifre 
- Una lineetta (facoltativa) 
- Sei cifre o
- 7-12 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_jp_sin.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
- 社会保険のテンキー 
- 社会保険番号 

## <a name="japanese-residence-card-number"></a>Numero di carta di soggiorno giapponese

### <a name="format"></a>Formato

12 lettere e cifre

### <a name="pattern"></a>Modello

12 lettere e cifre:
- Due lettere (senza distinzione tra maiuscole/minuscole)
- Otto cifre 
- Due lettere (senza distinzione tra maiuscole/minuscole)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="malaysia-id-card-number"></a>Malesia - Numero di carta d’identità

### <a name="format"></a>Formato

12 cifre contenenti lineette facoltative

### <a name="pattern"></a>Modello

12 cifre:
- Sei cifre nel formato AAMMGG, ovvero la data di nascita 
- Un trattino (facoltativo) 
- Codice luogo di nascita a due lettere  
- Un trattino (facoltativo) 
- Tre cifre casuali  
- Codice genere a una cifra singola

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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
   
## <a name="netherlands-citizens-service-bsn-number"></a>Paesi Bassi - Numero di servizio cittadino (BSN)

### <a name="format"></a>Formato

8-9 cifre contenenti spazi facoltativi 

### <a name="pattern"></a>Modello

8-9 cifre:
- Tre cifre 
- Uno spazio (facoltativo) 
- Tre cifre 
- Uno spazio (facoltativo) 
- 2-3 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_netherlands_bsn trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_netherlands_bsn.
- La funzione Func_eu_date2 trova una data nel formato di data appropriato.
- Il checksum ha esito positivo.

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_netherlands_bsn"></a>Keyword_netherlands_bsn

- Numero di servizio cittadino 
- BSN 
- Burgerservicenummer 
- Sofinummer 
- Persoonsgebonden nummer 
- Persoonsnummer    

   
## <a name="new-zealand-ministry-of-health-number"></a>Nuova Zelanda - Numero del Ministero della Sanità

### <a name="format"></a>Formato

Tre lettere, uno spazio (facoltativo) e quattro cifre

### <a name="pattern"></a>Modello

Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_nz_terms.
- Il checksum ha esito positivo.

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

Parole chiave

Keyword_nz_terms

- NHI 
- New Zealand 
- Sanità 
- trattamento 
   
## <a name="norway-identification-number"></a>Norvegia - Numero di identificazione


### <a name="format"></a>Formato

11 cifre

### <a name="pattern"></a>Modello

11 cifre:
- Sei cifre nel formato GGMMAA, ovvero la data di nascita 
- Numero individuale composto da tre cifre  
- Due cifre di controllo

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_norway_id_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_norway_id_number.
- Il checksum ha esito positivo.
- Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

   
## <a name="philippines-unified-multi-purpose-id-number"></a>Filippine - Numero ID multifunzione unificato

### <a name="format"></a>Formato

12 cifre separate da dei segni meno

### <a name="pattern"></a>Modello

12 cifre:
- Quattro cifre 
- Una lineetta 
- Sette cifre 
- Una lineetta 
- Una cifra

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="poland-identity-card"></a>Carta di identita - Polonia

### <a name="format"></a>Formato

Tre lettere e sei cifre

### <a name="pattern"></a>Modello

Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto corrispondente al modello.
Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.
Il checksum ha esito positivo.

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

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

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

11 cifre consecutive

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_pesel_identification_number.
- Il checksum ha esito positivo.

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- Nr PESEL
- PESEL   

   
## <a name="poland-passport"></a>Passaporto Polonia

### <a name="format"></a>Formato

Due lettere e sette cifre

### <a name="pattern"></a>Modello

Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Numero Paszportu
- Nr. Paszportu
- Paszport

   
## <a name="portugal-citizen-card-number"></a>Portogallo - Numero di carta del cittadino

### <a name="format"></a>Formato

Otto cifre

### <a name="pattern"></a>Modello

Otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

- Scheda cittadino
- Carta ID
- CC
- Cartão de Cidadão
- Bilhete de Identidade
   
## <a name="saudi-arabia-national-id"></a>Arabia Saudita - Identificativo nazionale

### <a name="format"></a>Formato

10 cifre

### <a name="pattern"></a>Modello

10 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Singapore - Numero di carta di identità di registrazione nazionale (NRIC)

### <a name="format"></a>Formato

Nove lettere e numeri

### <a name="pattern"></a>Modello

- Nove lettere e numeri:
- La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole)  
- Sette cifre 
- Una cifra di controllo alfabetica

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- L'espressione regolare Regex_singapore_nric trova contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_singapore_nric.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="south-africa-identification-number"></a>Sudafrica - Numero di identificazione


### <a name="format"></a>Formato

13 cifre che possono contenere spazi

### <a name="pattern"></a>Modello

13 cifre:
- Sei cifre nel formato AAMMGG, ovvero la data di nascita 
- Quattro cifre 
- Un indicatore di cittadinanza a una cifra  
- La cifra "8" o "9"  
- Una cifra, ovvero una cifra di checksum

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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
   
## <a name="south-korea-resident-registration-number"></a>Corea del Sud - Numero di registrazione dei residenti

### <a name="format"></a>Formato

13 cifre contenenti un segno meno

### <a name="pattern"></a>Modello

13 cifre:
- Sei cifre nel formato AAMMGG, ovvero la data di nascita 
- Una lineetta 
- Una cifra determinata dal secolo e dal sesso  
- Codice di quattro cifre dell’area geografica di nascita  
- Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali  
- Una cifra di controllo.

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_south_korea_resident_number trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_south_korea_resident_number.
- Il checksum ha esito positivo.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="spain-social-security-number-ssn"></a>Spagna - Numero di previdenza sociale (SSN)

### <a name="format"></a>Formato

11-12 cifre

### <a name="pattern"></a>Modello

11-12 cifre:
- Due cifre 
- Una barra (facoltativa) 
- 7-8 cifre 
- Una barra (facoltativa) 
- Due cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

## <a name="sql-server-connection-string"></a>Stringa di connessione di SQL Server

### <a name="format"></a>Formato

Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.

### <a name="pattern"></a>Modello

- Stringa "ID utente", "ID utente", "UID" o "UserId"
- Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo
- La stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola
- Segno di uguale (=)
- Qualsiasi carattere che non sia un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), il simbolo (@), le virgolette ("), il punto e virgola (;), parentesi graffa sinistra ([) o parentesi quadra sinistra ({)
- Qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")
- Un punto e virgola (;) o virgolette (")

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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

## <a name="sweden-national-id"></a>Svezia - Identificativo nazionale

### <a name="format"></a>Formato

10 o 12 cifre e un delimitatore facoltativo

### <a name="pattern"></a>Modello

10 o 12 cifre e un delimitatore facoltativo:
- 2-4 cifre (facoltative) 
- Sei cifre nel formato data AAMMGG 
- Delimitatore di "-" o "+" (facoltativo) più
- Quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.
- Il checksum ha esito positivo.

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

No
   
## <a name="sweden-passport-number"></a>Svezia - Numero di passaporto

### <a name="format"></a>Formato

Otto cifre

### <a name="pattern"></a>Modello

Otto cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.
- Si verifica una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_passport.
    - Viene trovata una parola chiave da Keyword_sweden_passport.

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
   
## <a name="swift-code"></a>Codice SWIFT

### <a name="format"></a>Formato

Quattro lettere seguite da 5-31 lettere o cifre

### <a name="pattern"></a>Modello

Quattro lettere seguite da 5-31 lettere o cifre:
- Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole) 
- Uno spazio facoltativo 
- 4-28 lettere o cifre (BBAN) 
- Uno spazio facoltativo 
- 1-3 lettere o cifre (resto del BBAN)

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
- Swift\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift code 
- swift number # 
- swift routing number 
- bic number 
- bic code 
- BIC\# 
- BIC\# 
- bank identifier code 
- 標準化 9362 
- 迅速＃ 
- SWIFTコード 
- SWIFT番号 
- 迅速なルーティング番号 
- BIC番号 
- BICコード 
- 銀行識別コードのための国際組織 
- Organisation internationale de normalisation 9362 
- rapide\# 
- code SWIFT 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \#BIC 
- code identificateur de banque 
   
## <a name="taiwan-national-id"></a>Taiwan National ID

### <a name="format"></a>Formato

Una lettera (in lingua inglese) seguita da nove cifre

### <a name="pattern"></a>Modello

Una lettera (in lingua inglese) seguita da nove cifre:
- Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole) 
- La cifra "1" o "2" 
- Otto cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_taiwanese_national_id.
- Il checksum ha esito positivo.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_taiwanese_national_id"></a>Keyword_taiwanese_national_id

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
   
## <a name="taiwan-passport-number"></a>	Taiwan - Numero di passaporto

### <a name="format"></a>Formato

- Numero di passaporto biometrico: nove cifre
- Numero di passaporto non biometrico: nove cifre

### <a name="pattern"></a>Modello
Numero di passaporto biometrico:
- La cifra "3"  
- Otto cifre

Numero di passaporto non biometrico:
- 9 cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Taiwan - Numero certificato di residenza (ARC/TARC)

### <a name="format"></a>Formato

10 lettere e cifre

### <a name="pattern"></a>Modello

10 lettere e cifre:
- Due lettere (senza distinzione tra maiuscole/minuscole) 
- Otto cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
- La prima cifra non è 0 o 9 
- 12 cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_Thai_Citizen_Id trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

#### <a name="keyword_thai_citizen_id"></a>Keyword_Thai_Citizen_Id

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

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_Turkish_National_Id trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_Turkish_National_Id.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

#### <a name="keyword_turkish_national_id"></a>Keyword_Turkish_National_Id

- TC Kimlik No
- Numarası Kimlik TC
- Vatandaşlık numarası
- Vatandaşlık No

## <a name="uk-drivers-license-number"></a>Regno Unito - Numero della patente di guida

### <a name="format"></a>Formato

Combinazione di 18 lettere e numeri nel formato specificato

### <a name="pattern"></a>Modello

18 lettere e cifre:
- Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera 
- Una cifra 
- Cinque cifre nel formato data MMDDY per data di nascita (il settimo carattere viene incrementato di 50 se il driver è di tipo femminile, ovvero 51 a 62 invece di 01 a 12)
- Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera 
- Cinque cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="uk-electoral-roll-number"></a>Regno Unito - Numero di iscrizione alle liste elettorali

### <a name="format"></a>Formato

Due lettere seguite da 1-4 cifre

### <a name="pattern"></a>Modello

Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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

   
## <a name="uk-national-health-service-number"></a>Regno Unito - Codice del servizio sanitario nazionale

### <a name="format"></a>Formato

10-17 cifre separate da spazi

### <a name="pattern"></a>Modello

10-17 cifre:
- 3 o 10 cifre 
- Uno spazio 
- Tre cifre 
- Uno spazio 
- Quattro cifre

### <a name="checksum"></a>Checksum

Sì

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
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
   
## <a name="uk-national-insurance-number-nino"></a>Regno Unito - Numero di assicurazione nazionale (NINO)

### <a name="format"></a>Formato

7 caratteri o 9 caratteri separati da spazi o trattini

### <a name="pattern"></a>Modello

Due modelli possibili:

- Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)
- Sei cifre
- ' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)

OPPURE

- Due lettere
- Uno spazio o un trattino
- Due cifre
- Uno spazio o un trattino
- Due cifre
- Uno spazio o un trattino
- Due cifre
- Uno spazio o un trattino
- ' A ',' B ',' c'o ' d'

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_uk_nino.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.
- Non vengono trovate parole chiave da Keyword_uk_nino.

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
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
- Insurance    
   
## <a name="us--uk-passport-number"></a>Stati Uniti/Regno Unito - Numero di passaporto

### <a name="format"></a>Formato

9 cifre

### <a name="pattern"></a>Modello

9 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="us-bank-account-number"></a>Stati Uniti - Numero di conto bancario

### <a name="format"></a>Formato

8-17 cifre

### <a name="pattern"></a>Modello

8-17 cifre consecutive

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
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
   
## <a name="us-drivers-license-number"></a>Stati Uniti - Numero della patente di guida

### <a name="format"></a>Formato

Varia in base allo stato

### <a name="pattern"></a>Modello

Varia in base allo stato. Ad esempio, per New York:
- Nove cifre formattate come ddd ddd ddd corrisponderanno.
- Nove cifre come ddddddddd non corrispondono.

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.
- Viene trovata una parola chiave da Keyword_us_drivers_license.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
- La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.
- Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.
- Non vengono trovate parole chiave da Keyword_us_drivers_license.

```xml
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

- Abbreviazione dello stato (ad esempio, "NY") 
- Nome dello stato (ad esempio, "New York")    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>Stati Uniti - Codice identificativo del contribuente individuale (ITIN)

### <a name="format"></a>Formato

Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)

### <a name="pattern"></a>Modello

Formattato
- La cifra "9" 
- Due cifre 
- Uno spazio o un trattino 
- Un "7" o un "8" 
- Una cifra 
- Uno spazio o un trattino 
- Quattro cifre

Formattato
- La cifra "9" 
- Due cifre 
- Un "7" o un "8" 
- Cinque cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.
- Si verifica almeno una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_itin.
    - La funzione Func_us_address rileva un indirizzo nel formato di data corretto.
    - La funzione Func_us_date rileva una data nel formato corretto.
    - Viene trovata una parola chiave da Keyword_itin_collaborative.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.
- Si verifica almeno una delle situazioni seguenti:
    - Viene trovata una parola chiave da Keyword_itin_collaborative.
    - La funzione Func_us_address rileva un indirizzo nel formato di data corretto.
    - La funzione Func_us_date rileva una data nel formato corretto.

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_itin"></a>Keyword_itin

- contribuente 
- tax id 
- tax identification 
- Itin 
- SSN 
- latta 
- social security 
- tax payer 
- itins 
- taxid 
- individual taxpayer 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- License 
- DL 
- DOB 
- Data di nascita 
- Compleanno 
- Date of Birth 
   
## <a name="us-social-security-number-ssn"></a>Stati Uniti - Numero di previdenza sociale (SSN)

### <a name="format"></a>Formato

9 cifre formattate o meno

> [!NOTE]
> Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).

### <a name="pattern"></a>Modello

Quattro funzioni cercano SNSS in quattro modelli diversi:
- Func_ssn trova SNSS con una formattazione complessa pre2011 formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)
- Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)
- Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)
- Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)

### <a name="checksum"></a>Checksum

No


### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
- La funzione Func_ssn restituisce contenuti che corrispondono al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
- La funzione Func_unformatted_ssn trova contenuto corrispondente al modello.
- Viene trovata una parola chiave da Keyword_ssn.

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
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

- Social Security 
- Social Security# 
- Soc Sec 
- SSN 
- SNSS 
- SSN # 
- SS # 
- SSID 
   

