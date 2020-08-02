---
title: Cosa cercano le funzioni di prevenzione della perdita di dati (DLP)
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
description: Informazioni sulle funzioni di prevenzione della perdita di dati (DLP, Data Loss Prevention).
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536311"
---
# <a name="what-the-dlp-functions-look-for"></a>Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati

La prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, ad esempio il numero di carta di credito e il numero di carta di debito dell'Unione europea, che sono pronti per l'utilizzo nei criteri DLP. Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.
  
In questo articolo vengono illustrate le funzionalità che devono essere cercate per comprendere il funzionamento dei tipi di informazioni riservate predefinite. Per ulteriori informazioni, vedere [definizioni di entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)
  
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

Questa funzione Cerca una data nel formato comunemente utilizzato nell'Unione (e la maggior parte delle posizioni al di fuori degli Stati Uniti), ad esempio "Day/Month/Year", "Day-Month-Year" e "Day Month Year". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.
  
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
    
  - Jan Feb maart apr Mei giu lug Aug Sep set out Okt Nov Dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Questa funzione consente di cercare una data nei formati comunemente utilizzati da carte di credito e di debito, sostituendo i giorni con i mesi. Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.
  
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
  
- English
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Questa funzione consente di cercare un nome di stato americano o una sigla postale seguita da un CAP valido, così come viene utilizzato negli indirizzi postali. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.
  
Esempi:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

