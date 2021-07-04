---
title: Tipi di file supportati in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Elenco dei tipi di file supportati in Microsoft 365 Advanced eDiscovery, inclusi i tipi di file di immagine supportati dalla funzionalità OCR in Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a637dc0505b74a2b7f7d726ed9a731db8e68c12
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288108"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Tipi di file supportati in Advanced eDiscovery

Advanced eDiscovery supporta molti tipi di file a diversi livelli. I tipi di file di supporto sono descritti nelle tabelle seguenti di questo articolo. Questo elenco non è finalizzato e verranno aggiunti nuovi tipi di file mentre si prosegue il test di convalida. Queste tabelle indicano se un tipo di file è supportato per l'estrazione del testo (e riconoscimento ottico dei caratteri o estrazione del testo OCR per i file di immagine), visualizzabile nel visualizzatore nativo e supportato anche nel visualizzatore Annotate in Advanced eDiscovery.

## <a name="archive--container"></a>Archivio/Contenitore

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione contenitore|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|
|application/x-7z-compressed|Sì|Sì|Sì|.7z|
|application/x-rar-compressed|Sì|Sì|Sì|.rar|
|application/x-tar|Sì|Sì|Sì|.tar|
|application/zip|Sì|Sì|Sì|.zip|
|

## <a name="audio--video"></a>Audio/Video

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/mp4|Sì|Sì|No|Sì|No|.f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; .mpeg4|
|audio/mpeg|Sì|Sì|No|Sì|No|.mpeg|
|video/3gpp|Sì|Sì|No|Sì|No|.3gp|
|video/3gpp2|Sì|Sì|No|Sì|No|.3g2; .3gp2|
|video/quicktime|Sì|Sì|No|Sì|No|.moov; .mov; .qt|
|video/x-m4v|Sì|Sì|No|Sì|No|.m4v|
|

## <a name="database"></a>Database

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-msaccess|Sì|Sì|Sì|No|No|.mdb|
|

## <a name="email"></a>Posta elettronica

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-outlook|Sì|Sì|Sì|Sì|Sì|.msg|
|message/rfc822|Sì|Sì|Sì|Sì|Sì|.eml|
|text/vcard-contact|Sì|Sì|Sì|Sì|Sì|.vcf|
|

## <a name="email-container"></a>Contenitore posta elettronica

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione contenitore|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|
|application/mbox|Sì|Sì|Sì|.mbox|
|application/vnd.ms-outlook-pst|Sì|Sì|Sì|.pst|
|

## <a name="html"></a>HTML

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/xhtml+xml|Sì|Sì|Sì|Sì|Sì|.xhtml|
|application/xml|Sì|Sì|Sì|Sì|Sì|.xml|
|text/html|Sì|Sì|Sì|Sì|Sì|.htm; .html; .shtml|
|

## <a name="image"></a>Immagine

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione del testo OCR|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|image/bmp|Sì|Sì|Sì|Sì|Sì|.bmp|
|image/emf|Sì|Sì|Sì|Sì|Sì|.emf|
|image/gif|Sì|Sì|Sì|Sì|Sì|.gif|
|image/jpeg|Sì|Sì|Sì|Sì|Sì|.jpeg; .jpg|
|image/png|Sì|Sì|Sì|Sì|Sì|.png|
|image/svg+xml|Sì|Sì|Sì|Sì|No|.svg|
|image/tiff|Sì|Sì|Sì|Sì|Sì|.tif|
|image/vnd.dwg|Sì|Sì|Sì|Sì|Sì|.dwg; .dxf|
|image/wmf|Sì|Sì|Sì|Sì|Sì|.wmf|
|

## <a name="microsoft-excel"></a>Microsoft Excel

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-excel|Sì|Sì|Sì|Sì|Sì|.dat; .xls|
|application/vnd.ms-excel.sheet.binary.macroenabled.12|Sì|Sì|Sì|Sì|No|.xlsb|
|application/vnd.ms-excel.sheet.macroenabled.12|Sì|Sì|Sì|Sì|Sì|.xlsm|
|application/vnd.ms-excel.template.macroenabled.12|Sì|Sì|Sì|No|No|.xltm|
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet|Sì|Sì|Sì|Sì|Sì|.xlsx|
|application/vnd.openxmlformats-officedocument.spreadsheetml.template|Sì|Sì|Sì|Sì|Sì|.xltx|
|

