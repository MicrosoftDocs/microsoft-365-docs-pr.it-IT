---
title: Ricerca delle funzioni di prevenzione della perdita dei dati (DLP)
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
description: Informazioni sulle funzioni di prevenzione della perdita dei dati (DLP).
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841447"
---
# <a name="what-the-dlp-functions-look-for"></a>Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati

I criteri di prevenzione della perdita dei dati (DLP) possono utilizzare i tipi di informazioni riservate per identificare gli elementi sensibili. Il numero di carta di credito e il numero di carta di debito dell'Unione Europea sono esempi di tipi di informazioni riservate. I tipi di informazioni riservate ricercano modelli specifici. I tipi di informazioni riservate convalidano i dati osservandone il formato, i checksum e cercando parole chiave o altre informazioni pertinenti. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate Numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza. Ciò consente di confermare che un numero è un numero di carta di credito.
  
In questo articolo vengono illustrate le funzioni ricercate per comprendere il funzionamento dei tipi di informazioni riservate predefiniti. Per ulteriori informazioni, vedere [Definizioni delle entità del tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Tabella delle funzioni

|nome funzione  |azione funzione  |è un validator|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|rileva e convalida la chiave fiscale univoca dell'Argentina|no|
|Func_aba_routing|rileva il numero di routing ABA| sì|
|Func_alabama_drivers_license_number|rileva il numero di patente di guida dell'Alabama|no|
|Func_alaska_delaware_oregon_drivers_license_number|rileva il numero di patente di guida di Alaska, Delaware, Oregon|no|
|Func_alaska_drivers_license_number|rileva il numero della patente di guida dell'Alaska|no|
|Func_alberta_drivers_license_number|rileva il numero di patente di guida di Alberta|no|
|Func_Argentina_Unique_Tax_Key|rileva la chiave fiscale univoca dell'Argentina|no|
|Func_arizona_drivers_license_number|rileva il numero di patente di guida di Arizona|no|
|Func_arkansas_drivers_license_number|rileva il numero di patente di guida dell'Arkansas|no|
|Func_australian_business_number|rileva il numero di azienda australiano|no|
|Func_Australian_Company_Number|rileva il numero di società australiano|no|
|Func_australian_medical_account_number|rileva il numero di conto medico dell'Australia|no|
|Func_australian_tax_file_number|rileva il numero di file fiscale australia|sì|
|Func_austria_eu_ssn_or_equivalent|rileva il numero di previdenza sociale dell'Austria|no|
|Func_austria_eu_tax_file_number|rileva il numero di file fiscale Austria|no|
|Func_Austria_Value_Added_Tax|rileva l'imposta sul valore aggiunto dell'Austria|no|
|Func_belgium_national_number|rileva il numero nazionale del Belgio|no|
|Func_belgium_value_added_tax_number|rileva il numero di imposta sul valore aggiunto del Belgio|no|
|Func_brazil_cnpj|rileva il numero di persona giuridica del Brasile (CNPJ)|sì|
|Func_brazil_cpf|rileva CPF Brasile|sì|
|Func_brazil_rg|rileva RG Brasile|no|
|Func_british_columbia_drivers_license_number|rileva il numero di patente di guida della British Columbia|no|
|Func_bulgaria_eu_national_id_card|rileva il numero civile uniforme bulgaro|no|
|Func_california_drivers_license_number|rileva il numero della patente di guida in California|no|
|Func_canadian_sin|rileva il canada sin|sì|
|Func_chile_id_card|rileva la carta d'identità del Cile|no|
|Func_china_resident_id|rileva l'ID residente in Cina|no|
|Func_colorado_drivers_license_number|rileva il numero della patente di guida|no|
|Func_connecticut_drivers_license_number|rileva il numero di patente di guida connecticut|no|
|Func_credit_card|rileva la carta di credito|sì|no|
|Func_croatia_id_card|rileva la carta d'identità della Croazia|no|
|Func_croatia_oib_number|rileva il numero OIB della Croazia|no|
|Func_cyprus_eu_tax_file_number|rileva il numero di file fiscale di Cipro|no|
|Func_czech_id_card|rileva la carta d'identità ceco|no|
|Func_czech_id_card_new_format|rileva la carta d'identità ceco nel nuovo formato|no|
|Func_dea_number|rileva il numero DEA|sì|
|Func_denmark_eu_tax_file_number|rileva il numero di identificazione personale della Danimarca|no|
|Func_district_of_columbia_drivers_license_number|rileva il numero di patente di guida del Distretto di Colombia|no|
|Func_estonia_eu_national_id_card|rileva il codice di identificazione personale dell'Estonia|no|
|Func_eu_debit_card|rileva la carta di debito dell'Unione Europea|no|
|Func_finnish_national_id|rileva l'ID nazionale finlandese|no|
|Func_florida_drivers_license_number|rileva il numero della patente di guida in Usa|no|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|rileva il numero di patente di guida in Nord America, Maryland, Stati Uniti|no|
|Func_formatted_itin|rileva l'ITIN statunitense formattato|sì|
|Func_fr_insee|rileva l'INSEE francese|no|
|Func_fr_passport|rileva il passaporto francese|no|
|Func_france_eu_tax_file_number|rileva il numero di file fiscale francese|no|
|Func_france_value_added_tax_number|rileva il numero di imposta sul valore aggiunto della Francia|no|
|Func_french_drivers_license|rileva la patente di guida francese|no|
|Func_french_insee|rileva l'INSEE francese|no|
|Func_georgia_drivers_license_number|rileva il numero della patente di guida georgia|no|
|Func_german_drivers_license|rileva la patente di guida in Germania|no|
|Func_german_passport|rileva il passaporto tedesco|no|
|Func_german_passport_data|rileva il passaporto germania|no|
|Func_germany_eu_tax_file_number|rileva il numero di file fiscale germania|no|
|Func_germany_value_added_tax_number|rileva il numero di imposta sul valore aggiunto della Germania|no|
|Func_greece_eu_ssn|rileva il seno greco (AMKA)|no|
|Func_hawaii_drivers_license_number|rileva il numero della patente di guida delle Hawaii|no|
|Func_hong_kong_id_card |rileva la scheda ID di Hong Kong|no|
|Func_hungarian_value_added_tax_number|rileva il numero di imposta sul valore aggiunto dell'Ungheria|no|
|Func_hungary_eu_national_id_card|rileva il numero di identificazione personale dell'Ungheria|no|
|Func_hungary_eu_ssn_or_equivalent|rileva il numero di previdenza sociale dell'Ungheria|no|
|Func_hungary_eu_tax_file_number|rileva il numero di file fiscale dell'Ungheria|no|
|Func_iban|rileva IBAN|sì|
|Func_idaho_drivers_license_number|rileva il numero di patente di guida Idaho|no|
|Func_illinois_drivers_license_number|rileva il numero della patente di guida dell'Università di Chicago|no|
|Func_india_aadhaar|detects India aadhaar|sì|
|Func_indiana_drivers_license_number|rileva il numero della patente di guida dell'Indiana|no|
|Func_iowa_drivers_license_number|rileva il numero della patente di guida di Iowa|no|
|Func_ireland_pps|rileva pps Irlanda|no|
|Func_israeli_national_id_number|rileva il numero di identificazione nazionale israele|no|
|Func_italy_eu_national_id_card |rileva il codice fiscale italiano|no|
|Func_italy_value_added_tax_number|rileva il numero di imposta sul valore aggiunto dell'Italia|no|
|Func_japanese_my_number_corporate|rileva il Giappone il mio numero aziendale|sì|
|Func_japanese_my_number_personal|rileva il Giappone il mio numero personale|sì|
|Func_jp_bank_account|rileva il conto corrente bancario giapponese|no|
|Func_jp_bank_account_branch_code|rileva il codice di succursale del conto corrente bancario giapponese|no|
|Func_jp_drivers_license_number|rileva il numero della patente giapponese|no|
|Func_jp_passport|rileva il passaporto giapponese|no|
|Func_jp_resident_registration_number|rileva il numero di registrazione residente in Giappone|no|
|Func_jp_sin|rileva il sin giappone|no|
|Func_jp_sin_pre_1997|rileva il seno giapponese prima del 1997|no|
|Func_kansas_drivers_license_number|rileva il numero della patente di guida di Kansas|no|
|Func_kentucky_drivers_license_number|rileva il numero di patente di guida di Dio|no|
|Func_kentucky_massachusetts_virginia_drivers_license_number|rileva il numero di patente di guida di Alaskaucky, Massachusetts, Virginia|no|
|Func_latvia_eu_national_id_card|rileva il codice personale lettone|no|
|Func_lithuania_eu_tax_file_number|rileva il codice personale della Lituania|no|
|Func_louisiana_drivers_license_number|rileva il numero di patente di guida della Louisiana|no|
|Func_luxemburg_eu_tax_file_number|rileva il numero di identificazione nazionale (persone fisiche)|no|
|Func_luxemburg_eu_tax_file_number_non_natural|rileva il numero di identificazione nazionale di Lussemburgo (persone non fisiche)|no|
|Func_maine_drivers_license_number|rileva il numero della patente di guida del Maine|no|
|Func_manitoba_drivers_license_number|rileva il numero di patente di guida manitoba|no|
|Func_maryland_drivers_license_number|rileva il numero della patente di guida del Maryland|no|
|Func_massachusetts_drivers_license_number|rileva il numero di patente di guida del Massachusetts|no|
|Func_mexico_population_registry_code|rileva il codice del Registro di sistema della popolazione in Messico|no|
|Func_michigan_minnesota_drivers_license_number|rileva il numero di patente di guida di Certosa|no|
|Func_minnesota_drivers_license_number|rileva il numero della patente di guida di Minnesota|no|
|Func_mississippi_oklahoma_drivers_license_number|rileva il numero di patente di guida di Unisas, Disas.|no|
|Func_missouri_drivers_license_number|rileva il numero della patente di guida di Missouri|no|
|Func_montana_drivers_license_number|rileva il numero della patente di guida di Taye|no|
|Func_nebraska_drivers_license_number|rileva il numero di patente di guida nebraska|no|
|Func_netherlands_bsn|rileva BSN Paesi Bassi|no|
|Func_netherlands_eu_tax_file_number|rileva il numero di file fiscale dei Paesi Bassi|no|
|Func_netherlands_value_added_tax_number|rileva il numero di imposta sul valore aggiunto dei Paesi Bassi|no|
|Func_nevada_drivers_license_number|rileva il numero di patente di guida di Unisa|no|
|Func_new_brunswick_drivers_license_number|rileva il numero di patente di guida di New Brunswick|no|
|Func_new_hampshire_drivers_license_number|rileva il numero di patente del New Hampshire|no|
|Func_new_jersey_drivers_license_number |rileva il numero di patente del New Jersey|no|
|Func_new_mexico_drivers_license_number |rileva il numero di patente del Nuovo Messico|no|
|Func_new_york_drivers_license_number   |rileva il numero di patente di guida di New York|no|
|Func_new_zealand_bank_account_number   |rileva il numero di conto corrente bancario della Nuova Zelanda|no|
|Func_new_zealand_inland_revenue_number |rileva il numero di ricavi dell'entroterra della Nuova Zelanda|no|
|Func_new_zealand_ministry_of_health_number|rileva il numero del ministero della sanità della Nuova Zelanda|no|
|Func_newfoundland_labrador_drivers_license_number|rileva il numero della patente di guida di Newfoundland Labrador|no|
|Func_newzealand_driver_license_number  |rileva il numero di patente di guida in Nuova Zelanda|no|
|Func_newzealand_social_welfare_number  |rileva il numero social della Nuova Zelanda|no|
|Func_north_carolina_drivers_license_number|rileva il numero di patente di guida north-10|no|
|Func_north_dakota_drivers_license_number|rileva il numero di patente di guida north-116|no|
|Func_norway_id_number  |rileva il numero ID norvegese|no|
|Func_nova_scotia_drivers_license_number|rileva il numero di patente di guida di Nova Scotia|no|
|Func_ohio_drivers_license_number   |rileva il numero della patente di guida di Unisa|no|
|Func_ontario_drivers_license_number    |rileva il numero della patente ontario|no|
|Func_pennsylvania_drivers_license_number|rileva il numero della patente di guida Disasser|no|
|Func_pesel_identification_number   |rileva l'ID nazionale della Polonia (PESEL)|no|
|Func_poland_eu_tax_file_number |rileva il numero di file fiscale della Polonia|no|
|Func_polish_national_id    |rileva la carta di identità della Polonia|no|
|Func_polish_passport_number    |rileva il numero di passaporto polacco|no|
|Func_polish_regon_number   |rileva il numero REGON polacco|no|
|Func_portugal_eu_tax_file_number|rileva il numero di identificazione fiscale del Portogallo|no|
|Func_prince_edward_island_drivers_license_number|rileva il numero di patente di guida dell'isola Diasas|no|
|Func_quebec_drivers_license_number |rileva il numero della patente di guida di Québec|no|
|Func_randomized_formatted_ssn  |rileva sSN US formattato in modo casuale|sì|
|Func_randomized_unformatted_ssn|rileva SSN US non formattato casualmente|sì|
|Func_rhode_island_drivers_license_number|rileva il numero della patente di guida dell'isola di 15 anni|no|
|Func_romania_eu_national_id_card   |rileva il codice numerico personale (CNP) della Romania|no|
|Func_saskatchewan_drivers_license_number|rileva il numero di patente di guida saskatchewan|no|
|Func_slovakia_eu_national_id_card  |rileva il numero personale della Slovacchia|no|
|Func_slovenia_eu_national_id_card  |rileva il numero cittadino master univoco sloveno|no|
|Func_slovenia_eu_tax_file_number   |rileva il numero di file fiscale della Slovenia|no|
|Func_south_africa_identification_number|rileva il numero di identificazione del Sudafrica|sì|
|Func_south_carolina_drivers_license_number|rileva il numero della patente di guida south-15|no|
|Func_south_dakota_drivers_license_number|rileva il numero di patente di guida di South Dakota|no|
|Func_south_korea_resident_number   |rileva il numero di residente della Corea del Sud|no|
|Func_spain_eu_DL_and_NI_number_citizen |rileva spagna DL e NUMERO NI citizen|no|
|Func_spain_eu_DL_and_NI_number_foreigner|rileva i numeri DL e NI spagnoli|no|
|Func_spain_eu_driver's_license_number  |rileva il numero della patente di guida spagnola|no|
|Func_spain_eu_tax_file_number  |rileva il numero di file fiscale della Spagna|no|
|Func_spanish_social_security_number|rileva il numero di previdenza sociale spagnolo|no|
|Func_ssn   |Funzione per rilevare un SSN statunitense non formattato in modo casuale|sì|
|Func_sweden_eu_tax_file_number|rileva il numero di file fiscale della Svezia|no|
|Func_swedish_national_identifier|rileva l'identificatore nazionale svedese|sì|
|Func_swiss_social_security_number_ahv|rileva il numero di previdenza sociale svizzero AVV|no|
|Func_taiwanese_national_id |rileva l'ID nazionale taiwanese|no|
|Func_tennessee_drivers_license_number|rileva il numero della patente di guida di Columbia|no|
|Func_texas_drivers_license_number  |rileva il numero di patente di guida del Texas|no|
|Func_Thai_Citizen_Id   |rileva l'ID cittadino thai|no|
|Func_Turkish_National_Id|rileva l'ID nazionale turco|sì|
|Func_uk_drivers_license|rileva la patente di guida nel Regno Unito|no|
|Func_uk_eu_tax_file_number|rileva il numero di contribuente univoco del Regno Unito|no|
|Func_uk_nhs_number |rileva il numero NHS del Regno Unito|sì|
|Func_uk_nino   |rileva NINO regno Unito|no|
|Func_unformatted_canadian_sin|rileva il SIN canadese non formattato|no|
|Func_unformatted_itin  |rileva l'ITIN degli Stati Uniti non formattato|sì|
|Func_unformatted_ssn   |rileva SSN us unformatted non casuale|sì|
|Func_usa_uk_passport   |rileva il passaporto degli Stati Uniti e del Regno Unito|sì|
|Func_utah_drivers_license_number|rileva il numero della patente di guida Disassato|no|
|Func_vermont_drivers_license_number|rileva il numero di patente di guida veghe|no|
|Func_virginia_drivers_license_number|rileva il numero della patente di guida di Virginia|no|
|Func_washington_drivers_license_number|rileva il numero della patente di guida di Washington|no|
|Func_west_virginia_drivers_license_number|rileva il numero della patente di guida di West Virginia|no|
|Func_wisconsin_drivers_license_number  |rileva il numero di patente di guida del Wisconsin|no|
|Func_wyoming_drivers_license_number    |rileva il numero di patente di guida del Wyoming|no|


## <a name="func_us_date"></a>Func_us_date

Func_us_date cercare le date nei formati comuni degli Stati Uniti. I formati comuni sono "month/day/year", "month-day-year" e "month day year". Per i nomi o le abbreviazioni dei mesi non viene maiuscole/minuscole. 
  
Esempi:
  
- 2 dicembre 2016
    
- 2 dicembre 2016
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates cercare date in E.U. comuni formati (e la maggior parte delle posizioni al di fuori degli Stati Uniti), ad esempio "giorno/mese/anno", "giorno-mese-anno" e "giorno mese anno". Per i nomi o le abbreviazioni dei mesi non viene maiuscole/minuscole.
  
Esempi:
  
- 2 dicembre 2016
    
- 02 dic 2016
    
- 2 dicembre 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dic-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.
    
- Olandese
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep sept oct okt nov dec
    
- Francese
    
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre
    
  - janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.
    
- Tedesco
    
  - jänuar, februar, märz, april, mai, juni juli, August, September, oktober, November, dezember
    
  - Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Set. Okt. Nov. Dez.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. <b0>1</ mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.
    
- Portoghese
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
- Spagnolo
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (obsoleto)

> [!NOTE]
> Questa funzione è deprecata perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella  `Func_eu_date` funzione precedente. 
  
Questa funzione consente di cercare una data nel formato comunemente utilizzato in portoghese. Il formato di questa funzione è uguale a  `Func_eu_date` , a differenza della lingua utilizzata.
  
Esempi:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Portoghese
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (obsoleto)

> [!NOTE]
> Questa funzione è deprecata perché supporta solo i nomi dei mesi in olandese, che ora sono inclusi nella  `Func_eu_date` funzione precedente. 
  
Questa funzione consente di cercare una data nel formato comunemente utilizzato in olandese. Il formato di questa funzione è uguale a  `Func_eu_date` , a differenza della lingua utilizzata.
  
Esempi:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Olandese
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep sept out okt nov dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date cercare le date in formati comunemente utilizzati dalle carte di credito e di debito. Questa funzione corrisponderà alle date nel formato "mese/anno", "mese-anno", "[nome mese] anno" e "[abbreviazione mese] anno". Per i nomi o le abbreviazioni dei mesi non viene maiuscole/minuscole.
  
Esempi:
  
- MM/AA -- ad esempio, 01/11 o 1/11
    
- MM/AAAA -- ad esempio, 01/2011 o 1/2011
    
- MM-AA -- ad esempio, 01-22 o 1-11
    
- MM-AAAA-- ad esempio, 01-2000 o 1-2000
    
I formati seguenti supportano AA o AAAA:
  
- Mese-AAAA, ad esempio gen-2010 o gennaio-2010 o gen-10 o gennaio-10
    
- Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"
    
- MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"
    
- Mese/AAAA-- ad esempio, 'gennaio/2010' o 'Gen/2010' o 'gennaio/10' o 'Gen/10'
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address ricerca di un nome di stato degli Stati Uniti o di un'abbreviazione postale seguita da un CAP valido. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.
  
Esempi:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
