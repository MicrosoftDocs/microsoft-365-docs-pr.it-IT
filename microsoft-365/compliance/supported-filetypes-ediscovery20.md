---
title: Tipi di file supportati in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Un elenco di tipi di file supportati in Microsoft 365 Advanced eDiscovery. Questo include un elenco dei tipi di file di immagine supportati dalla funzionalità OCR in Advanced eDiscovery.
ms.openlocfilehash: 562b39664dd29ff3cf738e0d3ded7cc2f0cbb21c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634634"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Tipi di file supportati in Advanced eDiscovery

Advanced eDiscovery supporta molti tipi di file a diversi livelli, descritti nelle tabelle seguenti. Questo elenco non è stato completato e verranno aggiunti nuovi tipi di file man mano che si continua il test di convalida. Queste tabelle indicano se un tipo di file è supportato per l'estrazione del testo (e il riconoscimento ottico dei caratteri o l'estrazione del testo OCR per i file di immagine), visualizzabile nel Visualizzatore nativo e supporta anche il Visualizzatore di annotazioni in Advanced eDiscovery.

## <a name="archive--container"></a>Archivio/contenitore

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del contenitore | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |
| applicazione/x-7z-compresso | Sì | Sì | Sì | .7z |
| applicazione/x-rar-compresso | Sì | Sì | Sì | . rar |
| applicazione/x-tar | Sì | Sì | Sì | . tar |
| applicazione/zip | Sì | Sì | Sì | .zip |
||||||||

## <a name="audio--video"></a>Audio/video

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| applicazione/MP4 | Sì | Sì | No | Sì | No | . F4V;. m4a;. m4v;. MP4;. mp4v;. MPEG;. MPEG4 |
| audio/MPEG | Sì | Sì | No | Sì | No | . MPEG |
| video/3GPP | Sì | Sì | No | Sì | No | .3GP |
| video/3GPP2 | Sì | Sì | No | Sì | No | .3G2;. 3gp2 |
| video/QuickTime | Sì | Sì | No | Sì | No | . Moov;. MOV;. QT |
| video/x-M4V | Sì | Sì | No | Sì | No | . m4v |
||||||||

## <a name="database"></a>Database

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/x-Msaccess | Sì | Sì | Sì | No | No | . mdb |
||||||||

## <a name="email"></a>Posta elettronica

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. MS-Outlook | Sì | Sì | Sì | Sì | Sì | . msg |
| messaggio/RFC822 | Sì | Sì | Sì | Sì | Sì | .eml |
| Text/vCard-contatti | Sì | Sì | Sì | Sì | Sì | . vcf |
||||||||

## <a name="email-container"></a>Contenitore di posta elettronica

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del contenitore | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |
| applicazione/mbox | Sì | Sì | Sì | . mbox |
| Application/vnd. MS-Outlook-PST | Sì | Sì | Sì | file con estensione pst |
||||||||

## <a name="html"></a>HTML

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| applicazione/XHTML + XML | Sì | Sì | Sì | Sì | Sì | . XHTML |
| applicazione/XML | Sì | Sì | Sì | Sì | Sì | . XML |
| testo/HTML | Sì | Sì | Sì | Sì | Sì | . htm;. html;. shtml |
||||||||

