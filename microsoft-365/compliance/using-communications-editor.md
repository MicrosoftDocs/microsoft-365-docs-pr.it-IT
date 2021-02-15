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
description: Utilizzare l'Editor comunicazioni per modificare il testo e le variabili dei campi unione durante la formattazione del contenuto.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769161"
---
# <a name="use-the-communications-editor"></a>Usare l'editor delle comunicazioni

Quando si definiscono il contenuto del portale, le notifiche di blocco a livello legale e i promemoria/escalation correlati, è possibile utilizzare Communications Editor per formattare e personalizzare dinamicamente il contenuto.

## <a name="rich-text-editor"></a>Editor di testo RTF

L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor. Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare il contenuto e altro ancora.

## <a name="merge-field-variables"></a>Variabili di campo unione

È possibile utilizzare le variabili di stampa unione dall'editor di comunicazioni per incorporare attributi di responsabile personalizzati nel corpo del testo di una comunicazione. Quando viene inviato al responsabile, il campo unione verrà popolato con il campo corrispondente. Ad esempio, quando viene inviato al responsabile John Smith, il campo unione [Nome del responsabile] viene convertito con il nome corrispondente.

È possibile utilizzare i campi di stampa unione selezionando le icone **dei** campi unione nella parte superiore del controllo editor rtf. Il segnaposto verrà aggiunto in base alla posizione del cursore dell'utente.

### <a name="list-of-merge-field-variables"></a>Elenco di variabili di campo unione

| Nome del campo                  | Dettagli campo |
| :------------------- | :------------------- |
| Nome visualizzato  | Nome e cognome del responsabile. | 
| Collegamento riconoscimento | Un collegamento personalizzato per registrare il riconoscimento di ogni responsabile.|                 |
| Collegamento al portale     | Collegamento personalizzato per il portale di conformità del responsabile.|                |
| Responsabile del rilascio                   | L'indirizzo di posta elettronica del responsabile emittente specificato.|                   |
| Data di emissione                   | Data di emissione dell'avviso (UTC).              |
|||
