---
title: Rilevamento di documenti simili
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
description: ''
ms.openlocfilehash: 8162cae8b69d420ffe87eda137be02688da778b0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602723"
---
# <a name="near-duplicate-detection"></a>Rilevamento di documenti simili

Si consideri un insieme di documenti da rivedere in cui un sottoinsieme si basa sullo stesso modello e ha per lo più lo stesso linguaggio standard, con poche differenze qua e là. Se un revisore è in grado di identificare questo sottoinsieme, esaminare uno di essi accuratamente ed esaminare le differenze per il resto, non avrebbero perso le informazioni univoche tenendo solo una frazione di tempo che li avrebbe necessari per leggere tutti i documenti da coprire. Nei pressi dei gruppi di rilevamento duplicati, i documenti simili insieme consentono di rendere più efficiente il processo di revisione.

## <a name="how-does-it-work"></a>Come funziona

Quando viene eseguito il rilevamento duplicato, il sistema analizza tutti i documenti con testo. Viene quindi confrontato ogni documento uno rispetto all'altro per determinare se la loro somiglianza è maggiore rispetto alla soglia impostata. In questo caso, i documenti vengono raggruppati. Una volta che tutti i documenti sono stati confrontati e raggruppati, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima un pivot ed esaminare gli altri documenti nello stesso set di duplicati vicino, concentrandosi sulla differenza tra il pivot e il documento in esame.