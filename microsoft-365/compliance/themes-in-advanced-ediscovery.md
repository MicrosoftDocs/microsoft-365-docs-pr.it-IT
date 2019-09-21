---
title: Temi
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084750"
---
# <a name="themes"></a>Temi
In che modo una persona scrive un documento? In genere iniziano con una o più idee che vogliono trasmettere nel documento e compongono l'utilizzo di parole che si allineano con le idee. Più è prevalente un'idea, più le parole che sono correlate a quell'idea tendono ad essere. In questo modo viene spiegato come gli utenti utilizzano i documenti. la cosa importante da leggere è la lettura di un documento e le idee che il documento sta cercando di trasmettere e quali idee vengono visualizzate e quali sono le relazioni tra le idee.

Questo può essere esteso a come una persona desidera utilizzare un insieme di documenti. Desiderano vedere quali idee sono presenti nei set e quali documenti si riferiscono a queste idee. Inoltre, se trovano un particolare documento di interesse, vogliono essere in grado di visualizzare i documenti che discutono di idee simili.

Il modulo themes cerca di simulare il modo in cui gli umani ragionano sui documenti, analizzando i "temi" descritti in un set di revisione e assegnando loro i documenti. I temi fanno un ulteriore passo e identifica per documento il "tema dominante"; vale a dire il tema più visualizzato.

## <a name="how-does-themes-work"></a>Modalità di funzionamento dei temi
Themes analizza i documenti con testo in un set di revisione per analizzare i temi comuni che vengono visualizzati tra i documenti. Assegna quindi tali temi ai documenti in cui vengono visualizzati. Le etichette vengono inoltre contrassegnate con le parole utilizzate nei documenti rappresentativi del tema. Poiché un documento può avere più di un argomento, in molti casi a un documento sono assegnati più temi. Il tema più prominente in un documento è designato come tema dominante.