---
title: Cosa individuano le funzioni DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
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
description: Informazioni sul funzionamento delle funzioni di prevenzione della perdita di dati (DLP), per comprendere come funzionano i tipi di informazioni riservate predefinite.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819276"
---
# <a name="what-the-dlp-functions-look-for"></a>Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati

Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.
  
In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti. Per ulteriori informazioni, vedere [definizioni di entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)
  
## <a name="func_us_date"></a>Func_us_date

Questa funzione Cerca una data nel formato comunemente utilizzato negli Stati Uniti. Sono inclusi i formati "month/day/year", "month-day-year" e "month day year". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole. 
  
Esempi:
  
- 2 dicembre 2016
    
- 2 dicembre 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nomi dei mesi accettati:
  
- English
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.
  
Esempi:
  
- 2 dicembre 2016
    
- 02 dicembre 2016
    
- 2 dicembre 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dec-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- English
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.
    
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec
    
- French
    
  - Janvier, février, Mars, avril, mai, Juin Juillet, août, septembre, Octobre, novembre, décembre
    
  - janv. févr. Mars Avril mai juin juil. août sett. personalizzazione. novembre. déc.
    
- German
    
  - jänuar, febbraio, März, April, mai, Juni Juli, August, September, Oktober, November, Dezember
    
  - Gen./Jän. Feb. März apr. mai Juni luglio Okt. Nov. dic.
    
- Italian
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Genn. febbr. mar. apr. magg. giugno luglio AG. ovvero. ott. novembre. dic.
    
- Portoghese
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan FEV Mar ABR mai Jun Jul ago set out nov dic
    
- Spanish
    
  - enero, febrero, marzo, Abril, Mayo, Junio, Julio, agosto, Septiembre, Octubre, Noviembre, Diciembre
    
  - enero feb. marzo ABR. Mayo Jun. luglio. agosto Sept/set. personalizzazione. novembre. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (obsoleto)

> [!NOTE]
> Questa funzione è obsoleta perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella `Func_eu_date` funzione precedente. 
  
Questa funzione consente di cercare una data nel formato comunemente utilizzato in portoghese. Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.
  
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
> Questa funzione è obsoleta perché supporta solo i nomi dei mesi olandesi, che ora sono inclusi nella `Func_eu_date` funzione precedente. 
  
Questa funzione consente di cercare una data nel formato comunemente utilizzato in olandese. Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.
  
Esempi:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Questa funzione consente di cercare una data nei formati comunemente utilizzati da carte di credito e di debito, sostituendo i giorni con i mesi. Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.
  
Esempi:
  
- MM/AA -- ad esempio, 01/11 o 1/11
    
- MM/AAAA -- ad esempio, 01/2011 o 1/2011
    
- MM-AA -- ad esempio, 01-22 o 1-11
    
- MM-AAAA-- ad esempio, 01-2000 o 1-2000
    
I formati seguenti supportano AA o AAAA:
  
- Mese-AAAA -- ad esempio, .Gen-2010 o gennaio-2010 o Gen-10 o gennaio-10
    
- Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"
    
- MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"
    
- Mese/AAAA--ad esempio, "gennaio/2010" o "gen/2010" o "gennaio/10" o "gen/10"
    
Nomi dei mesi accettati:
  
- English
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.
  
Esempi:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

