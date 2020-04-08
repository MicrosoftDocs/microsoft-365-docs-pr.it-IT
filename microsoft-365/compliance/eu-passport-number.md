---
title: Numero di passaporto EU
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592117"
---
# <a name="eu-passport-number"></a>Numero di passaporto EU

In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Una lettera seguita da uno spazio facoltativo e sette cifre
  
### <a name="pattern"></a>Modello

Combinazione di una lettera, sette cifre e uno spazio:
  
- Una lettera (senza distinzione tra maiuscole/minuscole)
    
- Uno spazio (facoltativo)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto austriaco  <br/> Passport No  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

Due lettere seguite da sei cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere e seguite da sei cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto belga  <br/> Passport No  <br/> paspoort  <br/> paspoortnummer  <br/> Reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto bulgaro  <br/> Passport No  <br/> Номер на паспорта  <br/> |
   
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto croato  <br/> Passport No  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

Una lettera seguita da 6-8 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una lettera seguita da sei a otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto di Cipro  <br/> Passport No  <br/> αριθμό διαβατηρίου  <br/> |
   
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Otto cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre senza spazi o delimitatori
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto ceco  <br/> Passport No  <br/> Cestovní pas  <br/> pas  <br/> |
   
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto danese  <br/> Passport No  <br/> pas  <br/> Pasnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Una lettera seguita da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una lettera seguita da sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto estone  <br/> Passport No  <br/> passaggio kodaniku Eesti  <br/> |
   
## <a name="finland"></a>Finlandia

Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per informazioni dettagliate, vedere la sezione "numero di passaporto tedesco" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Due lettere seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere seguite da 7 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto greco  <br/> Passport No  <br/> διαβατηριο  <br/> |
   
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Due lettere seguite da sei o sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere seguite da sei o sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto ungherese  <br/> Passport No  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Due lettere o cifre seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere o cifre seguite da sette cifre:
  
- Due cifre o lettere (senza distinzione tra maiuscole/minuscole)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto irlandese  <br/> Passport No  <br/> pas  <br/> passaporto  <br/> Passeport  <br/> numero Passeport  <br/> |
   
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Due lettere o cifre seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere o cifre seguite da sette cifre:
  
- Due cifre o lettere (senza distinzione tra maiuscole/minuscole)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|numero di passaporto italiano  <br/> Repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> passport number  <br/> italiana passaporto numero  <br/> Numero passaporto  <br/> numéro Passeport Italien  <br/> numéro Passeport  <br/> |
   
## <a name="latvia"></a>Lettonia

### <a name="format"></a>Formato

Due lettere o cifre seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere o cifre seguite da sette cifre:
  
- Due cifre o lettere (senza distinzione tra maiuscole/minuscole)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto lettone  <br/> Passport No  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Otto cifre o lettere senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto di lithunian  <br/> Passport No  <br/> numero di Paso  <br/> |
   
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

Otto cifre o lettere senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto lettone  <br/> Passport No  <br/> passnummer  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

 Sette cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto maltese  <br/> Passport No  <br/> numru tal-passaport  <br/> |
   
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

Nove lettere o cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Nove lettere o cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|numero di passaporto olandese  <br/> passport number  <br/> numero di passaporto per i Paesi Bassi  <br/> Nederlanden PASPOORT Nummer  <br/> paspoort  <br/> Nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>Polonia

Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portogallo

### <a name="format"></a>Formato

Una lettera seguita da sei cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una lettera seguita da sei cifre:
  
- Una lettera (senza distinzione tra maiuscole/minuscole)
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto portoghese  <br/> Passport No  <br/> número do passaporte  <br/> |
   
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

Otto o nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

Otto o nove cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto rumeno  <br/> Passport No  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto slovacco  <br/> Passport No  <br/> číslo Pasu  <br/> |
   
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

Due lettere seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere seguite da sette cifre:
  
- La lettera "P"
    
- Una lettera maiuscola
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|passport number  <br/> numero di passaporto sloveno  <br/> Passport No  <br/> številka potnega lista  <br/> |
   
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Combinazione di lettere e numeri di otto o nove caratteri:
  
-  Due cifre o lettere 
    
- Una cifra o una lettera (facoltativa)
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|passaporto  <br/> passaporto della Spagna  <br/> libro del passaporto  <br/> passport number  <br/> Passport No  <br/> libreta pasaporte  <br/> número pasaporte  <br/> pasaporte España  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>Svezia

Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).
  
## <a name="uk"></a>Regno Unito

Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vedere anche

[Tipi di informazioni riservate disponibili da cercare](what-the-sensitive-information-types-look-for.md)

