---
title: Rilevamento quasi duplicato - eDiscovery
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
description: Utilizzare il rilevamento quasi duplicato per raggruppare documenti simili in formato testo durante l'analisi dei dati del caso in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286022"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Rilevamento quasi duplicato in Advanced eDiscovery

È consigliabile esaminare un set di documenti in cui un sottoinsieme è basato sullo stesso modello e ha principalmente lo stesso linguaggio boilerplate, con alcune differenze. Se un revisore è in grado di identificare questo sottoinsieme, esaminarne accuratamente uno ed esaminare le differenze per il resto, non avrebbe perso informazioni univoche, occupando solo una frazione di tempo che li avrebbe portati a leggere tutte le copertine dei documenti da coprire. I gruppi di rilevamento quasi duplicati sono in grado di riunire documenti simili in modo testuale per rendere più efficiente il processo di revisione.

## <a name="how-does-it-work"></a>Come funziona?

Quando viene eseguito il rilevamento quasi duplicato, il sistema analizza ogni documento con testo. Quindi, confronta ogni documento l'uno con l'altro per determinare se la loro similarità è maggiore della soglia impostata. In caso contrario, i documenti vengono raggruppati. Dopo che tutti i documenti sono stati confrontati e raggruppati, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima un pivot e gli altri documenti nello stesso set di duplicati vicini, concentrandosi sulla differenza tra il pivot e il documento in revisione.