## <a name="image"></a>Immagine

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo OCR | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| immagine/BMP | Sì | Sì | Sì | Sì | Sì | . bmp |
| immagine/EMF | Sì | Sì | Sì | Sì | Sì | EMF |
| immagine/gif | Sì | Sì | Sì | Sì | Sì | . gif |
| immagine/JPEG | Sì | Sì | Sì | Sì | Sì | . jpeg;. jpg |
| immagine/png | Sì | Sì | Sì | Sì | Sì | . png |
| Image/svg + xml | Sì | Sì | Sì | Sì | No | . svg |
| immagine/TIFF | Sì | Sì | Sì | Sì | Sì | TIF |
| image/vnd. dwg | Sì | Sì | Sì | Sì | Sì | . dwg;. DXF |
| immagine/WMF | Sì | Sì | Sì | Sì | Sì | . wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. MS-Excel | Sì | Sì | Sì | Sì | Sì | . dat;. xls |
| Application/vnd. MS-Excel. Sheet. Binary. macroenabled. 12 | Sì | Sì | Sì | Sì | No | . xlsb |
| Application/vnd. MS-Excel. Sheet. macroenabled. 12 | Sì | Sì | Sì | Sì | Sì | . xlsm |
| Application/vnd. MS-Excel. template. macroenabled. 12 | Sì | Sì | Sì | No | No | . xltm |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. Sheet | Sì | Sì | Sì | Sì | Sì | XLSX |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. template | Sì | Sì | Sì | Sì | Sì | . xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| applicazione/OneNote | Sì | Sì | Sì | Sì | No | . One |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. MS-PowerPoint | Sì | Sì | Sì | Sì | Sì | . pot;. PPS;. ppt |
| Application/vnd. openxmlformats-officedocument. PresentationML. Presentation | Sì | Sì | Sì | Sì | Sì | .pptx |
| Application/vnd. openxmlformats-officedocument. PresentationML. slideshow | Sì | Sì | Sì | Sì | Sì | . ppsx |
| Application/vnd. openxmlformats-officedocument. PresentationML. template | Sì | Sì | Sì | Sì | Sì | . potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. MS-Project | Sì | Sì | Sì | No | Sì | . mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/x-MSPublisher | Sì | Sì | Sì | Sì | Sì | . pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. ms-Visio. Drawing | Sì | Sì | Sì | Sì | No |  |
| applicazione/VND. Visio | Sì | Sì | Sì | Sì | Sì | . vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| applicazione/MSWord | Sì | Sì | Sì | Sì | Sì | . dat;. doc |
| applicazione/RTF | Sì | Sì | Sì | Sì | Sì | . doc;. RTF |
| Application/vnd. MS-Word. Document. macroenabled. 12 | Sì | Sì | Sì | Sì | Sì | .docm |
| Application/vnd. MS-Word. template. macroenabled. 12 | Sì | Sì | Sì | Sì | Sì | . dotm |
| Application/vnd. openxmlformats-officedocument. WordprocessingML. Document | Sì | Sì | Sì | Sì | Sì | . docx |
| Application/vnd. openxmlformats-officedocument. WordprocessingML. template | Sì | Sì | Sì | Sì | Sì | . dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. MS-Works-SS | Sì | Sì | No | No | No | . WPS |
| Application/vnd. MS-Works-WP | Sì | Sì | No | No | No | . WPS |
||||||||

## <a name="open-document-format"></a>Formato di documento aperto

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. Oasis. OpenDocument. Text | Sì | Sì | Sì | Sì | Sì | . odt |
||||||||

## <a name="other"></a>Altro

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| applicazione/JSON | Sì | Sì | Sì | Sì | Sì | n/d |
| Application/vnd. MS-Graph | Sì | Sì | No | No | No |  |
| applicazione/Winhlp | Sì | Sì | No | No | No | . hlp |
| applicazione/x-TNEF | Sì | Sì | No | No | No |  |
||||||||

## <a name="plain-text"></a>Testo normale

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| testo/CSV | Sì | Sì | Sì | Sì | Sì | . csv |
| testo/normale | Sì | Sì | Sì | Sì | Sì | . con;. CSS;. csv;. dat;. pl;. txt |
||||||||

## <a name="portable-document-format"></a>PDF (Portable Document Format)

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| applicazione/PDF | Sì | Sì | Sì | Sì | Sì | .pdf |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. WordPerfect; Version = 5.0 | Sì | Sì | Sì | No | No | . WPD |
| Application/vnd. WordPerfect; Version = 5.1 | Sì | Sì | Sì | No | No | . WPD |
| Application/vnd. WordPerfect; Version = 6. x | Sì | Sì | Sì | No | No | . WPD |
||||||||

## <a name="word-pro"></a>Word Pro

| Tipo MIME | Identificazione file | Estrazione dei metadati | Estrazione del testo | Visualizzatore nativo | Visualizzatore annotazioni | Estensioni possibili |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. Lotus-WordPro | Sì | Sì | No | No | No | . LWP |
||||||||
