---
title: Cosa cercano le funzioni di prevenzione della perdita di dati (DLP)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni sulle funzioni di prevenzione della perdita di dati (DLP, Data Loss Prevention).
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841447"
---
# <a name="what-the-dlp-functions-look-for"></a>Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati

I criteri di prevenzione della perdita di dati (DLP) possono utilizzare tipi di informazioni riservate per identificare gli elementi sensibili. Il numero di carta di credito e il numero di carta di debito UE sono esempi di tipi di informazioni riservate. I tipi di informazioni riservate cercano modelli specifici. I tipi di informazioni riservate convalidano i dati osservando il formato, i checksum e la ricerca di parole chiave rilevanti o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate per il numero di carta di credito utilizza una funzione per cercare le date formattate come data di scadenza. Questo aiuta a confermare che un numero è un numero di carta di credito.
  
In questo articolo vengono illustrate le funzionalità che devono essere cercate per comprendere il funzionamento dei tipi di informazioni riservate predefinite. Per ulteriori informazioni, vedere [definizioni di entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Tabella delle funzioni

|Nome funzione  |azione funzione  |è un validator|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|rileva e convalida l'Argentina Unique Key Tax|no|
|Func_aba_routing|rileva il numero di Routing ABA| sì|
|Func_alabama_drivers_license_number|rileva il numero di patente del conducente Alabama|no|
|Func_alaska_delaware_oregon_drivers_license_number|rileva il numero di licenza del conducente di Alaska, Delaware e Oregon|no|
|Func_alaska_drivers_license_number|rileva il numero di patente del conducente Alaska|no|
|Func_alberta_drivers_license_number|rileva il numero di patente del conducente Alberta|no|
|Func_Argentina_Unique_Tax_Key|rileva la chiave fiscale univoca Argentina|no|
|Func_arizona_drivers_license_number|rileva il numero di patente del conducente Arizona|no|
|Func_arkansas_drivers_license_number|rileva il numero di patente del conducente Arkansas|no|
|Func_australian_business_number|rileva il numero dell'azienda Australia|no|
|Func_Australian_Company_Number|rileva il numero dell'azienda Australia|no|
|Func_australian_medical_account_number|rileva il numero di conto medica australiano|no|
|Func_australian_tax_file_number|rileva il numero di file fiscale Australia|sì|
|Func_austria_eu_ssn_or_equivalent|rileva il numero di previdenza sociale Austria|no|
|Func_austria_eu_tax_file_number|rileva il numero di file fiscale Austria|no|
|Func_Austria_Value_Added_Tax|rileva l'imposta sul valore aggiunto Austria|no|
|Func_belgium_national_number|rileva il numero nazionale belga|no|
|Func_belgium_value_added_tax_number|rileva il numero di imposta sul valore aggiunto belga|no|
|Func_brazil_cnpj|rileva il numero di entità legali del Brasile (CNPJ)|sì|
|Func_brazil_cpf|rileva il Brasile CPF|sì|
|Func_brazil_rg|rileva il Brasile RG|no|
|Func_british_columbia_drivers_license_number|rileva il numero di licenza del conducente della British Columbia|no|
|Func_bulgaria_eu_national_id_card|rileva il numero civile uniforme della Bulgaria|no|
|Func_california_drivers_license_number|rileva il numero della patente di guida California|no|
|Func_canadian_sin|rileva il peccato del Canada|sì|
|Func_chile_id_card|rileva la scheda ID Cile|no|
|Func_china_resident_id|rileva l'ID residente in Cina|no|
|Func_colorado_drivers_license_number|rileva il numero di patente del conducente Colorado|no|
|Func_connecticut_drivers_license_number|rileva il numero di patente del conducente Connecticut|no|
|Func_credit_card|rileva la carta di credito|sì|no|
|Func_croatia_id_card|rileva la carta di identità della Croazia|no|
|Func_croatia_oib_number|rileva il numero OIB Croatia|no|
|Func_cyprus_eu_tax_file_number|rileva il numero del file fiscale cipriota|no|
|Func_czech_id_card|rileva la scheda ID Ceca|no|
|Func_czech_id_card_new_format|rileva la scheda ID Ceca in nuovo formato|no|
|Func_dea_number|rileva il numero della DEA|sì|
|Func_denmark_eu_tax_file_number|rileva il numero di identificazione personale danese|no|
|Func_district_of_columbia_drivers_license_number|rileva il numero di patente del distretto di Columbia|no|
|Func_estonia_eu_national_id_card|rileva il codice di identificazione personale estone|no|
|Func_eu_debit_card|rileva la carta di debito dell'Unione europea|no|
|Func_finnish_national_id|rileva l'ID nazionale finlandese|no|
|Func_florida_drivers_license_number|rileva il numero della patente di guida Florida|no|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|rileva il numero della patente di guida di Florida, Maryland, Michigan, Minnesota|no|
|Func_formatted_itin|rileva formattato negli Stati Uniti.|sì|
|Func_fr_insee|rileva la Francia INSEE|no|
|Func_fr_passport|rileva il passaporto di Francia|no|
|Func_france_eu_tax_file_number|rileva il numero di file fiscale Francia|no|
|Func_france_value_added_tax_number|rileva il numero di imposta sul valore aggiunto Francia|no|
|Func_french_drivers_license|rileva la licenza francese del conducente|no|
|Func_french_insee|rileva la lingua francese INSEE|no|
|Func_georgia_drivers_license_number|rileva il numero della patente di guida Georgia|no|
|Func_german_drivers_license|rileva la patente di guida Germania|no|
|Func_german_passport|rileva il passaporto tedesco|no|
|Func_german_passport_data|rileva il passaporto tedesco|no|
|Func_germany_eu_tax_file_number|rileva il numero di file fiscale Germania|no|
|Func_germany_value_added_tax_number|rileva il numero di imposta sul valore aggiunto Germania|no|
|Func_greece_eu_ssn|rileva la Grecia sin (AMKA)|no|
|Func_hawaii_drivers_license_number|rileva il numero di licenza del conducente Hawaii|no|
|Func_hong_kong_id_card |rileva la scheda ID Hong Kong|no|
|Func_hungarian_value_added_tax_number|rileva il numero di imposta sul valore aggiunto Ungheria|no|
|Func_hungary_eu_national_id_card|rileva il numero di identificazione personale Ungheria|no|
|Func_hungary_eu_ssn_or_equivalent|rileva il numero di previdenza sociale ungherese|no|
|Func_hungary_eu_tax_file_number|rileva il numero di file fiscale ungherese|no|
|Func_iban|rileva IBAN|sì|
|Func_idaho_drivers_license_number|rileva il numero di patente dell'Idaho|no|
|Func_illinois_drivers_license_number|rileva il numero di patente del conducente Illinois|no|
|Func_india_aadhaar|rileva l'India Aadhaar|sì|
|Func_indiana_drivers_license_number|rileva il numero di patente del conducente indiana|no|
|Func_iowa_drivers_license_number|rileva il numero di patente del conducente Iowa|no|
|Func_ireland_pps|rileva l'Irlanda PPS|no|
|Func_israeli_national_id_number|rileva il numero di ID nazionale di Israele|no|
|Func_italy_eu_national_id_card |rileva il codice fiscale Italia|no|
|Func_italy_value_added_tax_number|rileva il numero di imposta sul valore aggiunto Italia|no|
|Func_japanese_my_number_corporate|rileva il Giappone il mio numero aziendale|sì|
|Func_japanese_my_number_personal|rileva il numero personale del Giappone|sì|
|Func_jp_bank_account|rileva il conto corrente in Giappone|no|
|Func_jp_bank_account_branch_code|rileva il codice della filiale del conto corrente bancario giapponese|no|
|Func_jp_drivers_license_number|rileva il numero della patente di guida del Giappone|no|
|Func_jp_passport|rileva il passaporto giapponese|no|
|Func_jp_resident_registration_number|rileva il numero di registrazione residente in Giappone|no|
|Func_jp_sin|rileva il peccato del Giappone|no|
|Func_jp_sin_pre_1997|rileva il Giappone sin pre1997|no|
|Func_kansas_drivers_license_number|rileva il numero della patente di guida Kansas|no|
|Func_kentucky_drivers_license_number|rileva il numero della patente di guida del Kentucky|no|
|Func_kentucky_massachusetts_virginia_drivers_license_number|rileva il numero di licenza di Kentucky, Massachusetts, Virginia driver|no|
|Func_latvia_eu_national_id_card|rileva il codice personale Latvia|no|
|Func_lithuania_eu_tax_file_number|rileva il codice personale della Lituania|no|
|Func_louisiana_drivers_license_number|rileva il numero di licenza del conducente della Louisiana|no|
|Func_luxemburg_eu_tax_file_number|rileva il numero di identificazione nazionale del Lussemburgo (persone fisiche)|no|
|Func_luxemburg_eu_tax_file_number_non_natural|rileva il numero di identificazione nazionale del Lussemburgo (persone non fisiche)|no|
|Func_maine_drivers_license_number|rileva il numero della patente di guida del Maine|no|
|Func_manitoba_drivers_license_number|rileva il numero della patente di guida Manitoba|no|
|Func_maryland_drivers_license_number|rileva il numero di licenza del conducente Maryland|no|
|Func_massachusetts_drivers_license_number|rileva il numero di licenza del conducente del Massachusetts|no|
|Func_mexico_population_registry_code|rileva il codice del registro di sistema della popolazione messicana|no|
|Func_michigan_minnesota_drivers_license_number|rileva il numero di patente Michigan, Minnesota|no|
|Func_minnesota_drivers_license_number|rileva il numero della patente di guida del Minnesota|no|
|Func_mississippi_oklahoma_drivers_license_number|rileva il numero di patente del Mississippi, Oklahoma|no|
|Func_missouri_drivers_license_number|rileva il numero di licenza del conducente del Missouri|no|
|Func_montana_drivers_license_number|rileva il numero di licenza del conducente del Montana|no|
|Func_nebraska_drivers_license_number|rileva il numero della patente di guida del Nebraska|no|
|Func_netherlands_bsn|rileva i Paesi Bassi BSN|no|
|Func_netherlands_eu_tax_file_number|rileva il numero di file delle tasse olandesi|no|
|Func_netherlands_value_added_tax_number|rileva il numero di imposta sul valore aggiunto (Paesi Bassi)|no|
|Func_nevada_drivers_license_number|rileva il numero della patente di guida del Nevada|no|
|Func_new_brunswick_drivers_license_number|rileva il numero di patente del Nuovo Brunswick driver|no|
|Func_new_hampshire_drivers_license_number|rileva il numero di patente del nuovo Hampshire|no|
|Func_new_jersey_drivers_license_number |rileva il numero di licenza del nuovo jersey driver|no|
|Func_new_mexico_drivers_license_number |rileva il numero di patente del nuovo Messico|no|
|Func_new_york_drivers_license_number   |rileva il numero di licenza del conducente di New York|no|
|Func_new_zealand_bank_account_number   |rileva il numero di conto corrente bancario neozelandese|no|
|Func_new_zealand_inland_revenue_number |rileva il numero di ricavo interno della Nuova Zelanda|no|
|Func_new_zealand_ministry_of_health_number|rileva il numero del Ministero della sanità della Nuova Zelanda|no|
|Func_newfoundland_labrador_drivers_license_number|rileva il numero di patente del conducente del Labrador di Terranova|no|
|Func_newzealand_driver_license_number  |rileva il numero di licenza del conducente neozelandese|no|
|Func_newzealand_social_welfare_number  |rileva il numero di Social Welfare neozelandese|no|
|Func_north_carolina_drivers_license_number|rileva il numero di licenza del conducente del North Carolina|no|
|Func_north_dakota_drivers_license_number|rileva il numero di licenza del conducente del Dakota del Nord|no|
|Func_norway_id_number  |rileva il numero ID Norvegia|no|
|Func_nova_scotia_drivers_license_number|rileva il numero della patente di guida di Nova Scotia|no|
|Func_ohio_drivers_license_number   |rileva il numero di patente del conducente Ohio|no|
|Func_ontario_drivers_license_number    |rileva il numero di patente dell'Ontario|no|
|Func_pennsylvania_drivers_license_number|rileva il numero della patente di guida Pennsylvania|no|
|Func_pesel_identification_number   |rileva la Polonia National ID (PESEL)|no|
|Func_poland_eu_tax_file_number |rileva il numero di file fiscale Polonia|no|
|Func_polish_national_id    |rileva la scheda di identità della Polonia|no|
|Func_polish_passport_number    |rileva il numero di passaporto polacco|no|
|Func_polish_regon_number   |rileva il numero di REGOia polacco|no|
|Func_portugal_eu_tax_file_number|rileva il numero di identificazione fiscale del Portogallo|no|
|Func_prince_edward_island_drivers_license_number|rileva il numero di patente del conducente del Principe Edoardo Island|no|
|Func_quebec_drivers_license_number |rileva il numero di licenza del conducente del Quebec|no|
|Func_randomized_formatted_ssn  |rileva la modalità randomizzata in formato US SSN|sì|
|Func_randomized_unformatted_ssn|rileva randomizzati non formattati US SSN|sì|
|Func_rhode_island_drivers_license_number|rileva il numero di patente del conducente di Rhode Island|no|
|Func_romania_eu_national_id_card   |rileva il codice numerico personale Romania (CNP)|no|
|Func_saskatchewan_drivers_license_number|rileva il numero di patente del conducente Saskatchewan|no|
|Func_slovakia_eu_national_id_card  |rileva il numero personale della Slovacchia|no|
|Func_slovenia_eu_national_id_card  |rileva il numero di Citizen Master Unique Slovenia|no|
|Func_slovenia_eu_tax_file_number   |rileva il numero di file fiscale sloveno|no|
|Func_south_africa_identification_number|rileva il numero di identificazione dell'Africa del sud|sì|
|Func_south_carolina_drivers_license_number|rileva il numero di patente del conducente della Carolina del sud|no|
|Func_south_dakota_drivers_license_number|rileva il numero di patente del conducente del Sud Dakota|no|
|Func_south_korea_resident_number   |rileva il numero residente in Corea del sud|no|
|Func_spain_eu_DL_and_NI_number_citizen |rileva la Spagna DL e il numero NI Citizen|no|
|Func_spain_eu_DL_and_NI_number_foreigner|rileva la Spagna DL e il numero NI Foreigner|no|
|Func_spain_eu_driver ' s_license_number  |rileva il numero della patente di guida della Spagna|no|
|Func_spain_eu_tax_file_number  |rileva il numero di file fiscale della Spagna|no|
|Func_spanish_social_security_number|rileva il numero di previdenza sociale spagnolo|no|
|Func_ssn   |Funzione per rilevare non randomizzati formato US SSN|sì|
|Func_sweden_eu_tax_file_number|rileva il numero di file delle tasse svedesi|no|
|Func_swedish_national_identifier|rileva l'identificatore nazionale svedese|sì|
|Func_swiss_social_security_number_ahv|rileva il numero di previdenza sociale svizzero AVS|no|
|Func_taiwanese_national_id |rileva l'ID nazionale taiwanese|no|
|Func_tennessee_drivers_license_number|rileva il numero di licenza di Tennessee driver|no|
|Func_texas_drivers_license_number  |rileva il numero della patente di guida Texas|no|
|Func_Thai_Citizen_Id   |rileva l'ID del cittadino tailandese|no|
|Func_Turkish_National_Id|rileva l'ID nazionale turco|sì|
|Func_uk_drivers_license|rileva la licenza del conducente del Regno Unito|no|
|Func_uk_eu_tax_file_number|rileva il numero del contribuente unico nel Regno Unito|no|
|Func_uk_nhs_number |rileva il numero NHS del Regno Unito|sì|
|Func_uk_nino   |rileva il Regno Unito NINO|no|
|Func_unformatted_canadian_sin|rileva i peccati canadesi non formattati|no|
|Func_unformatted_itin  |rileva la formattazione non formattata negli Stati Uniti|sì|
|Func_unformatted_ssn   |rileva la non-randomizzazione del SSN statunitense|sì|
|Func_usa_uk_passport   |rileva gli Stati Uniti e il passaporto del Regno Unito|sì|
|Func_utah_drivers_license_number|rileva il numero di licenza del conducente di Utah|no|
|Func_vermont_drivers_license_number|rileva il numero di patente del conducente del Vermont|no|
|Func_virginia_drivers_license_number|rileva il numero della patente di guida di Virginia|no|
|Func_washington_drivers_license_number|rileva il numero di patente del conducente di Washington|no|
|Func_west_virginia_drivers_license_number|rileva il numero di patente del conducente West Virginia|no|
|Func_wisconsin_drivers_license_number  |rileva il numero della patente di guida del Wisconsin|no|
|Func_wyoming_drivers_license_number    |rileva il numero della patente di guida del Wyoming|no|


## <a name="func_us_date"></a>Func_us_date

Func_us_date Cerca date nei formati comuni degli Stati Uniti. I formati comuni sono "month/day/year", "month-day-year" e "month day year". I nomi o le abbreviazioni dei mesi non sono distinzione tra maiuscole e minuscole. 
  
Esempi:
  
- 2 dicembre 2016
    
- 2 dicembre 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates Cerca date in common use formati (e la maggior parte delle posizioni al di fuori degli Stati Uniti), ad esempio "Day/Month/Year", "Day-Month-Year" e "Day Month Year". I nomi o le abbreviazioni dei mesi non sono distinzione tra maiuscole e minuscole.
  
Esempi:
  
- 2 dicembre 2016
    
- 02 dicembre 2016
    
- 2 dicembre 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dec-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.
    
- Olandese
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec
    
- Francese
    
  - Janvier, février, Mars, avril, mai, Juin Juillet, août, septembre, Octobre, novembre, décembre
    
  - janv. févr. Mars Avril mai juin juil. août sett. personalizzazione. novembre. déc.
    
- Tedesco
    
  - jänuar, febbraio, März, April, mai, Juni Juli, August, September, Oktober, November, Dezember
    
  - Gen./Jän. Feb. März apr. mai Juni luglio Okt. Nov. dic.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Genn. febbr. mar. apr. magg. giugno luglio AG. ovvero. ott. novembre. dic.
    
- Portoghese
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV Mar ABR mai Jun Jul ago set out nov dic
    
- Spagnolo
    
  - enero, febrero, marzo, Abril, Mayo, Junio, Julio, agosto, Septiembre, Octubre, Noviembre, Diciembre
    
  - enero feb. marzo ABR. Mayo Jun. luglio. agosto Sept/set. personalizzazione. novembre. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (obsoleto)

> [!NOTE]
> Questa funzione è obsoleta perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella  `Func_eu_date` funzione precedente. 
  
Questa funzione consente di cercare una data nel formato comunemente utilizzato in portoghese. Il formato di questa funzione è lo stesso che  `Func_eu_date` differisce solo nella lingua utilizzata.
  
Esempi:
  
- 2 (2016).
    
- 02 (2016).
    
- 2 con il 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-------2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Portoghese
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV Mar ABR mai Jun Jul ago set out nov dic
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (obsoleto)

> [!NOTE]
> Questa funzione è obsoleta perché supporta solo i nomi dei mesi olandesi, che ora sono inclusi nella  `Func_eu_date` funzione precedente. 
  
Questa funzione consente di cercare una data nel formato comunemente utilizzato in olandese. Il formato di questa funzione è lo stesso che  `Func_eu_date` differisce solo nella lingua utilizzata.
  
Esempi:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Olandese
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart apr Mei giu lug Aug Sep set out Okt Nov Dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date Cerca date che si trovano in formati comunemente usati dalle carte di credito e di debito. Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year". I nomi o le abbreviazioni dei mesi non sono distinzione tra maiuscole e minuscole.
  
Esempi:
  
- MM/AA -- ad esempio, 01/11 o 1/11
    
- MM/AAAA -- ad esempio, 01/2011 o 1/2011
    
- MM-AA -- ad esempio, 01-22 o 1-11
    
- MM-AAAA-- ad esempio, 01-2000 o 1-2000
    
I formati seguenti supportano AA o AAAA:
  
- Mese-AAAA--ad esempio gen-2010 o gennaio-2010 o gen-10 o gennaio-10
    
- Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"
    
- MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"
    
- Mese/AAAA--ad esempio, "gennaio/2010" o "gen/2010" o "gennaio/10" o "gen/10"
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address Cerca un nome di stato degli Stati Uniti o una sigla postale seguita da un CAP valido. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.
  
Esempi:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