## <a name="microsoft-onenote"></a>Microsoft OneNote

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/onenote|Sì|Sì|Sì|No|No|.one|
|

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-powerpoint|Sì|Sì|Sì|Sì|Sì|.pot; .pps; .ppt|
|application/vnd.openxmlformats-officedocument.presentationml.presentation|Sì|Sì|Sì|Sì|Sì|.pptx|
|application/vnd.openxmlformats-officedocument.presentationml.slideshow|Sì|Sì|Sì|Sì|Sì|.ppsx|
|application/vnd.openxmlformats-officedocument.presentationml.template|Sì|Sì|Sì|Sì|Sì|.potx|
|

## <a name="microsoft-project"></a>Microsoft Project

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-project|Sì|Sì|Sì|No|Sì|.mpp|
|

## <a name="microsoft-publisher"></a>Microsoft Publisher

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-mspublisher|Sì|Sì|Sì|Sì|Sì|.pub|
|

## <a name="microsoft-visio"></a>Microsoft Visio

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-visio.drawing|Sì|Sì|Sì|Sì|No||
|application/vnd.visio|Sì|Sì|Sì|Sì|Sì|.vsd|
|

## <a name="microsoft-word"></a>Microsoft Word

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/msword|Sì|Sì|Sì|Sì|Sì|.dat; .doc|
|application/rtf|Sì|Sì|Sì|Sì|Sì|.doc; .rtf|
|application/vnd.ms-word.document.macroenabled.12|Sì|Sì|Sì|Sì|Sì|.docm|
|application/vnd.ms-word.template.macroenabled.12|Sì|Sì|Sì|Sì|Sì|.dotm|
|application/vnd.openxmlformats-officedocument.wordprocessingml.document|Sì|Sì|Sì|Sì|Sì|.docx|
|application/vnd.openxmlformats-officedocument.wordprocessingml.template|Sì|Sì|Sì|Sì|Sì|.dotx|
|

## <a name="microsoft-works"></a>Microsoft Works

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-works-ss|Sì|Sì|No|No|No|.wps|
|application/vnd.ms-works-wp|Sì|Sì|No|No|No|.wps|
|

## <a name="open-document-format"></a>Apri formato documento

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.oasis.opendocument.text|Sì|Sì|Sì|Sì|Sì|.odt|
|

## <a name="other"></a>Altro

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/json|Sì|Sì|Sì|Sì|Sì|n/d|
|application/vnd.ms-graph|Sì|Sì|No|No|No||
|application/winhlp|Sì|Sì|No|No|No|.hlp|
|application/x-tnef|Sì|Sì|No|No|No||
|

## <a name="plain-text"></a>Testo normale

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|text/csv|Sì|Sì|Sì|Sì|Sì|.csv|
|text/plain|Sì|Sì|Sì|Sì|Sì|.con; .css; .csv; .dat; .pl; .txt|
|

## <a name="portable-document-format"></a>PDF (Portable Document Format)

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/pdf|Sì|Sì|Sì|Sì|Sì|.pdf|
|

## <a name="word-perfect"></a>Word Perfect

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.wordperfect; version=5.0|Sì|Sì|Sì|No|No|.wpd|
|application/vnd.wordperfect; version=5.1|Sì|Sì|Sì|No|No|.wpd|
|application/vnd.wordperfect; version=6.x|Sì|Sì|Sì|No|No|.wpd|
|

## <a name="word-pro"></a>Word Pro

<br>

****

|Tipo mime|Identificazione file|Estrazione metadati|Estrazione di testo|Visualizzatore nativo|Visualizzatore di annotazioni|Estensioni possibili|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.lotus-wordpro|Sì|Sì|No|No|No|.lwp|
|
