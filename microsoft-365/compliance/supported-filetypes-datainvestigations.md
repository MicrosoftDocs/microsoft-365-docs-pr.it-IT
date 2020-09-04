---
title: Tipi di file supportati in indagini sui dati (anteprima)
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
ms.assetid: ''
description: Tabella che elenca i tipi di file supportati e quali visualizzatori possono essere visualizzati in per le indagini sui dati (Preview).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95af625ece261061d6f797b50a382b1905254326
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357738"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>Tipi di file supportati in indagini sui dati (anteprima)

Le indagini sui dati (Preview) supportano numerosi tipi di file in diversi modi, descritti nella tabella seguente. Questo elenco non è stato completato e verranno aggiunti nuovi tipi di file man mano che si continua il test di convalida. Nella tabella è inoltre indicato se è possibile visualizzare un tipo di file nei visualizzatori disponibili quando si esaminano le prove.

| Tipo MIME | Classe file | Visualizzatore nativo | Visualizzatore di testo | Visualizzatore annotazioni | Estrazione del contenitore | Estensioni |
| :- | :- | :- | :- | :- | :- | :- |
| applicazione/MSWord | Documento | Sì | Sì | Sì | No | . doc;. dat |
| applicazione/PDF | Documento | Sì | Sì | Sì | No | .pdf |
| applicazione/RTF | Documento | Sì | Sì | Sì | No | . RTF;. doc |
| Application/vnd. MS-Excel | Documento | Sì | Sì | Sì | No | . xls;. dat |
| Application/vnd. MS-Excel. Sheet. Binary. macroenabled. 12 | Produttività/formato di documento aperto | Sì | Sì | No | No | . xlsb |
| Application/vnd. MS-Excel. Sheet. macroenabled. 12 | Documento | Sì | Sì | Sì | No | . xlsm |
| Application/vnd. MS-Excel. template. macroenabled. 12 | Produttività/formato di documento aperto | No | Sì | No | No | . xltm |
| Application/vnd. MS-Outlook | Produttività | No | No | No | No | . msg |
| Application/vnd. MS-Outlook-PST | Produttività/collaborazione | No | No | No | Sì | file con estensione pst |
| Application/vnd. MS-PowerPoint | Documento | Sì | Sì | Sì | No | . ppt,. PPS;. POT |
| applicazione/vnd.ms-word.document. macroenabled. 12 | Documento | Sì | Sì | Sì | No | .docm |
| Application/vnd. MS-Word. template. macroenabled. 12 | Documento | Sì | Sì | Sì | No | . dotm |
| Application/vnd. Oasis. OpenDocument. Text | Documento | Sì | Sì | Sì | No | ODT  |
| Application/vnd. openxmlformats-officedocument. PresentationML. Presentation | Documento | Sì | Sì | Sì | No | .pptx |
| Application/vnd. openxmlformats-officedocument. PresentationML. slideshow | Produttività/formato di documento aperto | Sì | Sì | Sì | No | . ppsx |
| Application/vnd. openxmlformats-officedocument. PresentationML. template | Documento | Sì | Sì | Sì | No | . potx |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. Sheet | Documento | Sì | Sì | Sì | No | XLSX |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. template | Documento | Sì | Sì | Sì | No | . xltx |
| applicazione/vnd.openxmlformats-officedocument.wordprocessingml.document | Documento | Sì | Sì | Sì | No | . docx |
| Application/vnd. openxmlformats-officedocument. WordprocessingML. template | Documento | Sì | Sì | Sì | No | . dotx |
| applicazione/VND. Visio | Documento | Sì | Sì | Sì | No | . vsd |
| applicazione/x-7z-compresso | Archivio/contenitore | No | No | No | Sì | .7z |
| applicazione/XHTML + XML | Documento | Sì | Sì | Sì | No | . XHTML |
| applicazione/XML | Documento | Sì | Sì | Sì | No | . XML |
| Application/x-Msaccess | Documento | Sì | Sì | Sì | No | . mdb |
| Application/x-MSPublisher | Documento | Sì | Sì | Sì | No | . pub |
| applicazione/x-rar-compresso | Archivio/contenitore | No | No | No | Sì | . rar |
| applicazione/zip | Archivio/contenitore | No | No | No | Sì | .zip |
| immagine/BMP | Immagine | Sì | Sì | Sì | No | . bmp |
| immagine/EMF | Immagine | Sì | Sì | Sì | No | EMF |
| immagine/gif | Documento | Sì | Sì | Sì | No | . gif |
| immagine/JPEG | Immagine | Sì | Sì | Sì | No | . jpg;. jpeg;. dat;. jpgt |
| immagine/png | Immagine | Sì | Sì | Sì | No | . png |
| immagine/TIFF | Immagine | Sì | Sì | Sì | No | TIF |
| image/vnd. dwg | Documento | Sì | Sì | Sì | No | . dwg;. DXF |
| immagine/WMF | Documento | Sì | Sì | Sì | No | . wmf |
| messaggio/RFC822 | Produttività/collaborazione | No | No | No | No | .eml |
| testo/CSV | Documento | Sì | Sì | Sì | No | . csv |
| testo/HTML | Documento | Sì | Sì | Sì | No | . html;. shtml;. htm |
| testo/normale | Documento | Sì | Sì | Sì | No | . txt;. CSS;. con;. pl;. csv;. dat |
| Text/vCard-contatti | Documento | Sì | Sì | Sì | No | . vcf |
||||||||
