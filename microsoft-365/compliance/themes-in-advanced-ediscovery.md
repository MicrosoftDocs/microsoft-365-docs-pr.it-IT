---
title: Temi - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Utilizzare Temi in Advanced eDiscovery per organizzare i set di revisioni individuando il tema dominante in ogni documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285532"
---
# <a name="themes-in-advanced-ediscovery"></a>Temi in Advanced eDiscovery

In che modo una persona scrive un documento? In genere iniziano con una o più idee che desiderano trasmettere nel documento e compongono usando parole allineate alle idee. Più diffusa è l'idea, più frequenti sono le parole correlate a tale idea. In questo modo viene informato anche il modo in cui gli utenti utilizzano i documenti. La cosa importante da comprendere dalla lettura di un documento è l'idea che il documento sta cercando di trasmettere, quali idee appaiono dove e quali sono le relazioni tra le idee.

Questo può essere esteso al modo in cui una persona vuole usare un set di documenti. Vogliono vedere quali idee sono presenti nei set e quali documenti parlano di tali idee. Inoltre, se trovano un particolare documento di interesse, vogliono essere in grado di visualizzare documenti che discutono di idee simili.

La funzionalità Temi di Advanced eDiscovery tenta di simulare il motivo  dei documenti da parte degli utenti, analizzando i temi descritti in un set di revisioni e assegnando un tema ai documenti nel set di revisioni. In Advanced eDiscovery, Themes fa un ulteriore passo avanti e identifica il *tema dominante* in ogni documento. Il tema dominante è quello visualizzato più spesso in un documento.

## <a name="how-does-themes-work"></a>Come funzionano i temi?

La funzionalità Temi analizza i documenti con testo in un insieme da rivedere per analizzare i temi comuni visualizzati in tutti i documenti dell'insieme da rivedere. Advanced eDiscovery assegna i temi ai documenti in cui sono visualizzati. Ogni tema viene inoltre etichettato con le parole utilizzate nei documenti che ne sono rappresentativi. Poiché un documento può contenere vari tipi di argomenti, Advanced eDiscovery assegna spesso più temi ai documenti. Il tema che compare principalmente in un documento viene designato come tema dominante.
