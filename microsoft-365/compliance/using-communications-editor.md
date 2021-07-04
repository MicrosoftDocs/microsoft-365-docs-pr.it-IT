---
title: Usare l'editor delle comunicazioni
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
description: Utilizzare l'Editor comunicazioni per modificare le variabili di campo di testo e unione durante la formattazione del contenuto.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 26076ff82ba226c2993c7c40e36bca2e08cbf683
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288120"
---
# <a name="use-the-communications-editor"></a>Usare l'editor delle comunicazioni

Quando si definisce il contenuto del portale, le notifiche di blocco legale e i promemoria/escalation correlati, è possibile utilizzare l'Editor comunicazioni per formattare e personalizzare dinamicamente il contenuto.

## <a name="rich-text-editor"></a>Editor di testo RTF

L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor. Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare contenuto e altro ancora.

## <a name="merge-field-variables"></a>Variabili di campo unione

È possibile utilizzare le variabili di stampa unione dall'Editor comunicazioni per incorporare attributi di custodia personalizzati nel corpo del testo di una comunicazione. Quando viene inviato al responsabile, il campo unione verrà popolato con il campo corrispondente. Ad esempio, quando viene inviato al responsabile John Smith, il campo unione [Nome depositario] viene convertito con il nome corrispondente.

È possibile utilizzare i campi di stampa unione selezionando le **icone dei** campi unione nella parte superiore del controllo editor di testo RTF. Il segnaposto verrà aggiunto in base alla posizione del cursore degli utenti.

### <a name="list-of-merge-field-variables"></a>Elenco di variabili di campo unione

<br>

****

|Nome del campo|Dettagli campo|
|---|---|
|Nome visualizzato|Nome e cognome del responsabile.|
|Collegamento di riconoscimento|Un collegamento personalizzato per registrare il riconoscimento di ogni responsabile.|
|Collegamento portale|Collegamento personalizzato per il portale di conformità del responsabile.|
|Responsabile dell'emissione|L'indirizzo di posta elettronica del responsabile del rilascio specificato.|
|Data di emissione|Data di emissione dell'avviso (UTC).|
|
