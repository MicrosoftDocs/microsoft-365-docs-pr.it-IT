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
description: Utilizzare il rilevamento quasi duplicato per raggruppare documenti testualmente simili durante l'analisi dei dati del caso in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286022"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Rilevamento quasi duplicato in Advanced eDiscovery

Considerare un set di documenti da rivedere in cui un sottoinsieme è basato sullo stesso modello e ha principalmente lo stesso linguaggio boilerplate, con alcune differenze qua e là. Se un revisore è in grado di identificare questo sottoinsieme, esaminarne uno a fondo ed esaminare le differenze per il resto, non avrebbe perso alcuna informazione univoca, pur occupando solo una frazione di tempo che li avrebbe portati a leggere tutti i documenti a copertura. Il rilevamento di documenti simili raggruppa documenti con similarità testuali per contribuire a rendere più efficiente il processo di revisione.

## <a name="how-does-it-work"></a>Come funziona?

Quando viene eseguito il rilevamento di documenti simili, il sistema analizza ogni documento con testo. Confronta quindi ogni documento con gli altri per determinare se la similarità è maggiore della soglia impostata. Se è questo il caso, i documenti vengono raggruppati. Dopo aver confrontato e raggruppato tutti i documenti, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima il pivot e dopo gli altri documenti dello stesso insieme, concentrandosi sulla differenza tra il pivot e il documento in revisione.
