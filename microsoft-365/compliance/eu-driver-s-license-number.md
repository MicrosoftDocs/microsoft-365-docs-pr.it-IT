---
title: Numero della patente di guida dell'Unione europea
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592657"
---
# <a name="eu-drivers-license-number"></a>Numero della patente di guida dell'Unione europea

In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from. 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_austria_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/>  numero della patente di guida  <br/> dlno #  <br/> fuhrerschein  <br/> fuhrerschein Republik Osterreich  <br/> |
   
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords__belgium_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> Führerschein-Nr  <br/> fuehrerschein-Nr  <br/> fuehrerschein-Nr  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_bulgaria_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> свидетелство за управление на мпс  <br/> свидетелство за управление на моторно превозно d'средство  <br/> сумпс  <br/> шофьорска книжка  <br/> |
   
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

Otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_croatia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

12 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

12 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_cyprus_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> άδεια οδήγησης  <br/> |
   
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Otto lettere e cifre:
  
- Due lettere (senza distinzione tra maiuscole e minuscole)
    
- Uno spazio (facoltativo)
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_czech_republic_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_denmark_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> kørekort  <br/> Kørekortnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Due lettere e sei cifre:
  
-  Lettere "ET" (senza distinzione tra maiuscole e minuscole) 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_estonia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero della patente di guida  <br/> dlno #  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

10 cifre contenenti una lineetta
  
### <a name="pattern"></a>Modello

10 cifre contenenti un trattino:
  
-  Sei cifre 
    
- Una lineetta
    
-  Quattro cifre 
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_finland_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>Francia

Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_greece_eu_driver ' s_license_number**|
|:-----|
|dlL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> δεια οδήγησης  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Due lettere e sei cifre:
  
-  Due lettere (senza distinzione tra maiuscole e minuscole) 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_hungary_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Sei cifre seguite da quattro lettere
  
### <a name="pattern"></a>Modello

Sei cifre e quattro lettere:
  
- Sei cifre
    
- Quattro lettere (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_ireland_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>Italia

Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="latvia"></a>Lettonia

### <a name="format"></a>Formato

Tre lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Tre lettere e sei cifre:
  
-  Tre lettere (senza distinzione tra maiuscole e minuscole) 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_latvia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Otto cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 Otto cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_lithuania_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

Sei cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 Sei cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_luxemburg_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Combinazione di due caratteri e di sei cifre nel modello specificato
  
### <a name="pattern"></a>Modello

Combinazione di due caratteri e di sei cifre:
  
- Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)
    
- Uno spazio (facoltativo)
    
- Tre cifre
    
- Uno spazio (facoltativo)
    
- Tre cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from. 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_malta_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> Liċenzja TAS-sewqan  <br/> |
   
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

10 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_netherlands_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

14 cifre contenenti 2 barre
  
### <a name="pattern"></a>Modello

14 cifre e 2 barre:
  
-  Cinque cifre 
    
- Una barra
    
- Due cifre
    
- Una barra
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_poland_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>Portogallo

### <a name="format"></a>Formato

Due lettere seguite da un numero di sette numeri nel modello specificato
  
### <a name="pattern"></a>Modello

Due lettere seguite da sette numeri con caratteri speciali:
  
-  Due lettere (senza distinzione tra maiuscole e minuscole) 
    
- Una lineetta
    
- Sei cifre
    
- Uno spazio
    
- Una cifra
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_portugal_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

Un carattere seguito da otto cifre
  
### <a name="pattern"></a>Modello

Un carattere seguito da otto cifre:
  
-  Una lettera (senza distinzione tra maiuscole e minuscole) o cifra 
    
- Otto cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_romania_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> Permis de conducere  <br/> |
   
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

Un carattere seguito da sette cifre
  
### <a name="pattern"></a>Modello

Un carattere seguito da sette cifre
  
- Una lettera (senza distinzione tra maiuscole e minuscole) o cifra
    
-  Sette cifre 
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovakia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovenia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Otto cifre seguite da un carattere
  
### <a name="pattern"></a>Modello

Otto cifre seguite da un carattere:
  
-  Otto cifre 
    
- Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_spain_eu_driver ' s_license_number**|
|:-----|
|dlno #  <br/> DL #  <br/> driver Lic.  <br/> patente di guida  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> driving licence  <br/> driving license  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> numero di patente di guida  <br/> numero della patente di guida  <br/> permesso di guida  <br/> numero di licenza di guida  <br/> Permiso de conducción  <br/> Permiso conducción  <br/> número licencia conducir  <br/> número de carnet de conducir  <br/> número carnet conducir  <br/> licencia conducir  <br/> número de Permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> El carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>Svezia

### <a name="format"></a>Formato

Dieci cifre contenenti un segno meno
  
### <a name="pattern"></a>Modello

Dieci cifre contenenti un trattino:
  
-  Sei cifre 
    
- Una lineetta
    
- Quattro cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_sweden_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> numero della patente di guida  <br/> patente di guida  <br/> driver Lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> numero della patente di guida  <br/> numero di patente del conducente  <br/> numero della patente di guida  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>Regno Unito

Per informazioni dettagliate, vedere la sezione "Regno Unito Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vedere anche

[Tipi di informazioni riservate disponibili da cercare](what-the-sensitive-information-types-look-for.md)

