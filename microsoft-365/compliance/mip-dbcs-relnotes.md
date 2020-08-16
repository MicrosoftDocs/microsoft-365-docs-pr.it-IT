---
title: Note sulla versione del supporto Conformità Microsoft 365 per i set di caratteri a due byte (anteprima)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Note sulla versione del supporto per i set di caratteri a due byte.
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695257"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Note sulla versione del supporto per i set di caratteri a due byte (anteprima)

 Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte nelle lingue seguenti:

- Cinese (semplificato)
- Cinese (tradizionale)
- Coreano
- Giapponese

La versione di anteprima è disponibile solo nel cloud commerciale e l'implementazione è limitata ai paesi o aree geografiche seguenti:

- Giappone
- Corea del Sud
- Cina
- RAS di Hong Kong
- RAS di Macao
- Taiwan

Il supporto è disponibile per i tipi di informazioni sensibili e i dizionari di parole chiave e riguarda le soluzioni di prevenzione della perdita dei dati, conformità alle comunicazioni, Exchange Online, SharePoint Online, OneDrive for Business e Teams.

## <a name="known-issues"></a>Problemi noti

- Se un file di testo allegato a un messaggio di posta elettronica è in formato UTF-8 senza BOM (Byte Order Mark), il messaggio non viene rilevato dai criteri di conformità delle comunicazioni.

- I criteri di conformità delle comunicazioni non rilevano valori se viene immessa una frase per la condizione del criterio: “Il messaggio contiene una di queste parole”. Se il testo specificato nel criterio è una parola, è possibile individuarla, ma se si trova in mezzo a una frase, non verrà rilevata.

- I criteri di conformità delle comunicazioni che descrivono i dizionari come informazioni tipo non rilevano le chat private e le chat di canale di Teams.

- Le condizioni seguenti non sono supportate dalla conformità delle comunicazioni in questa fase (prevediamo di risolvere questi problemi in futuro): 
  - “Il messaggio contiene alcune di queste parole”
  - “Il messaggio non contiene alcuna di queste parole”
  - “L'allegato contiene alcune di queste parole”
  - “L'allegato contiene alcune di queste parole”

In alternativa, è consigliabile creare un SIT (Sensitive Information Type) personalizzato con un dizionario di parole chiave che rileva i criteri nei messaggi e gli allegati e l’uso di tale tipo di contenuto personalizzato come condizione per la conformità alle comunicazioni.
